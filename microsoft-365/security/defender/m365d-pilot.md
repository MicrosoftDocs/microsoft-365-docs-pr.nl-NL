---
title: Uw pilot Microsoft 365 Defender-project uitvoeren
description: Voer uw pilot Microsoft 365 Defender-project in productie om de voordelen en acceptatie van Microsoft 365 Defender effectief te bepalen.
keywords: Microsoft 365 Defender pilot, run pilot Microsoft 365 Defender project, evaluate Microsoft 365 Defender in production, Microsoft 365 Defender pilot project, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 3219b329c53c32e02cd29acdd41a48cd93b2e8bb
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930509"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="a7cca-104">Uw pilot Microsoft 365 Defender-project uitvoeren</span><span class="sxs-lookup"><span data-stu-id="a7cca-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a7cca-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a7cca-105">**Applies to:**</span></span>
- <span data-ttu-id="a7cca-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7cca-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="a7cca-107">Deze handleiding helpt u bij het uitvoeren van een pilotproject door aanwijzers te geven om ervoor te zorgen dat u een goed gestructureerd plan hebt, u begeleidt bij het gebruik van de functie aanvalssimulatie en de pilot ten slotte afsluit met belangrijke take-aways om na te denken over en de resultaten te documenteren.</span><span class="sxs-lookup"><span data-stu-id="a7cca-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Fasen in het uitvoeren van een Microsoft 365 Defender-pilot](../../media/pilotphases.png)


<span data-ttu-id="a7cca-109">Met het uitvoeren van een pilot kunt u effectief bepalen wat het voordeel is van het Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a7cca-109">Running a pilot helps you effectively determine the benefit of adopting Microsoft 365 Defender.</span></span> <span data-ttu-id="a7cca-110">Voordat u Microsoft 365 Defender in uw productieomgeving inschakelen en uw gebruiksgevallen start, kunt u het beste de taken voor uw pilotproject bepalen en de succescriteria instellen.</span><span class="sxs-lookup"><span data-stu-id="a7cca-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="a7cca-111">Deze test playbook gebruiken</span><span class="sxs-lookup"><span data-stu-id="a7cca-111">How to use this pilot playbook</span></span>

<span data-ttu-id="a7cca-112">Deze handleiding bevat een overzicht van Microsoft 365 Defender en stapsgewijs instructies over het instellen van uw pilotproject.</span><span class="sxs-lookup"><span data-stu-id="a7cca-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="a7cca-113">Microsoft 365 Defender is een geïntegreerde suite voor bedrijfsdefensie vóór en na inbreuk die inheems bescherming, detectie, preventie, onderzoek en antwoord coördineert in eindpunten, identiteiten, e-mail en toepassingen om geïntegreerde bescherming te bieden tegen geavanceerde aanvallen.</span><span class="sxs-lookup"><span data-stu-id="a7cca-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="a7cca-114">Dit doet het door de volgende mogelijkheden te combineren en te orveren tot één beveiligingsoplossing:</span><span class="sxs-lookup"><span data-stu-id="a7cca-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="a7cca-115">Microsoft Defender voor Eindpunt (eindpunten)</span><span class="sxs-lookup"><span data-stu-id="a7cca-115">Microsoft Defender for Endpoint (endpoints)</span></span>
  - <span data-ttu-id="a7cca-116">Microsoft Defender voor Office 365 (e-mail)</span><span class="sxs-lookup"><span data-stu-id="a7cca-116">Microsoft Defender for Office 365 (email)</span></span> 
  - <span data-ttu-id="a7cca-117">Microsoft Defender voor identiteit (identiteit)</span><span class="sxs-lookup"><span data-stu-id="a7cca-117">Microsoft Defender for Identity (identity)</span></span> 
  - <span data-ttu-id="a7cca-118">Microsoft Cloud App Security (apps)</span><span class="sxs-lookup"><span data-stu-id="a7cca-118">Microsoft Cloud App Security (apps)</span></span>

![Image of_Microsoft 365 Defender solution for users, Microsoft Defender for Identity, for endpoints Microsoft Defender for Endpoint, for cloud apps, Microsoft Cloud App Security, and for data, Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="a7cca-120">Met de geïntegreerde Microsoft 365 Defender-oplossing kunnen beveiligingsprofessionals de bedreigingssignalen die Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365, Microsoft Defender voor identiteit en Microsoft Cloud App Security ontvangen, samenbrengen en bepalen wat het volledige bereik en de impact van de bedreiging zijn, hoe deze de omgeving is binnengekomen, wat de impact ervan is en wat de gevolgen zijn voor de organisatie.</span><span class="sxs-lookup"><span data-stu-id="a7cca-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="a7cca-121">Microsoft 365 Defender voert automatische actie uit om de aanval te voorkomen of te stoppen en getroffen postvakken, eindpunten en gebruikersidentiteiten te voorkomen of te herstellen.</span><span class="sxs-lookup"><span data-stu-id="a7cca-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="a7cca-122">Zie het [Microsoft 365 Defender-overzicht](microsoft-365-defender.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a7cca-122">See the [Microsoft 365 Defender overview](microsoft-365-defender.md) for details.</span></span>



<span data-ttu-id="a7cca-123">De volgende voorbeeldtijdlijn is afhankelijk van de juiste resources in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="a7cca-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="a7cca-124">Sommige detecties en werkstromen hebben mogelijk meer leertijd nodig dan de andere.</span><span class="sxs-lookup"><span data-stu-id="a7cca-124">Some detections and workflows might need more learning time than the others.</span></span>

![Voorbeeldtijdlijn bij het uitvoeren van een Microsoft 365 Defender-pilot](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="a7cca-126">Volg de testinstructies zo nauwkeurig mogelijk voor optimale resultaten.</span><span class="sxs-lookup"><span data-stu-id="a7cca-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="a7cca-127">Testfasen van een playbook</span><span class="sxs-lookup"><span data-stu-id="a7cca-127">Pilot playbook phases</span></span> 

<span data-ttu-id="a7cca-128">Er zijn vier fasen in het uitvoeren van een Microsoft 365 Defender-pilot:</span><span class="sxs-lookup"><span data-stu-id="a7cca-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="a7cca-129">Fase</span><span class="sxs-lookup"><span data-stu-id="a7cca-129">Phase</span></span> | <span data-ttu-id="a7cca-130">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="a7cca-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="a7cca-131">Planning</span><span class="sxs-lookup"><span data-stu-id="a7cca-131">Planning</span></span>](m365d-pilot-plan.md)<br> <span data-ttu-id="a7cca-132">~ 1 dag</span><span class="sxs-lookup"><span data-stu-id="a7cca-132">~ 1 day</span></span>| <span data-ttu-id="a7cca-133">Lees waar u rekening mee moet houden voordat u uw Microsoft 365 Defender-pilotproject gaat uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="a7cca-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="a7cca-134">- Bereik</span><span class="sxs-lookup"><span data-stu-id="a7cca-134">- Scope</span></span> <br> <span data-ttu-id="a7cca-135">- Use cases</span><span class="sxs-lookup"><span data-stu-id="a7cca-135">- Use cases</span></span> <br><span data-ttu-id="a7cca-136">- Vereisten</span><span class="sxs-lookup"><span data-stu-id="a7cca-136">- Requirements</span></span> <br><span data-ttu-id="a7cca-137">- Testplan</span><span class="sxs-lookup"><span data-stu-id="a7cca-137">- Test plan</span></span> <br> <span data-ttu-id="a7cca-138">- Succescriteria</span><span class="sxs-lookup"><span data-stu-id="a7cca-138">- Success criteria</span></span> <br> <span data-ttu-id="a7cca-139">- Scorecard</span><span class="sxs-lookup"><span data-stu-id="a7cca-139">- Scorecard</span></span> 
| [<span data-ttu-id="a7cca-140">Voorbereiding</span><span class="sxs-lookup"><span data-stu-id="a7cca-140">Preparation</span></span>](m365d-evaluation.md) <br><span data-ttu-id="a7cca-141">~2 dagen</span><span class="sxs-lookup"><span data-stu-id="a7cca-141">~2 days</span></span>|  <span data-ttu-id="a7cca-142">Access Microsoft 365 Beveiligingscentrum om uw Microsoft 365 Defender-testomgeving in te stellen.</span><span class="sxs-lookup"><span data-stu-id="a7cca-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="a7cca-143">U wordt begeleid naar:</span><span class="sxs-lookup"><span data-stu-id="a7cca-143">You'll be guided to:</span></span><br><br><span data-ttu-id="a7cca-144">- Identificeer belanghebbenden en zoek aanmelding voor uw pilot</span><span class="sxs-lookup"><span data-stu-id="a7cca-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="a7cca-145">- Milieuoverwegingen</span><span class="sxs-lookup"><span data-stu-id="a7cca-145">- Environment considerations</span></span> <br><span data-ttu-id="a7cca-146">- Access</span><span class="sxs-lookup"><span data-stu-id="a7cca-146">- Access</span></span> <br><span data-ttu-id="a7cca-147">- Azure Active Directory instellen</span><span class="sxs-lookup"><span data-stu-id="a7cca-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="a7cca-148">- Configuratieorder</span><span class="sxs-lookup"><span data-stu-id="a7cca-148">- Configuration order</span></span> <br> <span data-ttu-id="a7cca-149">- Registreren voor Microsoft 365 E5 proefversie</span><span class="sxs-lookup"><span data-stu-id="a7cca-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="a7cca-150">- Domein configureren</span><span class="sxs-lookup"><span data-stu-id="a7cca-150">- Configure domain</span></span> <br><span data-ttu-id="a7cca-151">- Licenties Microsoft 365 E5 toewijzen</span><span class="sxs-lookup"><span data-stu-id="a7cca-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="a7cca-152">- De installatiewizard in de portal voltooien</span><span class="sxs-lookup"><span data-stu-id="a7cca-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="a7cca-153">Aanvalssimulatie</span><span class="sxs-lookup"><span data-stu-id="a7cca-153">Attack simulation</span></span>](m365d-pilot-simulate.md) <br><span data-ttu-id="a7cca-154">~2 dagen</span><span class="sxs-lookup"><span data-stu-id="a7cca-154">~2 days</span></span>| <span data-ttu-id="a7cca-155">Als u een aanval wilt simuleren, wordt u begeleid naar:</span><span class="sxs-lookup"><span data-stu-id="a7cca-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="a7cca-156">- Controleer de vereisten voor de testomgeving</span><span class="sxs-lookup"><span data-stu-id="a7cca-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="a7cca-157">- Voer de simulatie uit</span><span class="sxs-lookup"><span data-stu-id="a7cca-157">-  Run the simulation</span></span> <br><span data-ttu-id="a7cca-158">- Een incident onderzoeken</span><span class="sxs-lookup"><span data-stu-id="a7cca-158">- Investigate an incident</span></span> <br><span data-ttu-id="a7cca-159">- het incident oplossen</span><span class="sxs-lookup"><span data-stu-id="a7cca-159">- resolve the incident</span></span> 
| [<span data-ttu-id="a7cca-160">Sluiten en samenvatting</span><span class="sxs-lookup"><span data-stu-id="a7cca-160">Closing and summary</span></span>](m365d-pilot-close.md) <br><span data-ttu-id="a7cca-161">~ 1 dag</span><span class="sxs-lookup"><span data-stu-id="a7cca-161">~ 1 day</span></span>| <span data-ttu-id="a7cca-162">Wanneer u het einde van het proces hebt bereikt, wordt u begeleid naar:</span><span class="sxs-lookup"><span data-stu-id="a7cca-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="a7cca-163">- Ga door de uiteindelijke uitvoer</span><span class="sxs-lookup"><span data-stu-id="a7cca-163">- Go through your final output</span></span><br><span data-ttu-id="a7cca-164">- Presenteert uw uitvoer aan uw belanghebbenden</span><span class="sxs-lookup"><span data-stu-id="a7cca-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="a7cca-165">- Feedback geven</span><span class="sxs-lookup"><span data-stu-id="a7cca-165">- Provide feedback</span></span> <br><span data-ttu-id="a7cca-166">- Volgende stappen ondernemen</span><span class="sxs-lookup"><span data-stu-id="a7cca-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="a7cca-167">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="a7cca-167">Next step</span></span>
|[<span data-ttu-id="a7cca-168">Planningsfase</span><span class="sxs-lookup"><span data-stu-id="a7cca-168">Planning phase</span></span>](m365d-pilot-plan.md) | <span data-ttu-id="a7cca-169">Plan uw Microsoft 365 Defender-pilotproject</span><span class="sxs-lookup"><span data-stu-id="a7cca-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
