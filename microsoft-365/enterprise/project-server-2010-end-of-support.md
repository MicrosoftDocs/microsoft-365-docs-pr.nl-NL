---
title: Routekaart voor einde van ondersteuning van Project Server 2010
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
description: Ondersteuning voor Project Server 2010 eindigt op 13 april 2021. Gebruik dit artikel als leidraad bij een upgrade naar project online of een nieuwere versie van de on-premises versie van Project Server.
ms.openlocfilehash: 2cf18c5e91c095c92230a33f1b8a19fa26840777
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464322"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Einde van ondersteunings schema van Project Server 2010

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Project Server 2010 krijgt het einde van de ondersteuning op **13 April 2021**. Deze datum is verlengd vanaf het vorige einde van de ondersteunings datum van 13 oktober 2020. Als u momenteel Project Server 2010 gebruikt, zijn deze andere verwante producten de volgende einden van de ondersteunings datums:

|Product |Einde van ondersteunings datum|
|---|---|
|Project 2010 Standard|13 oktober 2020|
|Project 2010 Professional|13 oktober 2020|

Zie [upgraden van office 2010-servers en clientproducten](plan-upgrade-previous-versions-office.md)voor meer informatie over Office 2010-servers die binnenkort niet meer worden ondersteund.

## <a name="what-does-end-of-support-mean"></a>Wat betekent einde van ondersteuning?

Project Server, zoals bijna alle Microsoft-producten, heeft een ondersteunings levenscyclus waarmee we nieuwe functies, foutoplossingen en beveiligingsupdates bieden. Deze levenscyclus duurt doorgaans tien jaar vanaf de datum van de eerste release van het product, en het einde van de levenscyclus bekend is als het einde van de ondersteuning van de producten. Wanneer Project Server 2010 het einde van de ondersteuning op 13 april 2021 bereikt, biedt Microsoft niet langer:

- Technische ondersteuning voor problemen die kunnen optreden.

- Oplossingen voor ontdekte problemen die gevolgen kunnen hebben voor de stabiliteit en bruikbaarheid van de server.

- Beveiligingscorrecties voor ontdekte beveiligingsproblemen die de server kwetsbaar kunnen maken voor beveiligingsproblemen.

- Tijdzone-updates.

De installatie van Project Server 2010 blijft na deze datum actief. Vanwege de bovenstaande wijzigingen is het echter raadzaam om te migreren van Project Server 2010 zo snel mogelijk.

## <a name="what-are-my-options"></a>Wat zijn mijn mogelijkheden?

Als u gebruikmaakt van Project Server 2010, moet u de volgende migratie opties verkennen:

- Migreren naar project online

- Migreren naar een nieuwere on-premises versie van Project Server (bij voorkeur Project Server 2019).

Dit zijn de twee paden die u kunt nemen om te voorkomen dat de ondersteuning van Project Server 2010 wordt beëindigd.

![Upgradepaden van Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Waarom wordt de migratie naar Project Server 2019 liever gemigreerd?|Wat is het voorkeur voor migratie naar project online?|
|---|---|
|Bedrijfsregels verhinderen me voor de exploitatie van mijn bedrijf in de Cloud.  <br/>  Ik wil zelf bepalen welke updates er in mijn omgeving worden uitgevoerd.|Ik heb mobiele of externe gebruikers.  <br/>  Kosten voor het migreren van on-premises servers is een grote bezorgdheid (hardware, software, uren en inspanning voor implementatie, enzovoort).  <br/>  Na de migratie zijn de kosten voor het onderhouden van de omgeving een grote rol (zoals automatische updates, gegarandeerde uptime, enzovoort).|

> [!NOTE]
> Zie [bronnen om u te helpen bij het upgraden van office 2010-servers en-clients](upgrade-from-office-2010-servers-and-products.md)voor meer informatie over opties voor het overstappen van uw Office 2010-servers. Let op: Project Server biedt geen ondersteuning voor een hybride configuratie, aangezien Project Server en project online niet dezelfde resourcegroep kunnen delen.

### <a name="what-are-my-options-for-project-client"></a>Wat zijn de opties voor project client?

Als u gebruikmaakt van Project Professional 2010 of Project Standard 2010 en u de migratie opties wilt verkennen, hebt u de volgende mogelijkheden:

- Overstappen op een nieuwere versie van Project Professional of Project Standard.
- Overstappen op een online oplossing zoals project online of project voor het web.

#### <a name="moving-to-a-newer-version-of-project-client"></a>Overstappen op een nieuwere versie van project client

Als u migreert van Project Standard 2010, kunt u migreren naar een nieuwere versie van Project Standard (Project Standard 2016 of Project Standard 2019).  We raden u aan om te overstappen op de nieuwste versie om te profiteren van de nieuwste functies en functionaliteit. Ook wanneer u naar een minder recente versie (Project Standard 2016) migreert, moet u de gegevens van deze versie sneller migreren wanneer het einde van de ondersteunings datum wordt weergegeven.

Als u migreert van Project Professional 2010, kunt u er ook voor kiezen om te migreren naar een nieuwere versie (Project Professional 2019 of Project Professional 2016). We raden u aan indien mogelijk naar de nieuwste versie te overstappen.  Als u Project Professional gebruikt om verbinding te maken met Project Server, moet u ervoor zorgen dat u migreert naar een versie van Project Professional die wordt ondersteund om verbinding te maken met de versie van Project Server die u gebruikt.

Gebruikers van Project Professional 2010 kunnen ook kiezen voor het migreren naar de project online-bureaubladclient. Het is een abonnementsversie van Project Professional 2019 en is opgenomen in Project abonnement 3 en project abonnement 5-abonnementen.

#### <a name="moving-to-an-online-solution"></a>Overstappen op een online oplossing

U kunt er ook voor kiezen om te migreren van Project Professional 2010 of Project Standard 2010 naar de online oplossingen van project op basis van een abonnement. Zowel project plan 3 als abonnement 5 omvat project online en de laatste Cloud aanbieding, [project voor het web](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1). Beide bieden een aantal nieuwe functies en voordelen die van alles te ontdekken zijn.

Zie de beschrijving van de [Microsoft Project-service](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description)voor meer informatie over functies die in beide gevallen zijn opgenomen en van de licenties voor het project abonnement waarop ze zijn opgenomen.

## <a name="important-considerations-you-need-to-make-when-planning-to-migrate-from-project-server-2010"></a>Belangrijke overwegingen bij het plannen van het migreren van Project Server 2010

Als u wilt migreren van Project Server 2010, moet u rekening houden met het volgende:

- **Hulp vragen bij een Microsoft Solution Provider** -upgraden van Project Server 2010 kan een uitdaging zijn en veel voorbereidingen en planningen vereisen. Dit kan vooral moeilijk zijn als u niet bij het instellen bent en Project Server 2010 oorspronkelijk te configureren. Gelukkig zijn Microsoft Solution Providers die u kunt inschakelen voor een woonplaats, ongeacht of u migreert naar Project Server 2019 of project online. U kunt zoeken naar een Microsoft Solution Provider voor hulp bij de migratie op het [Microsoft Solution Provider Center](https://go.microsoft.com/fwlink/p/?linkid=841249).

- **Plan voor uw aanpassingen** : Houd er rekening mee dat veel van de aanpassingen die u aan uw Project Server 2010-omgeving bewerkt, mogelijk niet werken wanneer u migreert naar project server 2019 of naar project online. Er bestaan grote verschillen tussen versies van de Project Server en de vereiste besturingssystemen, databaseservers en client Webbe browsers die worden ondersteund met de nieuwere versie. U kunt in uw nieuwe omgeving uw aanpassingen testen of opnieuw opbouwen met een plan. Het plannen van de upgrade is ook een goede mogelijkheid om te verifiëren of een specifieke aanpassing echt nodig is wanneer u verder gaat. [Maak een plan voor de huidige aanpassingen tijdens het upgraden naar SharePoint 2013]( https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013) biedt een aantal belangrijke algemene informatie over het evalueren en plannen van uw huidige aanpassingen tijdens het uitvoeren van een upgrade.

- **Tijd en geduld** -upgrade planning, uitvoering en testen kost veel tijd en moeite, met name als u een upgrade uitvoert naar Project Server 2019. Als u bijvoorbeeld migreert van Project Server 2010 naar Project Server 2019, moet u eerst migreren van Project Server 2010 naar Project Server 2013, de gegevens controleren en vervolgens hetzelfde doen wanneer u naar elke volgende versie (naar Project Server 2016 en vervolgens Project Server 2019) migreert. Neem contact op met een Microsoft Solution Provider als u de geraamde kosten wilt vergelijken met hun schatting van de hoeveelheid tijd die het duurt voordat het bedrag wordt uitgekeerd en op welke kosten.

## <a name="migrate-to-project-online"></a>Migreren naar project online

Als u ervoor kiest om te migreren van Project Server 2010 naar project online, kunt u het volgende doen om de gegevens van uw project plan handmatig te migreren:

1. Sla de project plannen van Project Server 2010 op. MPP-indeling.

2. Open elk MPP-bestand met Project Professional 2016, Project Professional 2019 of de project online-bureaubladclient en sla het bestand op en publiceer het naar project online.

U kunt handmatig een PWA-configuratie maken in project online (bijvoorbeeld alle benodigde aangepaste velden of Enterprise-agenda's opnieuw maken). Microsoft Solution Providers kan u ook helpen.

Belangrijke informatiebronnen:

|Materialen|Beschrijving|
|---|---|
|[Aan de slag met Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Het instellen en gebruiken van project online.|
|[Servicebeschrijving van Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088)|Informatie over de verschillende project online-abonnementen die voor u beschikbaar zijn.|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migreren naar een nieuwere on-premises versie van Project Server

Hoewel we de beste waarde en gebruikerservaring kunnen bereiken door te migreren naar project online, begrijpen we ook dat sommige organisaties de project gegevens in een on-premises omgeving moeten bewaren. Als u ervoor kiest om uw project data on-premises te houden, kunt u de 2010-omgeving van Project Server migreren naar Project Server 2013, Project Server 2016 of Project Server 2019.

U wordt aangeraden om te migreren naar Project Server 2019 als u niet kunt migreren naar project online. Project Server 2019 omvat de belangrijkste functies en de beschikbare functies van de eerdere releases van Project Server, en de meest nauwkeurigheid van de beschikbare ervaring met project online (weliswaar sommige functies zijn alleen beschikbaar in project online).

Na het voltooien van elke migratie, moet u uw gegevens controleren om te controleren of de migratie is voltooid.

> [!NOTE]
> Als u alleen migreert naar Project Server 2013 als u beperkt bent met een on-premises oplossing, moet u er rekening mee houden dat het nog maar een paar jaar ondersteuning biedt. Project Server 2013 met Service Pack 2 einde van de ondersteunings datum is 10/13/2023. Zie voor meer informatie over einde van ondersteunings datums het [Microsoft-product levenscyclus beleid](https://go.microsoft.com/fwlink/p/?linkid=842066).

### <a name="how-do-i-migrate-to-project-server-2019"></a>Hoe migreer ik naar Project Server 2019?

De architecturale verschillen tussen Project Server 2010 en Project Server 2019 voorkomt een rechtstreeks migratie traject. Dit betekent dat u de 2010-gegevens van uw project server naar de volgende opeenvolgende versie van Project Server moet migreren totdat u een upgrade uitvoert naar Project Server 2019.

U moet de volgende stappen uitvoeren om Project Server 2010 te upgraden naar Project Server 2019:

1. Migreren naar Project Server 2013.

2. Migreren van project voor 2013 naar Project Server 2016.

3. Migreren van Project Server 2016 naar Project Server 2019.

Na het voltooien van elke migratie, moet u uw gegevens controleren om te controleren of de migratie is voltooid.


### <a name="step-1-migrate-to-project-server-2013"></a>Stap 1: migreren naar Project Server 2013

De eerste stap bij het migreren van uw Project Server 2010-gegevens naar Project Server 2019 is eerst te migreren naar Project Server 2013.

Zie [upgraden naar Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)voor uitgebreide informatie over wat u moet doen om een upgrade uit te voeren van project Server 2010 naar project server 2013.

Belangrijke informatiebronnen:

- [Overzicht van het upgradeproces voor Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Hier ziet u algemene informatie over wat u moet doen om een upgrade van Project Server 2010 naar Project Server 2013 uit te voeren.
- [Upgrade van Project Server 2013 plannen](https://go.microsoft.com/fwlink/p/?linkid=841823)

  Bekijk de overwegingen bij de planning die u moet maken wanneer u een upgrade uitvoert van Project Server 2010 naar Project Server 2013, inclusief de systeemvereisten.

[Nieuw in de upgrade van Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841824) geeft u enkele belangrijke wijzigingen aan voor de upgrade voor deze versie, zoals u het volgende kunt doen:

- Er is geen interne upgrade naar Project Server 2013. De methode database-bijvoegen is de enige ondersteunde methode voor het upgraden van Project Server 2010 naar Project Server 2013.

- Tijdens het upgradeproces worden de 2010-gegevens van Project Server niet alleen geconverteerd naar Project Server 2013-indeling, maar de vier Project Server 2010-databases worden ook samengevoegd met één project web app-database.

- SharePoint Server 2013 en Project Server 2013 zijn gewijzigd in op claims gebaseerde verificatie van de eerdere versie. U moet overwegingen bij de upgrade doen als u gebruikmaakt van de klassieke verificatie. Zie [migreren van de klassieke modus naar op claims gebaseerde verificatie in SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013)voor meer informatie.

Belangrijke informatiebronnen:

- [Overzicht van het upgradeproces voor Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [Databases en Project Web app-siteverzamelingen upgraden (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Diagram van upgradeproces voor Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [De uitstekende database consolidatie, Project Server 2010 to 2013 Migration in 8 eenvoudige stappen](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Stap 2: migreren naar Project Server 2016

Na de migratie naar Project Server 2013 en controleren of uw gegevens zijn gemigreerd, is de volgende stap het migreren van uw gegevens naar Project Server 2016.

Zie [upgraden naar Project server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)voor uitgebreide informatie over wat u moet doen om een upgrade uit te voeren van project server 2013 naar project server 2016.

Belangrijke informatiebronnen:

- [Overzicht van het upgradeproces voor Project Server 2016](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Hier ziet u algemene informatie over wat u moet doen om een upgrade van Project Server 2013 naar Project Server 2016 uit te voeren.

- [Upgrade van Project Server 2016 plannen](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  Bekijk de overwegingen bij de planning die u moet maken wanneer u een upgrade uitvoert van Project Server 2013 naar Project Server 2016.

[Wat u moet weten over de upgrade van Project Server 2016](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) geeft u belangrijke wijzigingen aan voor het upgraden naar deze versie, zoals:

- Wanneer u de 2016-omgeving van Project Server maakt waarnaar u de gegevens van Project Server 2013 migreert, ziet u dat de installatiebestanden van Project Server 2016 zijn opgenomen in SharePoint Server 2016. Zie voor meer informatie [Project Server 2016 implementeren](https://go.microsoft.com/fwlink/p/?linkid=841829).

- Resource planningen zijn verouderd in Project Server 2016. Uw project server 2013-resource plannen worden gemigreerd naar Resourceafspraken in Project Server 2016 en in project online. Zie [overzicht: resource afspraken](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) voor meer informatie.

### <a name="step-3-migrate-to-project-server-2019"></a>Stap 3: migreren naar Project Server 2019

Na de migratie naar Project Server 2016 en controleren of uw gegevens zijn gemigreerd, is de volgende stap het migreren van uw gegevens naar Project Server 2019.

Zie [upgraden naar Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)voor uitgebreide informatie over wat u moet doen om een upgrade uit te voeren van project server 2016 naar project server 2019.

Belangrijke informatiebronnen:

- [Overzicht van het upgradeproces voor Project Server 2019](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Hier ziet u algemene informatie over wat u moet doen om een upgrade van Project Server 2013 naar Project Server 2016 uit te voeren.

- [Upgrade van Project Server 2019 plannen](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Bekijk de overwegingen bij de planning die u moet maken wanneer u een upgrade uitvoert van Project Server 2016 naar Project Server 2019.

[Wat u moet weten over de upgrade van Project Server 2019](https://go.microsoft.com/fwlink/p/?linkid=841827) geeft u belangrijke wijzigingen aan voor het upgraden naar deze versie, zoals:

- Tijdens het upgradeproces worden de gegevens van de Project Server 2016-database gemigreerd naar de inhoudsdatabase van SharePoint Server 2019.  Project Server 2019 maakt geen eigen Project Server-database meer in de SharePoint server-farm.

- Na de upgrade bedenken u enkele wijzigingen in Project Web app.  Zie [Nieuw in Project Server 2019](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)voor een beschrijving van deze functies.

**Andere informatiebronnen**:

- [Service beschrijvingen van project online](https://go.microsoft.com/fwlink/p/?linkid=841280): Bekijk de functies voor portfoliobeheer die deel uitmaken van project server 2016 en project online Premium.

- [Migratie handleiding voor Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Overzicht van opties voor Office 2010-client en-servers en Windows 7

Voor een visueel overzicht van de opties voor de upgrade, migratie en verplaatsen van een upgrade, migratie en migratie van Office 2010-clients en-servers en Windows 7, raadpleegt u het [einde van de ondersteunings poster](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Afbeelding van de poster Eindgebruikersondersteuning voor Office 2010-clients en -servers en Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Deze poster van één pagina is een snelle manier om inzicht te krijgen in de verschillende paden die u kunt nemen om te voorkomen dat Office 2010-client-en Server producten en Windows 7 niet meer worden ondersteund, met voorkeurs paden en optie ondersteuning in Microsoft 365 Enterprise gemarkeerd.

U kunt deze poster ook [downloaden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) en afdrukken in de indelingen letter, Legal en tabloid (11 x 17 inch).

## <a name="related-topics"></a>Verwante onderwerpen

[Een upgrade uitvoeren van SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Upgrade van Office 2010-servers en -clients](upgrade-from-office-2010-servers-and-products.md)
