---
title: Sessietime-outs voor Microsoft 365
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
description: Meer informatie over hoe sessietime-outs worden gebruikt om de beveiliging en toegankelijkheid van gebruikers in Microsoft 365-clienttoepassingen te salderen.
ms.openlocfilehash: 2c0a7c2633715ac23942a22858b41e83a091c46a
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769290"
---
# <a name="session-timeouts-for-microsoft-365"></a>Sessietime-outs voor Microsoft 365

De levensduur van een sessie is een belangrijk onderdeel van de verificatie voor Microsoft 365 en is een belangrijk onderdeel van de bescherming van de beveiliging en het aantal keren dat gebruikers op hun referenties worden gevraagd.

## <a name="session-times-for-microsoft-365-services"></a>Sessie tijden voor Microsoft 365-Services

Wanneer gebruikers in een van de Microsoft 365-web-apps of mobiele apps verifiëren, wordt een sessie tot stand gebracht. Voor de duur van de sessie hoeven gebruikers niet opnieuw te verifiëren. Sessies kunnen verlopen wanneer gebruikers inactief zijn, wanneer ze de browser of tab sluiten, of wanneer hun verificatietoken verloopt om andere redenen, bijvoorbeeld wanneer het wachtwoord opnieuw is ingesteld. De services van Microsoft 365 hebben verschillende sessietime-outs, zodat ze corresponderen met het typische gebruik van elke service.

De volgende tabel bevat een overzicht van de levensduur van de sessies voor Microsoft 365-Services:

| Microsoft 365-service | Sessietime-out |
|:-----|:-----|
|Microsoft 365-beheercentrum  <br/> |U wordt om de 8 uur gevraagd referenties op te geven voor het Beheercentrum.  <br/> |
|SharePoint Online  <br/> |5 dagen inactiviteit, mits de gebruikers **ingelogd blijven** . Als de gebruiker SharePoint Online opnieuw toegang tot SharePoint Online heeft na 24 of meer uur na voltooiing van de vorige aanmelding, wordt de time-outwaarde teruggezet op 5 dagen.  <br/> |
|Outlook Web App  <br/> |6 uur.  <br/> U kunt deze waarde wijzigen met behulp van de  _ActivityBasedAuthenticationTimeoutInterval_ -parameter in de cmdlet [set-OrganizationConfig](https://go.microsoft.com/fwlink/p/?LinkId=615378) .  <br/> |
|Microsoft Azure Active Directory  <br/> (Gebruikt door Office-en Microsoft 365-toepassingen in Windows-clients waarbij moderne verificatie is ingeschakeld)  <br/> | Moderne verificatie maakt gebruik van toegangstokens en vernieuwingstokens om gebruikers toegang tot Microsoft 365-bronnen te verlenen via Azure Active Directory. Een toegangstoken is een JSON Web token, opgegeven na verificatie met succes en geldig voor 1 uur. Een vernieuwingstoken met een langere levensduur wordt ook geleverd. Wanneer toegangstokens verlopen, gebruiken Office-clients een geldig vernieuwingstoken om een nieuw toegangstoken te verkrijgen. Deze Exchange slaagt als de initiële verificatie van de gebruiker nog geldig is.  <br/>  Vernieuwingstokens zijn geldig voor 90 dagen en met doorlopend gebruik kunnen ze geldig zijn totdat ze worden ingetrokken.  <br/>  Vernieuwingstokens kunnen ongeldig worden gemaakt door verschillende gebeurtenissen, zoals:  <br/>  Het gebruikerswachtwoord is gewijzigd sinds de vernieuwingstoken is uitgegeven.  <br/>  Een beheerder kan voorwaardelijk toegangsbeleid toepassen dat de toegang kan beperken tot de bron waartoe de gebruiker toegang wil hebben.  <br/> |
|Mobiele apps van SharePoint en OneDrive voor Android, iOS en Windows 10  <br/> |De standaardlevensduur voor het toegangstoken is 1 uur. De standaardinstelling voor het vernieuwingstoken van de periode is 90 dagen.  <br/> [Meer informatie over tokens en het configureren van token levensduur](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> Als u de vernieuwingstoken wilt intrekken, kunt u het Microsoft 365-wachtwoord van de gebruiker opnieuw instellen  <br/> |
|Yammer met Microsoft 365 Sign-In  <br/> |Levensduur van de browser. Als gebruikers de browser sluiten en Yammer gebruiken in een nieuwe browser, wordt deze met Yammer opnieuw geverifieerd met Microsoft 365. Als gebruikers gebruikmaken van browsers van derden die cache cookies gebruiken, hoeven ze zich mogelijk niet opnieuw te verifiëren wanneer ze de browser opnieuw openen.  <br/> > [!NOTE]> dit geldt alleen voor netwerken met Microsoft 365 Sign-In voor Yammer.           |

