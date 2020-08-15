---
title: Federatieve identiteit voor uw Microsoft 365-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: 'Overzicht: federatieve verificatie configureren voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: c7ff838522c0bd97da4ffff5122454b128f97bf2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689489"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="97c1a-103">Federatieve identiteit voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="97c1a-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="97c1a-104">*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="97c1a-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="97c1a-105">Microsoft 365 ondersteunt federatieve identiteit.</span><span class="sxs-lookup"><span data-stu-id="97c1a-105">Microsoft 365 supports federated identity.</span></span> <span data-ttu-id="97c1a-106">Dit betekent dat in plaats van de validatie van referenties zelf uit te voeren, Microsoft 365 de verbindende gebruiker verwijst naar een federatieve verificatieserver die Microsoft 365 vertrouwt.</span><span class="sxs-lookup"><span data-stu-id="97c1a-106">This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts.</span></span> <span data-ttu-id="97c1a-107">Als de inloggegevens van de gebruiker correct zijn, geeft de federatieve verificatieserver een beveiligingstoken uit dat de client vervolgens naar Microsoft 365 stuurt als bewijs van verificatie.</span><span class="sxs-lookup"><span data-stu-id="97c1a-107">If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication.</span></span> <span data-ttu-id="97c1a-108">Federatieve identiteit zorgt voor de offloading en schaalbaarheid van verificatie voor een Microsoft 365-abonnement en geavanceerde verificatie- en beveiligingsscenario's.</span><span class="sxs-lookup"><span data-stu-id="97c1a-108">Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="97c1a-109">In dit artikel wordt beschreven hoe u federatieve verificatie voor uw Microsoft 365-testomgeving kunt configureren, wat resulteert in het volgende:</span><span class="sxs-lookup"><span data-stu-id="97c1a-109">This article describes how you can configure federated authentication for your Microsoft 365 test environment, resulting in the following:</span></span>

![De federatieve verificatie voor Microsoft 365-testomgeving](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="97c1a-111">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="97c1a-111">This configuration consists of:</span></span> 
  
- <span data-ttu-id="97c1a-112">Een Microsoft 365 E5-proefabonnement of productie abonnement.</span><span class="sxs-lookup"><span data-stu-id="97c1a-112">A Microsoft 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="97c1a-113">Een vereenvoudigde organisatie die via intranet is verbonden met internet, bestaande uit vijf virtuele machines op een subnet van een virtueel Azure-netwerk (DC1, APP1, CLIENT1, ADFS1 en PROXY1).</span><span class="sxs-lookup"><span data-stu-id="97c1a-113">A simplified organization intranet connected to the Internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1).</span></span> <span data-ttu-id="97c1a-114">Azure AD Connect wordt uitgevoerd op APP1 om de lijst met accounts in het Active Directory Domain Services-domein te synchroniseren met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97c1a-114">Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Microsoft 365.</span></span> <span data-ttu-id="97c1a-115">PROXY1 ontvangt de binnenkomende verificatieaanvragen.</span><span class="sxs-lookup"><span data-stu-id="97c1a-115">PROXY1 receives the incoming authentication requests.</span></span> <span data-ttu-id="97c1a-116">ADFS1 valideert referenties met DC1 en beveiligingstokens.</span><span class="sxs-lookup"><span data-stu-id="97c1a-116">ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="97c1a-117">Er zijn vijf fasen om deze testomgeving in te stellen:</span><span class="sxs-lookup"><span data-stu-id="97c1a-117">There are five phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="97c1a-118">Maak de gesimuleerde bedrijfstestomgeving met wachtwoord-hash-synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="97c1a-118">Create the simulated enterprise test environment with password hash synchronization.</span></span>
    
2. <span data-ttu-id="97c1a-119">Maak de AD FS-server (ADFS1).</span><span class="sxs-lookup"><span data-stu-id="97c1a-119">Create the AD FS server (ADFS1).</span></span>
    
3. <span data-ttu-id="97c1a-120">Maak de webproxyserver (PROXY1).</span><span class="sxs-lookup"><span data-stu-id="97c1a-120">Create the web proxy server (PROXY1).</span></span>
    
4. <span data-ttu-id="97c1a-121">Maak een zelfondertekend certificaat en configureer ADFS1 en PROXY1.</span><span class="sxs-lookup"><span data-stu-id="97c1a-121">Create a self-signed certificate and configure ADFS1 and PROXY1.</span></span>
    
5. <span data-ttu-id="97c1a-122">Configureer Microsoft 365 voor federatieve identiteit.</span><span class="sxs-lookup"><span data-stu-id="97c1a-122">Configure Microsoft 365 for federated identity.</span></span>
    
> [!NOTE]
> <span data-ttu-id="97c1a-123">U kunt deze testomgeving niet configureren met een Azure-proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="97c1a-123">You cannot configure this test environment with an Azure Trial subscription.</span></span> 
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="97c1a-124">Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="97c1a-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="97c1a-125">Volg de instructies in [wachtwoord-hash-synchronisatie voor Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="97c1a-125">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="97c1a-126">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="97c1a-126">Here is your resulting configuration.</span></span>
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="97c1a-128">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="97c1a-128">This configuration consists of:</span></span> 
  
- <span data-ttu-id="97c1a-129">Een Microsoft 365 E5-proefabonnement of betaalde abonnementen.</span><span class="sxs-lookup"><span data-stu-id="97c1a-129">A Microsoft 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="97c1a-130">Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="97c1a-130">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="97c1a-131">Azure AD Connect wordt uitgevoerd op APP1 om het AD DS-domein TESTLAB te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="97c1a-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="97c1a-132">Fase 2: maak de AD FS-server</span><span class="sxs-lookup"><span data-stu-id="97c1a-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="97c1a-133">Een AD FS-server biedt federatieve verificatie tussen Microsoft 365 en de accounts in het corp.contoso.com-domein dat wordt gehost op DC1.</span><span class="sxs-lookup"><span data-stu-id="97c1a-133">An AD FS server provides federated authentication between Microsoft 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="97c1a-134">Als u een virtuele machine van Azure wilt maken voor ADFS1, vult u de naam van uw abonnement, de bronnengroep en de Azure-locatie voor uw basisconfiguratie in en voert u deze opdrachten uit op de opdrachtprompt van de Azure PowerShell op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="97c1a-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="97c1a-135">Gebruik vervolgens de [Azure-portal](https://portal.azure.com) om verbinding te maken met de ADFS1 virtuele machine met behulp van de ADFS1-naam en het wachtwoord van de lokale beheerdersaccount, en open vervolgens een Windows PowerShell-opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="97c1a-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="97c1a-136">Als u de naamresolutie en de netwerkcommunicatie tussen ADFS1 en DC1 wilt controleren, voert u de opdracht **ping dc1.corp.contoso.com** uit en controleert u of er vier antwoorden zijn.</span><span class="sxs-lookup"><span data-stu-id="97c1a-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="97c1a-137">Vervolgens voegt u de virtuele machine ADFS1 toe aan het CORP-domein met deze opdrachten bij de Windows PowerShell-prompt op ADFS1.</span><span class="sxs-lookup"><span data-stu-id="97c1a-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="97c1a-138">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="97c1a-138">Here is your resulting configuration.</span></span>
  
![De AD FS-server die is toegevoegd aan de testomgeving van DirSync voor Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="97c1a-140">Fase 3: de webproxyserver maken</span><span class="sxs-lookup"><span data-stu-id="97c1a-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="97c1a-141">PROXY1 biedt proxy van authenticatieberichten tussen gebruikers die proberen te authenticeren en ADFS1.</span><span class="sxs-lookup"><span data-stu-id="97c1a-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="97c1a-142">Als u een virtuele machine van Azure wilt maken voor PROXY1, vult u de naam van de resourcegroep en de Azure-locatie in en voert u deze opdrachten uit op de opdrachtprompt van de Azure PowerShell op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="97c1a-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="97c1a-143">PROXY1 krijgt een statisch openbaar IP-adres toegewezen, omdat u een openbaar DNS-record maakt dat ernaar verwijst en het niet mag veranderen wanneer u de virtuele machine PROXY1 opnieuw opstart.</span><span class="sxs-lookup"><span data-stu-id="97c1a-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span> 
  
<span data-ttu-id="97c1a-144">Voeg vervolgens een regel toe aan de netwerkbeveiligingsgroep voor het CorpNet-subnet om ongevraagd inkomend verkeer van internet naar het privé IP-adres van PROXY1 en TCP-poort 443 toe te staan.</span><span class="sxs-lookup"><span data-stu-id="97c1a-144">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the Internet to PROXY1's private IP address and TCP port 443.</span></span> <span data-ttu-id="97c1a-145">Voer deze opdrachten uit vanaf de opdrachtprompt van Azure PowerShell op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="97c1a-145">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="97c1a-146">Gebruik vervolgens de [Azure-portal](https://portal.azure.com) om verbinding te maken met de virtuele machine PROXY1 met behulp van de PROXY1-naam en het wachtwoord van de lokale beheerdersaccount, en open vervolgens een Windows PowerShell-opdrachtprompt op PROXY1.</span><span class="sxs-lookup"><span data-stu-id="97c1a-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="97c1a-147">Als u de naamresolutie en de netwerkcommunicatie tussen PROXY1 en DC1 wilt controleren, voert u de opdracht **ping dc1.corp.contoso.com** uit en controleert u of er vier antwoorden zijn.</span><span class="sxs-lookup"><span data-stu-id="97c1a-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="97c1a-148">Vervolgens voegt u de virtuele machine PROXY1 toe aan het CORP-domein met deze opdrachten bij de Windows PowerShell-prompt op PROXY1.</span><span class="sxs-lookup"><span data-stu-id="97c1a-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="97c1a-149">Geef het openbare IP-adres van PROXY1 weer met deze Azure PowerShell-opdrachten op uw lokale computer:</span><span class="sxs-lookup"><span data-stu-id="97c1a-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer:</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="97c1a-150">Werk vervolgens met uw openbare DNS-provider om een nieuw openbaar DNS A-record aan te maken voor **fs.testlab.**\<your DNS domain name></span><span class="sxs-lookup"><span data-stu-id="97c1a-150">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<your DNS domain name></span></span> <span data-ttu-id="97c1a-151">dat wordt omgezet naar het IP-adres dat wordt weergegeven door de **Write-Host**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-151">that resolves to the IP address displayed by the **Write-Host** command.</span></span> <span data-ttu-id="97c1a-152">De **fs.testlab.**\<your DNS domain name></span><span class="sxs-lookup"><span data-stu-id="97c1a-152">The **fs.testlab.**\<your DNS domain name></span></span> <span data-ttu-id="97c1a-153">wordt hierna de *federatiedienst FQDN* genoemd.</span><span class="sxs-lookup"><span data-stu-id="97c1a-153">is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="97c1a-154">Gebruik vervolgens de [Azure-portal](https://portal.azure.com) om verbinding te maken met de virtuele machine DC1 met behulp van de CORP\\gebruiker1-referenties en voer vervolgens de volgende opdrachten uit op een Windows PowerShell-opdrachtprompt op beheerdersniveau:</span><span class="sxs-lookup"><span data-stu-id="97c1a-154">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="97c1a-155">Met deze opdrachten maakt u een intern DNS A-record zodat virtuele machines op het virtuele Azure-netwerk de interne federatie FQDN kunnen omzetten in het privé IP-adres van ADFS1.</span><span class="sxs-lookup"><span data-stu-id="97c1a-155">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="97c1a-156">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="97c1a-156">Here is your resulting configuration.</span></span>
  
![De proxyserver van de webtoepassing is toegevoegd aan de testomgeving van DirSync voor Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="97c1a-158">Fase 4: maak een zelfondertekend certificaat en configureer ADFS1 en PROXY1.</span><span class="sxs-lookup"><span data-stu-id="97c1a-158">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="97c1a-159">In deze fase maakt u een zelfondertekend digitaal certificaat voor de FQDN van de federatieservice en configureert u ADFS1 en PROXY1 als een AD FS-farm.</span><span class="sxs-lookup"><span data-stu-id="97c1a-159">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="97c1a-160">Gebruik eerst de [Azure-portal](https://portal.azure.com) om verbinding te maken met de virtuele DC1-machine met de referenties voor CORP\\gebruiker1 en open vervolgens een opdrachtprompt op beheerdersniveau in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97c1a-160">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="97c1a-161">Maak vervolgens een AD FS-serviceaccount met deze opdracht met de Windows PowerShell-opdrachtprompt op DC1:</span><span class="sxs-lookup"><span data-stu-id="97c1a-161">Next, create AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="97c1a-162">Met deze opdracht wordt u gevraagd het wachtwoord van het account op te geven.</span><span class="sxs-lookup"><span data-stu-id="97c1a-162">Note that this command prompts you to supply the account password.</span></span> <span data-ttu-id="97c1a-163">Kies een sterk wachtwoord en sla dit op in een beveiligde locatie.</span><span class="sxs-lookup"><span data-stu-id="97c1a-163">Choose a strong password and record it in a secured location.</span></span> <span data-ttu-id="97c1a-164">U hebt het nodig voor deze fase en fase 5.</span><span class="sxs-lookup"><span data-stu-id="97c1a-164">You will need it for this phase and Phase 5.</span></span>
  
<span data-ttu-id="97c1a-165">Gebruik de [Azure-Portal](https://portal.azure.com) om verbinding te maken met de virtuele ADFS1-computer met de accountreferenties voor CORP\\gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="97c1a-165">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials.</span></span> <span data-ttu-id="97c1a-166">Open een Windows PowerShell-opdrachtprompt op beheerdersniveau op ADFS1, vul de FQDN van de federatiedienst in en voer vervolgens deze opdrachten uit om een zelfondertekend certificaat te maken:</span><span class="sxs-lookup"><span data-stu-id="97c1a-166">Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="97c1a-167">Gebruik vervolgens deze stappen om het nieuwe, zelfondertekend certificaat als een bestand op te slaan.</span><span class="sxs-lookup"><span data-stu-id="97c1a-167">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="97c1a-168">Klik op **Start**, typ **mmc.exe** en druk op **Enter**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-168">Click **Start**, type **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="97c1a-169">Klik op **Bestand > Snap-in toevoegen/verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-169">Click **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="97c1a-170">Dubbelklik in **Snap-ins toevoegen of verwijderen** op **Certificaten** in de lijst met beschikbare snap-ins, klik op **Computeraccount** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-170">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, click **Computer account**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="97c1a-171">Klik in **Computer selecteren** op **Voltooien** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-171">In **Select Computer**, click **Finish**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="97c1a-172">Open in het structuurvenster **certificaten (lokale computer) > persoonlijk > certificaten**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-172">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="97c1a-173">Klik met de rechtermuisknop op het certificaat met de FQDN van de federatieservice, klik op **alle taken**en klik vervolgens op **exporteren**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-173">Right-click the certificate with your federation service FQDN, click **All tasks**, and then click **Export**.</span></span>
    
7. <span data-ttu-id="97c1a-174">Klik op **Volgende** op de **welkomstpagina**.  </span><span class="sxs-lookup"><span data-stu-id="97c1a-174">On the **Welcome** page, click **Next**.</span></span>
    
8. <span data-ttu-id="97c1a-175">Klik op de pagina **persoonlijke sleutel exporteren** op **ja**en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-175">On the **Export Private Key** page, click **Yes**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="97c1a-176">Klik op de pagina **bestandsindeling exporteren** op **alle uitgebreide eigenschappen exporteren**en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-176">On the **Export File Format** page, click **Export all extended properties**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="97c1a-177">Klik op de pagina **beveiliging** op **wachtwoord** en typ een wachtwoord in **wachtwoord** en **wachtwoord bevestigen.**</span><span class="sxs-lookup"><span data-stu-id="97c1a-177">On the **Security** page, click **Password** and type a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="97c1a-178">Klik op de pagina **bestand om te exporteren** op **bladeren**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-178">On the **File to Export** page, click **Browse**.</span></span>
    
12. <span data-ttu-id="97c1a-179">Blader naar de map **C:\\certs**, typ **SSL** als **bestandsnaam** en klik vervolgens op **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="97c1a-179">Browse to the **C:\\Certs** folder, type **SSL** in **File name**, and then click **Save.**</span></span>
    
13. <span data-ttu-id="97c1a-180">Klik op de pagina **bestand om te exporteren** op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-180">On the **File to Export** page, click **Next**.</span></span>
    
14. <span data-ttu-id="97c1a-181">Klik op de pagina **wizard certificaat exporteren voltooien** op **voltooien**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-181">On the **Completing the Certificate Export Wizard** page, click **Finish**.</span></span> <span data-ttu-id="97c1a-182">Klik op **OK** wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="97c1a-182">When prompted, click **OK**.</span></span>
    
<span data-ttu-id="97c1a-183">Installeer vervolgens de AD FS-service met deze opdracht met de Windows PowerShell-opdrachtprompt op ADFS1:</span><span class="sxs-lookup"><span data-stu-id="97c1a-183">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="97c1a-184">Wacht totdat de installatie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="97c1a-184">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="97c1a-185">Configureer vervolgens de AD FS-service met de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="97c1a-185">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="97c1a-186">Klik op **start**en klik vervolgens op het pictogram **serverbeheer**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-186">Click **Start**, and then click the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="97c1a-187">Klik in het structuurvenster van serverbeheer op **AD FS**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-187">In the tree pane of Server Manager, click **AD FS**.</span></span>
    
3. <span data-ttu-id="97c1a-188">Klik op de werkbalk aan de bovenkant op het oranje waarschuwingssymbool en klik vervolgens op **de federatieservice op deze server configureren**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-188">In the tool bar at the top, click the orange caution symbol, and then click **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="97c1a-189">Klik op de **welkomstpagina** van de configuratiewizard van Active Directory Federation Services op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-189">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, click **Next**.</span></span>
    
5. <span data-ttu-id="97c1a-190">Klik op de pagina **verbinding maken met AD DS** op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-190">On the **Connect to AD DS** page, click **Next**.</span></span>
    
6. <span data-ttu-id="97c1a-191">Op de pagina **service-eigenschappen opgeven** pagina:</span><span class="sxs-lookup"><span data-stu-id="97c1a-191">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="97c1a-192">Voor **SSL-certificaat**klikt u op de pijl-omlaag en klikt u vervolgens op het certificaat met de naam van de FQDN van de federatieservice.</span><span class="sxs-lookup"><span data-stu-id="97c1a-192">For **SSL Certificate**, click the down arrow, and then click the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="97c1a-193">Typ in **weergavenaam van de federatieservice**de naam van uw fictieve organisatie.</span><span class="sxs-lookup"><span data-stu-id="97c1a-193">In **Federation Service Display Name**, type the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="97c1a-194">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-194">Click **Next**.</span></span>
    
7. <span data-ttu-id="97c1a-195">Klik op de pagina **serviceaccount opgeven** op **selecteren** voor **accountnaam**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-195">On the **Specify Service Account** page, click **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="97c1a-196">Typ in **gebruikers- of serviceaccount selecteren\*\*\*\*ADFS-service**, klik op **namen controleren**en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-196">In **Select User or Service Account**, type **ADFS-Service**, click **Check Names**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="97c1a-197">Typ het wachtwoord voor het account van de ADFS-service in **accountwachtwoord**en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-197">In **Account Password**, type the password for the ADFS-Service account, and then click **Next**.</span></span>
    
10. <span data-ttu-id="97c1a-198">Klik op de pagina **configuratiedatabase opgeven** op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-198">On the **Specify Configuration Database** page, click **Next**.</span></span>
    
11. <span data-ttu-id="97c1a-199">Klik op de pagina **revisieopties** op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-199">On the **Review Options** page, click **Next**.</span></span>
    
12. <span data-ttu-id="97c1a-200">Klik op de pagina **controle van de vereisten** op **configureren**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-200">On the **Pre-requisite Checks** page, click **Configure**.</span></span>
    
13. <span data-ttu-id="97c1a-201">Klik op de pagina **Resultaten** op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-201">On the **Results** page, click **Close**.</span></span>
    
14. <span data-ttu-id="97c1a-202">Klik op **start**, klik op het pictogram voor het energiebeheer, klik op **opnieuw opstarten**en klik vervolgens op **doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-202">Click **Start**, click the power icon, click **Restart**, and then click **Continue**.</span></span>
    
<span data-ttu-id="97c1a-203">Maak vanuit de [Azure-portal](https://portal.azure.com) verbinding met PROXY1 met de CORP\\gebruiker1-accountreferenties.</span><span class="sxs-lookup"><span data-stu-id="97c1a-203">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="97c1a-204">Voer vervolgens deze stappen uit om het zelfondertekende certificaat te installeren op **zowel PROXY1 als APP1**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-204">Next, use these steps to install the self-signed certificate on **both PROXY1 and APP1**.</span></span>
  
1. <span data-ttu-id="97c1a-205">Klik op **Start**, typ **mmc.exe** en druk op **Enter**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-205">Click **Start**, type **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="97c1a-206">Klik op **Bestand > Snap-in toevoegen/verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-206">Click **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="97c1a-207">Dubbelklik in **Snap-ins toevoegen of verwijderen** op **Certificaten** in de lijst met beschikbare snap-ins, klik op **Computeraccount** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-207">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, click **Computer account**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="97c1a-208">Klik in **Computer selecteren** op **Voltooien** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-208">In **Select Computer**, click **Finish**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="97c1a-209">Open in het structuurvenster **certificaten (lokale computer) > persoonlijk > certificaten**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-209">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="97c1a-210">Klik met de rechtermuisknop op **persoonlijk**, klik op **alle taken**en klik vervolgens op **importeren**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-210">Right-click **Personal**, click **All tasks**, and then click **Import**.</span></span>
    
7. <span data-ttu-id="97c1a-211">Klik op **Volgende** op de **welkomstpagina**.  </span><span class="sxs-lookup"><span data-stu-id="97c1a-211">On the **Welcome** page, click **Next**.</span></span>
    
8. <span data-ttu-id="97c1a-212">Typ op de pagina **bestand dat u wilt importeren**, **\\\\adfs1 \\certs\\ssl.pfx** en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-212">On the **File to Import** page, type **\\\\adfs1\\certs\\ssl.pfx**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="97c1a-213">Typ op de pagina **persoonlijke sleutels beveiligen** het certificaatwachtwoord in bij**wachtwoord**en klik vervolgens op **volgende.**</span><span class="sxs-lookup"><span data-stu-id="97c1a-213">On the **Private key protection** page, type the certificate password in **Password**, and then click **Next.**</span></span>
    
10. <span data-ttu-id="97c1a-214">Klik op de pagina **certificaatarchief** op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-214">On the **Certificate store** page, click **Next.**</span></span>
    
11. <span data-ttu-id="97c1a-215">Klik op de pagina **voltooien** op **voltooien**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-215">On the **Completing** page, click **Finish**.</span></span>
    
12. <span data-ttu-id="97c1a-216">Klik op de pagina **certificaatarchief** op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-216">On the **Certificate Store** page, click **Next**.</span></span>
    
13. <span data-ttu-id="97c1a-217">Klik op **OK** wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="97c1a-217">When prompted, click **OK**.</span></span>
    
14. <span data-ttu-id="97c1a-218">Klik in het structuurvenster op **certificaten**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-218">Click **Certificates** in the tree pane.</span></span>
    
15. <span data-ttu-id="97c1a-219">Klik met de rechtermuisknop op het certificaat en klik vervolgens op **kopiëren**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-219">Right-click the certificate, and then click **Copy**.</span></span>
    
16. <span data-ttu-id="97c1a-220">Open in het structuurvenster **vertrouwde basiscertificeringsinstanties > certificaten**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-220">In the tree pane, open **Trusted Root Certification Authorities > Certificates**.</span></span>
    
17. <span data-ttu-id="97c1a-221">Beweeg de muisaanwijzer onder de lijst met geïnstalleerde certificaten, klik er met de rechtermuisknop op en klik vervolgens op **plakken**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-221">Move your mouse pointer below the list of installed certificates, right-click, and then click **Paste**.</span></span>
    
<span data-ttu-id="97c1a-222">Open een PowerShell-opdrachtprompt op beheerdersniveau en voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="97c1a-222">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="97c1a-223">Wacht totdat de installatie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="97c1a-223">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="97c1a-224">Gebruik de volgende stappen om de service webtoepassingsproxy zo te configureren dat ADFS1 als federatieserver wordt gebruikt:</span><span class="sxs-lookup"><span data-stu-id="97c1a-224">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="97c1a-225">Klik op **start**en klik vervolgens op **serverbeheer**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-225">Click **Start**, and then click **Server Manager**.</span></span>
    
2. <span data-ttu-id="97c1a-226">Klik in het structuurvenster op **externe toegang**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-226">In the tree pane, click **Remote Access**.</span></span>
    
3. <span data-ttu-id="97c1a-227">Klik op de werkbalk aan de bovenkant op het oranje waarschuwingssymbool en klik vervolgens op **de wizard webtoepassingsproxy** openen.</span><span class="sxs-lookup"><span data-stu-id="97c1a-227">In the tool bar at the top, click the orange caution symbol, and then click **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="97c1a-228">Klik op de **welkomstpagina** van de configuratiewizard webtoepassingsproxy op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-228">On the **Welcome** page of the Web Application Proxy Configuration Wizard, click **Next**.</span></span>
    
5. <span data-ttu-id="97c1a-229">Op de pagina **federatieserver**:</span><span class="sxs-lookup"><span data-stu-id="97c1a-229">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="97c1a-230">Typ de FQDN van de federatieservice in bij **naam van de federatieservice**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-230">Type your federation service FQDN in **Federation service name**.</span></span>
    
  - <span data-ttu-id="97c1a-231">Typ **CORP\\gebruiker1** in als **gebruikersnaam**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-231">Type **CORP\\User1** in **User name**.</span></span>
    
  - <span data-ttu-id="97c1a-232">Typ het wachtwoord voor het gebruiker1-account in bij **wachtwoord**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-232">Type the password for the User1 account in **Password**.</span></span>
    
  - <span data-ttu-id="97c1a-233">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-233">Click **Next**.</span></span>
    
6. <span data-ttu-id="97c1a-234">Klik op de pagina **AD FS-proxycertificaat** op de pijl-omlaag, klik op het certificaat met de FQDN van de federatieservice en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-234">On the **AD FS Proxy Certificate** page, click the down arrow, click the certificate with your federation service FQDN, and then click **Next**.</span></span>
    
7. <span data-ttu-id="97c1a-235">Klik op de **bevestigingspagina** op **configureren**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-235">On the **Confirmation** page, click **Configure**.</span></span>
    
8. <span data-ttu-id="97c1a-236">Klik op de pagina **Resultaten** op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-236">On the **Results** page, click **Close**.</span></span>

    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a><span data-ttu-id="97c1a-237">Fase 5: Office 365 configureren voor federatieve identiteit</span><span class="sxs-lookup"><span data-stu-id="97c1a-237">Phase 5: Configure Microsoft 365 for federated identity</span></span>

<span data-ttu-id="97c1a-238">Gebruik de [Azure-Portal](https://portal.azure.com) om verbinding te maken met de virtuele APP1-computer met de accountreferenties voor CORP\\gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="97c1a-238">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="97c1a-239">Volg deze stappen voor het configureren van Azure AD Connect en uw Microsoft 365-abonnement voor federatieve verificatie:</span><span class="sxs-lookup"><span data-stu-id="97c1a-239">Use these steps to configure Azure AD Connect and your Microsoft 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="97c1a-240">Dubbelklik op het bureaublad op **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-240">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="97c1a-241">Klik op de pagina **Welkom bij Azure AD Connect** op **configureren**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-241">On the **Welcome to Azure AD Connect** page, click **Configure**.</span></span>
    
3. <span data-ttu-id="97c1a-242">Klik op de pagina **Aanvullende taken** op **Gebruikersaanmelding wijzigen**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-242">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="97c1a-243">Typ op de pagina **verbinding maken met Azure AD** de naam en het wachtwoord van het globale beheerdersaccount en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-243">On the **Connect to Azure AD** page, type your global administrator account name and password, and then click **Next**.</span></span>
    
5. <span data-ttu-id="97c1a-244">Klik op de pagina **gebruikersaanmelding** op **federatie met AD FS**en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-244">On the **User sign-in** page, click **Federation with AD FS**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="97c1a-245">Klik op de pagina **AD FS-farm** op **een bestaande AD FS-farm gebruiken**, typ **ADFS1** bij **servernaam**en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-245">On the **AD FS farm** page, click **Use an existing AD FS farm**, type **ADFS1** in **Server Name**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="97c1a-246">Wanneer u wordt gevraagd om serverreferenties, voert u de referenties van het account CORP\\gebruiker1 in en klikt u op **OK**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-246">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then click **OK**.</span></span>
    
8. <span data-ttu-id="97c1a-247">Typ op de referentiepagina **domeinbeheerder** de waarde **CORP\\gebruiker1** in als **gebruikersnaam** en het wachtwoord van het account bij **wachtwoord**en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-247">On the **Domain Administrator** credentials page, type **CORP\\User1** in **Username** and the account password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="97c1a-248">Typ op de pagina **AD FS-serviceaccount** de waarde **CORP\\ADFS-service** als **gebruikersnaam van het domein** en het wachtwoord van het account bij **wachtwoord voor gebruikersdomein**en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-248">On the **AD FS service account** page, type **CORP\\ADFS-Service** in **Domain Username** and the account password in **Domain User Password**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="97c1a-249">Selecteer de naam van het domein dat u eerder hebt gemaakt en toegevoegd aan uw abonnement in fase 1 op de pagina **Azure AD-domein** bij **domein** en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-249">On the **Azure AD Domain** page, in **Domain**, select the name of the domain you previously created and added to your subscription in Phase 1, and then click **Next**.</span></span>
    
11. <span data-ttu-id="97c1a-250">Klik op de pagina **Gereed om te configureren** op **Configureren**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-250">On the **Ready to configure** page, click **Configure**.</span></span>
    
12. <span data-ttu-id="97c1a-251">Klik op de pagina **installeren voltooid** op **verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-251">On the **Installation complete** page, click **Verify**.</span></span>
    
    <span data-ttu-id="97c1a-252">U zou berichten moeten zien die aangeven dat zowel de intranet- als de internetconfiguratie is gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="97c1a-252">You should see messages indicating that both the intranet and Internet configuration was verified.</span></span>
    
13. <span data-ttu-id="97c1a-253">Klik op de pagina **Installatie voltooid** op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-253">On the **Installation complete** page, click **Exit**.</span></span>
    
<span data-ttu-id="97c1a-254">Om aan te tonen dat federatieve verificatie werkt:</span><span class="sxs-lookup"><span data-stu-id="97c1a-254">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="97c1a-255">Open een nieuwe privétab van uw browser op uw lokale computer en ga naar [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="97c1a-255">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="97c1a-256">Typ **user1@**\<the domain created in Phase 1> voor de aanmeldingsreferenties.</span><span class="sxs-lookup"><span data-stu-id="97c1a-256">For the sign-in credentials, type **user1@**\<the domain created in Phase 1>.</span></span> 
    
    <span data-ttu-id="97c1a-257">Als uw testdomein bijvoorbeeld **testlab.contoso.com** is, typt u 'user1@testlab.contoso.com'.</span><span class="sxs-lookup"><span data-stu-id="97c1a-257">For example, if your test domain is **testlab.contoso.com**, you would type "user1@testlab.contoso.com".</span></span> <span data-ttu-id="97c1a-258">Druk op Tab of laat Microsoft 365 u automatisch omleiden.</span><span class="sxs-lookup"><span data-stu-id="97c1a-258">Press TAB or allow Microsoft 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="97c1a-259">U zou nu een pagina moeten zien met **Uw verbinding is niet privé**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-259">You should now see a **Your connection is not private** page.</span></span> <span data-ttu-id="97c1a-260">U ziet dit omdat u een zelfondertekend certificaat op ADFS1 heeft geïnstalleerd dat uw desktopcomputer niet kan valideren.</span><span class="sxs-lookup"><span data-stu-id="97c1a-260">You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer cannot validate.</span></span> <span data-ttu-id="97c1a-261">Bij een productie-implementatie van federatieve verificatie gebruikt u een certificaat van een vertrouwde certificeringsinstantie en zien uw gebruikers deze pagina niet.</span><span class="sxs-lookup"><span data-stu-id="97c1a-261">In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="97c1a-262">Klik op de pagina **Uw verbinding is niet privé** op **Geavanceerd** en klik vervolgens op **Doorgaan naar \<your federation service FQDN>**.</span><span class="sxs-lookup"><span data-stu-id="97c1a-262">On the **Your connection is not private** page, click **Advanced**, and then click **Proceed to \<your federation service FQDN>**.</span></span> 
    
4. <span data-ttu-id="97c1a-263">Ga op de pagina met de naam van uw fictieve organisatie als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="97c1a-263">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="97c1a-264">**CORP\\gebruiker1** voor de naam</span><span class="sxs-lookup"><span data-stu-id="97c1a-264">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="97c1a-265">Het wachtwoord voor het gebruiker1-account</span><span class="sxs-lookup"><span data-stu-id="97c1a-265">The password for the User1 account</span></span>
    
    <span data-ttu-id="97c1a-266">U zou de pagina van **Microsoft Office voor Thuisgebruik** moeten zien.</span><span class="sxs-lookup"><span data-stu-id="97c1a-266">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="97c1a-267">Deze procedure laat zien dat uw proefabonnement is verbonden met het AD DS corp.contoso.com-domein dat wordt gehost op DC1.</span><span class="sxs-lookup"><span data-stu-id="97c1a-267">This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1.</span></span> <span data-ttu-id="97c1a-268">Hier volgen de basisbeginselen van het verificatieproces:</span><span class="sxs-lookup"><span data-stu-id="97c1a-268">Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="97c1a-269">Wanneer u het federatieve domein gebruikt dat u in fase 1 hebt gemaakt binnen de aanmeldingsaccountnaam, leidt Microsoft 365 uw browser om naar uw federatiediensten FQDN en PROXY1.</span><span class="sxs-lookup"><span data-stu-id="97c1a-269">When you use the federated domain that you created in Phase 1 within the sign-in account name, Microsoft 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="97c1a-270">PROXY1 stuurt uw lokale computer naar de aanmeldingspagina voor fictief bedrijf.</span><span class="sxs-lookup"><span data-stu-id="97c1a-270">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="97c1a-271">Wanneer u CORP\\gebruiker1 en het wachtwoord voor PROXY1 verzendt, worden ze doorgestuurd naar ADFS1.</span><span class="sxs-lookup"><span data-stu-id="97c1a-271">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="97c1a-272">ADFS1 valideert CORP\\gebruiker1 en het wachtwoord met DC1 en stuurt uw lokale computer een beveiligingstoken.</span><span class="sxs-lookup"><span data-stu-id="97c1a-272">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="97c1a-273">Uw lokale computer verzendt het beveiligingstoken naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97c1a-273">Your local computer sends the security token to Microsoft 365.</span></span>
    
6. <span data-ttu-id="97c1a-274">Microsoft 365 valideert dat het beveiligingstoken is gemaakt door ADFS1 en biedt toegang.</span><span class="sxs-lookup"><span data-stu-id="97c1a-274">Microsoft 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="97c1a-275">Uw proefabonnement is nu geconfigureerd met federatieve verificatie.</span><span class="sxs-lookup"><span data-stu-id="97c1a-275">Your trial subscription is now configured with federated authentication.</span></span> <span data-ttu-id="97c1a-276">U kunt deze ontwikkel- en testomgeving gebruiken voor geavanceerde verificatiescenario's.</span><span class="sxs-lookup"><span data-stu-id="97c1a-276">You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="97c1a-277">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="97c1a-277">Next step</span></span>

<span data-ttu-id="97c1a-278">Zie [federatieve authenticatie van hoge beschikbaarheid voor Microsoft 365 in azure implementeren](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)wanneer u klaar bent om te beginnen met de implementatie, federatieve verificatie van hoge beschikbaarheid voor microsoft 365 in Azure.</span><span class="sxs-lookup"><span data-stu-id="97c1a-278">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 in Azure, see [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span></span>
  
