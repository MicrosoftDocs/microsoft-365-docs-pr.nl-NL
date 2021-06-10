---
title: Lidmaatschap van beveiligingsgroep behouden met PowerShell
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
description: Meer informatie over het gebruik van PowerShell om het lidmaatschap van Microsoft 365 behouden.
ms.openlocfilehash: 9696c9093ae6f24a2edaf544e80794bde45d18d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909572"
---
# <a name="maintain-security-group-membership-with-powershell"></a><span data-ttu-id="d0d58-103">Lidmaatschap van beveiligingsgroep behouden met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0d58-103">Maintain security group membership with PowerShell</span></span>

<span data-ttu-id="d0d58-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d0d58-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d0d58-105">U kunt PowerShell voor Microsoft 365 gebruiken als alternatief voor het Microsoft 365-beheercentrum om het lidmaatschap van beveiligingsgroep in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d0d58-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain security group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="d0d58-106">[Lees hoe u het lidmaatschap van Microsoft 365 groep kunt behouden](../admin/create-groups/add-or-remove-members-from-groups.md) met het Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d0d58-106">[Learn how to maintain Microsoft 365 group membership](../admin/create-groups/add-or-remove-members-from-groups.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="d0d58-107">Zie Gebruikers en groepen beheren voor een lijst met [aanvullende bronnen.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="d0d58-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="d0d58-108">De powershell Azure Active Directory powershell gebruiken voor Graph module</span><span class="sxs-lookup"><span data-stu-id="d0d58-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="d0d58-109">Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="d0d58-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="d0d58-110">Gebruikersaccounts toevoegen of verwijderen als leden van een groep</span><span class="sxs-lookup"><span data-stu-id="d0d58-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="d0d58-111">Als u een gebruikersaccount wilt toevoegen op basis van **de UPN,** vult u de user account User Principal Name (UPN) in (bijvoorbeeld: belindan@contoso.com) en de weergavenaam van de beveiligingsgroep, verwijdert u de tekens '<' en '>' en voert u deze opdrachten uit in het PowerShell-venster of de Geïntegreerde Scriptomgeving van PowerShell (ISE).</span><span class="sxs-lookup"><span data-stu-id="d0d58-111">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the security group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="d0d58-112">Als u een gebruikersaccount wilt toevoegen op de weergavenaam, vult u de weergavenaam van het gebruikersaccount in (bijvoorbeeld Belinda Newman) en de weergavenaam van de groep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.</span><span class="sxs-lookup"><span data-stu-id="d0d58-112">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="d0d58-113">Als u een gebruikersaccount wilt verwijderen met **de UPN,** vult u de UPN van het gebruikersaccount in (bijvoorbeeld: belindan@contoso.com) en de weergavenaam van de groep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="d0d58-113">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="d0d58-114">Als u een **gebruikersaccount** wilt verwijderen op de weergavenaam, vult u de weergavenaam van het gebruikersaccount in (bijvoorbeeld Belinda Newman) en de weergavenaam van de groep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.</span><span class="sxs-lookup"><span data-stu-id="d0d58-114">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="d0d58-115">Groepen toevoegen of verwijderen als leden van een groep</span><span class="sxs-lookup"><span data-stu-id="d0d58-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="d0d58-116">Beveiligingsgroepen kunnen andere groepen als leden bevatten.</span><span class="sxs-lookup"><span data-stu-id="d0d58-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="d0d58-117">Microsoft 365 groepen kunnen echter niet.</span><span class="sxs-lookup"><span data-stu-id="d0d58-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="d0d58-118">Deze sectie bevat PowerShell-opdrachten om groepen alleen voor een beveiligingsgroep toe te voegen of te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d0d58-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="d0d58-119">Als u een groep wilt toevoegen op de weergavenaam, vult u de weergavenaam in van de groep die u gaat toevoegen en de weergavenaam van de groep die de ledengroep bevat en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.</span><span class="sxs-lookup"><span data-stu-id="d0d58-119">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="d0d58-120">Als u een groep wilt verwijderen op de weergavenaam, vult u de weergavenaam in van de groep die u gaat verwijderen en de weergavenaam van de groep met de ledengroep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.</span><span class="sxs-lookup"><span data-stu-id="d0d58-120">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="d0d58-121">Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0d58-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="d0d58-122">Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="d0d58-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="d0d58-123">Gebruikersaccounts toevoegen of verwijderen als leden van een groep</span><span class="sxs-lookup"><span data-stu-id="d0d58-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="d0d58-124">Als u een gebruikersaccount wilt toevoegen op basis van **de UPN,** vult u de upn (User Principal Name) (user account User Principal Name) (voorbeeld: belindan@contoso.com) en de weergavenaam van de groep in, verwijdert u de tekens '<' en '>' en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.</span><span class="sxs-lookup"><span data-stu-id="d0d58-124">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="d0d58-125">Als u een gebruikersaccount wilt toevoegen op de weergavenaam, vult u de weergavenaam van het gebruikersaccount in (bijvoorbeeld Belinda Newman) en de weergavenaam van de groep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.</span><span class="sxs-lookup"><span data-stu-id="d0d58-125">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="d0d58-126">Als u een gebruikersaccount wilt verwijderen met **de UPN,** vult u de UPN van het gebruikersaccount in (bijvoorbeeld: belindan@contoso.com) en de weergavenaam van de groep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="d0d58-126">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="d0d58-127">Als u een **gebruikersaccount** wilt verwijderen op de weergavenaam, vult u de weergavenaam van het gebruikersaccount in (bijvoorbeeld Belinda Newman) en de weergavenaam van de groep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.</span><span class="sxs-lookup"><span data-stu-id="d0d58-127">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="d0d58-128">Groepen toevoegen of verwijderen als leden van een groep</span><span class="sxs-lookup"><span data-stu-id="d0d58-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="d0d58-129">Beveiligingsgroepen kunnen andere groepen als leden bevatten.</span><span class="sxs-lookup"><span data-stu-id="d0d58-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="d0d58-130">Microsoft 365 groepen kunnen echter niet.</span><span class="sxs-lookup"><span data-stu-id="d0d58-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="d0d58-131">Deze sectie bevat PowerShell-opdrachten om groepen alleen voor een beveiligingsgroep toe te voegen of te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d0d58-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="d0d58-132">Als u een groep wilt toevoegen op de weergavenaam, vult u de weergavenaam in van de groep die u gaat toevoegen en de weergavenaam van de groep die de ledengroep bevat en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.</span><span class="sxs-lookup"><span data-stu-id="d0d58-132">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="d0d58-133">Als u een groep wilt verwijderen op de weergavenaam, vult u de weergavenaam in van de groep die u gaat verwijderen en de weergavenaam van de groep met de ledengroep en voert u deze opdrachten uit in het PowerShell-venster of de PowerShell-ise.</span><span class="sxs-lookup"><span data-stu-id="d0d58-133">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="d0d58-134">Zie ook</span><span class="sxs-lookup"><span data-stu-id="d0d58-134">See also</span></span>

[<span data-ttu-id="d0d58-135">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0d58-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d0d58-136">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0d58-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d0d58-137">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d0d58-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)