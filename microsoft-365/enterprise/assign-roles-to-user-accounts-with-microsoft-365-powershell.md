---
title: Rollen toewijzen aan gebruikersaccounts van Microsoft 365 met PowerShell
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
description: In dit artikel leest u hoe u met PowerShell voor Microsoft 365 rollen snel en gemakkelijk kunt toewijzen aan gebruikersaccounts.
ms.openlocfilehash: 9df1b018cf3e89e0afbd5265fdd1ec9f92b34aec
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235428"
---
# <a name="assign-roles-to-microsoft-365-user-accounts-with-powershell"></a>Rollen toewijzen aan gebruikersaccounts van Microsoft 365 met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt snel en eenvoudig rollen toewijzen aan gebruikersaccounts met behulp van PowerShell voor Microsoft 365.

>[!Note]
>[Meer informatie over het toewijzen van rollen aan gebruikersaccounts](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) met het microsoft 365-Beheercentrum. Zie [gebruikers en groepen beheren](https://docs.microsoft.com/microsoft-365/admin/add-users/)voor een lijst met aanvullende bronnen.
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) met behulp van een account van een globale beheerder.
  
Bepaal vervolgens de aanmeldingsnaam van het gebruikersaccount dat u wilt toevoegen aan een rol (voorbeeld: fredsm@contoso.com). Dit wordt ook wel de UPN (User Principal Name) genoemd.

Bepaal vervolgens de naam van de rol. Gebruik deze [lijst met machtigingen voor beheerdersrollen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

>[!Note]
>Let op de notities in dit artikel. Sommige namen van rollen zijn verschillend voor Azure AD PowerShell. De rol ' SharePoint-beheerder ' in het Microsoft 365-Beheercentrum heeft bijvoorbeeld de naam SharePoint Service beheerder voor Azure AD PowerShell.
>

Vul vervolgens de namen van de aanmeld-en rollen in en voer deze opdrachten uit.
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

Hier ziet u een voorbeeld van een voltooide opdrachtenset waarmee de rol van SharePoint-Service beheerder wordt toegewezen aan het belindan@contoso.com-account:
  
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

Met deze opdrachten kunt u de lijst met gebruikersnamen voor een bepaalde rol weergeven.

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) met behulp van een account van een globale beheerder.
  
### <a name="for-a-single-role-change"></a>Voor één wijziging van een rol

De meest voorkomende manier van een specifiek gebruikersaccount is de naam van de weergave of de e-mail naam van de persoon, ook bekend als de naam van de aanmelding of de UPN (User Principal Name).

#### <a name="display-names-of-user-accounts"></a>Namen van gebruikersaccounts weergeven

Als u werkt met de weergavenamen van gebruikersaccounts, bepaalt u het volgende:
  
- Het gebruikersaccount dat u wilt configureren.
    
    Als u het gebruikersaccount wilt opgeven, moet u de weergavenaam ervan bepalen. Voor een volledige lijst van accounts gebruikt u deze opdracht:
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    Met deze opdracht wordt de weergavenaam van uw gebruikersaccounts weergegeven, gesorteerd op de weergavenaam, één scherm tegelijkertijd. U kunt de lijst filteren op een kleinere set met behulp **van de cmdlet** -cmdlet. Hier ziet u een voorbeeld:

   >[!Note]
   >PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    Met deze opdracht worden alleen de gebruikersaccounts weergegeven waarvoor de weergavenaam begint met ' John '.
    
- De rol die u wilt toewijzen.
    
    Met de volgende opdracht kunt u de lijst met beschikbare rollen weergeven die u kunt toewijzen aan gebruikersaccounts:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Wanneer u de weergavenaam van het account en de naam van de rol hebt vastgesteld, kunt u deze opdrachten gebruiken om de rol aan het account toe te wijzen:
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

Kopieer de opdrachten en plak deze in Kladblok. Voor de **$dispName** en **$roleName** variabelen vervangt u de beschrijvende tekst door de bijbehorende waarden, verwijdert u de \< and > tekens en verlaat u de aanhalingstekens. Kopieer de gewijzigde regels en plak ze in het venster Windows Azure Active Directory voor Windows PowerShell om ze uit te voeren. U kunt ook gebruikmaken van de Windows PowerShell Integrated script Environment (ISE).
  
Hier ziet u een voorbeeld van een voltooide opdrachtreeks:
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>Aanmeldingsnamen van gebruikersaccounts

Als u gebruikmaakt van aanmeldingsnamen of Upn's van gebruikersaccounts, controleert u het volgende:
  
- De UPN van de gebruikersaccount.
    
    Als u de UPN nog niet weet, gebruikt u deze opdracht:
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Met deze opdracht wordt de UPN van uw gebruikersaccounts weergegeven, gesorteerd op de UPN, één scherm tegelijkertijd. U kunt de lijst filteren op een kleinere set met behulp **van de cmdlet** -cmdlet. Hier ziet u een voorbeeld:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Met deze opdracht worden alleen de gebruikersaccounts weergegeven waarvoor de weergavenaam begint met ' John '.
    
- De rol die u wilt toewijzen.
    
    Met de volgende opdracht kunt u de lijst met beschikbare rollen weergeven die u kunt toewijzen aan gebruikersaccounts:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Wanneer u de UPN van het account en de naam van de rol hebt, kunt u deze opdrachten gebruiken om de rol aan het account toe te wijzen:
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

Kopieer de opdrachten en plak deze in Kladblok. Voor de **$upnName** en **$roleName** variabelen vervangt u de beschrijvende tekst door de bijbehorende waarden, verwijdert u de \< and > tekens en verlaat u de aanhalingstekens. Kopieer de gewijzigde regels en plak ze in het venster Windows Azure Active Directory voor Windows PowerShell om ze uit te voeren. U kunt ook het Windows PowerShell-ISE gebruiken.
  
Hier ziet u een voorbeeld van een voltooide opdrachtreeks:
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>Wijzigingen in meerdere rollen

Voor wijzigingen in meerdere rollen, controleert u het volgende:
  
- De gebruikersaccounts die u wilt configureren. U kunt de methoden in de vorige sectie gebruiken om de set weergavenamen of-Upn's te verzamelen.
    
- Welke rollen u wilt toewijzen aan de gebruikersaccounts.
    
    Met de volgende opdracht kunt u de lijst met beschikbare rollen weergeven die u kunt toewijzen aan gebruikersaccounts:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Maak vervolgens een tekstbestand met door komma's gescheiden waarden (CSV) met de velden weergavenaam of UPN en rollen namen. U kunt dit eenvoudig doen met Microsoft Excel.

Hier ziet u een voorbeeld van weergavenamen:
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

Vul vervolgens de locatie van het CSV-bestand in en voer de resultaat opdrachten uit op de PowerShell-opdrachtprompt.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

Hier ziet u een voorbeeld voor Upn's:
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

Vul vervolgens de locatie van het CSV-bestand in en voer de resultaat opdrachten uit op de PowerShell-opdrachtprompt.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a>Zie ook

- [Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
