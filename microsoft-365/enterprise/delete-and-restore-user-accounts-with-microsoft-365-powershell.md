---
title: Gebruikersaccounts Microsoft 365 verwijderen met PowerShell
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
description: Meer informatie over het gebruik van verschillende modules in PowerShell om Microsoft 365 gebruikersaccounts te verwijderen.
ms.openlocfilehash: 32081d1ce0cbc7aac89b337cf8b5d08bc8e43dfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919138"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>Gebruikersaccounts Microsoft 365 verwijderen met PowerShell

U kunt PowerShell gebruiken om Microsoft 365 gebruikersaccounts te verwijderen en te herstellen.

>[!Note]
>Meer informatie over het [herstellen van een gebruikersaccount](../admin/add-users/restore-user.md) via het Microsoft 365 beheercentrum.
>
>Zie Gebruikers en groepen beheren voor een lijst met [aanvullende bronnen.](../admin/add-users/index.yml)
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De powershell Azure Active Directory powershell gebruiken voor Graph module

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

Nadat u verbinding hebt gemaakt, gebruikt u de volgende syntaxis om een afzonderlijk gebruikersaccount te verwijderen:
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

In dit voorbeeld wordt de fabricec van het *\@ gebruikersaccount litwareinc.com.*
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> De *parameter -ObjectID* in de cmdlet **Remove-AzureADUser** accepteert de aanmeldingsnaam van het account, ook wel de gebruikersnaam of de object-id van het account genoemd.
  
Gebruik de volgende opdrachten om de accountnaam weer te geven op basis van de naam van de gebruiker:
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In dit voorbeeld wordt de accountnaam voor de gebruiker *Caleb Sills weergegeven.*
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Als u een account wilt verwijderen op basis van de weergavenaam van de gebruiker, gebruikt u de volgende opdrachten:
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell

Wanneer u een gebruikersaccount verwijdert via Microsoft Azure Active Directory module voor Windows PowerShell, wordt het account niet definitief verwijderd. U kunt het verwijderde gebruikersaccount binnen 30 dagen herstellen.

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Als u een gebruikersaccount wilt verwijderen, gebruikt u de volgende syntaxis:
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in hun naam. Voer deze cmdlets uit vanuit Windows PowerShell.
>

In dit voorbeeld wordt het gebruikersaccount *BelindaN@litwareinc.com.*
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

Als u een verwijderd gebruikersaccount binnen de respijtperiode van 30 dagen wilt herstellen, gebruikt u de volgende syntaxis:
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

In dit voorbeeld wordt het verwijderde account *BelindaN \@ litwareinc.com.*
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> Voer de volgende opdracht uit om de lijst met verwijderde gebruikers weer te geven die kunnen worden hersteld:
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> Als de oorspronkelijke gebruikersnaam van het gebruikersaccount door een ander account wordt gebruikt, gebruikt u de parameter _NewUserPrincipalName_ in plaats van _UserPrincipalName_ om een andere gebruikersnaam op te geven wanneer u het gebruikersaccount herstelt.


## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)