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
description: Meer informatie over het weergeven, weergeven en weergeven van uw Microsoft 365-gebruikersaccounts op verschillende manieren met PowerShell.
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754070"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="5a059-103">Microsoft 365-gebruikersaccounts weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a059-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="5a059-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5a059-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5a059-105">Met het Microsoft 365-Beheercentrum kunt u de accounts voor uw Microsoft 365-Tenant weergeven.</span><span class="sxs-lookup"><span data-stu-id="5a059-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="5a059-106">Met PowerShell voor Microsoft 365 kunt u dit maar ook extra functionaliteit bieden.</span><span class="sxs-lookup"><span data-stu-id="5a059-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="5a059-107">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="5a059-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="5a059-108">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="5a059-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="5a059-109">Alle accounts weergeven</span><span class="sxs-lookup"><span data-stu-id="5a059-109">View all accounts</span></span>

<span data-ttu-id="5a059-110">Voer de volgende opdracht uit om de volledige lijst met gebruikersaccounts weer te geven:</span><span class="sxs-lookup"><span data-stu-id="5a059-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="5a059-111">U ziet nu informatie over het volgende:</span><span class="sxs-lookup"><span data-stu-id="5a059-111">You should get information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="5a059-112">Een specifiek account weergeven</span><span class="sxs-lookup"><span data-stu-id="5a059-112">View a specific account</span></span>

<span data-ttu-id="5a059-113">Voer de volgende opdracht uit als u een specifiek gebruikersaccount wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="5a059-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="5a059-114">Vul de naam in van het aanmeldingsaccount van het gebruikersaccount dat ook wel de UPN (User Principal Name) wordt genoemd.</span><span class="sxs-lookup"><span data-stu-id="5a059-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="5a059-115">De tekens ' < ' en ' > ' verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5a059-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="5a059-116">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="5a059-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="5a059-117">Extra eigenschapswaarden voor een specifiek account weergeven</span><span class="sxs-lookup"><span data-stu-id="5a059-117">View additional property values for a specific account</span></span>

<span data-ttu-id="5a059-118">Standaard worden met de cmdlet **Get-AzureADUser** alleen de eigenschappen *ObjectID*, *DisplayName*en *userPrincipalName* van accounts weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5a059-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="5a059-119">Als u de eigenschappen die u wilt weergeven, verder wilt gebruiken, gebruikt u de cmdlet **Select** in combinatie met de cmdlet **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="5a059-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="5a059-120">Als u de twee cmdlets wilt combineren, gebruikt u het teken ' sluis ' (' | '), waarmee wordt aangegeven dat Azure Active Directory PowerShell voor Graph de resultaten van een opdracht oplevert en deze naar de volgende opdracht verzenden.</span><span class="sxs-lookup"><span data-stu-id="5a059-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="5a059-121">Hier ziet u een voorbeeld van een opdracht waarmee u de *naam*, *afdeling*en *UsageLocation* voor elke gebruikersaccount kunt weergeven:</span><span class="sxs-lookup"><span data-stu-id="5a059-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="5a059-122">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="5a059-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="5a059-123">U ontvangt alle informatie in de gebruikersaccounts (**Get-AzureADUser**) en stuurt u deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5a059-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="5a059-124">Alleen de naam, de afdeling en de gebruikslocatie van de gebruikersaccount weergeven (**Selecteer DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="5a059-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="5a059-125">Als u alle eigenschappen voor een specifiek gebruikersaccount wilt bekijken, gebruikt u de cmdlet **Select** en het jokerteken (\*).</span><span class="sxs-lookup"><span data-stu-id="5a059-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="5a059-126">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="5a059-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="5a059-127">Als u een ander voorbeeld, voert u de volgende opdracht uit om de ingeschakelde status van een specifiek gebruikersaccount in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="5a059-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="5a059-128">Synchronisatiestatus van een account weergeven</span><span class="sxs-lookup"><span data-stu-id="5a059-128">View account synchronization status</span></span>

<span data-ttu-id="5a059-129">Gebruikersaccounts hebben twee bronnen:</span><span class="sxs-lookup"><span data-stu-id="5a059-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="5a059-130">Windows Server Active Directory (AD), die accounts zijn die worden gesynchroniseerd vanuit on-premises advertenties met de Cloud.</span><span class="sxs-lookup"><span data-stu-id="5a059-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="5a059-131">AD-accounts van Azure Active Directory (Azure AD) die rechtstreeks in de cloud worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="5a059-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="5a059-132">Met de volgende opdracht wordt PowerShell geïnstrueerd voor alle gebruikers voor wie het kenmerk *DirSyncEnabled* is ingesteld op *waar*.</span><span class="sxs-lookup"><span data-stu-id="5a059-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="5a059-133">U kunt deze gebruiken om te zoeken naar accounts die worden gesynchroniseerd vanuit on-premises AD.</span><span class="sxs-lookup"><span data-stu-id="5a059-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="5a059-134">Met de volgende opdracht wordt PowerShell geïnstrueerd voor alle gebruikers voor wie het kenmerk *DirSyncEnabled* is ingesteld op *False*.</span><span class="sxs-lookup"><span data-stu-id="5a059-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="5a059-135">U kunt deze gebruiken om alleen Cloud accounts te zoeken.</span><span class="sxs-lookup"><span data-stu-id="5a059-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="5a059-136">Accounts weergeven op basis van een gemeenschappelijke eigenschap</span><span class="sxs-lookup"><span data-stu-id="5a059-136">View accounts based on a common property</span></span>

<span data-ttu-id="5a059-137">Als u een lijst wilt selecteren met de accounts die u wilt weergeven, kunt u de **where** -cmdlet gebruiken in combinatie met de cmdlet **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="5a059-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="5a059-138">Als u de twee cmdlets wilt combineren, gebruikt u het teken ' sluis ' (' | '), waarmee wordt aangegeven dat Azure Active Directory PowerShell voor Graph de resultaten van een opdracht oplevert en deze naar de volgende opdracht verzenden.</span><span class="sxs-lookup"><span data-stu-id="5a059-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="5a059-139">Hier ziet u een voorbeeld van een opdracht waarmee alleen gebruikersaccounts worden weergegeven met een niet-opgegeven gebruikslocatie:</span><span class="sxs-lookup"><span data-stu-id="5a059-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="5a059-140">Met deze opdracht krijgt u Azure Active Directory PowerShell voor Graph om het volgende te doen:</span><span class="sxs-lookup"><span data-stu-id="5a059-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="5a059-141">U ontvangt alle informatie in de gebruikersaccounts (**Get-AzureADUser**) en stuurt u deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5a059-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="5a059-142">Alle gebruikersaccounts zoeken met een niet-opgegeven gebruikslocatie (**waarbij {$ \_ . UsageLocation-EQ $Null}**).</span><span class="sxs-lookup"><span data-stu-id="5a059-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="5a059-143">Met de opdracht wordt in de accolades aangegeven dat PowerShell de accounts waarvan de eigenschap UsageLocation user account (\*\* $ \_ . UsageLocation**) is niet opgegeven (**-EQ $null\*\*).</span><span class="sxs-lookup"><span data-stu-id="5a059-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="5a059-144">De eigenschap **UsageLocation** is slechts een van de vele eigenschappen die aan een gebruikersaccount zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="5a059-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="5a059-145">Als u alle eigenschappen voor een specifiek gebruikersaccount wilt weergeven, gebruikt u de cmdlet **Select** en het jokerteken (\*).</span><span class="sxs-lookup"><span data-stu-id="5a059-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="5a059-146">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="5a059-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="5a059-147">**Plaats** is bijvoorbeeld de naam van een account eigenschap van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="5a059-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="5a059-148">Met de volgende opdracht kunt u een lijst weergeven met alle accounts van gebruikers die in Londen wonen:</span><span class="sxs-lookup"><span data-stu-id="5a059-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="5a059-149">De syntaxis voor de **where** -cmdlet in deze voorbeelden is **WHERE {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="5a059-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="5a059-150">[naam van eigenschap van gebruikersaccount] [vergelijkingsoperator] waardeparen **}**. > [vergelijkingsoperator] is **-EQ** voor gelijkteken, **-ne** voor niet gelijk aan,- **lt** voor kleiner dan, **-gt** voor groter dan, en overige.</span><span class="sxs-lookup"><span data-stu-id="5a059-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="5a059-151">[Value] is meestal een tekenreeks (een reeks letters, cijfers en andere tekens), een numerieke waarde of **$Null** voor niet-opgegeven waarde.</span><span class="sxs-lookup"><span data-stu-id="5a059-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="5a059-152">Zie [waar](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7), voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5a059-152">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="5a059-153">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="5a059-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="5a059-154">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5a059-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="5a059-155">Alle accounts weergeven</span><span class="sxs-lookup"><span data-stu-id="5a059-155">View all accounts</span></span>

<span data-ttu-id="5a059-156">Voer de volgende opdracht uit om de volledige lijst met gebruikersaccounts weer te geven:</span><span class="sxs-lookup"><span data-stu-id="5a059-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="5a059-157">PowerShell core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met *MSOL* in de naam.</span><span class="sxs-lookup"><span data-stu-id="5a059-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="5a059-158">Voer de volgende cmdlets uit vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a059-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="5a059-159">U ziet nu informatie over het volgende:</span><span class="sxs-lookup"><span data-stu-id="5a059-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="5a059-160">De cmdlet **Get-MsolUser** heeft ook een reeks parameters voor het filteren van de set gebruikersaccounts die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5a059-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="5a059-161">Als u bijvoorbeeld een lijst met gebruikers zonder licentie (gebruikers die zijn toegevoegd aan Microsoft 365 maar nog geen licentie hebt voor het gebruik van de Services), voert u deze opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="5a059-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="5a059-162">U ziet nu informatie over het volgende:</span><span class="sxs-lookup"><span data-stu-id="5a059-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="5a059-163">Zie [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100))voor meer informatie over aanvullende parameters voor het filteren van de set gebruikersaccounts die worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5a059-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="5a059-164">Een specifiek account weergeven</span><span class="sxs-lookup"><span data-stu-id="5a059-164">View a specific account</span></span>

<span data-ttu-id="5a059-165">Voer de volgende opdracht uit als u een specifiek gebruikersaccount wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="5a059-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="5a059-166">Voer de aanmeldingsnaam van het gebruikersaccount in, dat ook wel de UPN (User Principal Name) wordt genoemd.</span><span class="sxs-lookup"><span data-stu-id="5a059-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="5a059-167">De tekens ' < ' en ' > ' verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5a059-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="5a059-168">Accounts weergeven op basis van een gemeenschappelijke eigenschap</span><span class="sxs-lookup"><span data-stu-id="5a059-168">View accounts based on a common property</span></span>

<span data-ttu-id="5a059-169">Als u een lijst wilt selecteren met de accounts die u wilt weergeven, kunt u de **where** -cmdlet gebruiken in combinatie met de cmdlet **Get-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="5a059-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="5a059-170">Als u de twee cmdlets wilt combineren, gebruikt u het teken ' sluis ' (' | '), waarmee PowerShell de resultaten van één opdracht kan afronden en naar de volgende opdracht kunt verzenden.</span><span class="sxs-lookup"><span data-stu-id="5a059-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="5a059-171">Hier ziet u een voorbeeld waarin alleen gebruikersaccounts worden weergegeven met een niet-opgegeven gebruikslocatie:</span><span class="sxs-lookup"><span data-stu-id="5a059-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="5a059-172">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="5a059-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="5a059-173">U ontvangt alle informatie in de gebruikersaccounts (**Get-MsolUser**) en stuurt u deze naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5a059-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="5a059-174">Zoek alle gebruikersaccounts met een niet-opgegeven gebruikslocatie (**waarbij {$ \_ . UsageLocation-EQ $Null}**).</span><span class="sxs-lookup"><span data-stu-id="5a059-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="5a059-175">Met de opdracht wordt in PowerShell binnen de accolades gezocht naar de accounts waarvan de eigenschap UsageLocation (gebruikersaccount) is ingesteld\*\* $ \_ . UsageLocation**) is niet opgegeven (**-EQ $null\*\*).</span><span class="sxs-lookup"><span data-stu-id="5a059-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="5a059-176">U ziet nu informatie over het volgende:</span><span class="sxs-lookup"><span data-stu-id="5a059-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="5a059-177">De eigenschap *UsageLocation* is slechts een van de vele eigenschappen die aan een gebruikersaccount zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="5a059-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="5a059-178">Als u alle eigenschappen voor gebruikersaccounts wilt bekijken, gebruikt u de cmdlet **Select** en het jokerteken (\*) om alle eigenschappen voor een specifiek gebruikersaccount weer te geven.</span><span class="sxs-lookup"><span data-stu-id="5a059-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="5a059-179">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="5a059-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="5a059-180">*Plaats* is bijvoorbeeld de naam van een account eigenschap van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="5a059-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="5a059-181">Met de volgende opdracht kunt u een lijst weergeven met alle gebruikersaccounts van gebruikers die in Londen wonen:</span><span class="sxs-lookup"><span data-stu-id="5a059-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="5a059-182">De syntaxis voor de **where** -cmdlet in deze voorbeelden is **WHERE {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="5a059-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="5a059-183">[naam van eigenschap van gebruikersaccount] [vergelijkingsoperator] waardeparen **}**.</span><span class="sxs-lookup"><span data-stu-id="5a059-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="5a059-184">[vergelijkingsoperator] is **-EQ** voor gelijkteken, **-ne** voor niet gelijk aan,- **lt** voor kleiner dan, **-gt** voor groter dan, en overige.</span><span class="sxs-lookup"><span data-stu-id="5a059-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="5a059-185">[Value] is meestal een tekenreeks (een reeks letters, cijfers en andere tekens), een numerieke waarde of **$Null** voor niet-opgegeven waarde.</span><span class="sxs-lookup"><span data-stu-id="5a059-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="5a059-186">Zie [waar](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7), voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5a059-186">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  
<span data-ttu-id="5a059-187">Als u de geblokkeerde status van een gebruikersaccount wilt controleren, gebruikt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="5a059-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="5a059-188">Meer eigenschapswaarden voor accounts weergeven</span><span class="sxs-lookup"><span data-stu-id="5a059-188">View additional property values for accounts</span></span>

<span data-ttu-id="5a059-189">Standaard worden in de cmdlet **Get-MsolUser** de volgende drie eigenschappen van gebruikersaccounts weergegeven:</span><span class="sxs-lookup"><span data-stu-id="5a059-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="5a059-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="5a059-190">UserPrincipalName</span></span>
    
- <span data-ttu-id="5a059-191">Weergave</span><span class="sxs-lookup"><span data-stu-id="5a059-191">DisplayName</span></span>
    
- <span data-ttu-id="5a059-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="5a059-192">isLicensed</span></span>
    
<span data-ttu-id="5a059-193">Als u meer eigenschappen nodig hebt, zoals de afdeling met de gebruikers en het land of de regio waar ze Microsoft 365-Services gebruiken, kunt u de cmdlet **Get-MsolUser** gebruiken in combinatie met de **optie Select** om de lijst met eigenschappen van een gebruikersaccount op te geven.</span><span class="sxs-lookup"><span data-stu-id="5a059-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="5a059-194">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="5a059-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="5a059-195">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="5a059-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="5a059-196">Alle informatie over de gebruikersaccounts (**Get-MsolUser**) verzenden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5a059-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="5a059-197">Alleen de naam, de afdeling en de gebruikslocatie van de gebruikersaccount weergeven (**Selecteer DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="5a059-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="5a059-198">U ziet nu informatie over het volgende:</span><span class="sxs-lookup"><span data-stu-id="5a059-198">You should get information similar to this:</span></span>
  
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

<span data-ttu-id="5a059-199">Met de cmdlet **Select** kiest u welke eigenschappen moeten worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5a059-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="5a059-200">Als u alle eigenschappen voor een specifiek gebruikersaccount wilt weergeven, gebruikt u het jokerteken (\*).</span><span class="sxs-lookup"><span data-stu-id="5a059-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="5a059-201">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="5a059-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="5a059-202">Als u een lijst wilt selecteren met de accounts die u wilt weergeven, kunt u ook de **where** -cmdlet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5a059-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="5a059-203">Hier ziet u een voorbeeld van een opdracht waarmee alleen gebruikersaccounts worden weergegeven met een niet-opgegeven gebruikslocatie:</span><span class="sxs-lookup"><span data-stu-id="5a059-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="5a059-204">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="5a059-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="5a059-205">Alle informatie over de gebruikersaccounts (**Get-MsolUser**) verzenden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5a059-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="5a059-206">Zoek alle gebruikersaccounts met een niet-opgegeven gebruikslocatie (**waarbij {$ \_ . UsageLocation-EQ $Null}**) en verstuur de bijbehorende informatie naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5a059-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="5a059-207">Met de opdracht wordt in de accolades aangegeven dat PowerShell de accounts waarvan de eigenschap UsageLocation user account (\*\* $ \_ . UsageLocation**) is niet opgegeven (**-EQ $null\*\*).</span><span class="sxs-lookup"><span data-stu-id="5a059-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="5a059-208">Alleen de naam, de afdeling en de gebruikslocatie van de gebruikersaccount weergeven (**Selecteer DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="5a059-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="5a059-209">U ziet nu informatie over het volgende:</span><span class="sxs-lookup"><span data-stu-id="5a059-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="5a059-210">Als u adreslijstsynchronisatie gebruikt voor het maken en beheren van uw Microsoft 365-gebruikers, kunt u het lokale account weergeven waarmee een Microsoft 365-gebruiker is geprojecteerd.</span><span class="sxs-lookup"><span data-stu-id="5a059-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="5a059-211">In het volgende voorbeeld wordt ervan uitgegaan:</span><span class="sxs-lookup"><span data-stu-id="5a059-211">The following example assumes that:</span></span>

- <span data-ttu-id="5a059-212">Azure AD Connect is geconfigureerd voor gebruik van het standaardbron ankerpunt van ObjectGUID.</span><span class="sxs-lookup"><span data-stu-id="5a059-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="5a059-213">Ga voor meer informatie over het configureren van een bron ankerpunt naar [Azure AD Connect: ontwerp concepten](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts).</span><span class="sxs-lookup"><span data-stu-id="5a059-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="5a059-214">De Active Directory Domain Services-module voor PowerShell is geïnstalleerd (Zie de [hulpmiddelen voor RSAT](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span><span class="sxs-lookup"><span data-stu-id="5a059-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="5a059-215">Zie ook</span><span class="sxs-lookup"><span data-stu-id="5a059-215">See also</span></span>

[<span data-ttu-id="5a059-216">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a059-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5a059-217">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a059-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5a059-218">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5a059-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
