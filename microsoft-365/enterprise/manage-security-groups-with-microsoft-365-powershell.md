---
title: Beveiligingsgroepen beheren met PowerShell
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
description: Meer informatie over het gebruik van PowerShell voor het beheren van beveiligingsgroepen.
ms.openlocfilehash: a52fcf6a20598e92f9d5ac8d673a4b1c026030f8
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073205"
---
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="1e8f7-103">Beveiligingsgroepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e8f7-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="1e8f7-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1e8f7-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1e8f7-105">U kunt PowerShell voor Microsoft 365 als alternatief gebruiken voor het Beheercentrum van Microsoft 365 voor het beheren van beveiligingsgroepen.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="1e8f7-106">In dit artikel wordt beschreven hoe u de lijst, het maken, wijzigen van instellingen en beveiligingsgroepen verwijdert.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="1e8f7-107">Voer de volgende stappen uit als u in dit artikel de waarde van een variabele moet opgeven voor een opdracht blokkering in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="1e8f7-108">Kopieer het opdracht blok naar het Klembord en plak dit in Kladblok of in de ISE (Integrated script Environment) van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="1e8f7-109">Vul de waarden voor de variabele in en verwijder de tekens "<" en ">".</span><span class="sxs-lookup"><span data-stu-id="1e8f7-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="1e8f7-110">Voer de opdrachten uit in het PowerShell-venster of in het PowerShell-ISE.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="1e8f7-111">Zie [lidmaatschap van beveiligingsgroepen onderhouden](maintain-group-membership-with-microsoft-365-powershell.md) om groepslidmaatschap te beheren met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1e8f7-112">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="1e8f7-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1e8f7-113">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="1e8f7-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="1e8f7-114">Uw groepen weergeven</span><span class="sxs-lookup"><span data-stu-id="1e8f7-114">List your groups</span></span>

<span data-ttu-id="1e8f7-115">Gebruik deze opdracht om alle groepen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="1e8f7-116">Met deze opdrachten kunt u de instellingen van een specifieke groep weergeven op basis van de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="1e8f7-117">Een nieuwe groep maken</span><span class="sxs-lookup"><span data-stu-id="1e8f7-117">Create a new group</span></span>

<span data-ttu-id="1e8f7-118">Gebruik deze opdracht om een nieuwe beveiligingsgroep te maken.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="1e8f7-119">De instellingen van een groep wijzigen</span><span class="sxs-lookup"><span data-stu-id="1e8f7-119">Change the settings on a group</span></span>

<span data-ttu-id="1e8f7-120">De instellingen van de groep met deze opdrachten weergeven.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="1e8f7-121">Gebruik vervolgens het artikel [set-AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) om te bepalen hoe u een instelling kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-121">Then, use the [Set-AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="1e8f7-122">Een beveiligingsgroep verwijderen</span><span class="sxs-lookup"><span data-stu-id="1e8f7-122">Remove a security group</span></span>

<span data-ttu-id="1e8f7-123">Met deze opdrachten kunt u een beveiligingsgroep verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="1e8f7-124">De eigenaren van een beveiligingsgroep beheren</span><span class="sxs-lookup"><span data-stu-id="1e8f7-124">Manage the owners of a security group</span></span>

<span data-ttu-id="1e8f7-125">Met deze opdrachten kunt u de huidige eigenaren van een beveiligingsgroep weergeven.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="1e8f7-126">Met deze opdrachten kunt u een gebruikersaccount toevoegen door middel van de **UPN (User Principal Name)** van de huidige eigenaren van een beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="1e8f7-127">Gebruik deze opdrachten om een gebruikersaccount toe te voegen aan de **weergegeven naam** van de huidige eigenaren van een beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="1e8f7-128">Met deze opdrachten kunt u een gebruikersaccount door de **UPN** van de huidige eigenaren van een beveiligingsgroep verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="1e8f7-129">Met deze opdrachten kunt u een gebruikersaccount verwijderen met de **weergavenaam** van de huidige eigenaren van een beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="1e8f7-130">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="1e8f7-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="1e8f7-131">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="1e8f7-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="1e8f7-132">Uw groepen weergeven</span><span class="sxs-lookup"><span data-stu-id="1e8f7-132">List your groups</span></span>

<span data-ttu-id="1e8f7-133">Gebruik deze opdracht om alle groepen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="1e8f7-134">Met deze opdrachten kunt u de instellingen van een specifieke groep weergeven op basis van de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="1e8f7-135">Een nieuwe groep maken</span><span class="sxs-lookup"><span data-stu-id="1e8f7-135">Create a new group</span></span>

<span data-ttu-id="1e8f7-136">Gebruik deze opdracht om een nieuwe beveiligingsgroep te maken.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="1e8f7-137">De instellingen van een groep wijzigen</span><span class="sxs-lookup"><span data-stu-id="1e8f7-137">Change the settings on a group</span></span>

<span data-ttu-id="1e8f7-138">De instellingen van de groep met deze opdrachten weergeven.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="1e8f7-139">Gebruik vervolgens het artikel [set-Remove msolgroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) om te bepalen hoe u een instelling kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-139">Then, use the [Set-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="1e8f7-140">Een beveiligingsgroep verwijderen</span><span class="sxs-lookup"><span data-stu-id="1e8f7-140">Remove a security group</span></span>

<span data-ttu-id="1e8f7-141">Met deze opdrachten kunt u een beveiligingsgroep verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1e8f7-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="1e8f7-142">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1e8f7-142">See also</span></span>

[<span data-ttu-id="1e8f7-143">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e8f7-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1e8f7-144">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e8f7-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1e8f7-145">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1e8f7-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

