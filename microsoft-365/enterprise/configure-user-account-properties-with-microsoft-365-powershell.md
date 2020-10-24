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
description: Gebruik PowerShell voor Microsoft 365 om eigenschappen van afzonderlijke of meerdere gebruikersaccounts in uw Microsoft 365-Tenant te configureren.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754326"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="9e629-103">Eigenschappen van Microsoft 365-gebruikersaccounts configureren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e629-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="9e629-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9e629-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9e629-105">Met het Microsoft 365-Beheercentrum kunt u de eigenschappen van de gebruikersaccounts van uw Microsoft 365-Tenant configureren.</span><span class="sxs-lookup"><span data-stu-id="9e629-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="9e629-106">In PowerShell kunt u dit ook doen, en wel wat andere dingen die u niet kunt doen in het Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="9e629-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="9e629-107">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="9e629-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="9e629-108">Als u de eigenschappen van gebruikersaccounts in de module Azure Active Directory PowerShell voor Graph wilt configureren, gebruikt u de cmdlet [**set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) en geeft u de eigenschappen op die u wilt instellen of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9e629-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="9e629-109">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="9e629-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="9e629-110">Eigenschappen van een specifiek gebruikersaccount wijzigen</span><span class="sxs-lookup"><span data-stu-id="9e629-110">Change properties for a specific user account</span></span>

<span data-ttu-id="9e629-111">U identificeert het account met de parameter *-ObjectID* en stelt of wijzigt specifieke eigenschappen met behulp van aanvullende parameters.</span><span class="sxs-lookup"><span data-stu-id="9e629-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="9e629-112">Hier volgt een lijst met de meest voorkomende parameters:</span><span class="sxs-lookup"><span data-stu-id="9e629-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="9e629-113">-Afdeling " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="9e629-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="9e629-114">Naam van een \<full user name> '</span><span class="sxs-lookup"><span data-stu-id="9e629-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="9e629-115">-FacsimilieTelephoneNumber " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="9e629-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="9e629-116">-Benaming " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="9e629-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="9e629-117">-Achternaam " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="9e629-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="9e629-118">-Mobiel " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="9e629-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="9e629-119">-JobTitle \<job title></span><span class="sxs-lookup"><span data-stu-id="9e629-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="9e629-120">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="9e629-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="9e629-121">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="9e629-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="9e629-122">-Plaats " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="9e629-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="9e629-123">-Status " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="9e629-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="9e629-124">-Postcode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="9e629-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="9e629-125">-Land " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="9e629-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="9e629-126">-TelephoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="9e629-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="9e629-127">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="9e629-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="9e629-128">Dit is de ISO 3166-1 alfa-2 (a2) land-of regiocode van twee letters.</span><span class="sxs-lookup"><span data-stu-id="9e629-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="9e629-129">Zie [set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) voor aanvullende parameters.</span><span class="sxs-lookup"><span data-stu-id="9e629-129">For additional parameters, see [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="9e629-130">Voordat u licenties kunt toewijzen aan een gebruikersaccount, moet u een gebruikslocatie toewijzen.</span><span class="sxs-lookup"><span data-stu-id="9e629-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="9e629-131">Voer de volgende opdracht uit om de User Principal-naam van uw gebruikersaccounts weer te geven.</span><span class="sxs-lookup"><span data-stu-id="9e629-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="9e629-132">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="9e629-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="9e629-133">U ontvangt alle informatie in de gebruikersaccounts (**Get-AzureADUser**) en stuurt u deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="9e629-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="9e629-134">De lijst met gebruikersnamen alfabetisch sorteren (**Sorteer de userPrincipalName**) en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="9e629-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="9e629-135">Alleen de eigenschap voor de User Principal name weergeven voor elk account (**Selecteer userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="9e629-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="9e629-136">Toon ze één scherm voor één keer (**meer**).</span><span class="sxs-lookup"><span data-stu-id="9e629-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="9e629-137">Voer de volgende opdrachten uit om de User Principal-naam van een account weer te geven op basis van de weergavenaam (voornaam en achternaam).</span><span class="sxs-lookup"><span data-stu-id="9e629-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="9e629-138">Voer de *$username* variabele in en verwijder de \< and > tekens:</span><span class="sxs-lookup"><span data-stu-id="9e629-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="9e629-139">In dit voorbeeld wordt de User Principal name weergegeven voor het gebruikersaccount met de weergavenaam *Caleb Sills*.</span><span class="sxs-lookup"><span data-stu-id="9e629-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="9e629-140">Met behulp van een *$UPN* -variabele kunt u wijzigingen aanbrengen in afzonderlijke accounts op basis van de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="9e629-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="9e629-141">Hier ziet u een voorbeeld waarin de gebruikslocatie van *Belinda Newman*wordt ingesteld op Frankrijk.</span><span class="sxs-lookup"><span data-stu-id="9e629-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="9e629-142">Maar geeft de naam van de gebruikersnaam in plaats van de UPN van de gebruikersnaam aan.</span><span class="sxs-lookup"><span data-stu-id="9e629-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="9e629-143">Eigenschappen wijzigen voor alle gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="9e629-143">Change properties for all user accounts</span></span>

<span data-ttu-id="9e629-144">Als u de eigenschappen van alle gebruikers wilt wijzigen, kunt u een combinatie van de cmdlet **Get-AzureADUser** en **set-AzureADUser** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9e629-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="9e629-145">In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers gewijzigd in *Frankrijk*:</span><span class="sxs-lookup"><span data-stu-id="9e629-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="9e629-146">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="9e629-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="9e629-147">Alle informatie over de gebruikersaccounts (**Get-AzureADUser**) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="9e629-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="9e629-148">Stel de locatie van de gebruiker in op Frankrijk (**set-AzureADUser-UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="9e629-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="9e629-149">Eigenschappen wijzigen voor een bepaalde groep gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="9e629-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="9e629-150">Als u de eigenschappen van een bepaalde groep gebruikersaccounts wilt wijzigen, kunt u een combinatie van de cmdlet **Get-AzureADUser**, **where**en **set-AzureADUser** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9e629-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="9e629-151">In het volgende voorbeeld wordt de gebruikslocatie van alle gebruikers in de afdeling financieel medewerkers gewijzigd in *Frankrijk*:</span><span class="sxs-lookup"><span data-stu-id="9e629-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="9e629-152">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="9e629-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="9e629-153">Alle informatie over de gebruikersaccounts (**Get-AzureADUser**) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="9e629-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="9e629-154">Zoek alle gebruikersaccounts waarvan de *afdelings* eigenschap is ingesteld op ' Accounting ' (**waarbij {$ _. Afdeling-EQ "accounting"}**), en stuurt de daaruit verlichte informatie naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="9e629-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="9e629-155">Stel de locatie van de gebruiker in op Frankrijk (**set-AzureADUser-UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="9e629-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="9e629-156">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="9e629-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="9e629-157">Als u de eigenschappen van gebruikersaccounts met de Microsoft Azure Active Directory-module voor Windows PowerShell wilt configureren, gebruikt u de cmdlet **set-MsolUser** en geeft u de eigenschappen op die u wilt instellen of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9e629-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="9e629-158">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9e629-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="9e629-159">PowerShell core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met *MSOL* in de naam.</span><span class="sxs-lookup"><span data-stu-id="9e629-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="9e629-160">Voer de volgende cmdlets uit vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e629-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="9e629-161">Eigenschappen van een specifiek gebruikersaccount wijzigen</span><span class="sxs-lookup"><span data-stu-id="9e629-161">Change properties for a specific user account</span></span>

<span data-ttu-id="9e629-162">Als u de eigenschappen voor een specifiek gebruikersaccount wilt configureren, gebruikt u de cmdlet [**set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) en geeft u de eigenschappen op die u wilt instellen of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9e629-162">To configure properties for a specific user account, use the [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="9e629-163">U identificeert het account met de parameter *-userPrincipalName* en stelt of wijzigt specifieke eigenschappen met behulp van aanvullende parameters.</span><span class="sxs-lookup"><span data-stu-id="9e629-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="9e629-164">Hier volgt een lijst met de meest voorkomende parameters.</span><span class="sxs-lookup"><span data-stu-id="9e629-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="9e629-165">-Plaats " \<city name> "</span><span class="sxs-lookup"><span data-stu-id="9e629-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="9e629-166">-Land " \<country name> "</span><span class="sxs-lookup"><span data-stu-id="9e629-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="9e629-167">-Afdeling " \<department name> "</span><span class="sxs-lookup"><span data-stu-id="9e629-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="9e629-168">Naam van een \<full user name> '</span><span class="sxs-lookup"><span data-stu-id="9e629-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="9e629-169">-Fax " \<fax number> "</span><span class="sxs-lookup"><span data-stu-id="9e629-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="9e629-170">-Voornaam " \<user first name> "</span><span class="sxs-lookup"><span data-stu-id="9e629-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="9e629-171">-Achternaam " \<user last name> "</span><span class="sxs-lookup"><span data-stu-id="9e629-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="9e629-172">-MobilePhone " \<mobile phone number> "</span><span class="sxs-lookup"><span data-stu-id="9e629-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="9e629-173">-Office " \<office location> "</span><span class="sxs-lookup"><span data-stu-id="9e629-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="9e629-174">-PhoneNumber " \<office phone number> "</span><span class="sxs-lookup"><span data-stu-id="9e629-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="9e629-175">-Postcode " \<postal code> "</span><span class="sxs-lookup"><span data-stu-id="9e629-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="9e629-176">-PreferredLanguage " \<language> "</span><span class="sxs-lookup"><span data-stu-id="9e629-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="9e629-177">-Status " \<state name> "</span><span class="sxs-lookup"><span data-stu-id="9e629-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="9e629-178">-StreetAddress " \<street address> "</span><span class="sxs-lookup"><span data-stu-id="9e629-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="9e629-179">-Titel " \<title name> "</span><span class="sxs-lookup"><span data-stu-id="9e629-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="9e629-180">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="9e629-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="9e629-181">Dit is de ISO 3166-1 alfa-2 (a2) land-of regiocode van twee letters.</span><span class="sxs-lookup"><span data-stu-id="9e629-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="9e629-182">Zie [set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))voor aanvullende parameters.</span><span class="sxs-lookup"><span data-stu-id="9e629-182">For additional parameters, see [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="9e629-183">Voer de volgende opdracht uit om de hoofdnamen van gebruikers van alle gebruikers weer te geven:</span><span class="sxs-lookup"><span data-stu-id="9e629-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="9e629-184">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="9e629-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="9e629-185">Alle informatie voor de gebruikersaccounts (**Get-MsolUser**) weergeven en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="9e629-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="9e629-186">De lijst met gebruikersnamen alfabetisch sorteren (**Sorteer de userPrincipalName**) en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="9e629-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="9e629-187">Alleen de eigenschap voor de User Principal name weergeven voor elk account (**Selecteer userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="9e629-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="9e629-188">Toon ze één scherm voor één keer (**meer**).</span><span class="sxs-lookup"><span data-stu-id="9e629-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="9e629-189">Voer de volgende opdrachten uit om de User Principal-naam van een account weer te geven op basis van de weergavenaam (voornaam en achternaam).</span><span class="sxs-lookup"><span data-stu-id="9e629-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="9e629-190">Voer de *$username* variabele in en verwijder de \< and > tekens.</span><span class="sxs-lookup"><span data-stu-id="9e629-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="9e629-191">In dit voorbeeld wordt de User Principal name van de gebruiker met de naam Caleb Sills:</span><span class="sxs-lookup"><span data-stu-id="9e629-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="9e629-192">Met behulp van een *$UPN* -variabele kunt u wijzigingen aanbrengen in afzonderlijke accounts op basis van de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="9e629-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="9e629-193">Hier ziet u een voorbeeld waarin de gebruikslocatie van *Belinda Newman*wordt ingesteld op *Frankrijk*, maar geeft de naam van de gebruikersnaam in plaats van de UPN van de gebruikersnaam aan:</span><span class="sxs-lookup"><span data-stu-id="9e629-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="9e629-194">Eigenschappen wijzigen voor alle gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="9e629-194">Change properties for all user accounts</span></span>

<span data-ttu-id="9e629-195">Als u de eigenschappen van alle gebruikers wilt wijzigen, gebruikt u een combinatie van de cmdlet **Get-MsolUser** en **set-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="9e629-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="9e629-196">In het volgende voorbeeld wordt de gebruikslocatie voor alle gebruikers gewijzigd in *Frankrijk*:</span><span class="sxs-lookup"><span data-stu-id="9e629-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="9e629-197">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="9e629-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="9e629-198">Alle informatie voor de gebruikersaccounts (**Get-MsolUser**) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="9e629-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="9e629-199">Stel de locatie van de gebruiker in op Frankrijk (**set-MsolUser-UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="9e629-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="9e629-200">Eigenschappen wijzigen voor een bepaalde groep gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="9e629-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="9e629-201">Als u de eigenschappen van een bepaalde groep gebruikersaccounts wilt wijzigen, kunt u een combinatie van de cmdlet **Get-MsolUser**, **where**en **set-MsolUser** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9e629-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="9e629-202">In het volgende voorbeeld wordt de gebruikslocatie van alle gebruikers in de afdeling financieel medewerkers gewijzigd in *Frankrijk*:</span><span class="sxs-lookup"><span data-stu-id="9e629-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="9e629-203">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="9e629-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="9e629-204">Alle informatie voor de gebruikersaccounts (**Get-MsolUser**) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="9e629-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="9e629-205">Zoek alle gebruikersaccounts waarvan de *afdelings* eigenschap is ingesteld op ' Accounting ' (**waarbij {$ _. Afdeling-EQ "accounting"}**) en stuurt de resultaten naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="9e629-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="9e629-206">Stel de locatie van de gebruiker in op Frankrijk (**set-MsolUser-UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="9e629-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="9e629-207">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9e629-207">See also</span></span>

[<span data-ttu-id="9e629-208">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e629-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9e629-209">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e629-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9e629-210">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e629-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
