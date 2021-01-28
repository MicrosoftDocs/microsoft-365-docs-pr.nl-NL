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
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="30285-103">Rapport over niet-uitgevoerde bezorging van de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="30285-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="30285-104">Het **rapport over niet-** uitgevoerde bezorging van het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in het [Beveiligingscentrum van beveiligings &](https://protection.office.com) bevat de belangrijkste foutcodes in rapporten over niet-uitgevoerde bezorging (ook wel ndr's genoemd) voor gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="30285-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="30285-105">Dit rapport toont de details van Ndr's, zodat u problemen met de bezorging van e-mail kunt oplossen.</span><span class="sxs-lookup"><span data-stu-id="30285-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Widget rapport over niet-uitgevoerde bezorging in het dashboard voor e-mail stroom in de beveiligings & nalevings centrum](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="30285-107">Rapportweergave voor het rapport over niet-uitgevoerde bezorging</span><span class="sxs-lookup"><span data-stu-id="30285-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="30285-108">Door te klikken op de widget **niet-bezorgingsrapport** gaat u naar het **rapport niet-** uitgevoerde bezorging.</span><span class="sxs-lookup"><span data-stu-id="30285-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="30285-109">Standaard wordt de activiteit voor alle foutcodes weergegeven.</span><span class="sxs-lookup"><span data-stu-id="30285-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="30285-110">Als u op **gegevens weergeven** klikt, kunt u een specifieke foutcode selecteren in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="30285-110">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="30285-111">Als u een bepaalde kleur (foutcode) op een specifieke dag van de grafiek aanwijst, ziet u het totale aantal berichten voor de fout.</span><span class="sxs-lookup"><span data-stu-id="30285-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Rapportweergave in het niet-geaccepteerde domein rapport](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="30285-113">De tabel weergave Details voor het rapport over niet-uitgevoerde bezorging</span><span class="sxs-lookup"><span data-stu-id="30285-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="30285-114">Als u in een rapportweergave op **Details tabel weergeven** klikt, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="30285-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="30285-115">**Datum**</span><span class="sxs-lookup"><span data-stu-id="30285-115">**Date**</span></span>
- <span data-ttu-id="30285-116">**Rapportcode niet-uitgevoerde bezorging**</span><span class="sxs-lookup"><span data-stu-id="30285-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="30285-117">**Getal**</span><span class="sxs-lookup"><span data-stu-id="30285-117">**Count**</span></span>
- <span data-ttu-id="30285-118">**Voorbeeldberichten**: de bericht-id's van een voorbeeld van de betreffende berichten.</span><span class="sxs-lookup"><span data-stu-id="30285-118">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="30285-119">Als u in een weergave met detail tabellen op **filters** klikt, kunt u een datumbereik opgeven met de **begindatum** en **einddatum**.</span><span class="sxs-lookup"><span data-stu-id="30285-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="30285-120">Als u het rapport voor een specifiek datumbereik naar een of meer geadresseerden wilt verzenden, klikt u op **Download aanvragen**.</span><span class="sxs-lookup"><span data-stu-id="30285-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="30285-121">Wanneer u een rij in de tabel selecteert, wordt een flyout met de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="30285-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="30285-122">**Datum**</span><span class="sxs-lookup"><span data-stu-id="30285-122">**Date**</span></span>
- <span data-ttu-id="30285-123">**Rapportcode voor niet-** uitgevoerde bezorging: u kunt op de link klikken voor meer informatie over de oorzaken en oplossingen voor de specifieke foutcode.</span><span class="sxs-lookup"><span data-stu-id="30285-123">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="30285-124">**Getal**</span><span class="sxs-lookup"><span data-stu-id="30285-124">**Count**</span></span>
- <span data-ttu-id="30285-125">**Voorbeeldberichten**: u kunt op **voorbeeldberichten weergeven** klikken om de resultaten van de [bericht tracering](message-trace-scc.md) te zien voor een voorbeeld van de betreffende berichten.</span><span class="sxs-lookup"><span data-stu-id="30285-125">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Info-flyout na het selecteren van een rij in de tabel Details in het rapport niet-uitgevoerde bezorging](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="30285-127">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="30285-127">Related topics</span></span>

<span data-ttu-id="30285-128">Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="30285-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
