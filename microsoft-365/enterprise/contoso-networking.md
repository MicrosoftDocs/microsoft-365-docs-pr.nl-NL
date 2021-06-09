---
title: Netwerken voor de Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Meer informatie over de Contoso-netwerkinfrastructuur en hoe het bedrijf de SD-WAN-technologie gebruikt voor optimale netwerkprestaties Microsoft 365 voor zakelijke cloudservices.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754012"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="990fa-103">Netwerken voor de Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="990fa-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="990fa-104">Als u een cloudinclusieve infrastructuur wilt gebruiken, heeft Contoso een fundamentele verschuiving in de manier waarop netwerkverkeer naar cloudservices wordt verplaatst, ontworpen.</span><span class="sxs-lookup"><span data-stu-id="990fa-104">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels.</span></span> <span data-ttu-id="990fa-105">In plaats van een intern hub- en spaakmodel dat netwerkconnectiviteit en -verkeer voor het volgende niveau van de office-hiërarchie focust, hebben ze gebruikerslocaties in kaart gebracht aan lokale internetafding en lokale verbindingen met de dichtstbijzijnde Microsoft 365-netwerklocatie op internet.</span><span class="sxs-lookup"><span data-stu-id="990fa-105">Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="990fa-106">Netwerkinfrastructuur</span><span class="sxs-lookup"><span data-stu-id="990fa-106">Networking infrastructure</span></span>

<span data-ttu-id="990fa-107">Dit zijn de netwerkelementen die Contoso-kantoren over de hele wereld met elkaar verbinden:</span><span class="sxs-lookup"><span data-stu-id="990fa-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="990fa-108">Multiprotocol-Label Switching (MPLS) WAN-netwerk</span><span class="sxs-lookup"><span data-stu-id="990fa-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="990fa-109">Een MPLS WAN-netwerk verbindt het hoofdkantoor van Parijs met regionale kantoren en regionale kantoren met satellietkantoren in een spaak- en hubconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="990fa-109">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration.</span></span> <span data-ttu-id="990fa-110">Het netwerk stelt gebruikers in staat toegang te krijgen tot on-premises servers die line-of-businesstoepassingen maken in het hoofdkantoor van Parijs.</span><span class="sxs-lookup"><span data-stu-id="990fa-110">The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters.</span></span> <span data-ttu-id="990fa-111">Ook worden alle algemene internetverkeer naar het kantoor in Parijs gerouteerd, waar netwerkbeveiligingsapparaten de aanvragen opscruten.</span><span class="sxs-lookup"><span data-stu-id="990fa-111">It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests.</span></span> <span data-ttu-id="990fa-112">Binnen elke kantoor leiden routers het verkeer naar draadgebonden hosts of draadloze toegangspunten op subnetten, die gebruikmaken van de particuliere IP-adresruimte.</span><span class="sxs-lookup"><span data-stu-id="990fa-112">Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="990fa-113">Lokale directe internettoegang voor Microsoft 365 verkeer</span><span class="sxs-lookup"><span data-stu-id="990fa-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="990fa-114">Elk kantoor heeft een door software gedefinieerd WAN-apparaat (SD-WAN) dat een of meer lokale internetnetwerkcircuits met een eigen internetverbinding heeft via een proxyserver.</span><span class="sxs-lookup"><span data-stu-id="990fa-114">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server.</span></span> <span data-ttu-id="990fa-115">Dit wordt meestal geïmplementeerd als een WAN-koppeling naar een lokale internetprovider die ook openbare IP-adressen en een lokale DNS-server biedt.</span><span class="sxs-lookup"><span data-stu-id="990fa-115">This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="990fa-116">Internetaanwezigheid</span><span class="sxs-lookup"><span data-stu-id="990fa-116">Internet presence</span></span>

  <span data-ttu-id="990fa-117">Contoso is de eigenaar van de openbare domeinnaam contoso \. com.</span><span class="sxs-lookup"><span data-stu-id="990fa-117">Contoso owns the contoso\.com public domain name.</span></span> <span data-ttu-id="990fa-118">De openbare website van Contoso voor het bestellen van producten is een set servers in een datacenter met internetverbinding op de parijse campus.</span><span class="sxs-lookup"><span data-stu-id="990fa-118">The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus.</span></span> <span data-ttu-id="990fa-119">Contoso gebruikt een openbaar IP-adresbereik van /24 op internet.</span><span class="sxs-lookup"><span data-stu-id="990fa-119">Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="990fa-120">Afbeelding 1 toont de Contoso-netwerkinfrastructuur en de verbindingen met internet.</span><span class="sxs-lookup"><span data-stu-id="990fa-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![Het Contoso-netwerk](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="990fa-122">**Afbeelding 1: Het Contoso-netwerk**</span><span class="sxs-lookup"><span data-stu-id="990fa-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="990fa-123">Gebruik van SD-WAN voor optimale netwerkconnectiviteit met Microsoft</span><span class="sxs-lookup"><span data-stu-id="990fa-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="990fa-124">Contoso heeft de [Beginselen voor Microsoft 365-netwerkconnectiviteit](microsoft-365-network-connectivity-principles.md) gevolgd om:</span><span class="sxs-lookup"><span data-stu-id="990fa-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="990fa-125">Netwerkverkeer van Microsoft 365 te identificeren en te onderscheiden</span><span class="sxs-lookup"><span data-stu-id="990fa-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="990fa-126">Lokale uitgangen van netwerkverbindingen te regelen</span><span class="sxs-lookup"><span data-stu-id="990fa-126">Egress network connections locally</span></span>
- <span data-ttu-id="990fa-127">Netwerk-hairpins te vermijden</span><span class="sxs-lookup"><span data-stu-id="990fa-127">Avoid network hairpins</span></span>
- <span data-ttu-id="990fa-128">Dubbele netwerkbeveiligingsapparaten te omzeilen</span><span class="sxs-lookup"><span data-stu-id="990fa-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="990fa-129">Er zijn drie categorieën netwerkverkeer voor Microsoft 365: *Optimaliseren,* *Toestaan* en *Standaard.*</span><span class="sxs-lookup"><span data-stu-id="990fa-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="990fa-130">Het optimaliseren en toestaan van verkeer is vertrouwd netwerkverkeer dat is versleuteld en beveiligd op de eindpunten en bestemd is voor het Microsoft 365 netwerk.</span><span class="sxs-lookup"><span data-stu-id="990fa-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="990fa-131">Contoso heeft besloten om:</span><span class="sxs-lookup"><span data-stu-id="990fa-131">Contoso decided to:</span></span>

- <span data-ttu-id="990fa-132">Gebruik direct internet egress voor Het optimaliseren en toestaan van categorieverkeer en om alle standaardcategorieverkeer door te sturen naar de centrale internetverbinding in Parijs.</span><span class="sxs-lookup"><span data-stu-id="990fa-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="990fa-133">Implementeer SD-WAN-apparaten op elk kantoor als een eenvoudige manier om deze principes te volgen en optimale netwerkprestaties te bereiken voor Microsoft 365 cloudservices.</span><span class="sxs-lookup"><span data-stu-id="990fa-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="990fa-134">De SD-WAN-apparaten hebben een LAN-poort voor het lokale kantoornetwerk en meerdere WAN-poorten.</span><span class="sxs-lookup"><span data-stu-id="990fa-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="990fa-135">Eén WAN-poort maakt verbinding met het MPLS-netwerk.</span><span class="sxs-lookup"><span data-stu-id="990fa-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="990fa-136">Een andere verbinding maakt verbinding met een lokaal isp-circuit.</span><span class="sxs-lookup"><span data-stu-id="990fa-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="990fa-137">Het SD-WAN-apparaat leidt netwerkverkeer uit de categorieën Optimaliseren en Toestaan via de ISP-koppeling.</span><span class="sxs-lookup"><span data-stu-id="990fa-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="990fa-138">De contoso-app-infrastructuur</span><span class="sxs-lookup"><span data-stu-id="990fa-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="990fa-139">Contoso heeft de line-of-business-toepassings- en serverintranetinfrastructuur voor het volgende ontworpen:</span><span class="sxs-lookup"><span data-stu-id="990fa-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="990fa-140">Satellietkantoren gebruiken lokale cacheservers voor het opslaan van veelgebruikte documenten en interne websites.</span><span class="sxs-lookup"><span data-stu-id="990fa-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="990fa-141">Regionale hubs gebruiken regionale toepassingsservers voor de regionale en satellietkantoren.</span><span class="sxs-lookup"><span data-stu-id="990fa-141">Regional hubs use regional application servers for the regional and satellite offices.</span></span> <span data-ttu-id="990fa-142">Deze servers worden gesynchroniseerd met servers in het hoofdkantoor in Parijs.</span><span class="sxs-lookup"><span data-stu-id="990fa-142">These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="990fa-143">De parijse campus datacenters bevatten gecentraliseerde toepassingsservers die de hele organisatie bedienen.</span><span class="sxs-lookup"><span data-stu-id="990fa-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="990fa-144">Afbeelding 2 toont het percentage van de netwerkverkeerscapaciteit dat wordt gebruikt bij het openen van servers op het intranet van Contoso.</span><span class="sxs-lookup"><span data-stu-id="990fa-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![De Contoso-infrastructuur voor interne toepassingen](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="990fa-146">**Afbeelding 2: De Contoso-infrastructuur voor interne toepassingen**</span><span class="sxs-lookup"><span data-stu-id="990fa-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="990fa-147">Voor de satelliet- of regionale hubkantoren kan 60 procent van de benodigde resources door werknemers worden gebruikt via satelliet- en regionale hub-officeservers.</span><span class="sxs-lookup"><span data-stu-id="990fa-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="990fa-148">De extra 40 procent van de resourceaanvragen moet via de WAN-koppeling naar de parijse campus gaan.</span><span class="sxs-lookup"><span data-stu-id="990fa-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="990fa-149">Netwerkanalyse en voorbereiding voor Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="990fa-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="990fa-150">Succesvolle acceptatie van Microsoft 365 voor zakelijke services door Contoso-gebruikers is afhankelijk van zeer beschikbare en performante connectiviteit met internet of rechtstreeks met Microsoft-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="990fa-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="990fa-151">Contoso heeft de volgende stappen ondernomen om geoptimaliseerde connectiviteit te plannen en te implementeren Microsoft 365 voor zakelijke cloudservices:</span><span class="sxs-lookup"><span data-stu-id="990fa-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="990fa-152">Een BEDRIJFS WAN-netwerkdiagram maken om hulp te bieden bij het plannen</span><span class="sxs-lookup"><span data-stu-id="990fa-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="990fa-153">Om de netwerkplanning te starten, heeft Contoso een diagram gemaakt met hun kantoorlocaties, bestaande netwerkconnectiviteit, bestaande netwerkperimeters en serviceklassen die worden beheerd in het netwerk.</span><span class="sxs-lookup"><span data-stu-id="990fa-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="990fa-154">Ze hebben deze diagram gebruikt voor elke daaropvolgende stap in de planning en tijdens de implementatie van netwerkconnectiviteit.</span><span class="sxs-lookup"><span data-stu-id="990fa-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="990fa-155">Een plan maken voor Microsoft 365 voor zakelijke netwerkconnectiviteit</span><span class="sxs-lookup"><span data-stu-id="990fa-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="990fa-156">Contoso heeft de [Microsoft 365](microsoft-365-network-connectivity-principles.md) netwerkconnectiviteitsprincipes en voorbeeldverwijzingsnetwerkarchitectuur gebruikt om SD-WAN te identificeren als hun voorkeurstopologie voor Microsoft 365 connectiviteit.</span><span class="sxs-lookup"><span data-stu-id="990fa-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="990fa-157">Analyseer het gebruik van internetverbinding en MPLS-WAN-bandbreedte op elk kantoor en verhoog de bandbreedte zo nodig</span><span class="sxs-lookup"><span data-stu-id="990fa-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="990fa-158">Het huidige gebruik van elk kantoor is geanalyseerd en circuits zijn verhoogd, zodat voorspeld Microsoft 365 cloudverkeer zou werken met een gemiddelde van 20 procent ongebruikte capaciteit.</span><span class="sxs-lookup"><span data-stu-id="990fa-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="990fa-159">Prestaties optimaliseren voor Microsoft-netwerkservices</span><span class="sxs-lookup"><span data-stu-id="990fa-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="990fa-160">Contoso heeft de set Office 365, Intune en Azure-eindpunten en geconfigureerde firewalls, beveiligingsapparaten en andere systemen in het internetpad bepaald voor optimale prestaties.</span><span class="sxs-lookup"><span data-stu-id="990fa-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="990fa-161">Eindpunten voor Office 365 Categorieverkeer optimaliseren en toestaan zijn geconfigureerd op de SD-WAN-apparaten voor routering via het isp-circuit.</span><span class="sxs-lookup"><span data-stu-id="990fa-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="990fa-162">Interne DNS configureren</span><span class="sxs-lookup"><span data-stu-id="990fa-162">Configure internal DNS</span></span>

   <span data-ttu-id="990fa-163">DNS moet functioneel zijn en lokaal worden opgezocht voor Microsoft 365-verkeer.</span><span class="sxs-lookup"><span data-stu-id="990fa-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="990fa-164">Netwerk-eindpunt- en poortconnectiviteit valideren</span><span class="sxs-lookup"><span data-stu-id="990fa-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="990fa-165">Contoso heeft testprogramma's voor Microsoft-netwerkconnectiviteit uitgevoerd om connectiviteit te valideren Microsoft 365 voor zakelijke cloudservices.</span><span class="sxs-lookup"><span data-stu-id="990fa-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="990fa-166">Werknemerscomputers optimaliseren voor netwerkconnectiviteit</span><span class="sxs-lookup"><span data-stu-id="990fa-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="990fa-167">Afzonderlijke computers zijn gecontroleerd om ervoor te zorgen dat de meest recente updates van het besturingssysteem zijn geïnstalleerd en dat beveiligingscontrole van eindpunten actief was op alle clients.</span><span class="sxs-lookup"><span data-stu-id="990fa-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="990fa-168">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="990fa-168">Next step</span></span>

<span data-ttu-id="990fa-169">Lees hoe Contoso gebruik maakt van de [on-premises Active Directory Domain Services in](contoso-identity.md) de cloud voor werknemers en verificatie voor klanten en zakenpartners federatief maakt.</span><span class="sxs-lookup"><span data-stu-id="990fa-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="990fa-170">Zie ook</span><span class="sxs-lookup"><span data-stu-id="990fa-170">See also</span></span>

[<span data-ttu-id="990fa-171">Netwerkroutekaart voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="990fa-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="990fa-172">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="990fa-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="990fa-173">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="990fa-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
