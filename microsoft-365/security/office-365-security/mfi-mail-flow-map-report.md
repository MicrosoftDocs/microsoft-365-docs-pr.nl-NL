---
title: E-mailstroomkaart
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
description: Beheerders kunnen leren hoe ze de e-mailstroommap in het e-mailstroomdashboard in het beveiligings- & compliancecentrum kunnen gebruiken om te visualiseren en bij te houden hoe e-mail van en naar hun organisatie loopt via verbindingslijnen en zonder verbindingslijnen te gebruiken.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e806dde2e6f3ddde5cce3b61c85fe0b024ba2fe
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204930"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>E-mailstroommap in het beveiligings- & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

De **e-mailstroommap** in het [e-mailstroomdashboard](mail-flow-insights-v2.md) in & [Beveiligingscentrum](https://protection.office.com) geeft inzicht in de manier waarop e-mail door uw organisatie loopt. U kunt deze informatie gebruiken om patronen te leren, afwijkingen te identificeren en problemen op te lossen wanneer deze zich voordoen.

![Widget E-mailstroomkaart in het dashboard E-mailstroom in & Compliancecentrum](../../media/mfi-mail-flow-map-widget.png)

Standaard wordt in de widget het e-mailstroompatroon van de vorige dag weergegeven in een grafiek die bekend staat als een *Sankey-diagram.* U kunt de pijl-links en pijl-rechts pijl-rechts ![ gebruiken om informatie van verschillende dagen weer te ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) geven. Elke andere kleur vertegenwoordigt de e-mailstroom over een andere binnenkomende of uitgaande verbindingslijn (of zonder verbindingslijnen). Als u de muisaanwijzer op een bepaalde kleur beweegt, wordt het aantal berichten weergegeven voor dat type verbindingslijn.

## <a name="report-view-for-the-mail-flow-map"></a>Rapportweergave voor de e-mailstroommap

Als u op de widget **E-mailstroomkaart** klikt, gaat u naar het **rapport E-mailstroomkaart.**

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Gegevens weergeven voor: Overzicht:** Dit is in feite een grotere weergave van de widget. Als u de muisaanwijzer op een bepaalde kleur beweegt, wordt het aantal berichten weergegeven voor dat type verbindingslijn.

  ![Overzichtsweergave in het rapport E-mailstroomkaart](../../media/mfi-mail-flow-map-report-overview.png)

- **Gegevens weergeven voor: Detail:** In deze weergave ziet u details over de verbindingslijnen en doeldomeinen. De belangrijkste afzender- en geadresseerdedomeinen worden weergegeven en de rest wordt in Anderen **geplaatst.** Als u de muisaanwijzer boven een bepaalde kleur en sectie beweegt, wordt het aantal berichten weergegeven.

  ![Detailweergave in het rapport E-mailstroomkaart](../../media/mfi-mail-flow-map-report-detail.png)

Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**

Als u het rapport voor een bepaald datumbereik wilt e-mailen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**

Verwante inzichten worden weergegeven onder de e-mailstroomkaart als deze beschikbaar zijn (bijvoorbeeld het inzicht in mogelijke [e-maillus oplossen).](mfi-mail-loop-insight.md)

## <a name="details-table-view-for-the-mail-flow-map"></a>Tabelweergave Details voor de e-mailstroommap

Als u in **een rapportweergave op Detailstabel** weergeven klikt, worden de volgende gegevens weergegeven:

- **Datum**
- **Categorie**
- **Connector / Externe serviceprovider**
- **Domein afzender/geadresseerde**
- **Aantal berichten**

Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**

Als u een rij selecteert, worden soortgelijke details weergegeven in een flyout:

![Details flyout from the details table in the Mail flow map](../../media/mfi-mail-flow-map-view-details-table-details.png)

Als u het rapport voor een bepaald datumbereik wilt e-mailen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**

## <a name="see-also"></a>Zie ook

Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)
