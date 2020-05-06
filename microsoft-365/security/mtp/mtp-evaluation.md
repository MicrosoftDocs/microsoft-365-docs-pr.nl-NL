---
title: Microsoft-dreigingsbeveiliging evalueren
description: Stel uw proefversie van Microsoft Threat Protection in om uit te proberen hoe de gecoördineerde oplossing voor bedreigingsbescherming die is ontworpen om apparaten, identiteit, gegevens en toepassingen te beschermen, uw organisatie kan helpen
keywords: Proefversie van Microsoft Threat Protection, probeer Microsoft Threat Protection, evalueer Microsoft Threat Protection, Microsoft Threat Protection evaluation lab, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
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
ms.openlocfilehash: f6ee8147965a29b87d84690535116f096e4c6006
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049637"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="d4e1e-104">Een proefversie van Microsoft Threat Protection maken</span><span class="sxs-lookup"><span data-stu-id="d4e1e-104">Create a Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="d4e1e-105">**Geldt voor:**</span><span class="sxs-lookup"><span data-stu-id="d4e1e-105">**Applies to:**</span></span>
- <span data-ttu-id="d4e1e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d4e1e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d4e1e-107">Het doel van het maken van deze proeflabomgeving is het illustreren van de uitgebreide, geïntegreerde en intelligente mogelijkheden van Microsoft Threat Protection in detectie, preventie, onderzoek en respons die u in uw organisatie gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d4e1e-107">The purpose of creating this trial lab environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="d4e1e-108">Deze handleiding neemt u mee door de stappen om uw Microsoft Threat Protection-evaluatie te starten op basis van de aanbevolen implementatiepaden.</span><span class="sxs-lookup"><span data-stu-id="d4e1e-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="d4e1e-109">Het doel is om u te helpen bij het opzetten van de geïntegreerde Microsoft Threat Protection-services in een labomgeving of als proof of concept (POC) bij de presentatie aan besluitvormers van beveiligingsoplossingen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d4e1e-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment or as a proof of concept (POC) when presenting to security solution decision makers in your organization.</span></span> <span data-ttu-id="d4e1e-110">Wanneer u klaar bent met het uitvoeren van uw aanvalssimulaties, geautomatiseerd onderzoek en reactie, en tevreden bent met de resultaten, u deze implementeren in uw productieomgeving met de hulp van Microsoft Technical Sales Professionals of experts in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d4e1e-110">When you’re done running your attack simulations, automated investigation and response, and are satisfied with the results, you can deploy it in your production environment with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="d4e1e-111">Deze gids helpt u:</span><span class="sxs-lookup"><span data-stu-id="d4e1e-111">This guide will help you:</span></span>
- <span data-ttu-id="d4e1e-112">Uw labserver en computers instellen</span><span class="sxs-lookup"><span data-stu-id="d4e1e-112">Set up your lab server and computers</span></span>
- <span data-ttu-id="d4e1e-113">Active Directory configureren met gebruikers en groepen</span><span class="sxs-lookup"><span data-stu-id="d4e1e-113">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="d4e1e-114">Azure ATP, Office ATP, Microsoft Defender ATP en Microsoft Cloud App Security instellen en configureren</span><span class="sxs-lookup"><span data-stu-id="d4e1e-114">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="d4e1e-115">Lokaal beleid instellen voor uw server en computers</span><span class="sxs-lookup"><span data-stu-id="d4e1e-115">Setup local policies for your server and computers</span></span>
- <span data-ttu-id="d4e1e-116">Een bedreigingsaanval nabootsen om een testincident of waarschuwing te genereren in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d4e1e-116">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="d4e1e-117">Volg voor optimale resultaten de instructies voor het opzetten van het lab zo goed mogelijk.</span><span class="sxs-lookup"><span data-stu-id="d4e1e-117">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="d4e1e-118">Implementatiefasen</span><span class="sxs-lookup"><span data-stu-id="d4e1e-118">Deployment phases</span></span>

<span data-ttu-id="d4e1e-119">Er zijn drie fasen in het maken van een Microsoft Threat Protection trial lab omgeving en implementeren:</span><span class="sxs-lookup"><span data-stu-id="d4e1e-119">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="d4e1e-120">Fase</span><span class="sxs-lookup"><span data-stu-id="d4e1e-120">Phase</span></span> | <span data-ttu-id="d4e1e-121">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="d4e1e-121">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="d4e1e-122">![Fase 1: Voorbereiden](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="d4e1e-122">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="d4e1e-123">Fase 1: Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="d4e1e-123">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="d4e1e-124">Lees waar u rekening mee moet houden bij het implementeren van Microsoft Threat Protection in een proeflabomgeving:</span><span class="sxs-lookup"><span data-stu-id="d4e1e-124">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab environment:</span></span> <br><br><span data-ttu-id="d4e1e-125">- Belanghebbenden en afmelding</span><span class="sxs-lookup"><span data-stu-id="d4e1e-125">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="d4e1e-126">- Milieuoverwegingen</span><span class="sxs-lookup"><span data-stu-id="d4e1e-126">- Environment considerations</span></span> <br><span data-ttu-id="d4e1e-127">- Toegang</span><span class="sxs-lookup"><span data-stu-id="d4e1e-127">- Access</span></span> <br><span data-ttu-id="d4e1e-128">- Azure Active Directory-instelling</span><span class="sxs-lookup"><span data-stu-id="d4e1e-128">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="d4e1e-129">- Configuratievolgorde</span><span class="sxs-lookup"><span data-stu-id="d4e1e-129">- Configuration order</span></span>
|  <span data-ttu-id="d4e1e-130">![Fase 2: Setup](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="d4e1e-130">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="d4e1e-131">Fase 2: Setup</span><span class="sxs-lookup"><span data-stu-id="d4e1e-131">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="d4e1e-132">Neem de eerste stappen om toegang te krijgen tot Microsoft 365 Security Center om uw Microsoft Threat Protection trial lab-omgeving in te stellen.</span><span class="sxs-lookup"><span data-stu-id="d4e1e-132">Take the initial steps to access Microsoft 365 Security Center to setup your Microsoft Threat Protection trial lab environment.</span></span> <span data-ttu-id="d4e1e-133">U wordt begeleid naar:</span><span class="sxs-lookup"><span data-stu-id="d4e1e-133">You will be guided to:</span></span><br><br><span data-ttu-id="d4e1e-134">- Aanmelden voor Microsoft 365 E5-proefversie</span><span class="sxs-lookup"><span data-stu-id="d4e1e-134">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="d4e1e-135">- Domein configureren</span><span class="sxs-lookup"><span data-stu-id="d4e1e-135">- Configure domain</span></span><br><span data-ttu-id="d4e1e-136">- Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="d4e1e-136">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="d4e1e-137">- De wizard Setup voltooien in de portal</span><span class="sxs-lookup"><span data-stu-id="d4e1e-137">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="d4e1e-138">![Fase 3: & configureren](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="d4e1e-138">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="d4e1e-139">Fase 3: & configureren</span><span class="sxs-lookup"><span data-stu-id="d4e1e-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="d4e1e-140">Configureer elke Microsoft Threat Protection-pijler en eindpunten aan boord.</span><span class="sxs-lookup"><span data-stu-id="d4e1e-140">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="d4e1e-141">U wordt begeleid naar:</span><span class="sxs-lookup"><span data-stu-id="d4e1e-141">You will be guided to:</span></span><br><br><span data-ttu-id="d4e1e-142">- Geavanceerde bedreigingsbeveiliging van Office 365 configureren</span><span class="sxs-lookup"><span data-stu-id="d4e1e-142">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="d4e1e-143">- Microsoft Cloud App-beveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="d4e1e-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="d4e1e-144">- Azure Advanced Threat Protection configureren</span><span class="sxs-lookup"><span data-stu-id="d4e1e-144">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="d4e1e-145">- Microsoft Defender Advanced Threat Protection configureren</span><span class="sxs-lookup"><span data-stu-id="d4e1e-145">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="d4e1e-146">In werkingssfeer</span><span class="sxs-lookup"><span data-stu-id="d4e1e-146">In scope</span></span>

<span data-ttu-id="d4e1e-147">Het volgende is in het kader van deze proef lab omgeving gids:</span><span class="sxs-lookup"><span data-stu-id="d4e1e-147">The following is in scope for this trial lab environment guide:</span></span>
-   <span data-ttu-id="d4e1e-148">Azure Active Directory instellen</span><span class="sxs-lookup"><span data-stu-id="d4e1e-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="d4e1e-149">Microsoft-bedreigingsbeveiliging instellen</span><span class="sxs-lookup"><span data-stu-id="d4e1e-149">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="d4e1e-150">Aanmelden voor Microsoft 365 E5-proefversie</span><span class="sxs-lookup"><span data-stu-id="d4e1e-150">Sign up for Microsoft 365 E5 Trial</span></span>
    -   <span data-ttu-id="d4e1e-151">Domein configureren</span><span class="sxs-lookup"><span data-stu-id="d4e1e-151">Configure domain</span></span>
    -   <span data-ttu-id="d4e1e-152">Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="d4e1e-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="d4e1e-153">De wizard instellen in de portal voltooien</span><span class="sxs-lookup"><span data-stu-id="d4e1e-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="d4e1e-154">Alle pijlers voor Microsoft-bedreigingsbeveiliging configureren op basis van best practices</span><span class="sxs-lookup"><span data-stu-id="d4e1e-154">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="d4e1e-155">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d4e1e-155">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="d4e1e-156">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d4e1e-156">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="d4e1e-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d4e1e-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="d4e1e-158">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d4e1e-158">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="d4e1e-159">Buiten het toepassingsgebied</span><span class="sxs-lookup"><span data-stu-id="d4e1e-159">Out of scope</span></span>

<span data-ttu-id="d4e1e-160">Deze implementatiehandleiding valt buiten het bereik van deze implementatiehandleiding:</span><span class="sxs-lookup"><span data-stu-id="d4e1e-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="d4e1e-161">Configuratie van oplossingen van derden die kunnen worden geïntegreerd met Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="d4e1e-161">Configuration of third-party solutions that might integrate with Microsoft Defender ATP</span></span>
-   <span data-ttu-id="d4e1e-162">Penetratietesten in productieomgeving</span><span class="sxs-lookup"><span data-stu-id="d4e1e-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="d4e1e-163">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="d4e1e-163">Next step</span></span>
|||
|:-------|:-----|
|<span data-ttu-id="d4e1e-164">![Fase 1: Voorbereiden](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="d4e1e-164">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br>[<span data-ttu-id="d4e1e-165">Fase 1: Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="d4e1e-165">Phase 1: Prepare</span></span>](prepare-mtpeval.md) | <span data-ttu-id="d4e1e-166">Uw Microsoft Threat Protection-evaluatielabomgeving voorbereiden</span><span class="sxs-lookup"><span data-stu-id="d4e1e-166">Prepare your Microsoft Threat Protection evaluation lab environment</span></span>
