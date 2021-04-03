---
title: Overzicht van incidenten in Microsoft 365 Defender
description: Incidenten op verschillende apparaten, gebruikers en postvakken onderzoeken.
keywords: incidenten, waarschuwingen, onderzoeken, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: 6dd13c5f83d05be3c77e5f84608fb6aa5172d9a4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500926"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="0ecca-104">Overzicht van incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ecca-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0ecca-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0ecca-105">**Applies to:**</span></span>
- <span data-ttu-id="0ecca-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ecca-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="0ecca-107">Wilt u Microsoft 365 Defender ervaren?</span><span class="sxs-lookup"><span data-stu-id="0ecca-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="0ecca-108">U kunt het [evalueren in een testomgeving](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) of [uw pilotproject uitvoeren in een productieomgeving](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="0ecca-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>


<span data-ttu-id="0ecca-109">Incidenten zijn gebaseerd op gerelateerde waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="0ecca-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="0ecca-110">Waarschuwingen worden gemaakt wanneer er een schadelijke gebeurtenis of activiteit wordt gezien in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="0ecca-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="0ecca-111">Afzonderlijke waarschuwingen geven waardevolle aanwijzingen over een aan de hand van een aanval.</span><span class="sxs-lookup"><span data-stu-id="0ecca-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="0ecca-112">Bij aanvallen worden echter meestal verschillende vectoren en technieken gebruikt om een inbreuk uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="0ecca-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="0ecca-113">Het samenvlaaien van afzonderlijke aanwijzingen kan lastig en tijdrovend zijn.</span><span class="sxs-lookup"><span data-stu-id="0ecca-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="0ecca-114">In deze korte video wordt een overzicht gegeven van incidenten in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="0ecca-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="0ecca-115">Een incident is een verzameling gecorreleerde waarschuwingen die het verhaal van een aanval weergeven.</span><span class="sxs-lookup"><span data-stu-id="0ecca-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="0ecca-116">Schadelijke en verdachte gebeurtenissen die worden gevonden in verschillende apparaat-, gebruikers- en postvakentiteiten in het netwerk, worden automatisch samengevoegd door Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="0ecca-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="0ecca-117">Door gerelateerde waarschuwingen in een incident te groeperen, krijgen beveiligingsverdedigers een uitgebreide weergave van een aanval.</span><span class="sxs-lookup"><span data-stu-id="0ecca-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="0ecca-118">Beveiligingsverdedigers kunnen bijvoorbeeld zien waar de aanval is gestart, welke tactieken zijn gebruikt en hoe ver de aanval in het netwerk is gegaan.</span><span class="sxs-lookup"><span data-stu-id="0ecca-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="0ecca-119">Ze kunnen ook het bereik van de aanval zien, zoals het aantal apparaten, gebruikers en postvakken dat is beïnvloed, hoe ernstig de impact was en andere details over de betrokken entiteiten.</span><span class="sxs-lookup"><span data-stu-id="0ecca-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="0ecca-120">Als dit is ingeschakeld, kan Microsoft 365 Defender de afzonderlijke waarschuwingen automatisch onderzoeken en oplossen via automatisering en kunstmatige intelligentie.</span><span class="sxs-lookup"><span data-stu-id="0ecca-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="0ecca-121">Beveiligingsverdedigers kunnen ook aanvullende herstelstappen uitvoeren om de aanval rechtstreeks vanuit de incidentenweergave op te lossen.</span><span class="sxs-lookup"><span data-stu-id="0ecca-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="0ecca-122">Incidenten van de afgelopen 30 dagen worden weergegeven in de incidentwachtrij.</span><span class="sxs-lookup"><span data-stu-id="0ecca-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="0ecca-123">Van hieruit kunnen beveiligingsverdedigers zien welke incidenten prioriteit moeten krijgen op basis van risiconiveau en andere factoren.</span><span class="sxs-lookup"><span data-stu-id="0ecca-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="0ecca-124">Beveiligingsverdedigers kunnen incidenten ook een andere naam geven, deze toewijzen aan individuele analisten, tags classificeren en toevoegen aan incidenten voor een betere en meer aangepaste ervaring met incidentbeheer.</span><span class="sxs-lookup"><span data-stu-id="0ecca-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="0ecca-125">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0ecca-125">See also</span></span>
- [<span data-ttu-id="0ecca-126">Prioriteit geven aan incidenten</span><span class="sxs-lookup"><span data-stu-id="0ecca-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="0ecca-127">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="0ecca-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="0ecca-128">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="0ecca-128">Manage incidents</span></span>](manage-incidents.md)