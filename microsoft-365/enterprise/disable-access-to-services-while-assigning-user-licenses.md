---
title: Toegang tot Microsoft 365-Services uitschakelen tijdens het toewijzen van gebruikerslicenties
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
description: Meer informatie over hoe u licenties toewijst aan gebruikersaccounts en specifieke serviceplannen tegelijk uitschakelen met behulp van PowerShell voor Microsoft 365.
ms.openlocfilehash: b027c805638284a78d4e49f4c65518be02e60392
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689170"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a>Toegang tot Microsoft 365-Services uitschakelen tijdens het toewijzen van gebruikerslicenties

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Microsoft 365-abonnementen worden geleverd met Serviceabonnementen voor afzonderlijke services. Beheerders van Microsoft 365 moeten vaak bepaalde abonnementen uitschakelen wanneer ze licenties toewijzen aan gebruikers. U kunt aan de hand van de instructies in dit artikel een Microsoft 365-licentie toewijzen wanneer u bepaalde serviceplannen met behulp van PowerShell voor een afzonderlijke gebruikersaccount of meerdere gebruikersaccounts uitschakelt.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell voor Graph module gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  

Vermeld vervolgens de licentie plannen voor uw Tenant met deze opdracht.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Zorg vervolgens voor de aanmeldingsnaam van het account waaraan u een licentie wilt toevoegen, ook wel bekend als de UPN (User Principal Name).

Compileer vervolgens een lijst met Services om deze in te schakelen. Voor een volledige lijst met licentie plannen (ook wel productnamen genoemd), de opgenomen serviceplannen en de bijbehorende beschrijvende namen, raadpleegt u [productnamen en serviceplan-id's voor licenties](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

Voor het onderstaande opdracht blok typt u de User Principal-naam van het gebruikersaccount, het SKU-onderdeelnummer en de lijst met serviceplannen waarmee u de verklarende tekst en de tekens kunt inschakelen en verwijderen \< and > . Voer vervolgens de uitkomstige opdrachten uit op de PowerShell-opdrachtprompt.
  
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

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken

Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Voer vervolgens de volgende opdracht uit om uw huidige abonnementen weer te geven:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

In de weergave van de  `Get-MsolAccountSku` opdracht:
  
- **AccountSkuId** is een abonnement voor uw organisatie in \<OrganizationName> : \<Subscription> indeling. De \<OrganizationName> is de waarde die u hebt opgegeven bij het registreren in Microsoft 365 en is uniek voor uw organisatie. De \<Subscription> waarde is voor een bepaald abonnement. Voor abonnement litwareinc: Enterprise Pack is de naam van de organisatie abonnement litwareinc en de naam van het abonnement Enterprise Pack (Office 365 Enterprise E3).
    
- **ActiveUnits** is het aantal licenties dat u hebt aangeschaft voor het abonnement.
    
- **WarningUnits** is het aantal licenties in een abonnement dat u nog niet hebt verlengd en dat vervalt na de periode van 30 dagen.
    
- **ConsumedUnits** is het aantal licenties dat u hebt toegewezen aan gebruikers voor het abonnement.
    
Let op de AccountSkuId voor uw Microsoft 365-abonnement met de gebruikers voor wie u een licentie wilt. Zorg er ook voor dat er voldoende licenties zijn voor het toewijzen (aftrekken van **ConsumedUnits** van **ActiveUnits** ).
  
Vervolgens voert u deze opdracht uit om de details te bekijken van de Microsoft 365-Serviceabonnementen die beschikbaar zijn in al uw abonnementen:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

Op de weergave van deze opdracht bepaalt u welke serviceplannen u wilt uitschakelen wanneer u licenties toewijst aan gebruikers.
  
Hier volgt een gedeeltelijke lijst met Serviceabonnementen en bijbehorende Microsoft 365-Services.

In de volgende tabel ziet u de Microsoft 365-serviceplannen en de beschrijvende namen voor de meest gebruikte services. Het kan zijn dat uw lijst met Serviceabonnementen verschillend is. 
  
|**Service plan**|**Beschrijving**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Beheer van Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365-apps voor Enterprise *(eerder Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype voor Bedrijven Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online Abonnement 2  <br/> |
   
Voor een volledige lijst met licentie plannen (ook wel productnamen genoemd), de opgenomen serviceplannen en de bijbehorende beschrijvende namen, raadpleegt u [productnamen en serviceplan-id's voor licenties](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).
   
Nu u de AccountSkuId en serviceplannen hebt die u wilt uitschakelen, kunt u een licentie toewijzen voor een individuele gebruiker of voor meerdere gebruikers.
  
### <a name="for-a-single-user"></a>Voor één gebruiker

Voor één gebruiker vult u de User Principal-naam van het gebruikersaccount, de AccountSkuId en de lijst met serviceplannen in om de verklarende tekst en de tekens uit te schakelen en te verwijderen \< and > . Voer vervolgens de uitkomstige opdrachten uit op de PowerShell-opdrachtprompt.
  
```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

Hier ziet u een voorbeeld van een opdracht blok voor het account met de naam belindan@contoso.com, voor de contoso: Enterprise Pack-licentie en de serviceplannen die u wilt uitschakelen, zijn RMS_S_ENTERPRISE, SWAY, INTUNE_O365 en YAMMER_ENTERPRISE:
  
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

Als u deze beheertaak voor meerdere gebruikers wilt uitvoeren, maakt u een CSV-tekstbestand met door komma's gescheiden waarden dat de velden UserPrincipalName en UsageLocation bevat. Hier ziet u een voorbeeld:
  
```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

Vul vervolgens de locatie van de CSV-bestanden voor invoer en uitvoer in, de account SKU-ID, en de lijst met serviceplannen die u wilt uitschakelen, en voer vervolgens de bijbehorende opdrachten uit op de PowerShell-opdrachtprompt.
  
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

Dit PowerShell-opdracht blok:
  
- De User Principal name van elke gebruiker weergeven.
    
- Hiermee wijst u aan elke gebruiker aangepaste licenties toe.
    
- Hiermee maakt u een CSV-bestand met alle gebruikers die zijn verwerkt en wordt hun licentiestatus weergegeven.
    
## <a name="see-also"></a>Zie ook

[Toegang tot Microsoft 365-Services met PowerShell uitschakelen](disable-access-to-services-with-microsoft-365-powershell.md)
  
[Toegang tot Sway uitschakelen met PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md)
  
[Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
