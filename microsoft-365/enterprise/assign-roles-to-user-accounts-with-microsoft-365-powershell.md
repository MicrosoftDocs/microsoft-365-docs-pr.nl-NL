---
title: Rollen toewijzen aan gebruikersaccounts van Microsoft 365 met PowerShell
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
description: In dit artikel leest u hoe u met PowerShell voor Microsoft 365 rollen snel en gemakkelijk kunt toewijzen aan gebruikersaccounts.
ms.openlocfilehash: 9df1b018cf3e89e0afbd5265fdd1ec9f92b34aec
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235428"
---
# <a name="assign-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="9b6c4-103">Rollen toewijzen aan gebruikersaccounts van Microsoft 365 met PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b6c4-103">Assign roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="9b6c4-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9b6c4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9b6c4-105">U kunt snel en eenvoudig rollen toewijzen aan gebruikersaccounts met behulp van PowerShell voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-105">You can quickly and easily assign roles to user accounts using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="9b6c4-106">[Meer informatie over het toewijzen van rollen aan gebruikersaccounts](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) met het microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-106">[Learn how to assign roles to user accounts](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="9b6c4-107">Zie [gebruikers en groepen beheren](https://docs.microsoft.com/microsoft-365/admin/add-users/)voor een lijst met aanvullende bronnen.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="9b6c4-108">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="9b6c4-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="9b6c4-109">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) met behulp van een account van een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) using a global administrator account.</span></span>
  
<span data-ttu-id="9b6c4-110">Bepaal vervolgens de aanmeldingsnaam van het gebruikersaccount dat u wilt toevoegen aan een rol (voorbeeld: fredsm@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9b6c4-110">Next, determine the sign-in name of the user account that you want to add to a role (example: fredsm@contoso.com).</span></span> <span data-ttu-id="9b6c4-111">Dit wordt ook wel de UPN (User Principal Name) genoemd.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="9b6c4-112">Bepaal vervolgens de naam van de rol.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-112">Next, determine the name of the role.</span></span> <span data-ttu-id="9b6c4-113">Gebruik deze [lijst met machtigingen voor beheerdersrollen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="9b6c4-113">Use this [list of administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="9b6c4-114">Let op de notities in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="9b6c4-115">Sommige namen van rollen zijn verschillend voor Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-115">Some role names are different for Azure AD PowerShell.</span></span> <span data-ttu-id="9b6c4-116">De rol ' SharePoint-beheerder ' in het Microsoft 365-Beheercentrum heeft bijvoorbeeld de naam SharePoint Service beheerder voor Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-116">For example, the "SharePoint Administrator" role in the Microsoft 365 admin center is named "SharePoint Service Administrator" for Azure AD PowerShell.</span></span>
>

<span data-ttu-id="9b6c4-117">Vul vervolgens de namen van de aanmeld-en rollen in en voer deze opdrachten uit.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-117">Next, fill in the sign-in and role names and run these commands.</span></span>
  
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

<span data-ttu-id="9b6c4-118">Hier ziet u een voorbeeld van een voltooide opdrachtenset waarmee de rol van SharePoint-Service beheerder wordt toegewezen aan het belindan@contoso.com-account:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-118">Here is an example of a completed command set that assigns the SharePoint Service Administrator role to the belindan@contoso.com account:</span></span>
  
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

<span data-ttu-id="9b6c4-119">Met deze opdrachten kunt u de lijst met gebruikersnamen voor een bepaalde rol weergeven.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-119">To display the list of user names for a specific role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="9b6c4-120">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="9b6c4-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="9b6c4-121">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) met behulp van een account van een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-121">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) using a global administrator account.</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="9b6c4-122">Voor één wijziging van een rol</span><span class="sxs-lookup"><span data-stu-id="9b6c4-122">For a single role change</span></span>

<span data-ttu-id="9b6c4-123">De meest voorkomende manier van een specifiek gebruikersaccount is de naam van de weergave of de e-mail naam van de persoon, ook bekend als de naam van de aanmelding of de UPN (User Principal Name).</span><span class="sxs-lookup"><span data-stu-id="9b6c4-123">The most common ways of specific user account is with its display name or its email name, also known its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="9b6c4-124">Namen van gebruikersaccounts weergeven</span><span class="sxs-lookup"><span data-stu-id="9b6c4-124">Display names of user accounts</span></span>

<span data-ttu-id="9b6c4-125">Als u werkt met de weergavenamen van gebruikersaccounts, bepaalt u het volgende:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-125">If you are used to working with the display names of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="9b6c4-126">Het gebruikersaccount dat u wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-126">The user account that you want to configure.</span></span>
    
    <span data-ttu-id="9b6c4-127">Als u het gebruikersaccount wilt opgeven, moet u de weergavenaam ervan bepalen.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="9b6c4-128">Voor een volledige lijst van accounts gebruikt u deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-128">To get a complete list accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="9b6c4-129">Met deze opdracht wordt de weergavenaam van uw gebruikersaccounts weergegeven, gesorteerd op de weergavenaam, één scherm tegelijkertijd.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="9b6c4-130">U kunt de lijst filteren op een kleinere set met behulp **van de cmdlet** -cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="9b6c4-131">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-131">Here is an example:</span></span>

   >[!Note]
   ><span data-ttu-id="9b6c4-132">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-132">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="9b6c4-133">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-133">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="9b6c4-134">Met deze opdracht worden alleen de gebruikersaccounts weergegeven waarvoor de weergavenaam begint met ' John '.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="9b6c4-135">De rol die u wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-135">The role you want to assign.</span></span>
    
    <span data-ttu-id="9b6c4-136">Met de volgende opdracht kunt u de lijst met beschikbare rollen weergeven die u kunt toewijzen aan gebruikersaccounts:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-136">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="9b6c4-137">Wanneer u de weergavenaam van het account en de naam van de rol hebt vastgesteld, kunt u deze opdrachten gebruiken om de rol aan het account toe te wijzen:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-137">Once you have determined the Display Name of the account and the Name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="9b6c4-138">Kopieer de opdrachten en plak deze in Kladblok.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-138">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="9b6c4-139">Voor de **$dispName** en **$roleName** variabelen vervangt u de beschrijvende tekst door de bijbehorende waarden, verwijdert u de \< and > tekens en verlaat u de aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-139">For the **$dispName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="9b6c4-140">Kopieer de gewijzigde regels en plak ze in het venster Windows Azure Active Directory voor Windows PowerShell om ze uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-140">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="9b6c4-141">U kunt ook gebruikmaken van de Windows PowerShell Integrated script Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="9b6c4-141">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="9b6c4-142">Hier ziet u een voorbeeld van een voltooide opdrachtreeks:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-142">Here is an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="9b6c4-143">Aanmeldingsnamen van gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="9b6c4-143">Sign-in names of user accounts</span></span>

<span data-ttu-id="9b6c4-144">Als u gebruikmaakt van aanmeldingsnamen of Upn's van gebruikersaccounts, controleert u het volgende:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-144">If you are used to working with the sign-in names or UPNs of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="9b6c4-145">De UPN van de gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-145">The user account's UPN.</span></span>
    
    <span data-ttu-id="9b6c4-146">Als u de UPN nog niet weet, gebruikt u deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-146">If you don't already know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="9b6c4-147">Met deze opdracht wordt de UPN van uw gebruikersaccounts weergegeven, gesorteerd op de UPN, één scherm tegelijkertijd.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-147">This command lists the UPN of your user accounts, sorted by the UPN, one screen at a time.</span></span> <span data-ttu-id="9b6c4-148">U kunt de lijst filteren op een kleinere set met behulp **van de cmdlet** -cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-148">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="9b6c4-149">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-149">Here is an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="9b6c4-150">Met deze opdracht worden alleen de gebruikersaccounts weergegeven waarvoor de weergavenaam begint met ' John '.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-150">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="9b6c4-151">De rol die u wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-151">The role you want to assign.</span></span>
    
    <span data-ttu-id="9b6c4-152">Met de volgende opdracht kunt u de lijst met beschikbare rollen weergeven die u kunt toewijzen aan gebruikersaccounts:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-152">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="9b6c4-153">Wanneer u de UPN van het account en de naam van de rol hebt, kunt u deze opdrachten gebruiken om de rol aan het account toe te wijzen:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-153">Once you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="9b6c4-154">Kopieer de opdrachten en plak deze in Kladblok.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-154">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="9b6c4-155">Voor de **$upnName** en **$roleName** variabelen vervangt u de beschrijvende tekst door de bijbehorende waarden, verwijdert u de \< and > tekens en verlaat u de aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-155">For the **$upnName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="9b6c4-156">Kopieer de gewijzigde regels en plak ze in het venster Windows Azure Active Directory voor Windows PowerShell om ze uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-156">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="9b6c4-157">U kunt ook het Windows PowerShell-ISE gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-157">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="9b6c4-158">Hier ziet u een voorbeeld van een voltooide opdrachtreeks:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-158">Here is an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="9b6c4-159">Wijzigingen in meerdere rollen</span><span class="sxs-lookup"><span data-stu-id="9b6c4-159">Multiple role changes</span></span>

<span data-ttu-id="9b6c4-160">Voor wijzigingen in meerdere rollen, controleert u het volgende:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-160">For multiple role changes, determine the following:</span></span>
  
- <span data-ttu-id="9b6c4-161">De gebruikersaccounts die u wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-161">Which user accounts that you want to configure.</span></span> <span data-ttu-id="9b6c4-162">U kunt de methoden in de vorige sectie gebruiken om de set weergavenamen of-Upn's te verzamelen.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-162">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="9b6c4-163">Welke rollen u wilt toewijzen aan de gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-163">Which roles you want to assign to each user account.</span></span>
    
    <span data-ttu-id="9b6c4-164">Met de volgende opdracht kunt u de lijst met beschikbare rollen weergeven die u kunt toewijzen aan gebruikersaccounts:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-164">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="9b6c4-165">Maak vervolgens een tekstbestand met door komma's gescheiden waarden (CSV) met de velden weergavenaam of UPN en rollen namen.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-165">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="9b6c4-166">U kunt dit eenvoudig doen met Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-166">You can do this easily with Microsoft Excel.</span></span>

<span data-ttu-id="9b6c4-167">Hier ziet u een voorbeeld van weergavenamen:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-167">Here is an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="9b6c4-168">Vul vervolgens de locatie van het CSV-bestand in en voer de resultaat opdrachten uit op de PowerShell-opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-168">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="9b6c4-169">Hier ziet u een voorbeeld voor Upn's:</span><span class="sxs-lookup"><span data-stu-id="9b6c4-169">Here is an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="9b6c4-170">Vul vervolgens de locatie van het CSV-bestand in en voer de resultaat opdrachten uit op de PowerShell-opdrachtprompt.</span><span class="sxs-lookup"><span data-stu-id="9b6c4-170">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="9b6c4-171">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9b6c4-171">See also</span></span>

- [<span data-ttu-id="9b6c4-172">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b6c4-172">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="9b6c4-173">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b6c4-173">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="9b6c4-174">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9b6c4-174">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
