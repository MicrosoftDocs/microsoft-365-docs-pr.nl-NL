---
title: Federatieve authenticatiefase 2 van hoge beschikbaarheid domeincontrollers configureren
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
ms.assetid: 6b0eff4c-2c5e-4581-8393-a36f7b36a72f
description: 'Overzicht: Configureer de domeincontrollers en adreslijstsynchronisatie server voor uw federatieve authenticatie van hoge beschikbaarheid voor Microsoft 365 in Microsoft Azure.'
ms.openlocfilehash: 1c3fd686ee553a57d66dcfd51a6045167a12de8a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689337"
---
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a>Federatieve authenticatiefase van hoge beschikbaarheid 2: domeincontrollers configureren

In deze fase van de implementatie van hoge beschikbaarheid voor Microsoft 365 federatieve authenticatie in azure-infrastructuurservices configureert u twee domeincontrollers en de adreslijstsynchronisatie server in het virtuele Azure-netwerk. Client aanvragen voor verificatie kunnen vervolgens worden geverifieerd in het virtuele Azure-netwerk, in plaats van dit verificatieverkeer te verzenden via de site-naar-site VPN-verbinding met uw on-premises netwerk.
  
> [!NOTE]
> Active Directory Federation Services (AD FS) kan Azure Active Directory (Azure AD) niet gebruiken als vervanging voor domeincontrollers met Active Directory Domain Services (AD DS). 
  
U moet deze fase voltooien voordat u overstapt naar [fase 3: AD FS-servers configureren](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md). Zie [federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) voor alle fasen.
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a>De virtuele machines van de domeincontroller in azure maken

U moet eerst de kolom **naam van virtuele machine** van tabel M invullen en de grootte van virtuele machines naar wens wijzigen in de kolom **minimale grootte** .
  
|**Item**|**Naam virtuele machine**|**Afbeelding van galerie**|**Type opslag**|**Minimale grootte**|
|:-----|:-----|:-----|:-----|:-----|
|1.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) (eerste domeincontroller, voorbeeld DC1)  <br/> |Windows Server 2016 datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|2.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) (tweede domeincontroller, bijvoorbeeld DC2)  <br/> |Windows Server 2016 datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|3.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) (adreslijstsynchronisatie server, voorbeeld DS1)  <br/> |Windows Server 2016 datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|4.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) (eerste AD FS-server, bijvoorbeeld ADFS1)  <br/> |Windows Server 2016 datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|5.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) (tweede AD FS-server, bijvoorbeeld ADFS2)  <br/> |Windows Server 2016 datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|zes.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) (eerste webtoepassingsproxy-server, bijvoorbeeld WEB1)  <br/> |Windows Server 2016 datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|7,5.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) (tweede webtoepassingsproxy-server, bijvoorbeeld WEB2)  <br/> |Windows Server 2016 datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
   
 **Tabel M-virtuele machines voor de federatieve verificatie van hoge beschikbaarheid voor Microsoft 365 in azure**
  
Zie [formaten voor virtuele machines](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-sizes)voor de volledige lijst met formaten voor virtuele machines.
  
Met de volgende Azure PowerShell-opdracht blokkering maakt u de virtuele machines voor de twee domeincontrollers. Geef de waarden voor de variabelen op en verwijder de \< and > tekens. Houd er rekening mee dat deze Azure PowerShell-opdracht blokkering waarden uit de volgende tabellen gebruikt:
  
- Tabel M voor uw virtuele machines
    
- Tabel R voor de resourcegroepen
    
- Tabel V voor de instellingen van uw virtuele netwerk
    
- Tabel S voor de subnetten
    
- Tabel I voor uw vaste IP-adressen
    
- Tabel A voor uw beschikbaarheidssets
    
Het intrekken van tabellen R, V, S, I en A in [fase 1: Azure configureren](high-availability-federated-authentication-phase-1-configure-azure.md).
  
> [!NOTE]
> Met de volgende opdrachtsets wordt de meest recente versie van Azure PowerShell gebruikt. Zie [aan de slag met Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps). 
  
Wanneer u alle juiste waarden hebt opgegeven, voert u het door u gewenste blok uit via de Azure PowerShell-prompt of in de ISE (Integrated script Environment) van PowerShell op uw lokale computer.
  
> [!TIP]
> Als u kant-en-klare PowerShell-opdrachten blokken wilt genereren op basis van uw aangepaste instellingen, gebruikt u deze [Microsoft Excel-configuratie werkmap](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx). 

```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table S - Item 1 - Value column>"
$avName="<Table A - Item 1 - Availability set name column>"
$rgNameTier="<Table R - Item 1 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName 

# Create the first domain controller
$vmName="<Table M - Item 1 - Virtual machine name column>"
$vmSize="<Table M - Item 1 - Minimum size column>"
$staticIP="<Table I - Item 1 - Value column>"
$diskStorageType="<Table M - Item 1 - Storage type column>"
$diskSize=<size of the extra disk for Active Directory Domain Services (AD DS) data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second domain controller
$vmName="<Table M - Item 2 - Virtual machine name column>"
$vmSize="<Table M - Item 2 - Minimum size column>"
$staticIP="<Table I - Item 2 - Value column>"
$diskStorageType="<Table M - Item 2 - Storage type column>"
$diskSize=<size of the extra disk for AD DS data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the directory synchronization server
$vmName="<Table M - Item 3 - Virtual machine name column>"
$vmSize="<Table M - Item 3 - Minimum size column>"
$staticIP="<Table I - Item 3 - Value column>"
$diskStorageType="<Table M - Item 3 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the directory synchronization server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> Omdat deze virtuele machines zijn bedoeld voor een intranet toepassing, worden er geen openbaar IP-adres of een DNS-domeinnaamlabel toegewezen en op internet weergegeven. Dit houdt in dat u dit echter ook kunt verbinden met de Azure-Portal. De optie **verbinding** is niet beschikbaar wanneer u de eigenschappen van de virtuele computer bekijkt. Gebruik de accessor van het extern bureaublad of een ander hulpprogramma voor extern bureaublad om verbinding te maken met de virtuele machine met behulp van de bijbehorende persoonlijke IP-adressen of intranet namen.
  
## <a name="configure-the-first-domain-controller"></a>De eerste domeincontroller configureren

Gebruik de externe bureaubladclient van uw keuze en maak een verbinding met extern bureaublad met de eerste virtuele machine van de domeincontroller. Gebruik de intranet-of computernaam van het intranet en de referenties van het lokale beheerdersaccount.
  
Vervolgens voegt u de extra gegevensschijf toe aan de eerste domeincontroller met deze opdracht vanaf een Windows PowerShell-opdrachtprompt **op de eerste virtuele domeincontroller**:
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Test vervolgens de verbinding van de eerste domeincontroller met locaties in het netwerk met de opdracht **ping** om namen en IP-adressen van bronnen in het netwerk van uw organisatie te pingen.
  
Met deze procedure wordt gecontroleerd of de DNS-naamomzetting correct werkt (dat de virtuele machine correct is geconfigureerd met on-premises DNS-servers) en dat pakketten naar het virtuele netwerk van cross-premises kunnen worden verzonden. Neem contact op met uw IT-afdeling voor het oplossen van problemen met de DNS-naamomzetting en pakket bezorging als deze basistest mislukt.
  
Voer vervolgens de volgende opdrachten uit vanaf de Windows PowerShell-opdrachtprompt op de eerste domeincontroller:
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

U wordt gevraagd om de referenties van een domeinbeheerdersaccount op te geven. De computer wordt opnieuw gestart.
  
## <a name="configure-the-second-domain-controller"></a>De tweede domeincontroller configureren

Gebruik de externe bureaubladclient van uw keuze en maak een verbinding met extern bureaublad met de tweede virtuele machine van de domeincontroller. Gebruik de intranet-of computernaam van het intranet en de referenties van het lokale beheerdersaccount.
  
Vervolgens moet u de extra gegevensschijf toevoegen aan de tweede domeincontroller met deze opdracht vanaf een Windows PowerShell-opdrachtprompt **op de tweede virtuele machine van de domeincontroller**:
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Voer vervolgens de volgende opdrachten uit:
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

U wordt gevraagd om de referenties van een domeinbeheerdersaccount op te geven. De computer wordt opnieuw gestart.
  
Vervolgens moet u de DNS-servers voor uw virtuele netwerk bijwerken, zodat via Azure virtuele machines worden toegewezen aan de IP-adressen van de twee nieuwe domeincontrollers die als DNS-servers moeten worden gebruikt. Vul de variabelen in en voer deze opdrachten uit vanaf een Windows PowerShell-opdrachtprompt op uw lokale computer:
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$adrgName="<Table R - Item 1 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$onpremDNSIP1="<Table D - Item 1 - DNS server IP address column>"
$onpremDNSIP2="<Table D - Item 2 - DNS server IP address column>"
$staticIP1="<Table I - Item 1 - Value column>"
$staticIP2="<Table I - Item 2 - Value column>"
$firstDCName="<Table M - Item 1 - Virtual machine name column>"
$secondDCName="<Table M - Item 2 - Virtual machine name column>"

$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$vnet.DhcpOptions.DnsServers.Add($staticIP1)
$vnet.DhcpOptions.DnsServers.Add($staticIP2) 
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP1)
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP2) 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $adrgName -Name $firstDCName
Restart-AzVM -ResourceGroupName $adrgName -Name $secondDCName
```

U moet de twee domeincontrollers opnieuw opstarten, zodat ze niet worden geconfigureerd met de on-premises DNS-servers als DNS-servers. Aangezien beide DNS-servers zelf zijn, worden ze automatisch geconfigureerd met de on-premises DNS-servers als DNS-doorstuurservers wanneer ze worden gepromoveerd naar domeincontrollers.
  
Vervolgens moet u een Active Directory-replicatie site maken om ervoor te zorgen dat servers in het Azure Virtual Network gebruikmaken van lokale domeincontrollers. Maak verbinding met de domeincontroller met een domeinbeheerdersaccount en voer de volgende opdrachten uit op een Windows PowerShell-prompt op beheerderniveau:
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a>De adreslijstsynchronisatie server configureren

Gebruik de externe bureaubladclient van uw keuze en maak een verbinding met extern bureaublad met de virtuele machine van de adreslijstsynchronisatie server. Gebruik de intranet-of computernaam van het intranet en de referenties van het lokale beheerdersaccount.
  
Vervolgens voegt u dit toe aan het juiste AD DS-domein met deze opdrachten op de Windows PowerShell-prompt.
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

Dit is de configuratie die het resultaat is van de succesvolle voltooiing van deze fase, met tijdelijke aanduidingen voor de computernamen.
  
**Fase 2: de domeincontrollers en adreslijstsynchronisatie server voor uw federatieve authenticatie-infrastructuur voor hoge beschikbaarheid in azure**

![Fase 2 van de ' hoge beschikbaarheid Microsoft 365 federatieve verificatie-infrastructuur in azure met domeincontrollers](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a>Volgende stap

Gebruik [fase 3: Configureer de AD FS-servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) om door te gaan met het configureren van deze werkbelasting.
  
## <a name="see-also"></a>Zie ook

[Federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Federatieve identiteit voor uw Microsoft 365 dev/testomgeving](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365-oplossingen- en -architectuurcentrum](../solutions/solution-architecture-center.md)


