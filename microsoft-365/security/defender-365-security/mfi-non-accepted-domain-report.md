---
title: Niet-geaccepteerd domeinrapport in het e-mailstroomdashboard
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
description: Beheerders kunnen leren hoe ze het niet-geaccepteerde domeinrapport kunnen gebruiken in het e-mailstroomdashboard in het beveiligings- & compliancecentrum om berichten te controleren vanuit uw on-premises organisatie waar het domein van de afzender niet is geconfigureerd in Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fb33feb56bf2b52731c03273ce0c6444c333f348
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057870"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="d170e-103">Niet-geaccepteerd domeinrapport in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="d170e-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d170e-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="d170e-104">**Applies to**</span></span>
- [<span data-ttu-id="d170e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d170e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d170e-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d170e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d170e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d170e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="d170e-108">In het rapport **Niet-geaccepteerd** domein in het [e-mailstroomdashboard](mail-flow-insights-v2.md) in het [beveiligings- &](https://protection.office.com) compliancecentrum wordt informatie weergegeven over berichten van uw on-premises e-mailorganisatie waarin het domein van de afzender niet is geconfigureerd als een geaccepteerd domein in uw Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="d170e-108">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="d170e-109">Microsoft 365 kan deze berichten in de weg staan als we gegevens hebben om aan te tonen dat de bedoeling van deze berichten schadelijk is.</span><span class="sxs-lookup"><span data-stu-id="d170e-109">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="d170e-110">Daarom is het belangrijk dat u begrijpt wat er gebeurt en dat u het probleem kunt oplossen.</span><span class="sxs-lookup"><span data-stu-id="d170e-110">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Niet-geaccepteerde domeinwidget in het e-mailstroomdashboard in & Beveiligingscentrum](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="d170e-112">Rapportweergave voor het rapport Niet-geaccepteerde domein</span><span class="sxs-lookup"><span data-stu-id="d170e-112">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="d170e-113">Als u op de grafiek klikt in de **niet-geaccepteerde** domeinwidget, gaat u naar het **rapport Niet-geaccepteerde** domein.</span><span class="sxs-lookup"><span data-stu-id="d170e-113">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="d170e-114">Standaard wordt de activiteit voor alle betrokken verbindingslijnen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d170e-114">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="d170e-115">Als u op **Gegevens voor tonen klikt,** kunt u een specifieke verbindingslijn selecteren in de vervolgkeuzepagina.</span><span class="sxs-lookup"><span data-stu-id="d170e-115">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="d170e-116">Als u de muisaanwijzer boven een gegevenspunt (dag) in de grafiek beweegt, ziet u het totale aantal berichten voor de verbindingslijn.</span><span class="sxs-lookup"><span data-stu-id="d170e-116">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Rapportweergave in het rapport Niet-geaccepteerd domein](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="d170e-118">Tabelweergave details voor het rapport Niet-geaccepteerd domein</span><span class="sxs-lookup"><span data-stu-id="d170e-118">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="d170e-119">Als u in **een rapportweergave op Detailstabel** weergeven klikt, worden de volgende gegevens weergegeven:</span><span class="sxs-lookup"><span data-stu-id="d170e-119">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="d170e-120">**Datum**</span><span class="sxs-lookup"><span data-stu-id="d170e-120">**Date**</span></span>
- <span data-ttu-id="d170e-121">**Naam van inkomende verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="d170e-121">**Inbound connector name**</span></span>
- <span data-ttu-id="d170e-122">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="d170e-122">**Sender domain**</span></span>
- <span data-ttu-id="d170e-123">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="d170e-123">**Message count**</span></span>
- <span data-ttu-id="d170e-124">**Voorbeeldberichten:** de bericht-eds van een voorbeeld van de betreffende berichten.</span><span class="sxs-lookup"><span data-stu-id="d170e-124">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="d170e-125">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="d170e-125">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="d170e-126">Als u het rapport voor een bepaald datumbereik wilt e-mailen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**</span><span class="sxs-lookup"><span data-stu-id="d170e-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="d170e-127">Wanneer u een rij in de tabel selecteert, wordt een flyout weergegeven met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="d170e-127">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="d170e-128">**Datum**</span><span class="sxs-lookup"><span data-stu-id="d170e-128">**Date**</span></span>
- <span data-ttu-id="d170e-129">**Naam van inkomende verbindingslijn**</span><span class="sxs-lookup"><span data-stu-id="d170e-129">**Inbound connector name**</span></span>
- <span data-ttu-id="d170e-130">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="d170e-130">**Sender domain**</span></span>
- <span data-ttu-id="d170e-131">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="d170e-131">**Message count**</span></span>
- <span data-ttu-id="d170e-132">**Voorbeeldberichten:** U kunt op **Voorbeeldberichten weergeven klikken** om de resultaten van bericht trace te bekijken voor een voorbeeld van de betreffende berichten. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="d170e-132">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Details flyout after selecting a row in Details table view in the Non-accepted domain report](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="d170e-134">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="d170e-134">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d170e-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d170e-135">Related topics</span></span>

<span data-ttu-id="d170e-136">Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="d170e-136">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
