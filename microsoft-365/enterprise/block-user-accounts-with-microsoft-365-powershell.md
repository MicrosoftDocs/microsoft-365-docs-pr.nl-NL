---
title: Microsoft 365-gebruikersaccounts blokkeren met PowerShell
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
description: PowerShell gebruiken om de toegang tot Microsoft 365-accounts te blokkeren of te deblokkeren.
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754678"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>Microsoft 365-gebruikersaccounts blokkeren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Als u toegang tot een Microsoft 365-account blokkeert, voorkomt u dat iedereen het account kan gebruiken om u aan te melden en toegang te krijgen tot de services en gegevens in uw Microsoft 365-organisatie. U kunt PowerShell gebruiken om toegang te blokkeren voor afzonderlijke of meerdere gebruikersaccounts.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
 
### <a name="block-access-to-individual-user-accounts"></a>Toegang tot afzonderlijke gebruikersaccounts blokkeren

Gebruik de volgende syntaxis om een afzonderlijke gebruikersaccount te blokkeren:
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> Met de parameter *-ObjectID* in de cmdlet **set-AzureAD** wordt de aanmeldingsnaam van het account geaccepteerd, ook wel bekend als de User Principal name of de object-id van de account.
  
In dit voorbeeld wordt de toegang tot de *fabricec@litwareinc.com*van de gebruikersaccount geblokkeerd.
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

Voer de volgende opdracht uit als u dit gebruikersaccount wilt deblokkeren:
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

Als u de UPN van het gebruikersaccount wilt weergeven op basis van de weergavenaam van de gebruiker, gebruikt u de volgende opdrachten:
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

In dit voorbeeld wordt de UPN van het gebruikersaccount voor de gebruiker  *Caleb Sills*.
  
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

Als u de toegang voor meerdere gebruikersaccounts wilt blokkeren, maakt u een tekstbestand met één aanmeldingsnaam op elke regel, zoals deze:
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

In de volgende opdrachten is het voorbeeldtekst bestand *c:\mijn Documents\Accounts.txt*. Vervang de naam van het bestand met het pad en de bestandsnaam van het tekstbestand.
  
Voer de volgende opdracht uit als u de toegang tot de accounts die worden vermeld in het tekstbestand wilt blokkeren:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

Voer de volgende opdracht uit om de accounts die in het tekstbestand worden weergegeven, op te heffen:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
### <a name="block-individual-user-accounts"></a>Afzonderlijke gebruikersaccounts blokkeren

Gebruik de volgende syntaxis om toegang te blokkeren voor een afzonderlijke gebruikersaccount:
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met *MSOL* in de naam. U dient deze cmdlets uit te voeren vanuit Windows PowerShell.

In dit voorbeeld wordt de toegang blokkeren voor het gebruikersaccount *fabricec \@ litwareinc.com*.
  
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

Maak eerst als volgt een tekstbestand dat één account op elke regel bevat:
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

In de volgende opdrachten is het voorbeeldtekst bestand *c:\mijn Documents\Accounts.txt*. Vervang de naam van het bestand met het pad en de bestandsnaam van het tekstbestand.
    
Voer de volgende opdracht uit om toegang te blokkeren voor de accounts die in het tekstbestand worden weergegeven:
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
Voer de volgende opdracht uit om de accounts die in het tekstbestand worden weergegeven, op te heffen:
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
