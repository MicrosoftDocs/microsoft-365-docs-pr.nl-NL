---
title: Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Meer informatie over het instellen van bepaalde afzonderlijke gebruikerswachtwoorden die nooit verlopen met Windows PowerShell.
ms.openlocfilehash: 6562a4092c47d9c4bf7bf294767e6050a3e0577a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44386999"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="66705-103">Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt</span><span class="sxs-lookup"><span data-stu-id="66705-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="66705-104">Het wachtwoordverloopbeleid voor uw organisatie instellen:</span><span class="sxs-lookup"><span data-stu-id="66705-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="66705-105">Ga in het beheercentrum **Settings** naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Instellingen instellingen.</a></span><span class="sxs-lookup"><span data-stu-id="66705-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>
2. <span data-ttu-id="66705-106">Selecteer beveiliging **& Privacy**boven aan de pagina Instellingen .</span><span class="sxs-lookup"><span data-stu-id="66705-106">At the top of the Settings page select **Security & Privacy**.</span></span>
3. <span data-ttu-id="66705-107">Selecteer **Verloopbeleid wachtwoorden**.</span><span class="sxs-lookup"><span data-stu-id="66705-107">Select **Password expiration policy**.</span></span> 
4. <span data-ttu-id="66705-108">Als wachtwoorden nooit verlopen, klikt u op het selectievakje naast **Gebruikerswachtwoorden instellen om na een aantal dagen te verlopen.**</span><span class="sxs-lookup"><span data-stu-id="66705-108">If passwords are set to never expire, click the check box next to **Set user passwords to expire after a number of days**.</span></span> <span data-ttu-id="66705-109">U krijgt de optie om het aantal dagen op te geven totdat wachtwoorden verlopen.</span><span class="sxs-lookup"><span data-stu-id="66705-109">You'll get the option to specify the number of days until passwords expire.</span></span>

## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="66705-110">Het wachtwoordverloopbeleid instellen voor individuele gebruikers</span><span class="sxs-lookup"><span data-stu-id="66705-110">Set the password expiration policy for individual users</span></span>

<span data-ttu-id="66705-111">Een globale beheerder voor een Microsoft-cloudservice kan de [Azure Active Directory PowerShell voor Grafiek](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) gebruiken om in te stellen dat wachtwoorden niet verlopen voor specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="66705-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="66705-112">U [azuread-cmdlets](https://docs.microsoft.com/powershell/module/Azuread) ook gebruiken om de nooit verlopen configuratie te verwijderen of om te zien welke gebruikerswachtwoorden nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="66705-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="66705-113">Deze handleiding is van toepassing op andere providers, zoals Intune en Microsoft 365, die ook afhankelijk zijn van Azure AD voor identiteits- en directoryservices.</span><span class="sxs-lookup"><span data-stu-id="66705-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="66705-114">Het verlopen van wachtwoorden is het enige onderdeel van het beleid dat kan worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="66705-114">Password expiration is the only part of the policy that can be changed.</span></span>

<span data-ttu-id="66705-115">Zie [Azure Active Directory PowerShell voor Grafiek voor](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)meer informatie over Azure AD PowerShell voor Grafiek.</span><span class="sxs-lookup"><span data-stu-id="66705-115">For more information about Azure AD PowerShell for Graph, see [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span></span>

> [!NOTE]
> <span data-ttu-id="66705-116">Alleen wachtwoorden voor gebruikersaccounts die niet zijn gesynchroniseerd via adreslijstsynchronisatie, kunnen worden geconfigureerd om niet te verlopen.</span><span class="sxs-lookup"><span data-stu-id="66705-116">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="66705-117">Zie AD verbinden met Azure [AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)voor meer informatie over adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="66705-117">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="66705-118">Het verloopbeleid controleren op een wachtwoord</span><span class="sxs-lookup"><span data-stu-id="66705-118">How to check the expiration policy for a password</span></span>

<span data-ttu-id="66705-119">Zie het referentieartikel [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)voor meer informatie over de opdracht Get-AzureADUser in de AzureAD-module.</span><span class="sxs-lookup"><span data-stu-id="66705-119">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="66705-120">Voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="66705-120">Run one of the following commands:</span></span>

- <span data-ttu-id="66705-121">Als u wilt zien of het wachtwoord van één gebruiker nooit verloopt, voert u de volgende cmdlet uit met behulp van de UPN (bijvoorbeeld *user@contoso.onmicrosoft.com)* of de gebruikers-id van de gebruiker die u wilt controleren:</span><span class="sxs-lookup"><span data-stu-id="66705-121">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="66705-122">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="66705-122">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="66705-123">Voer de volgende cmdlet uit om de instelling Wachtwoord nooit voor alle gebruikers **te bekijken:**</span><span class="sxs-lookup"><span data-stu-id="66705-123">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="66705-124">Een rapport van alle gebruikers met PasswordNeverExpires in Html op het bureaublad van de huidige gebruiker met naam **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="66705-124">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="66705-125">Een rapport van alle gebruikers met PasswordNeverExpires in CSV op het bureaublad van de huidige gebruiker met naam **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="66705-125">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="66705-126">Een wachtwoord instellen om te verlopen</span><span class="sxs-lookup"><span data-stu-id="66705-126">Set a password to expire</span></span>

<span data-ttu-id="66705-127">Voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="66705-127">Run one of the following commands:</span></span>

- <span data-ttu-id="66705-128">Als u het wachtwoord van één gebruiker wilt instellen zodat het wachtwoord verloopt, voert u de volgende cmdlet uit met de UPN of de gebruikers-id van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="66705-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="66705-129">Als u de wachtwoorden van alle gebruikers in de organisatie zo wilt instellen dat ze verlopen, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="66705-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="66705-130">Een wachtwoord instellen dat nooit verloopt</span><span class="sxs-lookup"><span data-stu-id="66705-130">Set a password to never expire</span></span>

<span data-ttu-id="66705-131">Voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="66705-131">Run one of the following commands:</span></span>

- <span data-ttu-id="66705-132">Als u wilt instellen dat het wachtwoord van één gebruiker nooit verloopt, voert u de volgende cmdlet uit met de UPN of de gebruikers-id van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="66705-132">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="66705-133">Voer de volgende cmdlet uit om de wachtwoorden van alle gebruikers in een organisatie nooit te laten verlopen:</span><span class="sxs-lookup"><span data-stu-id="66705-133">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="66705-134">Wachtwoorden ingesteld `-PasswordPolicies DisablePasswordExpiration` op leeftijd op basis van het `pwdLastSet` kenmerk.</span><span class="sxs-lookup"><span data-stu-id="66705-134">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="66705-135">Als u de gebruikerswachtwoorden nooit laat verlopen en vervolgens meer dan 90 dagen voorbij gaat, verlopen de wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="66705-135">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="66705-136">Op basis van het `pwdLastSet` kenmerk moeten alle wachtwoorden die ouder zijn dan 90 dagen, als u de vervaldatum wijzigt, deze de volgende keer dat `-PasswordPolicies None` hij zich `pwdLastSet` aanmeldt, wijzigen.</span><span class="sxs-lookup"><span data-stu-id="66705-136">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="66705-137">Deze wijziging kan gevolgen hebben voor een groot aantal gebruikers.</span><span class="sxs-lookup"><span data-stu-id="66705-137">This change can affect a large number of users.</span></span>
