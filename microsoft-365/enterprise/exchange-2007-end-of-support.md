---
title: Roadmap voor einde van ondersteuning voor Exchange 2007
ms.author: dstrome
author: dstrome
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: c3024358-326b-404e-9fe6-b618e54d977d
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Lees meer over uw opties na het einde van de ondersteuning van Exchange Server 2007 en begin met het plannen van migratie naar Microsoft 365, Office 365 of Exchange 2016.
ms.openlocfilehash: d7e8f50118dab6fcb618273f5c28497c80d4a549
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924198"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Roadmap voor einde van ondersteuning voor Exchange 2007

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Exchange Server 2007 heeft in april 2017 het einde van de ondersteuning bereikt. Als u de migratie van Exchange 2007 naar Microsoft 365, Office 365 of Exchange 2016 nog niet hebt gestart, is het nu tijd om te beginnen met plannen.
  
## <a name="what-does-end-of-support-mean"></a>Wat betekent *het einde van de ondersteuning?*

Exchange Server heeft, net als bijna alle Microsoft-producten, een ondersteuningslevenscyclus waarin we nieuwe functies, bugfixes, beveiligingsfixes, en meer bieden. Deze levenscyclus duurt meestal tien jaar vanaf de eerste release van het product. Het einde van deze levenscyclus wordt het einde van de ondersteuning van het product genoemd. Sinds Exchange 2007 op 11 april 2017 het einde van de ondersteuning heeft bereikt, biedt Microsoft niet meer:
  
- Technische ondersteuning voor problemen die kunnen optreden.
    
- Oplossingen voor problemen die van invloed kunnen zijn op de stabiliteit en bruikbaarheid van de server.
    
- Beveiligingsfixes voor beveiligingsproblemen die de server kwetsbaar kunnen maken voor beveiligingsinbreuken.
    
- Tijdzone-updates.
    
De installatie van Exchange 2007 blijft na de einddatum van de ondersteuning worden uitgevoerd. Maar omdat er geen nieuwe updates of ondersteuning zijn, raden we u ten zeerste aan zo snel mogelijk te migreren van Exchange 2007.
  
Zie Uw upgrade plannen van Office [2007-servers en -producten](upgrade-from-office-2007-servers-and-products.md)voor meer informatie over Office 2007-servers die het einde van de ondersteuning nadert.
  
## <a name="what-are-my-options"></a>Wat zijn mijn opties?

U kunt:
  
- Migreren naar Microsoft 365 met behulp van cutover-, gefaseerd of hybride migratie.
    
- Migreert uw Exchange 2007-servers naar een nieuwere versie van Exchange op uw on-premises servers.
    
In de volgende secties wordt elke optie uitgebreider verkend.
  
### <a name="migrate-to-microsoft-365"></a>Migreren naar Microsoft 365

Het migreren van uw e-mail naar Microsoft 365 is de beste en eenvoudigste optie om uw Exchange 2007-implementatie te stoppen. Met een migratie naar Microsoft 365 kunt u één hop maken van 10 jaar oude technologie naar state-of-the-art functies, waaronder:
  
- Compliancemogelijkheden, zoals bewaarbeleid, In-Place en bewaring van rechtszaken, in-place eDiscovery en meer
    
- Microsoft 365 Groepen
    
- Postvak IN met focus
    
- MyAnalytics
    
- REST-API's voor programmatische toegang tot e-mail, agenda's, contactpersonen, en meer
    
Microsoft 365 krijgt ook eerst nieuwe functies en ervaringen, zodat u en uw gebruikers ze meestal meteen kunnen gaan gebruiken. En u hoeft zich geen zorgen te maken over:
  
- Hardware aanschaffen en onderhouden.
    
- Betalen om uw servers te warmen en af te koelen.
    
- Up-to-date blijven op het gebied van beveiligings-, product- en tijdzone-oplossingen.
    
- Opslag en software onderhouden ter ondersteuning van nalevingsvereisten.
    
- Een upgrade uitvoeren naar een nieuwe versie van Exchange. Met Microsoft 365 bent u altijd op de nieuwste versie van Exchange.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>Hoe moet ik migreren naar Microsoft 365?

U hebt een paar migratieopties. U moet rekening houden met een paar dingen, waaronder:

- Het aantal stoelen of postvakken dat u moet verplaatsen.
- Hoe lang wilt u de migratie laten duren?
- Of u tijdens de migratie een naadloze integratie tussen uw on-premises installatie en Microsoft 365 nodig hebt.

In deze tabel ziet u de migratieopties en de belangrijkste factoren die bepalen welke methode moet worden gebruikt:
  

|**Migratieoptie**|**Grootte van organisatie**|**Duur**|
|:-----|:-----|:-----|
|Cutover-migratie  <br/> |Minder dan 150 zitplaatsen  <br/> |Een week of minder  <br/> |
|Gefaseerde migratie  <br/> |Meer dan 150 zitplaatsen  <br/> |Een paar weken  <br/> |
|Volledige hybride migratie  <br/> |Enkele honderden tot duizenden zitplaatsen  <br/> |Een paar maanden of meer  <br/> |
   
In de volgende secties wordt een overzicht gegeven van deze methoden. Zie Beslissen over een migratiepad voor [meer informatie.](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27) 
  
#### <a name="cutover-migration"></a>Cutover-migratie

In een cutover-migratie migreert u al uw postvakken, distributiegroepen, contactpersonen, en ga zo maar door naar Microsoft 365 op een vooraf gekozen datum en tijd. Nadat de migratie is voltooid, sluit u uw on-premises Exchange-servers af en gebruikt u Microsoft 365 uitsluitend.
  
Cutover-migratie is zeer belangrijk voor kleine organisaties die niet veel postvakken hebben, snel naar Microsoft 365 willen gaan en niet willen omgaan met enkele van de complexiteiten van de andere methoden. Maar het moet over een week of minder zijn voltooid en gebruikers moeten hun Outlook-profielen opnieuw configureren. Cutover-migratie kan maximaal 2.000 postvakken verwerken, maar we raden u ten zeerste aan deze te gebruiken om maximaal 150 postvakken te migreren. Als u meer probeert te migreren, hebt u mogelijk geen tijd meer om alle postvakken vóór de deadline over te dragen. Uw IT-ondersteuningsmedewerkers worden mogelijk overstelpt met verzoeken om gebruikers te helpen Outlook opnieuw te configureren.
  
Als u overweegt een cutover-migratie uit te gaan, zijn hier de volgende zaken waar u rekening mee moet houden:
  
- Microsoft 365 moet verbinding maken met uw Exchange 2007-servers via Outlook Anywhere via TCP-poort 443.
    
- Alle on-premises postvakken worden verplaatst naar Microsoft 365.
    
- U hebt een on-premises beheerdersaccount nodig dat toegang heeft tot de postvakken van uw gebruikers.
    
- De geaccepteerde domeinen van Exchange 2007 die u wilt gebruiken in Microsoft 365, moeten worden toegevoegd als geverifieerde domeinen in de service.
    
- Tussen de tijd dat u de migratie start en wanneer u de voltooiingsfase start, worden de Microsoft 365- en on-premises postvakken regelmatig gesynchroniseerd met Microsoft 365. Hiermee kunt u de migratie voltooien zonder dat u zich zorgen hoeft te maken dat e-mail achterblijft in uw on-premises postvakken.
    
- Gebruikers ontvangen nieuwe tijdelijke wachtwoorden voor hun Microsoft 365-accounts. Ze moeten hun wachtwoord wijzigen wanneer ze zich voor de eerste keer aanmelden bij hun postvak.
    
- U hebt een Microsoft 365-licentie nodig die Exchange Online bevat voor elk gebruikerspostvak dat u migreert.
    
- Gebruikers moeten een nieuw Outlook-profiel instellen op elk van hun apparaten en hun e-mail opnieuw downloaden. De hoeveelheid e-mail die Outlook downloadt, kan variëren. Zie Hoeveel e-mail u offline wilt houden voor [meer informatie.](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
    
Zie voor meer informatie over cutover-migratie:
  
- [Wat u moet weten over een cutover-e-mailmigratie](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Een cutover-migratie van e-mail uitvoeren](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Gefaseerde migratie

In een gefaseerd migratie hebt u een paar honderd of een paar duizend postvakken die u wilt migreren naar Microsoft 365, moet u een week of meer duren om de migratie te voltooien en hebt u geen geavanceerde hybride migratiefuncties nodig, zoals gedeelde informatie over de vrije/bezet-agenda.
  
Gefaseerd migreren is geweldig voor organisaties die meer tijd nodig hebben om hun postvakken te migreren naar Microsoft 365, maar nog steeds van plan zijn om de migratie binnen enkele weken te voltooien. U kunt postvakken in batches migreren. U kunt bepalen hoeveel postvakken en welke postvakken op een bepaald moment worden gemigreerd. U kunt postvakken van gebruikers op dezelfde afdeling batchen, bijvoorbeeld om ervoor te zorgen dat ze allemaal tegelijk worden verplaatst. Of u kunt postvakken van leidinggevenden verlaten tot de laatste batch. Net als bij cutover-migraties moeten uw gebruikers hun Outlook-profielen opnieuw maken.
  
Als u een gefaseerd migratie wilt doen, moet u hier rekening mee houden:
  
- Microsoft 365 moet verbinding maken met uw Exchange 2007-servers via Outlook Anywhere via TCP-poort 443.
    
- U hebt een on-premises beheerdersaccount nodig dat toegang heeft tot de postvakken van uw gebruikers.
    
- De geaccepteerde domeinen van Exchange 2007 die u in Microsoft 365 wilt gebruiken, moeten worden toegevoegd als geverifieerde domeinen in de service.
    
- U moet een CSV-bestand maken met de volledige naam en het e-mailadres van elk postvak dat u in een batch wilt migreren. U moet ook een nieuw wachtwoord opnemen voor elk postvak dat u migreert en dat wachtwoord naar elke gebruiker verzenden. De gebruiker wordt gevraagd het wachtwoord te wijzigen wanneer hij of zij zich de eerste keer bij het nieuwe Microsoft 365-postvak aan melden.
    
- Vanaf het moment dat u de migratiebatch start en wanneer u de voltooiingsfase start, worden de Microsoft 365- en on-premises postvakken die in de batch zijn opgenomen, regelmatig gesynchroniseerd met Microsoft 365. Hiermee kunt u de migratie voltooien zonder dat u zich zorgen hoeft te maken dat e-mail achterblijft in uw on-premises postvakken.
    
- U hebt een Microsoft 365-licentie nodig die Exchange Online bevat voor elk gebruikerspostvak dat u migreert.
    
- Gebruikers moeten een nieuw Outlook-profiel instellen op elk van hun apparaten en hun e-mail opnieuw downloaden. De hoeveelheid e-mail die Outlook downloadt, kan variëren. Zie Hoeveel e-mail u offline wilt houden voor [meer informatie.](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
    
Zie voor meer informatie over gefaseerd migratie:
  
- [Wat u moet weten over een gefaseerd e-mailmigratie](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Een gefaseerd migratie van e-mail uitvoeren](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Volledig hybride

In een volledige hybride migratie heeft uw organisatie vele honderden, tot tienduizenden postvakken en wilt u sommige of alle postvakken verplaatsen naar Microsoft 365. Omdat deze migraties meestal op langere termijn zijn, kunnen hybride migraties het volgende doen:
  
- On-premises gebruikers de agendagegevens voor vrije/drukke agenda's voor gebruikers in Microsoft 365 en vice versa.
    
- Zie een geïntegreerde algemene adreslijst met geadresseerden in zowel on-premises als Microsoft 365.
    
- Bekijk de volledige eigenschappen van outlook-geadresseerden voor alle gebruikers, ongeacht of ze on-premises of in Microsoft 365 zijn.
    
- Beveilig e-mailcommunicatie tussen on-premises Exchange-servers en Microsoft 365 met TLS en certificaten.
    
- Berichten die tussen on-premises Exchange-servers en Microsoft 365 worden verzonden, behandelen als intern, zodat ze het volgende kunnen doen:
    
  - Correct worden geëvalueerd en verwerkt door transport- en complianceagenten die zich richten op interne berichten.
    
  - Antispamfilters omzeilen.
    
Volledige hybride migratie is het beste voor organisaties die verwachten dat ze maanden of langer in een hybride configuratie blijven. U krijgt de functies die eerder in deze sectie worden vermeld, plus adreslijstsynchronisatie, betere geïntegreerde compliancefuncties en de mogelijkheid om postvakken van en naar Microsoft 365 te verplaatsen met behulp van onlinepostvakken. Microsoft 365 wordt een uitbreiding van uw on-premises organisatie.
  
Als u overweegt om een volledige hybride migratie uit te gaan, zijn hier de volgende zaken waar u rekening mee moet houden:
  
- Volledige hybride migratie is niet geschikt voor alle soorten organisaties. Vanwege de complexiteit van volledig hybride migraties zien organisaties met minder dan een paar honderd postvakken meestal geen voordelen die de inspanning en kosten rechtvaardigen die nodig zijn om een postvak in te stellen. Als dit klinkt als uw organisatie, raden we u aan in plaats daarvan een cutover of gefaseerd migratie te overwegen.
    
- U moet ten minste één Exchange 2013-server implementeren in uw Exchange 2007-organisatie om op te treden als een 'hybride server'. Deze server communiceert met Microsoft 365 namens uw Exchange 2007-servers.
    
- Microsoft 365 moet verbinding maken met de 'hybride server' via Outlook Anywhere via TCP-poort 443.
    
- U moet adreslijstsynchronisatie instellen met Azure Active Directory (Azure AD) Verbinding maken tussen uw on-premises Active Directory-servers en Microsoft 365.
    
- Gebruikers kunnen zich aanmelden bij hun Microsoft 365-postvak met dezelfde gebruikersnaam en hetzelfde wachtwoord als wanneer ze zich aanmelden bij het lokale netwerk. (Voor deze functionaliteit is Azure AD Connect vereist met wachtwoordsynchronisatie en/of Active Directory Federation Services.)
    
- U hebt een Microsoft 365-licentie nodig die Exchange Online bevat voor elk gebruikerspostvak dat u migreert.
    
- Gebruikers hoeven op de meeste apparaten geen nieuw Outlook-profiel in te stellen, hoewel sommige oudere Android-telefoons mogelijk een nieuw profiel nodig hebben. Gebruikers moeten hun e-mail niet opnieuw downloaden.
    
Als volledige hybride migratie voor u goed klinkt, bekijkt u de volgende bronnen om te helpen bij uw migratie:
  
- [Exchange-implementatieassistent](/exchange/exchange-deployment-assistant)
    
- [Hybride implementaties van Exchange Server](/exchange/exchange-hybrid)
    
- [Wizard Hybride configuratie](/exchange/hybrid-configuration-wizard)
    
- [Veelgestelde vragen over de wizard Hybride configuratie](/exchange/hybrid-configuration-wizard-faqs)
    
- [Vereisten voor hybride implementatie](/exchange/hybrid-deployment-prerequisites)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Migreren naar een nieuwere versie van Exchange Server

We zijn ervan overtuigd dat u de beste waarde en gebruikerservaring kunt bereiken door te migreren naar Microsoft 365. Maar we begrijpen ook dat sommige organisaties hun e-mail on-premises moeten houden. Dit kan komen door wettelijke vereisten, om te garanderen dat gegevens niet worden opgeslagen in een datacenter in een ander land of iets dergelijks. Als u ervoor kiest om uw e-mail on-premises te houden, kunt u uw Exchange 2007-omgeving migreren naar Exchange 2010, Exchange 2013 of Exchange 2016.
  
Als u niet kunt migreren naar Microsoft 365, raden we u aan te migreren naar Exchange 2016. Exchange 2016 bevat alle functies van eerdere versies van Exchange. Het komt ook het meest overeen met de ervaring die beschikbaar is met Microsoft 365, hoewel sommige functies alleen beschikbaar zijn in Microsoft 365. Bekijk een paar dingen die u hebt gemist:
  
|**Exchange-release**|**Functies**|
|:-----|:-----|
|Exchange Server 2010  <br/> | Role-Based Access Control (machtigingen zonder ACL's)  <br/>  Postvakbeleid voor Outlook Web App  <br/>  Mogelijkheid om agenda's gratis/bezet en gedelegeerden te delen tussen organisaties  <br/> |
|Exchange 2013  <br/> | *Functies van Exchange 2010 en ...*  <br/>  Vereenvoudigde architectuur die het aantal serverrollen heeft teruggebracht tot drie (Postvak, Clienttoegang, Edge Transport)  <br/>  Beleid voor preventie van gegevensverlies (DLP) om te voorkomen dat gevoelige informatie lekt  <br/>  Verbeterde Outlook Web App-ervaring  <br/> |
|Exchange 2016  <br/> | *Functies van Exchange 2013 en ...*  <br/>  Verder vereenvoudigde serverrollen naar alleen Postvak en Edge Transport  <br/>  Verbeterde DLP samen met integratie met SharePoint  <br/>  Verbeterde databaseweerbaarheid  <br/>  Online documentsamenwerking |
   
#### <a name="which-version-should-i-migrate-to"></a>Naar welke versie moet ik migreren?

Het is raadzaam om in eerste instantie te gaan ervan uit dat u naar Exchange 2016 gaat migreren. Gebruik vervolgens de volgende informatie om uw aanname te bevestigen of om Exchange 2016 uit te sluiten. Als u om de een of andere reden niet kunt migreren naar Exchange 2016, doet u hetzelfde proces met Exchange 2013, en ga zo maar door.
  
|**Overweging**|**Meer informatie**|
|:-----|:-----|
|Einde van ondersteuningsdatums  <br/> | Net als in Exchange 2007 heeft elke versie van Exchange een eigen einddatum voor ondersteuning:  <br/> *Exchange 2010* - januari 2020  <br/> *Exchange 2013* - april 2023  <br/> *Exchange 2016* - oktober 2025  <br/>  Hoe eerder het einde van de ondersteuning, hoe eerder u een andere migratie moet uitvoeren.<br/> |
|Migratiepad naar Exchange 2010 en 2013.  <br/> |Hier zijn de algemene fasen voor het migreren naar Exchange 2010 of Exchange 2013:  <br/> - Installeer Exchange 2010 of 2013 in uw bestaande Exchange 2007-organisatie. <br/>- Services en andere infrastructuur verplaatsen naar Exchange 2010 of 2013.<br/>- Postvakken en openbare mappen verplaatsen naar Exchange 2010 of 2013.<br/>- Resterende Exchange 2007-servers buiten bedrijf stellen. |
|Migratiepad naar Exchange 2016  <br/> |Hier zijn de algemene fasen voor het migreren naar Exchange 2016:  <br/> - Installeer Exchange 2013 in uw bestaande Exchange 2007-organisatie.<br/>- Services en andere infrastructuur verplaatsen naar Exchange 2013.<br/>- Postvakken en openbare mappen verplaatsen naar Exchange 2013.<br/>- Resterende Exchange 2007-servers buiten bedrijf stellen.<br/>- Installeer Exchange 2016 in uw bestaande Exchange 2013-organisatie.<br/>- Postvakken, openbare mappen, services en andere infrastructuur verplaatsen naar Exchange 2016 (order maakt niet uit). Resterende Exchange 2013-servers buiten bedrijf stellen.<br/><br/> **Opmerking:** Migreren van Exchange 2013 naar Exchange 2016 is eenvoudig. De twee versies hebben bijna dezelfde hardwarevereisten en deze versies zijn zeer compatibel. U kunt dus een server die u hebt gekocht voor Exchange 2013 opnieuw opbouwen en Exchange 2016 op deze server installeren. Voor onlinepostvakbewegingen merken de meeste gebruikers niet eens dat hun postvak van de server is verplaatst en vervolgens terug nadat u het hebt opgebouwd met Exchange 2016.           |
|Coëxistentie van versie  <br/> | Wanneer u migreert naar ...  <br/> **Exchange 2016:** Exchange 2016 kan niet worden geïnstalleerd in een organisatie die een Exchange 2007-server bevat. U moet eerst migreren naar Exchange 2010 of 2013 (we raden Ten zeerste Exchange 2013 aan), verwijder alle Exchange 2007-servers en migreert vervolgens naar Exchange 2016.  <br/> **Exchange 2010 of Exchange 2013:** U kunt Exchange 2010 of Exchange 2013 installeren in een bestaande Exchange 2007-organisatie. Hiermee kunt u een of meer Exchange 2010- of 2013-servers installeren en uw migratie uitvoeren.  <br/> |
|Serverhardware  <br/> | Serverhardwarevereisten zijn gewijzigd in Exchange 2007. Zorg ervoor dat uw hardware compatibel is. Zie voor meer informatie:  <br/> [Systeemvereisten voor Exchange 2016](/Exchange/plan-and-deploy/system-requirements) <br/> [Systeemvereisten voor Exchange 2013](/exchange/exchange-2013-system-requirements-exchange-2013-help) <br/> [Systeemvereisten voor Exchange 2010](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) <br/>  U zult merken dat de aanzienlijke verbeteringen in de prestaties van Exchange en de toegenomen rekenkracht en opslagcapaciteit in nieuwere servers ervoor zorgen dat u waarschijnlijk minder servers nodig hebt om hetzelfde aantal postvakken te ondersteunen.  <br/> |
|Versie van besturingssysteem  <br/> | De minimaal ondersteunde besturingssysteemversies voor elke versie zijn:  <br/> **Exchange 2016** - Windows Server 2012  <br/> **Exchange 2013** - Windows Server 2008 R2 SP1  <br/> **Exchange 2010** - Windows Server 2008 SP2  <br/>  Meer informatie over ondersteuning van besturingssysteem vindt u in [Exchange Supportability Matrix](/Exchange/plan-and-deploy/supportability-matrix).  <br/> |
|Active Directory-forestfunctionaliteitsniveau  <br/> | De minimaal ondersteunde active directory-forestfunctionaliteitsniveaus voor elke versie zijn:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  Meer informatie over ondersteuning voor forestfunctionaliteit vindt u in [Exchange Supportability Matrix.](/Exchange/plan-and-deploy/supportability-matrix)  <br/> |
|Office-clientversies  <br/> | De minimaal ondersteunde Office-clientversies voor elke versie zijn:  <br/> **Exchange 2016** - Office 2010 (met de meest recente updates)  <br/> **Exchange 2013** - Office 2007 SP3  <br/> **Exchange 2010** - Office 2003  <br/>  Meer informatie over ondersteuning voor Office-client vindt u [bij Exchange Supportability Matrix](/Exchange/plan-and-deploy/supportability-matrix).  <br/> |
   
#### <a name="how-do-i-migrate"></a>Hoe kan ik migreren?

Als u hebt besloten uw e-mail on-premises te houden, gebruikt u de volgende bronnen om te helpen bij uw migratie:
  
- [Exchange-implementatieassistent](/exchange/exchange-deployment-assistant)
    
- Wijzigingen in Active Directory-schema voor Exchange [2016](/Exchange/plan-and-deploy/active-directory/ad-schema-changes), [2013](/exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- Systeemvereisten voor Exchange [2016](/Exchange/plan-and-deploy/system-requirements), [2013](/exchange/exchange-2013-system-requirements-exchange-2013-help), [2010](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141))
    
- Vereisten voor Exchange [2016](/Exchange/plan-and-deploy/prerequisites), [2013](/exchange/exchange-2013-prerequisites-exchange-2013-help), [2010](/previous-versions/office/exchange-server-2010/bb691354(v=exchg.141))
    
## <a name="get-help"></a>Help opvragen

Als u migreert naar Microsoft 365, komt u mogelijk in aanmerking voor het gebruik van onze Microsoft FastTrack-service. FastTrack biedt best practices, hulpprogramma's en resources om uw migratie naar Microsoft 365 zo naadloos mogelijk te maken. Het beste van alles is dat een ondersteuningstechnicus u door uw migratie zal helpen, van het plannen en ontwerpen tot het migreren van uw laatste postvak. Zie Microsoft FastTrack voor meer informatie [over FastTrack.](https://fasttrack.microsoft.com/)
  
Als u problemen hebt tijdens uw migratie naar Microsoft 365 en u geen FastTrack gebruikt of uw migratie naar een nieuwere versie van Exchange Server, zijn we hier om u te helpen. Hier zijn enkele bronnen die u kunt gebruiken:
  
- [Technische community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Klantondersteuning](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Verwante onderwerpen

[Resources om u te helpen bij het upgraden van uw Office 2007-servers en -clients](upgrade-from-office-2007-servers-and-products.md)