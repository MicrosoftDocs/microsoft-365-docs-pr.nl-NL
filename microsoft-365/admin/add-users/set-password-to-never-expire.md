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
description: Meer informatie over het instellen van wachtwoorden voor afzonderlijke gebruikers voor nooit verloopt, met behulp van Windows PowerShell.
ms.openlocfilehash: f85eb2d3aaf5b19779ea8f293e2cbdc28c1535aa
ms.sourcegitcommit: 5c16d270c7651c2080a5043d273d979a6fcc75c6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804206"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Het wachtwoord van een gebruiker zo instellen dat het nooit verloopt

## <a name="set-the-password-expiration-policy-for-your-organization"></a>Het wachtwoordverloopbeleid voor uw organisatie instellen:

1. Ga in het Beheercentrum naar de pagina **instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">instellingen</a> .
2. Selecteer boven aan de pagina instellingen de optie **beveiliging & privacy**.
3. Selecteer **Verloopbeleid wachtwoorden**. 
4. Als het wachtwoord zo is ingesteld dat het nooit verloopt, klikt u op het selectievakje naast **Gebruikerswachtwoorden instellen op verloopt na een aantal dagen**. U krijgt de optie om het aantal dagen op te geven dat wachtwoorden verlopen.

## <a name="set-the-password-expiration-policy-for-individual-users"></a>Het wachtwoord verloopbeleid voor afzonderlijke gebruikers instellen

Een globale beheerder van een Microsoft-cloudservice kan de [Azure Active Directory PowerShell voor Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) gebruiken om wachtwoorden zodanig in te stellen dat deze niet verlopen voor specifieke gebruikers. U kunt ook [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) -cmdlets gebruiken om de configuratie nooit-expires te verwijderen of om te zien welke gebruikerswachtwoorden zo zijn ingesteld dat nooit verloopt.

Deze handleiding is van toepassing op andere providers, zoals intune en Microsoft 365, die ook gebruikmaken van Azure AD voor identiteit en Directory Services. Het verlopen van wachtwoorden is het enige onderdeel van het beleid dat kan worden gewijzigd.

Zie voor meer informatie over Azure AD PowerShell voor Graph [Azure Active Directory PowerShell voor Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).

> [!NOTE]
> Alleen wachtwoorden voor gebruikersaccounts die niet zijn gesynchroniseerd via adreslijstsynchronisatie, kunnen zo worden geconfigureerd dat deze niet verlopen. Zie voor meer informatie over adreslijstsynchronisatie de [koppeling AD verbinden met Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

### <a name="how-to-check-the-expiration-policy-for-a-password"></a>Het verloopbeleid voor een wachtwoord controleren

Zie voor meer informatie over de opdracht Get-AzureADUser in de AzureAD-module de referentie artikel [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).

Voer een van de volgende opdrachten uit:

- Als u wilt controleren of het wachtwoord van een gebruiker zo is ingesteld dat het nooit verloopt, voert u de volgende cmdlet uit met behulp van de UPN (zoals *user@contoso.onmicrosoft.com*) of de gebruikers-id van de gebruiker die u wilt controleren:

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

- Voer de volgende cmdlet uit om de instelling **wachtwoord nooit verloopt** voor alle gebruikers weer te geven:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Als u een rapport wilt weergeven van alle gebruikers met PasswordNeverExpires in HTML op de desktopcomputer van de huidige gebruiker waarvan de naam  **ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- Als u een rapport wilt weergeven van alle gebruikers met PasswordNeverExpires in CSV op het bureaublad van de huidige gebruiker met naam **ReportPasswordNeverExpires.csv**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a>Instellen dat een wachtwoord verloopt

Voer een van de volgende opdrachten uit:

- Als u het wachtwoord van een gebruiker zo wilt instellen dat het wachtwoord verloopt, voert u de volgende cmdlet uit met behulp van de UPN of de gebruikers-ID van de gebruiker:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Als u de wachtwoorden van alle gebruikers in de organisatie wilt instellen zodat ze verlopen, gebruikt u de volgende cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a>Instellen dat een wachtwoord nooit verloopt

Voer een van de volgende opdrachten uit:

- Als u wilt instellen dat het wachtwoord van één gebruiker nooit verloopt, voert u de volgende cmdlet uit waarbij u de UPN of de gebruikers-ID van de gebruiker opgeeft:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- Voer de volgende cmdlet uit om het wachtwoord in te stellen, zodat alle gebruikers in een organisatie nooit verlopen:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> Gebruikersaccounts die zijn geconfigureerd met de `-PasswordPolicies DisablePasswordExpiration` parameter die nog ouder is gemaakt op basis van het kenmerk van het `pwdLastSet` gebruikersaccount. Als u bijvoorbeeld het wachtwoord van een gebruiker zo instelt dat het nooit verloopt en 90 of meer dagen gaat, verloopt het wachtwoord nog steeds. Op basis van het kenmerk van het `pwdLastSet` gebruikersaccount voor gebruikersaccounts die met de `-PasswordPolicies None` parameter zijn geconfigureerd, `pwdLastSet` moet de gebruiker de volgende keer dat u zich aanmeldt, gebruikersaccounts met een ouder dan 90 dagen wijzigen. Deze wijziging kan van invloed zijn op een groot aantal gebruikers.
