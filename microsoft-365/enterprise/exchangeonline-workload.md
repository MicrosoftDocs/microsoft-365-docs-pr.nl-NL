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
description: Stap door het planningsproces voor, de uitrol en het aansturen van de waarde van Exchange Online in Microsoft 365 Enterprise in uw hele organisatie.
ms.openlocfilehash: 30ba71fbf2af684afbbffe0a2e2b1720a8eeec2c
ms.sourcegitcommit: 255e8194bb5767a9983d54d16e79d628732a1d97
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/11/2019
ms.locfileid: "42806823"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Exchange Online implementeren voor Microsoft 365 Enterprise

*Deze werkbelasting is opgenomen in zowel de E3- als E5-versies van Microsoft 365 Enterprise*

Exchange Online is uw primaire cloudservice voor e-mail en agenda's waarmee uw gebruikers kunnen samenwerken op manieren waarvoor niet realtime hoeft te worden gechat of centrale documentopslag vereist is. Exchange Online is een belangrijk onderdeel van de waarde van Built for Teamwork van Microsoft 365 Enterprise. Met Exchange Online u meer bereiken en effectiever werken met de bekende Outlook-toepassing, ongeacht op welk apparaat u zich bevindt.

Exchange Online heeft ook geavanceerde beveiligingsmogelijkheden, waaronder anti-malware en antispamfiltering om mailboxen en mogelijkheden voor het voorkomen van gegevensverlies te beschermen die voorkomen dat gebruikers per ongeluk gevoelige informatie naar onbevoegde personen verzenden. Exchange Online-beveiliging is een belangrijk element van de waarde intelligente beveiliging van Microsoft 365 Enterprise.

Zie [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)als u nieuw bent in Exchange Online.

De volgende fasen en stappen begeleiden u bij het proces van het voorogen van de rol van Exchange Online in uw organisatie, het instappen van uw organisatie naar Exchange Online door middel van een reeks progressieve implementaties en het stimuleren van het gebruik van Exchange Online en de waarde voor uw eindgebruikers.

>[!Note]
>Deze implementatie-instructies moeten alleen worden opgevolgd nadat u [fase 2-identiteit van de Microsoft 365 Enterprise-infrastructuur](identity-infrastructure.md)hebt voltooid.
>

## <a name="phase-1-envision-your-exchange-online-deployment"></a>Fase 1: Envision uw Exchange Online-implementatie

In deze fase verzamelt u de mensen voor uw Exchange Online-implementatie en bepaalt u hoe uw organisatie Exchange Online zal gebruiken om aan de bedrijfsbehoeften te voldoen.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>Stap 1: Uw Exchange Online-implementatieleden verzamelen

Voor een succesvolle implementatie van Exchange Online bovenop [fase 2-identiteit](identity-infrastructure.md) van de Microsoft 365 Enterprise foundation-infrastructuur, moet u de juiste mensen verzamelen voor invoer en feedback. Belangrijke mensen zijn zakelijke besluitvormers, IT-medewerkers zoals architecten en uitvoerders, en pleitbezorgers voor uw eindgebruikers. 

Deze drie groepen zorgen ervoor dat uw Exchange Online-implementatie overwegingen bevat die beantwoorden aan de bedrijfsbehoeften, technische aspecten van postvakmigratie en -beveiliging, en dat het resultaat iets is dat typische gebruikers zullen gebruiken.

#### <a name="result"></a>Result

Een lijst van mensen die de zakelijke, technische en eindgebruikersaspecten van uw organisatie vertegenwoordigen.

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>Stap 2: Uw businessscenario's voor Exchange Online bepalen en prioriteren

Exchange Online kan voor verschillende doeleinden worden gebruikt. U moet uitzoeken welke doeleinden op de afzonderlijke niveaus van uw organisatie, uw bedrijfsgroepen, uw afdelingen of individuele werk- en projectteams in kaart worden gebracht aan uw bedrijfsbehoeften. U moet Exchange Online targeten om uw individuele en kleine groep van korte duur communicatie- en planningsbehoeften aan te pakken. 

Een manier om de voordelen van Exchange Online te zien, is door te onderzoeken hoe individuen, een team of v-team vandaag communiceren en vervolgens een geschikt scenario te vinden dat eenvoudigere manieren biedt om te communiceren, vergaderingen te plannen en samen te werken. Houd er rekening mee dat [Microsoft Teams](teams-workload.md) mogelijk een betere keuze is voor sommige van uw samenwerkingsscenario's.

#### <a name="result"></a>Result
Een lijst met Exchange Online-scenario's die tegemoet komen aan de behoeften van uw organisatie op het plaatsen van communicatie, planning en samenwerking van korte duur.

## <a name="phase-2-onboard"></a>Fase 2: Aan boord

In deze fase plant u de technische aspecten van een Exchange Online-implementatie en begint u deze uit te rollen naar geselecteerde groepen gebruikers.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Vereisten: configuratie van identiteits- en apparaattoegang

Als u de toegang tot Exchange Online-mailboxen wilt beveiligen, moet u ervoor zorgen dat u [het toegangsbeleid](identity-access-policies.md) voor identiteit en apparaat en het [aanbevolen toegangsbeleid](secure-email-recommended-policies.md)voor Exchange Online hebt geconfigureerd.

### <a name="step-1-complete-your-technical-planning"></a>Stap 1: Voltooi uw technische planning

Voordat u begint met de technische planning, bepaalt u of u FastTrack wilt gebruiken. Als uw organisatie meer dan 50 zitplaatsen heeft en deelneemt aan een [in aanmerking komend abonnement,](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)u [FastTrack voor Microsoft 365](https://fasttrack.microsoft.com/microsoft365)gebruiken, *zonder extra kosten beschikbaar* om u te begeleiden bij het plannen, implementeren en implementeren van services. U dit werk ook zelf uitvoeren met FastTrack Onboarding Wizards, die beschikbaar zijn bij [FastTrack](https://fasttrack.microsoft.com/) zodra u zich aanmeldt met uw Microsoft 365-account.

Als u uw eigen planning doet, of in samenwerking met FastTrack, moet u bepalen of uw netwerk en organisatie klaar zijn voor Exchange Online. Het is vooral belangrijk dat u voldoet aan de exitcriteria voor [netwerken](networking-infrastructure.md) in uw funderingsinfrastructuur voor gebruikers die zijn aangesloten op uw organisatienetwerk. Besteed speciale aandacht aan internetbandbreedte, doorvoer- en verkeersvertragingen om de prestaties voor het extra verkeer voor e-mail en bijlagen op basis van Exchange Online te maximaliseren.

Gebruik deze bronnen om u voor te bereiden op de technische aspecten van een Exchange Online-implementatie: 

- [Manieren om meerdere e-mailaccounts naar Office 365 te migreren](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration) .
- [Openbare mappen van Exchange Server migreren naar Exchange Online](https://docs.microsoft.com/Exchange/collaboration/public-folders/migrate-to-exchange-online?view=exchserver-2019)
- [Openbare mappen van Exchange Server migreren naar Office 365-groepen](https://docs.microsoft.com/Exchange/collaboration/public-folders/batch-migration-to-office-365-groups?view=exchserver-2019)
- [Samenwerking in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/collaboration-exo)
- [Ontvangers in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/recipients-in-exchange-online)
- [Outlook voor iOS en Android](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android)

Voor een beter begrip van de beveiliging in Exchange Online, bekijk de volgende bronnen:

- [Machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- [Beveiliging en naleving voor Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance) 
- [Bescherming tegen ongewenste e-mail en malware](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

Gebruik vervolgens deze bronnen om inzicht te krijgen in Exchange Online-postvakbeheer:

- [Gebruikerspostvakken maken in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/create-user-mailboxes)
- [Gebruikerspostvakken beheren](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 
- [Distributiegroepen maken en beheren](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)

#### <a name="result"></a>Result

U begrijpt de migratie, beveiliging en het beheer van postvaken en bent klaar om Exchange Online uit te rollen naar geselecteerde groepen in uw organisatie.

### <a name="step-2-run-an-it-pilot"></a>Stap 2: Voer een IT-piloot uit

Voor de meeste middelgrote en grote organisaties moet u een IT-pilot uitvoeren met uw stakeholders uit fase 1, early adopters en technische liefhebbers. Tijdens de IT-pilot:

- Geef uw deelnemers aan de piloot Microsoft 365-licenties en migreer hun on-premises mailboxen naar Exchange Online.
- Geef uw deelnemers aan de piloot een reeks oefeningen om Exchange Online-e-mail, planning en andere mogelijkheden te testen.
- Bepaal uw strategie voor wijzigingsbeheer en produceer materialen om de acceptatie van gebruikers in de hele organisatie van Outlook en Exchange Online te stimuleren. 
 
  Het materiaal van het veranderingsbeheer kan e-mailaankondigingstekst, interne opleidingsplannen, gangaffiches, en presentaties omvatten. Deze materialen zullen uw organisatie informeren over Exchange Online en de voordelen ervan met als doel het verhogen van de bewustwording en het stimuleren van het gebruik. Zie het [artikel change management strategie voor Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) voor sommige ideeën.

- Laat uw IT-pilotdeelnemers het materiaal voor verandermanagement bekijken op basis van hun ervaringen. Ze kunnen tips geven over best practices en advies over hoe je de voordelen van Outlook en Exchange Online het beste beschrijven en hoe je deze gebruiken voor communicatie en planning.

#### <a name="result"></a>Result

Uw Exchange Online IT-pilot is voltooid en de eerste materialen voor veranderingsbeheer zijn ontwikkeld, beoordeeld en verfijnd.

### <a name="step-3-roll-out-to-a-business-group"></a>Stap 3: Uitrollen naar een bedrijfsgroep

Nadat u uw IT-pilot hebt voltooid, rolt u Exchange Online uit naar een bedrijfsgroep of -afdeling in uw organisatie. Als uw organisatie een on-premises e-mailservice zoals Exchange Server gebruikt, bestaat deze implementatie uit postvakmigratie. Deze uitrol moet bestaan uit:

- Identificatie van belangrijke bedrijfsscenario's voor Exchange Online binnen de business group.
- Aankondigingsactiviteiten om gebruikers te informeren over de verwachtingen en tijdlijnen voor Exchange Online-gebruik voor afdelingen en werk- of projectteams.
- Migratie van on-premises postvakken van uw leden van uw bedrijfsgroep naar Exchange Online.
- Gebruikerstraining [user training](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) in Outlook of koppelingen naar bronnen leveren om Outlook te introduceren en hoe u deze gebruiken.
- Een feedbackmechanisme, zoals een centraal Microsoft Teams-team dat iedereen in de bedrijfsgroep bevat, om opmerkingen te verzamelen en te reageren op problemen van gebruikers in de bedrijfsgroep.

Tijdens de uitrol u uw change management materialen verfijnen ter voorbereiding op de organisatiebrede uitrol.

#### <a name="result"></a>Result

Een business group is operationeel met Outlook en Exchange Online en het materiaal voor wijzigingsbeheer is getest en verfijnd.

## <a name="phase-3-drive-value"></a>Fase 3: Schijfwaarde

In deze fase voltooit u de uitrol van Exchange Online en ondersteunt u uw gebruikers om hen te helpen de voordelen ervan te realiseren.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>Stap 1: Exchange Online uitrollen naar de rest van uw organisatie

De uitrol naar de rest van uw organisatie moet bestaan uit:

- Identificatie van belangrijke bedrijfsscenario's voor Exchange Online binnen afzonderlijke bedrijfsgroepen.
- Gebruik uw verfijnde wijzigingsbeheermaterialen voor aankondigingsactiviteiten om uw organisatie te informeren over de verwachtingen en tijdlijnen voor Exchange Online-gebruik.
- Migratie van de mailboxen voor de rest van uw organisatie naar Exchange Online.
- Gebruikerstraining [user training](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) in Outlook bieden of koppelingen naar bronnen bieden om Outlook te introduceren en hoe u deze gebruiken.
- Een feedbackmechanisme, zoals een centraal team dat iedereen bevat, om opmerkingen en problemen van gebruikers van organisaties te verzamelen. Als uw organisatie minder dan 2500 personen heeft, gebruikt u een openbaar kanaal in Teams. Gebruik anders een openbare groep in Yammer.

#### <a name="result"></a>Result

Uw organisatie is operationeel en uw change management strategie is op zijn plaats om te informeren, trainen en gebruikers in staat stellen om Exchange Online te gebruiken.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Stap 2: Meet het gebruik, beheer tevredenheid en stimuleer adoptie

Nadat u Exchange Online hebt uitgerold naar uw hele organisatie, moet u uw strategie voor veranderbeheer blijven gebruiken om:

- Laat uw leiderschap Exchange Online promoten als de primaire tool voor individuele en kortstondige communicatie en planning.
- Moedig individuen aan om het te gebruiken voor business group, afdelings-, werk- en projectteamcommunicatie, agenda's en samenwerking.

Hier zijn enkele voorgestelde activiteiten:

- Zie [Succesfactoren voor Office 365](https://aka.ms/successfactors) voor meer informatie over algemene aanbevolen procedures voor de acceptatie van cloudservices. 
- Zie [Office 365-activiteitenrapporten](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) om inzicht te krijgen in het gebruik van Office 365-service in uw hele organisatie. Als u geen globale beheerder van Office 365 voor uw organisatie bent, vraagt u iemand die een globale beheerder is om rapportenlezermachtigingen toe te kennen aan uw gebruikersaccount, zodat u toegang hebt tot activiteitenrapporten.
- Houd uw feedbacklocatie (een openbaar kanaal in een centraal team teams of Yammer) in de gaten op problemen en feedback van individuen over hun ervaringen met Exchange Online. Beantwoord vragen en problemen zo snel als je om gefrustreerde individuen te voorkomen en steun voor de uitrol aan te tonen.
- Identificeer en koester kampioenen in elke bedrijfsgroep en benadruk hun best practices met Outlook. Weerspiegelen hun successen aan de organisatie om projectsucces en adoptie te tonen. Goedkeuring door technische leiders binnen een business group kan een krachtige invloed uitoefenen op leiders en collega's.

#### <a name="result"></a>Result

Uw organisatie heeft Exchange Online en Outlook overgenomen als primaire individuele en kleine groep communicatie- en planningstool van korte duur.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Hoe Microsoft microsoft 365 Enterprise doet

Als u binnen Microsoft wilt gluren en wilt weten hoe we zijn gemigreerd naar Exchange Online en Exchange Online Protection gebruiken om te beschermen tegen cyberaanvallen, raadpleegt u:

- [Microsoft migreert 150.000 postvakken naar Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft gebruikt threat intelligence om bedreigingen te beschermen, te detecteren en erop te reageren](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft dwarsboomt phishingpogingen met Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>Volgende stappen

Bekijk deze bronnen voor het voortdurende onderhoud van Exchange Online:

- [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center) 
- [Monitoring, rapportage en het traceren van berichten in Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)
- [Een back-up maken van e-mail in Exchange Online](https://docs.microsoft.com/exchange/back-up-email) 
