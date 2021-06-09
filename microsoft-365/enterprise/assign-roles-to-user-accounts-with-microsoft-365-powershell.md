---
title: Rollen toewijzen aan Microsoft 365 gebruikersaccounts met PowerShell
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
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: In dit artikel leert u hoe u Snel en eenvoudig PowerShell kunt gebruiken Microsoft 365 beheerdersrollen toe te wijzen aan gebruikersaccounts.
ms.openlocfilehash: 84e785052c970ca15487540c3904eacdd0e9ca28
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905378"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="69513-103">Beheerdersrollen toewijzen aan Microsoft 365 gebruikersaccounts met PowerShell</span><span class="sxs-lookup"><span data-stu-id="69513-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="69513-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="69513-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="69513-105">U kunt eenvoudig rollen toewijzen aan gebruikersaccounts met PowerShell voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="69513-105">You can easily assign roles to user accounts by using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="69513-106">Meer informatie over [het toewijzen van beheerdersrollen](../admin/add-users/assign-admin-roles.md) aan gebruikersaccounts met het Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="69513-106">Learn how to  [assign admin roles](../admin/add-users/assign-admin-roles.md) to user accounts with the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="69513-107">Zie Gebruikers en groepen beheren voor een lijst met [aanvullende bronnen.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="69513-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="69513-108">De powershell Azure Active Directory powershell gebruiken voor Graph module</span><span class="sxs-lookup"><span data-stu-id="69513-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="69513-109">Gebruik eerst een globale beheerdersaccount om verbinding [te maken met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="69513-109">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="69513-110">Identificeer vervolgens de aanmeldingsnaam van het gebruikersaccount dat u wilt toevoegen aan een rol (bijvoorbeeld: fredsm \@ contoso.com).</span><span class="sxs-lookup"><span data-stu-id="69513-110">Next, identify the sign-in name of the user account that you want to add to a role (example: fredsm\@contoso.com).</span></span> <span data-ttu-id="69513-111">Dit wordt ook wel de naam van de gebruikershoofdnaam (UPN) genoemd.</span><span class="sxs-lookup"><span data-stu-id="69513-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="69513-112">Bepaal vervolgens de naam van de rol.</span><span class="sxs-lookup"><span data-stu-id="69513-112">Next, determine the name of the role.</span></span> <span data-ttu-id="69513-113">Zie [beheerdersrolmachtigingen in Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="69513-113">See [administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="69513-114">Let op de notities in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="69513-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="69513-115">Sommige rollennamen zijn anders voor Azure Active Directory (Azure AD) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69513-115">Some role names are different for Azure Active Directory (Azure AD) PowerShell.</span></span> <span data-ttu-id="69513-116">De rol van *SharePoint beheerder* in het Microsoft 365 beheercentrum is bijvoorbeeld SharePoint *servicebeheerder* in Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69513-116">For example, the *SharePoint Administrator* role in the Microsoft 365 admin center is *SharePoint Service Administrator* in Azure AD PowerShell.</span></span>
>

<span data-ttu-id="69513-117">Vul vervolgens de aanmeldings- en rolnamen in en voer de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="69513-117">Next, fill in the sign-in and role names and run these commands:</span></span>
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="69513-118">Hier is een voorbeeld van een voltooide opdrachtset die de rol SharePoint servicebeheerder toewijst aan het *belindan \@ contoso.com* account:</span><span class="sxs-lookup"><span data-stu-id="69513-118">Here's an example of a completed command set that assigns the SharePoint Service Administrator role to the *belindan\@contoso.com* account:</span></span>
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="69513-119">Als u de lijst met gebruikersnamen voor een specifieke beheerdersrol wilt weergeven, gebruikt u deze opdrachten.</span><span class="sxs-lookup"><span data-stu-id="69513-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="69513-120">Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="69513-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="69513-121">Gebruik eerst een globale beheerdersaccount om verbinding [te maken met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="69513-121">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="69513-122">Voor één rolwijziging</span><span class="sxs-lookup"><span data-stu-id="69513-122">For a single role change</span></span>

<span data-ttu-id="69513-123">De meest voorkomende manieren om het gebruikersaccount op te geven, is door de weergavenaam of de e-mailnaam te gebruiken, die ook wel de aanmeldingsnaam of de naam van de gebruikersnaam (UPN) wordt genoemd.</span><span class="sxs-lookup"><span data-stu-id="69513-123">The most common ways to specify the user account is by using its display name or its email name, which also known as its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="69513-124">Namen van gebruikersaccounts weergeven</span><span class="sxs-lookup"><span data-stu-id="69513-124">Display names of user accounts</span></span>

<span data-ttu-id="69513-125">Als u gewend bent om te werken met de weergavenamen van gebruikersaccounts, bepaalt u de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="69513-125">If you're used to working with the display names of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="69513-126">Het gebruikersaccount dat u wilt configureren</span><span class="sxs-lookup"><span data-stu-id="69513-126">The user account that you want to configure</span></span>
    
    <span data-ttu-id="69513-127">Als u het gebruikersaccount wilt opgeven, moet u de weergavenaam bepalen.</span><span class="sxs-lookup"><span data-stu-id="69513-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="69513-128">Gebruik deze opdracht om een volledige lijst met accounts te krijgen:</span><span class="sxs-lookup"><span data-stu-id="69513-128">To get a complete list of accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="69513-129">Deze opdracht bevat de weergavenaam van uw gebruikersaccounts, gesorteerd op weergavenaam, één scherm tegelijk.</span><span class="sxs-lookup"><span data-stu-id="69513-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="69513-130">U kunt de lijst filteren op een kleinere set met de **cmdlet Where.**</span><span class="sxs-lookup"><span data-stu-id="69513-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="69513-131">Zie het volgende voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="69513-131">See the following example.</span></span>

   >[!Note]
   ><span data-ttu-id="69513-132">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in hun naam.</span><span class="sxs-lookup"><span data-stu-id="69513-132">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="69513-133">Voer deze cmdlets uit vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69513-133">Run these cmdlets from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="69513-134">Deze opdracht bevat alleen de gebruikersaccounts waarvoor de weergavenaam begint met 'Jan'.</span><span class="sxs-lookup"><span data-stu-id="69513-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="69513-135">De rol die u wilt toewijzen</span><span class="sxs-lookup"><span data-stu-id="69513-135">The role you want to assign</span></span>
    
    <span data-ttu-id="69513-136">Als u de lijst met beschikbare beheerdersrollen wilt weergeven die u aan gebruikersaccounts kunt toewijzen, gebruikt u deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="69513-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="69513-137">Nadat u de weergavenaam van het account en de naam van de rol hebt bepaald, gebruikt u deze opdrachten om de rol toe te wijzen aan het account:</span><span class="sxs-lookup"><span data-stu-id="69513-137">After you determine the Display Name of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="69513-138">Plak de opdrachten in Kladblok.</span><span class="sxs-lookup"><span data-stu-id="69513-138">Paste the commands into Notepad.</span></span> <span data-ttu-id="69513-139">Voor de *$dispName* en *$roleName* variabelen vervangt u de beschrijvingstekst door de waarden.</span><span class="sxs-lookup"><span data-stu-id="69513-139">For the *$dispName* and *$roleName* variables, replace the description text with their values.</span></span> <span data-ttu-id="69513-140">Verwijder de \< and > tekens, maar bewaar de aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="69513-140">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="69513-141">Plak de gewijzigde lijnen in de Microsoft Azure Active Directory module om Windows PowerShell uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="69513-141">Paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="69513-142">U kunt ook de ise (Integrated Script Environment Windows PowerShell (Integrated Script Environment) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="69513-142">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="69513-143">Hier is een voorbeeld van een voltooide opdrachtset:</span><span class="sxs-lookup"><span data-stu-id="69513-143">Here's an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="69513-144">Aanmeldingsnamen van gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="69513-144">Sign-in names of user accounts</span></span>

<span data-ttu-id="69513-145">Als u gewend bent om te werken met de aanmeldingsnamen of UPN's van gebruikersaccounts, bepaalt u de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="69513-145">If you're used to working with the sign-in names or UPNs of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="69513-146">Upn van het gebruikersaccount</span><span class="sxs-lookup"><span data-stu-id="69513-146">The user account's UPN</span></span>
    
    <span data-ttu-id="69513-147">Als u de UPN niet kent, gebruikt u deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="69513-147">If you don't know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="69513-148">Deze opdracht bevat de UPN van uw gebruikersaccounts, gesorteerd op UPN, één scherm tegelijk.</span><span class="sxs-lookup"><span data-stu-id="69513-148">This command lists the UPN of your user accounts, sorted by UPN, one screen at a time.</span></span> <span data-ttu-id="69513-149">U kunt de cmdlet **Where** gebruiken om de lijst te filteren.</span><span class="sxs-lookup"><span data-stu-id="69513-149">You can use the **Where** cmdlet to filter the list.</span></span> <span data-ttu-id="69513-150">Hier volgt een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="69513-150">Here's an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="69513-151">Deze opdracht bevat alleen de gebruikersaccounts waarvoor de weergavenaam begint met 'Jan'.</span><span class="sxs-lookup"><span data-stu-id="69513-151">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="69513-152">De rol die u wilt toewijzen</span><span class="sxs-lookup"><span data-stu-id="69513-152">The role you want to assign</span></span>
    
    <span data-ttu-id="69513-153">Als u de lijst met beschikbare rollen wilt weergeven die u kunt toewijzen aan gebruikersaccounts, gebruikt u deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="69513-153">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="69513-154">Nadat u de UPN van het account en de naam van de rol hebt, gebruikt u deze opdrachten om de rol toe te wijzen aan het account:</span><span class="sxs-lookup"><span data-stu-id="69513-154">After you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="69513-155">Kopieer de opdrachten en plak ze in Kladblok.</span><span class="sxs-lookup"><span data-stu-id="69513-155">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="69513-156">Voor de **$upnName** en **$roleName** variabelen.</span><span class="sxs-lookup"><span data-stu-id="69513-156">For the **$upnName** and **$roleName** variables.</span></span> <span data-ttu-id="69513-157">Vervang de beschrijvingstekst door de waarden.</span><span class="sxs-lookup"><span data-stu-id="69513-157">Replace the description text with their values.</span></span> <span data-ttu-id="69513-158">Verwijder de \< and > tekens, maar bewaar de aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="69513-158">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="69513-159">Plak de gewijzigde lijnen in Microsoft Azure Active Directory module om Windows PowerShell uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="69513-159">Paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="69513-160">U kunt ook de ise Windows PowerShell gebruiken.</span><span class="sxs-lookup"><span data-stu-id="69513-160">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="69513-161">Hier is een voorbeeld van een voltooide opdrachtset:</span><span class="sxs-lookup"><span data-stu-id="69513-161">Here's an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="69513-162">Wijzigingen in meerdere rollen</span><span class="sxs-lookup"><span data-stu-id="69513-162">Multiple role changes</span></span>

<span data-ttu-id="69513-163">Voor meerdere rollenwijzigingen bepaalt u de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="69513-163">For multiple role changes, determine the following information:</span></span>
  
- <span data-ttu-id="69513-164">Welke gebruikersaccounts u wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="69513-164">Which user accounts you want to configure.</span></span> <span data-ttu-id="69513-165">U kunt de methoden in de vorige sectie gebruiken om de set weergavenamen of UPN's te verzamelen.</span><span class="sxs-lookup"><span data-stu-id="69513-165">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="69513-166">Welke rollen u wilt toewijzen aan elk gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="69513-166">Which roles you want to assign to each user account.</span></span> <span data-ttu-id="69513-167">Als u de lijst met beschikbare rollen wilt weergeven die u kunt toewijzen aan gebruikersaccounts, gebruikt u deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="69513-167">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="69513-168">Maak vervolgens een door komma's gescheiden tekstbestand (CSV) met de weergavenaam of UPN- en rolnaamvelden.</span><span class="sxs-lookup"><span data-stu-id="69513-168">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="69513-169">U kunt dit eenvoudig doen in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="69513-169">You can do this easily in Microsoft Excel.</span></span>

<span data-ttu-id="69513-170">Hier is een voorbeeld voor weergavenamen:</span><span class="sxs-lookup"><span data-stu-id="69513-170">Here's an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="69513-171">Vul vervolgens de locatie van het CSV-bestand in en voer de resulterende opdrachten uit op de opdrachtprompt van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69513-171">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="69513-172">Hier is een voorbeeld voor UPN's:</span><span class="sxs-lookup"><span data-stu-id="69513-172">Here's an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="69513-173">Vul vervolgens de locatie van het CSV-bestand in en voer de resulterende opdrachten uit op de opdrachtprompt van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69513-173">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="69513-174">Zie ook</span><span class="sxs-lookup"><span data-stu-id="69513-174">See also</span></span>

- [<span data-ttu-id="69513-175">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="69513-175">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="69513-176">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="69513-176">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="69513-177">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69513-177">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)