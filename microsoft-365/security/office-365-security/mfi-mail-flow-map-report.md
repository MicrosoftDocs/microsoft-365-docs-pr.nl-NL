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
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="b98f8-103">E-mailstroomkaart in het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="b98f8-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b98f8-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="b98f8-104">**Applies to**</span></span>
- [<span data-ttu-id="b98f8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b98f8-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="b98f8-106">Microsoft Defender voor Office 365-abonnement 1 en abonnement 2</span><span class="sxs-lookup"><span data-stu-id="b98f8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="b98f8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b98f8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="b98f8-108">De **e-mailstroomkaart** in het [dashboard E-mailstroom](mail-flow-insights-v2.md) in het & [compliancecentrum](https://protection.office.com) geeft inzicht in hoe e-mail door uw organisatie loopt.</span><span class="sxs-lookup"><span data-stu-id="b98f8-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="b98f8-109">U kunt deze informatie gebruiken om patronen te leren, problemen te identificeren en problemen op te lossen terwijl deze zich voordoen.</span><span class="sxs-lookup"><span data-stu-id="b98f8-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget E-mailstroomkaart in het dashboard E-mailstroom in het & Compliancecentrum](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="b98f8-111">De widget toont standaard het patroon van de e-mailstroom van de vorige dag in een grafiek die bekend staat als een *Sankey-diagram.*</span><span class="sxs-lookup"><span data-stu-id="b98f8-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="b98f8-112">U kunt de pijl-links en pijl-rechts gebruiken om ![ informatie van verschillende dagen weer te ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) geven.</span><span class="sxs-lookup"><span data-stu-id="b98f8-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="b98f8-113">Elke kleur geeft de e-mailstroom over een andere binnenkomende of uitgaande verbindingslijn aan (of zonder verbindingslijnen te gebruiken).</span><span class="sxs-lookup"><span data-stu-id="b98f8-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="b98f8-114">Als u de muisaanwijzer op een bepaalde kleur beweegt, wordt het aantal berichten voor dat type verbindingslijn weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b98f8-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="b98f8-115">Rapportweergave voor de e-mailstroomkaart</span><span class="sxs-lookup"><span data-stu-id="b98f8-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="b98f8-116">Als u op de widget **E-mailstroomkaart** klikt, gaat u naar het rapport **E-mailstroomkaart.**</span><span class="sxs-lookup"><span data-stu-id="b98f8-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="b98f8-117">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="b98f8-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b98f8-118">**Gegevens weergeven voor: Overzicht:** dit is in feite een grotere weergave van de widget.</span><span class="sxs-lookup"><span data-stu-id="b98f8-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="b98f8-119">Als u de muisaanwijzer op een bepaalde kleur beweegt, wordt het aantal berichten voor dat type verbindingslijn weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b98f8-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Overzichtsweergave in het rapport E-mailstroomoverzicht](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="b98f8-121">**Gegevens weergeven voor: Details:** deze weergave bevat details over de connectors en doeldomeinen.</span><span class="sxs-lookup"><span data-stu-id="b98f8-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="b98f8-122">De domeinen van de belangrijkste afzender en geadresseerde worden weergegeven en de rest wordt in Anderen **geplaatst.**</span><span class="sxs-lookup"><span data-stu-id="b98f8-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="b98f8-123">Als u de muisaanwijzer over een bepaalde kleur en sectie beweegt, wordt het aantal berichten weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b98f8-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Detailweergave in het rapport E-mailstroomkaart](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="b98f8-125">Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**</span><span class="sxs-lookup"><span data-stu-id="b98f8-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b98f8-126">Als u het rapport voor een bepaald datumbereik per e-mail wilt versturen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**</span><span class="sxs-lookup"><span data-stu-id="b98f8-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="b98f8-127">Gerelateerde inzichten worden onder de E-mailstroomkaart weergegeven als deze beschikbaar zijn (bijvoorbeeld het inzicht in Mogelijke [e-maillus oplossen).](mfi-mail-loop-insight.md)</span><span class="sxs-lookup"><span data-stu-id="b98f8-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="b98f8-128">Detailtabelweergave voor de e-mailstroomkaart</span><span class="sxs-lookup"><span data-stu-id="b98f8-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="b98f8-129">Als u in **een rapportweergave op Detailtabel** weergeven klikt, wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="b98f8-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="b98f8-130">**Datum**</span><span class="sxs-lookup"><span data-stu-id="b98f8-130">**Date**</span></span>
- <span data-ttu-id="b98f8-131">**Categorie**</span><span class="sxs-lookup"><span data-stu-id="b98f8-131">**Category**</span></span>
- <span data-ttu-id="b98f8-132">**Connector / Externe serviceprovider**</span><span class="sxs-lookup"><span data-stu-id="b98f8-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="b98f8-133">**Domein afzender/geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="b98f8-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="b98f8-134">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="b98f8-134">**Message count**</span></span>

<span data-ttu-id="b98f8-135">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**</span><span class="sxs-lookup"><span data-stu-id="b98f8-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b98f8-136">Als u een rij selecteert, worden soortgelijke details weergegeven in een flyout:</span><span class="sxs-lookup"><span data-stu-id="b98f8-136">If you select a row, similar details are shown in a flyout:</span></span>

![Flyout Details uit de tabel Details in de e-mailstroommap](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="b98f8-138">Als u het rapport voor een bepaald datumbereik per e-mail wilt versturen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**</span><span class="sxs-lookup"><span data-stu-id="b98f8-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="b98f8-139">Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="b98f8-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b98f8-140">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b98f8-140">See also</span></span>

<span data-ttu-id="b98f8-141">Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="b98f8-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
