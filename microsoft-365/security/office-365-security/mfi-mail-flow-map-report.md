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
description: Beheerders kunnen leren hoe u de e-mail stroom plattegrond kunt gebruiken in het dashboard voor e-mail stroom in het beveiligings & nalevings centrum voor het visualiseren en bijhouden van de manier waarop e-mail stromen van en naar hun organisatie via connectors en zonder connectors worden gebruikt.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c07730f3abcec8905285cdfdf1579ffb71573ec1
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029916"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>De kaart voor de e-mail stroom in het Beveiligingscentrum beveiligings &

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


De **e-mail stroom kaart** in het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in het [Beveiligingscentrum beveiligings &](https://protection.office.com) biedt inzicht in de manier waarop e-mail stromen via uw organisatie worden doorgevoerd. U kunt deze gegevens gebruiken om patronen te ontdekken, afwijkingen te identificeren en problemen op te lossen.

![Widget e-mail stroom in het dashboard voor e-mail stroom in de beveiligings & nalevings centrum](../../media/mfi-mail-flow-map-widget.png)

Standaard toont de widget de e-mail stroom patroon van de vorige dag in een grafiek die een *Sankey* -diagram wordt genoemd. U kunt de pijl-links ![ en pijl- ](../../media/scc-left-arrow.png) rechts gebruiken ![ ](../../media/scc-right-arrow.png) om informatie uit verschillende dagen weer te geven. Elke andere kleur vertegenwoordigt een e-mail stroom via een andere binnenkomende of uitgaande connector (of zonder connectors). Als u de muisaanwijzer boven een bepaalde kleur houdt, wordt het aantal berichten weergegeven voor dat type verbindingslijn.

## <a name="report-view-for-the-mail-flow-map"></a>Rapportweergave voor de e-mail stroom kaart

Als u op de widget **e-mail stroom kaart** klikt, gaat u naar het rapport met de **e-mail stroom kaart** .

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Gegevens weergeven voor: overzicht**: dit is een grotere weergave van de widget. Als u de muisaanwijzer boven een bepaalde kleur houdt, wordt het aantal berichten weergegeven voor dat type verbindingslijn.

  ![Overzichtsweergave in het rapport e-mail stroom kaart](../../media/mfi-mail-flow-map-report-overview.png)

- **Gegevens weergeven voor: detail**: in deze weergave worden details weergegeven over de connectors en doeldomeinen. De meeste e-mailadressen van de afzender en de ontvanger worden weergegeven en de rest wordt in **andere** gebieden meegenomen. Als u de muisaanwijzer boven een bepaalde kleur en sectie houdt, wordt het aantal berichten weergegeven.

  ![De weergave Details in het rapport van de e-mail stroom](../../media/mfi-mail-flow-map-report-detail.png)

Als u op **filters** in een rapportweergave klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.

Als u het rapport voor een specifiek datumbereik naar een of meer geadresseerden wilt verzenden, klikt u op **Download aanvragen**.

Gerelateerde inzichten worden weergegeven onder de weergave voor de e-mail stroom, als deze beschikbaar zijn (bijvoorbeeld de oplossing voor de [oplossing potentiële e-mail](mfi-mail-loop-insight.md)).

## <a name="details-table-view-for-the-mail-flow-map"></a>De tabel weergave Details voor de e-mail stroom kaart

Als u in een rapportweergave op **Details tabel weergeven** klikt, wordt de volgende informatie weergegeven:

- **Datum**
- **Categorie**
- **Service provider van connector/derden**
- **Domein afzender/ontvanger**
- **Aantal berichten**

Als u in een weergave met detail tabellen op **filters** klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.

Als u een rij selecteert, worden dezelfde gegevens weergegeven in een flyout:

![Flyout Details van de tabel Details in de toegewezen berichtenstroom](../../media/mfi-mail-flow-map-view-details-table-details.png)

Als u het rapport voor een specifiek datumbereik naar een of meer geadresseerden wilt verzenden, klikt u op **Download aanvragen**.

Als u terug wilt gaan naar de weergave rapporten, klikt u op **rapport weergeven**.

## <a name="see-also"></a>Zie ook

Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).
