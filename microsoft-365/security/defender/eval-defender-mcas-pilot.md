---
title: Test Microsoft Cloud App Security met Microsoft 365 Defender, maak testgroepen, configureer voorwaardelijke toegangscontrole, probeer mogelijkheden uit, stel de configuratie in als onderdeel van Microsoft 365 Defender
description: Stel uw testlaboratorium Microsoft 365 Defender testomgeving in om de beveiligingsoplossing te testen en te ervaren die is ontworpen om apparaten, identiteit, gegevens en toepassingen te beveiligen.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e061bf213ee929f91a48b03c71b9654a7ea76b8c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457760"
---
# <a name="pilot-microsoft-cloud-app-security-with-microsoft-365-defender"></a><span data-ttu-id="9cd55-103">Pilot Microsoft Cloud App Security met Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cd55-103">Pilot Microsoft Cloud App Security with Microsoft 365 Defender</span></span>


<span data-ttu-id="9cd55-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9cd55-104">**Applies to:**</span></span>
- <span data-ttu-id="9cd55-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cd55-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="9cd55-106">Dit artikel is [stap 3 van 3](eval-defender-mcas-overview.md) in het proces van het instellen van de evaluatieomgeving voor Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="9cd55-106">This article is [Step 3 of 3](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="9cd55-107">Zie het [overzichtsartikel](eval-defender-mcas-overview.md)voor meer informatie over dit proces.</span><span class="sxs-lookup"><span data-stu-id="9cd55-107">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="9cd55-108">Gebruik de volgende stappen om de pilot in te stellen en te configureren voor Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="9cd55-108">Use the following steps to setup and configure the pilot for Microsoft Cloud App Security.</span></span>


![Stappen voor het Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-pilot-steps.png)

- <span data-ttu-id="9cd55-110">Stap 1.</span><span class="sxs-lookup"><span data-stu-id="9cd55-110">Step 1.</span></span> [<span data-ttu-id="9cd55-111">De testgroep maken: bereik uw pilotimplementatie naar bepaalde gebruikersgroepen</span><span class="sxs-lookup"><span data-stu-id="9cd55-111">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [<span data-ttu-id="9cd55-112">Stap 2. Beveiliging configureren: Voorwaardelijke toegang app-beheer</span><span class="sxs-lookup"><span data-stu-id="9cd55-112">Step 2. Configure protection — Conditional Access App Control</span></span>](#step-2-configure-protection--conditional-access-app-control)
- [<span data-ttu-id="9cd55-113">Stap 3. Mogelijkheden uitproberen: zelfstudies voor het beschermen van uw omgeving</span><span class="sxs-lookup"><span data-stu-id="9cd55-113">Step 3. Try out capabilities — Walk through tutorials for protecting your environment</span></span>](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a><span data-ttu-id="9cd55-114">Stap 1.</span><span class="sxs-lookup"><span data-stu-id="9cd55-114">Step 1.</span></span> <span data-ttu-id="9cd55-115">De testgroep maken: bereik uw pilotimplementatie naar bepaalde gebruikersgroepen</span><span class="sxs-lookup"><span data-stu-id="9cd55-115">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>

<span data-ttu-id="9cd55-116">Microsoft Cloud App Security stelt u in staat om uw implementatie te scopen.</span><span class="sxs-lookup"><span data-stu-id="9cd55-116">Microsoft Cloud App Security enables you to scope your deployment.</span></span> <span data-ttu-id="9cd55-117">Met Scoping kunt u bepaalde gebruikersgroepen selecteren die moeten worden gecontroleerd op apps of worden uitgesloten van monitoring.</span><span class="sxs-lookup"><span data-stu-id="9cd55-117">Scoping allows you to select certain user groups to be monitored for apps or excluded from monitoring.</span></span> <span data-ttu-id="9cd55-118">U kunt gebruikersgroepen opnemen of uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="9cd55-118">You can include or exclude user groups.</span></span> <span data-ttu-id="9cd55-119">Zie Scoped Deployment (Scoped Deployment) voor een bereik van de [pilotimplementatie.](/cloud-app-security/scoped-deployment)</span><span class="sxs-lookup"><span data-stu-id="9cd55-119">To scope your pilot deployment, see [Scoped Deployment](/cloud-app-security/scoped-deployment).</span></span>


## <a name="step-2-configure-protection--conditional-access-app-control"></a><span data-ttu-id="9cd55-120">Stap 2.</span><span class="sxs-lookup"><span data-stu-id="9cd55-120">Step 2.</span></span> <span data-ttu-id="9cd55-121">Beveiliging configureren: Voorwaardelijke toegang app-beheer</span><span class="sxs-lookup"><span data-stu-id="9cd55-121">Configure protection — Conditional Access App Control</span></span>

<span data-ttu-id="9cd55-122">Een van de krachtigste beveiligingen die u kunt configureren, is Voorwaardelijke toegangsbeheer voor apps.</span><span class="sxs-lookup"><span data-stu-id="9cd55-122">One of the most powerful protections you can configure is Conditional Access App Control.</span></span> <span data-ttu-id="9cd55-123">Hiervoor is integratie met Azure Active Directory (Azure AD) vereist.</span><span class="sxs-lookup"><span data-stu-id="9cd55-123">This requires integration with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="9cd55-124">Hiermee kunt u beleidsregels voor voorwaardelijke toegang toepassen, inclusief verwante beleidsregels (zoals het vereisen van gezonde apparaten) op cloud-apps die u hebt goedgekeurd.</span><span class="sxs-lookup"><span data-stu-id="9cd55-124">It allows you to apply Conditional Access policies, including related policies (like requiring healthy devices), to cloud apps you've sanctioned.</span></span> 

<span data-ttu-id="9cd55-125">De eerste stap in het gebruik Microsoft Cloud App Security saaS-apps te beheren, is deze te ontdekken en vervolgens toe te voegen aan uw Azure AD-tenant.</span><span class="sxs-lookup"><span data-stu-id="9cd55-125">The first step in using Microsoft Cloud App Security to manage SaaS apps is to discover these and then add them to your Azure AD tenant.</span></span> <span data-ttu-id="9cd55-126">Zie [SaaS-apps](/cloud-app-security/tutorial-shadow-it)in uw netwerk ontdekken en beheren als u hulp nodig hebt bij detectie.</span><span class="sxs-lookup"><span data-stu-id="9cd55-126">If you need help with discovery, see [Discover and manage SaaS apps in your network](/cloud-app-security/tutorial-shadow-it).</span></span> <span data-ttu-id="9cd55-127">Nadat u apps hebt gevonden, voegt [u deze toe aan uw Azure AD-tenant.](/azure/active-directory/manage-apps/add-application-portal)</span><span class="sxs-lookup"><span data-stu-id="9cd55-127">After you've discovered apps, [add these to your Azure AD tenant](/azure/active-directory/manage-apps/add-application-portal).</span></span>

<span data-ttu-id="9cd55-128">U kunt beginnen deze te beheren door het volgende te doen:</span><span class="sxs-lookup"><span data-stu-id="9cd55-128">You can begin to manage these by doing the following:</span></span>

- <span data-ttu-id="9cd55-129">Maak eerst in Azure AD een nieuw beleid voor voorwaardelijke toegang en configureer dit in 'Voorwaardelijke toegang app-beheer gebruiken'.</span><span class="sxs-lookup"><span data-stu-id="9cd55-129">First, in Azure AD, create a new conditional access policy and configure it to "Use Conditional Access App Control."</span></span> <span data-ttu-id="9cd55-130">Hiermee wordt de aanvraag omgeleid naar Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="9cd55-130">This redirects the request to Cloud App Security.</span></span> <span data-ttu-id="9cd55-131">U kunt één beleid maken en alle SaaS-apps aan dit beleid toevoegen.</span><span class="sxs-lookup"><span data-stu-id="9cd55-131">You can create one policy and add all SaaS apps to this policy.</span></span>
- <span data-ttu-id="9cd55-132">Maak vervolgens in Cloud App Security sessiebeleid.</span><span class="sxs-lookup"><span data-stu-id="9cd55-132">Next, in Cloud App Security, create session policies.</span></span> <span data-ttu-id="9cd55-133">Maak één beleid voor elk besturingselement dat u wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="9cd55-133">Create one policy for each control you want to apply.</span></span>

<span data-ttu-id="9cd55-134">Zie Apps beveiligen met Microsoft Cloud App Security [Voorwaardelijke toegangsbeheer](/cloud-app-security/proxy-intro-aad)voor meer informatie, inclusief ondersteunde apps en clients.</span><span class="sxs-lookup"><span data-stu-id="9cd55-134">For more information, including supported apps and clients, see [Protect apps with Microsoft Cloud App Security Conditional Access App Control](/cloud-app-security/proxy-intro-aad).</span></span> 

<span data-ttu-id="9cd55-135">Zie Bijvoorbeeld beleidsregels, zie [Aanbevolen Microsoft Cloud App Security voor SaaS-apps.](../office-365-security/mcas-saas-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9cd55-135">For example policies, see [Recommended Microsoft Cloud App Security policies for SaaS apps](../office-365-security/mcas-saas-access-policies.md).</span></span> <span data-ttu-id="9cd55-136">Dit beleid is gebaseerd op een reeks algemene beleidsregels voor [identiteits-](../office-365-security/microsoft-365-policies-configurations.md) en apparaattoegang die worden aanbevolen als uitgangspunt voor alle klanten.</span><span class="sxs-lookup"><span data-stu-id="9cd55-136">These policies build on a set of [common identity and device access policies](../office-365-security/microsoft-365-policies-configurations.md) that are recommended as a starting point for all customers.</span></span> 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a><span data-ttu-id="9cd55-137">Stap 3.</span><span class="sxs-lookup"><span data-stu-id="9cd55-137">Step 3.</span></span> <span data-ttu-id="9cd55-138">Mogelijkheden uitproberen: zelfstudies voor het beschermen van uw omgeving</span><span class="sxs-lookup"><span data-stu-id="9cd55-138">Try out capabilities — Walk through tutorials for protecting your environment</span></span> 

<span data-ttu-id="9cd55-139">De Microsoft Cloud App Security bevat een reeks zelfstudies om u te helpen risico's te ontdekken en uw omgeving te beschermen.</span><span class="sxs-lookup"><span data-stu-id="9cd55-139">The Microsoft Cloud App Security documentation includes a series of tutorials to help you discover risk and protect your environment.</span></span> 

<span data-ttu-id="9cd55-140">Probeer zelfstudies Cloud App Security:</span><span class="sxs-lookup"><span data-stu-id="9cd55-140">Try out Cloud App Security tutorials:</span></span>

- [<span data-ttu-id="9cd55-141">Verdachte gebruikersactiviteit detecteren</span><span class="sxs-lookup"><span data-stu-id="9cd55-141">Detect suspicious user activity</span></span>](/cloud-app-security/tutorial-suspicious-activity)
- [<span data-ttu-id="9cd55-142">Risicovolle gebruikers onderzoeken</span><span class="sxs-lookup"><span data-stu-id="9cd55-142">Investigate risky users</span></span>](/cloud-app-security/tutorial-ueba)
- [<span data-ttu-id="9cd55-143">Riskante OAuth-apps onderzoeken</span><span class="sxs-lookup"><span data-stu-id="9cd55-143">Investigate risky OAuth apps</span></span>](/cloud-app-security/investigate-risky-oauth)
- [<span data-ttu-id="9cd55-144">Gevoelige informatie ontdekken en beveiligen</span><span class="sxs-lookup"><span data-stu-id="9cd55-144">Discover and protect sensitive information</span></span>](/cloud-app-security/tutorial-dlp)
- [<span data-ttu-id="9cd55-145">Elke app in uw organisatie in realtime beveiligen</span><span class="sxs-lookup"><span data-stu-id="9cd55-145">Protect any app in your organization in real time</span></span>](/cloud-app-security/tutorial-proxy)
- [<span data-ttu-id="9cd55-146">Downloads van gevoelige informatie blokkeren</span><span class="sxs-lookup"><span data-stu-id="9cd55-146">Block downloads of sensitive information</span></span>](/cloud-app-security/use-case-proxy-block-session-aad)
- [<span data-ttu-id="9cd55-147">Uw bestanden beveiligen met beheerders quarantaine</span><span class="sxs-lookup"><span data-stu-id="9cd55-147">Protect your files with admin quarantine</span></span>](/cloud-app-security/use-case-admin-quarantine)
- [<span data-ttu-id="9cd55-148">Stapsgewijs verificatie vereisen bij riskante actie</span><span class="sxs-lookup"><span data-stu-id="9cd55-148">Require step-up authentication upon risky action</span></span>](/cloud-app-security/tutorial-step-up-authentication)

## <a name="next-steps"></a><span data-ttu-id="9cd55-149">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="9cd55-149">Next steps</span></span>

[<span data-ttu-id="9cd55-150">Onderzoeken en reageren met Microsoft 365 Defender in een testomgeving</span><span class="sxs-lookup"><span data-stu-id="9cd55-150">Investigate and respond using Microsoft 365 Defender in a pilot environment</span></span>](eval-defender-investigate-respond.md)

<span data-ttu-id="9cd55-151">Ga terug naar het overzicht voor [Evalueren Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9cd55-151">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="9cd55-152">Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9cd55-152">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>