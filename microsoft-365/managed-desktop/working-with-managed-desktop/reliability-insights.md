---
title: Inzichten over betrouwbaarheid
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b7f56a64f1846676f458f7b3ddb210e84b9ca8f7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806860"
---
# <a name="reliability-insights"></a><span data-ttu-id="5a408-103">Inzichten over betrouwbaarheid</span><span class="sxs-lookup"><span data-stu-id="5a408-103">Reliability insights</span></span>

<span data-ttu-id="5a408-104">In deze weergave vindt u een statusoverzicht van uw beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="5a408-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="5a408-105">Als u betrouwbaarheidsgegevens wilt weergeven, selecteert u het tabblad **Betrouwbaarheid.**</span><span class="sxs-lookup"><span data-stu-id="5a408-105">To view reliability data, select the **Reliability** tab.</span></span>


![Betrouwbaarheidsvenster: betrouwbaarheid op apparaten linksboven, betrouwbaarheid in de tijdgrafiek rechtsboven, bovenste problemen tabel aan de onderkant.](../../media/insights_reliability.png)

<span data-ttu-id="5a408-108">De sectie **Betrouwbaarheid voor verschillende apparaten** biedt een snelle statussamenvatting van uw implementatie in de afgelopen 14 dagen door het percentage apparaten te rapporteren dat als "gezond" wordt beschouwd en de gemiddelde tijd die wordt waargenomen sinds de laatste gemelde storing.</span><span class="sxs-lookup"><span data-stu-id="5a408-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="5a408-109">De grafiek **Betrouwbaarheid na verloop** van tijd aan de rechterkant rapporteert het aantal apparaten met kritieke fouten en het totale aantal waargenomen kritieke fouten in de tijd.</span><span class="sxs-lookup"><span data-stu-id="5a408-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="5a408-110">In de sectie **Topproblemen** worden specifieke gedetecteerde problemen beschreven die ten minste 5% van uw beheerde apparaten beïnvloeden.</span><span class="sxs-lookup"><span data-stu-id="5a408-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="5a408-111">Gerapporteerde details zijn onder andere:</span><span class="sxs-lookup"><span data-stu-id="5a408-111">Reported details include:</span></span>

- <span data-ttu-id="5a408-112">Het type probleem</span><span class="sxs-lookup"><span data-stu-id="5a408-112">The type of issue</span></span>
    - <span data-ttu-id="5a408-113">Toepassingscrashes, waarbij een app niet meer functioneert of onverwacht stopt</span><span class="sxs-lookup"><span data-stu-id="5a408-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="5a408-114">Toepassing hangt, waarbij een toepassing niet meer reageert op invoer</span><span class="sxs-lookup"><span data-stu-id="5a408-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="5a408-115">Kritieke fouten die optreden wanneer Windows een probleem heeft ondervonden waarvan het niet kan herstellen</span><span class="sxs-lookup"><span data-stu-id="5a408-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="5a408-116">Het aantal apparaten dat door hetzelfde probleem wordt getroffen</span><span class="sxs-lookup"><span data-stu-id="5a408-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="5a408-117">Het percentage beheerde apparaten dat aantal vertegenwoordigt</span><span class="sxs-lookup"><span data-stu-id="5a408-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="5a408-118">Het totale aantal gebeurtenissen van het specifieke probleem</span><span class="sxs-lookup"><span data-stu-id="5a408-118">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="5a408-119">De softwarecomponent die de bron van het probleem lijkt te zijn</span><span class="sxs-lookup"><span data-stu-id="5a408-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="5a408-120">De categorie van het gedetecteerde probleem:</span><span class="sxs-lookup"><span data-stu-id="5a408-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="5a408-121">Browser (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="5a408-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="5a408-122">Onbekend (niet-Microsoft-componenten)</span><span class="sxs-lookup"><span data-stu-id="5a408-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="5a408-123">Stuurprogramma (audio, afbeeldingen of andere stuurprogramma's)</span><span class="sxs-lookup"><span data-stu-id="5a408-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="5a408-124">Productiviteit (Slack, G-Suites, Microsoft Office en de add-ons of extensies, Teams)</span><span class="sxs-lookup"><span data-stu-id="5a408-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="5a408-125">Media (afbeeldingen, muziek of video-apps</span><span class="sxs-lookup"><span data-stu-id="5a408-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="5a408-126">Beveiliging (Windows-beveiligingscomponenten)</span><span class="sxs-lookup"><span data-stu-id="5a408-126">Security (Windows security components)</span></span>
- <span data-ttu-id="5a408-127">De huidige status van Microsoft Managed Desktop Operations onderzoekt en herstelt het probleem</span><span class="sxs-lookup"><span data-stu-id="5a408-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

