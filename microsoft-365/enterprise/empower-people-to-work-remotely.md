---
title: Externe werknemers mogelijkheden bieden
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Configureer de infrastructuur en beveiliging waarmee uw medewerkers altijd en overal extern kunnen werken.
ms.openlocfilehash: cfbabfbe0c239ca837356b585171778d40daaa93
ms.sourcegitcommit: 6adfcf042e64b21f09f2b8e072e8eba6d3479e31
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2020
ms.locfileid: "42952052"
---
# <a name="empower-remote-workers"></a>Externe werknemers mogelijkheden bieden

*Dit scenario geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

Het is voor veel organisaties belangrijk dat medewerkers naadloos en veilig buiten het kantoor kunnen werken om kantoorruimte te besparen, medewerkers in dienst te nemen en te behouden die niet willen verhuizen en het woon-werkverkeer van medewerkers te verminderen, zodat ze meer tijd hebben om productief te zijn en voor activiteiten buiten het werk die stress verlagen.

Onder extern werken, dat ook wel telewerken wordt genoemd, valt het volgende:

- Medewerkers die af en toe niet op kantoor zijn vanwege conferenties of vergaderingen met klanten.
- Bepaalde medewerkers die fulltime extern werken.
- Een volledig externe organisatie die geen kantoor heeft en waarvan alle medewerkers extern werken.

Ter ondersteuning van externe medewerkers is er een combinatie van functies beschikbaar in Microsoft 365 Enterprise waarmee ze heel goed kunnen samenwerken, zoals:

- Onlinevergaderingen en chatsessies.
- Gedeelde werkruimten voor opslag in de cloud met wereldwijde toegankelijkheid en realtime samenwerking.
- Gedeelde taken en werkstromen om het werk te verdelen en taken uit te voeren.

Voor een krachtige beveiliging bevat Microsoft 365 Enterprise het volgende:

- Afgedwongen verificatievereisten, aanmeldingen met een hoog risico detecteren en hierop reageren en geselecteerde apps en niet-compatibele apparaten blokkeren.
- Versleutelde verbindingen en digitale activa in de cloud.
- Machtigingen om te definiëren wie wat mag doen met bestanden.
- Preventie van gegevensverlies (DLP) om lekkage van sterk gereglementeerde gegevens te voorkomen.

Als u aan deze criteria voor externe medewerkers wilt voldoen, gebruikt u de volgende functies van Microsoft 365 Enterprise:

- Gebruikersidentiteit en aanmeldingsbeveiliging
  - Azure AD-gebruikersaccounts (Azure Active Directory) met meervoudige verificatie (MFA)
  - Beleid voor voorwaardelijke toegang om MFA te vereisen voor risicovolle aanmeldingen
- Samenwerkingsplatforms
  - Microsoft Teams, SharePoint en OneDrive, waarmee externe medewerkers online videovergaderingen kunnen plannen en bijwonen en tegelijk aan dezelfde documenten kunnen werken
- Veilige toegang tot bronnen
  - Groepen en machtigingen voor Teams, SharePoint-sites en OneDrive, zodat alleen geverifieerde, gemachtigde gebruikers toegang hebben
- Bescherming voor gelekte bestanden
  - DLP-beleid van Office 365
  - Gevoeligheidslabels voor versleuteling en machtigingen die met bestanden worden verzonden.
- Apparaatbeheer en -beveiliging met Microsoft Intune
  - Inschrijving voor beheerde apparaten
  - App-instellingen voor persoonlijke apparaten
  - Beleid voor apparaten en apps
- Productiviteits-apps voor apparaten
  - Office 365 ProPlus-apps voor samenwerking via Teams, SharePoint en OneDrive 
- Windows 10 Enterprise
  - Uitgebreide beveiligingsfuncties ter bescherming tegen cyberaanvallen en ter voorkoming van het lekken van gegevens
- Toegang tot on-premises apps
  - Organisaties met een hybride identiteit kunnen de Azure AD-toepassingsproxy gebruiken in plaats van VPN-verbindingen (Virtual Private Network).

In de volgende fasen wordt u stapsgewijs begeleid bij de implementatie van de functie van Microsoft 365 Enterprise voor externe toegang, waarmee ingebruikname wordt bevorderd voor externe medewerkers. Als u al elementen van deze fasen hebt geïmplementeerd, moet u ervoor zorgen dat deze voldoen aan de vermelde vereisten voordat u doorgaat naar het volgende element.

<a name="poster"></a> Zie de [Poster Externe werknemers mogelijkheden bieden](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf) voor een overzicht van één pagina van dit scenario.

[![Poster Externe werknemers mogelijkheden bieden](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf)

U kunt deze poster ook downloaden in [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/empower-remote-workers-scenario.pdf) of [PowerPoint-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/empower-people-to-work-remotely/Empower-Remote-Workers-Poster.pptx) indeling en deze afdrukken op papier met formaat Letter, Legal of Tabloid (27,9 x 43,2 cm).


## <a name="phase-1-deploy-microsoft-365-features-and-capabilities-for-remote-workers"></a>Fase 1: De functies en mogelijkheden van Microsoft 365 implementeren voor externe medewerkers

Vanwege de breedte en het grote aantal van de vereiste functies en mogelijkheden voor dit scenario, wordt u stapsgewijs door de vereiste elementen van de basisinfrastructuur en werklastsecties van de [Implementatiehandleiding voor Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md) begeleid.

### <a name="step-1-foundation-infrastructure-requirements-for-remote-workers"></a>Stap 1: vereisten voor de basisinfrastructuur voor externe medewerkers

In deze stap gaat u naar de fasen van de [basisinfrastructuur](deploy-foundation-infrastructure.md) en worden de elementen weergegeven die nodig zijn om medewerkers extern te laten werken.

Voor [Fase 2: Identiteit](identity-infrastructure.md) kunt u het volgende implementeren voor gebruikersidentiteit en aanmeldingsbeveiliging:

- Voor hybride identiteit: gebruikersaccounts en groepen die zijn gesynchroniseerd vanuit on-premises Active Directory Domain Services (AD DS).
- Voor het toewijzen van machtigingen: gesynchroniseerde groepen of Azure AD-groepen met de juiste leden.
- Verificatie-instellingen, zoals het vereisen van MFA.
- Beleid voor voorwaardelijke toegang om MFA te vereisen voor risicovolle aanmeldingen en clients te blokkeren die geen moderne verificatie ondersteunen.

Hier ziet u de resulterende configuratie waarin de identiteitselementen zijn gemarkeerd.

![Identiteitselementen voor externe medewerkers](../media/empower-people-to-work-remotely/remote-workers-id-phase.png)
 
Voor [Fase 3: Windows 10 Enterprise](windows10-infrastructure.md) implementeert u:

- De infrastructuur voor het implementeren van nieuwe apparaten met Windows 10 Enterprise en het upgraden van uw Windows 7- of Windows 8.1-apparaten naar Windows 10 Enterprise
- Uitgebreide beveiligingsfuncties inschakelen voor identiteits-, bedreigings-en gegevensbeveiliging

Dit is de resulterende configuratie met Windows 10 Enterprise-apparaten.

![Windows 10 Enterprise-elementen voor externe medewerkers](../media/empower-people-to-work-remotely/remote-workers-win10-phase.png)
 
Voor [Fase 4: Office 365 ProPlus](office365proplus-infrastructure.md) implementeert u de infrastructuur voor het installeren van Office 365 ProPlus of voert u een upgrade uit op de geïnstalleerde Office-suite, zoals Office 2010 of Office 2013, naar Office 365 ProPlus op de apparaten in uw organisatie. Hiermee krijgen uw gebruikers de beste beveiligings-en samenwerkingsfunctionaliteit.

Hier ziet u de resulterende configuratie met Office 365 ProPlus geïnstalleerd op apparaten.

![Office 365 ProPlus-elementen voor externe medewerkers](../media/empower-people-to-work-remotely/remote-workers-proplus-phase.png)
 
Voor [Fase 5: Mobile Device Management](mobility-infrastructure.md) implementeert u apparaat- en app-beheer van Intune voor:

- Inschrijving van uw Windows 10 Enterprise-, iOS-, Mac-, Android-en Android Enterprise-apparaten, zodat ze functies en beveiligingsinstellingen ontvangen die door uw organisatie zijn gedefinieerd.
- App-instellingen voor extra beveiliging en om apps toe te staan of te blokkeren, zelfs op persoonlijke apparaten van medewerkers.
- Nalevingsbeleid met voorwaardelijke toegang om te voorkomen dat niet-compatibele apparaten verbinding maken.

Dit is de resulterende configuratie, waarin apparaten die zijn ingeschreven bij Intune, en de beleidsregels zijn gemarkeerd.

![Elementen van Mobile Device Management voor externe medewerkers](../media/empower-people-to-work-remotely/remote-workers-mdm-phase.png)
 
Voor [Fase 6: Gegevensbeveiliging](infoprotect-infrastructure.md), ontwerpt en configureert u beveiliging voor uw digitale activa met:

- DLP-beleid van Office 365.
- Office 365-gevoeligheidslabels voor versleuteling en machtigingen die met bestanden worden verzonden.

Dit is de resulterende configuratie, waarin DLP-beleid en gevoeligheidslabels zijn gemarkeerd.

![Elementen van gegevensbeveiliging voor externe medewerkers](../media/empower-people-to-work-remotely/remote-workers-ip-phase.png)
 
Voor toegang tot on-premises apps kunt u de [Azure AD-toepassingsproxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy) gebruiken, waarvoor een hybride identiteitsomgeving is vereist.

Hier ziet u de resulterende configuratie waarin de onderdelen van de toepassingsproxy zijn gemarkeerd.

![Elementen van de toepassingsproxy voor externe medewerkers](../media/empower-people-to-work-remotely/remote-workers-app-proxy.png)
 
### <a name="step-2-workloads-for-remote-workers"></a>Stap 2: workloads voor externe medewerkers

Voor [Exchange Online](exchangeonline-workload.md) implementeert u Exchange Online-postvakken voor al uw gebruikers.

Voor [Teams](teams-workload.md) implementeert u Teams voor uw gebruikers en groepen.

Voor [SharePoint en OneDrive](sharepoint-online-onedrive-workload.md) implementeert u SharePoint-teamsites -communicatiesites en OneDrive-mappen.

Hier ziet u de resulterende configuratie waarin de workloads zijn gemarkeerd.

![Microsoft 365-workloads voor externe medewerkers](../media/empower-people-to-work-remotely/remote-workers-workloads.png)
 
### <a name="deployment-results"></a>Implementatieresultaten

Na de implementatie van de basisinfrastructuur en workloads en de installatie van Windows 10 Enterprise en Office 365 ProPlus, geldt het volgende voor externe medewerkers:

- Ze beschikken over sterke verificatie- en identiteitsbescherming.
- Ze hebben de nieuwste en veiligste versie van Windows op hun Windows-apparaat.
- Ze hebben de recentste en productiefste versie van de Office-suite op hun apparaten.
- Ze moeten zich houden aan nalevingsbeleid voor app-beheer en apparaten.
- Ze moeten zich houden aan DLP-beleid en -beperkingen.
- Ze kunnen gevoeligheidslabels voor versleuteling en machtigingen die met bestanden en e-mailberichten worden verzonden, toewijzen.
- Ze hebben toegang tot on-premises apps zonder een VPN-verbinding.
- Ze kunnen hun eigen werk uitvoeren en in realtime samenwerken met collega's via chats, vergaderingen en bestanden in Teams en in SharePoint en OneDrive.

Wanneer de externe medewerkers offline zijn (niet verbonden met internet), kunnen ze lokale kopieën van bestanden wijzigen. Wanneer ze weer verbinding maken met internet, worden in OneDrive lokale kopieën gesynchroniseerd met de bestanden die zijn opgeslagen in uw Microsoft 365-abonnement. 

Dit is de resulterende configuratie voor externe medewerkers van uw organisatie als u de hybride identiteit gebruikt.

![Definitieve configuratie voor een organisatie met een hybride identiteit](../media/empower-people-to-work-remotely/remote-workers-hybrid.png) 
 
Dit is de resulterende configuratie voor externe medewerkers van uw organisatie als u alleen de cloudidentiteit gebruikt.

![Definitieve configuratie voor een organisatie met een cloudidentiteit](../media/empower-people-to-work-remotely/remote-workers-cloud-only.png)

## <a name="phase-2-drive-user-adoption-for-remote-workers"></a>Fase 2: Ingebruikname door externe medewerkers bevorderen

Nu de basisinfrastructuur en de workloads zijn geïmplementeerd, gaat u ervoor zorgen dat uw externe medewerkers deze kunnen gebruiken, zodat ze altijd en overal productief kunnen zijn.

### <a name="step-1-train-your-users"></a>Stap 1: uw gebruikers trainen

Geef uw externe medewerkers training in:

- De juiste aanmeldingsprocedures, waaronder MFA-registratie, en hoe aanmeldingen kunnen worden tegengehouden als een risico wordt gedetecteerd.
- Het gebruik van apparaten en hoe beleid kan worden gebruikt om toegang te blokkeren voor niet-compatibele apparaten.
- Het gebruik van toegestane apps en hoe app-beleid van Intune kan worden gebruikt om apps te blokkeren.
- Beveiligingsfuncties van Windows 10 Enterprise.
- Het gebruik van Outlook voor e-mail en agenda.
- Het gebruik van [Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) voor chatten, videovergaderingen, het delen van documenten en gesprekslijnen.
- Het gebruik van SharePoint-teamsites of -communicatiesites en OneDrive-mappen om door bestanden in de bibliotheek van een gebruiker of een groep te bladeren.
- Het gebruik en de toepassing van gevoeligheidslabels voor bestanden met gevoelige of sterk gereglementeerde gegevens voor zowel lokale als onlineversies van bestanden.

Bij deze training horen praktijkoefeningen, zodat de gebruikers deze functies en de resultaten ervan kunnen ervaren.

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-worker-feedback"></a>Stap 2: periodiek het gebruik bekijken en feedback van medewerkers verwerken

In de weken na de training:

- Verwerk de feedback van externe medewerkers snel en verfijn beleidsregels en configuraties.
- Analyseer het gebruik voor teams, SharePoint-sites en OneDrive-mappen en vergelijk dit met de gebruiksverwachtingen.
- Controleer of gevoelige of sterk gereglementeerde bestanden juist zijn gelabeld met het relevante gevoeligheidslabel.

School de gebruikers indien nodig bij.

### <a name="user-adoption-results"></a>Resultaten van gebruikersacceptatie

Uw externe medewerkers kunnen met hun Windows 10 Enterprise-apparaten of andere apparaten en Office 365 ProPlus in een beveiligde omgeving toegang krijgen tot en werken met gedeelde cloudservices en bronnen van Microsoft 365, waarbij ze in realtime vergaderen, creëren en samenwerken.

## <a name="see-also"></a>Zie ook

[Workloads en scenario's](deploy-workloads.md)

[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)

[Implementatiehandleiding](deploy-microsoft-365-enterprise.md)
