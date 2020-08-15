---
title: Federatieve authenticatiefase van hoge beschikbaarheid 3 AD FS-servers configureren
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
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 202b76ff-74a6-4486-ada1-a9bf099dab8f
description: Leer hoe u de AD FS-servers maakt en configureert voor uw federatieve authenticatie van hoge beschikbaarheid voor Microsoft 365 in Microsoft Azure.
ms.openlocfilehash: bf8b52f4cd0dead0c264b71363fd5248397ae88d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689564"
---
# <a name="high-availability-federated-authentication-phase-3-configure-ad-fs-servers"></a><span data-ttu-id="633c2-103">Federatieve authenticatiefase van hoge beschikbaarheid 3: AD FS-servers configureren</span><span class="sxs-lookup"><span data-stu-id="633c2-103">High availability federated authentication Phase 3: Configure AD FS servers</span></span>

<span data-ttu-id="633c2-104">In deze fase van het implementeren van hoge beschikbaarheid voor Microsoft 365 federatieve authenticatie in azure-infrastructuurservices, maakt u een interne Load Balancer en twee AD FS-servers.</span><span class="sxs-lookup"><span data-stu-id="633c2-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you create an internal load balancer and two AD FS servers.</span></span>
  
<span data-ttu-id="633c2-105">U moet deze fase voltooien voordat u overstapt naar [fase 4: proxy's voor webtoepassingen configureren](high-availability-federated-authentication-phase-4-configure-web-application-pro.md).</span><span class="sxs-lookup"><span data-stu-id="633c2-105">You must complete this phase before moving on to [Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md).</span></span> <span data-ttu-id="633c2-106">Zie [federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) voor alle fasen.</span><span class="sxs-lookup"><span data-stu-id="633c2-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-ad-fs-server-virtual-machines-in-azure"></a><span data-ttu-id="633c2-107">De virtuele machines voor de AD FS-server in azure maken</span><span class="sxs-lookup"><span data-stu-id="633c2-107">Create the AD FS server virtual machines in Azure</span></span>

<span data-ttu-id="633c2-108">Gebruik de volgende PowerShell-opdrachten om de virtuele machines voor de twee AD FS-servers te maken.</span><span class="sxs-lookup"><span data-stu-id="633c2-108">Use the following block of PowerShell commands to create the virtual machines for the two AD FS servers.</span></span> <span data-ttu-id="633c2-109">In deze PowerShell-opdrachtset worden waarden uit de volgende tabellen gebruikt:</span><span class="sxs-lookup"><span data-stu-id="633c2-109">This PowerShell command set uses values from the following tables:</span></span>
  
- <span data-ttu-id="633c2-110">Tabel M voor uw virtuele machines</span><span class="sxs-lookup"><span data-stu-id="633c2-110">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="633c2-111">Tabel R voor de resourcegroepen</span><span class="sxs-lookup"><span data-stu-id="633c2-111">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="633c2-112">Tabel V voor de instellingen van uw virtuele netwerk</span><span class="sxs-lookup"><span data-stu-id="633c2-112">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="633c2-113">Tabel S voor de subnetten</span><span class="sxs-lookup"><span data-stu-id="633c2-113">Table S, for your subnets</span></span>
    
- <span data-ttu-id="633c2-114">Tabel I voor uw vaste IP-adressen</span><span class="sxs-lookup"><span data-stu-id="633c2-114">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="633c2-115">Tabel A voor uw beschikbaarheidssets</span><span class="sxs-lookup"><span data-stu-id="633c2-115">Table A, for your availability sets</span></span>
    
<span data-ttu-id="633c2-116">Het intrekken van tabel M in [fase 2: configureer domeincontrollers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) en tabel R, V, S, I en A in [fase 1: Azure configureren](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="633c2-116">Recall that you defined Table M in [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="633c2-117">Met de volgende opdrachtsets wordt de meest recente versie van Azure PowerShell gebruikt.</span><span class="sxs-lookup"><span data-stu-id="633c2-117">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="633c2-118">Zie [aan de slag met Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="633c2-118">See [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="633c2-119">U maakt eerst een Azure Internal Load Balancer voor de twee AD FS-servers.</span><span class="sxs-lookup"><span data-stu-id="633c2-119">First, you create an Azure internal load balancer for the two AD FS servers.</span></span> <span data-ttu-id="633c2-120">Geef de waarden voor de variabelen op en verwijder de \< and > tekens.</span><span class="sxs-lookup"><span data-stu-id="633c2-120">Specify the values for the variables, removing the \< and > characters.</span></span> <span data-ttu-id="633c2-121">Wanneer u alle juiste waarden hebt opgegeven, voert u het resultaat uit op de Azure PowerShell-opdrachtprompt of in het PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="633c2-121">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
> [!TIP]
> <span data-ttu-id="633c2-122">Als u kant-en-klare PowerShell-opdrachten blokken wilt genereren op basis van uw aangepaste instellingen, gebruikt u deze [Microsoft Excel-configuratie werkmap](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span><span class="sxs-lookup"><span data-stu-id="633c2-122">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

```powershell
# Set up key variables
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 2 - Subnet name column>"
$privIP="<Table I - Item 4 - Value column>"
$rgName=<Table R - Item 4 - Resource group name column>"

$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "ADFSServers-LBFE" -PrivateIPAddress $privIP -Subnet $subnet
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "ADFSServers-LBBE"

$healthProbe=New-AzLoadBalancerProbeConfig -Name WebServersProbe -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "HTTPSTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "ADFSServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

<span data-ttu-id="633c2-123">Vervolgens maakt u de virtuele machines van de AD FS-server.</span><span class="sxs-lookup"><span data-stu-id="633c2-123">Next, create the AD FS server virtual machines.</span></span>
  
<span data-ttu-id="633c2-124">Wanneer u alle juiste waarden hebt opgegeven, voert u het resultaat uit op de Azure PowerShell-opdrachtprompt of in het PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="633c2-124">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 2 - Subnet name column>"
$avName="<Table A - Item 2 - Availability set name column>"
$rgNameTier="<Table R - Item 2 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "ADFSServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first ADFS server virtual machine
$vmName="<Table M - Item 4 - Virtual machine name column>"
$vmSize="<Table M - Item 4 - Minimum size column>"
$staticIP="<Table I - Item 5 - Value column>"
$diskStorageType="<Table M - Item 4 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first AD FS server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second AD FS virtual machine
$vmName="<Table M - Item 5 - Virtual machine name column>"
$vmSize="<Table M - Item 5 - Minimum size column>"
$staticIP="<Table I - Item 6 - Value column>"
$diskStorageType="<Table M - Item 5 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second AD FS server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

```

> [!NOTE]
> <span data-ttu-id="633c2-125">Omdat deze virtuele machines zijn bedoeld voor een intranet toepassing, worden er geen openbaar IP-adres of een DNS-domeinnaamlabel toegewezen en op internet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="633c2-125">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet.</span></span> <span data-ttu-id="633c2-126">Dit houdt in dat u dit echter ook kunt verbinden met de Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="633c2-126">However, this also means that you cannot connect to them from the Azure portal.</span></span> <span data-ttu-id="633c2-127">De optie **verbinding** is niet beschikbaar wanneer u de eigenschappen van de virtuele computer bekijkt.</span><span class="sxs-lookup"><span data-stu-id="633c2-127">The **Connect** option is unavailable when you view the properties of the virtual machine.</span></span> <span data-ttu-id="633c2-128">Gebruik de accessor van het extern bureaublad of een ander hulpprogramma voor extern bureaublad om verbinding te maken met de virtuele machine met behulp van de bijbehorende persoonlijke IP-adressen of intranet namen.</span><span class="sxs-lookup"><span data-stu-id="633c2-128">Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name.</span></span>
  
<span data-ttu-id="633c2-129">Voor elke virtuele machine gebruikt u de externe bureaubladclient van uw keuze en maakt u een verbinding met extern bureaublad.</span><span class="sxs-lookup"><span data-stu-id="633c2-129">For each virtual machine, use the remote desktop client of your choice and create a remote desktop connection.</span></span> <span data-ttu-id="633c2-130">Gebruik de intranet-of computernaam van het intranet en de referenties van het lokale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="633c2-130">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="633c2-131">Voor elke virtuele machine voegt u de volgende opdrachten toe aan het juiste AD DS-domein (Active Directory Domain Services) met deze opdrachten op de Windows PowerShell-prompt.</span><span class="sxs-lookup"><span data-stu-id="633c2-131">For each virtual machine, join them to the appropriate Active Directory Domain Services (AD DS) domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

<span data-ttu-id="633c2-132">Dit is de configuratie die het resultaat is van de succesvolle voltooiing van deze fase, met tijdelijke aanduidingen voor de computernamen.</span><span class="sxs-lookup"><span data-stu-id="633c2-132">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="633c2-133">**Fase 3: de AD FS-servers en interne Load Balancer voor de federatieve authenticatie-infrastructuur van hoge beschikbaarheid in azure**</span><span class="sxs-lookup"><span data-stu-id="633c2-133">**Phase 3: The AD FS servers and internal load balancer for your high availability federated authentication infrastructure in Azure**</span></span>

![Fase 3 van de ' hoge beschikbaarheid Microsoft 365 federatieve verificatie-infrastructuur in azure met de AD FS-servers](../media/f39b2d2f-8a5b-44da-b763-e1f943fcdbc4.png)
  
## <a name="next-step"></a><span data-ttu-id="633c2-135">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="633c2-135">Next step</span></span>

<span data-ttu-id="633c2-136">Gebruik [fase 4: proxy's voor webtoepassingen configureren](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) om door te gaan met het configureren van deze werkbelasting.</span><span class="sxs-lookup"><span data-stu-id="633c2-136">Use [Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="633c2-137">Zie ook</span><span class="sxs-lookup"><span data-stu-id="633c2-137">See Also</span></span>

[<span data-ttu-id="633c2-138">Federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure</span><span class="sxs-lookup"><span data-stu-id="633c2-138">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="633c2-139">Federatieve identiteit voor uw Microsoft 365 dev/testomgeving</span><span class="sxs-lookup"><span data-stu-id="633c2-139">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)


