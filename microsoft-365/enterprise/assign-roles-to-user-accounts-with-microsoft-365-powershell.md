---
title: Rollen toewijzen aan Microsoft 365 gebruikersaccounts met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: In dit artikel leert u hoe u Snel en eenvoudig PowerShell kunt gebruiken Microsoft 365 beheerdersrollen toe te wijzen aan gebruikersaccounts.
ms.openlocfilehash: 84e785052c970ca15487540c3904eacdd0e9ca28
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905378"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>Beheerdersrollen toewijzen aan Microsoft 365 gebruikersaccounts met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt eenvoudig rollen toewijzen aan gebruikersaccounts met PowerShell voor Microsoft 365.

>[!Note]
>Meer informatie over [het toewijzen van beheerdersrollen](../admin/add-users/assign-admin-roles.md) aan gebruikersaccounts met het Microsoft 365 beheercentrum.
>
>Zie Gebruikers en groepen beheren voor een lijst met [aanvullende bronnen.](../admin/add-users/index.yml)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De powershell Azure Active Directory powershell gebruiken voor Graph module

Gebruik eerst een globale beheerdersaccount om verbinding [te maken met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Identificeer vervolgens de aanmeldingsnaam van het gebruikersaccount dat u wilt toevoegen aan een rol (bijvoorbeeld: fredsm \@ contoso.com). Dit wordt ook wel de naam van de gebruikershoofdnaam (UPN) genoemd.

Bepaal vervolgens de naam van de rol. Zie [beheerdersrolmachtigingen in Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

>[!Note]
>Let op de notities in dit artikel. Sommige rollennamen zijn anders voor Azure Active Directory (Azure AD) PowerShell. De rol van *SharePoint beheerder* in het Microsoft 365 beheercentrum is bijvoorbeeld SharePoint *servicebeheerder* in Azure AD PowerShell.
>

Vul vervolgens de aanmeldings- en rolnamen in en voer de volgende opdrachten uit:
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

Hier is een voorbeeld van een voltooide opdrachtset die de rol SharePoint servicebeheerder toewijst aan het *belindan \@ contoso.com* account:
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

Als u de lijst met gebruikersnamen voor een specifieke beheerdersrol wilt weergeven, gebruikt u deze opdrachten.

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell

Gebruik eerst een globale beheerdersaccount om verbinding [te maken met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
### <a name="for-a-single-role-change"></a>Voor één rolwijziging

De meest voorkomende manieren om het gebruikersaccount op te geven, is door de weergavenaam of de e-mailnaam te gebruiken, die ook wel de aanmeldingsnaam of de naam van de gebruikersnaam (UPN) wordt genoemd.

#### <a name="display-names-of-user-accounts"></a>Namen van gebruikersaccounts weergeven

Als u gewend bent om te werken met de weergavenamen van gebruikersaccounts, bepaalt u de volgende informatie:
  
- Het gebruikersaccount dat u wilt configureren
    
    Als u het gebruikersaccount wilt opgeven, moet u de weergavenaam bepalen. Gebruik deze opdracht om een volledige lijst met accounts te krijgen:
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    Deze opdracht bevat de weergavenaam van uw gebruikersaccounts, gesorteerd op weergavenaam, één scherm tegelijk. U kunt de lijst filteren op een kleinere set met de **cmdlet Where.** Zie het volgende voorbeeld.

   >[!Note]
   >PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in hun naam. Voer deze cmdlets uit vanuit Windows PowerShell.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    Deze opdracht bevat alleen de gebruikersaccounts waarvoor de weergavenaam begint met 'Jan'.
    
- De rol die u wilt toewijzen
    
    Als u de lijst met beschikbare beheerdersrollen wilt weergeven die u aan gebruikersaccounts kunt toewijzen, gebruikt u deze opdracht:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Nadat u de weergavenaam van het account en de naam van de rol hebt bepaald, gebruikt u deze opdrachten om de rol toe te wijzen aan het account:
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

Plak de opdrachten in Kladblok. Voor de *$dispName* en *$roleName* variabelen vervangt u de beschrijvingstekst door de waarden. Verwijder de \< and > tekens, maar bewaar de aanhalingstekens. Plak de gewijzigde lijnen in de Microsoft Azure Active Directory module om Windows PowerShell uit te voeren. U kunt ook de ise (Integrated Script Environment Windows PowerShell (Integrated Script Environment) gebruiken.
  
Hier is een voorbeeld van een voltooide opdrachtset:
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>Aanmeldingsnamen van gebruikersaccounts

Als u gewend bent om te werken met de aanmeldingsnamen of UPN's van gebruikersaccounts, bepaalt u de volgende informatie:
  
- Upn van het gebruikersaccount
    
    Als u de UPN niet kent, gebruikt u deze opdracht:
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Deze opdracht bevat de UPN van uw gebruikersaccounts, gesorteerd op UPN, één scherm tegelijk. U kunt de cmdlet **Where** gebruiken om de lijst te filteren. Hier volgt een voorbeeld:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Deze opdracht bevat alleen de gebruikersaccounts waarvoor de weergavenaam begint met 'Jan'.
    
- De rol die u wilt toewijzen
    
    Als u de lijst met beschikbare rollen wilt weergeven die u kunt toewijzen aan gebruikersaccounts, gebruikt u deze opdracht:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Nadat u de UPN van het account en de naam van de rol hebt, gebruikt u deze opdrachten om de rol toe te wijzen aan het account:
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

Kopieer de opdrachten en plak ze in Kladblok. Voor de **$upnName** en **$roleName** variabelen. Vervang de beschrijvingstekst door de waarden. Verwijder de \< and > tekens, maar bewaar de aanhalingstekens. Plak de gewijzigde lijnen in Microsoft Azure Active Directory module om Windows PowerShell uit te voeren. U kunt ook de ise Windows PowerShell gebruiken.
  
Hier is een voorbeeld van een voltooide opdrachtset:
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>Wijzigingen in meerdere rollen

Voor meerdere rollenwijzigingen bepaalt u de volgende informatie:
  
- Welke gebruikersaccounts u wilt configureren. U kunt de methoden in de vorige sectie gebruiken om de set weergavenamen of UPN's te verzamelen.
    
- Welke rollen u wilt toewijzen aan elk gebruikersaccount. Als u de lijst met beschikbare rollen wilt weergeven die u kunt toewijzen aan gebruikersaccounts, gebruikt u deze opdracht:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Maak vervolgens een door komma's gescheiden tekstbestand (CSV) met de weergavenaam of UPN- en rolnaamvelden. U kunt dit eenvoudig doen in Microsoft Excel.

Hier is een voorbeeld voor weergavenamen:
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

Vul vervolgens de locatie van het CSV-bestand in en voer de resulterende opdrachten uit op de opdrachtprompt van PowerShell.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

Hier is een voorbeeld voor UPN's:
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

Vul vervolgens de locatie van het CSV-bestand in en voer de resulterende opdrachten uit op de opdrachtprompt van PowerShell.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a>Zie ook

- [Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)