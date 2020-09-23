---
title: Microsoft 365-licenties toewijzen aan gebruikersaccounts met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: In dit artikel wordt uitgelegd hoe u PowerShell gebruikt om een Microsoft 365-licentie toe te wijzen aan gebruikers zonder licentie.
ms.openlocfilehash: f042f8109bf9ac9b634bc66509c60a5181fb1af6
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235616"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>Microsoft 365-licenties toewijzen aan gebruikersaccounts met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Gebruikers kunnen geen Microsoft 365-Services gebruiken totdat hun account een licentie aan een licentie regeling heeft toegewezen. U kunt PowerShell gebruiken om snel licenties toe te wijzen aan accounts zonder licentie. 

>[!Note]
>Voor gebruikersaccounts moet een locatie worden toegewezen. U kunt dit doen met de eigenschappen van een gebruikersaccount in het Microsoft 365-Beheercentrum of vanuit PowerShell.
>

>[!Note]
>[Meer informatie over het toewijzen van licenties aan gebruikersaccounts](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) met het microsoft 365-Beheercentrum. Zie [gebruikers en groepen beheren](https://docs.microsoft.com/microsoft-365/admin/add-users/)voor een lijst met aanvullende bronnen.
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  

Vermeld vervolgens de licentie plannen voor uw Tenant met deze opdracht.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Zorg vervolgens voor de aanmeldingsnaam van het account waaraan u een licentie wilt toevoegen, ook wel bekend als de UPN (User Principal Name).

Controleer vervolgens of aan het gebruikersaccount een gebruikslocatie is toegewezen.

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

Als er geen gebruikslocatie is toegewezen, kunt u een van de volgende opdrachten toewijzen:

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

Geef ten slotte de naam van de aanmeldingsnaam en het licentie plan van de gebruiker op en voer deze opdrachten uit.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Voer de `Get-MsolAccountSku` opdracht uit om de beschikbare licentie plannen en het aantal beschikbare licenties in elk abonnement van uw organisatie weer te geven. Het aantal beschikbare licenties in elk abonnement is **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**. Zie [licenties en services in PowerShell weergeven](view-licenses-and-services-with-microsoft-365-powershell.md)voor meer informatie over licentie plannen, licenties en services.

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

Voer deze opdracht uit om de accounts zonder licentie in uw organisatie te zoeken.

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

U kunt alleen licenties toewijzen aan gebruikersaccounts waarvan de eigenschap **UsageLocation** is ingesteld op een geldige ISO 3166-1-landcode van 2 alfanumerieke landen. Bijvoorbeeld US voor de Verenigde Staten en FR voor Frankrijk. Sommige Microsoft 365-Services zijn niet beschikbaar in bepaalde landen. Zie voor meer informatie [over licentiebeperkingen](https://go.microsoft.com/fwlink/p/?LinkId=691730).
    
Voer deze opdracht uit om te zoeken naar accounts die geen **UsageLocation** waarde hebben.

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

Voer deze opdracht uit om de **UsageLocation** waarde voor een account in te stellen.

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

Bijvoorbeeld:

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
Als u de cmdlet **Get-MsolUser** gebruikt zonder de parameter **all** te gebruiken, worden alleen de eerste 500-accounts geretourneerd.

### <a name="assigning-licenses-to-user-accounts"></a>Licenties toewijzen aan gebruikersaccounts
    
Als u een licentie wilt toewijzen aan een gebruiker, gebruikt u de volgende opdracht in PowerShell.
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

In dit voorbeeld wordt een licentie toegewezen aan het licentie plan **abonnement litwareinc: Enterprise Pack** (Office 365 Enterprise E3) voor de gebruiker zonder licentie **belindan \@ litwareinc.com**:
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Als u een licentie wilt toewijzen aan alle gebruikers zonder licentie, voert u deze opdracht uit.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>U kunt niet meerdere licenties toewijzen aan een gebruiker vanuit hetzelfde licentie plan. Als u niet over voldoende licenties beschikt, worden de licenties aan gebruikers toegewezen in de volgorde waarin ze worden geretourneerd door de cmdlet **Get-MsolUser** totdat de beschikbare licenties worden uitgevoerd.
>

In dit voorbeeld worden licenties toegewezen via het licentie plan **abonnement litwareinc: Enterprise Pack** (Office 365 Enterprise E3) voor alle gebruikers zonder licentie:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

In het volgende voorbeeld worden in de Verenigde Staten dezelfde licenties toegewezen aan gebruikers zonder licentie in de afdeling verkoop:
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Een gebruiker overzetten naar een ander abonnement (licentie plan) met de Azure Active Directory PowerShell voor Graph module

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Vervolgens haalt u de aanmeldingsnaam op van het gebruikersaccount waarvoor u wilt overstappen op een ander abonnement, ook wel de UPN (User Principal Name) genoemd.

Vervolgens vermeldt u de abonnementen (licentie abonnementen) voor uw Tenant met deze opdracht.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Vervolgens vermeldt u de abonnementen die het gebruikersaccount momenteel heeft met deze opdrachten.

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

Identificeer het abonnement dat de gebruiker heeft op dit moment (de van-abonnement) en het abonnement waarnaar de gebruiker overstapt (het naar-abonnement).

Geef ten slotte de namen en waarden voor de abonnement op (SKU-onderdeelnummers) en voer deze opdrachten uit.

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

Met deze opdrachten kunt u de wijziging in het abonnement voor het gebruikersaccount controleren.

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>Zie ook

[Gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
