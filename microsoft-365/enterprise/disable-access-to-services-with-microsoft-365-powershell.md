---
title: Toegang tot Microsoft 365-services uitschakelen met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
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
- Ent_Office_Other
- PowerShell
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: In dit artikel leert u hoe u PowerShell kunt gebruiken om de toegang tot Microsoft 365 voor gebruikers uit te schakelen.
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689172"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a><span data-ttu-id="558bb-103">Toegang tot Microsoft 365-services uitschakelen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="558bb-103">Disable access to Microsoft 365 services with PowerShell</span></span>

<span data-ttu-id="558bb-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="558bb-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="558bb-105">Wanneer aan Microsoft 365-account een licentie is toegewezen vanuit een licentieplan, worden Microsoft 365 services beschikbaar gesteld aan de gebruiker via die licentie.</span><span class="sxs-lookup"><span data-stu-id="558bb-105">When a Microsoft 365 account is assigned a license from a licensing plan, Microsoft 365 services are made available to the user from that license.</span></span> <span data-ttu-id="558bb-106">U kunt echter wel de Microsoft 365 services die de gebruiker kan openen.</span><span class="sxs-lookup"><span data-stu-id="558bb-106">However, you can control the Microsoft 365 services that the user can access.</span></span> <span data-ttu-id="558bb-107">Hoewel de licentie bijvoorbeeld toegang biedt tot de SharePoint Online-service, kunt u de toegang tot de service uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="558bb-107">For example, even though the license allows access to the SharePoint Online service, you can disable access to it.</span></span> <span data-ttu-id="558bb-108">U kunt PowerShell gebruiken om toegang tot een bepaald aantal services voor een specifiek licentieplan uit te schakelen voor:</span><span class="sxs-lookup"><span data-stu-id="558bb-108">You can use PowerShell to disable access to any number of services for a specific licensing plan for:</span></span>

- <span data-ttu-id="558bb-109">Een afzonderlijk account.</span><span class="sxs-lookup"><span data-stu-id="558bb-109">An individual account.</span></span>
- <span data-ttu-id="558bb-110">Een groep accounts.</span><span class="sxs-lookup"><span data-stu-id="558bb-110">A group of accounts.</span></span>
- <span data-ttu-id="558bb-111">Alle accounts in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="558bb-111">All accounts in your organization.</span></span>

>[!Note]
><span data-ttu-id="558bb-112">Er zijn Microsoft 365 serviceafhankelijkheden waardoor u een opgegeven service niet kunt uitschakelen wanneer andere services ervan afhankelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="558bb-112">There are Microsoft 365 service dependencies that can prevent you from disabling a specified service when other services depend on it.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="558bb-113">Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="558bb-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="558bb-114">Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="558bb-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="558bb-115">Gebruik vervolgens deze opdracht om uw beschikbare licentieplannen weer te geven, ook wel AccountSkuIds genoemd:</span><span class="sxs-lookup"><span data-stu-id="558bb-115">Next, use this command to view your available licensing plans, also known as AccountSkuIds:</span></span>

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
><span data-ttu-id="558bb-116">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="558bb-116">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="558bb-117">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="558bb-117">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="558bb-118">Zie Licenties en services weergeven met PowerShell voor [meer informatie.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="558bb-118">For more information, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="558bb-119">Zie Accountlicentie- en servicedetails weergeven met PowerShell voor en na de resultaten van de procedures in [dit onderwerp.](view-account-license-and-service-details-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="558bb-119">To see the before and after results of the procedures in this topic, see [View account license and service details with PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="558bb-120">Er is een PowerShell-script beschikbaar dat de procedures automatiseert die in dit onderwerp worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="558bb-120">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="558bb-121">Met het script kunt u services weergeven en uitschakelen in uw Microsoft 365 organisatie, inclusief Sway.</span><span class="sxs-lookup"><span data-stu-id="558bb-121">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="558bb-122">Zie Toegang tot [Sway uitschakelen met PowerShell voor meer informatie.](disable-access-to-sway-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="558bb-122">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a><span data-ttu-id="558bb-123">Specifieke services Microsoft 365 specifieke gebruikers uitschakelen voor een specifiek licentieplan</span><span class="sxs-lookup"><span data-stu-id="558bb-123">Disable specific Microsoft 365 services for specific users for a specific licensing plan</span></span>
  
<span data-ttu-id="558bb-124">Voer de volgende stappen uit om Microsoft 365 specifieke set services voor gebruikers voor een specifiek licentieplan uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="558bb-124">To disable a specific set of Microsoft 365 services for users for a specific licensing plan, perform the following steps:</span></span>
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a><span data-ttu-id="558bb-125">Stap 1: Identificeer de ongewenste services in het licentieplan met de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="558bb-125">Step 1: Identify the undesirable services in the licensing plan by using the following syntax:</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

<span data-ttu-id="558bb-126">In het volgende voorbeeld wordt een **Object LicenseOptions** gemaakt dat de Office en SharePoint Online-services uit schakelt in het licentieplan met de naam `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="558bb-126">The following example creates a **LicenseOptions** object that disables the Office and SharePoint Online services in the licensing plan named `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a><span data-ttu-id="558bb-127">Stap 2: Gebruik het **object LicenseOptions** uit stap 1 voor een of meer gebruikers.</span><span class="sxs-lookup"><span data-stu-id="558bb-127">Step 2: Use the **LicenseOptions** object from Step 1 on one or more users.</span></span>
    
<span data-ttu-id="558bb-128">Als u een nieuw account wilt maken dat de services heeft uitgeschakeld, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="558bb-128">To create a new account that has the services disabled, use the following syntax:</span></span>
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

<span data-ttu-id="558bb-129">In het volgende voorbeeld wordt een nieuw account gemaakt voor Allie Bellew, dat de licentie toewijst en de services uit schakelt die worden beschreven in stap 1.</span><span class="sxs-lookup"><span data-stu-id="558bb-129">The following example creates a new account for Allie Bellew that assigns the license and disables the services described in Step 1.</span></span>
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

<span data-ttu-id="558bb-130">Zie Gebruikersaccounts maken met [PowerShell](create-user-accounts-with-microsoft-365-powershell.md)voor meer informatie over het maken van gebruikersaccounts in PowerShell voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="558bb-130">For more information about creating user accounts in PowerShell for Microsoft 365, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="558bb-131">Als u de services voor een bestaande gelicentieerde gebruiker wilt uitschakelen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="558bb-131">To disable the services for an existing licensed user, use the following syntax:</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

<span data-ttu-id="558bb-132">In dit voorbeeld worden de services voor de BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="558bb-132">This example disables the services for the user BelindaN@litwareinc.com.</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

<span data-ttu-id="558bb-133">Als u de services wilt uitschakelen die worden beschreven in stap 1 voor alle bestaande gelicentieerde gebruikers, geeft u de naam van uw Microsoft 365-abonnement op in de weergave van de **Get-MsolAccountSku-cmdlet** (zoals **litwareinc:ENTERPRISEPACK)** en voert u de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="558bb-133">To disable the services described in Step 1 for all existing licensed users, specify the name of your Microsoft 365 plan from the display of the **Get-MsolAccountSku** cmdlet (such as **litwareinc:ENTERPRISEPACK**), and then run the following commands:</span></span>
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 <span data-ttu-id="558bb-134">Als u de **get-MsolUser-cmdlet** gebruikt zonder de _parameter_ Alle te gebruiken, worden alleen de eerste 500 gebruikersaccounts geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="558bb-134">If you use the **Get-MsolUser** cmdlet without using the _All_ parameter, only the first 500 user accounts are returned.</span></span>

<span data-ttu-id="558bb-135">Als u de services voor een groep bestaande gebruikers wilt uitschakelen, gebruikt u een van de volgende methoden om de gebruikers te identificeren:</span><span class="sxs-lookup"><span data-stu-id="558bb-135">To disable the services for a group of existing users, use either of the following methods to identify the users:</span></span>
    
<span data-ttu-id="558bb-136">**Methode 1. De accounts filteren op basis van een bestaand accountkenmerk**</span><span class="sxs-lookup"><span data-stu-id="558bb-136">**Method 1. Filter the accounts based on an existing account attribute**</span></span> 

<span data-ttu-id="558bb-137">Gebruik hiervoor de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="558bb-137">To do this, use the following syntax:</span></span>
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="558bb-138">In het volgende voorbeeld worden de services uitgeschakeld voor gebruikers op de afdeling Verkoop in de Verenigde Staten.</span><span class="sxs-lookup"><span data-stu-id="558bb-138">The following example disables the services for users in the Sales department in the United States.</span></span>
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="558bb-139">**Methode 2: Een lijst met specifieke accounts gebruiken**</span><span class="sxs-lookup"><span data-stu-id="558bb-139">**Method 2: Use a list of specific accounts**</span></span> 

<span data-ttu-id="558bb-140">Voer hiervoor de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="558bb-140">To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="558bb-141">Maak een tekstbestand met één account op elke regel als dit:</span><span class="sxs-lookup"><span data-stu-id="558bb-141">Create a text file that contains one account on each line like this:</span></span>
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   <span data-ttu-id="558bb-142">In dit voorbeeld is het tekstbestand C: \\ Mijn \\ documentenAccounts.txt.</span><span class="sxs-lookup"><span data-stu-id="558bb-142">In this example, the text file is C:\\My Documents\\Accounts.txt.</span></span>
    
2. <span data-ttu-id="558bb-143">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="558bb-143">Run the following command:</span></span>
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

<span data-ttu-id="558bb-144">Als u de toegang tot services voor meerdere licentieplannen wilt uitschakelen, herhaalt u de bovenstaande instructies voor elk licentieplan en zorgt u ervoor dat:</span><span class="sxs-lookup"><span data-stu-id="558bb-144">If you want to disable access to services for multiple licensing plans, repeat the above instructions for each licensing plan, ensuring that:</span></span>

- <span data-ttu-id="558bb-145">Aan de gebruikersaccounts is het licentieplan toegewezen.</span><span class="sxs-lookup"><span data-stu-id="558bb-145">The user accounts have been assigned the licensing plan.</span></span>
- <span data-ttu-id="558bb-146">De services die u wilt uitschakelen, zijn beschikbaar in het licentieplan.</span><span class="sxs-lookup"><span data-stu-id="558bb-146">The services to disable are available in the licensing plan.</span></span>

<span data-ttu-id="558bb-147">Als u Microsoft 365 services voor gebruikers wilt uitschakelen terwijl u ze aan een licentieplan toewijst, gaat u naar Toegang tot services uitschakelen tijdens het toewijzen [van gebruikerslicenties.](disable-access-to-services-while-assigning-user-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="558bb-147">To disable Microsoft 365 services for users while you are assigning them to a licensing plan, see [Disable access to services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</span></span>

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a><span data-ttu-id="558bb-148">Alle services in een licentieplan toewijzen aan een gebruikersaccount</span><span class="sxs-lookup"><span data-stu-id="558bb-148">Assign all services in a licensing plan to a user account</span></span>

<span data-ttu-id="558bb-149">Voor gebruikersaccounts die services hebben uitgeschakeld, kunt u alle services voor een specifiek licentieplan inschakelen met de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="558bb-149">For user accounts that have had services disabled, you can enable all services for a specific licensing plan with these commands:</span></span>

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a><span data-ttu-id="558bb-150">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="558bb-150">Related topic</span></span>

[<span data-ttu-id="558bb-151">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="558bb-151">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="558bb-152">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="558bb-152">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="558bb-153">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="558bb-153">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
