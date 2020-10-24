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
description: PowerShell gebruiken om de toegang tot Microsoft 365-accounts te blokkeren of te deblokkeren.
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754678"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="61b55-103">Microsoft 365-gebruikersaccounts blokkeren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="61b55-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="61b55-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="61b55-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="61b55-105">Als u toegang tot een Microsoft 365-account blokkeert, voorkomt u dat iedereen het account kan gebruiken om u aan te melden en toegang te krijgen tot de services en gegevens in uw Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="61b55-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="61b55-106">U kunt PowerShell gebruiken om toegang te blokkeren voor afzonderlijke of meerdere gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="61b55-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="61b55-107">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="61b55-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="61b55-108">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="61b55-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="61b55-109">Toegang tot afzonderlijke gebruikersaccounts blokkeren</span><span class="sxs-lookup"><span data-stu-id="61b55-109">Block access to individual user accounts</span></span>

<span data-ttu-id="61b55-110">Gebruik de volgende syntaxis om een afzonderlijke gebruikersaccount te blokkeren:</span><span class="sxs-lookup"><span data-stu-id="61b55-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="61b55-111">Met de parameter *-ObjectID* in de cmdlet **set-AzureAD** wordt de aanmeldingsnaam van het account geaccepteerd, ook wel bekend als de User Principal name of de object-id van de account.</span><span class="sxs-lookup"><span data-stu-id="61b55-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="61b55-112">In dit voorbeeld wordt de toegang tot de *fabricec@litwareinc.com*van de gebruikersaccount geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="61b55-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="61b55-113">Voer de volgende opdracht uit als u dit gebruikersaccount wilt deblokkeren:</span><span class="sxs-lookup"><span data-stu-id="61b55-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="61b55-114">Als u de UPN van het gebruikersaccount wilt weergeven op basis van de weergavenaam van de gebruiker, gebruikt u de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="61b55-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="61b55-115">In dit voorbeeld wordt de UPN van het gebruikersaccount voor de gebruiker  *Caleb Sills*.</span><span class="sxs-lookup"><span data-stu-id="61b55-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="61b55-116">Als u een account wilt blokkeren op basis van de weergavenaam van de gebruiker, gebruikt u de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="61b55-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="61b55-117">Als u de geblokkeerde status van een gebruikersaccount wilt controleren, gebruikt u de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="61b55-117">To check the blocked status of a user account use the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="61b55-118">Meerdere gebruikersaccounts blokkeren</span><span class="sxs-lookup"><span data-stu-id="61b55-118">Block multiple user accounts</span></span>

<span data-ttu-id="61b55-119">Als u de toegang voor meerdere gebruikersaccounts wilt blokkeren, maakt u een tekstbestand met één aanmeldingsnaam op elke regel, zoals deze:</span><span class="sxs-lookup"><span data-stu-id="61b55-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="61b55-120">In de volgende opdrachten is het voorbeeldtekst bestand *c:\mijn Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="61b55-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="61b55-121">Vervang de naam van het bestand met het pad en de bestandsnaam van het tekstbestand.</span><span class="sxs-lookup"><span data-stu-id="61b55-121">Replace this file name with the path and file name of your text file.</span></span>
  
<span data-ttu-id="61b55-122">Voer de volgende opdracht uit als u de toegang tot de accounts die worden vermeld in het tekstbestand wilt blokkeren:</span><span class="sxs-lookup"><span data-stu-id="61b55-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="61b55-123">Voer de volgende opdracht uit om de accounts die in het tekstbestand worden weergegeven, op te heffen:</span><span class="sxs-lookup"><span data-stu-id="61b55-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="61b55-124">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="61b55-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="61b55-125">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="61b55-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-individual-user-accounts"></a><span data-ttu-id="61b55-126">Afzonderlijke gebruikersaccounts blokkeren</span><span class="sxs-lookup"><span data-stu-id="61b55-126">Block individual user accounts</span></span>

<span data-ttu-id="61b55-127">Gebruik de volgende syntaxis om toegang te blokkeren voor een afzonderlijke gebruikersaccount:</span><span class="sxs-lookup"><span data-stu-id="61b55-127">Use the following syntax to block access for an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="61b55-128">PowerShell core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met *MSOL* in de naam.</span><span class="sxs-lookup"><span data-stu-id="61b55-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="61b55-129">U dient deze cmdlets uit te voeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61b55-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="61b55-130">In dit voorbeeld wordt de toegang blokkeren voor het gebruikersaccount *fabricec \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="61b55-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="61b55-131">Voer de volgende opdracht uit om het gebruikersaccount te deblokkeren:</span><span class="sxs-lookup"><span data-stu-id="61b55-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="61b55-132">Voer de volgende opdracht uit om de geblokkeerde status van een gebruikersaccount te controleren:</span><span class="sxs-lookup"><span data-stu-id="61b55-132">To check the blocked status of a user account run the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="61b55-133">Toegang blokkeren voor meerdere gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="61b55-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="61b55-134">Maak eerst als volgt een tekstbestand dat één account op elke regel bevat:</span><span class="sxs-lookup"><span data-stu-id="61b55-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="61b55-135">In de volgende opdrachten is het voorbeeldtekst bestand *c:\mijn Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="61b55-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="61b55-136">Vervang de naam van het bestand met het pad en de bestandsnaam van het tekstbestand.</span><span class="sxs-lookup"><span data-stu-id="61b55-136">Replace this file name with the path and file name of your text file.</span></span>
    
<span data-ttu-id="61b55-137">Voer de volgende opdracht uit om toegang te blokkeren voor de accounts die in het tekstbestand worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="61b55-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="61b55-138">Voer de volgende opdracht uit om de accounts die in het tekstbestand worden weergegeven, op te heffen:</span><span class="sxs-lookup"><span data-stu-id="61b55-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="61b55-139">Zie ook</span><span class="sxs-lookup"><span data-stu-id="61b55-139">See also</span></span>

[<span data-ttu-id="61b55-140">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="61b55-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="61b55-141">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="61b55-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="61b55-142">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="61b55-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
