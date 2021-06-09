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
description: Op 10 oktober 2017 is de ondersteuning voor Project Server 2007, Project Portfolio Server en Project 2007 beëindigd. Gebruik dit artikel om uw upgrade nu te plannen.
ms.openlocfilehash: 12447eb2a021b3f92e3557b2c3ea87e859841346
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927346"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Roadmap voor einde van ondersteuning voor Project Server 2007

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

De ondersteuning is Office 2007-servers en -toepassingen beëindigd in 2017 en u moet rekening houden met migratieplannen. Als u op dit moment Project Server 2007 en gerelateerde producten gebruikt, noteert u de volgende datums voor het einde van de ondersteuning:
  
|**Product**|**Eind van de ondersteuningsdatum**|
|:-----|:-----|
|Project Server 2007  <br/> |10 oktober 2017  <br/> |
|Project Portfolio Server 2007  <br/> |10 oktober 2017  <br/> |
|Project 2007 Standard  <br/> |10 oktober 2017  <br/> |
|Project 2007 Professional  <br/> |10 oktober 2017  <br/> |
   
Zie Upgraden van Office [2007-servers en clientproducten](upgrade-from-office-2007-servers-and-products.md)voor meer informatie over Office 2007-servers die worden verwijderd.
  
## <a name="what-does-end-of-support-mean"></a>Wat betekent *het einde van de ondersteuning?*

De meeste Microsoft-producten hebben een ondersteuningslevenscyclus waarin ze nieuwe functies, bugfixes, beveiligingsfixes, en ga zo maar door krijgen. Deze levenscyclus duurt meestal tien jaar vanaf de eerste release van het product. Het einde van deze levenscyclus wordt het einde van de ondersteuning van het product genoemd. Omdat Project Server 2007 op 10 oktober 2017 het einde van de ondersteuning heeft bereikt, biedt Microsoft niet meer:
  
- Technische ondersteuning voor problemen die kunnen optreden.
    
- Oplossingen voor problemen die van invloed kunnen zijn op de stabiliteit en bruikbaarheid van de server.
    
- Beveiligingsfixes voor beveiligingsproblemen die de server kwetsbaar kunnen maken voor beveiligingsinbreuken.
    
- Tijdzone-updates.
    
De installatie van Project Server 2007 blijft na deze datum worden uitgevoerd. Maar vanwege de eerder genoemde wijzigingen raden we u ten zeerste aan om zo snel mogelijk van Project Server 2007 te migreren.
  
## <a name="what-are-my-options"></a>Wat zijn mijn opties?

Als u Project Server 2007 gebruikt, moet u de migratieopties verkennen:
  
- Migreren naar Project Online
    
- Migreren naar een nieuwere on-premises versie van Project Server (bij voorkeur Project Server 2016)
    
|**Waarom zou ik liever migreren naar Project Online**|**Waarom zou ik liever migreren naar Project Server 2016**|
|:-----|:-----|
| Ik heb mobiele gebruikers.  <br/> <br/>De kosten die moeten worden gemigreerd, zijn een belangrijk probleem (hardware, software, uren en inspanning om te implementeren). <br/><br/>  Na de migratie zijn de kosten voor het onderhouden van mijn omgeving een belangrijk probleem (bijvoorbeeld automatische updates, gegarandeerde uptime, etc. ).  <br/> | Met bedrijfsregels kan ik mijn bedrijf niet in de cloud bedienen.<br/><br/>  Ik heb controle nodig over updates voor mijn omgeving.  |
   
> [!NOTE]
> Zie Resources om u te helpen een upgrade uit te voeren van Office 2007-servers en -clients voor meer informatie over de opties voor het verplaatsen van uw Office [2007-servers.](upgrade-from-office-2007-servers-and-products.md) Houd er rekening Project server geen ondersteuning biedt voor een hybride configuratie, omdat Project Server en Project Online niet dezelfde resourcegroep kunnen delen. 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Belangrijke aandachtspunten bij het migreren van Project Server 2007

Houd rekening met het volgende wanneer u van plan bent te migreren van Project Server 2007:
  
- **Hulp krijgen van een Microsoft-partner:** een upgrade van Project Server 2007 kan lastig zijn en vereist veel voorbereiding en planning. Het kan vooral lastig zijn als u niet de persoon bent die Project Server 2007 heeft ingesteld. Gelukkig zijn er Microsoft-partners die u kunnen helpen, ongeacht of u van plan bent te migreren naar Project Server 2016 of om Project Online. Zoek een Microsoft-partner om te helpen bij uw migratie in het [Microsoft Partnercentrum.](https://go.microsoft.com/fwlink/p/?linkid=841249) Zoek op de term *Gold Project portfoliobeheer* om een lijst weer te geven met alle Microsoft-partners die expertise hebben in Project. 
    
- **Plan uw aanpassingen:** veel aanpassingen die u hebt aangebracht in uw Project Server 2007-omgeving werken mogelijk niet wanneer u migreert naar Project Server 2016 of Project Online. Er zijn aanzienlijke verschillen in Project serverarchitectuur tussen versies. De vereiste besturingssystemen, databaseservers en clientwebbrowsers die worden ondersteund, verschillen ook. Plan hoe u uw aanpassingen voor de nieuwe omgeving kunt testen of opnieuw kunt maken. Planning biedt ook een goede gelegenheid om na te gaan of elke aanpassing nog steeds nodig is. Zie Een plan maken voor huidige aanpassingen tijdens de upgrade naar SharePoint [2013 voor meer informatie.](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013) 
    
- **Tijd en geduld:** upgradeplanning, uitvoering en testen kost tijd en moeite, vooral als u een upgrade naar Project Server 2016. Als u bijvoorbeeld migreert van Project Server 2007 naar Project Server 2016, moet u eerst migreren naar Project Server 2010, uw gegevens controleren en hetzelfde doen wanneer u naar elke opeenvolgende versie migreert. U kunt contact op nemen met een Microsoft-partner om een schatting te krijgen van de duur en de kosten.
    
## <a name="migrate-to-project-online"></a>Migreren naar Project Online

Als u ervoor kiest om te migreren van Project Server 2007 naar Project Online, kunt u het volgende doen om uw projectplangegevens handmatig te migreren:
  
1. Sla uw projectplannen op van Project Server 2003 naar .mpp-indeling.
    
2. Open Project Professional 2013, Project Professional 2016 of de Project Online-bureaubladclient elk MPP-bestand en sla het op en publiceer het in Project Online.
    
U kunt handmatig uw Microsoft Project Web App (PWA) maken in Project Online. Maak bijvoorbeeld de benodigde aangepaste velden of bedrijfsagenda's opnieuw. Microsoft-partners kunnen ook helpen bij dit proces.
  
Belangrijke bronnen:
  
|**Resource**|**Beschrijving**|
|:-----|:-----|
|[Aan de slag met Project Online](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Het instellen en gebruiken van Project Online <br/> |
|[Project Online Servicebeschrijvingen](/office365/servicedescriptions/project-online-service-description/project-online-service-description) <br/> |Informatie over de verschillende Project Online abonnementen die voor u beschikbaar zijn <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>Migreren naar een nieuwere on-premises versie van Project Server

We zijn ervan overtuigd dat u de beste waarde en gebruikerservaring krijgt door te migreren naar Project Online. Maar we begrijpen ook dat sommige organisaties projectgegevens in een on-premises omgeving moeten bewaren. Als u ervoor kiest om uw projectgegevens on-premises te houden, kunt u uw Project Server 2007-omgeving migreren naar Project Server 2010, Project Server 2013 of Project Server 2016.
  
Als u niet kunt migreren naar Project Online, raden we u aan te migreren naar Project Server 2016. Project Server 2016 bevat alle functies van eerdere versies van Project Server. Het komt het meest overeen met de ervaring die beschikbaar is met Project Online, hoewel sommige functies alleen beschikbaar zijn in Project Online.
  
Na elke migratie moet u controleren of uw gegevens zijn gemigreerd.
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Hoe kan ik migreren naar Project Server 2016?

Architectuurverschillen tussen Project Server 2007 en Project Server 2016 voorkomen een direct migratiepad. U moet dus uw gegevens Project Server 2007 migreren naar elke opeenvolgende versie van Project Server totdat u de Project Server 2016.
  
Volg de volgende stappen om Project Server 2016:
  
1. Migreren van Project Server 2007 naar Project Server 2010.
    
2. Migreren van Project Serve 2010 naar Project Server 2013.
    
3. Migreren van Project Server 2013 naar Project Server 2016.
    
Na elke migratie moet u ervoor zorgen dat uw gegevens zijn gemigreerd.
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>Stap 1: Migreren van Project Server 2007 naar Project Server 2010

Zie Upgraden naar Project Server 2010 voor een uitgebreide beschrijving van wat u moet doen om te upgraden van Project Server 2007 naar Project Server [2010.](/previous-versions/office/project-server-2010/gg502590(v=office.14))
  
Belangrijke bronnen:
  
|**Resource**|**Beschrijving**|
|:-----|:-----|
|[Project Overzicht van upgrade van Server 2010](/previous-versions/office/project-server-2010/ee662496(v=office.14)) <br/> |Een weergave op hoog niveau van wat u moet doen om te upgraden van Project Server 2007 naar Project Server 2010 <br/> |
|[Upgraden naar Project Server 2010](/previous-versions/office/project-server-2010/ff603505(v=office.14)) <br/> |Planningsoverwegingen bij het upgraden van Project Server 2007 naar Project Server 2010, inclusief systeemvereisten  <br/> |
   
#### <a name="how-do-i-upgrade"></a>Hoe kan ik een upgrade uitvoeren?

Zie Upgraden naar [Project Server 2010](/previous-versions/office/project-server-2010/gg502590(v=office.14))voor meer informatie. Maar het is belangrijk om te begrijpen dat er twee verschillende methoden zijn die u kunt gebruiken om een upgrade uit te voeren:
  
- **Upgrade voor database-bijlage:** Met deze methode wordt alleen de inhoud voor uw omgeving aangepast, niet de configuratie-instellingen. Dit is vereist als u een upgrade wilt uitvoeren van Office Project Server 2007 die is geïmplementeerd op hardware die alleen een 32-bits serverbesturingssysteem ondersteunt. Er zijn twee typen upgrademethoden voor database-attachs:
    
  - **Database-attach *full upgrade*** - Migreert de projectgegevens die zijn opgeslagen in de Office Project Server 2007-databases, plus de Microsoft Project Web App-sitegegevens die zijn opgeslagen in een SharePoint-inhoudsdatabase.
    
  - **Database-attach *core upgrade:*** migreert alleen de projectgegevens die zijn opgeslagen in de Project Serverdatabases.
    
- **In-place upgrade:** De configuratiegegevens voor de farm en alle inhoud op de farm worden in een vaste volgorde bijgewerkt op de bestaande hardware. Wanneer u het upgradeproces start, wordt de hele farm offline gehaald. De websites en Microsoft Project web-app-sites zijn niet beschikbaar totdat de upgrade is voltooid en vervolgens wordt de server opnieuw gestart. Nadat u een in-place upgrade hebt uitgevoerd, kunt u de upgrade niet onderbreken of terugdraaien naar de vorige versie. U kunt het beste een gespiegelde afbeelding van uw productieomgeving maken en de in-place upgrade uitvoeren naar deze omgeving, niet in uw productieomgeving. 
    
Aanvullende informatiebronnen:
  
- [SuperFlow voor Microsoft Project Server 2010 Upgrade](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Migratie van Project Server 2007 naar Project Server 2010](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Upgradeoverwegingen voor Project Web App Webonderdelen](/previous-versions/office/project-server-2010/gg314581(v=office.14))
    
- [Project Softwareontwikkelingskit (SDK)](/previous-versions/office/developer/office-2010/ms481966(v=office.14))
    
### <a name="step-2-migrate-to-project-server-2013"></a>Stap 2: Migreren naar Project Server 2013

Nadat u hebt gecontroleerd of uw gegevens zijn gemigreerd, is de volgende stap om te migreren naar Project Server 2013.
  
Zie Upgraden naar Project Server 2013 voor een uitgebreide beschrijving van wat u moet doen om een upgrade uit te voeren van Project Server 2010 naar Project Server [2013.](/project/upgrade-to-project-server-2016) 
  
Belangrijke bronnen:
  
|**Resource**|**Beschrijving**|
|:-----|:-----|
|[Overzicht van het upgradeproces Project Server 2013](/project/upgrade-to-project-server-2016) <br/> |Overzicht van wat u moet doen om te upgraden van Project Server 2010 naar Project Server 2013  <br/> |
|[Een upgrade naar Project Server 2013 plannen](/project/plan-for-upgrade-to-project-server-2016) <br/> |Planningsoverwegingen bij het upgraden van Project Server 2010 naar Project Server 2013, inclusief systeemvereisten <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Dingen die u moet weten over het upgraden naar deze versie

[Nieuw in de upgrade Project server 2013](/project/what-s-new-in-project-server-2013-upgrade) beschrijft belangrijke wijzigingen voor de upgrade voor deze versie. De meest opvallende zijn: 
  
- Er is geen in-place upgrade naar Project Server 2013. De methode database-attach is de enige ondersteunde methode voor het upgraden van Project Server 2010 naar Project Server 2013.
    
- Tijdens het upgradeproces worden niet alleen uw Project Server 2010-gegevens ge converteerd naar de Project Server 2013-indeling, maar worden ook de vier Project Server 2010-databases samengevoegd tot één Project Web App-database.
    
- In de 2013-versies zijn zowel SharePoint Server als Project Server gewijzigd in verificatie op basis van claims. Als u klassieke verificatie gebruikt, moet u rekening houden met deze factor voor uw upgrade. Zie Migreren van de klassieke modus naar verificatie op basis van claims in SharePoint [2013 voor meer informatie.](/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server)
    
Aanvullende informatiebronnen:
  
- [Overzicht van het upgradeproces Project Server 2013](/project/overview-of-the-project-server-2016-upgrade-process)
    
- [Upgrade uw databases en Project Web App-siteverzamelingen (Project Server 2013)](/project/upgrading-to-project-server-2016)
    
- [Microsoft Project Procesdiagram serverupgrade](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [De grote databaseconsolidatie, Project Server 2010-2013-migratie in 8 eenvoudige stappen](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>Stap 3: Migreren naar Project Server 2016

Nadat u hebt gecontroleerd of uw gegevens zijn gemigreerd, is de volgende stap het migreren naar Project Server 2016.
  
Zie Upgraden naar Project Server 2016 voor een uitgebreide beschrijving van wat u moet doen om te upgraden van Project Server 2013 naar [Project Server 2016.](//project/upgrading-to-project-server-2016)
  
Belangrijke bronnen:
  
|**Resource**|**Beschrijving**|
|:-----|:-----|
|[Overzicht van het Project Server 2016 upgradeproces](/previous-versions/office/project-server-2010/ee662104(v=office.14)) <br/> |Overzicht van wat u moet doen om te upgraden van Project Server 2013 naar Project Server 2016 <br/> |
|[Plan een upgrade naar Project Server 2016](/project/plan-for-upgrade-to-project-server-2016) <br/> |Planningsoverwegingen die u upgradet van Project Server 2013 naar Project Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>Dingen die u moet weten over het upgraden naar deze versie

[Dingen die u moet weten over Project Server 2016 upgrade](/project/plan-for-upgrade-to-project-server-2016) vertelt u enkele belangrijke wijzigingen voor de upgrade voor deze versie, waaronder:
  
- Wanneer u uw Project Server 2016-omgeving maakt waaraan u uw Project Server 2013-gegevens wilt migreren, worden de Project Server 2016-installatiebestanden opgenomen in SharePoint Server 2016. Zie Implementatie van [Project Server 2016.](/project/deploy-project-server-2016)
    
- Resourceplannen worden afgeschaft in Project Server 2016. Uw Project Server 2013-resourceplannen worden gemigreerd naar Resourceafspraak in Project Server 2016 en in Project Online. Zie [Overzicht: Resourceafspraak voor](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) meer informatie. 
    
## <a name="migrate-from-portfolio-server-2007"></a>Migreren van Portfolio Server 2007

Project Portfolio Server 2007 is gebruikt Project Server 2007 voor portfoliostrategie, prioritering en optimalisatie. Er zijn geen extra versies van Project Portfolio Server gemaakt na deze versie. Portfoliobeheerfuncties zijn echter beschikbaar in Project Server 2016 en de Premium versie van Project Online. Maar gegevens uit Project Portfolio Server 2007 kunnen niet worden gemigreerd naar beide. Gegevens zoals zakelijke stuurprogramma's moeten opnieuw worden gemaakt.
  
Andere bronnen:
  
- [Project Online Servicebeschrijvingen:](/office365/servicedescriptions/project-online-service-description/project-online-service-description) Bekijk de functies voor portfoliobeheer die zijn opgenomen in Project Server 2016 en Project Online Premium.
    
- [Microsoft Office Project Portfolio Server 2007-migratiehandleiding.](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>Verwante onderwerpen

[SharePoint Roadmap voor het einde van de ondersteuning van Server 2007](sharepoint-2007-end-of-support.md)
  
[Resources om u te helpen bij het upgraden van Office 2007-servers en -clients](upgrade-from-office-2007-servers-and-products.md)
