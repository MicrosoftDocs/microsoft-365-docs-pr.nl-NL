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
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a><span data-ttu-id="f79f3-103">De Microsoft 365 en servicegegevens van uw account weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="f79f3-103">View Microsoft 365 account license and service details with PowerShell</span></span>

<span data-ttu-id="f79f3-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f79f3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f79f3-105">In Microsoft 365 geven licenties van licentieplannen (ook wel SKU's of Microsoft 365-abonnementen genoemd) gebruikers toegang tot de Microsoft 365-services die voor deze abonnementen zijn gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="f79f3-105">In Microsoft 365, licenses from licensing plans (also called SKUs or Microsoft 365 plans) give users access to the Microsoft 365 services that are defined for those plans.</span></span> <span data-ttu-id="f79f3-106">Een gebruiker heeft mogelijk echter geen toegang tot alle services die beschikbaar zijn in een licentie die momenteel aan hen is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="f79f3-106">However, a user might not have access to all the services that are available in a license that's currently assigned to them.</span></span> <span data-ttu-id="f79f3-107">U kunt PowerShell gebruiken voor Microsoft 365 om de status van services op gebruikersaccounts te bekijken.</span><span class="sxs-lookup"><span data-stu-id="f79f3-107">You can use PowerShell for Microsoft 365 to view the status of services on user accounts.</span></span> 

<span data-ttu-id="f79f3-108">Zie Licenties en services weergeven met PowerShell voor meer informatie over licentieplannen, licenties en [services.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="f79f3-108">For more information about licensing plans, license, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f79f3-109">De powershell Azure Active Directory powershell gebruiken voor Graph module</span><span class="sxs-lookup"><span data-stu-id="f79f3-109">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f79f3-110">Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="f79f3-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="f79f3-111">Vermeld vervolgens de licentieplannen voor uw tenant met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="f79f3-111">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="f79f3-112">Gebruik deze opdrachten om de services weer te geven die beschikbaar zijn in elk licentieplan.</span><span class="sxs-lookup"><span data-stu-id="f79f3-112">Use these commands to list the services that are available in each licensing plan.</span></span>

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

<span data-ttu-id="f79f3-113">Gebruik deze opdrachten om de licenties weer te geven die aan een gebruikersaccount zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="f79f3-113">Use these commands to list the licenses that are assigned to a user account.</span></span>

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f79f3-114">Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f79f3-114">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="f79f3-115">Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="f79f3-115">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="f79f3-116">Voer vervolgens deze opdracht uit om de licentieplannen weer te geven die beschikbaar zijn in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f79f3-116">Next, run this command to list the licensing plans that are available in your organization.</span></span> 

```powershell
Get-MsolAccountSku
```
>[!Note]
><span data-ttu-id="f79f3-117">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="f79f3-117">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="f79f3-118">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f79f3-118">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="f79f3-119">Voer vervolgens deze opdracht uit om de services weer te geven die beschikbaar zijn in elk licentieplan en de volgorde waarin ze worden vermeld (het indexnummer).</span><span class="sxs-lookup"><span data-stu-id="f79f3-119">Next, run this command to list the services that are available in each licensing plan, and the order in which they are listed (the index number).</span></span>

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
<span data-ttu-id="f79f3-120">Gebruik deze opdracht om de licenties op te geven die aan een gebruiker zijn toegewezen en de volgorde waarin deze worden vermeld (het indexnummer).</span><span class="sxs-lookup"><span data-stu-id="f79f3-120">Use this command to list the licenses that are assigned to a user, and the order in which they are listed (the index number).</span></span>

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a><span data-ttu-id="f79f3-121">Services voor een gebruikersaccount weergeven</span><span class="sxs-lookup"><span data-stu-id="f79f3-121">To view services for a user account</span></span>

<span data-ttu-id="f79f3-122">Gebruik de volgende syntaxis om alle Microsoft 365 services weer te geven die een gebruiker heeft:</span><span class="sxs-lookup"><span data-stu-id="f79f3-122">To view all the Microsoft 365 services that a user has access to, use the following syntax:</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

<span data-ttu-id="f79f3-123">In dit voorbeeld ziet u de services waarop de gebruiker BelindaN@litwareinc.com toegang heeft.</span><span class="sxs-lookup"><span data-stu-id="f79f3-123">This example shows the services to which the user BelindaN@litwareinc.com has access.</span></span> <span data-ttu-id="f79f3-124">Hier ziet u de services die zijn gekoppeld aan alle licenties die aan haar account zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="f79f3-124">This shows the services that are associated with all licenses that are assigned to her account.</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

<span data-ttu-id="f79f3-125">In dit voorbeeld ziet u de services BelindaN@litwareinc.com gebruikerstoegang hebben vanaf de eerste licentie die aan haar account is toegewezen (het indexnummer is 0).</span><span class="sxs-lookup"><span data-stu-id="f79f3-125">This example shows the services that user BelindaN@litwareinc.com has access to from the first license that's assigned to her account (the index number is 0).</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

<span data-ttu-id="f79f3-126">Als u alle services wilt weergeven voor een gebruiker die meerdere licenties *heeft* gekregen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="f79f3-126">To view all the services for a user who has been assigned *multiple licenses*, use the following syntax:</span></span>

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
 
## <a name="see-also"></a><span data-ttu-id="f79f3-127">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f79f3-127">See also</span></span>

[<span data-ttu-id="f79f3-128">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="f79f3-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f79f3-129">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="f79f3-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f79f3-130">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f79f3-130">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
