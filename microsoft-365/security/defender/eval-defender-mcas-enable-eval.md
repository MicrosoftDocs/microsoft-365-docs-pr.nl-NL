---
title: De evaluatieomgeving inschakelen voor Microsoft Cloud App Security
description: Leer de architectuur van MCAS in Microsoft Defender voor Office 365 en begrijp de interacties tussen de Microsoft 365 Defender producten.
keywords: Microsoft 365 Defender proefversie, probeer Microsoft 365 Defender, evalueer Microsoft 365 Defender, Microsoft 365 Defender evaluatielaboratorium, Microsoft 365 Defender-pilot, cyberbeveiliging, geavanceerde permanente bedreiging, bedrijfsbeveiliging, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerd zoeken
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6ada9613f852e085158b7002cbbb9a9928d36d58
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457761"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a><span data-ttu-id="49469-104">De evaluatieomgeving inschakelen voor Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="49469-104">Enable the evaluation environment for Microsoft Cloud App Security</span></span>


<span data-ttu-id="49469-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="49469-105">**Applies to:**</span></span>

- <span data-ttu-id="49469-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49469-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="49469-107">Dit artikel is [stap 2 van 2](eval-defender-mcas-overview.md) in het proces van het instellen van de evaluatieomgeving voor Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="49469-107">This article is [Step 2 of 2](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="49469-108">Zie het [overzichtsartikel](eval-defender-mcas-overview.md)voor meer informatie over dit proces.</span><span class="sxs-lookup"><span data-stu-id="49469-108">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="49469-109">In dit artikel wordt u beschreven hoe u toegang hebt tot de portal Cloud App Security en de benodigde integratie configureert voor het verzamelen van gegevens over het verkeer in cloud-apps.</span><span class="sxs-lookup"><span data-stu-id="49469-109">This article walks you through the process of accessing the Cloud App Security portal and configuring the necessary integration to collect cloud app traffic data.</span></span>

<span data-ttu-id="49469-110">Als u cloud-apps wilt ontdekken die in uw omgeving worden gebruikt, kunt u een of beide van de volgende dingen doen:</span><span class="sxs-lookup"><span data-stu-id="49469-110">To discover cloud apps used in your environment, you can do one or both of the following:</span></span>

- <span data-ttu-id="49469-111">Ga snel aan de weg met Cloud Discovery door te integreren met Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="49469-111">Get up and running quickly with Cloud Discovery by integrating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="49469-112">Met deze native integratie kunt u direct beginnen met het verzamelen van gegevens over cloudverkeer op uw Windows 10 apparaten, in en uit uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="49469-112">This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.</span></span>
- <span data-ttu-id="49469-113">Als u alle cloud-apps wilt ontdekken die toegankelijk zijn voor alle apparaten die zijn verbonden met uw netwerk, implementeert u de Cloud App Security logboekverzamelaar op uw firewalls en andere proxies.</span><span class="sxs-lookup"><span data-stu-id="49469-113">To discover all cloud apps accessed by all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies.</span></span> <span data-ttu-id="49469-114">Hiermee worden gegevens van uw eindpunten verzameld en naar Cloud App Security voor analyse.</span><span class="sxs-lookup"><span data-stu-id="49469-114">This collects data from your endpoints and sends it to Cloud App Security for analysis.</span></span> <span data-ttu-id="49469-115">Cloud App Security inheems geïntegreerd met sommige proxies van derden voor nog meer mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="49469-115">Cloud App Security natively integrates with some third-party proxies for even more capabilities.</span></span>

<span data-ttu-id="49469-116">Dit artikel bevat richtlijnen voor beide methoden.</span><span class="sxs-lookup"><span data-stu-id="49469-116">This article includes guidance for both methods.</span></span>

<span data-ttu-id="49469-117">Gebruik de volgende stappen om een Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="49469-117">Use the following steps to set up Microsoft Cloud App Security.</span></span>

![Stappen om Microsoft-Microsoft Cloud App Security in te stellen in de evaluatieomgeving van Microsoft Defender](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [<span data-ttu-id="49469-119">Stap 1. Verbinding maken naar de Cloud App Security portal</span><span class="sxs-lookup"><span data-stu-id="49469-119">Step 1. Connect to the Cloud App Security portal</span></span>](#step-1-connect-to-the-cloud-app-security-portal)
- [<span data-ttu-id="49469-120">Stap 2. Integreren met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="49469-120">Step 2. Integrate with Microsoft Defender for Endpoint</span></span>](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [<span data-ttu-id="49469-121">Stap 3. De logboekverzamelaar Cloud App Security uw firewalls en andere proxies implementeren</span><span class="sxs-lookup"><span data-stu-id="49469-121">Step 3. Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [<span data-ttu-id="49469-122">Stap 4. Bekijk het Cloud Discovery-dashboard om te zien welke apps worden gebruikt in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="49469-122">Step 4. View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a><span data-ttu-id="49469-123">Stap 1.</span><span class="sxs-lookup"><span data-stu-id="49469-123">Step 1.</span></span> <span data-ttu-id="49469-124">Verbinding maken naar de Cloud App Security portal</span><span class="sxs-lookup"><span data-stu-id="49469-124">Connect to the Cloud App Security portal</span></span>

<span data-ttu-id="49469-125">Zie Cloud App Security Snel [starten: Aan de](/cloud-app-security/getting-started-with-cloud-app-security)slag met Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="49469-125">To verify licensing and to connect to the Cloud App Security portal, see [Quickstart: Get started with Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security).</span></span> 

<span data-ttu-id="49469-126">Als u niet direct verbinding kunt maken met de portal, moet u mogelijk het IP-adres toevoegen aan de lijst met toegestane firewalls.</span><span class="sxs-lookup"><span data-stu-id="49469-126">If you're not immediately able to connect to the portal, you might need to add the IP address to the allow list of your firewall.</span></span> <span data-ttu-id="49469-127">Zie [Basisinstelling voor Cloud App Security.](/cloud-app-security/general-setup)</span><span class="sxs-lookup"><span data-stu-id="49469-127">See [Basic setup for Cloud App Security](/cloud-app-security/general-setup).</span></span>

<span data-ttu-id="49469-128">Als u nog steeds problemen hebt, controleert u [netwerkvereisten.](/cloud-app-security/network-requirements)</span><span class="sxs-lookup"><span data-stu-id="49469-128">If you're still having trouble, review [Network requirements](/cloud-app-security/network-requirements).</span></span>

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="49469-129">Stap 2.</span><span class="sxs-lookup"><span data-stu-id="49469-129">Step 2.</span></span> <span data-ttu-id="49469-130">Integreren met Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="49469-130">Integrate with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="49469-131">Microsoft Cloud App Security is inheems geïntegreerd met Microsoft Defender voor Endpoint.</span><span class="sxs-lookup"><span data-stu-id="49469-131">Microsoft Cloud App Security integrates with Microsoft Defender for Endpoint natively.</span></span> <span data-ttu-id="49469-132">De integratie vereenvoudigt de implementatie van Cloud Discovery, breidt Cloud Discovery-mogelijkheden uit buiten uw bedrijfsnetwerk en maakt onderzoek op apparaatbasis mogelijk.</span><span class="sxs-lookup"><span data-stu-id="49469-132">The integration simplifies roll out of Cloud Discovery, extends Cloud Discovery capabilities beyond your corporate network, and enables device-based investigation.</span></span> <span data-ttu-id="49469-133">Deze integratie laat zien dat cloud-apps en -services worden gebruikt vanaf it-beheerde Windows 10 apparaten.</span><span class="sxs-lookup"><span data-stu-id="49469-133">This integration reveals cloud apps and services being accessed from IT-managed Windows 10 devices.</span></span> 

<span data-ttu-id="49469-134">Als u Microsoft Defender voor Eindpunt al hebt ingesteld, is het configureren van integratie met Cloud App Security een schakelknop in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="49469-134">If you've already set up Microsoft Defender for Endpoint, configuring integration with Cloud App Security is a toggle in Microsoft 365 Defender.</span></span> <span data-ttu-id="49469-135">Nadat integratie is ingeschakeld, kunt u terugkeren naar de Cloud App Security portal en uitgebreide gegevens weergeven in het Cloud Discovery Dashboard.</span><span class="sxs-lookup"><span data-stu-id="49469-135">After integration is turned on, you can return to the Cloud App Security portal and view rich data in the Cloud Discovery Dashboard.</span></span>

<span data-ttu-id="49469-136">Zie Microsoft Defender voor [endpoint-integratie](/cloud-app-security/mde-integration)met Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="49469-136">To accomplish these tasks, see [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration).</span></span> 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a><span data-ttu-id="49469-137">Stap 3.</span><span class="sxs-lookup"><span data-stu-id="49469-137">Step 3.</span></span> <span data-ttu-id="49469-138">De logboekverzamelaar Cloud App Security uw firewalls en andere proxies implementeren</span><span class="sxs-lookup"><span data-stu-id="49469-138">Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>

<span data-ttu-id="49469-139">Voor dekking op alle apparaten die met uw netwerk zijn verbonden, implementeert u de Cloud App Security-logboekverzamelaar op uw firewalls en andere proxies om gegevens van uw eindpunten te verzamelen en deze te verzenden naar Cloud App Security voor analyse.</span><span class="sxs-lookup"><span data-stu-id="49469-139">For coverage on all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies to collect data from your endpoints and send it to Cloud App Security for analysis.</span></span> 

<span data-ttu-id="49469-140">Als u een van de volgende Secure Web Gateways (SWG) gebruikt, biedt Cloud App Security naadloze implementatie en integratie:</span><span class="sxs-lookup"><span data-stu-id="49469-140">If you're using one of the following Secure Web Gateways (SWG), Cloud App Security provides seamless deployment and integration:</span></span>
- <span data-ttu-id="49469-141">Zscaler</span><span class="sxs-lookup"><span data-stu-id="49469-141">Zscaler</span></span>
- <span data-ttu-id="49469-142">iboss</span><span class="sxs-lookup"><span data-stu-id="49469-142">iboss</span></span>
- <span data-ttu-id="49469-143">Corrata</span><span class="sxs-lookup"><span data-stu-id="49469-143">Corrata</span></span>
- <span data-ttu-id="49469-144">Beveiliging van Menlo</span><span class="sxs-lookup"><span data-stu-id="49469-144">Menlo Security</span></span>

<span data-ttu-id="49469-145">Zie Clouddetectie instellen voor meer informatie over het integreren met deze [netwerkapparaten.](/cloud-app-security/set-up-cloud-discovery)</span><span class="sxs-lookup"><span data-stu-id="49469-145">For more information on integrating with these network devices, see [Set up Cloud Discovery](/cloud-app-security/set-up-cloud-discovery).</span></span> 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a><span data-ttu-id="49469-146">Stap 4.</span><span class="sxs-lookup"><span data-stu-id="49469-146">Step 4.</span></span> <span data-ttu-id="49469-147">Bekijk het Cloud Discovery-dashboard om te zien welke apps worden gebruikt in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="49469-147">View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>

<span data-ttu-id="49469-148">Het Cloud Discovery-dashboard is ontworpen om u meer inzicht te geven in de manier waarop cloud-apps in uw organisatie worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="49469-148">The Cloud Discovery dashboard is designed to give you more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="49469-149">Het biedt in één oogopslag een overzicht van welke soorten apps worden gebruikt, uw geopende waarschuwingen en de risiconiveaus van apps in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="49469-149">It provides an at-a-glance overview of what kinds of apps are being used, your open alerts, and the risk levels of apps in your organization.</span></span> 

<span data-ttu-id="49469-150">Zie Werken met ontdekte apps om aan de slag te gaan met het Cloud [Discovery-dashboard.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="49469-150">To get started using the Cloud Discovery dashboard, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="next-steps"></a><span data-ttu-id="49469-151">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="49469-151">Next steps</span></span>

<span data-ttu-id="49469-152">Stap 3 van 3: [Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="49469-152">Step 3 of 3: [Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span></span>

<span data-ttu-id="49469-153">Ga terug naar het overzicht voor [Evalueren Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="49469-153">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="49469-154">Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="49469-154">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>