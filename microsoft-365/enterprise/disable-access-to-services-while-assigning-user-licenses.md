---
title: De toegang tot Microsoft 365 uitschakelen tijdens het toewijzen van gebruikerslicenties
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: Informatie over het toewijzen van licenties aan gebruikersaccounts en het tegelijk uitschakelen van specifieke serviceplannen met PowerShell voor Microsoft 365.
ms.openlocfilehash: ca5becb8709eeab7b5c535747ac93d36fefa0da8
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228901"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a>De toegang tot Microsoft 365 uitschakelen tijdens het toewijzen van gebruikerslicenties

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Microsoft 365 abonnementen worden aangeboden met serviceabonnementen voor afzonderlijke services. Microsoft 365 beheerders moeten vaak bepaalde abonnementen uitschakelen bij het toewijzen van licenties aan gebruikers. Met de instructies in dit artikel kunt u een Microsoft 365 toewijzen terwijl u specifieke serviceplannen uitwijst met PowerShell voor een afzonderlijk gebruikersaccount of meerdere gebruikersaccounts.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>De powershell Azure Active Directory powershell gebruiken voor Graph module

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)


Vermeld vervolgens de licentieplannen voor uw tenant met deze opdracht.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Vervolgens krijgt u de aanmeldingsnaam van het account waaraan u een licentie wilt toevoegen, ook wel de gebruikersnaam (UPN) genoemd.

Stel vervolgens een lijst met services samen die u wilt inschakelen. Zie Productnamen en [serviceplanaanduidingen](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)voor licenties voor een volledige lijst met licentieplannen (ook wel productnamen genoemd), de bijbehorende serviceplannen en de bijbehorende vriendelijke namen.

Vul voor het onderstaande opdrachtblok de gebruikersnaam van het gebruikersaccount, het SKU-onderdeelnummer en de lijst met serviceplannen in om de verklarende tekst en de tekens in te stellen en \< and > te verwijderen. Voer vervolgens de resulterende opdrachten uit op de opdrachtprompt van PowerShell.

```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell

Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Voer vervolgens deze opdracht uit om uw huidige abonnementen te bekijken:

```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

In de weergave van de  `Get-MsolAccountSku` opdracht:

- **AccountSkuId** is een abonnement voor uw organisatie in \<OrganizationName> : \<Subscription> indeling. Dit \<OrganizationName> is de waarde die u hebt opgegeven bij het Microsoft 365 en is uniek voor uw organisatie. De \<Subscription> waarde is voor een specifiek abonnement. Voor litwareinc:ENTERPRISEPACK is de naam van de organisatie bijvoorbeeld litwareinc en is de abonnementsnaam ENTERPRISEPACK (Office 365 Enterprise E3).

- **ActiveUnits** is het aantal licenties dat u voor het abonnement hebt gekocht.

- **WarningUnits** is het aantal licenties in een abonnement dat u niet hebt verlengd en dat na de respijtperiode van 30 dagen verloopt.

- **ConsumedUnits** is het aantal licenties dat u hebt toegewezen aan gebruikers voor het abonnement.

Let op accountSkuId voor uw Microsoft 365 die de gebruikers bevat die u wilt gebruiken. Zorg er ook voor dat er voldoende licenties zijn om toe te wijzen **(consumedUnits aftrekken** van **ActiveUnits).**

Voer vervolgens deze opdracht uit om de details te zien van de Microsoft 365 serviceabonnementen die beschikbaar zijn in al uw abonnementen:

```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

Bepaal in de weergave van deze opdracht welke serviceplannen u wilt uitschakelen wanneer u licenties toewijst aan gebruikers.

Hier is een gedeeltelijke lijst met serviceplannen en de bijbehorende Microsoft 365 services.

In de volgende tabel ziet u Microsoft 365 serviceplannen en hun vriendelijke namen voor de meest voorkomende services. Uw lijst met serviceplannen kan anders zijn.

|**Serviceplan**|**Beschrijving**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365-apps voor ondernemingen *(eerder benoemd Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype voor Bedrijven Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online Abonnement 2  <br/> |

Zie Productnamen en [serviceplanaanduidingen](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)voor licenties voor een volledige lijst met licentieplannen (ook wel productnamen genoemd), de bijbehorende serviceplannen en de bijbehorende vriendelijke namen.

Nu u de AccountSkuId en de serviceplannen wilt uitschakelen, kunt u licenties toewijzen voor een individuele gebruiker of voor meerdere gebruikers.

### <a name="for-a-single-user"></a>Voor één gebruiker

Vul voor één gebruiker de gebruikersnaam in van het gebruikersaccount, de AccountSkuId en de lijst met serviceplannen om de verklarende tekst en de tekens uit te schakelen en \< and > te verwijderen. Voer vervolgens de resulterende opdrachten uit op de opdrachtprompt van PowerShell.

```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

Hier is een voorbeeldopdrachtblok voor het account met de naam belindan@contoso.com, voor de licentie contoso:ENTERPRISEPACK en de serviceplannen die u wilt uitschakelen, zijn RMS_S_ENTERPRISE, SWAY, INTUNE_O365 en YAMMER_ENTERPRISE:

```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a>Voor meerdere gebruikers

Als u deze beheertaak voor meerdere gebruikers wilt uitvoeren, maakt u een door komma's gescheiden tekstbestand (CSV) dat de velden UserPrincipalName en UsageLocation bevat. Hier is een voorbeeld:

```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

Vul vervolgens de locatie in van de INVOER- en uitvoer-CSV-bestanden, de account-SKU-id en de lijst met serviceplannen die u wilt uitschakelen en voer de resulterende opdrachten uit op de opdrachtprompt van PowerShell.

```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

Dit PowerShell-opdrachtblok:

- Hiermee wordt de gebruikersnaam van elke gebruiker weergegeven.

- Wijs aangepaste licenties toe aan elke gebruiker.

- Hiermee maakt u een CSV-bestand met alle gebruikers die zijn verwerkt en wordt hun licentiestatus weergeven.

## <a name="see-also"></a>Zie ook

[Toegang tot Microsoft 365-services uitschakelen met PowerShell](disable-access-to-services-with-microsoft-365-powershell.md)

[Toegang tot Sway uitschakelen met PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md)

[Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)