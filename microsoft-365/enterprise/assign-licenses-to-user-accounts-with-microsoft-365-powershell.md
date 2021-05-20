---
title: Licenties voor Microsoft 365 toewijzen aan gebruikersaccounts met PowerShell
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
description: In dit artikel leert u hoe u PowerShell kunt gebruiken om een Microsoft 365 licentie toe te wijzen aan gebruikers zonder licentie.
ms.openlocfilehash: 6d7e005aff018394810082de57c68ea289057f8e
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572619"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>Licenties voor Microsoft 365 toewijzen aan gebruikersaccounts met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Gebruikers kunnen geen Microsoft 365 services gebruiken totdat aan hun account een licentie van een licentieplan is toegewezen. U kunt PowerShell gebruiken om snel licenties toe te wijzen aan accounts zonder licentie. 

Aan gebruikersaccounts moet eerst een locatie worden toegewezen. Het opgeven van een locatie is een vereist onderdeel van het maken van een nieuw gebruikersaccount in het [Microsoft 365-beheercentrum](../admin/add-users/add-users.md). 

Accounts die zijn gesynchroniseerd vanuit uw on-premises Active Directory Domain Services, hebben niet standaard een locatie opgegeven. U kunt een locatie voor deze accounts configureren vanuit:

- Het Microsoft 365-beheercentrum
 - [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
 - De [Azure Portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) ( Active  >  **Directory-gebruikers** > gebruikersaccount > **profiel**  >  **contactgegevens**  >  **land of regio**).

>[!Note]
>[Meer informatie over het toewijzen van licenties aan gebruikersaccounts](../admin/manage/assign-licenses-to-users.md) met het Microsoft 365-beheercentrum. Zie Gebruikers en groepen beheren voor een lijst met extra [resources.](../admin/add-users/index.yml)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De powershell voor Graph Azure Active Directory gebruiken

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  

Vermeld vervolgens de licentie plannen voor uw Tenant met deze opdracht.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Voer vervolgens de aanmeldings naam op van het account waaraan u een licentie wilt toevoegen, ook wel de upn (user principal name) genoemd.

Zorg er vervolgens voor dat aan het gebruikersaccount een gebruikslocatie is toegewezen.

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

Als er geen gebruikslocatie is toegewezen, kunt u er een toewijzen met de volgende opdrachten:

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

Geef ten slotte de aanmeldings naam van de gebruiker en de naam van het licentie plan op en voer deze opdrachten uit.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell

Houd er rekening mee dat we deze module beginnen af te keuren wanneer de functionaliteit van deze module beschikbaar is in de nieuwere [Azure Active Directory PowerShell voor Graph](/powershell/azuread/v2/azureactivedirectory) module. We adviseren klanten die nieuwe PowerShell-scripts maken om de nieuwere module te gebruiken in plaats van deze module.

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Voer de opdracht uit `Get-MsolAccountSku` om de beschikbare licentieplannen en het aantal beschikbare licenties in elk plan in uw organisatie weer te geven. Het aantal beschikbare licenties in elk abonnement is **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**. Zie Licenties en [services weergeven met PowerShell voor](view-licenses-and-services-with-microsoft-365-powershell.md)meer informatie over licentieplannen, licenties en services.

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

Voer deze opdracht uit om de accounts zonder vergunning in uw organisatie te vinden.

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

U kunt alleen licenties toewijzen aan gebruikersaccounts waarop de eigenschap **UsageLocation** is ingesteld op een geldige ISO 3166-1 alfa-2-landcode. Bijvoorbeeld de VS voor de Verenigde Staten en FR voor Frankrijk. Sommige Microsoft 365 services zijn niet beschikbaar in bepaalde landen. Zie [Over licentiebeperkingen](https://go.microsoft.com/fwlink/p/?LinkId=691730)voor meer informatie.
    
Voer deze opdracht uit om accounts te vinden die geen **UsageLocation-waarde** hebben.

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

Voer deze opdracht uit om de waarde **UsageLocation** voor een account in te stellen.

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

Bijvoorbeeld:

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
Als u de **cmdlet Get-MsolUser** gebruikt zonder de parameter **-All** te gebruiken, worden alleen de eerste 500 accounts geretourneerd.

### <a name="assigning-licenses-to-user-accounts"></a>Licenties toewijzen aan gebruikersaccounts
    
Als u een licentie aan een gebruiker wilt toewijzen, gebruikt u de volgende opdracht in PowerShell.
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

In het volgende voorbeeld wordt een licentie van het **litwareinc:ENTERPRISEPACK(Office 365 Enterprise** E3)-licentieplan toegewezen aan de gebruiker zonder licentie **\@ litwareinc.com**:
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Voer deze opdracht uit om een licentie toe te wijzen aan alle gebruikers zonder licentie.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>U kunt niet meerdere licenties toewijzen aan een gebruiker vanuit hetzelfde licentieplan. Als u niet over voldoende beschikbare licenties beschikt, worden de licenties toegewezen aan gebruikers in de volgorde waarin ze worden geretourneerd door de **Cmdlet Get-MsolUser** totdat de beschikbare licenties op zijn.
>

In het volgende voorbeeld worden licenties van het licentieplan **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) toegewezen aan alle gebruikers zonder licentie:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

In het volgende voorbeeld worden dezelfde licenties toegewezen aan gebruikers zonder licentie op de afdeling Verkoop in de Verenigde Staten:
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Een gebruiker verplaatsen naar een ander abonnement (licentieabonnement) met de Azure Active Directory PowerShell voor Graph module

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Voer vervolgens de aanmeldings naam op van het gebruikers account waarvoor u wilt switch abonnementen, ook wel de upn (user principal name) genoemd.

Vermeld vervolgens de abonnementen (licentie abonnementen) voor uw Tenant met deze opdracht.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Vermeld vervolgens de abonnementen die het gebruikersaccount momenteel heeft met deze opdrachten.

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

Identificeer het abonnement dat de gebruiker momenteel heeft (het FROM-abonnement) en het abonnement waarnaar de gebruiker verhuist (het TO-abonnement).

Geef ten slotte de TO- en FROM-abonnementsnamen (SKU-onderdeelnummers) op en voer deze opdrachten uit.

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

Met deze opdrachten kunt u de wijziging in het abonnement voor het gebruikersaccount verifiëren.

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>Zie ook

[Gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
