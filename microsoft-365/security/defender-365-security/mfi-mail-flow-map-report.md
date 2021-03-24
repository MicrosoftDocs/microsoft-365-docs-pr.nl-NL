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
description: Beheerders kunnen leren hoe ze de e-mailstroommap in het e-mailstroomdashboard in het beveiligings- & compliancecentrum kunnen gebruiken om te visualiseren en bij te houden hoe e-mail van en naar hun organisatie loopt via verbindingslijnen en zonder verbindingslijnen te gebruiken.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e806dde2e6f3ddde5cce3b61c85fe0b024ba2fe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057894"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="075f7-103">E-mailstroommap in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="075f7-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="075f7-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="075f7-104">**Applies to**</span></span>
- [<span data-ttu-id="075f7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="075f7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="075f7-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="075f7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="075f7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="075f7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="075f7-108">De **e-mailstroommap** in het [e-mailstroomdashboard](mail-flow-insights-v2.md) in & [Beveiligingscentrum](https://protection.office.com) geeft inzicht in de manier waarop e-mail door uw organisatie loopt.</span><span class="sxs-lookup"><span data-stu-id="075f7-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="075f7-109">U kunt deze informatie gebruiken om patronen te leren, afwijkingen te identificeren en problemen op te lossen wanneer deze zich voordoen.</span><span class="sxs-lookup"><span data-stu-id="075f7-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget E-mailstroomkaart in het dashboard E-mailstroom in & Compliancecentrum](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="075f7-111">Standaard wordt in de widget het e-mailstroompatroon van de vorige dag weergegeven in een grafiek die bekend staat als een *Sankey-diagram.*</span><span class="sxs-lookup"><span data-stu-id="075f7-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="075f7-112">U kunt de pijl-links en pijl-rechts pijl-rechts ![ gebruiken om informatie van verschillende dagen weer te ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) geven.</span><span class="sxs-lookup"><span data-stu-id="075f7-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="075f7-113">Elke andere kleur vertegenwoordigt de e-mailstroom over een andere binnenkomende of uitgaande verbindingslijn (of zonder verbindingslijnen).</span><span class="sxs-lookup"><span data-stu-id="075f7-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="075f7-114">Als u de muisaanwijzer op een bepaalde kleur beweegt, wordt het aantal berichten weergegeven voor dat type verbindingslijn.</span><span class="sxs-lookup"><span data-stu-id="075f7-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="075f7-115">Rapportweergave voor de e-mailstroommap</span><span class="sxs-lookup"><span data-stu-id="075f7-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="075f7-116">Als u op de widget **E-mailstroomkaart** klikt, gaat u naar het **rapport E-mailstroomkaart.**</span><span class="sxs-lookup"><span data-stu-id="075f7-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="075f7-117">De volgende grafieken zijn beschikbaar in de rapportweergave:</span><span class="sxs-lookup"><span data-stu-id="075f7-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="075f7-118">**Gegevens weergeven voor: Overzicht:** Dit is in feite een grotere weergave van de widget.</span><span class="sxs-lookup"><span data-stu-id="075f7-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="075f7-119">Als u de muisaanwijzer op een bepaalde kleur beweegt, wordt het aantal berichten weergegeven voor dat type verbindingslijn.</span><span class="sxs-lookup"><span data-stu-id="075f7-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Overzichtsweergave in het rapport E-mailstroomkaart](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="075f7-121">**Gegevens weergeven voor: Detail:** In deze weergave ziet u details over de verbindingslijnen en doeldomeinen.</span><span class="sxs-lookup"><span data-stu-id="075f7-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="075f7-122">De belangrijkste afzender- en geadresseerdedomeinen worden weergegeven en de rest wordt in Anderen **geplaatst.**</span><span class="sxs-lookup"><span data-stu-id="075f7-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="075f7-123">Als u de muisaanwijzer boven een bepaalde kleur en sectie beweegt, wordt het aantal berichten weergegeven.</span><span class="sxs-lookup"><span data-stu-id="075f7-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Detailweergave in het rapport E-mailstroomkaart](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="075f7-125">Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="075f7-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="075f7-126">Als u het rapport voor een bepaald datumbereik wilt e-mailen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**</span><span class="sxs-lookup"><span data-stu-id="075f7-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="075f7-127">Verwante inzichten worden weergegeven onder de e-mailstroomkaart als deze beschikbaar zijn (bijvoorbeeld het inzicht in mogelijke [e-maillus oplossen).](mfi-mail-loop-insight.md)</span><span class="sxs-lookup"><span data-stu-id="075f7-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="075f7-128">Tabelweergave Details voor de e-mailstroommap</span><span class="sxs-lookup"><span data-stu-id="075f7-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="075f7-129">Als u in **een rapportweergave op Detailstabel** weergeven klikt, worden de volgende gegevens weergegeven:</span><span class="sxs-lookup"><span data-stu-id="075f7-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="075f7-130">**Datum**</span><span class="sxs-lookup"><span data-stu-id="075f7-130">**Date**</span></span>
- <span data-ttu-id="075f7-131">**Categorie**</span><span class="sxs-lookup"><span data-stu-id="075f7-131">**Category**</span></span>
- <span data-ttu-id="075f7-132">**Connector / Externe serviceprovider**</span><span class="sxs-lookup"><span data-stu-id="075f7-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="075f7-133">**Domein afzender/geadresseerde**</span><span class="sxs-lookup"><span data-stu-id="075f7-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="075f7-134">**Aantal berichten**</span><span class="sxs-lookup"><span data-stu-id="075f7-134">**Message count**</span></span>

<span data-ttu-id="075f7-135">Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**</span><span class="sxs-lookup"><span data-stu-id="075f7-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="075f7-136">Als u een rij selecteert, worden soortgelijke details weergegeven in een flyout:</span><span class="sxs-lookup"><span data-stu-id="075f7-136">If you select a row, similar details are shown in a flyout:</span></span>

![Details flyout from the details table in the Mail flow map](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="075f7-138">Als u het rapport voor een bepaald datumbereik wilt e-mailen naar een of meer geadresseerden, klikt u op **Downloaden aanvragen.**</span><span class="sxs-lookup"><span data-stu-id="075f7-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="075f7-139">Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="075f7-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="075f7-140">Zie ook</span><span class="sxs-lookup"><span data-stu-id="075f7-140">See also</span></span>

<span data-ttu-id="075f7-141">Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="075f7-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
