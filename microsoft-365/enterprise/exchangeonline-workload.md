---
title: Exchange Online implementeren voor Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: Stap door het proces van planning, uitrol en het genereren van de waarde van Exchange Online in Microsoft 365 Enterprise in uw hele organisatie.
ms.openlocfilehash: 9214796c37e9cb5ca9fcb07ced5db7efd8e0f7d0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634144"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Exchange Online implementeren voor Microsoft 365 Enterprise

*Deze werkbelasting geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

Exchange Online is uw primaire cloudservice voor e-mail en agenda's waarmee uw gebruikers kunnen samenwerken op een manier die geen realtime chat of gecentraliseerde documentopslag vereist. Exchange Online is een belangrijk element van de waarde Built for Teamwork van Microsoft 365 Enterprise. Met Exchange Online u meer bereiken en effectiever werken met de bekende Outlook-toepassing, ongeacht op welk apparaat u zich bevindt.

Exchange Online beschikt ook over geavanceerde beveiligingsmogelijkheden, waaronder anti-malware en anti-spamfiltering om postvakken en mogelijkheden voor het voorkomen van gegevensverlies te beschermen die voorkomen dat gebruikers per ongeluk gevoelige informatie naar onbevoegde personen verzenden. Exchange Online-beveiliging is een belangrijk element van de waarde van intelligente beveiliging van Microsoft 365 Enterprise.

Zie Microsoft Exchange Online als u nieuw bent in Exchange [Online.](https://products.office.com/exchange/exchange-online)

De volgende fasen en stappen begeleiden u bij het proces van het voorstellen van de rol van Exchange Online in uw organisatie, het inwerken van uw organisatie naar Exchange Online door middel van een reeks progressieve implementaties en het stimuleren van het gebruik van Exchange Online en de waarde ervan voor uw eindgebruikers.

>[!Note]
>Deze implementatie-instructies moeten alleen worden opgevolgd nadat u [fase 2-identiteit van de Microsoft 365 Enterprise-basisinfrastructuur](identity-infrastructure.md)hebt voltooid.
>

## <a name="phase-1-envision-your-exchange-online-deployment"></a>Fase 1: Uw Exchange Online-implementatie voorstellen

In deze fase verzamelt u de mensen voor uw Exchange Online-implementatie en bepaalt u hoe uw organisatie Exchange Online zal gebruiken om aan haar zakelijke behoeften te voldoen.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>Stap 1: Uw Exchange Online-implementatieleden verzamelen

Voor een succesvolle implementatie van Exchange Online bovenop [fase 2-identiteit](identity-infrastructure.md) van de Microsoft 365 Enterprise-basisinfrastructuur, moet u de juiste mensen verzamelen voor invoer en feedback. Sleutelfiguren zijn onder meer zakelijke besluitvormers, IT-personeel zoals architecten en uitvoerders, en enthousiaste eindgebruikers. 

Deze drie groepen zorgen ervoor dat uw Exchange Online-implementatie overwegingen bevat die beantwoorden aan zakelijke behoeften, technische aspecten van postvakmigratie en beveiliging en dat het resultaat iets is dat typische gebruikers zullen gebruiken.

#### <a name="result"></a>Resultaat

Een lijst met mensen die de zakelijke, technische en eindgebruikeraspecten van uw organisatie vertegenwoordigen.

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>Stap 2: Uw Exchange Online-bedrijfsscenario's bepalen en prioriteren

Exchange Online kan voor verschillende doeleinden worden gebruikt. U moet uitzoeken welke doeleinden uw bedrijfsbehoeften in kaart brengen op de afzonderlijke niveaus van uw organisatie, uw bedrijfsgroepen, uw afdelingen of individuele werk- en projectteams. U moet Exchange Online targeten om tegemoet te komen aan de behoeften van uw individuele en kleine groep van korte duur. 

Een manier om de voordelen van Exchange Online te zien, is door te onderzoeken hoe individuen, een team of v-team vandaag met elkaar communiceren en vervolgens een geschikt scenario te vinden dat eenvoudigere manieren biedt om te communiceren, vergaderingen te plannen en samen te werken. Houd er rekening mee dat [Microsoft Teams](teams-workload.md) een betere keuze is voor sommige samenwerkingsscenario's.

#### <a name="result"></a>Resultaat
Een lijst met Exchange Online-scenario's die beantwoorden aan de behoeften van uw organisatie op het werk van communicatie, planning en kortstondige samenwerking.

## <a name="phase-2-onboard"></a>Fase 2: onboarding

In deze fase plant u de technische aspecten van een Exchange Online-implementatie en begint u deze uit te rollen naar geselecteerde groepen gebruikers.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Vereisten: configuratie van identiteit en apparaattoegang

Als u de toegang tot Exchange Online-postvakken wilt beveiligen, moet u ervoor zorgen dat u [het beleid voor identiteits- en apparaattoegangsbeleid](identity-access-policies.md) en het [aanbevolen exchange online-toegangsbeleid](secure-email-recommended-policies.md)hebt geconfigureerd.

### <a name="step-1-complete-your-technical-planning"></a>Stap 1: voltooi de technische planning

Voordat u met de technische planning begint, moet u bepalen of u FastTrack wilt gebruiken. Als uw organisatie meer dan 50 zitplaatsen heeft en deelneemt aan een [in aanmerking komend abonnement,](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)u [FastTrack gebruiken voor Microsoft 365](https://fasttrack.microsoft.com/microsoft365), *zonder extra kosten beschikbaar* om u te begeleiden bij het plannen, implementeren en service-adoptie. Of u kunt deze taak zelf voltooien met FastTrack Onboarding Wizards, die beschikbaar zijn bij [FastTrack](https://fasttrack.microsoft.com/) zodra u zich aanmeldt met uw Microsoft 365-account.

Als u uw eigen planning of in combinatie met FastTrack aan het doen bent, moet u bepalen of uw netwerk en organisatie klaar zijn voor Exchange Online. Het is vooral belangrijk dat u voldoet aan de exitcriteria voor [netwerken](networking-infrastructure.md) in uw funderingsinfrastructuur voor gebruikers die zijn aangesloten op uw organisatienetwerk. Besteed speciale aandacht aan internetbandbreedte, doorvoer en vertragingen in het verkeer om de prestaties voor het extra verkeer voor op Exchange Online gebaseerde e-mail en bijlagen te maximaliseren.

Gebruik deze bronnen om u voor te bereiden op de technische aspecten van een Exchange Online-implementatie: 

- [Manieren om meerdere e-mailaccounts naar Office 365 te migreren](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
- [Openbare mappen van Exchange Server migreren naar Exchange Online](https://docs.microsoft.com/Exchange/collaboration/public-folders/migrate-to-exchange-online?view=exchserver-2019)
- [Openbare mappen van Exchange Server migreren naar Microsoft 365-groepen](https://docs.microsoft.com/Exchange/collaboration/public-folders/batch-migration-to-office-365-groups?view=exchserver-2019)
- [Samenwerking in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/collaboration-exo)
- [Ontvangers in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/recipients-in-exchange-online)
- [Outlook voor iOS en Android](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android)

Bekijk de volgende bronnen voor een beter begrip van de beveiliging in Exchange Online:

- [Machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- [Beveiliging en naleving voor Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance) 
- [Bescherming tegen ongewenste e-mail en malware](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

Gebruik vervolgens deze bronnen om inzicht te krijgen in het postvakbeheer van Exchange Online:

- [Gebruikerspostvakken maken in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/create-user-mailboxes)
- [Gebruikerspostvakken beheren](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 
- [Distributiegroepen maken en beheren](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)

#### <a name="result"></a>Resultaat

U begrijpt de migratie, beveiliging en het beheer van postvaken en bent klaar om Exchange Online uit te rollen naar geselecteerde groepen in uw organisatie.

### <a name="step-2-run-an-it-pilot"></a>Stap 2: een IT-pilot uitvoeren

Voor de meeste middelgrote en grote organisaties moet u een IT-pilot uitvoeren met uw stakeholders uit fase 1, early adopters en technische enthousiastelingen. Tijdens de IT-pilot:

- Geef uw deelnemers aan de piloot Microsoft 365-licenties en migreer hun on-premises postvakken naar Exchange Online.
- Geef uw deelnemers aan de piloot een reeks oefeningen om Exchange Online-e-mail, planning en andere mogelijkheden te testen.
- Bepaal uw strategie voor wijzigingsbeheer en produceer materialen om de acceptatie van Outlook en Exchange Online voor de hele organisatie te stimuleren. 
 
  Materiaal voor verandermanagement kan bestaan uit e-mailaankondigingen, interne trainingsplannen, gangposters en presentaties. Deze materialen zullen uw organisatie informeren over Exchange Online en de voordelen ervan met als doel het verhogen van het bewustzijn en het rijden gebruik. Zie het artikel [over wijzigingsbeheer voor Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) voor een aantal ideeën.

- Laat de deelnemers aan de IT-pilot het materiaal voor veranderingsbeheer beoordelen op basis van hun ervaringen. Ze kunnen tips geven over best practices en advies over hoe u de voordelen van Outlook en Exchange Online het beste beschrijven en hoe u deze gebruiken voor communicatie en planning.

#### <a name="result"></a>Resultaat

Uw Exchange Online IT-pilot is voltooid en de eerste change management materialen zijn ontwikkeld, beoordeeld en verfijnd.

### <a name="step-3-roll-out-to-a-business-group"></a>Stap 3: uitrollen naar een bedrijfsonderdeel

Nadat u uw IT-pilot hebt voltooid, rolt u Exchange Online uit naar een business group of afdeling in uw organisatie. Als uw organisatie een on-premises e-mailservice zoals Exchange Server gebruikt, bestaat deze implementatie uit postvakmigratie. Deze implementatie moet het volgende omvatten:

- Identificatie van belangrijke bedrijfsscenario's voor Exchange Online binnen de business group.
- Aankondigingsactiviteiten om gebruikers te informeren over de verwachtingen en tijdlijnen voor Exchange Online-gebruik voor afdelingen en werk- of projectteams.
- Migratie van on-premises postvakken van uw leden van uw bedrijfsgroep naar Exchange Online.
- Gebruikerstraining [in](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) Outlook of koppelingen naar bronnen leveren om Outlook te introduceren en hoe deze te gebruiken.
- Een feedbackmechanisme, zoals een centraal team in Microsoft Teams met iedereen in het bedrijfsonderdeel, om opmerkingen te verzamelen en te reageren op problemen van gebruikers.

Tijdens de implementatie kunt u het materiaal voor veranderingenbeheer verfijnen, ter voorbereiding op de implementatie in de hele organisatie.

#### <a name="result"></a>Resultaat

Een business group is operationeel met Outlook en Exchange Online en de change management materialen zijn getest en verfijnd.

## <a name="phase-3-drive-value"></a>Fase 3: voordelen benadrukken 

In deze fase voltooit u de uitrol van Exchange Online en ondersteunt u uw gebruikers om hen te helpen de voordelen ervan te realiseren.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>Stap 1: Exchange Online uitrollen naar de rest van uw organisatie

De implementatie van de rest van uw organisatie moet het volgende omvatten:

- Identificatie van belangrijke bedrijfsscenario's voor Exchange Online binnen afzonderlijke bedrijfsgroepen.
- Gebruik uw verfijnde wijzigingsbeheermaterialen voor aankondigingsactiviteiten om uw organisatie te informeren over de verwachtingen en tijdlijnen voor Exchange Online-gebruik.
- Migratie van de postvakken voor de rest van uw organisatie naar Exchange Online.
- Gebruikerstraining [user training](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) in Outlook weergeven of koppelingen naar bronnen bieden om Outlook te introduceren en hoe deze te gebruiken.
- Een feedbackmechanisme, zoals een centraal team met daarin iedereen in de organisatie, om opmerkingen en problemen van gebruikers te verzamelen. Als uw organisatie minder dan 2500 personen heeft, gebruikt u een openbaar kanaal in Teams. In andere gevallen gebruikt u een openbare groep in Yammer.

#### <a name="result"></a>Resultaat

Uw organisatie is operationeel en uw strategie voor wijzigingsbeheer is van kracht om gebruikers te informeren, te trainen en in staat te stellen Exchange Online te gebruiken.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Stap 2: gebruik meten, tevredenheid beheren en acceptatie stimuleren

Nadat u Exchange Online hebt uitgerold naar uw hele organisatie, moet u uw strategie voor change management blijven gebruiken om:

- Laat uw leiderschap Exchange Online promoten als het primaire hulpmiddel voor individuele en kortstondige communicatie en planning.
- Moedig individuen aan om het te gebruiken voor bedrijfsgroep, afdeling, werk en projectteamcommunicatie, agenda's en samenwerking.

Hier volgen enkele aanbevolen activiteiten:

- Zie [Succesfactoren voor Microsoft 365](https://aka.ms/successfactors) voor meer informatie over algemene aanbevolen procedures voor het gebruik van cloudservices. 
- Zie [Microsoft 365-rapporten in het beheercentrum](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) om inzicht te krijgen in het servicegebruik in uw organisatie. Als u geen globale beheerder voor uw organisatie bent, vraagt u iemand die een globale beheerder is om Rapportenlezer-machtigingen toe te kennen aan uw gebruikersaccount, zodat u toegang hebt tot activiteitenrapporten.
- Houd uw feedbacklocatie (een openbaar kanaal in een centraal team van Teams of Yammer) in de gaten voor problemen en feedback van personen over hun ervaringen met Exchange Online. Beantwoord vragen en problemen zo snel mogelijk om frustratie te voorkomen en steun voor de uitrol te tonen.
- Identificeer en koester kampioenen in elke bedrijfsgroep en benadruk hun aanbevolen procedures met Outlook. Toon hun succes aan de rest van de organisatie om projectsucces en adoptie te tonen. Goedkeuring door technische leiders binnen een business group kan een krachtige invloed uitoefenen op leiders en collega's.

#### <a name="result"></a>Resultaat

Uw organisatie heeft Exchange Online en Outlook aangenomen als de primaire individuele en kleine groep korte-levende communicatie- en planningstool voor korte duur.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Hoe Microsoft omgaat met Microsoft 365 Enterprise

Zie:

- [Microsoft migrates 150,000 mailboxes to Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)(Hoe Microsoft 150.000 postvakken heeft gemigreerd naar Exchange Online)
- [Microsoft gebruikt threat intelligence om bedreigingen te beschermen, detecteren en erop te reageren](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft dwarsboomt phishing-pogingen met Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>Volgende stappen

Bekijk deze bronnen voor het voortdurende onderhoud van Exchange Online:

- [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center) 
- [Controle, rapportage en berichttracering in Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)
- [Een back-up van e-mail maken in Exchange Online](https://docs.microsoft.com/exchange/back-up-email) 
