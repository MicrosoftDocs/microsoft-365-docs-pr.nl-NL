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
ms.openlocfilehash: 4dba05ce440ec0d395fda58a12df3e9f751bb469
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357896"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="928c5-103">Microsoft 365-gebruikersaccounts weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="928c5-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="928c5-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="928c5-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="928c5-105">Hoewel u het Microsoft 365-Beheercentrum kunt gebruiken om de accounts voor uw Microsoft 365-Tenant weer te geven, kunt u ook PowerShell voor Microsoft 365 gebruiken en de volgende dingen doen voor het Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="928c5-105">Although you can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant, you can also use PowerShell for Microsoft 365 and do some things that the admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="928c5-106">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="928c5-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="928c5-107">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="928c5-107">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="928c5-108">Alle accounts weergeven</span><span class="sxs-lookup"><span data-stu-id="928c5-108">View all accounts</span></span>

<span data-ttu-id="928c5-109">Voer de volgende opdracht uit om de volledige lijst met gebruikersaccounts weer te geven:</span><span class="sxs-lookup"><span data-stu-id="928c5-109">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="928c5-110">U dient informatie te zien die er ongeveer als volgt uit ziet:</span><span class="sxs-lookup"><span data-stu-id="928c5-110">You should see information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="928c5-111">Een specifiek account weergeven</span><span class="sxs-lookup"><span data-stu-id="928c5-111">View a specific account</span></span>

<span data-ttu-id="928c5-112">Als u een specifiek gebruikersaccount wilt weergeven, vult u de naam van het aanmeldingsaccount van het gebruikersaccount in, ook wel bekend als de UPN (User Principal Name), verwijdert u de tekens ' < ' en ' > ' en voert u deze opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="928c5-112">To display a specific user account, fill in the sign-in account name of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="928c5-113">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="928c5-113">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="928c5-114">Extra eigenschapswaarden voor een specifiek account weergeven</span><span class="sxs-lookup"><span data-stu-id="928c5-114">View additional property values for a specific account</span></span>

<span data-ttu-id="928c5-115">Standaard worden met de cmdlet **Get-AzureADUser** alleen de eigenschappen ObjectID, DisplayName en userPrincipalName van accounts weergegeven.</span><span class="sxs-lookup"><span data-stu-id="928c5-115">By default, the **Get-AzureADUser** cmdlet only displays the ObjectID, DisplayName, and UserPrincipalName properties of accounts.</span></span>

<span data-ttu-id="928c5-116">Als u de lijst met eigenschappen wilt weergeven, kunt u de cmdlet **SELECT SELECT** gebruiken in combinatie met de cmdlet **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="928c5-116">To be more selective about the list of properties to display, you can use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="928c5-117">Als u de twee cmdlets wilt combineren, gebruikt u het teken ' pipe ' | ', waarmee wordt aangegeven dat Azure Active Directory PowerShell voor Graph de resultaten van één opdracht oplevert en deze naar de volgende opdracht verzenden.</span><span class="sxs-lookup"><span data-stu-id="928c5-117">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="928c5-118">Hier ziet u een voorbeeld van een opdracht waarmee u de naam, afdeling en UsageLocation voor elke gebruikersaccount kunt weergeven:</span><span class="sxs-lookup"><span data-stu-id="928c5-118">Here is an example command that displays the DisplayName, Department, and UsageLocation for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="928c5-119">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="928c5-119">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="928c5-120">Alle informatie over de gebruikersaccounts ( **Get-AzureADUser** ) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="928c5-120">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="928c5-121">Alleen de naam, de afdeling en de gebruikslocatie van de gebruikersaccount weergeven ( **Selecteer DisplayName, Department, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="928c5-121">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
  
<span data-ttu-id="928c5-122">Als u alle eigenschappen voor gebruikersaccounts wilt bekijken, gebruikt u de cmdlet **Select** en het jokerteken (\*) om alle eigenschappen voor een specifiek gebruikersaccount weer te geven.</span><span class="sxs-lookup"><span data-stu-id="928c5-122">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="928c5-123">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="928c5-123">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="928c5-124">Als ander voorbeeld kunt u de ingeschakelde status van een specifiek gebruikersaccount controleren met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="928c5-124">As another example, you can check the enabled status of a specific user account with the following command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="928c5-125">Synchronisatiestatus van een account weergeven</span><span class="sxs-lookup"><span data-stu-id="928c5-125">View account synchronization status</span></span>

<span data-ttu-id="928c5-126">Gebruikersaccounts bestaan uit twee bronnen: Windows Server Active Directory (AD) voor accounts die worden gesynchroniseerd vanuit on-premises AD-advertenties met de Cloud en Azure AD die accounts rechtstreeks in de Cloud maken.</span><span class="sxs-lookup"><span data-stu-id="928c5-126">User accounts have two sources; Windows Server Active Directory (AD) which are accounts that sync from on-premises AD to the cloud and Azure AD which are accounts directly created in the cloud.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```
<span data-ttu-id="928c5-127">Met deze opdracht wordt PowerShell geïnstrueerd voor alle gebruikers voor wie het kenmerk **DirSyncEnabled** is ingesteld op waar.</span><span class="sxs-lookup"><span data-stu-id="928c5-127">This command instructs PowerShell to get all users who have the attribute **DirSyncEnabled** set to True.</span></span> <span data-ttu-id="928c5-128">U kunt deze gebruiken voor het opschonen van accounts die worden gesynchroniseerd vanuit on-premises AD.</span><span class="sxs-lookup"><span data-stu-id="928c5-128">It can be used to pull up accounts synchronizing from on-premise AD.</span></span>


```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $true}
```
<span data-ttu-id="928c5-129">Met deze opdracht wordt PowerShell geïnstrueerd voor alle gebruikers voor wie het kenmerk **DirSyncEnabled** is ingesteld op false.</span><span class="sxs-lookup"><span data-stu-id="928c5-129">This command instructs PowerShell to get all users who have the attribute **DirSyncEnabled** set to False.</span></span> <span data-ttu-id="928c5-130">Dit kan worden gebruikt voor het opschonen van Cloud accounts.</span><span class="sxs-lookup"><span data-stu-id="928c5-130">It can be used to pull up cloud-only accounts.</span></span>

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="928c5-131">Sommige accounts weergeven op basis van een gemeenschappelijke eigenschap</span><span class="sxs-lookup"><span data-stu-id="928c5-131">View some accounts based on a common property</span></span>

<span data-ttu-id="928c5-132">Als u een lijst wilt selecteren met de accounts die u wilt weergeven, kunt u de **where** -cmdlet gebruiken in combinatie met de cmdlet **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="928c5-132">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="928c5-133">Als u de twee cmdlets wilt combineren, gebruikt u het teken ' pipe ' | ', waarmee wordt aangegeven dat Azure Active Directory PowerShell voor Graph de resultaten van één opdracht oplevert en deze naar de volgende opdracht verzenden.</span><span class="sxs-lookup"><span data-stu-id="928c5-133">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="928c5-134">Hier ziet u een voorbeeld van een opdracht waarmee alleen gebruikersaccounts worden weergegeven met een niet-opgegeven gebruikslocatie:</span><span class="sxs-lookup"><span data-stu-id="928c5-134">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="928c5-135">Met deze opdracht krijgt u Azure Active Directory PowerShell voor Graph om het volgende te doen:</span><span class="sxs-lookup"><span data-stu-id="928c5-135">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
- <span data-ttu-id="928c5-136">Alle informatie over de gebruikersaccounts ( **Get-AzureADUser** ) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="928c5-136">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="928c5-137">Alle gebruikersaccounts zoeken met een niet-opgegeven gebruikslocatie ( **waarbij {$ \_ . UsageLocation-EQ $Null}** ).</span><span class="sxs-lookup"><span data-stu-id="928c5-137">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="928c5-138">Met de opdracht wordt in de accolades aangegeven dat PowerShell de set met accounts waarvan de eigenschap UsageLocation user account ( \*\* $ \_ . UsageLocation\*\* ) is niet opgegeven ( **-EQ $null** ).</span><span class="sxs-lookup"><span data-stu-id="928c5-138">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="928c5-139">De eigenschap **UsageLocation** is slechts een van de vele eigenschappen die aan een gebruikersaccount zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="928c5-139">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="928c5-140">Als u alle eigenschappen voor gebruikersaccounts wilt bekijken, gebruikt u de cmdlet **Select** en het jokerteken (\*) om alle eigenschappen voor een specifiek gebruikersaccount weer te geven.</span><span class="sxs-lookup"><span data-stu-id="928c5-140">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="928c5-141">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="928c5-141">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="928c5-142">In deze lijst is **plaats** bijvoorbeeld de naam van een account eigenschap van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="928c5-142">For example, from this list, **City** is the name of a user account property.</span></span> <span data-ttu-id="928c5-143">Dit houdt in dat u de volgende opdracht kunt gebruiken om alle gebruikersaccounts van gebruikers in Londen weer te geven:</span><span class="sxs-lookup"><span data-stu-id="928c5-143">This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="928c5-144">De syntaxis voor de **where** -cmdlet wordt weergegeven in de volgende voorbeelden: **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="928c5-144">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="928c5-145">[naam van eigenschap van gebruikersaccount] [vergelijkingsoperator] waardeparen **}**. > [vergelijkingsoperator] is **-EQ** voor gelijkteken, **-ne** voor niet gelijk aan,- **lt** voor kleiner dan, **-gt** voor groter dan, en overige.</span><span class="sxs-lookup"><span data-stu-id="928c5-145">[user account property name] [comparison operator] [value] **}**.>  [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="928c5-146">[Value] is meestal een tekenreeks (een reeks letters, cijfers en andere tekens), een numerieke waarde of **$Null** voor niet-opgegeven> Zie [waar](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="928c5-146">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified>  See [Where](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) for more information.</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="928c5-147">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="928c5-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="928c5-148">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="928c5-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="928c5-149">Alle accounts weergeven</span><span class="sxs-lookup"><span data-stu-id="928c5-149">View all accounts</span></span>

<span data-ttu-id="928c5-150">Voer de volgende opdracht uit om de volledige lijst met gebruikersaccounts weer te geven:</span><span class="sxs-lookup"><span data-stu-id="928c5-150">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="928c5-151">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="928c5-151">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="928c5-152">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="928c5-152">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="928c5-153">U dient informatie te zien die er ongeveer als volgt uit ziet:</span><span class="sxs-lookup"><span data-stu-id="928c5-153">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="928c5-154">De cmdlet **Get-MsolUser** heeft ook een reeks parameters voor het filteren van de set gebruikersaccounts die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="928c5-154">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="928c5-155">Voer deze opdracht uit voor een lijst met gebruikers zonder licentie (gebruikers die zijn toegevoegd aan Microsoft 365 maar nog geen licentie hebben voor het gebruik van een van de Services).</span><span class="sxs-lookup"><span data-stu-id="928c5-155">For example, for the list of unlicensed users (users who've been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command.</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="928c5-156">U dient informatie te zien die er ongeveer als volgt uit ziet:</span><span class="sxs-lookup"><span data-stu-id="928c5-156">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="928c5-157">Zie [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100))voor meer informatie over aanvullende parameters voor het filteren van de weergave van de weergegeven gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="928c5-157">For more information about additional parameters to filter the display the set of user accounts displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="928c5-158">Een specifiek account weergeven</span><span class="sxs-lookup"><span data-stu-id="928c5-158">View a specific account</span></span>

<span data-ttu-id="928c5-159">Als u een specifiek gebruikersaccount wilt weergeven, vult u de aanmeldingsnaam van het gebruikersaccount van het gebruikersaccount in, ook wel bekend als de UPN (User Principal Name), verwijder de tekens ' < ' en ' > ' en voer deze opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="928c5-159">To display a specific user account, fill in the sign-in name of the user account of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="928c5-160">Sommige accounts weergeven op basis van een gemeenschappelijke eigenschap</span><span class="sxs-lookup"><span data-stu-id="928c5-160">View some accounts based on a common property</span></span>

<span data-ttu-id="928c5-161">Als u een lijst wilt selecteren met de accounts die u wilt weergeven, kunt u de **where** -cmdlet gebruiken in combinatie met de cmdlet **Get-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="928c5-161">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="928c5-162">Om de twee cmdlets te combineren, gebruiken we het teken ' pipe ' | ', waarmee wordt aangegeven dat PowerShell de resultaten van één opdracht moet aannemen en deze naar de volgende opdracht kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="928c5-162">To combine the two cmdlets, we use the "pipe" character "|", which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="928c5-163">Hier ziet u een voorbeeld van een opdracht waarmee alleen gebruikersaccounts worden weergegeven met een niet-opgegeven gebruikslocatie:</span><span class="sxs-lookup"><span data-stu-id="928c5-163">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="928c5-164">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="928c5-164">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="928c5-165">Alle informatie over de gebruikersaccounts ( **Get-MsolUser** ) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="928c5-165">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="928c5-166">Alle gebruikersaccounts zoeken met een niet-opgegeven gebruikslocatie ( **waarbij {$ \_ . UsageLocation-EQ $Null}** ).</span><span class="sxs-lookup"><span data-stu-id="928c5-166">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="928c5-167">Met de opdracht wordt in de accolades aangegeven dat PowerShell de set met accounts waarvan de eigenschap UsageLocation user account ( \*\* $ \_ . UsageLocation\*\* ) is niet opgegeven ( **-EQ $null** ).</span><span class="sxs-lookup"><span data-stu-id="928c5-167">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="928c5-168">U dient informatie te zien die er ongeveer als volgt uit ziet:</span><span class="sxs-lookup"><span data-stu-id="928c5-168">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="928c5-169">De eigenschap **UsageLocation** is slechts een van de vele eigenschappen die aan een gebruikersaccount zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="928c5-169">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="928c5-170">Als u alle eigenschappen voor gebruikersaccounts wilt bekijken, gebruikt u de cmdlet **Select** en het jokerteken (\*) om alle eigenschappen voor een specifiek gebruikersaccount weer te geven.</span><span class="sxs-lookup"><span data-stu-id="928c5-170">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="928c5-171">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="928c5-171">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="928c5-172">In deze lijst is **plaats** bijvoorbeeld de naam van een account eigenschap van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="928c5-172">For example, from this list, **City** is the name of a user account property.</span></span> <span data-ttu-id="928c5-173">Dit houdt in dat u de volgende opdracht kunt gebruiken om alle gebruikersaccounts van gebruikers in Londen weer te geven:</span><span class="sxs-lookup"><span data-stu-id="928c5-173">This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="928c5-174">De syntaxis voor de **where** -cmdlet wordt weergegeven in de volgende voorbeelden: **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="928c5-174">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="928c5-175">[naam van eigenschap van gebruikersaccount] [vergelijkingsoperator] waardeparen **}**.</span><span class="sxs-lookup"><span data-stu-id="928c5-175">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="928c5-176">[vergelijkingsoperator] is **-EQ** voor gelijkteken, **-ne** voor niet gelijk aan,- **lt** voor kleiner dan, **-gt** voor groter dan, en overige.</span><span class="sxs-lookup"><span data-stu-id="928c5-176">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="928c5-177">[Value] is meestal een tekenreeks (een reeks letters, cijfers en andere tekens), een numerieke waarde of **$Null** voor niet-opgegeven waarde.</span><span class="sxs-lookup"><span data-stu-id="928c5-177">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="928c5-178">Zie [waar](https://technet.microsoft.com/library/hh849715.aspx) vindt u meer informatie.</span><span class="sxs-lookup"><span data-stu-id="928c5-178">See [Where](https://technet.microsoft.com/library/hh849715.aspx) for more information.</span></span>
  
<span data-ttu-id="928c5-179">Met de volgende opdracht kunt u de geblokkeerde status van een gebruikersaccount controleren:</span><span class="sxs-lookup"><span data-stu-id="928c5-179">You can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="928c5-180">Meer eigenschapswaarden voor accounts weergeven</span><span class="sxs-lookup"><span data-stu-id="928c5-180">View additional property values for accounts</span></span>

<span data-ttu-id="928c5-181">Met de cmdlet **Get-MsolUser** worden standaard drie eigenschappen van gebruikersaccounts weergegeven:</span><span class="sxs-lookup"><span data-stu-id="928c5-181">The **Get-MsolUser** cmdlet by default displays three properties of user accounts:</span></span>
  
- <span data-ttu-id="928c5-182">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="928c5-182">UserPrincipalName</span></span>
    
- <span data-ttu-id="928c5-183">Weergave</span><span class="sxs-lookup"><span data-stu-id="928c5-183">DisplayName</span></span>
    
- <span data-ttu-id="928c5-184">isLicensed</span><span class="sxs-lookup"><span data-stu-id="928c5-184">isLicensed</span></span>
    
<span data-ttu-id="928c5-185">Als u meer eigenschappen nodig hebt, zoals de afdeling waarin de gebruiker werkt, en het land of de regio waarin de gebruiker Microsoft 365-Services gebruikt, kunt u de cmdlet **Get-MsolUser** in combinatie met de **Select** -cmdlet gebruiken om de lijst met eigenschappen van een gebruikersaccount op te geven.</span><span class="sxs-lookup"><span data-stu-id="928c5-185">If you need additional properties, such as the department the user works for and the country/region where the user uses Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="928c5-186">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="928c5-186">Here is an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="928c5-187">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="928c5-187">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="928c5-188">Alle informatie over de gebruikersaccounts ( **Get-MsolUser** ) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="928c5-188">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="928c5-189">Alleen de naam, de afdeling en de gebruikslocatie van de gebruikersaccount weergeven ( **Selecteer DisplayName, Department, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="928c5-189">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="928c5-190">U dient informatie te zien die er ongeveer als volgt uit ziet:</span><span class="sxs-lookup"><span data-stu-id="928c5-190">You should see information similar to this:</span></span>
  
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

<span data-ttu-id="928c5-191">Met de cmdlet **Select selecteert** u de eigenschappen die u wilt weergeven en kiest u de gewenste opdracht.</span><span class="sxs-lookup"><span data-stu-id="928c5-191">The **Select** cmdlet lets you pick and choose the properties you want a command to display.</span></span> <span data-ttu-id="928c5-192">Als u alle eigenschappen voor gebruikersaccounts wilt zien, gebruikt u het jokerteken (\*) om alle eigenschappen voor een specifiek gebruikersaccount weer te geven.</span><span class="sxs-lookup"><span data-stu-id="928c5-192">To see all of the properties for user accounts, use the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="928c5-193">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="928c5-193">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="928c5-194">Als u een lijst wilt selecteren met de accounts die u wilt weergeven, kunt u ook de **where** -cmdlet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="928c5-194">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="928c5-195">Hier ziet u een voorbeeld van een opdracht waarmee alleen gebruikersaccounts worden weergegeven met een niet-opgegeven gebruikslocatie:</span><span class="sxs-lookup"><span data-stu-id="928c5-195">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="928c5-196">Met deze opdracht wordt PowerShell overgeïnstrueerd:</span><span class="sxs-lookup"><span data-stu-id="928c5-196">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="928c5-197">Alle informatie over de gebruikersaccounts ( **Get-MsolUser** ) vinden en verzenden naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="928c5-197">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="928c5-198">Alle gebruikersaccounts zoeken met een niet-opgegeven gebruikslocatie ( **waarbij {$ \_ . UsageLocation-EQ $Null}** ) en verstuur de bijbehorende informatie naar de volgende opdracht ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="928c5-198">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ) and send the resulting information to the next command ( **|** ).</span></span> <span data-ttu-id="928c5-199">Binnen de accolades moet de opdracht PowerShell geïnstrueerd om alleen de groep met accounts te vinden waarin de eigenschap UsageLocation van het gebruikersaccount ( \*\* $ \_ . UsageLocation\*\* ) is niet opgegeven ( **-EQ $null** ).</span><span class="sxs-lookup"><span data-stu-id="928c5-199">Inside the braces, the command is instructing PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
- <span data-ttu-id="928c5-200">Alleen de naam, de afdeling en de gebruikslocatie van de gebruikersaccount weergeven ( **Selecteer DisplayName, Department, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="928c5-200">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="928c5-201">U dient informatie te zien die er ongeveer als volgt uit ziet:</span><span class="sxs-lookup"><span data-stu-id="928c5-201">You should see information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="928c5-202">Als u adreslijstsynchronisatie gebruikt voor het maken en beheren van uw Microsoft 365-gebruikers, kunt u weergeven naar welke lokale account een Microsoft 365-gebruiker is geprojecteerd.</span><span class="sxs-lookup"><span data-stu-id="928c5-202">If you are using directory synchronization to create and manage your Microsoft 365 users, you can display which local account a Microsoft 365 user has been projected from.</span></span> <span data-ttu-id="928c5-203">In de volgende stappen wordt ervan uitgegaan dat Azure AD Connect is geconfigureerd voor gebruik van het standaardbron ankerpunt van ObjectGUID (Zie [Azure AD Connect: ontwerp concepten](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) en wordt ervan uitgegaan dat de Active Directory Domain Services-module voor PowerShell is geïnstalleerd (Zie [RSAT-hulpmiddelen](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span><span class="sxs-lookup"><span data-stu-id="928c5-203">The following assumes that Azure AD Connect has been configured to use the default source anchor of ObjectGUID (for more on configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) and assumes that the Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="928c5-204">Zie ook</span><span class="sxs-lookup"><span data-stu-id="928c5-204">See also</span></span>

[<span data-ttu-id="928c5-205">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="928c5-205">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="928c5-206">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="928c5-206">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="928c5-207">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="928c5-207">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
