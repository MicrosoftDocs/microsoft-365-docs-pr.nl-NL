---
title: SharePoint en OneDrive voor Microsoft 365 Enterprise implementeren
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/11/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: Doorloop het proces van planning, implementatie en promotie van de waarde van SharePoint binnen uw organisatie.
ms.openlocfilehash: cb0cf16df328d667d796008ac7cabfc98c21ad17
ms.sourcegitcommit: 237589a0c8a24510e5c8f3b8b4747d944ad0afbf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/20/2019
ms.locfileid: "42810401"
---
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a>SharePoint en OneDrive voor Microsoft 365 Enterprise implementeren

*Deze werkbelasting geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

Sla bestanden op en deel ze met SharePoint en Microsoft Teams. Inhoudsbeheer en samenwerking zijn belangrijke elementen van het principe Gemaakt voor teamwerk van Microsoft 365 Enterprise. 

SharePoint heeft ook geavanceerde beveiligingsfuncties, waaronder toegangsbeheer met machtigingen en versleuteling. SharePoint-beveiliging is een sleutelelement van het Intelligent Security-principe van Microsoft 365 Enterprise.

Als u nog geen ervaring hebt met SharePoint, raadpleegt u [SharePoint](https://products.office.com/sharepoint/collaboration) en [Aan de slag met SharePoint](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121).

De volgende fasen en stappen leiden u door het proces van het promoten van de rol van SharePoint in uw organisatie, het onboarden van uw organisatie door middel van een reeks progressieve implementaties en het stimuleren van gebruik en de waarde ervan voor uw eindgebruikers. Voordat u begint, moet u ervoor zorgen dat u de juiste fasen van de [basisinfrastructuur](deploy-workloads.md#foundation-infrastructure-prerequisites) hebt geconfigureerd, zodat uw SharePoint-sites de beveiligingsmogelijkheden hebben die u nodig hebt. 

Zie de [OneDrive-handleiding voor bedrijven](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) om OneDrive voor Microsoft 365 Enterprise te implementeren.

## <a name="phase-1-envision"></a>Fase 1: visie
In deze fase verzamelt u de partners in uw organisatie voor uw SharePoint-implementatie en bepaalt u hoe uw organisatie SharePoint gaat gebruiken om aan haar zakelijke behoeften te voldoen.

### <a name="step-1-gather-your-sharepoint-deployment-members"></a>Stap 1: de partners voor uw SharePoint-implementatie verzamelen

Voor een succesvolle implementatie van SharePoint op de [basisinfrastructuur van Microsoft 365 Enterprise](deploy-foundation-infrastructure.md), moet u de juiste personen verzamelen voor input en feedback. Sleutelfiguren zijn onder meer zakelijke besluitvormers, IT-personeel zoals architecten en uitvoerders, en enthousiaste eindgebruikers. 

Deze drie groepen zorgen ervoor dat uw implementatie elementen bevat die betrekking hebben op zakelijke behoeften, technische aspecten van map- en documentmigratie en beveiliging, en dat het resultaat iets is dat typische gebruikers zullen gebruiken.

#### <a name="result"></a>Resultaat

Een lijst met personen die de zakelijke, technische en eindgebruikersperspectieven van uw organisatie vertegenwoordigen.

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a>Stap 2: uw SharePoint-bedrijfsscenario's vaststellen en hieraan een prioriteit toewijzen

SharePoint kan voor verschillende doeleinden worden gebruikt. U moet uitzoeken welke doelen aansluiten bij uw zakelijke behoeften. SharePoint kan voorzien in de behoeften aan documentopslag en delen, inhoudsbeheer en samenwerking van uw teams, uw divisie of uw hele organisatie. 

Bekijk de lijst met scenario's en mogelijkheden op [SharePoint](https://products.office.com/sharepoint/collaboration ).

De volgende zakelijke pijlers kunnen voorzien in de behoeften van uw organisatie:

|||
|:-----|:-----|
| Delen en samenwerken | Maak gebruik van teamsites, Communicatiesites en synchronisatie. |
| Informeren en engageren | Informatie in de toekomst. |
| Transformeren | Maak gebruik van Flow om geautomatiseerde werkstromen tussen apps en services te maken. |
| Gemeenschappelijke kennis gebruiken | Gebruikt de zoekfunctie om de gewenste resultaten binnen uw organisatie weer te geven. |
| Beveiligen | Garandeert dat uw organisatie is beveiligd en de juiste compliance heeft. |
|||

Zie [SharePoint-beheer](https://docs.microsoft.com/sharepoint/sharepoint-online) voor informatie over het configureren van SharePoint naar uw behoeften.

Een manier om de voordelen van SharePoint te zien, is door te onderzoeken hoe individuen, een team, een divisie of uw hele organisatie vandaag met elkaar omgaan. Zoek vervolgens naar een beter scenario dat het eenvoudiger maakt om bestanden op te slaan en te delen. Houd er rekening mee dat [Microsoft Teams](teams-workload.md) mogelijk een betere keuze is voor een sommige scenario's.

#### <a name="sharepoint-site-for-highly-regulated-data"></a>SharePoint-site voor sterk gereglementeerde gegevens

Zeer gereglementeerde gegevens zijn onderhevig aan regionale voorschriften of zijn de meest waardevolle gegevens voor uw organisatie, zoals handelsgeheimen, informatie over financiën of personeel, en de organisatorische strategie. U kunt een SharePoint-site configureren voor beperkte toegang, gegevensclassificatie, preventie van gegevensverlies en versleuteling voor dit type gegevens. Zie voor meer informatie [Microsoft Teams en SharePoint-sites voor sterk gereglementeerde gegevens](teams-sharepoint-online-sites-highly-regulated-data.md).

#### <a name="result"></a>Resultaat
Een lijst met SharePoint-scenario's waarin de behoeften van uw organisatie voor het opslaan en delen van documenten, inhoudsbeheer, samenwerking en beveiliging worden geadresseerd.

## <a name="phase-2-onboard"></a>Fase 2: onboarding

In deze fase plant u de technische aspecten van een SharePoint-implementatie en begint u deze uit te rollen naar geselecteerde groepen gebruikers.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Vereisten: configuratie van identiteit en apparaattoegang

Om de toegang tot SharePoint-sites te beschermen, moet u ervoor zorgen dat u [identiteits- en apparaattoegangsbeleid](identity-access-policies.md) en het [aanbevolen SharePoint-toegangsbeleid](sharepoint-file-access-policies.md) hebt geconfigureerd.

### <a name="step-1-complete-your-technical-planning"></a>Stap 1: voltooi de technische planning

Voordat u met de technische planning begint, moet u bepalen of u FastTrack wilt gebruiken. Als uw organisatie meer dan 50 seats heeft en deelneemt aan een [in aanmerking komend plan](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), kunt u voordelen van FastTrack gebruiken. Deze zijn zonder extra kosten beschikbaar om u te helpen bij planning, migratie, implementatie en service-acceptatie. Of u kunt deze taak zelf voltooien met FastTrack Onboarding Wizards, die beschikbaar zijn bij [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) zodra u zich aanmeldt met uw Microsoft 365-account.

Als u uw eigen planning doet, of in samenwerking met FastTrack, moet u bepalen of uw netwerk en organisatie klaar zijn voor SharePoint. Het is vooral belangrijk dat u voldoet aan de [exitcriteria voor netwerken](networking-exit-criteria.md) in uw basisinfrastructuur, met speciale aandacht voor internetbandbreedte, doorvoer en onderbrekingen, om de prestaties te maximaliseren voor het extra verkeer van op SharePoint gebaseerde documenten.

Gebruik [Migreren naar SharePoint](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) om u voor te bereiden op uw SharePoint-implementatie: 

Bekijk de volgende bronnen voor een beter begrip van beveiliging in SharePoint:

-   [Hoe SharePoint en OneDrive uw gegevens in de cloud beschermen](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
-   [Gegevensversleuteling in OneDrive en SharePoint](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo)

#### <a name="result"></a>Resultaat

U begrijpt SharePoint-sites en on-premises map- en documentmigratie en -beveiliging en kunt beginnen met de implementatie van SharePoint voor geselecteerde groepen in uw organisatie.

### <a name="step-2-run-an-it-pilot"></a>Stap 2: een IT-pilot uitvoeren

In de meeste middelgrote en grote organisaties moet u een IT-pilot uitvoeren met de belanghebbenden uit fase 1, early adopters en technische enthousiastelingen. Tijdens de IT-pilot:

- Kies een zakelijk scenario voor SharePoint waarmee deelnemers aan de IT-pilot kunnen oefenen.
- Geef uw pilot-deelnemers een reeks oefeningen om SharePoint-documentopslag, delen, samenwerking en andere mogelijkheden te testen.
- Bepaal uw verandermanagementstrategie en produceer materialen om organisatiebrede gebruikersacceptatie van SharePoint te stimuleren. Materiaal voor verandermanagement kan bestaan uit e-mailaankondigingen, interne trainingsplannen, gangposters en presentaties. Deze materialen informeren uw organisatie over SharePoint en de voordelen ervan met als doel het bewustzijn te vergroten en het gebruik te stimuleren. Bekijk de [SharePoint-adoptiebronnen](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/) om aan de slag te gaan.
- Laat de deelnemers aan de IT-pilot het materiaal voor veranderingsbeheer beoordelen op basis van hun ervaringen. Ze kunnen tips geven over aanbevolen procedures en advies geven over hoe de voordelen van SharePoint het beste kunnen worden beschreven en hoe deze te gebruiken.

#### <a name="result"></a>Resultaat

Uw SharePoint IT-pilot is voltooid en de eerste materialen voor wijzigingsbeheer zijn ontwikkeld, beoordeeld en verfijnd.

### <a name="step-3-roll-out-to-a-business-group"></a>Stap 3: uitrollen naar een bedrijfsonderdeel

Na het voltooien van uw IT-pilot, rolt u SharePoint uit naar een bedrijfsonderdeel of afdeling in uw organisatie. Deze implementatie moet het volgende omvatten:

- Identificatie van de belangrijkste bedrijfsscenario's voor SharePoint binnen afzonderlijke bedrijfsonderdelen.
- Aankondigingsactiviteiten om gebruikers te informeren over de verwachtingen en tijdlijnen voor SharePoint-gebruik voor afdelingen en voor werk- of projectteams.
- Migratie van on-premises mappen en documenten van de leden van uw bedrijfsonderdeel naar SharePoint.
- Gebruikerstraining geven of koppelingen naar bronnen bieden die SharePoint introduceren en uitleg geven over hoe het te gebruiken. Zie [videotraining voor SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23).
- Een feedbackmechanisme, zoals een centraal team in Microsoft Teams met iedereen in het bedrijfsonderdeel, om opmerkingen te verzamelen en te reageren op problemen van gebruikers.
 
Tijdens de implementatie kunt u het materiaal voor veranderingenbeheer verfijnen, ter voorbereiding op de implementatie in de hele organisatie.

#### <a name="result"></a>Resultaat

Een bedrijfsonderdeel gebruikt SharePoint en de materialen voor veranderingsbeheer zijn getest en verfijnd.

## <a name="phase-3-drive-value"></a>Fase 3: voordelen benadrukken 

In deze fase voltooit u de implementatie van SharePoint en helpt u uw gebruikers bij het realiseren van de voordelen.

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a>Stap 1: implementatie van de rest van uw organisatie

De implementatie van de rest van uw organisatie moet het volgende omvatten:

- Identificatie van de belangrijkste bedrijfsscenario's voor SharePoint Online binnen afzonderlijke bedrijfsonderdelen.
- Gebruik verfijnd materiaal voor wijzigingsbeheer en aankondigingen om uw organisatie te informeren over de verwachtingen en tijdlijnen voor gebruik.
- Migratie van mappen en documenten van de rest van uw organisatie naar SharePoint.
- Gebruikerstraining geven of koppelingen naar bronnen bieden die SharePoint introduceren en uitleg geven over hoe het te gebruiken.
- Een feedbackmechanisme, zoals een centraal team met daarin iedereen in de organisatie, om opmerkingen en problemen van gebruikers te verzamelen. Als uw organisatie minder dan 2500 personen heeft, gebruikt u een openbaar kanaal in Teams. In andere gevallen gebruikt u een openbare groep in Yammer.

#### <a name="result"></a>Resultaat
Uw organisatie is actief en uw strategie voor veranderingsbeheer is er om gebruikers te informeren, op te leiden en in staat te stellen SharePoint te gebruiken.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Stap 2: gebruik meten, tevredenheid beheren en acceptatie stimuleren

Nadat de implementatie naar uw hele organisatie is voltooid, moet u uw verandermanagementstrategie blijven gebruiken om:

- Laat uw managers SharePoint promoten als het belangrijkste hulpmiddel voor het opslaan en delen van documenten.
- Moedig individuen aan om het te gebruiken voor het opslaan en delen van documenten tussen bedrijfsgroepen, afdelingen en werk- en projectteams.

Hier volgen enkele aanbevolen activiteiten:

- Zie [succesfactoren voor Office 365](https://aka.ms/successfactors) voor meer informatie over algemene aanbevolen procedures voor de acceptatie van cloudservices. 
- Zie [activiteitenrapporten van Office 365](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) om inzicht te krijgen in het gebruik van de Office 365-service in uw organisatie. Als u geen globale beheerder van Office 365 bent voor uw organisatie, vraagt u iemand die een globale beheerder is om leesmachtigingen voor rapporten toe te kennen aan uw gebruikersaccount, zodat u activiteitenoverzichten kunt openen.
- Volg uw feedbackplatform (een openbaar kanaal in een centraal Teams-team of Yammer) voor problemen en feedback van individuen over hun ervaringen met SharePoint. Beantwoord vragen en problemen zo snel mogelijk om frustratie te voorkomen en steun voor de uitrol te tonen.
- Identificeer en voed kampioenen in elke bedrijfsgroep en benadruk hun prestaties en aanbevolen procedures voor het gebruik van SharePoint. Toon hun succes aan de rest van de organisatie om projectsucces en adoptie te tonen. Bekrachtiging door technische leiders binnen een bedrijfsgroep kan een krachtige werking hebben op leiderschap en collega's.

#### <a name="result"></a>Resultaat

Uw organisatie past SharePoint in Microsoft 365 Enterprise toe om de opslag en samenwerking van documenten te ondersteunen.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Hoe Microsoft omgaat met Microsoft 365 Enterprise

Voor meer informatie over hoe Microsoft zelf SharePoint heeft geïmplementeerd, zie [SharePoint naar de cloud: ontdek hoe Microsoft zijn eigen migratie heeft uitgevoerd](https://www.microsoft.com/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration).

## <a name="next-steps"></a>Volgende stappen

Raadpleeg de volgende bronnen voor het doorlopende onderhoud van SharePoint: 

- [Machtigingsniveaus in SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [SharePoint-site machtigingen aanpassen](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [Extern delen in- of uitschakelen voor SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [Toegangsaanvragen instellen en beheren](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
