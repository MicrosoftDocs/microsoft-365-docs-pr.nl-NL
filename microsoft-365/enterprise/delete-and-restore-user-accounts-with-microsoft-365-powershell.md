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
description: In dit artikel vindt u informatie over het gebruik van verschillende modules in PowerShell om Microsoft 365-gebruikersaccounts te verwijderen.
ms.openlocfilehash: 0c13b57c13fb3d01d648438a5d6973fea8b9db67
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235440"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="67095-103">Microsoft 365-gebruikersaccounts verwijderen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="67095-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="67095-104">Met PowerShell voor Microsoft 365 kunt u een gebruikersaccount verwijderen en herstellen.</span><span class="sxs-lookup"><span data-stu-id="67095-104">You can use PowerShell for Microsoft 365 to delete and restore a user account.</span></span>

>[!Note]
><span data-ttu-id="67095-105">[Meer informatie over het herstellen van een gebruikersaccount](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) met het microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="67095-105">[Learn how to restore a user account](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="67095-106">Zie [gebruikers en groepen beheren](https://docs.microsoft.com/microsoft-365/admin/add-users/)voor een lijst met aanvullende bronnen.</span><span class="sxs-lookup"><span data-stu-id="67095-106">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="67095-107">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="67095-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="67095-108">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="67095-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="67095-109">Wanneer u verbinding hebt, gebruikt u de volgende syntaxis om een afzonderlijke gebruikersaccount te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="67095-109">After you have connected, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="67095-110">In dit voorbeeld wordt de fabricec@litwareinc.com van de gebruikersaccount verwijderd.</span><span class="sxs-lookup"><span data-stu-id="67095-110">This example removes the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="67095-111">Met de parameter **-ObjectID** in de **Remove-AzureADUser** wordt de aanmeldingsnaam van de account geaccepteerd, ook wel bekend als de UPN (User Principal Name) of de object-id van het account.</span><span class="sxs-lookup"><span data-stu-id="67095-111">The **-ObjectID** parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="67095-112">Gebruik de volgende opdrachten om de accountnaam weer te geven op basis van de naam van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="67095-112">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="67095-113">In dit voorbeeld wordt de accountnaam van de gebruiker met de naam Caleb Sills weergegeven.</span><span class="sxs-lookup"><span data-stu-id="67095-113">This example displays the account name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="67095-114">Als u een account wilt verwijderen op basis van de weergavenaam van de gebruiker, gebruikt u de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="67095-114">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="67095-115">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="67095-115">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="67095-116">Wanneer u een gebruikersaccount verwijdert met de Microsoft Azure Active Directory-module voor Windows PowerShell, wordt het account niet permanent verwijderd.</span><span class="sxs-lookup"><span data-stu-id="67095-116">When you delete a user account with the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted.</span></span> <span data-ttu-id="67095-117">U kunt de verwijderde gebruikersaccount binnen 30 dagen herstellen.</span><span class="sxs-lookup"><span data-stu-id="67095-117">You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="67095-118">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="67095-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="67095-119">Als u een gebruikersaccount wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="67095-119">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="67095-120">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="67095-120">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="67095-121">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67095-121">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="67095-122">In dit voorbeeld wordt de BelindaN@litwareinc.com van het gebruikersaccount verwijderd.</span><span class="sxs-lookup"><span data-stu-id="67095-122">This example deletes the user account BelindaN@litwareinc.com.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="67095-123">Wanneer u een verwijderd gebruikersaccount binnen de termijn van 30 dagen wilt herstellen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="67095-123">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="67095-124">In dit voorbeeld worden de verwijderde account BelindaN@litwareinc.com hersteld.</span><span class="sxs-lookup"><span data-stu-id="67095-124">This example restores the deleted account BelindaN@litwareinc.com.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

 <span data-ttu-id="67095-125">**Opmerkingen:**</span><span class="sxs-lookup"><span data-stu-id="67095-125">**Notes:**</span></span>
  
- <span data-ttu-id="67095-126">Voer de volgende opdracht uit om de lijst weer te geven met verwijderde gebruikers die u kunt herstellen:</span><span class="sxs-lookup"><span data-stu-id="67095-126">To see the list of deleted users that can be restored, run the following command:</span></span>
    
  ```powershell
  Get-MsolUser -All -ReturnDeletedUsers
  ```

- <span data-ttu-id="67095-127">Als de oorspronkelijke User Principal name van de gebruikersaccount wordt gebruikt door een ander account, gebruikt u de _NewUserPrincipalName_ -parameter in plaats van _userPrincipalName_ om een andere Principal-naam van de gebruiker op te geven wanneer u het gebruikersaccount terugzet.</span><span class="sxs-lookup"><span data-stu-id="67095-127">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="67095-128">Zie ook</span><span class="sxs-lookup"><span data-stu-id="67095-128">See also</span></span>

[<span data-ttu-id="67095-129">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="67095-129">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="67095-130">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="67095-130">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="67095-131">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="67095-131">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
