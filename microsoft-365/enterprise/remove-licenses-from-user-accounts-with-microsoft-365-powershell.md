---
title: Microsoft 365-licenties verwijderen uit gebruikersaccounts met PowerShell
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
description: In dit artikel wordt uitgelegd hoe u PowerShell kunt gebruiken om Microsoft 365-licenties te verwijderen die eerder zijn toegewezen aan gebruikers.
ms.openlocfilehash: 8ae7ca1013e26a60f16177f2dab7ced4cc8b97a8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289591"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a>Microsoft 365-licenties verwijderen uit gebruikersaccounts met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

>[!Note]
>[Lees hoe u licenties verwijdert uit gebruikersaccounts](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) met het Microsoft 365-beheercentrum. Zie Gebruikers en groepen beheren voor een lijst [met aanvullende bronnen.](https://docs.microsoft.com/microsoft-365/admin/add-users/)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De Azure Active Directory PowerShell for Graph-module gebruiken

Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

Vermeld vervolgens de licentieplannen voor uw tenant met deze opdracht.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Zoek vervolgens de aanmeldingsnaam van het account waarvoor u een licentie wilt verwijderen, ook wel de UPN (User Principal Name) genoemd.

Geef ten slotte de namen van gebruikersaccounts en licenties op, verwijder de tekens '<' en '>' en voer deze opdrachten uit.

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

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
   
Zie de volgende onderwerpen als u de informatie over het licentieplan **(AccountSkuID)** in uw organisatie wilt bekijken:
    
  - [Licenties en services weergeven met PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [Accountlicentie- en servicedetails weergeven met PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
Als u de **get-MsolUser-cmdlet** gebruikt zonder de parameter _-All_ te gebruiken, worden alleen de eerste 500 accounts geretourneerd.
    
### <a name="removing-licenses-from-user-accounts"></a>Licenties verwijderen uit gebruikersaccounts

Gebruik de volgende syntaxis om licenties te verwijderen uit een bestaand gebruikersaccount:
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

In dit voorbeeld wordt de **licentie litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) verwijderd uit de licentie voor BelindaN@litwareinc.com.
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
>U kunt de `Set-MsolUserLicense` cmdlet niet gebruiken om de licentie voor gebruikers *van geannuleerde licenties in* te verwijderen. U moet dit afzonderlijk doen voor elk gebruikersaccount in het Microsoft 365-beheercentrum.
>

Als u alle licenties wilt verwijderen van een groep bestaande gebruikers met een licentie, gebruikt u een van de volgende methoden:
  
- **De accounts filteren op basis van een bestaand accountkenmerk** Gebruik hiervoor de volgende syntaxis:
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

In dit voorbeeld worden alle licenties verwijderd van alle gebruikersaccounts in de afdeling Verkoop in de Verenigde Staten.
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- **Een lijst met specifieke accounts gebruiken voor een specifieke licentie** Voer hiervoor de volgende stappen uit:
    
1. Maak en sla op elke regel een tekstbestand op dat één account bevat:
    
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
In dit voorbeeld wordt de **licentie litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) verwijderd uit de gebruikersaccounts die zijn gedefinieerd in het tekstbestand C:\My Documents\Accounts.txt.
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

Als u alle licenties van alle bestaande gebruikersaccounts wilt verwijderen, gebruikt u de volgende syntaxis:
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

Een andere manier om een licentie vrij te maken, is door het gebruikersaccount te verwijderen. Zie Gebruikersaccounts verwijderen en herstellen met [PowerShell voor meer informatie.](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
  
## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)

