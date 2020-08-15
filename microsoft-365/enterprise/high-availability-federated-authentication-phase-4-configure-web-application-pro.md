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
# <a name="high-availability-federated-authentication-phase-4-configure-web-application-proxies"></a>Federatieve authenticatiefase van hoge beschikbaarheid 4: proxy's voor webtoepassingen configureren

In deze fase van het implementeren van hoge beschikbaarheid voor Microsoft 365 federatieve authenticatie in azure-infrastructuurservices, maakt u een interne Load Balancer en twee AD FS-servers.
  
U moet deze fase voltooien voordat u overstapt op [fase 5: federatieve verificatie voor Microsoft 365 configureren](high-availability-federated-authentication-phase-5-configure-federated-authentic.md). Zie [federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) voor alle fasen.
  
## <a name="create-the-internet-facing-load-balancer-in-azure"></a>De Internet Facing Load Balancer in azure maken

U moet een Internet Facing Load Balancer aanmaken, zodat Azure het verificatieverkeer van de inkomende client en het Internet gelijkmatig verdelen over de twee webtoepassingsproxy-servers.
  
> [!NOTE]
> Met de volgende opdrachtsets wordt de meest recente versie van Azure PowerShell gebruikt. Zie [aan de slag met Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps). 
  
Wanneer u de waarden voor de locatie en de resourcegroep hebt opgegeven, voert u het resultaat uit op de Azure PowerShell-opdrachtprompt of in het PowerShell-ISE.
  
> [!TIP]
> Als u kant-en-klare PowerShell-opdrachten blokken wilt genereren op basis van uw aangepaste instellingen, gebruikt u deze [Microsoft Excel-configuratie werkmap](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx). 

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

Voer de volgende opdrachten uit bij de opdrachtprompt van Azure PowerShell op uw lokale computer om het openbare IP-adres weer te geven dat is toegewezen aan uw Internet Facing Load Balancer:
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "WebProxyPublicIP" -ResourceGroup $rgName).IPAddress
```

## <a name="determine-your-federation-service-fqdn-and-create-dns-records"></a>De FQDN van de Federation service bepalen en DNS-records maken

U moet de DNS-naam bepalen om de naam van de Federation-service op internet te identificeren. In azure AD Connect wordt Microsoft 365 geconfigureerd met deze naam in fase 5, die deel uitmaakt van de URL die Microsoft 365 verzendt naar clients met verbinding maken om een beveiligingstoken te verkrijgen. Een voorbeeld is fs.contoso.com (FS staat voor Federation service).
  
Wanneer u de Federation service-service hebt FDQN, maakt u een openbaar DNS-domein met een record voor de Federation service FDQN die wordt omgezet in het openbare IP-adres van de Azure Internet Facing Load Balancer.
  
|**Naam**|**Type**|**TTL**|**Waarde**|
|:-----|:-----|:-----|:-----|
|Federation service FDQN  <br/> |Een  <br/> |3600  <br/> |openbaar IP-adres van de Azure Internet Facing Load Balancer (wordt weergegeven door de opdracht **Write-host** in de vorige sectie) <br/> |
   
Hier ziet u een voorbeeld:
  
|**Naam**|**Type**|**TTL**|**Waarde**|
|:-----|:-----|:-----|:-----|
|fs.contoso.com  <br/> |Een  <br/> |3600  <br/> |131.107.249.117  <br/> |
   
Vervolgens voegt u een DNS-adresrecord toe aan de eigen DNS-naamruimte van uw organisatie die de FQDN-service-FQDN oplost met het persoonlijke IP-adres dat is toegewezen aan de interne Load Balancer voor de AD FS-servers (tabel I, item 4, waardenaam kolom).
  
## <a name="create-the-web-application-proxy-server-virtual-machines-in-azure"></a>De virtuele machines van de webtoepassingsproxy maken in azure

Gebruik het volgende blok van Azure PowerShell-opdrachten om de virtuele machines te maken voor de twee toepassingen voor webtoepassingsproxy. 
  
Houd er rekening mee dat met de volgende Azure PowerShell-opdracht waarden uit de volgende tabellen worden ingesteld:
  
- Tabel M voor uw virtuele machines
    
- Tabel R voor de resourcegroepen
    
- Tabel V voor de instellingen van uw virtuele netwerk
    
- Tabel S voor de subnetten
    
- Tabel I voor uw vaste IP-adressen
    
- Tabel A voor uw beschikbaarheidssets
    
Het intrekken van tabel M in [fase 2: configureer domeincontrollers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) en tabel R, V, S, I en A in [fase 1: Azure configureren](high-availability-federated-authentication-phase-1-configure-azure.md).
  
Wanneer u alle juiste waarden hebt opgegeven, voert u het resultaat uit op de Azure PowerShell-opdrachtprompt of in het PowerShell-ISE.
  
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
> Omdat deze virtuele machines zijn bedoeld voor een intranet toepassing, worden er geen openbaar IP-adres of een DNS-domeinnaamlabel toegewezen en op internet weergegeven. Dit houdt in dat u dit echter ook kunt verbinden met de Azure-Portal. De optie **verbinding** is niet beschikbaar wanneer u de eigenschappen van de virtuele computer bekijkt. Gebruik de accessor voor verbindings verbinding met extern bureaublad of een ander hulpprogramma voor extern bureaublad om verbinding te maken met de virtuele machine met behulp van zijn persoonlijke IP-adres of intranet DNS-naam en de referenties van het lokale beheerdersaccount.
  
Dit is de configuratie die het resultaat is van de succesvolle voltooiing van deze fase, met tijdelijke aanduidingen voor de computernamen.
  
**Fase 4: de Internet Facing Load Balancer en webtoepassingsproxy-servers voor de federatieve authenticatie-infrastructuur van hoge beschikbaarheid in azure**

![Fase 4 van de ' hoge beschikbaarheid Microsoft 365 federatieve verificatie-infrastructuur in azure met de webtoepassingsproxy-servers](../media/7e03183f-3b3b-4cbe-9028-89cc3f195a63.png)
  
## <a name="next-step"></a>Volgende stap

Gebruik [fase 5: Configureer federatieve verificatie voor Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) om door te gaan met het configureren van deze werkbelasting.
  
## <a name="see-also"></a>Zie ook

[Federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Federatieve identiteit voor uw Microsoft 365 dev/testomgeving](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365-oplossingen- en -architectuurcentrum](../solutions/solution-architecture-center.md)

