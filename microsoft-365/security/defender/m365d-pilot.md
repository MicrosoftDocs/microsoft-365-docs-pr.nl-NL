---
title: Uw testproject voor Microsoft 365 Defender uitvoeren
description: Voer uw testproject Microsoft 365 Defender in productie uit om de voordelen en acceptatie van Microsoft 365 Defender effectief te bepalen.
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
ms.openlocfilehash: b1616b39597a90ff8e8f7b4c92f29f75c62fea18
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934427"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="39c44-104">Uw testproject voor Microsoft 365 Defender uitvoeren</span><span class="sxs-lookup"><span data-stu-id="39c44-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="39c44-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="39c44-105">**Applies to:**</span></span>
- <span data-ttu-id="39c44-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39c44-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="39c44-107">Deze handleiding helpt u bij het uitvoeren van een pilotproject door aanwijzers te geven om ervoor te zorgen dat u een goed gestructureerd plan hebt, u begeleidt bij het gebruik van de functie aanvalssimulatie en de pilot ten slotte afsluit met belangrijke take-aways om na te denken over en de resultaten te documenteren.</span><span class="sxs-lookup"><span data-stu-id="39c44-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Fasen in het uitvoeren van een Microsoft 365 Defender-pilot](../../media/pilotphases.png)


<span data-ttu-id="39c44-109">Met een pilot kunt u effectief bepalen wat het voordeel is van het gebruik van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="39c44-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="39c44-110">Voordat u Microsoft 365 Defender in uw productieomgeving inschakelen en uw gebruiksgevallen start, kunt u het beste plannen om de taken voor uw testproject te bepalen en de succescriteria in te stellen.</span><span class="sxs-lookup"><span data-stu-id="39c44-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="39c44-111">Deze test playbook gebruiken</span><span class="sxs-lookup"><span data-stu-id="39c44-111">How to use this pilot playbook</span></span>

<span data-ttu-id="39c44-112">Deze handleiding bevat een overzicht van Microsoft 365 Defender en stapsgewijs instructies over het instellen van uw pilotproject.</span><span class="sxs-lookup"><span data-stu-id="39c44-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="39c44-113">Microsoft 365 Defender is een geïntegreerde suite voor bedrijfsdefensie vóór en na inbreuk die inheems bescherming, detectie, preventie, onderzoek en antwoord coördineert in eindpunten, identiteiten, e-mail en toepassingen om geïntegreerde bescherming tegen geavanceerde aanvallen te bieden.</span><span class="sxs-lookup"><span data-stu-id="39c44-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="39c44-114">Dit doet het door de volgende mogelijkheden te combineren en te orveren tot één beveiligingsoplossing:</span><span class="sxs-lookup"><span data-stu-id="39c44-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="39c44-115">Microsoft Defender voor Eindpunt (eindpunten)</span><span class="sxs-lookup"><span data-stu-id="39c44-115">Microsoft Defender for Endpoint (endpoints)</span></span>
  - <span data-ttu-id="39c44-116">Microsoft Defender voor Office 365 (e-mail)</span><span class="sxs-lookup"><span data-stu-id="39c44-116">Microsoft Defender for Office 365 (email)</span></span> 
  - <span data-ttu-id="39c44-117">Microsoft Defender voor identiteit (identiteit)</span><span class="sxs-lookup"><span data-stu-id="39c44-117">Microsoft Defender for Identity (identity)</span></span> 
  - <span data-ttu-id="39c44-118">Microsoft Cloud App Security (apps)</span><span class="sxs-lookup"><span data-stu-id="39c44-118">Microsoft Cloud App Security (apps)</span></span>

![Image of_Microsoft 365 Defender solution for users, Microsoft Defender for Identity, for endpoints Microsoft Defender for Endpoint, for cloud apps, Microsoft Cloud App Security, and for data, Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="39c44-120">Met de geïntegreerde Microsoft 365 Defender-oplossing kunnen beveiligingsprofessionals de bedreigingssignalen die Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365, Microsoft Defender voor identiteit en Microsoft Cloud App Security ontvangen, samensmelten en bepalen wat het volledige bereik en de impact van de bedreiging is, hoe de bedreiging in de omgeving is ingevoerd, wat de gevolgen zijn en wat de gevolgen zijn voor de organisatie.</span><span class="sxs-lookup"><span data-stu-id="39c44-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="39c44-121">Microsoft 365 Defender voert automatisch actie om de aanval te voorkomen of te stoppen en getroffen postvakken, eindpunten en gebruikersidentiteiten te voorkomen of te herstellen.</span><span class="sxs-lookup"><span data-stu-id="39c44-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="39c44-122">Zie het [Microsoft 365 Defender-overzicht voor](microsoft-365-defender.md) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="39c44-122">See the [Microsoft 365 Defender overview](microsoft-365-defender.md) for details.</span></span>



<span data-ttu-id="39c44-123">De volgende voorbeeldtijdlijn is afhankelijk van de juiste resources in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="39c44-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="39c44-124">Sommige detecties en werkstromen hebben mogelijk meer leertijd nodig dan de andere.</span><span class="sxs-lookup"><span data-stu-id="39c44-124">Some detections and workflows might need more learning time than the others.</span></span>

![Voorbeeldtijdlijn bij het uitvoeren van een Microsoft 365 Defender-pilot](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="39c44-126">Volg de testinstructies zo nauwkeurig mogelijk voor optimale resultaten.</span><span class="sxs-lookup"><span data-stu-id="39c44-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="39c44-127">Testfasen van een playbook</span><span class="sxs-lookup"><span data-stu-id="39c44-127">Pilot playbook phases</span></span> 

<span data-ttu-id="39c44-128">Er zijn vier fasen in het uitvoeren van een Microsoft 365 Defender-pilot:</span><span class="sxs-lookup"><span data-stu-id="39c44-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="39c44-129">Fase</span><span class="sxs-lookup"><span data-stu-id="39c44-129">Phase</span></span> | <span data-ttu-id="39c44-130">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="39c44-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="39c44-131">Planning</span><span class="sxs-lookup"><span data-stu-id="39c44-131">Planning</span></span>](m365d-pilot-plan.md)<br> <span data-ttu-id="39c44-132">~ 1 dag</span><span class="sxs-lookup"><span data-stu-id="39c44-132">~ 1 day</span></span>| <span data-ttu-id="39c44-133">Lees waar u rekening mee moet houden voordat u uw Microsoft 365 Defender-testproject gaat uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="39c44-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="39c44-134">- Bereik</span><span class="sxs-lookup"><span data-stu-id="39c44-134">- Scope</span></span> <br> <span data-ttu-id="39c44-135">- Use cases</span><span class="sxs-lookup"><span data-stu-id="39c44-135">- Use cases</span></span> <br><span data-ttu-id="39c44-136">- Vereisten</span><span class="sxs-lookup"><span data-stu-id="39c44-136">- Requirements</span></span> <br><span data-ttu-id="39c44-137">- Testplan</span><span class="sxs-lookup"><span data-stu-id="39c44-137">- Test plan</span></span> <br> <span data-ttu-id="39c44-138">- Succescriteria</span><span class="sxs-lookup"><span data-stu-id="39c44-138">- Success criteria</span></span> <br> <span data-ttu-id="39c44-139">- Scorecard</span><span class="sxs-lookup"><span data-stu-id="39c44-139">- Scorecard</span></span> 
| [<span data-ttu-id="39c44-140">Voorbereiding</span><span class="sxs-lookup"><span data-stu-id="39c44-140">Preparation</span></span>](m365d-evaluation.md) <br><span data-ttu-id="39c44-141">~2 dagen</span><span class="sxs-lookup"><span data-stu-id="39c44-141">~2 days</span></span>|  <span data-ttu-id="39c44-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot environment.</span><span class="sxs-lookup"><span data-stu-id="39c44-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="39c44-143">U wordt begeleid naar:</span><span class="sxs-lookup"><span data-stu-id="39c44-143">You'll be guided to:</span></span><br><br><span data-ttu-id="39c44-144">- Identificeer belanghebbenden en zoek aanmelding voor uw pilot</span><span class="sxs-lookup"><span data-stu-id="39c44-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="39c44-145">- Milieuoverwegingen</span><span class="sxs-lookup"><span data-stu-id="39c44-145">- Environment considerations</span></span> <br><span data-ttu-id="39c44-146">- Access</span><span class="sxs-lookup"><span data-stu-id="39c44-146">- Access</span></span> <br><span data-ttu-id="39c44-147">- Configuratie van Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="39c44-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="39c44-148">- Configuratieorder</span><span class="sxs-lookup"><span data-stu-id="39c44-148">- Configuration order</span></span> <br> <span data-ttu-id="39c44-149">- Registreren voor proefversie van Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="39c44-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="39c44-150">- Domein configureren</span><span class="sxs-lookup"><span data-stu-id="39c44-150">- Configure domain</span></span> <br><span data-ttu-id="39c44-151">- Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="39c44-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="39c44-152">- De installatiewizard in de portal voltooien</span><span class="sxs-lookup"><span data-stu-id="39c44-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="39c44-153">Aanvalssimulatie</span><span class="sxs-lookup"><span data-stu-id="39c44-153">Attack simulation</span></span>](m365d-pilot-simulate.md) <br><span data-ttu-id="39c44-154">~2 dagen</span><span class="sxs-lookup"><span data-stu-id="39c44-154">~2 days</span></span>| <span data-ttu-id="39c44-155">Als u een aanval wilt simuleren, wordt u begeleid naar:</span><span class="sxs-lookup"><span data-stu-id="39c44-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="39c44-156">- Controleer de vereisten voor de testomgeving</span><span class="sxs-lookup"><span data-stu-id="39c44-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="39c44-157">- Voer de simulatie uit</span><span class="sxs-lookup"><span data-stu-id="39c44-157">-  Run the simulation</span></span> <br><span data-ttu-id="39c44-158">- Een incident onderzoeken</span><span class="sxs-lookup"><span data-stu-id="39c44-158">- Investigate an incident</span></span> <br><span data-ttu-id="39c44-159">- het incident oplossen</span><span class="sxs-lookup"><span data-stu-id="39c44-159">- resolve the incident</span></span> 
| [<span data-ttu-id="39c44-160">Sluiten en samenvatting</span><span class="sxs-lookup"><span data-stu-id="39c44-160">Closing and summary</span></span>](m365d-pilot-close.md) <br><span data-ttu-id="39c44-161">~ 1 dag</span><span class="sxs-lookup"><span data-stu-id="39c44-161">~ 1 day</span></span>| <span data-ttu-id="39c44-162">Wanneer u het einde van het proces hebt bereikt, wordt u begeleid naar:</span><span class="sxs-lookup"><span data-stu-id="39c44-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="39c44-163">- Ga door de uiteindelijke uitvoer</span><span class="sxs-lookup"><span data-stu-id="39c44-163">- Go through your final output</span></span><br><span data-ttu-id="39c44-164">- Presenteert uw uitvoer aan uw belanghebbenden</span><span class="sxs-lookup"><span data-stu-id="39c44-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="39c44-165">- Feedback geven</span><span class="sxs-lookup"><span data-stu-id="39c44-165">- Provide feedback</span></span> <br><span data-ttu-id="39c44-166">- Volgende stappen ondernemen</span><span class="sxs-lookup"><span data-stu-id="39c44-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="39c44-167">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="39c44-167">Next step</span></span>
|[<span data-ttu-id="39c44-168">Planningsfase</span><span class="sxs-lookup"><span data-stu-id="39c44-168">Planning phase</span></span>](m365d-pilot-plan.md) | <span data-ttu-id="39c44-169">Uw Microsoft 365 Defender-testproject plannen</span><span class="sxs-lookup"><span data-stu-id="39c44-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
