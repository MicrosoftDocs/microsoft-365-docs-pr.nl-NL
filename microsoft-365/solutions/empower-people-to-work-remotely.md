---
title: Externe werknemers mogelijkheden bieden met Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 09/02/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
ms.custom: ''
description: Configureer de beveiligings- en service-infrastructuur waardoor uw werknemers altijd en overal op afstand kunnen werken.
ms.openlocfilehash: f5364103610fbac8efe47b9ae7e776d215fc0733
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327733"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>Externe werknemers mogelijkheden bieden met Microsoft 365

De werknemers van uw bedrijf moeten mogelijk vanuit huis veilige toegang tot de on-premises en cloudgegevens, -hulpprogramma's en -informatiebronnen van uw organisatie kunnen krijgen. Door werknemers op afstand te laten werken, kunnen veel organisaties:

- Besparen op kantoorruimte.
- Werknemers aannemen en behouden die niet bereid zijn te verhuizen.
- De reistijd van werknemers verminderen, waardoor er meer tijd overblijft om productief te zijn en stress verlagende activiteiten uit te voeren buiten werktijd.

Microsoft 365 biedt de mogelijkheden om uw werknemers in staat te stellen om op afstand te werken.

![Uw externe werknemers mogelijkheden bieden met Microsoft 365](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

Bekijk deze video voor een overzicht van het implementatieproces.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

Deze oplossing biedt de volgende belangrijke mogelijkheden.

- Verbonden

  Externe werknemers hebben overal ter wereld en op elk gewenst moment toegang tot: 

  - Op de cloud gebaseerde services en gegevens in uw Microsoft 365-abonnement. 
  - Resources van de organisatie, zoals de resources van on-premises toepassingsdatacenters.

- Beveiligd

  Aanmeldingen worden beveiligd met meervoudige verificatie (MFA) en ingebouwde beveiligingsfuncties van Microsoft 365 en Windows 10 beveiligen tegen malware, kwaadwillige aanvallen en gegevensverlies.

- Beheerd

  De apparaten van uw externe werknemers kunnen worden beheerd vanuit de cloud met beveiligingsinstellingen, toegestane apps en door naleving van de systeemstatus te vereisen.

- Samenwerking en productiviteit

  Uw externe werknemers kunnen net zo productief zijn als op kantoor in een omgeving waar samenwerking eenvoudig is met:
  - Online vergaderingen en chatsessies met Teams. 
  - Gedeelde werkruimten voor cloudopslag met wereldwijde toegankelijkheid en realtime samenwerking met SharePoint en OneDrive.
  - Gedeelde taken en werkstromen om het werk te verdelen en taken uit te voeren. 

Voor een naadloze aanmelding moeten de on-premise gebruikersaccounts van Active Directory Domain Services (AD DS) worden gesynchroniseerd met Azure Active Directory (Azure AD). Als u uw Windows 10-apparaten wilt beveiligen, moeten ze worden ingeschreven in Intune. Dit is een algemeen overzicht van de infrastructuur.

![De basisinfrastructuur voor externe werknemers met Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

Als u aan de criteria voor externe werknemers wilt voldoen, gebruikt u de volgende functies van Microsoft 365.

| Functie | Beschrijving | Licenties |
|:-------|:-----|:-------|
| Afgedwongen door MFA en met standaardbeveiligingsinstellingen   | Voorkom gecompromitteerde identiteiten en apparaten met een tweede vorm van verificatie voor aanmeldingen. Als standaardinstelling voor de beveiliging is MFA vereist voor alle gebruikersaccounts.   | Microsoft 365 E3 of E5 |
| Afgedwongen door MFA en met voorwaardelijke toegang| Gebruik beleid voor voorwaardelijke toegang om MFA te vereisen op basis van de eigenschappen van de aanmelding.    | Microsoft 365 E3 of E5 | 
| Afgedwongen door MFA en met voorwaardelijke toegang op basis van risico   | Gebruik Azure Advanced Threat Protection om MFA te vereisen op basis van het risico van de gebruikersaanmelding. | Microsoft 365 E5 of E3 met Azure AD Premium P2-licenties | 
| Selfservice voor wachtwoordherstel (SSPR)    | Sta toe dat gebruikers hun wachtwoorden of accounts opnieuw kunnen instellen of ontgrendelen.  | Microsoft 365 E3 of E5 |
| Azure AD-toepassingsproxy    | Bied beveiligde externe toegang bieden voor webtoepassingen die worden gehost op intranetservers.   | Hiervoor is een afzonderlijk betaald Azure-abonnement vereist |
| Azure-punt-naar-site-VPN   | Maak een veilige verbinding tussen het apparaat van een externe werknemer en uw intranet via een virtueel Azure-netwerk.   | Hiervoor is een afzonderlijk betaald Azure-abonnement vereist |
| Windows Virtual Desktop   | Bied ondersteuning voor externe werknemers die alleen hun persoonlijke en niet-beheerde apparaten kunnen gebruiken met virtuele bureaubladen die worden uitgevoerd in Azure. | Hiervoor is een afzonderlijk betaald Azure-abonnement vereist |
| Extern bureaublad-services (RDS) | Geef werknemers toestemming om verbinding te maken met Windows-computers op uw intranet. | Microsoft 365 E3 of E5 | 
| Gateway voor extern bureaublad-services   | Versleutel de communicatie en voorkom dat de RDS-hosts rechtstreeks worden weergegeven op internet. | Hiervoor zijn afzonderlijke Windows Server-licenties vereist |
| Microsoft Intune | Beheer apparaten en toepassingen.   | Microsoft 365 E3 of E5 | 
| Configuration Manager | Software-installaties, updates en instellingen op uw apparaten beheren | Hiervoor zijn afzonderlijke Configuration Manager-licenties vereist |
| Desktop Analytics | Bepaal de updategereedheid van uw Windows-clients.   | Hiervoor zijn afzonderlijke Configuration Manager-licenties vereist |
| Windows Autopilot | Configureer de nieuwe Windows 10-apparaten vooraf voor productief gebruik.   | Microsoft 365 E3 of E5 |
| Microsoft Teams, Exchange Online, SharePoint Online en OneDrive, Microsoft 365-apps, Microsoft Power Platform, Yammer en Power Apps | Maak, communiceer en werk samen. | Microsoft 365 E3 of E5 |
||||

Raadpleeg [Beveiliging en compliance implementeren voor beveiligings- en compliancecriteria voor externe werknemers](empower-people-to-work-remotely-security-compliance.md).

<a name="poster"></a> Zie de [Poster Externe werknemers mogelijkheden bieden](../downloads/empower-remote-workers.pdf) voor een overzicht van twee pagina's van deze oplossing.

[![Poster Externe werknemers mogelijkheden bieden](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)

U kunt deze poster ook downloaden in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf)-indeling en afdrukken op papier met formaat Letter, Legal of Tabloid (27,9 x 43,2 cm).

Gebruik de volgende stappen om de toegang tot de servers, gegevens en cloudservices van uw organisatie te beveiligen en optimaliseren, en uw werknemers maximaal productief te laten zijn.

1. [Beveiliging van aanmelden verbeteren met MFA](empower-people-to-work-remotely-secure-sign-in.md)
2. [Externe toegang tot on-premises apps en services bieden](empower-people-to-work-remotely-remote-access.md)
3. [Beveiligings- en complianceservices implementeren](empower-people-to-work-remotely-security-compliance.md)
4. [Eindpuntbeheer voor uw apparaten, pc's en andere eindpunten implementeren](empower-people-to-work-remotely-manage-endpoints.md)
5. [Productiviteitsapps en -services voor externe medewerkers implementeren](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [Externe werknemers trainen en voor feedback over gebruik zorgen](empower-people-to-work-remotely-train-monitor-usage.md)

![De stappen om externe werknemers mogelijkheden bieden met Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

Voor de meest recente informatie van Microsoft over het ondersteunen van externe werknemers, raadpleegt u de [Site van de Tech Community voor het inschakelen van werken op afstand](https://resources.techcommunity.microsoft.com/enabling-remote-work/).
