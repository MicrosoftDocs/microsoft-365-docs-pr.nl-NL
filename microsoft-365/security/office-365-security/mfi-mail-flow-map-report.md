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
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="72973-103">De kaart voor de e-mail stroom in het Beveiligingscentrum beveiligings &</span><span class="sxs-lookup"><span data-stu-id="72973-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="72973-104">De **e-mail stroom kaart** in het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in het [Beveiligingscentrum beveiligings &](https://protection.office.com) biedt inzicht in de manier waarop e-mail stromen via uw organisatie worden doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="72973-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="72973-105">U kunt deze gegevens gebruiken om patronen te ontdekken, afwijkingen te identificeren en problemen op te lossen.</span><span class="sxs-lookup"><span data-stu-id="72973-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget e-mail stroom in het dashboard voor e-mail stroom in de beveiligings & nalevings centrum](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="72973-107">Standaard toont de widget de e-mail stroom patroon van de vorige dag in een grafiek die een *Sankey* -diagram wordt genoemd.</span><span class="sxs-lookup"><span data-stu-id="72973-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="72973-108">U kunt de pijl-links ![ en pijl- ](../../media/scc-left-arrow.png) rechts gebruiken ![ ](../../media/scc-right-arrow.png) om informatie uit verschillende dagen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="72973-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="72973-109">Elke andere kleur vertegenwoordigt een e-mail stroom via een andere binnenkomende of uitgaande connector (of zonder connectors).</span><span class="sxs-lookup"><span data-stu-id="72973-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="72973-110">Als u de muisaanwijzer boven een bepaalde kleur houdt, wordt het aantal berichten weergegeven voor dat type verbindingslijn.</span><span class="sxs-lookup"><span data-stu-id="72973-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="72973-111">Rapportweergave voor de e-mail stroom kaart</span><span class="sxs-lookup"><span data-stu-id="72973-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="72973-112">Als u op de widget **e-mail stroom kaart** klikt, gaat u naar het rapport met de **e-mail stroom kaart** .</span><span class="sxs-lookup"><span data-stu-id="72973-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="72973-113">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="72973-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="72973-114">**Gegevens weergeven voor: overzicht**: dit is een grotere weergave van de widget.</span><span class="sxs-lookup"><span data-stu-id="72973-114">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="72973-115">Als u de muisaanwijzer boven een bepaalde kleur houdt, wordt het aantal berichten weergegeven voor dat type verbindingslijn.</span><span class="sxs-lookup"><span data-stu-id="72973-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Overzichtsweergave in het rapport e-mail stroom kaart](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="72973-117">**Gegevens weergeven voor: detail**: in deze weergave worden details weergegeven over de connectors en doeldomeinen.</span><span class="sxs-lookup"><span data-stu-id="72973-117">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="72973-118">De meeste e-mailadressen van de afzender en de ontvanger worden weergegeven en de rest wordt in **andere** gebieden meegenomen.</span><span class="sxs-lookup"><span data-stu-id="72973-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="72973-119">Als u de muisaanwijzer boven een bepaalde kleur en sectie houdt, wordt het aantal berichten weergegeven.</span><span class="sxs-lookup"><span data-stu-id="72973-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![De weergave Details in het rapport van de e-mail stroom](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="72973-121">Als u op **filters** in een rapportweergave klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="72973-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="72973-122">Als u het rapport voor een specifiek datumbereik naar een of meer geadresseerden wilt verzenden, klikt u op **Download aanvragen**.</span><span class="sxs-lookup"><span data-stu-id="72973-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="72973-123">Gerelateerde inzichten worden weergegeven onder de weergave voor de e-mail stroom, als deze beschikbaar zijn (bijvoorbeeld de oplossing voor de [oplossing potentiële e-mail](mfi-mail-loop-insight.md)).</span><span class="sxs-lookup"><span data-stu-id="72973-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="72973-124">De tabel weergave Details voor de e-mail stroom kaart</span><span class="sxs-lookup"><span data-stu-id="72973-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="72973-125">Als u in een rapportweergave op **Details tabel weergeven** klikt, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="72973-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="72973-126">**Datum**</span><span class="sxs-lookup"><span data-stu-id="72973-126">**Date**</span></span>
- <span data-ttu-id="72973-127">**Categorie**</span><span class="sxs-lookup"><span data-stu-id="72973-127">**Category**</span></span>
- <span data-ttu-id="72973-128">**Service provider van connector/derden**</span><span class="sxs-lookup"><span data-stu-id="72973-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="72973-129">**Domein afzender/ontvanger**</span><span class="sxs-lookup"><span data-stu-id="72973-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="72973-130">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="72973-130">**Message count**</span></span>

<span data-ttu-id="72973-131">Als u in een weergave met detail tabellen op **filters** klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="72973-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="72973-132">Als u een rij selecteert, worden dezelfde gegevens weergegeven in een flyout:</span><span class="sxs-lookup"><span data-stu-id="72973-132">If you select a row, similar details are shown in a flyout:</span></span>

![Flyout Details van de tabel Details in de toegewezen berichtenstroom](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="72973-134">Als u het rapport voor een specifiek datumbereik naar een of meer geadresseerden wilt verzenden, klikt u op **Download aanvragen**.</span><span class="sxs-lookup"><span data-stu-id="72973-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="72973-135">Als u terug wilt gaan naar de weergave rapporten, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="72973-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="72973-136">Zie ook</span><span class="sxs-lookup"><span data-stu-id="72973-136">See also</span></span>

<span data-ttu-id="72973-137">Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="72973-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
