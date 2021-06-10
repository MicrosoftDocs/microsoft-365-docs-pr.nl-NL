---
title: Sessie time-outs voor Microsoft 365
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
ms.collection:
- M365-security-compliance
description: Lees hoe sessie-time-outs worden gebruikt om de beveiliging en de toegankelijkheid in Microsoft 365 client-apps te balanceren.
ms.openlocfilehash: b85ed8a45727e8a8eed2537fa2233125cd05ece7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924914"
---
# <a name="session-timeouts-for-microsoft-365"></a>Sessie time-outs voor Microsoft 365

Sessielevens zijn een belangrijk onderdeel van verificatie voor Microsoft 365 en vormen een belangrijk onderdeel in het balanceren van beveiliging en het aantal keren dat gebruikers worden gevraagd om hun referenties.

## <a name="session-times-for-microsoft-365-services"></a>Sessietijden voor Microsoft 365 services

Wanneer gebruikers zich verifiëren in een van de Microsoft 365 web-apps of mobiele apps, wordt er een sessie tot stand gebracht. Gedurende de duur van de sessie hoeven gebruikers zich niet opnieuw te verifiëren. Sessies kunnen verlopen wanneer gebruikers inactief zijn, wanneer ze de browser of het tabblad sluiten of wanneer hun verificatie-token verloopt om andere redenen, zoals wanneer hun wachtwoord opnieuw is ingesteld. De Microsoft 365 services hebben verschillende sessie-time-outs die overeenkomen met het gebruikelijke gebruik van elke service.

De volgende tabel bevat de levensduur van de sessie voor Microsoft 365 services:

| Microsoft 365-service | Sessie time-out |
|:-----|:-----|
|Microsoft 365-beheercentrum  <br/> |U wordt gevraagd om elke 8 uur referenties op te geven voor het beheercentrum.  <br/> |
|SharePoint Online  <br/> |5 dagen inactiviteit zolang de gebruikers Mij aangemeld **houden kiezen.** Als de gebruiker opnieuw toegang SharePoint Online nadat 24 of meer uur is verstreken na de vorige aanmelding, wordt de time-outwaarde opnieuw ingesteld op 5 dagen.  <br/> |
|Outlook Web App  <br/> |6 uur.  <br/> U kunt deze waarde wijzigen met de _parameter ActivityBasedAuthenticationTimeoutInterval_ in de cmdlet [Set-OrganizationConfig.](/powershell/module/exchange/set-organizationconfig)  <br/> |
|Microsoft Azure Active Directory  <br/> (Gebruikt door Office en Microsoft 365 toepassingen in Windows clients met moderne verificatie ingeschakeld)  <br/> | Moderne verificatie gebruikt toegangstokens en vernieuwingstokens om gebruikers toegang te verlenen tot Microsoft 365 bronnen met Azure Active Directory. Een toegangs token is een JSON Web Token die wordt geleverd na een geslaagde verificatie en die 1 uur geldig is. U kunt ook een vernieuwings-token met een langere levensduur krijgen. Wanneer toegangstokens verlopen, Office clients een geldig vernieuwingstoken gebruiken om een nieuw toegangstoken te verkrijgen. Deze exchange slaagt als de eerste verificatie van de gebruiker nog steeds geldig is.  <br/>  Vernieuwingstokens zijn 90 dagen geldig en bij doorlopend gebruik kunnen ze geldig zijn totdat ze worden ingetrokken.  <br/>  Vernieuwingstokens kunnen ongeldig worden gemaakt door verschillende gebeurtenissen, zoals:  <br/>  Het wachtwoord van de gebruiker is gewijzigd sinds het vernieuwings-token is uitgegeven.  <br/>  Een beheerder kan beleidsregels voor voorwaardelijke toegang toepassen die de toegang beperken tot de resource die de gebruiker probeert te openen.  <br/> |
|SharePoint en OneDrive mobiele apps voor Android, iOS en Windows 10  <br/> |De standaardlevensduur voor het toegangs token is 1 uur. De standaard max inactieve tijd van het vernieuwings-token is 90 dagen.  <br/> [Meer informatie over tokens en het configureren van tokenlevens](/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> Als u het vernieuwings-token wilt intrekken, kunt u het wachtwoord van de gebruiker Microsoft 365 opnieuw instellen  <br/> |
|Yammer met Microsoft 365 Sign-In  <br/> |Levensduur van de browser. Als gebruikers de browser sluiten en toegang Yammer in een nieuwe browser, wordt Yammer opnieuw geverifieerd met Microsoft 365. Als gebruikers browsers van derden gebruiken die cookies in de cache plaatsen, hoeven ze zich mogelijk niet opnieuw te verifiëren wanneer ze de browser opnieuw openen.  <br/> > [!NOTE]> Dit is alleen geldig voor netwerken met Microsoft 365 Sign-In voor Yammer.           |