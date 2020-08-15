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
ms.openlocfilehash: 81588f803813d0da938d709e93e26b7dadc3b993
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695724"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Roadmap voor einde van ondersteuning voor Project Server 2007

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Ondersteuning is beëindigd voor Office 2007-servers en-toepassingen in 2017 en u moet de planning van de migratie overwegen. Als u momenteel Project Server 2007 gebruikt, is het mogelijk dat de andere verwante producten de volgende kant-en-ondersteunings datums hadden:
  
|**Product**|**Einde van ondersteunings datum**|
|:-----|:-----|
|Project Server 2007  <br/> |10 oktober 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10 oktober 2017  <br/> |
|Project 2007 Standard  <br/> |10 oktober 2017  <br/> |
|Project 2007 Professional  <br/> |10 oktober 2017  <br/> |
   
Zie [upgraden van office 2007-servers en clientproducten](upgrade-from-office-2007-servers-and-products.md)voor meer informatie over Office 2007-servers die buiten gebruik worden gesteld.
  
## <a name="what-does-end-of-support-mean"></a>Wat betekent einde van ondersteuning?

Project Server, zoals bijna alle Microsoft-producten, heeft een ondersteuningscyclus waarbij nieuwe functies, foutoplossingen, beveiligingsfixes en dergelijke worden geboden. Deze levenscyclus duurt doorgaans tien jaar vanaf de datum van de eerste release van het product, en het einde van de levenscyclus bekend is als het einde van de ondersteuning van de producten. Aangezien Project Server 2007 het einde van de ondersteuning op 10 oktober 2017 bereikt, biedt Microsoft niet langer:
  
- Technische ondersteuning voor problemen die kunnen optreden.
    
- Oplossingen voor ontdekte problemen die gevolgen kunnen hebben voor de stabiliteit en bruikbaarheid van de server.
    
- Beveiligingscorrecties voor ontdekte beveiligingsproblemen die de server kwetsbaar kunnen maken voor beveiligingsproblemen.
    
- Tijdzone-updates.
    
De installatie van Project Server 2007 blijft na deze datum actief. Vanwege de bovenstaande wijzigingen is het echter raadzaam om te migreren van Project Server 2007 zo snel mogelijk.
  
## <a name="what-are-my-options"></a>Wat zijn mijn mogelijkheden?

Als u gebruikmaakt van Project Server 2007, moet u de volgende migratie opties verkennen:
  
- Migreren naar project online
    
- Migreren naar een nieuwere on-premises versie van Project Server (bij voorkeur Project Server 2016).
    
|**Wat is het voorkeur voor migratie naar project online?**|**Waarom migratie naar Project Server 2016**|
|:-----|:-----|
| Ik heb mobiele gebruikers.  <br/>  Kosten voor migratie zijn een grote rol (hardware, software, uren en inspanning voor implementatie, enzovoort).  <br/>  Na de migratie zijn de kosten voor het onderhouden van de omgeving een grote rol (zoals automatische updates, gegarandeerde uptime, enzovoort).  <br/> | Bedrijfsregels verhinderen me voor de exploitatie van mijn bedrijf in de Cloud.  <br/>  Ik wil zelf bepalen welke updates er in mijn omgeving worden uitgevoerd.  <br/> |
   
> [!NOTE]
> Zie [bronnen om u te helpen bij het upgraden van office 2007-servers en-clients](upgrade-from-office-2007-servers-and-products.md)voor meer informatie over opties voor het overstappen van uw Office 2007-servers. Let op: Project Server biedt geen ondersteuning voor een hybride configuratie, aangezien Project Server en project online niet dezelfde resourcegroep kunnen delen. 
  
## <a name="important-considerations-you-need-to-make-when-planning-to-migrate-from-project-server-2007"></a>Belangrijke overwegingen bij het plannen van het migreren van Project Server 2007

Als u wilt migreren van Project Server 2007, moet u rekening houden met het volgende:
  
- **Hulp vragen bij een Microsoft-partner** -upgraden van Project Server 2007 kan lastig zijn en vergt veel voorbereidingen en planning. Dit kan vooral moeilijk zijn als u niet bij het instellen bent en Project Server 2007 oorspronkelijk te configureren. Gelukkig zijn er Microsoft-partners die u kunt inschakelen voor een woonplaats, of u nu plant voor de migratie naar Project Server 2016 of voor project online. U kunt zoeken naar een Microsoft-partner voor hulp bij de migratie via het [Microsoft Partner Center](https://go.microsoft.com/fwlink/p/?linkid=841249). U kunt een lijst met alle Microsoft-partners met expertise in project samenstellen met behulp van de periode  *goud project en het portfolio beheer*  . 
    
- **Plan voor uw aanpassingen** : Houd er rekening mee dat veel van de aanpassingen die u aan uw Project Server 2007-omgeving bewerkt, mogelijk niet werken wanneer u migreert naar project server 2016 of naar project online. Er bestaan grote verschillen tussen versies van de Project Server en de vereiste besturingssystemen, databaseservers en client Webbe browsers die worden ondersteund met de nieuwere versie. U kunt in uw nieuwe omgeving uw aanpassingen testen of opnieuw opbouwen met een plan. Het plannen van de upgrade is ook een goede mogelijkheid om te verifiëren of een specifieke aanpassing echt nodig is wanneer u verder gaat. [Maak een plan voor de huidige aanpassingen tijdens het upgraden naar SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=842061) biedt een aantal belangrijke algemene informatie over het evalueren en plannen van uw huidige aanpassingen tijdens het uitvoeren van een upgrade. 
    
- **Tijd en geduld** -upgrade planning, uitvoering en testen zullen veel tijd in beslag nemen, met name als u een upgrade uitvoert naar Project Server 2016. Als u bijvoorbeeld migreert van Project Server 2007 naar Project Server 2016, moet u eerst migreren van Project Server 2007 naar Project Server 2010, uw gegevens controleren en vervolgens hetzelfde doen wanneer u naar elke volgende versie migreert. U kunt inkijken bij een Microsoft-partner om uw kosten te vergelijken met hun schatting van de tijd die het duurt voordat ze worden uitgevoerd, en op welke kosten. 
    
## <a name="migrate-to-project-online"></a>Migreren naar project online

Als u ervoor kiest om te migreren van Project Server 2007 naar project online, kunt u het volgende doen om de gegevens van uw project plan handmatig te migreren:
  
1. Sla de project plannen van Project Server 2003 op. MPP-indeling.
    
2. Open elk MPP-bestand met Project Professional 2013, Project Professional 2016 of de project online-bureaubladclient en sla het bestand op en publiceer het naar project online.
    
U kunt handmatig een PWA-configuratie maken in project online (bijvoorbeeld alle benodigde aangepaste velden of Enterprise-agenda's opnieuw maken). Microsoft-partners kunnen u ook helpen.
  
Belangrijke informatiebronnen:
  
|**Materialen**|**Beschrijving**|
|:-----|:-----|
|[Aan de slag met Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Het instellen en gebruiken van project online.  <br/> |
|[Beschrijvingen van project Online-Services](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |Informatie over de verschillende project online-abonnementen die voor u beschikbaar zijn.  <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migreren naar een nieuwere on-premises versie van Project Server

Hoewel we de beste waarde en gebruikerservaring kunnen bereiken door te migreren naar project online, begrijpen we ook dat sommige organisaties de project gegevens in een on-premises omgeving moeten bewaren. Als u ervoor kiest om uw project data on-premises te houden, kunt u de 2007-omgeving van Project Server migreren naar Project Server 2010, Project Server 2013 of Project Server 2016.
  
U wordt aangeraden om te migreren naar Project Server 2016 als u niet kunt migreren naar project online. Project Server 2016 omvat alle functies en voorlopige functies die zijn opgenomen in eerdere versies van Project Server, en de meest nauwkeurigheid van de beschikbare ervaring met project online (alhoewel sommige functies alleen beschikbaar zijn in project online).
  
Na het voltooien van elke migratie, moet u uw gegevens controleren om te controleren of de migratie is voltooid.
  
> [!NOTE]
> Als u alleen migreert naar Project Server 2010 als u beperkt bent met een on-premises oplossing, moet u er rekening mee houden dat het nog maar een paar jaar ondersteuning biedt. Project Server 2010 met Service Pack 2 einde van de ondersteunings datum is 10/13/2020. Zie voor meer informatie over einde van ondersteunings datums het [Microsoft-product levenscyclus beleid](https://go.microsoft.com/fwlink/p/?linkid=842066). 
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Hoe migreer ik naar Project Server 2016?

De architecturale verschillen tussen Project Server 2007 en Project Server 2016 voorkomt een rechtstreeks migratie traject. Dit betekent dat u de 2007-gegevens van uw project server naar de volgende opeenvolgende versie van Project Server moet migreren totdat u een upgrade uitvoert naar Project Server 2016.
  
U moet het volgende doen om een upgrade uit te voeren naar Project Server 2016:
  
1. Stap 1: migreren van Project Server 2007 naar Project Server 2010.
    
2. Stap 2: migreren van project voor 2010 naar Project Server 2013.
    
3. Stap 3: migreren van Project Server 2013 naar Project Server 2016.
    
Na het voltooien van elke migratie, moet u uw gegevens controleren om te controleren of de migratie is voltooid.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Stap 1: migreren van Project Server 2007 naar Project Server 2010

Voor uitgebreide informatie over wat u moet doen om een upgrade van Project Server 2007 naar Project Server 2010 uit te voeren, raadpleegt u de artikel [upgrade to project server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812) -inhoud op TechNet. 
  
Belangrijke informatiebronnen:
  
|**Materialen**|**Beschrijving**|
|:-----|:-----|
|[Overzicht van upgrade van Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841813) <br/> |Hier ziet u algemene informatie over wat u moet doen om een upgrade van Project Server 2007 naar Project Server 2010 uit te voeren.  <br/> |
|[Upgrade van Project Server 2010 plannen](https://go.microsoft.com/fwlink/p/?linkid=841815) <br/> |Bekijk de overwegingen bij de planning die u moet maken wanneer u een upgrade uitvoert van Project Server 2007 naar Project Server 2010, inclusief de systeemvereisten.  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Hoe kan ik een upgrade uitvoeren?

Wanneer u meer informatie wilt over de upgrade van een upgrade [naar Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812) , is het belangrijk om te weten dat er twee verschillende methoden zijn die u kunt gebruiken om een upgrade uit te voeren: 
  
- **Database-upgrade bijvoegen:** Met deze methode kunt u alleen de inhoud van uw omgeving upgraden en niet de configuratie-instellingen. U moet dit doen als u een upgrade uitvoert van Office Project Server 2007, die wordt geïmplementeerd op de hardware die alleen een 32-bits server-besturingssysteem ondersteunt. Er zijn twee typen database-upgrademethoden bijvoegen: 
    
  - **Database-een volledige upgrade bijvoegen** -de projectgegevens die zijn opgeslagen in de Office project Server 2007-databases worden gemigreerd, plus de sitegegevens van Microsoft Project Web app (PWA) die zijn opgeslagen in een SharePoint-inhouds database. 
    
  - **Database: Core-upgrade bijvoegen** : alleen de projectgegevens die zijn opgeslagen in de Project Server-databases worden gemigreerd. 
    
- **In-place upgrade**: de configuratiegegevens voor de farm en alle inhoud in de farm worden bijgewerkt naar de bestaande hardware, in een vaste volgorde. Wanneer u de in-place upgradeprocedure start, wordt de hele farm offline gehouden en zijn de websites van Microsoft Project Web app niet beschikbaar totdat de upgrade is voltooid en de server vervolgens opnieuw wordt gestart. Wanneer u een in-place upgrade hebt gestart, kunt u de upgrade niet onderbreken of de vorige versie herstellen. Het wordt ten zeerste geadviseerd om een gespiegelde afbeelding van uw productieomgeving te maken en de interne upgrade uit te voeren naar deze omgeving, en niet uw productieomgeving. 
    
Aanvullende informatiebronnen:
  
- [Superflow voor upgrade naar Microsoft Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841277)
    
- [Migratie van Project Server 2007 naar Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841278)
    
- [Upgrade overwegingen voor Project Web app-webonderdelen](https://go.microsoft.com/fwlink/p/?linkid=841276)
    
- [Project Software Development Kit (SDK)](https://go.microsoft.com/fwlink/p/?linkid=841275)
    
### <a name="step-2-migrate-to-project-server-2013"></a>Stap 2: migreren naar Project Server 2013

Na de migratie naar Project Server 2010 en controleren of uw gegevens zijn gemigreerd, is de volgende stap het migreren van uw gegevens naar Project Server 2013.
  
Voor uitgebreide informatie over wat u moet doen om een upgrade van Project Server 2010 naar Project Server 2013 uit te voeren, raadpleegt u de artikel [upgrade to project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822) -inhoud op TechNet. 
  
Belangrijke informatiebronnen:
  
|**Materialen**|**Beschrijving**|
|:-----|:-----|
|[Overzicht van het upgradeproces voor Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822) <br/> |Hier ziet u algemene informatie over wat u moet doen om een upgrade van Project Server 2010 naar Project Server 2013 uit te voeren.  <br/> |
|[Upgrade van Project Server 2013 plannen](https://go.microsoft.com/fwlink/p/?linkid=841823) <br/> |Bekijk de overwegingen bij de planning die u moet maken wanneer u een upgrade uitvoert van Project Server 2010 naar Project Server 2013, inclusief de systeemvereisten.  <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Wat u moet weten over het upgraden naar deze versie

[Nieuw in de upgrade van Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841824) geeft u enkele belangrijke wijzigingen aan voor de upgrade voor deze versie, zoals u het volgende kunt doen: 
  
- Er is geen interne upgrade naar Project Server 2013. De methode database-bijvoegen is de enige ondersteunde methode voor het upgraden van Project Server 2010 naar Project Server 2013.
    
- Tijdens het upgradeproces worden de 2010-gegevens van Project Server niet alleen geconverteerd naar Project Server 2013-indeling, maar de vier Project Server 2010-databases worden ook samengevoegd met één project web app-database.
    
- SharePoint Server 2013 en Project Server 2013 zijn gewijzigd in op claims gebaseerde verificatie van de eerdere versie. U moet overwegingen bij de upgrade doen als u gebruikmaakt van de klassieke verificatie. Zie [migreren van de klassieke modus naar op claims gebaseerde verificatie in SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=841825)voor meer informatie.
    
Aanvullende informatiebronnen:
  
- [Overzicht van het upgradeproces voor Project Server 2013](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [Databases en Project Web app-siteverzamelingen upgraden (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Diagram van upgradeproces voor Microsoft Project Server](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [De uitstekende database consolidatie, Project Server 2010 to 2013 Migration in 8 eenvoudige stappen](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Stap 3: migreren naar Project Server 2016

Na de migratie naar Project Server 2013 en controleren of uw gegevens zijn gemigreerd, is de volgende stap het migreren van uw gegevens naar Project Server 2016.
  
Voor uitgebreide informatie over wat u moet doen om een upgrade van Project Server 2013 naar Project Server 2016 uit te voeren, raadpleegt u de artikel upgrade to Project Server 2016-inhoud op TechNet.
  
Belangrijke informatiebronnen:
  
|**Materialen**|**Beschrijving**|
|:-----|:-----|
|[Overzicht van het upgradeproces voor Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841260) <br/> |Hier ziet u algemene informatie over wat u moet doen om een upgrade van Project Server 2013 naar Project Server 2016 uit te voeren.  <br/> |
|[Upgrade van Project Server 2016 plannen](https://go.microsoft.com/fwlink/p/?linkid=841826) <br/> |Bekijk de overwegingen bij de planning die u moet maken wanneer u een upgrade uitvoert van Project Server 2013 naar Project Server 2016, waaronder.  <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Wat u moet weten over het upgraden naar deze versie

[Wat u moet weten over de upgrade van Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841827) biedt u belangrijke wijzigingen voor de upgrade voor deze versie, waaronder: 
  
- Wanneer u de 2016-omgeving van Project Server maakt waarnaar u de gegevens van Project Server 2013 migreert, ziet u dat de installatiebestanden van Project Server 2016 zijn opgenomen in SharePoint Server 2016. Zie voor meer informatie [Project Server 2016 implementeren](https://go.microsoft.com/fwlink/p/?linkid=841829).
    
- Resource planningen zijn verouderd in Project Server 2016. Uw project server 2013-resource plannen worden gemigreerd naar Resourceafspraken in Project Server 2016 en in project online. Zie [overzicht: resource afspraken](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) voor meer informatie. 
    
## <a name="migrate-from-portfolio-server-2007"></a>Migrate from Portfolio Server 2007

Project Portfolio Server 2007 is gebruikt met Project Server 2007 voor portfolio strategie, prioriteit en optimalisatie. Er is geen extra versie van Project Portfolio Server aangemaakt na deze versie. Functies voor portfoliobeheer zijn echter beschikbaar in Project Server 2016 en de Premium-versie van project online. Gegevens van de Project Portfolio Server 2007 kunnen niet worden gemigreerd. Gegevens, zoals bedrijfs drivers, moeten opnieuw worden gemaakt.
  
Andere informatiebronnen:
  
- [Service beschrijvingen van project online](https://go.microsoft.com/fwlink/p/?linkid=841280): Bekijk de functies voor portfoliobeheer die deel uitmaken van project server 2016 en project online Premium.
    
- [Migratie handleiding voor Microsoft Office Project Portfolio Server 2007](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Verwante onderwerpen

[Einde van ondersteunings schema van SharePoint Server 2007](sharepoint-2007-end-of-support.md)
  
[Bronnen om u te helpen bij het upgraden van Office 2007-servers en-clients](upgrade-from-office-2007-servers-and-products.md)
  

