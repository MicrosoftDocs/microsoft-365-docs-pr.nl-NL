---
title: Microsoft 365-gebruikersaccounts verwijderen met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
ms.openlocfilehash: 6da2d83b3f305db09f8c1d02f54e643a0ad1978b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689316"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="0597b-103">Microsoft 365-gebruikersaccounts verwijderen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="0597b-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="0597b-104">Met PowerShell voor Microsoft 365 kunt u een gebruikersaccount verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0597b-104">You can use PowerShell for Microsoft 365 to delete a user account.</span></span>
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="0597b-105">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="0597b-105">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="0597b-106">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="0597b-106">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="0597b-107">Wanneer u verbinding hebt, gebruikt u de volgende syntaxis om een afzonderlijke gebruikersaccount te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="0597b-107">After you have connected, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="0597b-108">In dit voorbeeld wordt de fabricec@litwareinc.com van de gebruikersaccount verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0597b-108">This example removes the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="0597b-109">Met de parameter **-ObjectID** in de **Remove-AzureADUser** wordt de aanmeldingsnaam van de account geaccepteerd, ook wel bekend als de UPN (User Principal Name) of de object-id van het account.</span><span class="sxs-lookup"><span data-stu-id="0597b-109">The **-ObjectID** parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="0597b-110">Gebruik de volgende opdrachten om de accountnaam weer te geven op basis van de naam van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="0597b-110">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="0597b-111">In dit voorbeeld wordt de accountnaam van de gebruiker met de naam Caleb Sills weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0597b-111">This example displays the account name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="0597b-112">Als u een account wilt verwijderen op basis van de weergavenaam van de gebruiker, gebruikt u de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="0597b-112">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="0597b-113">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="0597b-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="0597b-114">Wanneer u een gebruikersaccount verwijdert met de Microsoft Azure Active Directory-module voor Windows PowerShell, wordt het account niet permanent verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0597b-114">When you delete a user account with the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted.</span></span> <span data-ttu-id="0597b-115">U kunt de verwijderde gebruikersaccount binnen 30 dagen herstellen.</span><span class="sxs-lookup"><span data-stu-id="0597b-115">You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="0597b-116">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0597b-116">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="0597b-117">Als u een gebruikersaccount wilt verwijderen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0597b-117">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="0597b-118">De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam.</span><span class="sxs-lookup"><span data-stu-id="0597b-118">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="0597b-119">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0597b-119">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="0597b-120">In dit voorbeeld wordt de BelindaN@litwareinc.com van het gebruikersaccount verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0597b-120">This example deletes the user account BelindaN@litwareinc.com.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="0597b-121">Wanneer u een verwijderd gebruikersaccount binnen de termijn van 30 dagen wilt herstellen, gebruikt u de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="0597b-121">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="0597b-122">In dit voorbeeld worden de verwijderde account BelindaN@litwareinc.com hersteld.</span><span class="sxs-lookup"><span data-stu-id="0597b-122">This example restores the deleted account BelindaN@litwareinc.com.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

 <span data-ttu-id="0597b-123">**Opmerkingen:**</span><span class="sxs-lookup"><span data-stu-id="0597b-123">**Notes:**</span></span>
  
- <span data-ttu-id="0597b-124">Voer de volgende opdracht uit om de lijst weer te geven met verwijderde gebruikers die u kunt herstellen:</span><span class="sxs-lookup"><span data-stu-id="0597b-124">To see the list of deleted users that can be restored, run the following command:</span></span>
    
  ```powershell
  Get-MsolUser -All -ReturnDeletedUsers
  ```

- <span data-ttu-id="0597b-125">Als de oorspronkelijke User Principal name van de gebruikersaccount wordt gebruikt door een ander account, gebruikt u de _NewUserPrincipalName_ -parameter in plaats van _userPrincipalName_ om een andere Principal-naam van de gebruiker op te geven wanneer u het gebruikersaccount terugzet.</span><span class="sxs-lookup"><span data-stu-id="0597b-125">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="0597b-126">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0597b-126">See also</span></span>

[<span data-ttu-id="0597b-127">Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="0597b-127">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0597b-128">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="0597b-128">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0597b-129">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0597b-129">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
