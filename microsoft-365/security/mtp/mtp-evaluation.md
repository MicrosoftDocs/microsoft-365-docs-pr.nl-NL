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
ms.openlocfilehash: fe0a06dd104f0f0532363ee046f4bad1c03c5400
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130877"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="598ab-104">Een Microsoft 365 Defender-proef Lab of pilot omgeving maken</span><span class="sxs-lookup"><span data-stu-id="598ab-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="598ab-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="598ab-105">**Applies to:**</span></span>
- <span data-ttu-id="598ab-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="598ab-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="598ab-107">Het doel van het maken van deze proefversie of pilot omgeving is het illustreren van de allesomvattende en geïntegreerde Microsoft 365 Defender-mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="598ab-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="598ab-108">Ervaar hoe deze intelligente beveiligingsoplossing detecteert, voorkomt automatisch onderzoek en reageert op geavanceerde bedreigingen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="598ab-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="598ab-109">In deze handleiding vindt u de stappen voor het starten van uw Microsoft 365-evaluatieversie op basis van de aanbevolen distributie paden.</span><span class="sxs-lookup"><span data-stu-id="598ab-109">This guide takes you through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="598ab-110">Het doel is om u te helpen bij het instellen van de beveiligingsoplossing in een lab-omgeving met een proefaccount, of in een testomgeving in productie met een volledige licentie.</span><span class="sxs-lookup"><span data-stu-id="598ab-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="598ab-111">Het voorbereiden van uw proefversie of pilot omgeving kan u helpen bij het presenteren van beveiligingsactiviteiten voor besluitvormings Programma's in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="598ab-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="598ab-112">Wanneer u klaar bent met het uitvoeren van uw aanvals simulaties en tevreden bent over de resultaten, kunt u deze in uw organisatie volledig implementeren en operationalize met behulp van de Help van Microsoft Technical Sales professionals of experts in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="598ab-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="598ab-113">Deze handleiding helpt u bij:</span><span class="sxs-lookup"><span data-stu-id="598ab-113">This guide will help you:</span></span>
- <span data-ttu-id="598ab-114">Uw testserver en computers instellen</span><span class="sxs-lookup"><span data-stu-id="598ab-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="598ab-115">Active Directory configureren met gebruikers en groepen</span><span class="sxs-lookup"><span data-stu-id="598ab-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="598ab-116">Microsoft Defender voor identiteit instellen en configureren, Microsoft Defender voor Office 365, Microsoft Defender voor eindpunt en beveiliging van de Cloud-app</span><span class="sxs-lookup"><span data-stu-id="598ab-116">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="598ab-117">Lokale beleidsregels instellen voor uw server en computers</span><span class="sxs-lookup"><span data-stu-id="598ab-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="598ab-118">Een aanval in de bedreiging nabootsen voor het genereren van een test incident of waarschuwing in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="598ab-118">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="598ab-119">Voor optimale resultaten volgt u de installatie-instructies voor Lab zo sterk mogelijk.</span><span class="sxs-lookup"><span data-stu-id="598ab-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="598ab-120">Implementatiefasen</span><span class="sxs-lookup"><span data-stu-id="598ab-120">Deployment phases</span></span>

<span data-ttu-id="598ab-121">Er zijn drie fasen in het maken van een proefversie van Microsoft voor Microsoft 365 Defender met proef omgevingen en de implementatie ervan:</span><span class="sxs-lookup"><span data-stu-id="598ab-121">There are three phases in creating a Microsoft 365 Defender trial lab environment and deploying it:</span></span>

![Implementatiefasen: voorbereiden, instellen, onboardd](../../media/phase-diagrams/deployment-phases.png)

|<span data-ttu-id="598ab-123">Fase</span><span class="sxs-lookup"><span data-stu-id="598ab-123">Phase</span></span> | <span data-ttu-id="598ab-124">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="598ab-124">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="598ab-125">Fase 1: voorbereiding</span><span class="sxs-lookup"><span data-stu-id="598ab-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="598ab-126">Meer informatie over wat u moet doen wanneer u Microsoft 365 Defender implementeert in een proefversie van het lab of een testomgeving:</span><span class="sxs-lookup"><span data-stu-id="598ab-126">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="598ab-127">-Belanghebbenden en afmelden</span><span class="sxs-lookup"><span data-stu-id="598ab-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="598ab-128">-Aandachtspunten voor de omgeving</span><span class="sxs-lookup"><span data-stu-id="598ab-128">- Environment considerations</span></span> <br><span data-ttu-id="598ab-129">-Access</span><span class="sxs-lookup"><span data-stu-id="598ab-129">- Access</span></span> <br><span data-ttu-id="598ab-130">-Configuratie van Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="598ab-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="598ab-131">-De configuratie volgorde</span><span class="sxs-lookup"><span data-stu-id="598ab-131">- Configuration order</span></span>
|[<span data-ttu-id="598ab-132">Fase 2: instellen</span><span class="sxs-lookup"><span data-stu-id="598ab-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="598ab-133">Voer de volgende stappen uit om toegang te krijgen tot het Microsoft 365-Beveiligingscentrum voor het instellen van uw proefversie van Microsoft 365 Defender of prototype.</span><span class="sxs-lookup"><span data-stu-id="598ab-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="598ab-134">U wordt begeleid bij:</span><span class="sxs-lookup"><span data-stu-id="598ab-134">You'll be guided to:</span></span><br><br><span data-ttu-id="598ab-135">-Registreren voor Microsoft 365 E5-proefabonnement</span><span class="sxs-lookup"><span data-stu-id="598ab-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="598ab-136">Domein configureren</span><span class="sxs-lookup"><span data-stu-id="598ab-136">- Configure domain</span></span><br><span data-ttu-id="598ab-137">-Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="598ab-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="598ab-138">-De wizard Setup voltooien in de portal</span><span class="sxs-lookup"><span data-stu-id="598ab-138">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="598ab-139">Fase 3: & onboard configureren</span><span class="sxs-lookup"><span data-stu-id="598ab-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="598ab-140">Configureer elke Microsoft 365 Defender-pijler pijler en de ingebouwde eindpunten.</span><span class="sxs-lookup"><span data-stu-id="598ab-140">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="598ab-141">U wordt begeleid bij:</span><span class="sxs-lookup"><span data-stu-id="598ab-141">You'll be guided to:</span></span><br><br><span data-ttu-id="598ab-142">-Microsoft Defender voor Office 365 configureren</span><span class="sxs-lookup"><span data-stu-id="598ab-142">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="598ab-143">-Beveiliging van Microsoft Cloud-app configureren</span><span class="sxs-lookup"><span data-stu-id="598ab-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="598ab-144">-Microsoft Defender configureren voor identiteit</span><span class="sxs-lookup"><span data-stu-id="598ab-144">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="598ab-145">-Microsoft Defender voor eindpunt configureren</span><span class="sxs-lookup"><span data-stu-id="598ab-145">- Configure Microsoft Defender for Endpoint</span></span>


## <a name="in-scope"></a><span data-ttu-id="598ab-146">In bereik</span><span class="sxs-lookup"><span data-stu-id="598ab-146">In scope</span></span>

<span data-ttu-id="598ab-147">De volgende taken bevinden zich in het bereik van deze handleiding:</span><span class="sxs-lookup"><span data-stu-id="598ab-147">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="598ab-148">Azure Active Directory instellen</span><span class="sxs-lookup"><span data-stu-id="598ab-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="598ab-149">Microsoft 365 Defender instellen</span><span class="sxs-lookup"><span data-stu-id="598ab-149">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="598ab-150">Registreren voor Microsoft 365 E5-proefabonnement of de volledige licentie gebruiken als u een pilot uitvoert</span><span class="sxs-lookup"><span data-stu-id="598ab-150">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="598ab-151">Domein configureren</span><span class="sxs-lookup"><span data-stu-id="598ab-151">Configure domain</span></span>
    -   <span data-ttu-id="598ab-152">Microsoft 365 E5-licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="598ab-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="598ab-153">De installatiewizard in de portal voltooien</span><span class="sxs-lookup"><span data-stu-id="598ab-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="598ab-154">Alle Microsoft 365 Defender-pijlers configureren op basis van aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="598ab-154">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="598ab-155">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="598ab-155">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="598ab-156">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="598ab-156">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="598ab-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="598ab-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="598ab-158">Microsoft Defender voor Eindpunt </span><span class="sxs-lookup"><span data-stu-id="598ab-158">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="598ab-159">Buiten bereik</span><span class="sxs-lookup"><span data-stu-id="598ab-159">Out of scope</span></span>

<span data-ttu-id="598ab-160">Het volgende is niet het bereik van deze Implementatiehandleiding:</span><span class="sxs-lookup"><span data-stu-id="598ab-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="598ab-161">Configuratie van oplossingen van derden die kunnen worden geïntegreerd met Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="598ab-161">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="598ab-162">Penetratie tests in productieomgeving</span><span class="sxs-lookup"><span data-stu-id="598ab-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="598ab-163">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="598ab-163">Next step</span></span>
<span data-ttu-id="598ab-164">[Fase 1: voorbereiding](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="598ab-164">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="598ab-165">Uw proefabonnement voor Microsoft 365 Defender of pilot omgeving voorbereiden</span><span class="sxs-lookup"><span data-stu-id="598ab-165">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
