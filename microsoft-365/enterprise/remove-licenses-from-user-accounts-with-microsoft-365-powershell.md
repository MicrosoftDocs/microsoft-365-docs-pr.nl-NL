---
title: Microsoft 365-licenties verwijderen van gebruikersaccounts met PowerShell
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
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: In dit artikel wordt uitgelegd hoe u PowerShell gebruikt om Microsoft 365-licenties te verwijderen die eerder aan gebruikers zijn toegewezen.
ms.openlocfilehash: 815b2290ca3b5ac4ee3cfec87383161ea70f3dca
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689034"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a><span data-ttu-id="fcae6-103">Microsoft 365-licenties verwijderen van gebruikersaccounts met PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcae6-103">Remove Microsoft 365 licenses from user accounts with PowerShell</span></span>

<span data-ttu-id="fcae6-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fcae6-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="fcae6-105">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="fcae6-105">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="fcae6-106">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="fcae6-106">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="fcae6-107">Vermeld vervolgens de licentie plannen voor uw Tenant met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="fcae6-107">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="fcae6-108">Vervolgens haalt u de aanmeldingsnaam op van het account waarvoor u een licentie wilt verwijderen, ook wel bekend als de UPN (User Principal Name).</span><span class="sxs-lookup"><span data-stu-id="fcae6-108">Next, get the sign-in name of the account for which you want remove a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="fcae6-109">Geef ten slotte de namen van de gebruikersaanmelding en het licentie plan op, verwijder de tekens < en > en voer deze opdrachten uit.</span><span class="sxs-lookup"><span data-stu-id="fcae6-109">Finally, specify the user sign-in and license plan names, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

<span data-ttu-id="fcae6-110">Als u alle licenties voor een specifiek gebruikersaccount wilt verwijderen, geeft u de aanmeldingsnaam van de gebruiker op, verwijdert u de tekens < en > en voert u deze opdrachten uit.</span><span class="sxs-lookup"><span data-stu-id="fcae6-110">To remove all of the licenses for a specific user account, specify the user sign-in name, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
if($userList -is [array]) {
for ($i=0; $i -lt $userList.Count; $i++) {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList[$i].SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList[$i].SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}
} else {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList.SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList.SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="fcae6-111">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="fcae6-111">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="fcae6-112">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="fcae6-112">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
   
<span data-ttu-id="fcae6-113">Zie de volgende onderwerpen als u de licentie-informatie wilt weergeven voor**AccountSkuID**.</span><span class="sxs-lookup"><span data-stu-id="fcae6-113">To view the licensing plan (**AccountSkuID**) information in your organization, see the following topics:</span></span>
    
  - [<span data-ttu-id="fcae6-114">Licenties en services weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcae6-114">View licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="fcae6-115">Account licentie en servicedetails weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcae6-115">View account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
<span data-ttu-id="fcae6-116">Als u de cmdlet **Get-MsolUser** gebruikt zonder de parameter _all_ te gebruiken, worden alleen de eerste 500-accounts geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="fcae6-116">If you use the **Get-MsolUser** cmdlet without using the _-All_ parameter, only the first 500 accounts are returned.</span></span>
    
### <a name="removing-licenses-from-user-accounts"></a><span data-ttu-id="fcae6-117">Licenties verwijderen uit gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="fcae6-117">Removing licenses from user accounts</span></span>

<span data-ttu-id="fcae6-118">Gebruik de volgende syntaxis om licenties van een bestaand gebruikersaccount te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="fcae6-118">To remove licenses from an existing user account, use the following syntax:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
><span data-ttu-id="fcae6-119">De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam.</span><span class="sxs-lookup"><span data-stu-id="fcae6-119">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="fcae6-120">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fcae6-120">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="fcae6-121">In dit voorbeeld wordt de licentie **abonnement litwareinc: Enterprise Pack** (Office 365 Enterprise E3) van de gebruikersaccount BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="fcae6-121">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
><span data-ttu-id="fcae6-122">U kunt de cmdlet niet gebruiken `Set-MsolUserLicense` voor het intrekken van gebruikers van *geannuleerde* licenties.</span><span class="sxs-lookup"><span data-stu-id="fcae6-122">You cannot use the `Set-MsolUserLicense` cmdlet to unassign users from *canceled* licenses.</span></span> <span data-ttu-id="fcae6-123">U moet dit afzonderlijk doen voor elk gebruikersaccount in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="fcae6-123">You must do this individually for each user account in the Microsoft 365 admin center.</span></span>
>

<span data-ttu-id="fcae6-124">Gebruik een van de volgende methoden om alle licenties te verwijderen uit een groep bestaande gelicentieerde gebruikers:</span><span class="sxs-lookup"><span data-stu-id="fcae6-124">To remove all licenses from a group of existing licensed users, use either of the following methods:</span></span>
  
- <span data-ttu-id="fcae6-125">**De accounts filteren op basis van een bestaand account kenmerk** Gebruik hiervoor de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="fcae6-125">**Filter the accounts based on an existing account attribute** To do this, use the following syntax:</span></span>
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="fcae6-126">In dit voorbeeld worden alle licenties van alle gebruikersaccounts in de Verenigde Staten verwijderd.</span><span class="sxs-lookup"><span data-stu-id="fcae6-126">This example removes all licenses from all user accounts in the Sales department in the United States.</span></span>
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- <span data-ttu-id="fcae6-127">**Een lijst met specifieke accounts voor een bepaalde licentie gebruiken** Voer de volgende stappen uit om dit te doen:</span><span class="sxs-lookup"><span data-stu-id="fcae6-127">**Use a list of specific accounts for a specific license** To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="fcae6-128">U maakt en opslaat een tekstbestand met één account op elke regel, zoals dit:</span><span class="sxs-lookup"><span data-stu-id="fcae6-128">Create and save a text file that contains one account on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. <span data-ttu-id="fcae6-129">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="fcae6-129">Use the following syntax:</span></span>
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
<span data-ttu-id="fcae6-130">In dit voorbeeld wordt de licentie **abonnement litwareinc: Enterprise Pack** (Office 365 Enterprise E3) verwijderd uit de gebruikersaccounts die zijn gedefinieerd in het tekstbestand c:\Mijn Documents\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="fcae6-130">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user accounts defined in the text file C:\My Documents\Accounts.txt.</span></span>
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

<span data-ttu-id="fcae6-131">Als u alle licenties van alle bestaande gebruikersaccounts wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="fcae6-131">To remove all licenses from all existing user accounts, use the following syntax:</span></span>
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="fcae6-132">Een andere manier om een licentie vrij te maken, is door het gebruikersaccount te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="fcae6-132">Another way to free up a license is by deleting the user account.</span></span> <span data-ttu-id="fcae6-133">Zie voor meer informatie [gebruikersaccounts verwijderen en herstellen met PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="fcae6-133">For more information, see [Delete and restore user accounts with PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fcae6-134">Zie ook</span><span class="sxs-lookup"><span data-stu-id="fcae6-134">See also</span></span>

[<span data-ttu-id="fcae6-135">Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcae6-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fcae6-136">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcae6-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fcae6-137">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fcae6-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

