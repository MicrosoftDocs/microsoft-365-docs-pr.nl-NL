---
title: Waarschuwingen onderzoeken in Microsoft 365 Defender
description: Onderzoeken van waarschuwingen die worden gezien op apparaten, gebruikers en postvakken.
keywords: incidenten, waarschuwingen, onderzoeken, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c4a67a6b0df9308e9e61733a951a5016fa69c082
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50928692"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="ff3b1-104">Waarschuwingen onderzoeken in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff3b1-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ff3b1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ff3b1-105">**Applies to:**</span></span>
- <span data-ttu-id="ff3b1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff3b1-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="ff3b1-107">Waarschuwingen vormen de basis van alle incidenten en geven aan dat er schadelijke of verdachte gebeurtenissen in uw omgeving voorkomen.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="ff3b1-108">Waarschuwingen maken meestal deel uit van een bredere aanval en bevatten aanwijzingen over een incident.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-108">Alerts are typically part of a broader attack and provide pieces of clues about an incident.</span></span>

<span data-ttu-id="ff3b1-109">In Microsoft 365 Defender worden gerelateerde waarschuwingen samengevoegd tot incidenten.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-109">In Microsoft 365 Defender, related alerts are aggregated together to form incidents.</span></span> <span data-ttu-id="ff3b1-110">Incidenten bieden altijd de bredere context van een aanval, maar het onderzoeken van waarschuwingen kan waardevol zijn wanneer een diepere analyse is vereist.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-110">Incidents will always provide the broader context of an attack, however, investigating alerts can be valuable when deeper analysis is required.</span></span> 



## <a name="using-alert-pages-in-investigations"></a><span data-ttu-id="ff3b1-111">Waarschuwingspagina's gebruiken in onderzoeken</span><span class="sxs-lookup"><span data-stu-id="ff3b1-111">Using alert pages in investigations</span></span>

<span data-ttu-id="ff3b1-112">Als u op het tabblad Waarschuwingen van een incidentpagina een waarschuwing selecteert, gaat u naar de afzonderlijke waarschuwingspagina's.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-112">From the Alerts tab of any incident page, selecting an alert brings you to the individual alert pages.</span></span> <span data-ttu-id="ff3b1-113">Een waarschuwingspagina bestaat uit drie secties: de betreffende activa, het waarschuwingsverhaal en het detailvenster.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-113">An alert page is composed of three sections: affected assets, alert story, and the details pane.</span></span>

![Afbeelding van voorbeeldwaarschuwingspagina](../../media/new-alert-page2.png)

<span data-ttu-id="ff3b1-115">Op een waarschuwingspagina kunt u het pictogram met drie puntjes **(...)** naast een entiteit selecteren, zodat u beschikbare acties kunt zien, zoals het openen van de specifieke activapagina of het uitvoeren van specifieke herstelstappen.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-115">Throughout an alert page, you can select the three-dot icon (**...**) beside any entity so you can see available actions like opening the specific asset page or doing specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="ff3b1-116">Beïnvloede activa analyseren</span><span class="sxs-lookup"><span data-stu-id="ff3b1-116">Analyze affected assets</span></span>
<span data-ttu-id="ff3b1-117">De sectie betreffende activa bevat postvakken, apparaten en gebruikers die door deze waarschuwing worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-117">The affected assets section lists mailboxes, devices, and users affected by this alert.</span></span> <span data-ttu-id="ff3b1-118">Als u een van de activakaarten selecteert, wordt het detaildeelvenster gevuld met informatie, inclusief andere waarschuwingen die zijn opgetreden met betrekking tot de activa, indien van de gegevens.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-118">Selecting any of the asset cards populates the details side pane with information, including other alerts that occurred involving the assets, if any.</span></span>


### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="ff3b1-119">De rol van een waarschuwing in het waarschuwingsverhaal traceren</span><span class="sxs-lookup"><span data-stu-id="ff3b1-119">Trace an alert's role in the alert story</span></span>
<span data-ttu-id="ff3b1-120">In het waarschuwingsverhaal worden alle activa of entiteiten weergegeven die betrekking hebben op de waarschuwing in een processtructuurweergave.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-120">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="ff3b1-121">De waarschuwing in de titel is de waarschuwing in focus wanneer u voor het eerst op de pagina van de geselecteerde waarschuwing komt.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-121">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="ff3b1-122">Activa in het waarschuwingsverhaal kunnen worden uitvuwbaar en kunnen worden geklikt.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-122">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="ff3b1-123">Ze bieden extra informatie en versnellen de reactie doordat u acties kunt uitvoeren in de context van de waarschuwingspagina.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-123">They provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="ff3b1-124">De sectie Waarschuwingsverhaal kan meer dan één waarschuwing bevatten, met aanvullende waarschuwingen die betrekking hebben op dezelfde uitvoeringsstructuur die wordt weergegeven vóór of na de waarschuwing die u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-in-the-details-pane"></a><span data-ttu-id="ff3b1-125">Meer waarschuwingsgegevens weergeven in het detailvenster</span><span class="sxs-lookup"><span data-stu-id="ff3b1-125">View more alert information in the details pane</span></span>

<span data-ttu-id="ff3b1-126">In het detailvenster ziet u eerst de details van de geselecteerde waarschuwing, met details en acties die daaraan zijn gerelateerd.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-126">The details pane shows the details of the selected alert at first, with details and actions related to it.</span></span> <span data-ttu-id="ff3b1-127">Als u een van de getroffen activa of entiteiten in het waarschuwingsverhaal selecteert, wordt het detailvenster gewijzigd in contextuele informatie en acties voor het geselecteerde object.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-127">If you select any of the affected assets or entities in the alert story, the details pane changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="ff3b1-128">Nadat u een entiteit van belang hebt geselecteerd, wordt in het detailvenster informatie weergegeven over het geselecteerde entiteitstype, historische informatie wanneer deze beschikbaar is en opties om rechtstreeks vanaf de waarschuwingspagina actie te ondernemen op deze entiteit.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-128">Once you've selected an entity of interest, the details pane changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

### <a name="manage-alerts"></a><span data-ttu-id="ff3b1-129">Waarschuwingen beheren</span><span class="sxs-lookup"><span data-stu-id="ff3b1-129">Manage alerts</span></span>

<span data-ttu-id="ff3b1-130">Nadat u klaar bent met het onderzoeken van de waarschuwingen, kunt u teruggaan naar de waarschuwing die u hebt gestart, de status van de waarschuwing markeren als Opgelost en deze classificeren als een foutmelding of Een waar-waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-130">Once you're done investigating the alerts, you can go back to the alert you started with, mark the alert's status as Resolved and classify it as either a False alert or True alert.</span></span> <span data-ttu-id="ff3b1-131">Als u waarschuwingen classificeert, kunt u uw product afstemmen op meer waar waarschuwingen en minder onwaar waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-131">Classifying alerts helps tune your product to provide more true alerts and less false alerts.</span></span>

> [!NOTE]
> <span data-ttu-id="ff3b1-132">Een manier om waarschuwingen te beheren via het gebruik van tags.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-132">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="ff3b1-133">De labelfunctie voor Microsoft Defender voor Office 365 wordt stapsgewijs uitgerold en wordt momenteel in preview weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-133">The tagging capability for Microsoft Defender for Office 365 in incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="ff3b1-134">Op dit moment worden gewijzigde tagnamen alleen toegepast op waarschuwingen die *na de* update zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-134">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="ff3b1-135">Waarschuwingen die vóór de wijziging zijn gegenereerd, geven de bijgewerkte labelnaam niet weer.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-135">Alerts that were generated prior to the modification will not reflect the updated tag name.</span></span> 


## <a name="manage-the-unified-alert-queue"></a><span data-ttu-id="ff3b1-136">De geïntegreerde waarschuwingswachtrij beheren</span><span class="sxs-lookup"><span data-stu-id="ff3b1-136">Manage the unified alert queue</span></span>

<span data-ttu-id="ff3b1-137">Als u Waarschuwingen selecteert & meldingen in het navigatiedeelvenster van het Microsoft 365-beveiligingscentrum, wordt u in de geïntegreerde waarschuwingswachtrij geplaatst.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-137">Selecting Alerts under Incidents & Alerts in the Microsoft 365 security center navigation pane brings you to the unified alert queue.</span></span> <span data-ttu-id="ff3b1-138">Waarschuwingen van verschillende Microsoft-beveiligingsoplossingen, zoals Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365 en Microsoft 365 Defender, worden weergegeven in deze sectie.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-138">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear in this section.</span></span> 

![Afbeelding van voorbeeldwaarschuwingspagina](../../media/unified-alert-queue.png)

<span data-ttu-id="ff3b1-140">In de wachtrij Waarschuwingen ziet u een lijst met waarschuwingen die zijn gemarkeerd in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-140">The Alerts queue shows a list of alerts that were flagged in your network.</span></span> <span data-ttu-id="ff3b1-141">Standaard worden in de wachtrij waarschuwingen weergegeven die de afgelopen 30 dagen zijn weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-141">By default, the queue displays alerts seen in the last 30 days.</span></span> <span data-ttu-id="ff3b1-142">De meest recente waarschuwingen worden boven aan de lijst weergegeven, zodat u eerst de meest recente waarschuwingen kunt zien.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-142">The most recent alerts are shown at the top of the list helping you see the most recent alerts first.</span></span>

> [!NOTE]
> <span data-ttu-id="ff3b1-143">Op het moment van de lancering is in de wachtrij voor geïntegreerde waarschuwingen slechts 7 dagen aan Microsoft Defender voor Office 365-waarschuwingen beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-143">At the time of launch, the unified alerts queue will only have 7 days’ worth of Microsoft Defender for Office 365 alerts available.</span></span> <span data-ttu-id="ff3b1-144">De wachtrij blijft in de tijd worden opgebouwd.</span><span class="sxs-lookup"><span data-stu-id="ff3b1-144">The queue will continue to build over time.</span></span> <span data-ttu-id="ff3b1-145">Gebruik de waarschuwingenwachtrij in het Beveiligings- en compliancecentrum als u waarschuwingen wilt triagen vóór de start van de geïntegreerde [waarschuwingenwachtrij.](https://protection.office.com/viewalerts)</span><span class="sxs-lookup"><span data-stu-id="ff3b1-145">If you need to triage alerts prior to the launch of the unified alerts queue, use the alerts queue in the [Security and Compliance Center](https://protection.office.com/viewalerts).</span></span>


<span data-ttu-id="ff3b1-146">Op de bovenste navigatiebalk kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="ff3b1-146">On the top navigation, you can:</span></span>

- <span data-ttu-id="ff3b1-147">Filters toepassen</span><span class="sxs-lookup"><span data-stu-id="ff3b1-147">Apply filters</span></span>
- <span data-ttu-id="ff3b1-148">Kolommen aanpassen om kolommen toe te voegen of te verwijderen</span><span class="sxs-lookup"><span data-stu-id="ff3b1-148">Customize columns to add or remove columns</span></span>
- <span data-ttu-id="ff3b1-149">Gegevens exporteren</span><span class="sxs-lookup"><span data-stu-id="ff3b1-149">Export data</span></span>

<span data-ttu-id="ff3b1-150">U kunt waarschuwingen ook filteren op basis van verschillende criteria:</span><span class="sxs-lookup"><span data-stu-id="ff3b1-150">You can also filter alerts according to different criteria:</span></span>

- <span data-ttu-id="ff3b1-151">Ernst</span><span class="sxs-lookup"><span data-stu-id="ff3b1-151">Severity</span></span>
- <span data-ttu-id="ff3b1-152">Status</span><span class="sxs-lookup"><span data-stu-id="ff3b1-152">Status</span></span>
- <span data-ttu-id="ff3b1-153">Categorie</span><span class="sxs-lookup"><span data-stu-id="ff3b1-153">Category</span></span>
- <span data-ttu-id="ff3b1-154">Detectiebron</span><span class="sxs-lookup"><span data-stu-id="ff3b1-154">Detection source</span></span>
- <span data-ttu-id="ff3b1-155">Beleid</span><span class="sxs-lookup"><span data-stu-id="ff3b1-155">Policy</span></span>
- <span data-ttu-id="ff3b1-156">Beïnvloede activa</span><span class="sxs-lookup"><span data-stu-id="ff3b1-156">Impacted assets</span></span>
- <span data-ttu-id="ff3b1-157">Eerste activiteit</span><span class="sxs-lookup"><span data-stu-id="ff3b1-157">First activity</span></span>
- <span data-ttu-id="ff3b1-158">Laatste activiteit</span><span class="sxs-lookup"><span data-stu-id="ff3b1-158">Last activity</span></span>


<span data-ttu-id="ff3b1-159">Als u een onderzoek naar een incident wilt starten, leest [u Incidenten onderzoeken in Microsoft 365 Defender](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="ff3b1-159">To start an investigation on an incident, read [Investigate incidents in Microsoft 365 Defender](investigate-incidents.md)</span></span>
## <a name="see-also"></a><span data-ttu-id="ff3b1-160">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ff3b1-160">See also</span></span>

- [<span data-ttu-id="ff3b1-161">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="ff3b1-161">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="ff3b1-162">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="ff3b1-162">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="ff3b1-163">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="ff3b1-163">Manage incidents</span></span>](manage-incidents.md)
