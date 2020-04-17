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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Meer informatie over het instellen van bepaalde afzonderlijke gebruikerswachtwoorden die nooit verlopen met Windows PowerShell.
ms.openlocfilehash: 2645e6d5f307a5e5ce8fab5f3a848bf4a539b031
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2020
ms.locfileid: "43540889"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="28e66-103">Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt</span><span class="sxs-lookup"><span data-stu-id="28e66-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="28e66-104">Het wachtwoordverloopbeleid voor uw organisatie instellen:</span><span class="sxs-lookup"><span data-stu-id="28e66-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="28e66-105">Ga in het beheercentrum naar de privacypagina **Instellingenbeveiliging** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">&.</a></span><span class="sxs-lookup"><span data-stu-id="28e66-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
2. <span data-ttu-id="28e66-106">Selecteer naast **het wachtwoordbeleid** **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="28e66-106">Next to **Password policy** select **Edit**.</span></span> 
3. <span data-ttu-id="28e66-107">Als wachtwoorden nooit verlopen, stelt u de schakelaar in op **Uitschakelen.**</span><span class="sxs-lookup"><span data-stu-id="28e66-107">If passwords are set to never expire, set the toggle to **Off**.</span></span> <span data-ttu-id="28e66-108">U krijgt de optie om het aantal dagen op te geven totdat wachtwoorden verlopen.</span><span class="sxs-lookup"><span data-stu-id="28e66-108">You'll get the option to specify the number of days until passwords expire.</span></span>

## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="28e66-109">Het wachtwoordverloopbeleid instellen voor individuele gebruikers</span><span class="sxs-lookup"><span data-stu-id="28e66-109">Set the password expiration policy for individual users</span></span>

<span data-ttu-id="28e66-110">Een globale beheerder voor een Microsoft-cloudservice kan de [Azure Active Directory PowerShell voor Grafiek](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) gebruiken om in te stellen dat wachtwoorden niet verlopen voor specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="28e66-110">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="28e66-111">U [azuread-cmdlets](https://docs.microsoft.com/powershell/module/Azuread) ook gebruiken om de nooit verlopen configuratie te verwijderen of om te zien welke gebruikerswachtwoorden nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="28e66-111">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="28e66-112">Deze handleiding is van toepassing op andere providers, zoals Intune en Office 365, die ook afhankelijk zijn van Azure AD voor identiteits- en directoryservices.</span><span class="sxs-lookup"><span data-stu-id="28e66-112">This guide applies to other providers, such as Intune and Office 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="28e66-113">Het verlopen van wachtwoorden is het enige onderdeel van het beleid dat kan worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="28e66-113">Password expiration is the only part of the policy that can be changed.</span></span>

<span data-ttu-id="28e66-114">Zie [Azure Active Directory PowerShell voor Grafiek voor](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)meer informatie over Azure AD PowerShell voor Grafiek.</span><span class="sxs-lookup"><span data-stu-id="28e66-114">For more information about Azure AD PowerShell for Graph, see [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span></span>

> [!NOTE]
> <span data-ttu-id="28e66-115">Alleen wachtwoorden voor gebruikersaccounts die niet zijn gesynchroniseerd via adreslijstsynchronisatie, kunnen worden geconfigureerd om niet te verlopen.</span><span class="sxs-lookup"><span data-stu-id="28e66-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="28e66-116">Zie AD verbinden met Azure [AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)voor meer informatie over adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="28e66-116">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="28e66-117">Het verloopbeleid controleren op een wachtwoord</span><span class="sxs-lookup"><span data-stu-id="28e66-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="28e66-118">Zie het referentieartikel [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)voor meer informatie over de opdracht Get-AzureADUser in de AzureAD-module.</span><span class="sxs-lookup"><span data-stu-id="28e66-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="28e66-119">Voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="28e66-119">Run one of the following commands:</span></span>

- <span data-ttu-id="28e66-120">Als u wilt zien of het wachtwoord van één gebruiker nooit verloopt, voert u de volgende cmdlet uit met behulp van de UPN (bijvoorbeeld *user@contoso.onmicrosoft.com)* of de gebruikers-id van de gebruiker die u wilt controleren:</span><span class="sxs-lookup"><span data-stu-id="28e66-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="28e66-121">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="28e66-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="28e66-122">Voer de volgende cmdlet uit om de instelling Wachtwoord nooit voor alle gebruikers **te bekijken:**</span><span class="sxs-lookup"><span data-stu-id="28e66-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="28e66-123">Een rapport van alle gebruikers met PasswordNeverExpires in Html op het bureaublad van de huidige gebruiker met naam **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="28e66-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="28e66-124">Een rapport van alle gebruikers met PasswordNeverExpires in CSV op het bureaublad van de huidige gebruiker met naam **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="28e66-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="28e66-125">Een wachtwoord instellen om te verlopen</span><span class="sxs-lookup"><span data-stu-id="28e66-125">Set a password to expire</span></span>

<span data-ttu-id="28e66-126">Voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="28e66-126">Run one of the following commands:</span></span>

- <span data-ttu-id="28e66-127">Als u het wachtwoord van één gebruiker wilt instellen zodat het wachtwoord verloopt, voert u de volgende cmdlet uit met de UPN of de gebruikers-id van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="28e66-127">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="28e66-128">Als u de wachtwoorden van alle gebruikers in de organisatie zo wilt instellen dat ze verlopen, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="28e66-128">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="28e66-129">Een wachtwoord instellen dat nooit verloopt</span><span class="sxs-lookup"><span data-stu-id="28e66-129">Set a password to never expire</span></span>

<span data-ttu-id="28e66-130">Voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="28e66-130">Run one of the following commands:</span></span>

- <span data-ttu-id="28e66-131">Als u wilt instellen dat het wachtwoord van één gebruiker nooit verloopt, voert u de volgende cmdlet uit met de UPN of de gebruikers-id van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="28e66-131">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="28e66-132">Voer de volgende cmdlet uit om de wachtwoorden van alle gebruikers in een organisatie nooit te laten verlopen:</span><span class="sxs-lookup"><span data-stu-id="28e66-132">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="28e66-133">Wachtwoorden ingesteld `-PasswordPolicies DisablePasswordExpiration` op leeftijd `pwdLastSet` op basis van het kenmerk.</span><span class="sxs-lookup"><span data-stu-id="28e66-133">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="28e66-134">Als u de gebruikerswachtwoorden nooit laat verlopen en vervolgens meer dan 90 dagen voorbij gaat, verlopen de wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="28e66-134">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="28e66-135">Op basis `pwdLastSet` van het kenmerk moeten `-PasswordPolicies None`alle wachtwoorden die `pwdLastSet` ouder zijn dan 90 dagen, als u de vervaldatum wijzigt, deze de volgende keer dat hij zich aanmeldt, wijzigen.</span><span class="sxs-lookup"><span data-stu-id="28e66-135">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="28e66-136">Deze wijziging kan gevolgen hebben voor een groot aantal gebruikers.</span><span class="sxs-lookup"><span data-stu-id="28e66-136">This change can affect a large number of users.</span></span>
