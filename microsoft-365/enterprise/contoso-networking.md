---
title: Netwerken voor de Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Inzicht in de infrastructuur van Contoso netwerken en hoe deze wordt gebruikt voor optimale netwerkprestaties voor Microsoft 365 voor Enterprise cloudservices.
ms.openlocfilehash: bc2ae68917258b94ed46ef0c1257f56e0736105c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685816"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="62712-103">Netwerken voor de Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="62712-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="62712-104">Om een cloud-inclusieve infrastructuur te implementeren, hebben de netwerkengineers van Contoso een fundamentele verschuiving gerealiseerd in de manier waarop netwerkverkeer naar cloudservices wordt geleid.</span><span class="sxs-lookup"><span data-stu-id="62712-104">To adopt a cloud-inclusive infrastructure, Contoso's network engineers realized the fundamental shift in the way that network traffic to cloud services travels.</span></span> <span data-ttu-id="62712-105">In plaats van een intern hub-and-spoke-model waarin netwerkconnectiviteit en netwerkverkeer wordt gericht op het volgende niveau van de kantoorhiërarchie van Contoso, hebben ze gebruikerslocaties aan lokale internet-uitgangen en lokale verbindingen aan de dichtstbijzijnde Microsoft 365-netwerklocatie op het internet gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="62712-105">Instead of an internal hub and spoke model that focusses network connectivity and traffic for the next level of the Contoso office hierarchy, they worked to map user locations to local Internet egress and local connections to the closest Microsoft 365 network location on the Internet.</span></span>

## <a name="contosos-networking-infrastructure"></a><span data-ttu-id="62712-106">Netwerkinfrastructuur van Contoso</span><span class="sxs-lookup"><span data-stu-id="62712-106">Contoso's networking infrastructure</span></span>

<span data-ttu-id="62712-107">De elementen van het netwerk van Contoso die hun kantoren op de hele wereld koppelen, zijn de volgende:</span><span class="sxs-lookup"><span data-stu-id="62712-107">The elements of Contoso's network that links their offices across the globe are the following:</span></span>

- <span data-ttu-id="62712-108">Multiprotocol-Label Switching (MPLS) WAN-netwerk</span><span class="sxs-lookup"><span data-stu-id="62712-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="62712-109">Een MPLS WAN-netwerk verbindt het hoofdkantoor in Parijs met regionale kantoren en regionale kantoren met satellietkantoren in een hub-and-spoke-configuratie.</span><span class="sxs-lookup"><span data-stu-id="62712-109">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke and hub configuration.</span></span> <span data-ttu-id="62712-110">Zo hebben gebruikers toegang tot servers op locatie met Line of Business-toepassingen in het kantoor in Parijs.</span><span class="sxs-lookup"><span data-stu-id="62712-110">This is for users to access on-premises servers that make up line of business applications in the Paris office.</span></span> <span data-ttu-id="62712-111">Het leidt ook al het algemene internetverkeer naar het kantoor in Parijs, waar netwerkbeveiligingsapparaten de verzoeken beoordelen.</span><span class="sxs-lookup"><span data-stu-id="62712-111">It also routes any generic Internet traffic to the Paris office where network security devices scrub the requests.</span></span> <span data-ttu-id="62712-112">Binnen elke kantoor leiden routers het verkeer naar draadgebonden hosts of draadloze toegangspunten op subnetten, die gebruikmaken van de particuliere IP-adresruimte.</span><span class="sxs-lookup"><span data-stu-id="62712-112">Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="62712-113">Lokale rechtstreekse internettoegang voor Microsoft 365-verkeer</span><span class="sxs-lookup"><span data-stu-id="62712-113">Local direct Internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="62712-114">Elk kantoor heeft een softwaregedefinieerd WAN-apparaat met een of meer lokale netwerkcircuits van de internetprovider en een eigen internetverbinding via een proxyserver.</span><span class="sxs-lookup"><span data-stu-id="62712-114">Each office has a Software-Defined WAN (SD-WAN) device with one of more local Internet ISP network circuits, with its own Internet connectivity through a proxy server.</span></span> <span data-ttu-id="62712-115">Dit wordt meestal geïmplementeerd als een WAN-koppeling naar een lokale internetprovider die ook openbare IP-adressen en een lokale DNS-server biedt.</span><span class="sxs-lookup"><span data-stu-id="62712-115">This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="62712-116">Internetaanwezigheid</span><span class="sxs-lookup"><span data-stu-id="62712-116">Internet presence</span></span>

  <span data-ttu-id="62712-117">Contoso is de eigenaar van de openbare domeinnaam contoso.com.</span><span class="sxs-lookup"><span data-stu-id="62712-117">Contoso owns the contoso.com public domain name.</span></span> <span data-ttu-id="62712-118">De openbare website van Contoso voor het bestellen van producten draait op een reeks servers in een op het internet aangesloten datacenter op de campus in Parijs.</span><span class="sxs-lookup"><span data-stu-id="62712-118">The Contoso public web site for ordering products is a set of servers in an Internet-connected datacenter in the Paris campus.</span></span> <span data-ttu-id="62712-119">Contoso gebruikt een /24 openbaar IP-adresbereik op het internet.</span><span class="sxs-lookup"><span data-stu-id="62712-119">Contoso uses a /24 public IP address range on the Internet.</span></span>

<span data-ttu-id="62712-120">Afbeelding 1 toont de netwerkinfrastructuur van Contoso en de bijbehorende verbindingen met het internet.</span><span class="sxs-lookup"><span data-stu-id="62712-120">Figure 1 shows Contoso's networking infrastructure and its connections to the Internet.</span></span>

![Het netwerk van Contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="62712-122">**Afbeelding 1: Het netwerk van Contoso**</span><span class="sxs-lookup"><span data-stu-id="62712-122">**Figure 1: Contoso's network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="62712-123">Gebruik van SD-WAN voor optimale netwerkconnectiviteit met Microsoft</span><span class="sxs-lookup"><span data-stu-id="62712-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="62712-124">Contoso heeft de [Beginselen voor Microsoft 365-netwerkconnectiviteit](microsoft-365-network-connectivity-principles.md) gevolgd om:</span><span class="sxs-lookup"><span data-stu-id="62712-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

1. <span data-ttu-id="62712-125">Netwerkverkeer van Microsoft 365 te identificeren en te onderscheiden</span><span class="sxs-lookup"><span data-stu-id="62712-125">Identify and differentiate Microsoft 365 network traffic</span></span>
2. <span data-ttu-id="62712-126">Lokale uitgangen van netwerkverbindingen te regelen</span><span class="sxs-lookup"><span data-stu-id="62712-126">Egress network connections locally</span></span>
3. <span data-ttu-id="62712-127">Netwerk-hairpins te vermijden</span><span class="sxs-lookup"><span data-stu-id="62712-127">Avoid network hairpins</span></span>
4. <span data-ttu-id="62712-128">Dubbele netwerkbeveiligingsapparaten te omzeilen</span><span class="sxs-lookup"><span data-stu-id="62712-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="62712-129">Er zijn drie categorieën netwerkverkeer voor Microsoft 365: Optimaliseren, toestaan en standaard.</span><span class="sxs-lookup"><span data-stu-id="62712-129">There are three categories of network traffic for Microsoft 365: Optimize, Allow, and Default.</span></span> <span data-ttu-id="62712-130">Verkeer in de categorieën Optimaliseren en Toestaan is betrouwbaar netwerkverkeer dat versleuteld en beveiligd is bij de eindpunten en is bestemd voor het Microsoft 365-netwerk.</span><span class="sxs-lookup"><span data-stu-id="62712-130">Optimize and Allow traffic is trusted network traffic that is encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="62712-131">Contoso heeft besloten om:</span><span class="sxs-lookup"><span data-stu-id="62712-131">Contoso decided to:</span></span>

- <span data-ttu-id="62712-132">Directe internetuitgangen te gebruiken voor verkeer uit de categorieën Optimaliseren en Toestaan en voor het doorsturen van al het verkeer in de categorie Standaard naar de centrale internetverbinding met Parijs.</span><span class="sxs-lookup"><span data-stu-id="62712-132">Use direct Internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central Internet connection.</span></span>

- <span data-ttu-id="62712-133">Op elk van hun kantoorlocaties SD-WAN-apparaten te implementeren om deze principes op een eenvoudige manier toe te passen en optimale netwerkprestaties te bereiken voor de cloudservices van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="62712-133">Deploy SD-WAN devices at each of their office locations as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="62712-134">De SD-WAN-apparaten hebben een LAN-poort voor het lokale kantoornetwerk en meerdere WAN-poorten.</span><span class="sxs-lookup"><span data-stu-id="62712-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="62712-135">Een WAN-poort maakt verbinding met het MPLS-netwerk en een andere WAN-poort maakt verbinding met een lokaal ISP-circuit.</span><span class="sxs-lookup"><span data-stu-id="62712-135">One WAN port connects to their MPLS network and another WAN port connects to a local ISP circuit.</span></span> <span data-ttu-id="62712-136">Het SD-WAN-apparaat leidt netwerkverkeer uit de categorieën Optimaliseren en Toestaan via de ISP-koppeling.</span><span class="sxs-lookup"><span data-stu-id="62712-136">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="contosos-line-of-business-app-infrastructure"></a><span data-ttu-id="62712-137">De Line of Business-toepassingeninfrastructuur van Contoso</span><span class="sxs-lookup"><span data-stu-id="62712-137">Contoso's line of business app infrastructure</span></span>

<span data-ttu-id="62712-138">Contoso heeft haar Line of Business-toepassingen- en serverintranetinfrastructuur ingericht voor het volgende:</span><span class="sxs-lookup"><span data-stu-id="62712-138">Contoso has architected its line of business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="62712-139">Satellietkantoren gebruiken lokale cacheservers voor het opslaan van veelgebruikte documenten en interne websites.</span><span class="sxs-lookup"><span data-stu-id="62712-139">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="62712-140">Regionale hubs gebruiken regionale toepassingsservers voor de regionale en satellietkantoren.</span><span class="sxs-lookup"><span data-stu-id="62712-140">Regional hubs use regional application servers for the regional and satellite offices.</span></span> <span data-ttu-id="62712-141">Deze servers worden gesynchroniseerd met servers in het hoofdkantoor in Parijs.</span><span class="sxs-lookup"><span data-stu-id="62712-141">These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="62712-142">Op de campus in Parijs bevinden zich datacenters met gecentraliseerde toepassingsservers waar de hele organisatie gebruik van maakt.</span><span class="sxs-lookup"><span data-stu-id="62712-142">The Paris campus has the datacenters that contain the centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="62712-143">Afbeelding 2 toont het percentage van netwerkverkeer bij het verkrijgen van toegang tot servers in het intranet van contoso.</span><span class="sxs-lookup"><span data-stu-id="62712-143">Figure 2 shows the percentage of network traffic when accessing servers across Contoso’s intranet.</span></span>

![De infrastructuur van Contoso voor interne toepassingen](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="62712-145">**Afbeelding 2: De infrastructuur van Contoso voor interne toepassingen**</span><span class="sxs-lookup"><span data-stu-id="62712-145">**Figure 2: Contoso's infrastructure for internal applications**</span></span>

<span data-ttu-id="62712-146">Voor gebruikers op satelliet- of regionale hub-kantoren kan 60% van de resources die nodig zijn voor werknemers worden bediend door satelliet- en regionale kantoorservers.</span><span class="sxs-lookup"><span data-stu-id="62712-146">For users in satellite or regional hub offices, 60% of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="62712-147">De extra 40% van de resourceaanvragen moet via de WAN-koppeling naar de campus in Parijs worden geleid.</span><span class="sxs-lookup"><span data-stu-id="62712-147">The additional 40% of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-for-enterprise"></a><span data-ttu-id="62712-148">De netwerkanalyse en-voorbereiding van Contoso voor het netwerk voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="62712-148">Contoso's network analysis and preparation of their network for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="62712-149">De aanneming van Microsoft 365 voor Enterprise Services door de gebruikers van Contoso is afhankelijk van uiterst beschikbare en uitvoering van connectiviteit met internet, of rechtstreeks naar Microsoft-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="62712-149">Successful adoption of Microsoft 365 for enterprise services by Contoso’s users depend on highly available and performant connectivity to the Internet, or directly to Microsoft cloud services.</span></span> <span data-ttu-id="62712-150">Contoso heeft de volgende stappen uitgevoerd voor het plannen en implementeren van geoptimaliseerde verbindingen met Microsoft 365 voor Enterprise cloudservices:</span><span class="sxs-lookup"><span data-stu-id="62712-150">Contoso took these steps to plan for and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="62712-151">Een WAN-netwerkdiagram van het bedrijf gemaakt om te helpen bij de planning</span><span class="sxs-lookup"><span data-stu-id="62712-151">Created a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="62712-152">Contoso heeft de netwerkplanning gestart door een diagram te maken met de bijbehorende locaties, de bestaande netwerkconnectiviteit, de bestaande apparaten voor de netwerkperimeter en de klassen van de service die worden beheerd op het netwerk.</span><span class="sxs-lookup"><span data-stu-id="62712-152">Contoso started their network planning by creating a diagram showing their locations, the existing network connectivity, their existing network perimeter devices and classes of service that are managed on the network.</span></span> <span data-ttu-id="62712-153">Ze hebben deze diagram gebruikt voor elke daaropvolgende stap in de planning en tijdens de implementatie van netwerkconnectiviteit.</span><span class="sxs-lookup"><span data-stu-id="62712-153">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="62712-154">Een plan gemaakt voor Microsoft 365 voor Enterprise Network Connectivity</span><span class="sxs-lookup"><span data-stu-id="62712-154">Created a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="62712-155">Contoso heeft de [Basisprincipes voor Microsoft 365-netwerkconnectiviteit](microsoft-365-network-connectivity-principles.md) en netwerkarchitecturen ter referentie geleverd om SD-WAN vast te leggen als gewenste topologie voor Microsoft 365-connectiviteit.</span><span class="sxs-lookup"><span data-stu-id="62712-155">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and provided reference network architectures to determine SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="62712-156">Het verbruik van de internetverbinding en de MPLS WAN-bandbreedte op elke kantoor geanalyseerd en de bandbreedte indien nodig verhoogd</span><span class="sxs-lookup"><span data-stu-id="62712-156">Analyzed Internet connection utilization and MPLS WAN bandwidth at each office and increased bandwidth as needed</span></span>

   <span data-ttu-id="62712-157">Het huidige verbruik van elk kantoor is geanalyseerd en circuits zijn uitgebreid, zodat het verwachte verkeer in de Microsoft 365 Cloud zou worden uitgevoerd met een gemiddelde van 20% aan de niet-gebruikte capaciteit.</span><span class="sxs-lookup"><span data-stu-id="62712-157">Each office was analyzed for the current usage and circuits were increased so that predicted Microsoft 365 cloud-based traffic would be operating with an average of 20% of unused capacity.</span></span>

4. <span data-ttu-id="62712-158">Optimale prestaties van Microsoft-netwerkservices</span><span class="sxs-lookup"><span data-stu-id="62712-158">Optimized performance to Microsoft network services</span></span>

   <span data-ttu-id="62712-159">Contoso heeft de set met Office 365-, Intune- en Azure-eindpunten vastgesteld en firewalls, beveiligingsapparaten en andere systemen in het internetpad geconfigureerd voor optimale prestaties.</span><span class="sxs-lookup"><span data-stu-id="62712-159">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the Internet path for optimal performance.</span></span> <span data-ttu-id="62712-160">Eindpunten voor Office 365-verkeer in de categorieën Optimaliseren en Toestaan zijn in de SD-WAN-apparaten geconfigureerd voor routering via het ISP-circuit.</span><span class="sxs-lookup"><span data-stu-id="62712-160">Endpoints for Office 365 Optimize and Allow category traffic was configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="62712-161">Interne DNS geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="62712-161">Configured internal DNS</span></span>

   <span data-ttu-id="62712-162">DNS moet functioneel zijn en lokaal worden opgezocht voor Microsoft 365-verkeer.</span><span class="sxs-lookup"><span data-stu-id="62712-162">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="62712-163">Gevalideerd netwerkeindpunt en poortconnectiviteit</span><span class="sxs-lookup"><span data-stu-id="62712-163">Validated network endpoint and port connectivity</span></span>

   <span data-ttu-id="62712-164">Contoso heeft testhulpprogramma's voor netwerkverbindingen van Microsoft uitgevoerd om de connectiviteit voor Microsoft 365 te valideren voor Enterprise cloudservices.</span><span class="sxs-lookup"><span data-stu-id="62712-164">Contoso ran network connectivity test tools provided by Microsoft to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="62712-165">Computers van werknemers geoptimaliseerd voor netwerkconnectiviteit</span><span class="sxs-lookup"><span data-stu-id="62712-165">Optimized employee computers for network connectivity</span></span>

   <span data-ttu-id="62712-166">Afzonderlijke computers zijn gecontroleerd om te controleren of de meest recente updates voor het besturingssysteem geïnstalleerd waren en controle van de eindpuntbeveiliging bij alle clients actief was.</span><span class="sxs-lookup"><span data-stu-id="62712-166">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring is active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="62712-167">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="62712-167">Next step</span></span>

<span data-ttu-id="62712-168">[Lees hier meer](contoso-identity.md) over hoe Contoso op locatie Active Directory Domain Services (AD DS) in de Cloud gebruikt voor werknemers en federatieve verificatie voor klanten en zakenpartners.</span><span class="sxs-lookup"><span data-stu-id="62712-168">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises Active Directory Domain Services (AD DS) in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="62712-169">Zie ook</span><span class="sxs-lookup"><span data-stu-id="62712-169">See also</span></span>

[<span data-ttu-id="62712-170">Netwerkkaart voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62712-170">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="62712-171">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="62712-171">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="62712-172">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="62712-172">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
