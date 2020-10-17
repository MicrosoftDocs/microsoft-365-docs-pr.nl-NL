---
title: Groepslidmaatschap van Microsoft 365 in PowerShell onderhouden
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Meer informatie over het gebruik van PowerShell om lidmaatschap te onderhouden in Microsoft 365 groepen.
ms.openlocfilehash: 7763f4275ff31f3dc26aa7fecba93e545f7c7644
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580972"
---
# <a name="maintain-microsoft-365-group-membership-with-powershell"></a><span data-ttu-id="b58ad-103">Groepslidmaatschap van Microsoft 365 in PowerShell onderhouden</span><span class="sxs-lookup"><span data-stu-id="b58ad-103">Maintain Microsoft 365 group membership with PowerShell</span></span>

<span data-ttu-id="b58ad-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b58ad-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b58ad-105">U kunt PowerShell voor Microsoft 365 als alternatief voor het Beheercentrum van Microsoft 365 gebruiken om groepslidmaatschappen in Microsoft 365 te onderhouden.</span><span class="sxs-lookup"><span data-stu-id="b58ad-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="b58ad-106">[Meer informatie over het beheren van groepslidmaatschappen van Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) met het microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="b58ad-106">[Learn how to maintain Microsoft 365 group membership](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="b58ad-107">Zie [gebruikers en groepen beheren](https://docs.microsoft.com/microsoft-365/admin/add-users/)voor een lijst met aanvullende bronnen.</span><span class="sxs-lookup"><span data-stu-id="b58ad-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="b58ad-108">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="b58ad-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="b58ad-109">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="b58ad-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="b58ad-110">Gebruikersaccounts toevoegen of verwijderen als lid van een groep</span><span class="sxs-lookup"><span data-stu-id="b58ad-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="b58ad-111">**Als u een gebruikersaccount wilt toevoegen aan de UPN**, vult u de User Principal Name (UPN) van het gebruikersaccount in en de naam van de groepsweergave, verwijdert u de tekens ' < ' en ' > ' en voert u deze opdrachten uit in het PowerShell-venster of in de ISE (Integrated script Environment) van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b58ad-111">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="b58ad-112">**Als u een gebruikersaccount wilt toevoegen op basis van de weergavenaam**, vult u de weergavenaam van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="b58ad-112">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="b58ad-113">**Als u een gebruikersaccount wilt verwijderen van de UPN**, vult u de UPN van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="b58ad-113">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="b58ad-114">**Als u een gebruikersaccount wilt verwijderen met de weergavenaam**, vult u de weergavenaam van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="b58ad-114">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="b58ad-115">Groepen toevoegen aan of verwijderen uit de groepsleden</span><span class="sxs-lookup"><span data-stu-id="b58ad-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="b58ad-116">Beveiligingsgroepen kunnen andere groepen als leden bevatten.</span><span class="sxs-lookup"><span data-stu-id="b58ad-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="b58ad-117">Microsoft 365 groepen is echter niet mogelijk.</span><span class="sxs-lookup"><span data-stu-id="b58ad-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="b58ad-118">Dit gedeelte bevat PowerShell-opdrachten voor het toevoegen of verwijderen van groepen voor een beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="b58ad-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="b58ad-119">**Als u een groep wilt toevoegen op basis van de weergavenaam**, vult u de weergavenaam in van de groep die u wilt toevoegen, en de weergavenaam van de groep die de leden groep bevat, en voert u deze opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="b58ad-119">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="b58ad-120">**Als u een groep op basis van de weergavenaam wilt verwijderen**, vult u de weergavenaam in van de groep die u wilt verwijderen en de weergavenaam van de groep die de leden groep bevat, en voert u deze opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="b58ad-120">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="b58ad-121">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="b58ad-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="b58ad-122">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b58ad-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="b58ad-123">Gebruikersaccounts toevoegen of verwijderen als lid van een groep</span><span class="sxs-lookup"><span data-stu-id="b58ad-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="b58ad-124">**Als u een gebruikersaccount wilt toevoegen aan de UPN**, vult u de User Principal Name (UPN) van het gebruikersaccount in en de naam van de groepsweergave, verwijdert u de tekens ' < ' en ' > ' en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="b58ad-124">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="b58ad-125">**Als u een gebruikersaccount wilt toevoegen op basis van de weergavenaam**, vult u de weergavenaam van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="b58ad-125">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="b58ad-126">**Als u een gebruikersaccount wilt verwijderen van de UPN**, vult u de UPN van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="b58ad-126">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="b58ad-127">**Als u een gebruikersaccount wilt verwijderen met de weergavenaam**, vult u de weergavenaam van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="b58ad-127">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="b58ad-128">Groepen toevoegen aan of verwijderen uit de groepsleden</span><span class="sxs-lookup"><span data-stu-id="b58ad-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="b58ad-129">Beveiligingsgroepen kunnen andere groepen als leden bevatten.</span><span class="sxs-lookup"><span data-stu-id="b58ad-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="b58ad-130">Microsoft 365 groepen is echter niet mogelijk.</span><span class="sxs-lookup"><span data-stu-id="b58ad-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="b58ad-131">Dit gedeelte bevat PowerShell-opdrachten voor het toevoegen of verwijderen van groepen voor een beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="b58ad-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="b58ad-132">**Als u een groep wilt toevoegen op basis van de weergavenaam**, vult u de weergavenaam in van de groep die u wilt toevoegen, en de weergavenaam van de groep die de leden groep bevat, en voert u deze opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="b58ad-132">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="b58ad-133">**Als u een groep op basis van de weergavenaam wilt verwijderen**, vult u de weergavenaam in van de groep die u wilt verwijderen en de weergavenaam van de groep die de leden groep bevat, en voert u deze opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="b58ad-133">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="b58ad-134">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b58ad-134">See also</span></span>

[<span data-ttu-id="b58ad-135">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b58ad-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b58ad-136">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="b58ad-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b58ad-137">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b58ad-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

