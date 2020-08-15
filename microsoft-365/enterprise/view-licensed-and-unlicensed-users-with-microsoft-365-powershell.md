---
title: Licentie-en niet-gelicentieerde Microsoft 365-gebruikers weergeven met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/21/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: In dit artikel wordt uitgelegd hoe u PowerShell kunt gebruiken voor het weergeven van licentie-en niet-gelicentieerde Microsoft 365-gebruikersaccounts.
ms.openlocfilehash: 8a99ba2a80f1d814ec5268c4f8f479837eb54dc0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689126"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a><span data-ttu-id="223f7-103">Licentie-en niet-gelicentieerde Microsoft 365-gebruikers weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="223f7-103">View licensed and unlicensed Microsoft 365 users with PowerShell</span></span>

<span data-ttu-id="223f7-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="223f7-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="223f7-105">Gebruikersaccounts in uw Microsoft 365-organisatie kunnen enkele, alle of geen van de beschikbare licenties die aan hen zijn toegewezen, krijgen van de licentie plannen die beschikbaar zijn in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="223f7-105">User accounts in your Microsoft 365 organization may have some, all, or none of the available licenses assigned to them from the licensing plans that are available in your organization.</span></span> <span data-ttu-id="223f7-106">U kunt PowerShell voor Microsoft 365 gebruiken om snel de gebruikers met een licentie en gebruikers zonder licentie te vinden in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="223f7-106">You can use PowerShell for Microsoft 365 to quickly find the licensed and unlicensed users in your organization.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="223f7-107">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="223f7-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="223f7-108">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="223f7-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
<span data-ttu-id="223f7-109">Voer de volgende opdracht uit als u de lijst wilt weergeven met alle gebruikersaccounts in uw organisatie waaraan geen licentie plannen zijn toegewezen (gebruikers zonder licentie):</span><span class="sxs-lookup"><span data-stu-id="223f7-109">To view the list of all user accounts in your organization that have NOT been assigned any of your licensing plans (unlicensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

<span data-ttu-id="223f7-110">Voer de volgende opdracht uit om de lijst met alle gebruikersaccounts in uw organisatie weer te geven waaraan een licentie abonnement is toegewezen (gebruikers met een licentie):</span><span class="sxs-lookup"><span data-stu-id="223f7-110">To view the list of all user accounts in your organization that have been assigned any of your licensing plans (licensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
><span data-ttu-id="223f7-111">Als u alle gebruikers in uw abonnement wilt weergeven, gebruikt u de `Get-AzureAdUser -All $true` opdracht.</span><span class="sxs-lookup"><span data-stu-id="223f7-111">To list all of the users in your subscription, use the `Get-AzureAdUser -All $true` command.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="223f7-112">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="223f7-112">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="223f7-113">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="223f7-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="223f7-114">Voer de volgende opdracht uit in PowerShell om de lijst met alle gebruikersaccounts en de bijbehorende licentiestatus in uw organisatie weer te geven:</span><span class="sxs-lookup"><span data-stu-id="223f7-114">To view the list of all user accounts and their licensing status in your organization, run the following command in PowerShell:</span></span>
  
```powershell
Get-MsolUser -All
```

>[!Note]
><span data-ttu-id="223f7-115">De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam.</span><span class="sxs-lookup"><span data-stu-id="223f7-115">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="223f7-116">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="223f7-116">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="223f7-117">Voer de volgende opdracht uit om de lijst met alle gebruikersaccounts zonder licentie in uw organisatie weer te geven:</span><span class="sxs-lookup"><span data-stu-id="223f7-117">To view the list of all unlicensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="223f7-118">Voer de volgende opdracht uit om de lijst met alle gelicentieerde gebruikersaccounts in uw organisatie weer te geven:</span><span class="sxs-lookup"><span data-stu-id="223f7-118">To view the list of all licensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a><span data-ttu-id="223f7-119">Zie ook</span><span class="sxs-lookup"><span data-stu-id="223f7-119">See also</span></span>

[<span data-ttu-id="223f7-120">Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="223f7-120">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="223f7-121">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="223f7-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="223f7-122">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="223f7-122">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
