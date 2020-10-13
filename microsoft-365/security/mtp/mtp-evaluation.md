---
title: Microsoft Threat Protection evalueren
description: Stel uw Microsoft Threat Protection-proef Lab of pilot omgeving in om de beveiligingsoplossing voor het beschermen van apparaten, identiteit, gegevens en toepassingen in uw organisatie uit te proberen.
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
ms.openlocfilehash: d3f63c8ac4ba82a80c365dce564bbd8d3dd4da4b
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447117"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="bf45c-104">Een Microsoft Threat Protection-proefversie Lab of pilot omgeving maken</span><span class="sxs-lookup"><span data-stu-id="bf45c-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bf45c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bf45c-105">**Applies to:**</span></span>
- <span data-ttu-id="bf45c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="bf45c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="bf45c-107">Het doel van het maken van deze proefversie of pilot omgeving is om de uitgebreide en geïntegreerde functies voor Microsoft Threat Protection te illustreren.</span><span class="sxs-lookup"><span data-stu-id="bf45c-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="bf45c-108">Ervaar hoe deze intelligente beveiligingsoplossing detecteert, voorkomt automatisch onderzoek en reageert op geavanceerde bedreigingen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="bf45c-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="bf45c-109">In deze handleiding vindt u de stappen voor het starten van de evaluatieversie van Microsoft Threat Protection op basis van de aanbevolen implementatie paden.</span><span class="sxs-lookup"><span data-stu-id="bf45c-109">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="bf45c-110">Het doel is om u te helpen bij het instellen van de beveiligingsoplossing in een lab-omgeving met een proefaccount, of in een testomgeving in productie met een volledige licentie.</span><span class="sxs-lookup"><span data-stu-id="bf45c-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="bf45c-111">Het voorbereiden van uw proefversie of pilot omgeving kan u helpen bij het presenteren van beveiligingsactiviteiten voor besluitvormings Programma's in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="bf45c-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="bf45c-112">Wanneer u klaar bent met het uitvoeren van uw aanvals simulaties en tevreden bent over de resultaten, kunt u deze in uw organisatie volledig implementeren en operationalize met behulp van de Help van Microsoft Technical Sales professionals of experts in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="bf45c-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="bf45c-113">Deze handleiding helpt u bij:</span><span class="sxs-lookup"><span data-stu-id="bf45c-113">This guide will help you:</span></span>
- <span data-ttu-id="bf45c-114">Uw testserver en computers instellen</span><span class="sxs-lookup"><span data-stu-id="bf45c-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="bf45c-115">Active Directory configureren met gebruikers en groepen</span><span class="sxs-lookup"><span data-stu-id="bf45c-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="bf45c-116">Azure ATP, Office ATP, Microsoft Defender ATP en de beveiligingsinstellingen voor Microsoft Cloud apps instellen en configureren</span><span class="sxs-lookup"><span data-stu-id="bf45c-116">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="bf45c-117">Lokale beleidsregels instellen voor uw server en computers</span><span class="sxs-lookup"><span data-stu-id="bf45c-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="bf45c-118">Een bedreiging voor de bedreiging nabootsen voor het genereren van een test incident of waarschuwing in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="bf45c-118">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="bf45c-119">Voor optimale resultaten volgt u de installatie-instructies voor Lab zo sterk mogelijk.</span><span class="sxs-lookup"><span data-stu-id="bf45c-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="bf45c-120">Implementatiefasen</span><span class="sxs-lookup"><span data-stu-id="bf45c-120">Deployment phases</span></span>

<span data-ttu-id="bf45c-121">Er zijn drie fasen in het maken van een testomgeving voor Microsoft Threat Protection en de implementatie ervan:</span><span class="sxs-lookup"><span data-stu-id="bf45c-121">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="bf45c-122">Fase</span><span class="sxs-lookup"><span data-stu-id="bf45c-122">Phase</span></span> | <span data-ttu-id="bf45c-123">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="bf45c-123">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="bf45c-124">![Fase 1: voorbereiding](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="bf45c-124">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="bf45c-125">Fase 1: voorbereiding</span><span class="sxs-lookup"><span data-stu-id="bf45c-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="bf45c-126">Meer informatie over wat u moet doen wanneer u Microsoft Threat Protection implementeert in een proefversie van het lab of een testomgeving:</span><span class="sxs-lookup"><span data-stu-id="bf45c-126">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="bf45c-127">-Belanghebbenden en afmelden</span><span class="sxs-lookup"><span data-stu-id="bf45c-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="bf45c-128">-Aandachtspunten voor de omgeving</span><span class="sxs-lookup"><span data-stu-id="bf45c-128">- Environment considerations</span></span> <br><span data-ttu-id="bf45c-129">-Access</span><span class="sxs-lookup"><span data-stu-id="bf45c-129">- Access</span></span> <br><span data-ttu-id="bf45c-130">-Configuratie van Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bf45c-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="bf45c-131">-De configuratie volgorde</span><span class="sxs-lookup"><span data-stu-id="bf45c-131">- Configuration order</span></span>
|  <span data-ttu-id="bf45c-132">![Fase 2: instellen](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="bf45c-132">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="bf45c-133">Fase 2: instellen</span><span class="sxs-lookup"><span data-stu-id="bf45c-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="bf45c-134">Voer de volgende stappen uit om toegang te krijgen tot het Microsoft 365-Beveiligingscentrum voor het instellen van uw Microsoft Threat Protection-proefversie Lab of pilot omgeving.</span><span class="sxs-lookup"><span data-stu-id="bf45c-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="bf45c-135">U wordt begeleid bij:</span><span class="sxs-lookup"><span data-stu-id="bf45c-135">You'll be guided to:</span></span><br><br><span data-ttu-id="bf45c-136">-Registreren voor Microsoft 365 E5-proefabonnement</span><span class="sxs-lookup"><span data-stu-id="bf45c-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="bf45c-137">Domein configureren</span><span class="sxs-lookup"><span data-stu-id="bf45c-137">- Configure domain</span></span><br><span data-ttu-id="bf45c-138">-Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="bf45c-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="bf45c-139">-De wizard Setup voltooien in de portal</span><span class="sxs-lookup"><span data-stu-id="bf45c-139">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="bf45c-140">![Fase 3: & onboard configureren](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="bf45c-140">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="bf45c-141">Fase 3: & onboard configureren</span><span class="sxs-lookup"><span data-stu-id="bf45c-141">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="bf45c-142">Configureer elke Microsoft Threat Protection-pijler en de ingebouwde eindpunten.</span><span class="sxs-lookup"><span data-stu-id="bf45c-142">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="bf45c-143">U wordt begeleid bij:</span><span class="sxs-lookup"><span data-stu-id="bf45c-143">You'll be guided to:</span></span><br><br><span data-ttu-id="bf45c-144">-Office 365 Advanced Threat Protection configureren</span><span class="sxs-lookup"><span data-stu-id="bf45c-144">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="bf45c-145">-Beveiliging van Microsoft Cloud-app configureren</span><span class="sxs-lookup"><span data-stu-id="bf45c-145">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="bf45c-146">-Beveiliging van Azure Advanced Threat configureren</span><span class="sxs-lookup"><span data-stu-id="bf45c-146">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="bf45c-147">-Microsoft Defender Advanced Threat Protection configureren</span><span class="sxs-lookup"><span data-stu-id="bf45c-147">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="bf45c-148">In bereik</span><span class="sxs-lookup"><span data-stu-id="bf45c-148">In scope</span></span>

<span data-ttu-id="bf45c-149">De volgende taken bevinden zich in het bereik van deze handleiding:</span><span class="sxs-lookup"><span data-stu-id="bf45c-149">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="bf45c-150">Azure Active Directory instellen</span><span class="sxs-lookup"><span data-stu-id="bf45c-150">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="bf45c-151">Microsoft Threat Protection instellen</span><span class="sxs-lookup"><span data-stu-id="bf45c-151">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="bf45c-152">Registreren voor Microsoft 365 E5-proefabonnement of de volledige licentie gebruiken als u een pilot uitvoert</span><span class="sxs-lookup"><span data-stu-id="bf45c-152">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="bf45c-153">Domein configureren</span><span class="sxs-lookup"><span data-stu-id="bf45c-153">Configure domain</span></span>
    -   <span data-ttu-id="bf45c-154">Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="bf45c-154">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="bf45c-155">De installatiewizard in de portal voltooien</span><span class="sxs-lookup"><span data-stu-id="bf45c-155">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="bf45c-156">Alle Microsoft Threat Protection-pijlers configureren op basis van aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="bf45c-156">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="bf45c-157">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="bf45c-157">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="bf45c-158">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="bf45c-158">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="bf45c-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bf45c-159">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="bf45c-160">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="bf45c-160">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="bf45c-161">Buiten bereik</span><span class="sxs-lookup"><span data-stu-id="bf45c-161">Out of scope</span></span>

<span data-ttu-id="bf45c-162">Het volgende is niet het bereik van deze Implementatiehandleiding:</span><span class="sxs-lookup"><span data-stu-id="bf45c-162">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="bf45c-163">Configuratie van oplossingen van derden die kunnen worden geïntegreerd met Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="bf45c-163">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="bf45c-164">Penetratie tests in productieomgeving</span><span class="sxs-lookup"><span data-stu-id="bf45c-164">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="bf45c-165">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="bf45c-165">Next step</span></span>
<span data-ttu-id="bf45c-166">![Fase 1: voorbereiding](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="bf45c-166">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="bf45c-167">[Fase 1: voorbereiding](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="bf45c-167">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="bf45c-168">Uw proefabonnement voor Microsoft Threat Protection of een testomgeving voorbereiden</span><span class="sxs-lookup"><span data-stu-id="bf45c-168">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
