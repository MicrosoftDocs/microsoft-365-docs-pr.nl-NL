---
title: Beveiligingsaanbevelingen voor prioriteits accounts in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie lezen over de verhoging van de beveiligingsinstellingen en rapporten, waarschuwingen en onderzoek voor prioriteits accounts in hun Microsoft 365-organisaties.
ms.openlocfilehash: aee238d2fb58d2772881d8d77f98959906943290
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668153"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Beveiligingsaanbevelingen voor prioriteits accounts in Microsoft 365

Wat moet u doen als u een urgent bericht ontvangt van een directeur in uw organisatie waarmee u iets hoeft te doen? Wilt u doen? De meeste personen zouden aan de aanvraag voldoen.

Voor hackers kunnen een reguliere phishing-aanval die een willekeurig net afneemt, de gegevens van willekeurige of onbekende gebruikers inefficiënten. Met een _spear phishing_ -of _Whaling_ -aanval kunnen ook gebruikers die op hun doelgericht zijn op de kracht van de macht of de overheid, veel meer doen. Als deze prioriteits accounts worden aangetast, kan de aanvaller toegang krijgen tot accounts met beheerders, financiële producten, producten of zelfs de fysieke toegangsmogelijkheden binnen de organisatie.

Microsoft 365 en Microsoft Defender voor Office 365 bevatten veel verschillende functies waarmee u extra beveiligingslagen voor uw prioriteits accounts kunt bieden. De beschikbare functies en de manier waarop ze worden gebruikt, worden beschreven in dit artikel.

## <a name="increase-sign-in-security-for-priority-accounts"></a>Aanmeld beveiliging voor prioriteits accounts vergroten

Voor prioriteits accounts is een betere aanmeld beveiliging vereist. U kunt de aanmeldingsbeveiliging vergroten door multi-factor Authentication (MFA) te vereisen en oudere verificatieprotocollen uit te schakelen.

Zie [stap 1 voor instructies. De aanmeldingsbeveiliging voor externe werknemers vergroten met MFA](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in). Dit artikel bevat informatie over externe werknemers, en ook van toepassing op prioritaire gebruikers.

**Opmerkingen**:

- Basisverificatie wordt afgeschaft in Exchange Online voor Exchange Web Services (EWS), Exchange ActiveSync, POP3, IMAP4 en Remote PowerShell. Zie dit [blogbericht](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)voor meer informatie.

- U kunt [authenticatiebeleid](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) en [regels voor client toegang](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) in Exchange Online gebruiken om basisverificatie en verouderings protocollen zoals POP3, IMAP4 en geverifieerde SMTP te blokkeren.

- U kunt POP3-en IMAP4-toegang uitschakelen voor afzonderlijke postvakken. U kunt geverifieerde SMTP uitschakelen op organisatieniveau en de optie inschakelen voor bepaalde postvakken waarvoor deze nog niet is vereist. Zie de volgende onderwerpen voor instructies:
  - [POP3-of IMAP4-toegang voor een gebruiker in-of uitschakelen](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [Geverifieerde clientverificatie in-of uitschakelen (SMTP AUTH)](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>Strikte vooraf ingestelde beveiligingsbeleidsregels gebruiken voor prioriteits accounts

Prioritaire gebruikers vereisen een stringentere actie voor de verschillende beveiligingsinstellingen die beschikbaar zijn in Exchange Online Protection (EOP) en Defender voor Office 365.

In plaats van berichten die als spam zijn geclassificeerd naar de map Ongewenste E-mail, kunt u bijvoorbeeld de volgende berichten in plaats daarvan in de juiste volgorde plaatsen.

U kunt deze strikte aanpak voor prioriteit accounts implementeren met behulp van het strikte profiel in vooraf ingestelde beveiligingsbeleidsregels.

Vooraf ingestelde beveiligingsbeleidsregels vormen een gemakkelijke en centrale locatie voor het toepassen van de aanbevolen strikte beleidsinstellingen voor alle beveiligingen in EOP en Defender voor Office 365. Zie voor meer informatie [vooraf gedefinieerde beveiligingsbeleidsregels in EOP en Microsoft Defender voor Office 365](preset-security-policies.md).

Zie [Aanbevolen instellingen voor EOP en Microsoft Defender for Office 365-beveiliging](recommended-settings-for-eop-and-office365-atp.md)voor informatie over de manier waarop de strikte beleidsinstellingen afwijken van de standaardinstellingen en de standaardbeleidsinstellingen.

## <a name="user-tags"></a>Gebruikers Tags

Gebruikers Tags in Microsoft Defender for Office 365 plan 2 (als onderdeel van Microsoft 365 E5 of een aanvullend abonnement) is een manier om bepaalde gebruikers of groepen gebruikers snel op te sporen en in te delen in rapporten en incidenten onderzoek.

**Prioriteits accounts** is een type ingebouwde gebruikerscode (een _systeemcode_ genoemd) die u kunt gebruiken om incidenten en waarschuwingen voor prioritaire accounts te identificeren. Zie [prioriteit accounts beheren en bijhouden](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)voor meer informatie over **prioriteits accounts**.

U kunt ook aangepaste tags maken waarmee u uw prioriteits accounts kunt identificeren en classificeren. Zie voor meer informatie [gebruikers Tags](user-tags.md). Houd er rekening mee dat u **prioriteit accounts** (systeem Tags) in dezelfde interface kunt beheren als aangepaste gebruikers Tags.

## <a name="priority-accounts-in-reports-and-investigations-in-microsoft-365"></a>Prioriteits accounts in rapporten en onderzoeken in Microsoft 365

****

|Functie|Beschrijving|
|---|---|
|Waarschuwingen|De gebruikers Tags van dit soort gebruikers zijn weergegeven en beschikbaar als filters op de pagina **waarschuwingen weergeven** in het Beveiligingscentrum beveiligings &. Zie [waarschuwingen weergeven](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts)voor meer informatie.|
|Bedreigingsverkenner <p> Detecties in realtime|In de **Threat Explorer** (Microsoft Defender for Office 365-abonnement 2) of **realtime detecties** (Microsoft Defender voor Office 365 abonnement 1) zijn gebruikers Tags zichtbaar in de weergave e-mail raster en de flyout e-mail details. Gebruikers Tags zijn ook beschikbaar als een filter bare eigenschap. Zie voor meer informatie  [Tags in de Threat Explorer](threat-explorer.md#tags-in-threat-explorer).|
|Campagneweergaven|Gebruikers Tags zijn een van de vele beschikbare eigenschappen in campagne weergaven in Microsoft Defender voor Office 365, abonnement 2. Zie voor meer informatie [campagne weergaven](campaigns.md).|
|Statusrapport bedreigingsbeveiliging|In vrijwel alle weergaven en detail tabellen in het **rapport status van bedreigingsbeveiliging** kunt u de resultaten filteren op **prioriteits accounts**. Zie [statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)voor meer informatie.|
|E-mail problemen voor het rapport met prioriteit accounts|In het rapport **e-mail problemen met prioriteit-accounts** in het Exchange-Beheercentrum vindt u informatie over niet-bezorgde en vertraagde berichten voor **prioritaire accounts**. Zie [e-mail problemen voor het rapport met prioriteits accounts](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)voor meer informatie.|
|

## <a name="see-also"></a>Zie ook

[Account beveiliging voor een aankondiging van de prioriteit in Microsoft Defender voor Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
