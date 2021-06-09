---
title: Gebruikersaccounts Microsoft 365 blokkeren met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: PowerShell gebruiken om toegang tot accounts te blokkeren en Microsoft 365 deblokkeren.
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754678"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>Gebruikersaccounts Microsoft 365 blokkeren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Wanneer u de toegang tot een Microsoft 365 account blokkeert, voorkomt u dat iemand het account gebruikt om zich aan te melden en toegang te krijgen tot de services en gegevens in uw Microsoft 365 organisatie. U kunt PowerShell gebruiken om de toegang tot afzonderlijke of meerdere gebruikersaccounts te blokkeren.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De powershell Azure Active Directory powershell gebruiken voor Graph module

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
 
### <a name="block-access-to-individual-user-accounts"></a>Toegang tot afzonderlijke gebruikersaccounts blokkeren

Gebruik de volgende syntaxis om een afzonderlijk gebruikersaccount te blokkeren:
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> De *parameter -ObjectID* in de cmdlet **Set-AzureAD** accepteert de aanmeldingsnaam van het account, ook wel de gebruikersnaam genoemd, of de object-id van het account.
  
In dit voorbeeld wordt de toegang tot het gebruikersaccount *fabricec@litwareinc.com.*
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

Voer de volgende opdracht uit om dit gebruikersaccount te deblokkeren:
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

Gebruik de volgende opdrachten om de UPN van het gebruikersaccount weer te geven op basis van de weergavenaam van de gebruiker:
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

In dit voorbeeld wordt de UPN van het gebruikersaccount voor de gebruiker *Caleb Sills weergegeven.*
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Als u een account wilt blokkeren op basis van de weergavenaam van de gebruiker, gebruikt u de volgende opdrachten:
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

Als u de geblokkeerde status van een gebruikersaccount wilt controleren, gebruikt u de volgende opdracht:
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>Meerdere gebruikersaccounts blokkeren

Als u de toegang voor meerdere gebruikersaccounts wilt blokkeren, maakt u een tekstbestand met één accountnaam op elke regel als deze:
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

In de volgende opdrachten is het voorbeeldtekstbestand *C:\Mijn Documents\Accounts.txt.* Vervang deze bestandsnaam door het pad en de bestandsnaam van het tekstbestand.
  
Voer de volgende opdracht uit om de toegang tot de accounts in het tekstbestand te blokkeren:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

Als u de blokkering van de accounts in het tekstbestand wilt opheffen, gaat u als volgt te werk:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
    
### <a name="block-individual-user-accounts"></a>Afzonderlijke gebruikersaccounts blokkeren

Gebruik de volgende syntaxis om toegang voor een afzonderlijk gebruikersaccount te blokkeren:
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory module voor Windows PowerShell module en cmdlets met *Msol* in hun naam. U moet deze cmdlets uitvoeren vanaf Windows PowerShell.

In dit voorbeeld wordt de toegang tot de fabricec van het gebruikersaccount *\@ litwareinc.com.*
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

Voer de volgende opdracht uit om het gebruikersaccount te deblokkeren:
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

Voer de volgende opdracht uit om de geblokkeerde status van een gebruikersaccount te controleren:
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a>Toegang blokkeren voor meerdere gebruikersaccounts

Maak eerst een tekstbestand met één account op elke regel als dit:
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

In de volgende opdrachten is het voorbeeldtekstbestand *C:\Mijn Documents\Accounts.txt.* Vervang deze bestandsnaam door het pad en de bestandsnaam van het tekstbestand.
    
Voer de volgende opdracht uit als u de toegang wilt blokkeren voor de accounts die in het tekstbestand worden vermeld:
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
Als u de blokkering van de accounts in het tekstbestand wilt opheffen, gaat u als volgt te werk:
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
