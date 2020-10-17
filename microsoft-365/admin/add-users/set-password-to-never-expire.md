---
title: Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Meer informatie over het instellen van wachtwoorden voor afzonderlijke gebruikers voor nooit verloopt, met behulp van Windows PowerShell.
ms.openlocfilehash: e778ad8a020a6767934d51f8bc227bfc39b13a9b
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580914"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="a7680-103">Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt</span><span class="sxs-lookup"><span data-stu-id="a7680-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="a7680-104">In dit artikel wordt uitgelegd hoe u een wachtwoord instelt waarmee een individuele gebruiker niet verloopt.</span><span class="sxs-lookup"><span data-stu-id="a7680-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="a7680-105">U moet deze stappen uitvoeren met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7680-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a7680-106">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="a7680-106">Before you begin</span></span>

<span data-ttu-id="a7680-107">Dit artikel is bedoeld voor personen die het wachtwoordverloopbeleid voor een bedrijf, school of non-profitorganisatie opstellen.</span><span class="sxs-lookup"><span data-stu-id="a7680-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="a7680-108">Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="a7680-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="a7680-109">[Wat is een beheerdersaccount?](../admin-overview/admin-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a7680-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> 

<span data-ttu-id="a7680-110">U moet een [globale beheerder of wachtwoordbeheerder](about-admin-roles.md) zijn om deze stappen te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="a7680-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="a7680-111">Een globale beheerder van een Microsoft-cloudservice kan de [Azure Active Directory PowerShell voor Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) gebruiken om wachtwoorden zodanig in te stellen dat deze niet verlopen voor specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="a7680-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="a7680-112">U kunt ook [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) -cmdlets gebruiken om de configuratie nooit-expires te verwijderen of om te zien welke gebruikerswachtwoorden zo zijn ingesteld dat nooit verloopt.</span><span class="sxs-lookup"><span data-stu-id="a7680-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="a7680-113">Deze handleiding is van toepassing op andere providers, zoals intune en Microsoft 365, die ook gebruikmaken van Azure AD voor identiteit en Directory Services.</span><span class="sxs-lookup"><span data-stu-id="a7680-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="a7680-114">Het verlopen van wachtwoorden is het enige onderdeel van het beleid dat kan worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="a7680-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="a7680-115">Alleen wachtwoorden voor gebruikersaccounts die niet zijn gesynchroniseerd via adreslijstsynchronisatie, kunnen zo worden geconfigureerd dat deze niet verlopen.</span><span class="sxs-lookup"><span data-stu-id="a7680-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="a7680-116">Zie voor meer informatie over adreslijstsynchronisatie de [koppeling AD verbinden met Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="a7680-116">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="a7680-117">Het verloopbeleid voor een wachtwoord controleren</span><span class="sxs-lookup"><span data-stu-id="a7680-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="a7680-118">Zie het artikel [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)voor meer informatie over de opdracht Get-AzureADUser in de AzureAD-module.</span><span class="sxs-lookup"><span data-stu-id="a7680-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="a7680-119">Voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="a7680-119">Run one of the following commands:</span></span>

- <span data-ttu-id="a7680-120">Als u wilt controleren of het wachtwoord van een gebruiker zo is ingesteld dat het nooit verloopt, voert u de volgende cmdlet uit met behulp van de UPN (zoals *user@contoso.onmicrosoft.com*) of de gebruikers-id van de gebruiker die u wilt controleren:</span><span class="sxs-lookup"><span data-stu-id="a7680-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="a7680-121">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="a7680-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="a7680-122">Voer de volgende cmdlet uit om de instelling **wachtwoord nooit verloopt** voor alle gebruikers weer te geven:</span><span class="sxs-lookup"><span data-stu-id="a7680-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="a7680-123">Als u een rapport wilt weergeven van alle gebruikers met PasswordNeverExpires in HTML op de desktopcomputer van de huidige gebruiker waarvan de naam  **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="a7680-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="a7680-124">Als u een rapport wilt weergeven van alle gebruikers met PasswordNeverExpires in CSV op het bureaublad van de huidige gebruiker met naam **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="a7680-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv

## Set a password to never expire

Run one of the following commands:

- To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="a7680-125">Voer de volgende cmdlet uit om het wachtwoord in te stellen, zodat alle gebruikers in een organisatie nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="a7680-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="a7680-126">Instellen dat een wachtwoord verloopt</span><span class="sxs-lookup"><span data-stu-id="a7680-126">Set a password to expire</span></span>

<span data-ttu-id="a7680-127">Voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="a7680-127">Run one of the following commands:</span></span>

- <span data-ttu-id="a7680-128">Als u het wachtwoord van een gebruiker zo wilt instellen dat het wachtwoord verloopt, voert u de volgende cmdlet uit met behulp van de UPN of de gebruikers-ID van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="a7680-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="a7680-129">Als u de wachtwoorden van alle gebruikers in de organisatie wilt instellen zodat ze verlopen, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a7680-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

> [!WARNING]
> <span data-ttu-id="a7680-130">Gebruikersaccounts die zijn geconfigureerd met de `-PasswordPolicies DisablePasswordExpiration` parameter die nog ouder is gemaakt op basis van het kenmerk van het `pwdLastSet` gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="a7680-130">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` user account attribute.</span></span> <span data-ttu-id="a7680-131">Als u bijvoorbeeld het wachtwoord van een gebruiker zo instelt dat het nooit verloopt en 90 of meer dagen gaat, verloopt het wachtwoord nog steeds.</span><span class="sxs-lookup"><span data-stu-id="a7680-131">For example, if you set user passwords to never expire and then 90 or more days go by, the passwords still expire.</span></span> <span data-ttu-id="a7680-132">Op basis van het kenmerk van het `pwdLastSet` gebruikersaccount voor gebruikersaccounts die met de `-PasswordPolicies None` parameter zijn geconfigureerd, `pwdLastSet` moet de gebruiker de volgende keer dat u zich aanmeldt, gebruikersaccounts met een ouder dan 90 dagen wijzigen. Deze wijziging kan van invloed zijn op een groot aantal gebruikers.</span><span class="sxs-lookup"><span data-stu-id="a7680-132">Based on the `pwdLastSet` user account attribute, for user accounts configured with the `-PasswordPolicies None` parameter, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.This change can affect a large number of users.</span></span>

## <a name="related-content"></a><span data-ttu-id="a7680-133">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a7680-133">Related content</span></span>

[<span data-ttu-id="a7680-134">Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen</span><span class="sxs-lookup"><span data-stu-id="a7680-134">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="a7680-135">Wachtwoorden opnieuw instellen</span><span class="sxs-lookup"><span data-stu-id="a7680-135">Reset passwords</span></span>](../add-users/reset-passwords.md)