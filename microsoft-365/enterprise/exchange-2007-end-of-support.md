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
description: Meer informatie over de opties na Exchange Server 2007 einde van de ondersteuning en de plannings migratie met Microsoft 365, Office 365 of Exchange 2016 te starten.
ms.openlocfilehash: 3f0a5c8ef9765a184358b932548eaa2ae7c59adc
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519843"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Roadmap voor einde van ondersteuning voor Exchange 2007

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Exchange Server 2007 bereikte einde van de ondersteuning in april 2017. Als u de migratie van Exchange 2007 naar Microsoft 365, Office 365 of Exchange 2016 nog niet hebt gestart, is het tijd om te beginnen met plannen.
  
## <a name="what-does-end-of-support-mean"></a>Wat betekent *einde van ondersteuning* ?

De Exchange-Server, zoals bijna alle Microsoft-producten, heeft een ondersteuningscyclus waarbij nieuwe functies, foutoplossingen, beveiligingsfixes en dergelijke worden geboden. Deze levenscyclus duurt doorgaans tien jaar lang uit de eerste versie van het product. Het einde van de levenscyclus is bekend als het einde van de ondersteuning van het product. Aangezien Exchange 2007 het einde van de ondersteuning voor 11 april 2017 bereikt, biedt Microsoft niet langer:
  
- Technische ondersteuning voor problemen die kunnen optreden.
    
- Oplossingen voor problemen die gevolgen kunnen hebben voor de stabiliteit en bruikbaarheid van de server.
    
- Beveiligingscorrecties voor beveiligingsproblemen die de server kwetsbaar kunnen maken voor beveiligingsproblemen.
    
- Tijdzone-updates.
    
De installatie van Exchange 2007 wordt voortgezet na de ondersteuning van het einde van de dag. Maar omdat er geen nieuwe updates of ondersteuning zijn, raden wij u ten zeerste aan dat u zo snel mogelijk migreert van Exchange 2007.
  
Zie [de upgrade van office 2007-servers en-producten plannen](upgrade-from-office-2007-servers-and-products.md)voor meer informatie over Office 2007-servers die binnenkort niet meer worden ondersteund.
  
## <a name="what-are-my-options"></a>Wat zijn mijn mogelijkheden?

U kunt:
  
- Migreren naar Microsoft 365 met behulp van cutover, gefaseerde of hybride migratie.
    
- Migreer uw Exchange 2007-servers naar een nieuwere versie van Exchange op uw on-premises servers.
    
In de volgende secties wordt elke optie uitvoerig besproken.
  
### <a name="migrate-to-microsoft-365"></a>Migreren naar Microsoft 365

Het migreren van uw e-mailbericht naar Microsoft 365 is de beste en eenvoudigste optie om uw implementatie van Exchange 2007 buiten te trekken. Met een migratie naar Microsoft 365 kunt u één hop maken van 10-jaar-oude technologie en de functies van de geavanceerde functies, waaronder:
  
- Nalevings mogelijkheden zoals bewaarbeleid, In-Place en de bewaring in-place eDiscovery en meer
    
- Microsoft 365 Groepen
    
- Postvak in met prioriteit
    
- MyAnalytics
    
- REST-Api's voor programmatische toegang tot e-mail, agenda's, contactpersonen, enzovoort
    
Microsoft 365 ontvangt ook nieuwe functies en ervaring, zodat u en uw gebruikers ze meestal direct kunnen gebruiken. U hoeft zich geen zorgen te maken over:
  
- Kopen en onderhouden van hardware.
    
- Betaalde systemen en coole servers.
    
- Up-to-date houden van oplossingen voor beveiliging, producten en tijdzone.
    
- Opslag en softwareonderhoud ter ondersteuning van nalevingsvereisten.
    
- Een upgrade uitvoeren naar een nieuwe versie van Exchange. Met Microsoft 365 gaat u altijd op de nieuwste versie van Exchange.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>Hoe moet ik migreren naar Microsoft 365?

U hebt een paar migratie opties. U dient enkele zaken te bespreken, waaronder:

- Het aantal stoelen of postvakken dat u wilt verplaatsen.
- Hoelang u de migratie wilt laten duren.
- Of u de migratie met de on-premises installatie en Microsoft 365 naadloos wilt integreren.

In deze tabel worden de migratie opties en de belangrijkste factoren weergegeven om te bepalen welke methode moet worden gebruikt:
  

|**Migratieoptie**|**Organisatie formaat**|**Peri**|
|:-----|:-----|:-----|
|Cutover-migratie  <br/> |Minder dan 150 stoelen  <br/> |Een week of minder  <br/> |
|Gefaseerde migratie  <br/> |Meer dan 150 stoelen  <br/> |Een paar weken  <br/> |
|Volledig hybride migratie  <br/> |Honderd tot duizenden seats  <br/> |Een paar maanden of meer  <br/> |
   
In de volgende secties vindt u een overzicht van deze methoden. Zie voor meer informatie [een pad voor de migratie kiezen](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27). 
  
#### <a name="cutover-migration"></a>Cutover-migratie

In een cutover-migratie migreert u alle postvakken, distributiegroepen, contactpersonen, enzovoort, naar Microsoft 365 op een voorgeselecteerde datum en tijd. Wanneer de migratie is voltooid, sluit u uw on-premises Exchange-servers af en gaat u verder met Microsoft 365.
  
Cutover-migratie is ideaal voor kleine organisaties die niet veel postvakken hebben, willen snel aan de slag met Microsoft 365 en willen geen enkele complexe zaken van de andere methoden behandelen. Maar het moet binnen een week of minder lang zijn en moet gebruikers hun Outlook-profielen opnieuw configureren. Cutover-migratie kan worden verwerkt tot 2.000-postvakken, maar wij raden u het beste aan om maximaal 150-postvakken te migreren. Als u meer probeert te migreren, kon u niet langer gebruikmaken van alle postvakken vóór de deadline en kunnen uw IT-ondersteuningsmedewerkers worden overspoeld met aanvragen om gebruikers te helpen opnieuw de configuratie van Outlook te helpen.
  
Als u overweegt om een cutover-migratie uit te voeren, kunt u het volgende doen:
  
- Microsoft 365 moet verbinding maken met uw Exchange 2007-servers via Outlook Anywhere en TCP-poort 443.
    
- Alle on-premises postvakken worden verplaatst naar Microsoft 365.
    
- U hebt een on-premises Administrator-account nodig met leestoegang tot de postvakken van uw gebruikers.
    
- De geaccepteerde domeinen van Exchange 2007 die u wilt gebruiken in Microsoft 365 moeten als geverifieerde domeinen worden toegevoegd aan de service.
    
- Tussen het moment dat u de migratie begint en wanneer u de voltooiings fase begint, worden in Microsoft 365 regelmatig de postvakken van Microsoft 365 en on-premises gesynchroniseerd. Hiermee kunt u de migratie voltooien, zonder dat u zich zorgen hoeft te maken over e-mail achter uw on-premises postvakken.
    
- Gebruikers ontvangen nieuwe tijdelijke wachtwoorden voor hun Microsoft 365-accounts. De persoon moet hun wachtwoord wijzigen wanneer ze zich voor de eerste keer aanmelden bij hun postvak.
    
- Voor elk gebruikerspostvak dat u migreert, moet u een licentie voor Microsoft 365 met Exchange Online hebben.
    
- Gebruikers moeten een nieuw Outlook-profiel op elk van hun apparaten instellen en hun e-mail opnieuw downloaden. De hoeveelheid e-mail die in Outlook wordt gedownload, kan variëren. Zie de hoeveelheid offline beschikbare [E-mail wijzigen](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)voor meer informatie.
    
Zie voor meer informatie over cutover-migratie:
  
- [Wat u moet weten over een cutover-e-mail migratie](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Een cutover-migratie van e-mail uitvoeren](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Gefaseerde migratie

In een gefaseerde migratie hebt u een paar honderden of een paar duizenden postvakken die u wilt migreren naar Microsoft 365, moet u een week of langer nodig hebben om de migratie te voltooien en hebt u geen geavanceerde functies voor hybride migratie, zoals gedeelde beschikbaarheidsinfo-agendagegevens, nodig.
  
Gefaseerde migratie is ideaal voor organisaties die meer tijd nodig hebben om hun postvakken te migreren naar Microsoft 365, maar wel de migratie binnen een paar weken voltooien. U kunt postvakken in batches migreren. U bepaalt het aantal en welke postvakken op een bepaald moment worden gemigreerd. U kunt ook batch postvakken van gebruikers in dezelfde afdeling, bijvoorbeeld, om ervoor te zorgen dat ze allen tegelijk worden verplaatst. U kunt ook de postvakken van Executive blijven bewaren voor de laatste batch. Net als met cutover-migraties moeten uw gebruikers hun Outlook-profielen opnieuw maken.
  
Als u overweegt om een gefaseerde migratie uit te voeren, kunt u het volgende doen:
  
- Microsoft 365 moet verbinding maken met uw Exchange 2007-servers via Outlook Anywhere en TCP-poort 443.
    
- U hebt een on-premises Administrator-account nodig met leestoegang tot de postvakken van uw gebruikers.
    
- De geaccepteerde domeinen van Exchange 2007 die u wilt gebruiken in Microsoft 365 moeten als geverifieerde domeinen worden toegevoegd aan de service.
    
- U moet een CSV-bestand maken met de volledige naam en het e-mailadres van elk postvak dat u wilt migreren in een batch. U moet ook een nieuw wachtwoord opnemen voor elk postvak dat u migreert, en het wachtwoord naar iedere gebruiker verzenden. De gebruiker wordt gevraagd het wachtwoord te wijzigen voor de eerste keer dat hij of zij zich aanmeldt bij het nieuwe Microsoft 365-postvak.
    
- Tussen het moment dat u de migratie batch start en wanneer u de voltooiings fase begint, zal Microsoft 365 periodiek de Microsoft 365-en on-premises postvakken in de batch synchroniseren. Hiermee kunt u de migratie voltooien, zonder dat u zich zorgen hoeft te maken over e-mail achter uw on-premises postvakken.
    
- Voor elk gebruikerspostvak dat u migreert, moet u een licentie voor Microsoft 365 met Exchange Online hebben.
    
- Gebruikers moeten een nieuw Outlook-profiel op elk van hun apparaten instellen en hun e-mail opnieuw downloaden. De hoeveelheid e-mail die in Outlook wordt gedownload, kan variëren. Zie de hoeveelheid offline beschikbare [E-mail wijzigen](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)voor meer informatie.
    
Zie voor meer informatie over gefaseerde migratie:
  
- [Wat u moet weten over een gefaseerde e-mail migratie](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Een gefaseerde migratie van e-mail uitvoeren](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Volledige hybride

In een volledige hybride migratie heeft uw organisatie veel honderden, tot tientallen duizenden, van postvakken, en u wilt enkele of alle andere items verplaatsen naar Microsoft 365. Omdat deze migraties doorgaans langer lang zijn, kunt u het volgende doen met hybride migraties:
  
- On-premises gebruikers van de beschikbaarheidsinfo weergeven voor gebruikers in Microsoft 365 en omgekeerd.
    
- Een geïntegreerde algemene adreslijst weergeven met geadresseerden in zowel on-premises als in Microsoft 365.
    
- Alle Outlook-instellingen voor geadresseerden weergeven voor alle gebruikers, ongeacht of ze on-premises of in Microsoft 365.
    
- Beveilig e-mail communicatie tussen on-premises Exchange-servers en Microsoft 365 met behulp van TLS en certificaten.
    
- Berichten behandelen die zijn verzonden tussen on-premises Exchange-servers en Microsoft 365 als intern, zodat ze het volgende kunnen doen:
    
  - U wordt op de juiste wijze geëvalueerd en verwerkt door agents en compliance-medewerkers die interne berichten richten.
    
  - Negeer antispam filters.
    
De volledige hybride migratie is geschikt voor organisaties die verwacht te blijven in een hybride configuratie van een groot aantal maanden. U krijgt de functies die eerder in deze sectie worden vermeld, plus Directory-synchronisatie, betere geïntegreerde functies voor naleving en de mogelijkheid om postvakken te verplaatsen naar en naar Microsoft 365 via Online postvak wordt verplaatst. Microsoft 365 wordt een uitbreiding van uw on-premises organisatie.
  
Als u overweegt om een volledig hybride migratie uit te voeren, kunt u het volgende doen:
  
- De volledige hybride migratie is niet geschikt voor alle organisatietypen. Als gevolg van de complexiteit van de hybride migraties zijn organisaties met minder dan een paar honderd postvakken meestal voordelen die de inspanning en de kosten voor het eerst instellen. Als dit klinkt zoals uw organisatie, raden we u aan om een cutover of gefaseerde migratie uit te voeren.
    
- U moet ten minste één Exchange 2013-server in uw Exchange 2007-organisatie implementeren om als een ' hybride server ' te fungeren. Deze server communiceert met Microsoft 365 namens uw Exchange 2007-servers.
    
- Microsoft 365 moet verbinding maken met de ' hybride server ' via Outlook Anywhere via TCP-poort 443.
    
- U moet adreslijstsynchronisatie instellen met Azure Active Directory (Azure AD) verbinding maken tussen uw on-premises Active Directory-servers en Microsoft 365.
    
- Gebruikers kunnen zich aanmelden bij hun Microsoft 365-postvak met dezelfde gebruikersnaam en hetzelfde wachtwoord als wanneer ze zich aanmelden bij het lokale netwerk. Voor deze functionaliteit is Azure AD Connect met Wachtwoordsynchronisatie en/of Active Directory Federation Services vereist.
    
- Voor elk gebruikerspostvak dat u migreert, moet u een licentie voor Microsoft 365 met Exchange Online hebben.
    
- Gebruikers hoeven geen nieuw Outlook-profiel in te stellen op de meeste apparaten, hoewel voor sommige oudere Android-telefoons mogelijk een nieuw profiel is vereist. Gebruikers hoeven hun e-mail niet opnieuw te downloaden.
    
Raadpleeg de volgende bronnen voor hulp bij de migratie als u de volledige hybride migratie voor u hebt.
  
- [Exchange Deployment Assistant](https://aka.ms/exdeploy)
    
- [Hybride implementaties van Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)
    
- [Wizard hybride configuratie](https://technet.microsoft.com/library/hh529921%28v=exchg.150%29.aspx)
    
- [Veelgestelde vragen over de wizard hybride configuratie](https://technet.microsoft.com/library/mt488940%28v=exchg.150%29.aspx)
    
- [Vereisten voor hybride implementatie](https://technet.microsoft.com/library/hh534377%28v=exchg.150%29.aspx)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Migreren naar een nieuwere versie van Exchange Server

We geloven dat u de beste waarde en gebruikerservaring kunt verkrijgen door te migreren naar Microsoft 365. Maar we begrijpen ook dat sommige organisaties hun on-premises e-mailadres moeten bewaren. Dit kan ten gevolge van wettelijke vereisten gelden voor garanties die niet zijn opgeslagen in een datacenter dat zich in een ander land bevindt, of vergelijkbaar. Als u ervoor kiest om uw e-mails on-premises te houden, kunt u uw Exchange 2007-omgeving migreren naar Exchange 2010, Exchange 2013 of Exchange 2016.
  
Als u niet kunt migreren naar Microsoft 365, is het raadzaam om te migreren naar Exchange 2016. Exchange 2016 omvat alle functies van vorige releases van Exchange. Dit komt ook overeen met de beschikbare ervaring met Microsoft 365, maar sommige functies zijn alleen beschikbaar in Microsoft 365. Bekijk slechts een paar van de dingen die u missen:
  
|**Exchange-versie**|**Functies**|
|:-----|:-----|
|Exchange Server 2010  <br/> | Toegangsbeheer Role-Based (machtigingen zonder Acl's)  <br/>  Beleidsregels voor Postvak in in Outlook Web app  <br/>  Mogelijkheid om beschikbaarheidsinfo te delen tussen organisaties en agenda's te delegeren  <br/> |
|Exchange 2013  <br/> | *Functies van Exchange 2010 en...*  <br/>  Vereenvoudigde architectuur waarmee het aantal serverrollen wordt verlaagd tot drie (Postvak, client toegang en Edge-transport)  <br/>  Beleidsregels voor preventie van gegevensverlies (DLP) om te voorkomen dat gevoelige informatie wordt lekt  <br/>  Verbeterde Outlook Web app-ervaring  <br/> |
|Exchange 2016  <br/> | *Functies van Exchange 2013 en...*  <br/>  Uitgebreide serverfuncties uitsluitend voor postvak en Edge-transport  <br/>  Verbeterde DLP, naast integratie met SharePoint  <br/>  Verbeterde database tolerantie  <br/>  Online samenwerken aan documenten |
   
#### <a name="which-version-should-i-migrate-to"></a>Naar welke versie moet ik migreren?

U wordt aangeraden dat u eerst migreert naar Exchange 2016. Vervolgens gaat u op de volgende informatie om uw hypothese of de regel Exchange 2016 te bevestigen. Als u om wat voor reden dan ook niet kunt migreren naar Exchange 2016, doet u hetzelfde proces met Exchange 2013, enzovoort.
  
|**Aanmerking**|**Meer informatie**|
|:-----|:-----|
|Einde van ondersteunings datums  <br/> | Net als Exchange 2007, heeft elke versie van Exchange een eigen datum voor de einde-en ondersteunings datum:  <br/> *Exchange 2010* -januari 2020  <br/> *Exchange 2013* -april 2023  <br/> *Exchange 2016* -oktober 2025  <br/>  Het einde van de ondersteuning, hoe sneller u een andere migratie moet uitvoeren.<br/> |
|Configuratiepad voor Exchange 2010 en 2013.  <br/> |Dit zijn de algemene fasen voor de migratie naar Exchange 2010 of Exchange 2013:  <br/> -Exchange 2010 of 2013 installeren in uw bestaande Exchange 2007-organisatie. <br/>-Services en andere infrastructuur overbrengen naar Exchange 2010 of 2013.<br/>-Postvakken en openbare mappen verplaatsen naar Exchange 2010 of 2013.<br/>-Overige Exchange 2007-servers buiten bedrijf stellen. |
|Configuratiepad voor Exchange 2016  <br/> |Dit zijn de algemene fasen voor de migratie naar Exchange 2016:  <br/> -Exchange 2013 installeren in uw bestaande Exchange 2007-organisatie.<br/>-Services en andere infrastructuur overbrengen naar Exchange 2013.<br/>-Postvakken en openbare mappen verplaatsen naar Exchange 2013.<br/>-Overige Exchange 2007-servers buiten bedrijf stellen.<br/>-Exchange 2016 installeren in uw bestaande Exchange 2013-organisatie.<br/>-Postvakken, openbare mappen, services en andere infrastructuur verplaatsen naar Exchange 2016 (de volgorde is niet belangrijk). Overige Exchange 2013-servers buiten bedrijf stellen.<br/><br/> **Opmerking:** Migreren van Exchange 2013 naar Exchange 2016 is eenvoudig. De twee versies hebben bijna dezelfde hardwarevereisten, en deze versies zijn zeer compatibel. U kunt een server die u hebt gekocht voor Exchange 2013 opnieuw opbouwen en Exchange 2016 installeren. Voor de overstap van een Online postvak melden de meeste gebruikers niet dat hun postvak van de server werd verplaatst en daarna weer terug nadat u het postvak opnieuw hebt samengesteld met Exchange 2016.           |
|Versies naast elkaar  <br/> | Wanneer u migreert naar...  <br/> **Exchange 2016:** Exchange 2016 kan niet worden geïnstalleerd in een organisatie die een Exchange 2007-server bevat. U dient eerst te migreren naar Exchange 2010 of 2013 (wij raden u ten zeerste aan Exchange 2013), alle Exchange 2007-servers te verwijderen en vervolgens te migreren naar Exchange-2016.  <br/> **Exchange 2010 of exchange 2013:** U kunt Exchange 2010 of Exchange 2013 installeren in een bestaande Exchange 2007-organisatie. Hiermee kunt u een of meer Exchange 2010-of 2013-servers installeren en uw migratie uitvoeren.  <br/> |
|Serverhardware  <br/> | De hardwarevereisten voor de server zijn gewijzigd in Exchange 2007. Zorg dat de hardware compatibel is. Zie voor meer informatie:  <br/> [Systeemvereisten voor Exchange 2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx) <br/> [Systeemvereisten voor Exchange 2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx) <br/> [Systeemvereisten voor Exchange 2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx) <br/>  U zult merken dat belangrijke verbeteringen in de prestaties van de Exchange-prestaties en de betere computerkracht en-opslagcapaciteit in nieuwere servers betekenen dat u waarschijnlijk minder servers moet ondersteunen voor hetzelfde aantal postvakken.  <br/> |
|Versie van besturingssysteem  <br/> | De minimaal ondersteunde besturingssysteemversies voor elke versie zijn:  <br/> **Exchange 2016** -Windows Server 2012  <br/> **Exchange 2013** -Windows Server 2008 R2 SP1  <br/> **Exchange 2010** -Windows Server 2008 SP2  <br/>  Ga voor meer informatie over de ondersteuning van besturingssystemen naar de [Exchange-ondersteunings matrix](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Functioneel niveau van Active Directory-forest  <br/> | De minimaal ondersteunde functies voor Active Directory-forests voor elke versie zijn:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  Meer informatie over het functionele niveau van de forest is te vinden in de [Exchange-ondersteunings matrix](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Versies van Office-clients  <br/> | De minimaal ondersteunde versies van Office-clients voor elke versie zijn:  <br/> **Exchange 2016** -Office 2010 (met de nieuwste updates)  <br/> **Exchange 2013** -Office 2007 SP3  <br/> **Exchange 2010** -Office 2003  <br/>  Ga voor meer informatie over de ondersteuning van Office-clients naar de [Exchange-ondersteunings matrix](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
   
#### <a name="how-do-i-migrate"></a>Hoe migreer ik?

Als u besluit uw e-mailberichten on-premises te houden, kunt u de volgende bronnen gebruiken om de migratie te vereenvoudigen:
  
- [Exchange Deployment Assistant](https://aka.ms/exdeploy)
    
- Wijzigingen van Active Directory-schema voor Exchange [2016](https://technet.microsoft.com/library/bb738144%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb738144%28v=exchg.150%29.aspx), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- Systeemvereisten voor Exchange [2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx)
    
- Vereisten voor Exchange [2016](https://technet.microsoft.com/library/bb691354%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb691354%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/bb691354%28v=exchg.141%29.aspx)
    
## <a name="get-help"></a>Help opvragen

Als u migreert naar Microsoft 365, komt u mogelijk in aanmerking voor de service van Microsoft FastTrack. FastTrack biedt aanbevolen procedures, hulpprogramma's en informatiebronnen om de migratie naar Microsoft 365 zo eenvoudig mogelijk te maken. De beste van een ondersteuningstechnicus helpt u bij de migratie, van het plannen en ontwerpen van de overstap naar het laatste postvak. Zie [Microsoft FastTrack](https://fasttrack.microsoft.com/)voor meer informatie over FastTrack.
  
Als u problemen ondervindt tijdens de migratie naar Microsoft 365 en u geen gebruikmaakt van FastTrack of de migratie naar een nieuwere versie van Exchange Server, dan kunnen we u helpen. Hier volgen enkele bronnen die u kunt gebruiken:
  
- [Technische community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Klantondersteuning](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Verwante onderwerpen

[Bronnen om u te helpen bij het upgraden van uw Office 2007-servers en-clients](upgrade-from-office-2007-servers-and-products.md)
