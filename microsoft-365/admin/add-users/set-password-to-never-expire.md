---
title: Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
description: Meld u aan bij uw Microsoft 365 beheerdersaccount om in te stellen dat sommige afzonderlijke gebruikerswachtwoorden nooit verlopen met behulp van Windows PowerShell.
ms.openlocfilehash: 0747e0bfe8a7389db554d5d6a7f685605e013306
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571923"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="ddc47-103">Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt</span><span class="sxs-lookup"><span data-stu-id="ddc47-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="ddc47-104">In dit artikel wordt uitgelegd hoe u een wachtwoord instelt voor een afzonderlijke gebruiker om niet te verlopen.</span><span class="sxs-lookup"><span data-stu-id="ddc47-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="ddc47-105">U moet deze stappen uitvoeren met PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ddc47-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ddc47-106">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="ddc47-106">Before you begin</span></span>

<span data-ttu-id="ddc47-107">Dit artikel is bedoeld voor personen die het wachtwoordverloopbeleid voor een bedrijf, school of non-profitorganisatie opstellen.</span><span class="sxs-lookup"><span data-stu-id="ddc47-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="ddc47-108">Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="ddc47-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="ddc47-109">[Wat is een beheerdersaccount?](../../business-video/admin-center-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ddc47-109">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span> 

<span data-ttu-id="ddc47-110">U moet een [globale beheerder of wachtwoordbeheerder](about-admin-roles.md) zijn om deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="ddc47-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="ddc47-111">Een globale beheerder voor een Microsoft-cloudservice kan de [Azure Active Directory PowerShell voor Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) gebruiken om in te stellen dat wachtwoorden niet verlopen voor specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ddc47-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="ddc47-112">U kunt [azureAD-cmdlets](/powershell/module/Azuread) ook gebruiken om de configuratie voor nooit verlopen te verwijderen of om te zien welke gebruikerswachtwoorden zijn ingesteld om nooit te verlopen.</span><span class="sxs-lookup"><span data-stu-id="ddc47-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="ddc47-113">Deze handleiding is van toepassing op andere providers, zoals Intune en Microsoft 365, die ook afhankelijk zijn van Azure AD voor identiteits- en directoryservices.</span><span class="sxs-lookup"><span data-stu-id="ddc47-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="ddc47-114">Het verlopen van wachtwoorden is het enige deel van het beleid dat kan worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="ddc47-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="ddc47-115">Alleen wachtwoorden voor gebruikersaccounts die niet zijn gesynchroniseerd via adreslijstsynchronisatie, kunnen worden geconfigureerd om niet te verlopen.</span><span class="sxs-lookup"><span data-stu-id="ddc47-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="ddc47-116">Zie Verbinding maken AD met [Azure AD](/azure/active-directory/connect/active-directory-aadconnect)voor meer informatie over adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="ddc47-116">For more information about directory synchronization, see [Connect AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="ddc47-117">Het verloopbeleid voor een wachtwoord controleren</span><span class="sxs-lookup"><span data-stu-id="ddc47-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="ddc47-118">Zie het referentie artikel [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)voor meer informatie over de opdracht Get-AzureADUser in de AzureAD-module.</span><span class="sxs-lookup"><span data-stu-id="ddc47-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="ddc47-119">Voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="ddc47-119">Run one of the following commands:</span></span>

- <span data-ttu-id="ddc47-120">Als u wilt zien of het wachtwoord van één gebruiker is ingesteld op nooit verlopen, voert u de volgende cmdlet uit met behulp van de UPN (bijvoorbeeld *user@contoso.onmicrosoft.com*) of de gebruikers-ID van de gebruiker die u wilt controleren:</span><span class="sxs-lookup"><span data-stu-id="ddc47-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="ddc47-121">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ddc47-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="ddc47-122">Voer de volgende cmdlet uit om te zien of de instelling **Wachtwoord nooit verloopt** voor alle gebruikers:</span><span class="sxs-lookup"><span data-stu-id="ddc47-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="ddc47-123">Om een rapport te krijgen van alle gebruikers met PasswordNeverExpires in Html op het bureaublad van de huidige gebruiker met naam  **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="ddc47-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="ddc47-124">Een rapport kregen van alle gebruikers met PasswordNeverExpires in CSV op het bureaublad van de huidige gebruiker met naam **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="ddc47-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="ddc47-125">Voer de volgende cmdlet uit om de wachtwoorden van alle gebruikers in een organisatie in te stellen op nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="ddc47-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="ddc47-126">Gebruikersaccounts die zijn geconfigureerd met de `-PasswordPolicies DisablePasswordExpiration` parameter worden nog steeds leeftijd op basis van het `pwdLastSet` kenmerk.</span><span class="sxs-lookup"><span data-stu-id="ddc47-126">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="ddc47-127">Als u op basis van het `pwdLastSet` kenmerk de vervaldatum wijzigt in , moeten alle wachtwoorden met een `-PasswordPolicies None` pwdLastSet ouder dan 90 dagen de gebruiker deze wijzigen de volgende keer dat ze zich aanmelden.</span><span class="sxs-lookup"><span data-stu-id="ddc47-127">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="ddc47-128">Deze wijziging kan van invloed zijn op een groot aantal gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ddc47-128">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="ddc47-129">Een wachtwoord instellen om te verlopen</span><span class="sxs-lookup"><span data-stu-id="ddc47-129">Set a password to expire</span></span>

<span data-ttu-id="ddc47-130">Voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="ddc47-130">Run one of the following commands:</span></span>

- <span data-ttu-id="ddc47-131">Als u het wachtwoord van één gebruiker zo wilt instellen dat het wachtwoord verloopt, voert u de volgende cmdlet uit met behulp van de UPN of de gebruikers-ID van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="ddc47-131">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="ddc47-132">Als u de wachtwoorden van alle gebruikers in de organisatie wilt instellen zodat ze verlopen, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ddc47-132">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="ddc47-133">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ddc47-133">Related content</span></span>

<span data-ttu-id="ddc47-134">[Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen](../add-users/let-users-reset-passwords.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ddc47-134">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>

<span data-ttu-id="ddc47-135">[Wachtwoorden opnieuw instellen](../add-users/reset-passwords.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ddc47-135">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>