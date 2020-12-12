---
title: Voer uw proef Microsoft 365 Defender-project uit.
description: Voer uw pilot Microsoft 365 Defender-project in de productie om de voordelen en aanneming van Microsoft 365 te effectief te bepalen.
keywords: Microsoft Threat Protection pilot, een prototype Microsoft Threat Protection-project, Microsoft Threat Protection evalueren in productie, Microsoft Threat Protection pilotproject, Cyber beveiliging, geavanceerde permanente bedreiging, beveiliging van uw organisatie, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerde jacht
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: f01e918d35ce77d9239c200355c7b4c48c9e2b84
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659314"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="458ea-104">Voer uw proef Microsoft 365 Defender-project uit.</span><span class="sxs-lookup"><span data-stu-id="458ea-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="458ea-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="458ea-105">**Applies to:**</span></span>
- <span data-ttu-id="458ea-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="458ea-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="458ea-107">Deze handleiding helpt u bij het uitvoeren van een pilotproject met behulp van pointers, zodat u zeker weet dat u een goed gestructureerd abonnement hebt, u kunt met de functie voor simulatie van een aanval de functie voor simulatie van aanval en de proefversie sluiten.</span><span class="sxs-lookup"><span data-stu-id="458ea-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Fasen in een proef met Microsoft 365 Defender](../../media/pilotphases.png)


<span data-ttu-id="458ea-109">Door een pilot uit te voeren, kunt u de voordelen van adoptiing Microsoft 365 Defender optimaal bepalen.</span><span class="sxs-lookup"><span data-stu-id="458ea-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="458ea-110">Voordat u Microsoft 365 Defender in uw productieomgeving inschakelt en beproefde zaken begint, is het raadzaam om te bepalen welke taken u uitvoert voor uw pilotproject en stelt u de criteria voor slagen in.</span><span class="sxs-lookup"><span data-stu-id="458ea-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="458ea-111">Het gebruik van deze pilot-Playbook</span><span class="sxs-lookup"><span data-stu-id="458ea-111">How to use this pilot playbook</span></span>

<span data-ttu-id="458ea-112">Deze handleiding biedt een overzicht van Microsoft 365 Defender en stapsgewijze instructies voor het instellen van uw proefproject.</span><span class="sxs-lookup"><span data-stu-id="458ea-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="458ea-113">Microsoft 365 Defender is een in-en uitbraak centrale Enterprise-verdedigings suite die de bescherming, detectie, preventie, onderzoek en respons van eindpunten, identiteiten, e-mailberichten en toepassingen biedt voor geïntegreerde beveiliging tegen geavanceerde aanvallen.</span><span class="sxs-lookup"><span data-stu-id="458ea-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="458ea-114">Dit houdt in dat u de volgende mogelijkheden combineert en vasthoudt in één beveiligingsoplossing:</span><span class="sxs-lookup"><span data-stu-id="458ea-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="458ea-115">Microsoft Defender for Endpoint, de nieuwe naam voor Microsoft Defender Advanced Threat Protection (eindpunten)</span><span class="sxs-lookup"><span data-stu-id="458ea-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="458ea-116">Microsoft Defender voor Office 365, de nieuwe naam voor Office 365 ATP (e-mail)</span><span class="sxs-lookup"><span data-stu-id="458ea-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="458ea-117">Microsoft Defender for Identity, de nieuwe naam voor Azure ATP (identiteit)</span><span class="sxs-lookup"><span data-stu-id="458ea-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="458ea-118">Beveiligingsupdates voor Microsoft Cloud-app (apps)</span><span class="sxs-lookup"><span data-stu-id="458ea-118">Microsoft Cloud App Security (apps)</span></span>

![Afbeelding of_Microsoft 365, oplossing voor gebruikers, Microsoft Defender for-eindpunten, Microsoft Defender for endpoints, voor Cloud-apps, Microsoft Cloud app Security en voor gegevens, Microsoft Defender voor Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="458ea-120">Met de geïntegreerde Microsoft 365 Defender-oplossing kunnen beveiligings technici de bedreigings signalen voor Microsoft Defender voor eindpunten, Microsoft Defender for Office 365, Microsoft Defender for Identity en de beveiliging van de Microsoft Cloud-app, bepalen, en de volledige omvang en impact van de bedreiging, hoe die de omgeving heeft ingevoerd, wat van invloed is op de organisatie.</span><span class="sxs-lookup"><span data-stu-id="458ea-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="458ea-121">Microsoft 365 Defender doet automatische actie om de aanval te voorkomen of te stoppen, en de desbetreffende postvakken, eindpunten en gebruikersidentiteiten te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="458ea-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="458ea-122">Zie het [overzicht van Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="458ea-122">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>



<span data-ttu-id="458ea-123">Het volgende voorbeeld van een tijdlijn is afhankelijk van de juiste bronnen in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="458ea-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="458ea-124">Voor sommige detecties en werkstromen is mogelijk meer leer tijd nodig dan voor de andere.</span><span class="sxs-lookup"><span data-stu-id="458ea-124">Some detections and workflows might need more learning time than the others.</span></span>

![Voorbeeld van een tijdlijn in een Microsoft 365 Defender-pilot](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="458ea-126">Volg voor optimale resultaten de instructies voor het testen.</span><span class="sxs-lookup"><span data-stu-id="458ea-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="458ea-127">Playbook fasen voor prototype</span><span class="sxs-lookup"><span data-stu-id="458ea-127">Pilot playbook phases</span></span> 

<span data-ttu-id="458ea-128">Er zijn vier fasen met een Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="458ea-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="458ea-129">Fase</span><span class="sxs-lookup"><span data-stu-id="458ea-129">Phase</span></span> | <span data-ttu-id="458ea-130">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="458ea-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="458ea-131">Planning</span><span class="sxs-lookup"><span data-stu-id="458ea-131">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="458ea-132">~ 1 dag</span><span class="sxs-lookup"><span data-stu-id="458ea-132">~ 1 day</span></span>| <span data-ttu-id="458ea-133">Meer informatie over wat u moet doen voordat u uw Microsoft 365-proefproject voor Microsoft-Defender uitvoert:</span><span class="sxs-lookup"><span data-stu-id="458ea-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="458ea-134">-Bereik</span><span class="sxs-lookup"><span data-stu-id="458ea-134">- Scope</span></span> <br> <span data-ttu-id="458ea-135">-Use cases</span><span class="sxs-lookup"><span data-stu-id="458ea-135">- Use cases</span></span> <br><span data-ttu-id="458ea-136">-Vereisten</span><span class="sxs-lookup"><span data-stu-id="458ea-136">- Requirements</span></span> <br><span data-ttu-id="458ea-137">Test plan</span><span class="sxs-lookup"><span data-stu-id="458ea-137">- Test plan</span></span> <br> <span data-ttu-id="458ea-138">-Succescriteria</span><span class="sxs-lookup"><span data-stu-id="458ea-138">- Success criteria</span></span> <br> <span data-ttu-id="458ea-139">-Scorecard</span><span class="sxs-lookup"><span data-stu-id="458ea-139">- Scorecard</span></span> 
| [<span data-ttu-id="458ea-140">Uitwerking</span><span class="sxs-lookup"><span data-stu-id="458ea-140">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="458ea-141">~ 2 dagen</span><span class="sxs-lookup"><span data-stu-id="458ea-141">~2 days</span></span>|  <span data-ttu-id="458ea-142">Open Microsoft 365-Beveiligingscentrum voor het instellen van uw proef omgeving voor Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="458ea-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="458ea-143">U wordt begeleid bij:</span><span class="sxs-lookup"><span data-stu-id="458ea-143">You'll be guided to:</span></span><br><br><span data-ttu-id="458ea-144">-Belanghebbenden identificeren en zich afmelden voor uw pilot</span><span class="sxs-lookup"><span data-stu-id="458ea-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="458ea-145">-Aandachtspunten voor de omgeving</span><span class="sxs-lookup"><span data-stu-id="458ea-145">- Environment considerations</span></span> <br><span data-ttu-id="458ea-146">-Access</span><span class="sxs-lookup"><span data-stu-id="458ea-146">- Access</span></span> <br><span data-ttu-id="458ea-147">-Configuratie van Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="458ea-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="458ea-148">-De configuratie volgorde</span><span class="sxs-lookup"><span data-stu-id="458ea-148">- Configuration order</span></span> <br> <span data-ttu-id="458ea-149">-Registreren voor Microsoft 365 E5-proefabonnement</span><span class="sxs-lookup"><span data-stu-id="458ea-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="458ea-150">Domein configureren</span><span class="sxs-lookup"><span data-stu-id="458ea-150">- Configure domain</span></span> <br><span data-ttu-id="458ea-151">-Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="458ea-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="458ea-152">-De wizard Setup voltooien in de portal</span><span class="sxs-lookup"><span data-stu-id="458ea-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="458ea-153">Simulatie van aanval</span><span class="sxs-lookup"><span data-stu-id="458ea-153">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="458ea-154">~ 2 dagen</span><span class="sxs-lookup"><span data-stu-id="458ea-154">~2 days</span></span>| <span data-ttu-id="458ea-155">U wordt begeleid bij het maken van een aanval:</span><span class="sxs-lookup"><span data-stu-id="458ea-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="458ea-156">-Controleer de vereisten voor de testomgeving</span><span class="sxs-lookup"><span data-stu-id="458ea-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="458ea-157">-De simulatie uitvoeren</span><span class="sxs-lookup"><span data-stu-id="458ea-157">-  Run the simulation</span></span> <br><span data-ttu-id="458ea-158">-Onderzoek een incident</span><span class="sxs-lookup"><span data-stu-id="458ea-158">- Investigate an incident</span></span> <br><span data-ttu-id="458ea-159">-het incident oplossen</span><span class="sxs-lookup"><span data-stu-id="458ea-159">- resolve the incident</span></span> 
| [<span data-ttu-id="458ea-160">Sluiten en samenvatting</span><span class="sxs-lookup"><span data-stu-id="458ea-160">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="458ea-161">~ 1 dag</span><span class="sxs-lookup"><span data-stu-id="458ea-161">~ 1 day</span></span>| <span data-ttu-id="458ea-162">Wanneer u het einde van het proces hebt bereikt, gaat u verder met:</span><span class="sxs-lookup"><span data-stu-id="458ea-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="458ea-163">-Doorgaan met de laatste uitvoer</span><span class="sxs-lookup"><span data-stu-id="458ea-163">- Go through your final output</span></span><br><span data-ttu-id="458ea-164">-De uitvoer presenteren aan de belanghebbenden</span><span class="sxs-lookup"><span data-stu-id="458ea-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="458ea-165">-Feedback geven</span><span class="sxs-lookup"><span data-stu-id="458ea-165">- Provide feedback</span></span> <br><span data-ttu-id="458ea-166">-Voer de volgende stappen uit</span><span class="sxs-lookup"><span data-stu-id="458ea-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="458ea-167">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="458ea-167">Next step</span></span>
|[<span data-ttu-id="458ea-168">Planningfase</span><span class="sxs-lookup"><span data-stu-id="458ea-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="458ea-169">Een proefproject voor Microsoft 365 Defender plannen</span><span class="sxs-lookup"><span data-stu-id="458ea-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
