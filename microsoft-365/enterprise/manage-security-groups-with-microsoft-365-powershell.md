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
ms.openlocfilehash: 64a02a1472fdeb0d61cfb4f380cbe61dd7b557b6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909500"
---
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="2814e-103">Beveiligingsgroepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="2814e-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="2814e-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2814e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2814e-105">U kunt PowerShell voor Microsoft 365 gebruiken als alternatief voor het Microsoft 365 beheercentrum voor het beheren van beveiligingsgroepen.</span><span class="sxs-lookup"><span data-stu-id="2814e-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="2814e-106">In dit artikel wordt beschreven hoe u beveiligingsgroepen kunt maken, maken, wijzigen en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="2814e-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="2814e-107">Als voor een opdrachtblok in dit artikel variabele waarden moeten worden opgegeven, gebruikt u deze stappen.</span><span class="sxs-lookup"><span data-stu-id="2814e-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="2814e-108">Kopieer het opdrachtblok naar het klembord en plak het in Kladblok of de Geïntegreerde Scriptomgeving (ISE) van PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2814e-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="2814e-109">Vul de variabele waarden in en verwijder de tekens '<' en '>'.</span><span class="sxs-lookup"><span data-stu-id="2814e-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="2814e-110">Voer de opdrachten uit in het PowerShell-venster of de PowerShell-ise.</span><span class="sxs-lookup"><span data-stu-id="2814e-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="2814e-111">Zie [Lidmaatschap van beveiligingsgroep behouden om](maintain-group-membership-with-microsoft-365-powershell.md) het groepslidmaatschap met PowerShell te beheren.</span><span class="sxs-lookup"><span data-stu-id="2814e-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="2814e-112">De powershell Azure Active Directory powershell gebruiken voor Graph module</span><span class="sxs-lookup"><span data-stu-id="2814e-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="2814e-113">Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="2814e-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="2814e-114">Uw groepen op een lijst zetten</span><span class="sxs-lookup"><span data-stu-id="2814e-114">List your groups</span></span>

<span data-ttu-id="2814e-115">Gebruik deze opdracht om al uw groepen op te geven.</span><span class="sxs-lookup"><span data-stu-id="2814e-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="2814e-116">Gebruik deze opdrachten om de instellingen van een bepaalde groep weer te geven op de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="2814e-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="2814e-117">Een nieuwe groep maken</span><span class="sxs-lookup"><span data-stu-id="2814e-117">Create a new group</span></span>

<span data-ttu-id="2814e-118">Gebruik deze opdracht om een nieuwe beveiligingsgroep te maken.</span><span class="sxs-lookup"><span data-stu-id="2814e-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="2814e-119">De instellingen voor een groep wijzigen</span><span class="sxs-lookup"><span data-stu-id="2814e-119">Change the settings on a group</span></span>

<span data-ttu-id="2814e-120">Geef de instellingen van de groep weer met deze opdrachten.</span><span class="sxs-lookup"><span data-stu-id="2814e-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="2814e-121">Gebruik vervolgens het artikel [Set-AzureADGroup](/powershell/module/azuread/set-azureadgroup) om te bepalen hoe u een instelling wijzigt.</span><span class="sxs-lookup"><span data-stu-id="2814e-121">Then, use the [Set-AzureADGroup](/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="2814e-122">Een beveiligingsgroep verwijderen</span><span class="sxs-lookup"><span data-stu-id="2814e-122">Remove a security group</span></span>

<span data-ttu-id="2814e-123">Gebruik deze opdrachten om een beveiligingsgroep te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="2814e-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="2814e-124">De eigenaren van een beveiligingsgroep beheren</span><span class="sxs-lookup"><span data-stu-id="2814e-124">Manage the owners of a security group</span></span>

<span data-ttu-id="2814e-125">Gebruik deze opdrachten om de huidige eigenaren van een beveiligingsgroep weer te geven.</span><span class="sxs-lookup"><span data-stu-id="2814e-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="2814e-126">Gebruik deze opdrachten om een gebruikersaccount op basis van de gebruikersnaam **(UPN)** toe te voegen aan de huidige eigenaren van een beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="2814e-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="2814e-127">Gebruik deze opdrachten om een gebruikersaccount op de weergavenaam **toe te** voegen aan de huidige eigenaren van een beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="2814e-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="2814e-128">Gebruik deze opdrachten om een gebruikersaccount van de **UPN** te verwijderen naar de huidige eigenaren van een beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="2814e-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="2814e-129">Gebruik deze opdrachten om een gebruikersaccount met de **weergavenaam te verwijderen** voor de huidige eigenaren van een beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="2814e-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="2814e-130">Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2814e-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="2814e-131">Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="2814e-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="2814e-132">Uw groepen op een lijst zetten</span><span class="sxs-lookup"><span data-stu-id="2814e-132">List your groups</span></span>

<span data-ttu-id="2814e-133">Gebruik deze opdracht om al uw groepen op te geven.</span><span class="sxs-lookup"><span data-stu-id="2814e-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="2814e-134">Gebruik deze opdrachten om de instellingen van een bepaalde groep weer te geven op de weergavenaam.</span><span class="sxs-lookup"><span data-stu-id="2814e-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="2814e-135">Een nieuwe groep maken</span><span class="sxs-lookup"><span data-stu-id="2814e-135">Create a new group</span></span>

<span data-ttu-id="2814e-136">Gebruik deze opdracht om een nieuwe beveiligingsgroep te maken.</span><span class="sxs-lookup"><span data-stu-id="2814e-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="2814e-137">De instellingen voor een groep wijzigen</span><span class="sxs-lookup"><span data-stu-id="2814e-137">Change the settings on a group</span></span>

<span data-ttu-id="2814e-138">Geef de instellingen van de groep weer met deze opdrachten.</span><span class="sxs-lookup"><span data-stu-id="2814e-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="2814e-139">Gebruik vervolgens het artikel [Set-MsolGroup](/powershell/module/msonline/set-msolgroup) om te bepalen hoe u een instelling wijzigt.</span><span class="sxs-lookup"><span data-stu-id="2814e-139">Then, use the [Set-MsolGroup](/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="2814e-140">Een beveiligingsgroep verwijderen</span><span class="sxs-lookup"><span data-stu-id="2814e-140">Remove a security group</span></span>

<span data-ttu-id="2814e-141">Gebruik deze opdrachten om een beveiligingsgroep te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="2814e-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="2814e-142">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2814e-142">See also</span></span>

[<span data-ttu-id="2814e-143">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="2814e-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2814e-144">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="2814e-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2814e-145">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2814e-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)