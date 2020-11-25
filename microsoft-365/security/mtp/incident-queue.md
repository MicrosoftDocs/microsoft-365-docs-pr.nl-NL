---
title: Incidenten prioriteren in Microsoft 365 Defender
description: Meer informatie over het filteren van incidenten in de wachtrij incident in Microsoft 365 Defender
keywords: incident, wachtrij, overzicht, apparaten, identiteiten, gebruikers, postvak, e-mail, incidenten
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: e587004fbb3bc6defab985cea9b427f64b3aab35
ms.sourcegitcommit: a9486f9dc51f0908393000ec3c211e3430c26abd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/25/2020
ms.locfileid: "49409253"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Incidenten prioriteren in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



Met Microsoft 365 Defender past u correlatie analyses toe en voegt u alle gerelateerde waarschuwingen en onderzoek van verschillende producten samen tot één voorval. Microsoft 365 Defender zorgt ook voor unieke meldingen van activiteiten die alleen als schadelijk kunnen worden geïdentificeerd op basis van de end-to-end detectie van de end-to-end-versie van Microsoft 365 voor het hele erfgoed en de productsuite. In deze weergave kunnen uw beveiligings voering de analist van een Hacke aanval bieden zodat ze beter inzicht krijgen in en omgaan met ingewikkelde bedreigingen binnen de organisatie.


In de **wachtrij incidenten** wordt een verzameling incidenten weergegeven die zijn gemarkeerd voor alle apparaten, gebruikers en postvakken. Met deze functie kunt u een weloverwogen Cyber Security-antwoord beslissing stellen en een weloverwogen antwoord beslissing stellen.


![Afbeelding van een wachtrij voor incidenten](../../media/incidents-queue.png) 

Standaard worden in de wachtrij in het Microsoft 365-Beveiligingscentrum de incidenten weergegeven die in de afgelopen 30 dagen zijn weergegeven. Het nieuwste incident staat boven aan de lijst, zodat u het eerst kunt zien.

In de wachtrij voor incidenten worden aanpasbare kolommen getoond die u inzicht geven in verschillende kenmerken van het incident of de opgenomen entiteiten. Dit helpt u bij het maken van een weloverwogen beslissing met betrekking tot de prioriteit van incidenten.

Voor een extra detectie in één oogopslag worden de namen van de incidenten gegenereerd op basis van waarschuwings kenmerken, zoals het aantal desbetreffende eindpunten, gebruikers die worden getroffen, detectie bronnen of categorieën. Zo kunt u snel inzicht krijgen in de reikwijdte van het incident.

Voorbeeld: een *incident van meerdere stappen op meerdere eindpunten, gerapporteerd door meerdere bronnen.*

> [!NOTE]
> Voor incidenten die bestonden vóór de implementatie van de naam van het automatische incident, is de naam niet gewijzigd.

In de wachtrij voor incidenten worden ook meerdere filteropties getoond die u kunt toepassen, zodat u een breed opruimen kunt maken van alle bestaande incidenten in uw omgeving, of als u de focus wilt verplaatsen naar een specifiek scenario of bedreiging. Door filters toe te passen op de incident wachtrij, kunt u bepalen welk incident directe aandacht vereist. 

## <a name="available-filters"></a>Beschikbare filters

### <a name="assigned-to"></a>Toegewezen aan
U kunt ervoor kiezen om waarschuwingen weer te geven die aan u zijn toegewezen of die zijn afgehandeld door automatisering.

### <a name="categories"></a>Categorieën
Kies categorieën om te focussen op specifieke tactiek, technieken of onderdelen van een aanval. 

### <a name="classification"></a>Contactpersoonclassificatie
Filter incidenten op basis van de ingestelde classificaties van de gerelateerde waarschuwingen. De waarden bestaan uit echte waarschuwingen, onjuiste waarschuwingen of niet ingesteld.

### <a name="data-sensitivity"></a>Gegevens gevoeligheid
Sommige aanvallen richten op het bereiken van exfiltrate gevoelige of waardevolle gegevens. Door een filter toe te passen om te zien of de gevoelige gegevens bij het incident passen, kunt u snel vaststellen of gevoelige informatie al mogelijk is aangetast en de prioriteit van die incidenten bepalen.

>[!NOTE]
>Alleen van toepassing als Microsoft-informatiebeveiliging is ingeschakeld.

### <a name="device-group"></a>Apparaten groep
Filteren op gedefinieerde apparaatgroepen.

### <a name="investigation-state"></a>Onderzoek status
Filteren op incidenten met de status van een geautomatiseerd onderzoek. 

### <a name="multiple-categories"></a>Meerdere categorieën 
U kunt ervoor kiezen om alleen aanvragen weer te geven die zijn toegewezen aan meerdere categorieën en daarom mogelijk meer schade kunnen veroorzaken. 

### <a name="multiple-service-sources"></a>Meerdere servicebronnen 
Filteren om alleen incidenten weer te geven die waarschuwingen van verschillende bronnen bevatten (Microsoft Defender for Endpoint, Microsoft Cloud app Security, Microsoft Defender for Identity, Microsoft Defender voor Office 365).

### <a name="os-platform"></a>Platform van OS
De weergave van de incidenten wachtrij beperken met besturingssysteem.

### <a name="service-sources"></a>Service bronnen
Als u een specifieke bron kiest, kunt u zich richten op incidenten met minstens één waarschuwing van de gekozen bron. 

### <a name="severity"></a>Ernst
De ernst van een incident is een indicatie van de invloed die op uw tegoed kan worden beïnvloed. Hoe hoger de ernst, wat groter de gevolgen en is meestal de enige directe aandacht. 

### <a name="status"></a>Status
U kunt ervoor kiezen de lijst te beperken van de namen die worden weergegeven op basis van hun status, zodat u kunt zien welke gebeurtenissen actief zijn of worden opgelost.




## <a name="next-steps"></a>Volgende stappen
Nadat u hebt vastgesteld voor welk incident de hoogste prioriteit is vereist, kunt u doorgaan met het verdere onderzoek verder werken aan een incident.
- [Incidenten onderzoeken](investigate-incidents.md)


## <a name="see-also"></a>Zie ook
- [Overzicht van incidenten](incidents-overview.md)
- [Incidenten onderzoeken](investigate-incidents.md)
- [Incidenten beheren](manage-incidents.md)
