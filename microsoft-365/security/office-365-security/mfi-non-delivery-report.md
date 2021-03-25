---
title: Rapport Niet-bezorging in het e-mailstroomdashboard
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
description: Beheerders kunnen leren hoe ze het rapport Niet-bezorgingsdetails gebruiken in het e-mailstroomdashboard in het beveiligings- & compliancecentrum om de meest voorkomende foutcodes in niet-bezorgingsrapporten (ook wel bekend als NDR's of niet-bezorgde berichten) van afzenders in uw organisatie te controleren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d25f11051606139c2ee8b88cade18963de599d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204546"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>Rapport niet-bezorging in het beveiligings- & Compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Het **rapport Niet-bezorging** in het [e-mailstroomdashboard](mail-flow-insights-v2.md) in het [Compliancecentrum](https://protection.office.com) voor beveiliging & toont de meest voorkomende foutcodes in niet-bezorgingsrapporten (ook wel bekend als NR's of niet-bezorgde berichten) voor gebruikers in uw organisatie. In dit rapport ziet u de details van NR's, zodat u problemen met e-mailbezorging kunt oplossen.

![Rapportwidget Niet-bezorging in het e-mailstroomdashboard in & Beveiligingscentrum](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>Rapportweergave voor het rapport Niet-bezorging

Als u op de widget **Rapport niet-bezorging** klikt, gaat u naar het **rapport Niet-bezorging.**

Standaard wordt de activiteit voor alle foutcodes weergegeven. Als u op **Gegevens voor tonen klikt,** kunt u een specifieke foutcode selecteren in de vervolgkeuzepagina.

Als u op een bepaalde dag in de grafiek de muisaanwijzer op een bepaalde kleur (foutcode) plaats, ziet u het totale aantal berichten voor de fout.

![Rapportweergave in het rapport Niet-geaccepteerd domein](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>Tabelweergave details voor het rapport Niet-bezorging

Als u in **een rapportweergave op Detailstabel** weergeven klikt, worden de volgende gegevens weergegeven:

- **Datum**
- **Rapportcode voor niet-bezorging**
- **Aantal**
- **Voorbeeldberichten:** de bericht-eds van een voorbeeld van de betreffende berichten.

Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**

Als u het rapport voor een bepaald datumbereik wilt e-mailen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**

Wanneer u een rij in de tabel selecteert, wordt een flyout weergegeven met de volgende informatie:

- **Datum**
- **Rapportcode** voor niet-bezorging: U kunt op de koppeling klikken voor meer informatie over de oorzaken en oplossingen voor de specifieke foutcode.
- **Aantal**
- **Voorbeeldberichten:** U kunt op **Voorbeeldberichten weergeven klikken** om de resultaten van bericht trace te bekijken voor een voorbeeld van de betreffende berichten. [](message-trace-scc.md)

![Details flyout after selecting a row in Details table view in the Non-delivery report](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>Verwante onderwerpen

Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)
