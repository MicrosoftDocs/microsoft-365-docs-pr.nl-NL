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
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a><span data-ttu-id="48292-103">Federatieve authenticatiefase van hoge beschikbaarheid 2: domeincontrollers configureren</span><span class="sxs-lookup"><span data-stu-id="48292-103">High availability federated authentication Phase 2: Configure domain controllers</span></span>

<span data-ttu-id="48292-104">In deze fase van de implementatie van hoge beschikbaarheid voor Microsoft 365 federatieve authenticatie in azure-infrastructuurservices configureert u twee domeincontrollers en de adreslijstsynchronisatie server in het virtuele Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="48292-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you configure two domain controllers and the directory synchronization server in the Azure virtual network.</span></span> <span data-ttu-id="48292-105">Client aanvragen voor verificatie kunnen vervolgens worden geverifieerd in het virtuele Azure-netwerk, in plaats van dit verificatieverkeer te verzenden via de site-naar-site VPN-verbinding met uw on-premises netwerk.</span><span class="sxs-lookup"><span data-stu-id="48292-105">Client web requests for authentication can then be authenticated in the Azure virtual network, rather than sending that authentication traffic across the site-to-site VPN connection to your on-premises network.</span></span>
  
> [!NOTE]
> <span data-ttu-id="48292-106">Active Directory Federation Services (AD FS) kan Azure Active Directory (Azure AD) niet gebruiken als vervanging voor domeincontrollers met Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="48292-106">Active Directory Federation Services (AD FS) cannot use Azure Active Directory (Azure AD) as a substitute for Active Directory Domain Services (AD DS) domain controllers.</span></span> 
  
<span data-ttu-id="48292-107">U moet deze fase voltooien voordat u overstapt naar [fase 3: AD FS-servers configureren](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span><span class="sxs-lookup"><span data-stu-id="48292-107">You must complete this phase before moving on to [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span></span> <span data-ttu-id="48292-108">Zie [federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) voor alle fasen.</span><span class="sxs-lookup"><span data-stu-id="48292-108">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a><span data-ttu-id="48292-109">De virtuele machines van de domeincontroller in azure maken</span><span class="sxs-lookup"><span data-stu-id="48292-109">Create the domain controller virtual machines in Azure</span></span>

<span data-ttu-id="48292-110">U moet eerst de kolom **naam van virtuele machine** van tabel M invullen en de grootte van virtuele machines naar wens wijzigen in de kolom **minimale grootte** .</span><span class="sxs-lookup"><span data-stu-id="48292-110">First, you need to fill out the **Virtual machine name** column of Table M and modify virtual machine sizes as needed in the **Minimum size** column.</span></span>
  
|<span data-ttu-id="48292-111">**Item**</span><span class="sxs-lookup"><span data-stu-id="48292-111">**Item**</span></span>|<span data-ttu-id="48292-112">**Naam virtuele machine**</span><span class="sxs-lookup"><span data-stu-id="48292-112">**Virtual machine name**</span></span>|<span data-ttu-id="48292-113">**Afbeelding van galerie**</span><span class="sxs-lookup"><span data-stu-id="48292-113">**Gallery image**</span></span>|<span data-ttu-id="48292-114">**Type opslag**</span><span class="sxs-lookup"><span data-stu-id="48292-114">**Storage type**</span></span>|<span data-ttu-id="48292-115">**Minimale grootte**</span><span class="sxs-lookup"><span data-stu-id="48292-115">**Minimum size**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="48292-116">1.</span><span class="sxs-lookup"><span data-stu-id="48292-116">1.</span></span>  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) <span data-ttu-id="48292-118">(eerste domeincontroller, voorbeeld DC1)</span><span class="sxs-lookup"><span data-stu-id="48292-118">(first domain controller, example DC1)</span></span>  <br/> |<span data-ttu-id="48292-119">Windows Server 2016 datacenter</span><span class="sxs-lookup"><span data-stu-id="48292-119">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="48292-120">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="48292-120">Standard_LRS</span></span>  <br/> |<span data-ttu-id="48292-121">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="48292-121">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="48292-122">2.</span><span class="sxs-lookup"><span data-stu-id="48292-122">2.</span></span>  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) <span data-ttu-id="48292-124">(tweede domeincontroller, bijvoorbeeld DC2)</span><span class="sxs-lookup"><span data-stu-id="48292-124">(second domain controller, example DC2)</span></span>  <br/> |<span data-ttu-id="48292-125">Windows Server 2016 datacenter</span><span class="sxs-lookup"><span data-stu-id="48292-125">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="48292-126">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="48292-126">Standard_LRS</span></span>  <br/> |<span data-ttu-id="48292-127">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="48292-127">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="48292-128">3.</span><span class="sxs-lookup"><span data-stu-id="48292-128">3.</span></span>  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) <span data-ttu-id="48292-130">(adreslijstsynchronisatie server, voorbeeld DS1)</span><span class="sxs-lookup"><span data-stu-id="48292-130">(directory synchronization server, example DS1)</span></span>  <br/> |<span data-ttu-id="48292-131">Windows Server 2016 datacenter</span><span class="sxs-lookup"><span data-stu-id="48292-131">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="48292-132">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="48292-132">Standard_LRS</span></span>  <br/> |<span data-ttu-id="48292-133">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="48292-133">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="48292-134">4.</span><span class="sxs-lookup"><span data-stu-id="48292-134">4.</span></span>  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) <span data-ttu-id="48292-136">(eerste AD FS-server, bijvoorbeeld ADFS1)</span><span class="sxs-lookup"><span data-stu-id="48292-136">(first AD FS server, example ADFS1)</span></span>  <br/> |<span data-ttu-id="48292-137">Windows Server 2016 datacenter</span><span class="sxs-lookup"><span data-stu-id="48292-137">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="48292-138">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="48292-138">Standard_LRS</span></span>  <br/> |<span data-ttu-id="48292-139">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="48292-139">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="48292-140">5.</span><span class="sxs-lookup"><span data-stu-id="48292-140">5.</span></span>  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) <span data-ttu-id="48292-142">(tweede AD FS-server, bijvoorbeeld ADFS2)</span><span class="sxs-lookup"><span data-stu-id="48292-142">(second AD FS server, example ADFS2)</span></span>  <br/> |<span data-ttu-id="48292-143">Windows Server 2016 datacenter</span><span class="sxs-lookup"><span data-stu-id="48292-143">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="48292-144">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="48292-144">Standard_LRS</span></span>  <br/> |<span data-ttu-id="48292-145">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="48292-145">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="48292-146">zes.</span><span class="sxs-lookup"><span data-stu-id="48292-146">6.</span></span>  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) <span data-ttu-id="48292-148">(eerste webtoepassingsproxy-server, bijvoorbeeld WEB1)</span><span class="sxs-lookup"><span data-stu-id="48292-148">(first web application proxy server, example WEB1)</span></span>  <br/> |<span data-ttu-id="48292-149">Windows Server 2016 datacenter</span><span class="sxs-lookup"><span data-stu-id="48292-149">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="48292-150">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="48292-150">Standard_LRS</span></span>  <br/> |<span data-ttu-id="48292-151">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="48292-151">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="48292-152">7,5.</span><span class="sxs-lookup"><span data-stu-id="48292-152">7.</span></span>  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) <span data-ttu-id="48292-154">(tweede webtoepassingsproxy-server, bijvoorbeeld WEB2)</span><span class="sxs-lookup"><span data-stu-id="48292-154">(second web application proxy server, example WEB2)</span></span>  <br/> |<span data-ttu-id="48292-155">Windows Server 2016 datacenter</span><span class="sxs-lookup"><span data-stu-id="48292-155">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="48292-156">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="48292-156">Standard_LRS</span></span>  <br/> |<span data-ttu-id="48292-157">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="48292-157">Standard_D2</span></span>  <br/> |
   
 <span data-ttu-id="48292-158">**Tabel M-virtuele machines voor de federatieve verificatie van hoge beschikbaarheid voor Microsoft 365 in azure**</span><span class="sxs-lookup"><span data-stu-id="48292-158">**Table M - Virtual machines for the high availability federated authentication for Microsoft 365 in Azure**</span></span>
  
<span data-ttu-id="48292-159">Zie [formaten voor virtuele machines](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-sizes)voor de volledige lijst met formaten voor virtuele machines.</span><span class="sxs-lookup"><span data-stu-id="48292-159">For the complete list of virtual machine sizes, see [Sizes for virtual machines](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-sizes).</span></span>
  
<span data-ttu-id="48292-160">Met de volgende Azure PowerShell-opdracht blokkering maakt u de virtuele machines voor de twee domeincontrollers.</span><span class="sxs-lookup"><span data-stu-id="48292-160">The following Azure PowerShell command block creates the virtual machines for the two domain controllers.</span></span> <span data-ttu-id="48292-161">Geef de waarden voor de variabelen op en verwijder de \< and > tekens.</span><span class="sxs-lookup"><span data-stu-id="48292-161">Specify the values for the variables, removing the \< and > characters.</span></span> <span data-ttu-id="48292-162">Houd er rekening mee dat deze Azure PowerShell-opdracht blokkering waarden uit de volgende tabellen gebruikt:</span><span class="sxs-lookup"><span data-stu-id="48292-162">Note that this Azure PowerShell command block uses values from the following tables:</span></span>
  
- <span data-ttu-id="48292-163">Tabel M voor uw virtuele machines</span><span class="sxs-lookup"><span data-stu-id="48292-163">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="48292-164">Tabel R voor de resourcegroepen</span><span class="sxs-lookup"><span data-stu-id="48292-164">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="48292-165">Tabel V voor de instellingen van uw virtuele netwerk</span><span class="sxs-lookup"><span data-stu-id="48292-165">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="48292-166">Tabel S voor de subnetten</span><span class="sxs-lookup"><span data-stu-id="48292-166">Table S, for your subnets</span></span>
    
- <span data-ttu-id="48292-167">Tabel I voor uw vaste IP-adressen</span><span class="sxs-lookup"><span data-stu-id="48292-167">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="48292-168">Tabel A voor uw beschikbaarheidssets</span><span class="sxs-lookup"><span data-stu-id="48292-168">Table A, for your availability sets</span></span>
    
<span data-ttu-id="48292-169">Het intrekken van tabellen R, V, S, I en A in [fase 1: Azure configureren](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="48292-169">Recall that you defined Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="48292-170">Met de volgende opdrachtsets wordt de meest recente versie van Azure PowerShell gebruikt.</span><span class="sxs-lookup"><span data-stu-id="48292-170">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="48292-171">Zie [aan de slag met Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="48292-171">See [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="48292-172">Wanneer u alle juiste waarden hebt opgegeven, voert u het door u gewenste blok uit via de Azure PowerShell-prompt of in de ISE (Integrated script Environment) van PowerShell op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="48292-172">When you have supplied all the correct values, run the resulting block at the Azure PowerShell prompt or in the PowerShell Integrated Script Environment (ISE) on your local computer.</span></span>
  
> [!TIP]
> <span data-ttu-id="48292-173">Als u kant-en-klare PowerShell-opdrachten blokken wilt genereren op basis van uw aangepaste instellingen, gebruikt u deze [Microsoft Excel-configuratie werkmap](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span><span class="sxs-lookup"><span data-stu-id="48292-173">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

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
> <span data-ttu-id="48292-174">Omdat deze virtuele machines zijn bedoeld voor een intranet toepassing, worden er geen openbaar IP-adres of een DNS-domeinnaamlabel toegewezen en op internet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="48292-174">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet.</span></span> <span data-ttu-id="48292-175">Dit houdt in dat u dit echter ook kunt verbinden met de Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="48292-175">However, this also means that you cannot connect to them from the Azure portal.</span></span> <span data-ttu-id="48292-176">De optie **verbinding** is niet beschikbaar wanneer u de eigenschappen van de virtuele computer bekijkt.</span><span class="sxs-lookup"><span data-stu-id="48292-176">The **Connect** option is unavailable when you view the properties of the virtual machine.</span></span> <span data-ttu-id="48292-177">Gebruik de accessor van het extern bureaublad of een ander hulpprogramma voor extern bureaublad om verbinding te maken met de virtuele machine met behulp van de bijbehorende persoonlijke IP-adressen of intranet namen.</span><span class="sxs-lookup"><span data-stu-id="48292-177">Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name.</span></span>
  
## <a name="configure-the-first-domain-controller"></a><span data-ttu-id="48292-178">De eerste domeincontroller configureren</span><span class="sxs-lookup"><span data-stu-id="48292-178">Configure the first domain controller</span></span>

<span data-ttu-id="48292-179">Gebruik de externe bureaubladclient van uw keuze en maak een verbinding met extern bureaublad met de eerste virtuele machine van de domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="48292-179">Use the remote desktop client of your choice and create a remote desktop connection to the first domain controller virtual machine.</span></span> <span data-ttu-id="48292-180">Gebruik de intranet-of computernaam van het intranet en de referenties van het lokale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="48292-180">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="48292-181">Vervolgens voegt u de extra gegevensschijf toe aan de eerste domeincontroller met deze opdracht vanaf een Windows PowerShell-opdrachtprompt **op de eerste virtuele domeincontroller**:</span><span class="sxs-lookup"><span data-stu-id="48292-181">Next, add the extra data disk to the first domain controller with this command from a Windows PowerShell command prompt **on the first domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="48292-182">Test vervolgens de verbinding van de eerste domeincontroller met locaties in het netwerk met de opdracht **ping** om namen en IP-adressen van bronnen in het netwerk van uw organisatie te pingen.</span><span class="sxs-lookup"><span data-stu-id="48292-182">Next, test the first domain controller's connectivity to locations on your organization network by using the **ping** command to ping names and IP addresses of resources on your organization network.</span></span>
  
<span data-ttu-id="48292-183">Met deze procedure wordt gecontroleerd of de DNS-naamomzetting correct werkt (dat de virtuele machine correct is geconfigureerd met on-premises DNS-servers) en dat pakketten naar het virtuele netwerk van cross-premises kunnen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="48292-183">This procedure ensures that DNS name resolution is working correctly (that the virtual machine is correctly configured with on-premises DNS servers) and that packets can be sent to and from the cross-premises virtual network.</span></span> <span data-ttu-id="48292-184">Neem contact op met uw IT-afdeling voor het oplossen van problemen met de DNS-naamomzetting en pakket bezorging als deze basistest mislukt.</span><span class="sxs-lookup"><span data-stu-id="48292-184">If this basic test fails, contact your IT department to troubleshoot the DNS name resolution and packet delivery issues.</span></span>
  
<span data-ttu-id="48292-185">Voer vervolgens de volgende opdrachten uit vanaf de Windows PowerShell-opdrachtprompt op de eerste domeincontroller:</span><span class="sxs-lookup"><span data-stu-id="48292-185">Next, from the Windows PowerShell command prompt on the first domain controller, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

<span data-ttu-id="48292-186">U wordt gevraagd om de referenties van een domeinbeheerdersaccount op te geven.</span><span class="sxs-lookup"><span data-stu-id="48292-186">You will be prompted to supply the credentials of a domain administrator account.</span></span> <span data-ttu-id="48292-187">De computer wordt opnieuw gestart.</span><span class="sxs-lookup"><span data-stu-id="48292-187">The computer will restart.</span></span>
  
## <a name="configure-the-second-domain-controller"></a><span data-ttu-id="48292-188">De tweede domeincontroller configureren</span><span class="sxs-lookup"><span data-stu-id="48292-188">Configure the second domain controller</span></span>

<span data-ttu-id="48292-189">Gebruik de externe bureaubladclient van uw keuze en maak een verbinding met extern bureaublad met de tweede virtuele machine van de domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="48292-189">Use the remote desktop client of your choice and create a remote desktop connection to the second domain controller virtual machine.</span></span> <span data-ttu-id="48292-190">Gebruik de intranet-of computernaam van het intranet en de referenties van het lokale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="48292-190">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="48292-191">Vervolgens moet u de extra gegevensschijf toevoegen aan de tweede domeincontroller met deze opdracht vanaf een Windows PowerShell-opdrachtprompt **op de tweede virtuele machine van de domeincontroller**:</span><span class="sxs-lookup"><span data-stu-id="48292-191">Next, you need to add the extra data disk to the second domain controller with this command from a Windows PowerShell command prompt **on the second domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="48292-192">Voer vervolgens de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="48292-192">Next, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

<span data-ttu-id="48292-193">U wordt gevraagd om de referenties van een domeinbeheerdersaccount op te geven.</span><span class="sxs-lookup"><span data-stu-id="48292-193">You will be prompted to supply the credentials of a domain administrator account.</span></span> <span data-ttu-id="48292-194">De computer wordt opnieuw gestart.</span><span class="sxs-lookup"><span data-stu-id="48292-194">The computer will restart.</span></span>
  
<span data-ttu-id="48292-195">Vervolgens moet u de DNS-servers voor uw virtuele netwerk bijwerken, zodat via Azure virtuele machines worden toegewezen aan de IP-adressen van de twee nieuwe domeincontrollers die als DNS-servers moeten worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="48292-195">Next, you need to update the DNS servers for your virtual network so that Azure assigns virtual machines the IP addresses of the two new domain controllers to use as their DNS servers.</span></span> <span data-ttu-id="48292-196">Vul de variabelen in en voer deze opdrachten uit vanaf een Windows PowerShell-opdrachtprompt op uw lokale computer:</span><span class="sxs-lookup"><span data-stu-id="48292-196">Fill in the variables and then run these commands from a Windows PowerShell command prompt on your local computer:</span></span>
  
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

<span data-ttu-id="48292-197">U moet de twee domeincontrollers opnieuw opstarten, zodat ze niet worden geconfigureerd met de on-premises DNS-servers als DNS-servers.</span><span class="sxs-lookup"><span data-stu-id="48292-197">Note that we restart the two domain controllers so that they are not configured with the on-premises DNS servers as DNS servers.</span></span> <span data-ttu-id="48292-198">Aangezien beide DNS-servers zelf zijn, worden ze automatisch geconfigureerd met de on-premises DNS-servers als DNS-doorstuurservers wanneer ze worden gepromoveerd naar domeincontrollers.</span><span class="sxs-lookup"><span data-stu-id="48292-198">Because they are both DNS servers themselves, they were automatically configured with the on-premises DNS servers as DNS forwarders when they were promoted to domain controllers.</span></span>
  
<span data-ttu-id="48292-199">Vervolgens moet u een Active Directory-replicatie site maken om ervoor te zorgen dat servers in het Azure Virtual Network gebruikmaken van lokale domeincontrollers.</span><span class="sxs-lookup"><span data-stu-id="48292-199">Next, we need to create an Active Directory replication site to ensure that servers in the Azure virtual network use the local domain controllers.</span></span> <span data-ttu-id="48292-200">Maak verbinding met de domeincontroller met een domeinbeheerdersaccount en voer de volgende opdrachten uit op een Windows PowerShell-prompt op beheerderniveau:</span><span class="sxs-lookup"><span data-stu-id="48292-200">Connect to either domain controller with a domain administrator account and run the following commands from an administrator-level Windows PowerShell prompt:</span></span>
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a><span data-ttu-id="48292-201">De adreslijstsynchronisatie server configureren</span><span class="sxs-lookup"><span data-stu-id="48292-201">Configure the directory synchronization server</span></span>

<span data-ttu-id="48292-202">Gebruik de externe bureaubladclient van uw keuze en maak een verbinding met extern bureaublad met de virtuele machine van de adreslijstsynchronisatie server.</span><span class="sxs-lookup"><span data-stu-id="48292-202">Use the remote desktop client of your choice and create a remote desktop connection to the directory synchronization server virtual machine.</span></span> <span data-ttu-id="48292-203">Gebruik de intranet-of computernaam van het intranet en de referenties van het lokale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="48292-203">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="48292-204">Vervolgens voegt u dit toe aan het juiste AD DS-domein met deze opdrachten op de Windows PowerShell-prompt.</span><span class="sxs-lookup"><span data-stu-id="48292-204">Next, join it to the appropriate AD DS domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

<span data-ttu-id="48292-205">Dit is de configuratie die het resultaat is van de succesvolle voltooiing van deze fase, met tijdelijke aanduidingen voor de computernamen.</span><span class="sxs-lookup"><span data-stu-id="48292-205">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="48292-206">**Fase 2: de domeincontrollers en adreslijstsynchronisatie server voor uw federatieve authenticatie-infrastructuur voor hoge beschikbaarheid in azure**</span><span class="sxs-lookup"><span data-stu-id="48292-206">**Phase 2: The domain controllers and directory synchronization server for your high availability federated authentication infrastructure in Azure**</span></span>

![Fase 2 van de ' hoge beschikbaarheid Microsoft 365 federatieve verificatie-infrastructuur in azure met domeincontrollers](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a><span data-ttu-id="48292-208">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="48292-208">Next step</span></span>

<span data-ttu-id="48292-209">Gebruik [fase 3: Configureer de AD FS-servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) om door te gaan met het configureren van deze werkbelasting.</span><span class="sxs-lookup"><span data-stu-id="48292-209">Use [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="48292-210">Zie ook</span><span class="sxs-lookup"><span data-stu-id="48292-210">See Also</span></span>

[<span data-ttu-id="48292-211">Federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure</span><span class="sxs-lookup"><span data-stu-id="48292-211">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="48292-212">Federatieve identiteit voor uw Microsoft 365 dev/testomgeving</span><span class="sxs-lookup"><span data-stu-id="48292-212">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="48292-213">Microsoft 365-oplossingen- en -architectuurcentrum</span><span class="sxs-lookup"><span data-stu-id="48292-213">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)


