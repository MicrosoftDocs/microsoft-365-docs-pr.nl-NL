---
title: Voer uw proefproject voor Microsoft Threat Protection uit.
description: Voer uw pilot Microsoft Threat Protection-project uit om de voordelen en aanneming van Microsoft Threat Protection (MTP) te bepalen.
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
ms.openlocfilehash: af47f45ca4f3d14e835a39a334a9400002ac8560
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418071"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="0e2fb-104">Voer uw proefproject voor Microsoft Threat Protection uit.</span><span class="sxs-lookup"><span data-stu-id="0e2fb-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0e2fb-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0e2fb-105">**Applies to:**</span></span>
- <span data-ttu-id="0e2fb-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0e2fb-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0e2fb-107">Als u de voordelen en aanneming van Microsoft Threat Protection (MTP) daadwerkelijk wilt bepalen, kunt u een proefproject uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="0e2fb-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="0e2fb-108">Voordat u Microsoft Threat Protection in uw productieomgeving inschakelt en aan de slag gaat, kunt u het beste een planningsproces treffen voor het bepalen van de taken die moeten worden uitgevoerd in dit prototypeproject en de succescriteria.</span><span class="sxs-lookup"><span data-stu-id="0e2fb-108">Before enabling Microsoft Threat Protection in your production environment and starting with defined use cases, it is best to go through a planning process to determine the tasks that must be accomplished in this pilot project, and the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="0e2fb-109">Het gebruik van deze pilot-Playbook</span><span class="sxs-lookup"><span data-stu-id="0e2fb-109">How to use this pilot playbook</span></span>

<span data-ttu-id="0e2fb-110">Deze handleiding biedt een overzicht van Microsoft Threat Protection en stapsgewijze instructies voor het instellen van uw proefproject.</span><span class="sxs-lookup"><span data-stu-id="0e2fb-110">This guide provides an overview of Microsoft Threat Protection and step-by-step instructions on how to set up your pilot project.</span></span> 

![Fasen in de proefwerken met Microsoft Threat Protection](../../media/pilotphases.png)

<span data-ttu-id="0e2fb-112">Het volgende voorbeeld van een tijdlijn is afhankelijk van de juiste bronnen in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="0e2fb-112">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="0e2fb-113">Voor sommige detecties en werkstromen is mogelijk meer leer tijd nodig dan voor de andere.</span><span class="sxs-lookup"><span data-stu-id="0e2fb-113">Some detections and workflows might need more learning time than the others.</span></span>

![Voorbeeld van een tijdlijn met een Microsoft Threat Protection-proef](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="0e2fb-115">Volg voor optimale resultaten de instructies voor het testen.</span><span class="sxs-lookup"><span data-stu-id="0e2fb-115">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="0e2fb-116">Playbook fasen voor prototype</span><span class="sxs-lookup"><span data-stu-id="0e2fb-116">Pilot playbook phases</span></span> 

<span data-ttu-id="0e2fb-117">Er zijn vier fasen in het uitvoeren van een pilot van Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="0e2fb-117">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="0e2fb-118">Fase</span><span class="sxs-lookup"><span data-stu-id="0e2fb-118">Phase</span></span> | <span data-ttu-id="0e2fb-119">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="0e2fb-119">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="0e2fb-120">![Planning](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="0e2fb-120">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="0e2fb-121">Planning</span><span class="sxs-lookup"><span data-stu-id="0e2fb-121">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="0e2fb-122">Meer informatie over wat u moet doen voordat u uw Microsoft Threat Protection-proefproject kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="0e2fb-122">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="0e2fb-123">-Bereik</span><span class="sxs-lookup"><span data-stu-id="0e2fb-123">- Scope</span></span> <br> <span data-ttu-id="0e2fb-124">-Use cases</span><span class="sxs-lookup"><span data-stu-id="0e2fb-124">- Use cases</span></span> <br><span data-ttu-id="0e2fb-125">-Vereisten</span><span class="sxs-lookup"><span data-stu-id="0e2fb-125">- Requirements</span></span> <br><span data-ttu-id="0e2fb-126">Test plan</span><span class="sxs-lookup"><span data-stu-id="0e2fb-126">- Test plan</span></span> <br> <span data-ttu-id="0e2fb-127">-Succescriteria</span><span class="sxs-lookup"><span data-stu-id="0e2fb-127">- Success criteria</span></span> <br> <span data-ttu-id="0e2fb-128">-Scorecard</span><span class="sxs-lookup"><span data-stu-id="0e2fb-128">- Scorecard</span></span> 
| <span data-ttu-id="0e2fb-129">![Uitwerking](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="0e2fb-129">![Preparation](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="0e2fb-130">Uitwerking</span><span class="sxs-lookup"><span data-stu-id="0e2fb-130">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="0e2fb-131">Open Microsoft 365-Beveiligingscentrum om uw testomgeving voor Microsoft Threat Protection te installeren.</span><span class="sxs-lookup"><span data-stu-id="0e2fb-131">Access Microsoft 365 Security Center to setup your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="0e2fb-132">U wordt begeleid bij:</span><span class="sxs-lookup"><span data-stu-id="0e2fb-132">You will be guided to:</span></span><br><br><span data-ttu-id="0e2fb-133">-Belanghebbenden identificeren en zich afmelden voor uw pilot</span><span class="sxs-lookup"><span data-stu-id="0e2fb-133">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="0e2fb-134">-Aandachtspunten voor de omgeving</span><span class="sxs-lookup"><span data-stu-id="0e2fb-134">- Environment considerations</span></span> <br><span data-ttu-id="0e2fb-135">-Access</span><span class="sxs-lookup"><span data-stu-id="0e2fb-135">- Access</span></span> <br><span data-ttu-id="0e2fb-136">-Configuratie van Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0e2fb-136">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="0e2fb-137">-De configuratie volgorde</span><span class="sxs-lookup"><span data-stu-id="0e2fb-137">- Configuration order</span></span> <br> <span data-ttu-id="0e2fb-138">-Registreren voor Microsoft 365 E5-proefabonnement</span><span class="sxs-lookup"><span data-stu-id="0e2fb-138">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="0e2fb-139">Domein configureren</span><span class="sxs-lookup"><span data-stu-id="0e2fb-139">- Configure domain</span></span> <br><span data-ttu-id="0e2fb-140">-Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="0e2fb-140">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="0e2fb-141">-De wizard Setup voltooien in de portal</span><span class="sxs-lookup"><span data-stu-id="0e2fb-141">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="0e2fb-142">![Simulatie van aanval](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="0e2fb-142">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="0e2fb-143">Simulatie van aanval</span><span class="sxs-lookup"><span data-stu-id="0e2fb-143">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="0e2fb-144">U wordt begeleid bij het maken van een aanval:</span><span class="sxs-lookup"><span data-stu-id="0e2fb-144">To simulate an attack, you will be guided to:</span></span><br><br><span data-ttu-id="0e2fb-145">-Controleer de vereisten voor de testomgeving</span><span class="sxs-lookup"><span data-stu-id="0e2fb-145">- Verify the test environment requirements</span></span> <br><span data-ttu-id="0e2fb-146">-De simulatie uitvoeren</span><span class="sxs-lookup"><span data-stu-id="0e2fb-146">-  Run the simulation</span></span> <br><span data-ttu-id="0e2fb-147">-Onderzoek een incident</span><span class="sxs-lookup"><span data-stu-id="0e2fb-147">- Investigate an incident</span></span> <br><span data-ttu-id="0e2fb-148">-het incident oplossen</span><span class="sxs-lookup"><span data-stu-id="0e2fb-148">- resolve the incident</span></span> 
| <span data-ttu-id="0e2fb-149">![Sluiten en samenvatting](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="0e2fb-149">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="0e2fb-150">Sluiten en samenvatting</span><span class="sxs-lookup"><span data-stu-id="0e2fb-150">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="0e2fb-151">Wanneer u het einde van het proces hebt bereikt, wordt u begeleid bij het volgende:</span><span class="sxs-lookup"><span data-stu-id="0e2fb-151">When you've reached the end of the process, you will be guided to:</span></span><br><br><span data-ttu-id="0e2fb-152">-Doorgaan met de laatste uitvoer</span><span class="sxs-lookup"><span data-stu-id="0e2fb-152">- Go through your final output</span></span><br><span data-ttu-id="0e2fb-153">-De uitvoer presenteren aan de belanghebbenden</span><span class="sxs-lookup"><span data-stu-id="0e2fb-153">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="0e2fb-154">-Feedback geven</span><span class="sxs-lookup"><span data-stu-id="0e2fb-154">- Provide feedback</span></span> <br><span data-ttu-id="0e2fb-155">-Voer de volgende stappen uit</span><span class="sxs-lookup"><span data-stu-id="0e2fb-155">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="0e2fb-156">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="0e2fb-156">Next step</span></span>
|<span data-ttu-id="0e2fb-157">![Planningfase](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="0e2fb-157">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="0e2fb-158">Planningfase</span><span class="sxs-lookup"><span data-stu-id="0e2fb-158">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="0e2fb-159">Uw proefproject voor Microsoft Threat Protection plannen</span><span class="sxs-lookup"><span data-stu-id="0e2fb-159">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
