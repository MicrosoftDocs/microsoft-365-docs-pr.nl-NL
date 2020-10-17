---
title: Eigenschappen van Microsoft 365-gebruikersaccounts configureren met PowerShell
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
description: 'Overzicht: gebruik PowerShell voor Microsoft 365 om eigenschappen van afzonderlijke of meerdere gebruikersaccounts in uw Microsoft 365-Tenant te configureren.'
ms.openlocfilehash: ae797d67b47c637dc95176b92fad8090f8a7ab37
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580926"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="bfb71-103">Eigenschappen van Microsoft 365-gebruikersaccounts configureren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfb71-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="bfb71-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="bfb71-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bfb71-105">Hoewel u het Microsoft 365-Beheercentrum kunt gebruiken om de eigenschappen van de gebruikersaccounts van uw Microsoft 365-Tenant te configureren, kunt u ook PowerShell gebruiken en de volgende dingen doen, wat niet mogelijk is met het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="bfb71-105">Although you can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant, you can also use PowerShell and do some things that the Microsoft 365 admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="bfb71-106">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="bfb71-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="bfb71-107">Voor het configureren van eigenschappen voor gebruikersaccounts met de module Azure Active Directory PowerShell voor Graph, gebruikt u de cmdlet [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) en geeft u de eigenschappen op die u wilt instellen of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="bfb71-107">To configure properties for user accounts with the Azure Active Directory PowerShell for Graph module, you use the [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="bfb71-108">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="bfb71-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="bfb71-109">Eigenschappen van een specifiek gebruikersaccount wijzigen</span><span class="sxs-lookup"><span data-stu-id="bfb71-109">Change properties for a specific user account</span></span>

<span data-ttu-id="bfb71-110">U identificeert het account met de parameter **-ObjectID** en stelt of wijzigt specifieke eigenschappen met aanvullende parameters.</span><span class="sxs-lookup"><span data-stu-id="bfb71-110">You identify the account with the **-ObjectID** parameter and set or change specific properties with additional parameters.</span></span> <span data-ttu-id="bfb71-111">Hier volgt een lijst met de meest voorkomende parameters.</span><span class="sxs-lookup"><span data-stu-id="bfb71-111">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="bfb71-112">-Afdeling " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-112">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="bfb71-113">Naam van een \<full user name> '</span><span class="sxs-lookup"><span data-stu-id="bfb71-113">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="bfb71-114">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-114">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="bfb71-115">-Benaming " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-115">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="bfb71-116">-Achternaam " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-116">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="bfb71-117">-Mobiel " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-117">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="bfb71-118">-JobTitle \<job title></span><span class="sxs-lookup"><span data-stu-id="bfb71-118">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="bfb71-119">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-119">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="bfb71-120">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-120">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="bfb71-121">-Plaats " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-121">-City "\<city name>"</span></span>
    
- <span data-ttu-id="bfb71-122">-Status " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-122">-State "\<state name>"</span></span>
    
- <span data-ttu-id="bfb71-123">-Postcode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-123">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="bfb71-124">-Land " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-124">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="bfb71-125">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-125">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="bfb71-126">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-126">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="bfb71-127">Dit is de ISO 3166-1 alfa-2 (a2) land-of regiocode van twee letters.</span><span class="sxs-lookup"><span data-stu-id="bfb71-127">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="bfb71-128">Zie [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) voor aanvullende parameters.</span><span class="sxs-lookup"><span data-stu-id="bfb71-128">See [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) for additional parameters.</span></span>

>[!Note]
><span data-ttu-id="bfb71-129">Voordat u licenties kunt toewijzen aan een gebruikersaccount, moet u een gebruikslocatie toewijzen.</span><span class="sxs-lookup"><span data-stu-id="bfb71-129">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="bfb71-130">Voer de volgende opdracht uit om de User Principal-naam van uw gebruikersaccounts weer te geven.</span><span class="sxs-lookup"><span data-stu-id="bfb71-130">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="bfb71-131">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="bfb71-131">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="bfb71-132">Alle informatie over de gebruikersaccounts (**Get-AzureADUser**) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bfb71-132">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bfb71-133">De lijst met gebruikersnamen alfabetisch sorteren (**Sorteer de userPrincipalName**) en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bfb71-133">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bfb71-134">Alleen de eigenschap voor de User Principal name weergeven voor elk account (**Selecteer userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="bfb71-134">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

- <span data-ttu-id="bfb71-135">Toon ze één scherm voor één keer (**meer**).</span><span class="sxs-lookup"><span data-stu-id="bfb71-135">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="bfb71-136">Met deze opdracht worden al uw accounts weergegeven.</span><span class="sxs-lookup"><span data-stu-id="bfb71-136">This command will list all of your accounts.</span></span> <span data-ttu-id="bfb71-137">Als u de User Principal-naam van een account wilt weergeven op basis van de naam van de persoon (voor-en achternaam), vult u de **$username** variabele onder (verwijdert \< and > u de tekens) en voert u de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="bfb71-137">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="bfb71-138">In dit voorbeeld wordt de User Principal name voor het gebruikersaccount weergegeven met de weergavenaam van Caleb Sills.</span><span class="sxs-lookup"><span data-stu-id="bfb71-138">This example displays the User Principal Name for the user account with the display name of Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="bfb71-139">Met behulp van een **$UPN** -variabele kunt u wijzigingen aanbrengen in afzonderlijke accounts op basis van de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="bfb71-139">By using a **$upn** variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="bfb71-140">Hier ziet u een voorbeeld van het instellen van de gebruikslocatie van Belinda Newman op Frankrijk, maar het opgeven van een weergavenaam in plaats van de naam van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="bfb71-140">Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="bfb71-141">Eigenschappen wijzigen voor alle gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="bfb71-141">Change properties for all user accounts</span></span>

<span data-ttu-id="bfb71-142">Als u de eigenschappen van alle gebruikers wilt wijzigen, kunt u de combinatie van de cmdlet **Get-AzureADUser** en **set-AzureADUser** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="bfb71-142">To change properties for all users, you can use the combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="bfb71-143">In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers gewijzigd in Frankrijk:</span><span class="sxs-lookup"><span data-stu-id="bfb71-143">The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="bfb71-144">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="bfb71-144">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="bfb71-145">Alle informatie over de gebruikersaccounts (**Get-AzureADUser**) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bfb71-145">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bfb71-146">Stel de locatie van de gebruiker in op Frankrijk (**set-AzureADUser-UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="bfb71-146">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="bfb71-147">Eigenschappen wijzigen voor een bepaalde groep gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="bfb71-147">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="bfb71-148">Als u de eigenschappen van een bepaalde groep gebruikersaccount wilt wijzigen, kunt u de combinatie van de cmdlet **Get-AzureADUser**, **where**en **set-AzureADUser** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="bfb71-148">To change properties for a specific set of user account, you can use the combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="bfb71-149">In het volgende voorbeeld wordt de gebruikslocatie van alle gebruikers in de afdeling financieel medewerkers gewijzigd in Frankrijk:</span><span class="sxs-lookup"><span data-stu-id="bfb71-149">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="bfb71-150">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="bfb71-150">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="bfb71-151">Alle informatie over de gebruikersaccounts (**Get-AzureADUser**) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bfb71-151">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bfb71-152">Zoek alle gebruikersaccounts waarvan de afdelings eigenschap is ingesteld op ' Accounting ' (**waarbij {$ _. Afdeling-EQ "accounting"}**) en stuurt de resultaten naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bfb71-152">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="bfb71-153">Stel de locatie van de gebruiker in op Frankrijk (**set-AzureADUser-UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="bfb71-153">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="bfb71-154">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="bfb71-154">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="bfb71-155">Voor het configureren van eigenschappen voor gebruikersaccounts met de Microsoft Azure Active Directory-module voor Windows PowerShell gebruikt u de cmdlet **set-MsolUser** en geeft u de eigenschappen op die u wilt instellen of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="bfb71-155">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, you use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="bfb71-156">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="bfb71-156">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="bfb71-157">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="bfb71-157">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="bfb71-158">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfb71-158">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="bfb71-159">Eigenschappen van een specifiek gebruikersaccount wijzigen</span><span class="sxs-lookup"><span data-stu-id="bfb71-159">Change properties for a specific user account</span></span>

<span data-ttu-id="bfb71-160">Als u de eigenschappen voor een specifiek gebruikersaccount wilt configureren, gebruikt u de cmdlet [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) en geeft u de eigenschappen op die u wilt instellen of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="bfb71-160">To configure properties for a specific user account, you use the [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="bfb71-161">U identificeert het account met de parameter **-userPrincipalName** en stelt of wijzigt specifieke eigenschappen met aanvullende parameters.</span><span class="sxs-lookup"><span data-stu-id="bfb71-161">You identify the account with the **-UserPrincipalName** parameter and set or change specific properties with additional parameters.</span></span> <span data-ttu-id="bfb71-162">Hier volgt een lijst met de meest voorkomende parameters.</span><span class="sxs-lookup"><span data-stu-id="bfb71-162">Here is a list of the most common parameters.</span></span>
  
- <span data-ttu-id="bfb71-163">-Plaats " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-163">-City "\<city name>"</span></span>
    
- <span data-ttu-id="bfb71-164">-Land " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-164">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="bfb71-165">-Afdeling " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-165">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="bfb71-166">Naam van een \<full user name> '</span><span class="sxs-lookup"><span data-stu-id="bfb71-166">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="bfb71-167">-Fax " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-167">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="bfb71-168">-Voornaam " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-168">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="bfb71-169">-Achternaam " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-169">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="bfb71-170">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-170">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="bfb71-171">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-171">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="bfb71-172">-PhoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-172">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="bfb71-173">-Postcode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-173">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="bfb71-174">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-174">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="bfb71-175">-Status " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-175">-State "\<state name>"</span></span>
    
- <span data-ttu-id="bfb71-176">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-176">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="bfb71-177">-Titel " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-177">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="bfb71-178">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="bfb71-178">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="bfb71-179">Dit is de ISO 3166-1 alfa-2 (a2) land-of regiocode van twee letters.</span><span class="sxs-lookup"><span data-stu-id="bfb71-179">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="bfb71-180">Zie [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) voor aanvullende parameters.</span><span class="sxs-lookup"><span data-stu-id="bfb71-180">See [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) for additional parameters.</span></span>

<span data-ttu-id="bfb71-181">Voer de volgende opdracht uit om de hoofdnamen van gebruikers weer te geven voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="bfb71-181">To see the User Principal Names of all your users, run the following command.</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="bfb71-182">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="bfb71-182">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="bfb71-183">Alle informatie over de gebruikersaccounts (**Get-MsolUser**) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bfb71-183">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bfb71-184">De lijst met gebruikersnamen alfabetisch sorteren (**Sorteer de userPrincipalName**) en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bfb71-184">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bfb71-185">Alleen de eigenschap voor de User Principal name weergeven voor elk account (**Selecteer userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="bfb71-185">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
- <span data-ttu-id="bfb71-186">Toon ze één scherm voor één keer (**meer**).</span><span class="sxs-lookup"><span data-stu-id="bfb71-186">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="bfb71-187">Met deze opdracht worden al uw accounts weergegeven.</span><span class="sxs-lookup"><span data-stu-id="bfb71-187">This command will list all of your accounts.</span></span> <span data-ttu-id="bfb71-188">Als u de User Principal-naam van een account wilt weergeven op basis van de naam van de persoon (voor-en achternaam), vult u de **$username** variabele onder (verwijdert \< and > u de tekens) en voert u de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="bfb71-188">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="bfb71-189">In dit voorbeeld wordt de User Principal name weergegeven voor de gebruiker met de naam Caleb Sills.</span><span class="sxs-lookup"><span data-stu-id="bfb71-189">This example displays the User Principal Name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="bfb71-190">Met behulp van een **$UPN** -variabele kunt u wijzigingen aanbrengen in afzonderlijke accounts op basis van de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="bfb71-190">By using a **$upn** variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="bfb71-191">Hier ziet u een voorbeeld van het instellen van de gebruikslocatie van Belinda Newman op Frankrijk, maar het opgeven van een weergavenaam in plaats van de naam van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="bfb71-191">Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="bfb71-192">Eigenschappen wijzigen voor alle gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="bfb71-192">Change properties for all user accounts</span></span>

<span data-ttu-id="bfb71-193">Als u de eigenschappen van alle gebruikers wilt wijzigen, kunt u de combinatie van de cmdlet **Get-MsolUser** en **set-MsolUser** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="bfb71-193">To change properties for all users, you can use the combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="bfb71-194">In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers gewijzigd in Frankrijk:</span><span class="sxs-lookup"><span data-stu-id="bfb71-194">The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="bfb71-195">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="bfb71-195">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="bfb71-196">Alle informatie over de gebruikersaccounts (**Get-MsolUser**) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bfb71-196">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bfb71-197">Stel de locatie van de gebruiker in op Frankrijk (**set-MsolUser-UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="bfb71-197">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="bfb71-198">Eigenschappen wijzigen voor een bepaalde groep gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="bfb71-198">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="bfb71-199">Als u de eigenschappen van een bepaalde groep gebruikersaccount wilt wijzigen, kunt u de combinatie van de cmdlet **Get-MsolUser**, **where**en **set-MsolUser** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="bfb71-199">To change properties for a specific set of user account, you can use the combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="bfb71-200">In het volgende voorbeeld wordt de gebruikslocatie van alle gebruikers in de afdeling financieel medewerkers gewijzigd in Frankrijk:</span><span class="sxs-lookup"><span data-stu-id="bfb71-200">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="bfb71-201">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="bfb71-201">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="bfb71-202">Alle informatie over de gebruikersaccounts (**Get-MsolUser**) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bfb71-202">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bfb71-203">Zoek alle gebruikersaccounts waarvan de afdelings eigenschap is ingesteld op ' Accounting ' (**waarbij {$ _. Afdeling-EQ "accounting"}**) en stuurt de resultaten naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bfb71-203">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="bfb71-204">Stel de locatie van de gebruiker in op Frankrijk (**set-MsolUser-UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="bfb71-204">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>


## <a name="see-also"></a><span data-ttu-id="bfb71-205">Zie ook</span><span class="sxs-lookup"><span data-stu-id="bfb71-205">See also</span></span>

[<span data-ttu-id="bfb71-206">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfb71-206">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="bfb71-207">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfb71-207">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="bfb71-208">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bfb71-208">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
