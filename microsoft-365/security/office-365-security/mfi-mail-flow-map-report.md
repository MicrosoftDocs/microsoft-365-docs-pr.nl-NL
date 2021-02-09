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
description: Beheerders kunnen in het beveiligings &- en compliancecentrum voor e-mailstromen in het beveiligings- en compliancecentrum leren hoe ze de e-mailstroomkaart in het dashboard E-mailstroom gebruiken om te visualiseren en bij te houden hoe e-mail van en naar hun organisatie loopt via connectors en zonder het gebruik van connectors.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 87a5780bd2485ba6ad3b295c09a30a4d7fc34277
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150558"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>E-mailstroomkaart in het & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender voor Office 365-abonnement 1 en abonnement 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

De **e-mailstroomkaart** in het [dashboard E-mailstroom](mail-flow-insights-v2.md) in het & [compliancecentrum](https://protection.office.com) geeft inzicht in hoe e-mail door uw organisatie loopt. U kunt deze informatie gebruiken om patronen te leren, problemen te identificeren en problemen op te lossen terwijl deze zich voordoen.

![Widget E-mailstroomkaart in het dashboard E-mailstroom in het & Compliancecentrum](../../media/mfi-mail-flow-map-widget.png)

De widget toont standaard het patroon van de e-mailstroom van de vorige dag in een grafiek die bekend staat als een *Sankey-diagram.* U kunt de pijl-links en pijl-rechts gebruiken om ![ informatie van verschillende dagen weer te ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) geven. Elke kleur geeft de e-mailstroom over een andere binnenkomende of uitgaande verbindingslijn aan (of zonder verbindingslijnen te gebruiken). Als u de muisaanwijzer op een bepaalde kleur beweegt, wordt het aantal berichten voor dat type verbindingslijn weergegeven.

## <a name="report-view-for-the-mail-flow-map"></a>Rapportweergave voor de e-mailstroomkaart

Als u op de widget **E-mailstroomkaart** klikt, gaat u naar het rapport **E-mailstroomkaart.**

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Gegevens weergeven voor: Overzicht:** dit is in feite een grotere weergave van de widget. Als u de muisaanwijzer op een bepaalde kleur beweegt, wordt het aantal berichten voor dat type verbindingslijn weergegeven.

  ![Overzichtsweergave in het rapport E-mailstroomoverzicht](../../media/mfi-mail-flow-map-report-overview.png)

- **Gegevens weergeven voor: Details:** deze weergave bevat details over de connectors en doeldomeinen. De domeinen van de belangrijkste afzender en geadresseerde worden weergegeven en de rest wordt in Anderen **geplaatst.** Als u de muisaanwijzer over een bepaalde kleur en sectie beweegt, wordt het aantal berichten weergegeven.

  ![Detailweergave in het rapport E-mailstroomkaart](../../media/mfi-mail-flow-map-report-detail.png)

Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**

Als u het rapport voor een bepaald datumbereik per e-mail wilt versturen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**

Gerelateerde inzichten worden onder de E-mailstroomkaart weergegeven als deze beschikbaar zijn (bijvoorbeeld het inzicht in Mogelijke [e-maillus oplossen).](mfi-mail-loop-insight.md)

## <a name="details-table-view-for-the-mail-flow-map"></a>Detailtabelweergave voor de e-mailstroomkaart

Als u in **een rapportweergave op Detailtabel** weergeven klikt, wordt de volgende informatie weergegeven:

- **Datum**
- **Categorie**
- **Connector / Externe serviceprovider**
- **Domein afzender/geadresseerde**
- **Aantal berichten**

Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**

Als u een rij selecteert, worden soortgelijke details weergegeven in een flyout:

![Flyout Details uit de tabel Details in de e-mailstroommap](../../media/mfi-mail-flow-map-view-details-table-details.png)

Als u het rapport voor een bepaald datumbereik per e-mail wilt versturen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**

Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="see-also"></a>Zie ook

Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)
