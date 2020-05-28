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
# <a name="set-an-individual-users-password-to-never-expire"></a>Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt

## <a name="set-the-password-expiration-policy-for-your-organization"></a>Het wachtwoordverloopbeleid voor uw organisatie instellen:

1. Ga in het beheercentrum **Settings** naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Instellingen instellingen.</a>
2. Selecteer beveiliging **& Privacy**boven aan de pagina Instellingen .
3. Selecteer **Verloopbeleid wachtwoorden**. 
4. Als wachtwoorden nooit verlopen, klikt u op het selectievakje naast **Gebruikerswachtwoorden instellen om na een aantal dagen te verlopen.** U krijgt de optie om het aantal dagen op te geven totdat wachtwoorden verlopen.

## <a name="set-the-password-expiration-policy-for-individual-users"></a>Het wachtwoordverloopbeleid instellen voor individuele gebruikers

Een globale beheerder voor een Microsoft-cloudservice kan de [Azure Active Directory PowerShell voor Grafiek](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) gebruiken om in te stellen dat wachtwoorden niet verlopen voor specifieke gebruikers. U [azuread-cmdlets](https://docs.microsoft.com/powershell/module/Azuread) ook gebruiken om de nooit verlopen configuratie te verwijderen of om te zien welke gebruikerswachtwoorden nooit verlopen.

Deze handleiding is van toepassing op andere providers, zoals Intune en Microsoft 365, die ook afhankelijk zijn van Azure AD voor identiteits- en directoryservices. Het verlopen van wachtwoorden is het enige onderdeel van het beleid dat kan worden gewijzigd.

Zie [Azure Active Directory PowerShell voor Grafiek voor](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)meer informatie over Azure AD PowerShell voor Grafiek.

> [!NOTE]
> Alleen wachtwoorden voor gebruikersaccounts die niet zijn gesynchroniseerd via adreslijstsynchronisatie, kunnen worden geconfigureerd om niet te verlopen. Zie AD verbinden met Azure [AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)voor meer informatie over adreslijstsynchronisatie.

### <a name="how-to-check-the-expiration-policy-for-a-password"></a>Het verloopbeleid controleren op een wachtwoord

Zie het referentieartikel [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)voor meer informatie over de opdracht Get-AzureADUser in de AzureAD-module.

Voer een van de volgende opdrachten uit:

- Als u wilt zien of het wachtwoord van één gebruiker nooit verloopt, voert u de volgende cmdlet uit met behulp van de UPN (bijvoorbeeld *user@contoso.onmicrosoft.com)* of de gebruikers-id van de gebruiker die u wilt controleren:

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

- Voer de volgende cmdlet uit om de instelling Wachtwoord nooit voor alle gebruikers **te bekijken:**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Een rapport van alle gebruikers met PasswordNeverExpires in Html op het bureaublad van de huidige gebruiker met naam **ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- Een rapport van alle gebruikers met PasswordNeverExpires in CSV op het bureaublad van de huidige gebruiker met naam **ReportPasswordNeverExpires.csv**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a>Een wachtwoord instellen om te verlopen

Voer een van de volgende opdrachten uit:

- Als u het wachtwoord van één gebruiker wilt instellen zodat het wachtwoord verloopt, voert u de volgende cmdlet uit met de UPN of de gebruikers-id van de gebruiker:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Als u de wachtwoorden van alle gebruikers in de organisatie zo wilt instellen dat ze verlopen, gebruikt u de volgende cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a>Een wachtwoord instellen dat nooit verloopt

Voer een van de volgende opdrachten uit:

- Als u wilt instellen dat het wachtwoord van één gebruiker nooit verloopt, voert u de volgende cmdlet uit met de UPN of de gebruikers-id van de gebruiker:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- Voer de volgende cmdlet uit om de wachtwoorden van alle gebruikers in een organisatie nooit te laten verlopen:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Wachtwoorden ingesteld `-PasswordPolicies DisablePasswordExpiration` op leeftijd op basis van het `pwdLastSet` kenmerk. Als u de gebruikerswachtwoorden nooit laat verlopen en vervolgens meer dan 90 dagen voorbij gaat, verlopen de wachtwoorden. Op basis van het `pwdLastSet` kenmerk moeten alle wachtwoorden die ouder zijn dan 90 dagen, als u de vervaldatum wijzigt, deze de volgende keer dat `-PasswordPolicies None` hij zich `pwdLastSet` aanmeldt, wijzigen. Deze wijziging kan gevolgen hebben voor een groot aantal gebruikers.
