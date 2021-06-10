---
title: Federatieverificatie met hoge beschikbaarheid Fase 1 Azure configureren
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 91266aac-4d00-4b5f-b424-86a1a837792c
description: 'Overzicht: Configureer de Microsoft Azure infrastructuur om federatief hoge beschikbaarheid te hosten voor Microsoft 365.'
ms.openlocfilehash: 7f9a935648fedd2c6235c443f7398f97c0a06e06
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929106"
---
# <a name="high-availability-federated-authentication-phase-1-configure-azure"></a><span data-ttu-id="a561e-103">Federatief hoge beschikbaarheid fase 1: Azure configureren</span><span class="sxs-lookup"><span data-stu-id="a561e-103">High availability federated authentication Phase 1: Configure Azure</span></span>

<span data-ttu-id="a561e-104">In deze fase maakt u de resourcegroepen, virtuele netwerken (VNet) en beschikbaarheidssets in Azure die de virtuele machines hosten in fasen 2, 3 en 4.</span><span class="sxs-lookup"><span data-stu-id="a561e-104">In this phase, you create the resource groups, virtual network (VNet), and availability sets in Azure that will host the virtual machines in phases 2, 3, and 4.</span></span> <span data-ttu-id="a561e-105">U moet deze fase voltooien voordat u verder gaat [met fase 2: Domeincontrollers configureren.](high-availability-federated-authentication-phase-2-configure-domain-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="a561e-105">You must complete this phase before moving on to [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span></span> <span data-ttu-id="a561e-106">Zie [Federatieverificatie met hoge](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) beschikbaarheid implementeren voor Microsoft 365 in Azure voor alle fasen.</span><span class="sxs-lookup"><span data-stu-id="a561e-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
<span data-ttu-id="a561e-107">Azure moet zijn ingericht met deze basisonderdelen:</span><span class="sxs-lookup"><span data-stu-id="a561e-107">Azure must be provisioned with these basic components:</span></span>
  
- <span data-ttu-id="a561e-108">Resourcegroepen</span><span class="sxs-lookup"><span data-stu-id="a561e-108">Resource groups</span></span>
    
- <span data-ttu-id="a561e-109">Een cross-premises Azure Virtual Network (VNet) met subnetten voor het hosten van de Virtuele Azure-machines</span><span class="sxs-lookup"><span data-stu-id="a561e-109">A cross-premises Azure virtual network (VNet) with subnets for hosting the Azure virtual machines</span></span>
    
- <span data-ttu-id="a561e-110">Netwerkbeveiligingsgroepen voor het uitvoeren van subnetisolatie</span><span class="sxs-lookup"><span data-stu-id="a561e-110">Network security groups for performing subnet isolation</span></span>
    
- <span data-ttu-id="a561e-111">Beschikbaarheidssets</span><span class="sxs-lookup"><span data-stu-id="a561e-111">Availability sets</span></span>
    
## <a name="configure-azure-components"></a><span data-ttu-id="a561e-112">Azure-onderdelen configureren</span><span class="sxs-lookup"><span data-stu-id="a561e-112">Configure Azure components</span></span>

<span data-ttu-id="a561e-113">Voordat u Begint met het configureren van Azure-onderdelen, vult u de volgende tabellen in.</span><span class="sxs-lookup"><span data-stu-id="a561e-113">Before you begin configuring Azure components, fill in the following tables.</span></span> <span data-ttu-id="a561e-114">Als u wilt helpen bij de procedures voor het configureren van Azure, print u deze sectie af en noteert u de benodigde informatie of kopieert u deze sectie naar een document en vult u deze in.</span><span class="sxs-lookup"><span data-stu-id="a561e-114">To assist you in the procedures for configuring Azure, print this section and write down the needed information or copy this section to a document and fill it in.</span></span> <span data-ttu-id="a561e-115">Vul tabel V in voor de instellingen van het VNet.</span><span class="sxs-lookup"><span data-stu-id="a561e-115">For the settings of the VNet, fill in Table V.</span></span>
  
|<span data-ttu-id="a561e-116">**Item**</span><span class="sxs-lookup"><span data-stu-id="a561e-116">**Item**</span></span>|<span data-ttu-id="a561e-117">**Configuratie-instelling**</span><span class="sxs-lookup"><span data-stu-id="a561e-117">**Configuration setting**</span></span>|<span data-ttu-id="a561e-118">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="a561e-118">**Description**</span></span>|<span data-ttu-id="a561e-119">**Value**</span><span class="sxs-lookup"><span data-stu-id="a561e-119">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a561e-120">1.</span><span class="sxs-lookup"><span data-stu-id="a561e-120">1.</span></span>  <br/> |<span data-ttu-id="a561e-121">VNet-naam</span><span class="sxs-lookup"><span data-stu-id="a561e-121">VNet name</span></span>  <br/> |<span data-ttu-id="a561e-122">Een naam die u wilt toewijzen aan het VNet (bijvoorbeeld FedAuthNet).</span><span class="sxs-lookup"><span data-stu-id="a561e-122">A name to assign to the VNet (example FedAuthNet).</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-124">2.</span><span class="sxs-lookup"><span data-stu-id="a561e-124">2.</span></span>  <br/> |<span data-ttu-id="a561e-125">VNet-locatie</span><span class="sxs-lookup"><span data-stu-id="a561e-125">VNet location</span></span>  <br/> |<span data-ttu-id="a561e-126">Het regionale Azure-datacenter dat het virtuele netwerk zal bevatten.</span><span class="sxs-lookup"><span data-stu-id="a561e-126">The regional Azure datacenter that will contain the virtual network.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-128">3.</span><span class="sxs-lookup"><span data-stu-id="a561e-128">3.</span></span>  <br/> |<span data-ttu-id="a561e-129">IP-adres VPN-apparaat</span><span class="sxs-lookup"><span data-stu-id="a561e-129">VPN device IP address</span></span>  <br/> |<span data-ttu-id="a561e-130">Het openbare IPv4-adres van de interface van uw VPN-apparaat op internet.</span><span class="sxs-lookup"><span data-stu-id="a561e-130">The public IPv4 address of your VPN device's interface on the Internet.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-132">4.</span><span class="sxs-lookup"><span data-stu-id="a561e-132">4.</span></span>  <br/> |<span data-ttu-id="a561e-133">VNet-adresruimte</span><span class="sxs-lookup"><span data-stu-id="a561e-133">VNet address space</span></span>  <br/> |<span data-ttu-id="a561e-134">De adresruimte voor het virtuele netwerk.</span><span class="sxs-lookup"><span data-stu-id="a561e-134">The address space for the virtual network.</span></span> <span data-ttu-id="a561e-135">Werk samen met uw IT-afdeling om deze adresruimte te bepalen.</span><span class="sxs-lookup"><span data-stu-id="a561e-135">Work with your IT department to determine this address space.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-137">5.</span><span class="sxs-lookup"><span data-stu-id="a561e-137">5.</span></span>  <br/> |<span data-ttu-id="a561e-138">Gedeelde IPsec-sleutel</span><span class="sxs-lookup"><span data-stu-id="a561e-138">IPsec shared key</span></span>  <br/> |<span data-ttu-id="a561e-139">Een willekeurige, alfanumerieke tekenreeks van 32 tekens die wordt gebruikt om beide zijden van de SITE-naar-site VPN-verbinding te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="a561e-139">A 32-character random, alphanumeric string that will be used to authenticate both sides of the site-to-site VPN connection.</span></span> <span data-ttu-id="a561e-140">Werk samen met uw IT- of beveiligingsafdeling om deze sleutelwaarde te bepalen.</span><span class="sxs-lookup"><span data-stu-id="a561e-140">Work with your IT or security department to determine this key value.</span></span> <span data-ttu-id="a561e-141">Zie Een willekeurige tekenreeks maken voor een vooraf gedeelde [IPsec-toets.](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx)</span><span class="sxs-lookup"><span data-stu-id="a561e-141">Alternately, see [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="a561e-143">**Tabel V: Configuratie van een virtueel netwerk met een cross-premises locatie**</span><span class="sxs-lookup"><span data-stu-id="a561e-143">**Table V: Cross-premises virtual network configuration**</span></span>
  
<span data-ttu-id="a561e-144">Vul vervolgens tabel S in voor de subnetten van deze oplossing.</span><span class="sxs-lookup"><span data-stu-id="a561e-144">Next, fill in Table S for the subnets of this solution.</span></span> <span data-ttu-id="a561e-145">Alle adressaties moeten de indeling Classless Interdomain Routing (CIDR) hebben, ook wel bekend als netwerkprefixnotatie.</span><span class="sxs-lookup"><span data-stu-id="a561e-145">All address spaces should be in Classless Interdomain Routing (CIDR) format, also known as network prefix format.</span></span> <span data-ttu-id="a561e-146">Een voorbeeld is 10.24.64.0/20.</span><span class="sxs-lookup"><span data-stu-id="a561e-146">An example is 10.24.64.0/20.</span></span>
  
<span data-ttu-id="a561e-147">Geef voor de eerste drie subnetten een naam en één IP-adresruimte op op basis van de virtuele netwerkadresruimte.</span><span class="sxs-lookup"><span data-stu-id="a561e-147">For the first three subnets, specify a name and a single IP address space based on the virtual network address space.</span></span> <span data-ttu-id="a561e-148">Voor het gateway-subnet bepaalt u de 27-bits adresruimte (met een lengte van /27) voor het Azure Gateway-subnet met de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="a561e-148">For the gateway subnet, determine the 27-bit address space (with a /27 prefix length) for the Azure gateway subnet with the following:</span></span>
  
1. <span data-ttu-id="a561e-149">Stel de variabele bits in de adresruimte van het VNet in op 1, tot de bits die worden gebruikt door het gateway subnet en stel vervolgens de resterende bits in op 0.</span><span class="sxs-lookup"><span data-stu-id="a561e-149">Set the variable bits in the address space of the VNet to 1, up to the bits being used by the gateway subnet, then set the remaining bits to 0.</span></span>
    
2. <span data-ttu-id="a561e-150">Converteert de resulterende bits naar decimaal en druk deze uit als een adresruimte met de lengte van het voorvoegsel ingesteld op de grootte van het gateway-subnet.</span><span class="sxs-lookup"><span data-stu-id="a561e-150">Convert the resulting bits to decimal and express it as an address space with the prefix length set to the size of the gateway subnet.</span></span>
    
<span data-ttu-id="a561e-151">Zie [Adresruimteberekening voor Azure Gateway-subnetten](address-space-calculator-for-azure-gateway-subnets.md) voor een PowerShell-opdrachtblok en C# of Python-consoletoepassing die deze berekening voor u uitvoert.</span><span class="sxs-lookup"><span data-stu-id="a561e-151">See [Address space calculator for Azure gateway subnets](address-space-calculator-for-azure-gateway-subnets.md) for a PowerShell command block and C# or Python console application that performs this calculation for you.</span></span>
  
<span data-ttu-id="a561e-152">Werk samen met uw IT-afdeling om deze adresruimten te bepalen vanuit de virtuele netwerkadresruimte.</span><span class="sxs-lookup"><span data-stu-id="a561e-152">Work with your IT department to determine these address spaces from the virtual network address space.</span></span>
  
|<span data-ttu-id="a561e-153">**Item**</span><span class="sxs-lookup"><span data-stu-id="a561e-153">**Item**</span></span>|<span data-ttu-id="a561e-154">**Subnetnaam**</span><span class="sxs-lookup"><span data-stu-id="a561e-154">**Subnet name**</span></span>|<span data-ttu-id="a561e-155">**Subnetadresruimte**</span><span class="sxs-lookup"><span data-stu-id="a561e-155">**Subnet address space**</span></span>|<span data-ttu-id="a561e-156">**Doel**</span><span class="sxs-lookup"><span data-stu-id="a561e-156">**Purpose**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a561e-157">1.</span><span class="sxs-lookup"><span data-stu-id="a561e-157">1.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="a561e-160">Het subnet dat wordt gebruikt door de Ad DS-domeincontroller (Active Directory Domain Services) en virtuele adreslijstsynchronisatieserver virtuele machines (VM's).</span><span class="sxs-lookup"><span data-stu-id="a561e-160">The subnet used by the Active Directory Domain Services (AD DS) domain controller and directory synchronization server virtual machines (VMs).</span></span>  <br/> |
|<span data-ttu-id="a561e-161">2.</span><span class="sxs-lookup"><span data-stu-id="a561e-161">2.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="a561e-164">Het subnet dat wordt gebruikt door de AD FS-VM's.</span><span class="sxs-lookup"><span data-stu-id="a561e-164">The subnet used by the AD FS VMs.</span></span>  <br/> |
|<span data-ttu-id="a561e-165">3.</span><span class="sxs-lookup"><span data-stu-id="a561e-165">3.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="a561e-168">Het subnet dat wordt gebruikt door de proxy-VM's van de webtoepassing.</span><span class="sxs-lookup"><span data-stu-id="a561e-168">The subnet used by the web application proxy VMs.</span></span>  <br/> |
|<span data-ttu-id="a561e-169">4.</span><span class="sxs-lookup"><span data-stu-id="a561e-169">4.</span></span>  <br/> |<span data-ttu-id="a561e-170">GatewaySubnet</span><span class="sxs-lookup"><span data-stu-id="a561e-170">GatewaySubnet</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="a561e-172">Het subnet dat wordt gebruikt door de Azure Gateway VM's.</span><span class="sxs-lookup"><span data-stu-id="a561e-172">The subnet used by the Azure gateway VMs.</span></span>  <br/> |
   
 <span data-ttu-id="a561e-173">**Tabel S: Subnetten in het virtuele netwerk**</span><span class="sxs-lookup"><span data-stu-id="a561e-173">**Table S: Subnets in the virtual network**</span></span>
  
<span data-ttu-id="a561e-174">Vul vervolgens tabel I in voor de statische IP-adressen die zijn toegewezen aan virtuele machines en load balancer-exemplaren.</span><span class="sxs-lookup"><span data-stu-id="a561e-174">Next, fill in Table I for the static IP addresses assigned to virtual machines and load balancer instances.</span></span>
  
|<span data-ttu-id="a561e-175">**Item**</span><span class="sxs-lookup"><span data-stu-id="a561e-175">**Item**</span></span>|<span data-ttu-id="a561e-176">**Doel**</span><span class="sxs-lookup"><span data-stu-id="a561e-176">**Purpose**</span></span>|<span data-ttu-id="a561e-177">**IP-adres op het subnet**</span><span class="sxs-lookup"><span data-stu-id="a561e-177">**IP address on the subnet**</span></span>|<span data-ttu-id="a561e-178">**Value**</span><span class="sxs-lookup"><span data-stu-id="a561e-178">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a561e-179">1.</span><span class="sxs-lookup"><span data-stu-id="a561e-179">1.</span></span>  <br/> |<span data-ttu-id="a561e-180">Statisch IP-adres van de eerste domeincontroller</span><span class="sxs-lookup"><span data-stu-id="a561e-180">Static IP address of the first domain controller</span></span>  <br/> |<span data-ttu-id="a561e-181">Het vierde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 1 van tabel S.</span><span class="sxs-lookup"><span data-stu-id="a561e-181">The fourth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-183">2.</span><span class="sxs-lookup"><span data-stu-id="a561e-183">2.</span></span>  <br/> |<span data-ttu-id="a561e-184">Statisch IP-adres van de tweede domeincontroller</span><span class="sxs-lookup"><span data-stu-id="a561e-184">Static IP address of the second domain controller</span></span>  <br/> |<span data-ttu-id="a561e-185">Het vijfde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 1 van tabel S.</span><span class="sxs-lookup"><span data-stu-id="a561e-185">The fifth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-187">3.</span><span class="sxs-lookup"><span data-stu-id="a561e-187">3.</span></span>  <br/> |<span data-ttu-id="a561e-188">Statisch IP-adres van de adreslijstsynchronisatieserver</span><span class="sxs-lookup"><span data-stu-id="a561e-188">Static IP address of the directory synchronization server</span></span>  <br/> |<span data-ttu-id="a561e-189">Het zesde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 1 van tabel S.</span><span class="sxs-lookup"><span data-stu-id="a561e-189">The sixth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-191">4.</span><span class="sxs-lookup"><span data-stu-id="a561e-191">4.</span></span>  <br/> |<span data-ttu-id="a561e-192">Statisch IP-adres van de interne load balancer voor de AD FS-servers</span><span class="sxs-lookup"><span data-stu-id="a561e-192">Static IP address of the internal load balancer for the AD FS servers</span></span>  <br/> |<span data-ttu-id="a561e-193">Het vierde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 2 van tabel S.</span><span class="sxs-lookup"><span data-stu-id="a561e-193">The fourth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-195">5.</span><span class="sxs-lookup"><span data-stu-id="a561e-195">5.</span></span>  <br/> |<span data-ttu-id="a561e-196">Statisch IP-adres van de eerste AD FS-server</span><span class="sxs-lookup"><span data-stu-id="a561e-196">Static IP address of the first AD FS server</span></span>  <br/> |<span data-ttu-id="a561e-197">Het vijfde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 2 van tabel S.</span><span class="sxs-lookup"><span data-stu-id="a561e-197">The fifth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-199">6.</span><span class="sxs-lookup"><span data-stu-id="a561e-199">6.</span></span>  <br/> |<span data-ttu-id="a561e-200">Statisch IP-adres van de tweede AD FS-server</span><span class="sxs-lookup"><span data-stu-id="a561e-200">Static IP address of the second AD FS server</span></span>  <br/> |<span data-ttu-id="a561e-201">Het zesde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 2 van tabel S.</span><span class="sxs-lookup"><span data-stu-id="a561e-201">The sixth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-203">7.</span><span class="sxs-lookup"><span data-stu-id="a561e-203">7.</span></span>  <br/> |<span data-ttu-id="a561e-204">Statisch IP-adres van de eerste proxyserver voor webtoepassing</span><span class="sxs-lookup"><span data-stu-id="a561e-204">Static IP address of the first web application proxy server</span></span>  <br/> |<span data-ttu-id="a561e-205">Het vierde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 3 van tabel S.</span><span class="sxs-lookup"><span data-stu-id="a561e-205">The fourth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-207">8.</span><span class="sxs-lookup"><span data-stu-id="a561e-207">8.</span></span>  <br/> |<span data-ttu-id="a561e-208">Statisch IP-adres van de tweede proxyserver voor webtoepassing</span><span class="sxs-lookup"><span data-stu-id="a561e-208">Static IP address of the second web application proxy server</span></span>  <br/> |<span data-ttu-id="a561e-209">Het vijfde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 3 van tabel S.</span><span class="sxs-lookup"><span data-stu-id="a561e-209">The fifth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="a561e-211">**Tabel I: Statische IP-adressen in het virtuele netwerk**</span><span class="sxs-lookup"><span data-stu-id="a561e-211">**Table I: Static IP addresses in the virtual network**</span></span>
  
<span data-ttu-id="a561e-212">Voor twee DNS-servers (Domain Name System) in uw on-premises netwerk die u wilt gebruiken bij het instellen van de domeincontrollers in uw virtuele netwerk, vult u tabel D in. Werk samen met uw IT-afdeling om deze lijst te bepalen.</span><span class="sxs-lookup"><span data-stu-id="a561e-212">For two Domain Name System (DNS) servers in your on-premises network that you want to use when initially setting up the domain controllers in your virtual network, fill in Table D. Work with your IT department to determine this list.</span></span>
  
|<span data-ttu-id="a561e-213">**Item**</span><span class="sxs-lookup"><span data-stu-id="a561e-213">**Item**</span></span>|<span data-ttu-id="a561e-214">**NAAM VAN DNS-servervriendelijke naam**</span><span class="sxs-lookup"><span data-stu-id="a561e-214">**DNS server friendly name**</span></span>|<span data-ttu-id="a561e-215">**IP-adres dns-server**</span><span class="sxs-lookup"><span data-stu-id="a561e-215">**DNS server IP address**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a561e-216">1.</span><span class="sxs-lookup"><span data-stu-id="a561e-216">1.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-219">2.</span><span class="sxs-lookup"><span data-stu-id="a561e-219">2.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="a561e-222">**Tabel D: On-premises DNS-servers**</span><span class="sxs-lookup"><span data-stu-id="a561e-222">**Table D: On-premises DNS servers**</span></span>
  
<span data-ttu-id="a561e-223">Als u pakketten van het cross-premises netwerk naar uw organisatienetwerk wilt doorverplaatsen via de SITE-naar-site VPN-verbinding, moet u het virtuele netwerk configureren met een lokaal netwerk met een lijst met de adressaties (in CIDR-notatie) voor alle bereikbare locaties in het on-premises netwerk van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a561e-223">To route packets from the cross-premises network to your organization network across the site-to-site VPN connection, you must configure the virtual network with a local network that has a list of the address spaces (in CIDR notation) for all of the reachable locations on your organization's on-premises network.</span></span> <span data-ttu-id="a561e-224">De lijst met adresruimten die uw lokale netwerk definiëren, moet uniek zijn en mag niet overlappen met de adresruimte die wordt gebruikt voor andere virtuele netwerken of andere lokale netwerken.</span><span class="sxs-lookup"><span data-stu-id="a561e-224">The list of address spaces that define your local network must be unique and must not overlap with the address space used for other virtual networks or other local networks.</span></span>
  
<span data-ttu-id="a561e-225">Vul tabel L in voor de set lokale netwerkadressen. Houd er rekening mee dat er drie lege items worden weergegeven, maar dat u meestal meer nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="a561e-225">For the set of local network address spaces, fill in Table L. Note that three blank entries are listed but you will typically need more.</span></span> <span data-ttu-id="a561e-226">Werk samen met uw IT-afdeling om deze lijst met adressruimten te bepalen.</span><span class="sxs-lookup"><span data-stu-id="a561e-226">Work with your IT department to determine this list of address spaces.</span></span>
  
|<span data-ttu-id="a561e-227">**Item**</span><span class="sxs-lookup"><span data-stu-id="a561e-227">**Item**</span></span>|<span data-ttu-id="a561e-228">**Lokale netwerkadresruimte**</span><span class="sxs-lookup"><span data-stu-id="a561e-228">**Local network address space**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a561e-229">1.</span><span class="sxs-lookup"><span data-stu-id="a561e-229">1.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-231">2.</span><span class="sxs-lookup"><span data-stu-id="a561e-231">2.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-233">3.</span><span class="sxs-lookup"><span data-stu-id="a561e-233">3.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="a561e-235">**Tabel L: Adres voorvoegsels voor het lokale netwerk**</span><span class="sxs-lookup"><span data-stu-id="a561e-235">**Table L: Address prefixes for the local network**</span></span>
  
<span data-ttu-id="a561e-236">Laten we nu beginnen met het bouwen van de Azure-infrastructuur om uw federatiele verificatie te hosten voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a561e-236">Now let's begin building the Azure infrastructure to host your federated authentication for Microsoft 365.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a561e-237">Met de volgende opdrachtsets wordt de meest recente versie van Azure PowerShell gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a561e-237">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="a561e-238">Zie [Aan de slag met Azure PowerShell.](/powershell/azure/get-started-azureps)</span><span class="sxs-lookup"><span data-stu-id="a561e-238">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="a561e-239">Start eerst een Azure PowerShell en meld u aan bij uw account.</span><span class="sxs-lookup"><span data-stu-id="a561e-239">First, start an Azure PowerShell prompt and login to your account.</span></span>
  
```powershell
Connect-AzAccount
```

> [!TIP]
> <span data-ttu-id="a561e-240">Als u kant-en-klaar PowerShell-opdrachtblokken wilt genereren op basis van uw aangepaste instellingen, gebruikt u [deze Microsoft Excel configuratiewerkboek.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)</span><span class="sxs-lookup"><span data-stu-id="a561e-240">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

<span data-ttu-id="a561e-241">Haal de naam van uw abonnement op met de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="a561e-241">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="a561e-242">Voor oudere versies van Azure PowerShell gebruikt u deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="a561e-242">For older versions of Azure PowerShell, use this command instead.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select SubscriptionName
```

<span data-ttu-id="a561e-243">Stel uw Azure-abonnement in.</span><span class="sxs-lookup"><span data-stu-id="a561e-243">Set your Azure subscription.</span></span> <span data-ttu-id="a561e-244">Vervang alles binnen de aanhalingstekens, inclusief de \< and >-tekens, met de juiste naam.</span><span class="sxs-lookup"><span data-stu-id="a561e-244">Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="a561e-245">Maak vervolgens de nieuwe resourcegroepen.</span><span class="sxs-lookup"><span data-stu-id="a561e-245">Next, create the new resource groups.</span></span> <span data-ttu-id="a561e-246">Als u een unieke set namen van resourcegroepen wilt bepalen, gebruikt u deze opdracht om uw bestaande resourcegroepen op te geven.</span><span class="sxs-lookup"><span data-stu-id="a561e-246">To determine a unique set of resource group names, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="a561e-247">Vul de volgende tabel in voor de set unieke resourcegroepnamen.</span><span class="sxs-lookup"><span data-stu-id="a561e-247">Fill in the following table for the set of unique resource group names.</span></span>
  
|<span data-ttu-id="a561e-248">**Item**</span><span class="sxs-lookup"><span data-stu-id="a561e-248">**Item**</span></span>|<span data-ttu-id="a561e-249">**Naam van resourcegroep**</span><span class="sxs-lookup"><span data-stu-id="a561e-249">**Resource group name**</span></span>|<span data-ttu-id="a561e-250">**Doel**</span><span class="sxs-lookup"><span data-stu-id="a561e-250">**Purpose**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a561e-251">1.</span><span class="sxs-lookup"><span data-stu-id="a561e-251">1.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="a561e-253">Domeincontrollers</span><span class="sxs-lookup"><span data-stu-id="a561e-253">Domain controllers</span></span>  <br/> |
|<span data-ttu-id="a561e-254">2.</span><span class="sxs-lookup"><span data-stu-id="a561e-254">2.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="a561e-256">AD FS-servers</span><span class="sxs-lookup"><span data-stu-id="a561e-256">AD FS servers</span></span>  <br/> |
|<span data-ttu-id="a561e-257">3.</span><span class="sxs-lookup"><span data-stu-id="a561e-257">3.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="a561e-259">Proxyservers voor webtoepassing</span><span class="sxs-lookup"><span data-stu-id="a561e-259">Web application proxy servers</span></span>  <br/> |
|<span data-ttu-id="a561e-260">4.</span><span class="sxs-lookup"><span data-stu-id="a561e-260">4.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="a561e-262&quot;>Infrastructuurelementen</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a561e-262&quot;>Infrastructure elements</span></span>  <br/> |
   
 <span data-ttu-id=&quot;a561e-263&quot;>**Tabel R: Resourcegroepen**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a561e-263&quot;>**Table R: Resource groups**</span></span>
  
<span data-ttu-id=&quot;a561e-264&quot;>Maak uw nieuwe resourcegroepen met deze opdrachten.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a561e-264&quot;>Create your new resource groups with these commands.</span></span>
  
```powershell
$locName=&quot;<an Azure location, such as West US>&quot;
$rgName=&quot;<Table R - Item 1 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
$rgName=&quot;<Table R - Item 2 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
$rgName=&quot;<Table R - Item 3 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
$rgName=&quot;<Table R - Item 4 - Name column>&quot;
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id=&quot;a561e-265&quot;>Vervolgens maakt u het virtuele Azure-netwerk en de subnetten.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a561e-265&quot;>Next, you create the Azure virtual network and its subnets.</span></span>
  
```powershell
$rgName=&quot;<Table R - Item 4 - Resource group name column>&quot;
$locName=&quot;<your Azure location>&quot;
$vnetName=&quot;<Table V - Item 1 - Value column>&quot;
$vnetAddrPrefix=&quot;<Table V - Item 4 - Value column>&quot;
$dnsServers=@( &quot;<Table D - Item 1 - DNS server IP address column>&quot;, &quot;<Table D - Item 2 - DNS server IP address column>" )
# Get the shortened version of the location
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the subnets
$subnet1Name="<Table S - Item 1 - Subnet name column>"
$subnet1Prefix="<Table S - Item 1 - Subnet address space column>"
$subnet1=New-AzVirtualNetworkSubnetConfig -Name $subnet1Name -AddressPrefix $subnet1Prefix
$subnet2Name="<Table S - Item 2 - Subnet name column>"
$subnet2Prefix="<Table S - Item 2 - Subnet address space column>"
$subnet2=New-AzVirtualNetworkSubnetConfig -Name $subnet2Name -AddressPrefix $subnet2Prefix
$subnet3Name="<Table S - Item 3 - Subnet name column>"
$subnet3Prefix="<Table S - Item 3 - Subnet address space column>"
$subnet3=New-AzVirtualNetworkSubnetConfig -Name $subnet3Name -AddressPrefix $subnet3Prefix
$gwSubnet4Prefix="<Table S - Item 4 - Subnet address space column>"
$gwSubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnet4Prefix

# Create the virtual network
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gwSubnet,$subnet1,$subnet2,$subnet3 -DNSServer $dnsServers

```

<span data-ttu-id="a561e-266">Vervolgens maakt u netwerkbeveiligingsgroepen voor elk subnet dat virtuele machines heeft.</span><span class="sxs-lookup"><span data-stu-id="a561e-266">Next, you create network security groups for each subnet that has virtual machines.</span></span> <span data-ttu-id="a561e-267">Als u subnetisolatie wilt uitvoeren, kunt u regels toevoegen voor de specifieke typen verkeer die zijn toegestaan of geweigerd aan de netwerkbeveiligingsgroep van een subnet.</span><span class="sxs-lookup"><span data-stu-id="a561e-267">To perform subnet isolation, you can add rules for the specific types of traffic allowed or denied to the network security group of a subnet.</span></span>
  
```powershell
# Create network security groups
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName

New-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet1Name -AddressPrefix $subnet1Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet2Name -AddressPrefix $subnet2Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet3Name -AddressPrefix $subnet3Prefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="a561e-268">Gebruik vervolgens deze opdrachten om de gateways te maken voor de SITE-naar-site VPN-verbinding.</span><span class="sxs-lookup"><span data-stu-id="a561e-268">Next, use these commands to create the gateways for the site-to-site VPN connection.</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "GatewaySubnet"

# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -Subnet $subnet

# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig

# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix

# Define the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway

```

> [!NOTE]
> <span data-ttu-id="a561e-269">Federatief verificatie van afzonderlijke gebruikers is niet afhankelijk van on-premises bronnen.</span><span class="sxs-lookup"><span data-stu-id="a561e-269">Federated authentication of individual users does not rely on any on-premises resources.</span></span> <span data-ttu-id="a561e-270">Als deze SITE-naar-site VPN-verbinding echter niet beschikbaar wordt, ontvangen de domeincontrollers in het VNet geen updates voor gebruikersaccounts en groepen die zijn gemaakt in de on-premises Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="a561e-270">However, if this site-to-site VPN connection becomes unavailable, the domain controllers in the VNet will not receive updates to user accounts and groups made in the on-premises Active Directory Domain Services.</span></span> <span data-ttu-id="a561e-271">Om ervoor te zorgen dat dit niet gebeurt, kunt u een hoge beschikbaarheid configureren voor uw SITE-naar-site VPN-verbinding.</span><span class="sxs-lookup"><span data-stu-id="a561e-271">To ensure this does not happen, you can configure high availability for your site-to-site VPN connection.</span></span> <span data-ttu-id="a561e-272">Zie Zeer beschikbare [cross-premises en VNet-to-VNet-connectiviteit](/azure/vpn-gateway/vpn-gateway-highlyavailable) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a561e-272">For more information, see [Highly Available Cross-Premises and VNet-to-VNet Connectivity](/azure/vpn-gateway/vpn-gateway-highlyavailable)</span></span>
  
<span data-ttu-id="a561e-273">Neem vervolgens het openbare IPv4-adres van de Azure VPN-gateway voor uw virtuele netwerk op via de weergave van deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="a561e-273">Next, record the public IPv4 address of the Azure VPN gateway for your virtual network from the display of this command:</span></span>
  
```powershell
Get-AzPublicIpAddress -Name $publicGatewayVipName -ResourceGroupName $rgName
```

<span data-ttu-id="a561e-274">Configureer vervolgens uw on-premises VPN-apparaat om verbinding te maken met de Azure VPN-gateway.</span><span class="sxs-lookup"><span data-stu-id="a561e-274">Next, configure your on-premises VPN device to connect to the Azure VPN gateway.</span></span> <span data-ttu-id="a561e-275">Zie Uw [VPN-apparaat configureren voor meer informatie.](/azure/vpn-gateway/vpn-gateway-about-vpn-devices)</span><span class="sxs-lookup"><span data-stu-id="a561e-275">For more information, see [Configure your VPN device](/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
  
<span data-ttu-id="a561e-276">Als u uw on-premises VPN-apparaat wilt configureren, hebt u het volgende nodig:</span><span class="sxs-lookup"><span data-stu-id="a561e-276">To configure your on-premises VPN device, you will need the following:</span></span>
  
- <span data-ttu-id="a561e-277">Het openbare IPv4-adres van de Azure VPN-gateway.</span><span class="sxs-lookup"><span data-stu-id="a561e-277">The public IPv4 address of the Azure VPN gateway.</span></span>
    
- <span data-ttu-id="a561e-278">De vooraf gedeelde IPsec-sleutel voor de SITE-naar-site VPN-verbinding (Tabel V - Item 5 - kolom Waarde).</span><span class="sxs-lookup"><span data-stu-id="a561e-278">The IPsec pre-shared key for the site-to-site VPN connection (Table V - Item 5 - Value column).</span></span>
    
<span data-ttu-id="a561e-279">Controleer vervolgens of de adresruimte van het virtuele netwerk bereikbaar is vanuit uw on-premises netwerk.</span><span class="sxs-lookup"><span data-stu-id="a561e-279">Next, ensure that the address space of the virtual network is reachable from your on-premises network.</span></span> <span data-ttu-id="a561e-280">Dit wordt meestal gedaan door een route toe te voegen die overeenkomt met de virtuele netwerkadresruimte aan uw VPN-apparaat en vervolgens reclame te maken voor die route naar de rest van de routeringsinfrastructuur van uw organisatienetwerk.</span><span class="sxs-lookup"><span data-stu-id="a561e-280">This is usually done by adding a route corresponding to the virtual network address space to your VPN device and then advertising that route to the rest of the routing infrastructure of your organization network.</span></span> <span data-ttu-id="a561e-281">Werk samen met uw IT-afdeling om te bepalen hoe u dit doet.</span><span class="sxs-lookup"><span data-stu-id="a561e-281">Work with your IT department to determine how to do this.</span></span>
  
<span data-ttu-id="a561e-282">Definieer vervolgens de namen van drie beschikbaarheidssets.</span><span class="sxs-lookup"><span data-stu-id="a561e-282">Next, define the names of three availability sets.</span></span> <span data-ttu-id="a561e-283">Vul tabel A in.</span><span class="sxs-lookup"><span data-stu-id="a561e-283">Fill out Table A.</span></span> 
  
|<span data-ttu-id="a561e-284">**Item**</span><span class="sxs-lookup"><span data-stu-id="a561e-284">**Item**</span></span>|<span data-ttu-id="a561e-285">**Doel**</span><span class="sxs-lookup"><span data-stu-id="a561e-285">**Purpose**</span></span>|<span data-ttu-id="a561e-286">**Naam van beschikbaarheidsset**</span><span class="sxs-lookup"><span data-stu-id="a561e-286">**Availability set name**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a561e-287">1.</span><span class="sxs-lookup"><span data-stu-id="a561e-287">1.</span></span>  <br/> |<span data-ttu-id="a561e-288">Domeincontrollers</span><span class="sxs-lookup"><span data-stu-id="a561e-288">Domain controllers</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-290">2.</span><span class="sxs-lookup"><span data-stu-id="a561e-290">2.</span></span>  <br/> |<span data-ttu-id="a561e-291">AD FS-servers</span><span class="sxs-lookup"><span data-stu-id="a561e-291">AD FS servers</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="a561e-293">3.</span><span class="sxs-lookup"><span data-stu-id="a561e-293">3.</span></span>  <br/> |<span data-ttu-id="a561e-294">Proxyservers voor webtoepassing</span><span class="sxs-lookup"><span data-stu-id="a561e-294">Web application proxy servers</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="a561e-296">**Tabel A: Beschikbaarheidssets**</span><span class="sxs-lookup"><span data-stu-id="a561e-296">**Table A: Availability sets**</span></span>
  
<span data-ttu-id="a561e-297">U hebt deze namen nodig wanneer u de virtuele machines maakt in fasen 2, 3 en 4.</span><span class="sxs-lookup"><span data-stu-id="a561e-297">You will need these names when you create the virtual machines in phases 2, 3, and 4.</span></span>
  
<span data-ttu-id="a561e-298">Maak de nieuwe beschikbaarheidssets met deze Azure PowerShell opdrachten.</span><span class="sxs-lookup"><span data-stu-id="a561e-298">Create the new availability sets with these Azure PowerShell commands.</span></span>
  
```powershell
$locName="<the Azure location for your new resource group>"
$rgName="<Table R - Item 1 - Resource group name column>"
$avName="<Table A - Item 1 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 2 - Resource group name column>"
$avName="<Table A - Item 2 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 3 - Resource group name column>"
$avName="<Table A - Item 3 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
```

<span data-ttu-id="a561e-299">Dit is de configuratie die het resultaat is van de succesvolle voltooiing van deze fase.</span><span class="sxs-lookup"><span data-stu-id="a561e-299">This is the configuration resulting from the successful completion of this phase.</span></span>
  
<span data-ttu-id="a561e-300">**Fase 1: De Azure-infrastructuur voor federatieverificatie met hoge beschikbaarheid voor Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="a561e-300">**Phase 1: The Azure infrastructure for high availability federated authentication for Microsoft 365**</span></span>

![Fase 1 van de hoge beschikbaarheid Microsoft 365 federatief verificatie in Azure met de Azure-infrastructuur](../media/4e7ba678-07df-40ce-b372-021bf7fc91fa.png)
  
## <a name="next-step"></a><span data-ttu-id="a561e-302">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="a561e-302">Next step</span></span>

<span data-ttu-id="a561e-303">Fase [2 gebruiken: Domeincontrollers configureren](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) om door te gaan met de configuratie van deze werkbelasting.</span><span class="sxs-lookup"><span data-stu-id="a561e-303">Use [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) to continue with the configuration of this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a561e-304">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a561e-304">See Also</span></span>

[<span data-ttu-id="a561e-305">Federatieverificatie met hoge beschikbaarheid implementeren voor Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="a561e-305">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="a561e-306">Federatief identiteit voor uw Microsoft 365 v/testomgeving</span><span class="sxs-lookup"><span data-stu-id="a561e-306">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="a561e-307">Microsoft 365-oplossings- en -architectuurcentrum</span><span class="sxs-lookup"><span data-stu-id="a561e-307">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)

[<span data-ttu-id="a561e-308">Inzicht Microsoft 365 identiteit en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a561e-308">Understanding Microsoft 365 identity and Azure Active Directory</span></span>](about-microsoft-365-identity.md)