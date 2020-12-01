---
title: Einde van ondersteunings schema van Exchange 2010
ms.author: dstrome
author: dstrome
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: e150e7b9-c432-4c8d-a0ae-c11847129a7d
f1.keywords:
- NOCSH
description: Exchange 2010 heeft het einde van de ondersteuning bereikt. Met deze plannings kaart kunt u een upgrade voorbereiden voor Exchange Online of een nieuwere versie van Exchange Server on-premises.
ms.openlocfilehash: 23384d93c4e65fb25a66ca6f2f0bcbe46b34ee18
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519689"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Einde van ondersteunings schema van Exchange 2010

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Exchange Server 2010 bereikte het einde van de ondersteuning op **13 oktober 2020**. Als u de migratie van Exchange 2010 naar Microsoft 365, Office 365 of Exchange 2016 nog niet hebt gemaakt, is het tijd om te beginnen met plannen.

## <a name="what-does-end-of-support-mean"></a>Wat betekent *einde van ondersteuning* ?

De meeste Microsoft-producten hebben een ondersteuningscyclus waarover ze nieuwe functies, foutoplossingen, beveiligingsfixes en dergelijke kunnen krijgen. Deze levenscyclus duurt doorgaans tien jaar lang uit de eerste versie van het product. Het einde van de levenscyclus is bekend als het einde van de ondersteuning van het product. Aangezien Exchange 2010 het einde van de ondersteuning op 13 oktober 2020 bereikt, biedt Microsoft niet langer:

- Technische ondersteuning voor problemen die kunnen optreden.
- Oplossingen voor problemen die gevolgen kunnen hebben voor de stabiliteit en bruikbaarheid van de server.
- Beveiligingscorrecties voor beveiligingsproblemen die de server kwetsbaar kunnen maken voor beveiligingsproblemen.
- Tijdzone-updates.

De installatie van Exchange 2010 blijft na deze datum actief. Maar vanwege de bovenstaande wijzigingen is het raadzaam van Exchange 2010 zo snel mogelijk te migreren vanaf Exchange.

Zie [bronnen om u te helpen bij het upgraden van Office 2010-servers en-clients](upgrade-from-office-2010-servers-and-products.md)voor meer informatie over het einde van de ondersteuning.

## <a name="what-are-my-options"></a>Wat zijn mijn mogelijkheden?

Het is een geweldig moment om uw opties te verkennen en een migratieplan voor te bereiden. U kunt:

- Volledig migreren naar Microsoft 365. Postvakken migreren met behulp van cutover, minimale hybride migratie of volledige hybride migratie. Verwijder vervolgens on-premises Exchange-servers en Active Directory.
- Migreer uw Exchange 2010-servers naar Exchange 2016 op uw on-premises servers.

> [!IMPORTANT]
> Als uw organisatie van plan is om postvakken te migreren naar Microsoft 365, maar abonnement om DirSync of Azure AD Connect op hun plaats te houden om door te gaan met het beheren van gebruikersaccounts vanuit on-premises Active Directory, moet u minimaal één Microsoft Exchange Server on-premises bewaren. Als u alle Exchange-servers verwijdert, kunt u geen wijzigingen aanbrengen in Exchange-geadresseerden in Exchange Online omdat de bron van de autoriteit in uw on-premises Active Directory blijft staan. U moet er wijzigingen in aanbrengen. In dit scenario hebt u de volgende opties:
>
>- *Aanbevolen:* Als u uw postvakken hebt gemigreerd naar Microsoft 365 en uw servers een upgrade hebt uitgevoerd vanaf 13 oktober 2020, kunt u Exchange 2010 gebruiken om verbinding te maken met Microsoft 365 en postvakken te migreren. Migreer daarna Exchange 2010 naar Exchange 2016 en Dede resterende Exchange 2010-servers buiten bedrijf.
>- Als u de migratie van postvakken en on-premises servers niet hebt voltooid vóór 13 oktober 2020, voert u eerst uw on-premises Exchange 2010-servers uit naar Exchange 2016. Vervolgens gebruikt u Exchange 2016 om verbinding te maken met Microsoft 365 en postvakken te migreren.

> [!NOTE]
> Het is iets ingewikkeld, maar u kunt ook postvakken migreren naar Microsoft 365 terwijl u uw on-premises Exchange 2010-servers migreert naar Exchange 2016.

Dit zijn de drie paden die u kunt nemen om te voorkomen dat de ondersteuning voor Exchange Server 2010 wordt beëindigd.

![Upgradepaden van Exchange Server 2010](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

In de volgende secties wordt elke optie uitvoerig besproken.

## <a name="migrate-to-microsoft-365"></a>Migreren naar Microsoft 365

Het migreren van uw e-mailbericht naar Microsoft 365 is de beste en eenvoudigste optie om u te helpen bij het buiten gebruik stellen van uw implementatie van Exchange 2010. Met een migratie naar Microsoft 365, kunt u één hop van oude technologie maken voor de huidige functies, zoals:

- Nalevings mogelijkheden zoals bewaarbeleid, In-Place en de bewaring in-place eDiscovery en meer.
- Microsoft teams.
- Power BI.
- Postvak in met prioriteit.
- MyAnalytics.

Microsoft 365 ontvangt ook nieuwe functies en ervaring, zodat uw organisatie direct aan de slag kan. Daarnaast hoeft u zich geen zorgen te maken over:

- Kopen en onderhouden van hardware.
- Betaalde systemen en coole servers.
- Up-to-date houden van oplossingen voor beveiliging, producten en tijdzone.
- Opslag en softwareonderhoud ter ondersteuning van nalevingsvereisten.
- Een upgrade uitvoeren naar een nieuwe versie van Exchange. U bevindt zich altijd in de nieuwste versie van Exchange in Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>Hoe moet ik migreren naar Microsoft 365?

Afhankelijk van uw organisatie hebt u een paar opties voor het gebruik van Microsoft 365. U dient eerst enkele zaken te doen, zoals:
- Het aantal stoelen of postvakken dat u wilt verplaatsen.
- Hoelang u de migratie wilt laten duren.
- Of u nu een naadloze integratie nodig hebt tussen uw on-premises installatie en Microsoft 365 tijdens de migratie.
 
In deze tabel worden de migratie opties en de belangrijkste factoren weergegeven om te bepalen welke methode moet worden gebruikt.

|Migratieoptie|Organisatie formaat|Peri|
|---|---|---|
|Cutover-migratie|Minder dan 150 stoelen|Een week of minder|
|Minimale Hybrid Migration|Minder dan 150 stoelen|Een paar weken of minder|
|Volledig hybride migratie|Meer dan 150 stoelen|Een paar weken of meer|

De volgende secties bieden een overzicht van deze methoden. Zie voor meer informatie [een pad voor de migratie kiezen](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27).

### <a name="cutover-migration"></a>Cutover-migratie

In een cutover-migratie migreert u alle postvakken, distributiegroepen, contactpersonen, enzovoort, naar Office 365 op een ingestelde datum en tijd. Wanneer u klaar bent, sluit u uw on-premises Exchange-servers af en gaat u verder met Microsoft 365.

Cutover-migratie is ideaal voor kleine organisaties die niet veel postvakken hebben, willen snel naar Microsoft 365 en willen de complexiteit van de andere methoden niet behandelen. Maar het moet binnen een week of minder worden voltooid. Gebruikers moeten hun Outlook-profielen opnieuw configureren. Met Cutover-migratie kunt u maximaal 2.000 postvakken migreren, maar we raden u aan om maximaal 150 te gebruiken. Als u meer probeert te migreren, kon u niet langer gebruikmaken van alle postvakken vóór de deadline en kunnen uw IT-ondersteuningsmedewerkers worden overspoeld met aanvragen om gebruikers te helpen opnieuw de configuratie van Outlook te helpen.

U dient rekening te houden met de volgende punten over de migratie van cutover:

- Microsoft 365 moet verbinding maken met uw Exchange 2010-servers via Outlook Anywhere en TCP-poort 443.
- Alle on-premises postvakken worden verplaatst naar Microsoft 365.
- U hebt een on-premises Administrator-account nodig met leestoegang tot de postvakken van uw gebruikers.
- De geaccepteerde domeinen van Exchange 2010 die u wilt gebruiken in Microsoft 365 moeten als geverifieerde domeinen worden toegevoegd aan de service.
- Wanneer u de migratie start en wanneer u de voltooiings fase begint, worden in Microsoft 365 regelmatig de postvakken van Microsoft 365 en on-premises gesynchroniseerd. Hiermee kunt u de migratie voltooien, zonder dat u zich zorgen hoeft te maken over e-mail achter uw on-premises postvakken.
- Gebruikers ontvangen nieuwe tijdelijke wachtwoorden voor hun Microsoft 365-account. De persoon moet die persoon wijzigen wanneer ze zich voor de eerste keer aanmelden bij hun postvakken.
- Voor elk gebruikerspostvak dat u migreert, moet u een licentie voor Microsoft 365 met Exchange Online hebben.
- Gebruikers moeten een nieuw Outlook-profiel op elk van hun apparaten instellen en hun e-mail opnieuw downloaden. De hoeveelheid e-mail die in Outlook wordt gedownload, kan variëren. Zie [offline werken in Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633)voor meer informatie.

Zie voor meer informatie over cutover-migratie:

- [Wat u moet weten over een cutover-e-mail migratie](https://docs.microsoft.com/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Een cutover-migratie van e-mail naar Office 365 uitvoeren](https://docs.microsoft.com/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Minimale Hybrid Migration

Bij een minimale Hybrid-of snelle migratie zet u gedurende enkele weken een paar honderd postvakken naar Microsoft 365. Deze methode biedt geen ondersteuning voor geavanceerde Hybrid-migratiefuncties, zoals gedeelde agendagegevens van een beschikbaarheidsinfo.

De minimale hybride migratie is ideaal voor organisaties die meer tijd nodig hebben om hun postvakken te migreren naar Microsoft 365, maar wel de voltooiing van de migratie binnen enkele weken. U krijgt enkele voordelen van de uitgebreidere *volledige hybride migratie* zonder veel van de complexiteit. U kunt bepalen hoeveel en welke postvakken op een bepaald moment worden gemigreerd. Microsoft 365-postvakken worden gemaakt met de gebruikersnamen en wachtwoorden van de on-premises accounts. In tegenstelling tot cutover-migraties hoeven uw gebruikers hun Outlook-profielen niet opnieuw te maken.

Hier volgen enkele aandachtspunten bij minimale Hybrid Migration:

- U moet een eenmalige synchronisatie uitvoeren tussen uw on-premises Active Directory-servers en Microsoft 365.
- Gebruikers kunnen zich aanmelden bij hun Microsoft 365-postvak met dezelfde gebruikersnaam en hetzelfde wachtwoord als vóór hun postvak.
- Voor elk gebruikerspostvak dat u migreert, moet u een licentie voor Microsoft 365 met Exchange Online opnemen voor elk gebruikerspostvak dat u wilt migreren.
- Gebruikers hoeven geen nieuw Outlook-profiel in te stellen op de meeste apparaten, hoewel voor sommige oudere Android-telefoons mogelijk een nieuw profiel is vereist. Gebruikers hoeven hun e-mail niet opnieuw te downloaden.

Voor meer informatie raadpleegt [u minimale Hybrid gebruiken om snel Exchange-postvakken te migreren naar Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate).

### <a name="full-hybrid"></a>Volledige hybride

Bij een volledige hybride migratie hebt u veel honderden, tot tientallen duizenden, van postvakken, en kunt u alles of alles verplaatsen naar Microsoft 365. Omdat deze migraties doorgaans langer lang zijn, kunt u het volgende doen met hybride migraties:

- On-premises gebruikers van de beschikbaarheidsinfo weergeven voor gebruikers in Microsoft 365 en omgekeerd.
- Een geïntegreerde algemene adreslijst weergeven met geadresseerden in zowel on-premises als in Microsoft 365.
- Alle Outlook-instellingen voor geadresseerden weergeven voor alle gebruikers, ongeacht of ze on-premises of in Microsoft 365.
- Beveilig e-mail communicatie tussen on-premises Exchange-servers en Office 365 met behulp van TLS en certificaten.
- Berichten behandelen die zijn verzonden tussen on-premises Exchange-servers en Microsoft 365 als intern, zodat ze het volgende kunnen doen:
  - U wordt op de juiste wijze geëvalueerd en verwerkt door agents en compliance-medewerkers die interne berichten richten.
  - Negeer antispam filters.

Volledige hybride migraties zijn geschikt voor organisaties die verwachten dat ze gedurende een of meer maanden een hybride configuratie blijven. U ontvangt de functies die eerder in deze sectie worden vermeld, plus adreslijstsynchronisatie, betere geïntegreerde functies voor naleving en de mogelijkheid om postvakken te verplaatsen naar en naar Microsoft 365 via Online postvak wordt verplaatst. Microsoft 365 wordt een uitbreiding van uw on-premises organisatie.

Aandachtspunten voor de volledige hybride migratie:

- Ze zijn niet geschikt voor alle organisaties. Vanwege de complexiteit van de volledige hybride migraties zijn organisaties met minder dan een paar honderd postvakken meestal geen voordelen te zien die de inspanning en de kosten rechtvaardigen. In dergelijke gevallen is het raadzaam om in plaats hiervan cutover of minimale hybride migratie uit te voeren.
- U moet adreslijstsynchronisatie instellen met Azure Active Directory (Azure AD) verbinding maken tussen uw on-premises Active Directory-servers en Microsoft 365.
- Gebruikers kunnen zich aanmelden bij hun Microsoft 365-postvak met dezelfde gebruikersnaam en hetzelfde wachtwoord als ze zich aanmelden bij het lokale netwerk. Voor deze functionaliteit is Azure AD Connect met Wachtwoordsynchronisatie en/of Active Directory Federation Services vereist.
- U hebt een Microsoft 365-licentie met Exchange Online nodig voor elk gebruikerspostvak dat u wilt migreren.
- Gebruikers hoeven geen nieuw Outlook-profiel in te stellen op de meeste apparaten, hoewel voor sommige oudere Android-telefoons mogelijk een nieuw profiel is vereist. Gebruikers hoeven hun e-mail niet opnieuw te downloaden.

> [!IMPORTANT]
> Als in uw organisatie postvakken worden gemigreerd naar Microsoft 365, maar het gebruik van DirSync of Azure AD Connect op de juiste plaats om door te gaan met het beheren van gebruikersaccounts vanuit on-premises Active Directory, moet u ten minste één Exchange Server on-premises bewaren. Als alle Exchange-servers worden verwijderd, kunt u geen wijzigingen aanbrengen in Exchange-geadresseerden in Exchange Online. Dit komt doordat de bron van de autoriteit in uw on-premises Active Directory blijft staan en de wijzigingen daar moeten worden aangebracht.

Raadpleeg de volgende nuttige bronnen als een volledige hybride migratie voor u geschikt is voor u:

- [Exchange Deployment Assistant](https://aka.ms/exdeploy)
- [Hybride implementaties van Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid)
- [Wizard hybride configuratie](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)
- [Veelgestelde vragen over de wizard hybride configuratie](https://docs.microsoft.com/exchange/hybrid-configuration-wizard-faqs)
- [Vereisten voor hybride implementatie](https://docs.microsoft.com/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Een upgrade uitvoeren naar een nieuwere versie van Exchange Server on-premises

We geloven dat u de beste prijs en de gebruikerservaring krijgt door volledig te migreren naar Microsoft 365. Maar we begrijpen dat sommige organisaties hun on-premises Exchange-servers on-premises moeten bewaren. Dit kan ten gevolge van wettelijke vereisten zijn, voor het garanderen van gegevens in een buitenlands datacenter, omdat u unieke instellingen of vereisten hebt die niet in de Cloud kunnen worden gebruikt, of omdat u Exchange moet gebruiken voor het beheren van Cloud postvakken omdat u nog steeds Active Directory gebruikt. Als u Exchange on-premises aanmeldt, moet u ervoor zorgen dat uw Exchange 2010-omgeving wordt bijgewerkt naar ten minste Exchange 2013 of Exchange 2016.

Voor de beste ervaring raden we u aan de resterende lokale on-premises omgeving te upgraden naar Exchange 2016. U hoeft Exchange Server 2013 niet te installeren als u rechtstreeks van Exchange Server 2010 naar Exchange Server 2016 wilt gaan.

Exchange 2016 omvat alle functies van vorige releases van Exchange. Dit komt overeen met de beschikbare ervaring met Microsoft 365, alhoewel sommige functies alleen beschikbaar zijn in Microsoft 365. Bekijk slechts een paar van de dingen die u missen:

|Exchange-versie|Functies|
|---|---|
|**Exchange 2013**|Vereenvoudigde architectuur Hiermee wordt het aantal serverrollen beperkt tot drie (Postvak, client toegang en Edge-transport)|
||Beleidsregels voor preventie van gegevensverlies (DLP) om te voorkomen dat gevoelige informatie wordt lekt|
||Verbeterde Outlook Web app-ervaring|
|**Exchange 2016**|*Functies van Exchange 2013 en...*|
||Uitgebreide serverfuncties uitsluitend voor postvak en Edge-transport|
||Verbeterde DLP, naast integratie met SharePoint|
||Verbeterde database tolerantie|
||Online samenwerken aan documenten|

|Aanmerking|Meer informatie|
|---|---|
|Einde van ondersteunings datums|Net als Exchange 2010, heeft elke versie van Exchange een eigen datum voor de einde-en ondersteunings datum:<br/><br/>Exchange 2013-april 2023<br/>Exchange 2016-oktober 2025<br/><br/>Hoe eerder de laatste dag van de ondersteuning, hoe sneller u een andere migratie moet uitvoeren. April 2023 is een heleboel dichter dan u ervan vindt!|
|Configuratiepad voor Exchange 2013 of 2016|Het metabasepad van Exchange 2010 naar een nieuwere versie is hetzelfde, ongeacht of u Exchange 2013 of Exchange 2016 kiest:<br/><br/>Installeer Exchange 2013 of 2016 in uw bestaande Exchange 2010-organisatie.<br/>Services en andere infrastructuur overbrengen naar Exchange 2013 of 2016.<br/>Postvakken en openbare mappen verplaatsen naar Exchange 2013 of 2016 decommissioning resterende Exchange 2010-servers.|
|Versies naast elkaar|Wanneer u migreert naar Exchange 2013 of Exchange 2016, kunt u de versie installeren in een bestaande Exchange 2010-organisatie. Hiermee kunt u een of meer Exchange 2013-of Exchange 2016-servers installeren en de migratie uitvoeren.|
|Serverhardware|De hardwarevereisten voor de server zijn gewijzigd in Exchange 2010. Zorg dat de hardware compatibel is. Lees hier meer over de hardwarevereisten voor elke versie:<br/><br/>[Systeemvereisten voor Exchange 2016](https://docs.microsoft.com/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)<br/>[Systeemvereisten voor Exchange 2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)<br/><br/>Met de belangrijkste verbeteringen in de prestaties van Exchange en de verbeterde bewerkings capaciteit van de computer in nieuwere servers, hebt u waarschijnlijk minder servers om hetzelfde aantal postvakken te ondersteunen.|
|Versie van besturingssysteem|De minimaal ondersteunde besturingssysteemversies voor elke versie zijn:<br/><br/>Exchange 2016-Windows Server 2012<br/>Exchange 2013-Windows Server 2008 R2 SP1<br/><br/>U vindt meer informatie over de ondersteuning van besturingssystemen op de [Exchange-ondersteunings matrix](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Functioneel niveau van Active Directory-forest|De minimaal ondersteunde functies voor Active Directory-forests voor elke versie zijn:<br/><br/>Exchange 2016-Windows Server 2008 R2 SP1<br/>Exchange 2013-Windows Server 2003<br/><br/>U vindt meer informatie over de ondersteuning van het functionele niveau voor forests via de [Exchange-ondersteunings matrix](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Versies van Office-clients|De minimaal ondersteunde versies van Office-clients voor elke versie zijn:<br/><br/>Exchange 2016-Office 2010 (met de nieuwste updates)<br/>Exchange 2013-Office 2007 SP3<br/><br/>Ga voor meer informatie over de ondersteuning van Office-clients naar de [Exchange-ondersteunings matrix](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).||| 


Gebruik de volgende bronnen voor hulp bij de migratie:

- [Exchange Deployment Assistant](https://aka.ms/exdeploy)
- Wijzigingen van Active Directory-schema voor Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- Systeemvereisten voor Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/system-requirements?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Vereisten voor Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/prerequisites?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Overzicht van opties voor Office 2010-client en-servers en Windows 7

Voor een visueel overzicht van de opties voor de upgrade, migratie en verplaatsen van een upgrade, migratie en migratie van Office 2010-clients en-servers en Windows 7, raadpleegt u het [einde van de ondersteunings poster](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Einde van de ondersteuning voor Office 2010-clients en-servers en Windows 7-poster](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Deze poster van één pagina toont de verschillende paden die u kunt nemen om te reageren op de client van Office 2010 en Server producten en Windows 7 waarbij u de ondersteuning van de gewenste paden en optie in Microsoft 365 Enterprise hebt gemarkeerd.

U kunt deze poster ook [downloaden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) en afdrukken met de indeling letter, juridisch of tabloid (11 x 17).

## <a name="what-if-i-need-help"></a>En als ik hulp nodig heb?

Als u migreert naar Microsoft 365, komt u mogelijk in aanmerking voor de service van Microsoft FastTrack. FastTrack biedt aanbevolen procedures, hulpprogramma's en informatiebronnen om de migratie naar Microsoft 365 zo eenvoudig mogelijk te maken. De beste van alles is een ondersteuningsmedewerker waarmee u door de planning en het ontwerp van uw laatste postvak wordt gemigreerd. Zie [Microsoft FastTrack](https://fasttrack.microsoft.com/)voor meer informatie over FastTrack.

Als u problemen ondervindt tijdens de migratie naar Microsoft 365 en u geen gebruikmaakt van FastTrack of als u migreert naar een nieuwere versie van Exchange Server, kunt u de volgende bronnen gebruiken:

- [Technische community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Klantondersteuning](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>Verwante artikelen

[Bronnen om u te helpen bij het upgraden van Office 2010-servers en-clients](upgrade-from-office-2010-servers-and-products.md)
