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
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="3010e-103">Microsoft 365-licenties toewijzen aan gebruikersaccounts met PowerShell</span><span class="sxs-lookup"><span data-stu-id="3010e-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="3010e-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="3010e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3010e-105">Gebruikers kunnen geen Microsoft 365-services gebruiken totdat aan hun account een licentie is toegewezen via een licentieplan.</span><span class="sxs-lookup"><span data-stu-id="3010e-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="3010e-106">U kunt PowerShell gebruiken om snel licenties toe te wijzen aan accounts zonder licentie.</span><span class="sxs-lookup"><span data-stu-id="3010e-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="3010e-107">Gebruikersaccounts moeten eerst een locatie worden toegewezen.</span><span class="sxs-lookup"><span data-stu-id="3010e-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="3010e-108">Het opgeven van een locatie is een verplicht onderdeel van het maken van een nieuw gebruikersaccount in het [Microsoft 365-beheercentrum.](../admin/add-users/add-users.md)</span><span class="sxs-lookup"><span data-stu-id="3010e-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="3010e-109">Accounts die zijn gesynchroniseerd met uw on-premises Active Directory Domain Services, hebben standaard geen locatie opgegeven.</span><span class="sxs-lookup"><span data-stu-id="3010e-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="3010e-110">U kunt een locatie voor deze accounts configureren via:</span><span class="sxs-lookup"><span data-stu-id="3010e-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="3010e-111">Het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="3010e-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="3010e-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3010e-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="3010e-113">De [Azure-portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active**  >  **Directory-gebruikers** > gebruikersaccount >   >  **Profielgegevens**  >  **land of regio**).</span><span class="sxs-lookup"><span data-stu-id="3010e-113">The [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="3010e-114">[Meer informatie over het toewijzen van licenties aan gebruikersaccounts](../admin/manage/assign-licenses-to-users.md) met het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="3010e-114">[Learn how to assign licenses to user accounts](../admin/manage/assign-licenses-to-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="3010e-115">Zie Gebruikers en groepen beheren voor een lijst met [aanvullende bronnen.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="3010e-115">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="3010e-116">De Azure Active Directory PowerShell voor Graph-module gebruiken</span><span class="sxs-lookup"><span data-stu-id="3010e-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="3010e-117">Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="3010e-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="3010e-118">Vermeld vervolgens de licentieplannen voor uw tenant met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="3010e-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="3010e-119">Vervolgens krijgt u de aanmeldingsnaam van het account waaraan u een licentie wilt toevoegen, ook wel de gebruikersnaam (UPN) genoemd.</span><span class="sxs-lookup"><span data-stu-id="3010e-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="3010e-120">Controleer vervolgens of aan het gebruikersaccount een gebruikslocatie is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="3010e-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="3010e-121">Als er geen gebruikslocatie is toegewezen, kunt u er een toewijzen met deze opdrachten:</span><span class="sxs-lookup"><span data-stu-id="3010e-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="3010e-122">Geef ten slotte de naam van de aanmeldings- en licentieplannaam van de gebruiker op en voer deze opdrachten uit.</span><span class="sxs-lookup"><span data-stu-id="3010e-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="3010e-123">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="3010e-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="3010e-124">Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="3010e-124">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="3010e-125">Voer de opdracht uit om de beschikbare licentieplannen en het aantal beschikbare licenties in elk `Get-MsolAccountSku` abonnement in uw organisatie weer te geven.</span><span class="sxs-lookup"><span data-stu-id="3010e-125">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="3010e-126">Het aantal beschikbare licenties in elk abonnement is **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**.</span><span class="sxs-lookup"><span data-stu-id="3010e-126">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="3010e-127">Zie Licenties en services weergeven met [PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md)voor meer informatie over licentieplannen, licenties en services.</span><span class="sxs-lookup"><span data-stu-id="3010e-127">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="3010e-128">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="3010e-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="3010e-129">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3010e-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="3010e-130">Als u de accounts zonder een vergunning in uw organisatie wilt zoeken, kunt u deze opdracht uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="3010e-130">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="3010e-131">U kunt alleen licenties toewijzen aan gebruikersaccounts die de eigenschap **UsageLocation** hebben ingesteld op een geldige ISO 3166-1 alfa-2-landcode.</span><span class="sxs-lookup"><span data-stu-id="3010e-131">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="3010e-132">Bijvoorbeeld VS voor de Verenigde Staten en FR voor Frankrijk.</span><span class="sxs-lookup"><span data-stu-id="3010e-132">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="3010e-133">Sommige Microsoft 365-services zijn niet beschikbaar in bepaalde landen.</span><span class="sxs-lookup"><span data-stu-id="3010e-133">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="3010e-134">Zie Over licentiebeperkingen [voor meer informatie.](https://go.microsoft.com/fwlink/p/?LinkId=691730)</span><span class="sxs-lookup"><span data-stu-id="3010e-134">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="3010e-135">Als u accounts wilt zoeken die geen **UsageLocation-waarde** hebben, kunt u deze opdracht uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="3010e-135">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="3010e-136">Voer deze opdracht uit als u de **waarde UsageLocation** voor een account wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="3010e-136">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="3010e-137">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="3010e-137">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="3010e-138">Als u de **get-MsolUser-cmdlet** gebruikt zonder de parameter **-All** te gebruiken, worden alleen de eerste 500 accounts geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="3010e-138">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="3010e-139">Licenties toewijzen aan gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="3010e-139">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="3010e-140">Als u een licentie wilt toewijzen aan een gebruiker, gebruikt u de volgende opdracht in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3010e-140">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="3010e-141">In dit voorbeeld wordt een licentie van het **licentieplan litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) toegewezen aan de gebruiker zonder licentie **litwareinc.com: \@**</span><span class="sxs-lookup"><span data-stu-id="3010e-141">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="3010e-142">Voer deze opdracht uit als u een licentie wilt toewijzen aan alle gebruikers zonder licentie.</span><span class="sxs-lookup"><span data-stu-id="3010e-142">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="3010e-143">U kunt niet meerdere licenties toewijzen aan een gebruiker via hetzelfde licentieplan.</span><span class="sxs-lookup"><span data-stu-id="3010e-143">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="3010e-144">Als u niet voldoende beschikbare licenties hebt, worden de licenties toegewezen aan gebruikers in de volgorde dat ze worden geretourneerd door de **cmdlet Get-MsolUser** totdat de beschikbare licenties zijn op.</span><span class="sxs-lookup"><span data-stu-id="3010e-144">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="3010e-145">In dit voorbeeld worden licenties van het **licentieplan litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) toegewezen aan alle gebruikers zonder licentie:</span><span class="sxs-lookup"><span data-stu-id="3010e-145">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="3010e-146">In dit voorbeeld worden dezelfde licenties toegewezen aan gebruikers zonder licentie op de afdeling Verkoop in de Verenigde Staten:</span><span class="sxs-lookup"><span data-stu-id="3010e-146">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="3010e-147">Een gebruiker verplaatsen naar een ander abonnement (licentieplan) met de Azure Active Directory PowerShell voor Graph-module</span><span class="sxs-lookup"><span data-stu-id="3010e-147">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="3010e-148">Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="3010e-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="3010e-149">Vervolgens krijgt u de aanmeldingsnaam van het gebruikersaccount waarvoor u van abonnement wilt veranderen, ook wel de gebruikersnaam (UPN) genoemd.</span><span class="sxs-lookup"><span data-stu-id="3010e-149">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="3010e-150">Vermeld vervolgens de abonnementen (licentieplannen) voor uw tenant met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="3010e-150">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="3010e-151">Vermeld vervolgens de abonnementen die het gebruikersaccount momenteel heeft met deze opdrachten.</span><span class="sxs-lookup"><span data-stu-id="3010e-151">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="3010e-152">Bepaal het abonnement dat de gebruiker momenteel heeft (het FROM-abonnement) en het abonnement dat de gebruiker verplaatst (het TO-abonnement).</span><span class="sxs-lookup"><span data-stu-id="3010e-152">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="3010e-153">Geef ten slotte de namen van het TO- en FROM-abonnement (SKU-onderdeelnummers) op en voer deze opdrachten uit.</span><span class="sxs-lookup"><span data-stu-id="3010e-153">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

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

<span data-ttu-id="3010e-154">Met deze opdrachten kunt u de wijziging van het abonnement voor het gebruikersaccount verifiëren.</span><span class="sxs-lookup"><span data-stu-id="3010e-154">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="3010e-155">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3010e-155">See also</span></span>

[<span data-ttu-id="3010e-156">Gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="3010e-156">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3010e-157">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="3010e-157">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3010e-158">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3010e-158">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)