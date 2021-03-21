---
title: Microsoft 365-licenties verwijderen uit gebruikersaccounts met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
description: Hier wordt uitgelegd hoe u PowerShell gebruikt om Microsoft 365-licenties te verwijderen die eerder aan gebruikers zijn toegewezen.
ms.openlocfilehash: 9944d1ab056d109b6bf71a44fe01acef78ce1f14
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920666"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a><span data-ttu-id="db82d-103">Microsoft 365-licenties verwijderen uit gebruikersaccounts met PowerShell</span><span class="sxs-lookup"><span data-stu-id="db82d-103">Remove Microsoft 365 licenses from user accounts with PowerShell</span></span>

<span data-ttu-id="db82d-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="db82d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

>[!Note]
><span data-ttu-id="db82d-105">[Meer informatie over het verwijderen van licenties uit gebruikersaccounts](../admin/manage/remove-licenses-from-users.md) met het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="db82d-105">[Learn how to remove licenses from user accounts](../admin/manage/remove-licenses-from-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="db82d-106">Zie Gebruikers en groepen beheren voor een lijst met [aanvullende bronnen.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="db82d-106">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="db82d-107">De Azure Active Directory PowerShell voor Graph-module gebruiken</span><span class="sxs-lookup"><span data-stu-id="db82d-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="db82d-108">Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="db82d-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="db82d-109">Vermeld vervolgens de licentieplannen voor uw tenant met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="db82d-109">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="db82d-110">Vervolgens krijgt u de aanmeldingsnaam van het account waarvoor u een licentie wilt verwijderen, ook wel de gebruikersnaam (UPN) genoemd.</span><span class="sxs-lookup"><span data-stu-id="db82d-110">Next, get the sign-in name of the account for which you want remove a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="db82d-111">Geef ten slotte de namen van de aanmeldings- en licentieplannen van de gebruiker op, verwijder de tekens '<' en '>' en voer deze opdrachten uit.</span><span class="sxs-lookup"><span data-stu-id="db82d-111">Finally, specify the user sign-in and license plan names, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

<span data-ttu-id="db82d-112">Als u alle licenties voor een specifiek gebruikersaccount wilt verwijderen, geeft u de aanmeldingsnaam van de gebruiker op, verwijdert u de tekens '<' en '>' en voert u deze opdrachten uit.</span><span class="sxs-lookup"><span data-stu-id="db82d-112">To remove all of the licenses for a specific user account, specify the user sign-in name, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userList = Get-AzureADUser -ObjectID $userUPN
$Skus = $userList | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
    if($Skus -is [array])
    {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        for ($i=0; $i -lt $Skus.Count; $i++) {
            $Licenses.RemoveLicenses +=  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus[$i].SkuId -EQ).SkuID   
        }
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    } else {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        $Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus.SkuId -EQ).SkuID
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    }
}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="db82d-113">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="db82d-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="db82d-114">Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="db82d-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
   
<span data-ttu-id="db82d-115">Zie de volgende onderwerpen als u de informatie over het licentieplan **(AccountSkuID)** in uw organisatie wilt bekijken:</span><span class="sxs-lookup"><span data-stu-id="db82d-115">To view the licensing plan (**AccountSkuID**) information in your organization, see the following topics:</span></span>
    
  - [<span data-ttu-id="db82d-116">Licenties en services weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="db82d-116">View licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="db82d-117">Accountlicentie- en servicedetails weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="db82d-117">View account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
<span data-ttu-id="db82d-118">Als u de **get-MsolUser-cmdlet** gebruikt zonder de parameter _-All_ te gebruiken, worden alleen de eerste 500 accounts geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="db82d-118">If you use the **Get-MsolUser** cmdlet without using the _-All_ parameter, only the first 500 accounts are returned.</span></span>
    
### <a name="removing-licenses-from-user-accounts"></a><span data-ttu-id="db82d-119">Licenties verwijderen uit gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="db82d-119">Removing licenses from user accounts</span></span>

<span data-ttu-id="db82d-120">Als u licenties wilt verwijderen uit een bestaand gebruikersaccount, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="db82d-120">To remove licenses from an existing user account, use the following syntax:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
><span data-ttu-id="db82d-121">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="db82d-121">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="db82d-122">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db82d-122">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="db82d-123">In dit voorbeeld wordt de **licentie litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) verwijderd uit het gebruikersaccount BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="db82d-123">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
><span data-ttu-id="db82d-124">U kunt de `Set-MsolUserLicense` cmdlet niet gebruiken om gebruikers te ontzeggen van *geannuleerde* licenties.</span><span class="sxs-lookup"><span data-stu-id="db82d-124">You cannot use the `Set-MsolUserLicense` cmdlet to unassign users from *canceled* licenses.</span></span> <span data-ttu-id="db82d-125">U moet dit afzonderlijk doen voor elk gebruikersaccount in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="db82d-125">You must do this individually for each user account in the Microsoft 365 admin center.</span></span>
>

<span data-ttu-id="db82d-126">Als u alle licenties wilt verwijderen uit een groep bestaande gebruikers met een licentie, gebruikt u een van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="db82d-126">To remove all licenses from a group of existing licensed users, use either of the following methods:</span></span>
  
- <span data-ttu-id="db82d-127">**De accounts filteren op basis van een bestaand accountkenmerk** Gebruik hiervoor de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="db82d-127">**Filter the accounts based on an existing account attribute** To do this, use the following syntax:</span></span>
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="db82d-128">In dit voorbeeld worden alle licenties verwijderd uit alle gebruikersaccounts van de afdeling Verkoop in de Verenigde Staten.</span><span class="sxs-lookup"><span data-stu-id="db82d-128">This example removes all licenses from all user accounts in the Sales department in the United States.</span></span>
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- <span data-ttu-id="db82d-129">**Een lijst met specifieke accounts gebruiken voor een specifieke licentie** Voer hiervoor de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="db82d-129">**Use a list of specific accounts for a specific license** To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="db82d-130">Maak en sla een tekstbestand op met één account op elke regel als dit:</span><span class="sxs-lookup"><span data-stu-id="db82d-130">Create and save a text file that contains one account on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. <span data-ttu-id="db82d-131">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="db82d-131">Use the following syntax:</span></span>
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
<span data-ttu-id="db82d-132">In dit voorbeeld wordt de **licentie litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) verwijderd uit de gebruikersaccounts die zijn gedefinieerd in het tekstbestand C:\Mijn Documents\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="db82d-132">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user accounts defined in the text file C:\My Documents\Accounts.txt.</span></span>
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

<span data-ttu-id="db82d-133">Als u alle licenties wilt verwijderen uit alle bestaande gebruikersaccounts, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="db82d-133">To remove all licenses from all existing user accounts, use the following syntax:</span></span>
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="db82d-134">Een andere manier om een licentie vrij te maken is door het gebruikersaccount te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="db82d-134">Another way to free up a license is by deleting the user account.</span></span> <span data-ttu-id="db82d-135">Zie Gebruikersaccounts verwijderen [en herstellen met PowerShell voor meer informatie.](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="db82d-135">For more information, see [Delete and restore user accounts with PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="db82d-136">Zie ook</span><span class="sxs-lookup"><span data-stu-id="db82d-136">See also</span></span>

[<span data-ttu-id="db82d-137">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="db82d-137">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="db82d-138">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="db82d-138">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="db82d-139">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="db82d-139">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)