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
description: Meer informatie over uw opties nadat Exchange Server 2007 het einde van de ondersteuning heeft bereikt en de plannings migratie naar Microsoft 365, Office 365 of Exchange 2016 te starten.
ms.openlocfilehash: 864a4bc64f35a12dfea1a98b3d50430cd3e5714b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689495"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Roadmap voor einde van ondersteuning voor Exchange 2007

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Op **11 April 2017**bereikte Exchange Server 2007 einde van de ondersteuning. Als u de migratie van Exchange 2007 naar Microsoft 365, Office 365 of Exchange 2016 nog niet hebt gedaan, kunt u het beste eerst de planning starten. 
  
## <a name="what-does-end-of-support-mean"></a>Wat betekent einde van ondersteuning?

De Exchange-Server, zoals bijna alle Microsoft-producten, heeft een ondersteuningscyclus waarbij nieuwe functies, foutoplossingen, beveiligingsfixes en dergelijke worden geboden. Deze levenscyclus duurt doorgaans tien jaar vanaf de datum van de eerste release van het product, en het einde van de levenscyclus bekend is als het einde van de ondersteuning van de producten. Aangezien Exchange 2007 het einde van de ondersteuning voor 11 april 2017 bereikt, biedt Microsoft niet langer:
  
- Technische ondersteuning voor problemen die kunnen optreden;
    
- Oplossingen voor ontdekte problemen die gevolgen kunnen hebben voor de stabiliteit en bruikbaarheid van de server;
    
- Beveiligingscorrecties voor ontdekte beveiligingsproblemen die de server kwetsbaar kunnen maken voor beveiligingsproblemen.
    
- Tijdzone-updates.
    
De installatie van Exchange 2007 blijft na deze datum actief. Vanwege de bovenstaande wijzigingen is het echter raadzaam om te migreren vanaf Exchange 2007, zo snel mogelijk.
  
Zie [de upgrade van office 2007-servers en-producten plannen](upgrade-from-office-2007-servers-and-products.md)voor meer informatie over Office 2007-servers die binnenkort niet meer worden ondersteund.
  
## <a name="what-are-my-options"></a>Wat zijn mijn mogelijkheden?

Nu Exchange 2007 het einde van de ondersteuning heeft bereikt, raden we u ten zeerste aan om uw opties te verkennen en een migratieplan voor te bereiden. U kunt:
  
- Migreren naar Microsoft 365 met behulp van cutover, gefaseerde of hybride migratie;
    
- Migreer uw Exchange 2007-servers naar een nieuwere versie van Exchange op uw on-premises servers.
    
In de volgende secties wordt elke optie uitvoerig besproken.
  
### <a name="migrate-to-microsoft-365"></a>Migreren naar Microsoft 365

Het migreren van e-mail naar Microsoft 365 is de beste en eenvoudigste optie om u te helpen bij het buiten gebruik stellen van uw implementatie van Exchange 2007. Met een migratie naar Microsoft 365 kunt u één hop maken van 10-jaar-oude technologie en de functies van de versie van de Art, zoals:
  
- Nalevings mogelijkheden zoals bewaarbeleid, in-place bewaring en bewaring in-place eDiscovery en meer;
    
- Microsoft 365 groepen;
    
- Postvak in met prioriteit;
    
- MyAnalytics
    
- REST-Api's voor programmatische toegang tot e-mail, agenda's, contactpersonen, enzovoort.
    
Microsoft 365 krijgt ook nieuwe functies en ervaring, en u en uw gebruikers kunnen ze direct gebruiken. Naast de nieuwe functies hoeft u zich geen zorgen te maken over het volgende:
  
- Kopen en onderhouden van hardware;
    
- Betaalt voor verwarming en koeling van uw servers;
    
- Up-to-date houden van oplossingen voor veiligheid, producten en tijdzone.
    
- Opslag en softwareonderhoud ter ondersteuning van nalevingsvereisten;
    
- Upgraden naar een nieuwe versie van Exchange-u bevindt zich altijd in de nieuwste versie van Exchange in Microsoft 365.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>Hoe moet ik migreren naar Microsoft 365?

Afhankelijk van uw organisatie hebt u een paar opties voor de ondersteuning van Microsoft 365. Als u een migratieoptie kiest, moet u een paar dingen doen, zoals het aantal seats of postvakken dat u wilt verplaatsen, hoe lang u de migratie wilt uitvoeren en of u een naadloze integratie nodig hebt tussen uw on-premises installatie en Microsoft 365 tijdens de migratie. In deze tabel worden de migratie opties en de belangrijkste factoren weergegeven om te bepalen welke methode u wilt gebruiken.
  
| |
|**Migratieoptie**|**Organisatie formaat**|**Peri**|
|:-----|:-----|:-----|
|Cutover-migratie  <br/> |Minder dan 150 stoelen  <br/> |Een week of minder  <br/> |
|Gefaseerde migratie  <br/> |Meer dan 150 stoelen  <br/> |Een paar weken  <br/> |
|Volledig hybride migratie  <br/> |Honderd tot duizenden seats  <br/> |Een paar maanden of meer  <br/> |
   
De volgende secties bieden een overzicht van deze methoden. Kijk [op een sharepad](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27) om de details van elke methode te leren kennen. 
  
#### <a name="cutover-migration"></a>Cutover-migratie

Een cutover-migratie is één plaats, wanneer u bij een vooraf geselecteerde datum en tijd al uw postvakken, distributiegroepen, contactpersonen, enzovoort, migreert naar Microsoft 365. Wanneer u klaar bent, sluit u uw on-premises Exchange-servers af en begint u Microsoft 365 uitsluitend te gebruiken.
  
De cutover-migratiemethode is ideaal voor kleine organisaties die niet met een groot aantal postvakken werken, willen snel naar Microsoft 365 en willen ze de complexe zaken van de andere methoden niet leren. Maar het is ook enigszins beperkt omdat het in een week of minder moet worden voltooid en omdat daarvoor gebruikers hun Outlook-profielen opnieuw moeten configureren. Hoewel een cutover-migratie kan worden uitgevoerd voor 2.000-postvakken, is het raadzaam om maximaal 150 postvakken te migreren met deze methode. Als u meer dan 150 postvakken probeert te migreren, kon u niet langer gebruikmaken van alle postvakken voor de deadline en kunnen uw IT-medewerkers u helpen om Outlook opnieuw te configureren.
  
Als u overweegt om een cutover-migratie uit te voeren, zijn dit een paar dingen waar u aan moet denken:
  
- Microsoft 365 moet verbinding maken met uw Exchange 2007-servers via Outlook Anywhere en TCP-poort 443.
    
- Alle on-premises postvakken worden verplaatst naar Microsoft 365;
    
- U hebt een on-premises Administrator-account nodig met toegangsrechten voor het lezen van de inhoud van de postvakken van uw gebruikers.
    
- De geaccepteerde domeinen van Exchange 2007 die u wilt gebruiken in Microsoft 365 moeten als geverifieerde domeinen worden toegevoegd aan de service.
    
- Tussen het moment dat u de migratie begint en wanneer u de voltooiings fase begint, worden in Microsoft 365 regelmatig de postvakken van Microsoft 365 en on-premises gesynchroniseerd. Hiermee kunt u de migratie voltooien zonder dat u zich zorgen hoeft te maken over e-mail achter uw on-premises postvakken.
    
- Gebruikers krijgen nieuwe tijdelijke wachtwoorden voor hun Microsoft 365-account, die ze bij de eerste aanmelding bij hun postvak moeten wijzigen.
    
- Voor elk gebruikerspostvak dat u migreert, moet u een licentie voor Microsoft 365 met Exchange Online hebben.
    
- Gebruikers moeten een nieuw Outlook-profiel op elk van hun apparaten instellen en hun e-mail opnieuw downloaden. De hoeveelheid e-mail die in Outlook wordt gedownload, kan variëren. Voor meer informatie raadpleegt u de [hoeveelheid e-mail die u offline wilt houden, wijzigen](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Ga voor meer informatie over cutover-migratie naar het volgende:
  
- [Wat u moet weten over een cutover-e-mail migratie](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Een cutover-migratie van e-mail uitvoeren](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Gefaseerde migratie

Een gefaseerde migratie is een functie waarbij u een paar honderden of een paar duizenden postvakken hebt die u wilt migreren naar Microsoft 365, moet u een week of meer nodig hebben om de migratie te voltooien en geen geavanceerde functies voor hybride migratie zoals gedeelde beschikbaarheidsinfo-agendagegevens nodig hebben.
  
Gefaseerde migratie is ideaal voor organisaties die meer tijd nodig hebben om hun postvakken te migreren naar Microsoft 365, maar wel de voltooiing van de migratie binnen enkele weken. U kunt postvakken migreren in batches, zodat u kunt bepalen hoeveel en welke postvakken op een bepaald moment worden gemigreerd. U kunt ook batch postvakken van gebruikers in dezelfde afdeling, bijvoorbeeld, om ervoor te zorgen dat ze allen tegelijk worden verplaatst. U kunt ook de postvakken van Executive blijven bewaren voor de laatste batch. Net als met cutover-migraties moeten uw gebruikers hun Outlook-profielen opnieuw maken.
  
Als u overweegt om een gefaseerde migratie uit te voeren, zijn dit een paar dingen waar u aan moet denken:
  
- Microsoft 365 moet verbinding maken met uw Exchange 2007-servers via Outlook Anywhere en TCP-poort 443.
    
- U hebt een on-premises Administrator-account nodig met toegangsrechten voor het lezen van de inhoud van de postvakken van uw gebruikers.
    
- De geaccepteerde domeinen van Exchange 2007 die u wilt gebruiken in Microsoft 365 moeten als geverifieerde domeinen worden toegevoegd aan de service.
    
- U moet een CSV-bestand maken met de volledige naam en het e-mailadres van elk postvak dat u wilt migreren in een batch. U moet ook een nieuw wachtwoord opnemen voor elk postvak dat u migreert en het wachtwoord van een gebruiker verzenden. De gebruiker wordt gevraagd het wachtwoord te wijzigen, wanneer ze zich voor de eerste keer aanmelden bij hun nieuwe Microsoft 365-postvak.
    
- Tussen het moment dat u de migratie batch start en wanneer u de voltooiings fase begint, zal Microsoft 365 periodiek de Microsoft 365-en on-premises postvakken in de batch synchroniseren. Hiermee kunt u de migratie voltooien zonder dat u zich zorgen hoeft te maken over e-mail achter uw on-premises postvakken.
    
- Gebruikers krijgen nieuwe tijdelijke wachtwoorden voor hun Microsoft 365-account, die ze bij de eerste aanmelding bij hun postvak moeten wijzigen.
    
- Voor elk gebruikerspostvak dat u migreert, moet u een licentie voor Microsoft 365 met Exchange Online hebben.
    
- Gebruikers moeten een nieuw Outlook-profiel op elk van hun apparaten instellen en hun e-mail opnieuw downloaden. De hoeveelheid e-mail die in Outlook wordt gedownload, kan variëren. Voor meer informatie raadpleegt u de [hoeveelheid e-mail die u offline wilt houden, wijzigen](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Als u meer wilt weten over een gefaseerde migratie, gaat u naar:
  
- [Wat u moet weten over een gefaseerde e-mail migratie](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Een gefaseerde migratie van e-mail uitvoeren](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Volledige hybride

Een volledige hybride migratie is een functie waarbij uw organisatie veel honderden, maximaal tienduizenden duizenden, van postvakken, en u enkele of alle andere items naar Microsoft 365 wilt verplaatsen. Omdat deze migraties doorgaans langer lang zijn, kunt u het volgende doen met hybride migraties:
  
- On-premises gebruikers van de beschikbaarheidsinfo weergeven voor gebruikers in Microsoft 365 en omgekeerd;
    
- Een geïntegreerde algemene adreslijst weergeven die geadresseerden bevat in zowel on-premises als Microsoft 365;
    
- Alle Outlook-instellingen voor geadresseerden weergeven voor alle gebruikers, ongeacht of ze on-premises of in Microsoft 365 zijn.
    
- Beveilig e-mail communicatie tussen on-premises Exchange-servers en Microsoft 365 met behulp van TLS en certificaten;
    
- Berichten behandelen die zijn verzonden tussen on-premises Exchange-servers en Microsoft 365 als intern, zodat ze het volgende kunnen doen:
    
  - U wordt op de juiste wijze geëvalueerd en verwerkt door agents en compliance-medewerkers die interne berichten richten.
    
  - Negeer antispam filters.
    
Volledige hybride migraties zijn geschikt voor organisaties die verwachten dat ze gedurende een of meer maanden een hybride configuratie blijven. U krijgt de functies die eerder in deze sectie worden vermeld, plus adreslijstsynchronisatie, betere geïntegreerde functies voor naleving en de mogelijkheid om postvakken te verplaatsen naar en naar Microsoft 365 via Online postvak wordt verplaatst. Microsoft 365 wordt een uitbreiding van uw on-premises organisatie.
  
Als u overweegt om een volledig hybride migratie uit te voeren, zijn dit een paar dingen waar u aan moet denken:
  
- Volledige hybride migraties zijn niet geschikt voor alle organisatietypen. Als gevolg van de complexiteit van de hybride migraties zijn organisaties met minder dan een paar honderd postvakken meestal voordelen die de inspanning en de kosten voor het eerst instellen. Als dit klinkt zoals uw organisatie, raden we u ten zeerste aan om Cutover of gefaseerde migraties uit te voeren.
    
- U moet ten minste één Exchange 2013-server in uw Exchange 2007-organisatie implementeren om als een ' hybride server ' te fungeren. Deze server communiceert met Microsoft 365 namens uw Exchange 2007-servers;
    
- Microsoft 365 moet verbinding maken met de ' hybride server ' via Outlook Anywhere via TCP-poort 443.
    
- U moet adreslijstsynchronisatie instellen met Azure Active Directory (Azure AD) verbinding maken tussen uw on-premises Active Directory-servers en Microsoft 365;
    
- Gebruikers kunnen zich aanmelden bij hun Microsoft 365-postvak met dezelfde gebruikersnaam en hetzelfde wachtwoord als ze worden gebruikt wanneer ze zich aanmelden bij het lokale netwerk (vereist Azure AD Connect met Wachtwoordsynchronisatie en/of Active Directory Federation Services).
    
- Voor elk gebruikerspostvak dat u migreert, moet u een licentie voor Microsoft 365 met Exchange Online hebben.
    
- Gebruikers hoeven geen nieuw Outlook-profiel in te stellen op de meeste apparaten (sommige oudere Android-telefoons hebben mogelijk een nieuw profiel nodig) en hoeven hun e-mail niet opnieuw te downloaden.
    
Als u de volledige hybride migratie voor u geschikt vindt, raadpleegt u de volgende bronnen om u te helpen bij de migratie:
  
- [Exchange Deployment Assistant](https://aka.ms/exdeploy)
    
- [Hybride implementaties van Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)
    
- [Wizard hybride configuratie](https://technet.microsoft.com/library/hh529921%28v=exchg.150%29.aspx)
    
- [Veelgestelde vragen over de wizard hybride configuratie](https://technet.microsoft.com/library/mt488940%28v=exchg.150%29.aspx)
    
- [Vereisten voor hybride implementatie](https://technet.microsoft.com/library/hh534377%28v=exchg.150%29.aspx)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Migreren naar een nieuwere versie van Exchange Server

Hoewel we de beste waarde en gebruikerservaring kunnen bereiken door te migreren naar Microsoft 365, weten we ook dat sommige organisaties hun e-mail on-premises moeten bewaren. Dit kan ten gevolge van wettelijke vereisten zijn, om te zorgen dat gegevens niet worden opgeslagen in een datacenter dat zich in een ander land bevindt, enzovoort. Als u ervoor kiest om uw e-mails on-premises te houden, kunt u uw Exchange 2007-omgeving migreren naar Exchange 2010, Exchange 2013 of Exchange 2016.
  
U wordt aangeraden om te migreren naar Exchange 2016 als u niet kunt migreren naar Microsoft 365. Exchange 2016 omvat alle functies en beschikbare functies die zijn opgenomen in vorige releases van Exchange, en is het meest geschikt voor de beschikbare ervaring met Microsoft 365 (hoewel sommige functies alleen beschikbaar zijn in Microsoft 365). Bekijk slechts een paar van de dingen die u missen:
  
|**Exchange-versie**|**Functies**|
|:-----|:-----|
|Exchange 2010  <br/> | Toegangsbeheer op basis van rollen (machtigingen zonder Acl's)  <br/>  Beleidsregels voor Postvak in in Outlook Web app  <br/>  Mogelijkheid om beschikbaarheidsinfo te delen tussen organisaties en agenda's te delegeren  <br/> |
|Exchange 2013  <br/> | *Functies van Exchange 2010 en...*  <br/>  Vereenvoudigde architectuur voor het verminderen van het aantal serverrollen tot drie (Postvak, client toegang en Edge-transport)  <br/>  Beleidsregels voor preventie van gegevensverlies (DLP) om te voorkomen dat gevoelige informatie wordt lekt  <br/>  Aanzienlijk verbeterde Outlook Web app-ervaring  <br/> |
|Exchange 2016  <br/> | *Functies van Exchange 2013 en...*  <br/>  Uitgebreide serverfuncties uitsluitend voor postvak en Edge-transport  <br/>  Verbeterde DLP, naast integratie met SharePoint  <br/>  Verbeterde database tolerantie  <br/>  Online samenwerken aan documenten  <br/> |
   
#### <a name="which-version-should-i-migrate-to"></a>Naar welke versie moet ik migreren?

U wordt aangeraden dat u eerst migreert naar Exchange 2016. Vervolgens gaat u op de volgende informatie om uw hypothese of de regel Exchange 2016 te bevestigen. Als u niet om een of andere reden kunt migreren naar Exchange 2016, doet u hetzelfde proces met Exchange 2013, enzovoort.
  
|**Aanmerking**|**Meer informatie**|
|:-----|:-----|
|Einde van ondersteunings datums  <br/> | Net als Exchange 2007, heeft elke versie van Exchange een eigen einde van de ondersteunings datum:  <br/> **Exchange 2010** -januari 2020  <br/> **Exchange 2013** -april 2023  <br/> **Exchange 2016** -oktober 2025  <br/>  Hoe eerder het einde van de ondersteunings datum is, hoe sneller u een andere migratie moet uitvoeren. Januari 2020 is een heleboel dichter dan u ervan vindt!  <br/> |
|Configuratiepad voor Exchange 2010 en 2013  <br/> |Dit zijn de algemene fasen voor de migratie naar Exchange 2010 of Exchange 2013:  <br/> Installeer Exchange 2010 of 2013 in uw bestaande Exchange 2007-verplaatsings Services en andere infrastructuur naar Exchange 2010 of 2013 Verplaats postvakken en openbare mappen naar Exchange 2010 of 2013 decommissiond Exchange 2007-servers |
|Configuratiepad voor Exchange 2016  <br/> |Dit zijn de algemene fasen voor de migratie naar Exchange 2016:  <br/> Installeer Exchange 2013 in uw bestaande Exchange 2007-verplaatsings Services en andere infrastructuur naar Exchange 2013 postvakken en openbare mappen verplaatsen naar Exchange 2013 destappen Exchange 2007-servers installeren Exchange-beheerder installeren in uw bestaande Exchange-beheerder. Postvakken, openbare mappen, services en andere infrastructuur verplaatsen naar Exchange 2016 (de volgorde is niet belangrijk). Overige Exchange 2013-servers buiten bedrijf > [!NOTE]> migratie van exchange 2013 naar Exchange 2016 is eenvoudig. Beide versies hebben bijna dezelfde hardwarevereisten. Dit en deze versies zijn zo compatibel: u kunt een server die u hebt gekocht voor Exchange 2013 opnieuw opbouwen en Exchange 2016 installeren. En wanneer Online postvak wordt verplaatst, melden de meeste gebruikers niet dat het postvak wordt verplaatst van de server en daarna terug nadat u het opnieuw hebt gebouwd met Exchange 2016.           |
|Versies naast elkaar  <br/> | Wanneer u migreert naar:  <br/> **Exchange 2016** Exchange 2016 kan niet worden geïnstalleerd in een organisatie die een Exchange 2007-server bevat. U dient eerst te migreren naar Exchange 2010 of 2013 (wij raden u ten zeerste aan Exchange 2013), alle Exchange 2007-servers te verwijderen en vervolgens te migreren naar Exchange-2016.  <br/> **Exchange 2010 of exchange 2013** U kunt Exchange 2010 of Exchange 2013 installeren in een bestaande Exchange 2007-organisatie. Hiermee kunt u een of meer Exchange 2010-of 2013-servers installeren en uw migratie uitvoeren.  <br/> |
|Serverhardware  <br/> | De hardwarevereisten voor de server zijn gewijzigd in Exchange 2007. U moet ervoor zorgen dat de hardware die u gaat gebruiken compatibel is. U vindt hier meer informatie over de hardwarevereisten voor elke versie:  <br/> [Systeemvereisten voor Exchange 2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx) <br/> [Systeemvereisten voor Exchange 2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx) <br/> [Systeemvereisten voor Exchange 2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx) <br/>  U zult merken dat de belangrijkste verbeteringen in de prestaties van Exchange, en de betere computerkracht en-opslagcapaciteit in nieuwere servers, u waarschijnlijk minder servers nodig heeft om hetzelfde aantal postvakken te ondersteunen.  <br/> |
|Versie van besturingssysteem  <br/> | De minimaal ondersteunde besturingssysteemversies voor elke versie zijn:  <br/> **Exchange 2016** Windows Server 2012  <br/> **Exchange 2013** Windows Server 2008 R2 SP1  <br/> **Exchange 2010** Windows Server 2008 SP2  <br/>  U vindt meer informatie over de ondersteuning van besturingssystemen op de [Exchange-ondersteunings matrix](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Functioneel niveau van Active Directory-forest  <br/> | De minimaal ondersteunde functies voor Active Directory-forests voor elke versie zijn:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  U vindt meer informatie over de ondersteuning van het functionele niveau voor forests via de [Exchange-ondersteunings matrix](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Versies van Office-clients  <br/> | De minimaal ondersteunde versies van Office-clients voor elke versie zijn:  <br/> **Exchange 2016** Office 2010 (met de nieuwste updates)  <br/> **Exchange 2013** Office 2007 SP3  <br/> **Exchange 2010** Office 2003  <br/>  U vindt meer informatie over de ondersteuning van Office-clients op de site van [Exchange supportity](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
   
#### <a name="how-do-i-migrate"></a>Hoe migreer ik?

Als u hebt besloten dat u uw e-mailberichten on-premises wilt houden, kunt u de volgende bronnen gebruiken om u te helpen bij de migratie:
  
- [Exchange Deployment Assistant](https://aka.ms/exdeploy)
    
- Wijzigingen van Active Directory-schema voor Exchange [2016](https://technet.microsoft.com/library/bb738144%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb738144%28v=exchg.150%29.aspx), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- Systeemvereisten voor Exchange [2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx)
    
- Vereisten voor Exchange [2016](https://technet.microsoft.com/library/bb691354%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb691354%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/bb691354%28v=exchg.141%29.aspx)
    
## <a name="what-if-i-need-help"></a>En als ik hulp nodig heb?

Als u migreert naar Microsoft 365, komt u mogelijk in aanmerking voor de service van Microsoft FastTrack. FastTrack biedt aanbevolen procedures, hulpprogramma's en informatiebronnen om de migratie naar Microsoft 365 zo eenvoudig mogelijk te maken. Het beste van alles is dat u een echte ondersteuningstechnicus hebt die u ter verkrijging van uw migratie leert, van het plannen en ontwerpen van de overstap naar het laatste postvak. Als u meer wilt weten over FastTrack, raadpleegt u [Microsoft FastTrack](https://fasttrack.microsoft.com/).
  
Als u problemen ondervindt tijdens de migratie naar Microsoft 365 en u geen gebruikmaakt van FastTrack of de migratie naar een nieuwere versie van Exchange Server, dan kunnen we u helpen. Hier volgen enkele bronnen die u kunt gebruiken:
  
- [Technische community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Klantondersteuning](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Verwante onderwerpen

[Bronnen om u te helpen bij het upgraden van uw Office 2007-servers en-clients](upgrade-from-office-2007-servers-and-products.md)