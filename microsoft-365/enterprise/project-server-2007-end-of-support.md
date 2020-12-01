---
title: Roadmap voor einde van ondersteuning voor Project Server 2007
ms.author: efrene
author: efrene
manager: laurawi
ms.date: 1/31/2018
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
ms.assetid: d379018f-72b7-4284-b40a-6c23c8ae38fe
description: Op 10 oktober 2017 wordt de ondersteuning beëindigd voor Project Server 2007, Project Portfolio Server en Project 2007. Gebruik dit artikel om de upgrade nu te plannen.
ms.openlocfilehash: f59b319ec39c6b2d1df0876c916332491f1bb0f6
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519797"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Roadmap voor einde van ondersteuning voor Project Server 2007

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Ondersteuning is beëindigd voor Office 2007-servers en-toepassingen in 2017 en u moet de planning van de migratie overwegen. Als u momenteel Project Server 2007 en verwante producten gebruikt, moet u rekening houden met de volgende einde-ondersteunings datums:
  
|**Product**|**Einde van ondersteunings datum**|
|:-----|:-----|
|Project Server 2007  <br/> |10 oktober 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10 oktober 2017  <br/> |
|Project 2007 Standard  <br/> |10 oktober 2017  <br/> |
|Project 2007 Professional  <br/> |10 oktober 2017  <br/> |
   
Zie [upgraden van office 2007-servers en clientproducten](upgrade-from-office-2007-servers-and-products.md)voor meer informatie over Office 2007-servers die buiten gebruik worden gesteld.
  
## <a name="what-does-end-of-support-mean"></a>Wat betekent *einde van ondersteuning* ?

De meeste Microsoft-producten hebben een ondersteuningscyclus waarover ze nieuwe functies, foutoplossingen, beveiligingsfixes en dergelijke kunnen krijgen. Deze levenscyclus duurt doorgaans tien jaar lang uit de eerste versie van het product. Het einde van de levenscyclus is bekend als het einde van de ondersteuning van het product. Aangezien Project Server 2007 het einde van de ondersteuning op 10 oktober 2017 bereikt, biedt Microsoft niet langer:
  
- Technische ondersteuning voor problemen die kunnen optreden.
    
- Oplossingen voor problemen die gevolgen kunnen hebben voor de stabiliteit en bruikbaarheid van de server.
    
- Beveiligingscorrecties voor beveiligingsproblemen die de server kwetsbaar kunnen maken voor beveiligingsproblemen.
    
- Tijdzone-updates.
    
De installatie van Project Server 2007 blijft na deze datum actief. Maar vanwege de bovenstaande wijzigingen is het raadzaam om te migreren van Project Server 2007.
  
## <a name="what-are-my-options"></a>Wat zijn mijn mogelijkheden?

Als u werkt met Project Server 2007, moet u de volgende migratie opties verkennen:
  
- Migreren naar project online
    
- Migreren naar een nieuwere on-premises versie van Project Server (bij voorkeur Project Server 2016)
    
|**Wat is het voorkeur voor migratie naar project online?**|**Waarom migratie naar Project Server 2016**|
|:-----|:-----|
| Ik heb mobiele gebruikers.  <br/> <br/>Het migreren van kosten is een belangrijke rol (hardware, software, uren en inspanning voor implementatie). <br/><br/>  Na de migratie zijn de kosten voor het onderhouden van de omgeving een grote rol (zoals automatische updates, gegarandeerde uptime, enzovoort).  <br/> | Bedrijfsregels verhinderen me voor de exploitatie van mijn bedrijf in de Cloud.<br/><br/>  Ik wil zelf bepalen welke updates er in mijn omgeving worden uitgevoerd.  |
   
> [!NOTE]
> Zie [bronnen om u te helpen bij het upgraden van office 2007-servers en-clients](upgrade-from-office-2007-servers-and-products.md)voor meer informatie over opties voor het overstappen van uw Office 2007-servers. Let op: Project Server biedt geen ondersteuning voor een hybride configuratie omdat Project Server en project online geen resourcegroep kunnen delen. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Belangrijke overwegingen bij het migreren van Project Server 2007

Houd rekening met het volgende wanneer u wilt migreren van Project Server 2007:
  
- **Hulp vragen bij een Microsoft-partner** -upgraden van Project Server 2007 kan lastig zijn en veel voorbereiding en planning nodig. Dit kan vooral moeilijk zijn als u niet degene bent die Project Server 2007 oorspronkelijk heeft ingesteld. Gelukkig zijn er Microsoft-partners die u kunnen helpen, of u van plan bent om te migreren naar Project Server 2016 of project online. Zoek naar een Microsoft-partner voor hulp bij de migratie in het [Microsoft partner centrum](https://go.microsoft.com/fwlink/p/?linkid=841249). Zoek op de term  *goud project en portfolio beheer* om een lijst weer te geven met alle Microsoft-partners die expertise hebben in project. 
    
- **Plan uw aanpassingen** -veel van de aanpassingen die u hebt aangebracht in de omgeving van Project Server 2007 werken mogelijk niet wanneer u migreert naar project server 2016 of project online. Er bestaan belangrijke verschillen tussen versies van de Project Server-architectuur. De vereiste besturingssystemen, databaseservers en clientbrowsers die worden ondersteund, zijn ook verschillend. Plan hoe u aanpassingen voor de nieuwe omgeving moet testen of opnieuw moet maken. Planning biedt ook een goede mogelijkheid om na te gaan of u de aanpassingen nog nodig hebt. Zie voor meer informatie [een plan maken voor huidige aanpassingen tijdens een upgrade naar SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=842061). 
    
- **Tijd en geduld** -upgrade planning, uitvoering en testen duurt lang en inspanning, met name als u een upgrade uitvoert naar Project Server 2016. Als u bijvoorbeeld van Project Server 2007 naar Project Server 2016 migreert, moet u eerst migreren naar Project Server 2010, uw gegevens controleren en hetzelfde doen wanneer u migreert naar elke volgende versie. Neem contact op met een Microsoft-partner als u wilt weten hoe lang deze duurt en wat de kosten kosten zijn.
    
## <a name="migrate-to-project-online"></a>Migreren naar project online

Als u ervoor kiest om te migreren van Project Server 2007 naar project online, kunt u het volgende doen om de gegevens van uw project plan handmatig te migreren:
  
1. Sla de project plannen van Project Server 2003 op in de MPP-indeling.
    
2. Open in Project Professional 2013, Project Professional 2016 of de project online-bureaubladclient elk. MPP-bestand en sla het bestand op en publiceer het naar project online.
    
U kunt de configuratie van Microsoft Project Web app (PWA) handmatig maken in project online. U kunt bijvoorbeeld alle benodigde aangepaste velden of Enterprise-agenda's opnieuw maken. Microsoft-partners kunnen ook bij deze procedure helpen.
  
Belangrijke informatiebronnen:
  
|**Materialen**|**Beschrijving**|
|:-----|:-----|
|[Aan de slag met Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Project online instellen en gebruiken <br/> |
|[Beschrijvingen van project Online-Services](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |Informatie over de verschillende project online-abonnementen die voor u beschikbaar zijn <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migreren naar een nieuwere on-premises versie van Project Server

We geloven dat u de beste waarde en gebruikerservaring krijgt door te migreren naar project online. Maar we begrijpen ook dat sommige organisaties de projectgegevens in een on-premises omgeving moeten bewaren. Als u ervoor kiest om uw project data on-premises te houden, kunt u de 2007-omgeving van Project Server migreren naar Project Server 2010, Project Server 2013 of Project Server 2016.
  
Als u niet kunt migreren naar project online, raden we u aan te migreren naar Project Server 2016. Project Server 2016 omvat alle functies van vorige releases van Project Server. Dit komt overeen met de beschikbare ervaring met project online, maar sommige functies zijn alleen beschikbaar in project online.
  
Na elke migratie dient u te controleren of de gegevens correct zijn gemigreerd.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Hoe migreer ik naar Project Server 2016?

Architecturale verschillen tussen Project Server 2007 en Project Server 2016 voorkomt een direct migratie traject. Daarom moet u de 2007-gegevens van Project Server naar elke volgende versie van Project Server migreren totdat u Project Server 2016 bereikt.
  
Voer de volgende stappen uit naar Project Server 2016:
  
1. Migreren van Project Server 2007 naar Project Server 2010.
    
2. Migreren van project voor 2010 naar Project Server 2013.
    
3. Migreren van Project Server 2013 naar Project Server 2016.
    
Controleer na elke migratie of de gegevens zijn gemigreerd.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Stap 1: migreren van Project Server 2007 naar Project Server 2010

Zie [upgraden naar Project server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812)voor een uitgebreide beschrijving van wat u moet doen om een upgrade uit te voeren van project Server 2007 naar project Server 2010.
  
Belangrijke informatiebronnen:
  
|**Materialen**|**Beschrijving**|
|:-----|:-----|
|[Overzicht van upgrade van Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841813) <br/> |Een algemeen overzicht van wat u moet doen om een upgrade uit te voeren van Project Server 2007 naar Project Server 2010 <br/> |
|[Upgrade van Project Server 2010 plannen](https://go.microsoft.com/fwlink/p/?linkid=841815) <br/> |Overwegingen bij het plannen van een upgrade van Project Server 2007 naar Project Server 2010, inclusief systeemvereisten  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Hoe kan ik een upgrade uitvoeren?

Zie [upgraden naar Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812)voor meer informatie. Maar het is belangrijk te weten dat er twee verschillende methoden zijn waarmee u een upgrade kunt uitvoeren:
  
- **Database-upgrade bijvoegen:** Met deze methode wordt de inhoud voor de omgeving alleen bijgewerkt, niet de instellingen van de configuratie. Dit is nodig als u een upgrade uitvoert van Office Project Server 2007 die wordt geïmplementeerd op de hardware die alleen een 32-bits server besturingssysteem ondersteunt. Er zijn twee typen database-upgrademethoden bijvoegen:
    
  - **Database-een *volledige upgrade* bijvoegen** -de projectgegevens die zijn opgeslagen in de Office Project Server 2007-databases worden gemigreerd en de Microsoft Project Web app-sitegegevens zijn opgeslagen in een SharePoint-inhouds database.
    
  - **Database: *Core-upgrade* bijvoegen** : alleen de projectgegevens die zijn opgeslagen in de Project Server-databases worden gemigreerd.
    
- **In-place upgrade**: de configuratiegegevens voor de farm en alle inhoud in de farm worden bijgewerkt naar de bestaande hardware in een vaste volgorde. Wanneer u het upgradeproces start, wordt de hele farm offline gehouden. De websites en de Microsoft Project Web app-sites zijn niet beschikbaar totdat de upgrade is voltooid en de server vervolgens opnieuw wordt gestart. Wanneer u een in-place upgrade hebt gestart, kunt u de upgrade niet onderbreken of de vorige versie herstellen. Het is een goed idee om een gespiegelde afbeelding van uw productieomgeving te maken en de interne upgrade uit te voeren naar deze omgeving, niet in uw productieomgeving. 
    
Aanvullende informatiebronnen:
  
- [Superflow voor upgrade naar Microsoft Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841277)
    
- [Migratie van Project Server 2007 naar Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841278)
    
- [Upgrade overwegingen voor Project Web app-webonderdelen](https://go.microsoft.com/fwlink/p/?linkid=841276)
    
- [Project Software Development Kit (SDK)](https://go.microsoft.com/fwlink/p/?linkid=841275)
    
### <a name="step-2-migrate-to-project-server-2013"></a>Stap 2: migreren naar Project Server 2013

Nadat u hebt gecontroleerd of de gegevens zijn gemigreerd, is de volgende stap het migreren naar Project Server 2013.
  
Zie [upgraden naar Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)voor een uitgebreide beschrijving van wat u moet doen om een upgrade uit te voeren van project Server 2010 naar project server 2013. 
  
Belangrijke informatiebronnen:
  
|**Materialen**|**Beschrijving**|
|:-----|:-----|
|[Overzicht van het upgradeproces voor Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822) <br/> |Overzicht van wat u moet doen om een upgrade uit te voeren van Project Server 2010 naar Project Server 2013  <br/> |
|[Upgrade van Project Server 2013 plannen](https://go.microsoft.com/fwlink/p/?linkid=841823) <br/> |Overwegingen bij het plannen van een upgrade van Project Server 2010 naar Project Server 2013, inclusief systeemvereisten <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Wat u moet weten over het upgraden naar deze versie

[Nieuwe functies in Project Server 2013 upgrade](https://go.microsoft.com/fwlink/p/?linkid=841824) beschrijving van belangrijke wijzigingen voor de upgrade voor deze versie. Dit zijn de meest opmerkelijke: 
  
- Er is geen interne upgrade naar Project Server 2013. De methode database-bijvoegen is de enige ondersteunde methode voor het upgraden van Project Server 2010 naar Project Server 2013.
    
- Tijdens het upgradeproces worden de 2010-gegevens van Project Server niet alleen geconverteerd naar de Project Server 2013-indeling, maar worden de vier Project Server 2010-databases ook samengevoegd tot één project web app-database.
    
- In de 2013-versies zijn de SharePoint-Server en Project Server gewijzigd in op claims gebaseerde verificatie. Als u de klassieke verificatie gebruikt, moet u eerst rekening houden met de volgende factor voor de upgrade. Zie [migreren van de klassieke modus naar op claims gebaseerde verificatie in SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=841825)voor meer informatie.
    
Aanvullende informatiebronnen:
  
- [Overzicht van het upgradeproces voor Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [Databases en Project Web app-siteverzamelingen upgraden (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Diagram van upgradeproces voor Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [De uitstekende database consolidatie, Project Server 2010 to 2013 Migration in 8 eenvoudige stappen](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Stap 3: migreren naar Project Server 2016

Nadat u hebt gecontroleerd of de gegevens zijn gemigreerd, is de volgende stap het migreren naar Project Server 2016.
  
Zie [upgraden naar Project server 2016](https://docs.microsoft.com//project/upgrading-to-project-server-2016)voor een uitgebreide beschrijving van wat u moet doen om een upgrade uit te voeren van project server 2013 naar project server 2016.
  
Belangrijke informatiebronnen:
  
|**Materialen**|**Beschrijving**|
|:-----|:-----|
|[Overzicht van het upgradeproces voor Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841260) <br/> |Overzicht van wat u moet doen om een upgrade uit te voeren van Project Server 2013 naar Project Server 2016 <br/> |
|[Upgrade van Project Server 2016 plannen](https://go.microsoft.com/fwlink/p/?linkid=841826) <br/> |Overwegingen bij het plannen van een upgrade van Project Server 2013 naar Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Wat u moet weten over het upgraden naar deze versie

[Wat u moet weten over de upgrade van Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841827) biedt u belangrijke wijzigingen voor de upgrade voor deze versie, waaronder:
  
- Wanneer u de 2016-omgeving van Project Server maakt waarnaar u de gegevens van Project Server 2013 migreert, worden de installatiebestanden van Project Server 2016 in SharePoint Server 2016 opgenomen. Zie voor meer informatie [Project Server 2016 implementeren](https://go.microsoft.com/fwlink/p/?linkid=841829).
    
- Resource planningen zijn verouderd in Project Server 2016. Uw project server 2013-resource plannen worden gemigreerd naar Resourceafspraken in Project Server 2016 en in project online. Zie [overzicht: resource afspraken](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) voor meer informatie. 
    
## <a name="migrate-from-portfolio-server-2007"></a>Migrate from Portfolio Server 2007

Project Portfolio Server 2007 is gebruikt met Project Server 2007 voor portfolio strategie, prioriteit en optimalisatie. Er is geen extra versie van Project Portfolio Server aangemaakt na deze versie. Functies voor portfoliobeheer zijn echter beschikbaar in Project Server 2016 en de Premium-versie van project online. Maar het is niet mogelijk dat gegevens van de Project Portfolio Server 2007 worden gemigreerd. Gegevens zoals bedrijfs drivers moeten opnieuw worden gemaakt.
  
Andere informatiebronnen:
  
- [Beschrijvingen van de project online-service:](https://go.microsoft.com/fwlink/p/?linkid=841280) Bekijk de functies voor portfoliobeheer die deel uitmaken van Project Server 2016 en project online Premium.
    
- [Migratie handleiding voor Microsoft Office Project Portfolio Server 2007.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Verwante onderwerpen

[Einde van ondersteunings schema van SharePoint Server 2007](sharepoint-2007-end-of-support.md)
  
[Bronnen om u te helpen bij het upgraden van Office 2007-servers en-clients](upgrade-from-office-2007-servers-and-products.md)
  
