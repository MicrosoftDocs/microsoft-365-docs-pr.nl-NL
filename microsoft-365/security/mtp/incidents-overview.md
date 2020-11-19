---
title: Overzicht van incidenten in Microsoft 365 Defender
description: Onderzoek gebeurtenissen die worden weergegeven op een apparaat, gebruikers en postvakken.
keywords: incidenten, waarschuwingen, onderzoek, correlatie, aanval, computers, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 6149b6f128b3c96d2338e325caa8df835c292b13
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357609"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="62fba-104">Overzicht van incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62fba-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="62fba-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="62fba-105">**Applies to:**</span></span>
- <span data-ttu-id="62fba-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62fba-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="62fba-107">Wilt u Microsoft 365 Defender ervaren?</span><span class="sxs-lookup"><span data-stu-id="62fba-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="62fba-108">U kunt [deze beoordelen in een testomgeving](https://aka.ms/mtp-trial-lab) of een [proefproject uitvoeren op de productie](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="62fba-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="62fba-109">Incidenten zijn gebaseerd op verwante meldingen.</span><span class="sxs-lookup"><span data-stu-id="62fba-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="62fba-110">Er worden waarschuwingen gemaakt wanneer een schadelijke gebeurtenis of activiteit op uw netwerk wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="62fba-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="62fba-111">Afzonderlijke waarschuwingen zorgen voor nuttige aanwijzingen over een voortdurende aanval.</span><span class="sxs-lookup"><span data-stu-id="62fba-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="62fba-112">Een aanval maakt echter meestal uiteenlopende vectoren en technieken om een schending te voeren.</span><span class="sxs-lookup"><span data-stu-id="62fba-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="62fba-113">Piecing afzonderlijk aanvullen van een ogenblik kan lastig en tijdrovend zijn.</span><span class="sxs-lookup"><span data-stu-id="62fba-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="62fba-114">Met deze korte video krijgt u een overzicht van incidenten in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="62fba-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="62fba-115">Een incident is een verzameling gerelateerde waarschuwingen die het verhaal van een aanval vormen.</span><span class="sxs-lookup"><span data-stu-id="62fba-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="62fba-116">Schadelijke en verdachte gebeurtenissen die zich in verschillende apparaten, gebruikers en Postvak eenheden in het netwerk bevinden, worden automatisch samengevoegd met Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="62fba-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="62fba-117">Het groeperen van waarschuwingen in een incident biedt beveiligings bescherming tegen een uitgebreide weergave van een aanval.</span><span class="sxs-lookup"><span data-stu-id="62fba-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="62fba-118">Beveiligings bescherming van een aanval kan bijvoorbeeld zien waar de aanval is gestart, welke tactieken werden gebruikt en hoe ver de aanval in het netwerk is verdwenen.</span><span class="sxs-lookup"><span data-stu-id="62fba-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="62fba-119">Ze kunnen ook het reikwijdte van de aanval zien, zoals het aantal apparaten, gebruikers en postvakken, wat van invloed is op de impact van de impact, en andere informatie over de beïnvloede entiteiten.</span><span class="sxs-lookup"><span data-stu-id="62fba-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="62fba-120">Als deze functie is ingeschakeld, kan Microsoft 365 Defender automatisch de afzonderlijke waarschuwingen via automatisering en de ondersteuning van kunstmatige informatie achterhalen.</span><span class="sxs-lookup"><span data-stu-id="62fba-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="62fba-121">Beveiligings beschermters kunnen ook extra herstel stappen uitvoeren om de aanval direct in de weergave incidenten op te lossen.</span><span class="sxs-lookup"><span data-stu-id="62fba-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="62fba-122">Incidenten in de afgelopen 30 dagen worden weergegeven in de incident wachtrij.</span><span class="sxs-lookup"><span data-stu-id="62fba-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="62fba-123">Van hieruit kan beveiligings bescherming zien welke incidenten op basis van risiconiveau en andere factoren op basis van risiconiveau gelden.</span><span class="sxs-lookup"><span data-stu-id="62fba-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="62fba-124">Beveiligings beschermings problemen kunnen ook de naam van een voorval wijzigen, ze toewijzen aan afzonderlijke analisten, classificeren en labels aan incidenten toevoegen voor een betere en meer aangepaste ervaring voor het beheren van incidenten.</span><span class="sxs-lookup"><span data-stu-id="62fba-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="62fba-125">Zie ook</span><span class="sxs-lookup"><span data-stu-id="62fba-125">See also</span></span>
- [<span data-ttu-id="62fba-126">Prioriteit geven aan incidenten</span><span class="sxs-lookup"><span data-stu-id="62fba-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="62fba-127">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="62fba-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="62fba-128">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="62fba-128">Manage incidents</span></span>](manage-incidents.md)
