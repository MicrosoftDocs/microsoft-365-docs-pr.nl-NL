---
title: Microsoft 365 Defender evalueren
description: Stel uw testlaboratorium Microsoft 365 Defender testomgeving in om de beveiligingsoplossing uit te proberen en te ervaren die is ontworpen om apparaten, identiteit, gegevens en toepassingen in uw organisatie te beschermen.
keywords: Microsoft 365 Defender proefversie, probeer Microsoft 365 Defender, evalueer Microsoft 365 Defender, Microsoft 365 Defender evaluatielaboratorium, Microsoft 365 Defender-pilot, cyberbeveiliging, geavanceerde permanente bedreiging, bedrijfsbeveiliging, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerd zoeken
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c260588b80d8325567b74148a7a62586cfbc707
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/16/2021
ms.locfileid: "53457950"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="bf43c-104">Een Microsoft 365 Defender proeflaboratorium of testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="bf43c-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bf43c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bf43c-105">**Applies to:**</span></span>
- <span data-ttu-id="bf43c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf43c-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="bf43c-107">Deze handleiding helpt u bij het instellen van een labomgeving met gebruikers en groepen en begeleidt u vervolgens bij de configuratie van de mogelijkheden in Microsoft 365 Defender, zodat u een bedreigingsaanval kunt nabootsen en een zinvol proefresultaat kunt verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="bf43c-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="bf43c-108">Het doel van het maken van dit proeflaboratorium of testomgeving is het illustreren van de uitgebreide en geïntegreerde Microsoft 365 Defender mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="bf43c-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="bf43c-109">Ervaar hoe deze intelligente beveiligingsoplossing geavanceerde bedreigingen in uw organisatie detecteert, voorkomt, automatisch onderzoekt en beantwoordt.</span><span class="sxs-lookup"><span data-stu-id="bf43c-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="bf43c-110">U wordt begeleid bij de stappen om uw evaluatie Microsoft 365 Defender op basis van de aanbevolen implementatiepaden.</span><span class="sxs-lookup"><span data-stu-id="bf43c-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="bf43c-111">Het doel is om u te helpen bij het instellen van de beveiligingsoplossing in een labomgeving met een proefaccount of in een testomgeving in productie met een volledige licentie.</span><span class="sxs-lookup"><span data-stu-id="bf43c-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="bf43c-112">Als u uw proeflaboratorium of testomgeving voorbereidt, kunt u gebruiksgevallen voor beveiligingsbewerkingen presenteren aan besluitvormers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="bf43c-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="bf43c-113">Wanneer u klaar bent met het uitvoeren van uw aanvalssimulaties en tevreden bent over de resultaten, kunt u deze volledig implementeren en operationeel maken in uw organisatie met de hulp van Technische Verkoopmedewerkers of experts van Microsoft in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="bf43c-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="bf43c-114">Deze handleiding helpt u:</span><span class="sxs-lookup"><span data-stu-id="bf43c-114">This guide will help you:</span></span>
- <span data-ttu-id="bf43c-115">Uw labserver en -computers instellen</span><span class="sxs-lookup"><span data-stu-id="bf43c-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="bf43c-116">Active Directory configureren met gebruikers en groepen</span><span class="sxs-lookup"><span data-stu-id="bf43c-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="bf43c-117">Microsoft Defender voor identiteit instellen en configureren, Microsoft Defender voor Office 365, Microsoft Defender voor Eindpunt en Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bf43c-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="bf43c-118">Lokaal beleid instellen voor uw server en computers</span><span class="sxs-lookup"><span data-stu-id="bf43c-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="bf43c-119">Een bedreigingsaanval nabootsen om een testincident of waarschuwing te genereren in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf43c-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="bf43c-120">Voor optimale resultaten volgt u de instructies voor het instellen van het lab zo goed mogelijk.</span><span class="sxs-lookup"><span data-stu-id="bf43c-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="bf43c-121">Implementatiefasen</span><span class="sxs-lookup"><span data-stu-id="bf43c-121">Deployment phases</span></span>

<span data-ttu-id="bf43c-122">Er zijn drie fasen in het maken van een Microsoft 365 Defender proeflabomgeving.</span><span class="sxs-lookup"><span data-stu-id="bf43c-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Implementatiefasen: voorbereiden, instellen, onboard](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="bf43c-124">Fase</span><span class="sxs-lookup"><span data-stu-id="bf43c-124">Phase</span></span> | <span data-ttu-id="bf43c-125">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="bf43c-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="bf43c-126">Fase 1: Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="bf43c-126">Phase 1: Prepare</span></span>](prepare-m365d-eval.md)| <span data-ttu-id="bf43c-127">Lees waar u rekening mee moet houden bij het implementeren van Microsoft 365 Defender in een proeflaboratorium of testomgeving:</span><span class="sxs-lookup"><span data-stu-id="bf43c-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="bf43c-128">- Belanghebbenden en aanmelding</span><span class="sxs-lookup"><span data-stu-id="bf43c-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="bf43c-129">- Milieuoverwegingen</span><span class="sxs-lookup"><span data-stu-id="bf43c-129">- Environment considerations</span></span> <br><span data-ttu-id="bf43c-130">- Access</span><span class="sxs-lookup"><span data-stu-id="bf43c-130">- Access</span></span> <br><span data-ttu-id="bf43c-131">- Azure Active Directory instellen</span><span class="sxs-lookup"><span data-stu-id="bf43c-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="bf43c-132">- Configuratieorder</span><span class="sxs-lookup"><span data-stu-id="bf43c-132">- Configuration order</span></span>
|[<span data-ttu-id="bf43c-133">Fase 2: Instellen</span><span class="sxs-lookup"><span data-stu-id="bf43c-133">Phase 2: Setup</span></span>](setup-m365deval.md)|  <span data-ttu-id="bf43c-134">Neem de eerste stappen om toegang te krijgen Microsoft 365 beveiligingscentrum om uw Microsoft 365 Defender proeflaboratorium of testomgeving in te stellen.</span><span class="sxs-lookup"><span data-stu-id="bf43c-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="bf43c-135">U wordt begeleid naar:</span><span class="sxs-lookup"><span data-stu-id="bf43c-135">You'll be guided to:</span></span><br><br><span data-ttu-id="bf43c-136">- Registreren voor Microsoft 365 E5 proefversie</span><span class="sxs-lookup"><span data-stu-id="bf43c-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="bf43c-137">- Domein configureren</span><span class="sxs-lookup"><span data-stu-id="bf43c-137">- Configure domain</span></span><br><span data-ttu-id="bf43c-138">- Licenties Microsoft 365 E5 toewijzen</span><span class="sxs-lookup"><span data-stu-id="bf43c-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="bf43c-139">- De installatiewizard in de portal voltooien</span><span class="sxs-lookup"><span data-stu-id="bf43c-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="bf43c-140">Fase 3: Configureren & Onboard</span><span class="sxs-lookup"><span data-stu-id="bf43c-140">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="bf43c-141">Configureer elke Microsoft 365 Defender en onboard eindpunten.</span><span class="sxs-lookup"><span data-stu-id="bf43c-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="bf43c-142">U wordt begeleid naar:</span><span class="sxs-lookup"><span data-stu-id="bf43c-142">You'll be guided to:</span></span><br><br><span data-ttu-id="bf43c-143">- Microsoft Defender configureren voor Office 365</span><span class="sxs-lookup"><span data-stu-id="bf43c-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="bf43c-144">- Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bf43c-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="bf43c-145">- Microsoft Defender configureren voor identiteit</span><span class="sxs-lookup"><span data-stu-id="bf43c-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="bf43c-146">- Microsoft Defender configureren voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="bf43c-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="bf43c-147">Nadat u deze handleiding hebt voltooid, hebt u de betrokken belanghebbenden en de vereiste goedkeuringen geïdentificeerd, hebt u de juiste toegangsmachtigingen, hebt u zich aangemeld voor proefversies, geconfigureerde domeinen en elk van de Microsoft 365 Defender-pilaren, en worden uw eindpunten aan de service aangemeld.</span><span class="sxs-lookup"><span data-stu-id="bf43c-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="bf43c-148">Belangrijke mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="bf43c-148">Key capabilities</span></span>

<span data-ttu-id="bf43c-149">Hoewel Microsoft 365 Defender mogelijkheden biedt, is het primaire doel van deze implementatiehandleiding om aan de slag te gaan met onboarding-apparaten.</span><span class="sxs-lookup"><span data-stu-id="bf43c-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="bf43c-150">Naast onboarding kunt u met deze richtlijnen aan de slag met de volgende mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="bf43c-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="bf43c-151">Mogelijkheid</span><span class="sxs-lookup"><span data-stu-id="bf43c-151">Capability</span></span> | <span data-ttu-id="bf43c-152">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="bf43c-152">Description</span></span> 
:---|:---
<span data-ttu-id="bf43c-153">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="bf43c-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="bf43c-154">Beschermt uw hele Office 365 envrionment tegen de huidige bedreigingen</span><span class="sxs-lookup"><span data-stu-id="bf43c-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="bf43c-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="bf43c-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="bf43c-156">Identificeert en detecteert bedreigingen op gecompromitteerde identiteiten en kwaadaardige insideracties.</span><span class="sxs-lookup"><span data-stu-id="bf43c-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="bf43c-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bf43c-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="bf43c-158">Biedt uitgebreide zichtbaarheid, beheer gegevensreizen en detecteer cyberthreats in cloudservices.</span><span class="sxs-lookup"><span data-stu-id="bf43c-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="bf43c-159">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="bf43c-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="bf43c-160">Voorkomt, detecteert en biedt antwoordmogelijkheden voor geavanceerde bedreigingen met uitgebreide eindpuntbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="bf43c-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="bf43c-161">In bereik</span><span class="sxs-lookup"><span data-stu-id="bf43c-161">In scope</span></span>

<span data-ttu-id="bf43c-162">De volgende taken vallen onder het bereik van deze handleiding:</span><span class="sxs-lookup"><span data-stu-id="bf43c-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="bf43c-163">Een Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bf43c-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="bf43c-164">Een Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf43c-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="bf43c-165">Meld u aan voor Microsoft 365 E5 proefversie of gebruik uw volledige licentie als u een pilot gebruikt</span><span class="sxs-lookup"><span data-stu-id="bf43c-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="bf43c-166">Domein configureren</span><span class="sxs-lookup"><span data-stu-id="bf43c-166">Configure domain</span></span>
    -   <span data-ttu-id="bf43c-167">Licenties Microsoft 365 E5 toewijzen</span><span class="sxs-lookup"><span data-stu-id="bf43c-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="bf43c-168">De installatiewizard in de portal voltooien</span><span class="sxs-lookup"><span data-stu-id="bf43c-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="bf43c-169">Alle pilaren Microsoft 365 Defender op basis van best practices configureren</span><span class="sxs-lookup"><span data-stu-id="bf43c-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="bf43c-170">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="bf43c-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="bf43c-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="bf43c-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="bf43c-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bf43c-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="bf43c-173">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="bf43c-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="bf43c-174">Buiten bereik</span><span class="sxs-lookup"><span data-stu-id="bf43c-174">Out of scope</span></span>

<span data-ttu-id="bf43c-175">De volgende opties vallen buiten het bereik van deze implementatiehandleiding:</span><span class="sxs-lookup"><span data-stu-id="bf43c-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="bf43c-176">Configuratie van oplossingen van derden die kunnen worden geïntegreerd met Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf43c-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="bf43c-177">Penetratietests in de productieomgeving</span><span class="sxs-lookup"><span data-stu-id="bf43c-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="bf43c-178">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="bf43c-178">Next step</span></span>
<span data-ttu-id="bf43c-179">[Fase 1: Voorbereiden](prepare-m365d-eval.md) 
</span><span class="sxs-lookup"><span data-stu-id="bf43c-179">[Phase 1: Prepare](prepare-m365d-eval.md) 
</span></span><br> <span data-ttu-id="bf43c-180">Uw proeflaboratorium Microsoft 365 Defender testomgeving voorbereiden</span><span class="sxs-lookup"><span data-stu-id="bf43c-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
