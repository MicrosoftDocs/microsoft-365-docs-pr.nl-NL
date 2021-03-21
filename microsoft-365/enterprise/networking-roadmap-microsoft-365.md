---
title: Netwerk roadmap voor Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: De roadmap voor het implementeren van Microsoft 365-netwerken.
ms.openlocfilehash: be1691138290a592822bfb4d59286fe795270450
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923550"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="536dd-103">Netwerk roadmap voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="536dd-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="536dd-104">Microsoft 365 voor bedrijven omvat samenwerkings- en productiviteitscloudservices, Microsoft Intune en veel identiteits- en beveiligingsservices van Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="536dd-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="536dd-105">Al deze cloudservices zijn gebaseerd op de beveiliging, prestaties en betrouwbaarheid van verbindingen van clientapparaten via internet of speciale circuits.</span><span class="sxs-lookup"><span data-stu-id="536dd-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="536dd-106">Als u deze services wilt hosten en ze beschikbaar wilt maken voor klanten over de hele wereld, heeft Microsoft een netwerkinfrastructuur ontwikkeld die de prestaties en integratie versterkt.</span><span class="sxs-lookup"><span data-stu-id="536dd-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="536dd-107">Een belangrijk onderdeel van uw Microsoft 365-onboarding is ervoor te zorgen dat uw netwerk- en internetverbinding zijn ingesteld voor geoptimaliseerde toegang.</span><span class="sxs-lookup"><span data-stu-id="536dd-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="536dd-108">Het configureren van uw on-premises netwerk om toegang te krijgen tot een saas-cloud (Software-as-a-Service) die wereldwijd wordt gedistribueerd, verschilt van een traditioneel netwerk dat is geoptimaliseerd voor verkeer naar on-premises datacenters en een centrale internetverbinding.</span><span class="sxs-lookup"><span data-stu-id="536dd-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="536dd-109">Gebruik deze artikelen om de belangrijkste verschillen te begrijpen en om uw edge-apparaten, clientcomputers en on-premises netwerk te wijzigen om de beste prestaties te krijgen voor uw on-premises gebruikers.</span><span class="sxs-lookup"><span data-stu-id="536dd-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="536dd-110">Plannen</span><span class="sxs-lookup"><span data-stu-id="536dd-110">Plan</span></span>

<span data-ttu-id="536dd-111">In de planningsfase van de implementatie van uw netwerk:</span><span class="sxs-lookup"><span data-stu-id="536dd-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="536dd-112">Meer informatie over hoe Microsoft 365-netwerken werken</span><span class="sxs-lookup"><span data-stu-id="536dd-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="536dd-113">Uw huidige netwerkconnectiviteit beoordelen</span><span class="sxs-lookup"><span data-stu-id="536dd-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="536dd-114">Bepalen of ExpressRoute juist is voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="536dd-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="536dd-115">Plannen voor uw netwerkapparaten</span><span class="sxs-lookup"><span data-stu-id="536dd-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="536dd-116">Uw netwerk instellen voor migratie</span><span class="sxs-lookup"><span data-stu-id="536dd-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="536dd-117">Implementeren</span><span class="sxs-lookup"><span data-stu-id="536dd-117">Deploy</span></span>

<span data-ttu-id="536dd-118">In de implementatiefase van uw netwerkimplementatie:</span><span class="sxs-lookup"><span data-stu-id="536dd-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="536dd-119">Zorg ervoor dat uw bedrijfsnetwerk is geoptimaliseerd voor Microsoft 365-connectiviteit</span><span class="sxs-lookup"><span data-stu-id="536dd-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="536dd-120">De DNS-domeinen voor uw organisatie toevoegen</span><span class="sxs-lookup"><span data-stu-id="536dd-120">Add the DNS domains for your organization</span></span>](../admin/setup/add-domain.md)
- [<span data-ttu-id="536dd-121">Uw connectiviteit met Microsoft 365-eindpunten optimaliseren</span><span class="sxs-lookup"><span data-stu-id="536dd-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="536dd-122">Connectiviteit optimaliseren voor externe werknemers</span><span class="sxs-lookup"><span data-stu-id="536dd-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="536dd-123">Configureer Indien nodig [ExpressRoute](azure-expressroute.md)</span><span class="sxs-lookup"><span data-stu-id="536dd-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="536dd-124">Beheren</span><span class="sxs-lookup"><span data-stu-id="536dd-124">Manage</span></span>

<span data-ttu-id="536dd-125">In de beheerfase van de implementatie van uw netwerk:</span><span class="sxs-lookup"><span data-stu-id="536dd-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="536dd-126">Controleer of uw netwerkapparaten de nieuwste Office 365-eindpunten gebruiken</span><span class="sxs-lookup"><span data-stu-id="536dd-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="536dd-127">Uw netwerkprestaties controleren en afstemmen</span><span class="sxs-lookup"><span data-stu-id="536dd-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="536dd-128">Uw ExpressRoute-verbindingen bewaken</span><span class="sxs-lookup"><span data-stu-id="536dd-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="536dd-129">Leveranciers van netwerkapparatuur</span><span class="sxs-lookup"><span data-stu-id="536dd-129">Network equipment vendors</span></span>

<span data-ttu-id="536dd-130">Als u een leverancier van netwerkapparatuur bent, kunt u deelnemen aan het [Microsoft 365 Networking Partner Program.](microsoft-365-networking-partner-program.md)</span><span class="sxs-lookup"><span data-stu-id="536dd-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="536dd-131">Schrijf u in voor het programma om microsoft 365-netwerkconnectiviteitsprincipes te bouwen in uw producten en oplossingen.</span><span class="sxs-lookup"><span data-stu-id="536dd-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="536dd-132">Hoe Contoso heeft genetwerkt voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="536dd-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="536dd-133">Bekijk hoe Contoso Corporation, een fictieve maar representatieve multinational, [hun netwerkapparaten en internetverbindingen hebben geoptimaliseerd](contoso-networking.md) voor Microsoft 365-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="536dd-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="536dd-135">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="536dd-135">Next step</span></span>

<span data-ttu-id="536dd-136">Start uw netwerkplanning met het overzicht van [de Microsoft 365-netwerkconnectiviteit.](microsoft-365-networking-overview.md)</span><span class="sxs-lookup"><span data-stu-id="536dd-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>