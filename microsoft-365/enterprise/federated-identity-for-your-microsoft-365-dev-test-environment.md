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
ms.openlocfilehash: 0fb8c55f5b7291cdc6bcec636981a9d31015e723
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487682"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="ae471-103">Federatieve identiteit voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="ae471-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="ae471-104">*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="ae471-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="ae471-105">Microsoft 365 ondersteunt federatieve identiteit.</span><span class="sxs-lookup"><span data-stu-id="ae471-105">Microsoft 365 supports federated identity.</span></span> <span data-ttu-id="ae471-106">Dit betekent dat in plaats van de validatie van referenties zelf uit te voeren, Microsoft 365 de verbindende gebruiker verwijst naar een federatieve verificatieserver die Microsoft 365 vertrouwt.</span><span class="sxs-lookup"><span data-stu-id="ae471-106">This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts.</span></span> <span data-ttu-id="ae471-107">Als de inloggegevens van de gebruiker correct zijn, geeft de federatieve verificatieserver een beveiligingstoken uit dat de client vervolgens naar Microsoft 365 stuurt als bewijs van verificatie.</span><span class="sxs-lookup"><span data-stu-id="ae471-107">If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication.</span></span> <span data-ttu-id="ae471-108">Federatieve identiteit zorgt voor de offloading en schaalbaarheid van verificatie voor een Microsoft 365-abonnement en geavanceerde verificatie- en beveiligingsscenario's.</span><span class="sxs-lookup"><span data-stu-id="ae471-108">Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="ae471-109">In dit artikel wordt uitgelegd hoe u federatieve verificatie voor uw Microsoft 365-testomgeving configureert, wat resulteert in het volgende:</span><span class="sxs-lookup"><span data-stu-id="ae471-109">This article describes how to configure federated authentication for your Microsoft 365 test environment, resulting in the following:</span></span>

![De federatieve verificatie voor Microsoft 365-testomgeving](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="ae471-111">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="ae471-111">This configuration consists of:</span></span>
  
- <span data-ttu-id="ae471-112">Een Microsoft 365 E5-proefabonnement of productie abonnement.</span><span class="sxs-lookup"><span data-stu-id="ae471-112">A Microsoft 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="ae471-113">Een eenvoudiger organisatie intranet verbonden met internet, bestaande uit vijf virtuele machines op een subnet van een Azure virtueel netwerk (DC1, APP1, CLIENT1, ADFS1 en PROXY1).</span><span class="sxs-lookup"><span data-stu-id="ae471-113">A simplified organization intranet connected to the internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1).</span></span> <span data-ttu-id="ae471-114">Azure AD Connect wordt uitgevoerd op APP1 om de lijst met accounts in het Active Directory Domain Services-domein te synchroniseren met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae471-114">Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Microsoft 365.</span></span> <span data-ttu-id="ae471-115">PROXY1 ontvangt de binnenkomende verificatieaanvragen.</span><span class="sxs-lookup"><span data-stu-id="ae471-115">PROXY1 receives the incoming authentication requests.</span></span> <span data-ttu-id="ae471-116">ADFS1 valideert referenties met DC1 en beveiligingstokens.</span><span class="sxs-lookup"><span data-stu-id="ae471-116">ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="ae471-117">Het instellen van deze testomgeving omvat vijf fasen:</span><span class="sxs-lookup"><span data-stu-id="ae471-117">Setting up this test environment involves five phases:</span></span>
- [<span data-ttu-id="ae471-118">Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="ae471-118">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="ae471-119">Fase 2: maak de AD FS-server</span><span class="sxs-lookup"><span data-stu-id="ae471-119">Phase 2: Create the AD FS server</span></span>](#phase-2-create-the-ad-fs-server)
- [<span data-ttu-id="ae471-120">Fase 3: de webproxyserver maken</span><span class="sxs-lookup"><span data-stu-id="ae471-120">Phase 3: Create the web proxy server</span></span>](#phase-3-create-the-web-proxy-server)
- [<span data-ttu-id="ae471-121">Fase 4: maak een zelfondertekend certificaat en configureer ADFS1 en PROXY1.</span><span class="sxs-lookup"><span data-stu-id="ae471-121">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [<span data-ttu-id="ae471-122">Fase 5: Office 365 configureren voor federatieve identiteit</span><span class="sxs-lookup"><span data-stu-id="ae471-122">Phase 5: Configure Microsoft 365 for federated identity</span></span>](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> <span data-ttu-id="ae471-123">U kunt deze testomgeving niet configureren met een Azure-proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="ae471-123">You can't configure this test environment with an Azure Trial subscription.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="ae471-124">Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="ae471-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="ae471-125">Volg de instructies in [wachtwoord-hash-synchronisatie voor Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="ae471-125">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="ae471-126">De uiteindelijke configuratie ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="ae471-126">Your resulting configuration looks like this:</span></span>
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="ae471-128">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="ae471-128">This configuration consists of:</span></span>
  
- <span data-ttu-id="ae471-129">Een Microsoft 365 E5-proefabonnement of betaalde abonnementen.</span><span class="sxs-lookup"><span data-stu-id="ae471-129">A Microsoft 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="ae471-130">Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines op een subnet van een Azure virtueel netwerk.</span><span class="sxs-lookup"><span data-stu-id="ae471-130">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="ae471-131">Azure AD Connect wordt uitgevoerd op APP1 om het TESTLAB Active Directory Domain Services (AD DS)-domein te synchroniseren met de Azure AD-Tenant van uw Microsoft 365-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="ae471-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="ae471-132">Fase 2: maak de AD FS-server</span><span class="sxs-lookup"><span data-stu-id="ae471-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="ae471-133">Een AD FS-server biedt federatieve verificatie tussen Microsoft 365 en de accounts in het corp.contoso.com-domein dat wordt gehost op DC1.</span><span class="sxs-lookup"><span data-stu-id="ae471-133">An AD FS server provides federated authentication between Microsoft 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="ae471-134">Als u een virtuele machine van Azure wilt maken voor ADFS1, vult u de naam van uw abonnement, de bronnengroep en de Azure-locatie voor uw basisconfiguratie in en voert u deze opdrachten uit op de opdrachtprompt van de Azure PowerShell op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="ae471-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="ae471-135">Gebruik vervolgens de [Azure-portal](https://portal.azure.com) om verbinding te maken met de ADFS1 virtuele machine met behulp van de ADFS1-naam en het wachtwoord van de lokale beheerdersaccount, en open vervolgens een Windows PowerShell-opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="ae471-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="ae471-136">Als u de naamresolutie en de netwerkcommunicatie tussen ADFS1 en DC1 wilt controleren, voert u de opdracht **ping dc1.corp.contoso.com** uit en controleert u of er vier antwoorden zijn.</span><span class="sxs-lookup"><span data-stu-id="ae471-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="ae471-137">Vervolgens voegt u de virtuele machine ADFS1 toe aan het CORP-domein met deze opdrachten bij de Windows PowerShell-prompt op ADFS1.</span><span class="sxs-lookup"><span data-stu-id="ae471-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="ae471-138">De uiteindelijke configuratie ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="ae471-138">Your resulting configuration looks like this:</span></span>
  
![De AD FS-server die is toegevoegd aan de testomgeving van DirSync voor Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="ae471-140">Fase 3: de webproxyserver maken</span><span class="sxs-lookup"><span data-stu-id="ae471-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="ae471-141">PROXY1 biedt proxy van authenticatieberichten tussen gebruikers die proberen te authenticeren en ADFS1.</span><span class="sxs-lookup"><span data-stu-id="ae471-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="ae471-142">Als u een virtuele machine van Azure wilt maken voor PROXY1, vult u de naam van de resourcegroep en de Azure-locatie in en voert u deze opdrachten uit op de opdrachtprompt van de Azure PowerShell op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="ae471-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
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
> <span data-ttu-id="ae471-143">PROXY1 krijgt een statisch openbaar IP-adres toegewezen, omdat u een openbaar DNS-record maakt dat ernaar verwijst en het niet mag veranderen wanneer u de virtuele machine PROXY1 opnieuw opstart.</span><span class="sxs-lookup"><span data-stu-id="ae471-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span>
  
<span data-ttu-id="ae471-144">Voeg vervolgens een regel toe aan de groep netwerkbeveiliging voor het CorpNet-subnet, zodat ongevraagde inkomende verkeer van Internet naar PROXY1's Private IP Address en TCP-poort 443 wordt toegestaan.</span><span class="sxs-lookup"><span data-stu-id="ae471-144">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the internet to PROXY1's private IP address and TCP port 443.</span></span> <span data-ttu-id="ae471-145">Voer deze opdrachten uit vanaf de opdrachtprompt van Azure PowerShell op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="ae471-145">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="ae471-146">Gebruik vervolgens de [Azure-portal](https://portal.azure.com) om verbinding te maken met de virtuele machine PROXY1 met behulp van de PROXY1-naam en het wachtwoord van de lokale beheerdersaccount, en open vervolgens een Windows PowerShell-opdrachtprompt op PROXY1.</span><span class="sxs-lookup"><span data-stu-id="ae471-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="ae471-147">Als u de naamresolutie en de netwerkcommunicatie tussen PROXY1 en DC1 wilt controleren, voert u de opdracht **ping dc1.corp.contoso.com** uit en controleert u of er vier antwoorden zijn.</span><span class="sxs-lookup"><span data-stu-id="ae471-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="ae471-148">Vervolgens voegt u de virtuele machine PROXY1 toe aan het CORP-domein met deze opdrachten bij de Windows PowerShell-prompt op PROXY1.</span><span class="sxs-lookup"><span data-stu-id="ae471-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="ae471-149">Geef het openbare IP-adres van PROXY1 weer met de volgende Azure PowerShell-opdrachten op uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="ae471-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer.</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="ae471-150">Werk vervolgens met uw openbare DNS-provider om een nieuw openbaar DNS A-record aan te maken voor **fs.testlab.**\<*your DNS domain name*></span><span class="sxs-lookup"><span data-stu-id="ae471-150">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<*your DNS domain name*></span></span> <span data-ttu-id="ae471-151">dat wordt omgezet naar het IP-adres dat wordt weergegeven door de **Write-Host**.</span><span class="sxs-lookup"><span data-stu-id="ae471-151">that resolves to the IP address displayed by the **Write-Host** command.</span></span> <span data-ttu-id="ae471-152">De **fs.testlab.**\<*your DNS domain name*></span><span class="sxs-lookup"><span data-stu-id="ae471-152">The **fs.testlab.**\<*your DNS domain name*></span></span> <span data-ttu-id="ae471-153">wordt hierna de *federatiedienst FQDN* genoemd.</span><span class="sxs-lookup"><span data-stu-id="ae471-153">is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="ae471-154">Gebruik vervolgens de [Azure-portal](https://portal.azure.com) om verbinding te maken met de virtuele machine DC1 met behulp van de CORP\\gebruiker1-referenties en voer vervolgens de volgende opdrachten uit op een Windows PowerShell-opdrachtprompt op beheerdersniveau:</span><span class="sxs-lookup"><span data-stu-id="ae471-154">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="ae471-155">Met deze opdrachten maakt u een interne DNS A-record, zodat virtuele machines in het virtuele netwerk van Azure de FQDN-naam van het interne Federation service-ADFS1's kunnen omzetten in een particulier IP-adres van.</span><span class="sxs-lookup"><span data-stu-id="ae471-155">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation service FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="ae471-156">De uiteindelijke configuratie ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="ae471-156">Your resulting configuration looks like this:</span></span>
  
![De proxyserver van de webtoepassing is toegevoegd aan de testomgeving van DirSync voor Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="ae471-158">Fase 4: maak een zelfondertekend certificaat en configureer ADFS1 en PROXY1.</span><span class="sxs-lookup"><span data-stu-id="ae471-158">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="ae471-159">In deze fase maakt u een zelfondertekend digitaal certificaat voor de FQDN van de federatieservice en configureert u ADFS1 en PROXY1 als een AD FS-farm.</span><span class="sxs-lookup"><span data-stu-id="ae471-159">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="ae471-160">Gebruik eerst de [Azure-portal](https://portal.azure.com) om verbinding te maken met de virtuele DC1-machine met de referenties voor CORP\\gebruiker1 en open vervolgens een opdrachtprompt op beheerdersniveau in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae471-160">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="ae471-161">Maak vervolgens een AD FS-serviceaccount met deze opdracht op de Windows PowerShell-opdrachtprompt op DC1:</span><span class="sxs-lookup"><span data-stu-id="ae471-161">Next, create an AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="ae471-162">Met deze opdracht wordt u gevraagd het wachtwoord van het account op te geven.</span><span class="sxs-lookup"><span data-stu-id="ae471-162">Note that this command prompts you to supply the account password.</span></span> <span data-ttu-id="ae471-163">Kies een sterk wachtwoord en sla dit op in een beveiligde locatie.</span><span class="sxs-lookup"><span data-stu-id="ae471-163">Choose a strong password and record it in a secured location.</span></span> <span data-ttu-id="ae471-164">Dit hebt u nodig voor deze fase en voor fase 5.</span><span class="sxs-lookup"><span data-stu-id="ae471-164">You will need it for this phase and for Phase 5.</span></span>
  
<span data-ttu-id="ae471-165">Gebruik de [Azure-Portal](https://portal.azure.com) om verbinding te maken met de virtuele ADFS1-computer met de accountreferenties voor CORP\\gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="ae471-165">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials.</span></span> <span data-ttu-id="ae471-166">Open een Windows PowerShell-opdrachtprompt op beheerdersniveau op ADFS1, vul de FQDN van de federatiedienst in en voer vervolgens deze opdrachten uit om een zelfondertekend certificaat te maken:</span><span class="sxs-lookup"><span data-stu-id="ae471-166">Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="ae471-167">Gebruik vervolgens deze stappen om het nieuwe, zelfondertekend certificaat als een bestand op te slaan.</span><span class="sxs-lookup"><span data-stu-id="ae471-167">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="ae471-168">Selecteer **Start**, typ **mmc.exe**en druk op **Enter**.</span><span class="sxs-lookup"><span data-stu-id="ae471-168">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="ae471-169">Selecteer **File**invoeg  >  **toepassing voor bestands toevoegen/verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="ae471-169">Select **File** > **Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="ae471-170">Dubbel **Klik in de**lijst met beschikbare invoegtoepassingen in de lijst met beschikbare modules op **certificaten** en **Selecteer vervolgens** **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-170">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="ae471-171">Selecteer in **computer selecteren**de optie **Voltooien**en selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae471-171">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="ae471-172">Open in het structuurvenster **certificaten (lokale computer) > persoonlijk > certificaten**.</span><span class="sxs-lookup"><span data-stu-id="ae471-172">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="ae471-173">Selecteer het certificaat met behulp van de Federatie service-FQDN en houd deze ingedrukt (of klik erop met de rechtermuisknop), selecteer **alle taken**en selecteer vervolgens **exporteren**.</span><span class="sxs-lookup"><span data-stu-id="ae471-173">Select and hold (or right-click) the certificate with your federation service FQDN, select **All tasks**, and then select **Export**.</span></span>
    
7. <span data-ttu-id="ae471-174">Selecteer **volgende**op de **welkomst** pagina.</span><span class="sxs-lookup"><span data-stu-id="ae471-174">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="ae471-175">Selecteer op de pagina **persoonlijke sleutel exporteren** de optie **Ja**en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-175">On the **Export Private Key** page, select **Yes**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="ae471-176">Selecteer op de pagina **bestandsindeling exporteren** de optie **alle uitgebreide eigenschappen exporteren**en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-176">On the **Export File Format** page, select **Export all extended properties**, and then select **Next**.</span></span>
    
10. <span data-ttu-id="ae471-177">Selecteer **wachtwoord** op de pagina **beveiliging** en voer een wachtwoord in **wachtwoord** in en **Bevestig uw wachtwoord.**</span><span class="sxs-lookup"><span data-stu-id="ae471-177">On the **Security** page, select **Password** and enter a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="ae471-178">Selecteer op de pagina **bestand to export** de optie **Browse**.</span><span class="sxs-lookup"><span data-stu-id="ae471-178">On the **File to Export** page, select **Browse**.</span></span>
    
12. <span data-ttu-id="ae471-179">Blader naar de **map C \\ : certs** , Voer **SSL** in de **bestandsnaam**in en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="ae471-179">Browse to the **C:\\Certs** folder, enter **SSL** in **File name**, and then select **Save.**</span></span>
    
13. <span data-ttu-id="ae471-180">Selecteer op de pagina **te exporteren bestand** de optie **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-180">On the **File to Export** page, select **Next**.</span></span>
    
14. <span data-ttu-id="ae471-181">Selecteer op de pagina **de wizard Certificaat exporteren** volt **ooien**.</span><span class="sxs-lookup"><span data-stu-id="ae471-181">On the **Completing the Certificate Export Wizard** page, select **Finish**.</span></span> <span data-ttu-id="ae471-182">Selecteer **OK**wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="ae471-182">When prompted, select **OK**.</span></span>
    
<span data-ttu-id="ae471-183">Installeer vervolgens de AD FS-service met deze opdracht met de Windows PowerShell-opdrachtprompt op ADFS1:</span><span class="sxs-lookup"><span data-stu-id="ae471-183">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="ae471-184">Wacht totdat de installatie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="ae471-184">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="ae471-185">Configureer vervolgens de AD FS-service met de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="ae471-185">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="ae471-186">Selecteer **Start**en selecteer vervolgens het pictogram **Server beheer** .</span><span class="sxs-lookup"><span data-stu-id="ae471-186">Select **Start**, and then select the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="ae471-187">Selecteer in het deelvenster structuur van server beheer de optie **AD FS**.</span><span class="sxs-lookup"><span data-stu-id="ae471-187">In the tree pane of Server Manager, select **AD FS**.</span></span>
    
3. <span data-ttu-id="ae471-188">Selecteer op de werkbalk aan de bovenkant het oranje waarschuwingssymbool en selecteer vervolgens **de Federatie service configureren op deze server**.</span><span class="sxs-lookup"><span data-stu-id="ae471-188">In the tool bar at the top, select the orange caution symbol, and then select **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="ae471-189">Selecteer op de **welkomst** pagina van de wizard Active Directory Federation Services configureren de optie **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-189">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="ae471-190">Selecteer op de pagina **verbinding maken met AD DS** de optie **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-190">On the **Connect to AD DS** page, select **Next**.</span></span>
    
6. <span data-ttu-id="ae471-191">Op de pagina **service-eigenschappen opgeven** pagina:</span><span class="sxs-lookup"><span data-stu-id="ae471-191">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="ae471-192">Selecteer voor **SSL-certificaat**de pijl-omlaag en selecteer vervolgens het certificaat met de naam van de FQDN voor de Federation service.</span><span class="sxs-lookup"><span data-stu-id="ae471-192">For **SSL Certificate**, select the down arrow, and then select the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="ae471-193">Voer in de **weergavenaam van de Federation service**de naam van uw fictieve organisatie in.</span><span class="sxs-lookup"><span data-stu-id="ae471-193">In **Federation Service Display Name**, enter the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="ae471-194">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-194">Select **Next**.</span></span>
    
7. <span data-ttu-id="ae471-195">Selecteer op de pagina **Service account opgeven** de optie **selecteren** voor **account naam**.</span><span class="sxs-lookup"><span data-stu-id="ae471-195">On the **Specify Service Account** page, select **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="ae471-196">Typ **ADFS-service**in **Select User of service account**, selecteer **Namen controleren**en selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae471-196">In **Select User or Service Account**, enter **ADFS-Service**, select **Check Names**, and then select **OK**.</span></span>
    
9. <span data-ttu-id="ae471-197">Voer het wachtwoord in van het **account**dat u hebt opgegeven voor het ADFS-Service account en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-197">In **Account Password**, enter the password for the ADFS-Service account, and then select **Next**.</span></span>
    
10. <span data-ttu-id="ae471-198">Selecteer op de pagina **configuratie database opgeven** de optie **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-198">On the **Specify Configuration Database** page, select **Next**.</span></span>
    
11. <span data-ttu-id="ae471-199">Selecteer op de pagina **opties controleren** de optie **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-199">On the **Review Options** page, select **Next**.</span></span>
    
12. <span data-ttu-id="ae471-200">Selecteer op de pagina **controle vereisten** de optie **configureren**.</span><span class="sxs-lookup"><span data-stu-id="ae471-200">On the **Pre-requisite Checks** page, select **Configure**.</span></span>

13. <span data-ttu-id="ae471-201">Selecteer op de pagina **resultaten** de optie **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="ae471-201">On the **Results** page, select **Close**.</span></span>
    
14. <span data-ttu-id="ae471-202">Selecteer **Start**, selecteer het pictogram van de stekker, selecteer **opnieuw opstarten**en selecteer vervolgens **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="ae471-202">Select **Start**, select the power icon, select **Restart**, and then select **Continue**.</span></span>
    
<span data-ttu-id="ae471-203">Maak vanuit de [Azure-portal](https://portal.azure.com) verbinding met PROXY1 met de CORP\\gebruiker1-accountreferenties.</span><span class="sxs-lookup"><span data-stu-id="ae471-203">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="ae471-204">Voer vervolgens deze stappen uit om het zelfondertekende certificaat te installeren op **zowel PROXY1 als APP1**.</span><span class="sxs-lookup"><span data-stu-id="ae471-204">Next, use these steps to install the self-signed certificate on **both PROXY1 and APP1**.</span></span>
  
1. <span data-ttu-id="ae471-205">Selecteer **Start**, typ **mmc.exe**en druk op **Enter**.</span><span class="sxs-lookup"><span data-stu-id="ae471-205">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="ae471-206">Selecteer **bestand > module toevoegen/verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="ae471-206">Select **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="ae471-207">Dubbel **Klik in de**lijst met beschikbare invoegtoepassingen in de lijst met beschikbare modules op **certificaten** en **Selecteer vervolgens** **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-207">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="ae471-208">Selecteer in **computer selecteren**de optie **Voltooien**en selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae471-208">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="ae471-209">Open **certificates (local computer)**  >  **Personal**  >  **certificates**in het deelvenster structuur.</span><span class="sxs-lookup"><span data-stu-id="ae471-209">In the tree pane, open **Certificates (Local Computer)** > **Personal** > **Certificates**.</span></span>
    
6. <span data-ttu-id="ae471-210">Selecteer of klik met de rechtermuisknop op **persoonlijk**, selecteer **alle taken**en selecteer vervolgens **importeren**.</span><span class="sxs-lookup"><span data-stu-id="ae471-210">Select and hold (or right-click) **Personal**, select **All tasks**, and then select **Import**.</span></span>
    
7. <span data-ttu-id="ae471-211">Selecteer **volgende**op de **welkomst** pagina.</span><span class="sxs-lookup"><span data-stu-id="ae471-211">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="ae471-212">Voer op de pagina **te importeren bestand** de \*\* \\ \\ adfs1- \\ certificerings versie van \\ SSL. pfx\*\*in en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-212">On the **File to Import** page, enter **\\\\adfs1\\certs\\ssl.pfx**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="ae471-213">Voer op de pagina **Persoonlijke sleutelbeveiliging** het certificaatwachtwoord in het **wachtwoord**in en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="ae471-213">On the **Private key protection** page, enter the certificate password in **Password**, and then select **Next.**</span></span>
    
10. <span data-ttu-id="ae471-214">Selecteer op de pagina **certificaatarchief** de optie **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="ae471-214">On the **Certificate store** page, select **Next.**</span></span>
    
11. <span data-ttu-id="ae471-215">Selecteer op de pagina **volt** ooien de optie **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="ae471-215">On the **Completing** page, select **Finish**.</span></span>
    
12. <span data-ttu-id="ae471-216">Selecteer op de pagina **certificaatarchief** de optie **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-216">On the **Certificate Store** page, select **Next**.</span></span>
    
13. <span data-ttu-id="ae471-217">Selecteer **OK**wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="ae471-217">When prompted, select **OK**.</span></span>
    
14. <span data-ttu-id="ae471-218">Selecteer in het deelvenster Structuur de optie **certificaten**.</span><span class="sxs-lookup"><span data-stu-id="ae471-218">In the tree pane, select **Certificates**.</span></span>
    
15. <span data-ttu-id="ae471-219">Selecteer het certificaat en houd deze ingedrukt (of klik er met de rechtermuisknop op) en selecteer **kopiëren**.</span><span class="sxs-lookup"><span data-stu-id="ae471-219">Select and hold (or right-click) the certificate, and then select **Copy**.</span></span>
    
16. <span data-ttu-id="ae471-220">Open in het deelvenster Structuur de certificaten van **vertrouwde basiscertificeringsinstanties**  >  **Certificates**.</span><span class="sxs-lookup"><span data-stu-id="ae471-220">In the tree pane, open **Trusted Root Certification Authorities** > **Certificates**.</span></span>
    
17. <span data-ttu-id="ae471-221">Beweeg de muisaanwijzer onder de lijst met geïnstalleerde certificaten, selecteer en houd de muisknop ingedrukt (of klik er met de rechtermuisknop op) en selecteer vervolgens **Plakken**.</span><span class="sxs-lookup"><span data-stu-id="ae471-221">Move your mouse pointer below the list of installed certificates, select and hold (or right-click), and then select **Paste**.</span></span>
    
<span data-ttu-id="ae471-222">Open een PowerShell-opdrachtprompt op beheerdersniveau en voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="ae471-222">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="ae471-223">Wacht totdat de installatie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="ae471-223">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="ae471-224">Gebruik de volgende stappen om de service webtoepassingsproxy zo te configureren dat ADFS1 als federatieserver wordt gebruikt:</span><span class="sxs-lookup"><span data-stu-id="ae471-224">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="ae471-225">Selecteer **Start**en selecteer **Server beheer**.</span><span class="sxs-lookup"><span data-stu-id="ae471-225">Select **Start**, and then select **Server Manager**.</span></span>
    
2. <span data-ttu-id="ae471-226">Selecteer in het deelvenster Structuur de optie **externe toegang**.</span><span class="sxs-lookup"><span data-stu-id="ae471-226">In the tree pane, select **Remote Access**.</span></span>
    
3. <span data-ttu-id="ae471-227">Selecteer op de werkbalk aan de bovenkant het oranje waarschuwingssymbool en selecteer vervolgens **de wizard van de**Webtoepassingsproxy-toepassing.</span><span class="sxs-lookup"><span data-stu-id="ae471-227">In the tool bar at the top, select the orange caution symbol, and then select **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="ae471-228">Selecteer op de **welkomst** pagina van de wizard Configuratie van webtoepassingsproxy de optie **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-228">On the **Welcome** page of the Web Application Proxy Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="ae471-229">Op de pagina **federatieserver**:</span><span class="sxs-lookup"><span data-stu-id="ae471-229">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="ae471-230">Voer in het vak **naam van Federation service** de Federation service-FQDN in.</span><span class="sxs-lookup"><span data-stu-id="ae471-230">In the **Federation service name** box, enter your federation service FQDN.</span></span>
    
  - <span data-ttu-id="ae471-231">Voer in het vak **gebruikersnaam** **Corp \\ gebruiker1**in.</span><span class="sxs-lookup"><span data-stu-id="ae471-231">In the **User name** box, enter **CORP\\User1**.</span></span>
    
  - <span data-ttu-id="ae471-232">Voer in het vak **wachtwoord** het wachtwoord in voor het account gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="ae471-232">In the **Password** box, enter the password for the User1 account.</span></span>
    
  - <span data-ttu-id="ae471-233">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-233">Select **Next**.</span></span>
    
6. <span data-ttu-id="ae471-234">Selecteer op de pagina **AD FS-proxy certificaat** de pijl-omlaag, selecteer het certificaat met de FQDN-service-FQDN en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-234">On the **AD FS Proxy Certificate** page, select the down arrow, select the certificate with your federation service FQDN, and then select **Next**.</span></span>
    
7. <span data-ttu-id="ae471-235">Selecteer op de pagina **confirmation** de optie **Configure**.</span><span class="sxs-lookup"><span data-stu-id="ae471-235">On the **Confirmation** page, select **Configure**.</span></span>
    
8. <span data-ttu-id="ae471-236">Selecteer op de pagina **resultaten** de optie **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="ae471-236">On the **Results** page, select **Close**.</span></span>
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a><span data-ttu-id="ae471-237">Fase 5: Office 365 configureren voor federatieve identiteit</span><span class="sxs-lookup"><span data-stu-id="ae471-237">Phase 5: Configure Microsoft 365 for federated identity</span></span>

<span data-ttu-id="ae471-238">Gebruik de [Azure-Portal](https://portal.azure.com) om verbinding te maken met de virtuele APP1-computer met de accountreferenties voor CORP\\gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="ae471-238">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="ae471-239">Volg deze stappen voor het configureren van Azure AD Connect en uw Microsoft 365-abonnement voor federatieve verificatie:</span><span class="sxs-lookup"><span data-stu-id="ae471-239">Use these steps to configure Azure AD Connect and your Microsoft 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="ae471-240">Dubbelklik op het bureaublad op **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="ae471-240">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="ae471-241">Selecteer op de pagina **Welkom bij Azure AD Connect** de optie **configureren**.</span><span class="sxs-lookup"><span data-stu-id="ae471-241">On the **Welcome to Azure AD Connect** page, select **Configure**.</span></span>
    
3. <span data-ttu-id="ae471-242">Selecteer op de pagina **extra taken** de optie **gebruikersaanmelding wijzigen**en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-242">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="ae471-243">Voer op de pagina **verbinding maken met Azure AD** de naam en het wachtwoord van uw globale beheerder account in en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-243">On the **Connect to Azure AD** page, enter your global administrator account name and password, and then select **Next**.</span></span>
    
5. <span data-ttu-id="ae471-244">Selecteer **Federatie met AD FS**op de aanmeldingspagina van de **gebruiker** en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-244">On the **User sign-in** page, select **Federation with AD FS**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="ae471-245">Selecteer op de pagina **AD FS-Farm** de optie **een bestaande AD FS-farm gebruiken**, typ **ADFS1** in het vak **Server naam** en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-245">On the **AD FS farm** page, select **Use an existing AD FS farm**, enter **ADFS1** in the **Server Name** box, and then select **Next**.</span></span>
    
7. <span data-ttu-id="ae471-246">Wanneer u wordt gevraagd om Server referenties, voert u de referenties van het account van de \\ gebruiker1-account in en selecteert u **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae471-246">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then select **OK**.</span></span>
    
8. <span data-ttu-id="ae471-247">Voer op de pagina referenties van **domeinbeheerder** **Corp \\ gebruiker1** in het **vak Gebruikersnaam** in, voer het accountwachtwoord in het vak **wachtwoord** in en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-247">On the **Domain Administrator** credentials page, enter **CORP\\User1** in the **Username** box, enter the account password in the **Password** box, and then select **Next**.</span></span>
    
9. <span data-ttu-id="ae471-248">Voer op de pagina **AD FS-serviceaccount** de naam **Corp \\ -service** in in het vak **domeinnaam** van het account, voer het accountwachtwoord in het vak **wachtwoord voor domeingebruikers** in en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-248">On the **AD FS service account** page, enter **CORP\\ADFS-Service** in the **Domain Username** box, enter the account password in the **Domain User Password** box, and then select **Next**.</span></span>
    
10. <span data-ttu-id="ae471-249">Selecteer op de pagina **Azure AD domain** in **Domain**de naam van het domein dat u eerder hebt gemaakt en toegevoegd aan uw abonnement in fase 1, en selecteer vervolgens **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae471-249">On the **Azure AD Domain** page, in **Domain**, select the name of the domain that you previously created and added to your subscription in Phase 1, and then select **Next**.</span></span>
    
11. <span data-ttu-id="ae471-250">Selecteer **configureren**op de pagina **klaar voor de configuratie** .</span><span class="sxs-lookup"><span data-stu-id="ae471-250">On the **Ready to configure** page, select **Configure**.</span></span>
    
12. <span data-ttu-id="ae471-251">Selecteer **verifiëren**op de pagina **installatie voltooien** .</span><span class="sxs-lookup"><span data-stu-id="ae471-251">On the **Installation complete** page, select **Verify**.</span></span>
    
    <span data-ttu-id="ae471-252">U ziet een bericht waarin wordt aangegeven dat het intranet en de Internet configuratie zijn geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="ae471-252">You should see messages indicating that both the intranet and internet configuration was verified.</span></span>
    
13. <span data-ttu-id="ae471-253">Selecteer op de pagina **installatie voltooien** de optie **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="ae471-253">On the **Installation complete** page, select **Exit**.</span></span>
    
<span data-ttu-id="ae471-254">Om aan te tonen dat federatieve verificatie werkt:</span><span class="sxs-lookup"><span data-stu-id="ae471-254">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="ae471-255">Open een nieuwe privétab van uw browser op uw lokale computer en ga naar [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="ae471-255">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="ae471-256">Voer voor de aanmeldingsreferenties **user1@** in \<*the domain created in Phase 1*> .</span><span class="sxs-lookup"><span data-stu-id="ae471-256">For the sign-in credentials, enter **user1@**\<*the domain created in Phase 1*>.</span></span>
    
    <span data-ttu-id="ae471-257">Als uw test domein bijvoorbeeld **testlab.contoso.com**is, typt u ' user1@testlab.contoso.com '.</span><span class="sxs-lookup"><span data-stu-id="ae471-257">For example, if your test domain is **testlab.contoso.com**, you would enter "user1@testlab.contoso.com".</span></span> <span data-ttu-id="ae471-258">Druk op de **Tab** -toets of laat microsoft 365 u automatisch omleiden.</span><span class="sxs-lookup"><span data-stu-id="ae471-258">Press the **Tab** key or allow Microsoft 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="ae471-259">U zou nu een pagina moeten zien met **Uw verbinding is niet privé**.</span><span class="sxs-lookup"><span data-stu-id="ae471-259">You should now see a **Your connection is not private** page.</span></span> <span data-ttu-id="ae471-260">U ziet het volgende omdat u een zelfondertekend certificaat op ADFS1 hebt geïnstalleerd dat op uw desktopcomputer niet kan worden gevalideerd.</span><span class="sxs-lookup"><span data-stu-id="ae471-260">You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer can't validate.</span></span> <span data-ttu-id="ae471-261">Bij een productie-implementatie van federatieve verificatie gebruikt u een certificaat van een vertrouwde certificeringsinstantie en zien uw gebruikers deze pagina niet.</span><span class="sxs-lookup"><span data-stu-id="ae471-261">In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="ae471-262">Selecteer op de pagina **uw verbinding is niet persoonlijk** de optie **Geavanceerd**en \*\* \<*your federation service FQDN*> Selecteer vervolgens doorgaan \*\*.</span><span class="sxs-lookup"><span data-stu-id="ae471-262">On the **Your connection is not private** page, select **Advanced**, and then select **Proceed to \<*your federation service FQDN*>**.</span></span> 
    
4. <span data-ttu-id="ae471-263">Ga op de pagina met de naam van uw fictieve organisatie als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="ae471-263">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="ae471-264">**CORP\\gebruiker1** voor de naam</span><span class="sxs-lookup"><span data-stu-id="ae471-264">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="ae471-265">Het wachtwoord voor het gebruiker1-account</span><span class="sxs-lookup"><span data-stu-id="ae471-265">The password for the User1 account</span></span>
    
    <span data-ttu-id="ae471-266">U zou de pagina van **Microsoft Office voor Thuisgebruik** moeten zien.</span><span class="sxs-lookup"><span data-stu-id="ae471-266">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="ae471-267">Deze procedure laat zien dat uw proefabonnement is verbonden met het AD DS corp.contoso.com-domein dat wordt gehost op DC1.</span><span class="sxs-lookup"><span data-stu-id="ae471-267">This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1.</span></span> <span data-ttu-id="ae471-268">Hier volgen de basisbeginselen van het verificatieproces:</span><span class="sxs-lookup"><span data-stu-id="ae471-268">Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="ae471-269">Wanneer u het federatieve domein gebruikt dat u in fase 1 hebt gemaakt binnen de aanmeldingsaccountnaam, leidt Microsoft 365 uw browser om naar uw federatiediensten FQDN en PROXY1.</span><span class="sxs-lookup"><span data-stu-id="ae471-269">When you use the federated domain that you created in Phase 1 within the sign-in account name, Microsoft 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="ae471-270">PROXY1 stuurt uw lokale computer naar de aanmeldingspagina voor fictief bedrijf.</span><span class="sxs-lookup"><span data-stu-id="ae471-270">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="ae471-271">Wanneer u CORP\\gebruiker1 en het wachtwoord voor PROXY1 verzendt, worden ze doorgestuurd naar ADFS1.</span><span class="sxs-lookup"><span data-stu-id="ae471-271">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="ae471-272">ADFS1 valideert CORP\\gebruiker1 en het wachtwoord met DC1 en stuurt uw lokale computer een beveiligingstoken.</span><span class="sxs-lookup"><span data-stu-id="ae471-272">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="ae471-273">Uw lokale computer verzendt het beveiligingstoken naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae471-273">Your local computer sends the security token to Microsoft 365.</span></span>
    
6. <span data-ttu-id="ae471-274">Microsoft 365 valideert dat het beveiligingstoken is gemaakt door ADFS1 en biedt toegang.</span><span class="sxs-lookup"><span data-stu-id="ae471-274">Microsoft 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="ae471-275">Uw proefabonnement is nu geconfigureerd met federatieve verificatie.</span><span class="sxs-lookup"><span data-stu-id="ae471-275">Your trial subscription is now configured with federated authentication.</span></span> <span data-ttu-id="ae471-276">U kunt deze ontwikkel- en testomgeving gebruiken voor geavanceerde verificatiescenario's.</span><span class="sxs-lookup"><span data-stu-id="ae471-276">You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="ae471-277">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="ae471-277">Next step</span></span>

<span data-ttu-id="ae471-278">Zie [federatieve authenticatie van hoge beschikbaarheid voor Microsoft 365 in azure implementeren](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)wanneer u klaar bent om te beginnen met de implementatie, federatieve verificatie van hoge beschikbaarheid voor microsoft 365 in Azure.</span><span class="sxs-lookup"><span data-stu-id="ae471-278">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 in Azure, see [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span></span>
  
