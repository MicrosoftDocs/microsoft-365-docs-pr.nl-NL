---
title: Rapport over niet-uitgevoerde bezorging van het dashboard voor e-mail stroom
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
description: Beheerders kunnen informatie over het gebruik van het rapport over niet-uitgevoerde bezorgings gegevens in het dashboard voor e-mail stroom in de beveiligings & nalevings centrum voor het bewaken van de meest voorkomende foutcodes in rapporten over niet-uitgevoerde bezorging (ook wel Ndr's of stuiteren) van afzenders in uw organisatie.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbd27fc818a46a983874a04f0e313c622e047ea5
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029832"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a>Rapport over niet-uitgevoerde bezorging van de beveiligings & nalevings centrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Het **rapport over niet-** uitgevoerde bezorging van het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in het [Beveiligingscentrum van beveiligings &](https://protection.office.com) bevat de belangrijkste foutcodes in rapporten over niet-uitgevoerde bezorging (ook wel ndr's genoemd) voor gebruikers in uw organisatie. Dit rapport toont de details van Ndr's, zodat u problemen met de bezorging van e-mail kunt oplossen.

![Widget rapport over niet-uitgevoerde bezorging in het dashboard voor e-mail stroom in de beveiligings & nalevings centrum](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a>Rapportweergave voor het rapport over niet-uitgevoerde bezorging

Door te klikken op de widget **niet-bezorgingsrapport** gaat u naar het **rapport niet-** uitgevoerde bezorging.

Standaard wordt de activiteit voor alle foutcodes weergegeven. Als u op **gegevens weergeven** klikt, kunt u een specifieke foutcode selecteren in de vervolgkeuzelijst.

Als u een bepaalde kleur (foutcode) op een specifieke dag van de grafiek aanwijst, ziet u het totale aantal berichten voor de fout.

![Rapportweergave in het niet-geaccepteerde domein rapport](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a>De tabel weergave Details voor het rapport over niet-uitgevoerde bezorging

Als u in een rapportweergave op **Details tabel weergeven** klikt, wordt de volgende informatie weergegeven:

- **Datum**
- **Rapportcode niet-uitgevoerde bezorging**
- **Getal**
- **Voorbeeldberichten**: de bericht-id's van een voorbeeld van de betreffende berichten.

Als u in een weergave met detail tabellen op **filters** klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.

Als u het rapport voor een specifiek datumbereik naar een of meer geadresseerden wilt verzenden, klikt u op **Download aanvragen**.

Wanneer u een rij in de tabel selecteert, wordt een flyout met de volgende informatie weergegeven:

- **Datum**
- **Rapportcode voor niet-** uitgevoerde bezorging: u kunt op de link klikken voor meer informatie over de oorzaken en oplossingen voor de specifieke foutcode.
- **Getal**
- **Voorbeeldberichten**: u kunt op **voorbeeldberichten weergeven** klikken om de resultaten van de [bericht tracering](message-trace-scc.md) te zien voor een voorbeeld van de betreffende berichten.

![Info-flyout na het selecteren van een rij in de tabel Details in het rapport niet-uitgevoerde bezorging](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a>Verwante onderwerpen

Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).
