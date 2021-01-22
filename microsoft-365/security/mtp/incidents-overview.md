---
title: Overzicht van incidenten in Microsoft 365 Defender
description: Onderzoek incidenten die zijn gezien voor apparaten, gebruikers en postvakken.
keywords: incidenten, waarschuwingen, onderzoeken, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
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
ms.openlocfilehash: 7fcbecddd5e8f83e9c78d6db90939fbfc2f2df07
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929280"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="f7137-104">Overzicht van incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7137-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f7137-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f7137-105">**Applies to:**</span></span>
- <span data-ttu-id="f7137-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7137-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="f7137-107">Wilt u ervaring met Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="f7137-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="f7137-108">U kunt [dit evalueren in een testomgeving](https://aka.ms/mtp-trial-lab) of uw [pilotproject in productie nemen.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="f7137-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="f7137-109">Incidenten zijn gebaseerd op gerelateerde waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="f7137-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="f7137-110">Er worden waarschuwingen gemaakt wanneer er een schadelijke gebeurtenis of activiteit wordt gezien op uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="f7137-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="f7137-111">Afzonderlijke waarschuwingen geven waardevolle aanwijzingen over een on-going aanval.</span><span class="sxs-lookup"><span data-stu-id="f7137-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="f7137-112">Aanvallen gebruiken echter meestal verschillende vectoren en technieken om een inbreuk uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="f7137-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="f7137-113">Het kan lastig en tijdrovend zijn om afzonderlijke aanwijzingen bij elkaar te zetten.</span><span class="sxs-lookup"><span data-stu-id="f7137-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="f7137-114">Deze korte video geeft een overzicht van incidenten met Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f7137-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="f7137-115">Een incident is een verzameling correleren waarschuwingen die het verhaal van een aanval be benden.</span><span class="sxs-lookup"><span data-stu-id="f7137-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="f7137-116">Kwaadaardige en verdachte gebeurtenissen die worden aangetroffen in verschillende entiteiten van apparaten, gebruikers en postvakken in het netwerk, worden automatisch samengevoegd door Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f7137-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="f7137-117">Door verwante waarschuwingen in een incident te groeperen, krijgen beveiligingsverdedigers een uitgebreide weergave van een aanval.</span><span class="sxs-lookup"><span data-stu-id="f7137-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="f7137-118">Zo kunnen beveiligingsverdedigers zien waar de aanval is begonnen, welke tactieken zijn gebruikt en hoe ver de aanval in het netwerk is gegaan.</span><span class="sxs-lookup"><span data-stu-id="f7137-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="f7137-119">Ze kunnen ook het bereik van de aanval zien, zoals het aantal apparaten, gebruikers en postvakken dat is beïnvloed, hoe ernstig de impact was en andere details over betrokken entiteiten.</span><span class="sxs-lookup"><span data-stu-id="f7137-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="f7137-120">Indien ingeschakeld, kan Microsoft 365 Defender de afzonderlijke waarschuwingen automatisch onderzoeken en oplossen via automatisering en kunstmatige intelligentie.</span><span class="sxs-lookup"><span data-stu-id="f7137-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="f7137-121">Beveiligingsverdedigers kunnen ook aanvullende herstelstappen uitvoeren om de aanval rechtstreeks vanuit de weergave incidenten op te lossen.</span><span class="sxs-lookup"><span data-stu-id="f7137-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="f7137-122">Incidenten van de afgelopen 30 dagen worden weergegeven in de wachtrij voor incidenten.</span><span class="sxs-lookup"><span data-stu-id="f7137-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="f7137-123">Van hieruit kunnen beveiligingsverdedigers zien welke incidenten prioriteit moeten krijgen op basis van risiconiveau en andere factoren.</span><span class="sxs-lookup"><span data-stu-id="f7137-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="f7137-124">Beveiligingsverdedigers kunnen ook incidenten hernoemen, deze toewijzen aan afzonderlijke analisten, classificeren en labels toevoegen aan incidenten voor een betere en meer aangepaste ervaring met het beheer van incidenten.</span><span class="sxs-lookup"><span data-stu-id="f7137-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="f7137-125">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f7137-125">See also</span></span>
- [<span data-ttu-id="f7137-126">Prioriteit geven aan incidenten</span><span class="sxs-lookup"><span data-stu-id="f7137-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="f7137-127">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="f7137-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="f7137-128">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="f7137-128">Manage incidents</span></span>](manage-incidents.md)
