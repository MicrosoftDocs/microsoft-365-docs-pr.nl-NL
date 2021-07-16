---
title: Schakel de evaluatieomgeving voor Microsoft Defender voor identiteit in, stel het MDI-exemplaar in, installeer en configureer MDI-sensor, laat MDI-sensor lokale beheerders detecteren
description: Stel Microsoft Defender voor identiteit in Microsoft 365 Defender proeflaboratorium of testomgeving in door & sensor te installeren en lokale beheerders op andere computers te ontdekken.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: f739c9897c9c43831cb4ed23cabaa1705c75d712
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457779"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a><span data-ttu-id="27477-103">De evaluatieomgeving voor Microsoft Defender voor identiteit inschakelen</span><span class="sxs-lookup"><span data-stu-id="27477-103">Enable the evaluation environment for Microsoft Defender for Identity</span></span>

<span data-ttu-id="27477-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="27477-104">**Applies to:**</span></span>
- <span data-ttu-id="27477-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27477-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="27477-106">Dit artikel is [stap 2 van 2](eval-defender-identity-overview.md) in het proces van het instellen van de evaluatieomgeving voor Microsoft Defender voor identiteit.</span><span class="sxs-lookup"><span data-stu-id="27477-106">This article is [Step 2 of 2](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="27477-107">Zie het [overzichtsartikel](eval-defender-identity-overview.md)voor meer informatie over dit proces.</span><span class="sxs-lookup"><span data-stu-id="27477-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="27477-108">Gebruik de volgende stappen om uw Microsoft Defender voor identiteitsomgeving in te stellen.</span><span class="sxs-lookup"><span data-stu-id="27477-108">Use the following steps to set up your Microsoft Defender for Identity environment.</span></span> 

![Stappen voor het inschakelen van Microsoft Defender voor identiteit in de evaluatieomgeving van Microsoft Defender](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [<span data-ttu-id="27477-110">Stap 1. Het exemplaar Defender voor identiteit instellen</span><span class="sxs-lookup"><span data-stu-id="27477-110">Step 1. Set up the Defender for Identity Instance</span></span>](#step-1-set-up-the-defender-for-identity-instance)
- [<span data-ttu-id="27477-111">Stap 2. De sensor installeren en configureren</span><span class="sxs-lookup"><span data-stu-id="27477-111">Step 2. Install and configure the sensor</span></span>](#step-2-install-and-configure-the-sensor)
- [<span data-ttu-id="27477-112">Stap 3. Instellingen voor gebeurtenislogboek en proxy configureren op machines met de sensor</span><span class="sxs-lookup"><span data-stu-id="27477-112">Step 3. Configure event log and proxy settings on machines with the sensor</span></span>](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [<span data-ttu-id="27477-113">Stap 4. Toestaan dat Defender voor identiteit lokale beheerders op andere computers identificeert</span><span class="sxs-lookup"><span data-stu-id="27477-113">Step 4. Allow Defender for Identity to identify local admins on other computers</span></span>](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a><span data-ttu-id="27477-114">Stap 1.</span><span class="sxs-lookup"><span data-stu-id="27477-114">Step 1.</span></span> <span data-ttu-id="27477-115">Het exemplaar Defender voor identiteit instellen</span><span class="sxs-lookup"><span data-stu-id="27477-115">Set up the Defender for Identity Instance</span></span>

<span data-ttu-id="27477-116">Meld u aan bij de Defender for Identity-portal om uw exemplaar te maken en verbind dit exemplaar vervolgens met uw Active Directory-omgeving.</span><span class="sxs-lookup"><span data-stu-id="27477-116">Sign in to the Defender for Identity portal to create your instance and then connect this instance to your Active Directory environment.</span></span> 

|  |<span data-ttu-id="27477-117">Stap</span><span class="sxs-lookup"><span data-stu-id="27477-117">Step</span></span>     |<span data-ttu-id="27477-118">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="27477-118">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="27477-119">1</span><span class="sxs-lookup"><span data-stu-id="27477-119">1</span></span>     | <span data-ttu-id="27477-120">Het exemplaar Defender voor identiteit maken</span><span class="sxs-lookup"><span data-stu-id="27477-120">Create the Defender for Identity instance</span></span>        | [<span data-ttu-id="27477-121">Snelstart: Uw Exemplaar van Microsoft Defender voor identiteit maken</span><span class="sxs-lookup"><span data-stu-id="27477-121">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](/defender-for-identity/install-step1)        |
|<span data-ttu-id="27477-122">2</span><span class="sxs-lookup"><span data-stu-id="27477-122">2</span></span>     | <span data-ttu-id="27477-123">Verbinding maken exemplaar Defender voor identiteit naar uw Active Directory-forest</span><span class="sxs-lookup"><span data-stu-id="27477-123">Connect the Defender for Identity instance to your Active Directory forest</span></span>   | [<span data-ttu-id="27477-124">Snelstart: Verbinding maken naar uw Active Directory-forest</span><span class="sxs-lookup"><span data-stu-id="27477-124">Quickstart: Connect to your Active Directory Forest</span></span>](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a><span data-ttu-id="27477-125">Stap 2.</span><span class="sxs-lookup"><span data-stu-id="27477-125">Step 2.</span></span> <span data-ttu-id="27477-126">De sensor installeren en configureren</span><span class="sxs-lookup"><span data-stu-id="27477-126">Install and configure the sensor</span></span>

<span data-ttu-id="27477-127">Download, installeer en configureer vervolgens de Defender for Identity-sensor op de domeincontrollers en AD FS-servers in uw on-premises omgeving.</span><span class="sxs-lookup"><span data-stu-id="27477-127">Next, download, install, and configure the Defender for Identity sensor on the domain controllers and AD FS servers in your on-premises environment.</span></span>

|  |<span data-ttu-id="27477-128">Stap</span><span class="sxs-lookup"><span data-stu-id="27477-128">Step</span></span>     |<span data-ttu-id="27477-129">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="27477-129">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="27477-130">1</span><span class="sxs-lookup"><span data-stu-id="27477-130">1</span></span>     | <span data-ttu-id="27477-131">Bepaal hoeveel Microsoft Defender voor identiteitssensoren u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="27477-131">Determine how many Microsoft Defender for Identity sensors you need.</span></span>        | [<span data-ttu-id="27477-132">Capaciteit plannen voor Microsoft Defender voor identiteit</span><span class="sxs-lookup"><span data-stu-id="27477-132">Plan capacity for Microsoft Defender for Identity</span></span>](/defender-for-identity/capacity-planning)   |
|<span data-ttu-id="27477-133">2</span><span class="sxs-lookup"><span data-stu-id="27477-133">2</span></span>     | <span data-ttu-id="27477-134">Het installatiepakket voor de sensor downloaden</span><span class="sxs-lookup"><span data-stu-id="27477-134">Download the sensor setup package</span></span>  |  [<span data-ttu-id="27477-135">Snelstart: Het installatiepakket voor de Microsoft Defender voor identiteits sensor downloaden</span><span class="sxs-lookup"><span data-stu-id="27477-135">Quickstart: Download the Microsoft Defender for Identity sensor setup package</span></span>](/defender-for-identity/install-step3)   |
|<span data-ttu-id="27477-136">3</span><span class="sxs-lookup"><span data-stu-id="27477-136">3</span></span>     | <span data-ttu-id="27477-137">De Defender for Identity-sensor installeren</span><span class="sxs-lookup"><span data-stu-id="27477-137">Install the Defender for Identity sensor</span></span>    |  [<span data-ttu-id="27477-138">Snelstart: De Microsoft Defender for Identity-sensor installeren</span><span class="sxs-lookup"><span data-stu-id="27477-138">Quickstart: Install the Microsoft Defender for Identity sensor</span></span>](/defender-for-identity/install-step4)       |
|<span data-ttu-id="27477-139">4</span><span class="sxs-lookup"><span data-stu-id="27477-139">4</span></span>     | <span data-ttu-id="27477-140">De sensor configureren</span><span class="sxs-lookup"><span data-stu-id="27477-140">Configure the sensor</span></span>       |  [<span data-ttu-id="27477-141">Instellingen voor De sensor van Microsoft Defender voor identiteit configureren </span><span class="sxs-lookup"><span data-stu-id="27477-141">Configure Microsoft Defender for Identity sensor settings </span></span>](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a><span data-ttu-id="27477-142">Stap 3.</span><span class="sxs-lookup"><span data-stu-id="27477-142">Step 3.</span></span> <span data-ttu-id="27477-143">Instellingen voor gebeurtenislogboek en proxy configureren op machines met de sensor</span><span class="sxs-lookup"><span data-stu-id="27477-143">Configure event log and proxy settings on machines with the sensor</span></span>

<span data-ttu-id="27477-144">Op de machines waar u de sensor op hebt geïnstalleerd, configureert u Windows instellingen voor gebeurtenislogboekverzameling en internetproxy om detectiemogelijkheden in te stellen en te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="27477-144">On the machines that you installed the sensor on, configure Windows event log collection and Internet proxy settings to enable and enhance detection capabilities.</span></span>

|  |<span data-ttu-id="27477-145">Stap</span><span class="sxs-lookup"><span data-stu-id="27477-145">Step</span></span>     |<span data-ttu-id="27477-146">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="27477-146">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="27477-147">1</span><span class="sxs-lookup"><span data-stu-id="27477-147">1</span></span>     | <span data-ttu-id="27477-148">De Windows gebeurtenislogboekverzameling configureren</span><span class="sxs-lookup"><span data-stu-id="27477-148">Configure Windows event log collection</span></span>         | [<span data-ttu-id="27477-149">De Windows gebeurtenisverzameling configureren</span><span class="sxs-lookup"><span data-stu-id="27477-149">Configure Windows Event collection</span></span>](/defender-for-identity/configure-windows-event-collection)        |
|<span data-ttu-id="27477-150">2</span><span class="sxs-lookup"><span data-stu-id="27477-150">2</span></span>     | <span data-ttu-id="27477-151">Instellingen voor internetproxy configureren</span><span class="sxs-lookup"><span data-stu-id="27477-151">Configure Internet proxy settings</span></span>        | [<span data-ttu-id="27477-152">Instellingen voor eindpuntproxy en internetverbinding configureren voor uw Microsoft Defender voor identiteits sensor</span><span class="sxs-lookup"><span data-stu-id="27477-152">Configure endpoint proxy and Internet connectivity settings for your Microsoft Defender for Identity Sensor</span></span>](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a><span data-ttu-id="27477-153">Stap 4.</span><span class="sxs-lookup"><span data-stu-id="27477-153">Step 4.</span></span> <span data-ttu-id="27477-154">Toestaan dat Defender voor identiteit lokale beheerders op andere computers identificeert</span><span class="sxs-lookup"><span data-stu-id="27477-154">Allow Defender for Identity to identify local admins on other computers</span></span>

<span data-ttu-id="27477-155">De detectie van het zijpad van Microsoft Defender for Identity is gebaseerd op query's die lokale beheerders op specifieke machines identificeren.</span><span class="sxs-lookup"><span data-stu-id="27477-155">Microsoft Defender for Identity lateral movement path detection relies on queries that identify local admins on specific machines.</span></span> <span data-ttu-id="27477-156">Deze query's worden uitgevoerd met het SAM-R-protocol, met behulp van het Defender for Identity Service-account.</span><span class="sxs-lookup"><span data-stu-id="27477-156">These queries are performed with the SAM-R protocol, using the Defender for Identity Service account.</span></span> 

<span data-ttu-id="27477-157">Om ervoor te zorgen dat Windows clients en servers toestaan dat uw Defender for Identity-account SAM-R kan uitvoeren, moet er een wijziging worden aangebracht in groepsbeleid om het serviceaccount defender voor identiteit toe te voegen naast de geconfigureerde accounts die worden vermeld in het netwerktoegangsbeleid.</span><span class="sxs-lookup"><span data-stu-id="27477-157">To ensure Windows clients and servers allow your Defender for Identity account to perform SAM-R, a modification to Group Policy must be made to add the Defender for Identity service account in addition to the configured accounts listed in the Network access policy.</span></span> <span data-ttu-id="27477-158">Zorg ervoor dat u groepsbeleid op alle computers, **behalve domeincontrollers, kunt toepassen.**</span><span class="sxs-lookup"><span data-stu-id="27477-158">Make sure to apply group policies to all computers **except domain controllers**.</span></span>

<span data-ttu-id="27477-159">Zie Microsoft Defender voor identiteit configureren voor externe oproepen naar SAM voor instructies over hoe u dit [doet.](/defender-for-identity/install-step8-samr)</span><span class="sxs-lookup"><span data-stu-id="27477-159">For instructions on how to do this, see [Configure Microsoft Defender for Identity to make remote calls to SAM](/defender-for-identity/install-step8-samr).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="27477-160">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="27477-160">Next steps</span></span>

<span data-ttu-id="27477-161">Stap 3 van 3: [Pilot Microsoft Defender voor identiteit](eval-defender-identity-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="27477-161">Step 3 of 3: [Pilot Microsoft Defender for Identity](eval-defender-identity-pilot.md)</span></span>

<span data-ttu-id="27477-162">Ga terug naar het overzicht voor [Microsoft Defender evalueren voor identiteit](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="27477-162">Return to the overview for [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)</span></span>

<span data-ttu-id="27477-163">Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="27477-163">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>