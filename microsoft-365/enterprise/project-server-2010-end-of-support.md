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
ms.openlocfilehash: 239b3d93cfa6a1184ea21225fa97732712b8eb14
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519700"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Einde van ondersteunings schema van Project Server 2010

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Project Server 2010 krijgt het einde van de ondersteuning op **13 April 2021**. Deze datum is verlengd vanaf de vorige datum van het einde van de ondersteunings datum van 13 oktober 2020. Als u momenteel Project Server 2010 gebruikt, hebben deze verwante producten de volgende einde-ondersteunings datums:

|Product |Einde van ondersteunings datum|
|---|---|
|Project 2010 Standard|13 oktober 2020|
|Project 2010 Professional|13 oktober 2020|

Zie [upgraden van Office 2010-servers en clientproducten](plan-upgrade-previous-versions-office.md)voor meer informatie over het beëindigen van ondersteuning.

## <a name="what-does-end-of-support-mean"></a>Wat betekent *einde van ondersteuning* ?

Bijna alle Microsoft-producten ondersteunings levensduur, waarover ze nieuwe functies, foutoplossingen en beveiligingsupdates krijgen. Deze levenscyclus duurt doorgaans tien jaar lang uit de eerste versie van het product. Het einde van de levenscyclus is bekend als het einde van de ondersteuning van het product. Nadat Project Server 2010 het einde van de ondersteuning op 13 april 2021 bereikt, biedt Microsoft niet langer:

- Technische ondersteuning voor problemen die kunnen optreden.

- Oplossingen voor ontdekte problemen die gevolgen kunnen hebben voor de stabiliteit en bruikbaarheid van de server.

- Beveiligingscorrecties voor ontdekte beveiligingsproblemen die de server kwetsbaar kunnen maken voor beveiligingsproblemen.

- Tijdzone-updates.

De installatie van Project Server 2010 blijft na deze datum actief. Vanwege de bovenstaande wijzigingen is het raadzaam om zo snel mogelijk van Project Server 2010 te migreren.

## <a name="what-are-my-options"></a>Wat zijn mijn mogelijkheden?

U hebt de volgende migratie opties:

- Migreren naar project online

- Migreren naar een nieuwere on-premises versie van Project Server (bij voorkeur Project Server 2019)

Dit zijn de twee paden die u kunt nemen om te voorkomen dat de ondersteuning van Project Server 2010 wordt beëindigd.

![Upgradepaden van Project Server 2010](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Waarom wordt de migratie naar Project Server 2019 liever gemigreerd?|Wat is het voorkeur voor migratie naar project online?|
|---|---|
|Bedrijfsregels verhinderen me voor de exploitatie van mijn bedrijf in de Cloud.  <br/><br/>  Ik wil zelf bepalen welke updates er in mijn omgeving worden uitgevoerd.|Ik heb mobiele of externe gebruikers.<br/><br/>  Kosten voor het migreren van on-premises servers zijn belangrijke gevolgen (hardware, software, tijd en inspanning voor implementatie, enzovoort). <br/><br/>  Na de migratie zijn de kosten voor het onderhouden van de omgeving een bezorgdheid (zoals automatische updates, gegarandeerde uptime, enzovoort).|

> [!NOTE]
> Zie [bronnen om u te helpen bij het upgraden van Office 2010-servers en-clients](upgrade-from-office-2010-servers-and-products.md)voor meer informatie over de migratie opties. Houd er rekening mee dat Project Server geen ondersteuning biedt voor hybride configuratie omdat Project Server en project online niet dezelfde resourcegroep kunnen gebruiken.

### <a name="what-are-my-options-for-project-client"></a>Wat zijn de opties voor project client?

Als u Project Professional 2010 of Project Standard 2010 gebruikt, zijn de volgende opties:

- Overstappen op een nieuwere versie van Project Professional of Project Standard
- Naar een online oplossing gaan, zoals project online of project voor het web

#### <a name="move-to-a-newer-version-of-project-client"></a>Overstappen op een nieuwere versie van project client

Als u migreert van Project Standard 2010, kunt u overstappen op een nieuwere versie van Project Standard (Project Standard 2016 of Project Standard 2019). We raden u aan om te overstappen op de nieuwste versie om gebruik te maken van de meest recente functies. Wanneer u migreert naar een minder recente versie (Project Standard 2016), betekent dit ook dat u de versie sneller moet migreren.

Als u migreert van Project Professional 2010, kunt u ook naar een nieuwere versie gaan (Project Professional 2019 of Project Professional 2016). Ga weer naar de nieuwste versie, indien mogelijk. Als u Project Professional gebruikt om verbinding te maken met Project Server, zorgt u ervoor dat u een versie van Project Professional migreert die verbinding maakt met de versie van Project Server die u gebruikt.

Gebruikers van Project Professional 2010 kunnen ook migreren naar de project online-bureaubladclient, een abonnementsversie van Project Professional 2019. Is opgenomen in Project abonnement 3 en project abonnement 5-abonnementen.

#### <a name="move-to-an-online-solution"></a>Naar een online oplossing gaan

U kunt ook migreren van Project Professional 2010 of Project Standard 2010 naar een online oplossing van project abonnement. Zowel project plan 3 als abonnement 5 omvat project online en de laatste Cloud aanbieding, [project voor het web](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1). Ze bieden nieuwe functies en voordelen die te maken hebben.

Zie voor meer informatie over functies en licenties de [Microsoft Project service-beschrijving](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description).

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Belangrijke aandachtspunten voor de migratie van Project Server 2010

Houd rekening met het volgende wanneer u wilt migreren van Project Server 2010:

- U kunt ook **hulp vragen bij een Microsoft Solution Provider** -een upgrade van Project Server 2010 kan een uitdaging zijn. Voor de voorbereiding en planning is veel meer nodig. Dit kan met name moeilijk zijn als u niet degene bent die de eerste keer Project Server 2010 hebt ingesteld. Microsoft Solution Providers zijn beschikbaar om te bepalen of u van plan bent om te migreren naar Project Server 2019 of naar project online. Zoek een oplossingsprovider in het [Microsoft Solution Provider Center](https://go.microsoft.com/fwlink/p/?linkid=841249).

- **Het plannen van aanpassingen** in uw project Server 2010-omgeving werken mogelijk niet wanneer u migreert naar project server 2019 of project online. Er bestaan belangrijke verschillen tussen versies van de Project Server-architectuur. Daarnaast zijn de vereiste besturingssystemen, databaseservers en browsers die met de versies werken, verschillend. Heb een plan voor het testen of opnieuw opbouwen van uw aanpassingen in de nieuwe omgeving. U kunt deze mogelijkheid volgen om te bepalen of bepaalde aanpassingen nog nodig zijn. Zie voor meer informatie [een plan maken voor huidige aanpassingen tijdens een upgrade naar SharePoint 2013](https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013).

- **Tijd en geduld** -upgrade planning, uitvoering en testen kost veel tijd en inspanning, met name voor een upgrade naar Project Server 2019. Als u migreert van Project Server 2010 naar Project Server 2019, moet u eerst migreren naar Project Server 2013, uw gegevens controleren en vervolgens migreren naar Project Server 2016 en vervolgens naar Project Server 2019. U kunt ook contact opnemen met een Microsoft Solution Provider voor een tijdsbestek en geschatte kosten voor de assistent.

## <a name="migrate-to-project-online"></a>Migreren naar project online

Als u ervoor kiest om te migreren van Project Server 2010 naar project online, kunt u deze stappen uitvoeren om de gegevens van uw project plan handmatig te migreren:

1. Sla de project plannen van Project Server 2010 op in de MPP-indeling.

2. Open elk MPP-bestand met Project Professional 2016, Project Professional 2019 of de project online-bureaubladclient en sla het bestand op en publiceer het naar project online.

U kunt handmatig een PWA-configuratie maken in project online (bijvoorbeeld alle benodigde aangepaste velden of Enterprise-agenda's opnieuw maken). Microsoft Solution Providers kan ook bij deze procedure worden geholpen.

Belangrijke informatiebronnen:

|Materialen|Beschrijving|
|---|---|
|[Aan de slag met Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Project online instellen en gebruiken|
|[Servicebeschrijving van Project Online](https://go.microsoft.com/fwlink/p/?linkid=829088)|Informatie over de verschillende project online-abonnementen die beschikbaar zijn|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migreren naar een nieuwere on-premises versie van Project Server

We geloven dat u de beste waarde en gebruikerservaring krijgt door te migreren naar project online. Maar we begrijpen ook dat sommige organisaties project data on-premises moeten bewaren. Als u ervoor kiest om uw project data on-premises te houden, kunt u de 2010-omgeving van Project Server migreren naar Project Server 2013, Project Server 2016 of Project Server 2019.

Als u niet kunt migreren naar project online, raden we u aan te migreren naar Project Server 2019. Project Server 2019 omvat de belangrijkste functies in vorige releases van Project Server. Dat is het meest geschikt voor de beschikbare ervaring met project online, maar sommige functies zijn alleen beschikbaar in project online.

Wanneer u elke migratie hebt voltooid, controleert u of de gegevens zijn gemigreerd.

> [!NOTE]
> Als u beperkt bent met een on-premises oplossing en alleen migreert naar Project Server 2013, is het raadzaam om deze versie slechts een paar extra jaar ondersteuning te bieden. Het einde van de ondersteunings datum voor Project Server 2013 met Service Pack 2 oktober 2023. Zie [Microsoft-product levenscyclus beleid](https://go.microsoft.com/fwlink/p/?linkid=842066)voor meer informatie over het beëindigen van ondersteunings datums.

### <a name="how-do-i-migrate-to-project-server-2019"></a>Hoe migreer ik naar Project Server 2019?

De architecturale verschillen tussen Project Server 2010 en Project Server 2019 voorkomt een direct migratie traject. Daarom moet u de 2010-gegevens van Project Server naar elke volgende versie van Project Server migreren totdat u Project Server 2019 bereikt. Stappen om Project Server 2010 te upgraden naar Project Server 2019:

1. Migreren naar Project Server 2013.

2. Migreren van project voor 2013 naar Project Server 2016.

3. Migreren van Project Server 2016 naar Project Server 2019.

Wanneer u elke migratie hebt voltooid, controleert u of de gegevens zijn gemigreerd.

### <a name="step-1-migrate-to-project-server-2013"></a>Stap 1: migreren naar Project Server 2013

Zie [upgraden naar Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)voor uitgebreide informatie over het upgraden van project Server 2010 naar project server 2013.

Belangrijke informatiebronnen:

- [Overzicht van het upgradeproces voor Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)

  U krijgt een algemeen overzicht van hoe u een upgrade uitvoert van Project Server 2010 naar Project Server 2013.
- [Upgrade van Project Server 2013 plannen](https://go.microsoft.com/fwlink/p/?linkid=841823)

  Zie overwegingen bij de planning wanneer u een upgrade uitvoert van Project Server 2010 naar Project Server 2013, inclusief de systeemvereisten.

- [Wat is er nieuw in de upgrade van Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841824) , met een belangrijke wijziging voor deze versie, waaronder:

   - Er is geen interne upgrade naar Project Server 2013. De methode database-bijvoegen is de enige ondersteunde manier om een upgrade uit te voeren van Project Server 2010 naar Project Server 2013.

   - Tijdens het upgradeproces worden de 2010-gegevens van Project Server niet alleen geconverteerd naar de Project Server 2013-indeling, maar worden de vier Project Server 2010-databases ook samengevoegd tot één project web app-database.

   - SharePoint Server 2013 en Project Server 2013 zijn gewijzigd in op claims gebaseerde verificatie van de eerdere versie. Als u de klassieke verificatie gebruikt, moet u dit overwegen wanneer u een upgrade uitvoert. Zie [migreren van de klassieke modus naar op claims gebaseerde verificatie in SharePoint 2013]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013)voor meer informatie.

Belangrijke informatiebronnen:

- [Overzicht van het upgradeproces voor Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [Databases en Project Web app-siteverzamelingen upgraden (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Diagram van upgradeproces voor Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [De uitstekende database consolidatie, Project Server 2010 to 2013 Migration in 8 eenvoudige stappen](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>Stap 2: migreren naar Project Server 2016

Wanneer u de gegevens hebt overgebracht naar Project Server 2013 en controleren of uw gegevens zijn gemigreerd, is de volgende stap het migreren naar Project Server 2016.

Zie een [upgrade uitvoeren naar Project Server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)voor meer informatie.

Belangrijke informatiebronnen:

- [Overzicht van het upgradeproces voor Project Server 2016](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Meer informatie over wat u moet doen om een upgrade uit te voeren van Project Server 2013 naar Project Server 2016.

- [Upgrade van Project Server 2016 plannen](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  Zie de overwegingen bij de planning voor het maken van een upgrade van Project Server 2013 naar Project Server 2016.

[Wat u moet weten over de upgrade van Project Server 2016](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) omvat belangrijke wijzigingen in de upgrade naar deze versie, waaronder:

- Wanneer u de 2016-omgeving van Project Server maakt, ziet u dat de installatiebestanden van Project Server 2016 in SharePoint Server 2016 zijn opgenomen. Zie voor meer informatie [Project Server 2016 implementeren](https://go.microsoft.com/fwlink/p/?linkid=841829).

- Resource planningen zijn verouderd in Project Server 2016. Uw project server 2013-resource plannen worden gemigreerd naar Resourceafspraken in Project Server 2016 en in project online. Zie [overzicht: resource afspraken](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) voor meer informatie.

### <a name="step-3-migrate-to-project-server-2019"></a>Stap 3: migreren naar Project Server 2019

Nadat u hebt gemigreerd naar Project Server 2016 en controleren of de gegevens zijn gemigreerd, is de volgende stap het migreren van uw gegevens naar Project Server 2019.

Zie een [upgrade uitvoeren naar Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)voor informatie over wat u moet doen om een upgrade uit te voeren van project server 2016 naar project server 2019.

Belangrijke informatiebronnen:

- [Overzicht van het upgradeproces voor Project Server 2019](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Hier ziet u algemene informatie over wat u moet doen om een upgrade van Project Server 2013 naar Project Server 2016 uit te voeren.

- [Upgrade van Project Server 2019 plannen](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Zie overwegingen bij de planning voor een upgrade van Project Server 2016 naar Project Server 2019.

- [Wat u moet weten over de upgrade van Project Server 2019](https://go.microsoft.com/fwlink/p/?linkid=841827)<br/><br/>Meer informatie over belangrijke wijzigingen voor het upgraden naar deze versie, waaronder:

   - Tijdens het upgradeproces worden de gegevens van de Project Server 2016-database gemigreerd naar de inhoudsdatabase van SharePoint Server 2019.  Project Server 2019 maakt geen eigen Project Server-database meer in de SharePoint server-farm.

   - Na de upgrade bedacht u enkele wijzigingen in Project Web app.  Zie [Nieuw in Project Server 2019](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)voor meer informatie.

**Andere informatiebronnen**:

- [Service beschrijvingen van project online](https://go.microsoft.com/fwlink/p/?linkid=841280): Bekijk de functies voor portfoliobeheer die deel uitmaken van project server 2016 en project online Premium.

- [Migratie handleiding voor Microsoft Office Project Portfolio Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Overzicht van opties voor Office 2010-client en-servers en Windows 7

Voor een visueel overzicht van de opties voor de upgrade, migratie en verplaatsen van een upgrade, migratie en migratie van Office 2010-clients en-servers en Windows 7, raadpleegt u het [einde van de ondersteunings poster](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Einde van de ondersteuning voor Office 2010-clients en-servers en Windows 7-poster](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

In deze poster ziet u de verschillende paden die u kunt nemen om te voorkomen dat de ondersteuning voor Office 2010-client en-Server producten en Windows 7 wordt beëindigd, waarbij de gewenste paden en optie ondersteuning in Microsoft 365 Enterprise zijn gemarkeerd.

U kunt deze poster ook [downloaden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) en afdrukken met de indeling letter, juridisch of tabloid (11 x 17).

## <a name="related-topics"></a>Verwante onderwerpen

[Een upgrade uitvoeren van SharePoint 2010](upgrade-from-sharepoint-2010.md)

[Upgrade van Office 2010-servers en -clients](upgrade-from-office-2010-servers-and-products.md)
