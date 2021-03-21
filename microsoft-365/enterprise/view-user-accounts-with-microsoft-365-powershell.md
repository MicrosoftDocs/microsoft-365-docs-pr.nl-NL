---
title: Microsoft 365-gebruikersaccounts weergeven met PowerShell
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: Meer informatie over het weergeven, weergeven of weergeven van uw Microsoft 365-gebruikersaccounts op verschillende manieren met PowerShell.
ms.openlocfilehash: de91195afeb8480bf231d9536e4b3a94502a6da1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924646"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="3656a-103">Microsoft 365-gebruikersaccounts weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="3656a-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="3656a-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="3656a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3656a-105">U kunt het Microsoft 365-beheercentrum gebruiken om de accounts voor uw Microsoft 365-tenant te bekijken.</span><span class="sxs-lookup"><span data-stu-id="3656a-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="3656a-106">PowerShell voor Microsoft 365 maakt dit mogelijk, maar biedt ook extra functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="3656a-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="3656a-107">De Azure Active Directory PowerShell voor Graph-module gebruiken</span><span class="sxs-lookup"><span data-stu-id="3656a-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="3656a-108">Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="3656a-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="3656a-109">Alle accounts weergeven</span><span class="sxs-lookup"><span data-stu-id="3656a-109">View all accounts</span></span>

<span data-ttu-id="3656a-110">Voer deze opdracht uit om de volledige lijst met gebruikersaccounts weer te geven:</span><span class="sxs-lookup"><span data-stu-id="3656a-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="3656a-111">U krijgt ongeveer dezelfde informatie:</span><span class="sxs-lookup"><span data-stu-id="3656a-111">You should get information similar to this:</span></span>
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a><span data-ttu-id="3656a-112">Een specifiek account weergeven</span><span class="sxs-lookup"><span data-stu-id="3656a-112">View a specific account</span></span>

<span data-ttu-id="3656a-113">Voer de volgende opdracht uit om een specifiek gebruikersaccount weer te geven.</span><span class="sxs-lookup"><span data-stu-id="3656a-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="3656a-114">Vul de naam van het aanmeldingsaccount in van het gebruikersaccount, dat ook wel de gebruikersnaam (UPN) wordt genoemd.</span><span class="sxs-lookup"><span data-stu-id="3656a-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="3656a-115">Verwijder de tekens '<' en '>'.</span><span class="sxs-lookup"><span data-stu-id="3656a-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="3656a-116">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="3656a-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="3656a-117">Aanvullende eigenschapswaarden voor een specifiek account weergeven</span><span class="sxs-lookup"><span data-stu-id="3656a-117">View additional property values for a specific account</span></span>

<span data-ttu-id="3656a-118">Standaard worden in **de get-AzureADUser-cmdlet** alleen de *eigenschappen ObjectID,* *DisplayName* en *UserPrincipalName van* accounts weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3656a-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="3656a-119">Als u selectiever wilt zijn over  de eigenschappen die moeten worden weergegeven, gebruikt u de cmdlet Selecteren in combinatie met de **cmdlet Get-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="3656a-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="3656a-120">Als u de twee cmdlets wilt combineren, gebruikt u het teken 'pipe' ('|'), waarmee Azure Active Directory PowerShell voor Graph de resultaten van één opdracht krijgt en deze naar de volgende opdracht verzendt.</span><span class="sxs-lookup"><span data-stu-id="3656a-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="3656a-121">Hier ziet u een voorbeeldopdracht met de *weergavenaam,* *afdeling* en *Gebruikslocatie* voor elk gebruikersaccount:</span><span class="sxs-lookup"><span data-stu-id="3656a-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="3656a-122">Met deze opdracht wordt PowerShell instructies gegeven voor:</span><span class="sxs-lookup"><span data-stu-id="3656a-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="3656a-123">Ontvang alle informatie over de gebruikersaccounts **(Get-AzureADUser)** en stuur deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="3656a-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="3656a-124">Alleen de gebruikersnaam, de afdeling en de gebruikslocatie weergeven **(Selecteer DisplayName, Afdeling, UsageLocation).**</span><span class="sxs-lookup"><span data-stu-id="3656a-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="3656a-125">Als u alle eigenschappen voor een specifiek gebruikersaccount wilt zien, gebruikt u **de** cmdlet Selecteren en het jokerteken (\*).</span><span class="sxs-lookup"><span data-stu-id="3656a-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="3656a-126">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="3656a-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="3656a-127">Voer als een ander voorbeeld de volgende opdracht uit om de ingeschakelde status van een specifiek gebruikersaccount te controleren:</span><span class="sxs-lookup"><span data-stu-id="3656a-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="3656a-128">Accountsynchronisatiestatus weergeven</span><span class="sxs-lookup"><span data-stu-id="3656a-128">View account synchronization status</span></span>

<span data-ttu-id="3656a-129">Gebruikersaccounts hebben twee bronnen:</span><span class="sxs-lookup"><span data-stu-id="3656a-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="3656a-130">Windows Server Active Directory (AD), accounts die worden gesynchroniseerd van on-premises AD naar de cloud.</span><span class="sxs-lookup"><span data-stu-id="3656a-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="3656a-131">Azure Active Directory(Azure AD) AD-accounts, die rechtstreeks in de cloud worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="3656a-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="3656a-132">De volgende opdracht geeft PowerShell opdracht om alle gebruikers te krijgen die het kenmerk *DirSyncEnabled* hebben ingesteld op *Waar.*</span><span class="sxs-lookup"><span data-stu-id="3656a-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="3656a-133">U kunt het gebruiken om accounts te zoeken die worden gesynchroniseerd vanuit on-premises AD.</span><span class="sxs-lookup"><span data-stu-id="3656a-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="3656a-134">De volgende opdracht geeft PowerShell opdracht om alle gebruikers te krijgen die het kenmerk *DirSyncEnabled* hebben ingesteld op *Onwaar.*</span><span class="sxs-lookup"><span data-stu-id="3656a-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="3656a-135">U kunt het gebruiken om alleen-cloudaccounts te zoeken.</span><span class="sxs-lookup"><span data-stu-id="3656a-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="3656a-136">Accounts weergeven op basis van een gemeenschappelijke eigenschap</span><span class="sxs-lookup"><span data-stu-id="3656a-136">View accounts based on a common property</span></span>

<span data-ttu-id="3656a-137">Als u selectiever wilt zijn over de lijst met accounts die u wilt weergeven, kunt u de cmdlet **Where** gebruiken in combinatie met de **get-AzureADUser-cmdlet.**</span><span class="sxs-lookup"><span data-stu-id="3656a-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="3656a-138">Als u de twee cmdlets wilt combineren, gebruikt u het teken 'pipe' ('|'), waarmee Azure Active Directory PowerShell voor Graph de resultaten van één opdracht krijgt en deze naar de volgende opdracht verzendt.</span><span class="sxs-lookup"><span data-stu-id="3656a-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="3656a-139">Hier ziet u een voorbeeldopdracht die alleen de gebruikersaccounts wekt die een niet-gespecificeerde gebruikslocatie hebben:</span><span class="sxs-lookup"><span data-stu-id="3656a-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="3656a-140">Met deze opdracht geeft Azure Active Directory PowerShell voor Graph instructies voor:</span><span class="sxs-lookup"><span data-stu-id="3656a-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="3656a-141">Ontvang alle informatie over de gebruikersaccounts **(Get-AzureADUser)** en stuur deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="3656a-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="3656a-142">Zoek alle gebruikersaccounts met een niet-gespecificeerde gebruikslocatie (**Where {$ \_ . UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="3656a-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="3656a-143">In de accolades geeft de opdracht PowerShell de opdracht alleen de set accounts te vinden waarvoor de eigenschap Gebruikersaccount UsageLocation **$ \_ (. UsageLocation**) is niet opgegeven (**-eq $Null).**</span><span class="sxs-lookup"><span data-stu-id="3656a-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="3656a-144">De **eigenschap UsageLocation** is slechts een van de vele eigenschappen die zijn gekoppeld aan een gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="3656a-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="3656a-145">Als u alle eigenschappen voor een specifiek gebruikersaccount wilt weergeven, gebruikt u **de** cmdlet Selecteren en het jokerteken (\*).</span><span class="sxs-lookup"><span data-stu-id="3656a-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="3656a-146">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="3656a-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="3656a-147">Plaats is **bijvoorbeeld de** naam van een eigenschap van een gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="3656a-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="3656a-148">U kunt de volgende opdracht gebruiken om alle accounts weer te geven van gebruikers die in Londen wonen:</span><span class="sxs-lookup"><span data-stu-id="3656a-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="3656a-149">De syntaxis voor de **cmdlet** Where in deze voorbeelden is **Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="3656a-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="3656a-150">[naam van de eigenschap gebruikersaccount] [vergelijkingsoperator] [waarde] **}**.> [vergelijkingsoperator] is **-eq** voor gelijken, **-ne** voor niet gelijk aan, **-lt** voor minder dan, **-gt** voor groter dan en andere.</span><span class="sxs-lookup"><span data-stu-id="3656a-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="3656a-151">[waarde] is meestal een tekenreeks (een reeks letters, getallen en andere  tekens), een numerieke waarde of $Null voor niet-gespecificeerde tekens.</span><span class="sxs-lookup"><span data-stu-id="3656a-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="3656a-152">Zie Where [.](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="3656a-152">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="3656a-153">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="3656a-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="3656a-154">Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="3656a-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="3656a-155">Alle accounts weergeven</span><span class="sxs-lookup"><span data-stu-id="3656a-155">View all accounts</span></span>

<span data-ttu-id="3656a-156">Voer deze opdracht uit om de volledige lijst met gebruikersaccounts weer te geven:</span><span class="sxs-lookup"><span data-stu-id="3656a-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="3656a-157">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in hun naam.</span><span class="sxs-lookup"><span data-stu-id="3656a-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="3656a-158">Voer deze cmdlets uit vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3656a-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="3656a-159">U krijgt ongeveer dezelfde informatie:</span><span class="sxs-lookup"><span data-stu-id="3656a-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="3656a-160">De **get-MsolUser-cmdlet** bevat ook een set parameters om de weergegeven set gebruikersaccounts te filteren.</span><span class="sxs-lookup"><span data-stu-id="3656a-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="3656a-161">Voer bijvoorbeeld de volgende opdracht uit voor de lijst met gebruikers zonder licentie (gebruikers die zijn toegevoegd aan Microsoft 365, maar nog geen licentie hebben gekregen om een van de services te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="3656a-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="3656a-162">U krijgt ongeveer dezelfde informatie:</span><span class="sxs-lookup"><span data-stu-id="3656a-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="3656a-163">Zie [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100))voor informatie over aanvullende parameters voor het filteren van de set gebruikersaccounts die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3656a-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="3656a-164">Een specifiek account weergeven</span><span class="sxs-lookup"><span data-stu-id="3656a-164">View a specific account</span></span>

<span data-ttu-id="3656a-165">Voer de volgende opdracht uit om een specifiek gebruikersaccount weer te geven.</span><span class="sxs-lookup"><span data-stu-id="3656a-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="3656a-166">Vul de aanmeldingsnaam in van het gebruikersaccount, dat ook wel de gebruikersnaam (UPN) wordt genoemd.</span><span class="sxs-lookup"><span data-stu-id="3656a-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="3656a-167">Verwijder de tekens '<' en '>'.</span><span class="sxs-lookup"><span data-stu-id="3656a-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="3656a-168">Accounts weergeven op basis van een gemeenschappelijke eigenschap</span><span class="sxs-lookup"><span data-stu-id="3656a-168">View accounts based on a common property</span></span>

<span data-ttu-id="3656a-169">Als u selectiever wilt zijn over de lijst met accounts die u wilt weergeven, kunt u de cmdlet **Where** gebruiken in combinatie met de **get-MsolUser-cmdlet.**</span><span class="sxs-lookup"><span data-stu-id="3656a-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="3656a-170">Als u de twee cmdlets wilt combineren, gebruikt u het teken 'pipe' ("|"), waarmee PowerShell wordt verteld dat de resultaten van één opdracht moeten worden genomen en naar de volgende opdracht moeten worden doorsturen.</span><span class="sxs-lookup"><span data-stu-id="3656a-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="3656a-171">Hier ziet u een voorbeeld van alleen gebruikersaccounts met een niet-gespecificeerde gebruikslocatie:</span><span class="sxs-lookup"><span data-stu-id="3656a-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="3656a-172">Met deze opdracht wordt PowerShell instructies gegeven voor:</span><span class="sxs-lookup"><span data-stu-id="3656a-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="3656a-173">Ontvang alle informatie over de gebruikersaccounts **(Get-MsolUser)** en stuur deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="3656a-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="3656a-174">Zoek alle gebruikersaccounts met een niet-gespecificeerde gebruikslocatie (**Where {$ \_ . UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="3656a-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="3656a-175">In de accolades geeft de opdracht PowerShell opdracht om alleen de set accounts te zoeken waarvoor de eigenschap Gebruikersaccount UsageLocation **$ \_ (. UsageLocation**) is niet opgegeven (**-eq $Null).**</span><span class="sxs-lookup"><span data-stu-id="3656a-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="3656a-176">U krijgt ongeveer dezelfde informatie:</span><span class="sxs-lookup"><span data-stu-id="3656a-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="3656a-177">De *eigenschap UsageLocation* is slechts een van de vele eigenschappen die zijn gekoppeld aan een gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="3656a-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="3656a-178">Als u alle eigenschappen voor gebruikersaccounts wilt zien, gebruikt u de **cmdlet** Selecteren en het jokerteken (\*) om ze allemaal weer te geven voor een specifiek gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="3656a-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="3656a-179">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="3656a-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="3656a-180">Plaats is *bijvoorbeeld de* naam van een eigenschap van een gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="3656a-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="3656a-181">U kunt de volgende opdracht gebruiken om alle gebruikersaccounts weer te geven voor gebruikers die in Londen wonen:</span><span class="sxs-lookup"><span data-stu-id="3656a-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="3656a-182">De syntaxis voor de **cmdlet** Where in deze voorbeelden is **Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="3656a-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="3656a-183">[naam van de eigenschap gebruikersaccount] [vergelijkingsoperator] [waarde] **}**.</span><span class="sxs-lookup"><span data-stu-id="3656a-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="3656a-184">[vergelijkingsoperator] is **-eq** voor gelijken, **-ne** voor niet gelijk aan, **-lt** voor kleiner dan, **-gt** voor groter dan, en anderen.</span><span class="sxs-lookup"><span data-stu-id="3656a-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="3656a-185">[waarde] is meestal een tekenreeks (een reeks letters, getallen en andere  tekens), een numerieke waarde of $Null voor niet-gespecificeerde tekens.</span><span class="sxs-lookup"><span data-stu-id="3656a-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="3656a-186">Zie Where [.](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="3656a-186">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  
<span data-ttu-id="3656a-187">Als u de geblokkeerde status van een gebruikersaccount wilt controleren, gebruikt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="3656a-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="3656a-188">Aanvullende eigenschapswaarden voor accounts weergeven</span><span class="sxs-lookup"><span data-stu-id="3656a-188">View additional property values for accounts</span></span>

<span data-ttu-id="3656a-189">Standaard worden deze drie eigenschappen van gebruikersaccounts weergegeven op de **get-MsolUser-cmdlet:**</span><span class="sxs-lookup"><span data-stu-id="3656a-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="3656a-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="3656a-190">UserPrincipalName</span></span>
    
- <span data-ttu-id="3656a-191">Weergavenaam</span><span class="sxs-lookup"><span data-stu-id="3656a-191">DisplayName</span></span>
    
- <span data-ttu-id="3656a-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="3656a-192">isLicensed</span></span>
    
<span data-ttu-id="3656a-193">Als u extra eigenschappen nodig hebt, zoals de afdeling waar de gebruiker werkt en het land/de regio waar de gebruiker  Microsoft 365-services gebruikt, kunt u **Get-MsolUser** uitvoeren in combinatie met de cmdlet Selecteren om de lijst met gebruikersaccounteigenschappen op te geven.</span><span class="sxs-lookup"><span data-stu-id="3656a-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="3656a-194">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="3656a-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="3656a-195">Met deze opdracht wordt PowerShell instructies gegeven voor:</span><span class="sxs-lookup"><span data-stu-id="3656a-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="3656a-196">Ontvang alle informatie over de gebruikersaccounts **(Get-MsolUser)** en stuur deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="3656a-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="3656a-197">Alleen de gebruikersnaam, de afdeling en de gebruikslocatie weergeven **(Selecteer DisplayName, Afdeling, UsageLocation).**</span><span class="sxs-lookup"><span data-stu-id="3656a-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="3656a-198">U krijgt ongeveer dezelfde informatie:</span><span class="sxs-lookup"><span data-stu-id="3656a-198">You should get information similar to this:</span></span>
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

<span data-ttu-id="3656a-199">Met **de** cmdlet Selecteren kunt u kiezen welke eigenschappen u wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="3656a-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="3656a-200">Als u alle eigenschappen voor een specifiek gebruikersaccount wilt weergeven, gebruikt u het jokerteken (\*).</span><span class="sxs-lookup"><span data-stu-id="3656a-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="3656a-201">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="3656a-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="3656a-202">Als u selectiever wilt zijn over de lijst met accounts die u wilt weergeven, kunt u ook de cmdlet **Where** gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3656a-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="3656a-203">Hier ziet u een voorbeeldopdracht die alleen de gebruikersaccounts wekt die een niet-gespecificeerde gebruikslocatie hebben:</span><span class="sxs-lookup"><span data-stu-id="3656a-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="3656a-204">Met deze opdracht wordt PowerShell instructies gegeven voor:</span><span class="sxs-lookup"><span data-stu-id="3656a-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="3656a-205">Ontvang alle informatie over de gebruikersaccounts **(Get-MsolUser)** en stuur deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="3656a-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="3656a-206">Zoek alle gebruikersaccounts met een niet-gespecificeerde gebruikslocatie (**Where {$ \_ . UsageLocation -eq $Null} )** en stuur de resulterende informatie naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="3656a-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="3656a-207">In de accolades geeft de opdracht PowerShell de opdracht alleen de set accounts te vinden waarvoor de eigenschap Gebruikersaccount UsageLocation **$ \_ (. UsageLocation**) is niet opgegeven (**-eq $Null).**</span><span class="sxs-lookup"><span data-stu-id="3656a-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="3656a-208">Alleen de gebruikersnaam, de afdeling en de gebruikslocatie weergeven **(Selecteer DisplayName, Afdeling, UsageLocation).**</span><span class="sxs-lookup"><span data-stu-id="3656a-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="3656a-209">U krijgt ongeveer dezelfde informatie:</span><span class="sxs-lookup"><span data-stu-id="3656a-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="3656a-210">Als u adreslijstsynchronisatie gebruikt om uw Microsoft 365-gebruikers te maken en te beheren, kunt u het lokale account weergeven waaruit een Microsoft 365-gebruiker is geprojecteerd.</span><span class="sxs-lookup"><span data-stu-id="3656a-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="3656a-211">In het volgende voorbeeld wordt ervan uitgenomen dat:</span><span class="sxs-lookup"><span data-stu-id="3656a-211">The following example assumes that:</span></span>

- <span data-ttu-id="3656a-212">Azure AD Connect is geconfigureerd om het standaardbronanker van ObjectGUID te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3656a-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="3656a-213">(Zie [Azure AD Connect: Ontwerpconcepten](/azure/active-directory/hybrid/plan-connect-design-concepts)voor meer informatie over het configureren van een bronanker.</span><span class="sxs-lookup"><span data-stu-id="3656a-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="3656a-214">De Active Directory Domain Services-module voor PowerShell is geïnstalleerd (zie [RSAT-hulpprogramma's).](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)</span><span class="sxs-lookup"><span data-stu-id="3656a-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="3656a-215">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3656a-215">See also</span></span>

[<span data-ttu-id="3656a-216">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="3656a-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3656a-217">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="3656a-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3656a-218">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3656a-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)