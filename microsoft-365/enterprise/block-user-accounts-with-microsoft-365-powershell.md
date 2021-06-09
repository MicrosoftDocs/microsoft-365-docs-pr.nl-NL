---
title: Gebruikersaccounts Microsoft 365 blokkeren met PowerShell
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
description: PowerShell gebruiken om toegang tot accounts te blokkeren en Microsoft 365 deblokkeren.
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754678"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="aaf32-103">Gebruikersaccounts Microsoft 365 blokkeren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="aaf32-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="aaf32-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="aaf32-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="aaf32-105">Wanneer u de toegang tot een Microsoft 365 account blokkeert, voorkomt u dat iemand het account gebruikt om zich aan te melden en toegang te krijgen tot de services en gegevens in uw Microsoft 365 organisatie.</span><span class="sxs-lookup"><span data-stu-id="aaf32-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="aaf32-106">U kunt PowerShell gebruiken om de toegang tot afzonderlijke of meerdere gebruikersaccounts te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="aaf32-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="aaf32-107">De powershell Azure Active Directory powershell gebruiken voor Graph module</span><span class="sxs-lookup"><span data-stu-id="aaf32-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="aaf32-108">Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="aaf32-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="aaf32-109">Toegang tot afzonderlijke gebruikersaccounts blokkeren</span><span class="sxs-lookup"><span data-stu-id="aaf32-109">Block access to individual user accounts</span></span>

<span data-ttu-id="aaf32-110">Gebruik de volgende syntaxis om een afzonderlijk gebruikersaccount te blokkeren:</span><span class="sxs-lookup"><span data-stu-id="aaf32-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="aaf32-111">De *parameter -ObjectID* in de cmdlet **Set-AzureAD** accepteert de aanmeldingsnaam van het account, ook wel de gebruikersnaam genoemd, of de object-id van het account.</span><span class="sxs-lookup"><span data-stu-id="aaf32-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="aaf32-112">In dit voorbeeld wordt de toegang tot het gebruikersaccount *fabricec@litwareinc.com.*</span><span class="sxs-lookup"><span data-stu-id="aaf32-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="aaf32-113">Voer de volgende opdracht uit om dit gebruikersaccount te deblokkeren:</span><span class="sxs-lookup"><span data-stu-id="aaf32-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="aaf32-114">Gebruik de volgende opdrachten om de UPN van het gebruikersaccount weer te geven op basis van de weergavenaam van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="aaf32-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="aaf32-115">In dit voorbeeld wordt de UPN van het gebruikersaccount voor de gebruiker *Caleb Sills weergegeven.*</span><span class="sxs-lookup"><span data-stu-id="aaf32-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="aaf32-116">Als u een account wilt blokkeren op basis van de weergavenaam van de gebruiker, gebruikt u de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="aaf32-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="aaf32-117">Als u de geblokkeerde status van een gebruikersaccount wilt controleren, gebruikt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="aaf32-117">To check the blocked status of a user account use the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="aaf32-118">Meerdere gebruikersaccounts blokkeren</span><span class="sxs-lookup"><span data-stu-id="aaf32-118">Block multiple user accounts</span></span>

<span data-ttu-id="aaf32-119">Als u de toegang voor meerdere gebruikersaccounts wilt blokkeren, maakt u een tekstbestand met één accountnaam op elke regel als deze:</span><span class="sxs-lookup"><span data-stu-id="aaf32-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="aaf32-120">In de volgende opdrachten is het voorbeeldtekstbestand *C:\Mijn Documents\Accounts.txt.*</span><span class="sxs-lookup"><span data-stu-id="aaf32-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="aaf32-121">Vervang deze bestandsnaam door het pad en de bestandsnaam van het tekstbestand.</span><span class="sxs-lookup"><span data-stu-id="aaf32-121">Replace this file name with the path and file name of your text file.</span></span>
  
<span data-ttu-id="aaf32-122">Voer de volgende opdracht uit om de toegang tot de accounts in het tekstbestand te blokkeren:</span><span class="sxs-lookup"><span data-stu-id="aaf32-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="aaf32-123">Als u de blokkering van de accounts in het tekstbestand wilt opheffen, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="aaf32-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="aaf32-124">Gebruik de Microsoft Azure Active Directory module voor Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aaf32-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="aaf32-125">Maak eerst [verbinding met uw Microsoft 365 tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="aaf32-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-individual-user-accounts"></a><span data-ttu-id="aaf32-126">Afzonderlijke gebruikersaccounts blokkeren</span><span class="sxs-lookup"><span data-stu-id="aaf32-126">Block individual user accounts</span></span>

<span data-ttu-id="aaf32-127">Gebruik de volgende syntaxis om toegang voor een afzonderlijk gebruikersaccount te blokkeren:</span><span class="sxs-lookup"><span data-stu-id="aaf32-127">Use the following syntax to block access for an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="aaf32-128">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory module voor Windows PowerShell module en cmdlets met *Msol* in hun naam.</span><span class="sxs-lookup"><span data-stu-id="aaf32-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="aaf32-129">U moet deze cmdlets uitvoeren vanaf Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aaf32-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="aaf32-130">In dit voorbeeld wordt de toegang tot de fabricec van het gebruikersaccount *\@ litwareinc.com.*</span><span class="sxs-lookup"><span data-stu-id="aaf32-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="aaf32-131">Voer de volgende opdracht uit om het gebruikersaccount te deblokkeren:</span><span class="sxs-lookup"><span data-stu-id="aaf32-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="aaf32-132">Voer de volgende opdracht uit om de geblokkeerde status van een gebruikersaccount te controleren:</span><span class="sxs-lookup"><span data-stu-id="aaf32-132">To check the blocked status of a user account run the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="aaf32-133">Toegang blokkeren voor meerdere gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="aaf32-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="aaf32-134">Maak eerst een tekstbestand met één account op elke regel als dit:</span><span class="sxs-lookup"><span data-stu-id="aaf32-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="aaf32-135">In de volgende opdrachten is het voorbeeldtekstbestand *C:\Mijn Documents\Accounts.txt.*</span><span class="sxs-lookup"><span data-stu-id="aaf32-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="aaf32-136">Vervang deze bestandsnaam door het pad en de bestandsnaam van het tekstbestand.</span><span class="sxs-lookup"><span data-stu-id="aaf32-136">Replace this file name with the path and file name of your text file.</span></span>
    
<span data-ttu-id="aaf32-137">Voer de volgende opdracht uit als u de toegang wilt blokkeren voor de accounts die in het tekstbestand worden vermeld:</span><span class="sxs-lookup"><span data-stu-id="aaf32-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="aaf32-138">Als u de blokkering van de accounts in het tekstbestand wilt opheffen, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="aaf32-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="aaf32-139">Zie ook</span><span class="sxs-lookup"><span data-stu-id="aaf32-139">See also</span></span>

[<span data-ttu-id="aaf32-140">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="aaf32-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="aaf32-141">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="aaf32-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="aaf32-142">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aaf32-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
