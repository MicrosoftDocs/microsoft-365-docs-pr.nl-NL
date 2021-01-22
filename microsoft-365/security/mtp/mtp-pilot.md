---
title: Uw testfase microsoft 365 Defender-project uitvoeren
description: Voer uw testfase microsoft 365 Defender-project uit in productie om zo effectief de voordelen en acceptatie van Microsoft 365 Defender te bepalen.
keywords: Microsoft Threat Protection-pilot, voer pilot Microsoft Threat Protection-project uit, evalueer Microsoft Threat Protection in productie, Microsoft Threat Protection-pilotproject, cyberbeveiliging, geavanceerde permanente bedreiging, bedrijfsbeveiliging, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerd zoeken
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9c0635058539e464a76f1720f041c205a05fa9b2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933028"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="4d4f6-104">Uw testfase microsoft 365 Defender-project uitvoeren</span><span class="sxs-lookup"><span data-stu-id="4d4f6-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4d4f6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4d4f6-105">**Applies to:**</span></span>
- <span data-ttu-id="4d4f6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d4f6-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="4d4f6-107">Deze handleiding helpt u bij het uitvoeren van een pilotproject door pointers te bieden om ervoor te zorgen dat u over een goed gestructureerd plan kunt beschikken, om u te begeleiden door de functie voor de aanvalsversleuteling te gebruiken en ten slotte de test af te sluiten met belangrijke take-aways om de resultaten te bekijken en vast te stellen.</span><span class="sxs-lookup"><span data-stu-id="4d4f6-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Fasen in een Microsoft 365 Defender-testfase](../../media/pilotphases.png)


<span data-ttu-id="4d4f6-109">Het uitvoeren van een testfase helpt u om effectief vast te stellen wat de voordelen zijn van het gebruik van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4d4f6-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="4d4f6-110">Voordat u Microsoft 365 Defender inschakelen in uw productieomgeving en uw use cases start, kunt u het beste plannen welke taken u moet uitvoeren voor uw pilotproject en de criteria voor succes instellen.</span><span class="sxs-lookup"><span data-stu-id="4d4f6-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="4d4f6-111">Dit playbook gebruiken in de testfase</span><span class="sxs-lookup"><span data-stu-id="4d4f6-111">How to use this pilot playbook</span></span>

<span data-ttu-id="4d4f6-112">Deze handleiding bevat een overzicht van Microsoft 365 Defender en stapsgewijste instructies voor het instellen van uw pilotproject.</span><span class="sxs-lookup"><span data-stu-id="4d4f6-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="4d4f6-113">Microsoft 365 Defender is een geïntegreerde pre- en post-breach Enterprise Defense Suite die ingebouwde beveiliging, detectie, preventie, onderzoek en antwoorden voor eindpunten, identiteiten, e-mail en toepassingen coördineren om geïntegreerde beveiliging tegen geavanceerde aanvallen te bieden.</span><span class="sxs-lookup"><span data-stu-id="4d4f6-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="4d4f6-114">Dit doet u door de volgende mogelijkheden te combineren en te verbeteren in één beveiligingsoplossing:</span><span class="sxs-lookup"><span data-stu-id="4d4f6-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="4d4f6-115">Microsoft Defender voor eindpunt, de nieuwe naam voor Microsoft Defender Advanced Threat Protection (eindpunten)</span><span class="sxs-lookup"><span data-stu-id="4d4f6-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="4d4f6-116">Microsoft Defender voor Office 365, de nieuwe naam voor Office 365 ATP (e-mail)</span><span class="sxs-lookup"><span data-stu-id="4d4f6-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="4d4f6-117">Microsoft Defender for Identity, de nieuwe naam voor Azure ATP (identity)</span><span class="sxs-lookup"><span data-stu-id="4d4f6-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="4d4f6-118">Beveiliging van Microsoft Cloud-apps (apps)</span><span class="sxs-lookup"><span data-stu-id="4d4f6-118">Microsoft Cloud App Security (apps)</span></span>

![Afbeelding of_Microsoft 365 Defender-oplossing voor gebruikers, Microsoft Defender for Identity, voor eindpunten Microsoft Defender voor eindpunt, voor cloud-apps, Microsoft Cloud App-beveiliging en voor gegevens, Microsoft Defender voor Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="4d4f6-120">Met de geïntegreerde Microsoft 365 Defender-oplossing kunnen beveiligingsprofessionals samenwerken aan de bedreigingssignalen die Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365, Microsoft Defender voor identiteit en Microsoft Cloud App Security ontvangen, en bepalen wat het volledige bereik en de invloed van de bedreiging zijn, hoe de bedreiging is ingevoerd in de omgeving, wat de gevolgen zijn en hoe deze op dit moment van invloed is op de organisatie.</span><span class="sxs-lookup"><span data-stu-id="4d4f6-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="4d4f6-121">Microsoft 365 Defender onderneemt automatische acties om de aanval en postvakken, eindpunten en gebruikersidentiteiten te voorkomen of te stoppen.</span><span class="sxs-lookup"><span data-stu-id="4d4f6-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="4d4f6-122">Zie het [overzicht van Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4d4f6-122">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>



<span data-ttu-id="4d4f6-123">De volgende voorbeeldtijdlijn varieert afhankelijk van de juiste resources in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="4d4f6-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="4d4f6-124">Sommige detecties en werkstromen hebben mogelijk meer leertijd nodig dan de andere.</span><span class="sxs-lookup"><span data-stu-id="4d4f6-124">Some detections and workflows might need more learning time than the others.</span></span>

![Voorbeeldtijdlijn in een Microsoft 365 Defender-testfase](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="4d4f6-126">Voor optimale resultaten volgt u de instructies van de testfase zo goed mogelijk.</span><span class="sxs-lookup"><span data-stu-id="4d4f6-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="4d4f6-127">Fases van playbook pilot</span><span class="sxs-lookup"><span data-stu-id="4d4f6-127">Pilot playbook phases</span></span> 

<span data-ttu-id="4d4f6-128">Een Microsoft 365 Defender-testfase bestaat uit vier fasen:</span><span class="sxs-lookup"><span data-stu-id="4d4f6-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="4d4f6-129">Fase</span><span class="sxs-lookup"><span data-stu-id="4d4f6-129">Phase</span></span> | <span data-ttu-id="4d4f6-130">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="4d4f6-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="4d4f6-131">Planning</span><span class="sxs-lookup"><span data-stu-id="4d4f6-131">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="4d4f6-132">~ 1 dag</span><span class="sxs-lookup"><span data-stu-id="4d4f6-132">~ 1 day</span></span>| <span data-ttu-id="4d4f6-133">Lees waar u aan moet denken voordat u een Microsoft 365 Defender-testproject gaat uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="4d4f6-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="4d4f6-134">- Bereik</span><span class="sxs-lookup"><span data-stu-id="4d4f6-134">- Scope</span></span> <br> <span data-ttu-id="4d4f6-135">- Use cases</span><span class="sxs-lookup"><span data-stu-id="4d4f6-135">- Use cases</span></span> <br><span data-ttu-id="4d4f6-136">- Vereisten</span><span class="sxs-lookup"><span data-stu-id="4d4f6-136">- Requirements</span></span> <br><span data-ttu-id="4d4f6-137">- Testplan</span><span class="sxs-lookup"><span data-stu-id="4d4f6-137">- Test plan</span></span> <br> <span data-ttu-id="4d4f6-138">- Criteria voor succes</span><span class="sxs-lookup"><span data-stu-id="4d4f6-138">- Success criteria</span></span> <br> <span data-ttu-id="4d4f6-139">- Scorecard</span><span class="sxs-lookup"><span data-stu-id="4d4f6-139">- Scorecard</span></span> 
| [<span data-ttu-id="4d4f6-140">Voorbereiding</span><span class="sxs-lookup"><span data-stu-id="4d4f6-140">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="4d4f6-141">~2 dagen</span><span class="sxs-lookup"><span data-stu-id="4d4f6-141">~2 days</span></span>|  <span data-ttu-id="4d4f6-142">Krijg toegang tot het Microsoft 365-beveiligingscentrum om uw Microsoft 365 Defender-testomgeving in te stellen.</span><span class="sxs-lookup"><span data-stu-id="4d4f6-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="4d4f6-143">U wordt begeleid bij het volgende:</span><span class="sxs-lookup"><span data-stu-id="4d4f6-143">You'll be guided to:</span></span><br><br><span data-ttu-id="4d4f6-144">- Identificeer belanghebbenden en zoek het aanmelden voor uw testfase</span><span class="sxs-lookup"><span data-stu-id="4d4f6-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="4d4f6-145">- Aandachtspunten voor de omgeving</span><span class="sxs-lookup"><span data-stu-id="4d4f6-145">- Environment considerations</span></span> <br><span data-ttu-id="4d4f6-146">- Access</span><span class="sxs-lookup"><span data-stu-id="4d4f6-146">- Access</span></span> <br><span data-ttu-id="4d4f6-147">- Azure Active Directory instellen</span><span class="sxs-lookup"><span data-stu-id="4d4f6-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="4d4f6-148">- Configuratieorder</span><span class="sxs-lookup"><span data-stu-id="4d4f6-148">- Configuration order</span></span> <br> <span data-ttu-id="4d4f6-149">- Aanmelden voor de proefversie van Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4d4f6-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="4d4f6-150">- Domein configureren</span><span class="sxs-lookup"><span data-stu-id="4d4f6-150">- Configure domain</span></span> <br><span data-ttu-id="4d4f6-151">- Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="4d4f6-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="4d4f6-152">- Voltooi de installatiewizard in de portal</span><span class="sxs-lookup"><span data-stu-id="4d4f6-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="4d4f6-153">Aanvalssyrulatie</span><span class="sxs-lookup"><span data-stu-id="4d4f6-153">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="4d4f6-154">~2 dagen</span><span class="sxs-lookup"><span data-stu-id="4d4f6-154">~2 days</span></span>| <span data-ttu-id="4d4f6-155">Als u een aanval wilt simuleren, kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="4d4f6-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="4d4f6-156">- De vereisten voor de testomgeving controleren</span><span class="sxs-lookup"><span data-stu-id="4d4f6-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="4d4f6-157">- Deulatie uitvoeren</span><span class="sxs-lookup"><span data-stu-id="4d4f6-157">-  Run the simulation</span></span> <br><span data-ttu-id="4d4f6-158">- Een incident onderzoeken</span><span class="sxs-lookup"><span data-stu-id="4d4f6-158">- Investigate an incident</span></span> <br><span data-ttu-id="4d4f6-159">- het incident oplossen</span><span class="sxs-lookup"><span data-stu-id="4d4f6-159">- resolve the incident</span></span> 
| [<span data-ttu-id="4d4f6-160">Afsluiting en samenvatting</span><span class="sxs-lookup"><span data-stu-id="4d4f6-160">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="4d4f6-161">~ 1 dag</span><span class="sxs-lookup"><span data-stu-id="4d4f6-161">~ 1 day</span></span>| <span data-ttu-id="4d4f6-162">Wanneer u het einde van het proces hebt bereikt, kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="4d4f6-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="4d4f6-163">- De uiteindelijke uitvoer door</span><span class="sxs-lookup"><span data-stu-id="4d4f6-163">- Go through your final output</span></span><br><span data-ttu-id="4d4f6-164">- Presenteert uw uitvoer aan uw belanghebbenden</span><span class="sxs-lookup"><span data-stu-id="4d4f6-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="4d4f6-165">- Feedback geven</span><span class="sxs-lookup"><span data-stu-id="4d4f6-165">- Provide feedback</span></span> <br><span data-ttu-id="4d4f6-166">- Neem de volgende stappen</span><span class="sxs-lookup"><span data-stu-id="4d4f6-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="4d4f6-167">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="4d4f6-167">Next step</span></span>
|[<span data-ttu-id="4d4f6-168">Planningsfase</span><span class="sxs-lookup"><span data-stu-id="4d4f6-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="4d4f6-169">Uw Microsoft 365 Defender-pilotproject plannen</span><span class="sxs-lookup"><span data-stu-id="4d4f6-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
