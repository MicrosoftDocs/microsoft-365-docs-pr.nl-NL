---
title: Gelicentieerde en niet-gelicentieerde Microsoft 365 weergeven met PowerShell
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
description: In dit artikel wordt uitgelegd hoe u PowerShell kunt gebruiken om gelicentieerde en niet-gelicentieerde Microsoft 365 gebruikersaccounts weer te geven.
ms.openlocfilehash: b38ee7674abaea6b63d0661ba79a9814f8c54229
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651382"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a>Gelicentieerde en niet-gelicentieerde Microsoft 365 weergeven met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Gebruikersaccounts in Microsoft 365 organisatie kunnen bepaalde, alle of geen beschikbare licenties aan hen hebben toegewezen vanuit de licentieplannen die beschikbaar zijn in uw organisatie. U kunt PowerShell voor Microsoft 365 gebruiken om snel de gelicentieerde en niet-gelicentieerde gebruikers in uw organisatie te vinden.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De powershell Azure Active Directory powershell gebruiken voor Graph module

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
 
Voer de volgende opdracht uit als u de lijst wilt weergeven met alle gebruikersaccounts in uw organisatie die geen licentieplannen (gebruikers zonder licentie) hebben gekregen:
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

Voer de volgende opdracht uit als u de lijst wilt weergeven met alle gebruikersaccounts in uw organisatie die aan een licentie zijn toegewezen (gelicentieerde gebruikers):
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$True ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
>Gebruik de opdracht om alle gebruikers in uw abonnement op te `Get-AzureAdUser -All $true` nemen.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Als u de lijst met alle gebruikersaccounts en de licentiestatus in uw organisatie wilt weergeven, voer dan de volgende opdracht uit in PowerShell:
  
```powershell
Get-MsolUser -All
```

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

Voer de volgende opdracht uit om de lijst met alle gebruikersaccounts zonder een vergunning in uw organisatie weer te geven:
  
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
