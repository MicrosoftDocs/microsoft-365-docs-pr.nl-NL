---
title: Inzichten in batterijen
description: Een rapport met gegevens over de voorspelde levensduur van de batterij en de beste consumenten van stroomverbruikers
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579708"
---
# <a name="battery-insights"></a><span data-ttu-id="b655a-104">Inzichten in batterijen</span><span class="sxs-lookup"><span data-stu-id="b655a-104">Battery insights</span></span>
<span data-ttu-id="b655a-105">Deze weergave biedt metrische energie, batterij en app-gebruik voor uw Microsoft Managed Desktop-apparaten.</span><span class="sxs-lookup"><span data-stu-id="b655a-105">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b655a-106">Voor deze doeleinden wordt een app beschouwd als 'in gebruik' als deze wordt uitgevoerd en in focus staat.</span><span class="sxs-lookup"><span data-stu-id="b655a-106">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="b655a-107">Als u gebruiksgegevens wilt weergeven, selecteert u het **tabblad** Batterij.</span><span class="sxs-lookup"><span data-stu-id="b655a-107">To view usage data, select the **Battery** tab.</span></span>

![Batterijdeelvenster: voorspelde levensduur van de batterij per apparaatmodel in de linkerbovenhoek, beste energieverbruikers (per app) in de rechterbovenhoek, inzichtentabel aan de onderkant.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="b655a-110">Voorspelde levensduur van de batterij</span><span class="sxs-lookup"><span data-stu-id="b655a-110">Predicted battery life</span></span>

<span data-ttu-id="b655a-111">In het **gebied Voorspelde levensduur** van de batterij geven we voorspellingen voor de verwachte levensduur van de batterij voor uw apparaten, ingedeeld per apparaatmodel.</span><span class="sxs-lookup"><span data-stu-id="b655a-111">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="b655a-112">Deze gegevens zijn afgeleid van het gebruik van energie, <em></em> de gebruiksduur en de batterijcapaciteit van een willekeurige selectie van de apparaten in uw Microsoft Managed Desktop-implementatie die ook gegevens rapporteren.</span><span class="sxs-lookup"><span data-stu-id="b655a-112">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="b655a-113">De tabel bevat de voorspelde levensduur van de batterij (in uren), de gemiddelde levensduur van de batterij voor dezelfde modellen in andere Microsoft Managed Desktop-implementaties en het aantal apparaten dat deze gegevens in uw omgeving rapporteert.</span><span class="sxs-lookup"><span data-stu-id="b655a-113">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="b655a-114">Sorteer de gegevens door de kolomkoppen te selecteren.</span><span class="sxs-lookup"><span data-stu-id="b655a-114">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="b655a-115">Beste energieverbruikers</span><span class="sxs-lookup"><span data-stu-id="b655a-115">Top energy consumers</span></span>

<span data-ttu-id="b655a-116">In het **gebied Top energy consumers** vindt u de apps in uw omgeving die de meeste energie verbruiken in milliWatt-uren (mWh).</span><span class="sxs-lookup"><span data-stu-id="b655a-116">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="b655a-117">De weergegeven apps zijn per specifiek apparaat, dat u selecteert in de sectie **Voorspelde** batterijduur aan de linkerkant.</span><span class="sxs-lookup"><span data-stu-id="b655a-117">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="b655a-118">Als u bijvoorbeeld het verbruik per app wilt zien voor uw Microsoft Surface Book 2-apparaten, selecteert u die rij in het batterijduurgebied.</span><span class="sxs-lookup"><span data-stu-id="b655a-118">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="b655a-119">Als u geen model selecteert, zijn de weergegeven verbruiksgegevens voor apps voor alle apps waar we gegevens voor hebben.</span><span class="sxs-lookup"><span data-stu-id="b655a-119">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="b655a-120">In gekleurde segmenten voor elke app ziet u de verdeling van het energiegebruik van de app over deze categorieën:</span><span class="sxs-lookup"><span data-stu-id="b655a-120">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="b655a-121">CPU</span><span class="sxs-lookup"><span data-stu-id="b655a-121">CPU</span></span>
- <span data-ttu-id="b655a-122">Weergeven</span><span class="sxs-lookup"><span data-stu-id="b655a-122">Display</span></span>
- <span data-ttu-id="b655a-123">Netwerk</span><span class="sxs-lookup"><span data-stu-id="b655a-123">Network</span></span>
- <span data-ttu-id="b655a-124">Overige</span><span class="sxs-lookup"><span data-stu-id="b655a-124">Other</span></span>

<span data-ttu-id="b655a-125">'Overige' kan het energieverbruik omvatten van diverse bronnen, zoals schijfactiviteit, mobiel breedbandgebruik en energie die verloren gaat door interne weerstand.</span><span class="sxs-lookup"><span data-stu-id="b655a-125">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="b655a-126">U kunt deze weergave filteren om alleen voorgrond-apps, achtergrond-apps of beide weer te geven met behulp van het menu in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="b655a-126">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="b655a-127">Voorgrond-apps zijn apps die de afgelopen 28 dagen interactie hebben gehad met de gebruiker, zoals het selecteren van iets met een muis.</span><span class="sxs-lookup"><span data-stu-id="b655a-127">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="b655a-128">Inzichten</span><span class="sxs-lookup"><span data-stu-id="b655a-128">Insights</span></span>

<span data-ttu-id="b655a-129">In **het gebied** Inzichten ziet u de drie beste energieverbruikers in de cpu- en netwerkcategorieën.</span><span class="sxs-lookup"><span data-stu-id="b655a-129">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="b655a-130">Deze items verbruiken meer dan gemiddelde energie in vergelijking met alle Microsoft Managed Desktop-implementaties.</span><span class="sxs-lookup"><span data-stu-id="b655a-130">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="b655a-131">De weergaveresource wordt niet weergegeven, omdat deze sterk afhankelijk is van de tijd van apparaatgebruik en de schermhelderheidsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="b655a-131">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="b655a-132">Selecteer de vermeldingen in de **kolom Details** voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b655a-132">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="b655a-133">Batterijoptimalisatie</span><span class="sxs-lookup"><span data-stu-id="b655a-133">Battery optimization</span></span>

<span data-ttu-id="b655a-134">Windows 10 biedt talloze [apparaatinstellingen om](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) het stroomverbruik te verbeteren en de levensduur van de batterij van uw Microsoft Managed Desktop-apparaten te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="b655a-134">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b655a-135">Sommige van deze instellingen kunnen andere Windows-functionaliteit verminderen, dus u moet ook rekening houden met andere factoren, zoals de rol van het apparaat in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b655a-135">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="b655a-136">Windows-ondersteuning onderhoudt een lijst met deze [tips voor batterijbesparing.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)</span><span class="sxs-lookup"><span data-stu-id="b655a-136">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="b655a-137">Gebruikers kunnen bepaalde instellingen zelf aanpassen zonder dat ze de beheerder hoeven te verheffing of ondersteuning nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="b655a-137">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="b655a-138">Voor andere instellingen is ondersteuning nodig van de IT-beheerder van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b655a-138">Other settings require support from your organization's IT administrator.</span></span>
