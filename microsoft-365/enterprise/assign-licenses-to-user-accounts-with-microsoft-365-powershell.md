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
description: In dit artikel leert u hoe u PowerShell kunt gebruiken om een Microsoft 365-licentie toe te wijzen aan gebruikers zonder licentie.
ms.openlocfilehash: 5fb5f9095d4f732b0bf23f26eebb22eff608b48c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905462"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>Microsoft 365-licenties toewijzen aan gebruikersaccounts met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Gebruikers kunnen geen Microsoft 365-services gebruiken totdat aan hun account een licentie is toegewezen via een licentieplan. U kunt PowerShell gebruiken om snel licenties toe te wijzen aan accounts zonder licentie. 

Gebruikersaccounts moeten eerst een locatie worden toegewezen. Het opgeven van een locatie is een verplicht onderdeel van het maken van een nieuw gebruikersaccount in het [Microsoft 365-beheercentrum.](../admin/add-users/add-users.md) 

Accounts die zijn gesynchroniseerd met uw on-premises Active Directory Domain Services, hebben standaard geen locatie opgegeven. U kunt een locatie voor deze accounts configureren via:

- Het Microsoft 365-beheercentrum
 - [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
 - De [Azure-portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active**  >  **Directory-gebruikers** > gebruikersaccount >   >  **Profielgegevens**  >  **land of regio**).

>[!Note]
>[Meer informatie over het toewijzen van licenties aan gebruikersaccounts](../admin/manage/assign-licenses-to-users.md) met het Microsoft 365-beheercentrum. Zie Gebruikers en groepen beheren voor een lijst met [aanvullende bronnen.](../admin/add-users/index.yml)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De Azure Active Directory PowerShell voor Graph-module gebruiken

Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  

Vermeld vervolgens de licentieplannen voor uw tenant met deze opdracht.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Vervolgens krijgt u de aanmeldingsnaam van het account waaraan u een licentie wilt toevoegen, ook wel de gebruikersnaam (UPN) genoemd.

Controleer vervolgens of aan het gebruikersaccount een gebruikslocatie is toegewezen.

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

Als er geen gebruikslocatie is toegewezen, kunt u er een toewijzen met deze opdrachten:

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

Geef ten slotte de naam van de aanmeldings- en licentieplannaam van de gebruiker op en voer deze opdrachten uit.

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

Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Voer de opdracht uit om de beschikbare licentieplannen en het aantal beschikbare licenties in elk `Get-MsolAccountSku` abonnement in uw organisatie weer te geven. Het aantal beschikbare licenties in elk abonnement is **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**. Zie Licenties en services weergeven met [PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md)voor meer informatie over licentieplannen, licenties en services.

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

Als u de accounts zonder een vergunning in uw organisatie wilt zoeken, kunt u deze opdracht uitvoeren.

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

U kunt alleen licenties toewijzen aan gebruikersaccounts die de eigenschap **UsageLocation** hebben ingesteld op een geldige ISO 3166-1 alfa-2-landcode. Bijvoorbeeld VS voor de Verenigde Staten en FR voor Frankrijk. Sommige Microsoft 365-services zijn niet beschikbaar in bepaalde landen. Zie Over licentiebeperkingen [voor meer informatie.](https://go.microsoft.com/fwlink/p/?LinkId=691730)
    
Als u accounts wilt zoeken die geen **UsageLocation-waarde** hebben, kunt u deze opdracht uitvoeren.

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

Voer deze opdracht uit als u de **waarde UsageLocation** voor een account wilt instellen.

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

Bijvoorbeeld:

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
Als u de **get-MsolUser-cmdlet** gebruikt zonder de parameter **-All** te gebruiken, worden alleen de eerste 500 accounts geretourneerd.

### <a name="assigning-licenses-to-user-accounts"></a>Licenties toewijzen aan gebruikersaccounts
    
Als u een licentie wilt toewijzen aan een gebruiker, gebruikt u de volgende opdracht in PowerShell.
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

In dit voorbeeld wordt een licentie van het **licentieplan litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) toegewezen aan de gebruiker zonder licentie **litwareinc.com: \@**
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Voer deze opdracht uit als u een licentie wilt toewijzen aan alle gebruikers zonder licentie.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>U kunt niet meerdere licenties toewijzen aan een gebruiker via hetzelfde licentieplan. Als u niet voldoende beschikbare licenties hebt, worden de licenties toegewezen aan gebruikers in de volgorde dat ze worden geretourneerd door de **cmdlet Get-MsolUser** totdat de beschikbare licenties zijn op.
>

In dit voorbeeld worden licenties van het **licentieplan litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) toegewezen aan alle gebruikers zonder licentie:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

In dit voorbeeld worden dezelfde licenties toegewezen aan gebruikers zonder licentie op de afdeling Verkoop in de Verenigde Staten:
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Een gebruiker verplaatsen naar een ander abonnement (licentieplan) met de Azure Active Directory PowerShell voor Graph-module

Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Vervolgens krijgt u de aanmeldingsnaam van het gebruikersaccount waarvoor u van abonnement wilt veranderen, ook wel de gebruikersnaam (UPN) genoemd.

Vermeld vervolgens de abonnementen (licentieplannen) voor uw tenant met deze opdracht.

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

Bepaal het abonnement dat de gebruiker momenteel heeft (het FROM-abonnement) en het abonnement dat de gebruiker verplaatst (het TO-abonnement).

Geef ten slotte de namen van het TO- en FROM-abonnement (SKU-onderdeelnummers) op en voer deze opdrachten uit.

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

Met deze opdrachten kunt u de wijziging van het abonnement voor het gebruikersaccount verifiëren.

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>Zie ook

[Gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)