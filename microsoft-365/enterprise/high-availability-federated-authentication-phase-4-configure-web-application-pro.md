---
title: Federatieve authenticatiefase van hoge beschikbaarheid 4 webtoepassingen configureren
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
ms.assetid: 1c903173-67cd-47da-86d9-d333972dda80
description: 'Overzicht: Configureer de webtoepassingsproxy voor uw federatieve authenticatie van hoge beschikbaarheid voor Microsoft 365 in Microsoft Azure.'
ms.openlocfilehash: fd63274ffb9528cedb88fc2ba77834cfd56664d4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689335"
---
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a><span data-ttu-id="6dc1b-103">Federatieve authenticatiefase van hoge beschikbaarheid 4: proxy's voor webtoepassingen configureren</span><span class="sxs-lookup"><span data-stu-id="6dc1b-103">High availability federated authentication Phase 4: Configure web application proxies</span></span>

<span data-ttu-id="6dc1b-104">In deze fase van het implementeren van hoge beschikbaarheid voor Microsoft 365 federatieve authenticatie in azure-infrastructuurservices, maakt u een interne Load Balancer en twee AD FS-servers.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you create an internal load balancer and two AD FS servers.</span></span>
  
<span data-ttu-id="6dc1b-105">U moet deze fase voltooien voordat u overstapt op [fase 5: federatieve verificatie voor Microsoft 365 configureren](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span><span class="sxs-lookup"><span data-stu-id="6dc1b-105">You must complete this phase before moving on to [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="6dc1b-106">Zie [federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) voor alle fasen.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a><span data-ttu-id="6dc1b-107">De Internet Facing Load Balancer in azure maken</span><span class="sxs-lookup"><span data-stu-id="6dc1b-107">Create the Internet-facing load balancer in Azure</span></span>

<span data-ttu-id="6dc1b-108">U moet een Internet Facing Load Balancer aanmaken, zodat Azure het verificatieverkeer van de inkomende client en het Internet gelijkmatig verdelen over de twee webtoepassingsproxy-servers.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-108">You must create an Internet-facing load balancer so that Azure distributes the incoming client authentication traffic from the Internet evenly among the two web application proxy servers.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6dc1b-109">Met de volgende opdrachtsets wordt de meest recente versie van Azure PowerShell gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-109">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="6dc1b-110">Zie [aan de slag met Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="6dc1b-110">See [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="6dc1b-111">Wanneer u de waarden voor de locatie en de resourcegroep hebt opgegeven, voert u het resultaat uit op de Azure PowerShell-opdrachtprompt of in het PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-111">When you have supplied location and resource group values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
> [!TIP]
> <span data-ttu-id="6dc1b-112">Als u kant-en-klare PowerShell-opdrachten blokken wilt genereren op basis van uw aangepaste instellingen, gebruikt u deze [Microsoft Excel-configuratie werkmap](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span><span class="sxs-lookup"><span data-stu-id="6dc1b-112">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

```powershell
# Set up key variables
$locName="<your Azure location>"
$rgName="<Table R - Item 4 - Resource group name column>"

$publicIP=New-AzPublicIpAddress -ResourceGroupName $rgName -Name "WebProxyPublicIP" -Location $LocName -AllocationMethod "Static"
$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "WebAppProxyServers-LBFE" -PublicIpAddress $publicIP
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "WebAppProxyServers-LBBE"
$healthProbe=New-AzLoadBalancerProbeConfig -Name "WebServersProbe" -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "WebTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

<span data-ttu-id="6dc1b-113">Voer de volgende opdrachten uit bij de opdrachtprompt van Azure PowerShell op uw lokale computer om het openbare IP-adres weer te geven dat is toegewezen aan uw Internet Facing Load Balancer:</span><span class="sxs-lookup"><span data-stu-id="6dc1b-113">To display the public IP address assigned to your Internet-facing load balancer, run these commands at the Azure PowerShell command prompt on your local computer:</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a><span data-ttu-id="6dc1b-114">De FQDN van de Federation service bepalen en DNS-records maken</span><span class="sxs-lookup"><span data-stu-id="6dc1b-114">Determine your federation service FQDN and create DNS records</span></span>

<span data-ttu-id="6dc1b-115">U moet de DNS-naam bepalen om de naam van de Federation-service op internet te identificeren.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-115">You need to determine the DNS name to identify your federation service name on the Internet.</span></span> <span data-ttu-id="6dc1b-116">In azure AD Connect wordt Microsoft 365 geconfigureerd met deze naam in fase 5, die deel uitmaakt van de URL die Microsoft 365 verzendt naar clients met verbinding maken om een beveiligingstoken te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-116">Azure AD Connect will configure Microsoft 365 with this name in Phase 5, which will become part of the URL that Microsoft 365 sends to connecting clients to get a security token.</span></span> <span data-ttu-id="6dc1b-117">Een voorbeeld is fs.contoso.com (FS staat voor Federation service).</span><span class="sxs-lookup"><span data-stu-id="6dc1b-117">An example is fs.contoso.com (fs stands for federation service).</span></span>
  
<span data-ttu-id="6dc1b-118">Wanneer u de Federation service-service hebt FDQN, maakt u een openbaar DNS-domein met een record voor de Federation service FDQN die wordt omgezet in het openbare IP-adres van de Azure Internet Facing Load Balancer.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-118">Once you have your federation service FDQN, create a public DNS domain A record for the federation service FDQN that resolves to the public IP address of the Azure Internet-facing load balancer.</span></span>
  
|<span data-ttu-id="6dc1b-119">**Naam**</span><span class="sxs-lookup"><span data-stu-id="6dc1b-119">**Name**</span></span>|<span data-ttu-id="6dc1b-120">**Type**</span><span class="sxs-lookup"><span data-stu-id="6dc1b-120">**Type**</span></span>|<span data-ttu-id="6dc1b-121">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6dc1b-121">**TTL**</span></span>|<span data-ttu-id="6dc1b-122">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="6dc1b-122">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6dc1b-123">Federation service FDQN</span><span class="sxs-lookup"><span data-stu-id="6dc1b-123">federation service FDQN</span></span>  <br/> |<span data-ttu-id="6dc1b-124">Een</span><span class="sxs-lookup"><span data-stu-id="6dc1b-124">A</span></span>  <br/> |<span data-ttu-id="6dc1b-125">3600</span><span class="sxs-lookup"><span data-stu-id="6dc1b-125">3600</span></span>  <br/> |<span data-ttu-id="6dc1b-126">openbaar IP-adres van de Azure Internet Facing Load Balancer (wordt weergegeven door de opdracht **Write-host** in de vorige sectie)</span><span class="sxs-lookup"><span data-stu-id="6dc1b-126">public IP address of the Azure Internet-facing load balancer (displayed by the **Write-Host** command in the previous section)</span></span> <br/> |
   
<span data-ttu-id="6dc1b-127">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="6dc1b-127">Here is an example:</span></span>
  
|<span data-ttu-id="6dc1b-128">**Naam**</span><span class="sxs-lookup"><span data-stu-id="6dc1b-128">**Name**</span></span>|<span data-ttu-id="6dc1b-129">**Type**</span><span class="sxs-lookup"><span data-stu-id="6dc1b-129">**Type**</span></span>|<span data-ttu-id="6dc1b-130">**TTL**</span><span class="sxs-lookup"><span data-stu-id="6dc1b-130">**TTL**</span></span>|<span data-ttu-id="6dc1b-131">**Waarde**</span><span class="sxs-lookup"><span data-stu-id="6dc1b-131">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6dc1b-132">fs.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6dc1b-132">fs.contoso.com</span></span>  <br/> |<span data-ttu-id="6dc1b-133">Een</span><span class="sxs-lookup"><span data-stu-id="6dc1b-133">A</span></span>  <br/> |<span data-ttu-id="6dc1b-134">3600</span><span class="sxs-lookup"><span data-stu-id="6dc1b-134">3600</span></span>  <br/> |<span data-ttu-id="6dc1b-135">131.107.249.117</span><span class="sxs-lookup"><span data-stu-id="6dc1b-135">131.107.249.117</span></span>  <br/> |
   
<span data-ttu-id="6dc1b-136">Vervolgens voegt u een DNS-adresrecord toe aan de eigen DNS-naamruimte van uw organisatie die de FQDN-service-FQDN oplost met het persoonlijke IP-adres dat is toegewezen aan de interne Load Balancer voor de AD FS-servers (tabel I, item 4, waardenaam kolom).</span><span class="sxs-lookup"><span data-stu-id="6dc1b-136">Next, add a DNS address record to your organization's private DNS namespace that resolves your federation service FQDN to the private IP address assigned to the internal load balancer for the AD FS servers (Table I, item 4, Value column).</span></span>
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a><span data-ttu-id="6dc1b-137">De virtuele machines van de webtoepassingsproxy maken in azure</span><span class="sxs-lookup"><span data-stu-id="6dc1b-137">Create the web application proxy server virtual machines in Azure</span></span>

<span data-ttu-id="6dc1b-138">Gebruik het volgende blok van Azure PowerShell-opdrachten om de virtuele machines te maken voor de twee toepassingen voor webtoepassingsproxy.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-138">Use the following block of Azure PowerShell commands to create the virtual machines for the two web application proxy servers.</span></span> 
  
<span data-ttu-id="6dc1b-139">Houd er rekening mee dat met de volgende Azure PowerShell-opdracht waarden uit de volgende tabellen worden ingesteld:</span><span class="sxs-lookup"><span data-stu-id="6dc1b-139">Note that the following Azure PowerShell command sets use values from the following tables:</span></span>
  
- <span data-ttu-id="6dc1b-140">Tabel M voor uw virtuele machines</span><span class="sxs-lookup"><span data-stu-id="6dc1b-140">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="6dc1b-141">Tabel R voor de resourcegroepen</span><span class="sxs-lookup"><span data-stu-id="6dc1b-141">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="6dc1b-142">Tabel V voor de instellingen van uw virtuele netwerk</span><span class="sxs-lookup"><span data-stu-id="6dc1b-142">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="6dc1b-143">Tabel S voor de subnetten</span><span class="sxs-lookup"><span data-stu-id="6dc1b-143">Table S, for your subnets</span></span>
    
- <span data-ttu-id="6dc1b-144">Tabel I voor uw vaste IP-adressen</span><span class="sxs-lookup"><span data-stu-id="6dc1b-144">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="6dc1b-145">Tabel A voor uw beschikbaarheidssets</span><span class="sxs-lookup"><span data-stu-id="6dc1b-145">Table A, for your availability sets</span></span>
    
<span data-ttu-id="6dc1b-146">Het intrekken van tabel M in [fase 2: configureer domeincontrollers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) en tabel R, V, S, I en A in [fase 1: Azure configureren](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="6dc1b-146">Recall that you defined Table M in [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
<span data-ttu-id="6dc1b-147">Wanneer u alle juiste waarden hebt opgegeven, voert u het resultaat uit op de Azure PowerShell-opdrachtprompt of in het PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-147">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 3 - Subnet name column>"
$avName="<Table A - Item 3 - Availability set name column>"
$rgNameTier="<Table R - Item 3 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "WebAppProxyServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first web application proxy server virtual machine
$vmName="<Table M - Item 6 - Virtual machine name column>"
$vmSize="<Table M - Item 6 - Minimum size column>"
$staticIP="<Table I - Item 7 - Value column>"
$diskStorageType="<Table M - Item 6 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second web application proxy virtual machine
$vmName="<Table M - Item 7 - Virtual machine name column>"
$vmSize="<Table M - Item 7 - Minimum size column>"
$staticIP="<Table I - Item 8 - Value column>"
$diskStorageType="<Table M - Item 7 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second web application proxy server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="6dc1b-148">Omdat deze virtuele machines zijn bedoeld voor een intranet toepassing, worden er geen openbaar IP-adres of een DNS-domeinnaamlabel toegewezen en op internet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-148">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet.</span></span> <span data-ttu-id="6dc1b-149">Dit houdt in dat u dit echter ook kunt verbinden met de Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-149">However, this also means that you cannot connect to them from the Azure portal.</span></span> <span data-ttu-id="6dc1b-150">De optie **verbinding** is niet beschikbaar wanneer u de eigenschappen van de virtuele computer bekijkt.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-150">The **Connect** option is unavailable when you view the properties of the virtual machine.</span></span> <span data-ttu-id="6dc1b-151">Gebruik de accessor voor verbindings verbinding met extern bureaublad of een ander hulpprogramma voor extern bureaublad om verbinding te maken met de virtuele machine met behulp van zijn persoonlijke IP-adres of intranet DNS-naam en de referenties van het lokale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-151">Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="6dc1b-152">Dit is de configuratie die het resultaat is van de succesvolle voltooiing van deze fase, met tijdelijke aanduidingen voor de computernamen.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-152">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="6dc1b-153">**Fase 4: de Internet Facing Load Balancer en webtoepassingsproxy-servers voor de federatieve authenticatie-infrastructuur van hoge beschikbaarheid in azure**</span><span class="sxs-lookup"><span data-stu-id="6dc1b-153">**Phase 4: The Internet-facing load balancer and web application proxy servers for your high availability federated authentication infrastructure in Azure**</span></span>

![Fase 4 van de ' hoge beschikbaarheid Microsoft 365 federatieve verificatie-infrastructuur in azure met de webtoepassingsproxy-servers](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a><span data-ttu-id="6dc1b-155">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="6dc1b-155">Next step</span></span>

<span data-ttu-id="6dc1b-156">Gebruik [fase 5: Configureer federatieve verificatie voor Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) om door te gaan met het configureren van deze werkbelasting.</span><span class="sxs-lookup"><span data-stu-id="6dc1b-156">Use [Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6dc1b-157">Zie ook</span><span class="sxs-lookup"><span data-stu-id="6dc1b-157">See Also</span></span>

[<span data-ttu-id="6dc1b-158">Federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure</span><span class="sxs-lookup"><span data-stu-id="6dc1b-158">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="6dc1b-159">Federatieve identiteit voor uw Microsoft 365 dev/testomgeving</span><span class="sxs-lookup"><span data-stu-id="6dc1b-159">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="6dc1b-160">Microsoft 365-oplossingen- en -architectuurcentrum</span><span class="sxs-lookup"><span data-stu-id="6dc1b-160">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)

