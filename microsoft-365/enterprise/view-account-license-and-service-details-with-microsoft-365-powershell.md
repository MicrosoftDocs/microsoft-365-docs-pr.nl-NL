---
title: De Microsoft 365 en servicegegevens van uw account weergeven met PowerShell
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
- LIL_Placement
ms.assetid: ace07d8a-15ca-4b89-87f0-abbce809b519
description: Hier wordt uitgelegd hoe u PowerShell gebruikt om te bepalen Microsoft 365 services die aan gebruikers zijn toegewezen.
ms.openlocfilehash: 163a92ec31f700aa6157e58b49e23a1cec587815
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689541"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a>De Microsoft 365 en servicegegevens van uw account weergeven met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

In Microsoft 365 geven licenties van licentieplannen (ook wel SKU's of Microsoft 365-abonnementen genoemd) gebruikers toegang tot de Microsoft 365-services die voor deze abonnementen zijn gedefinieerd. Een gebruiker heeft mogelijk echter geen toegang tot alle services die beschikbaar zijn in een licentie die momenteel aan hen is toegewezen. U kunt PowerShell gebruiken voor Microsoft 365 om de status van services op gebruikersaccounts te bekijken. 

Zie Licenties en services weergeven met PowerShell voor meer informatie over licentieplannen, licenties en [services.](view-licenses-and-services-with-microsoft-365-powershell.md)

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De powershell Azure Active Directory powershell gebruiken voor Graph module

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Vermeld vervolgens de licentieplannen voor uw tenant met deze opdracht.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Gebruik deze opdrachten om de services weer te geven die beschikbaar zijn in elk licentieplan.

```powershell
$allSKUs=Get-AzureADSubscribedSku
$licArray = @()
for($i = 0; $i -lt $allSKUs.Count; $i++)
{
$licArray += "Service Plan: " + $allSKUs[$i].SkuPartNumber
$licArray +=  Get-AzureADSubscribedSku -ObjectID $allSKUs[$i].ObjectID | Select -ExpandProperty ServicePlans
$licArray +=  ""
}
$licArray
```

Gebruik deze opdrachten om de licenties weer te geven die aan een gebruikersaccount zijn toegewezen.

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Voer vervolgens deze opdracht uit om de licentieplannen weer te geven die beschikbaar zijn in uw organisatie. 

```powershell
Get-MsolAccountSku
```
>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

Voer vervolgens deze opdracht uit om de services weer te geven die beschikbaar zijn in elk licentieplan en de volgorde waarin ze worden vermeld (het indexnummer).

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
Gebruik deze opdracht om de licenties op te geven die aan een gebruiker zijn toegewezen en de volgorde waarin deze worden vermeld (het indexnummer).

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a>Services voor een gebruikersaccount weergeven

Gebruik de volgende syntaxis om alle Microsoft 365 services weer te geven die een gebruiker heeft:
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

In dit voorbeeld ziet u de services waarop de gebruiker BelindaN@litwareinc.com toegang heeft. Hier ziet u de services die zijn gekoppeld aan alle licenties die aan haar account zijn toegewezen.
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

In dit voorbeeld ziet u de services BelindaN@litwareinc.com gebruikerstoegang hebben vanaf de eerste licentie die aan haar account is toegewezen (het indexnummer is 0).
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

Als u alle services wilt weergeven voor een gebruiker die meerdere licenties *heeft* gekregen, gebruikt u de volgende syntaxis:

```powershell
$userUPN="<user account UPN>"
$AllLicenses=(Get-MsolUser -UserPrincipalName $userUPN).Licenses
$licArray = @()
for($i = 0; $i -lt $AllLicenses.Count; $i++)
{
$licArray += "License: " + $AllLicenses[$i].AccountSkuId
$licArray +=  $AllLicenses[$i].ServiceStatus
$licArray +=  ""
}
$licArray
```
 
## <a name="see-also"></a>Zie ook

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
