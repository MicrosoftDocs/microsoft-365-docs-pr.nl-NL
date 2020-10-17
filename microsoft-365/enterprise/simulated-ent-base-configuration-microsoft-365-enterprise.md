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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Met deze test lab-gids maakt u een gesimuleerde Enterprise-test omgeving voor Microsoft 365 for Enterprise.
ms.openlocfilehash: e66ec8c48e309daeb15aad5fcc475edcb2b8bb35
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487657"
---
# <a name="the-simulated-enterprise-base-configuration"></a>De basisconfiguratie voor een gesimuleerde Enterprise

*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*

In dit artikel wordt uitgelegd hoe u een vereenvoudigde omgeving maakt voor Microsoft 365 for Enterprise, waaronder:

- Een proef- of betaald abonnement op Microsoft 365 E5.
- Een eenvoudiger organisatie intranet, dat verbonden is met internet, bestaande uit drie virtuele machines op een virtueel Azure-netwerk (DC1, APP1 en CLIENT1).
 
![De basisconfiguratie voor een gesimuleerde Enterprise](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

Het maken van een vereenvoudigde testomgeving bestaat uit twee fasen:
- [Fase 1: Creëer een gesimuleerd intranet](#phase-1-create-a-simulated-intranet)
- [Fase 2: Maak uw abonnement op Microsoft 365 E5](#phase-2-create-your-microsoft-365-e5-subscription)

U kunt de beschikbare omgeving gebruiken om de functies en functionaliteit van [Microsoft 365 te testen voor Enterprise](https://www.microsoft.com/microsoft-365/enterprise) met extra testlab- [handleidingen](m365-enterprise-test-lab-guides.md) of zelf een eigen omgeving.

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.

## <a name="phase-1-create-a-simulated-intranet"></a>Fase 1: Creëer een gesimuleerd intranet

In deze fase maakt u een gesimuleerd intranet in azure-infrastructuurservices die een Active Directory Domain Services (AD DS)-domeincontroller, een toepassingsserver en een clientcomputer omvat.

U gebruikt deze computers in extra [Microsoft 365 voor Enterprise test lab-handleidingen voor](m365-enterprise-test-lab-guides.md) het configureren en demonstreren van de Hybrid Identity en andere mogelijkheden.

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a>Methode 1: Maak uw gesimuleerde intranet met een Azure Resource Manager-sjabloon

Bij deze methode gebruikt u een Azure Resource Manager-sjabloon om de gesimuleerde intranet samen te stellen. Azure Resource Manager-sjablonen bevatten alle instructies voor het maken van de infrastructuur van Azure-netwerken, de virtuele machines en hun configuratie.

Lees voordat u de sjabloon implementeert, de [Leesmij-pagina voor sjablonen](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) en de volgende informatie:

- De openbare DNS-domeinnaam van uw testomgeving (testlab.\<*your public domain*>). U typt deze naam in het veld **domain name** van de pagina **Custom Deployment** .
- Een DNS-label voorvoegsel voor de Url's van de openbare IP-adressen van uw virtuele machines. U moet dit label invoeren in het veld **DNS-label voorvoegsel** van de pagina **Aangepaste implementatie**.

Nadat u de instructies hebt gelezen, selecteert u **implementeren naar Azure** op de [Leesmij-pagina](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) van het sjabloon om aan de slag te gaan.

>[!Note]
>Voor een gesimuleerd intranet dat is gemaakt met de Azure Resource Manager-sjabloon is een betaald Azure-abonnement vereist.

Wanneer de sjabloon is voltooid, ziet de configuratie er als volgt uit:

![Het gesimuleerde intranet in Azure-infrastructuurservices](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a>Methode 2: Maak uw gesimuleerde intranet met Azure PowerShell

Bij deze methode gebruikt u Windows PowerShell en de Azure PowerShell-module om de netwerkinfrastructuur, de virtuele machines en de configuratie ervan op te bouwen.

Gebruik deze methode als u ervaring wilt opdoen met het stap voor stap maken van elementen van de Azure-infrastructuur met PowerShell. Vervolgens kunt u de PowerShell-opdrachtblokken aanpassen voor uw eigen implementatie van andere virtuele machines in Azure.

#### <a name="step-1-create-dc1"></a>Stap 1: DC1 maken

In deze stap maakt u een virtueel Azure-netwerk en voegt u DC1, een virtuele machine met een domeincontroller voor een AD DS-domein toe.

Begin met het aanmaken van een Windows PowerShell-opdrachtprompt op uw lokale computer.
  
> [!NOTE]
> Met de volgende opdrachtsets wordt de meest recente versie van Azure PowerShell gebruikt. Zie [Aan de slag met Azure PowerShell-cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). 
  
Meld u aan bij uw Azure-account met behulp van de volgende opdracht.
  
```powershell
Connect-AzAccount
```

Haal de naam van uw abonnement op met de volgende opdracht.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Stel uw Azure-abonnement in. Vervang alles tussen de aanhalingstekens, inclusief de punthaken ("<" en ">"), met de juiste naam.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Maak vervolgens een nieuwe resourcegroep aan voor uw gesimuleerde Enterprise-testlab. Als u de naam van een unieke resourcegroep wilt bepalen, gebruikt u deze opdracht om uw bestaande resourcegroepen weer te geven.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Maak uw nieuwe resourcegroep aan met deze opdrachten. Vervang alles tussen de aanhalingstekens, inclusief de punthaken, en de juiste namen.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Vervolgens maakt u een TestLab virtueel netwerk dat het subnet van het bedrijfsnetwerk van de gesimuleerde bedrijfsomgeving host, en Beveilig dit met een netwerkbeveiligingsgroep. Vul de naam van uw resourcegroep in en voer deze opdrachten uit bij de opdrachtprompt van PowerShell op uw lokale computer.
  
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

Vervolgens maakt u de DC1-virtuele machine en configureert u deze als een domeincontroller voor het **testlab.**\<your public domain> AD DS-domein en een DNS-server voor de virtuele machines van het Testlab-virtuele netwerk. Als de naam van uw openbare domein bijvoorbeeld **<span>contoso</span>. com** is, is de DC1-virtuele machine een domeincontroller voor het **<span>testlab</span>. contoso.com**-domein.
  
Als u een virtuele machine van Azure wilt aanmaken voor DC1, vult u de naam van uw resourcegroep in en voert u deze opdrachten uit bij de opdrachtprompt van PowerShell op uw lokale computer.
  
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

U wordt gevraagd om een gebruikersnaam en wachtwoord voor het lokale Administrator-account op DC1 aan te maken. Gebruik een sterk wachtwoord en sla de naam en het wachtwoord op een veilige locatie op.
  
Maak vervolgens verbinding met de virtuele computer van DC1:
  
1. Selecteer in de [Azure](https://portal.azure.com)-Portal **resource groepen** > <***de naam van uw nieuwe resource groep***> > **DC1**  >  **verbinden**.
    
2. Selecteer in het deelvenster openen de optie **RDP-bestand downloaden**. Open het bestand DC1. RDP dat is gedownload en selecteer vervolgens **verbinding maken**.
    
3. Geef de naam van het lokale administrator-account van DC1 op:
    
   - Voor Windows 7:
    
     Selecteer in het dialoogvenster **Windows-beveiliging** de optie **een ander account gebruiken**. Voer in **gebruikersnaam** **DC1 \\ **van < *lokale beheerdersaccount* in>.
    
   - Voor Windows 8 of Windows 10:
    
     Selecteer in het dialoogvenster **Windows** -beveiliging **meer opties**en selecteer vervolgens **een ander account gebruiken**. Voer in **gebruikersnaam** **DC1 \\ **van < *lokale beheerdersaccount* in>.
    
4. Voer bij **wachtwoord**het wachtwoord van het lokale beheerdersaccount in en selecteer **OK**.
    
5. Selecteer **Ja**wanneer u daarom wordt gevraagd.
    
Voeg vervolgens een extra gegevensschijf toe als een nieuw volume met de stationsaanduiding F: met deze opdracht met een opdrachtprompt op het beheerdersniveau van Windows PowerShell op DC1.
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Configureer DC1 vervolgens als een domeincontroller en DNS-server voor het **testlab.**\<*your public domain*> -domein. Geef de naam op van uw openbare domein, verwijder de punthaken en voer deze opdrachten uit op een beheerdersniveau Windows PowerShell-opdrachtprompt op DC1.
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
U zult een beheerderswachtwoord moeten opgeven voor de veilige modus. Sla dit wachtwoord op een veilige locatie op.
  
Houd er rekening mee dat deze opdrachten een paar minuten in beslag nemen.
  
Nadat DC1 opnieuw is gestart, maakt u opnieuw verbinding met de DC1-virtuele machine.
  
1. Selecteer in de [Azure](https://portal.azure.com)-Portal **resource groepen** > <*de naam van de resource groep*> > **DC1**  >  **verbinden**.
    
2. Voer het bestand DC1. RDP uit en selecteer vervolgens **verbinding maken**.
    
3. Selecteer in **Windows**-beveiliging **een ander account gebruiken**. Voer in **gebruikersnaam**de naam van het **TESTLAB \\ **- < *account voor lokale beheerders*>.
    
4. Voer in het vak **wachtwoord** het wachtwoord van het lokale beheerdersaccount in en selecteer **OK**.
    
5. Selecteer **Ja**wanneer u daarom wordt gevraagd.
    
Vervolgens maakt u een gebruikersaccount in Active Directory die wordt gebruikt wanneer u zich aanmeldt bij TESTLAB-domein lidcomputers. Voer deze opdracht uit op een Windows PowerShell-opdrachtprompt op beheerdersniveau.
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

Met deze opdracht wordt u gevraagd het wachtwoord van het Gebruiker1-account te verstrekken. Deze account wordt gebruikt voor externe bureaubladverbindingen voor alle TESTLAB-domein lidcomputers, dus kies een sterk wachtwoord. Noteer het wachtwoord van het Gebruiker1-account en sla het op een beveiligde locatie op.
  
Configureer vervolgens het nieuwe Gebruiker1-account als een domein-, enterprise- en schemabeheerder. Voer deze opdracht uit op de Windows PowerShell-opdrachtprompt op beheerdersniveau.
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

Sluit de Extern bureaublad-sessie met DC1 en maak opnieuw verbinding via het \\Gebruiker1-account van TESTLAB.
  
Voer deze opdracht uit op een Windows PowerShell-opdrachtprompt op beheerdersniveau om verkeer voor het Ping-hulpprogramma toe te staan.
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

De huidige configuratie ziet er als volgt uit:
  
![Stap 1 voor de basisconfiguratie van de gesimuleerde enterprise](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a>Stap 2: APP1 configureren

Bij deze stap maakt en configureert u APP1, een toepassingsserver die in eerste instantie Services biedt voor het delen van bestanden.

Om een virtuele machine van Azure voor APP1 aan te maken, vult u de naam van uw resourcegroep in en voert u deze opdrachten uit bij de opdrachtprompt op uw lokale computer.
  
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

Vervolgens maakt u verbinding met de APP1-virtuele machine met de naam en het wachtwoord van het lokale APP1-administratoraccount en opent u een Windows PowerShell-opdrachtprompt.
  
Als u de naamresolutie en de netwerkcommunicatie tussen APP1 en DC1 wilt controleren, voert u de opdracht **ping dc1. testlab.**\<*your public domain name*> uit en controleert u of er vier antwoorden zijn.
  
Vervolgens voegt u de APP1-virtuele machine toe aan het TESTLAB-domein met deze opdrachten bij de Windows PowerShell-prompt.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Wanneer u de opdracht **add-computer** hebt uitgevoerd, moet u de domeinreferenties voor het TESTLAB- \\ account opgeven.
  
Nadat APP1 opnieuw is gestart, maakt u verbinding met het bestand met behulp van het \\Gebruiker1-account van TESTLAB en opent u vervolgens een Windows PowerShell-opdrachtprompt op beheerdersniveau.
  
Vervolgens maakt u APP1 een webserver door deze opdracht uit te voeren op een Windows PowerShell-opdrachtprompt op beheerdersniveau op APP1.
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

Maak vervolgens een gedeelde map aan en een tekstbestand in de map op APP1 met deze PowerShell-opdrachten.
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

De huidige configuratie ziet er als volgt uit:
  
![Stap 2 van de basisconfiguratie van de gesimuleerde enterprise](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a>Stap 3: CLIENT1 configureren

In deze stap maakt en configureert u CLIENT1, die fungeert als een normale laptop, tablet of desktopcomputer op het intranet.

> [!NOTE]  
> Met de volgende opdrachtsets maakt u CLIENT1 met Windows Server 2016 Datacenter, wat kan worden uitgevoerd voor alle typen Azure-abonnementen. Als u een Azure-abonnement hebt op basis van Visual Studio, kunt u CLIENT1 met Windows 10 maken met behulp van de [Azure-portal](https://portal.azure.com).
  
Als u een virtuele Azure-computer wilt maken voor CLIENT1, vult u de naam van de resourcegroep in en voert u deze opdrachten uit bij de opdrachtprompt op uw lokale computer.
  
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

Vervolgens maakt u verbinding met de CLIENT1-virtuele machine met de naam en het wachtwoord van het lokale CLIENT1-administratoraccount en opent u een Windows PowerShell-opdrachtprompt.
  
Als u de naamresolutie en de netwerkcommunicatie tussen CLIENT1 en DC1 wilt controleren, voert u de opdracht **ping dc1. testlab.**\<*your public domain name*> uit via de opdrachtprompt van Windows PowerShell en controleert u of er vier antwoorden zijn.
  
Vervolgens voegt u de CLIENT1-virtuele machine toe aan het TESTLAB-domein met deze opdrachten bij de Windows PowerShell-prompt.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Houd er rekening mee dat u de gegevens van het \\Gebruiker1-domeinaccount van TESTLAB op moet geven nadat u de opdracht **Add-computer** hebt uitgevoerd.
  
Nadat CLIENT1 opnieuw is gestart, maakt u verbinding met het bestand met behulp van het \\Gebruiker1-account van TESTLAB en opent u vervolgens een Windows PowerShell-opdrachtprompt op beheerdersniveau.
  
Controleer vervolgens of u toegang hebt tot web- en bestandssharebronnen op APP1 vanuit CLIENT1.
  
1. Selecteer in Server beheer in het deelvenster Structuur de optie **lokale server**.
    
2. **Selecteer bij** **Eigenschappen voor CLIENT1**de optie naast **verbeterde beveiligingsinstellingen van Internet Explorer**.
    
3. Bij **Verbeterde beveiliging van Internet Explorer**, selecteert u **uit** voor **beheerders** en **gebruikers**en selecteert u vervolgens **OK**.
    
4. Selecteer **Internet Explorer**in het Start scherm en selecteer vervolgens **OK**.
    
5. Voer in de adresbalk **http<span>://</span>app1. testab**in \<*your public domain name*> **/** en druk vervolgens op **Enter**. U ziet nu de standaardwebpagina voor Internet Information Services voor APP1.
    
6. Selecteer op de bureaublad taakbalk het pictogram Verkenner.
    
7. Voer in de adresbalk ** \\ \\ app1 \\ bestanden**in en druk vervolgens op **Enter**. Er wordt een mappenvenster met de inhoud van de map met gedeelde bestanden weergegeven.
    
8. Dubbelklik in het venster van de map met **Gedeelde bestanden** op het bestand **Voorbeeld.txt**. U ziet nu de inhoud van het bestand Voorbeeld.txt.
    
9. Sluit het **Voorbeeld.txt - Notepad** en de map met **Gedeelde bestanden**.
    
De huidige configuratie ziet er als volgt uit:
  
![Stap 3 van de basisconfiguratie van de gesimuleerde enterprise](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a>Fase 2: Maak uw abonnement op Microsoft 365 E5

In deze fase maakt u een nieuw Microsoft 365 E5-abonnement aan dat gebruikmaakt van een nieuwe Azure AD-tenant, die losstaat van uw productieabonnement. U kunt dit op twee manieren doen:

- Gebruik een proefabonnement op Microsoft 365 E5.

  Het proefabonnement op Microsoft 365 E5 duurt 30 dagen en kan gemakkelijk tot 60 dagen worden verlengd. Wanneer het proefabonnement is verlopen, moet u dit omzetten naar een betaald abonnement of een nieuw proefabonnement starten. Het starten van nieuwe proefabonnementen houdt in dat u uw configuratie achterlaat, inclusief eventuele ingewikkelde scenario's.  

- Gebruik een afzonderlijk productieabonnement op Microsoft 365 E5 met een beperkt aantal licenties.

  Dit is een extra kosten, maar zorgt ervoor dat u een testomgeving hebt die niet verloopt. Hierin kunt u functies, configuraties en scenario's proberen. U kunt dezelfde testomgeving op de lange termijn gebruiken voor de proefversies van concepten, demonstraties voor collega's en het beheer, en voor het ontwikkelen en testen van toepassingen. Dit is de aanbevolen methode.

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Registreer u voor een proefabonnement op Office 365 E5

Maak via de Azure-Portal verbinding met CLIENT1 met het CORP\User1-account.

Als u een nieuw Office 365 E5-proefabonnement wilt maken, volgt u de instructies uit [Fase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) van de Testlabrichtlijnen voor eenvoudige basisconfiguratie.

Als u uw nieuwe Office 365 E5-proefabonnement wilt maken, volgt u de instructies uit [Fase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) van de Testlabrichtlijnen voor eenvoudige basisconfiguratie.

#### <a name="using-an-office-365-e5-test-environment"></a>Een Office 365 E5-testomgeving gebruiken

Als u alleen een Office 365-testomgeving nodig hebt, hoeft u de rest van dit artikel niet te lezen.

Zie [Microsoft 365 voor Enterprise test lab-handleidingen](m365-enterprise-test-lab-guides.md)voor extra test lab-gidsen die van toepassing zijn op microsoft 365 en Office 365.

### <a name="add-a-microsoft-365-e5-trial-subscription"></a>Een Microsoft 365 E5-proefabonnement toevoegen.

Als u een Microsoft 365 E5-proefabonnement wilt toevoegen en uw gebruikersaccounts met een licentie wilt configureren, voert u de instructies uit in [fase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) van de Lightweight Base configuration test lab-gids.

  
## <a name="results"></a>Resultaten

Uw testomgeving heeft nu:
  
- Microsoft 365 E5-proefabonnement.
- Al uw geschikte gebruikersaccounts kunnen Microsoft 365 E5 gebruiken.
- Een gesimuleerd en vereenvoudigd intranet.
    
De laatste configuratie ziet er als volgt uit:
  
![Fase 2 van de basisconfiguratie van de gesimuleerde enterprise](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
U bent nu klaar om te experimenteren met de extra functies van [Microsoft 365 for Enterprise](https://www.microsoft.com/microsoft-365/enterprise).
  
## <a name="next-steps"></a>Volgende stappen

Verken de volgende extra sets testlabrichtlijnen:
  
- [Identiteit](m365-enterprise-test-lab-guides.md#identity)
- [Mobile Device Management](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Gegevensbeveiliging](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
