---
title: Eigenschappen Microsoft 365 gebruikersaccount configureren met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Gebruik PowerShell voor Microsoft 365 om eigenschappen van afzonderlijke of meerdere gebruikersaccounts in uw Microsoft 365 configureren.
ms.openlocfilehash: aeb9b586c42a0bdfb8d69b8d297998fedc1124e6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286007"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="e4170-103">Eigenschappen Microsoft 365 gebruikersaccount configureren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4170-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="e4170-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e4170-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e4170-105">U kunt de Microsoft 365-beheercentrum gebruiken om eigenschappen te configureren voor de gebruikersaccounts van uw Microsoft 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="e4170-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="e4170-106">In PowerShell kunt u dit ook doen, plus enkele andere dingen die u niet kunt doen in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="e4170-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e4170-107">De powershell Azure Active Directory powershell gebruiken voor Graph module</span><span class="sxs-lookup"><span data-stu-id="e4170-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e4170-108">Als u eigenschappen wilt configureren voor gebruikersaccounts in de Azure Active Directory PowerShell voor Graph-module, gebruikt u de cmdlet [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser) en geeft u de eigenschappen op die u wilt instellen of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e4170-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="e4170-109">Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="e4170-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="e4170-110">Eigenschappen wijzigen voor een specifiek gebruikersaccount</span><span class="sxs-lookup"><span data-stu-id="e4170-110">Change properties for a specific user account</span></span>

<span data-ttu-id="e4170-111">U identificeert het account met de *parameter -ObjectID* en stelt of wijzigt specifieke eigenschappen met behulp van extra parameters.</span><span class="sxs-lookup"><span data-stu-id="e4170-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="e4170-112">Hier is een lijst met de meest voorkomende parameters:</span><span class="sxs-lookup"><span data-stu-id="e4170-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="e4170-113">-Department " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="e4170-113">-Department "\<department name>"</span></span>

- <span data-ttu-id="e4170-114">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="e4170-114">-DisplayName "\<full user name>"</span></span>

- <span data-ttu-id="e4170-115">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="e4170-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>

- <span data-ttu-id="e4170-116">-GivenName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="e4170-116">-GivenName "\<user first name>"</span></span>

- <span data-ttu-id="e4170-117">-Achternaam \<user last name> " "</span><span class="sxs-lookup"><span data-stu-id="e4170-117">-Surname "\<user last name>"</span></span>

- <span data-ttu-id="e4170-118">-Mobile " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="e4170-118">-Mobile "\<mobile phone number>"</span></span>

- <span data-ttu-id="e4170-119">-JobTitle " \<job title> "</span><span class="sxs-lookup"><span data-stu-id="e4170-119">-JobTitle "\<job title>"</span></span>

- <span data-ttu-id="e4170-120">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="e4170-120">-PreferredLanguage "\<language>"</span></span>

- <span data-ttu-id="e4170-121">-StreetAddress \<street address> " "</span><span class="sxs-lookup"><span data-stu-id="e4170-121">-StreetAddress "\<street address>"</span></span>

- <span data-ttu-id="e4170-122">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="e4170-122">-City "\<city name>"</span></span>

- <span data-ttu-id="e4170-123">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="e4170-123">-State "\<state name>"</span></span>

- <span data-ttu-id="e4170-124">-Postcode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="e4170-124">-PostalCode "\<postal code>"</span></span>

- <span data-ttu-id="e4170-125">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="e4170-125">-Country "\<country name>"</span></span>

- <span data-ttu-id="e4170-126">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="e4170-126">-TelephoneNumber "\<office phone number>"</span></span>

- <span data-ttu-id="e4170-127">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="e4170-127">-UsageLocation "\<2-character country or region code>"</span></span>

    <span data-ttu-id="e4170-128">Dit is de ISO 3166-1 alfa-2 (A2) land- of regiocode met twee letters.</span><span class="sxs-lookup"><span data-stu-id="e4170-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>

<span data-ttu-id="e4170-129">Zie [Set-AzureADUser voor meer parameters.](/powershell/module/azuread/set-azureaduser)</span><span class="sxs-lookup"><span data-stu-id="e4170-129">For additional parameters, see [Set-AzureADUser](/powershell/module/azuread/set-azureaduser).</span></span>

> [!NOTE]
> <span data-ttu-id="e4170-130">Voordat u licenties kunt toewijzen aan een gebruikersaccount, moet u een gebruikslocatie toewijzen.</span><span class="sxs-lookup"><span data-stu-id="e4170-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>

<span data-ttu-id="e4170-131">Voer de volgende opdracht uit om de gebruikersnaam voor uw gebruikersaccounts weer te geven.</span><span class="sxs-lookup"><span data-stu-id="e4170-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="e4170-132">Met deze opdracht wordt PowerShell instructies gegeven voor:</span><span class="sxs-lookup"><span data-stu-id="e4170-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="e4170-133">Ontvang alle informatie over de gebruikersaccounts **(Get-AzureADUser)** en stuur deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4170-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="e4170-134">Sorteer de lijst met gebruikershoofdnamen alfabetisch **(Sorteer UserPrincipalName)** en verzend deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4170-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="e4170-135">Geef alleen de eigenschap User Principal Name weer voor elk account **(Selecteer UserPrincipalName).**</span><span class="sxs-lookup"><span data-stu-id="e4170-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="e4170-136">Geef ze één scherm tegelijk weer **(Meer).**</span><span class="sxs-lookup"><span data-stu-id="e4170-136">Display them one screen at a time (**More**).</span></span>

<span data-ttu-id="e4170-137">Als u de gebruikersnaam voor een account wilt weergeven op basis van de weergavenaam (voor- en achternaam), voert u de volgende opdrachten uit.</span><span class="sxs-lookup"><span data-stu-id="e4170-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="e4170-138">Vul de variabele *$userName* en verwijder de \< and > tekens:</span><span class="sxs-lookup"><span data-stu-id="e4170-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="e4170-139">In dit voorbeeld wordt de gebruikersnaam weergegeven voor het gebruikersaccount met de weergavenaam *Caleb Sills.*</span><span class="sxs-lookup"><span data-stu-id="e4170-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="e4170-140">Met behulp van *$upn* variabele kunt u wijzigingen aanbrengen in afzonderlijke accounts op basis van de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="e4170-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="e4170-141">Hier is een voorbeeld dat de gebruikslocatie van *Belinda Newman* in stelt op Frankrijk.</span><span class="sxs-lookup"><span data-stu-id="e4170-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="e4170-142">Maar hiermee wordt de weergavenaam opgegeven in plaats van de naam van de hoofdgebruiker:</span><span class="sxs-lookup"><span data-stu-id="e4170-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="e4170-143">Eigenschappen wijzigen voor alle gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="e4170-143">Change properties for all user accounts</span></span>

<span data-ttu-id="e4170-144">Als u eigenschappen voor alle gebruikers wilt wijzigen, kunt u een combinatie van **de get-AzureADUser-** en **Set-AzureADUser-cmdlets** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e4170-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="e4170-145">In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers gewijzigd in *Frankrijk:*</span><span class="sxs-lookup"><span data-stu-id="e4170-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="e4170-146">Met deze opdracht wordt PowerShell instructies gegeven voor:</span><span class="sxs-lookup"><span data-stu-id="e4170-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="e4170-147">Ontvang alle informatie over de gebruikersaccounts **(Get-AzureADUser)** en stuur deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4170-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="e4170-148">Stel de gebruikerslocatie in op Frankrijk (**Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="e4170-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="e4170-149">Eigenschappen wijzigen voor een specifieke set gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="e4170-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="e4170-150">Als u eigenschappen voor een specifieke set gebruikersaccounts wilt wijzigen, kunt u een combinatie van de **cmdlets Get-AzureADUser**, **Where** en **Set-AzureADUser** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e4170-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="e4170-151">In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers van de afdeling Accounting gewijzigd in *Frankrijk:*</span><span class="sxs-lookup"><span data-stu-id="e4170-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="e4170-152">Met deze opdracht wordt PowerShell instructies gegeven voor:</span><span class="sxs-lookup"><span data-stu-id="e4170-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="e4170-153">Ontvang alle informatie over de gebruikersaccounts **(Get-AzureADUser)** en stuur deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4170-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>

1.  <span data-ttu-id="e4170-154">Zoek alle gebruikersaccounts waarop de *eigenschap Afdeling* is ingesteld op 'Accounting' (**Where {$_. Department -eq "Accounting"} ) en** stuur de resulterende informatie naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4170-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>

1. <span data-ttu-id="e4170-155">Stel de gebruikerslocatie in op Frankrijk (**Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="e4170-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e4170-156">Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4170-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e4170-157">Als u eigenschappen voor gebruikersaccounts wilt configureren met de Microsoft Azure Active Directory module voor Windows PowerShell, gebruikt u de cmdlet **Set-MsolUser** en geeft u de eigenschappen op die u wilt instellen of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e4170-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="e4170-158">Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="e4170-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4170-159">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in hun naam.</span><span class="sxs-lookup"><span data-stu-id="e4170-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="e4170-160">Voer deze cmdlets uit vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4170-160">Run these cmdlets from Windows PowerShell.</span></span>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="e4170-161">Eigenschappen wijzigen voor een specifiek gebruikersaccount</span><span class="sxs-lookup"><span data-stu-id="e4170-161">Change properties for a specific user account</span></span>

<span data-ttu-id="e4170-162">Als u eigenschappen voor een specifiek gebruikersaccount wilt configureren, gebruikt u de cmdlet [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) en geeft u de eigenschappen op die u wilt instellen of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e4170-162">To configure properties for a specific user account, use the [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="e4170-163">U identificeert het account met *de parameter -UserPrincipalName* en stelt specifieke eigenschappen in of wijzigt deze met behulp van extra parameters.</span><span class="sxs-lookup"><span data-stu-id="e4170-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="e4170-164">Hier is een lijst met de meest voorkomende parameters.</span><span class="sxs-lookup"><span data-stu-id="e4170-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="e4170-165">-City " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="e4170-165">-City "\<city name>"</span></span>

- <span data-ttu-id="e4170-166">-Country " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="e4170-166">-Country "\<country name>"</span></span>

- <span data-ttu-id="e4170-167">-Department " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="e4170-167">-Department "\<department name>"</span></span>

- <span data-ttu-id="e4170-168">-DisplayName " \<full user name> "</span><span class="sxs-lookup"><span data-stu-id="e4170-168">-DisplayName "\<full user name>"</span></span>

- <span data-ttu-id="e4170-169">-Fax " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="e4170-169">-Fax "\<fax number>"</span></span>

- <span data-ttu-id="e4170-170">-FirstName " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="e4170-170">-FirstName "\<user first name>"</span></span>

- <span data-ttu-id="e4170-171">-LastName " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="e4170-171">-LastName "\<user last name>"</span></span>

- <span data-ttu-id="e4170-172">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="e4170-172">-MobilePhone "\<mobile phone number>"</span></span>

- <span data-ttu-id="e4170-173">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="e4170-173">-Office "\<office location>"</span></span>

- <span data-ttu-id="e4170-174">-PhoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="e4170-174">-PhoneNumber "\<office phone number>"</span></span>

- <span data-ttu-id="e4170-175">-Postcode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="e4170-175">-PostalCode "\<postal code>"</span></span>

- <span data-ttu-id="e4170-176">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="e4170-176">-PreferredLanguage "\<language>"</span></span>

- <span data-ttu-id="e4170-177">-State " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="e4170-177">-State "\<state name>"</span></span>

- <span data-ttu-id="e4170-178">-StreetAddress \<street address> " "</span><span class="sxs-lookup"><span data-stu-id="e4170-178">-StreetAddress "\<street address>"</span></span>

- <span data-ttu-id="e4170-179">-Titel " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="e4170-179">-Title "\<title name>"</span></span>

- <span data-ttu-id="e4170-180">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="e4170-180">-UsageLocation "\<2-character country or region code>"</span></span>

    <span data-ttu-id="e4170-181">Dit is de ISO 3166-1 alfa-2 (A2) land- of regiocode met twee letters.</span><span class="sxs-lookup"><span data-stu-id="e4170-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>

<span data-ttu-id="e4170-182">Zie [Set-MsolUser voor meer parameters.](/previous-versions/azure/dn194136(v=azure.100))</span><span class="sxs-lookup"><span data-stu-id="e4170-182">For additional parameters, see [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="e4170-183">Voer de volgende opdracht uit om de gebruikersnamen van al uw gebruikers te zien:</span><span class="sxs-lookup"><span data-stu-id="e4170-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="e4170-184">Met deze opdracht wordt PowerShell instructies gegeven voor:</span><span class="sxs-lookup"><span data-stu-id="e4170-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="e4170-185">Haal alle informatie op voor de gebruikersaccounts **(Get-MsolUser)** en stuur deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4170-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="e4170-186">Sorteer de lijst met gebruikershoofdnamen alfabetisch **(Sorteer UserPrincipalName)** en verzend deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4170-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="e4170-187">Geef alleen de eigenschap User Principal Name weer voor elk account **(Selecteer UserPrincipalName).**</span><span class="sxs-lookup"><span data-stu-id="e4170-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="e4170-188">Geef ze één scherm tegelijk weer **(Meer).**</span><span class="sxs-lookup"><span data-stu-id="e4170-188">Display them one screen at a time (**More**).</span></span>

<span data-ttu-id="e4170-189">Als u de gebruikersnaam voor een account wilt weergeven op basis van de weergavenaam (voor- en achternaam), voert u de volgende opdrachten uit.</span><span class="sxs-lookup"><span data-stu-id="e4170-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="e4170-190">Vul de variabele *$userName* en verwijder de \< and > tekens.</span><span class="sxs-lookup"><span data-stu-id="e4170-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="e4170-191">In dit voorbeeld wordt de gebruikersnaam weergegeven voor de gebruiker met de naam Caleb Sills:</span><span class="sxs-lookup"><span data-stu-id="e4170-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="e4170-192">Met behulp van *$upn* variabele kunt u wijzigingen aanbrengen in afzonderlijke accounts op basis van de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="e4170-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="e4170-193">Hier is een voorbeeld dat de gebruikslocatie van *Belinda Newman* in frankrijk in *stelt,* maar dat de weergavenaam wordt opgegeven in plaats van de naam van de hoofdgebruiker:</span><span class="sxs-lookup"><span data-stu-id="e4170-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="e4170-194">Eigenschappen wijzigen voor alle gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="e4170-194">Change properties for all user accounts</span></span>

<span data-ttu-id="e4170-195">Als u eigenschappen voor alle gebruikers wilt wijzigen, gebruikt u een combinatie van **de cmdlets Get-MsolUser** en **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="e4170-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="e4170-196">In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers gewijzigd in *Frankrijk:*</span><span class="sxs-lookup"><span data-stu-id="e4170-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="e4170-197">Met deze opdracht wordt PowerShell instructies gegeven voor:</span><span class="sxs-lookup"><span data-stu-id="e4170-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="e4170-198">Haal alle informatie op voor de gebruikersaccounts **(Get-MsolUser)** en stuur deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4170-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="e4170-199">Stel de gebruikerslocatie in op Frankrijk (**Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="e4170-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="e4170-200">Eigenschappen wijzigen voor een specifieke set gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="e4170-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="e4170-201">Als u eigenschappen voor een specifieke set gebruikersaccounts wilt wijzigen, kunt u een combinatie van de **cmdlets Get-MsolUser,** **Where** en **Set-MsolUser** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e4170-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="e4170-202">In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers van de afdeling Accounting gewijzigd in *Frankrijk:*</span><span class="sxs-lookup"><span data-stu-id="e4170-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="e4170-203">Met deze opdracht wordt PowerShell instructies gegeven voor:</span><span class="sxs-lookup"><span data-stu-id="e4170-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="e4170-204">Haal alle informatie op voor de gebruikersaccounts **(Get-MsolUser)** en stuur deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4170-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="e4170-205">Zoek alle gebruikersaccounts waarop de *eigenschap Afdeling* is ingesteld op 'Accounting' (**Where {$_. Department -eq "Accounting"}**) en stuur de resulterende informatie naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="e4170-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>

1. <span data-ttu-id="e4170-206">Stel de gebruikerslocatie in op Frankrijk (**Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="e4170-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4170-207">Zie ook</span><span class="sxs-lookup"><span data-stu-id="e4170-207">See also</span></span>

[<span data-ttu-id="e4170-208">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4170-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e4170-209">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4170-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e4170-210">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e4170-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
