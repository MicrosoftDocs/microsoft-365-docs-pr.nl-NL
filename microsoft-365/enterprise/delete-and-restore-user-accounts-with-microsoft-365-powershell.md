---
title: Microsoft 365-gebruikersaccounts verwijderen met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: In dit artikel vindt u informatie over het gebruik van verschillende modules in PowerShell om Microsoft 365-gebruikersaccounts te verwijderen.
ms.openlocfilehash: 6da2d83b3f305db09f8c1d02f54e643a0ad1978b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689316"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>Microsoft 365-gebruikersaccounts verwijderen met PowerShell

Met PowerShell voor Microsoft 365 kunt u een gebruikersaccount verwijderen.
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Wanneer u verbinding hebt, gebruikt u de volgende syntaxis om een afzonderlijke gebruikersaccount te verwijderen:
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

In dit voorbeeld wordt de fabricec@litwareinc.com van de gebruikersaccount verwijderd.
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> Met de parameter **-ObjectID** in de **Remove-AzureADUser** wordt de aanmeldingsnaam van de account geaccepteerd, ook wel bekend als de UPN (User Principal Name) of de object-id van het account.
  
Gebruik de volgende opdrachten om de accountnaam weer te geven op basis van de naam van de gebruiker:
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In dit voorbeeld wordt de accountnaam van de gebruiker met de naam Caleb Sills weergegeven.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Als u een account wilt verwijderen op basis van de weergavenaam van de gebruiker, gebruikt u de volgende opdrachten:
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Wanneer u een gebruikersaccount verwijdert met de Microsoft Azure Active Directory-module voor Windows PowerShell, wordt het account niet permanent verwijderd. U kunt de verwijderde gebruikersaccount binnen 30 dagen herstellen.

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Als u een gebruikersaccount wilt verwijderen, gebruikt u de volgende syntaxis:
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

In dit voorbeeld wordt de BelindaN@litwareinc.com van het gebruikersaccount verwijderd.
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

Wanneer u een verwijderd gebruikersaccount binnen de termijn van 30 dagen wilt herstellen, gebruikt u de volgende syntaxis:
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

In dit voorbeeld worden de verwijderde account BelindaN@litwareinc.com hersteld.
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

 **Opmerkingen:**
  
- Voer de volgende opdracht uit om de lijst weer te geven met verwijderde gebruikers die u kunt herstellen:
    
  ```powershell
  Get-MsolUser -All -ReturnDeletedUsers
  ```

- Als de oorspronkelijke User Principal name van de gebruikersaccount wordt gebruikt door een ander account, gebruikt u de _NewUserPrincipalName_ -parameter in plaats van _userPrincipalName_ om een andere Principal-naam van de gebruiker op te geven wanneer u het gebruikersaccount terugzet.


## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
