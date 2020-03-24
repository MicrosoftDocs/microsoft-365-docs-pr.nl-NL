---
title: 'Fase 1: Netwerkinfrastructuur voor Microsoft 365 Enterprise'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: De stappen om de netwerkinfrastructuur voor Microsoft 365 Enterprise te implementeren.
ms.openlocfilehash: 9a805ffbdbdc19ef5943a0c0ba0ff8f010d3e19b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806613"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="ab266-103">Fase 1: Netwerkinfrastructuur voor Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ab266-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![Fase 1: Netwerk](../media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="ab266-105">Microsoft 365 Enterprise omvat Office 365, Microsoft Intune en veel identiteits- en beveiligingsservices van Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="ab266-105">Microsoft 365 Enterprise includes Office 365, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="ab266-106">Al deze cloudservices zijn gebaseerd op de beveiliging, prestaties en betrouwbaarheid van verbindingen van clientapparaten via internet of speciale circuits.</span><span class="sxs-lookup"><span data-stu-id="ab266-106">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="ab266-107">Als u deze services wilt hosten en ze beschikbaar wilt maken voor klanten over de hele wereld, heeft Microsoft een netwerkinfrastructuur ontwikkeld die de prestaties en integratie versterkt.</span><span class="sxs-lookup"><span data-stu-id="ab266-107">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="ab266-108">In deze fase wordt u stapsgewijs begeleid bij het maken van een verbinding met de cloudservices van Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ab266-108">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="ab266-109">Zie voor een overzicht de [netwerkprincipes voor Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span><span class="sxs-lookup"><span data-stu-id="ab266-109">For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="ab266-110">Als u al een netwerkinfrastructuur hebt geïmplementeerd, bekijkt u het [afsluitcriterium](networking-exit-criteria.md) voor deze fase om er zeker van te zijn dat deze voldoet aan de vereiste en optionele voorwaarden voor Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ab266-110">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="ab266-111">Uw netwerkinfrastructuur voor Microsoft 365 Enterprise plannen en implementeren</span><span class="sxs-lookup"><span data-stu-id="ab266-111">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="ab266-112">Gebruik de volgende stappen om uw netwerkinfrastructuur te maken voor de vereisten en mogelijkheden van Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ab266-112">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![Stap 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="ab266-114">Uw netwerk voorbereiden voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ab266-114">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![Stap 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="ab266-116">Lokale internetverbindingen configureren voor elk kantoor</span><span class="sxs-lookup"><span data-stu-id="ab266-116">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![Stap 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="ab266-118">Netwerkhairpins vermijden</span><span class="sxs-lookup"><span data-stu-id="ab266-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![Stap 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="ab266-120">Omleiden van verkeer configureren</span><span class="sxs-lookup"><span data-stu-id="ab266-120">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![Stap 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="ab266-122">Prestaties van client en Office 365-service optimaliseren</span><span class="sxs-lookup"><span data-stu-id="ab266-122">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="ab266-123">Wanneer u deze stappen hebt voltooid, gaat u naar het [afsluitcriterium](networking-exit-criteria.md) voor deze fase om er zeker van te zijn dat u voldoet aan de vereiste en optionele voorwaarden voor Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ab266-123">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="ab266-124">Hoe Microsoft omgaat met Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ab266-124">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="ab266-125">Neem een kijkje achter de schermen en lees hoe het bedrijf [het Microsoft-netwerk voor cloudservices heeft geoptimaliseerd](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span><span class="sxs-lookup"><span data-stu-id="ab266-125">Peek inside Microsoft and learn how the company [optimized the Microsoft network for cloud services](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="ab266-126">Hoe Contoso Microsoft 365 Enterprise gebruikt</span><span class="sxs-lookup"><span data-stu-id="ab266-126">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="ab266-127">Bekijk hoe Contoso Corporation, een fictieve maar representatieve multinational, [hun netwerkapparaten en internetverbindingen hebben geoptimaliseerd](contoso-networking.md) voor Microsoft 365-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="ab266-127">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="ab266-129">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="ab266-129">Next step</span></span>

|||
|:-------|:-----|
|![Stap 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="ab266-131">Uw netwerk voorbereiden voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ab266-131">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|

