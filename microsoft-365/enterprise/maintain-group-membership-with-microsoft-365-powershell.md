---
title: Groepslidmaatschap van Microsoft 365 in PowerShell onderhouden
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Meer informatie over het gebruik van PowerShell om lidmaatschap te onderhouden in Microsoft 365 groepen.
ms.openlocfilehash: 464ebcebe87fcd7ce081de85e75acf76cd6d5a46
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235628"
---
# <a name="maintain-microsoft-365-group-membership-with-powershell"></a><span data-ttu-id="37d96-103">Groepslidmaatschap van Microsoft 365 in PowerShell onderhouden</span><span class="sxs-lookup"><span data-stu-id="37d96-103">Maintain Microsoft 365 group membership with PowerShell</span></span>

<span data-ttu-id="37d96-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="37d96-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="37d96-105">U kunt PowerShell voor Microsoft 365 als alternatief voor het Beheercentrum van Microsoft 365 gebruiken om groepslidmaatschappen in Microsoft 365 te onderhouden.</span><span class="sxs-lookup"><span data-stu-id="37d96-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain group membership in Microsoft 365.</span></span> 

> [!TIP]
> <span data-ttu-id="37d96-106">Als u de kant-en-klare PowerShell-opdrachten wilt genereren door gebruikersaccounts en groepen namen op te geven, gebruikt u deze [groeps onderhoud Microsoft Excel-werkmap](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx).</span><span class="sxs-lookup"><span data-stu-id="37d96-106">To generate ready-to-run PowerShell commands by specifying user account and group names, use this [group maintenance Microsoft Excel workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx).</span></span> 

>[!Note]
><span data-ttu-id="37d96-107">[Meer informatie over het beheren van groepslidmaatschappen van Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) met het microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="37d96-107">[Learn how to maintain Microsoft 365 group membership](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="37d96-108">Zie [gebruikers en groepen beheren](https://docs.microsoft.com/microsoft-365/admin/add-users/)voor een lijst met aanvullende bronnen.</span><span class="sxs-lookup"><span data-stu-id="37d96-108">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="37d96-109">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="37d96-109">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="37d96-110">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="37d96-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="37d96-111">Gebruikersaccounts toevoegen of verwijderen als lid van een groep</span><span class="sxs-lookup"><span data-stu-id="37d96-111">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="37d96-112">**Als u een gebruikersaccount wilt toevoegen aan de UPN**, vult u de User Principal Name (UPN) van het gebruikersaccount in en de naam van de groepsweergave, verwijdert u de tekens ' < ' en ' > ' en voert u deze opdrachten uit in het PowerShell-venster of in de ISE (Integrated script Environment) van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37d96-112">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="37d96-113">**Als u een gebruikersaccount wilt toevoegen op basis van de weergavenaam**, vult u de weergavenaam van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="37d96-113">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="37d96-114">**Als u een gebruikersaccount wilt verwijderen van de UPN**, vult u de UPN van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="37d96-114">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="37d96-115">**Als u een gebruikersaccount wilt verwijderen met de weergavenaam**, vult u de weergavenaam van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="37d96-115">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="37d96-116">Groepen toevoegen aan of verwijderen uit de groepsleden</span><span class="sxs-lookup"><span data-stu-id="37d96-116">Add or remove groups as members of a group</span></span>

<span data-ttu-id="37d96-117">Beveiligingsgroepen kunnen andere groepen als leden bevatten.</span><span class="sxs-lookup"><span data-stu-id="37d96-117">Security groups can contain other groups as members.</span></span> <span data-ttu-id="37d96-118">Microsoft 365 groepen is echter niet mogelijk.</span><span class="sxs-lookup"><span data-stu-id="37d96-118">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="37d96-119">Dit gedeelte bevat PowerShell-opdrachten voor het toevoegen of verwijderen van groepen voor een beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="37d96-119">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="37d96-120">**Als u een groep wilt toevoegen op basis van de weergavenaam**, vult u de weergavenaam in van de groep die u wilt toevoegen, en de weergavenaam van de groep die de leden groep bevat, en voert u deze opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="37d96-120">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="37d96-121">**Als u een groep op basis van de weergavenaam wilt verwijderen**, vult u de weergavenaam in van de groep die u wilt verwijderen en de weergavenaam van de groep die de leden groep bevat, en voert u deze opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="37d96-121">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="37d96-122">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="37d96-122">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="37d96-123">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="37d96-123">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="37d96-124">Gebruikersaccounts toevoegen of verwijderen als lid van een groep</span><span class="sxs-lookup"><span data-stu-id="37d96-124">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="37d96-125">**Als u een gebruikersaccount wilt toevoegen aan de UPN**, vult u de User Principal Name (UPN) van het gebruikersaccount in en de naam van de groepsweergave, verwijdert u de tekens ' < ' en ' > ' en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="37d96-125">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="37d96-126">**Als u een gebruikersaccount wilt toevoegen op basis van de weergavenaam**, vult u de weergavenaam van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="37d96-126">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="37d96-127">**Als u een gebruikersaccount wilt verwijderen van de UPN**, vult u de UPN van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="37d96-127">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="37d96-128">**Als u een gebruikersaccount wilt verwijderen met de weergavenaam**, vult u de weergavenaam van het gebruikersaccount in en voert u de naam van de groep in en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="37d96-128">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="37d96-129">Groepen toevoegen aan of verwijderen uit de groepsleden</span><span class="sxs-lookup"><span data-stu-id="37d96-129">Add or remove groups as members of a group</span></span>

<span data-ttu-id="37d96-130">Beveiligingsgroepen kunnen andere groepen als leden bevatten.</span><span class="sxs-lookup"><span data-stu-id="37d96-130">Security groups can contain other groups as members.</span></span> <span data-ttu-id="37d96-131">Microsoft 365 groepen is echter niet mogelijk.</span><span class="sxs-lookup"><span data-stu-id="37d96-131">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="37d96-132">Dit gedeelte bevat PowerShell-opdrachten voor het toevoegen of verwijderen van groepen voor een beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="37d96-132">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="37d96-133">**Als u een groep wilt toevoegen op basis van de weergavenaam**, vult u de weergavenaam in van de groep die u wilt toevoegen, en de weergavenaam van de groep die de leden groep bevat, en voert u deze opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="37d96-133">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="37d96-134">**Als u een groep op basis van de weergavenaam wilt verwijderen**, vult u de weergavenaam in van de groep die u wilt verwijderen en de weergavenaam van de groep die de leden groep bevat, en voert u deze opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="37d96-134">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="37d96-135">Zie ook</span><span class="sxs-lookup"><span data-stu-id="37d96-135">See also</span></span>

[<span data-ttu-id="37d96-136">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="37d96-136">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="37d96-137">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="37d96-137">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="37d96-138">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="37d96-138">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

