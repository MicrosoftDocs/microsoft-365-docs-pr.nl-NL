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
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057861"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="c6086-103">Rapport niet-bezorging in het beveiligings- & Compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="c6086-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c6086-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="c6086-104">**Applies to**</span></span>
- [<span data-ttu-id="c6086-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c6086-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c6086-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c6086-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c6086-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6086-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c6086-108">Het **rapport Niet-bezorging** in het [e-mailstroomdashboard](mail-flow-insights-v2.md) in het [Compliancecentrum](https://protection.office.com) voor beveiliging & toont de meest voorkomende foutcodes in niet-bezorgingsrapporten (ook wel bekend als NR's of niet-bezorgde berichten) voor gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c6086-108">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="c6086-109">In dit rapport ziet u de details van NR's, zodat u problemen met e-mailbezorging kunt oplossen.</span><span class="sxs-lookup"><span data-stu-id="c6086-109">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Rapportwidget Niet-bezorging in het e-mailstroomdashboard in & Beveiligingscentrum](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="c6086-111">Rapportweergave voor het rapport Niet-bezorging</span><span class="sxs-lookup"><span data-stu-id="c6086-111">Report view for the Non-delivery report</span></span>

<span data-ttu-id="c6086-112">Als u op de widget **Rapport niet-bezorging** klikt, gaat u naar het **rapport Niet-bezorging.**</span><span class="sxs-lookup"><span data-stu-id="c6086-112">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="c6086-113">Standaard wordt de activiteit voor alle foutcodes weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c6086-113">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="c6086-114">Als u op **Gegevens voor tonen klikt,** kunt u een specifieke foutcode selecteren in de vervolgkeuzepagina.</span><span class="sxs-lookup"><span data-stu-id="c6086-114">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="c6086-115">Als u op een bepaalde dag in de grafiek de muisaanwijzer op een bepaalde kleur (foutcode) plaats, ziet u het totale aantal berichten voor de fout.</span><span class="sxs-lookup"><span data-stu-id="c6086-115">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Rapportweergave in het rapport Niet-geaccepteerd domein](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="c6086-117">Tabelweergave details voor het rapport Niet-bezorging</span><span class="sxs-lookup"><span data-stu-id="c6086-117">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="c6086-118">Als u in **een rapportweergave op Detailstabel** weergeven klikt, worden de volgende gegevens weergegeven:</span><span class="sxs-lookup"><span data-stu-id="c6086-118">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="c6086-119">**Datum**</span><span class="sxs-lookup"><span data-stu-id="c6086-119">**Date**</span></span>
- <span data-ttu-id="c6086-120">**Rapportcode voor niet-bezorging**</span><span class="sxs-lookup"><span data-stu-id="c6086-120">**Non-delivery report code**</span></span>
- <span data-ttu-id="c6086-121">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="c6086-121">**Count**</span></span>
- <span data-ttu-id="c6086-122">**Voorbeeldberichten:** de bericht-eds van een voorbeeld van de betreffende berichten.</span><span class="sxs-lookup"><span data-stu-id="c6086-122">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="c6086-123">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="c6086-123">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="c6086-124">Als u het rapport voor een bepaald datumbereik wilt e-mailen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**</span><span class="sxs-lookup"><span data-stu-id="c6086-124">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="c6086-125">Wanneer u een rij in de tabel selecteert, wordt een flyout weergegeven met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="c6086-125">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="c6086-126">**Datum**</span><span class="sxs-lookup"><span data-stu-id="c6086-126">**Date**</span></span>
- <span data-ttu-id="c6086-127">**Rapportcode** voor niet-bezorging: U kunt op de koppeling klikken voor meer informatie over de oorzaken en oplossingen voor de specifieke foutcode.</span><span class="sxs-lookup"><span data-stu-id="c6086-127">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="c6086-128">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="c6086-128">**Count**</span></span>
- <span data-ttu-id="c6086-129">**Voorbeeldberichten:** U kunt op **Voorbeeldberichten weergeven klikken** om de resultaten van bericht trace te bekijken voor een voorbeeld van de betreffende berichten. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="c6086-129">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Details flyout after selecting a row in Details table view in the Non-delivery report](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="c6086-131">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c6086-131">Related topics</span></span>

<span data-ttu-id="c6086-132">Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="c6086-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
