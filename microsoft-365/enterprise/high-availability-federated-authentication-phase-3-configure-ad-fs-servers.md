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
# <a name="high-availability-federated-authentication-phase-3-configure-ad-fs-servers"></a>Federatieve authenticatiefase van hoge beschikbaarheid 3: AD FS-servers configureren

In deze fase van het implementeren van hoge beschikbaarheid voor Microsoft 365 federatieve authenticatie in azure-infrastructuurservices, maakt u een interne Load Balancer en twee AD FS-servers.
  
U moet deze fase voltooien voordat u overstapt naar [fase 4: proxy's voor webtoepassingen configureren](high-availability-federated-authentication-phase-4-configure-web-application-pro.md). Zie [federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) voor alle fasen.
  
## <a name="create-the-ad-fs-server-virtual-machines-in-azure"></a>De virtuele machines voor de AD FS-server in azure maken

Gebruik de volgende PowerShell-opdrachten om de virtuele machines voor de twee AD FS-servers te maken. In deze PowerShell-opdrachtset worden waarden uit de volgende tabellen gebruikt:
  
- Tabel M voor uw virtuele machines
    
- Tabel R voor de resourcegroepen
    
- Tabel V voor de instellingen van uw virtuele netwerk
    
- Tabel S voor de subnetten
    
- Tabel I voor uw vaste IP-adressen
    
- Tabel A voor uw beschikbaarheidssets
    
Het intrekken van tabel M in [fase 2: configureer domeincontrollers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) en tabel R, V, S, I en A in [fase 1: Azure configureren](high-availability-federated-authentication-phase-1-configure-azure.md).
  
> [!NOTE]
> Met de volgende opdrachtsets wordt de meest recente versie van Azure PowerShell gebruikt. Zie [aan de slag met Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps). 
  
U maakt eerst een Azure Internal Load Balancer voor de twee AD FS-servers. Geef de waarden voor de variabelen op en verwijder de \< and > tekens. Wanneer u alle juiste waarden hebt opgegeven, voert u het resultaat uit op de Azure PowerShell-opdrachtprompt of in het PowerShell-ISE.
  
> [!TIP]
> Als u kant-en-klare PowerShell-opdrachten blokken wilt genereren op basis van uw aangepaste instellingen, gebruikt u deze [Microsoft Excel-configuratie werkmap](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx). 

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

Vervolgens maakt u de virtuele machines van de AD FS-server.
  
Wanneer u alle juiste waarden hebt opgegeven, voert u het resultaat uit op de Azure PowerShell-opdrachtprompt of in het PowerShell-ISE.
  
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
> Omdat deze virtuele machines zijn bedoeld voor een intranet toepassing, worden er geen openbaar IP-adres of een DNS-domeinnaamlabel toegewezen en op internet weergegeven. Dit houdt in dat u dit echter ook kunt verbinden met de Azure-Portal. De optie **verbinding** is niet beschikbaar wanneer u de eigenschappen van de virtuele computer bekijkt. Gebruik de accessor van het extern bureaublad of een ander hulpprogramma voor extern bureaublad om verbinding te maken met de virtuele machine met behulp van de bijbehorende persoonlijke IP-adressen of intranet namen.
  
Voor elke virtuele machine gebruikt u de externe bureaubladclient van uw keuze en maakt u een verbinding met extern bureaublad. Gebruik de intranet-of computernaam van het intranet en de referenties van het lokale beheerdersaccount.
  
Voor elke virtuele machine voegt u de volgende opdrachten toe aan het juiste AD DS-domein (Active Directory Domain Services) met deze opdrachten op de Windows PowerShell-prompt.
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

Dit is de configuratie die het resultaat is van de succesvolle voltooiing van deze fase, met tijdelijke aanduidingen voor de computernamen.
  
**Fase 3: de AD FS-servers en interne Load Balancer voor de federatieve authenticatie-infrastructuur van hoge beschikbaarheid in azure**

![Fase 3 van de ' hoge beschikbaarheid Microsoft 365 federatieve verificatie-infrastructuur in azure met de AD FS-servers](../media/f39b2d2f-8a5b-44da-b763-e1f943fcdbc4.png)
  
## <a name="next-step"></a>Volgende stap

Gebruik [fase 4: proxy's voor webtoepassingen configureren](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) om door te gaan met het configureren van deze werkbelasting.
  
## <a name="see-also"></a>Zie ook

[Federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Federatieve identiteit voor uw Microsoft 365 dev/testomgeving](federated-identity-for-your-microsoft-365-dev-test-environment.md)


