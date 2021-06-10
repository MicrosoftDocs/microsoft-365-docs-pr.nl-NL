---
title: Niet-geaccepteerd domeinrapport in het e-mailstroomdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe ze het niet-geaccepteerde domeinrapport kunnen gebruiken in het e-mailstroomdashboard in het beveiligings- & compliancecentrum om berichten te controleren vanuit uw on-premises organisatie waar het domein van de afzender niet is geconfigureerd in Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fb33feb56bf2b52731c03273ce0c6444c333f348
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204553"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Niet-geaccepteerd domeinrapport in het beveiligings- & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In het rapport **Niet-geaccepteerd** domein in het [e-mailstroomdashboard](mail-flow-insights-v2.md) in het [beveiligings- & compliancecentrum](https://protection.office.com) wordt informatie weergegeven over berichten van uw on-premises e-mailorganisatie waarin het domein van de afzender niet is geconfigureerd als een geaccepteerd domein in uw Microsoft 365 organisatie.

Microsoft 365 kunnen deze berichten in de weg staan als we gegevens hebben om aan te tonen dat de bedoeling van deze berichten schadelijk is. Daarom is het belangrijk dat u begrijpt wat er gebeurt en dat u het probleem kunt oplossen.

![Niet-geaccepteerde domeinwidget in het e-mailstroomdashboard in & Beveiligingscentrum](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Rapportweergave voor het rapport Niet-geaccepteerde domein

Als u op de grafiek klikt in de **niet-geaccepteerde** domeinwidget, gaat u naar het **rapport Niet-geaccepteerde** domein.

Standaard wordt de activiteit voor alle betrokken verbindingslijnen weergegeven. Als u op **Gegevens voor tonen klikt,** kunt u een specifieke verbindingslijn selecteren in de vervolgkeuzepagina.

Als u de muisaanwijzer boven een gegevenspunt (dag) in de grafiek beweegt, ziet u het totale aantal berichten voor de verbindingslijn.

![Rapportweergave in het rapport Niet-geaccepteerd domein](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Tabelweergave details voor het rapport Niet-geaccepteerd domein

Als u in **een rapportweergave op Detailstabel** weergeven klikt, worden de volgende gegevens weergegeven:

- **Datum**
- **Naam van inkomende verbindingslijn**
- **Afzenderdomein**
- **Aantal berichten**
- **Voorbeeldberichten:** de bericht-eds van een voorbeeld van de betreffende berichten.

Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**

Als u het rapport voor een bepaald datumbereik wilt e-mailen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**

Wanneer u een rij in de tabel selecteert, wordt een flyout weergegeven met de volgende informatie:

- **Datum**
- **Naam van inkomende verbindingslijn**
- **Afzenderdomein**
- **Aantal berichten**
- **Voorbeeldberichten:** U kunt op **Voorbeeldberichten weergeven klikken** om de resultaten van bericht trace te bekijken voor een voorbeeld van de betreffende berichten. [](message-trace-scc.md)

![Details flyout after selecting a row in Details table view in the Non-accepted domain report](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**

## <a name="related-topics"></a>Verwante onderwerpen

Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)
