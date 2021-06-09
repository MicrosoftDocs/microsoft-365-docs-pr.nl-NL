---
title: Het voorbereiden van een niet-routeerbaar domein voor adreslijstsynchronisatie
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: Lees wat u moet doen als u een niet-routable domain hebt dat is gekoppeld aan uw on-premises gebruikersaccounts voordat u deze synchroniseert met uw Microsoft 365 tenant.
ms.openlocfilehash: e4d0e020c5792c610d501c33e8f3d5131b7a1ff0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927394"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a>Het voorbereiden van een niet-routeerbaar domein voor adreslijstsynchronisatie

Wanneer u uw on-premises adreslijst synchroniseert met Microsoft 365, moet u een geverifieerd domein hebben in Azure Active Directory (Azure AD). Alleen de UPN's (User Principal Names) die zijn gekoppeld aan het on-premises Ad DS-domein (Active Directory Domain Services) worden gesynchroniseerd. Elke UPN die een niet-routable domein bevat, zoals '.lokaal' (bijvoorbeeld: billa@contoso.local), wordt echter gesynchroniseerd met een .onmicrosoft.com-domein (bijvoorbeeld: billa@contoso.onmicrosoft.com). 

Als u momenteel een '.lokaal' domein gebruikt voor uw gebruikersaccounts in AD DS, wordt u aangeraden deze te wijzigen in een geverifieerd domein, zoals billa@contoso.com, om op de juiste manier te synchroniseren met uw Microsoft 365-domein.
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a>Wat gebeurt er als ik alleen een on-premises domein '.lokaal' heb?

U gebruikt Azure AD Verbinding maken om uw AD DS te synchroniseren met de Azure AD-tenant van uw Microsoft 365 tenant. Zie Uw [on-premises](/azure/architecture/reference-architectures/identity/azure-ad)identiteiten integreren met Azure AD voor meer informatie.
  
Azure AD Verbinding maken synchroniseert de UPN en het wachtwoord van uw gebruikers, zodat gebruikers zich kunnen aanmelden met dezelfde referenties die ze on-premises gebruiken. Azure AD-Verbinding maken synchroniseert echter alleen gebruikers met domeinen die worden geverifieerd door Microsoft 365. Dit betekent dat het domein ook wordt geverifieerd door Azure AD omdat Microsoft 365 identiteiten worden beheerd door Azure AD. Met andere woorden, het domein moet een geldig internetdomein zijn (zoals .com, .org, .net, .us). Als uw interne AD DS alleen een niet-routable-domein gebruikt (bijvoorbeeld '.lokaal'), kan dit mogelijk niet overeenkomen met het geverifieerde domein dat u hebt voor uw Microsoft 365 tenant. U kunt dit probleem oplossen door uw primaire domein in uw on-premises AD DS te wijzigen of door een of meer UPN-achtervoegsels toe te voegen.
  
### <a name="change-your-primary-domain"></a>Uw primaire domein wijzigen

Wijzig uw primaire domein in een domein dat u hebt geverifieerd in Microsoft 365, bijvoorbeeld contoso.com. Elke gebruiker met het domein contoso.local wordt vervolgens bijgewerkt naar contoso.com. Dit is echter een zeer betrokken proces en een eenvoudigere oplossing wordt beschreven in de volgende sectie.
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a>UPN-achtervoegsels toevoegen en uw gebruikers hieraan bijwerken

U kunt het probleem '.lokaal' oplossen door nieuwe UPN-achtervoegsels of achtervoegsels in AD DS te registreren die overeenkomen met het domein (of domeinen) dat u hebt geverifieerd in Microsoft 365. Nadat u het nieuwe achtervoegsel hebt geregistreerd, kunt u de UPN's van de gebruiker bijwerken om bijvoorbeeld de '.local' te vervangen door de nieuwe domeinnaam, zodat een gebruikersaccount eruitziet als billa@contoso.com.
  
Nadat u de UPN's hebt bijgewerkt om het geverifieerde domein te gebruiken, kunt u uw on-premises AD DS synchroniseren met Microsoft 365.
  
#### <a name="step-1-add-the-new-upn-suffix"></a>Stap 1: Het nieuwe UPN-achtervoegsel toevoegen**
  
1. Kies op de AD DS-domeincontroller in Serverbeheer **de optie Extra** Active \> **Directory-domeinen en -vertrouwensinstellingen.**
    
    **Of als u geen Windows Server 2012**
    
    Druk **Windows +R** om het dialoogvenster Uitvoeren te **openen** en typ domein.msc en kies **OK.**
    
    ![Kies Active Directory-domeinen en -vertrouwensrelatie.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. Klik in **het venster Active Directory Domains and Trusts** met de rechtermuisknop op Active Directory **Domains and Trusts** en kies **vervolgens Eigenschappen.**
    
    ![Klik met de rechtermuisknop op Active Directory-domeinen en -vertrouwensrelatie en kies Eigenschappen](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. Typ op **het tabblad UPN-achtervoegsels** in het vak Alternatieve **UPN-achtervoegsels** uw nieuwe UPN-achtervoegsel of achtervoegsels en kies vervolgens **Toepassen** \> **toevoegen.**
    
    ![Een nieuw UPN-achtervoegsel toevoegen](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    Kies **OK** wanneer u klaar bent met het toevoegen van achtervoegsels. 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a>Stap 2: het UPN-achtervoegsel voor bestaande gebruikers wijzigen
  
1. Kies op de AD DS-domeincontroller in Serverbeheer **de optie Extra** Active \> **Directory-gebruikers en -computers.**
    
    **Of als u geen Windows Server 2012**
    
    Druk **Windows +R** om het dialoogvenster Uitvoeren te **openen** en typ Dsa.msc en klik vervolgens op **OK**
    
2. Selecteer een gebruiker, klik met de rechtermuisknop en kies vervolgens **Eigenschappen.**
    
3. Kies op **het** tabblad Account in de vervolgkeuzelijst UPN-achtervoegsel het nieuwe UPN-achtervoegsel en kies **OK.**
    
    ![Nieuw UPN-achtervoegsel toevoegen voor een gebruiker](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. Voltooi deze stappen voor elke gebruiker.
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a>PowerShell gebruiken om het UPN-achtervoegsel voor al uw gebruikers te wijzigen

Als u veel gebruikersaccounts wilt bijwerken, kunt u PowerShell gemakkelijker gebruiken. In het volgende voorbeeld worden de cmdlets [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) en [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) gebruikt om alle contoso.local-achtervoegsels te wijzigen in contoso.com in AD DS. 

U kunt bijvoorbeeld de volgende PowerShell-opdrachten uitvoeren om alle contoso.local-achtervoegsels bij te werken naar contoso.com:
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

Zie [Active Directory Windows PowerShell module](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) voor meer informatie over het gebruik Windows PowerShell in AD DS.