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
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a><span data-ttu-id="90a86-103">Microsoft 365-account licentie en servicedetails weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="90a86-103">View Microsoft 365 account license and service details with PowerShell</span></span>

<span data-ttu-id="90a86-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="90a86-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="90a86-105">In Microsoft 365 kunnen licenties van licentie plannen (ook wel Sku's of Microsoft 365-abonnementen genoemd) gebruikers toegang geven tot de Microsoft 365-services die zijn gedefinieerd voor die plannen.</span><span class="sxs-lookup"><span data-stu-id="90a86-105">In Microsoft 365, licenses from licensing plans (also called SKUs or Microsoft 365 plans) give users access to the Microsoft 365 services that are defined for those plans.</span></span> <span data-ttu-id="90a86-106">Een gebruiker heeft echter mogelijk geen toegang tot alle services die beschikbaar zijn in een licentie die momenteel aan de gebruikers is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="90a86-106">However, a user might not have access to all the services that are available in a license that's currently assigned to them.</span></span> <span data-ttu-id="90a86-107">Met PowerShell voor Microsoft 365 kunt u de status van services op gebruikersaccounts bekijken.</span><span class="sxs-lookup"><span data-stu-id="90a86-107">You can use PowerShell for Microsoft 365 to view the status of services on user accounts.</span></span> 

<span data-ttu-id="90a86-108">Zie [licenties en services in PowerShell weergeven](view-licenses-and-services-with-microsoft-365-powershell.md)voor meer informatie over licentie regelingen, licenties en services.</span><span class="sxs-lookup"><span data-stu-id="90a86-108">For more information about licensing plans, license, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="90a86-109">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="90a86-109">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="90a86-110">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="90a86-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="90a86-111">Vermeld vervolgens de licentie plannen voor uw Tenant met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="90a86-111">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="90a86-112">Met deze opdrachten kunt u een lijst weergeven met de beschikbare services in elk licentie plan.</span><span class="sxs-lookup"><span data-stu-id="90a86-112">Use these commands to list the services that are available in each licensing plan.</span></span>

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

<span data-ttu-id="90a86-113">Met deze opdrachten kunt u de licenties weergeven die zijn toegewezen aan een gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="90a86-113">Use these commands to list the licenses that are assigned to a user account.</span></span>

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="90a86-114">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="90a86-114">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="90a86-115">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="90a86-115">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="90a86-116">Vervolgens voert u deze opdracht uit om een lijst weer te geven met licentie plannen die beschikbaar zijn in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="90a86-116">Next, run this command to list the licensing plans that are available in your organization.</span></span> 

```powershell
Get-MsolAccountSku
```
>[!Note]
><span data-ttu-id="90a86-117">De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam.</span><span class="sxs-lookup"><span data-stu-id="90a86-117">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="90a86-118">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90a86-118">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="90a86-119">Vervolgens voert u deze opdracht uit om een lijst weer te geven van de services die beschikbaar zijn in elk licentie plan, en de volgorde waarin ze worden weergegeven (het indexnummer).</span><span class="sxs-lookup"><span data-stu-id="90a86-119">Next, run this command to list the services that are available in each licensing plan, and the order in which they are listed (the index number).</span></span>

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
<span data-ttu-id="90a86-120">Gebruik deze opdracht om de licenties weer te geven die aan een gebruiker zijn toegewezen, en in welke volgorde ze worden weergegeven (het indexnummer).</span><span class="sxs-lookup"><span data-stu-id="90a86-120">Use this command to list the licenses that are assigned to a user, and the order in which they are listed (the index number).</span></span>

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a><span data-ttu-id="90a86-121">Services voor een gebruikersaccount weergeven</span><span class="sxs-lookup"><span data-stu-id="90a86-121">To view services for a user account</span></span>

<span data-ttu-id="90a86-122">Als u alle Microsoft 365-Services wilt bekijken waartoe een gebruiker toegang heeft, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="90a86-122">To view all the Microsoft 365 services that a user has access to, use the following syntax:</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

<span data-ttu-id="90a86-123">In dit voorbeeld ziet u de services waartoe de gebruiker BelindaN@litwareinc.com toegang heeft.</span><span class="sxs-lookup"><span data-stu-id="90a86-123">This example shows the services to which the user BelindaN@litwareinc.com has access.</span></span> <span data-ttu-id="90a86-124">Hier ziet u de services die zijn gekoppeld aan alle licenties die aan haar account zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="90a86-124">This shows the services that are associated with all licenses that are assigned to her account.</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

<span data-ttu-id="90a86-125">In het volgende voorbeeld ziet u de services waartoe de gebruiker BelindaN@litwareinc.com toegang heeft vanaf de eerste licentie die is toegewezen aan haar account (het indexnummer is 0).</span><span class="sxs-lookup"><span data-stu-id="90a86-125">This example shows the services that user BelindaN@litwareinc.com has access to from the first license that's assigned to her account (the index number is 0).</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

<span data-ttu-id="90a86-126">Als u alle services wilt weergeven voor een gebruiker aan wie *meerdere licenties*zijn toegewezen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="90a86-126">To view all the services for a user who has been assigned *multiple licenses*, use the following syntax:</span></span>

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
 
## <a name="see-also"></a><span data-ttu-id="90a86-127">Zie ook</span><span class="sxs-lookup"><span data-stu-id="90a86-127">See also</span></span>

[<span data-ttu-id="90a86-128">Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="90a86-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="90a86-129">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="90a86-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="90a86-130">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="90a86-130">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
