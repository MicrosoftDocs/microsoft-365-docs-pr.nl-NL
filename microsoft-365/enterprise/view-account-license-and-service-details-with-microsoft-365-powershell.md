---
title: Microsoft 365-account licentie en servicedetails weergeven met PowerShell
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
description: In dit onderwerp wordt uitgelegd hoe u PowerShell gebruikt om te bepalen welke Microsoft 365-services aan gebruikers zijn toegewezen.
ms.openlocfilehash: 163a92ec31f700aa6157e58b49e23a1cec587815
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689541"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a>Microsoft 365-account licentie en servicedetails weergeven met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

In Microsoft 365 kunnen licenties van licentie plannen (ook wel Sku's of Microsoft 365-abonnementen genoemd) gebruikers toegang geven tot de Microsoft 365-services die zijn gedefinieerd voor die plannen. Een gebruiker heeft echter mogelijk geen toegang tot alle services die beschikbaar zijn in een licentie die momenteel aan de gebruikers is toegewezen. Met PowerShell voor Microsoft 365 kunt u de status van services op gebruikersaccounts bekijken. 

Zie [licenties en services in PowerShell weergeven](view-licenses-and-services-with-microsoft-365-powershell.md)voor meer informatie over licentie regelingen, licenties en services.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Vermeld vervolgens de licentie plannen voor uw Tenant met deze opdracht.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Met deze opdrachten kunt u een lijst weergeven met de beschikbare services in elk licentie plan.

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

Met deze opdrachten kunt u de licenties weergeven die zijn toegewezen aan een gebruikersaccount.

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Vervolgens voert u deze opdracht uit om een lijst weer te geven met licentie plannen die beschikbaar zijn in uw organisatie. 

```powershell
Get-MsolAccountSku
```
>[!Note]
>De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

Vervolgens voert u deze opdracht uit om een lijst weer te geven van de services die beschikbaar zijn in elk licentie plan, en de volgorde waarin ze worden weergegeven (het indexnummer).

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
Gebruik deze opdracht om de licenties weer te geven die aan een gebruiker zijn toegewezen, en in welke volgorde ze worden weergegeven (het indexnummer).

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a>Services voor een gebruikersaccount weergeven

Als u alle Microsoft 365-Services wilt bekijken waartoe een gebruiker toegang heeft, gebruikt u de volgende syntaxis:
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

In dit voorbeeld ziet u de services waartoe de gebruiker BelindaN@litwareinc.com toegang heeft. Hier ziet u de services die zijn gekoppeld aan alle licenties die aan haar account zijn toegewezen.
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

In het volgende voorbeeld ziet u de services waartoe de gebruiker BelindaN@litwareinc.com toegang heeft vanaf de eerste licentie die is toegewezen aan haar account (het indexnummer is 0).
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

Als u alle services wilt weergeven voor een gebruiker aan wie *meerdere licenties*zijn toegewezen, gebruikt u de volgende syntaxis:

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

[Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
