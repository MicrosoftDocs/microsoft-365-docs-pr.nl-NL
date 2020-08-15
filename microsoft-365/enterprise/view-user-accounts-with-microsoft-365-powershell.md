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
ms.openlocfilehash: ea631d12a95ca813ebf9da3286e36d724d51a2f7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695789"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="2ff0b-103">Microsoft 365-gebruikersaccounts weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ff0b-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="2ff0b-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2ff0b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2ff0b-105">Hoewel u het Microsoft 365-Beheercentrum kunt gebruiken om de accounts voor uw Microsoft 365-Tenant weer te geven, kunt u ook PowerShell voor Microsoft 365 gebruiken en de volgende dingen doen voor het Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-105">Although you can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant, you can also use PowerShell for Microsoft 365 and do some things that the admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="2ff0b-106">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="2ff0b-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="2ff0b-107">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-107">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="2ff0b-108">Alle accounts weergeven</span><span class="sxs-lookup"><span data-stu-id="2ff0b-108">View all accounts</span></span>

<span data-ttu-id="2ff0b-109">Voer de volgende opdracht uit om de volledige lijst met gebruikersaccounts weer te geven:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-109">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="2ff0b-110">U dient informatie te zien die er ongeveer als volgt uit ziet:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-110">You should see information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="2ff0b-111">Een specifiek account weergeven</span><span class="sxs-lookup"><span data-stu-id="2ff0b-111">View a specific account</span></span>

<span data-ttu-id="2ff0b-112">Als u een specifiek gebruikersaccount wilt weergeven, vult u de naam van het aanmeldingsaccount van het gebruikersaccount in, ook wel bekend als de UPN (User Principal Name), verwijdert u de tekens ' < ' en ' > ' en voert u deze opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-112">To display a specific user account, fill in the sign-in account name of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="2ff0b-113">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-113">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="2ff0b-114">Extra eigenschapswaarden voor een specifiek account weergeven</span><span class="sxs-lookup"><span data-stu-id="2ff0b-114">View additional property values for a specific account</span></span>

<span data-ttu-id="2ff0b-115">Standaard worden met de cmdlet **Get-AzureADUser** alleen de eigenschappen ObjectID, DisplayName en userPrincipalName van accounts weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-115">By default, the **Get-AzureADUser** cmdlet only displays the ObjectID, DisplayName, and UserPrincipalName properties of accounts.</span></span>

<span data-ttu-id="2ff0b-116">Als u de lijst met eigenschappen wilt weergeven, kunt u de cmdlet **SELECT SELECT** gebruiken in combinatie met de cmdlet **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="2ff0b-116">To be more selective about the list of properties to display, you can use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="2ff0b-117">Als u de twee cmdlets wilt combineren, gebruikt u het teken ' pipe ' | ', waarmee wordt aangegeven dat Azure Active Directory PowerShell voor Graph de resultaten van één opdracht oplevert en deze naar de volgende opdracht verzenden.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-117">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="2ff0b-118">Hier ziet u een voorbeeld van een opdracht waarmee u de naam, afdeling en UsageLocation voor elke gebruikersaccount kunt weergeven:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-118">Here is an example command that displays the DisplayName, Department, and UsageLocation for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="2ff0b-119">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-119">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="2ff0b-120">Alle informatie over de gebruikersaccounts ( **Get-AzureADUser** ) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-120">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="2ff0b-121">Alleen de naam, de afdeling en de gebruikslocatie van de gebruikersaccount weergeven ( **Selecteer DisplayName, Department, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-121">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
  
<span data-ttu-id="2ff0b-122">Als u alle eigenschappen voor gebruikersaccounts wilt bekijken, gebruikt u de cmdlet **Select** en het jokerteken (\*) om alle eigenschappen voor een specifiek gebruikersaccount weer te geven.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-122">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="2ff0b-123">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-123">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="2ff0b-124">Als ander voorbeeld kunt u de ingeschakelde status van een specifiek gebruikersaccount controleren met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-124">As another example, you can check the enabled status of a specific user account with the following command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="2ff0b-125">Sommige accounts weergeven op basis van een gemeenschappelijke eigenschap</span><span class="sxs-lookup"><span data-stu-id="2ff0b-125">View some accounts based on a common property</span></span>

<span data-ttu-id="2ff0b-126">Als u een lijst wilt selecteren met de accounts die u wilt weergeven, kunt u de **where** -cmdlet gebruiken in combinatie met de cmdlet **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="2ff0b-126">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="2ff0b-127">Als u de twee cmdlets wilt combineren, gebruikt u het teken ' pipe ' | ', waarmee wordt aangegeven dat Azure Active Directory PowerShell voor Graph de resultaten van één opdracht oplevert en deze naar de volgende opdracht verzenden.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-127">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="2ff0b-128">Hier ziet u een voorbeeld van een opdracht waarmee alleen gebruikersaccounts worden weergegeven met een niet-opgegeven gebruikslocatie:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-128">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="2ff0b-129">Met deze opdracht krijgt u Azure Active Directory PowerShell voor Graph om het volgende te doen:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-129">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
- <span data-ttu-id="2ff0b-130">Alle informatie over de gebruikersaccounts ( **Get-AzureADUser** ) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-130">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="2ff0b-131">Alle gebruikersaccounts zoeken met een niet-opgegeven gebruikslocatie ( **waarbij {$ \_ . UsageLocation-EQ $Null}** ).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-131">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="2ff0b-132">Met de opdracht wordt in de accolades aangegeven dat PowerShell de set met accounts waarvan de eigenschap UsageLocation user account ( \*\* $ \_ . UsageLocation\*\* ) is niet opgegeven ( **-EQ $null** ).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-132">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="2ff0b-133">De eigenschap **UsageLocation** is slechts een van de vele eigenschappen die aan een gebruikersaccount zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-133">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="2ff0b-134">Als u alle eigenschappen voor gebruikersaccounts wilt bekijken, gebruikt u de cmdlet **Select** en het jokerteken (\*) om alle eigenschappen voor een specifiek gebruikersaccount weer te geven.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-134">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="2ff0b-135">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-135">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="2ff0b-136">In deze lijst is **plaats** bijvoorbeeld de naam van een account eigenschap van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-136">For example, from this list, **City** is the name of a user account property.</span></span> <span data-ttu-id="2ff0b-137">Dit houdt in dat u de volgende opdracht kunt gebruiken om alle gebruikersaccounts van gebruikers in Londen weer te geven:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-137">This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="2ff0b-138">De syntaxis voor de **where** -cmdlet wordt weergegeven in de volgende voorbeelden: **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="2ff0b-138">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="2ff0b-139">[naam van eigenschap van gebruikersaccount] [vergelijkingsoperator] waardeparen **}**. > [vergelijkingsoperator] is **-EQ** voor gelijkteken, **-ne** voor niet gelijk aan,- **lt** voor kleiner dan, **-gt** voor groter dan, en overige.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-139">[user account property name] [comparison operator] [value] **}**.>  [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="2ff0b-140">[Value] is meestal een tekenreeks (een reeks letters, cijfers en andere tekens), een numerieke waarde of **$Null** voor niet-opgegeven> Zie [waar](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-140">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified>  See [Where](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) for more information.</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="2ff0b-141">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="2ff0b-141">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="2ff0b-142">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-142">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="2ff0b-143">Alle accounts weergeven</span><span class="sxs-lookup"><span data-stu-id="2ff0b-143">View all accounts</span></span>

<span data-ttu-id="2ff0b-144">Voer de volgende opdracht uit om de volledige lijst met gebruikersaccounts weer te geven:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-144">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="2ff0b-145">De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-145">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="2ff0b-146">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-146">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="2ff0b-147">U dient informatie te zien die er ongeveer als volgt uit ziet:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-147">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="2ff0b-148">De cmdlet **Get-MsolUser** heeft ook een reeks parameters voor het filteren van de set gebruikersaccounts die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-148">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="2ff0b-149">Voer deze opdracht uit voor een lijst met gebruikers zonder licentie (gebruikers die zijn toegevoegd aan Microsoft 365 maar nog geen licentie hebben voor het gebruik van een van de Services).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-149">For example, for the list of unlicensed users (users who've been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command.</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="2ff0b-150">U dient informatie te zien die er ongeveer als volgt uit ziet:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-150">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="2ff0b-151">Zie [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100))voor meer informatie over aanvullende parameters voor het filteren van de weergave van de weergegeven gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-151">For more information about additional parameters to filter the display the set of user accounts displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="2ff0b-152">Een specifiek account weergeven</span><span class="sxs-lookup"><span data-stu-id="2ff0b-152">View a specific account</span></span>

<span data-ttu-id="2ff0b-153">Als u een specifiek gebruikersaccount wilt weergeven, vult u de aanmeldingsnaam van het gebruikersaccount van het gebruikersaccount in, ook wel bekend als de UPN (User Principal Name), verwijder de tekens ' < ' en ' > ' en voer deze opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-153">To display a specific user account, fill in the sign-in name of the user account of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="2ff0b-154">Sommige accounts weergeven op basis van een gemeenschappelijke eigenschap</span><span class="sxs-lookup"><span data-stu-id="2ff0b-154">View some accounts based on a common property</span></span>

<span data-ttu-id="2ff0b-155">Als u een lijst wilt selecteren met de accounts die u wilt weergeven, kunt u de **where** -cmdlet gebruiken in combinatie met de cmdlet **Get-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="2ff0b-155">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="2ff0b-156">Om de twee cmdlets te combineren, gebruiken we het teken ' pipe ' | ', waarmee wordt aangegeven dat PowerShell de resultaten van één opdracht moet aannemen en deze naar de volgende opdracht kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-156">To combine the two cmdlets, we use the "pipe" character "|", which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="2ff0b-157">Hier ziet u een voorbeeld van een opdracht waarmee alleen gebruikersaccounts worden weergegeven met een niet-opgegeven gebruikslocatie:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-157">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="2ff0b-158">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-158">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="2ff0b-159">Alle informatie over de gebruikersaccounts ( **Get-MsolUser** ) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-159">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="2ff0b-160">Alle gebruikersaccounts zoeken met een niet-opgegeven gebruikslocatie ( **waarbij {$ \_ . UsageLocation-EQ $Null}** ).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-160">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="2ff0b-161">Met de opdracht wordt in de accolades aangegeven dat PowerShell de set met accounts waarvan de eigenschap UsageLocation user account ( \*\* $ \_ . UsageLocation\*\* ) is niet opgegeven ( **-EQ $null** ).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-161">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="2ff0b-162">U dient informatie te zien die er ongeveer als volgt uit ziet:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-162">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="2ff0b-163">De eigenschap **UsageLocation** is slechts een van de vele eigenschappen die aan een gebruikersaccount zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-163">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="2ff0b-164">Als u alle eigenschappen voor gebruikersaccounts wilt bekijken, gebruikt u de cmdlet **Select** en het jokerteken (\*) om alle eigenschappen voor een specifiek gebruikersaccount weer te geven.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-164">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="2ff0b-165">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-165">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="2ff0b-166">In deze lijst is **plaats** bijvoorbeeld de naam van een account eigenschap van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-166">For example, from this list, **City** is the name of a user account property.</span></span> <span data-ttu-id="2ff0b-167">Dit houdt in dat u de volgende opdracht kunt gebruiken om alle gebruikersaccounts van gebruikers in Londen weer te geven:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-167">This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="2ff0b-168">De syntaxis voor de **where** -cmdlet wordt weergegeven in de volgende voorbeelden: **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="2ff0b-168">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="2ff0b-169">[naam van eigenschap van gebruikersaccount] [vergelijkingsoperator] waardeparen **}**.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-169">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="2ff0b-170">[vergelijkingsoperator] is **-EQ** voor gelijkteken, **-ne** voor niet gelijk aan,- **lt** voor kleiner dan, **-gt** voor groter dan, en overige.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-170">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="2ff0b-171">[Value] is meestal een tekenreeks (een reeks letters, cijfers en andere tekens), een numerieke waarde of **$Null** voor niet-opgegeven waarde.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-171">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="2ff0b-172">Zie [waar](https://technet.microsoft.com/library/hh849715.aspx) vindt u meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-172">See [Where](https://technet.microsoft.com/library/hh849715.aspx) for more information.</span></span>
  
<span data-ttu-id="2ff0b-173">Met de volgende opdracht kunt u de geblokkeerde status van een gebruikersaccount controleren:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-173">You can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="2ff0b-174">Meer eigenschapswaarden voor accounts weergeven</span><span class="sxs-lookup"><span data-stu-id="2ff0b-174">View additional property values for accounts</span></span>

<span data-ttu-id="2ff0b-175">Met de cmdlet **Get-MsolUser** worden standaard drie eigenschappen van gebruikersaccounts weergegeven:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-175">The **Get-MsolUser** cmdlet by default displays three properties of user accounts:</span></span>
  
- <span data-ttu-id="2ff0b-176">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="2ff0b-176">UserPrincipalName</span></span>
    
- <span data-ttu-id="2ff0b-177">Weergave</span><span class="sxs-lookup"><span data-stu-id="2ff0b-177">DisplayName</span></span>
    
- <span data-ttu-id="2ff0b-178">isLicensed</span><span class="sxs-lookup"><span data-stu-id="2ff0b-178">isLicensed</span></span>
    
<span data-ttu-id="2ff0b-179">Als u meer eigenschappen nodig hebt, zoals de afdeling waarin de gebruiker werkt, en het land of de regio waarin de gebruiker Microsoft 365-Services gebruikt, kunt u de cmdlet **Get-MsolUser** in combinatie met de **Select** -cmdlet gebruiken om de lijst met eigenschappen van een gebruikersaccount op te geven.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-179">If you need additional properties, such as the department the user works for and the country/region where the user uses Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="2ff0b-180">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-180">Here is an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="2ff0b-181">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-181">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="2ff0b-182">Alle informatie over de gebruikersaccounts ( **Get-MsolUser** ) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-182">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="2ff0b-183">Alleen de naam, de afdeling en de gebruikslocatie van de gebruikersaccount weergeven ( **Selecteer DisplayName, Department, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-183">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="2ff0b-184">U dient informatie te zien die er ongeveer als volgt uit ziet:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-184">You should see information similar to this:</span></span>
  
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

<span data-ttu-id="2ff0b-185">Met de cmdlet **Select selecteert** u de eigenschappen die u wilt weergeven en kiest u de gewenste opdracht.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-185">The **Select** cmdlet lets you pick and choose the properties you want a command to display.</span></span> <span data-ttu-id="2ff0b-186">Als u alle eigenschappen voor gebruikersaccounts wilt zien, gebruikt u het jokerteken (\*) om alle eigenschappen voor een specifiek gebruikersaccount weer te geven.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-186">To see all of the properties for user accounts, use the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="2ff0b-187">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-187">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="2ff0b-188">Als u een lijst wilt selecteren met de accounts die u wilt weergeven, kunt u ook de **where** -cmdlet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-188">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="2ff0b-189">Hier ziet u een voorbeeld van een opdracht waarmee alleen gebruikersaccounts worden weergegeven met een niet-opgegeven gebruikslocatie:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-189">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="2ff0b-190">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-190">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="2ff0b-191">Alle informatie over de gebruikersaccounts ( **Get-MsolUser** ) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-191">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="2ff0b-192">Alle gebruikersaccounts zoeken met een niet-opgegeven gebruikslocatie ( **waarbij {$ \_ . UsageLocation-EQ $Null}** ) en verstuur de bijbehorende informatie naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-192">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ) and send the resulting information to the next command ( **|** ).</span></span> <span data-ttu-id="2ff0b-193">Binnen de accolades moet de opdracht PowerShell geïnstrueerd om alleen de groep met accounts te vinden waarin de eigenschap UsageLocation van het gebruikersaccount ( \*\* $ \_ . UsageLocation\*\* ) is niet opgegeven ( **-EQ $null** ).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-193">Inside the braces, the command is instructing PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
- <span data-ttu-id="2ff0b-194">Alleen de naam, de afdeling en de gebruikslocatie van de gebruikersaccount weergeven ( **Selecteer DisplayName, Department, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="2ff0b-194">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="2ff0b-195">U dient informatie te zien die er ongeveer als volgt uit ziet:</span><span class="sxs-lookup"><span data-stu-id="2ff0b-195">You should see information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="2ff0b-196">Als u adreslijstsynchronisatie gebruikt voor het maken en beheren van uw Microsoft 365-gebruikers, kunt u weergeven naar welke lokale account een Microsoft 365-gebruiker is geprojecteerd.</span><span class="sxs-lookup"><span data-stu-id="2ff0b-196">If you are using directory synchronization to create and manage your Microsoft 365 users, you can display which local account a Microsoft 365 user has been projected from.</span></span> <span data-ttu-id="2ff0b-197">In de volgende stappen wordt ervan uitgegaan dat Azure AD Connect is geconfigureerd voor gebruik van het standaardbron ankerpunt van ObjectGUID (Zie [Azure AD Connect: ontwerp concepten](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) en wordt ervan uitgegaan dat de Active Directory Domain Services-module voor PowerShell is geïnstalleerd (Zie [RSAT-hulpmiddelen](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span><span class="sxs-lookup"><span data-stu-id="2ff0b-197">The following assumes that Azure AD Connect has been configured to use the default source anchor of ObjectGUID (for more on configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) and assumes that the Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="2ff0b-198">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2ff0b-198">See also</span></span>

[<span data-ttu-id="2ff0b-199">Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ff0b-199">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2ff0b-200">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ff0b-200">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2ff0b-201">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2ff0b-201">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

