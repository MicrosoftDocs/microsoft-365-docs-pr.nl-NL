---
title: Lichtgewicht basisconfiguratie
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
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Gebruik deze Test Lab Guide om een lichtgewicht testomgeving te maken voor het testen Microsoft 365 voor bedrijven.
ms.openlocfilehash: 2de0760cef7339f62229575b1e0a54b3c67a4e9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909704"
---
# <a name="the-lightweight-base-configuration"></a>De lichtgewicht basisconfiguratie

*Deze testlaborator kan worden gebruikt voor zowel Microsoft 365 voor bedrijven als Office 365 Enterprise testomgevingen.*

In dit artikel wordt beschreven hoe u een vereenvoudigde omgeving kunt maken met een Microsoft 365 E5 en een computer met Windows 10 Enterprise.

![De lichtgewicht Microsoft 365 Enterprise-testomgeving](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Het maken van een lichtgewicht testomgeving bestaat uit vijf fasen:
- [Fase 1: Uw abonnement Microsoft 365 E5 maken](#phase-1-create-your-microsoft-365-e5-subscription)
- [Fase 2: uw proefabonnement voor Office 365 configureren](#phase-2-configure-your-office-365-trial-subscription)
- [Fase 3: een Microsoft 365 E5-proefabonnement toevoegen](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [Fase 4: een Windows 10 Enterprise-computer maken](#phase-4-create-a-windows-10-enterprise-computer)
- [Fase 5: uw Windows 10-computer verbinden met Azure Active Directory](#phase-5-join-your-windows-10-computer-to-azure-ad)

Gebruik de resulterende omgeving om de functies en functionaliteit van Microsoft 365 [voor bedrijven te testen.](https://www.microsoft.com/microsoft-365/enterprise)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, zie Microsoft 365 [voor enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

>[!NOTE]
>Mogelijk wilt u dit artikel afdrukken voor het vastleggen van de specifieke informatie die u nodig hebt voor deze omgeving gedurende de 30 dagen van het proefabonnement voor Office 365. U kunt het proefabonnement eenvoudig verlengen met nog eens 30 dagen. Voor een permanente testomgeving kunt u een nieuw betaald abonnement maken met een afzonderlijke Azure Active Directory-tenant en een klein aantal licenties.

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>Fase 1: Uw abonnement Microsoft 365 E5 maken

We beginnen met een Microsoft 365 E5 proefabonnement en voegen vervolgens het Microsoft 365 E5 abonnement toe.

>[!NOTE]
>U wordt aangeraden een proefabonnement op Office 365 te maken, zodat uw testomgeving een aparte Azure AD-tenant heeft dan alle betaalde abonnementen die u momenteel hebt. Deze scheiding betekent dat u gebruikers en groepen in de testten tenant kunt toevoegen en verwijderen zonder dat dit gevolgen heeft voor uw productieabonnementen.

Als u uw proefabonnement Microsoft 365 E5, hebt u eerst een fictieve bedrijfsnaam en een nieuw Microsoft-account nodig.
  
1. Het is raadzaam dat u een variant op de bedrijfsnaam Contoso gebruikt voor uw bedrijfsnaam. Dit is een fictief bedrijf dat wordt gebruikt in de voorbeeldinhoud van Microsoft, maar dit is niet vereist. Noteer hier uw fictieve bedrijfsnaam: ![Lijn](../media/Common-Images/TableLine.png)
    
2. Als u zich wilt registreren voor een nieuw Microsoft-account, gaat u naar [https://outlook.com](https://outlook.com) en maakt u een account aan met een nieuw e-mailaccount en adres. U gebruikt dit account om u aan te melden bij Office 365.
    
    - Noteer hier de voor- en achternaam van uw nieuwe account: ![Lijn](../media/Common-Images/TableLine.png)
    
    - Noteer hier het adres van het nieuwe e-mailaccount: ![Lijn](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Registreer u voor een proefabonnement op Office 365 E5

1. Ga in uw browser naar [https://aka.ms/e5trial](https://aka.ms/e5trial) .
    
2. Voer in stap 1 van de pagina Bedankt voor het kiezen **van Office 365 E5** uw nieuwe e-mailadres in.
3. Voer in stap 2 van het trailabonnement de gevraagde gegevens in en voer de verificatie uit.
4. Voer in stap 3 een organisatienaam in en vervolgens een accountnaam die de globale beheerder van het abonnement wordt.
5. In stap 4, leg hier de aanmeldingspagina vast (selecteren en kopiëren): ![Lijn](../media/Common-Images/TableLine.png)
6. Noteer hier de gebruikers-ID: ![Lijn](../media/Common-Images/TableLine.png). onmicrosoft.com  
   Neem het wachtwoord op dat u hebt ingevoerd op een veilige locatie.
   Deze waarde wordt beschouwd als de **naam van de globale beheerder**.
7. Selecteer **Ga naar Setup.**
8. Selecteer Office 365 E5 Setup de optie Doorgaan met uw organisatie **.onmicrosoft.com** voor e-mail en aanmelden en selecteer vervolgens Afsluiten en **ga later verder.**

Nu ziet u het Microsoft 365-beheercentrum.
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>Fase 2: uw proefabonnement voor Office 365 configureren

In deze fase configureert u uw abonnement met aanvullende gebruikers en wijst u Office 365 E5-licenties aan ze toe.
  
Als u verbinding wilt maken met uw abonnement met Azure Active Directory PowerShell voor Graph-module vanaf uw computer, gebruikt u de instructies in Verbinding maken om Microsoft 365 [PowerShell.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
    
Voer in **Windows PowerShell dialoogvenster Aanvraag** voor referenties de algemene beheerdersnaam (bijvoorbeeld jdoe@contosotoycompany.onmicrosoft.com) en wachtwoord in. 
  
Vul de naam van uw organisatie in (bijvoorbeeld *contosotoycompany),* de landcode met twee tekens voor uw locatie, een gemeenschappelijk accountwachtwoord en voer de volgende opdrachten uit vanuit de PowerShell-prompt:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> U gebruikt hier een algemeen wachtwoord voor automatisering en configuratiegemak in een testomgeving. Uiteraard wordt dit sterk afgeraden voor productieabonnementen. 

### <a name="record-key-information-for-future-reference"></a>Noteer belangrijke informatie voor toekomstig gebruik

Als u deze waarden nog niet hebt opgenomen, kunt u deze nu opnemen:
  
- Naam globale beheerder: ![Lijn](../media/Common-Images/TableLine.png).onmicrosoft.com (uit stap 6 van fase 1)
    
    Noteer ook het wachtwoord voor dit account op een veilige locatie.
    
- De naam van de organisatie voor uw proefabonnement: ![Lijn](../media/Common-Images/TableLine.png) (uit stap 4 van fase 1)
    
- Voer de volgende opdracht uit vanuit de Windows Azure Active Directory-module voor Windows PowerShell-prompt om de accounts weer te geven voor gebruiker 2, gebruiker 3, gebruiker 4 en gebruiker 5:
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    Noteer hier de accountnamen:
    
  - Naam van gebruiker 2-account: gebruiker2@![Lijn](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Naam van gebruiker 3-account: gebruiker3@![Lijn](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Naam van gebruiker 4-account: gebruiker4@![Lijn](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Naam van gebruiker 5-account: gebruiker5@![Lijn](../media/Common-Images/TableLine.png).onmicrosoft.com
    
    Noteer ook het algemene wachtwoord voor dit account op een veilige locatie.
   
### <a name="using-an-office-365-test-environment"></a>Een Office 365 E5-testomgeving gebruiken

Als u alleen een testomgeving Office 365, hoeft u de rest van dit artikel niet te lezen.

Zie voor aanvullende testlaboratoriumhulplijnen die van toepassing zijn op zowel Office 365 als Microsoft 365, [Microsoft 365 voor ondernemingstestlaboratoriumhulplijnen.](m365-enterprise-test-lab-guides.md)
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>Fase 3: een Microsoft 365 E5-proefabonnement toevoegen

In deze fase meld u zich aan voor het Microsoft 365 E5-proefabonnement en voegt het toe aan dezelfde organisatie als uw Office 365 E5-proefabonnement.
  
Voeg eerst het Microsoft 365 E5-proefabonnement toe en wijs de nieuwe Microsoft 365-licentie toe aan uw globale-beheerdersaccount.
  
1. Gebruik in een privévenster van een internetbrowser uw globale beheerdersaccountreferenties om u aan te melden bij het Microsoft 365 beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com) .
    
2. Selecteer op **Microsoft 365 pagina beheercentrum** in de linkernavigatie de optie **Facturering > Services aanschaffen.**
    
3. Selecteer op **de pagina** Services aanschaffen de **optie Microsoft 365 E5** en selecteer vervolgens **Gratis proefversie downloaden.**

4. Op de **Microsoft 365 E5 proefversie,** besluit u een sms-bericht of een telefoongesprek te ontvangen, voert u uw telefoonnummer in en selecteert u Vervolgens **Sms mij** of **Bel mij**. Voer de verificatie uit.

5. Selecteer op **de pagina Uw bestelling bevestigen** de optie Nu **proberen.**

6. Selecteer op de pagina Orderbevestiging de **optie Doorgaan.** 

7. Selecteer in Microsoft 365 beheercentrum **Gebruikers > Actieve gebruikers.**

8. Selecteer **in Actieve gebruikers** uw beheerdersaccount.

9. Selecteer **Licenties en apps.**

10. Schakel de licentie voor Office 365 Enterprise E5 uit en activeer de licentie voor Microsoft 365 E5.

11. Selecteer **Wijzigingen opslaan** en sluit het informatievenster voor gebruikersaccounts.

Herhaal vervolgens stap 8 tot en met 11 van de vorige procedure voor al uw andere accounts (gebruiker 2, gebruiker 3, gebruiker 4 en gebruiker 5).
  
> [!NOTE]
> De duur van het Microsoft 365 E5 proefabonnement is 30 dagen. Voor een permanente testomgeving kunt u het omzetten naar een betaald abonnement met een klein aantal licenties.
  
Uw testomgeving heeft nu:
  
- Een Microsoft 365 E5-proefabonnement.
- Al uw toepasselijke gebruikersaccounts (alleen de globale beheerder of alle vijf gebruikersaccounts) zijn geschikt voor het gebruik van Microsoft 365 E5.
    
De resulterende configuratie, die Microsoft 365 E5 toevoegt, ziet er als volgende uit:
  
![Fase 3 van de Microsoft 365 Enterprise-testomgeving](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>Fase 4: een Windows 10 Enterprise-computer maken

In deze fase maakt u een zelfstandige computer met Windows 10 Enterprise als een fysieke computer, een virtuele machine of een virtuele machine van Azure.
  
### <a name="physical-computer"></a>Fysieke computer

Op een persoonlijke computer installeert u Windows 10 Enterprise. U kunt de proefversie voor Windows 10 Enterprise [hier](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)downloaden.
  
### <a name="virtual-machine"></a>Virtuele machine

Gebruik de hypervisor van uw keuze om een virtuele machine te maken en installeer Windows 10 Enterprise op. U kunt de proefversie voor Windows 10 Enterprise [hier](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)downloaden.
  
### <a name="virtual-machine-in-azure"></a>Virtuele machine in Azure

Als u een virtuele Windows 10-machine in Microsoft Azure wilt maken, ***heeft u een abonnement nodig dat is gebaseerd op Visual Studio***, dat toegang biedt tot de afbeelding voor Windows 10 Enterprise. Andere typen Azure-abonnementen, zoals proefabonnementen en betaalde abonnementen, hebben geen toegang tot deze afbeelding. Zie [Windows-client in Azure gebruiken voor dev/test-scenario's](/azure/virtual-machines/windows/client-images)voor de meest recente informatie.
  
> [!NOTE]
> De volgende opdrachtsets gebruiken de nieuwste versie van Azure PowerShell. Zie [Aan de slag met Azure PowerShell-cmdlets](/powershell/azureps-cmdlets-docs/). Met deze opdracht bouwt u een virtuele machine voor Windows 10 Enterprise genaamd WIN10 en alle benodigde infrastructuur, inclusief een resourcegroep, een opslagaccount en een virtueel netwerk. Als u al bekend bent met Azure-infrastructuurservices, past u deze instructies aan aan uw momenteel geïmplementeerde infrastructuur.
  
Start eerst een Microsoft PowerShell-prompt.
  
Meld u aan bij uw Azure-account met behulp van de volgende opdracht.
  
```powershell
Connect-AzAccount
```

Gebruik deze opdracht om de naam van uw abonnement op te halen.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Stel uw Azure-abonnement in. Vervang alles in de aanhalingstekens, inclusief \< and > de tekens, door de juiste naam.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Vervolgens maakt u een nieuwe resourcegroep aan. Als u de naam van een unieke resourcegroep wilt bepalen, gebruikt u deze opdracht om uw bestaande resourcegroepen weer te geven.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Maak uw nieuwe resourcegroep aan met deze opdrachten. Vervang alles in de aanhalingstekens, inclusief \< and > de tekens, door de juiste namen.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Maak vervolgens een nieuw virtueel netwerk en de win10-virtuele machine met deze opdrachten. Geef desgevraagd de naam en het wachtwoord op van het lokale beheerdersaccount voor WIN10 en bewaar deze op een veilige locatie.
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a>Fase 5: uw Windows 10-computer verbinden met Azure Active Directory

Zodra de fysieke of virtuele computer met Windows 10 Enterprise is gemaakt, meldt u zich aan met een lokaal beheerdersaccount.
  
> [!NOTE]
> Gebruik deze instructies voor een virtuele computer in Azure  [om](/azure/virtual-machines/windows/connect-logon) er verbinding mee te maken.
  
Vervolgens verbindt u de WIN10-computer met de Azure Active Directory-tenant van uw Microsoft 365 E5-abonnement.
  
1. Selecteer op het bureaublad van de WIN10-computer de optie Start > Instellingen > Accounts > Toegang tot werk- of **schoolaccounts > Verbinding maken.**
    
2. Selecteer in **het dialoogvenster Een werk-** of schoolaccount instellen de optie Deelnemen aan dit apparaat om **Azure Active Directory.**
    
3. Voer **in werk-** of schoolaccount de naam van het globale beheerdersaccount van uw Microsoft 365 E5 en selecteer **Volgende.**
    
4. Voer **in Wachtwoord** invoeren het wachtwoord in voor uw globale beheerdersaccount en selecteer vervolgens **Aanmelden.**
    
5. Wanneer u wordt gevraagd of dit uw organisatie is, **selecteert** u Deelnemen en selecteert u **vervolgens Klaar**.
    
6. Sluit het Instellingenvenster.
    
Installeer vervolgens Microsoft 365-apps voor ondernemingen op de WIN10-computer:
  
1. Open de Microsoft Edge browser en meld u aan [bij het Microsoft 365 beheercentrum](https://admin.microsoft.com) met uw globale beheerdersaccountreferenties.
    
2. Selecteer op **Microsoft Office tabblad Start** de optie **Office.**
    
3. Wanneer u wordt gevraagd wat u moet doen, **selecteert** u Uitvoeren en selecteert u **Vervolgens Ja** voor **gebruikersaccountbeheer.**
    
4. Wacht totdat de installatie van Office is voltooid. Wanneer u Ziet **Dat u klaar bent!**, selecteert u **tweemaal** sluiten.
    
De resulterende omgeving ziet er als volgende uit:

![Fase 5 van de Microsoft 365 Enterprise-testomgeving](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Dit geldt ook voor de WIN10-computer die:

- Verbonden is met de Azure Active Directory-tenant van uw Microsoft 365 E5-abonnement.
- Geregistreerd is als een Azure Active Directory-apparaat in Microsoft Intune (EMS).
- Microsoft 365-apps voor ondernemingen geïnstalleerd.
  
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