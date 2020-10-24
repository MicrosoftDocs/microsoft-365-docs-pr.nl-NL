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
description: Inzicht in de infrastructuur contoso-netwerken en de manier waarop het bedrijf de SD-WAN-technologie gebruikt voor optimale netwerkprestaties voor Microsoft 365 voor Enterprise Cloud-Services.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754012"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="69851-103">Netwerken voor de Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="69851-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="69851-104">Als u een infrastructuur van de Cloud gebruikt, is contoso een fundamentele dienst ontwikkeld voor de manier waarop netwerkverkeer voor cloudservices wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="69851-104">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels.</span></span> <span data-ttu-id="69851-105">In plaats van een intern hub-en-spoke-model dat de netwerkverbinding en het verkeer voor het volgende niveau van de Office-hiërarchie benadert, hebben ze gebruikerslocaties toegewezen aan lokale Internet uitvullen en lokale verbindingen met de dichtstbijzijnde Microsoft 365-netwerklocatie op internet.</span><span class="sxs-lookup"><span data-stu-id="69851-105">Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="69851-106">Netwerkinfrastructuur</span><span class="sxs-lookup"><span data-stu-id="69851-106">Networking infrastructure</span></span>

<span data-ttu-id="69851-107">Dit zijn de netwerkelementen waarmee contoso-afdelingen overal ter wereld worden gekoppeld:</span><span class="sxs-lookup"><span data-stu-id="69851-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="69851-108">Multiprotocol-Label Switching (MPLS) WAN-netwerk</span><span class="sxs-lookup"><span data-stu-id="69851-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="69851-109">Een MPLS WAN-netwerk verbindt de hoofdkantoren van Parijs met regionale kantoren en regionale kantoren naar satelliet kantoren via een spoke-en-hub-configuratie.</span><span class="sxs-lookup"><span data-stu-id="69851-109">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration.</span></span> <span data-ttu-id="69851-110">Het netwerk biedt gebruikers toegang tot on-premises servers die line-of-business-toepassingen maken in de Headquarters van Parijs.</span><span class="sxs-lookup"><span data-stu-id="69851-110">The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters.</span></span> <span data-ttu-id="69851-111">Ook wordt elk algemeen internetverkeer naar het kantoor van Parijs gerouteerd, waarbij de netwerk beveiligingsapparaten de verzoeken reinigen.</span><span class="sxs-lookup"><span data-stu-id="69851-111">It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests.</span></span> <span data-ttu-id="69851-112">Binnen elke kantoor leiden routers het verkeer naar draadgebonden hosts of draadloze toegangspunten op subnetten, die gebruikmaken van de particuliere IP-adresruimte.</span><span class="sxs-lookup"><span data-stu-id="69851-112">Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="69851-113">Lokale directe Internet toegang voor Microsoft 365-verkeer</span><span class="sxs-lookup"><span data-stu-id="69851-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="69851-114">Elke Office heeft een door software gedefinieerd WAN (SD)-apparaat met een of meer lokale netwerkclients met een internetverbinding via een proxyserver.</span><span class="sxs-lookup"><span data-stu-id="69851-114">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server.</span></span> <span data-ttu-id="69851-115">Dit wordt meestal geïmplementeerd als een WAN-koppeling naar een lokale internetprovider die ook openbare IP-adressen en een lokale DNS-server biedt.</span><span class="sxs-lookup"><span data-stu-id="69851-115">This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="69851-116">Internetaanwezigheid</span><span class="sxs-lookup"><span data-stu-id="69851-116">Internet presence</span></span>

  <span data-ttu-id="69851-117">Contoso bezit de naam van het \. openbare com-domein van contoso.</span><span class="sxs-lookup"><span data-stu-id="69851-117">Contoso owns the contoso\.com public domain name.</span></span> <span data-ttu-id="69851-118">De openbare website van Contoso voor het bestellen van producten is een reeks servers in een datacenter dat verbonden is met internet in de Parijs.</span><span class="sxs-lookup"><span data-stu-id="69851-118">The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus.</span></span> <span data-ttu-id="69851-119">Contoso maakt gebruik van een openbaar IP-adresbereik op internet.</span><span class="sxs-lookup"><span data-stu-id="69851-119">Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="69851-120">Afbeelding 1 toont de infrastructuur van Contoso-netwerken en de bijbehorende verbindingen met internet.</span><span class="sxs-lookup"><span data-stu-id="69851-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![Het contoso netwerk](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="69851-122">**Afbeelding 1: het contoso netwerk**</span><span class="sxs-lookup"><span data-stu-id="69851-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="69851-123">Gebruik van SD-WAN voor optimale netwerkconnectiviteit met Microsoft</span><span class="sxs-lookup"><span data-stu-id="69851-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="69851-124">Contoso heeft de [Beginselen voor Microsoft 365-netwerkconnectiviteit](microsoft-365-network-connectivity-principles.md) gevolgd om:</span><span class="sxs-lookup"><span data-stu-id="69851-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="69851-125">Netwerkverkeer van Microsoft 365 te identificeren en te onderscheiden</span><span class="sxs-lookup"><span data-stu-id="69851-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="69851-126">Lokale uitgangen van netwerkverbindingen te regelen</span><span class="sxs-lookup"><span data-stu-id="69851-126">Egress network connections locally</span></span>
- <span data-ttu-id="69851-127">Netwerk-hairpins te vermijden</span><span class="sxs-lookup"><span data-stu-id="69851-127">Avoid network hairpins</span></span>
- <span data-ttu-id="69851-128">Dubbele netwerkbeveiligingsapparaten te omzeilen</span><span class="sxs-lookup"><span data-stu-id="69851-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="69851-129">Er zijn drie categorieën netwerkverkeer voor Microsoft 365: *optimaliseren*, *toestaan*en *standaard*.</span><span class="sxs-lookup"><span data-stu-id="69851-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="69851-130">Verkeer optimaliseren en toestaan wordt vertrouwd netwerkverkeer dat is versleuteld en beveiligd bij de eindpunten en is bestemd voor het Microsoft 365-netwerk.</span><span class="sxs-lookup"><span data-stu-id="69851-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="69851-131">Contoso heeft besloten om:</span><span class="sxs-lookup"><span data-stu-id="69851-131">Contoso decided to:</span></span>

- <span data-ttu-id="69851-132">U kunt direct Internet uitvullen gebruiken voor het optimaliseren en toestaan van categorie verkeer en alle standaardcategorie verkeer door te sturen naar de op de basis internetverbinding van Parijs.</span><span class="sxs-lookup"><span data-stu-id="69851-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="69851-133">Implementeer een SD-WAN-apparaat op elk Office als eenvoudige manier om deze principes te volgen en de prestaties van het netwerk te verbeteren voor Microsoft 365 cloudservices.</span><span class="sxs-lookup"><span data-stu-id="69851-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="69851-134">De SD-WAN-apparaten hebben een LAN-poort voor het lokale kantoornetwerk en meerdere WAN-poorten.</span><span class="sxs-lookup"><span data-stu-id="69851-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="69851-135">Eén WAN-poort maakt verbinding met het MPLS-netwerk.</span><span class="sxs-lookup"><span data-stu-id="69851-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="69851-136">Een andere verbinding maakt met een lokaal ISP-circuit.</span><span class="sxs-lookup"><span data-stu-id="69851-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="69851-137">Het SD-WAN-apparaat leidt netwerkverkeer uit de categorieën Optimaliseren en Toestaan via de ISP-koppeling.</span><span class="sxs-lookup"><span data-stu-id="69851-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="69851-138">De infrastructuur van de app contoso line-of-Business</span><span class="sxs-lookup"><span data-stu-id="69851-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="69851-139">Contoso heeft de toepassing line-van-Business en de intranet infrastructuur van de server voor het volgende:</span><span class="sxs-lookup"><span data-stu-id="69851-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="69851-140">Satellietkantoren gebruiken lokale cacheservers voor het opslaan van veelgebruikte documenten en interne websites.</span><span class="sxs-lookup"><span data-stu-id="69851-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="69851-141">Regionale hubs gebruiken regionale toepassingsservers voor de regionale en satellietkantoren.</span><span class="sxs-lookup"><span data-stu-id="69851-141">Regional hubs use regional application servers for the regional and satellite offices.</span></span> <span data-ttu-id="69851-142">Deze servers worden gesynchroniseerd met servers in het hoofdkantoor in Parijs.</span><span class="sxs-lookup"><span data-stu-id="69851-142">These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="69851-143">De bevestigingen van Parijs van Parijs bevatten gecentraliseerde toepassingsservers die de hele organisatie dienen.</span><span class="sxs-lookup"><span data-stu-id="69851-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="69851-144">Afbeelding 2 toont het percentage netwerkverkeer dat wordt gebruikt voor het openen van servers in het intranet van contoso.</span><span class="sxs-lookup"><span data-stu-id="69851-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![De infrastructuur contoso voor interne toepassingen](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="69851-146">**Afbeelding 2: de infrastructuur contoso voor interne toepassingen**</span><span class="sxs-lookup"><span data-stu-id="69851-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="69851-147">Voor de satelliet-of Regional hub-kantoren is 60 procent van de resources die nodig zijn voor de werknemers aan de satelliet en de regionale hub Office servers geleverd.</span><span class="sxs-lookup"><span data-stu-id="69851-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="69851-148">Het extra 40 procent van de resourceaanvragen moet via de WAN-koppeling naar de Parijs van de campus gaan.</span><span class="sxs-lookup"><span data-stu-id="69851-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="69851-149">Netwerkanalyse en-voorbereiding voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="69851-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="69851-150">Geslaagde aanneming van Microsoft 365 voor Enterprise Services door contoso gebruikers is afhankelijk van zeer beschikbare verbindingen met internet of rechtstreeks naar Microsoft-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="69851-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="69851-151">Contoso heeft de volgende stappen uitgevoerd voor het plannen en implementeren van geoptimaliseerde connectiviteit met Microsoft 365 voor Enterprise cloudservices:</span><span class="sxs-lookup"><span data-stu-id="69851-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="69851-152">Een diagram maken van een WAN-netwerk van het bedrijf voor hulp bij de planning</span><span class="sxs-lookup"><span data-stu-id="69851-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="69851-153">Om de netwerk planning te starten, heeft Contoso een diagram gemaakt met hun Office-locaties, bestaande netwerkconnectiviteit, bestaande netwerk verbindingsapparaten en serviceklassen die worden beheerd op het netwerk.</span><span class="sxs-lookup"><span data-stu-id="69851-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="69851-154">Ze hebben deze diagram gebruikt voor elke daaropvolgende stap in de planning en tijdens de implementatie van netwerkconnectiviteit.</span><span class="sxs-lookup"><span data-stu-id="69851-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="69851-155">Een plan maken voor Microsoft 365 voor Enterprise-netwerkconnectiviteit</span><span class="sxs-lookup"><span data-stu-id="69851-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="69851-156">Contoso heeft de [Microsoft 365-netwerk verbindings beginselen](microsoft-365-network-connectivity-principles.md) en de voorbeelden van netwerk architecturen voor de client Architecture voor de microsoft 365-verbinding aangeduid met de desbetreffende topologie.</span><span class="sxs-lookup"><span data-stu-id="69851-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="69851-157">Analyseren van Internet-verbinding met MPLS en de bandbreedte van de WAN-verbinding op elk Office, en de bandbreedte naar wens verhogen</span><span class="sxs-lookup"><span data-stu-id="69851-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="69851-158">Het huidige gebruik van Office is geanalyseerd, en de circuits zijn opgegroeid, zodat Microsoft 365 op de Cloud op basis van het voorspeld verkeer met een gemiddelde van 20 procent niet-gebruikte capaciteit werkt.</span><span class="sxs-lookup"><span data-stu-id="69851-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="69851-159">Prestaties optimaliseren voor Microsoft-netwerkservices</span><span class="sxs-lookup"><span data-stu-id="69851-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="69851-160">Contoso heeft de set Office 365-, intune-en Azure-eindpunten, en de geconfigureerde firewalls, beveiligingsapparaten en andere systemen in Internet Path voor optimale prestaties vastgesteld.</span><span class="sxs-lookup"><span data-stu-id="69851-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="69851-161">Eindpunten voor Office 365 optimaliseren en toestaan dat categorie verkeer is geconfigureerd in de SD-WAN-apparaten voor routering via het routerings circuit.</span><span class="sxs-lookup"><span data-stu-id="69851-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="69851-162">Interne DNS configureren</span><span class="sxs-lookup"><span data-stu-id="69851-162">Configure internal DNS</span></span>

   <span data-ttu-id="69851-163">DNS moet functioneel zijn en lokaal worden opgezocht voor Microsoft 365-verkeer.</span><span class="sxs-lookup"><span data-stu-id="69851-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="69851-164">Netwerkeindpunt en poort verbinding valideren</span><span class="sxs-lookup"><span data-stu-id="69851-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="69851-165">Contoso heeft de testhulpprogramma's voor Microsoft netwerkverbindingen uitgevoerd om de connectiviteit voor Microsoft 365 te valideren voor Enterprise cloudservices.</span><span class="sxs-lookup"><span data-stu-id="69851-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="69851-166">Computers van werknemers voor netwerkconnectiviteit optimaliseren</span><span class="sxs-lookup"><span data-stu-id="69851-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="69851-167">Afzonderlijke computers zijn gecontroleerd om er zeker van te zijn dat de nieuwste updates voor het besturingssysteem zijn geïnstalleerd en dat beveiligings bewaking van endpoint voor alle clients actief was.</span><span class="sxs-lookup"><span data-stu-id="69851-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="69851-168">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="69851-168">Next step</span></span>

<span data-ttu-id="69851-169">Meer informatie over hoe contoso [de on-premises Active Directory-domein Services in de Cloud](contoso-identity.md) verloopt voor werknemers en federeren-verificatie voor klanten en zakenpartners.</span><span class="sxs-lookup"><span data-stu-id="69851-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="69851-170">Zie ook</span><span class="sxs-lookup"><span data-stu-id="69851-170">See also</span></span>

[<span data-ttu-id="69851-171">Netwerkkaart voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69851-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="69851-172">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="69851-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="69851-173">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="69851-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
