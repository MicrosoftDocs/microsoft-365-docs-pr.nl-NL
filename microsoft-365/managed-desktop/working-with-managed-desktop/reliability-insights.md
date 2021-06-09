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
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739781"
---
# <a name="reliability-insights"></a><span data-ttu-id="8f92c-103">Inzichten in betrouwbaarheid</span><span class="sxs-lookup"><span data-stu-id="8f92c-103">Reliability insights</span></span>

<span data-ttu-id="8f92c-104">In deze weergave ziet u een overzicht van de status van uw beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="8f92c-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="8f92c-105">Als u betrouwbaarheidsgegevens wilt weergeven, selecteert u **het tabblad** Betrouwbaarheid.</span><span class="sxs-lookup"><span data-stu-id="8f92c-105">To view reliability data, select the **Reliability** tab.</span></span>


![Betrouwbaarheidsvenster: betrouwbaarheid op apparaten in de linkerbovenhoek, betrouwbaarheid in de tijdgrafiek in de rechterbovenhoek, de bovenste tabel met problemen aan de onderkant.](../../media/insights_reliability.png)

<span data-ttu-id="8f92c-108">De  sectie Betrouwbaarheid op verschillende apparaten biedt een beknopt overzicht van uw implementatie in de afgelopen 14 dagen door het percentage apparaten te rapporteren dat als 'gezond' wordt beschouwd en de gemiddelde tijd die is waargenomen sinds de laatste gerapporteerde fout.</span><span class="sxs-lookup"><span data-stu-id="8f92c-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="8f92c-109">De **grafiek Betrouwbaarheid in de** tijd aan de rechterkant meldt het aantal apparaten met kritieke fouten en het totale aantal waargenomen kritieke fouten in de tijd.</span><span class="sxs-lookup"><span data-stu-id="8f92c-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="8f92c-110">De **sectie Belangrijkste problemen** details specifieke gedetecteerde problemen die van invloed zijn op ten minste 5% van uw beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="8f92c-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="8f92c-111">Gerapporteerde details zijn:</span><span class="sxs-lookup"><span data-stu-id="8f92c-111">Reported details include:</span></span>

- <span data-ttu-id="8f92c-112">Het type probleem</span><span class="sxs-lookup"><span data-stu-id="8f92c-112">The type of issue</span></span>
    - <span data-ttu-id="8f92c-113">Toepassing loopt vast, waarbij een app niet meer werkt of onverwacht stopt</span><span class="sxs-lookup"><span data-stu-id="8f92c-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="8f92c-114">Toepassing blijft hangen, waarbij een toepassing niet meer reageert op invoer</span><span class="sxs-lookup"><span data-stu-id="8f92c-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="8f92c-115">Kritieke fouten, die optreden wanneer Windows een probleem heeft ondervonden waarvan het probleem niet kan worden hersteld</span><span class="sxs-lookup"><span data-stu-id="8f92c-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="8f92c-116">Het aantal apparaten dat door hetzelfde probleem wordt beïnvloed</span><span class="sxs-lookup"><span data-stu-id="8f92c-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="8f92c-117">Het percentage beheerde apparaten dat getal vertegenwoordigt</span><span class="sxs-lookup"><span data-stu-id="8f92c-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="8f92c-118">Het totale aantal exemplaren van het specifieke probleem</span><span class="sxs-lookup"><span data-stu-id="8f92c-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="8f92c-119">Het softwareonderdeel dat de oorzaak van het probleem lijkt te zijn</span><span class="sxs-lookup"><span data-stu-id="8f92c-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="8f92c-120">De categorie van het gedetecteerde probleem:</span><span class="sxs-lookup"><span data-stu-id="8f92c-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="8f92c-121">Browser (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="8f92c-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="8f92c-122">Onbekend (niet-Microsoft-onderdelen)</span><span class="sxs-lookup"><span data-stu-id="8f92c-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="8f92c-123">Stuurprogramma (audio, graphics of andere stuurprogramma's)</span><span class="sxs-lookup"><span data-stu-id="8f92c-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="8f92c-124">Productiviteit (Slack, G-Suites, Microsoft Office en de invoegtoepassingen of extensies, Teams)</span><span class="sxs-lookup"><span data-stu-id="8f92c-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="8f92c-125">Media -apps (afbeeldings-, muziek- of video-apps)</span><span class="sxs-lookup"><span data-stu-id="8f92c-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="8f92c-126">Beveiligingsonderdelen (Windows beveiligingsonderdelen)</span><span class="sxs-lookup"><span data-stu-id="8f92c-126">Security (Windows security components)</span></span>
- <span data-ttu-id="8f92c-127">De huidige status als Microsoft Managed Desktop Operations onderzoekt en herstelt het probleem</span><span class="sxs-lookup"><span data-stu-id="8f92c-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

