---
title: Strategieën voor de implementatie van de basisinfrastructuur van Microsoft 365 voor Enterprise
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 09/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Ontdek enkele manieren waarop u de fasen van de basisinfrastructuur voor Microsoft 365 voor ondernemingen kunt implementeren.
ms.openlocfilehash: 765bba743485c13c65cd6377abe01f80f2df4c23
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811298"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure-deployment-strategies"></a><span data-ttu-id="6b290-103">Strategieën voor de implementatie van de basisinfrastructuur van Microsoft 365 voor Enterprise</span><span class="sxs-lookup"><span data-stu-id="6b290-103">Microsoft 365 for enterprise foundation infrastructure deployment strategies</span></span>

<span data-ttu-id="6b290-104">Er zijn veel manieren waarop u de fasen van de [basisinfrastructuur](deploy-foundation-infrastructure.md) van Microsoft 365 voor ondernemingen kunt implementeren en de mogelijkheden, software en services voor uw gebruikers kunt uitrollen.</span><span class="sxs-lookup"><span data-stu-id="6b290-104">There are many ways you can deploy the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) of Microsoft 365 for enterprise and roll out its capabilities, software, and services to your users.</span></span> <span data-ttu-id="6b290-105">De implementatie kan groot en complex zijn, afhankelijk van de grootte van uw organisatie en de bestaande infrastructuur. Om u op weg te helpen met het projectbeheer kunt u de volgende implementatiestrategieën overwegen:</span><span class="sxs-lookup"><span data-stu-id="6b290-105">To get you started on the project management of this undertaking, which can be large and complex depending on the size of your organization and its existing infrastructure, consider the following deployment strategies:</span></span>

- <span data-ttu-id="6b290-106">Seriële implementatie</span><span class="sxs-lookup"><span data-stu-id="6b290-106">Serial deployment</span></span>
- <span data-ttu-id="6b290-107">Parallelle implementatie met niet-overlappende implementatie van gebruikers</span><span class="sxs-lookup"><span data-stu-id="6b290-107">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="6b290-108">Parallelle implementatie met overlappende implementatie van gebruikers</span><span class="sxs-lookup"><span data-stu-id="6b290-108">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="6b290-109">Up-front infrastructuur en uitrol van de end-to-end configuratie</span><span class="sxs-lookup"><span data-stu-id="6b290-109">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="6b290-110">Gebruik deze strategieën voor ideeën over hoe u het totale project kunt beheren en sneller de zakelijke voordelen van Microsoft 365 voor ondernemingen kunt realiseren.</span><span class="sxs-lookup"><span data-stu-id="6b290-110">Use these strategies for ideas on how to manage the overall project and more quickly realize the business benefits of Microsoft 365 for enterprise.</span></span>

>[!Note]
><span data-ttu-id="6b290-111">Dit artikel bevat veronderstellingen en vereenvoudigingen zodat de implementatiestrategieën op consistente wijze kunnen worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="6b290-111">This article contains assumptions and simplifications for a consistent way to describe the deployment strategies.</span></span> <span data-ttu-id="6b290-112">Deze implementatiestrategieën zijn algemeen van aard en zijn niet bedoeld als specifiek tijdsbestek, noch zijn ze bedoeld voor alle organisaties en situaties.</span><span class="sxs-lookup"><span data-stu-id="6b290-112">These deployment strategies are generalized and are not meant to imply any specific timeframes, nor are they meant to apply to all organizations and situations.</span></span>
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a><span data-ttu-id="6b290-113">Elementen van IT-projectbeheer voor typische ondernemingen</span><span class="sxs-lookup"><span data-stu-id="6b290-113">Elements of IT project management for typical enterprise organizations</span></span>

<span data-ttu-id="6b290-114">De IT-infrastructuur omvat zowel backend-services als de implementatie van nieuwe of verbeterde mogelijkheden, of geïnstalleerde software voor eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="6b290-114">IT infrastructure includes both backend services and the rollout of new or improved capabilities or installed software to end users.</span></span> <span data-ttu-id="6b290-115">IT-afdelingen implementeren meestal elementen van een IT-infrastructuur op een methodische wijze.</span><span class="sxs-lookup"><span data-stu-id="6b290-115">IT departments typically deploy elements of an IT infrastructure in a methodical way.</span></span> <span data-ttu-id="6b290-116">Een van de manieren waarop een element van de IT-infrastructuur succesvol kan worden geïmplementeerd, bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="6b290-116">One approach to the successful deployment of an element of IT infrastructure consists of:</span></span>

- <span data-ttu-id="6b290-117">Een proefimplementatie</span><span class="sxs-lookup"><span data-stu-id="6b290-117">A pilot rollout</span></span> 

  <span data-ttu-id="6b290-118">Dit omvat initiële infrastructuurconfiguratie en uitrol naar een proefset van gebruikers, testen en daaropvolgende aanpassingen aan de infrastructuurconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="6b290-118">This includes initial infrastructure configuration and rollout to a pilot set of users, testing, and subsequent modifications to the infrastructure configuration.</span></span>

- <span data-ttu-id="6b290-119">Een gebruikersimplementatie</span><span class="sxs-lookup"><span data-stu-id="6b290-119">A user rollout</span></span>

  <span data-ttu-id="6b290-120">Dit omvat de uitrol naar de rest van uw organisatie op basis van regio's, afdelingen, groepen of andere soorten systematische verspreiding van de configuratie of software.</span><span class="sxs-lookup"><span data-stu-id="6b290-120">This includes the rollout to the rest of your organization based on regions, departments, groups, or other types of systematic propagation of configuration or software.</span></span>

<span data-ttu-id="6b290-121">De gebruikers in de proefimplementatie zijn niet hetzelfde als die in de gebruikersimplementatie.</span><span class="sxs-lookup"><span data-stu-id="6b290-121">The set of users in the pilot rollout are not the same as those in the user rollout.</span></span>

<span data-ttu-id="6b290-122">In dit artikel worden de volgende afbeeldingen gebruikt om deze definities weer te geven:</span><span class="sxs-lookup"><span data-stu-id="6b290-122">This article uses the following graphics to depict these definitions:</span></span> 

![De grafische weergave van de definities van prototype- en gebruikersimplementatie](../media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

<span data-ttu-id="6b290-124">De arcering van de afbeelding voor de gebruikersimplementatie geeft het percentage binnen uw organisatie aan van 0% tot 100% bij een gestructureerde of methodische aanpak, zoals groepen, afdelingen of regio's.</span><span class="sxs-lookup"><span data-stu-id="6b290-124">The shading for the user rollout graphic indicates the percentage across your organization from 0% to 100% using a structured or methodical approach such as groups, departments, or regions.</span></span>

## <a name="deployment-strategies"></a><span data-ttu-id="6b290-125">Implementatiestrategieën</span><span class="sxs-lookup"><span data-stu-id="6b290-125">Deployment strategies</span></span>

<span data-ttu-id="6b290-126">Overweeg met de volgende implementatiestrategieën:</span><span class="sxs-lookup"><span data-stu-id="6b290-126">Consider the following deployment strategies:</span></span>

- <span data-ttu-id="6b290-127">Seriële implementatie</span><span class="sxs-lookup"><span data-stu-id="6b290-127">Serial deployment</span></span>
- <span data-ttu-id="6b290-128">Parallelle implementatie met niet-overlappende implementatie van gebruikers</span><span class="sxs-lookup"><span data-stu-id="6b290-128">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="6b290-129">Parallelle implementatie met overlappende implementatie van gebruikers</span><span class="sxs-lookup"><span data-stu-id="6b290-129">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="6b290-130">Up-front infrastructuur en uitrol van de end-to-end configuratie</span><span class="sxs-lookup"><span data-stu-id="6b290-130">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

### <a name="serial-deployment"></a><span data-ttu-id="6b290-131">Seriële implementatie</span><span class="sxs-lookup"><span data-stu-id="6b290-131">Serial deployment</span></span>

<span data-ttu-id="6b290-132">Met een seriële implementatie kunt u een fase volledig uitrollen, waardoor de fase 100% kan worden voltooid voor al uw gebruikers, voordat u naar de volgende stap gaat.</span><span class="sxs-lookup"><span data-stu-id="6b290-132">With a serial deployment, you completely roll out a phase, allowing the phase to reach 100% completion of deployment to all of your users, before moving on to the next one.</span></span> <span data-ttu-id="6b290-133">Hier zijn enkele redenen waarom u op deze manier zou kunnen implementeren:</span><span class="sxs-lookup"><span data-stu-id="6b290-133">Here are some of the reasons why you might deploy this way:</span></span>

- <span data-ttu-id="6b290-134">Risicobeperking</span><span class="sxs-lookup"><span data-stu-id="6b290-134">Risk mitigation</span></span>
- <span data-ttu-id="6b290-135">Resourcing-beperkingen</span><span class="sxs-lookup"><span data-stu-id="6b290-135">Resourcing constraints</span></span>
- <span data-ttu-id="6b290-136">Financieringscycli van de IT-afdeling</span><span class="sxs-lookup"><span data-stu-id="6b290-136">IT department funding cycles</span></span>
- <span data-ttu-id="6b290-137">Afhankelijkheden van IT-technologie</span><span class="sxs-lookup"><span data-stu-id="6b290-137">IT technology dependencies</span></span>
- <span data-ttu-id="6b290-138">Beheer van bedrijfsveranderingen en weerstand van eindgebruikers</span><span class="sxs-lookup"><span data-stu-id="6b290-138">Business change management and end-user resistance</span></span>

<span data-ttu-id="6b290-139">Dit Gantt-diagram toont een vereenvoudigde seriële implementatie van fasen 2-6 van de basisinfrastructuur voor Microsoft 365 voor ondernemingen.</span><span class="sxs-lookup"><span data-stu-id="6b290-139">This Gantt chart shows a simplified serial deployment of phases 2-6 of the foundation infrastructure for Microsoft 365 for enterprise.</span></span>

![De seriële implementatie van fasen 2-6 van de Foundation-infrastructuur](../media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
<span data-ttu-id="6b290-141">Om de discussie en het voorbeeld te vereenvoudigen, wordt aangenomen dat elke fase en implementatiesegment binnen elke fase evenveel tijd in beslag nemen.</span><span class="sxs-lookup"><span data-stu-id="6b290-141">To simplify the discussion and example, each phase and deployment segment within each phase are assumed to take the same amount of time.</span></span>

>[!Note]
><span data-ttu-id="6b290-142">Fase 1: netwerken van de basisinfrastructuur voor Microsoft 365 voor ondernemingen is een fase specifiek voor IT-afdelingen.</span><span class="sxs-lookup"><span data-stu-id="6b290-142">Phase 1: Networking of the Microsoft 365 for enterprise Foundation Infrastructure is an IT department-only phase.</span></span> <span data-ttu-id="6b290-143">Gebruikers profiteren van de voordelen van geoptimaliseerde connectiviteit met de cloudbronnen van Microsoft, maar hen wordt niet opgelegd dit na te streven.</span><span class="sxs-lookup"><span data-stu-id="6b290-143">Users reap the benefits of optimized connectivity to Microsoft’s cloud resources but are not imposed upon to achieve it.</span></span>
>

<span data-ttu-id="6b290-144">Dit is een vereenvoudigde gebruikerservaring voor prototypen als voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="6b290-144">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="6b290-145">In december moet ik mijn smartphone voor MFA gaan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6b290-145">In December, I need to use my smart phone for MFA.</span></span> <span data-ttu-id="6b290-146">(Identiteit)</span><span class="sxs-lookup"><span data-stu-id="6b290-146">(Identity)</span></span>
- <span data-ttu-id="6b290-147">In maart wordt Windows 10 Enterprise geïnstalleerd op mijn Windows 8.1-desktop.</span><span class="sxs-lookup"><span data-stu-id="6b290-147">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop.</span></span> <span data-ttu-id="6b290-148">(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="6b290-148">(Windows 10 Enterprise)</span></span>
- <span data-ttu-id="6b290-149">In juni wordt Office 365 ProPlus geïnstalleerd, ter vervanging van Office 2013.</span><span class="sxs-lookup"><span data-stu-id="6b290-149">In June, I get Office 365 ProPlus installed, replacing Office 2013.</span></span> <span data-ttu-id="6b290-150">(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="6b290-150">(Office 365 ProPlus)</span></span>
- <span data-ttu-id="6b290-151">In september worden de apparaatimplementatie en het app- en apparaatbeleid toegepast.</span><span class="sxs-lookup"><span data-stu-id="6b290-151">In September, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="6b290-152">(Mobile device management)</span><span class="sxs-lookup"><span data-stu-id="6b290-152">(Mobile device management)</span></span>
- <span data-ttu-id="6b290-153">In december wordt de Azure Information Protection-client geïnstalleerd en krijg ik training in het toepassen van labels op documenten.</span><span class="sxs-lookup"><span data-stu-id="6b290-153">In December, I get the Azure Information Protection client installed and get trained on how to apply labels to documents.</span></span> <span data-ttu-id="6b290-154">(Informatiebescherming)</span><span class="sxs-lookup"><span data-stu-id="6b290-154">(Information protection)</span></span>

<span data-ttu-id="6b290-155">Het resultaat is een frequentie van 90 dagen tussen opeenvolgende proefimplementaties.</span><span class="sxs-lookup"><span data-stu-id="6b290-155">The result is a 90-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="6b290-156">Hieronder ziet u een vereenvoudigde ervaring voor de eindgebruiker als voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="6b290-156">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="6b290-157">In januari moet ik mijn smartphone voor MFA gaan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6b290-157">In January, I need to use my smart phone for MFA.</span></span> <span data-ttu-id="6b290-158">(Identiteit)</span><span class="sxs-lookup"><span data-stu-id="6b290-158">(Identity)</span></span>
- <span data-ttu-id="6b290-159">In april wordt Windows 10 Enterprise geïnstalleerd op mijn Windows 8.1-desktop.</span><span class="sxs-lookup"><span data-stu-id="6b290-159">In April, I get Windows 10 Enterprise installed on my Windows 8.1 desktop.</span></span> <span data-ttu-id="6b290-160">(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="6b290-160">(Windows 10 Enterprise)</span></span>
- <span data-ttu-id="6b290-161">In juli wordt Office 365 ProPlus geïnstalleerd, ter vervanging van Office 2013.</span><span class="sxs-lookup"><span data-stu-id="6b290-161">In July, I get Office 365 ProPlus installed, replacing Office 2013.</span></span> <span data-ttu-id="6b290-162">(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="6b290-162">(Office 365 ProPlus)</span></span>
- <span data-ttu-id="6b290-163">In oktober worden de apparaatimplementatie en het app- en apparaatbeleid toegepast.</span><span class="sxs-lookup"><span data-stu-id="6b290-163">In October, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="6b290-164">(Mobile device management)</span><span class="sxs-lookup"><span data-stu-id="6b290-164">(Mobile device management)</span></span>
- <span data-ttu-id="6b290-165">In januari van het volgend jaar wordt de Azure Information Protection-client geïnstalleerd en krijg ik training in het toepassen van labels op documenten.</span><span class="sxs-lookup"><span data-stu-id="6b290-165">In January of the following year, I get the Azure Information Protection client installed and get trained on how to apply labels to documents.</span></span> <span data-ttu-id="6b290-166">(Informatiebescherming)</span><span class="sxs-lookup"><span data-stu-id="6b290-166">(Information protection)</span></span>

<span data-ttu-id="6b290-167">Het resultaat is een frequentie van 90 dagen tussen opeenvolgende gebruikersimplementaties.</span><span class="sxs-lookup"><span data-stu-id="6b290-167">The result is a 90-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="6b290-168">Het nadeel van deze implementatiestrategie is dat het lang kan duren voordat de basisinfrastructuur van Microsoft 365 voor ondernemingen volledig is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="6b290-168">The disadvantage to this deployment strategy is that it can take a long time to fully deploy the Microsoft 365 for enterprise foundation infrastructure.</span></span>

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a><span data-ttu-id="6b290-169">Parallelle implementatie met niet-overlappende implementatie van gebruikers (parallel 1)</span><span class="sxs-lookup"><span data-stu-id="6b290-169">Parallel deployment with non-overlapping user rollout (Parallel 1)</span></span>

<span data-ttu-id="6b290-170">Voor deze implementatiestrategie start u de proefimplementatie van de volgende fase tijdens het laatste deel van de gebruikersimplementatie van de huidige fase.</span><span class="sxs-lookup"><span data-stu-id="6b290-170">For this deployment strategy, you start the pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
<span data-ttu-id="6b290-171">Hier is de implementatie van fase 2-6 wanneer de proefimplementatie plaatsvindt terwijl de implementatie van de gebruiker van de vorige fase wordt afgerond.</span><span class="sxs-lookup"><span data-stu-id="6b290-171">Here is the deployment of phases 2-6 when the pilot rollout occurs as the user rollout of the previous phase is wrapping up.</span></span>

![De parallelle implementatie van fasen 2-6 met niet-overlappende gebruikersimplementatie](../media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
<span data-ttu-id="6b290-173">Het eindresultaat is dat de gebruikersimplementatie voor de huidige fase in uw hele organisatie is voltooid voordat de volgende begint.</span><span class="sxs-lookup"><span data-stu-id="6b290-173">The end result is that user rollout for the current phase completes across your organization before the next one starts.</span></span> <span data-ttu-id="6b290-174">Gebruikers die niet deelnemen aan proefimplementaties hebben niet te maken met de implementatie van meerdere fasen tegelijk, maar proefimplementaties worden parallel uitgevoerd met gebruikersimplementaties.</span><span class="sxs-lookup"><span data-stu-id="6b290-174">Users that are not in pilot rollouts are not dealing with the rollouts of multiple phases at the same time, but pilot rollouts are done in parallel with user rollouts.</span></span>

<span data-ttu-id="6b290-175">Dit is een vereenvoudigde gebruikerservaring voor prototypen als voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="6b290-175">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="6b290-176">In december moet ik mijn smartphone voor MFA gaan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6b290-176">In December, I need to use my smart phone for MFA.</span></span> <span data-ttu-id="6b290-177">(Identiteit)</span><span class="sxs-lookup"><span data-stu-id="6b290-177">(Identity)</span></span>
- <span data-ttu-id="6b290-178">In februari wordt Windows 10 Enterprise geïnstalleerd op mijn Windows 8.1-desktop.</span><span class="sxs-lookup"><span data-stu-id="6b290-178">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop.</span></span> <span data-ttu-id="6b290-179">(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="6b290-179">(Windows 10 Enterprise)</span></span>
- <span data-ttu-id="6b290-180">In april wordt Office 365 ProPlus geïnstalleerd, ter vervanging van Office 2013.</span><span class="sxs-lookup"><span data-stu-id="6b290-180">In April, I get Office 365 ProPlus installed, replacing Office 2013.</span></span> <span data-ttu-id="6b290-181">(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="6b290-181">(Office 365 ProPlus)</span></span>
- <span data-ttu-id="6b290-182">In juni worden de apparaatimplementatie en het app- en apparaatbeleid toegepast.</span><span class="sxs-lookup"><span data-stu-id="6b290-182">In June, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="6b290-183">(Mobile device management)</span><span class="sxs-lookup"><span data-stu-id="6b290-183">(Mobile device management)</span></span>
- <span data-ttu-id="6b290-184">In augustus wordt de Azure Information Protection-client geïnstalleerd en krijg ik training in het toepassen van labels op documenten.</span><span class="sxs-lookup"><span data-stu-id="6b290-184">In August, I get the Azure Information Protection client installed and get trained on how to apply labels to documents.</span></span> <span data-ttu-id="6b290-185">(Informatiebescherming)</span><span class="sxs-lookup"><span data-stu-id="6b290-185">(Information protection)</span></span>

<span data-ttu-id="6b290-186">Het resultaat is een frequentie van 60 dagen tussen opeenvolgende proefimplementaties.</span><span class="sxs-lookup"><span data-stu-id="6b290-186">The result is a 60-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="6b290-187">Hieronder ziet u een vereenvoudigde ervaring voor de eindgebruiker als voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="6b290-187">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="6b290-188">In januari moet ik mijn smartphone voor MFA gaan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6b290-188">In January, I need to use my smart phone for MFA.</span></span> <span data-ttu-id="6b290-189">(Identiteit)</span><span class="sxs-lookup"><span data-stu-id="6b290-189">(Identity)</span></span>
- <span data-ttu-id="6b290-190">In maart wordt Windows 10 Enterprise geïnstalleerd op mijn Windows 8.1-desktop.</span><span class="sxs-lookup"><span data-stu-id="6b290-190">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop.</span></span> <span data-ttu-id="6b290-191">(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="6b290-191">(Windows 10 Enterprise)</span></span>
- <span data-ttu-id="6b290-192">In mei wordt Office 365 ProPlus geïnstalleerd, ter vervanging van Office 2013.</span><span class="sxs-lookup"><span data-stu-id="6b290-192">In May, I get Office 365 ProPlus installed, replacing Office 2013.</span></span> <span data-ttu-id="6b290-193">(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="6b290-193">(Office 365 ProPlus)</span></span>
- <span data-ttu-id="6b290-194">In juli worden de apparaatimplementatie en het app- en apparaatbeleid toegepast.</span><span class="sxs-lookup"><span data-stu-id="6b290-194">In July, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="6b290-195">(Mobile device management)</span><span class="sxs-lookup"><span data-stu-id="6b290-195">(Mobile device management)</span></span>
- <span data-ttu-id="6b290-196">In september wordt de Azure Information Protection-client geïnstalleerd en krijg ik training in het toepassen van labels op documenten.</span><span class="sxs-lookup"><span data-stu-id="6b290-196">In September, I get the Azure Information Protection client installed and get trained on how to apply labels to documents.</span></span> <span data-ttu-id="6b290-197">(Informatiebescherming)</span><span class="sxs-lookup"><span data-stu-id="6b290-197">(Information protection)</span></span>

<span data-ttu-id="6b290-198">Het resultaat is een frequentie van 60 dagen tussen opeenvolgende gebruikersimplementaties.</span><span class="sxs-lookup"><span data-stu-id="6b290-198">The result is a 60-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="6b290-199">Het voordeel van deze implementatiestrategie is dat het minder tijd kost om de basisinfrastructuur van Microsoft 365 voor ondernemingen volledig te implementeren, zonder dat uw IT-afdeling en gebruikers tegelijkertijd met meerdere implementaties te maken krijgen.</span><span class="sxs-lookup"><span data-stu-id="6b290-199">The advantage to this deployment strategy is that it can take less time to fully deploy the Microsoft 365 for enterprise foundation infrastructure, without having your IT department and users deal with multiple rollouts the same time.</span></span>

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a><span data-ttu-id="6b290-200">Parallelle implementatie met overlappende implementatie van gebruikers (parallel 2)</span><span class="sxs-lookup"><span data-stu-id="6b290-200">Parallel deployment with overlapping user rollout (Parallel 2)</span></span>

<span data-ttu-id="6b290-201">Voor deze implementatiestrategie start u het volgende:</span><span class="sxs-lookup"><span data-stu-id="6b290-201">For this deployment strategy, you start the:</span></span>

- <span data-ttu-id="6b290-202">Proefimplementatie van de volgende fase tijdens het laatste deel van de gebruikersimplementatie van de huidige fase.</span><span class="sxs-lookup"><span data-stu-id="6b290-202">Pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
- <span data-ttu-id="6b290-203">De gebruikersimplementatie van de volgende fase tijdens de implementatie van de huidige fase op zodanige wijze dat er geen gebruikers zijn die meerdere fasen tegelijk doorlopen.</span><span class="sxs-lookup"><span data-stu-id="6b290-203">User rollout of the next phase during the user rollout of the current phase in such a way that no user is dealing with the rollouts of multiple phases at the same time.</span></span> <span data-ttu-id="6b290-204">Hierbij wordt ervan uitgegaan dat u elke fase van de Foundation-infrastructuur op dezelfde manier uitvouwt, zoals regio's, afdelingen of andere groepen.</span><span class="sxs-lookup"><span data-stu-id="6b290-204">This assumes that you are rolling out each phase of the foundation infrastructure in the same way, using regions, departments, or other groupings.</span></span>

<span data-ttu-id="6b290-205">Dit is een vereenvoudigde vergelijking tussen de verschillende implementatiestrategieën.</span><span class="sxs-lookup"><span data-stu-id="6b290-205">Here is a simplified comparison between the different deployment strategies.</span></span>

![De parallelle implementatie van fasen 2-6 met overlappende gebruikersimplementatie](../media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

<span data-ttu-id="6b290-207">Het eindresultaat luidt als volgt:</span><span class="sxs-lookup"><span data-stu-id="6b290-207">The end result is that:</span></span>

- <span data-ttu-id="6b290-208">Proefimplementaties gaan zonder pauze van de ene fase over in de volgende.</span><span class="sxs-lookup"><span data-stu-id="6b290-208">Pilot rollouts go from one phase to the next without a pause.</span></span>
- <span data-ttu-id="6b290-209">De gebruikersimplementatie voor een fase begint met het voltooien van de gebruikersimplementatie in de vorige fase, maar er wordt niet meer dan één fase tegelijk uitgerold.</span><span class="sxs-lookup"><span data-stu-id="6b290-209">The user rollout for a phase begins before the completion of the user rollout of the previous phase, but no individual user is rolling out more than one phase at a time.</span></span>

<span data-ttu-id="6b290-210">Dit is een vereenvoudigde gebruikerservaring voor prototypen als voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="6b290-210">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="6b290-211">In december moet ik mijn smartphone voor MFA gaan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6b290-211">In December, I need to use my smart phone for MFA.</span></span> <span data-ttu-id="6b290-212">(Identiteit)</span><span class="sxs-lookup"><span data-stu-id="6b290-212">(Identity)</span></span>
- <span data-ttu-id="6b290-213">In januari wordt Windows 10 Enterprise geïnstalleerd op mijn Windows 8.1-desktop.</span><span class="sxs-lookup"><span data-stu-id="6b290-213">In January, I get Windows 10 Enterprise installed on my Windows 8.1 desktop.</span></span> <span data-ttu-id="6b290-214">(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="6b290-214">(Windows 10 Enterprise)</span></span>
- <span data-ttu-id="6b290-215">In februari wordt Office 365 ProPlus geïnstalleerd, ter vervanging van Office 2013.</span><span class="sxs-lookup"><span data-stu-id="6b290-215">In February, I get Office 365 ProPlus installed, replacing Office 2013.</span></span> <span data-ttu-id="6b290-216">(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="6b290-216">(Office 365 ProPlus)</span></span>
- <span data-ttu-id="6b290-217">In maart worden de apparaatimplementatie en het app- en apparaatbeleid toegepast.</span><span class="sxs-lookup"><span data-stu-id="6b290-217">In March, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="6b290-218">(Mobile device management)</span><span class="sxs-lookup"><span data-stu-id="6b290-218">(Mobile device management)</span></span>
- <span data-ttu-id="6b290-219">In april wordt de Azure Information Protection-client geïnstalleerd en krijg ik training in het toepassen van labels op documenten.</span><span class="sxs-lookup"><span data-stu-id="6b290-219">In April, I get the Azure Information Protection client installed and get trained on how to apply labels to documents.</span></span> <span data-ttu-id="6b290-220">(Informatiebescherming)</span><span class="sxs-lookup"><span data-stu-id="6b290-220">(Information protection)</span></span>

<span data-ttu-id="6b290-221">Het resultaat is een frequentie van 30 dagen tussen opeenvolgende proefimplementaties.</span><span class="sxs-lookup"><span data-stu-id="6b290-221">The result is a 30-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="6b290-222">Hieronder ziet u een vereenvoudigde ervaring voor de eindgebruiker als voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="6b290-222">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="6b290-223">In januari moet ik mijn smartphone voor MFA gaan gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6b290-223">In January, I need to use my smart phone for MFA.</span></span> <span data-ttu-id="6b290-224">(Identiteit)</span><span class="sxs-lookup"><span data-stu-id="6b290-224">(Identity)</span></span>
- <span data-ttu-id="6b290-225">In februari wordt Windows 10 Enterprise geïnstalleerd op mijn Windows 8.1-desktop.</span><span class="sxs-lookup"><span data-stu-id="6b290-225">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop.</span></span> <span data-ttu-id="6b290-226">(Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="6b290-226">(Windows 10 Enterprise)</span></span>
- <span data-ttu-id="6b290-227">In maart wordt Office 365 ProPlus geïnstalleerd, ter vervanging van Office 2013.</span><span class="sxs-lookup"><span data-stu-id="6b290-227">In March, I get Office 365 ProPlus installed, replacing Office 2013.</span></span> <span data-ttu-id="6b290-228">(Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="6b290-228">(Office 365 ProPlus)</span></span>
- <span data-ttu-id="6b290-229">In april worden de apparaatimplementatie en het app- en apparaatbeleid toegepast.</span><span class="sxs-lookup"><span data-stu-id="6b290-229">In April, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="6b290-230">(Mobile device management)</span><span class="sxs-lookup"><span data-stu-id="6b290-230">(Mobile device management)</span></span>
- <span data-ttu-id="6b290-231">In mei wordt de Azure Information Protection-client geïnstalleerd en krijg ik training in het toepassen van labels op documenten.</span><span class="sxs-lookup"><span data-stu-id="6b290-231">In May, I get the Azure Information Protection client installed and get trained on how to apply labels to documents.</span></span> <span data-ttu-id="6b290-232">(Informatiebescherming)</span><span class="sxs-lookup"><span data-stu-id="6b290-232">(Information protection)</span></span>

<span data-ttu-id="6b290-233">Het resultaat is een frequentie van 30 dagen tussen opeenvolgende gebruikersimplementaties.</span><span class="sxs-lookup"><span data-stu-id="6b290-233">The result is a 30-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="6b290-234">Het voordeel van deze implementatiestrategie is dat het nog minder tijd kost om de basisinfrastructuur van Microsoft 365 voor ondernemingen volledig te implementeren, zonder dat eindgebruikers tegelijkertijd met meerdere implementaties te maken krijgen.</span><span class="sxs-lookup"><span data-stu-id="6b290-234">The advantage to this deployment strategy is that it can take even less time to fully deploy the Microsoft 365 for enterprise foundation infrastructure, still without having end-users deal with multiple rollouts the same time.</span></span> <span data-ttu-id="6b290-235">Gebruikers krijgen echter geen onderbreking tussen de opeenvolgende fasen.</span><span class="sxs-lookup"><span data-stu-id="6b290-235">However, users don’t get a break between successive phases.</span></span>

### <a name="up-front-infrastructure-and-rollout-of-the-end-to-end-configuration"></a><span data-ttu-id="6b290-236">Up-front infrastructuur en uitrol van de end-to-end configuratie</span><span class="sxs-lookup"><span data-stu-id="6b290-236">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="6b290-237">Voor kleinere organisaties die de fasen 2-6 kunnen comprimeren tot één implementatiesegment, ziet de resulterende implementatie er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="6b290-237">For smaller organizations with the ability to compress phases 2-6 into a single deployment segment, the resulting deployment looks like this:</span></span>
 
![Up-front infrastructuur en uitrol van de end-to-end configuratie](../media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

<span data-ttu-id="6b290-239">De IT-afdeling configureert de infrastructuur voor fase 2-6 en rolt vervolgens uit naar de prototypegebruikers, om te controleren op end-to-end-functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="6b290-239">The IT department configures the infrastructure for phases 2-6, then rolls out to the pilot users to check for the end-to-end functionality.</span></span> <span data-ttu-id="6b290-240">Prototypegebruikers krijgen bijvoorbeeld al deze functionaliteit tegelijkertijd:</span><span class="sxs-lookup"><span data-stu-id="6b290-240">For example, pilot users get all of this functionality at the same time:</span></span>

- <span data-ttu-id="6b290-241">MFA en andere identiteitsfuncties (Identiteit)</span><span class="sxs-lookup"><span data-stu-id="6b290-241">MFA and other identity features (Identity)</span></span>
- <span data-ttu-id="6b290-242">Windows 10 Enterprise op Windows-apparaten (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="6b290-242">Windows 10 Enterprise on Windows devices (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="6b290-243">Office 365 ProPlus voor de Office-suite (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="6b290-243">Office 365 ProPlus for the Office suite (Office 365 ProPlus)</span></span>
- <span data-ttu-id="6b290-244">App- en apparaatinstellingen (Mobile Device Management)</span><span class="sxs-lookup"><span data-stu-id="6b290-244">App and device policies (Mobile device management)</span></span>
- <span data-ttu-id="6b290-245">Azure Information Protection-client geïnstalleerd en training over het toepassen van labels op documenten (informatiebeveiliging)</span><span class="sxs-lookup"><span data-stu-id="6b290-245">Azure Information Protection client installed and training on how to apply labels to documents (Information protection)</span></span>

<span data-ttu-id="6b290-246">Zodra de proefimplementatie is voltooid, begint de implementatie van de gebruikers, waarbij elke gebruiker tegelijkertijd alle functionaliteit krijgt.</span><span class="sxs-lookup"><span data-stu-id="6b290-246">Once the pilot rollout is concluded, the user rollout begins in which each user gets all the functionality the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="6b290-247">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="6b290-247">Next step</span></span>

<span data-ttu-id="6b290-248">Start de implementatie van Microsoft 365 voor ondernemingen met de [basisinfrastructuur](deploy-foundation-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="6b290-248">Start your deployment of Microsoft 365 for enterprise with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
