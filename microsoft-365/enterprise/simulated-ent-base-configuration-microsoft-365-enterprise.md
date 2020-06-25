---
title: 'Basisconfiguratie voor gesimuleerde enterprise Microsoft 365 '
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Gebruik deze Testlabrichtlijnen om een gesimuleerde Enterprise-testomgeving te maken voor Microsoft 365 Enterprise.
ms.openlocfilehash: 486429bf9e1c0a88c9beb01a092f968256c1fa77
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818493"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="a39b2-103">De basisconfiguratie voor een gesimuleerde Enterprise</span><span class="sxs-lookup"><span data-stu-id="a39b2-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="a39b2-104">*Deze testlabrichtlijnen kunnen worden gebruikt voor zowel Microsoft 365 Enterprise- en Office 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="a39b2-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="a39b2-105">In dit artikel vindt u stapsgewijze instructies voor het maken van een vereenvoudigde omgeving voor Microsoft 365 Enterprise die het volgende bevat:</span><span class="sxs-lookup"><span data-stu-id="a39b2-105">This article provides you with step-by-step instructions to create a simplified environment for Microsoft 365 Enterprise that includes:</span></span>

- <span data-ttu-id="a39b2-106">Een proef- of betaald abonnement op Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a39b2-106">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="a39b2-107">Een vereenvoudigde organisatie die via intranet is verbonden met internet, bestaande uit drie virtuele machines op een virtueel Azure-netwerk (DC1, APP1 en CLIENT1).</span><span class="sxs-lookup"><span data-stu-id="a39b2-107">A simplified organization intranet connected to the Internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![De basisconfiguratie voor een gesimuleerde Enterprise](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="a39b2-109">U kunt de resulterende omgeving gebruiken om de functies en functionaliteit van [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) zelfstandig of met behulp van extra [Testlabrichtlijnen](m365-enterprise-test-lab-guides.md) te testen.</span><span class="sxs-lookup"><span data-stu-id="a39b2-109">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="a39b2-111">Ga naar de [Testlabrichtlijnen-stack van Microsoft 365](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="a39b2-111">Go to [Microsoft 365 Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="a39b2-112">Fase 1: Creëer een gesimuleerd intranet</span><span class="sxs-lookup"><span data-stu-id="a39b2-112">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="a39b2-113">In deze fase maakt u een gesimuleerd intranet in Azure-infrastructuurservices met een AD DS-domeincontroller (Active Directory Domain Services), een toepassingsserver en een clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="a39b2-113">In this phase, you build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span> 

<span data-ttu-id="a39b2-114">U gebruikt deze computers in extra [Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md) om de hybride identiteit en andere mogelijkheden te configureren en demonstreren.</span><span class="sxs-lookup"><span data-stu-id="a39b2-114">You'll use these computers in additional [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="a39b2-115">Methode 1: Maak uw gesimuleerde intranet met een Azure Resource Manager-sjabloon</span><span class="sxs-lookup"><span data-stu-id="a39b2-115">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="a39b2-116">Bij deze methode gebruikt u een sjabloon van Azure Resource Manager (ARM) om het gesimuleerde intranet te maken.</span><span class="sxs-lookup"><span data-stu-id="a39b2-116">In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet.</span></span> <span data-ttu-id="a39b2-117">ARM-sjablonen bevatten alle instructies voor het maken van de Azure-netwerkinfrastructuur, de virtuele machines en de configuratie ervan.</span><span class="sxs-lookup"><span data-stu-id="a39b2-117">ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="a39b2-118">Voorafgaand aan de implementatie van de sjabloon leest u de pagina met de [Leesmij-sjabloon](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) en verzamelt u de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="a39b2-118">Prior to deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="a39b2-119">De openbare DNS-domeinnaam van uw testomgeving (testlab.\<your public domain>).</span><span class="sxs-lookup"><span data-stu-id="a39b2-119">The public DNS domain name of your test environment (testlab.\<your public domain>).</span></span> <span data-ttu-id="a39b2-120">U moet deze naam invoeren in het veld **Domeinnaam** van de pagina **Aangepaste implementatie**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-120">You'll need to enter this name in the **Domain Name field** of the **Custom deployment** page.</span></span>
- <span data-ttu-id="a39b2-121">Een DNS-label voorvoegsel voor de Url's van de openbare IP-adressen van uw virtuele machines.</span><span class="sxs-lookup"><span data-stu-id="a39b2-121">A DNS label prefix for the URLs of the public IP addresses of your virtual machines.</span></span> <span data-ttu-id="a39b2-122">U moet dit label invoeren in het veld **DNS-label voorvoegsel** van de pagina **Aangepaste implementatie**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-122">You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="a39b2-123">Nadat u de instructies hebt gelezen, klikt u op **implementeren naar Azure** op de pagina [Leesmij-sjabloon](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="a39b2-123">After reading through the instructions, click **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="a39b2-124">Voor het gesimuleerde intranet dat is gemaakt door de ARM-sjabloon is een betaald Azure-abonnement vereist.</span><span class="sxs-lookup"><span data-stu-id="a39b2-124">The simulated intranet built by the ARM template requires a paid Azure subscription.</span></span>
>

<span data-ttu-id="a39b2-125">Hier ziet u uw configuratie nadat de sjabloon is voltooid.</span><span class="sxs-lookup"><span data-stu-id="a39b2-125">Here is your configuration after the template is complete.</span></span>

![Het gesimuleerde intranet in Azure-infrastructuurservices](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="a39b2-127">Methode 2: Maak uw gesimuleerde intranet met Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="a39b2-127">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="a39b2-128">Bij deze methode gebruikt u Windows PowerShell en de Azure PowerShell-module om de netwerkinfrastructuur, de virtuele machines en de configuratie ervan op te bouwen.</span><span class="sxs-lookup"><span data-stu-id="a39b2-128">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="a39b2-129">Gebruik deze methode als u ervaring wilt opdoen met het stap voor stap maken van elementen van de Azure-infrastructuur met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a39b2-129">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell.</span></span> <span data-ttu-id="a39b2-130">Vervolgens kunt u de PowerShell-opdrachtblokken aanpassen voor uw eigen implementatie van andere virtuele machines in Azure.</span><span class="sxs-lookup"><span data-stu-id="a39b2-130">You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="a39b2-131">Stap 1: DC1 maken</span><span class="sxs-lookup"><span data-stu-id="a39b2-131">Step 1: Create DC1</span></span>

<span data-ttu-id="a39b2-132">Bij deze stap maakt u een virtueel Azure-netwerk aan en voegt u DC1 toe, een virtuele machine die dient als domeincontroller voor een AD DS-domein.</span><span class="sxs-lookup"><span data-stu-id="a39b2-132">In this step, we create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="a39b2-133">Begin met het aanmaken van een Windows PowerShell-opdrachtprompt op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="a39b2-133">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a39b2-134">Met de volgende opdrachtsets wordt de meest recente versie van Azure PowerShell gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a39b2-134">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="a39b2-135">Zie [Aan de slag met Azure PowerShell-cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="a39b2-135">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="a39b2-136">Meld u aan bij uw Azure-account met behulp van de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="a39b2-136">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="a39b2-137">Haal de naam van uw abonnement op met de volgende opdracht.</span><span class="sxs-lookup"><span data-stu-id="a39b2-137">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="a39b2-138">Stel uw Azure-abonnement in.</span><span class="sxs-lookup"><span data-stu-id="a39b2-138">Set your Azure subscription.</span></span> <span data-ttu-id="a39b2-139">Vervang alles binnen de aanhalingstekens, inclusief de < en >-tekens, met de juiste naam.</span><span class="sxs-lookup"><span data-stu-id="a39b2-139">Replace everything within the quotes, including the < and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="a39b2-140">Maak vervolgens een nieuwe resourcegroep aan voor uw gesimuleerde Enterprise-testlab.</span><span class="sxs-lookup"><span data-stu-id="a39b2-140">Next, create a new resource group for your simulated enterprise test lab.</span></span> <span data-ttu-id="a39b2-141">Als u de naam van een unieke resourcegroep wilt bepalen, gebruikt u deze opdracht om uw bestaande resourcegroepen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="a39b2-141">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="a39b2-142">Maak uw nieuwe resourcegroep aan met deze opdrachten.</span><span class="sxs-lookup"><span data-stu-id="a39b2-142">Create your new resource group with these commands.</span></span> <span data-ttu-id="a39b2-143">Vervang alles binnen de aanhalingstekens, inclusief de < en >-tekens, met de juiste namen.</span><span class="sxs-lookup"><span data-stu-id="a39b2-143">Replace everything within the quotes, including the < and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="a39b2-144">Vervolgens maakt u het virtuele netwerk van TestLab aan dat het Corpnet-subnet van de gesimuleerde bedrijfsomgeving host en beveiligt u het met een netwerkbeveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="a39b2-144">Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group.</span></span> <span data-ttu-id="a39b2-145">Vul de naam van uw resourcegroep in en voer deze opdrachten uit bij de opdrachtprompt van PowerShell op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="a39b2-145">Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<name of your new resource group>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="a39b2-146">Vervolgens maakt u de DC1-virtuele machine en configureert u deze als een domeincontroller voor het **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="a39b2-146">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain></span></span> <span data-ttu-id="a39b2-147">AD DS-domein en een DNS-server voor de virtuele machines van het Testlab-virtuele netwerk.</span><span class="sxs-lookup"><span data-stu-id="a39b2-147">AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="a39b2-148">Als de naam van uw openbare domein bijvoorbeeld **<span>contoso</span>. com** is, is de DC1-virtuele machine een domeincontroller voor het **<span>testlab</span>. contoso.com**-domein.</span><span class="sxs-lookup"><span data-stu-id="a39b2-148">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="a39b2-149">Als u een virtuele machine van Azure wilt aanmaken voor DC1, vult u de naam van uw resourcegroep in en voert u deze opdrachten uit bij de opdrachtprompt van PowerShell op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="a39b2-149">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC1-OS" -DiskSizeInGB 128 -CreateOption FromImage
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC1-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC1-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="a39b2-150">U wordt gevraagd om een gebruikersnaam en wachtwoord voor het lokale Administrator-account op DC1 aan te maken.</span><span class="sxs-lookup"><span data-stu-id="a39b2-150">You will be prompted for a user name and password for the local administrator account on DC1.</span></span> <span data-ttu-id="a39b2-151">Gebruik een sterk wachtwoord en sla de naam en het wachtwoord op een veilige locatie op.</span><span class="sxs-lookup"><span data-stu-id="a39b2-151">Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="a39b2-152">Maak vervolgens verbinding met de DC1-virtuele machine.</span><span class="sxs-lookup"><span data-stu-id="a39b2-152">Next, connect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="a39b2-153">Klik in het [Azure-portaal](https://portal.azure.com)op **Resourcegroepen >** [de naam van uw nieuwe resourcegroep] **> DC1 > Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-153">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [the name of your new resource group] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="a39b2-154">Klik in het openstaande venster op **RDP-bestand downloaden**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-154">In the open pane, click **Download RDP file**.</span></span> <span data-ttu-id="a39b2-155">Open het gedownloade DC1.rdp-bestand en klik vervolgens op **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-155">Open the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="a39b2-156">Geef de naam van het lokale administrator-account van DC1 op:</span><span class="sxs-lookup"><span data-stu-id="a39b2-156">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="a39b2-157">Voor Windows 7:</span><span class="sxs-lookup"><span data-stu-id="a39b2-157">For Windows 7:</span></span>
    
     <span data-ttu-id="a39b2-158">Klik in het dialoogvenster **Windows Security** op **Gebruik een ander account**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-158">In the **Windows Security** dialog box, click **Use another account**.</span></span> <span data-ttu-id="a39b2-159">Bij **Gebruikersnaam** typt u **DC1\\**[naam van lokaal administrator-account].</span><span class="sxs-lookup"><span data-stu-id="a39b2-159">In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
   - <span data-ttu-id="a39b2-160">Voor Windows 8 of Windows 10:</span><span class="sxs-lookup"><span data-stu-id="a39b2-160">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="a39b2-161">Klik in het dialoogvenster **Windows Security** op **Meer opties**en klik vervolgens op **Gebruik een ander account**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-161">In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**.</span></span> <span data-ttu-id="a39b2-162">Bij **Gebruikersnaam** typt u **DC1\\**[naam van lokaal administrator-account].</span><span class="sxs-lookup"><span data-stu-id="a39b2-162">In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="a39b2-163">Bij **Wachtwoord** typt u het wachtwoord van het lokale administrator-account en klikt u vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-163">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="a39b2-164">Klik op **Ja** wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="a39b2-164">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="a39b2-165">Voeg vervolgens een extra gegevensschijf toe als een nieuw volume met de stationsaanduiding F: met deze opdracht met een opdrachtprompt op het beheerdersniveau van Windows PowerShell op DC1.</span><span class="sxs-lookup"><span data-stu-id="a39b2-165">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="a39b2-166">Configureer DC1 vervolgens als een domeincontroller en DNS-server voor het **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="a39b2-166">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<your public domain></span></span> <span data-ttu-id="a39b2-167">-domein.</span><span class="sxs-lookup"><span data-stu-id="a39b2-167">domain.</span></span> <span data-ttu-id="a39b2-168">Geef de naam van uw openbare domein op, verwijder de \< and >-tekens en voer deze opdrachten uit op een Windows PowerShell-opdrachtprompt op beheerdersniveau op DC1.</span><span class="sxs-lookup"><span data-stu-id="a39b2-168">Specify your public domain name, remove the \< and > characters, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="a39b2-169">U zult een beheerderswachtwoord moeten opgeven voor de veilige modus.</span><span class="sxs-lookup"><span data-stu-id="a39b2-169">You will need to specify a safe mode administrator password.</span></span> <span data-ttu-id="a39b2-170">Sla dit wachtwoord op een veilige locatie op.</span><span class="sxs-lookup"><span data-stu-id="a39b2-170">Store this password in a secure location.</span></span>
  
<span data-ttu-id="a39b2-171">Houd er rekening mee dat deze opdrachten een paar minuten in beslag nemen.</span><span class="sxs-lookup"><span data-stu-id="a39b2-171">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="a39b2-172">Nadat DC1 opnieuw is gestart, maakt u opnieuw verbinding met de DC1-virtuele machine.</span><span class="sxs-lookup"><span data-stu-id="a39b2-172">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="a39b2-173">Klik in het [Azure-portaal](https://portal.azure.com) op **Resourcegroepen >** [naam van uw resourcegroep] **> DC1 > Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-173">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [your resource group name] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="a39b2-174">Open het gedownloade DC1.rdp-bestand en klik vervolgens op **Verbinden**</span><span class="sxs-lookup"><span data-stu-id="a39b2-174">Run the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="a39b2-175">Klik in het dialoogvenster **Windows Security** op **Gebruik een ander account**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-175">In **Windows Security**, click **Use another account**.</span></span> <span data-ttu-id="a39b2-176">Bij **Gebruikersnaam** typt u **TESTLAB\\**[naam van lokaal administrator-account].</span><span class="sxs-lookup"><span data-stu-id="a39b2-176">In **User name**, type **TESTLAB\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="a39b2-177">Bij **Wachtwoord** typt u het wachtwoord van het lokale administrator-account en klikt u vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-177">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="a39b2-178">Klik op **Ja** wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="a39b2-178">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="a39b2-179">Maak vervolgens een gebruikersaccount in Active Directory aan dat wordt gebruikt bij het aanmelden op TESTLAB-domeincomputers.</span><span class="sxs-lookup"><span data-stu-id="a39b2-179">Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers.</span></span> <span data-ttu-id="a39b2-180">Voer deze opdracht uit op een Windows PowerShell-opdrachtprompt op beheerdersniveau.</span><span class="sxs-lookup"><span data-stu-id="a39b2-180">Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="a39b2-181">Met deze opdracht wordt u gevraagd het wachtwoord van het Gebruiker1-account te verstrekken.</span><span class="sxs-lookup"><span data-stu-id="a39b2-181">Note that this command prompts you to supply the User1 account password.</span></span> <span data-ttu-id="a39b2-182">Aangezien dit account wordt gebruikt voor verbindingen met externe desktops voor alle TESTLAB-computers die lid zijn van het domein, dient u een sterk wachtwoord te kiezen.</span><span class="sxs-lookup"><span data-stu-id="a39b2-182">Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password.</span></span> <span data-ttu-id="a39b2-183">Noteer het wachtwoord van het Gebruiker1-account en sla het op een beveiligde locatie op.</span><span class="sxs-lookup"><span data-stu-id="a39b2-183">Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="a39b2-184">Configureer vervolgens het nieuwe Gebruiker1-account als een domein-, enterprise- en schemabeheerder.</span><span class="sxs-lookup"><span data-stu-id="a39b2-184">Next, configure the new User1 account as a domain, enterprise, and schema administrator.</span></span> <span data-ttu-id="a39b2-185">Voer deze opdracht uit op de Windows PowerShell-opdrachtprompt op beheerdersniveau.</span><span class="sxs-lookup"><span data-stu-id="a39b2-185">Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="a39b2-186">Sluit de Extern bureaublad-sessie met DC1 en maak opnieuw verbinding via het \\Gebruiker1-account van TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="a39b2-186">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="a39b2-187">Voer deze opdracht uit op een Windows PowerShell-opdrachtprompt op beheerdersniveau om verkeer voor het Ping-hulpprogramma toe te staan.</span><span class="sxs-lookup"><span data-stu-id="a39b2-187">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="a39b2-188">Dit is uw huidige configuratie.</span><span class="sxs-lookup"><span data-stu-id="a39b2-188">This is your current configuration.</span></span>
  
![Stap 1 voor de basisconfiguratie van de gesimuleerde enterprise](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="a39b2-190">Stap 2: APP1 configureren</span><span class="sxs-lookup"><span data-stu-id="a39b2-190">Step 2: Configure APP1</span></span>

<span data-ttu-id="a39b2-191">Bij deze stap maakt en configureert u APP1, een toepassingsserver die in eerste instantie Services biedt voor het delen van bestanden.</span><span class="sxs-lookup"><span data-stu-id="a39b2-191">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="a39b2-192">Om een virtuele machine van Azure voor APP1 aan te maken, vult u de naam van uw resourcegroep in en voert u deze opdrachten uit bij de opdrachtprompt op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="a39b2-192">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="a39b2-193">Vervolgens maakt u verbinding met de APP1-virtuele machine met de naam en het wachtwoord van het lokale APP1-administratoraccount en opent u een Windows PowerShell-opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="a39b2-193">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="a39b2-194">Als u de naamresolutie en de netwerkcommunicatie tussen APP1 en DC1 wilt controleren, voert u de opdracht **ping dc1. testlab.**\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="a39b2-194">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<your public domain name></span></span> <span data-ttu-id="a39b2-195">uit en controleert u of er vier antwoorden zijn.</span><span class="sxs-lookup"><span data-stu-id="a39b2-195">command and verify that there are four replies.</span></span>
  
<span data-ttu-id="a39b2-196">Vervolgens voegt u de APP1-virtuele machine toe aan het TESTLAB-domein met deze opdrachten bij de Windows PowerShell-prompt.</span><span class="sxs-lookup"><span data-stu-id="a39b2-196">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="a39b2-197">U moet de gegevens van het \\Gebruiker1-domeinaccount van TESTLAB opgeven nadat u de opdracht **Add-computer** hebt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a39b2-197">Note that you must supply the TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="a39b2-198">Nadat APP1 opnieuw is gestart, maakt u verbinding met het bestand met behulp van het \\Gebruiker1-account van TESTLAB en opent u vervolgens een Windows PowerShell-opdrachtprompt op beheerdersniveau.</span><span class="sxs-lookup"><span data-stu-id="a39b2-198">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="a39b2-199">Vervolgens maakt u APP1 een webserver door deze opdracht uit te voeren op een Windows PowerShell-opdrachtprompt op beheerdersniveau op APP1.</span><span class="sxs-lookup"><span data-stu-id="a39b2-199">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="a39b2-200">Maak vervolgens een gedeelde map aan en een tekstbestand in de map op APP1 met deze PowerShell-opdrachten.</span><span class="sxs-lookup"><span data-stu-id="a39b2-200">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="a39b2-201">Dit is uw huidige configuratie.</span><span class="sxs-lookup"><span data-stu-id="a39b2-201">This is your current configuration.</span></span>
  
![Stap 2 van de basisconfiguratie van de gesimuleerde enterprise](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="a39b2-203">Stap 3: CLIENT1 configureren</span><span class="sxs-lookup"><span data-stu-id="a39b2-203">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="a39b2-204">In deze stap maakt en configureert u CLIENT1, die fungeert als een normale laptop, tablet of desktopcomputer op het intranet.</span><span class="sxs-lookup"><span data-stu-id="a39b2-204">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="a39b2-205">Met de volgende opdrachtsets maakt u CLIENT1 met Windows Server 2016 Datacenter, wat kan worden uitgevoerd voor alle typen Azure-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="a39b2-205">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions.</span></span> <span data-ttu-id="a39b2-206">Als u een Azure-abonnement hebt op basis van Visual Studio, kunt u CLIENT1 met Windows 10 maken met behulp van de [Azure-portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="a39b2-206">If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span> 
  
<span data-ttu-id="a39b2-207">Om een virtuele machine van Azure voor CLIENT1 aan te maken, vult u de naam van uw resourcegroep in en voert u deze opdrachten uit bij de opdrachtprompt op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="a39b2-207">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="a39b2-208">Vervolgens maakt u verbinding met de CLIENT1-virtuele machine met de naam en het wachtwoord van het lokale CLIENT1-administratoraccount en opent u een Windows PowerShell-opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="a39b2-208">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="a39b2-209">Als u de naamresolutie en de netwerkcommunicatie tussen CLIENT1 en DC1 wilt controleren, voert u de opdracht **ping dc1. testlab.**\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="a39b2-209">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<your public domain name></span></span> <span data-ttu-id="a39b2-210">uit via de opdrachtprompt van Windows PowerShell en controleert u of er vier antwoorden zijn.</span><span class="sxs-lookup"><span data-stu-id="a39b2-210">command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="a39b2-211">Vervolgens voegt u de CLIENT1-virtuele machine toe aan het TESTLAB-domein met deze opdrachten bij de Windows PowerShell-prompt.</span><span class="sxs-lookup"><span data-stu-id="a39b2-211">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="a39b2-212">Houd er rekening mee dat u de gegevens van het \\Gebruiker1-domeinaccount van TESTLAB op moet geven nadat u de opdracht **Add-computer** hebt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a39b2-212">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="a39b2-213">Nadat CLIENT1 opnieuw is gestart, maakt u verbinding met het bestand met behulp van het \\Gebruiker1-account van TESTLAB en opent u vervolgens een Windows PowerShell-opdrachtprompt op beheerdersniveau.</span><span class="sxs-lookup"><span data-stu-id="a39b2-213">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="a39b2-214">Controleer vervolgens of u toegang hebt tot web- en bestandssharebronnen op APP1 vanuit CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="a39b2-214">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="a39b2-215">Klik in Server Manager in het structuurvenster op **Lokale server**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-215">In Server Manager, in the tree pane, click **Local Server**.</span></span>
    
2. <span data-ttu-id="a39b2-216">Klik in **Eigenschappen voor CLIENT1** op **Aan** naast **Verbeterde beveiligingsconfiguratie van IE**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-216">In **Properties for CLIENT1**, click **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="a39b2-217">Klik in **Verbeterde beveiligingsconfiguratie van Internet Explorer**op **Uit** voor **Beheerders** en **Gebruikers** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-217">In **Internet Explorer Enhanced Security Configuration**, click **Off** for **Administrators** and **Users**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="a39b2-218">Klik in het Startscherm op **Internet Explorer** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-218">From the Start screen, click **Internet Explorer**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="a39b2-219">Typ **http<span>://</span>app1.testab.**\<your public domain name>**/** in de adresbalk en druk vervolgens op ENTER.</span><span class="sxs-lookup"><span data-stu-id="a39b2-219">In the Address bar, type **http<span>://</span>app1.testab.**\<your public domain name>**/**, and then press ENTER.</span></span> <span data-ttu-id="a39b2-220">U ziet nu de standaardwebpagina voor Internet Information Services voor APP1.</span><span class="sxs-lookup"><span data-stu-id="a39b2-220">You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="a39b2-221">Klik op de taakbalk van het bureaublad op het pictogram van de Verkenner.</span><span class="sxs-lookup"><span data-stu-id="a39b2-221">From the desktop taskbar, click the File Explorer icon.</span></span>
    
7. <span data-ttu-id="a39b2-222">Typ **\\\\app1\\bestanden** in de adresbalk en druk op ENTER.</span><span class="sxs-lookup"><span data-stu-id="a39b2-222">In the address bar, type **\\\\app1\\Files**, and then press ENTER.</span></span> <span data-ttu-id="a39b2-223">Er wordt een mappenvenster met de inhoud van de map met gedeelde bestanden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a39b2-223">You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="a39b2-224">Dubbelklik in het venster van de map met **Gedeelde bestanden** op het bestand **Voorbeeld.txt**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-224">In the **Files** shared folder window, double-click the **Example.txt** file.</span></span> <span data-ttu-id="a39b2-225">U ziet nu de inhoud van het bestand Voorbeeld.txt.</span><span class="sxs-lookup"><span data-stu-id="a39b2-225">You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="a39b2-226">Sluit het **Voorbeeld.txt - Notepad** en de map met **Gedeelde bestanden**.</span><span class="sxs-lookup"><span data-stu-id="a39b2-226">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="a39b2-227">Dit is uw huidige configuratie.</span><span class="sxs-lookup"><span data-stu-id="a39b2-227">This is your current configuration.</span></span>
  
![Stap 3 van de basisconfiguratie van de gesimuleerde enterprise](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="a39b2-229">Fase 2: Maak uw abonnement op Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="a39b2-229">Phase 2: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="a39b2-230">In deze fase maakt u een nieuw Microsoft 365 E5-abonnement aan dat gebruikmaakt van een nieuwe Azure AD-tenant, die losstaat van uw productieabonnement.</span><span class="sxs-lookup"><span data-stu-id="a39b2-230">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription.</span></span> <span data-ttu-id="a39b2-231">U kunt dit op twee manieren doen:</span><span class="sxs-lookup"><span data-stu-id="a39b2-231">You can do this in two ways:</span></span>

- <span data-ttu-id="a39b2-232">Gebruik een proefabonnement op Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a39b2-232">Use a trial subscription of Microsoft 365 E5.</span></span> 

  <span data-ttu-id="a39b2-233">Het proefabonnement op Microsoft 365 E5 duurt 30 dagen en kan gemakkelijk tot 60 dagen worden verlengd.</span><span class="sxs-lookup"><span data-stu-id="a39b2-233">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days.</span></span> <span data-ttu-id="a39b2-234">Wanneer het proefabonnement is verlopen, moet u dit omzetten naar een betaald abonnement of een nieuw proefabonnement starten.</span><span class="sxs-lookup"><span data-stu-id="a39b2-234">When the trial subscription expires, you must either convert it to a paid subscription or create a new trial subscription.</span></span> <span data-ttu-id="a39b2-235">Het starten van nieuwe proefabonnementen houdt in dat u uw configuratie achterlaat, inclusief eventuele ingewikkelde scenario's.</span><span class="sxs-lookup"><span data-stu-id="a39b2-235">Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="a39b2-236">Gebruik een afzonderlijk productieabonnement op Microsoft 365 E5 met een beperkt aantal licenties.</span><span class="sxs-lookup"><span data-stu-id="a39b2-236">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="a39b2-237">Hier komen extra kosten bij kijken, maar het zorgt er wel voor dat u beschikt over een omgeving voor het testen van functies, configuraties en scenario's die niet verloopt.</span><span class="sxs-lookup"><span data-stu-id="a39b2-237">This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire.</span></span> <span data-ttu-id="a39b2-238">U kunt dezelfde testomgeving op de lange termijn gebruiken voor de proefversies van concepten, demonstraties voor collega's en het beheer, en voor het ontwikkelen en testen van toepassingen.</span><span class="sxs-lookup"><span data-stu-id="a39b2-238">You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing.</span></span> <span data-ttu-id="a39b2-239">Dit is de aanbevolen methode.</span><span class="sxs-lookup"><span data-stu-id="a39b2-239">This is the recommended method.</span></span>

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="a39b2-240">Registreer u voor een proefabonnement op Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="a39b2-240">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="a39b2-241">Maak verbinding met CLIENT1 met het CORP\Gebruiker1-account van de Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="a39b2-241">Connect to CLIENT1 with the CORP\User1 account from the Azure portal.</span></span>

<span data-ttu-id="a39b2-242">Als u een nieuw Office 365 E5-proefabonnement wilt maken, volgt u de instructies uit [Fase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-office-365-e5-subscription) van de Testlabrichtlijnen voor eenvoudige basisconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="a39b2-242">To create a new Office 365 E5 trial subscription, perform the instructions in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-office-365-e5-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

<span data-ttu-id="a39b2-243">Als u uw nieuwe Office 365 E5-proefabonnement wilt maken, volgt u de instructies uit [Fase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) van de Testlabrichtlijnen voor eenvoudige basisconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="a39b2-243">To configure your new Office 365 E5 trial subscription, perform the instructions in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

#### <a name="using-an-office-365-e5-test-environment"></a><span data-ttu-id="a39b2-244">Een Office 365 E5-testomgeving gebruiken</span><span class="sxs-lookup"><span data-stu-id="a39b2-244">Using an Office 365 E5 test environment</span></span>

<span data-ttu-id="a39b2-245">Als u alleen een Office 365-testomgeving nodig hebt, kunt u hier stoppen.</span><span class="sxs-lookup"><span data-stu-id="a39b2-245">If all you need is an Office 365 test environment, you can stop here.</span></span> 

<span data-ttu-id="a39b2-246">Zie [Microsoft 365 Enterprise-Testlabrichtlijnen](m365-enterprise-test-lab-guides.md) voor extra Testlabrichtlijnen die van toepassing zijn op Office 365 en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a39b2-246">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>

### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="a39b2-247">Een Microsoft 365 E5-proefabonnement toevoegen.</span><span class="sxs-lookup"><span data-stu-id="a39b2-247">Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="a39b2-248">Om een Microsoft 365 E5-proefabonnement te installeren en uw gebruikersaccounts met licenties te configureren, voert u de instructies uit in [Fase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) van de Testlabrichtlijnen voor eenvoudige basisconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="a39b2-248">To a Microsoft 365 E5 trial subscription and configure your users accounts with licenses, perform the instructions in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

  
## <a name="results"></a><span data-ttu-id="a39b2-249">Resultaten</span><span class="sxs-lookup"><span data-stu-id="a39b2-249">Results</span></span>

<span data-ttu-id="a39b2-250">Uw testomgeving heeft nu:</span><span class="sxs-lookup"><span data-stu-id="a39b2-250">Your test environment now has:</span></span>
  
- <span data-ttu-id="a39b2-251">Microsoft 365 E5-proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="a39b2-251">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="a39b2-252">Al uw geschikte gebruikersaccounts kunnen Microsoft 365 E5 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a39b2-252">All your appropriate user accounts are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="a39b2-253">Een gesimuleerd en vereenvoudigd intranet.</span><span class="sxs-lookup"><span data-stu-id="a39b2-253">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="a39b2-254">Dit is uw definitieve configuratie.</span><span class="sxs-lookup"><span data-stu-id="a39b2-254">This is your final configuration.</span></span>
  
![Fase 2 van de basisconfiguratie van de gesimuleerde enterprise](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="a39b2-256">U bent nu klaar om te experimenteren met de extra functies van [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="a39b2-256">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="a39b2-257">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="a39b2-257">Next steps</span></span>

<span data-ttu-id="a39b2-258">Verken de volgende extra sets testlabrichtlijnen:</span><span class="sxs-lookup"><span data-stu-id="a39b2-258">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="a39b2-259">Identiteit</span><span class="sxs-lookup"><span data-stu-id="a39b2-259">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="a39b2-260">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="a39b2-260">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="a39b2-261">Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="a39b2-261">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="a39b2-262">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a39b2-262">See also</span></span>

[<span data-ttu-id="a39b2-263">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="a39b2-263">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a39b2-264">Microsoft 365 Enterprise implementeren</span><span class="sxs-lookup"><span data-stu-id="a39b2-264">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a39b2-265">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="a39b2-265">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
