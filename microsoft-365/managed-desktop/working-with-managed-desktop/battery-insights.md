---
title: Inzichten in batterijen
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f339fc98ea94c291c533045e9906f626f4b74e2a
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529837"
---
# <a name="battery-insights"></a><span data-ttu-id="88070-103">Inzichten in batterijen</span><span class="sxs-lookup"><span data-stu-id="88070-103">Battery insights</span></span>
<span data-ttu-id="88070-104">Deze weergave biedt stroom-, batterij- en app-gebruiksstatistieken voor uw Microsoft Managed Desktop-apparaten.</span><span class="sxs-lookup"><span data-stu-id="88070-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="88070-105">Voor deze doeleinden wordt een app beschouwd als 'in gebruik' als deze wordt uitgevoerd en scherp is.</span><span class="sxs-lookup"><span data-stu-id="88070-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="88070-106">Als u gebruiksgegevens wilt **weergeven,** selecteert u het tabblad Batterij.</span><span class="sxs-lookup"><span data-stu-id="88070-106">To view usage data, select the **Battery** tab.</span></span>

![Batterijvenster: voorspelde levensduur van de batterij per apparaatmodel in de linkerbovenhoek, bovenenergieconsumenten (per app) in de rechterbovenhoek, insights tabel aan de onderkant.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="88070-109">Voorspelde levensduur van de batterij</span><span class="sxs-lookup"><span data-stu-id="88070-109">Predicted battery life</span></span>

<span data-ttu-id="88070-110">In het gebied **Met de voorspelde levensduur** van de batterij geven we voorspellingen voor de verwachte levensduur van de batterij voor uw apparaten, georganiseerd op apparaatmodel.</span><span class="sxs-lookup"><span data-stu-id="88070-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="88070-111">Deze gegevens zijn afgeleid van het energieverbruik, de gebruiksduur en de batterijcapaciteit van een willekeurige <em>selectie</em> van de apparaten in uw Microsoft Managed Desktop-implementatie die ook gegevens rapporteren.</span><span class="sxs-lookup"><span data-stu-id="88070-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="88070-112">De tabel biedt de voorspelde levensduur van de batterij (in uren), de gemiddelde levensduur van de batterij voor dezelfde modellen in andere Microsoft Managed Desktop-implementaties en het aantal apparaten dat deze gegevens in uw omgeving rapporteert.</span><span class="sxs-lookup"><span data-stu-id="88070-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="88070-113">Sorteer de gegevens door de kolomkoppen te selecteren.</span><span class="sxs-lookup"><span data-stu-id="88070-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="88070-114">Top energieverbruikers</span><span class="sxs-lookup"><span data-stu-id="88070-114">Top energy consumers</span></span>

<span data-ttu-id="88070-115">In de **top van de energieverbruikers** vindt u de apps in uw omgeving die de meeste energie verbruiken in milliWatt-uren (mWh).</span><span class="sxs-lookup"><span data-stu-id="88070-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="88070-116">De weergegeven apps zijn per specifiek apparaat, dat u selecteert in de sectie **Voorspelde levensduur** van de batterij aan de linkerkant.</span><span class="sxs-lookup"><span data-stu-id="88070-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="88070-117">Als u bijvoorbeeld het verbruik per app voor uw Microsoft Surface Book 2-apparaten wilt bekijken, selecteert u die rij in het gebied van de levensduur van de batterij.</span><span class="sxs-lookup"><span data-stu-id="88070-117">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="88070-118">Als u geen enkel model selecteert, worden de weergegeven gegevens voor het verbruik van apps weergegeven voor alle apps waarvoor we gezamenlijk gegevens hebben.</span><span class="sxs-lookup"><span data-stu-id="88070-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="88070-119">Voor elke app tonen gekleurde segmenten u de verdeling van het energieverbruik van de app over deze categorieën:</span><span class="sxs-lookup"><span data-stu-id="88070-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="88070-120">Cpu</span><span class="sxs-lookup"><span data-stu-id="88070-120">CPU</span></span>
- <span data-ttu-id="88070-121">Weergeven</span><span class="sxs-lookup"><span data-stu-id="88070-121">Display</span></span>
- <span data-ttu-id="88070-122">Netwerk</span><span class="sxs-lookup"><span data-stu-id="88070-122">Network</span></span>
- <span data-ttu-id="88070-123">Overige</span><span class="sxs-lookup"><span data-stu-id="88070-123">Other</span></span>

<span data-ttu-id="88070-124">"Andere" kan het energieverbruik van verschillende bronnen omvatten, zoals schijfactiviteit, mobiel breedbandgebruik en energie die verloren is gegaan door interne weerstand.</span><span class="sxs-lookup"><span data-stu-id="88070-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="88070-125">U deze weergave filteren om alleen apps op de voorgrond, achtergrond-apps of beide weer te geven met behulp van het menu rechtsboven.</span><span class="sxs-lookup"><span data-stu-id="88070-125">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="88070-126">Voorgrond apps zijn die gebruikersinteractie hebben gehad in de afgelopen 28 dagen, zoals het selecteren van iets met een muis.</span><span class="sxs-lookup"><span data-stu-id="88070-126">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="88070-127">Inzichten</span><span class="sxs-lookup"><span data-stu-id="88070-127">Insights</span></span>

<span data-ttu-id="88070-128">Het **insights-gebied** toont de top drie van energieconsumenten in de CPU- en netwerkcategorieën.</span><span class="sxs-lookup"><span data-stu-id="88070-128">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="88070-129">Deze items verbruiken meer dan gemiddelde energie in vergelijking met alle Microsoft Managed Desktop-implementaties.</span><span class="sxs-lookup"><span data-stu-id="88070-129">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="88070-130">We tonen de weergavebron niet omdat deze sterk afhankelijk is van de gebruikstijd van het apparaat en de instellingen voor schermhelderheid.</span><span class="sxs-lookup"><span data-stu-id="88070-130">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="88070-131">Selecteer de aanbiedingen in de kolom **Details** voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="88070-131">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="88070-132">Batterijoptimalisatie</span><span class="sxs-lookup"><span data-stu-id="88070-132">Battery optimization</span></span>

<span data-ttu-id="88070-133">Windows 10 biedt tal van [apparaatinstellingen](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) om het energieverbruik te verbeteren en de levensduur van de batterij van uw Microsoft Managed Desktop-apparaten te verlengen.</span><span class="sxs-lookup"><span data-stu-id="88070-133">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="88070-134">Sommige van deze instellingen kunnen andere Windows-functionaliteit verminderen, dus u moet ook rekening houden met andere factoren, zoals de rol van het apparaat in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="88070-134">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="88070-135">Windows-ondersteuning houdt een lijst bij van deze tips voor het opslaan van [batterijen.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)</span><span class="sxs-lookup"><span data-stu-id="88070-135">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="88070-136">Gebruikers kunnen sommige instellingen zelf aanpassen zonder dat ze beheerdersverhoging of -ondersteuning nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="88070-136">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="88070-137">Andere instellingen vereisen ondersteuning van de IT-beheerder van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="88070-137">Other settings require support from your organization's IT administrator.</span></span>
