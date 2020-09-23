---
title: Microsoft 365-licenties verwijderen van gebruikersaccounts met PowerShell
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
description: In dit artikel wordt uitgelegd hoe u PowerShell gebruikt om Microsoft 365-licenties te verwijderen die eerder aan gebruikers zijn toegewezen.
ms.openlocfilehash: 7651f300dbf7a57ce163096d500401365e624663
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235452"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a>Microsoft 365-licenties verwijderen van gebruikersaccounts met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

>[!Note]
>[Informatie over het verwijderen van licenties van gebruikersaccounts](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) met het microsoft 365-Beheercentrum. Zie [gebruikers en groepen beheren](https://docs.microsoft.com/microsoft-365/admin/add-users/)voor een lijst met aanvullende bronnen.
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Vermeld vervolgens de licentie plannen voor uw Tenant met deze opdracht.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Vervolgens haalt u de aanmeldingsnaam op van het account waarvoor u een licentie wilt verwijderen, ook wel bekend als de UPN (User Principal Name).

Geef ten slotte de namen van de gebruikersaanmelding en het licentie plan op, verwijder de tekens < en > en voer deze opdrachten uit.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

Als u alle licenties voor een specifiek gebruikersaccount wilt verwijderen, geeft u de aanmeldingsnaam van de gebruiker op, verwijdert u de tekens < en > en voert u deze opdrachten uit.

```powershell
$userUPN="<user sign-in name (UPN)>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
if($userList -is [array]) {
for ($i=0; $i -lt $userList.Count; $i++) {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList[$i].SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList[$i].SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}
} else {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList.SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList.SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
   
Zie de volgende onderwerpen als u de licentie-informatie wilt weergeven voor**AccountSkuID**.
    
  - [Licenties en services weergeven met PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [Account licentie en servicedetails weergeven met PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
Als u de cmdlet **Get-MsolUser** gebruikt zonder de parameter _all_ te gebruiken, worden alleen de eerste 500-accounts geretourneerd.
    
### <a name="removing-licenses-from-user-accounts"></a>Licenties verwijderen uit gebruikersaccounts

Gebruik de volgende syntaxis om licenties van een bestaand gebruikersaccount te verwijderen:
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

In dit voorbeeld wordt de licentie **abonnement litwareinc: Enterprise Pack** (Office 365 Enterprise E3) van de gebruikersaccount BelindaN@litwareinc.com.
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
>U kunt de cmdlet niet gebruiken `Set-MsolUserLicense` voor het intrekken van gebruikers van *geannuleerde* licenties. U moet dit afzonderlijk doen voor elk gebruikersaccount in het Microsoft 365-Beheercentrum.
>

Gebruik een van de volgende methoden om alle licenties te verwijderen uit een groep bestaande gelicentieerde gebruikers:
  
- **De accounts filteren op basis van een bestaand account kenmerk** Gebruik hiervoor de volgende syntaxis:
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

In dit voorbeeld worden alle licenties van alle gebruikersaccounts in de Verenigde Staten verwijderd.
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- **Een lijst met specifieke accounts voor een bepaalde licentie gebruiken** Voer de volgende stappen uit om dit te doen:
    
1. U maakt en opslaat een tekstbestand met één account op elke regel, zoals dit:
    
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
In dit voorbeeld wordt de licentie **abonnement litwareinc: Enterprise Pack** (Office 365 Enterprise E3) verwijderd uit de gebruikersaccounts die zijn gedefinieerd in het tekstbestand c:\Mijn Documents\Accounts.txt.
    
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

Een andere manier om een licentie vrij te maken, is door het gebruikersaccount te verwijderen. Zie voor meer informatie [gebruikersaccounts verwijderen en herstellen met PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).
  
## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)

