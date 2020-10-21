---
title: Licentie-en niet-gelicentieerde Microsoft 365-gebruikers weergeven met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/21/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: In dit artikel wordt uitgelegd hoe u PowerShell kunt gebruiken voor het weergeven van licentie-en niet-gelicentieerde Microsoft 365-gebruikersaccounts.
ms.openlocfilehash: b38ee7674abaea6b63d0661ba79a9814f8c54229
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651382"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a>Licentie-en niet-gelicentieerde Microsoft 365-gebruikers weergeven met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Gebruikersaccounts in uw Microsoft 365-organisatie kunnen enkele, alle of geen van de beschikbare licenties die aan hen zijn toegewezen, krijgen van de licentie plannen die beschikbaar zijn in uw organisatie. U kunt PowerShell voor Microsoft 365 gebruiken om snel de gebruikers met een licentie en gebruikers zonder licentie te vinden in uw organisatie.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
 
Voer de volgende opdracht uit als u de lijst wilt weergeven met alle gebruikersaccounts in uw organisatie waaraan geen licentie plannen zijn toegewezen (gebruikers zonder licentie):
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

Voer de volgende opdracht uit om de lijst met alle gebruikersaccounts in uw organisatie weer te geven waaraan een licentie abonnement is toegewezen (gebruikers met een licentie):
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$True ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
>Als u alle gebruikers in uw abonnement wilt weergeven, gebruikt u de `Get-AzureAdUser -All $true` opdracht.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Voer de volgende opdracht uit in PowerShell om de lijst met alle gebruikersaccounts en de bijbehorende licentiestatus in uw organisatie weer te geven:
  
```powershell
Get-MsolUser -All
```

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

Voer de volgende opdracht uit om de lijst met alle gebruikersaccounts zonder licentie in uw organisatie weer te geven:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

Voer de volgende opdracht uit om de lijst met alle gelicentieerde gebruikersaccounts in uw organisatie weer te geven:
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
