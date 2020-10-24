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
ms.openlocfilehash: 39bf57fe7e7aad1bdc9915e503107ad799515030
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754538"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="6a337-103">Microsoft 365-gebruikersaccounts verwijderen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a337-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="6a337-104">Met PowerShell voor Microsoft 365 kunt u gebruikersaccounts verwijderen en herstellen.</span><span class="sxs-lookup"><span data-stu-id="6a337-104">You can use PowerShell for Microsoft 365 to delete and restore user accounts.</span></span>

>[!Note]
><span data-ttu-id="6a337-105">Informatie over het [herstellen van een gebruikersaccount](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) met behulp van het microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="6a337-105">Learn how to [restore a user account](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) by using the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="6a337-106">Zie [gebruikers en groepen beheren](https://docs.microsoft.com/microsoft-365/admin/add-users/)voor een lijst met aanvullende bronnen.</span><span class="sxs-lookup"><span data-stu-id="6a337-106">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6a337-107">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="6a337-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6a337-108">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="6a337-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="6a337-109">Nadat u verbinding hebt gemaakt, gebruikt u de volgende syntaxis om een afzonderlijke gebruikersaccount te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="6a337-109">After you connect, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="6a337-110">In dit voorbeeld wordt de gebruikersaccount *fabricec \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="6a337-110">This example removes the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="6a337-111">Met de parameter *-ObjectID* in de **Remove-AzureADUser** wordt de aanmeldingsnaam van de account geaccepteerd, ook wel bekend als de User Principal name of de object-id van de account.</span><span class="sxs-lookup"><span data-stu-id="6a337-111">The *-ObjectID* parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name or the account's object ID.</span></span>
  
<span data-ttu-id="6a337-112">Gebruik de volgende opdrachten om de accountnaam weer te geven op basis van de naam van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="6a337-112">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="6a337-113">In dit voorbeeld wordt de accountnaam weergegeven voor de gebruiker *Caleb Sills*.</span><span class="sxs-lookup"><span data-stu-id="6a337-113">This example displays the account name for the user *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="6a337-114">Als u een account wilt verwijderen op basis van de weergavenaam van de gebruiker, gebruikt u de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="6a337-114">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="6a337-115">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="6a337-115">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="6a337-116">Wanneer u een gebruikersaccount verwijdert via Microsoft Azure Active Directory-module voor Windows PowerShell, wordt het account niet permanent verwijderd.</span><span class="sxs-lookup"><span data-stu-id="6a337-116">When you delete a user account through the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted.</span></span> <span data-ttu-id="6a337-117">U kunt de verwijderde gebruikersaccount binnen 30 dagen herstellen.</span><span class="sxs-lookup"><span data-stu-id="6a337-117">You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="6a337-118">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="6a337-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="6a337-119">Als u een gebruikersaccount wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="6a337-119">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="6a337-120">PowerShell core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met *MSOL* in de naam.</span><span class="sxs-lookup"><span data-stu-id="6a337-120">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="6a337-121">Voer de volgende cmdlets uit vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a337-121">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="6a337-122">In dit voorbeeld wordt de *BelindaN@litwareinc.com*van het gebruikersaccount verwijderd.</span><span class="sxs-lookup"><span data-stu-id="6a337-122">This example deletes the user account *BelindaN@litwareinc.com*.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="6a337-123">Wanneer u een verwijderd gebruikersaccount binnen de termijn van 30 dagen wilt herstellen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="6a337-123">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="6a337-124">In dit voorbeeld worden de verwijderde account *BelindaN \@ litwareinc.com*hersteld.</span><span class="sxs-lookup"><span data-stu-id="6a337-124">This example restores the deleted account *BelindaN\@litwareinc.com*.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> <span data-ttu-id="6a337-125">Voer de volgende opdracht uit om de lijst weer te geven met verwijderde gebruikers die u kunt herstellen:</span><span class="sxs-lookup"><span data-stu-id="6a337-125">To see the list of deleted users that can be restored, run the following command:</span></span>
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> <span data-ttu-id="6a337-126">Als de oorspronkelijke User Principal name van de gebruikersaccount wordt gebruikt door een ander account, gebruikt u de _NewUserPrincipalName_ -parameter in plaats van _userPrincipalName_ om een andere Principal-naam van de gebruiker op te geven wanneer u het gebruikersaccount terugzet.</span><span class="sxs-lookup"><span data-stu-id="6a337-126">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="6a337-127">Zie ook</span><span class="sxs-lookup"><span data-stu-id="6a337-127">See also</span></span>

[<span data-ttu-id="6a337-128">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a337-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6a337-129">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a337-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6a337-130">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6a337-130">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
