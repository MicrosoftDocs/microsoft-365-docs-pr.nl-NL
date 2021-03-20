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
# <a name="high-availability-federated-authentication-phase-3-configure-ad-fs-servers"></a>Federatief hoge beschikbaarheid fase 3: AD FS-servers configureren

In deze fase van het implementeren van hoge beschikbaarheid voor Microsoft 365 federatieve verificatie in Azure-infrastructuurservices, maakt u een interne load balancer en twee AD FS-servers.
  
U moet deze fase voltooien voordat u verder gaat [met fase 4: Webtoepassingsproxies configureren.](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) Zie [Federatieverificatie met hoge beschikbaarheid implementeren voor Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) voor alle fasen.
  
## <a name="create-the-ad-fs-server-virtual-machines-in-azure"></a>Virtuele machines voor AD FS-server maken in Azure

Gebruik het volgende blok met PowerShell-opdrachten om de virtuele machines voor de twee AD FS-servers te maken. In deze PowerShell-opdrachtset worden waarden uit de volgende tabellen gebruikt:
  
- Tabel M, voor uw virtuele machines
    
- Tabel R, voor uw resourcegroepen
    
- Tabel V, voor uw virtuele netwerkinstellingen
    
- Tabel S, voor uw subnetten
    
- Tabel I, voor uw statische IP-adressen
    
- Tabel A, voor uw beschikbaarheidssets
    
U hebt tabel M gedefinieerd in [fase 2: Domeincontrollers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) en tabellen R, V, S, I en A configureren in [fase 1: Azure configureren.](high-availability-federated-authentication-phase-1-configure-azure.md)
  
> [!NOTE]
> Met de volgende opdrachtsets wordt de meest recente versie van Azure PowerShell gebruikt. Zie [Aan de slag met Azure PowerShell](/powershell/azure/get-started-azureps). 
  
Eerst maakt u een Azure Internal Load Balancer voor de twee AD FS-servers. Geef de waarden op voor de variabelen en verwijder de \< and > tekens. Wanneer u alle juiste waarden hebt opgegeven, kunt u het resulterende blok uitvoeren op de opdrachtprompt van Azure PowerShell of in de PowerShell-ise.
  
> [!TIP]
> Als u kant-en-klaar PowerShell-opdrachtblokken wilt genereren op basis van uw aangepaste instellingen, gebruikt u deze [Configuratiewerkboek van Microsoft Excel.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx) 

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

Maak vervolgens de virtuele machines van de AD FS-server.
  
Wanneer u alle juiste waarden hebt opgegeven, kunt u het resulterende blok uitvoeren op de opdrachtprompt van Azure PowerShell of in de PowerShell-ise.
  
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
> Omdat deze virtuele machines voor een intranettoepassing zijn, krijgen ze geen openbaar IP-adres of een DNS-domeinnaamlabel toegewezen en worden ze blootgesteld aan internet. Dit betekent echter ook dat u geen verbinding met ze kunt maken vanuit de Azure-portal. De **optie** Verbinding maken is niet beschikbaar wanneer u de eigenschappen van de virtuele computer bekijkt. Gebruik het accessoire Extern bureaublad-verbinding of een ander hulpprogramma voor extern bureaublad om verbinding te maken met de virtuele computer met de dns-naam van het privé-IP-adres of intranet.
  
Gebruik voor elke virtuele computer de externe bureaubladclient van uw keuze en maak een externe bureaubladverbinding. Gebruik de intranet DNS- of computernaam en de referenties van het lokale beheerdersaccount.
  
Neem voor elke virtuele machine deel aan het juiste AD DS-domein (Active Directory Domain Services) met deze opdrachten in de Windows PowerShell-prompt.
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

Hier is de configuratie die het resultaat is van de succesvolle voltooiing van deze fase, met computernamen van tijdelijke aanduidingen.
  
**Fase 3: De AD FS-servers en interne load balancer voor uw federatieve verificatieinfrastructuur met hoge beschikbaarheid in Azure**

![Fase 3 van de hoge beschikbaarheid van Microsoft 365 federatief verificatie-infrastructuur in Azure met de AD FS-servers](../media/f39b2d2f-8a5b-44da-b763-e1f943fcdbc4.png)
  
## <a name="next-step"></a>Volgende stap

Fase [4: Webtoepassingsproxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) configureren om deze werkbelasting te blijven configureren.
  
## <a name="see-also"></a>Zie ook

[Federatieverificatie met hoge beschikbaarheid implementeren voor Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Federatief identiteit voor uw Microsoft 365-dev/testomgeving](federated-identity-for-your-microsoft-365-dev-test-environment.md)