---
title: Evalueer Microsoft 365 Defender
description: Stel uw proefabonnement voor Microsoft 365 Defender of pilot omgeving in om de beveiligingsoplossing voor het beschermen van apparaten, identiteit, gegevens en toepassingen in uw organisatie uit te proberen.
keywords: Microsoft Threat Protection-proefversie, Microsoft Threat Protection, Microsoft Threat Protection, Microsoft Threat Protection evaluatie lab, Microsoft Threat Protection pilot, Cyber beveiliging, geavanceerde, permanente bedreiging, Enterprise-gebruikers, gegevens, toepassingen, incidenten, automatisch onderzoek en herstel, geavanceerde jacht
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 8504b036203e1f73dc9e0a0d79a228425fb88bfa
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659631"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="f4dc6-104">Een Microsoft 365 Defender-proef Lab of pilot omgeving maken</span><span class="sxs-lookup"><span data-stu-id="f4dc6-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f4dc6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f4dc6-105">**Applies to:**</span></span>
- <span data-ttu-id="f4dc6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4dc6-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="f4dc6-107">Deze handleiding helpt u bij het instellen van een lab-omgeving met gebruikers en groepen, en begeleidt u door de configuratie van de mogelijkheden in Microsoft 365 Defender, zodat u een aanvals probleem kunt nabootsen en een zinvolle resultaten kunt krijgen.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="f4dc6-108">Het doel van het maken van deze proefversie of pilot omgeving is het illustreren van de allesomvattende en geïntegreerde Microsoft 365 Defender-mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="f4dc6-109">Ervaar hoe deze intelligente beveiligingsoplossing detecteert, voorkomt automatisch onderzoek en reageert op geavanceerde bedreigingen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="f4dc6-110">U wordt begeleid bij de stappen om uw proefversie van Microsoft 365 Defender te starten op basis van de aanbevolen implementatie paden.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="f4dc6-111">Het doel is om u te helpen bij het instellen van de beveiligingsoplossing in een lab-omgeving met een proefaccount, of in een testomgeving in productie met een volledige licentie.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="f4dc6-112">Het voorbereiden van uw proefversie of pilot omgeving kan u helpen bij het presenteren van beveiligingsactiviteiten voor besluitvormings Programma's in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="f4dc6-113">Wanneer u klaar bent met het uitvoeren van uw aanvals simulaties en tevreden bent over de resultaten, kunt u deze in uw organisatie volledig implementeren en operationalize met behulp van de Help van Microsoft Technical Sales professionals of experts in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="f4dc6-114">Deze handleiding helpt u bij:</span><span class="sxs-lookup"><span data-stu-id="f4dc6-114">This guide will help you:</span></span>
- <span data-ttu-id="f4dc6-115">Uw testserver en computers instellen</span><span class="sxs-lookup"><span data-stu-id="f4dc6-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="f4dc6-116">Active Directory configureren met gebruikers en groepen</span><span class="sxs-lookup"><span data-stu-id="f4dc6-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="f4dc6-117">Microsoft Defender voor identiteit instellen en configureren, Microsoft Defender voor Office 365, Microsoft Defender voor eindpunt en beveiliging van de Cloud-app</span><span class="sxs-lookup"><span data-stu-id="f4dc6-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="f4dc6-118">Lokale beleidsregels instellen voor uw server en computers</span><span class="sxs-lookup"><span data-stu-id="f4dc6-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="f4dc6-119">Een aanval in de bedreiging nabootsen voor het genereren van een test incident of waarschuwing in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4dc6-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="f4dc6-120">Voor optimale resultaten volgt u de installatie-instructies voor Lab zo sterk mogelijk.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="f4dc6-121">Implementatiefasen</span><span class="sxs-lookup"><span data-stu-id="f4dc6-121">Deployment phases</span></span>

<span data-ttu-id="f4dc6-122">Er zijn drie fasen in het maken van een proefversie van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Implementatiefasen: voorbereiden, instellen, onboardd](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="f4dc6-124">Fase</span><span class="sxs-lookup"><span data-stu-id="f4dc6-124">Phase</span></span> | <span data-ttu-id="f4dc6-125">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f4dc6-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="f4dc6-126">Fase 1: voorbereiding</span><span class="sxs-lookup"><span data-stu-id="f4dc6-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="f4dc6-127">Meer informatie over wat u moet doen wanneer u Microsoft 365 Defender implementeert in een proefversie van het lab of een testomgeving:</span><span class="sxs-lookup"><span data-stu-id="f4dc6-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="f4dc6-128">-Belanghebbenden en afmelden</span><span class="sxs-lookup"><span data-stu-id="f4dc6-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="f4dc6-129">-Aandachtspunten voor de omgeving</span><span class="sxs-lookup"><span data-stu-id="f4dc6-129">- Environment considerations</span></span> <br><span data-ttu-id="f4dc6-130">-Access</span><span class="sxs-lookup"><span data-stu-id="f4dc6-130">- Access</span></span> <br><span data-ttu-id="f4dc6-131">-Configuratie van Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f4dc6-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="f4dc6-132">-De configuratie volgorde</span><span class="sxs-lookup"><span data-stu-id="f4dc6-132">- Configuration order</span></span>
|[<span data-ttu-id="f4dc6-133">Fase 2: instellen</span><span class="sxs-lookup"><span data-stu-id="f4dc6-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="f4dc6-134">Voer de volgende stappen uit om toegang te krijgen tot het Microsoft 365-Beveiligingscentrum voor het instellen van uw proefversie van Microsoft 365 Defender of prototype.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="f4dc6-135">U wordt begeleid bij:</span><span class="sxs-lookup"><span data-stu-id="f4dc6-135">You'll be guided to:</span></span><br><br><span data-ttu-id="f4dc6-136">-Registreren voor Microsoft 365 E5-proefabonnement</span><span class="sxs-lookup"><span data-stu-id="f4dc6-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="f4dc6-137">Domein configureren</span><span class="sxs-lookup"><span data-stu-id="f4dc6-137">- Configure domain</span></span><br><span data-ttu-id="f4dc6-138">-Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="f4dc6-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="f4dc6-139">-De wizard Setup voltooien in de portal</span><span class="sxs-lookup"><span data-stu-id="f4dc6-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="f4dc6-140">Fase 3: & onboard configureren</span><span class="sxs-lookup"><span data-stu-id="f4dc6-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="f4dc6-141">Configureer elke Microsoft 365 Defender-pijler pijler en de ingebouwde eindpunten.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="f4dc6-142">U wordt begeleid bij:</span><span class="sxs-lookup"><span data-stu-id="f4dc6-142">You'll be guided to:</span></span><br><br><span data-ttu-id="f4dc6-143">-Microsoft Defender voor Office 365 configureren</span><span class="sxs-lookup"><span data-stu-id="f4dc6-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="f4dc6-144">-Beveiliging van Microsoft Cloud-app configureren</span><span class="sxs-lookup"><span data-stu-id="f4dc6-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="f4dc6-145">-Microsoft Defender configureren voor identiteit</span><span class="sxs-lookup"><span data-stu-id="f4dc6-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="f4dc6-146">-Microsoft Defender voor eindpunt configureren</span><span class="sxs-lookup"><span data-stu-id="f4dc6-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="f4dc6-147">Wanneer u klaar bent met deze handleiding, hebt u de betrokken belanghebbenden geïdentificeerd en moeten ze de juiste machtigingen hebben, de juiste toegangsmachtigingen hebben, zich hebben geregistreerd voor proefversies, geconfigureerde domeinen en elk van de Microsoft 365-werkbalken, en de eindpunten worden in de service gehouden.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="f4dc6-148">Belangrijkste mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="f4dc6-148">Key capabilities</span></span>

<span data-ttu-id="f4dc6-149">Hoewel Microsoft 365 Defender veel mogelijkheden biedt, kunt u het hoofddoel van deze Implementatiehandleiding gebruiken om u op weg te helpen.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="f4dc6-150">Daarnaast kunt u met deze richtlijnen aan de slag met de volgende mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="f4dc6-151">Mogelijkheid</span><span class="sxs-lookup"><span data-stu-id="f4dc6-151">Capability</span></span> | <span data-ttu-id="f4dc6-152">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f4dc6-152">Description</span></span> 
:---|:---
<span data-ttu-id="f4dc6-153">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f4dc6-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="f4dc6-154">Beschermt uw volledige Office 365-envrionment vanaf de bedreiging van vandaag</span><span class="sxs-lookup"><span data-stu-id="f4dc6-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="f4dc6-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="f4dc6-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="f4dc6-156">Identificeert en detecteert bedreigingen voor de compromisloze identiteiten en schadelijke Insider-acties.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="f4dc6-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f4dc6-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="f4dc6-158">Zorgt voor uitgebreide informatie over het beheren van gegevens en het vinden van cyberthreats in de cloudservices.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="f4dc6-159">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f4dc6-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="f4dc6-160">Maakt, detecteert en levert antwoord mogelijkheden voor geavanceerde bedreigingen met uitgebreide beveiliging van het eindpunt.</span><span class="sxs-lookup"><span data-stu-id="f4dc6-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="f4dc6-161">In bereik</span><span class="sxs-lookup"><span data-stu-id="f4dc6-161">In scope</span></span>

<span data-ttu-id="f4dc6-162">De volgende taken bevinden zich in het bereik van deze handleiding:</span><span class="sxs-lookup"><span data-stu-id="f4dc6-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="f4dc6-163">Azure Active Directory instellen</span><span class="sxs-lookup"><span data-stu-id="f4dc6-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="f4dc6-164">Microsoft 365 Defender instellen</span><span class="sxs-lookup"><span data-stu-id="f4dc6-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="f4dc6-165">Registreren voor Microsoft 365 E5-proefabonnement of de volledige licentie gebruiken als u een pilot uitvoert</span><span class="sxs-lookup"><span data-stu-id="f4dc6-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="f4dc6-166">Domein configureren</span><span class="sxs-lookup"><span data-stu-id="f4dc6-166">Configure domain</span></span>
    -   <span data-ttu-id="f4dc6-167">Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="f4dc6-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="f4dc6-168">De installatiewizard in de portal voltooien</span><span class="sxs-lookup"><span data-stu-id="f4dc6-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="f4dc6-169">Alle Microsoft 365 Defender-pijlers configureren op basis van aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="f4dc6-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="f4dc6-170">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f4dc6-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="f4dc6-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="f4dc6-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="f4dc6-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f4dc6-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="f4dc6-173">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f4dc6-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="f4dc6-174">Buiten bereik</span><span class="sxs-lookup"><span data-stu-id="f4dc6-174">Out of scope</span></span>

<span data-ttu-id="f4dc6-175">Het volgende is niet het bereik van deze Implementatiehandleiding:</span><span class="sxs-lookup"><span data-stu-id="f4dc6-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="f4dc6-176">Configuratie van oplossingen van derden die kunnen worden geïntegreerd met Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4dc6-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="f4dc6-177">Penetratie tests in productieomgeving</span><span class="sxs-lookup"><span data-stu-id="f4dc6-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="f4dc6-178">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="f4dc6-178">Next step</span></span>
<span data-ttu-id="f4dc6-179">[Fase 1: voorbereiding](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="f4dc6-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="f4dc6-180">Uw proefabonnement voor Microsoft 365 Defender of pilot omgeving voorbereiden</span><span class="sxs-lookup"><span data-stu-id="f4dc6-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
