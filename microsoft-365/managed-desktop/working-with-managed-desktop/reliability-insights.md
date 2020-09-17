---
title: Inzichten in betrouwbaarheid
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950340"
---
# <a name="reliability-insights"></a><span data-ttu-id="e338d-103">Inzichten in betrouwbaarheid</span><span class="sxs-lookup"><span data-stu-id="e338d-103">Reliability insights</span></span>

<span data-ttu-id="e338d-104">Deze weergave bevat een overzicht van de status van uw beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="e338d-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="e338d-105">Als u betrouwbaarheids gegevens wilt weergeven, selecteert u het tabblad **betrouwbaarheid** .</span><span class="sxs-lookup"><span data-stu-id="e338d-105">To view reliability data, select the **Reliability** tab.</span></span>


![Deelvenster betrouwbaarheid: betrouwbaarheid van de verschillende apparaten in de linkerbovenhoek, de betrouwbaarheid van de grafiek in de rechterbovenhoek en de tabel belangrijkste problemen onder aan de onderkant.](../../media/insights_reliability.png)

<span data-ttu-id="e338d-108">De sectie **betrouwbaarheid** van de apparaten biedt een beknopt overzicht van de afgelopen 14 dagen door het percentage van de ondergebrachte apparatuur te rapporteren, en de gemiddelde tijd sinds de laatste gerapporteerde fout.</span><span class="sxs-lookup"><span data-stu-id="e338d-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="e338d-109">In de rechterbenedenhoek van de grafiek **betrouwbaarheid** wordt het aantal apparaten met een kritieke fout en het totale aantal nageleefde kritieke fouten in de loop van de tijd gerapporteerd.</span><span class="sxs-lookup"><span data-stu-id="e338d-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="e338d-110">In de sectie met **belangrijkste problemen** vindt u specifieke problemen die van invloed zijn op ten minste 5% van uw beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="e338d-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="e338d-111">Gerapporteerde informatie omvat:</span><span class="sxs-lookup"><span data-stu-id="e338d-111">Reported details include:</span></span>

- <span data-ttu-id="e338d-112">Het type probleem</span><span class="sxs-lookup"><span data-stu-id="e338d-112">The type of issue</span></span>
    - <span data-ttu-id="e338d-113">Toepassing loopt vast, waarbij een app niet meer werkt of niet meer verwacht</span><span class="sxs-lookup"><span data-stu-id="e338d-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="e338d-114">Toepassing loopt vast, waarbij een toepassing niet meer reageert op invoer</span><span class="sxs-lookup"><span data-stu-id="e338d-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="e338d-115">Kritieke fouten die zich voordoen wanneer Windows een probleem voordeed dat niet kan worden hersteld</span><span class="sxs-lookup"><span data-stu-id="e338d-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="e338d-116">Het aantal apparaten waarop hetzelfde probleem optreedt</span><span class="sxs-lookup"><span data-stu-id="e338d-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="e338d-117">Het percentage beheerde apparaten dat een getal voorstelt</span><span class="sxs-lookup"><span data-stu-id="e338d-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="e338d-118">Het totale aantal exemplaren van een specifiek probleem</span><span class="sxs-lookup"><span data-stu-id="e338d-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="e338d-119">De softwarecomponent die de oorzaak is van het probleem</span><span class="sxs-lookup"><span data-stu-id="e338d-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="e338d-120">De categorie van het gevonden probleem:</span><span class="sxs-lookup"><span data-stu-id="e338d-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="e338d-121">Browser (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="e338d-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="e338d-122">Onbekend (niet-Microsoft-onderdelen)</span><span class="sxs-lookup"><span data-stu-id="e338d-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="e338d-123">Stuurprogramma (audio, graphics en andere Stuurprogramma's)</span><span class="sxs-lookup"><span data-stu-id="e338d-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="e338d-124">Productiviteit (marge, G-suites, Microsoft Office en de bijbehorende invoegtoepassingen of uitbreidingen, teams)</span><span class="sxs-lookup"><span data-stu-id="e338d-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="e338d-125">Media (afbeelding, muziek of video-apps)</span><span class="sxs-lookup"><span data-stu-id="e338d-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="e338d-126">Beveiliging (beveiligingsonderdelen van Windows)</span><span class="sxs-lookup"><span data-stu-id="e338d-126">Security (Windows security components)</span></span>
- <span data-ttu-id="e338d-127">De huidige status als door Microsoft beheerde bureaublad bewerkingen wordt het probleem onderzocht en hersteld.</span><span class="sxs-lookup"><span data-stu-id="e338d-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

