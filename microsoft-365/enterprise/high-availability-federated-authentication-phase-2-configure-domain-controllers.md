---
title: Federatieverificatie met hoge beschikbaarheid Fase 2 Domeincontrollers configureren
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
description: 'Overzicht: Configureer de domeincontrollers en adreslijstsynchronisatieserver voor uw federatieverificatie met hoge beschikbaarheid voor Microsoft 365 in Microsoft Azure.'
ms.openlocfilehash: 751d332ce5f5606fe5f833182f002a1f4b6f29ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909808"
---
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a><span data-ttu-id="9a4cc-103">Federatief hoge beschikbaarheid fase 2: domeincontrollers configureren</span><span class="sxs-lookup"><span data-stu-id="9a4cc-103">High availability federated authentication Phase 2: Configure domain controllers</span></span>

<span data-ttu-id="9a4cc-104">In deze fase van het implementeren van hoge beschikbaarheid voor Microsoft 365 federatief verificatie in Azure-infrastructuurservices, configureert u twee domeincontrollers en de adreslijstsynchronisatieserver in het virtuele Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you configure two domain controllers and the directory synchronization server in the Azure virtual network.</span></span> <span data-ttu-id="9a4cc-105">Clientwebaanvragen voor verificatie kunnen vervolgens worden geverifieerd in het virtuele Azure-netwerk, in plaats van dat verificatieverkeer via de SITE-naar-site VPN-verbinding naar uw on-premises netwerk te verzenden.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-105">Client web requests for authentication can then be authenticated in the Azure virtual network, rather than sending that authentication traffic across the site-to-site VPN connection to your on-premises network.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9a4cc-106">Active Directory Federation Services (AD FS) kan Azure Active Directory (Azure AD) niet gebruiken als vervanging voor AD DS-domeincontrollers (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="9a4cc-106">Active Directory Federation Services (AD FS) cannot use Azure Active Directory (Azure AD) as a substitute for Active Directory Domain Services (AD DS) domain controllers.</span></span> 
  
<span data-ttu-id="9a4cc-107">U moet deze fase voltooien voordat u verder gaat [met fase 3: AD FS-servers configureren.](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md)</span><span class="sxs-lookup"><span data-stu-id="9a4cc-107">You must complete this phase before moving on to [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span></span> <span data-ttu-id="9a4cc-108">Zie [Federatieverificatie met hoge](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) beschikbaarheid implementeren voor Microsoft 365 in Azure voor alle fasen.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-108">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a><span data-ttu-id="9a4cc-109">Virtuele machines voor domeincontrollers maken in Azure</span><span class="sxs-lookup"><span data-stu-id="9a4cc-109">Create the domain controller virtual machines in Azure</span></span>

<span data-ttu-id="9a4cc-110">Eerst moet u de kolom Virtuele **machinenaam** van tabel M invullen en de grootte van virtuele machines zo nodig wijzigen in de **kolom Minimumgrootte.**</span><span class="sxs-lookup"><span data-stu-id="9a4cc-110">First, you need to fill out the **Virtual machine name** column of Table M and modify virtual machine sizes as needed in the **Minimum size** column.</span></span>
  
|<span data-ttu-id="9a4cc-111">**Item**</span><span class="sxs-lookup"><span data-stu-id="9a4cc-111">**Item**</span></span>|<span data-ttu-id="9a4cc-112">**Naam virtuele machine**</span><span class="sxs-lookup"><span data-stu-id="9a4cc-112">**Virtual machine name**</span></span>|<span data-ttu-id="9a4cc-113">**Galerieafbeelding**</span><span class="sxs-lookup"><span data-stu-id="9a4cc-113">**Gallery image**</span></span>|<span data-ttu-id="9a4cc-114">**Storage type**</span><span class="sxs-lookup"><span data-stu-id="9a4cc-114">**Storage type**</span></span>|<span data-ttu-id="9a4cc-115">**Minimumgrootte**</span><span class="sxs-lookup"><span data-stu-id="9a4cc-115">**Minimum size**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9a4cc-116">1.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-116">1.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png) <span data-ttu-id="9a4cc-118">(eerste domeincontroller, voorbeeld DC1)</span><span class="sxs-lookup"><span data-stu-id="9a4cc-118">(first domain controller, example DC1)</span></span>  <br/> |<span data-ttu-id="9a4cc-119">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="9a4cc-119">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="9a4cc-120">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="9a4cc-120">Standard_LRS</span></span>  <br/> |<span data-ttu-id="9a4cc-121">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="9a4cc-121">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="9a4cc-122">2.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-122">2.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png) <span data-ttu-id="9a4cc-124">(tweede domeincontroller, voorbeeld DC2)</span><span class="sxs-lookup"><span data-stu-id="9a4cc-124">(second domain controller, example DC2)</span></span>  <br/> |<span data-ttu-id="9a4cc-125">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="9a4cc-125">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="9a4cc-126">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="9a4cc-126">Standard_LRS</span></span>  <br/> |<span data-ttu-id="9a4cc-127">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="9a4cc-127">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="9a4cc-128">3.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-128">3.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png) <span data-ttu-id="9a4cc-130">(adreslijstsynchronisatieserver, bijvoorbeeld DS1)</span><span class="sxs-lookup"><span data-stu-id="9a4cc-130">(directory synchronization server, example DS1)</span></span>  <br/> |<span data-ttu-id="9a4cc-131">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="9a4cc-131">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="9a4cc-132">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="9a4cc-132">Standard_LRS</span></span>  <br/> |<span data-ttu-id="9a4cc-133">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="9a4cc-133">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="9a4cc-134">4.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-134">4.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png) <span data-ttu-id="9a4cc-136">(eerste AD FS-server, bijvoorbeeld ADFS1)</span><span class="sxs-lookup"><span data-stu-id="9a4cc-136">(first AD FS server, example ADFS1)</span></span>  <br/> |<span data-ttu-id="9a4cc-137">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="9a4cc-137">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="9a4cc-138">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="9a4cc-138">Standard_LRS</span></span>  <br/> |<span data-ttu-id="9a4cc-139">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="9a4cc-139">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="9a4cc-140">5.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-140">5.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png) <span data-ttu-id="9a4cc-142">(tweede AD FS-server, bijvoorbeeld ADFS2)</span><span class="sxs-lookup"><span data-stu-id="9a4cc-142">(second AD FS server, example ADFS2)</span></span>  <br/> |<span data-ttu-id="9a4cc-143">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="9a4cc-143">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="9a4cc-144">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="9a4cc-144">Standard_LRS</span></span>  <br/> |<span data-ttu-id="9a4cc-145">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="9a4cc-145">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="9a4cc-146">6.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-146">6.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png) <span data-ttu-id="9a4cc-148">(first web application proxy server, example WEB1)</span><span class="sxs-lookup"><span data-stu-id="9a4cc-148">(first web application proxy server, example WEB1)</span></span>  <br/> |<span data-ttu-id="9a4cc-149">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="9a4cc-149">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="9a4cc-150">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="9a4cc-150">Standard_LRS</span></span>  <br/> |<span data-ttu-id="9a4cc-151">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="9a4cc-151">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="9a4cc-152">7.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-152">7.</span></span>  <br/> |![regel](../media/Common-Images/TableLine.png) <span data-ttu-id="9a4cc-154">(tweede webtoepassingsproxyserver, voorbeeld WEB2)</span><span class="sxs-lookup"><span data-stu-id="9a4cc-154">(second web application proxy server, example WEB2)</span></span>  <br/> |<span data-ttu-id="9a4cc-155">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="9a4cc-155">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="9a4cc-156">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="9a4cc-156">Standard_LRS</span></span>  <br/> |<span data-ttu-id="9a4cc-157">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="9a4cc-157">Standard_D2</span></span>  <br/> |
   
 <span data-ttu-id="9a4cc-158">**Tabel M - Virtuele machines voor federatief hoge beschikbaarheid voor Microsoft 365 in Azure**</span><span class="sxs-lookup"><span data-stu-id="9a4cc-158">**Table M - Virtual machines for the high availability federated authentication for Microsoft 365 in Azure**</span></span>
  
<span data-ttu-id="9a4cc-159">Zie Groottes voor virtuele machines voor de volledige lijst met virtuele [machineformaten.](/azure/virtual-machines/virtual-machines-windows-sizes)</span><span class="sxs-lookup"><span data-stu-id="9a4cc-159">For the complete list of virtual machine sizes, see [Sizes for virtual machines](/azure/virtual-machines/virtual-machines-windows-sizes).</span></span>
  
<span data-ttu-id="9a4cc-160">Met de Azure PowerShell opdrachtblok worden de virtuele machines voor de twee domeincontrollers gemaakt.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-160">The following Azure PowerShell command block creates the virtual machines for the two domain controllers.</span></span> <span data-ttu-id="9a4cc-161">Geef de waarden op voor de variabelen en verwijder de \< and > tekens.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-161">Specify the values for the variables, removing the \< and > characters.</span></span> <span data-ttu-id="9a4cc-162">In dit Azure PowerShell opdrachtblok worden waarden uit de volgende tabellen gebruikt:</span><span class="sxs-lookup"><span data-stu-id="9a4cc-162">Note that this Azure PowerShell command block uses values from the following tables:</span></span>
  
- <span data-ttu-id="9a4cc-163">Tabel M, voor uw virtuele machines</span><span class="sxs-lookup"><span data-stu-id="9a4cc-163">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="9a4cc-164">Tabel R, voor uw resourcegroepen</span><span class="sxs-lookup"><span data-stu-id="9a4cc-164">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="9a4cc-165">Tabel V, voor uw virtuele netwerkinstellingen</span><span class="sxs-lookup"><span data-stu-id="9a4cc-165">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="9a4cc-166">Tabel S, voor uw subnetten</span><span class="sxs-lookup"><span data-stu-id="9a4cc-166">Table S, for your subnets</span></span>
    
- <span data-ttu-id="9a4cc-167">Tabel I, voor uw statische IP-adressen</span><span class="sxs-lookup"><span data-stu-id="9a4cc-167">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="9a4cc-168">Tabel A, voor uw beschikbaarheidssets</span><span class="sxs-lookup"><span data-stu-id="9a4cc-168">Table A, for your availability sets</span></span>
    
<span data-ttu-id="9a4cc-169">U hebt tabellen R, V, S, I en A gedefinieerd in [fase 1: Azure configureren.](high-availability-federated-authentication-phase-1-configure-azure.md)</span><span class="sxs-lookup"><span data-stu-id="9a4cc-169">Recall that you defined Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9a4cc-170">Met de volgende opdrachtsets wordt de meest recente versie van Azure PowerShell gebruikt.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-170">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="9a4cc-171">Zie [Aan de slag met Azure PowerShell.](/powershell/azure/get-started-azureps)</span><span class="sxs-lookup"><span data-stu-id="9a4cc-171">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="9a4cc-172">Wanneer u alle juiste waarden hebt opgegeven, kunt u het resulterende blok uitvoeren op de Azure PowerShell prompt of in de Geïntegreerde scriptomgeving van PowerShell (ISE) op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-172">When you have supplied all the correct values, run the resulting block at the Azure PowerShell prompt or in the PowerShell Integrated Script Environment (ISE) on your local computer.</span></span>
  
> [!TIP]
> <span data-ttu-id="9a4cc-173">Als u kant-en-klaar PowerShell-opdrachtblokken wilt genereren op basis van uw aangepaste instellingen, gebruikt u [deze Microsoft Excel configuratiewerkboek.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)</span><span class="sxs-lookup"><span data-stu-id="9a4cc-173">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

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
> <span data-ttu-id="9a4cc-174">Omdat deze virtuele machines voor een intranettoepassing zijn, krijgen ze geen openbaar IP-adres of een DNS-domeinnaamlabel toegewezen en worden ze blootgesteld aan internet.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-174">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet.</span></span> <span data-ttu-id="9a4cc-175">Dit betekent echter ook dat u geen verbinding met ze kunt maken vanuit de Azure-portal.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-175">However, this also means that you cannot connect to them from the Azure portal.</span></span> <span data-ttu-id="9a4cc-176">De **Verbinding maken** optie is niet beschikbaar wanneer u de eigenschappen van de virtuele computer bekijkt.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-176">The **Connect** option is unavailable when you view the properties of the virtual machine.</span></span> <span data-ttu-id="9a4cc-177">Gebruik het accessoire Extern bureaublad-verbinding of een ander hulpprogramma voor extern bureaublad om verbinding te maken met de virtuele computer met de dns-naam van het privé-IP-adres of intranet.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-177">Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name.</span></span>
  
## <a name="configure-the-first-domain-controller"></a><span data-ttu-id="9a4cc-178">De eerste domeincontroller configureren</span><span class="sxs-lookup"><span data-stu-id="9a4cc-178">Configure the first domain controller</span></span>

<span data-ttu-id="9a4cc-179">Gebruik de externe bureaubladclient van uw keuze en maak een externe bureaubladverbinding met de eerste virtuele domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-179">Use the remote desktop client of your choice and create a remote desktop connection to the first domain controller virtual machine.</span></span> <span data-ttu-id="9a4cc-180">Gebruik de intranet DNS- of computernaam en de referenties van het lokale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-180">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="9a4cc-181">Voeg vervolgens de extra gegevensschijf toe aan de eerste domeincontroller met deze opdracht vanaf Windows PowerShell opdrachtprompt op de eerste virtuele **domeincontroller:**</span><span class="sxs-lookup"><span data-stu-id="9a4cc-181">Next, add the extra data disk to the first domain controller with this command from a Windows PowerShell command prompt **on the first domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="9a4cc-182">Test vervolgens de connectiviteit van de eerste domeincontroller met locaties in uw organisatienetwerk door de **pingopdracht** te gebruiken om namen en IP-adressen van resources in uw organisatienetwerk te pingen.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-182">Next, test the first domain controller's connectivity to locations on your organization network by using the **ping** command to ping names and IP addresses of resources on your organization network.</span></span>
  
<span data-ttu-id="9a4cc-183">Deze procedure zorgt ervoor dat de DNS-naamresolutie correct werkt (dat de virtuele machine correct is geconfigureerd met on-premises DNS-servers) en dat pakketten van en naar het cross-premises virtuele netwerk kunnen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-183">This procedure ensures that DNS name resolution is working correctly (that the virtual machine is correctly configured with on-premises DNS servers) and that packets can be sent to and from the cross-premises virtual network.</span></span> <span data-ttu-id="9a4cc-184">Als deze basistest mislukt, neem dan contact op met uw IT-afdeling om de problemen met dns-naamoplossing en pakketbezorging op te lossen.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-184">If this basic test fails, contact your IT department to troubleshoot the DNS name resolution and packet delivery issues.</span></span>
  
<span data-ttu-id="9a4cc-185">Voer vervolgens vanuit de opdrachtprompt Windows PowerShell de eerste domeincontroller de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="9a4cc-185">Next, from the Windows PowerShell command prompt on the first domain controller, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

<span data-ttu-id="9a4cc-186">U wordt gevraagd de referenties van een domeinbeheerderaccount op te leveren.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-186">You will be prompted to supply the credentials of a domain administrator account.</span></span> <span data-ttu-id="9a4cc-187">De computer wordt opnieuw gestart.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-187">The computer will restart.</span></span>
  
## <a name="configure-the-second-domain-controller"></a><span data-ttu-id="9a4cc-188">De tweede domeincontroller configureren</span><span class="sxs-lookup"><span data-stu-id="9a4cc-188">Configure the second domain controller</span></span>

<span data-ttu-id="9a4cc-189">Gebruik de externe bureaubladclient van uw keuze en maak een externe bureaubladverbinding met de virtuele machine van de tweede domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-189">Use the remote desktop client of your choice and create a remote desktop connection to the second domain controller virtual machine.</span></span> <span data-ttu-id="9a4cc-190">Gebruik de intranet DNS- of computernaam en de referenties van het lokale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-190">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="9a4cc-191">Vervolgens moet u de extra gegevensschijf toevoegen aan de tweede domeincontroller met deze opdracht vanuit een opdrachtprompt Windows PowerShell op de virtuele machine van de tweede **domeincontroller:**</span><span class="sxs-lookup"><span data-stu-id="9a4cc-191">Next, you need to add the extra data disk to the second domain controller with this command from a Windows PowerShell command prompt **on the second domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="9a4cc-192">Voer vervolgens de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="9a4cc-192">Next, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

<span data-ttu-id="9a4cc-193">U wordt gevraagd de referenties van een domeinbeheerderaccount op te leveren.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-193">You will be prompted to supply the credentials of a domain administrator account.</span></span> <span data-ttu-id="9a4cc-194">De computer wordt opnieuw gestart.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-194">The computer will restart.</span></span>
  
<span data-ttu-id="9a4cc-195">Vervolgens moet u de DNS-servers voor uw virtuele netwerk bijwerken, zodat Azure virtuele machines de IP-adressen van de twee nieuwe domeincontrollers toewijst om te gebruiken als hun DNS-servers.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-195">Next, you need to update the DNS servers for your virtual network so that Azure assigns virtual machines the IP addresses of the two new domain controllers to use as their DNS servers.</span></span> <span data-ttu-id="9a4cc-196">Vul de variabelen in en voer deze opdrachten uit vanaf Windows PowerShell opdrachtprompt op uw lokale computer:</span><span class="sxs-lookup"><span data-stu-id="9a4cc-196">Fill in the variables and then run these commands from a Windows PowerShell command prompt on your local computer:</span></span>
  
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

<span data-ttu-id="9a4cc-197">Houd er rekening mee dat we de twee domeincontrollers opnieuw starten, zodat ze niet zijn geconfigureerd met de on-premises DNS-servers als DNS-servers.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-197">Note that we restart the two domain controllers so that they are not configured with the on-premises DNS servers as DNS servers.</span></span> <span data-ttu-id="9a4cc-198">Omdat ze beide DNS-servers zelf zijn, zijn ze automatisch geconfigureerd met de on-premises DNS-servers als DNS-doorsturende servers toen ze werden gepromoveerd naar domeincontrollers.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-198">Because they are both DNS servers themselves, they were automatically configured with the on-premises DNS servers as DNS forwarders when they were promoted to domain controllers.</span></span>
  
<span data-ttu-id="9a4cc-199">Vervolgens moeten we een Active Directory-replicatiesite maken om ervoor te zorgen dat servers in het virtuele Azure-netwerk gebruikmaken van de lokale domeincontrollers.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-199">Next, we need to create an Active Directory replication site to ensure that servers in the Azure virtual network use the local domain controllers.</span></span> <span data-ttu-id="9a4cc-200">Verbinding maken domeincontroller met een domeinbeheerderaccount en voer de volgende opdrachten uit vanaf een administratorniveau Windows PowerShell prompt:</span><span class="sxs-lookup"><span data-stu-id="9a4cc-200">Connect to either domain controller with a domain administrator account and run the following commands from an administrator-level Windows PowerShell prompt:</span></span>
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a><span data-ttu-id="9a4cc-201">De adreslijstsynchronisatieserver configureren</span><span class="sxs-lookup"><span data-stu-id="9a4cc-201">Configure the directory synchronization server</span></span>

<span data-ttu-id="9a4cc-202">Gebruik de externe bureaubladclient van uw keuze en maak een externe bureaubladverbinding met de virtuele computer van de adreslijstsynchronisatieserver.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-202">Use the remote desktop client of your choice and create a remote desktop connection to the directory synchronization server virtual machine.</span></span> <span data-ttu-id="9a4cc-203">Gebruik de intranet DNS- of computernaam en de referenties van het lokale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-203">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="9a4cc-204">Sluit u vervolgens aan bij het juiste AD DS-domein met deze opdrachten op de Windows PowerShell prompt.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-204">Next, join it to the appropriate AD DS domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

<span data-ttu-id="9a4cc-205">Hier is de configuratie die het resultaat is van de succesvolle voltooiing van deze fase, met computernamen van tijdelijke aanduidingen.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-205">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="9a4cc-206">**Fase 2: De domeincontrollers en adreslijstsynchronisatieserver voor uw federatief verificatie-infrastructuur met hoge beschikbaarheid in Azure**</span><span class="sxs-lookup"><span data-stu-id="9a4cc-206">**Phase 2: The domain controllers and directory synchronization server for your high availability federated authentication infrastructure in Azure**</span></span>

![Fase 2 van de hoge beschikbaarheid Microsoft 365 federatief verificatie-infrastructuur in Azure met domeincontrollers](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a><span data-ttu-id="9a4cc-208">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="9a4cc-208">Next step</span></span>

<span data-ttu-id="9a4cc-209">Fase [3: AD FS-servers configureren om](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) deze werkbelasting te blijven configureren.</span><span class="sxs-lookup"><span data-stu-id="9a4cc-209">Use [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9a4cc-210">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9a4cc-210">See Also</span></span>

[<span data-ttu-id="9a4cc-211">Federatieverificatie met hoge beschikbaarheid implementeren voor Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="9a4cc-211">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="9a4cc-212">Federatief identiteit voor uw Microsoft 365 v/testomgeving</span><span class="sxs-lookup"><span data-stu-id="9a4cc-212">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="9a4cc-213">Microsoft 365-oplossings- en -architectuurcentrum</span><span class="sxs-lookup"><span data-stu-id="9a4cc-213">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)