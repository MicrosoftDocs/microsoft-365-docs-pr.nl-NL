---
title: Microsoft 365-gebruikersaccounts verwijderen met PowerShell
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: Meer informatie over het gebruik van verschillende modules in PowerShell om Microsoft 365-gebruikersaccounts te verwijderen.
ms.openlocfilehash: 39bf57fe7e7aad1bdc9915e503107ad799515030
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754538"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>Microsoft 365-gebruikersaccounts verwijderen met PowerShell

Met PowerShell voor Microsoft 365 kunt u gebruikersaccounts verwijderen en herstellen.

>[!Note]
>Informatie over het [herstellen van een gebruikersaccount](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) met behulp van het microsoft 365-Beheercentrum.
>
>Zie [gebruikers en groepen beheren](https://docs.microsoft.com/microsoft-365/admin/add-users/)voor een lijst met aanvullende bronnen.
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Nadat u verbinding hebt gemaakt, gebruikt u de volgende syntaxis om een afzonderlijke gebruikersaccount te verwijderen:
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

In dit voorbeeld wordt de gebruikersaccount *fabricec \@ litwareinc.com*.
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> Met de parameter *-ObjectID* in de **Remove-AzureADUser** wordt de aanmeldingsnaam van de account geaccepteerd, ook wel bekend als de User Principal name of de object-id van de account.
  
Gebruik de volgende opdrachten om de accountnaam weer te geven op basis van de naam van de gebruiker:
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In dit voorbeeld wordt de accountnaam weergegeven voor de gebruiker *Caleb Sills*.
  
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

Wanneer u een gebruikersaccount verwijdert via Microsoft Azure Active Directory-module voor Windows PowerShell, wordt het account niet permanent verwijderd. U kunt de verwijderde gebruikersaccount binnen 30 dagen herstellen.

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Als u een gebruikersaccount wilt verwijderen, gebruikt u de volgende syntaxis:
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>PowerShell core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met *MSOL* in de naam. Voer de volgende cmdlets uit vanuit Windows PowerShell.
>

In dit voorbeeld wordt de *BelindaN@litwareinc.com*van het gebruikersaccount verwijderd.
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

Wanneer u een verwijderd gebruikersaccount binnen de termijn van 30 dagen wilt herstellen, gebruikt u de volgende syntaxis:
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

In dit voorbeeld worden de verwijderde account *BelindaN \@ litwareinc.com*hersteld.
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> Voer de volgende opdracht uit om de lijst weer te geven met verwijderde gebruikers die u kunt herstellen:
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> Als de oorspronkelijke User Principal name van de gebruikersaccount wordt gebruikt door een ander account, gebruikt u de _NewUserPrincipalName_ -parameter in plaats van _userPrincipalName_ om een andere Principal-naam van de gebruiker op te geven wanneer u het gebruikersaccount terugzet.


## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
