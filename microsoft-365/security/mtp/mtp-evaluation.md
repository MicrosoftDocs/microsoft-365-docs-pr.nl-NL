---
title: Microsoft Threat Protection evalueren
description: Uw Microsoft Threat Protection proef lab-omgeving instellen voor meer informatie over hoe de gecoördineerde oplossing voor beveiliging van apparaten, identiteiten, gegevens en toepassingen uw organisatie kan helpen
keywords: Microsoft Threat Protection-proefversie, Microsoft Threat Protection, Microsoft Threat Protection, Microsoft Threat Protection evaluatie lab, Cyber beveiliging, Geavanceerd permanent risico, beveiliging van ondernemingen, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, automatisch onderzoek en herstel, geavanceerde jacht
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
ms.openlocfilehash: a9d7b514aac8d1a769c0dabf6dcdb54f4bcb447b
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/14/2020
ms.locfileid: "47649959"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="61da1-104">Een testomgeving voor Microsoft Threat Protection maken</span><span class="sxs-lookup"><span data-stu-id="61da1-104">Create a Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="61da1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="61da1-105">**Applies to:**</span></span>
- <span data-ttu-id="61da1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="61da1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="61da1-107">Het doel van het maken van deze proefversie van de proefversie is het illustreren van de veelomvattende, geïntegreerde en intelligente mogelijkheden van Microsoft Threat Protection ter detectie, preventie, onderzoek en antwoorden die u kunt gebruiken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="61da1-107">The purpose of creating this trial lab environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="61da1-108">In deze handleiding vindt u de stappen voor het starten van de evaluatieversie van Microsoft Threat Protection op basis van de aanbevolen implementatie paden.</span><span class="sxs-lookup"><span data-stu-id="61da1-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="61da1-109">Het doel is om u te helpen bij het instellen van de geïntegreerde Microsoft Threat Protection-Services in een laboratorium omgeving of als concept van een HAALBAARHEIDstest</span><span class="sxs-lookup"><span data-stu-id="61da1-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment or as a proof of concept (POC) when presenting to security solution decision makers in your organization.</span></span> <span data-ttu-id="61da1-110">Wanneer u klaar bent met het uitvoeren van uw aanvals simulaties, een geautomatiseerd onderzoek en antwoord, en als u tevreden bent over de resultaten, kunt u deze implementeren in uw productieomgeving met behulp van de hulp van Microsoft technische verkoopmedewerkers of experts binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="61da1-110">When you’re done running your attack simulations, automated investigation and response, and are satisfied with the results, you can deploy it in your production environment with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="61da1-111">Deze handleiding helpt u bij:</span><span class="sxs-lookup"><span data-stu-id="61da1-111">This guide will help you:</span></span>
- <span data-ttu-id="61da1-112">Uw testserver en computers instellen</span><span class="sxs-lookup"><span data-stu-id="61da1-112">Set up your lab server and computers</span></span>
- <span data-ttu-id="61da1-113">Active Directory configureren met gebruikers en groepen</span><span class="sxs-lookup"><span data-stu-id="61da1-113">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="61da1-114">Azure ATP, Office ATP, Microsoft Defender ATP en de beveiligingsinstellingen voor Microsoft Cloud apps instellen en configureren</span><span class="sxs-lookup"><span data-stu-id="61da1-114">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="61da1-115">Lokaal beleid instellen voor uw server en computers</span><span class="sxs-lookup"><span data-stu-id="61da1-115">Setup local policies for your server and computers</span></span>
- <span data-ttu-id="61da1-116">Een bedreiging voor de bedreiging nabootsen voor het genereren van een test incident of waarschuwing in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="61da1-116">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="61da1-117">Voor optimale resultaten volgt u de installatie-instructies voor Lab zo sterk mogelijk.</span><span class="sxs-lookup"><span data-stu-id="61da1-117">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="61da1-118">Implementatiefasen</span><span class="sxs-lookup"><span data-stu-id="61da1-118">Deployment phases</span></span>

<span data-ttu-id="61da1-119">Er zijn drie fasen in het maken van een testomgeving voor Microsoft Threat Protection en de implementatie ervan:</span><span class="sxs-lookup"><span data-stu-id="61da1-119">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="61da1-120">Fase</span><span class="sxs-lookup"><span data-stu-id="61da1-120">Phase</span></span> | <span data-ttu-id="61da1-121">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="61da1-121">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="61da1-122">![Fase 1: voorbereiding](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="61da1-122">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="61da1-123">Fase 1: voorbereiding</span><span class="sxs-lookup"><span data-stu-id="61da1-123">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="61da1-124">Meer informatie over wat u moet doen als u Microsoft Threat Protection implementeert in een proefversie van het Lab:</span><span class="sxs-lookup"><span data-stu-id="61da1-124">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab environment:</span></span> <br><br><span data-ttu-id="61da1-125">-Belanghebbenden en afmelden</span><span class="sxs-lookup"><span data-stu-id="61da1-125">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="61da1-126">-Aandachtspunten voor de omgeving</span><span class="sxs-lookup"><span data-stu-id="61da1-126">- Environment considerations</span></span> <br><span data-ttu-id="61da1-127">-Access</span><span class="sxs-lookup"><span data-stu-id="61da1-127">- Access</span></span> <br><span data-ttu-id="61da1-128">-Configuratie van Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="61da1-128">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="61da1-129">-De configuratie volgorde</span><span class="sxs-lookup"><span data-stu-id="61da1-129">- Configuration order</span></span>
|  <span data-ttu-id="61da1-130">![Fase 2: instellen](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="61da1-130">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="61da1-131">Fase 2: instellen</span><span class="sxs-lookup"><span data-stu-id="61da1-131">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="61da1-132">Voer de stappen uit voor het instellen van uw Microsoft 365-Beveiligingscentrum voor het instellen van uw Microsoft Threat Protection-proef omgeving.</span><span class="sxs-lookup"><span data-stu-id="61da1-132">Take the initial steps to access Microsoft 365 Security Center to setup your Microsoft Threat Protection trial lab environment.</span></span> <span data-ttu-id="61da1-133">U wordt begeleid bij:</span><span class="sxs-lookup"><span data-stu-id="61da1-133">You will be guided to:</span></span><br><br><span data-ttu-id="61da1-134">-Registreren voor Microsoft 365 E5-proefabonnement</span><span class="sxs-lookup"><span data-stu-id="61da1-134">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="61da1-135">Domein configureren</span><span class="sxs-lookup"><span data-stu-id="61da1-135">- Configure domain</span></span><br><span data-ttu-id="61da1-136">-Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="61da1-136">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="61da1-137">-De wizard Setup voltooien in de portal</span><span class="sxs-lookup"><span data-stu-id="61da1-137">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="61da1-138">![Fase 3: & onboard configureren](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="61da1-138">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="61da1-139">Fase 3: & onboard configureren</span><span class="sxs-lookup"><span data-stu-id="61da1-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="61da1-140">Configureer elke Microsoft Threat Protection-pijler en de ingebouwde eindpunten.</span><span class="sxs-lookup"><span data-stu-id="61da1-140">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="61da1-141">U wordt begeleid bij:</span><span class="sxs-lookup"><span data-stu-id="61da1-141">You will be guided to:</span></span><br><br><span data-ttu-id="61da1-142">-Office 365 Advanced Threat Protection configureren</span><span class="sxs-lookup"><span data-stu-id="61da1-142">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="61da1-143">-Beveiliging van Microsoft Cloud-app configureren</span><span class="sxs-lookup"><span data-stu-id="61da1-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="61da1-144">-Beveiliging van Azure Advanced Threat configureren</span><span class="sxs-lookup"><span data-stu-id="61da1-144">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="61da1-145">-Microsoft Defender Advanced Threat Protection configureren</span><span class="sxs-lookup"><span data-stu-id="61da1-145">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="61da1-146">In bereik</span><span class="sxs-lookup"><span data-stu-id="61da1-146">In scope</span></span>

<span data-ttu-id="61da1-147">Het volgende is in het bereik voor de omgevings handleiding voor de proefversie van Lab:</span><span class="sxs-lookup"><span data-stu-id="61da1-147">The following is in scope for this trial lab environment guide:</span></span>
-   <span data-ttu-id="61da1-148">Azure Active Directory instellen</span><span class="sxs-lookup"><span data-stu-id="61da1-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="61da1-149">Microsoft Threat Protection instellen</span><span class="sxs-lookup"><span data-stu-id="61da1-149">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="61da1-150">Registreren voor Microsoft 365 E5-proefabonnement</span><span class="sxs-lookup"><span data-stu-id="61da1-150">Sign up for Microsoft 365 E5 Trial</span></span>
    -   <span data-ttu-id="61da1-151">Domein configureren</span><span class="sxs-lookup"><span data-stu-id="61da1-151">Configure domain</span></span>
    -   <span data-ttu-id="61da1-152">Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="61da1-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="61da1-153">De installatiewizard in de portal voltooien</span><span class="sxs-lookup"><span data-stu-id="61da1-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="61da1-154">Alle Microsoft Threat Protection-pijlers configureren op basis van aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="61da1-154">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="61da1-155">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="61da1-155">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="61da1-156">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="61da1-156">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="61da1-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="61da1-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="61da1-158">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="61da1-158">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="61da1-159">Buiten bereik</span><span class="sxs-lookup"><span data-stu-id="61da1-159">Out of scope</span></span>

<span data-ttu-id="61da1-160">Het volgende is niet het bereik van deze Implementatiehandleiding:</span><span class="sxs-lookup"><span data-stu-id="61da1-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="61da1-161">Configuratie van oplossingen van derden die kunnen worden geïntegreerd met Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="61da1-161">Configuration of third-party solutions that might integrate with Microsoft Defender ATP</span></span>
-   <span data-ttu-id="61da1-162">Penetratie tests in productieomgeving</span><span class="sxs-lookup"><span data-stu-id="61da1-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="61da1-163">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="61da1-163">Next step</span></span>
<span data-ttu-id="61da1-164">![Fase 1: voorbereiding](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="61da1-164">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="61da1-165">[Fase 1: voorbereiding](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="61da1-165">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="61da1-166">Uw Microsoft Threat Protection evaluatie lab-omgeving voorbereiden</span><span class="sxs-lookup"><span data-stu-id="61da1-166">Prepare your Microsoft Threat Protection evaluation lab environment</span></span>
