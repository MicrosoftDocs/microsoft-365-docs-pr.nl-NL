---
title: Batterij-inzichten
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 434f62d5ddfc8bc75c54de422aafc8c6325c4086
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "42812075"
---
# <a name="battery-insights"></a><span data-ttu-id="b1a00-103">Batterij-inzichten</span><span class="sxs-lookup"><span data-stu-id="b1a00-103">Battery insights</span></span>
<span data-ttu-id="b1a00-104">Deze weergave biedt statistieken over stroom-, batterij- en app-gebruik voor uw Microsoft Managed Desktop-apparaten.</span><span class="sxs-lookup"><span data-stu-id="b1a00-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b1a00-105">Voor deze doeleinden wordt een app beschouwd als "in gebruik" als deze wordt uitgevoerd en scherp is.</span><span class="sxs-lookup"><span data-stu-id="b1a00-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="b1a00-106">Als u gebruiksgegevens wilt weergeven, selecteert u het tabblad **Batterij.**</span><span class="sxs-lookup"><span data-stu-id="b1a00-106">To view usage data, select the **Battery** tab.</span></span>

![Batterijvenster: voorspelde levensduur van de batterij per apparaatmodel linksboven, topenergieverbruikers (via app) rechtsboven, tabel met inzichten aan de onderkant.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="b1a00-109">Voorspelde levensduur van de batterij</span><span class="sxs-lookup"><span data-stu-id="b1a00-109">Predicted battery life</span></span>

<span data-ttu-id="b1a00-110">In het **voorspelde batterijduurgebied** bieden we voorspellingen voor de verwachte levensduur van de batterij voor uw apparaten, georganiseerd op apparaatmodel.</span><span class="sxs-lookup"><span data-stu-id="b1a00-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="b1a00-111">Deze gegevens zijn afgeleid van het samplen van energieverbruik, gebruikstijd en batterijcapaciteit van een willekeurige <em>selectie</em> van de apparaten in uw Microsoft Managed Desktop-implementatie die ook gegevens rapporteren.</span><span class="sxs-lookup"><span data-stu-id="b1a00-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="b1a00-112">De tabel biedt de voorspelde levensduur van de batterij (in uren), de gemiddelde levensduur van de batterij voor dezelfde modellen in andere Microsoft Managed Desktop-implementaties en het aantal apparaten dat deze gegevens in uw omgeving rapporteert.</span><span class="sxs-lookup"><span data-stu-id="b1a00-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="b1a00-113">Sorteer de gegevens door de kolomkoppen te selecteren.</span><span class="sxs-lookup"><span data-stu-id="b1a00-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="b1a00-114">Top energieverbruikers</span><span class="sxs-lookup"><span data-stu-id="b1a00-114">Top energy consumers</span></span>

<span data-ttu-id="b1a00-115">In de top **van energieconsumenten** vind je de apps in je omgeving die de meeste energie verbruiken in milliWatt-uren (mWh).</span><span class="sxs-lookup"><span data-stu-id="b1a00-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="b1a00-116">De getoonde apps zijn per specifiek apparaat, dat u selecteert in de sectie **Voorspelde levensduur van** de batterij aan de linkerkant.</span><span class="sxs-lookup"><span data-stu-id="b1a00-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="b1a00-117">Als u bijvoorbeeld het verbruik per app voor uw Microsoft Surface Book 2-apparaten wilt zien, selecteert u die rij in het gebied van de levensduur van de batterij.</span><span class="sxs-lookup"><span data-stu-id="b1a00-117">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="b1a00-118">Als u geen model selecteert, zijn de weergegeven gegevens over het app-verbruik voor alle apps waarvoor we gegevens gezamenlijk hebben.</span><span class="sxs-lookup"><span data-stu-id="b1a00-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="b1a00-119">Voor elke app tonen gekleurde segmenten u de verdeling van het energieverbruik van de app over deze categorieën:</span><span class="sxs-lookup"><span data-stu-id="b1a00-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="b1a00-120">Cpu</span><span class="sxs-lookup"><span data-stu-id="b1a00-120">CPU</span></span>
- <span data-ttu-id="b1a00-121">Weergeven</span><span class="sxs-lookup"><span data-stu-id="b1a00-121">Display</span></span>
- <span data-ttu-id="b1a00-122">Netwerk</span><span class="sxs-lookup"><span data-stu-id="b1a00-122">Network</span></span>
- <span data-ttu-id="b1a00-123">Andere</span><span class="sxs-lookup"><span data-stu-id="b1a00-123">Other</span></span>

<span data-ttu-id="b1a00-124">"Andere" kunnen het energieverbruik door verschillende bronnen omvatten, zoals schijfactiviteit, mobiel breedbandgebruik en energie die verloren gaat aan interne weerstand.</span><span class="sxs-lookup"><span data-stu-id="b1a00-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="b1a00-125">U deze weergave filteren om alleen apps op de voorgrond, achtergrond-apps of beide weer te geven met behulp van het menu rechtsboven.</span><span class="sxs-lookup"><span data-stu-id="b1a00-125">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="b1a00-126">Voorgrond-apps zijn apps die de afgelopen 28 dagen interactie met gebruikers hebben gehad, zoals het selecteren van iets met een muis.</span><span class="sxs-lookup"><span data-stu-id="b1a00-126">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="b1a00-127">Inzichten</span><span class="sxs-lookup"><span data-stu-id="b1a00-127">Insights</span></span>

<span data-ttu-id="b1a00-128">Het **insights-gebied** toont de top drie van energieconsumenten in de CPU- en netwerkcategorieën.</span><span class="sxs-lookup"><span data-stu-id="b1a00-128">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="b1a00-129">Deze items verbruiken meer dan gemiddelde energie in vergelijking met alle Microsoft Managed Desktop-implementaties.</span><span class="sxs-lookup"><span data-stu-id="b1a00-129">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="b1a00-130">We tonen de weergavebron niet omdat deze sterk afhankelijk is van de gebruikstijd van het apparaat en de instellingen voor schermhelderheid.</span><span class="sxs-lookup"><span data-stu-id="b1a00-130">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="b1a00-131">Selecteer de aanbiedingen in de kolom **Details** voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b1a00-131">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="b1a00-132">Batterijoptimalisatie</span><span class="sxs-lookup"><span data-stu-id="b1a00-132">Battery optimization</span></span>

<span data-ttu-id="b1a00-133">Windows 10 biedt tal van [apparaatinstellingen](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) om het energieverbruik te verbeteren en de levensduur van de batterij van uw Microsoft Managed Desktop-apparaten te verhogen.</span><span class="sxs-lookup"><span data-stu-id="b1a00-133">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b1a00-134">Sommige van deze instellingen kunnen andere Windows-functionaliteit verminderen, dus u moet ook rekening houden met andere factoren, zoals de rol van het apparaat in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b1a00-134">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="b1a00-135">Windows-ondersteuning houdt een lijst bij van deze [tips voor batterijbesparing.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)</span><span class="sxs-lookup"><span data-stu-id="b1a00-135">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="b1a00-136">Gebruikers kunnen sommige instellingen zelf aanpassen zonder dat er beheerdersverhoging of ondersteuning nodig is.</span><span class="sxs-lookup"><span data-stu-id="b1a00-136">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="b1a00-137">Andere instellingen vereisen ondersteuning van de IT-beheerder van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b1a00-137">Other settings require support from your organization's IT administrator.</span></span>
