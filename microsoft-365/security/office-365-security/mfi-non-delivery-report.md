---
title: Rapport over niet-bezorging in het dashboard E-mailstroom
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
description: Beheerders kunnen informatie vinden over het gebruik van het rapport Niet-bezorgingsdetails in het dashboard E-mailstroom in het beveiligings- & Compliancecentrum om de meest voorkomende foutcodes in rapporten over niet-bezorging (ook wel NDR's of niet-bezorgdberichten genoemd) van afzenders in uw organisatie te controleren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e31e7dfcbd3c0cacaa6020464ed315f466a849b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287887"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="d872d-103">Rapport over niet-levering in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="d872d-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d872d-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="d872d-104">**Applies to**</span></span>
- [<span data-ttu-id="d872d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d872d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d872d-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d872d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="d872d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d872d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="d872d-108">Het rapport Niet-bezorging in het [dashboard E-mailstroom](mail-flow-insights-v2.md) in het [beveiligings- &-compliancecentrum](https://protection.office.com) bevat de meest voorkomende foutcodes in rapporten over **niet-bezorging** (ook wel NDR's of niet-bezorgdberichten genoemd) voor gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d872d-108">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="d872d-109">Dit rapport bevat de details van NR's, zodat u problemen met de bezorging van e-mail kunt oplossen.</span><span class="sxs-lookup"><span data-stu-id="d872d-109">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Widget Rapport over niet-bezorging in het dashboard E-mailstroom in het & Compliancecentrum](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="d872d-111">Rapportweergave voor het rapport Niet-bezorging</span><span class="sxs-lookup"><span data-stu-id="d872d-111">Report view for the Non-delivery report</span></span>

<span data-ttu-id="d872d-112">Als u op de widget **Rapport over niet-bezorging** klikt, gaat u naar het rapport **Niet-bezorging.**</span><span class="sxs-lookup"><span data-stu-id="d872d-112">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="d872d-113">Standaard wordt de activiteit voor alle foutcodes weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d872d-113">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="d872d-114">Als u op **Gegevens tonen klikt,** kunt u een specifieke foutcode selecteren in de vervolgkeuzepagina.</span><span class="sxs-lookup"><span data-stu-id="d872d-114">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="d872d-115">Als u op een bepaalde dag in de grafiek de muisaanwijzer over een bepaalde kleur (foutcode) beweegt, ziet u het totale aantal berichten voor de fout.</span><span class="sxs-lookup"><span data-stu-id="d872d-115">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Rapportweergave in het rapport Niet-geaccepteerd domein](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="d872d-117">Tabelweergave Details voor het rapport Niet-bezorging</span><span class="sxs-lookup"><span data-stu-id="d872d-117">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="d872d-118">Als u in **een rapportweergave op Detailtabel** weergeven klikt, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="d872d-118">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="d872d-119">**Datum**</span><span class="sxs-lookup"><span data-stu-id="d872d-119">**Date**</span></span>
- <span data-ttu-id="d872d-120">**Rapportcode voor niet-bezorging**</span><span class="sxs-lookup"><span data-stu-id="d872d-120">**Non-delivery report code**</span></span>
- <span data-ttu-id="d872d-121">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="d872d-121">**Count**</span></span>
- <span data-ttu-id="d872d-122">**Voorbeeldberichten:** de bericht-e-mailberichten van een steekproef van beïnvloede berichten.</span><span class="sxs-lookup"><span data-stu-id="d872d-122">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="d872d-123">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**</span><span class="sxs-lookup"><span data-stu-id="d872d-123">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="d872d-124">Als u het rapport voor een bepaald datumbereik per e-mail wilt versturen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**</span><span class="sxs-lookup"><span data-stu-id="d872d-124">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="d872d-125">Wanneer u een rij in de tabel selecteert, wordt een flyout met de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="d872d-125">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="d872d-126">**Datum**</span><span class="sxs-lookup"><span data-stu-id="d872d-126">**Date**</span></span>
- <span data-ttu-id="d872d-127">**Rapportcode voor niet-bezorging:** klik op de koppeling voor meer informatie over de oorzaken en oplossingen voor de specifieke foutcode.</span><span class="sxs-lookup"><span data-stu-id="d872d-127">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="d872d-128">**Aantal**</span><span class="sxs-lookup"><span data-stu-id="d872d-128">**Count**</span></span>
- <span data-ttu-id="d872d-129">**Voorbeeldberichten:** u kunt op **Voorbeeldberichten weergeven** klikken om de [resultaten](message-trace-scc.md) van bericht traceren voor een voorbeeld van de betreffende berichten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="d872d-129">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Flyout Details na het selecteren van een rij in de tabelweergave Details in het rapport Niet-bezorging](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="d872d-131">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d872d-131">Related topics</span></span>

<span data-ttu-id="d872d-132">Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="d872d-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
