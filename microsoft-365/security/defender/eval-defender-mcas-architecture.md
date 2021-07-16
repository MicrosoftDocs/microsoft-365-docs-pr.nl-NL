---
title: Bekijk de architectuurvereisten en de structuur voor Microsoft Cloud App Security, plan de configuratie en het ontwerp door het kader van Cloud App Security in Microsoft 365 Defender
description: Microsoft Cloud App Security technische diagrammen leggen de architectuur in Microsoft 365 Defender uit, waarmee u een testomgeving kunt bouwen.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: a3fa9670262b90d1566c375680946a131bb9c78a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457744"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-cloud-app-security"></a>Architectuurvereisten en belangrijke concepten voor Microsoft Cloud App Security


**Van toepassing op:**

- Microsoft 365 Defender

Dit artikel is [stap 1 van 3](eval-defender-mcas-overview.md) in het proces van het instellen van de evaluatieomgeving voor Microsoft Cloud App Security naast Microsoft 365 Defender. Zie het [overzichtsartikel](eval-defender-identity-overview.md)voor meer informatie over dit proces.

Voordat u Microsoft Cloud App Security inschakelen, moet u de architectuur begrijpen en aan de vereisten voldoen. 

## <a name="understand-the-architecture"></a>De architectuur begrijpen

Microsoft Cloud App Security is een Cloud Access Security Broker (CASB). CASB's fungeren als poortwachter voor realtime toegang tot makelaars tussen uw zakelijke gebruikers en cloudbronnen die ze gebruiken, waar uw gebruikers zich ook bevinden en ongeacht het apparaat dat ze gebruiken. Microsoft Cloud App Security is inheems geïntegreerd met microsoft-beveiligingsmogelijkheden, waaronder Microsoft 365 Defender. 

Zonder Cloud App Security zijn cloud-apps die door uw organisatie worden gebruikt, niet-beveiligd, zoals wordt geïllustreerd.

![Architectuur voor Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-architecture-a.png)

In de afbeelding:
- Het gebruik van cloud-apps door een organisatie wordt niet gecontroleerd en niet beveiligd. 
- Dit gebruik valt buiten de beveiligingen die binnen een beheerde organisatie zijn bereikt. 

#### <a name="discovering-cloud-apps"></a>Cloud-apps ontdekken

De eerste stap voor het beheren van het gebruik van cloud-apps is om te ontdekken welke cloud-apps door uw organisatie worden gebruikt. In dit volgende diagram ziet u hoe clouddetectie werkt met Cloud App Security.

![Architectuur voor Microsoft Cloud App Security - Clouddetectie](../../media/defender/m365-defender-mcas-architecture-b.png)

In deze afbeelding zijn er twee methoden die kunnen worden gebruikt om netwerkverkeer te controleren en cloud-apps te ontdekken die door uw organisatie worden gebruikt.
- A. Cloud App Discovery is inheems geïntegreerd met Microsoft Defender voor Endpoint. Defender voor Eindpunt meldt dat cloud-apps en -services worden gebruikt vanaf it-beheerde Windows 10 apparaten. 
- B. Voor dekking op alle apparaten die zijn verbonden met een netwerk, wordt Cloud App Security logboekverzamelaar geïnstalleerd op firewalls en andere proxies om gegevens van eindpunten te verzamelen. Deze gegevens worden verzonden naar Cloud App Security voor analyse.

#### <a name="managing-cloud-apps"></a>Cloud-apps beheren

Nadat u cloud-apps hebt ontdekt en het gedrag hebt geanalyseerd van hoe deze door uw organisatie worden gebruikt, kunt u beginnen met het beheren van cloud-apps die u kiest. 

![Architectuur voor Microsoft Cloud App Security - Cloud-apps beheren](../../media/defender/m365-defender-mcas-architecture-c.png)

In deze afbeelding:
- Sommige apps worden gesanctioneerd voor gebruik. Dit is een eenvoudige manier om apps te beheren.
- U kunt meer zichtbaarheid en controle inschakelen door apps te verbinden met app-connectors. App-connectors gebruiken de API's van app-providers.


#### <a name="applying-session-controls-to-cloud-apps"></a>Sessiebesturingselementen toepassen op cloud-apps

Microsoft Cloud App Security fungeert als omgekeerde proxy en biedt proxytoegang tot goedgekeurde cloud-apps. Hierdoor kunnen Cloud App Security sessiebesturingselementen toepassen die u configureert. 

![Architectuur voor Microsoft Cloud App Security - Proxy access-sessiebesturingselement](../../media/defender/m365-defender-mcas-architecture-d.png)

In deze afbeelding:
- Toegang tot goedgekeurde cloud-apps van gebruikers en apparaten in uw organisatie wordt doorgeleid via Cloud App Security.
- Met deze proxytoegang kunnen sessiebesturingselementen worden toegepast.
- Cloud-apps die u niet hebt gesanctioneerd of expliciet niet hebt goedgekeurd, worden niet beïnvloed.

Met sessiebesturingselementen kunt u parameters toepassen op de manier waarop cloud-apps door uw organisatie worden gebruikt. Als uw organisatie bijvoorbeeld Salesforce gebruikt, kunt u een sessiebeleid configureren waarmee alleen beheerde apparaten toegang hebben tot de gegevens van uw organisatie in Salesforce. Een eenvoudiger voorbeeld is het configureren van een beleid voor het controleren van verkeer vanaf niet-beheerbare apparaten, zodat u het risico van dit verkeer kunt analyseren voordat u strikter beleid kunt toepassen.

#### <a name="integrating-with-azure-ad-with-conditional-access-app-control"></a>Integratie met Azure AD met Voorwaardelijke toegang app-beheer

Mogelijk hebt u al SaaS-apps toegevoegd aan uw Azure AD-tenant om meervoudige verificatie en ander beleid voor voorwaardelijke toegang af te dwingen. Microsoft Cloud App Security is inheems geïntegreerd met Azure AD. Het enige wat u hoeft te doen, is een beleid configureren in Azure AD om Voorwaardelijke toegangsbeheer voor apps te gebruiken in Cloud App Security. Hiermee wordt netwerkverkeer voor deze beheerde SaaS-apps door Cloud App Security als proxy gerouteerd, zodat Cloud App Security dit verkeer kan controleren en sessiebesturingselementen kunt toepassen. 

![Architectuur voor Microsoft Cloud App Security - SaaS-apps](../../media/defender/m365-defender-mcas-architecture-e.png)

In deze afbeelding:
- SaaS-apps zijn geïntegreerd met de Azure AD-tenant. Hierdoor kan Azure AD beleid voor voorwaardelijke toegang afdwingen, inclusief meervoudige verificatie.
- Er wordt een beleid toegevoegd aan Azure Active Directory om het verkeer voor SaaS-apps te Cloud App Security. Het beleid geeft aan op welke SaaS-apps u dit beleid wilt toepassen. Wanneer Azure AD dus beleid voor voorwaardelijke toegang afdwingt dat van toepassing is op deze SaaS-apps, wordt het sessieverkeer vervolgens door Azure AD door (proxies) door de Cloud App Security.
- Cloud App Security controleert dit verkeer en past alle beleidsregels voor sessiebeheer toe die zijn geconfigureerd door beheerders. 

Mogelijk hebt u cloud-apps ontdekt en gesanctioneerd met Cloud App Security die niet zijn toegevoegd aan Azure AD. U kunt profiteren van Voorwaardelijke toegangsbeheer door deze cloud-apps toe te voegen aan uw Azure AD-tenant en het bereik van uw regels voor voorwaardelijke toegang.

#### <a name="protecting-your-organization-from-hackers"></a>Uw organisatie beschermen tegen hackers

Cloud App Security biedt zelf krachtige beveiliging. Wanneer u dit echter combineert met de andere mogelijkheden van Microsoft 365 Defender, Cloud App Security gegevens in de gedeelde signalen, waarmee u samen aanvallen kunt stoppen.

Het is de moeite waard om deze afbeelding te herhalen vanuit het overzicht naar deze Microsoft 365 Defender evaluatie- en pilothandleiding. 

![Hoe Microsoft 365 Defender een reeks bedreigingen stopt](../../media/defender/m365-defender-eval-threat-chain.png)

Aan de rechterkant van deze afbeelding ziet Microsoft Cloud App Security afwijkende gedragingen, zoals onmogelijk reizen, toegang tot referenties en ongebruikelijke download-, bestands delen- of e-mail doorsturen, en worden deze gemeld aan het beveiligingsteam. Daarom helpt Cloud App Security voorkomen dat hackers laterale bewegingen maken en gevoelige gegevens exfiltreren. Microsoft 356 Defender correleert de signalen van alle onderdelen om het volledige aanvalsverhaal te bieden.

## <a name="understand-key-concepts"></a>Belangrijke concepten begrijpen

In de volgende tabel worden belangrijke concepten geïdentificeerd die belangrijk zijn om te begrijpen bij het evalueren, configureren en implementeren van Microsoft Cloud App Security.


|Concept  |Omschrijving |Meer informatie  |
|---------|---------|---------|
| Cloud App Security Dashboard | Geeft een overzicht van de belangrijkste informatie over uw organisatie en geeft koppelingen naar dieper onderzoek.        | [Werken met het dashboard ](/cloud-app-security/daily-activities-to-protect-your-cloud-environment)       |
| App-beheer voor voorwaardelijke toegang    | Reverse proxyarchitectuur die is geïntegreerd met uw IdP (Identity Provider) om Beleid voor voorwaardelijke toegang van Azure AD te geven en selectief sessiebesturingselementen af te dwingen.        |  [Apps beveiligen met Microsoft Cloud App Security Voorwaardelijke toegang app-besturingselement](/cloud-app-security/proxy-intro-aad)       |
|  Cloud-app-catalogus   | De catalogus met cloud-apps geeft u een volledig beeld ten opzichte van de Microsoft-catalogus van meer dan 16.000 cloud-apps die worden gerangschikt en gescored op basis van meer dan 80 risicofactoren.    |  [Werken met app-risicoscores](/cloud-app-security/risk-score)       |
| Cloud Discovery Dashboard    | Cloud Discovery analyseert uw verkeerslogboeken en is ontworpen om meer inzicht te geven in hoe cloud-apps in uw organisatie worden gebruikt en om waarschuwingen en risiconiveaus te geven.     |  [Werken met gevonden apps   ](/cloud-app-security/discovered-apps)    |
|Verbonden apps |Cloud App Security biedt end-to-endbeveiliging voor verbonden apps met cloud-to-cloudintegratie, API-connectors en realtime toegangs- en sessiebesturingselementen die gebruikmaken van onze voorwaardelijke toegangsbesturingselementen voor apps. |[Verbonden apps beveiligen](/cloud-app-security/protect-connected-apps) |
| | | |

## <a name="review-architecture-requirements"></a>Architectuurvereisten controleren

### <a name="discovering-cloud-apps"></a>Cloud-apps ontdekken

Als u cloud-apps wilt ontdekken die in uw omgeving worden gebruikt, kunt u een of beide van de volgende dingen doen:

- Ga snel aan de weg met Cloud Discovery door te integreren met Microsoft Defender voor Eindpunt. Met deze native integratie kunt u direct beginnen met het verzamelen van gegevens over cloudverkeer op uw Windows 10 apparaten, in en uit uw netwerk.
- Als u alle cloud-apps wilt ontdekken die toegankelijk zijn voor alle apparaten die zijn verbonden met uw netwerk, implementeert u de Cloud App Security logboekverzamelaar op uw firewalls en andere proxies. Hiermee worden gegevens van uw eindpunten verzameld en naar Cloud App Security voor analyse. Cloud App Security inheems geïntegreerd met sommige proxies van derden voor nog meer mogelijkheden.

Deze opties zijn opgenomen in [stap 2. Schakel de evaluatieomgeving in.](eval-defender-mcas-enable-eval.md) 

### <a name="applying-azure-ad-conditional-access-policies-to-cloud-apps"></a>Azure AD-beleid voor voorwaardelijke toegang toepassen op cloud-apps

Voorwaardelijke toegang App Control (de mogelijkheid om beleid voor voorwaardelijke toegang toe te passen op cloud-apps) vereist integratie met Azure AD. Dit is geen vereiste om aan de slag te gaan met Cloud App Security. Het is een stap die we u aanmoedigen om het uit te proberen tijdens de testfase: [stap 3. Pilot Microsoft Cloud App Security.](eval-defender-mcas-pilot.md)

## <a name="siem-integration"></a>SIEM-integratie

U kunt uw Microsoft Cloud App Security met uw algemene SIEM-server of met Azure Sentinel integreren om gecentraliseerde monitoring van waarschuwingen en activiteiten vanuit verbonden apps in te stellen. 

Daarnaast bevat Azure Sentinel een Microsoft Cloud App Security connector voor een diepere integratie met Azure Sentinel. Hierdoor kunt u niet alleen inzicht krijgen in uw cloud-apps, maar ook geavanceerde analyses krijgen om cyberaanvallen te identificeren en te bestrijden en om te bepalen hoe uw gegevens worden verplaatst.

- [Algemene SIEM-integratie](/cloud-app-security/siem)
- [Streamwaarschuwingen en Cloud Discovery-logboeken van MCAS naar Azure Sentinel](/azure/sentinel/connect-cloud-app-security)

### <a name="next-steps"></a>Volgende stappen

Stap 2 van 3: [De evaluatieomgeving inschakelen voor Microsoft Cloud App Security](eval-defender-mcas-enable-eval.md)

Ga terug naar het overzicht voor [Evalueren Microsoft Cloud App Security](eval-defender-mcas-overview.md)

Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)