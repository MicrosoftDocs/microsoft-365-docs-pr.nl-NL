---
title: Licenties Microsoft 365 gebruikersaccounts verwijderen met PowerShell
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
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: Hier wordt uitgelegd hoe u PowerShell kunt gebruiken om Microsoft 365 licenties te verwijderen die eerder aan gebruikers zijn toegewezen.
ms.openlocfilehash: 9944d1ab056d109b6bf71a44fe01acef78ce1f14
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920666"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a>Licenties Microsoft 365 gebruikersaccounts verwijderen met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

>[!Note]
>[Meer informatie over het verwijderen van licenties uit gebruikersaccounts](../admin/manage/remove-licenses-from-users.md) met het Microsoft 365 beheercentrum. Zie Gebruikers en groepen beheren voor een lijst met [aanvullende bronnen.](../admin/add-users/index.yml)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De powershell Azure Active Directory powershell gebruiken voor Graph module

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

Vermeld vervolgens de licentieplannen voor uw tenant met deze opdracht.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Vervolgens krijgt u de aanmeldingsnaam van het account waarvoor u een licentie wilt verwijderen, ook wel de gebruikersnaam (UPN) genoemd.

Geef ten slotte de namen van de aanmeldings- en licentieplannen van de gebruiker op, verwijder de tekens '<' en '>' en voer deze opdrachten uit.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

Als u alle licenties voor een specifiek gebruikersaccount wilt verwijderen, geeft u de aanmeldingsnaam van de gebruiker op, verwijdert u de tekens '<' en '>' en voert u deze opdrachten uit.

```powershell
$userUPN="<user sign-in name (UPN)>"
$userList = Get-AzureADUser -ObjectID $userUPN
$Skus = $userList | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
    if($Skus -is [array])
    {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        for ($i=0; $i -lt $Skus.Count; $i++) {
            $Licenses.RemoveLicenses +=  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus[$i].SkuId -EQ).SkuID   
        }
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    } else {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        $Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus.SkuId -EQ).SkuID
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    }
}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
   
Zie de volgende onderwerpen als u de informatie over het licentieplan **(AccountSkuID)** in uw organisatie wilt bekijken:
    
  - [Licenties en services weergeven met PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [Accountlicentie- en servicedetails weergeven met PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
Als u de **get-MsolUser-cmdlet** gebruikt zonder de parameter _-All_ te gebruiken, worden alleen de eerste 500 accounts geretourneerd.
    
### <a name="removing-licenses-from-user-accounts"></a>Licenties verwijderen uit gebruikersaccounts

Als u licenties wilt verwijderen uit een bestaand gebruikersaccount, gebruikt u de volgende syntaxis:
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

In dit voorbeeld wordt de **licentie litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) verwijderd uit het gebruikersaccount BelindaN@litwareinc.com.
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
>U kunt de `Set-MsolUserLicense` cmdlet niet gebruiken om gebruikers te ontzeggen van *geannuleerde* licenties. U moet dit afzonderlijk doen voor elk gebruikersaccount in het Microsoft 365 beheercentrum.
>

Als u alle licenties wilt verwijderen uit een groep bestaande gebruikers met een licentie, gebruikt u een van de volgende methoden:
  
- **De accounts filteren op basis van een bestaand accountkenmerk** Gebruik hiervoor de volgende syntaxis:
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

In dit voorbeeld worden alle licenties verwijderd uit alle gebruikersaccounts van de afdeling Verkoop in de Verenigde Staten.
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- **Een lijst met specifieke accounts gebruiken voor een specifieke licentie** Voer hiervoor de volgende stappen uit:
    
1. Maak en sla een tekstbestand op met één account op elke regel als dit:
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. Gebruik de volgende syntaxis:
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
In dit voorbeeld wordt de **licentie litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) verwijderd uit de gebruikersaccounts die zijn gedefinieerd in het tekstbestand C:\Mijn Documents\Accounts.txt.
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

Als u alle licenties wilt verwijderen uit alle bestaande gebruikersaccounts, gebruikt u de volgende syntaxis:
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

Een andere manier om een licentie vrij te maken is door het gebruikersaccount te verwijderen. Zie Gebruikersaccounts verwijderen [en herstellen met PowerShell voor meer informatie.](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
  
## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)