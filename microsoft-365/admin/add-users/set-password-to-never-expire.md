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
description: Meer informatie over het instellen van een aantal afzonderlijke gebruikerswachtwoorden om nooit te verlopen met Windows PowerShell.
ms.openlocfilehash: 564ea3338fcb11d699d385a40c9594f34964edf7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903638"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt

In dit artikel wordt uitgelegd hoe u een wachtwoord kunt instellen voor een individuele gebruiker die niet verloopt. U moet deze stappen met PowerShell voltooien.

## <a name="before-you-begin"></a>Voordat u begint

Dit artikel is bedoeld voor personen die het wachtwoordverloopbeleid voor een bedrijf, school of non-profitorganisatie opstellen. Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount. [Wat is een beheerdersaccount?](../admin-overview/admin-overview.md). 

U moet een globale [beheerder of wachtwoordbeheerder zijn om](about-admin-roles.md) deze stappen uit te voeren.

Een globale beheerder voor een Microsoft-cloudservice kan [de Azure Active Directory PowerShell voor Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) gebruiken om wachtwoorden in te stellen die niet voor specifieke gebruikers verlopen. U kunt [azureAD-cmdlets](/powershell/module/Azuread) ook gebruiken om de configuratie die nooit verloopt te verwijderen of om te zien welke gebruikerswachtwoorden zijn ingesteld op nooit verlopen.

Deze handleiding is van toepassing op andere providers, zoals Intune en Microsoft 365, die ook afhankelijk zijn van Azure AD voor identiteits- en adreslijstservices. Wachtwoordverloop is het enige deel van het beleid dat kan worden gewijzigd.

> [!NOTE]
> Alleen wachtwoorden voor gebruikersaccounts die niet worden gesynchroniseerd via adreslijstsynchronisatie, kunnen zo worden geconfigureerd dat ze niet verlopen. Zie AD verbinden met Azure [AD](/azure/active-directory/connect/active-directory-aadconnect)voor meer informatie over adreslijstsynchronisatie.

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Het verloopbeleid controleren op een wachtwoord

Zie het naslagartikel [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)voor meer informatie over Get-AzureADUser opdracht in de AzureAD-module.

Voer een van de volgende opdrachten uit:

- Als u wilt zien of het wachtwoord van één gebruiker nooit verloopt, moet u de volgende cmdlet uitvoeren met behulp van de UPN (bijvoorbeeld *user@contoso.onmicrosoft.com)* of de gebruikers-id van de gebruiker die u wilt controleren:

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

- Voer de **volgende** cmdlet uit om te zien dat de instelling Wachtwoord nooit verloopt voor alle gebruikers:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Een rapport downloaden van alle gebruikers met PasswordNeverExpires in Html op het bureaublad van de huidige gebruiker met  **ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- Een rapport van alle gebruikers met PasswordNeverExpires in CSV op het bureaublad van de huidige gebruiker met naam **enReportPasswordNeverExpires.csv**

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

- Voer de volgende cmdlet uit als u wilt instellen dat de wachtwoorden van alle gebruikers in een organisatie nooit verlopen:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Gebruikersaccounts die zijn geconfigureerd met `-PasswordPolicies DisablePasswordExpiration` de parameter die nog steeds ouder wordt op basis van het `pwdLastSet` kenmerk. Als u op basis van het kenmerk de vervaldatum wijzigt in , moeten alle wachtwoorden met een pwdLastSet ouder dan 90 dagen de gebruiker wijzigen wanneer ze zich de volgende keer `pwdLastSet` `-PasswordPolicies None` aanmelden. Deze wijziging kan van invloed zijn op een groot aantal gebruikers.

### <a name="set-a-password-to-expire"></a>Een wachtwoord instellen dat moet verlopen

Voer een van de volgende opdrachten uit:

- Als u het wachtwoord van één gebruiker zo wilt instellen dat het wachtwoord verloopt, moet u de volgende cmdlet uitvoeren met behulp van de UPN of de gebruikers-id van de gebruiker:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Als u de wachtwoorden van alle gebruikers in de organisatie zo wilt instellen dat ze verlopen, gebruikt u de volgende cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>Verwante onderwerpen

[Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen](../add-users/let-users-reset-passwords.md)

[Wachtwoorden opnieuw instellen](../add-users/reset-passwords.md)