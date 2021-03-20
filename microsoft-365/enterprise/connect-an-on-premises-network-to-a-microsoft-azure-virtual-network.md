---
title: Een on-premises netwerk verbinden met een virtueel Microsoft Azure-netwerk
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 81190961-5454-4a5c-8b0e-6ae75b9fb035
description: 'Overzicht: Informatie over het configureren van een cross-premises Azure-virtueel netwerk voor office-serverwerkbelastingen met een site-naar-site VPN-verbinding.'
ms.openlocfilehash: 00fd1c2246e9e9ac3eb55ca5ece9d84ecf49a1d3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907706"
---
# <a name="connect-an-on-premises-network-to-a-microsoft-azure-virtual-network"></a><span data-ttu-id="0e5a8-103">Een on-premises netwerk verbinden met een virtueel Microsoft Azure-netwerk</span><span class="sxs-lookup"><span data-stu-id="0e5a8-103">Connect an on-premises network to a Microsoft Azure virtual network</span></span>

<span data-ttu-id="0e5a8-104">Er is een cross-premises Azure-virtueel netwerk verbonden met uw on-premises netwerk, dat uw netwerk uitbreidt tot subnetten en virtuele machines die worden gehost in Azure-infrastructuurservices.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-104">A cross-premises Azure virtual network is connected to your on-premises network, extending your network to include subnets and virtual machines hosted in Azure infrastructure services.</span></span> <span data-ttu-id="0e5a8-105">Met deze verbinding hebben computers op uw on-premises netwerk rechtstreeks toegang tot virtuele machines in Azure en vice versa.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-105">This connection lets computers on your on-premises network to directly access virtual machines in Azure and vice versa.</span></span> 

<span data-ttu-id="0e5a8-106">Een adreslijstsynchronisatieserver die op een virtuele Azure-computer wordt uitgevoerd, moet bijvoorbeeld uw on-premises domeincontrollers opvragen voor wijzigingen in accounts en deze wijzigingen synchroniseren met uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-106">For example, a directory synchronization server running on an Azure virtual machine needs to query your on-premises domain controllers for changes to accounts and synchronize those changes with your Microsoft 365 subscription.</span></span> <span data-ttu-id="0e5a8-107">In dit artikel wordt beschreven hoe u een lokaal virtueel Azure-netwerk kunt instellen met een VPN-verbinding (Virtual Private Network) van site naar site die klaar is om Azure-virtuele machines te hosten.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-107">This article shows you how to set up a cross-premises Azure virtual network using a site-to-site virtual private network (VPN) connection that is ready to host Azure virtual machines.</span></span>

## <a name="configure-a-cross-premises-azure-virtual-network"></a><span data-ttu-id="0e5a8-108">Een cross-premises Azure Virtual Network configureren</span><span class="sxs-lookup"><span data-stu-id="0e5a8-108">Configure a cross-premises Azure virtual network</span></span>

<span data-ttu-id="0e5a8-109">Uw virtuele machines in Azure hoeven niet te worden geïsoleerd van uw on-premises omgeving.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-109">Your virtual machines in Azure don't have to be isolated from your on-premises environment.</span></span> <span data-ttu-id="0e5a8-110">Als u virtuele Azure-machines wilt verbinden met uw on-premises netwerkbronnen, moet u een lokaal virtueel Azure-netwerk configureren.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-110">To connect Azure virtual machines to your on-premises network resources, you must configure a cross-premises Azure virtual network.</span></span> <span data-ttu-id="0e5a8-111">In het volgende diagram ziet u de vereiste onderdelen voor het implementeren van een cross-premises Azure-virtueel netwerk met een virtuele computer in Azure.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-111">The following diagram shows the required components to deploy a cross-premises Azure virtual network with a virtual machine in Azure.</span></span>
  
![On-premises netwerk dat is verbonden met Microsoft Azure via een SITE-naar-site VPN-verbinding](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
 
<span data-ttu-id="0e5a8-113">In het diagram zijn er twee netwerken verbonden via een site-naar-site VPN-verbinding: het on-premises netwerk en het virtuele Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-113">In the diagram, there are two networks connected by a site-to-site VPN connection: the on-premises network and the Azure virtual network.</span></span> <span data-ttu-id="0e5a8-114">De SITE-naar-site VPN-verbinding is:</span><span class="sxs-lookup"><span data-stu-id="0e5a8-114">The site-to-site VPN connection is:</span></span>

- <span data-ttu-id="0e5a8-115">Tussen twee eindpunten die adresseerbaar zijn en zich bevinden op het openbare internet.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-115">Between two endpoints that are addressable and located on the public Internet.</span></span>
- <span data-ttu-id="0e5a8-116">Beëindigd door een VPN-apparaat op het on-premises netwerk en een Azure VPN-gateway op het virtuele Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-116">Terminated by a VPN device on the on-premises network and an Azure VPN gateway on the Azure virtual network.</span></span>

<span data-ttu-id="0e5a8-117">Het virtuele Azure-netwerk host virtuele machines.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-117">The Azure virtual network hosts virtual machines.</span></span> <span data-ttu-id="0e5a8-118">Netwerkverkeer dat afkomstig is van virtuele machines op het virtuele Azure-netwerk, wordt doorgestuurd naar de VPN-gateway, die vervolgens het verkeer via de SITE-naar-site VPN-verbinding doorgestuurd naar het VPN-apparaat op het on-premises netwerk.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-118">Network traffic originating from virtual machines on the Azure virtual network gets forwarded to the VPN gateway, which then forwards the traffic across the site-to-site VPN connection to the VPN device on the on-premises network.</span></span> <span data-ttu-id="0e5a8-119">De routeringsinfrastructuur van het on-premises netwerk wordt vervolgens doorgestuurd naar de bestemming.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-119">The routing infrastructure of the on-premises network then forwards the traffic to its destination.</span></span>

>[!Note]
><span data-ttu-id="0e5a8-120">U kunt ook [ExpressRoute](https://azure.microsoft.com/services/expressroute/)gebruiken, een directe verbinding tussen uw organisatie en het netwerk van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-120">You can also use [ExpressRoute](https://azure.microsoft.com/services/expressroute/), which is a direct connection between your organization and Microsoft's network.</span></span> <span data-ttu-id="0e5a8-121">Verkeer via ExpressRoute gaat niet via het openbare internet.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-121">Traffic over ExpressRoute does not travel over the public Internet.</span></span> <span data-ttu-id="0e5a8-122">In dit artikel wordt het gebruik van ExpressRoute niet beschreven.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-122">This article does not describe the use of ExpressRoute.</span></span>
>
  
<span data-ttu-id="0e5a8-123">Als u de VPN-verbinding wilt instellen tussen uw virtuele Azure-netwerk en uw on-premises netwerk, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="0e5a8-123">To set up the VPN connection between your Azure virtual network and your on-premises network, follow these steps:</span></span> 
  
1. <span data-ttu-id="0e5a8-124">**On-premises:** Definieer en maak een on-premises netwerkroute voor de adresruimte van het virtuele Azure-netwerk die naar uw on-premises VPN-apparaat wijst.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-124">**On-premises:** Define and create an on-premises network route for the address space of the Azure virtual network that points to your on-premises VPN device.</span></span>
    
2. <span data-ttu-id="0e5a8-125">**Microsoft Azure:** Maak een virtueel Azure-netwerk met een SITE-naar-site VPN-verbinding.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-125">**Microsoft Azure:** Create an Azure virtual network with a site-to-site VPN connection.</span></span> 
    
3. <span data-ttu-id="0e5a8-126">**On-premises:** Configureer uw on-premises hardware- of software-VPN-apparaat om de VPN-verbinding te beëindigen, die gebruikmaakt van internetprotocolbeveiliging (IPsec).</span><span class="sxs-lookup"><span data-stu-id="0e5a8-126">**On premises:** Configure your on-premises hardware or software VPN device to terminate the VPN connection, which uses Internet Protocol security (IPsec).</span></span>
    
<span data-ttu-id="0e5a8-127">Nadat u de SITE-to-site VPN-verbinding hebt gemaakt, voegt u Azure-virtuele machines toe aan de subnetten van het virtuele netwerk.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-127">After you establish the site-to-site VPN connection, you add Azure virtual machines to the subnets of the virtual network.</span></span>
  
## <a name="plan-your-azure-virtual-network"></a><span data-ttu-id="0e5a8-128">Uw Virtuele Azure-netwerk plannen</span><span class="sxs-lookup"><span data-stu-id="0e5a8-128">Plan your Azure virtual network</span></span>
<a name="PlanningVirtual"></a>

### <a name="prerequisites"></a><span data-ttu-id="0e5a8-129">Vereisten</span><span class="sxs-lookup"><span data-stu-id="0e5a8-129">Prerequisites</span></span>
<a name="Prerequisites"></a>

- <span data-ttu-id="0e5a8-130">Een Azure-abonnement.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-130">An Azure subscription.</span></span> <span data-ttu-id="0e5a8-131">Ga naar de pagina Azure kopen voor informatie over [Azure-abonnementen.](https://azure.microsoft.com/pricing/purchase-options/)</span><span class="sxs-lookup"><span data-stu-id="0e5a8-131">For information about Azure subscriptions, go to the [How To Buy Azure page](https://azure.microsoft.com/pricing/purchase-options/).</span></span>
    
- <span data-ttu-id="0e5a8-132">Een beschikbare privé-IPv4-adresruimte om toe te wijzen aan het virtuele netwerk en de subnetten, met voldoende ruimte voor groei om het aantal virtuele machines te kunnen gebruiken dat nu en in de toekomst nodig is.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-132">An available private IPv4 address space to assign to the virtual network and its subnets, with sufficient room for growth to accommodate the number of virtual machines needed now and in the future.</span></span>
    
- <span data-ttu-id="0e5a8-133">Een beschikbaar VPN-apparaat in uw on-premises netwerk om de SITE-to-site VPN-verbinding te beëindigen die de vereisten voor IPsec ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-133">An available VPN device in your on-premises network to terminate the site-to-site VPN connection that supports the requirements for IPsec.</span></span> <span data-ttu-id="0e5a8-134">Zie Over VPN-apparaten voor [virtuele netwerkverbindingen van site naar site voor meer informatie.](/azure/vpn-gateway/vpn-gateway-about-vpn-devices)</span><span class="sxs-lookup"><span data-stu-id="0e5a8-134">For more information, see [About VPN devices for site-to-site virtual network connections](/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
    
- <span data-ttu-id="0e5a8-135">Wijzigingen in uw routeringsinfrastructuur, zodat verkeer dat wordt doorgestuurd naar de adresruimte van het virtuele Azure-netwerk, wordt doorgestuurd naar het VPN-apparaat dat de SITE-to-site VPN-verbinding host.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-135">Changes to your routing infrastructure so that traffic routed to the address space of the Azure virtual network gets forwarded to the VPN device that hosts the site-to-site VPN connection.</span></span>
    
- <span data-ttu-id="0e5a8-136">Een webproxy die computers biedt die zijn verbonden met het on-premises netwerk en de virtuele azure-netwerktoegang tot internet.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-136">A web proxy that gives computers that are connected to the on-premises network and the Azure virtual network access to the Internet.</span></span>
    
### <a name="solution-architecture-design-assumptions"></a><span data-ttu-id="0e5a8-137">Ontwerp-aannames voor oplossingsarchitectuur</span><span class="sxs-lookup"><span data-stu-id="0e5a8-137">Solution architecture design assumptions</span></span>

<span data-ttu-id="0e5a8-138">In de volgende lijst worden de ontwerpopties weergegeven die zijn gemaakt voor deze oplossingsarchitectuur.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-138">The following list represents the design choices that have been made for this solution architecture.</span></span> 
  
- <span data-ttu-id="0e5a8-139">Deze oplossing maakt gebruik van één virtueel Azure-netwerk met een SITE-naar-site VPN-verbinding.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-139">This solution uses a single Azure virtual network with a site-to-site VPN connection.</span></span> <span data-ttu-id="0e5a8-140">Het virtuele Azure-netwerk host één subnet dat meerdere virtuele machines kan bevatten.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-140">The Azure virtual network hosts a single subnet that can contain multiple virtual machines.</span></span> 
    
- <span data-ttu-id="0e5a8-141">U kunt de routerings- en externe toegangsservice (RRAS) in Windows Server 2016 of Windows Server 2012 gebruiken om een VPN-verbinding tussen het on-premises netwerk en het virtuele Azure-netwerk tot stand te brengen.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-141">You can use the Routing and Remote Access Service (RRAS) in Windows Server 2016 or Windows Server 2012 to establish an IPsec site-to-site VPN connection between the on-premises network and the Azure virtual network.</span></span> <span data-ttu-id="0e5a8-142">U kunt ook andere opties gebruiken, zoals VPN-apparaten van Cisco of Juniper Networks.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-142">You can also use other options, such as Cisco or Juniper Networks VPN devices.</span></span>
    
- <span data-ttu-id="0e5a8-143">Het on-premises netwerk kan nog steeds netwerkservices hebben, zoals Ad DS (Active Directory Domain Services), Domain Name System (DNS) en proxyservers.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-143">The on-premises network might still have network services like Active Directory Domain Services (AD DS), Domain Name System (DNS), and proxy servers.</span></span> <span data-ttu-id="0e5a8-144">Afhankelijk van uw vereisten kan het handig zijn om een aantal van deze netwerkbronnen in het virtuele Azure-netwerk te plaatsen.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-144">Depending on your requirements, it might be beneficial to place some of these network resources in the Azure virtual network.</span></span>
    
<span data-ttu-id="0e5a8-145">Voor een bestaand virtueel Azure-netwerk met een of meer subnetten bepaalt u of er nog adresruimte is voor een extra subnet om uw benodigde virtuele machines te hosten, op basis van uw vereisten.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-145">For an existing Azure virtual network with one or more subnets, determine whether there is remaining address space for an additional subnet to host your needed virtual machines, based on your requirements.</span></span> <span data-ttu-id="0e5a8-146">Als u geen resterende adresruimte hebt voor een extra subnet, maakt u een extra virtueel netwerk met een eigen VPN-verbinding van site naar site.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-146">If you don't have remaining address space for an additional subnet, create an additional virtual network that has its own site-to-site VPN connection.</span></span>
  
### <a name="plan-the-routing-infrastructure-changes-for-the-azure-virtual-network"></a><span data-ttu-id="0e5a8-147">Wijzigingen in de routeringsinfrastructuur plannen voor het virtuele Azure-netwerk</span><span class="sxs-lookup"><span data-stu-id="0e5a8-147">Plan the routing infrastructure changes for the Azure virtual network</span></span>

<span data-ttu-id="0e5a8-148">U moet uw on-premises routeringsinfrastructuur zo configureren dat verkeer dat bestemd is voor de adresruimte van het virtuele Azure-netwerk, wordt doorgestuurd naar het on-premises VPN-apparaat dat de VPN-verbinding van de site-naar-site host.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-148">You must configure your on-premises routing infrastructure to forward traffic destined for the address space of the Azure virtual network to the on-premises VPN device that is hosting the site-to-site VPN connection.</span></span>
  
<span data-ttu-id="0e5a8-149">De exacte methode voor het bijwerken van uw routeringsinfrastructuur is afhankelijk van de manier waarop u routeringsgegevens beheert:</span><span class="sxs-lookup"><span data-stu-id="0e5a8-149">The exact method of updating your routing infrastructure depends on how you manage routing information, which can be:</span></span>
  
- <span data-ttu-id="0e5a8-150">Routeringstabelupdates op basis van handmatige configuratie.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-150">Routing table updates based on manual configuration.</span></span>
    
- <span data-ttu-id="0e5a8-151">Routeringstabelupdates op basis van routeringsprotocollen, zoals Routing Information Protocol (RIP) of Open Shortest Path First (OSPF).</span><span class="sxs-lookup"><span data-stu-id="0e5a8-151">Routing table updates based on routing protocols, such as Routing Information Protocol (RIP) or Open Shortest Path First (OSPF).</span></span>
    
<span data-ttu-id="0e5a8-152">Neem contact op met uw routeringsspecialist om ervoor te zorgen dat verkeer dat bestemd is voor het virtuele Azure-netwerk, wordt doorgestuurd naar het on-premises VPN-apparaat.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-152">Consult with your routing specialist to make sure that traffic destined for the Azure virtual network is forwarded to the on-premises VPN device.</span></span>
  
### <a name="plan-for-firewall-rules-for-traffic-to-and-from-the-on-premises-vpn-device"></a><span data-ttu-id="0e5a8-153">Firewallregels plannen voor verkeer van en naar het on-premises VPN-apparaat</span><span class="sxs-lookup"><span data-stu-id="0e5a8-153">Plan for firewall rules for traffic to and from the on-premises VPN device</span></span>

<span data-ttu-id="0e5a8-154">Als uw VPN-apparaat zich op een perimeternetwerk met een firewall tussen het perimeternetwerk en internet heeft, moet u mogelijk de firewall configureren voor de volgende regels om de VPN-verbinding van site-naar-site toe te staan.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-154">If your VPN device is on a perimeter network that has a firewall between the perimeter network and the Internet, you might have to configure the firewall for the following rules to allow the site-to-site VPN connection.</span></span>
  
- <span data-ttu-id="0e5a8-155">Verkeer naar het VPN-apparaat (binnenkomend vanaf internet):</span><span class="sxs-lookup"><span data-stu-id="0e5a8-155">Traffic to the VPN device (incoming from the Internet):</span></span>
    
  - <span data-ttu-id="0e5a8-156">Doel-IP-adres van het VPN-apparaat en IP-protocol 50</span><span class="sxs-lookup"><span data-stu-id="0e5a8-156">Destination IP address of the VPN device and IP protocol 50</span></span>
    
  - <span data-ttu-id="0e5a8-157">Doel-IP-adres van het VPN-apparaat en UDP-doelpoort 500</span><span class="sxs-lookup"><span data-stu-id="0e5a8-157">Destination IP address of the VPN device and UDP destination port 500</span></span>
    
  - <span data-ttu-id="0e5a8-158">Doel-IP-adres van het VPN-apparaat en UDP-doelpoort 4500</span><span class="sxs-lookup"><span data-stu-id="0e5a8-158">Destination IP address of the VPN device and UDP destination port 4500</span></span>
    
- <span data-ttu-id="0e5a8-159">Verkeer vanaf het VPN-apparaat (uitgaande naar internet):</span><span class="sxs-lookup"><span data-stu-id="0e5a8-159">Traffic from the VPN device (outgoing to the Internet):</span></span>
    
  - <span data-ttu-id="0e5a8-160">Bron-IP-adres van het VPN-apparaat en IP-protocol 50</span><span class="sxs-lookup"><span data-stu-id="0e5a8-160">Source IP address of the VPN device and IP protocol 50</span></span>
    
  - <span data-ttu-id="0e5a8-161">Bron-IP-adres van het VPN-apparaat en UDP-bronpoort 500</span><span class="sxs-lookup"><span data-stu-id="0e5a8-161">Source IP address of the VPN device and UDP source port 500</span></span>
    
  - <span data-ttu-id="0e5a8-162">Bron-IP-adres van het VPN-apparaat en UDP-bronpoort 4500</span><span class="sxs-lookup"><span data-stu-id="0e5a8-162">Source IP address of the VPN device and UDP source port 4500</span></span>
    
### <a name="plan-for-the-private-ip-address-space-of-the-azure-virtual-network"></a><span data-ttu-id="0e5a8-163">Plannen voor de privé-IP-adresruimte van het virtuele Azure-netwerk</span><span class="sxs-lookup"><span data-stu-id="0e5a8-163">Plan for the private IP address space of the Azure virtual network</span></span>

<span data-ttu-id="0e5a8-164">De privé-IP-adresruimte van het virtuele Azure-netwerk moet geschikt zijn voor adressen die door Azure worden gebruikt om het virtuele netwerk te hosten en met ten minste één subnet dat voldoende adressen heeft voor uw Azure-virtuele machines.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-164">The private IP address space of the Azure virtual network must be able to accommodate addresses used by Azure to host the virtual network and with at least one subnet that has enough addresses for your Azure virtual machines.</span></span>
  
<span data-ttu-id="0e5a8-165">Als u het aantal adressen wilt bepalen dat nodig is voor het subnet, telt u het aantal virtuele machines dat u nu nodig hebt, schat u de toekomstige groei in en gebruikt u vervolgens de volgende tabel om de grootte van het subnet te bepalen.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-165">To determine the number of addresses needed for the subnet, count the number of virtual machines that you need now, estimate for future growth, and then use the following table to determine the size of the subnet.</span></span>
  
|<span data-ttu-id="0e5a8-166">**Aantal virtuele machines dat nodig is**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-166">**Number of virtual machines needed**</span></span>|<span data-ttu-id="0e5a8-167">**Aantal hostbits nodig**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-167">**Number of host bits needed**</span></span>|<span data-ttu-id="0e5a8-168">**Grootte van het subnet**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-168">**Size of the subnet**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e5a8-169">1-3</span><span class="sxs-lookup"><span data-stu-id="0e5a8-169">1-3</span></span>  <br/> |<span data-ttu-id="0e5a8-170">3</span><span class="sxs-lookup"><span data-stu-id="0e5a8-170">3</span></span>  <br/> |<span data-ttu-id="0e5a8-171">/29</span><span class="sxs-lookup"><span data-stu-id="0e5a8-171">/29</span></span>  <br/> |
|<span data-ttu-id="0e5a8-172">4-11</span><span class="sxs-lookup"><span data-stu-id="0e5a8-172">4-11</span></span>  <br/> |<span data-ttu-id="0e5a8-173">4</span><span class="sxs-lookup"><span data-stu-id="0e5a8-173">4</span></span>  <br/> |<span data-ttu-id="0e5a8-174">/28</span><span class="sxs-lookup"><span data-stu-id="0e5a8-174">/28</span></span>  <br/> |
|<span data-ttu-id="0e5a8-175">12-27</span><span class="sxs-lookup"><span data-stu-id="0e5a8-175">12-27</span></span>  <br/> |<span data-ttu-id="0e5a8-176">5</span><span class="sxs-lookup"><span data-stu-id="0e5a8-176">5</span></span>  <br/> |<span data-ttu-id="0e5a8-177">/27</span><span class="sxs-lookup"><span data-stu-id="0e5a8-177">/27</span></span>  <br/> |
|<span data-ttu-id="0e5a8-178">28-59</span><span class="sxs-lookup"><span data-stu-id="0e5a8-178">28-59</span></span>  <br/> |<span data-ttu-id="0e5a8-179">6</span><span class="sxs-lookup"><span data-stu-id="0e5a8-179">6</span></span>  <br/> |<span data-ttu-id="0e5a8-180">/26</span><span class="sxs-lookup"><span data-stu-id="0e5a8-180">/26</span></span>  <br/> |
|<span data-ttu-id="0e5a8-181">60-123</span><span class="sxs-lookup"><span data-stu-id="0e5a8-181">60-123</span></span>  <br/> |<span data-ttu-id="0e5a8-182">7</span><span class="sxs-lookup"><span data-stu-id="0e5a8-182">7</span></span>  <br/> |<span data-ttu-id="0e5a8-183">/25</span><span class="sxs-lookup"><span data-stu-id="0e5a8-183">/25</span></span>  <br/> |
   
### <a name="planning-worksheet-for-configuring-your-azure-virtual-network"></a><span data-ttu-id="0e5a8-184">Werkblad plannen voor het configureren van uw Virtuele Azure-netwerk</span><span class="sxs-lookup"><span data-stu-id="0e5a8-184">Planning worksheet for configuring your Azure virtual network</span></span>
<span data-ttu-id="0e5a8-185"><a name="worksheet"> </a></span><span class="sxs-lookup"><span data-stu-id="0e5a8-185"><a name="worksheet"> </a></span></span>

<span data-ttu-id="0e5a8-186">Voordat u een virtueel Azure-netwerk maakt om virtuele machines te hosten, moet u de instellingen bepalen die nodig zijn in de volgende tabellen.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-186">Before you create an Azure virtual network to host virtual machines, you must determine the settings needed in the following tables.</span></span>
  
<span data-ttu-id="0e5a8-187">Vul tabel V in voor de instellingen van het virtuele netwerk.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-187">For the settings of the virtual network, fill in Table V.</span></span>
  
 <span data-ttu-id="0e5a8-188">**Tabel V: Configuratie van een virtueel netwerk met een cross-premises locatie**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-188">**Table V: Cross-premises virtual network configuration**</span></span>
  
|<span data-ttu-id="0e5a8-189">**Item**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-189">**Item**</span></span>|<span data-ttu-id="0e5a8-190">**Configuratie-element**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-190">**Configuration element**</span></span>|<span data-ttu-id="0e5a8-191">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-191">**Description**</span></span>|<span data-ttu-id="0e5a8-192">**Value**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-192">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0e5a8-193">1.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-193">1.</span></span>  <br/> |<span data-ttu-id="0e5a8-194">Naam van virtueel netwerk</span><span class="sxs-lookup"><span data-stu-id="0e5a8-194">Virtual network name</span></span>  <br/> |<span data-ttu-id="0e5a8-195">Een naam die u wilt toewijzen aan het virtuele Azure-netwerk (bijvoorbeeld DirSyncNet).</span><span class="sxs-lookup"><span data-stu-id="0e5a8-195">A name to assign to the Azure virtual network (example DirSyncNet).</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png) |
|<span data-ttu-id="0e5a8-197">2.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-197">2.</span></span>  <br/> |<span data-ttu-id="0e5a8-198">Virtuele netwerklocatie</span><span class="sxs-lookup"><span data-stu-id="0e5a8-198">Virtual network location</span></span>  <br/> |<span data-ttu-id="0e5a8-199">Het Azure-datacenter dat het virtuele netwerk (zoals West-VS) zal bevatten.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-199">The Azure datacenter that will contain the virtual network (such as West US).</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="0e5a8-201">3.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-201">3.</span></span>  <br/> |<span data-ttu-id="0e5a8-202">IP-adres VPN-apparaat</span><span class="sxs-lookup"><span data-stu-id="0e5a8-202">VPN device IP address</span></span>  <br/> |<span data-ttu-id="0e5a8-203">Het openbare IPv4-adres van de interface van uw VPN-apparaat op internet.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-203">The public IPv4 address of your VPN device's interface on the Internet.</span></span> <span data-ttu-id="0e5a8-204">Werk samen met uw IT-afdeling om dit adres te bepalen.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-204">Work with your IT department to determine this address.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="0e5a8-206">4.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-206">4.</span></span>  <br/> |<span data-ttu-id="0e5a8-207">Virtuele netwerkadresruimte</span><span class="sxs-lookup"><span data-stu-id="0e5a8-207">Virtual network address space</span></span>  <br/> |<span data-ttu-id="0e5a8-208">De adresruimte (gedefinieerd in één privéadres voorvoegsel) voor het virtuele netwerk.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-208">The address space (defined in a single private address prefix) for the virtual network.</span></span> <span data-ttu-id="0e5a8-209">Werk samen met uw IT-afdeling om deze adresruimte te bepalen.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-209">Work with your IT department to determine this address space.</span></span> <span data-ttu-id="0e5a8-210">De adresruimte moet de indeling Classless Interdomain Routing (CIDR) hebben, ook wel netwerkprefix-indeling genoemd.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-210">The address space should be in Classless Interdomain Routing (CIDR) format, also known as network prefix format.</span></span> <span data-ttu-id="0e5a8-211">Een voorbeeld is 10.24.64.0/20.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-211">An example is 10.24.64.0/20.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png) <br/> |
|<span data-ttu-id="0e5a8-213">5.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-213">5.</span></span>  <br/> |<span data-ttu-id="0e5a8-214">Gedeelde IPsec-sleutel</span><span class="sxs-lookup"><span data-stu-id="0e5a8-214">IPsec shared key</span></span>  <br/> |<span data-ttu-id="0e5a8-215">Een willekeurige, alfanumerieke tekenreeks van 32 tekens die wordt gebruikt om beide zijden van de SITE-naar-site VPN-verbinding te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-215">A 32-character random, alphanumeric string that will be used to authenticate both sides of the site-to-site VPN connection.</span></span> <span data-ttu-id="0e5a8-216">Werk samen met uw IT- of beveiligingsafdeling om deze sleutelwaarde te bepalen en bewaar deze vervolgens op een veilige locatie.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-216">Work with your IT or security department to determine this key value and then store it in a secure location.</span></span> <span data-ttu-id="0e5a8-217">Zie Een willekeurige tekenreeks maken voor een vooraf gedeelde [IPsec-toets.](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx)</span><span class="sxs-lookup"><span data-stu-id="0e5a8-217">Alternately, see [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png) <br/> |
   
<span data-ttu-id="0e5a8-219">Vul tabel S in voor de subnetten van deze oplossing.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-219">Fill in Table S for the subnets of this solution.</span></span>
  
- <span data-ttu-id="0e5a8-220">Bepaal voor het eerste subnet een 28-bits adresruimte (met een lengte van /28) voor het Azure Gateway-subnet.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-220">For the first subnet, determine a 28-bit address space (with a /28 prefix length) for the Azure gateway subnet.</span></span> <span data-ttu-id="0e5a8-221">Zie [De ruimte voor het gateway-subnet voor virtuele Azure-netwerken](/archive/blogs/solutions_advisory_board/calculating-the-gateway-subnet-address-space-for-azure-virtual-networks) berekenen voor informatie over het bepalen van deze adresruimte.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-221">See [Calculating the gateway subnet address space for Azure virtual networks](/archive/blogs/solutions_advisory_board/calculating-the-gateway-subnet-address-space-for-azure-virtual-networks) for information about how to determine this address space.</span></span>
    
- <span data-ttu-id="0e5a8-222">Geef voor het tweede subnet een vriendelijke naam op, één IP-adresruimte op basis van de virtuele netwerkadresruimte en een beschrijvend doel.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-222">For the second subnet, specify a friendly name, a single IP address space based on the virtual network address space, and a descriptive purpose.</span></span>
    
<span data-ttu-id="0e5a8-223">Werk samen met uw IT-afdeling om deze adresruimten te bepalen vanuit de virtuele netwerkadresruimte.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-223">Work with your IT department to determine these address spaces from the virtual network address space.</span></span> <span data-ttu-id="0e5a8-224">Beide adressaties moeten cidr-indeling hebben.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-224">Both address spaces should be in CIDR format.</span></span>
  
 <span data-ttu-id="0e5a8-225">**Tabel S: Subnetten in het virtuele netwerk**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-225">**Table S: Subnets in the virtual network**</span></span>
  
|<span data-ttu-id="0e5a8-226">**Item**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-226">**Item**</span></span>|<span data-ttu-id="0e5a8-227">**Subnetnaam**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-227">**Subnet name**</span></span>|<span data-ttu-id="0e5a8-228">**Subnetadresruimte**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-228">**Subnet address space**</span></span>|<span data-ttu-id="0e5a8-229">**Doel**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-229">**Purpose**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0e5a8-230">1.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-230">1.</span></span>  <br/> |<span data-ttu-id="0e5a8-231">GatewaySubnet</span><span class="sxs-lookup"><span data-stu-id="0e5a8-231">GatewaySubnet</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="0e5a8-233">Het subnet dat door de Azure-gateway wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-233">The subnet used by the Azure gateway.</span></span>  <br/> |
|<span data-ttu-id="0e5a8-234">2.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-234">2.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
   
<span data-ttu-id="0e5a8-238">Voor de on-premises DNS-servers die u wilt gebruiken voor de virtuele machines in het virtuele netwerk, vult u Tabel D in. Geef elke DNS-server een vriendelijke naam en één IP-adres.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-238">For the on-premises DNS servers that you want the virtual machines in the virtual network to use, fill in Table D. Give each DNS server a friendly name and a single IP address.</span></span> <span data-ttu-id="0e5a8-239">Deze vriendelijke naam hoeft niet overeen te komen met de hostnaam of computernaam van de DNS-server.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-239">This friendly name does not need to match the host name or computer name of the DNS server.</span></span> <span data-ttu-id="0e5a8-240">Houd er rekening mee dat er twee lege items worden weergegeven, maar u kunt er meer toevoegen.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-240">Note that two blank entries are listed, but you can add more.</span></span> <span data-ttu-id="0e5a8-241">Werk samen met uw IT-afdeling om deze lijst te bepalen.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-241">Work with your IT department to determine this list.</span></span>
  
 <span data-ttu-id="0e5a8-242">**Tabel D: On-premises DNS-servers**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-242">**Table D: On-premises DNS servers**</span></span>
  
|<span data-ttu-id="0e5a8-243">**Item**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-243">**Item**</span></span>|<span data-ttu-id="0e5a8-244">**NAAM VAN DNS-servervriendelijke naam**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-244">**DNS server friendly name**</span></span>|<span data-ttu-id="0e5a8-245">**IP-adres dns-server**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-245">**DNS server IP address**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e5a8-246">1.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-246">1.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="0e5a8-249">2.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-249">2.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
   
<span data-ttu-id="0e5a8-252">Als u pakketten van het virtuele Azure-netwerk wilt doorverplaatsen naar uw organisatienetwerk via de SITE-naar-site VPN-verbinding, moet u het virtuele netwerk configureren met een lokaal netwerk.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-252">To route packets from the Azure virtual network to your organization network across the site-to-site VPN connection, you must configure the virtual network with a local network.</span></span> <span data-ttu-id="0e5a8-253">Dit lokale netwerk heeft een lijst met adressaties (in CIDR-indeling) voor alle locaties in het on-premises netwerk van uw organisatie dat de virtuele machines in het virtuele netwerk moeten bereiken.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-253">This local network has a list of the address spaces (in CIDR format) for all of the locations on your organization's on-premises network that the virtual machines in the virtual network must reach.</span></span> <span data-ttu-id="0e5a8-254">Dit kunnen alle locaties in het on-premises netwerk of een subset zijn.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-254">This can be all of the locations on the on-premises network or a subset.</span></span> <span data-ttu-id="0e5a8-255">De lijst met adresruimten die uw lokale netwerk definiëren, moet uniek zijn en mag niet overlappen met de adresruimten die worden gebruikt voor dit virtuele netwerk of uw andere cross-premises virtuele netwerken.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-255">The list of address spaces that define your local network must be unique and must not overlap with the address spaces used for this virtual network or your other cross-premises virtual networks.</span></span>
  
<span data-ttu-id="0e5a8-256">Vul tabel L in voor de set lokale netwerkadressen. Houd er rekening mee dat er drie lege items worden weergegeven, maar dat u meestal meer nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-256">For the set of local network address spaces, fill in Table L. Note that three blank entries are listed but you will typically need more.</span></span> <span data-ttu-id="0e5a8-257">Werk samen met uw IT-afdeling om deze lijst te bepalen.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-257">Work with your IT department to determine this list.</span></span>
  
 <span data-ttu-id="0e5a8-258">**Tabel L: Adres voorvoegsels voor het lokale netwerk**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-258">**Table L: Address prefixes for the local network**</span></span>
  
|<span data-ttu-id="0e5a8-259">**Item**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-259">**Item**</span></span>|<span data-ttu-id="0e5a8-260">**Lokale netwerkadresruimte**</span><span class="sxs-lookup"><span data-stu-id="0e5a8-260">**Local network address space**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0e5a8-261">1.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-261">1.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="0e5a8-263">2.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-263">2.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="0e5a8-265">3.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-265">3.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
   
## <a name="deployment-roadmap"></a><span data-ttu-id="0e5a8-267">Routekaart voor implementatie</span><span class="sxs-lookup"><span data-stu-id="0e5a8-267">Deployment roadmap</span></span>
<span data-ttu-id="0e5a8-268"><a name="DeploymentRoadmap"> </a></span><span class="sxs-lookup"><span data-stu-id="0e5a8-268"><a name="DeploymentRoadmap"> </a></span></span>

<span data-ttu-id="0e5a8-269">Het maken van het virtuele cross-premises netwerk en het toevoegen van virtuele machines in Azure bestaat uit drie fasen:</span><span class="sxs-lookup"><span data-stu-id="0e5a8-269">Creating the cross-premises virtual network and adding virtual machines in Azure consists of three phases:</span></span>
  
- <span data-ttu-id="0e5a8-270">Fase 1: Uw on-premises netwerk voorbereiden.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-270">Phase 1: Prepare your on-premises network.</span></span>
    
- <span data-ttu-id="0e5a8-271">Fase 2: Het cross-premises virtuele netwerk maken in Azure.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-271">Phase 2: Create the cross-premises virtual network in Azure.</span></span>
    
- <span data-ttu-id="0e5a8-272">Fase 3 (optioneel): Virtuele machines toevoegen.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-272">Phase 3 (Optional): Add virtual machines.</span></span>
    
### <a name="phase-1-prepare-your-on-premises-network"></a><span data-ttu-id="0e5a8-273">Fase 1: uw on-premises netwerk voorbereiden</span><span class="sxs-lookup"><span data-stu-id="0e5a8-273">Phase 1: Prepare your on-premises network</span></span>
<a name="Phase1"></a>

<span data-ttu-id="0e5a8-274">U moet uw on-premises netwerk configureren met een route die naar het adres van het virtuele netwerk wijst en uiteindelijk verkeer levert dat bestemd is voor de router aan de rand van het on-premises netwerk.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-274">You must configure your on-premises network with a route that points to and ultimately delivers traffic destined for the address space of the virtual network to the router on the edge of the on-premises network.</span></span> <span data-ttu-id="0e5a8-275">Neem contact op met de netwerkbeheerder om te bepalen hoe u de route toevoegt aan de routeringsinfrastructuur van uw on-premises netwerk.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-275">Consult with your network administrator to determine how to add the route to the routing infrastructure of your on-premises network.</span></span>
  
<span data-ttu-id="0e5a8-276">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-276">Here is your resulting configuration.</span></span>
  
![Het on-premises netwerk moet een route hebben voor de adresruimte van het virtuele netwerk die naar het VPN-apparaat wijst.](../media/90bab36b-cb60-4ea5-81d5-4737b696d41c.png)
  
### <a name="phase-2-create-the-cross-premises-virtual-network-in-azure"></a><span data-ttu-id="0e5a8-278">Fase 2: het cross-premises virtuele netwerk maken in Azure</span><span class="sxs-lookup"><span data-stu-id="0e5a8-278">Phase 2: Create the cross-premises virtual network in Azure</span></span>
<a name="Phase2"></a>

<span data-ttu-id="0e5a8-279">Open eerst een Azure PowerShell-prompt.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-279">First, open an Azure PowerShell prompt.</span></span> <span data-ttu-id="0e5a8-280">Zie Aan de slag met [Azure PowerShell](/powershell/azure/get-started-azureps)als u Azure PowerShell niet hebt geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-280">If you have not installed Azure PowerShell, see [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span>

 
<span data-ttu-id="0e5a8-281">Meld u vervolgens aan bij uw Azure-account met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-281">Next, login to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="0e5a8-282">Haal de naam van uw abonnement op met de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-282">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort SubscriptionName | Select SubscriptionName
```

<span data-ttu-id="0e5a8-283">Stel uw Azure-abonnement in met deze opdrachten.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-283">Set your Azure subscription with these commands.</span></span> <span data-ttu-id="0e5a8-284">Vervang alles in de aanhalingstekens, inclusief de < en > tekens, door de juiste abonnementsnaam.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-284">Replace everything within the quotes, including the < and > characters, with the correct subscription name.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="0e5a8-285">Maak vervolgens een nieuwe resourcegroep voor uw virtuele netwerk.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-285">Next, create a new resource group for your virtual network.</span></span> <span data-ttu-id="0e5a8-286">Als u de naam van een unieke resourcegroep wilt bepalen, gebruikt u deze opdracht om uw bestaande resourcegroepen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-286">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="0e5a8-287">Maak uw nieuwe resourcegroep aan met deze opdrachten.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-287">Create your new resource group with these commands.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<Table V - Item 2 - Value column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="0e5a8-288">Vervolgens maakt u het virtuele Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-288">Next, you create the Azure virtual network.</span></span>
  
```powershell
# Fill in the variables from previous values and from Tables V, S, and D
$rgName="<name of your new resource group>"
$locName="<Azure location of your new resource group>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$gwSubnetPrefix="<Table S - Item 1 - Subnet address space column>"
$SubnetName="<Table S - Item 2 - Subnet name column>"
$SubnetPrefix="<Table S - Item 2 - Subnet address space column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the Azure virtual network and a network security group that allows incoming remote desktop connections to the subnet that is hosting virtual machines
$gatewaySubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnetPrefix
$vmSubnet=New-AzVirtualNetworkSubnetConfig -Name $SubnetName -AddressPrefix $SubnetPrefix
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gatewaySubnet,$vmSubnet -DNSServer $dnsServers
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name $SubnetName -ResourceGroupName $rgName -Location $locShortName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$nsg=Get-AzNetworkSecurityGroup -Name $SubnetName -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $SubnetName -AddressPrefix $SubnetPrefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="0e5a8-289">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-289">Here is your resulting configuration.</span></span>
  
![Het virtuele netwerk is nog niet verbonden met het on-premises netwerk.](../media/54a37782-a6cc-4d48-b38d-73e128b44a82.png)
  
<span data-ttu-id="0e5a8-291">Gebruik vervolgens deze opdrachten om de gateways te maken voor de SITE-naar-site VPN-verbinding.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-291">Next, use these commands to create the gateways for the site-to-site VPN connection.</span></span>
  
```powershell
# Fill in the variables from previous values and from Tables V and L
$vnetName="<Table V - Item 1 - Value column>"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -SubnetId $vnet.Subnets[0].Id
# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig
# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix
# Create the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway
```

<span data-ttu-id="0e5a8-292">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-292">Here is your resulting configuration.</span></span>
  
![Het virtuele netwerk heeft nu een gateway.](../media/82dd66b2-a4b7-48f6-a89b-cfdd94630980.png)
  
<span data-ttu-id="0e5a8-294">Configureer vervolgens uw on-premises VPN-apparaat om verbinding te maken met de Azure VPN-gateway.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-294">Next, configure your on-premises VPN device to connect to the Azure VPN gateway.</span></span> <span data-ttu-id="0e5a8-295">Zie Over VPN-apparaten voor [site-naar-site Azure Virtual Network-verbindingen voor meer informatie.](/azure/vpn-gateway/vpn-gateway-about-vpn-devices)</span><span class="sxs-lookup"><span data-stu-id="0e5a8-295">For more information, see [About VPN Devices for site-to-site Azure Virtual Network connections](/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
  
<span data-ttu-id="0e5a8-296">Als u uw VPN-apparaat wilt configureren, hebt u het volgende nodig:</span><span class="sxs-lookup"><span data-stu-id="0e5a8-296">To configure your VPN device, you will need the following:</span></span>
  
- <span data-ttu-id="0e5a8-297">Het openbare IPv4-adres van de Azure VPN-gateway voor uw virtuele netwerk.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-297">The public IPv4 address of the Azure VPN gateway for your virtual network.</span></span> <span data-ttu-id="0e5a8-298">Gebruik de **opdracht Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName** om dit adres weer te geven.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-298">Use the **Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName** command to display this address.</span></span>
    
- <span data-ttu-id="0e5a8-299">De vooraf gedeelde IPsec-sleutel voor de VPN-verbinding van site naar site (tabel V- item 5 - kolom Waarde).</span><span class="sxs-lookup"><span data-stu-id="0e5a8-299">The IPsec pre-shared key for the site-to-site VPN connection (Table V- Item 5 - Value column).</span></span>
    
<span data-ttu-id="0e5a8-300">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-300">Here is your resulting configuration.</span></span>
  
![Het virtuele netwerk is nu verbonden met het on-premises netwerk.](../media/6379c423-4f22-4453-941b-7ff32484a0a5.png)
  
### <a name="phase-3-optional-add-virtual-machines"></a><span data-ttu-id="0e5a8-302">Fase 3 (optioneel): Virtuele machines toevoegen</span><span class="sxs-lookup"><span data-stu-id="0e5a8-302">Phase 3 (Optional): Add virtual machines</span></span>

<span data-ttu-id="0e5a8-303">Maak de virtuele machines die u nodig hebt in Azure.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-303">Create the virtual machines you need in Azure.</span></span> <span data-ttu-id="0e5a8-304">Zie Een virtuele Windows-computer maken met [de Azure-portal](https://go.microsoft.com/fwlink/p/?LinkId=393098)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-304">For more information, see [Create a Windows virtual machine with the Azure portal](https://go.microsoft.com/fwlink/p/?LinkId=393098).</span></span>
  
<span data-ttu-id="0e5a8-305">Gebruik de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="0e5a8-305">Use the following settings:</span></span>
  
- <span data-ttu-id="0e5a8-306">Selecteer op **het** tabblad Basisbeginselen hetzelfde abonnement en dezelfde resourcegroep als uw virtuele netwerk.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-306">On the **Basics** tab, select the same subscription and resource group as your virtual network.</span></span> <span data-ttu-id="0e5a8-307">U hebt deze later nodig om u aan te melden bij de virtuele machine.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-307">You will need these later to sign in to the virtual machine.</span></span> <span data-ttu-id="0e5a8-308">Kies in **de sectie Exemplaardetails** de juiste virtuele machinegrootte.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-308">In the **Instance details** section, choose the appropriate virtual machine size.</span></span> <span data-ttu-id="0e5a8-309">Neem de gebruikersnaam en het wachtwoord van het beheerdersaccount op op een veilige locatie.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-309">Record the administrator account user name and password in a secure location.</span></span> 
    
- <span data-ttu-id="0e5a8-310">Selecteer op **het** tabblad Netwerken de naam van uw virtuele netwerk en het subnet voor het hosten van virtuele machines (niet het GatewaySubnet).</span><span class="sxs-lookup"><span data-stu-id="0e5a8-310">On the **Networking** tab, select the name of your virtual network and the subnet for hosting virtual machines (not the GatewaySubnet).</span></span> <span data-ttu-id="0e5a8-311">Laat alle andere instellingen op hun standaardwaarden staan.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-311">Leave all other settings at their default values.</span></span>
    
<span data-ttu-id="0e5a8-312">Controleer of uw virtuele computer DNS correct gebruikt door uw interne DNS te controleren om ervoor te zorgen dat adresrecords (A) voor u nieuwe virtuele machine zijn toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-312">Verify that your virtual machine is using DNS correctly by checking your internal DNS to ensure that Address (A) records were added for you new virtual machine.</span></span> <span data-ttu-id="0e5a8-313">Als u toegang wilt tot internet, moeten uw Azure-virtuele machines zijn geconfigureerd om de proxyserver van uw on-premises netwerk te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-313">To access the Internet, your Azure virtual machines must be configured to use your on-premises network's proxy server.</span></span> <span data-ttu-id="0e5a8-314">Neem contact op met de netwerkbeheerder voor aanvullende configuratiestappen om uit te voeren op de server.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-314">Contact your network administrator for additional configuration steps to perform on the server.</span></span>
  
<span data-ttu-id="0e5a8-315">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="0e5a8-315">Here is your resulting configuration.</span></span>
  
![Het virtuele netwerk host nu virtuele machines die toegankelijk zijn vanuit het on-premises netwerk.](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
  
## <a name="next-step"></a><span data-ttu-id="0e5a8-317">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="0e5a8-317">Next step</span></span>
  
[<span data-ttu-id="0e5a8-318">Microsoft 365 Directory-synchronisatie implementeren in Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="0e5a8-318">Deploy Microsoft 365 Directory Synchronization in Microsoft Azure</span></span>](deploy-microsoft-365-directory-synchronization-dirsync-in-microsoft-azure.md)