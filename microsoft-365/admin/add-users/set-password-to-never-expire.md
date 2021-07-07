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
description: Meld u aan bij uw Microsoft 365 beheerdersaccount om bepaalde afzonderlijke gebruikerswachtwoorden zo in te stellen dat ze nooit verlopen met behulp van Windows PowerShell.
ms.openlocfilehash: c9f0c245aca0e028183c42f6a257068d74aa563d
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53326721"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="f6d6f-103">Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt</span><span class="sxs-lookup"><span data-stu-id="f6d6f-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="f6d6f-104">In dit artikel wordt uitgelegd hoe u een wachtwoord kunt instellen voor een individuele gebruiker die niet verloopt.</span><span class="sxs-lookup"><span data-stu-id="f6d6f-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="f6d6f-105">U moet deze stappen met PowerShell voltooien.</span><span class="sxs-lookup"><span data-stu-id="f6d6f-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f6d6f-106">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="f6d6f-106">Before you begin</span></span>

<span data-ttu-id="f6d6f-107">Dit artikel is bedoeld voor personen die het wachtwoordverloopbeleid voor een bedrijf, school of non-profitorganisatie opstellen.</span><span class="sxs-lookup"><span data-stu-id="f6d6f-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="f6d6f-108">Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="f6d6f-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="f6d6f-109">[Wat is een beheerdersaccount?](../../business-video/admin-center-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f6d6f-109">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span>

<span data-ttu-id="f6d6f-110">U moet een globale [beheerder of wachtwoordbeheerder zijn om](about-admin-roles.md) deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="f6d6f-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="f6d6f-111">Een globale beheerder van een Microsoft-cloudservice kan de Azure Active Directory [PowerShell](/powershell/azure/active-directory/install-adv2) voor Graph instellen dat wachtwoorden niet verlopen voor specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="f6d6f-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="f6d6f-112">U kunt [azureAD-cmdlets](/powershell/module/Azuread) ook gebruiken om de configuratie die nooit verloopt te verwijderen of om te zien welke gebruikerswachtwoorden zijn ingesteld op nooit verlopen.</span><span class="sxs-lookup"><span data-stu-id="f6d6f-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="f6d6f-113">Deze handleiding is van toepassing op andere providers, zoals Intune en Microsoft 365, die ook afhankelijk zijn van Azure AD voor identiteits- en adreslijstservices.</span><span class="sxs-lookup"><span data-stu-id="f6d6f-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="f6d6f-114">Wachtwoordverloop is het enige deel van het beleid dat kan worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="f6d6f-114">Password expiration is the only part of the policy that can be changed.</span></span>


## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="f6d6f-115">Het verloopbeleid controleren op een wachtwoord</span><span class="sxs-lookup"><span data-stu-id="f6d6f-115">How to check the expiration policy for a password</span></span>

<span data-ttu-id="f6d6f-116">Zie het naslagartikel [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser)voor meer informatie over Get-AzureADUser opdracht in de AzureAD-module.</span><span class="sxs-lookup"><span data-stu-id="f6d6f-116">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser).</span></span>

<span data-ttu-id="f6d6f-117">Voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="f6d6f-117">Run one of the following commands:</span></span>

- <span data-ttu-id="f6d6f-118">Als u wilt zien of het wachtwoord van één gebruiker nooit verloopt, moet u de volgende cmdlet uitvoeren met behulp van de UPN (bijvoorbeeld *user@contoso.onmicrosoft.com)* of de gebruikers-id van de gebruiker die u wilt controleren:</span><span class="sxs-lookup"><span data-stu-id="f6d6f-118">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="f6d6f-119">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="f6d6f-119">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

- <span data-ttu-id="f6d6f-120">Voer de **volgende** cmdlet uit om te zien dat de instelling Wachtwoord nooit verloopt voor alle gebruikers:</span><span class="sxs-lookup"><span data-stu-id="f6d6f-120">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="f6d6f-121">Een rapport downloaden van alle gebruikers met PasswordNeverExpires in Html op het bureaublad van de huidige gebruiker met  **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="f6d6f-121">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```

- <span data-ttu-id="f6d6f-122">Een rapport van alle gebruikers met PasswordNeverExpires in CSV op het bureaublad van de huidige gebruiker met naam **enReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="f6d6f-122">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="f6d6f-123">Voer de volgende cmdlet uit als u wilt instellen dat de wachtwoorden van alle gebruikers in een organisatie nooit verlopen:</span><span class="sxs-lookup"><span data-stu-id="f6d6f-123">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="f6d6f-124">Gebruikersaccounts die zijn geconfigureerd met `-PasswordPolicies DisablePasswordExpiration` de parameter die nog steeds ouder wordt op basis van het `pwdLastSet` kenmerk.</span><span class="sxs-lookup"><span data-stu-id="f6d6f-124">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="f6d6f-125">Als u op basis van het kenmerk de vervaldatum wijzigt in , moeten alle wachtwoorden met een pwdLastSet ouder dan 90 dagen de gebruiker wijzigen wanneer ze zich de volgende keer `pwdLastSet` `-PasswordPolicies None` aanmelden.</span><span class="sxs-lookup"><span data-stu-id="f6d6f-125">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="f6d6f-126">Deze wijziging kan van invloed zijn op een groot aantal gebruikers.</span><span class="sxs-lookup"><span data-stu-id="f6d6f-126">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="f6d6f-127">Een wachtwoord instellen dat moet verlopen</span><span class="sxs-lookup"><span data-stu-id="f6d6f-127">Set a password to expire</span></span>

<span data-ttu-id="f6d6f-128">Voer een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="f6d6f-128">Run one of the following commands:</span></span>

- <span data-ttu-id="f6d6f-129">Als u het wachtwoord van één gebruiker zo wilt instellen dat het wachtwoord verloopt, moet u de volgende cmdlet uitvoeren met behulp van de UPN of de gebruikers-id van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="f6d6f-129">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="f6d6f-130">Als u de wachtwoorden van alle gebruikers in de organisatie zo wilt instellen dat ze verlopen, gebruikt u de volgende cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f6d6f-130">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="f6d6f-131">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f6d6f-131">Related content</span></span>

<span data-ttu-id="f6d6f-132">[Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen](../add-users/let-users-reset-passwords.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="f6d6f-132">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>\
<span data-ttu-id="f6d6f-133">[Wachtwoorden opnieuw instellen](../add-users/reset-passwords.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="f6d6f-133">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>\
<span data-ttu-id="f6d6f-134">[Het wachtwoordverloopbeleid voor uw organisatie instellen](../manage/set-password-expiration-policy.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="f6d6f-134">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>
