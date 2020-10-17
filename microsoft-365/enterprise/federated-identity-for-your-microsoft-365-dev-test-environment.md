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
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a>Federatieve identiteit voor uw Microsoft 365-testomgeving

*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*

Microsoft 365 ondersteunt federatieve identiteit. Dit betekent dat in plaats van de validatie van referenties zelf uit te voeren, Microsoft 365 de verbindende gebruiker verwijst naar een federatieve verificatieserver die Microsoft 365 vertrouwt. Als de inloggegevens van de gebruiker correct zijn, geeft de federatieve verificatieserver een beveiligingstoken uit dat de client vervolgens naar Microsoft 365 stuurt als bewijs van verificatie. Federatieve identiteit zorgt voor de offloading en schaalbaarheid van verificatie voor een Microsoft 365-abonnement en geavanceerde verificatie- en beveiligingsscenario's.
  
In dit artikel wordt uitgelegd hoe u federatieve verificatie voor uw Microsoft 365-testomgeving configureert, wat resulteert in het volgende:

![De federatieve verificatie voor Microsoft 365-testomgeving](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
Deze configuratie bestaat uit:
  
- Een Microsoft 365 E5-proefabonnement of productie abonnement.
    
- Een eenvoudiger organisatie intranet verbonden met internet, bestaande uit vijf virtuele machines op een subnet van een Azure virtueel netwerk (DC1, APP1, CLIENT1, ADFS1 en PROXY1). Azure AD Connect wordt uitgevoerd op APP1 om de lijst met accounts in het Active Directory Domain Services-domein te synchroniseren met Microsoft 365. PROXY1 ontvangt de binnenkomende verificatieaanvragen. ADFS1 valideert referenties met DC1 en beveiligingstokens.
    
Het instellen van deze testomgeving omvat vijf fasen:
- [Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: maak de AD FS-server](#phase-2-create-the-ad-fs-server)
- [Fase 3: de webproxyserver maken](#phase-3-create-the-web-proxy-server)
- [Fase 4: maak een zelfondertekend certificaat en configureer ADFS1 en PROXY1.](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [Fase 5: Office 365 configureren voor federatieve identiteit](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> U kunt deze testomgeving niet configureren met een Azure-proefabonnement.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving

Volg de instructies in [wachtwoord-hash-synchronisatie voor Microsoft 365](password-hash-sync-m365-ent-test-environment.md). De uiteindelijke configuratie ziet er als volgt uit:
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
Deze configuratie bestaat uit:
  
- Een Microsoft 365 E5-proefabonnement of betaalde abonnementen.
- Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines op een subnet van een Azure virtueel netwerk. Azure AD Connect wordt uitgevoerd op APP1 om het TESTLAB Active Directory Domain Services (AD DS)-domein te synchroniseren met de Azure AD-Tenant van uw Microsoft 365-abonnementen.

## <a name="phase-2-create-the-ad-fs-server"></a>Fase 2: maak de AD FS-server

Een AD FS-server biedt federatieve verificatie tussen Microsoft 365 en de accounts in het corp.contoso.com-domein dat wordt gehost op DC1.
  
Als u een virtuele machine van Azure wilt maken voor ADFS1, vult u de naam van uw abonnement, de bronnengroep en de Azure-locatie voor uw basisconfiguratie in en voert u deze opdrachten uit op de opdrachtprompt van de Azure PowerShell op uw lokale computer.
  
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

Gebruik vervolgens de [Azure-portal](https://portal.azure.com) om verbinding te maken met de ADFS1 virtuele machine met behulp van de ADFS1-naam en het wachtwoord van de lokale beheerdersaccount, en open vervolgens een Windows PowerShell-opdrachtprompt.
  
Als u de naamresolutie en de netwerkcommunicatie tussen ADFS1 en DC1 wilt controleren, voert u de opdracht **ping dc1.corp.contoso.com** uit en controleert u of er vier antwoorden zijn.
  
Vervolgens voegt u de virtuele machine ADFS1 toe aan het CORP-domein met deze opdrachten bij de Windows PowerShell-prompt op ADFS1.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

De uiteindelijke configuratie ziet er als volgt uit:
  
![De AD FS-server die is toegevoegd aan de testomgeving van DirSync voor Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a>Fase 3: de webproxyserver maken

PROXY1 biedt proxy van authenticatieberichten tussen gebruikers die proberen te authenticeren en ADFS1.
  
Als u een virtuele machine van Azure wilt maken voor PROXY1, vult u de naam van de resourcegroep en de Azure-locatie in en voert u deze opdrachten uit op de opdrachtprompt van de Azure PowerShell op uw lokale computer.
  
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
> PROXY1 krijgt een statisch openbaar IP-adres toegewezen, omdat u een openbaar DNS-record maakt dat ernaar verwijst en het niet mag veranderen wanneer u de virtuele machine PROXY1 opnieuw opstart.
  
Voeg vervolgens een regel toe aan de groep netwerkbeveiliging voor het CorpNet-subnet, zodat ongevraagde inkomende verkeer van Internet naar PROXY1's Private IP Address en TCP-poort 443 wordt toegestaan. Voer deze opdrachten uit vanaf de opdrachtprompt van Azure PowerShell op uw lokale computer.
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

Gebruik vervolgens de [Azure-portal](https://portal.azure.com) om verbinding te maken met de virtuele machine PROXY1 met behulp van de PROXY1-naam en het wachtwoord van de lokale beheerdersaccount, en open vervolgens een Windows PowerShell-opdrachtprompt op PROXY1.
  
Als u de naamresolutie en de netwerkcommunicatie tussen PROXY1 en DC1 wilt controleren, voert u de opdracht **ping dc1.corp.contoso.com** uit en controleert u of er vier antwoorden zijn.
  
Vervolgens voegt u de virtuele machine PROXY1 toe aan het CORP-domein met deze opdrachten bij de Windows PowerShell-prompt op PROXY1.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

Geef het openbare IP-adres van PROXY1 weer met de volgende Azure PowerShell-opdrachten op uw lokale computer.
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

Werk vervolgens met uw openbare DNS-provider om een nieuw openbaar DNS A-record aan te maken voor **fs.testlab.**\<*your DNS domain name*> dat wordt omgezet naar het IP-adres dat wordt weergegeven door de **Write-Host**. De **fs.testlab.**\<*your DNS domain name*> wordt hierna de *federatiedienst FQDN* genoemd.
  
Gebruik vervolgens de [Azure-portal](https://portal.azure.com) om verbinding te maken met de virtuele machine DC1 met behulp van de CORP\\gebruiker1-referenties en voer vervolgens de volgende opdrachten uit op een Windows PowerShell-opdrachtprompt op beheerdersniveau:
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
Met deze opdrachten maakt u een interne DNS A-record, zodat virtuele machines in het virtuele netwerk van Azure de FQDN-naam van het interne Federation service-ADFS1's kunnen omzetten in een particulier IP-adres van.
  
De uiteindelijke configuratie ziet er als volgt uit:
  
![De proxyserver van de webtoepassing is toegevoegd aan de testomgeving van DirSync voor Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a>Fase 4: maak een zelfondertekend certificaat en configureer ADFS1 en PROXY1.

In deze fase maakt u een zelfondertekend digitaal certificaat voor de FQDN van de federatieservice en configureert u ADFS1 en PROXY1 als een AD FS-farm.
  
Gebruik eerst de [Azure-portal](https://portal.azure.com) om verbinding te maken met de virtuele DC1-machine met de referenties voor CORP\\gebruiker1 en open vervolgens een opdrachtprompt op beheerdersniveau in Windows PowerShell.
  
Maak vervolgens een AD FS-serviceaccount met deze opdracht op de Windows PowerShell-opdrachtprompt op DC1:
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
Met deze opdracht wordt u gevraagd het wachtwoord van het account op te geven. Kies een sterk wachtwoord en sla dit op in een beveiligde locatie. Dit hebt u nodig voor deze fase en voor fase 5.
  
Gebruik de [Azure-Portal](https://portal.azure.com) om verbinding te maken met de virtuele ADFS1-computer met de accountreferenties voor CORP\\gebruiker1. Open een Windows PowerShell-opdrachtprompt op beheerdersniveau op ADFS1, vul de FQDN van de federatiedienst in en voer vervolgens deze opdrachten uit om een zelfondertekend certificaat te maken:
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

Gebruik vervolgens deze stappen om het nieuwe, zelfondertekend certificaat als een bestand op te slaan.
  
1. Selecteer **Start**, typ **mmc.exe**en druk op **Enter**.
    
2. Selecteer **File**invoeg  >  **toepassing voor bestands toevoegen/verwijderen**.
    
3. Dubbel **Klik in de**lijst met beschikbare invoegtoepassingen in de lijst met beschikbare modules op **certificaten** en **Selecteer vervolgens** **volgende**.
    
4. Selecteer in **computer selecteren**de optie **Voltooien**en selecteer vervolgens **OK**.
    
5. Open in het structuurvenster **certificaten (lokale computer) > persoonlijk > certificaten**.
    
6. Selecteer het certificaat met behulp van de Federatie service-FQDN en houd deze ingedrukt (of klik erop met de rechtermuisknop), selecteer **alle taken**en selecteer vervolgens **exporteren**.
    
7. Selecteer **volgende**op de **welkomst** pagina.
    
8. Selecteer op de pagina **persoonlijke sleutel exporteren** de optie **Ja**en selecteer **volgende**.
    
9. Selecteer op de pagina **bestandsindeling exporteren** de optie **alle uitgebreide eigenschappen exporteren**en selecteer **volgende**.
    
10. Selecteer **wachtwoord** op de pagina **beveiliging** en voer een wachtwoord in **wachtwoord** in en **Bevestig uw wachtwoord.**
    
11. Selecteer op de pagina **bestand to export** de optie **Browse**.
    
12. Blader naar de **map C \\ : certs** , Voer **SSL** in de **bestandsnaam**in en selecteer **opslaan.**
    
13. Selecteer op de pagina **te exporteren bestand** de optie **volgende**.
    
14. Selecteer op de pagina **de wizard Certificaat exporteren** volt **ooien**. Selecteer **OK**wanneer u daarom wordt gevraagd.
    
Installeer vervolgens de AD FS-service met deze opdracht met de Windows PowerShell-opdrachtprompt op ADFS1:
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

Wacht totdat de installatie is voltooid.
  
Configureer vervolgens de AD FS-service met de volgende stappen:
  
1. Selecteer **Start**en selecteer vervolgens het pictogram **Server beheer** .
    
2. Selecteer in het deelvenster structuur van server beheer de optie **AD FS**.
    
3. Selecteer op de werkbalk aan de bovenkant het oranje waarschuwingssymbool en selecteer vervolgens **de Federatie service configureren op deze server**.
    
4. Selecteer op de **welkomst** pagina van de wizard Active Directory Federation Services configureren de optie **volgende**.
    
5. Selecteer op de pagina **verbinding maken met AD DS** de optie **volgende**.
    
6. Op de pagina **service-eigenschappen opgeven** pagina:
    
  - Selecteer voor **SSL-certificaat**de pijl-omlaag en selecteer vervolgens het certificaat met de naam van de FQDN voor de Federation service.
    
  - Voer in de **weergavenaam van de Federation service**de naam van uw fictieve organisatie in.
    
  - Selecteer **Volgende**.
    
7. Selecteer op de pagina **Service account opgeven** de optie **selecteren** voor **account naam**.
    
8. Typ **ADFS-service**in **Select User of service account**, selecteer **Namen controleren**en selecteer vervolgens **OK**.
    
9. Voer het wachtwoord in van het **account**dat u hebt opgegeven voor het ADFS-Service account en selecteer **volgende**.
    
10. Selecteer op de pagina **configuratie database opgeven** de optie **volgende**.
    
11. Selecteer op de pagina **opties controleren** de optie **volgende**.
    
12. Selecteer op de pagina **controle vereisten** de optie **configureren**.

13. Selecteer op de pagina **resultaten** de optie **sluiten**.
    
14. Selecteer **Start**, selecteer het pictogram van de stekker, selecteer **opnieuw opstarten**en selecteer vervolgens **Doorgaan**.
    
Maak vanuit de [Azure-portal](https://portal.azure.com) verbinding met PROXY1 met de CORP\\gebruiker1-accountreferenties.
  
Voer vervolgens deze stappen uit om het zelfondertekende certificaat te installeren op **zowel PROXY1 als APP1**.
  
1. Selecteer **Start**, typ **mmc.exe**en druk op **Enter**.
    
2. Selecteer **bestand > module toevoegen/verwijderen**.
    
3. Dubbel **Klik in de**lijst met beschikbare invoegtoepassingen in de lijst met beschikbare modules op **certificaten** en **Selecteer vervolgens** **volgende**.
    
4. Selecteer in **computer selecteren**de optie **Voltooien**en selecteer vervolgens **OK**.
    
5. Open **certificates (local computer)**  >  **Personal**  >  **certificates**in het deelvenster structuur.
    
6. Selecteer of klik met de rechtermuisknop op **persoonlijk**, selecteer **alle taken**en selecteer vervolgens **importeren**.
    
7. Selecteer **volgende**op de **welkomst** pagina.
    
8. Voer op de pagina **te importeren bestand** de ** \\ \\ adfs1- \\ certificerings versie van \\ SSL. pfx**in en selecteer **volgende**.
    
9. Voer op de pagina **Persoonlijke sleutelbeveiliging** het certificaatwachtwoord in het **wachtwoord**in en selecteer **Volgende.**
    
10. Selecteer op de pagina **certificaatarchief** de optie **Volgende.**
    
11. Selecteer op de pagina **volt** ooien de optie **Voltooien**.
    
12. Selecteer op de pagina **certificaatarchief** de optie **volgende**.
    
13. Selecteer **OK**wanneer u daarom wordt gevraagd.
    
14. Selecteer in het deelvenster Structuur de optie **certificaten**.
    
15. Selecteer het certificaat en houd deze ingedrukt (of klik er met de rechtermuisknop op) en selecteer **kopiëren**.
    
16. Open in het deelvenster Structuur de certificaten van **vertrouwde basiscertificeringsinstanties**  >  **Certificates**.
    
17. Beweeg de muisaanwijzer onder de lijst met geïnstalleerde certificaten, selecteer en houd de muisknop ingedrukt (of klik er met de rechtermuisknop op) en selecteer vervolgens **Plakken**.
    
Open een PowerShell-opdrachtprompt op beheerdersniveau en voer de volgende opdracht uit:
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

Wacht totdat de installatie is voltooid.
  
Gebruik de volgende stappen om de service webtoepassingsproxy zo te configureren dat ADFS1 als federatieserver wordt gebruikt:
  
1. Selecteer **Start**en selecteer **Server beheer**.
    
2. Selecteer in het deelvenster Structuur de optie **externe toegang**.
    
3. Selecteer op de werkbalk aan de bovenkant het oranje waarschuwingssymbool en selecteer vervolgens **de wizard van de**Webtoepassingsproxy-toepassing.
    
4. Selecteer op de **welkomst** pagina van de wizard Configuratie van webtoepassingsproxy de optie **volgende**.
    
5. Op de pagina **federatieserver**:
    
  - Voer in het vak **naam van Federation service** de Federation service-FQDN in.
    
  - Voer in het vak **gebruikersnaam** **Corp \\ gebruiker1**in.
    
  - Voer in het vak **wachtwoord** het wachtwoord in voor het account gebruiker1.
    
  - Selecteer **Volgende**.
    
6. Selecteer op de pagina **AD FS-proxy certificaat** de pijl-omlaag, selecteer het certificaat met de FQDN-service-FQDN en selecteer **volgende**.
    
7. Selecteer op de pagina **confirmation** de optie **Configure**.
    
8. Selecteer op de pagina **resultaten** de optie **sluiten**.
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a>Fase 5: Office 365 configureren voor federatieve identiteit

Gebruik de [Azure-Portal](https://portal.azure.com) om verbinding te maken met de virtuele APP1-computer met de accountreferenties voor CORP\\gebruiker1.
  
Volg deze stappen voor het configureren van Azure AD Connect en uw Microsoft 365-abonnement voor federatieve verificatie:
  
1. Dubbelklik op het bureaublad op **Azure AD Connect**.
    
2. Selecteer op de pagina **Welkom bij Azure AD Connect** de optie **configureren**.
    
3. Selecteer op de pagina **extra taken** de optie **gebruikersaanmelding wijzigen**en selecteer **volgende**.
    
4. Voer op de pagina **verbinding maken met Azure AD** de naam en het wachtwoord van uw globale beheerder account in en selecteer **volgende**.
    
5. Selecteer **Federatie met AD FS**op de aanmeldingspagina van de **gebruiker** en selecteer **volgende**.
    
6. Selecteer op de pagina **AD FS-Farm** de optie **een bestaande AD FS-farm gebruiken**, typ **ADFS1** in het vak **Server naam** en selecteer **volgende**.
    
7. Wanneer u wordt gevraagd om Server referenties, voert u de referenties van het account van de \\ gebruiker1-account in en selecteert u **OK**.
    
8. Voer op de pagina referenties van **domeinbeheerder** **Corp \\ gebruiker1** in het **vak Gebruikersnaam** in, voer het accountwachtwoord in het vak **wachtwoord** in en selecteer **volgende**.
    
9. Voer op de pagina **AD FS-serviceaccount** de naam **Corp \\ -service** in in het vak **domeinnaam** van het account, voer het accountwachtwoord in het vak **wachtwoord voor domeingebruikers** in en selecteer **volgende**.
    
10. Selecteer op de pagina **Azure AD domain** in **Domain**de naam van het domein dat u eerder hebt gemaakt en toegevoegd aan uw abonnement in fase 1, en selecteer vervolgens **volgende**.
    
11. Selecteer **configureren**op de pagina **klaar voor de configuratie** .
    
12. Selecteer **verifiëren**op de pagina **installatie voltooien** .
    
    U ziet een bericht waarin wordt aangegeven dat het intranet en de Internet configuratie zijn geverifieerd.
    
13. Selecteer op de pagina **installatie voltooien** de optie **Afsluiten**.
    
Om aan te tonen dat federatieve verificatie werkt:
  
1. Open een nieuwe privétab van uw browser op uw lokale computer en ga naar [https://admin.microsoft.com](https://admin.microsoft.com).
    
2. Voer voor de aanmeldingsreferenties **user1@** in \<*the domain created in Phase 1*> .
    
    Als uw test domein bijvoorbeeld **testlab.contoso.com**is, typt u ' user1@testlab.contoso.com '. Druk op de **Tab** -toets of laat microsoft 365 u automatisch omleiden.
    
    U zou nu een pagina moeten zien met **Uw verbinding is niet privé**. U ziet het volgende omdat u een zelfondertekend certificaat op ADFS1 hebt geïnstalleerd dat op uw desktopcomputer niet kan worden gevalideerd. Bij een productie-implementatie van federatieve verificatie gebruikt u een certificaat van een vertrouwde certificeringsinstantie en zien uw gebruikers deze pagina niet.
    
3. Selecteer op de pagina **uw verbinding is niet persoonlijk** de optie **Geavanceerd**en ** \<*your federation service FQDN*> Selecteer vervolgens doorgaan **. 
    
4. Ga op de pagina met de naam van uw fictieve organisatie als volgt te werk:
    
  - **CORP\\gebruiker1** voor de naam
    
  - Het wachtwoord voor het gebruiker1-account
    
    U zou de pagina van **Microsoft Office voor Thuisgebruik** moeten zien.
    
Deze procedure laat zien dat uw proefabonnement is verbonden met het AD DS corp.contoso.com-domein dat wordt gehost op DC1. Hier volgen de basisbeginselen van het verificatieproces:
  
1. Wanneer u het federatieve domein gebruikt dat u in fase 1 hebt gemaakt binnen de aanmeldingsaccountnaam, leidt Microsoft 365 uw browser om naar uw federatiediensten FQDN en PROXY1.
    
2. PROXY1 stuurt uw lokale computer naar de aanmeldingspagina voor fictief bedrijf.
    
3. Wanneer u CORP\\gebruiker1 en het wachtwoord voor PROXY1 verzendt, worden ze doorgestuurd naar ADFS1.
    
4. ADFS1 valideert CORP\\gebruiker1 en het wachtwoord met DC1 en stuurt uw lokale computer een beveiligingstoken.
    
5. Uw lokale computer verzendt het beveiligingstoken naar Microsoft 365.
    
6. Microsoft 365 valideert dat het beveiligingstoken is gemaakt door ADFS1 en biedt toegang.
    
Uw proefabonnement is nu geconfigureerd met federatieve verificatie. U kunt deze ontwikkel- en testomgeving gebruiken voor geavanceerde verificatiescenario's.
  
## <a name="next-step"></a>Volgende stap

Zie [federatieve authenticatie van hoge beschikbaarheid voor Microsoft 365 in azure implementeren](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)wanneer u klaar bent om te beginnen met de implementatie, federatieve verificatie van hoge beschikbaarheid voor microsoft 365 in Azure.
  
