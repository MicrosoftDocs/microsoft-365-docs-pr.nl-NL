---
title: Microsoft 365 Defender evalueren
description: Stel uw testtestomgeving of pilotomgeving van Microsoft 365 Defender in om de beveiligingsoplossing uit te proberen en te gebruiken die is ontworpen om apparaten, identiteit, gegevens en toepassingen in uw organisatie te beschermen.
keywords: Microsoft Threat Protection proefversie, probeer Microsoft Threat Protection, evalueer Microsoft Threat Protection, Microsoft Threat Protection evaluation lab, Microsoft Threat Protection pilot, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6735817a71f9fb50843acad3a13596ec247aa407
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930208"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="f5cb1-104">Een testtest of pilotomgeving met Microsoft 365 Defender maken</span><span class="sxs-lookup"><span data-stu-id="f5cb1-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f5cb1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f5cb1-105">**Applies to:**</span></span>
- <span data-ttu-id="f5cb1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5cb1-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="f5cb1-107">Deze handleiding helpt u bij het instellen van een testomgeving met gebruikers en groepen en begeleidt u vervolgens bij de configuratie van de mogelijkheden in Microsoft 365 Defender, zodat u een bedreigings-aanval kunt nabootsen en een zinvolle proefresultaat kunt verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="f5cb1-108">Het doel van het maken van deze testtestomgeving of pilotomgeving is het illustreren van de uitgebreide en geïntegreerde mogelijkheden van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="f5cb1-109">Ervaar hoe deze intelligente beveiligingsoplossing geavanceerde bedreigingen voor uw organisatie detecteert, voorkomt, automatisch onderzoek doet en reageert op geavanceerde bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="f5cb1-110">U wordt door de stappen begeleid bij het starten van uw evaluatie met Microsoft 365 Defender op basis van de aanbevolen implementatiepaden.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="f5cb1-111">Het doel is om de beveiligingsoplossing in te stellen in een testomgeving met een proefaccount of in een pilotomgeving waarin een volledige licentie wordt geproduceerd.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="f5cb1-112">Door uw testomgeving of pilotomgeving voor te bereiden, kunt u gebruiks zaken voor beveiligingsbewerkingen presenteren aan besluitvormers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="f5cb1-113">Wanneer u klaar bent met het uitvoeren van uw aanvalsen en tevreden bent met de resultaten, kunt u deze volledig implementeren en operationeel maken in uw organisatie met behulp van technische verkoopmedewerkers of experts van Microsoft in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="f5cb1-114">Deze handleiding helpt u bij het volgende:</span><span class="sxs-lookup"><span data-stu-id="f5cb1-114">This guide will help you:</span></span>
- <span data-ttu-id="f5cb1-115">De testserver en computers instellen</span><span class="sxs-lookup"><span data-stu-id="f5cb1-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="f5cb1-116">Active Directory configureren met gebruikers en groepen</span><span class="sxs-lookup"><span data-stu-id="f5cb1-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="f5cb1-117">Microsoft Defender voor identiteit, Microsoft Defender voor Office 365, Microsoft Defender voor eindpunt en Microsoft Cloud App-beveiliging instellen en configureren</span><span class="sxs-lookup"><span data-stu-id="f5cb1-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="f5cb1-118">Lokaal beleid instellen voor uw server en computers</span><span class="sxs-lookup"><span data-stu-id="f5cb1-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="f5cb1-119">Een bedreigings-aanval nabootsen om een test-incident of waarschuwing te genereren in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5cb1-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="f5cb1-120">Voor optimale resultaten volgt u de instructies voor het testen van de test zo goed mogelijk.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="f5cb1-121">Implementatiefasen</span><span class="sxs-lookup"><span data-stu-id="f5cb1-121">Deployment phases</span></span>

<span data-ttu-id="f5cb1-122">Er zijn drie fasen bij het maken van een testomgeving met Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Implementatiefasen: voorbereiden, instellen, onboarden](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="f5cb1-124">Fase</span><span class="sxs-lookup"><span data-stu-id="f5cb1-124">Phase</span></span> | <span data-ttu-id="f5cb1-125">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f5cb1-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="f5cb1-126">Fase 1: Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="f5cb1-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="f5cb1-127">Informatie over waar u rekening mee moet houden bij het implementeren van Microsoft 365 Defender in een testtestomgeving of pilotomgeving:</span><span class="sxs-lookup"><span data-stu-id="f5cb1-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="f5cb1-128">- Belanghebbenden en sign-off</span><span class="sxs-lookup"><span data-stu-id="f5cb1-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="f5cb1-129">- Aandachtspunten voor de omgeving</span><span class="sxs-lookup"><span data-stu-id="f5cb1-129">- Environment considerations</span></span> <br><span data-ttu-id="f5cb1-130">- Access</span><span class="sxs-lookup"><span data-stu-id="f5cb1-130">- Access</span></span> <br><span data-ttu-id="f5cb1-131">- Azure Active Directory instellen</span><span class="sxs-lookup"><span data-stu-id="f5cb1-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="f5cb1-132">- Configuratieorder</span><span class="sxs-lookup"><span data-stu-id="f5cb1-132">- Configuration order</span></span>
|[<span data-ttu-id="f5cb1-133">Fase 2: Installatie</span><span class="sxs-lookup"><span data-stu-id="f5cb1-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="f5cb1-134">Ga als eerste te werk om het Microsoft 365-beveiligingscentrum te openen voor het instellen van uw testomgeving of pilotomgeving met Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="f5cb1-135">U wordt begeleid bij het volgende:</span><span class="sxs-lookup"><span data-stu-id="f5cb1-135">You'll be guided to:</span></span><br><br><span data-ttu-id="f5cb1-136">- Aanmelden voor de proefversie van Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f5cb1-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="f5cb1-137">- Domein configureren</span><span class="sxs-lookup"><span data-stu-id="f5cb1-137">- Configure domain</span></span><br><span data-ttu-id="f5cb1-138">- Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="f5cb1-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="f5cb1-139">- Voltooi de installatiewizard in de portal</span><span class="sxs-lookup"><span data-stu-id="f5cb1-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="f5cb1-140">Fase 3: & onboard</span><span class="sxs-lookup"><span data-stu-id="f5cb1-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="f5cb1-141">Configureer elke Microsoft 365 Defender- en onboard-eindpunten.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="f5cb1-142">U wordt begeleid bij het volgende:</span><span class="sxs-lookup"><span data-stu-id="f5cb1-142">You'll be guided to:</span></span><br><br><span data-ttu-id="f5cb1-143">- Microsoft Defender voor Office 365 configureren</span><span class="sxs-lookup"><span data-stu-id="f5cb1-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="f5cb1-144">- Microsoft Cloud App-beveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="f5cb1-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="f5cb1-145">- Microsoft Defender configureren voor identiteit</span><span class="sxs-lookup"><span data-stu-id="f5cb1-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="f5cb1-146">- Microsoft Defender configureren voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="f5cb1-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="f5cb1-147">Nadat u deze handleiding hebt voltooid, zou u de belanghebbenden hebben geïdentificeerd en de vereiste goedkeuringen hebben, de juiste toegangsrechten hebben, zich hebben aangemeld voor een proefabonnement, geconfigureerde domeinen en alle Microsoft 365 Defender-pilaren en worden uw eindpunten onboarded bij de service.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="f5cb1-148">Belangrijkste mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="f5cb1-148">Key capabilities</span></span>

<span data-ttu-id="f5cb1-149">Hoewel Microsoft 365 Defender vele mogelijkheden biedt, is het primaire doel van deze implementatiehandleiding om u op weg te helpen met onboarding-apparaten.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="f5cb1-150">Naast onboarding krijgt u met deze richtlijnen de volgende mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="f5cb1-151">Mogelijkheid</span><span class="sxs-lookup"><span data-stu-id="f5cb1-151">Capability</span></span> | <span data-ttu-id="f5cb1-152">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f5cb1-152">Description</span></span> 
:---|:---
<span data-ttu-id="f5cb1-153">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f5cb1-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="f5cb1-154">Beschermt uw volledige Office 365-omgeving tegen de bedreigingen van vandaag</span><span class="sxs-lookup"><span data-stu-id="f5cb1-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="f5cb1-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="f5cb1-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="f5cb1-156">Identificeert en detecteert bedreigingen op gekromde identiteiten en kwaadaardige Insider-acties.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="f5cb1-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f5cb1-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="f5cb1-158">Biedt uitgebreide zichtbaarheid, controle over gegevensreizen en het detecteren van cyberaanvallen in cloudservices.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="f5cb1-159">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f5cb1-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="f5cb1-160">Voorkomt, detecteert en biedt antwoordmogelijkheden voor geavanceerde bedreigingen met een uitgebreide eindpuntbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="f5cb1-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="f5cb1-161">Binnen het bereik</span><span class="sxs-lookup"><span data-stu-id="f5cb1-161">In scope</span></span>

<span data-ttu-id="f5cb1-162">De volgende taken vallen binnen het kader van deze handleiding:</span><span class="sxs-lookup"><span data-stu-id="f5cb1-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="f5cb1-163">Azure Active Directory instellen</span><span class="sxs-lookup"><span data-stu-id="f5cb1-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="f5cb1-164">Microsoft 365 Defender instellen</span><span class="sxs-lookup"><span data-stu-id="f5cb1-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="f5cb1-165">Meld u aan voor de proefversie van Microsoft 365 E5 of gebruik uw volledige licentie als u een testfase hebt</span><span class="sxs-lookup"><span data-stu-id="f5cb1-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="f5cb1-166">Domein configureren</span><span class="sxs-lookup"><span data-stu-id="f5cb1-166">Configure domain</span></span>
    -   <span data-ttu-id="f5cb1-167">Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="f5cb1-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="f5cb1-168">De installatiewizard in de portal voltooien</span><span class="sxs-lookup"><span data-stu-id="f5cb1-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="f5cb1-169">Alle Microsoft 365 Defender-pilaren configureren op basis van best practices</span><span class="sxs-lookup"><span data-stu-id="f5cb1-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="f5cb1-170">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f5cb1-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="f5cb1-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="f5cb1-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="f5cb1-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f5cb1-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="f5cb1-173">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f5cb1-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="f5cb1-174">Buiten het bereik</span><span class="sxs-lookup"><span data-stu-id="f5cb1-174">Out of scope</span></span>

<span data-ttu-id="f5cb1-175">Deze implementatiehandleiding valt buiten het bereik:</span><span class="sxs-lookup"><span data-stu-id="f5cb1-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="f5cb1-176">Configuratie van oplossingen van derden die kunnen worden geïntegreerd met Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5cb1-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="f5cb1-177">Proeftests in productieomgeving</span><span class="sxs-lookup"><span data-stu-id="f5cb1-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="f5cb1-178">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="f5cb1-178">Next step</span></span>
<span data-ttu-id="f5cb1-179">[Fase 1: Voorbereiden](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="f5cb1-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="f5cb1-180">De testtest of testomgeving van Microsoft 365 Defender voorbereiden</span><span class="sxs-lookup"><span data-stu-id="f5cb1-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
