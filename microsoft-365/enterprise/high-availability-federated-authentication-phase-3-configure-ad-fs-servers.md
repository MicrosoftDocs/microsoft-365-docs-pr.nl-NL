---
title: Federatief hoge beschikbaarheid fase 3 Ad FS-servers configureren
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
description: Meer informatie over het maken en configureren van de AD FS-servers voor federatieverificatie met hoge beschikbaarheid voor Microsoft 365 in Microsoft Azure.
ms.openlocfilehash: 388a99aa496c4ecd9145759d4dfb1b9441b4fb2c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909796"
---
# <a name="high-availability-federated-authentication-phase-3-configure-ad-fs-servers"></a><span data-ttu-id="c0e72-103">Federatief hoge beschikbaarheid fase 3: AD FS-servers configureren</span><span class="sxs-lookup"><span data-stu-id="c0e72-103">High availability federated authentication Phase 3: Configure AD FS servers</span></span>

<span data-ttu-id="c0e72-104">In deze fase van het implementeren van hoge beschikbaarheid voor Microsoft 365 federatieve verificatie in Azure-infrastructuurservices, maakt u een interne load balancer en twee AD FS-servers.</span><span class="sxs-lookup"><span data-stu-id="c0e72-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you create an internal load balancer and two AD FS servers.</span></span>
  
<span data-ttu-id="c0e72-105">U moet deze fase voltooien voordat u verder gaat [met fase 4: Webtoepassingsproxies configureren.](high-availability-federated-authentication-phase-4-configure-web-application-pro.md)</span><span class="sxs-lookup"><span data-stu-id="c0e72-105">You must complete this phase before moving on to [Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md).</span></span> <span data-ttu-id="c0e72-106">Zie [Federatieverificatie met hoge](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) beschikbaarheid implementeren voor Microsoft 365 in Azure voor alle fasen.</span><span class="sxs-lookup"><span data-stu-id="c0e72-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-ad-fs-server-virtual-machines-in-azure"></a><span data-ttu-id="c0e72-107">Virtuele machines voor AD FS-server maken in Azure</span><span class="sxs-lookup"><span data-stu-id="c0e72-107">Create the AD FS server virtual machines in Azure</span></span>

<span data-ttu-id="c0e72-108">Gebruik het volgende blok met PowerShell-opdrachten om de virtuele machines voor de twee AD FS-servers te maken.</span><span class="sxs-lookup"><span data-stu-id="c0e72-108">Use the following block of PowerShell commands to create the virtual machines for the two AD FS servers.</span></span> <span data-ttu-id="c0e72-109">In deze PowerShell-opdrachtset worden waarden uit de volgende tabellen gebruikt:</span><span class="sxs-lookup"><span data-stu-id="c0e72-109">This PowerShell command set uses values from the following tables:</span></span>
  
- <span data-ttu-id="c0e72-110">Tabel M, voor uw virtuele machines</span><span class="sxs-lookup"><span data-stu-id="c0e72-110">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="c0e72-111">Tabel R, voor uw resourcegroepen</span><span class="sxs-lookup"><span data-stu-id="c0e72-111">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="c0e72-112">Tabel V, voor uw virtuele netwerkinstellingen</span><span class="sxs-lookup"><span data-stu-id="c0e72-112">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="c0e72-113">Tabel S, voor uw subnetten</span><span class="sxs-lookup"><span data-stu-id="c0e72-113">Table S, for your subnets</span></span>
    
- <span data-ttu-id="c0e72-114">Tabel I, voor uw statische IP-adressen</span><span class="sxs-lookup"><span data-stu-id="c0e72-114">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="c0e72-115">Tabel A, voor uw beschikbaarheidssets</span><span class="sxs-lookup"><span data-stu-id="c0e72-115">Table A, for your availability sets</span></span>
    
<span data-ttu-id="c0e72-116">U hebt tabel M gedefinieerd in [fase 2: Domeincontrollers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) en tabellen R, V, S, I en A configureren in [fase 1: Azure configureren.](high-availability-federated-authentication-phase-1-configure-azure.md)</span><span class="sxs-lookup"><span data-stu-id="c0e72-116">Recall that you defined Table M in [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0e72-117">Met de volgende opdrachtsets wordt de meest recente versie van Azure PowerShell gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c0e72-117">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="c0e72-118">Zie [Aan de slag met Azure PowerShell.](/powershell/azure/get-started-azureps)</span><span class="sxs-lookup"><span data-stu-id="c0e72-118">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="c0e72-119">Eerst maakt u een Azure Internal Load Balancer voor de twee AD FS-servers.</span><span class="sxs-lookup"><span data-stu-id="c0e72-119">First, you create an Azure internal load balancer for the two AD FS servers.</span></span> <span data-ttu-id="c0e72-120">Geef de waarden op voor de variabelen en verwijder de \< and > tekens.</span><span class="sxs-lookup"><span data-stu-id="c0e72-120">Specify the values for the variables, removing the \< and > characters.</span></span> <span data-ttu-id="c0e72-121">Wanneer u alle juiste waarden hebt opgegeven, kunt u het resulterende blok uitvoeren bij de opdrachtprompt Azure PowerShell powershell of in de PowerShell-ise.</span><span class="sxs-lookup"><span data-stu-id="c0e72-121">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
> [!TIP]
> <span data-ttu-id="c0e72-122">Als u kant-en-klaar PowerShell-opdrachtblokken wilt genereren op basis van uw aangepaste instellingen, gebruikt u [deze Microsoft Excel configuratiewerkboek.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)</span><span class="sxs-lookup"><span data-stu-id="c0e72-122">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

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

<span data-ttu-id="c0e72-123">Maak vervolgens de virtuele machines van de AD FS-server.</span><span class="sxs-lookup"><span data-stu-id="c0e72-123">Next, create the AD FS server virtual machines.</span></span>
  
<span data-ttu-id="c0e72-124">Wanneer u alle juiste waarden hebt opgegeven, kunt u het resulterende blok uitvoeren bij de opdrachtprompt Azure PowerShell powershell of in de PowerShell-ise.</span><span class="sxs-lookup"><span data-stu-id="c0e72-124">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
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
> <span data-ttu-id="c0e72-125">Omdat deze virtuele machines voor een intranettoepassing zijn, krijgen ze geen openbaar IP-adres of een DNS-domeinnaamlabel toegewezen en worden ze blootgesteld aan internet.</span><span class="sxs-lookup"><span data-stu-id="c0e72-125">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet.</span></span> <span data-ttu-id="c0e72-126">Dit betekent echter ook dat u geen verbinding met ze kunt maken vanuit de Azure-portal.</span><span class="sxs-lookup"><span data-stu-id="c0e72-126">However, this also means that you cannot connect to them from the Azure portal.</span></span> <span data-ttu-id="c0e72-127">De **Verbinding maken** optie is niet beschikbaar wanneer u de eigenschappen van de virtuele computer bekijkt.</span><span class="sxs-lookup"><span data-stu-id="c0e72-127">The **Connect** option is unavailable when you view the properties of the virtual machine.</span></span> <span data-ttu-id="c0e72-128">Gebruik het accessoire Extern bureaublad-verbinding of een ander hulpprogramma voor extern bureaublad om verbinding te maken met de virtuele computer met de dns-naam van het privé-IP-adres of intranet.</span><span class="sxs-lookup"><span data-stu-id="c0e72-128">Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name.</span></span>
  
<span data-ttu-id="c0e72-129">Gebruik voor elke virtuele computer de externe bureaubladclient van uw keuze en maak een externe bureaubladverbinding.</span><span class="sxs-lookup"><span data-stu-id="c0e72-129">For each virtual machine, use the remote desktop client of your choice and create a remote desktop connection.</span></span> <span data-ttu-id="c0e72-130">Gebruik de intranet DNS- of computernaam en de referenties van het lokale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="c0e72-130">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="c0e72-131">Sluit u voor elke virtuele computer aan bij het juiste AD DS-domein (Active Directory Domain Services) met deze opdrachten op de Windows PowerShell prompt.</span><span class="sxs-lookup"><span data-stu-id="c0e72-131">For each virtual machine, join them to the appropriate Active Directory Domain Services (AD DS) domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

<span data-ttu-id="c0e72-132">Hier is de configuratie die het resultaat is van de succesvolle voltooiing van deze fase, met computernamen van tijdelijke aanduidingen.</span><span class="sxs-lookup"><span data-stu-id="c0e72-132">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="c0e72-133">**Fase 3: De AD FS-servers en interne load balancer voor uw federatieve verificatieinfrastructuur met hoge beschikbaarheid in Azure**</span><span class="sxs-lookup"><span data-stu-id="c0e72-133">**Phase 3: The AD FS servers and internal load balancer for your high availability federated authentication infrastructure in Azure**</span></span>

![Fase 3 van de hoge beschikbaarheid Microsoft 365 federatief verificatie-infrastructuur in Azure met de AD FS-servers](../media/f39b2d2f-8a5b-44da-b763-e1f943fcdbc4.png)
  
## <a name="next-step"></a><span data-ttu-id="c0e72-135">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="c0e72-135">Next step</span></span>

<span data-ttu-id="c0e72-136">Fase [4: Webtoepassingsproxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) configureren om deze werkbelasting te blijven configureren.</span><span class="sxs-lookup"><span data-stu-id="c0e72-136">Use [Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c0e72-137">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c0e72-137">See Also</span></span>

[<span data-ttu-id="c0e72-138">Federatieverificatie met hoge beschikbaarheid implementeren voor Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="c0e72-138">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="c0e72-139">Federatief identiteit voor uw Microsoft 365 v/testomgeving</span><span class="sxs-lookup"><span data-stu-id="c0e72-139">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)