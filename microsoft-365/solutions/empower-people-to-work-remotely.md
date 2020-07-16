---
title: Externe werknemers mogelijkheden bieden met Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Configureer de beveiligings- en service-infrastructuur waardoor uw werknemers altijd en overal op afstand kunnen werken.
ms.openlocfilehash: 763c8e745eb54897c1df88ecb5a9064987ed5a13
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560460"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>Externe werknemers mogelijkheden bieden met Microsoft 365

De werknemers van uw bedrijf moeten mogelijk vanuit huis veilige toegang tot de on-premises en cloudgegevens, -hulpprogramma's en -informatiebronnen van uw organisatie kunnen krijgen. Door werknemers naadloos en veilig op afstand te laten werken, kunnen veel organisaties:

- Besparen op kantoorruimte.
- Werknemers aannemen en behouden die niet bereid zijn te verhuizen.
- De reistijd van werknemers verminderen, waardoor er meer tijd overblijft om productief te zijn en stress verlagende activiteiten uit te voeren buiten werktijd.

Onder extern werken, ook wel telewerken wordt genoemd, valt het volgende:

- Werknemers die af en toe niet op kantoor zijn vanwege conferenties of vergaderingen met klanten.
- Bepaalde werknemers die fulltime extern werken.
- Een volledig externe organisatie die geen kantoor heeft en waarvan alle werknemers extern werken.

Externe werknemers moeten overal ter wereld en op elk gewenst moment toegang hebben tot:

- Resources van de organisatie, zoals de resources van on-premises toepassingsdatacenters.
- Cloudservices en -gegevens in uw Microsoft 365-abonnement, zoals Teams, Exchange Online, SharePoint en OneDrive.

Voor een naadloze aanmelding moeten de gebruikersaccounts van Active Directory Domain Services (AD DS) worden gesynchroniseerd met Azure Active Directory (Azure AD). Als u uw Windows 10-apparaten wilt beveiligen, moeten ze worden ingeschreven in Intune. Dit is een algemeen overzicht van de infrastructuur.

![De basisinfrastructuur voor externe werknemers met Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)


Ter ondersteuning van externe werknemers, bijvoorbeeld in reactie op de COVID-19-crisis, is er een combinatie van functies beschikbaar in Microsoft 365 waarmee ze beter kunnen samenwerken, zoals:

- Onlinevergaderingen en chatsessies.
- Gedeelde werkruimten voor cloudopslag met wereldwijde toegankelijkheid en realtime samenwerking.
- Gedeelde taken en werkstromen om het werk te verdelen en taken uit te voeren.

Voor een krachtige beveiliging bevat Microsoft 365 het volgende:

- Afgedwongen verificatievereisten, aanmeldingen met een hoog risico detecteren en hierop reageren en geselecteerde apps en niet-compatibele apparaten blokkeren.
- Versleutelde verbindingen en digitale hulpmiddelen in de cloud.
- Machtigingen om te definiëren wie wat mag doen met bestanden.
- Uitgebreide beveiligingsfuncties om Windows 10-apparaten te beveiligen.

Als u aan deze criteria voor externe werknemers wilt voldoen, gebruikt u de volgende functies van Microsoft 365.

| Functie | Beschrijving | Licenties |
|:-------|:-----|:-------|
| Afgedwongen door MFA en met standaardbeveiligingsinstellingen   | Voorkom gecompromitteerde identiteiten en apparaten met een tweede vorm van verificatie voor aanmeldingen. Als standaardinstelling voor de beveiliging is MFA vereist voor alle gebruikersaccounts.   | Microsoft 365 E3 en E5 |
| Afgedwongen door MFA en met voorwaardelijke toegang| Gebruik beleid voor voorwaardelijke toegang om MFA te vereisen op basis van de eigenschappen van de aanmelding.    | Microsoft 365 E3 en E5 | 
| Afgedwongen door MFA en met voorwaardelijke toegang op basis van risico   | Gebruik Azure Advanced Threat Protection om MFA te vereisen op basis van het risico van de gebruikersaanmelding. | Microsoft 365 E5 of E3 met Azure AD Premium P2-licenties | 
| Selfservice voor wachtwoordherstel (SSPR)    | Sta toe dat gebruikers hun wachtwoorden of accounts opnieuw kunnen instellen of ontgrendelen.  | Microsoft 365 E3 en E5 |
| Azure AD-toepassingsproxy    | Bied beveiligde externe toegang bieden voor webtoepassingen die worden gehost op intranetservers.   | Hiervoor is een afzonderlijk betaald Azure-abonnement vereist |
| Azure-punt-naar-site-VPN   | Maak een veilige verbinding tussen het apparaat van een externe werknemer en uw intranet via een virtueel Azure-netwerk.   | Hiervoor is een afzonderlijk betaald Azure-abonnement vereist |
| Windows Virtual Desktop   | Bied ondersteuning voor externe werknemers die alleen hun persoonlijke en niet-beheerde apparaten kunnen gebruiken met virtuele bureaubladen die worden uitgevoerd in Azure. | Hiervoor is een afzonderlijk betaald Azure-abonnement vereist |
| Extern bureaublad-services (RDS) | Geef werknemers toestemming om verbinding te maken met Windows-computers op uw intranet. | Microsoft 365 E3 en E5 | 
| Gateway voor extern bureaublad-services   | Versleutel de communicatie en voorkom dat de RDS-hosts rechtstreeks worden weergegeven op internet. | Hiervoor zijn afzonderlijke Windows Server-licenties vereist |
| Microsoft Intune | Beheer apparaten en toepassingen.   | Microsoft 365 E3 en E5 | 
| Configuration Manager | Software-installaties, updates en instellingen op uw apparaten beheren | Hiervoor zijn afzonderlijke Configuration Manager-licenties vereist |
| Desktop Analytics | Bepaal de updategereedheid van uw Windows-clients.   | Hiervoor zijn afzonderlijke Configuration Manager-licenties vereist |
| Windows Autopilot | Configureer de nieuwe Windows 10-apparaten vooraf voor productief gebruik.   | Microsoft 365 E3 en E5 |
| Microsoft Teams, Exchange Online, SharePoint Online en OneDrive, Microsoft 365-apps, Microsoft Power Platform, Yammer en Power Apps | Maak, communiceer en werk samen. | Microsoft 365 E3 en E5 |
||||

Gebruik de volgende stappen om de toegang tot de servers, gegevens en cloudservices van uw organisatie te beveiligen en optimaliseren, en uw werknemers maximaal productief te laten zijn.

1. [Beveiliging van aanmelden verbeteren met MFA](empower-people-to-work-remotely-secure-sign-in.md)
2. [Externe toegang tot on-premises apps en services bieden](empower-people-to-work-remotely-remote-access.md)
3. [Eindpuntbeheer voor uw apparaten, pc's en andere eindpunten implementeren](empower-people-to-work-remotely-manage-endpoints.md)
4. [Productiviteitsapps en -services voor externe medewerkers implementeren](empower-people-to-work-remotely-teams-productivity-apps.md)
5. [Communicatielocaties maken](empower-people-to-work-remotely-communication-venues.md)
6. [Externe werknemers trainen en voor feedback over gebruik zorgen](empower-people-to-work-remotely-train-monitor-usage.md)

![De stappen om externe werknemers mogelijkheden bieden met Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

Voor de meest recente informatie van Microsoft over het ondersteunen van externe werknemers, raadpleegt u de [Site van de Tech Community voor het inschakelen van werken op afstand](https://resources.techcommunity.microsoft.com/enabling-remote-work/).
