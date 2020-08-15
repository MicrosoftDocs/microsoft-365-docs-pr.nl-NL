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
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a><span data-ttu-id="663f0-103">Toegang tot Microsoft 365-Services uitschakelen tijdens het toewijzen van gebruikerslicenties</span><span class="sxs-lookup"><span data-stu-id="663f0-103">Disable access to Microsoft 365 services while assigning user licenses</span></span>

<span data-ttu-id="663f0-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="663f0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="663f0-105">Microsoft 365-abonnementen worden geleverd met Serviceabonnementen voor afzonderlijke services.</span><span class="sxs-lookup"><span data-stu-id="663f0-105">Microsoft 365 subscriptions come with service plans for individual services.</span></span> <span data-ttu-id="663f0-106">Beheerders van Microsoft 365 moeten vaak bepaalde abonnementen uitschakelen wanneer ze licenties toewijzen aan gebruikers.</span><span class="sxs-lookup"><span data-stu-id="663f0-106">Microsoft 365 administrators often need to disable certain plans when assigning licenses to users.</span></span> <span data-ttu-id="663f0-107">U kunt aan de hand van de instructies in dit artikel een Microsoft 365-licentie toewijzen wanneer u bepaalde serviceplannen met behulp van PowerShell voor een afzonderlijke gebruikersaccount of meerdere gebruikersaccounts uitschakelt.</span><span class="sxs-lookup"><span data-stu-id="663f0-107">With the instructions in this article, you can assign a Microsoft 365 license while disabling specific service plans using PowerShell for an individual user account or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="663f0-108">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="663f0-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="663f0-109">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="663f0-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="663f0-110">Vermeld vervolgens de licentie plannen voor uw Tenant met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="663f0-110">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="663f0-111">Zorg vervolgens voor de aanmeldingsnaam van het account waaraan u een licentie wilt toevoegen, ook wel bekend als de UPN (User Principal Name).</span><span class="sxs-lookup"><span data-stu-id="663f0-111">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="663f0-112">Compileer vervolgens een lijst met Services om deze in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="663f0-112">Next, compile a list of services to enable.</span></span> <span data-ttu-id="663f0-113">Voor een volledige lijst met licentie plannen (ook wel productnamen genoemd), de opgenomen serviceplannen en de bijbehorende beschrijvende namen, raadpleegt u [productnamen en serviceplan-id's voor licenties](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="663f0-113">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="663f0-114">Voor het onderstaande opdracht blok typt u de User Principal-naam van het gebruikersaccount, het SKU-onderdeelnummer en de lijst met serviceplannen waarmee u de verklarende tekst en de tekens kunt inschakelen en verwijderen \< and > .</span><span class="sxs-lookup"><span data-stu-id="663f0-114">For the command block below, fill in the user principal name of the user account, the SKU part number, and the list of service plans to enable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="663f0-115">Voer vervolgens de uitkomstige opdrachten uit op de PowerShell-opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="663f0-115">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
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

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="663f0-116">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="663f0-116">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="663f0-117">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="663f0-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="663f0-118">Voer vervolgens de volgende opdracht uit om uw huidige abonnementen weer te geven:</span><span class="sxs-lookup"><span data-stu-id="663f0-118">Next, run this command to see your current subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="663f0-119">De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam.</span><span class="sxs-lookup"><span data-stu-id="663f0-119">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="663f0-120">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="663f0-120">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="663f0-121">In de weergave van de  `Get-MsolAccountSku` opdracht:</span><span class="sxs-lookup"><span data-stu-id="663f0-121">In the display of the  `Get-MsolAccountSku` command:</span></span>
  
- <span data-ttu-id="663f0-122">**AccountSkuId** is een abonnement voor uw organisatie in \<OrganizationName> : \<Subscription> indeling.</span><span class="sxs-lookup"><span data-stu-id="663f0-122">**AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format.</span></span> <span data-ttu-id="663f0-123">De \<OrganizationName> is de waarde die u hebt opgegeven bij het registreren in Microsoft 365 en is uniek voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="663f0-123">The \<OrganizationName> is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="663f0-124">De \<Subscription> waarde is voor een bepaald abonnement.</span><span class="sxs-lookup"><span data-stu-id="663f0-124">The \<Subscription> value is for a specific subscription.</span></span> <span data-ttu-id="663f0-125">Voor abonnement litwareinc: Enterprise Pack is de naam van de organisatie abonnement litwareinc en de naam van het abonnement Enterprise Pack (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="663f0-125">For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).</span></span>
    
- <span data-ttu-id="663f0-126">**ActiveUnits** is het aantal licenties dat u hebt aangeschaft voor het abonnement.</span><span class="sxs-lookup"><span data-stu-id="663f0-126">**ActiveUnits** is the number of licenses that you've purchased for the subscription.</span></span>
    
- <span data-ttu-id="663f0-127">**WarningUnits** is het aantal licenties in een abonnement dat u nog niet hebt verlengd en dat vervalt na de periode van 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="663f0-127">**WarningUnits** is the number of licenses in a subscription that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="663f0-128">**ConsumedUnits** is het aantal licenties dat u hebt toegewezen aan gebruikers voor het abonnement.</span><span class="sxs-lookup"><span data-stu-id="663f0-128">**ConsumedUnits** is the number of licenses that you've assigned to users for the subscription.</span></span>
    
<span data-ttu-id="663f0-129">Let op de AccountSkuId voor uw Microsoft 365-abonnement met de gebruikers voor wie u een licentie wilt.</span><span class="sxs-lookup"><span data-stu-id="663f0-129">Note the AccountSkuId for your Microsoft 365 subscription that contains the users you want to license.</span></span> <span data-ttu-id="663f0-130">Zorg er ook voor dat er voldoende licenties zijn voor het toewijzen (aftrekken van **ConsumedUnits** van **ActiveUnits** ).</span><span class="sxs-lookup"><span data-stu-id="663f0-130">Also, ensure that there are enough licenses to assign (subtract **ConsumedUnits** from **ActiveUnits** ).</span></span>
  
<span data-ttu-id="663f0-131">Vervolgens voert u deze opdracht uit om de details te bekijken van de Microsoft 365-Serviceabonnementen die beschikbaar zijn in al uw abonnementen:</span><span class="sxs-lookup"><span data-stu-id="663f0-131">Next, run this command to see the details about the Microsoft 365 service plans that are available in all your subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="663f0-132">Op de weergave van deze opdracht bepaalt u welke serviceplannen u wilt uitschakelen wanneer u licenties toewijst aan gebruikers.</span><span class="sxs-lookup"><span data-stu-id="663f0-132">From the display of this command, determine which service plans you would like to disable when you assign licenses to users.</span></span>
  
<span data-ttu-id="663f0-133">Hier volgt een gedeeltelijke lijst met Serviceabonnementen en bijbehorende Microsoft 365-Services.</span><span class="sxs-lookup"><span data-stu-id="663f0-133">Here is a partial list of service plans and their corresponding Microsoft 365 services.</span></span>

<span data-ttu-id="663f0-134">In de volgende tabel ziet u de Microsoft 365-serviceplannen en de beschrijvende namen voor de meest gebruikte services.</span><span class="sxs-lookup"><span data-stu-id="663f0-134">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="663f0-135">Het kan zijn dat uw lijst met Serviceabonnementen verschillend is.</span><span class="sxs-lookup"><span data-stu-id="663f0-135">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="663f0-136">**Service plan**</span><span class="sxs-lookup"><span data-stu-id="663f0-136">**Service plan**</span></span>|<span data-ttu-id="663f0-137">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="663f0-137">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="663f0-138">Sway</span><span class="sxs-lookup"><span data-stu-id="663f0-138">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="663f0-139">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="663f0-139">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="663f0-140">Yammer</span><span class="sxs-lookup"><span data-stu-id="663f0-140">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="663f0-141">Beheer van Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="663f0-141">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="663f0-142">Microsoft 365-apps voor Enterprise *(eerder Office 365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="663f0-142">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="663f0-143">Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="663f0-143">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="663f0-144">Office</span><span class="sxs-lookup"><span data-stu-id="663f0-144">Office</span></span>   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="663f0-145">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="663f0-145">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="663f0-146">Exchange Online Abonnement 2</span><span class="sxs-lookup"><span data-stu-id="663f0-146">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="663f0-147">Voor een volledige lijst met licentie plannen (ook wel productnamen genoemd), de opgenomen serviceplannen en de bijbehorende beschrijvende namen, raadpleegt u [productnamen en serviceplan-id's voor licenties](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="663f0-147">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>
   
<span data-ttu-id="663f0-148">Nu u de AccountSkuId en serviceplannen hebt die u wilt uitschakelen, kunt u een licentie toewijzen voor een individuele gebruiker of voor meerdere gebruikers.</span><span class="sxs-lookup"><span data-stu-id="663f0-148">Now that you have the AccountSkuId and the service plans to disable, you can assign licenses for an individual user or for multiple users.</span></span>
  
### <a name="for-a-single-user"></a><span data-ttu-id="663f0-149">Voor één gebruiker</span><span class="sxs-lookup"><span data-stu-id="663f0-149">For a single user</span></span>

<span data-ttu-id="663f0-150">Voor één gebruiker vult u de User Principal-naam van het gebruikersaccount, de AccountSkuId en de lijst met serviceplannen in om de verklarende tekst en de tekens uit te schakelen en te verwijderen \< and > .</span><span class="sxs-lookup"><span data-stu-id="663f0-150">For a single user, fill in the user principal name of the user account, the AccountSkuId, and the list of service plans to disable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="663f0-151">Voer vervolgens de uitkomstige opdrachten uit op de PowerShell-opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="663f0-151">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

<span data-ttu-id="663f0-152">Hier ziet u een voorbeeld van een opdracht blok voor het account met de naam belindan@contoso.com, voor de contoso: Enterprise Pack-licentie en de serviceplannen die u wilt uitschakelen, zijn RMS_S_ENTERPRISE, SWAY, INTUNE_O365 en YAMMER_ENTERPRISE:</span><span class="sxs-lookup"><span data-stu-id="663f0-152">Here is an example command block for the account named belindan@contoso.com, for the contoso:ENTERPRISEPACK license, and the service plans to disable are RMS_S_ENTERPRISE, SWAY, INTUNE_O365, and YAMMER_ENTERPRISE:</span></span>
  
```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a><span data-ttu-id="663f0-153">Voor meerdere gebruikers</span><span class="sxs-lookup"><span data-stu-id="663f0-153">For multiple users</span></span>

<span data-ttu-id="663f0-154">Als u deze beheertaak voor meerdere gebruikers wilt uitvoeren, maakt u een CSV-tekstbestand met door komma's gescheiden waarden dat de velden UserPrincipalName en UsageLocation bevat.</span><span class="sxs-lookup"><span data-stu-id="663f0-154">To perform this administration task for multiple users, create a comma-separated value (CSV) text file that contains the UserPrincipalName and UsageLocation fields.</span></span> <span data-ttu-id="663f0-155">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="663f0-155">Here is an example:</span></span>
  
```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

<span data-ttu-id="663f0-156">Vul vervolgens de locatie van de CSV-bestanden voor invoer en uitvoer in, de account SKU-ID, en de lijst met serviceplannen die u wilt uitschakelen, en voer vervolgens de bijbehorende opdrachten uit op de PowerShell-opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="663f0-156">Next, fill in the location of the input and output CSV files, the account SKU ID, and the list of service plans to disable, and then run the resulting commands at the PowerShell command prompt.</span></span>
  
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

<span data-ttu-id="663f0-157">Dit PowerShell-opdracht blok:</span><span class="sxs-lookup"><span data-stu-id="663f0-157">This PowerShell command block:</span></span>
  
- <span data-ttu-id="663f0-158">De User Principal name van elke gebruiker weergeven.</span><span class="sxs-lookup"><span data-stu-id="663f0-158">Displays the user principal name of each user.</span></span>
    
- <span data-ttu-id="663f0-159">Hiermee wijst u aan elke gebruiker aangepaste licenties toe.</span><span class="sxs-lookup"><span data-stu-id="663f0-159">Assigns customized licenses to each user.</span></span>
    
- <span data-ttu-id="663f0-160">Hiermee maakt u een CSV-bestand met alle gebruikers die zijn verwerkt en wordt hun licentiestatus weergegeven.</span><span class="sxs-lookup"><span data-stu-id="663f0-160">Creates a CSV file with all the users that were processed and shows their license status.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="663f0-161">Zie ook</span><span class="sxs-lookup"><span data-stu-id="663f0-161">See also</span></span>

[<span data-ttu-id="663f0-162">Toegang tot Microsoft 365-Services met PowerShell uitschakelen</span><span class="sxs-lookup"><span data-stu-id="663f0-162">Disable access to Microsoft 365 services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="663f0-163">Toegang tot Sway uitschakelen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="663f0-163">Disable access to Sway with PowerShell</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="663f0-164">Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="663f0-164">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="663f0-165">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="663f0-165">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
