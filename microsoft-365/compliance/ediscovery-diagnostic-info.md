---
title: Diagnostische gegevens voor eDiscovery verzamelen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het verzamelen van diagnostische gegevens voor eDiscovery voor een microsoft-ondersteuningscase.
ms.openlocfilehash: 842f8baf770f178df3298bbfa911de26ce946ed0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162158"
---
# <a name="collect-ediscovery-diagnostic-information"></a>Diagnostische gegevens voor eDiscovery verzamelen

Soms hebben technici van Microsoft Support specifieke informatie over uw probleem nodig wanneer u een ondersteuningscase opent met betrekking tot Core eDiscovery of Advanced eDiscovery. Dit artikel bevat richtlijnen voor het verzamelen van diagnostische gegevens om ondersteuningstechnici te helpen bij het onderzoeken en oplossen van problemen. Meestal hoeft u deze gegevens pas te verzamelen als u daarom wordt gevraagd door een microsoft-ondersteuningstechnicus.

> [!IMPORTANT]
> De uitvoer van de cmdlets en diagnostische informatie die in dit artikel wordt beschreven, kan gevoelige informatie bevatten over rechtszaken of interne onderzoeken in uw organisatie. Voordat u de onbewerkte diagnostische gegevens naar Microsoft Support verstuurt, moet u de informatie controleren en alle gevoelige informatie (zoals namen of andere informatie over partijen bij rechtszaken of onderzoeken) opnieuw uitvoeren door deze te vervangen door `XXXXXXX` . Als u deze methode gebruikt, wordt ook aan de microsoft-ondersteuningstechnicus aangegeven dat de gegevens opnieuw zijn verwerkt.

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>Diagnostische gegevens verzamelen voor Core eDiscovery

Het verzamelen van diagnostische gegevens voor Core eDiscovery is cmdletgebaseerd, dus u moet Beveiligings- & Compliancecentrum PowerShell gebruiken. In de volgende PowerShell-voorbeelden worden cmdlets uitgevoerd en wordt de uitvoer opgeslagen in een opgegeven tekstbestand. In de meeste ondersteuningsgevallen hoeft u slechts één van deze opdrachten uit te voeren.

Als u de volgende cmdlets wilt uitvoeren, maakt u verbinding met [Security & Compliance Center PowerShell </span> ](/powershell/exchange/connect-to-scc-powershell). Nadat u bent verbonden, voert u een of meer van de volgende opdrachten uit en moet u tijdelijke aanduidingen vervangen door de werkelijke objectnamen.

Nadat u het gegenereerde tekstbestand hebt beoordeeld en gevoelige informatie opnieuw hebt gemaakt, stuurt u deze naar de Microsoft Support-engineer die aan uw zaak werkt.

> [!NOTE]
> U kunt ook de opdrachten in deze sectie uitvoeren om diagnostische  gegevens te verzamelen voor de zoekopdrachten en exporten die worden weergegeven op de pagina Inhoud zoeken in het Microsoft 365 compliancecentrum.

### <a name="collect-information-about-searches"></a>Informatie over zoekopdrachten verzamelen

Met de volgende opdracht worden gegevens verzameld die nuttig zijn bij het onderzoeken van problemen met een inhoudszoekactie of een zoekopdracht die is gekoppeld aan een Core eDiscovery-zaak.

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>Gegevens verzamelen over zoekacties

Met de volgende opdracht worden gegevens verzameld om problemen te onderzoeken met het bekijken, exporteren of verwijderen van de resultaten van een inhoudszoekactie of een zoekopdracht die is gekoppeld aan een Core eDiscovery-zaak. U kunt de naam van de zoekactie identificeren door te klikken op een export die wordt weergegeven op het **tabblad** Export. Als u de namen van voorbeeld- en purgeacties wilt identificeren, kunt u de **cmdlet Get-ComplianceSearchAction** uitvoeren om een lijst met alle acties weer te geven. De notatie voor de naam van de zoekactie wordt samengesteld op basis van het gebruik of de `_Preview` `_Export` naam van de `_Purge` bijbehorende zoekopdracht.

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>Gegevens verzamelen over eDiscovery-bezit

Wanneer een eDiscovery-hold die is gekoppeld aan een Core eDiscovery-zaak niet werkt zoals verwacht, voer dan de volgende opdracht uit om informatie te verzamelen over het beleid voor het in de wacht houden van gevallen en de bijbehorende case hold-regel voor de eDiscovery-hold. De *naam van het case hold-beleid* in de volgende opdracht is hetzelfde als de naam van de eDiscovery-hold. U kunt deze naam identificeren op de **tabbladen Holds** in de hoofd-eDiscovery-zaak.

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>Alle case-informatie verzamelen

Soms is het niet duidelijk welke informatie vereist is door Microsoft Support om uw probleem te onderzoeken. In deze situatie kunt u alle diagnostische gegevens verzamelen voor een kern-eDiscovery-zaak. De hoofdnaam van de hoofdzaak *eDiscovery* in de volgende opdracht is hetzelfde als de naam van een zaak die wordt weergegeven op de pagina Core **eDiscovery** in het Microsoft 365 compliancecentrum.

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>Diagnostische gegevens verzamelen voor Advanced eDiscovery

Met **Instellingen** tabblad in een Advanced eDiscovery kunt u snel de diagnostische gegevens voor de zaak kopiëren. De diagnostische gegevens worden opgeslagen op het klembord, zodat u deze in een tekstbestand kunt plakken en naar Microsoft Ondersteuning kunt verzenden.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op Alle > **eDiscovery > Geavanceerd.**

2. Selecteer een zaak en klik vervolgens op **Instellingen** tabblad.

3. Klik **onder Case Information** op **Selecteren.**

4. Klik op de flyoutpagina op **Diagnostische gegevens kopiëren** om de informatie naar het klembord te kopiëren.

5. Open een tekstbestand (in Kladblok) en plak de gegevens in het tekstbestand.

6. Sla het tekstbestand op en noem het een naam `AeD Diagnostic Info YYYY.MM.DD` als `AeD Diagnostic Info 2020.11.03` (bijvoorbeeld).

Nadat u het bestand hebt beoordeeld en gevoelige informatie opnieuw hebt gemaakt, stuurt u deze naar de Microsoft Support-engineer die aan uw zaak werkt.