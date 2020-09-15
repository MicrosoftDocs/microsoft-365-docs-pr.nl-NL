---
title: Microsoft Threat Protection evalueren
description: Uw Microsoft Threat Protection-proefversie Lab of pilot omgeving instellen voor meer informatie over hoe de gecoördineerde oplossing voor beveiliging van apparaten, identiteit, gegevens en toepassingen uw organisatie kan helpen
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 62852dfe75794d5d0e33453f978967fff40813e1
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816935"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="226a3-104">Een Microsoft Threat Protection-proefversie Lab of pilot omgeving maken</span><span class="sxs-lookup"><span data-stu-id="226a3-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

<span data-ttu-id="226a3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="226a3-105">**Applies to:**</span></span>
- <span data-ttu-id="226a3-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="226a3-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="226a3-107">Het maken van deze proefversie Lab of pilot omgeving is het illustreren van de veelomvattende, geïntegreerde en intelligente mogelijkheden van Microsoft Threat Protection, zodat u deze kunt gebruiken in de detectie, preventie, onderzoek en reactie die u kunt gebruiken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="226a3-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="226a3-108">In deze handleiding vindt u de stappen voor het starten van de evaluatieversie van Microsoft Threat Protection op basis van de aanbevolen implementatie paden.</span><span class="sxs-lookup"><span data-stu-id="226a3-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="226a3-109">Het doel is om u te helpen bij het instellen van de geïntegreerde Microsoft Threat Protection-Services in een testomgeving wanneer u een proefaccount gebruikt, of in een testomgeving in productie wanneer u een volledige licentie gebruikt.</span><span class="sxs-lookup"><span data-stu-id="226a3-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment when using a trial account, or in a pilot environment in production when using a full license.</span></span> <span data-ttu-id="226a3-110">De resultaten van het gebruik van beveiligings bewerkings kwesties voor besluitvormings makers van beveiligingsoplossingen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="226a3-110">The results of which will be useful in presenting security operation use cases to security solution decision makers in your organization.</span></span> <span data-ttu-id="226a3-111">Wanneer u klaar bent met het uitvoeren van uw aanvals simulaties en u tevreden bent over de resultaten, kunt u deze in uw organisatie volledig implementeren en operationalize met behulp van de hulp van Microsoft technische verkoopmedewerkers of experts binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="226a3-111">When you’re done running your attack simulations, and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="226a3-112">Deze handleiding helpt u bij:</span><span class="sxs-lookup"><span data-stu-id="226a3-112">This guide will help you:</span></span>
- <span data-ttu-id="226a3-113">Uw testserver en computers instellen</span><span class="sxs-lookup"><span data-stu-id="226a3-113">Set up your lab server and computers</span></span>
- <span data-ttu-id="226a3-114">Active Directory configureren met gebruikers en groepen</span><span class="sxs-lookup"><span data-stu-id="226a3-114">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="226a3-115">Azure ATP, Office ATP, Microsoft Defender ATP en de beveiligingsinstellingen voor Microsoft Cloud apps instellen en configureren</span><span class="sxs-lookup"><span data-stu-id="226a3-115">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="226a3-116">Lokale beleidsregels instellen voor uw server en computers</span><span class="sxs-lookup"><span data-stu-id="226a3-116">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="226a3-117">Een bedreiging voor de bedreiging nabootsen voor het genereren van een test incident of waarschuwing in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="226a3-117">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="226a3-118">Voor optimale resultaten volgt u de installatie-instructies voor Lab zo sterk mogelijk.</span><span class="sxs-lookup"><span data-stu-id="226a3-118">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="226a3-119">Implementatiefasen</span><span class="sxs-lookup"><span data-stu-id="226a3-119">Deployment phases</span></span>

<span data-ttu-id="226a3-120">Er zijn drie fasen in het maken van een testomgeving voor Microsoft Threat Protection en de implementatie ervan:</span><span class="sxs-lookup"><span data-stu-id="226a3-120">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="226a3-121">Fase</span><span class="sxs-lookup"><span data-stu-id="226a3-121">Phase</span></span> | <span data-ttu-id="226a3-122">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="226a3-122">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="226a3-123">![Fase 1: voorbereiding](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="226a3-123">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="226a3-124">Fase 1: voorbereiding</span><span class="sxs-lookup"><span data-stu-id="226a3-124">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="226a3-125">Meer informatie over wat u moet doen wanneer u Microsoft Threat Protection implementeert in een proefversie van het lab of een testomgeving:</span><span class="sxs-lookup"><span data-stu-id="226a3-125">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="226a3-126">-Belanghebbenden en afmelden</span><span class="sxs-lookup"><span data-stu-id="226a3-126">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="226a3-127">-Aandachtspunten voor de omgeving</span><span class="sxs-lookup"><span data-stu-id="226a3-127">- Environment considerations</span></span> <br><span data-ttu-id="226a3-128">-Access</span><span class="sxs-lookup"><span data-stu-id="226a3-128">- Access</span></span> <br><span data-ttu-id="226a3-129">-Configuratie van Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="226a3-129">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="226a3-130">-De configuratie volgorde</span><span class="sxs-lookup"><span data-stu-id="226a3-130">- Configuration order</span></span>
|  <span data-ttu-id="226a3-131">![Fase 2: instellen](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="226a3-131">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="226a3-132">Fase 2: instellen</span><span class="sxs-lookup"><span data-stu-id="226a3-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="226a3-133">Voer de volgende stappen uit om toegang te krijgen tot het Microsoft 365-Beveiligingscentrum voor het instellen van uw Microsoft Threat Protection-proefversie Lab of pilot omgeving.</span><span class="sxs-lookup"><span data-stu-id="226a3-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="226a3-134">U wordt begeleid bij:</span><span class="sxs-lookup"><span data-stu-id="226a3-134">You'll be guided to:</span></span><br><br><span data-ttu-id="226a3-135">-Registreren voor Microsoft 365 E5-proefabonnement</span><span class="sxs-lookup"><span data-stu-id="226a3-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="226a3-136">Domein configureren</span><span class="sxs-lookup"><span data-stu-id="226a3-136">- Configure domain</span></span><br><span data-ttu-id="226a3-137">-Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="226a3-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="226a3-138">-De wizard Setup voltooien in de portal</span><span class="sxs-lookup"><span data-stu-id="226a3-138">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="226a3-139">![Fase 3: & onboard configureren](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="226a3-139">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="226a3-140">Fase 3: & onboard configureren</span><span class="sxs-lookup"><span data-stu-id="226a3-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="226a3-141">Configureer elke Microsoft Threat Protection-pijler en de ingebouwde eindpunten.</span><span class="sxs-lookup"><span data-stu-id="226a3-141">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="226a3-142">U wordt begeleid bij:</span><span class="sxs-lookup"><span data-stu-id="226a3-142">You'll be guided to:</span></span><br><br><span data-ttu-id="226a3-143">-Office 365 Advanced Threat Protection configureren</span><span class="sxs-lookup"><span data-stu-id="226a3-143">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="226a3-144">-Beveiliging van Microsoft Cloud-app configureren</span><span class="sxs-lookup"><span data-stu-id="226a3-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="226a3-145">-Beveiliging van Azure Advanced Threat configureren</span><span class="sxs-lookup"><span data-stu-id="226a3-145">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="226a3-146">-Microsoft Defender Advanced Threat Protection configureren</span><span class="sxs-lookup"><span data-stu-id="226a3-146">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="226a3-147">In bereik</span><span class="sxs-lookup"><span data-stu-id="226a3-147">In scope</span></span>

<span data-ttu-id="226a3-148">De volgende taken bevinden zich in het bereik van deze handleiding:</span><span class="sxs-lookup"><span data-stu-id="226a3-148">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="226a3-149">Azure Active Directory instellen</span><span class="sxs-lookup"><span data-stu-id="226a3-149">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="226a3-150">Microsoft Threat Protection instellen</span><span class="sxs-lookup"><span data-stu-id="226a3-150">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="226a3-151">Registreren voor Microsoft 365 E5-proefabonnement of de volledige licentie gebruiken als u een pilot uitvoert</span><span class="sxs-lookup"><span data-stu-id="226a3-151">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="226a3-152">Domein configureren</span><span class="sxs-lookup"><span data-stu-id="226a3-152">Configure domain</span></span>
    -   <span data-ttu-id="226a3-153">Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="226a3-153">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="226a3-154">De installatiewizard in de portal voltooien</span><span class="sxs-lookup"><span data-stu-id="226a3-154">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="226a3-155">Alle Microsoft Threat Protection-pijlers configureren op basis van aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="226a3-155">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="226a3-156">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="226a3-156">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="226a3-157">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="226a3-157">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="226a3-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="226a3-158">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="226a3-159">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="226a3-159">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="226a3-160">Buiten bereik</span><span class="sxs-lookup"><span data-stu-id="226a3-160">Out of scope</span></span>

<span data-ttu-id="226a3-161">Het volgende is niet het bereik van deze Implementatiehandleiding:</span><span class="sxs-lookup"><span data-stu-id="226a3-161">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="226a3-162">Configuratie van oplossingen van derden die kunnen worden geïntegreerd met Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="226a3-162">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="226a3-163">Penetratie tests in productieomgeving</span><span class="sxs-lookup"><span data-stu-id="226a3-163">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="226a3-164">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="226a3-164">Next step</span></span>
<span data-ttu-id="226a3-165">![Fase 1: voorbereiding](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="226a3-165">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="226a3-166">[Fase 1: voorbereiding](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="226a3-166">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="226a3-167">Uw proefabonnement voor Microsoft Threat Protection of een testomgeving voorbereiden</span><span class="sxs-lookup"><span data-stu-id="226a3-167">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
