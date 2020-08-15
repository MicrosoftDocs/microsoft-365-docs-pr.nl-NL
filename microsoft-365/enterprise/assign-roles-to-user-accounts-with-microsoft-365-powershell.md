---
title: Rollen toewijzen aan gebruikersaccounts van Microsoft 365 met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
description: In dit artikel leest u hoe u met PowerShell voor Microsoft 365 rollen snel en gemakkelijk kunt toewijzen aan gebruikersaccounts.
ms.openlocfilehash: 4726dcea109490ff28299002bc5263aa15dca949
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688992"
---
# <a name="assign-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="cc349-103">Rollen toewijzen aan gebruikersaccounts van Microsoft 365 met PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc349-103">Assign roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="cc349-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="cc349-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="cc349-105">U kunt snel en eenvoudig rollen toewijzen aan gebruikersaccounts met behulp van PowerShell voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cc349-105">You can quickly and easily assign roles to user accounts using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="cc349-106">Als u rollen wilt toewijzen aan gebruikersaccounts met het Microsoft 365-Beheercentrum, raadpleegt u [deze instructies](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="cc349-106">To assign roles to user accounts with the Microsoft 365 admin center, see [these instructions](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="cc349-107">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="cc349-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="cc349-108">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) met behulp van een account van een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="cc349-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) using a global administrator account.</span></span>
  
<span data-ttu-id="cc349-109">Bepaal vervolgens de aanmeldingsnaam van het gebruikersaccount dat u wilt toevoegen aan een rol (voorbeeld: fredsm@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cc349-109">Next, determine the sign-in name of the user account that you want to add to a role (example: fredsm@contoso.com).</span></span> <span data-ttu-id="cc349-110">Dit wordt ook wel de UPN (User Principal Name) genoemd.</span><span class="sxs-lookup"><span data-stu-id="cc349-110">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="cc349-111">Bepaal vervolgens de naam van de rol.</span><span class="sxs-lookup"><span data-stu-id="cc349-111">Next, determine the name of the role.</span></span> <span data-ttu-id="cc349-112">Gebruik deze [lijst met machtigingen voor beheerdersrollen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="cc349-112">Use this [list of administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="cc349-113">Let op de notities in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="cc349-113">Pay attention to the notes in this article.</span></span> <span data-ttu-id="cc349-114">Sommige namen van rollen zijn verschillend voor Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc349-114">Some role names are different for Azure AD PowerShell.</span></span> <span data-ttu-id="cc349-115">De rol ' SharePoint-beheerder ' in het Microsoft 365-Beheercentrum heeft bijvoorbeeld de naam SharePoint Service beheerder voor Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc349-115">For example, the "SharePoint Administrator" role in the Microsoft 365 admin center is named "SharePoint Service Administrator" for Azure AD PowerShell.</span></span>
>

<span data-ttu-id="cc349-116">Vul vervolgens de namen van de aanmeld-en rollen in en voer deze opdrachten uit.</span><span class="sxs-lookup"><span data-stu-id="cc349-116">Next, fill in the sign-in and role names and run these commands.</span></span>
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="cc349-117">Hier ziet u een voorbeeld van een voltooide opdrachtenset waarmee de rol van SharePoint-Service beheerder wordt toegewezen aan het belindan@contoso.com-account:</span><span class="sxs-lookup"><span data-stu-id="cc349-117">Here is an example of a completed command set that assigns the SharePoint Service Administrator role to the belindan@contoso.com account:</span></span>
  
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

<span data-ttu-id="cc349-118">Met deze opdrachten kunt u de lijst met gebruikersnamen voor een bepaalde rol weergeven.</span><span class="sxs-lookup"><span data-stu-id="cc349-118">To display the list of user names for a specific role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="cc349-119">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="cc349-119">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="cc349-120">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) met behulp van een account van een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="cc349-120">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) using a global administrator account.</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="cc349-121">Voor één wijziging van een rol</span><span class="sxs-lookup"><span data-stu-id="cc349-121">For a single role change</span></span>

<span data-ttu-id="cc349-122">De meest voorkomende manier van een specifiek gebruikersaccount is de naam van de weergave of de e-mail naam van de persoon, ook bekend als de naam van de aanmelding of de UPN (User Principal Name).</span><span class="sxs-lookup"><span data-stu-id="cc349-122">The most common ways of specific user account is with its display name or its email name, also known its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="cc349-123">Namen van gebruikersaccounts weergeven</span><span class="sxs-lookup"><span data-stu-id="cc349-123">Display names of user accounts</span></span>

<span data-ttu-id="cc349-124">Als u werkt met de weergavenamen van gebruikersaccounts, bepaalt u het volgende:</span><span class="sxs-lookup"><span data-stu-id="cc349-124">If you are used to working with the display names of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="cc349-125">Het gebruikersaccount dat u wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="cc349-125">The user account that you want to configure.</span></span>
    
    <span data-ttu-id="cc349-126">Als u het gebruikersaccount wilt opgeven, moet u de weergavenaam ervan bepalen.</span><span class="sxs-lookup"><span data-stu-id="cc349-126">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="cc349-127">Voor een volledige lijst van accounts gebruikt u deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="cc349-127">To get a complete list accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="cc349-128">Met deze opdracht wordt de weergavenaam van uw gebruikersaccounts weergegeven, gesorteerd op de weergavenaam, één scherm tegelijkertijd.</span><span class="sxs-lookup"><span data-stu-id="cc349-128">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="cc349-129">U kunt de lijst filteren op een kleinere set met behulp **van de cmdlet** -cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cc349-129">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="cc349-130">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="cc349-130">Here is an example:</span></span>

   >[!Note]
   ><span data-ttu-id="cc349-131">De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam.</span><span class="sxs-lookup"><span data-stu-id="cc349-131">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="cc349-132">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc349-132">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="cc349-133">Met deze opdracht worden alleen de gebruikersaccounts weergegeven waarvoor de weergavenaam begint met ' John '.</span><span class="sxs-lookup"><span data-stu-id="cc349-133">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="cc349-134">De rol die u wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="cc349-134">The role you want to assign.</span></span>
    
    <span data-ttu-id="cc349-135">Met de volgende opdracht kunt u de lijst met beschikbare rollen weergeven die u kunt toewijzen aan gebruikersaccounts:</span><span class="sxs-lookup"><span data-stu-id="cc349-135">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="cc349-136">Wanneer u de weergavenaam van het account en de naam van de rol hebt vastgesteld, kunt u deze opdrachten gebruiken om de rol aan het account toe te wijzen:</span><span class="sxs-lookup"><span data-stu-id="cc349-136">Once you have determined the Display Name of the account and the Name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="cc349-137">Kopieer de opdrachten en plak deze in Kladblok.</span><span class="sxs-lookup"><span data-stu-id="cc349-137">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="cc349-138">Voor de **$dispName** en **$roleName** variabelen vervangt u de beschrijvende tekst door de bijbehorende waarden, verwijdert u de \< and > tekens en verlaat u de aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="cc349-138">For the **$dispName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="cc349-139">Kopieer de gewijzigde regels en plak ze in het venster Windows Azure Active Directory voor Windows PowerShell om ze uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="cc349-139">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="cc349-140">U kunt ook gebruikmaken van de Windows PowerShell Integrated script Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="cc349-140">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="cc349-141">Hier ziet u een voorbeeld van een voltooide opdrachtreeks:</span><span class="sxs-lookup"><span data-stu-id="cc349-141">Here is an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="cc349-142">Aanmeldingsnamen van gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="cc349-142">Sign-in names of user accounts</span></span>

<span data-ttu-id="cc349-143">Als u gebruikmaakt van aanmeldingsnamen of Upn's van gebruikersaccounts, controleert u het volgende:</span><span class="sxs-lookup"><span data-stu-id="cc349-143">If you are used to working with the sign-in names or UPNs of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="cc349-144">De UPN van de gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="cc349-144">The user account's UPN.</span></span>
    
    <span data-ttu-id="cc349-145">Als u de UPN nog niet weet, gebruikt u deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="cc349-145">If you don't already know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="cc349-146">Met deze opdracht wordt de UPN van uw gebruikersaccounts weergegeven, gesorteerd op de UPN, één scherm tegelijkertijd.</span><span class="sxs-lookup"><span data-stu-id="cc349-146">This command lists the UPN of your user accounts, sorted by the UPN, one screen at a time.</span></span> <span data-ttu-id="cc349-147">U kunt de lijst filteren op een kleinere set met behulp **van de cmdlet** -cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cc349-147">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="cc349-148">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="cc349-148">Here is an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="cc349-149">Met deze opdracht worden alleen de gebruikersaccounts weergegeven waarvoor de weergavenaam begint met ' John '.</span><span class="sxs-lookup"><span data-stu-id="cc349-149">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="cc349-150">De rol die u wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="cc349-150">The role you want to assign.</span></span>
    
    <span data-ttu-id="cc349-151">Met de volgende opdracht kunt u de lijst met beschikbare rollen weergeven die u kunt toewijzen aan gebruikersaccounts:</span><span class="sxs-lookup"><span data-stu-id="cc349-151">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="cc349-152">Wanneer u de UPN van het account en de naam van de rol hebt, kunt u deze opdrachten gebruiken om de rol aan het account toe te wijzen:</span><span class="sxs-lookup"><span data-stu-id="cc349-152">Once you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="cc349-153">Kopieer de opdrachten en plak deze in Kladblok.</span><span class="sxs-lookup"><span data-stu-id="cc349-153">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="cc349-154">Voor de **$upnName** en **$roleName** variabelen vervangt u de beschrijvende tekst door de bijbehorende waarden, verwijdert u de \< and > tekens en verlaat u de aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="cc349-154">For the **$upnName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="cc349-155">Kopieer de gewijzigde regels en plak ze in het venster Windows Azure Active Directory voor Windows PowerShell om ze uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="cc349-155">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="cc349-156">U kunt ook het Windows PowerShell-ISE gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cc349-156">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="cc349-157">Hier ziet u een voorbeeld van een voltooide opdrachtreeks:</span><span class="sxs-lookup"><span data-stu-id="cc349-157">Here is an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="cc349-158">Wijzigingen in meerdere rollen</span><span class="sxs-lookup"><span data-stu-id="cc349-158">Multiple role changes</span></span>

<span data-ttu-id="cc349-159">Voor wijzigingen in meerdere rollen, controleert u het volgende:</span><span class="sxs-lookup"><span data-stu-id="cc349-159">For multiple role changes, determine the following:</span></span>
  
- <span data-ttu-id="cc349-160">De gebruikersaccounts die u wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="cc349-160">Which user accounts that you want to configure.</span></span> <span data-ttu-id="cc349-161">U kunt de methoden in de vorige sectie gebruiken om de set weergavenamen of-Upn's te verzamelen.</span><span class="sxs-lookup"><span data-stu-id="cc349-161">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="cc349-162">Welke rollen u wilt toewijzen aan de gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="cc349-162">Which roles you want to assign to each user account.</span></span>
    
    <span data-ttu-id="cc349-163">Met de volgende opdracht kunt u de lijst met beschikbare rollen weergeven die u kunt toewijzen aan gebruikersaccounts:</span><span class="sxs-lookup"><span data-stu-id="cc349-163">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="cc349-164">Maak vervolgens een tekstbestand met door komma's gescheiden waarden (CSV) met de velden weergavenaam of UPN en rollen namen.</span><span class="sxs-lookup"><span data-stu-id="cc349-164">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="cc349-165">U kunt dit eenvoudig doen met Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="cc349-165">You can do this easily with Microsoft Excel.</span></span>

<span data-ttu-id="cc349-166">Hier ziet u een voorbeeld van weergavenamen:</span><span class="sxs-lookup"><span data-stu-id="cc349-166">Here is an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="cc349-167">Vul vervolgens de locatie van het CSV-bestand in en voer de resultaat opdrachten uit op de PowerShell-opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="cc349-167">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="cc349-168">Hier ziet u een voorbeeld voor Upn's:</span><span class="sxs-lookup"><span data-stu-id="cc349-168">Here is an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="cc349-169">Vul vervolgens de locatie van het CSV-bestand in en voer de resultaat opdrachten uit op de PowerShell-opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="cc349-169">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="cc349-170">Zie ook</span><span class="sxs-lookup"><span data-stu-id="cc349-170">See also</span></span>

- [<span data-ttu-id="cc349-171">Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc349-171">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cc349-172">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc349-172">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cc349-173">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc349-173">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
