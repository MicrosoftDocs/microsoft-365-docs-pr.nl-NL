---
title: Toegang tot Microsoft 365-services uitschakelen tijdens het toewijzen van gebruikerslicenties
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
description: Meer informatie over het toewijzen van licenties aan gebruikersaccounts en het tegelijk uitschakelen van specifieke serviceplannen met PowerShell voor Microsoft 365.
ms.openlocfilehash: 7486968f6f4822047a1697ee1e05129277fd11a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929430"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a><span data-ttu-id="06a3c-103">Toegang tot Microsoft 365-services uitschakelen tijdens het toewijzen van gebruikerslicenties</span><span class="sxs-lookup"><span data-stu-id="06a3c-103">Disable access to Microsoft 365 services while assigning user licenses</span></span>

<span data-ttu-id="06a3c-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="06a3c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="06a3c-105">Microsoft 365-abonnementen worden aangeboden met serviceabonnementen voor afzonderlijke services.</span><span class="sxs-lookup"><span data-stu-id="06a3c-105">Microsoft 365 subscriptions come with service plans for individual services.</span></span> <span data-ttu-id="06a3c-106">Microsoft 365-beheerders moeten vaak bepaalde abonnementen uitschakelen bij het toewijzen van licenties aan gebruikers.</span><span class="sxs-lookup"><span data-stu-id="06a3c-106">Microsoft 365 administrators often need to disable certain plans when assigning licenses to users.</span></span> <span data-ttu-id="06a3c-107">Met de instructies in dit artikel kunt u een Microsoft 365-licentie toewijzen terwijl u specifieke serviceplannen uitwijst met PowerShell voor een afzonderlijk gebruikersaccount of meerdere gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="06a3c-107">With the instructions in this article, you can assign a Microsoft 365 license while disabling specific service plans using PowerShell for an individual user account or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="06a3c-108">De Azure Active Directory PowerShell voor Graph-module gebruiken</span><span class="sxs-lookup"><span data-stu-id="06a3c-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="06a3c-109">Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="06a3c-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="06a3c-110">Vermeld vervolgens de licentieplannen voor uw tenant met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="06a3c-110">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="06a3c-111">Vervolgens krijgt u de aanmeldingsnaam van het account waaraan u een licentie wilt toevoegen, ook wel de gebruikersnaam (UPN) genoemd.</span><span class="sxs-lookup"><span data-stu-id="06a3c-111">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="06a3c-112">Stel vervolgens een lijst met services samen die u wilt inschakelen.</span><span class="sxs-lookup"><span data-stu-id="06a3c-112">Next, compile a list of services to enable.</span></span> <span data-ttu-id="06a3c-113">Zie Productnamen en [serviceplanaanduidingen](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)voor licenties voor een volledige lijst met licentieplannen (ook wel productnamen genoemd), de bijbehorende serviceplannen en de bijbehorende vriendelijke namen.</span><span class="sxs-lookup"><span data-stu-id="06a3c-113">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="06a3c-114">Vul voor het onderstaande opdrachtblok de gebruikersnaam van het gebruikersaccount, het SKU-onderdeelnummer en de lijst met serviceplannen in om de verklarende tekst en de tekens in te stellen en \< and > te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="06a3c-114">For the command block below, fill in the user principal name of the user account, the SKU part number, and the list of service plans to enable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="06a3c-115">Voer vervolgens de resulterende opdrachten uit op de opdrachtprompt van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06a3c-115">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
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

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="06a3c-116">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="06a3c-116">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="06a3c-117">Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="06a3c-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="06a3c-118">Voer vervolgens deze opdracht uit om uw huidige abonnementen te bekijken:</span><span class="sxs-lookup"><span data-stu-id="06a3c-118">Next, run this command to see your current subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="06a3c-119">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="06a3c-119">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="06a3c-120">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06a3c-120">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="06a3c-121">In de weergave van de  `Get-MsolAccountSku` opdracht:</span><span class="sxs-lookup"><span data-stu-id="06a3c-121">In the display of the  `Get-MsolAccountSku` command:</span></span>
  
- <span data-ttu-id="06a3c-122">**AccountSkuId** is een abonnement voor uw organisatie in \<OrganizationName> : \<Subscription> indeling.</span><span class="sxs-lookup"><span data-stu-id="06a3c-122">**AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format.</span></span> <span data-ttu-id="06a3c-123">Dit is de waarde die u hebt opgegeven toen u zich in Microsoft 365 hebt geregistreerd \<OrganizationName> en uniek is voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="06a3c-123">The \<OrganizationName> is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="06a3c-124">De \<Subscription> waarde is voor een specifiek abonnement.</span><span class="sxs-lookup"><span data-stu-id="06a3c-124">The \<Subscription> value is for a specific subscription.</span></span> <span data-ttu-id="06a3c-125">Voor litwareinc:ENTERPRISEPACK is de naam van de organisatie bijvoorbeeld litwareinc en is de abonnementsnaam ENTERPRISEPACK (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="06a3c-125">For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).</span></span>
    
- <span data-ttu-id="06a3c-126">**ActiveUnits** is het aantal licenties dat u voor het abonnement hebt gekocht.</span><span class="sxs-lookup"><span data-stu-id="06a3c-126">**ActiveUnits** is the number of licenses that you've purchased for the subscription.</span></span>
    
- <span data-ttu-id="06a3c-127">**WarningUnits** is het aantal licenties in een abonnement dat u niet hebt verlengd en dat na de respijtperiode van 30 dagen verloopt.</span><span class="sxs-lookup"><span data-stu-id="06a3c-127">**WarningUnits** is the number of licenses in a subscription that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="06a3c-128">**ConsumedUnits** is het aantal licenties dat u hebt toegewezen aan gebruikers voor het abonnement.</span><span class="sxs-lookup"><span data-stu-id="06a3c-128">**ConsumedUnits** is the number of licenses that you've assigned to users for the subscription.</span></span>
    
<span data-ttu-id="06a3c-129">Let op de AccountSkuId voor uw Microsoft 365-abonnement met de gebruikers die u een licentie wilt geven.</span><span class="sxs-lookup"><span data-stu-id="06a3c-129">Note the AccountSkuId for your Microsoft 365 subscription that contains the users you want to license.</span></span> <span data-ttu-id="06a3c-130">Zorg er ook voor dat er voldoende licenties zijn om toe te wijzen **(consumedUnits aftrekken** van **ActiveUnits).**</span><span class="sxs-lookup"><span data-stu-id="06a3c-130">Also, ensure that there are enough licenses to assign (subtract **ConsumedUnits** from **ActiveUnits** ).</span></span>
  
<span data-ttu-id="06a3c-131">Voer vervolgens deze opdracht uit om de details te zien van de Microsoft 365-serviceabonnementen die beschikbaar zijn in al uw abonnementen:</span><span class="sxs-lookup"><span data-stu-id="06a3c-131">Next, run this command to see the details about the Microsoft 365 service plans that are available in all your subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="06a3c-132">Bepaal in de weergave van deze opdracht welke serviceplannen u wilt uitschakelen wanneer u licenties toewijst aan gebruikers.</span><span class="sxs-lookup"><span data-stu-id="06a3c-132">From the display of this command, determine which service plans you would like to disable when you assign licenses to users.</span></span>
  
<span data-ttu-id="06a3c-133">Hier is een gedeeltelijke lijst met serviceplannen en de bijbehorende Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="06a3c-133">Here is a partial list of service plans and their corresponding Microsoft 365 services.</span></span>

<span data-ttu-id="06a3c-134">In de volgende tabel ziet u de Microsoft 365-serviceplannen en hun vriendelijke namen voor de meest voorkomende services.</span><span class="sxs-lookup"><span data-stu-id="06a3c-134">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="06a3c-135">Uw lijst met serviceplannen kan anders zijn.</span><span class="sxs-lookup"><span data-stu-id="06a3c-135">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="06a3c-136">**Serviceplan**</span><span class="sxs-lookup"><span data-stu-id="06a3c-136">**Service plan**</span></span>|<span data-ttu-id="06a3c-137">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="06a3c-137">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="06a3c-138">Sway</span><span class="sxs-lookup"><span data-stu-id="06a3c-138">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="06a3c-139">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06a3c-139">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="06a3c-140">Yammer</span><span class="sxs-lookup"><span data-stu-id="06a3c-140">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="06a3c-141">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="06a3c-141">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="06a3c-142">Microsoft 365 Apps voor ondernemingen *(voorheen Office 365 ProPlus genoemd)*</span><span class="sxs-lookup"><span data-stu-id="06a3c-142">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="06a3c-143">Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="06a3c-143">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="06a3c-144">Office</span><span class="sxs-lookup"><span data-stu-id="06a3c-144">Office</span></span>   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="06a3c-145">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="06a3c-145">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="06a3c-146">Exchange Online Abonnement 2</span><span class="sxs-lookup"><span data-stu-id="06a3c-146">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="06a3c-147">Zie Productnamen en [serviceplanaanduidingen](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)voor licenties voor een volledige lijst met licentieplannen (ook wel productnamen genoemd), de bijbehorende serviceplannen en de bijbehorende vriendelijke namen.</span><span class="sxs-lookup"><span data-stu-id="06a3c-147">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>
   
<span data-ttu-id="06a3c-148">Nu u de AccountSkuId en de serviceplannen wilt uitschakelen, kunt u licenties toewijzen voor een individuele gebruiker of voor meerdere gebruikers.</span><span class="sxs-lookup"><span data-stu-id="06a3c-148">Now that you have the AccountSkuId and the service plans to disable, you can assign licenses for an individual user or for multiple users.</span></span>
  
### <a name="for-a-single-user"></a><span data-ttu-id="06a3c-149">Voor één gebruiker</span><span class="sxs-lookup"><span data-stu-id="06a3c-149">For a single user</span></span>

<span data-ttu-id="06a3c-150">Vul voor één gebruiker de gebruikersnaam in van het gebruikersaccount, de AccountSkuId en de lijst met serviceplannen om de verklarende tekst en de tekens uit te schakelen en \< and > te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="06a3c-150">For a single user, fill in the user principal name of the user account, the AccountSkuId, and the list of service plans to disable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="06a3c-151">Voer vervolgens de resulterende opdrachten uit op de opdrachtprompt van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06a3c-151">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

<span data-ttu-id="06a3c-152">Hier is een voorbeeldopdrachtblok voor het account met de naam belindan@contoso.com, voor de licentie contoso:ENTERPRISEPACK en de serviceplannen die u wilt uitschakelen, zijn RMS_S_ENTERPRISE, SWAY, INTUNE_O365 en YAMMER_ENTERPRISE:</span><span class="sxs-lookup"><span data-stu-id="06a3c-152">Here is an example command block for the account named belindan@contoso.com, for the contoso:ENTERPRISEPACK license, and the service plans to disable are RMS_S_ENTERPRISE, SWAY, INTUNE_O365, and YAMMER_ENTERPRISE:</span></span>
  
```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a><span data-ttu-id="06a3c-153">Voor meerdere gebruikers</span><span class="sxs-lookup"><span data-stu-id="06a3c-153">For multiple users</span></span>

<span data-ttu-id="06a3c-154">Als u deze beheertaak voor meerdere gebruikers wilt uitvoeren, maakt u een door komma's gescheiden tekstbestand (CSV) dat de velden UserPrincipalName en UsageLocation bevat.</span><span class="sxs-lookup"><span data-stu-id="06a3c-154">To perform this administration task for multiple users, create a comma-separated value (CSV) text file that contains the UserPrincipalName and UsageLocation fields.</span></span> <span data-ttu-id="06a3c-155">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="06a3c-155">Here is an example:</span></span>
  
```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

<span data-ttu-id="06a3c-156">Vul vervolgens de locatie in van de INVOER- en uitvoer-CSV-bestanden, de account-SKU-id en de lijst met serviceplannen die u wilt uitschakelen en voer de resulterende opdrachten uit op de opdrachtprompt van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06a3c-156">Next, fill in the location of the input and output CSV files, the account SKU ID, and the list of service plans to disable, and then run the resulting commands at the PowerShell command prompt.</span></span>
  
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

<span data-ttu-id="06a3c-157">Dit PowerShell-opdrachtblok:</span><span class="sxs-lookup"><span data-stu-id="06a3c-157">This PowerShell command block:</span></span>
  
- <span data-ttu-id="06a3c-158">Hiermee wordt de gebruikersnaam van elke gebruiker weergegeven.</span><span class="sxs-lookup"><span data-stu-id="06a3c-158">Displays the user principal name of each user.</span></span>
    
- <span data-ttu-id="06a3c-159">Wijs aangepaste licenties toe aan elke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="06a3c-159">Assigns customized licenses to each user.</span></span>
    
- <span data-ttu-id="06a3c-160">Hiermee maakt u een CSV-bestand met alle gebruikers die zijn verwerkt en wordt hun licentiestatus weergeven.</span><span class="sxs-lookup"><span data-stu-id="06a3c-160">Creates a CSV file with all the users that were processed and shows their license status.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="06a3c-161">Zie ook</span><span class="sxs-lookup"><span data-stu-id="06a3c-161">See also</span></span>

[<span data-ttu-id="06a3c-162">Toegang tot Microsoft 365-services uitschakelen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="06a3c-162">Disable access to Microsoft 365 services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="06a3c-163">Toegang tot Sway uitschakelen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="06a3c-163">Disable access to Sway with PowerShell</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="06a3c-164">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="06a3c-164">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="06a3c-165">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="06a3c-165">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)