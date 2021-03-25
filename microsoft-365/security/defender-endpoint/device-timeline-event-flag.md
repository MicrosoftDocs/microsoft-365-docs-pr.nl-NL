---
title: Gebeurtenisvlaggen van Microsoft Defender voor eindpuntapparaat
description: Gebeurtenisvlaggen van Microsoft Defender voor eindpuntapparaat gebruiken om
keywords: Tijdlijn van Het Apparaat van Defender voor Eindpunt, gebeurtenisvlaggen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165151"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a><span data-ttu-id="f6b00-104">Gebeurtenisvlaggen van Microsoft Defender voor eindpuntapparaat</span><span class="sxs-lookup"><span data-stu-id="f6b00-104">Microsoft Defender for Endpoint device timeline event flags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f6b00-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f6b00-105">**Applies to:**</span></span>
- [<span data-ttu-id="f6b00-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="f6b00-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f6b00-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6b00-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f6b00-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f6b00-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f6b00-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f6b00-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="f6b00-110">Gebeurtenisvlaggen in de tijdlijn van het Defender for Endpoint-apparaat helpen u specifieke gebeurtenissen te filteren en te organiseren wanneer u mogelijke aanvallen onderzoekt.</span><span class="sxs-lookup"><span data-stu-id="f6b00-110">Event flags in the Defender for Endpoint device timeline help you filter and organize specific events when you're  investigate potential attacks.</span></span>

<span data-ttu-id="f6b00-111">De tijdlijn van het Apparaat van Defender voor Eindpunt biedt een chronologische weergave van de gebeurtenissen en bijbehorende waarschuwingen die op een apparaat worden waargenomen.</span><span class="sxs-lookup"><span data-stu-id="f6b00-111">The Defender for Endpoint device timeline provides a chronological view of the events and associated alerts observed on a device.</span></span> <span data-ttu-id="f6b00-112">Deze lijst met gebeurtenissen biedt volledige zichtbaarheid in gebeurtenissen, bestanden en IP-adressen die op het apparaat worden waargenomen.</span><span class="sxs-lookup"><span data-stu-id="f6b00-112">This list of events provides full visibility into any events, files, and IP addresses observed on the device.</span></span> <span data-ttu-id="f6b00-113">De lijst kan soms lang zijn.</span><span class="sxs-lookup"><span data-stu-id="f6b00-113">The list can sometimes be lengthy.</span></span> <span data-ttu-id="f6b00-114">Gebeurtenisvlaggen van apparaattijdlijn helpen u bij het bijhouden van gebeurtenissen die gerelateerd kunnen zijn.</span><span class="sxs-lookup"><span data-stu-id="f6b00-114">Device timeline event flags help you track events that could be related.</span></span> 

<span data-ttu-id="f6b00-115">Nadat u een apparaattijdlijn hebt doorgetrokken, kunt u de specifieke gebeurtenissen sorteren, filteren en exporteren die u hebt gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="f6b00-115">After you've gone through a device timeline, you can sort, filter, and export the specific events that you flagged.</span></span>

<span data-ttu-id="f6b00-116">Terwijl u door de tijdlijn van het apparaat navigeert, kunt u zoeken en filteren op specifieke gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="f6b00-116">While navigating the device timeline, you can search and filter for specific events.</span></span> <span data-ttu-id="f6b00-117">U kunt gebeurtenisvlaggen instellen op:</span><span class="sxs-lookup"><span data-stu-id="f6b00-117">You can set event flags by:</span></span> 

- <span data-ttu-id="f6b00-118">De belangrijkste gebeurtenissen markeren</span><span class="sxs-lookup"><span data-stu-id="f6b00-118">Highlighting the most important events</span></span> 
- <span data-ttu-id="f6b00-119">Gebeurtenissen markeren die diep moeten worden gedoken</span><span class="sxs-lookup"><span data-stu-id="f6b00-119">Marking events that requires deep dive</span></span> 
- <span data-ttu-id="f6b00-120">Een tijdlijn voor een schone inbreuk maken</span><span class="sxs-lookup"><span data-stu-id="f6b00-120">Building a clean breach timeline</span></span>



## <a name="flag-an-event"></a><span data-ttu-id="f6b00-121">Een vlag voor een gebeurtenis markeren</span><span class="sxs-lookup"><span data-stu-id="f6b00-121">Flag an event</span></span>
1. <span data-ttu-id="f6b00-122">De gebeurtenis zoeken die u wilt markeren</span><span class="sxs-lookup"><span data-stu-id="f6b00-122">Find the event that you want to flag</span></span>
2. <span data-ttu-id="f6b00-123">Klik op het vlagpictogram in de kolom Vlag.</span><span class="sxs-lookup"><span data-stu-id="f6b00-123">Click the flag icon in the Flag column.</span></span> 
<span data-ttu-id="f6b00-124">![Afbeelding van apparaattijdlijnvlag](images/device-flags.png)</span><span class="sxs-lookup"><span data-stu-id="f6b00-124">![Image of device timeline flag](images/device-flags.png)</span></span>

## <a name="view-flagged-events"></a><span data-ttu-id="f6b00-125">Gebeurtenissen met vlag weergeven</span><span class="sxs-lookup"><span data-stu-id="f6b00-125">View flagged events</span></span>  
1. <span data-ttu-id="f6b00-126">Schakel in de **sectie Tijdlijnfilters** **gemarkeerde gebeurtenissen in.**</span><span class="sxs-lookup"><span data-stu-id="f6b00-126">In the timeline **Filters** section, enable **Flagged events**.</span></span>
2. <span data-ttu-id="f6b00-127">Klik op **Toepassen**.</span><span class="sxs-lookup"><span data-stu-id="f6b00-127">Click **Apply**.</span></span> <span data-ttu-id="f6b00-128">Alleen gebeurtenissen met vlag worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f6b00-128">Only flagged events are displayed.</span></span>
<span data-ttu-id="f6b00-129">U kunt extra filters toepassen door op de tijdbalk te klikken.</span><span class="sxs-lookup"><span data-stu-id="f6b00-129">You can apply additional filters by clicking on the time bar.</span></span> <span data-ttu-id="f6b00-130">Hiermee worden alleen gebeurtenissen vóór de gebeurtenis met vlag weer te geven.</span><span class="sxs-lookup"><span data-stu-id="f6b00-130">This will only show events prior to the flagged event.</span></span>  
<span data-ttu-id="f6b00-131">![Afbeelding van apparaattijdlijnvlag met filter op](images/device-flag-filter.png)</span><span class="sxs-lookup"><span data-stu-id="f6b00-131">![Image of device timeline flag with filter on](images/device-flag-filter.png)</span></span>
