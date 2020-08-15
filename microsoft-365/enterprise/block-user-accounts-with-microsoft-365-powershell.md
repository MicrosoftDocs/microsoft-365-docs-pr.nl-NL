---
title: Microsoft 365-gebruikersaccounts blokkeren met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: In dit artikel wordt uitgelegd hoe u PowerShell gebruikt om de toegang tot Microsoft 365-accounts te blokkeren of te deblokkeren.
ms.openlocfilehash: a9ade2f41fb601da00ca1c2d1905ca0cb003dcb3
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689191"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="9ad42-103">Microsoft 365-gebruikersaccounts blokkeren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ad42-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="9ad42-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9ad42-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9ad42-105">Als u de toegang tot een Microsoft 365-account blokkeert, kan iedereen het account gebruiken om zich aan te melden en toegang te krijgen tot de services en gegevens in uw Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="9ad42-105">Blocking access to a Microsoft 365 account prevents anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="9ad42-106">U kunt PowerShell gebruiken om toegang te blokkeren voor afzonderlijke en meerdere gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="9ad42-106">You can use PowerShell to block access to individual and multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="9ad42-107">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="9ad42-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="9ad42-108">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="9ad42-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="9ad42-109">Toegang tot afzonderlijke gebruikersaccounts blokkeren</span><span class="sxs-lookup"><span data-stu-id="9ad42-109">Block access to individual user accounts</span></span>

<span data-ttu-id="9ad42-110">Gebruik de volgende syntaxis om een afzonderlijke gebruikersaccount te blokkeren:</span><span class="sxs-lookup"><span data-stu-id="9ad42-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="9ad42-111">Met de parameter-ObjectID in de cmdlet Set-AzureAD wordt de aanmeldingsnaam van het account geaccepteerd, ook wel bekend als de User Principal name of de object-ID van de account.</span><span class="sxs-lookup"><span data-stu-id="9ad42-111">The -ObjectID parameter in the Set-AzureAD cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span> 
  
<span data-ttu-id="9ad42-112">In dit voorbeeld wordt de toegang tot de fabricec@litwareinc.com van de gebruikersaccount geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="9ad42-112">This example blocks access to the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="9ad42-113">Voer de volgende opdracht uit als u dit gebruikersaccount wilt deblokkeren:</span><span class="sxs-lookup"><span data-stu-id="9ad42-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="9ad42-114">Als u de UPN van het gebruikersaccount wilt weergeven op basis van de weergavenaam van de gebruiker, gebruikt u de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="9ad42-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="9ad42-115">In dit voorbeeld wordt de UPN van het gebruikersaccount voor de gebruiker met de naam Caleb Sills weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9ad42-115">This example displays the user account UPN for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="9ad42-116">Als u een account wilt blokkeren op basis van de weergavenaam van de gebruiker, gebruikt u de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="9ad42-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="9ad42-117">U kunt op elk gewenst moment de geblokkeerde status van een gebruikersaccount controleren aan de hand van de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="9ad42-117">At any time, you can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-access-to-multiple-user-accounts"></a><span data-ttu-id="9ad42-118">Toegang tot meerdere gebruikersaccounts blokkeren</span><span class="sxs-lookup"><span data-stu-id="9ad42-118">Block access to multiple user accounts</span></span>

<span data-ttu-id="9ad42-119">Als u toegang tot meerdere gebruikersaccounts wilt blokkeren, maakt u een tekstbestand met één aanmeldingsnaam op elke regel, zoals deze:</span><span class="sxs-lookup"><span data-stu-id="9ad42-119">To block access to multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="9ad42-120">In de volgende opdrachten is het voorbeeldtekst bestand C:\Mijn Documents\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="9ad42-120">In the following commands, the example text file is C:\My Documents\Accounts.txt.</span></span> <span data-ttu-id="9ad42-121">Vervang dit door het pad en de bestandsnaam van het tekstbestand.</span><span class="sxs-lookup"><span data-stu-id="9ad42-121">Replace this with the path and file name of your text file.</span></span>
  
<span data-ttu-id="9ad42-122">Voer de volgende opdracht uit als u de toegang tot de accounts die worden vermeld in het tekstbestand wilt blokkeren:</span><span class="sxs-lookup"><span data-stu-id="9ad42-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="9ad42-123">Voer de volgende opdracht uit om de accounts die in het tekstbestand worden weergegeven, op te heffen:</span><span class="sxs-lookup"><span data-stu-id="9ad42-123">To unblock the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="9ad42-124">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="9ad42-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="9ad42-125">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9ad42-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="9ad42-126">Toegang tot afzonderlijke gebruikersaccounts blokkeren</span><span class="sxs-lookup"><span data-stu-id="9ad42-126">Block access to individual user accounts</span></span>

<span data-ttu-id="9ad42-127">Gebruik de volgende syntaxis om toegang te blokkeren met een account voor afzonderlijke gebruikers:</span><span class="sxs-lookup"><span data-stu-id="9ad42-127">Use the following syntax to block access to an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="9ad42-128">De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam.</span><span class="sxs-lookup"><span data-stu-id="9ad42-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="9ad42-129">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ad42-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="9ad42-130">In dit voorbeeld wordt de toegang tot de fabricec@litwareinc.com van de gebruikersaccount geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="9ad42-130">This example blocks access to the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="9ad42-131">Voer de volgende opdracht uit om het gebruikersaccount te deblokkeren:</span><span class="sxs-lookup"><span data-stu-id="9ad42-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="9ad42-132">U kunt op elk gewenst moment de geblokkeerde status van een gebruikersaccount controleren aan de hand van de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="9ad42-132">At any time, you can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-to-multiple-user-accounts"></a><span data-ttu-id="9ad42-133">Toegang tot meerdere gebruikersaccounts blokkeren</span><span class="sxs-lookup"><span data-stu-id="9ad42-133">Block access to multiple user accounts</span></span>

<span data-ttu-id="9ad42-134">Maak eerst als volgt een tekstbestand dat één account op elke regel bevat:</span><span class="sxs-lookup"><span data-stu-id="9ad42-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="9ad42-135">In de volgende opdrachten is het voorbeeldtekst bestand C:\Mijn Documents\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="9ad42-135">In the following commands, the example text file is C:\My Documents\Accounts.txt.</span></span> <span data-ttu-id="9ad42-136">Vervang dit door het pad en de bestandsnaam van het tekstbestand.</span><span class="sxs-lookup"><span data-stu-id="9ad42-136">Replace this with the path and file name of your text file.</span></span>
    
<span data-ttu-id="9ad42-137">Voer de volgende opdracht uit als u de toegang tot de accounts die worden vermeld in het tekstbestand wilt blokkeren:</span><span class="sxs-lookup"><span data-stu-id="9ad42-137">To block access to the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="9ad42-138">Voer de volgende opdracht uit om de accounts die in het tekstbestand worden weergegeven, op te heffen:</span><span class="sxs-lookup"><span data-stu-id="9ad42-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="9ad42-139">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9ad42-139">See also</span></span>

[<span data-ttu-id="9ad42-140">Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ad42-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9ad42-141">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ad42-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9ad42-142">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9ad42-142">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
