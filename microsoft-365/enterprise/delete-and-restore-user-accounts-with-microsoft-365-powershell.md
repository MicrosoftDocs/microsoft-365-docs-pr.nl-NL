---
title: Microsoft 365-gebruikersaccounts verwijderen met PowerShell
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
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: Meer informatie over het gebruik van verschillende modules in PowerShell om Microsoft 365-gebruikersaccounts te verwijderen.
ms.openlocfilehash: 32081d1ce0cbc7aac89b337cf8b5d08bc8e43dfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919138"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="a746d-103">Microsoft 365-gebruikersaccounts verwijderen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="a746d-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="a746d-104">U kunt PowerShell voor Microsoft 365 gebruiken om gebruikersaccounts te verwijderen en te herstellen.</span><span class="sxs-lookup"><span data-stu-id="a746d-104">You can use PowerShell for Microsoft 365 to delete and restore user accounts.</span></span>

>[!Note]
><span data-ttu-id="a746d-105">Meer informatie over het [herstellen van een gebruikersaccount](../admin/add-users/restore-user.md) via het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="a746d-105">Learn how to [restore a user account](../admin/add-users/restore-user.md) by using the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="a746d-106">Zie Gebruikers en groepen beheren voor een lijst met [aanvullende bronnen.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="a746d-106">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="a746d-107">De Azure Active Directory PowerShell voor Graph-module gebruiken</span><span class="sxs-lookup"><span data-stu-id="a746d-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="a746d-108">Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="a746d-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="a746d-109">Nadat u verbinding hebt gemaakt, gebruikt u de volgende syntaxis om een afzonderlijk gebruikersaccount te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="a746d-109">After you connect, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="a746d-110">In dit voorbeeld wordt de fabricec van het *\@ gebruikersaccount litwareinc.com.*</span><span class="sxs-lookup"><span data-stu-id="a746d-110">This example removes the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="a746d-111">De *parameter -ObjectID* in de cmdlet **Remove-AzureADUser** accepteert de aanmeldingsnaam van het account, ook wel de gebruikersnaam of de object-id van het account genoemd.</span><span class="sxs-lookup"><span data-stu-id="a746d-111">The *-ObjectID* parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name or the account's object ID.</span></span>
  
<span data-ttu-id="a746d-112">Gebruik de volgende opdrachten om de accountnaam weer te geven op basis van de naam van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="a746d-112">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="a746d-113">In dit voorbeeld wordt de accountnaam voor de gebruiker *Caleb Sills weergegeven.*</span><span class="sxs-lookup"><span data-stu-id="a746d-113">This example displays the account name for the user *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="a746d-114">Als u een account wilt verwijderen op basis van de weergavenaam van de gebruiker, gebruikt u de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="a746d-114">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="a746d-115">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="a746d-115">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="a746d-116">Wanneer u een gebruikersaccount verwijdert via de Microsoft Azure Active Directory-module voor Windows PowerShell, wordt het account niet definitief verwijderd.</span><span class="sxs-lookup"><span data-stu-id="a746d-116">When you delete a user account through the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted.</span></span> <span data-ttu-id="a746d-117">U kunt het verwijderde gebruikersaccount binnen 30 dagen herstellen.</span><span class="sxs-lookup"><span data-stu-id="a746d-117">You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="a746d-118">Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="a746d-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="a746d-119">Als u een gebruikersaccount wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="a746d-119">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="a746d-120">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell en cmdlets met *Msol* in hun naam.</span><span class="sxs-lookup"><span data-stu-id="a746d-120">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="a746d-121">Voer deze cmdlets uit vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a746d-121">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="a746d-122">In dit voorbeeld wordt het gebruikersaccount *BelindaN@litwareinc.com.*</span><span class="sxs-lookup"><span data-stu-id="a746d-122">This example deletes the user account *BelindaN@litwareinc.com*.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="a746d-123">Als u een verwijderd gebruikersaccount binnen de respijtperiode van 30 dagen wilt herstellen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="a746d-123">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="a746d-124">In dit voorbeeld wordt het verwijderde account *BelindaN \@ litwareinc.com.*</span><span class="sxs-lookup"><span data-stu-id="a746d-124">This example restores the deleted account *BelindaN\@litwareinc.com*.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> <span data-ttu-id="a746d-125">Voer de volgende opdracht uit om de lijst met verwijderde gebruikers weer te geven die kunnen worden hersteld:</span><span class="sxs-lookup"><span data-stu-id="a746d-125">To see the list of deleted users that can be restored, run the following command:</span></span>
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> <span data-ttu-id="a746d-126">Als de oorspronkelijke gebruikersnaam van het gebruikersaccount door een ander account wordt gebruikt, gebruikt u de parameter _NewUserPrincipalName_ in plaats van _UserPrincipalName_ om een andere gebruikersnaam op te geven wanneer u het gebruikersaccount herstelt.</span><span class="sxs-lookup"><span data-stu-id="a746d-126">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="a746d-127">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a746d-127">See also</span></span>

[<span data-ttu-id="a746d-128">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="a746d-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a746d-129">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="a746d-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a746d-130">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a746d-130">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)