---
title: Rapport over niet-geaccepteerd domein in het dashboard voor de e-mail stroom
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u het niet-geaccepteerde domein rapport gebruikt in het dashboard voor e-mail stromen in de beveiligings & nalevings centrum voor het bewaken van berichten van uw on-premises organisatie waarbij het domein van de afzender niet is geconfigureerd in Microsoft 365.
ms.openlocfilehash: ef5f1c26168347b6696e90292d9c957e63615c0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826939"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="5769b-103">Rapport over niet-geaccepteerd domein in de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="5769b-103">Non-accepted domain report in the Security & Compliance Center</span></span>

<span data-ttu-id="5769b-104">Het **niet-geaccepteerde domein** rapport op het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in de beveiligings & nalevings centrum geeft informatie weer over berichten van de on-premises e-mail organisatie waarbij het domein van de afzender niet is geconfigureerd als een geaccepteerd domein in uw Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="5769b-104">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="5769b-105">In Microsoft 365 kunnen deze berichten worden beperkt als we gegevens hebben om te bewijzen dat de intentie van deze berichten schadelijk is.</span><span class="sxs-lookup"><span data-stu-id="5769b-105">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="5769b-106">Daarom is het belangrijk om te begrijpen wat er gebeurt en om het probleem te verhelpen.</span><span class="sxs-lookup"><span data-stu-id="5769b-106">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Niet-geaccepteerd domein widget in het dashboard voor e-mail stroom in de beveiligings & nalevings centrum](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="5769b-108">Rapportweergave voor het niet-geaccepteerde domein rapport</span><span class="sxs-lookup"><span data-stu-id="5769b-108">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="5769b-109">Door te klikken op het diagram in het **niet-geaccepteerde domein** object, gaat u naar het rapport **niet-geaccepteerd domein** .</span><span class="sxs-lookup"><span data-stu-id="5769b-109">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="5769b-110">Standaard wordt de activiteit voor alle desbetreffende verbindingslijnen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5769b-110">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="5769b-111">Als u op **gegevens weergeven**klikt, kunt u een specifieke verbindingslijn selecteren in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="5769b-111">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="5769b-112">Als u de muisaanwijzer over een gegevenspunt (dag) van de grafiek houdt, ziet u het totale aantal berichten voor de verbindingslijn.</span><span class="sxs-lookup"><span data-stu-id="5769b-112">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Rapportweergave in het niet-geaccepteerde domein rapport](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="5769b-114">De tabel weergave Details voor het niet-geaccepteerde domein rapport</span><span class="sxs-lookup"><span data-stu-id="5769b-114">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="5769b-115">Als u in een rapportweergave op **Details tabel weergeven** klikt, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="5769b-115">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="5769b-116">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="5769b-116">**Date**</span></span>
- <span data-ttu-id="5769b-117">**Naam van inkomende connector**</span><span class="sxs-lookup"><span data-stu-id="5769b-117">**Inbound connector name**</span></span>
- <span data-ttu-id="5769b-118">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="5769b-118">**Sender domain**</span></span>
- <span data-ttu-id="5769b-119">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="5769b-119">**Message count**</span></span>
- <span data-ttu-id="5769b-120">**Voorbeeldberichten**: de bericht-id's van een voorbeeld van de betreffende berichten.</span><span class="sxs-lookup"><span data-stu-id="5769b-120">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="5769b-121">Als u in een weergave met detail tabellen op **filters** klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="5769b-121">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="5769b-122">Als u het rapport voor een specifiek datumbereik naar een of meer geadresseerden wilt verzenden, klikt u op **Download aanvragen**.</span><span class="sxs-lookup"><span data-stu-id="5769b-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="5769b-123">Wanneer u een rij in de tabel selecteert, wordt een flyout met de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="5769b-123">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="5769b-124">**Einddatum**</span><span class="sxs-lookup"><span data-stu-id="5769b-124">**Date**</span></span>
- <span data-ttu-id="5769b-125">**Naam van inkomende connector**</span><span class="sxs-lookup"><span data-stu-id="5769b-125">**Inbound connector name**</span></span>
- <span data-ttu-id="5769b-126">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="5769b-126">**Sender domain**</span></span>
- <span data-ttu-id="5769b-127">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="5769b-127">**Message count**</span></span>
- <span data-ttu-id="5769b-128">**Voorbeeldberichten**: u kunt op **voorbeeldberichten weergeven** klikken om de resultaten van de [bericht tracering](message-trace-scc.md) te zien voor een voorbeeld van de betreffende berichten.</span><span class="sxs-lookup"><span data-stu-id="5769b-128">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Info-flyout na het selecteren van een rij in de weergave Details van een niet-geaccepteerd domein rapport](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="5769b-130">Als u terug wilt gaan naar de weergave rapporten, klikt u op **rapport weergeven**.</span><span class="sxs-lookup"><span data-stu-id="5769b-130">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5769b-131">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="5769b-131">Related topics</span></span>

<span data-ttu-id="5769b-132">Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="5769b-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
