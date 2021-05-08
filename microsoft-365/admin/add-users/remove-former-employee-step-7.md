---
title: Stap 7 - Het gebruikersaccount van een voormalige werknemer verwijderen
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Volg deze stappen om het gebruikersaccount van een voormalige werknemer te verwijderen.
ms.openlocfilehash: 0afa9b112919d2668d7553ac5bcf08e664bc1749
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244193"
---
# <a name="step-7---delete-a-former-employees-user-account"></a>Stap 7 - Het gebruikersaccount van een voormalige werknemer verwijderen

Nadat u de gegevens van de voormalige werknemer hebt opgeslagen en beschikbaar hebt gemaakt, kunt u het account van de werknemer verwijderen.

> [!IMPORTANT]
> Verwijder het account niet als u doorsturen van e-mail hebt ingesteld of het account hebt omgezet naar een gedeeld postvak. Het account is nodig om het gedeelde postvak of het doorsturen van e-mail te kunnen blijven gebruiken.

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
2. Selecteer de naam van de werknemer die u wilt verwijderen.
3. Selecteer onder de naam van de gebruiker de optie **Gebruiker verwijderen.** Kies de opties die u voor deze gebruiker wilt gebruiken en selecteer **vervolgens Gebruiker verwijderen.** Als u al een andere gebruiker toegang hebt gegeven tot de e-mail en OneDrive van deze gebruiker, hoeft u dit hier niet opnieuw te doen.

Wanneer u een gebruiker verwijdert, wordt het account inactief gedurende ongeveer 30 dagen. Tot die tijd kunt u het account herstellen. Daarna worden de gegevens permanent verwijderd.
  
## <a name="does-your-organization-use-active-directory"></a>Maakt uw organisatie gebruik van Active Directory?

Als uw organisatie gebruikersaccounts synchroniseert Microsoft 365 vanuit een lokale Active Directory-omgeving, moet u deze gebruikersaccounts in uw lokale Active Directory-service verwijderen en herstellen. U kunt ze niet verwijderen of herstellen via Office 365.

Zie Een gebruikersaccount [verwijderen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))voor meer informatie over het verwijderen en herstellen van gebruikersaccounts in Active Directory.
  
Zie de cmdlet Remove-MsolUser PowerShell Azure Active Directory u de powershell-cmdlet [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) gebruikt.
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Wat u moet weten over het beëindigen van een sessie van een werknemer

Zo ontzegt u een werknemer de toegang tot e-mail (Exchange).
  
|||
|:-----|:-----|
|**Wat u kunt doen** <br/> |**Hoe u dat kunt doen** <br/> |
|Een sessie beëindigen (zoals voor de webversie van Outlook, Outlook, Exchange Active Sync, enzovoort) en een nieuwe sessie geforceerd openen  <br/> |Wachtwoord opnieuw instellen  <br/> |
|Een sessie beëindigen en toegang blokkeren voor toekomstige sessies (voor alle protocollen)  <br/> |Schakel het account uit. Bijvoorbeeld(in het Exchange beheercentrum of met PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|De sessie voor een bepaald protocol (zoals ActiveSync) beëindigen  <br/> |Schakel het protocol uit. Bijvoorbeeld(in het Exchange beheercentrum of met PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

De bovenstaande bewerkingen kunnen op drie plaatsen worden uitgevoerd:
  
|||
|:-----|:-----|
|**Als u de sessie hier beëindigt** <br/> |**Hoe lang dit duurt** <br/> |
|In het Exchange-beheercentrum of via PowerShell  <br/> |Verwachte vertraging is korter dan 30 minuten  <br/> |
|In het Azure Active Directory-beheercentrum  <br/> |Verwachte vertraging is 60 minuten  <br/> |
|In een lokale omgeving  <br/> |Verwachte vertraging is 3 uur of langer  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a>Zo krijgt u de snelste reactie voor het beëindigen van een account

 **Snelst**: maak gebruik van het Exchange-beheercentrum (gebruik PowerShell) of van het Azure Active Directory-beheercentrum. In een on-premises omgeving kan het enkele uren duren om de wijziging via DirSync te synchroniseren.
  
 **Snelst voor een gebruiker met aanwezigheid on-premises en in het Exchange-Datacenter**: Beëindig de sessie met behulp van het Azure Active Directory-beheercentrum/Exchange-beheercentrum, en breng de wijziging OOK aan in de on-premises omgeving. Anders worden de wijzigingen in het Azure Active Directory-beheercentrum/Exchange-beheercentrum overschreven door DirSync.
  
## <a name="related-articles"></a>Verwante artikelen

[Een gebruiker herstellen](restore-user.md)
