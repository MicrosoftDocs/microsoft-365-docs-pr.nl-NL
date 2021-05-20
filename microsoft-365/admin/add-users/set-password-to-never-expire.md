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
# <a name="set-an-individual-users-password-to-never-expire"></a>Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt

In dit artikel wordt uitgelegd hoe u een wachtwoord instelt voor een afzonderlijke gebruiker om niet te verlopen. U moet deze stappen uitvoeren met PowerShell.

## <a name="before-you-begin"></a>Voordat u begint

Dit artikel is bedoeld voor personen die het wachtwoordverloopbeleid voor een bedrijf, school of non-profitorganisatie opstellen. Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount. [Wat is een beheerdersaccount?](../../business-video/admin-center-overview.md). 

U moet een [globale beheerder of wachtwoordbeheerder](about-admin-roles.md) zijn om deze stappen uit te voeren.

Een globale beheerder voor een Microsoft-cloudservice kan de [Azure Active Directory PowerShell voor Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) gebruiken om in te stellen dat wachtwoorden niet verlopen voor specifieke gebruikers. U kunt [azureAD-cmdlets](/powershell/module/Azuread) ook gebruiken om de configuratie voor nooit verlopen te verwijderen of om te zien welke gebruikerswachtwoorden zijn ingesteld om nooit te verlopen.

Deze handleiding is van toepassing op andere providers, zoals Intune en Microsoft 365, die ook afhankelijk zijn van Azure AD voor identiteits- en directoryservices. Het verlopen van wachtwoorden is het enige deel van het beleid dat kan worden gewijzigd.

> [!NOTE]
> Alleen wachtwoorden voor gebruikersaccounts die niet zijn gesynchroniseerd via adreslijstsynchronisatie, kunnen worden geconfigureerd om niet te verlopen. Zie Verbinding maken AD met [Azure AD](/azure/active-directory/connect/active-directory-aadconnect)voor meer informatie over adreslijstsynchronisatie.

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Het verloopbeleid voor een wachtwoord controleren

Zie het referentie artikel [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)voor meer informatie over de opdracht Get-AzureADUser in de AzureAD-module.

Voer een van de volgende opdrachten uit:

- Als u wilt zien of het wachtwoord van één gebruiker is ingesteld op nooit verlopen, voert u de volgende cmdlet uit met behulp van de UPN (bijvoorbeeld *user@contoso.onmicrosoft.com*) of de gebruikers-ID van de gebruiker die u wilt controleren:

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    Voorbeeld:

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- Voer de volgende cmdlet uit om te zien of de instelling **Wachtwoord nooit verloopt** voor alle gebruikers:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Om een rapport te krijgen van alle gebruikers met PasswordNeverExpires in Html op het bureaublad van de huidige gebruiker met naam  **ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- Een rapport kregen van alle gebruikers met PasswordNeverExpires in CSV op het bureaublad van de huidige gebruiker met naam **ReportPasswordNeverExpires.csv**

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

- Voer de volgende cmdlet uit om de wachtwoorden van alle gebruikers in een organisatie in te stellen op nooit verlopen:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Gebruikersaccounts die zijn geconfigureerd met de `-PasswordPolicies DisablePasswordExpiration` parameter worden nog steeds leeftijd op basis van het `pwdLastSet` kenmerk. Als u op basis van het `pwdLastSet` kenmerk de vervaldatum wijzigt in , moeten alle wachtwoorden met een `-PasswordPolicies None` pwdLastSet ouder dan 90 dagen de gebruiker deze wijzigen de volgende keer dat ze zich aanmelden. Deze wijziging kan van invloed zijn op een groot aantal gebruikers.

### <a name="set-a-password-to-expire"></a>Een wachtwoord instellen om te verlopen

Voer een van de volgende opdrachten uit:

- Als u het wachtwoord van één gebruiker zo wilt instellen dat het wachtwoord verloopt, voert u de volgende cmdlet uit met behulp van de UPN of de gebruikers-ID van de gebruiker:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Als u de wachtwoorden van alle gebruikers in de organisatie wilt instellen zodat ze verlopen, gebruikt u de volgende cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>Verwante onderwerpen

[Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen](../add-users/let-users-reset-passwords.md) (artikel)

[Wachtwoorden opnieuw instellen](../add-users/reset-passwords.md) (artikel)