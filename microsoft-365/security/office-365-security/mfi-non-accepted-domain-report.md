---
title: Rapport over niet-geaccepteerd domein in het dashboard mailstroom
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
description: Beheerders kunnen informatie vinden over het gebruik van het rapport Niet-geaccepteerd domein in het dashboard E-mailstroom in het beveiligings- & Compliancecentrum om berichten te controleren van uw on-premises organisatie waar het domein van de afzender niet is geconfigureerd in Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6d7355af49c5810a593c5776b70cf7497b43af6b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287863"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="ecb18-103">Rapport over niet-geaccepteerd domein in het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="ecb18-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ecb18-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="ecb18-104">**Applies to**</span></span>
- [<span data-ttu-id="ecb18-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ecb18-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ecb18-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="ecb18-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ecb18-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ecb18-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ecb18-108">In het rapport Niet-geaccepteerd domein in het [dashboard](mail-flow-insights-v2.md) E-mailstroom in het [beveiligings- & compliancecentrum](https://protection.office.com) wordt informatie weergegeven over berichten van uw **on-premises e-mailorganisatie** waarin het domein van de afzender niet is geconfigureerd als een geaccepteerd domein in uw Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="ecb18-108">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="ecb18-109">Microsoft 365 kan deze berichten beperkt als we gegevens hebben om te bewijzen dat de bedoeling van deze berichten schadelijk is.</span><span class="sxs-lookup"><span data-stu-id="ecb18-109">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="ecb18-110">Het is dus belangrijk dat u begrijpt wat er gebeurt en dat u het probleem kunt oplossen.</span><span class="sxs-lookup"><span data-stu-id="ecb18-110">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Widget voor niet-geaccepteerd domein in het dashboard E-mailstroom in het & Compliancecentrum](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="ecb18-112">Rapportweergave voor het rapport Niet-geaccepteerd domein</span><span class="sxs-lookup"><span data-stu-id="ecb18-112">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="ecb18-113">Als u op de grafiek in de widget **Niet-geaccepteerd** domein klikt, gaat u naar het rapport **Niet-geaccepteerd domein.**</span><span class="sxs-lookup"><span data-stu-id="ecb18-113">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="ecb18-114">Standaard wordt de activiteit voor alle betrokken verbindingslijnen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ecb18-114">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="ecb18-115">Als u op **Gegevens tonen klikt,** kunt u een specifieke verbindingslijn selecteren in de vervolgkeuzepagina.</span><span class="sxs-lookup"><span data-stu-id="ecb18-115">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="ecb18-116">Als u de muisaanwijzer op een gegevenspunt (dag) in de grafiek beweegt, ziet u het totale aantal berichten voor de connector.</span><span class="sxs-lookup"><span data-stu-id="ecb18-116">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Rapportweergave in het rapport Niet-geaccepteerd domein](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="ecb18-118">Tabelweergave Details voor het rapport Niet-geaccepteerd domein</span><span class="sxs-lookup"><span data-stu-id="ecb18-118">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="ecb18-119">Als u in **een rapportweergave op Detailtabel** weergeven klikt, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="ecb18-119">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="ecb18-120">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ecb18-120">**Date**</span></span>
- <span data-ttu-id="ecb18-121">**Naam van binnenkomende connector**</span><span class="sxs-lookup"><span data-stu-id="ecb18-121">**Inbound connector name**</span></span>
- <span data-ttu-id="ecb18-122">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="ecb18-122">**Sender domain**</span></span>
- <span data-ttu-id="ecb18-123">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="ecb18-123">**Message count**</span></span>
- <span data-ttu-id="ecb18-124">**Voorbeeldberichten:** de bericht-e-mailberichten van een steekproef van beïnvloede berichten.</span><span class="sxs-lookup"><span data-stu-id="ecb18-124">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="ecb18-125">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**</span><span class="sxs-lookup"><span data-stu-id="ecb18-125">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="ecb18-126">Als u het rapport voor een bepaald datumbereik per e-mail wilt versturen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**</span><span class="sxs-lookup"><span data-stu-id="ecb18-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="ecb18-127">Wanneer u een rij in de tabel selecteert, wordt een flyout met de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="ecb18-127">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="ecb18-128">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ecb18-128">**Date**</span></span>
- <span data-ttu-id="ecb18-129">**Naam van binnenkomende connector**</span><span class="sxs-lookup"><span data-stu-id="ecb18-129">**Inbound connector name**</span></span>
- <span data-ttu-id="ecb18-130">**Afzenderdomein**</span><span class="sxs-lookup"><span data-stu-id="ecb18-130">**Sender domain**</span></span>
- <span data-ttu-id="ecb18-131">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="ecb18-131">**Message count**</span></span>
- <span data-ttu-id="ecb18-132">**Voorbeeldberichten:** u kunt op **Voorbeeldberichten weergeven** klikken om de [resultaten](message-trace-scc.md) van bericht traceren voor een voorbeeld van de betreffende berichten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="ecb18-132">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Flyout Details na het selecteren van een rij in de tabelweergave Details in het rapport Niet-geaccepteerd domein](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="ecb18-134">Als u terug wilt gaan naar de rapportweergave, klikt u **op Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="ecb18-134">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ecb18-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ecb18-135">Related topics</span></span>

<span data-ttu-id="ecb18-136">Voor informatie over andere inzichten in het dashboard voor de e-mailstroom, bekijkt u inzichten in de e-mailstroom in het & [compliancecentrum.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="ecb18-136">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
