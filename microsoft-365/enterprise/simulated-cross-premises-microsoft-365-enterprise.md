---
title: Gesimuleerd cross-premises virtueel netwerk in een Microsoft 365-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: seo-marvel-apr2020
description: 'Samenvatting: maak een gesimuleerd cross-premises virtueel netwerk in Microsoft Azure als een Microsoft 365-testomgeving.'
ms.openlocfilehash: 545cce668df66b594de6b45ddd506b87afcf44ac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926030"
---
# <a name="simulated-cross-premises-virtual-network-in-a-microsoft-365-test-environment"></a>Gesimuleerd cross-premises virtueel netwerk in een Microsoft 365-testomgeving

*Deze testlaborator kan worden gebruikt voor zowel Microsoft 365 voor bedrijven als Office 365 Enterprise testomgevingen.*

In dit artikel wordt stapsgewijs uitgelegd hoe u een gesimuleerde hybride cloudomgeving met Microsoft Azure maakt met behulp van twee virtuele Azure-netwerken. Dit is de resulterende configuratie. 
  
![Fase 3 van de testomgeving met de gesimuleerde cross-premises virtueel netwerkomgeving, met de virtuele DC2 machine in het XPrem VNet](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
Hiermee wordt een Azure IaaS-productieomgeving met een hybride cloud gesimuleerd. Deze bestaat uit:
  
- Een gesimuleerd en vereenvoudigd on-premises netwerk dat wordt gehost in een virtueel Azure-netwerk (het virtuele netwerk van TestLab).
    
- Een gesimuleerd cross-premises virtueel netwerk dat wordt gehost in Azure (XPrem).
    
- Een VNet-peeringrelatie tussen de twee virtuele netwerken.
    
- Een secundaire domeincontroller in het virtuele XPrem-netwerk.
    
Dit biedt een basis en een gemeenschappelijk startpunt van waaruit u kunt: 
  
- Toepassingen in een gesimuleerde Azure IaaS hybride cloud-omgeving ontwikkelen en testen.
    
- Testconfiguraties van computers maken, sommige binnen het virtuele TestLab-netwerk en sommige binnen het virtuele XPrem-netwerk, om hybride cloudgebaseerde IT-workloads te simuleren.
    
Er zijn drie belangrijke fasen om deze testomgeving in te stellen:
  
1. Het virtuele TestLab-netwerk configureren.
    
2. Het cross-premises virtuele netwerk maken.
    
3. DC2 configureren.
    
> [!NOTE]
> Voor deze configuratie is een betaald Azure-abonnement vereist. 

U kunt de resulterende omgeving gebruiken [](https://www.microsoft.com/microsoft-365/enterprise) om de functies en functionaliteit van Microsoft 365 voor bedrijven te testen met extra [Test Lab Guides](m365-enterprise-test-lab-guides.md) of alleen.

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Ga naar [Microsoft 365 voor enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack.

## <a name="phase-1-configure-the-testlab-virtual-network"></a>Fase 1: het virtuele TestLab-netwerk configureren.

Gebruik de instructies in **fase 1** van de [gesimuleerde enterprise base-configuratie](simulated-ent-base-configuration-microsoft-365-enterprise.md) om de DC1-, APP1- en CLIENT1-computers in het virtuele Azure-netwerk met de naam TestLab te configureren.
  
Dit is de huidige configuratie. 
  
![De gesimuleerde Enterprise-basisconfiguratie in Azure](../media/simulated-cross-premises-microsoft-365-enterprise/25a010a6-c870-4690-b8f3-84421f8bc5c7.png)
  
## <a name="phase-2-create-the-xprem-virtual-network"></a>Fase 2: het virtuele netwerk XPrem maken

In deze fase maakt en configureert u het nieuwe virtuele netwerk XPrem en verbindt u het vervolgens door middel van VNet-peering met het virtuele netwerk van TestLab.
  
Start eerst een Azure PowerShell-prompt op uw lokale computer.
  
> [!NOTE]
> De volgende opdrachtsets gebruiken de nieuwste versie van Azure PowerShell. Zie [Aan de slag met Azure PowerShell-cmdlets](/powershell/azureps-cmdlets-docs/). 
  
Meld u aan bij uw Azure-account met behulp van de volgende opdracht.
  
```powershell
Connect-AzAccount
```

Haal de naam van uw abonnement op met behulp van de volgende opdracht.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Stel uw Azure-abonnement in. Vervang alles binnen de aanhalingstekens, inclusief de \< and >-tekens, met de juiste namen.
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

Maak vervolgens het virtuele XPrem-netwerk en beveilig dit met een netwerkbeveiligingsgroep met deze opdrachten.
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$Testnet=New-AzVirtualNetworkSubnetConfig -Name "Testnet" -AddressPrefix 192.168.0.0/24
New-AzVirtualNetwork -Name "XPrem" -ResourceGroupName $rgName -Location $locName -AddressPrefix 192.168.0.0/16 -Subnet $Testnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
$nsg=Get-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "Testnet" -AddressPrefix 192.168.0.0/24 -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

Vervolgens maakt u met de volgende opdrachten de VNet-peeringrelatie tussen het TestLab en XPrem VNets.
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$vnet1=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$vnet2=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
Add-AzVirtualNetworkPeering -Name TestLab2XPrem -VirtualNetwork $vnet1 -RemoteVirtualNetworkId $vnet2.Id
Add-AzVirtualNetworkPeering -Name XPrem2TestLab -VirtualNetwork $vnet2 -RemoteVirtualNetworkId $vnet1.Id
```

Dit is de huidige configuratie. 
  
![Fase 2 van de gesimuleerde cross-premises virtuele netwerktestomgeving, met de XPrem VNet en de VNet-peering-relatie](../media/simulated-cross-premises-microsoft-365-enterprise/cac5e999-69c7-4f4c-bfce-a7f4006115ef.png)
  
## <a name="phase-3-configure-dc2"></a>Fase 3: DC2 configureren

In deze fase maakt u de virtuele DC2-machine in het virtuele XPrem-netwerk en configureert u deze vervolgens als een replicadomeincontroller.
  
Maak eerst een virtuele machine voor DC2. Voer deze opdrachten uit vanaf de opdrachtprompt van Azure PowerShell op uw lokale computer.
  
```powershell
$rgName="<your resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name XPrem -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC2-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC2-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 192.168.0.4
$vm=New-AzVMConfig -VMName DC2 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC2."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC2 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC2-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC2-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC2-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Maak vervolgens verbinding met de nieuwe virtuele DC2-machine vanuit de [Microsoft Azure-portal](https://portal.azure.com) met de naam en het wachtwoord van de lokale beheerdersaccount.
  
Configureer vervolgens een Windows Firewall-regel om verkeer toe te staan voor elementaire connectiviteitstests. Voer deze opdrachten uit vanaf een Windows PowerShell-opdrachtprompt op beheerdersniveau op DC2. 
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
ping dc1.corp.contoso.com
```

Het ping-commando moet resulteren in vier succesvolle antwoorden vanaf IP-adres 10.0.0.4. Dit is een test van het verkeer binnen de VNet-peering-relatie. 
  
Voeg vervolgens de extra gegevensschijf toe als een nieuw volume met de stationsletter F: met deze opdracht vanaf de opdrachtprompt van Windows PowerShell op DC2.
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Configureer vervolgens DC2 als een replicadomeincontroller voor het corp.contoso.com-domein. Voer deze opdrachten uit vanaf de Windows PowerShell-opdrachtprompt op DC2.
  
```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -Credential (Get-Credential CORP\User1) -DomainName "corp.contoso.com" -InstallDns:$true -DatabasePath "F:\NTDS" -LogPath "F:\Logs" -SysvolPath "F:\SYSVOL"
```

Merk op dat u wordt gevraagd om zowel het CORP\\ User1-wachtwoord als een Directory Services Restore Mode (DSRM) -wachtwoord op te geven en DC2 opnieuw te starten. 
  
Nu het virtuele XPrem-netwerk een eigen DNS-server (DC2) heeft, moet u het virtuele XPrem-netwerk configureren om deze DNS-server te gebruiken. Voer deze opdrachten uit vanaf de opdrachtprompt van Azure PowerShell op uw lokale computer.
  
```powershell
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -name "XPrem"
$vnet.DhcpOptions.DnsServers="192.168.0.4" 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $rgName -Name "DC2"
```

Maak vanuit de Microsoft Azure-portal op uw lokale computer verbinding met DC1 met de CORP\\User1-referenties. Om het CORP-domein zo te configureren dat computers en gebruikers hun lokale domeincontroller gebruiken voor verificatie, voert u deze opdrachten uit vanaf een Windows PowerShell-opdrachtprompt op beheerdersniveau op DC1.
  
```powershell
New-ADReplicationSite -Name "TestLab" 
New-ADReplicationSite -Name "XPrem"
New-ADReplicationSubnet -Name "10.0.0.0/8" -Site "TestLab"
New-ADReplicationSubnet -Name "192.168.0.0/16" -Site "XPrem"
```

Dit is de huidige configuratie. 
  
![Fase 3 van de testomgeving met de gesimuleerde cross-premises virtueel netwerkomgeving, met de virtuele DC2 machine in het XPrem VNet](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
De gesimuleerde Azure hybride cloudomgeving is nu gereed om getest te worden.
  
U bent nu klaar om te experimenteren met extra functies van [Microsoft 365 voor bedrijven.](https://www.microsoft.com/microsoft-365/enterprise)
  
## <a name="next-steps"></a>Volgende stappen

Verken de volgende extra sets testlabrichtlijnen:
  
- [Identiteit](m365-enterprise-test-lab-guides.md#identity)
- [Mobile Device Management](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Gegevensbeveiliging](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Microsoft 365 enterprise-documentatie](/microsoft-365-enterprise/)