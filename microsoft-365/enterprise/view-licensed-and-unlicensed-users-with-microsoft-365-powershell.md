---
title: Gelicentieerde en niet-gelicentieerde Microsoft 365 weergeven met PowerShell
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
description: In dit artikel wordt uitgelegd hoe u PowerShell kunt gebruiken om gelicentieerde en niet-gelicentieerde Microsoft 365 gebruikersaccounts weer te geven.
ms.openlocfilehash: b38ee7674abaea6b63d0661ba79a9814f8c54229
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651382"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a><span data-ttu-id="452fe-103">Gelicentieerde en niet-gelicentieerde Microsoft 365 weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="452fe-103">View licensed and unlicensed Microsoft 365 users with PowerShell</span></span>

<span data-ttu-id="452fe-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="452fe-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="452fe-105">Gebruikersaccounts in Microsoft 365 organisatie kunnen bepaalde, alle of geen beschikbare licenties aan hen hebben toegewezen vanuit de licentieplannen die beschikbaar zijn in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="452fe-105">User accounts in your Microsoft 365 organization may have some, all, or none of the available licenses assigned to them from the licensing plans that are available in your organization.</span></span> <span data-ttu-id="452fe-106">U kunt PowerShell voor Microsoft 365 gebruiken om snel de gelicentieerde en niet-gelicentieerde gebruikers in uw organisatie te vinden.</span><span class="sxs-lookup"><span data-stu-id="452fe-106">You can use PowerShell for Microsoft 365 to quickly find the licensed and unlicensed users in your organization.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="452fe-107">De powershell Azure Active Directory powershell gebruiken voor Graph module</span><span class="sxs-lookup"><span data-stu-id="452fe-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="452fe-108">Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="452fe-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
<span data-ttu-id="452fe-109">Voer de volgende opdracht uit als u de lijst wilt weergeven met alle gebruikersaccounts in uw organisatie die geen licentieplannen (gebruikers zonder licentie) hebben gekregen:</span><span class="sxs-lookup"><span data-stu-id="452fe-109">To view the list of all user accounts in your organization that have NOT been assigned any of your licensing plans (unlicensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

<span data-ttu-id="452fe-110">Voer de volgende opdracht uit als u de lijst wilt weergeven met alle gebruikersaccounts in uw organisatie die aan een licentie zijn toegewezen (gelicentieerde gebruikers):</span><span class="sxs-lookup"><span data-stu-id="452fe-110">To view the list of all user accounts in your organization that have been assigned any of your licensing plans (licensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$True ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
><span data-ttu-id="452fe-111">Gebruik de opdracht om alle gebruikers in uw abonnement op te `Get-AzureAdUser -All $true` nemen.</span><span class="sxs-lookup"><span data-stu-id="452fe-111">To list all of the users in your subscription, use the `Get-AzureAdUser -All $true` command.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="452fe-112">Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="452fe-112">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="452fe-113">Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="452fe-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="452fe-114">Als u de lijst met alle gebruikersaccounts en de licentiestatus in uw organisatie wilt weergeven, voer dan de volgende opdracht uit in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="452fe-114">To view the list of all user accounts and their licensing status in your organization, run the following command in PowerShell:</span></span>
  
```powershell
Get-MsolUser -All
```

>[!Note]
><span data-ttu-id="452fe-115">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="452fe-115">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="452fe-116">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="452fe-116">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="452fe-117">Voer de volgende opdracht uit om de lijst met alle gebruikersaccounts zonder een vergunning in uw organisatie weer te geven:</span><span class="sxs-lookup"><span data-stu-id="452fe-117">To view the list of all unlicensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="452fe-118">Voer de volgende opdracht uit om de lijst met alle gelicentieerde gebruikersaccounts in uw organisatie weer te geven:</span><span class="sxs-lookup"><span data-stu-id="452fe-118">To view the list of all licensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a><span data-ttu-id="452fe-119">Zie ook</span><span class="sxs-lookup"><span data-stu-id="452fe-119">See also</span></span>

[<span data-ttu-id="452fe-120">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="452fe-120">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="452fe-121">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="452fe-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="452fe-122">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="452fe-122">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
