---
title: Exchange 2010 einde van de ondersteuningsroutekaart
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
description: Exchange 2010 heeft het einde van de ondersteuning bereikt. Gebruik deze planningsroutekaart om een upgrade uit te voeren naar Exchange Online of een nieuwere versie van Exchange Server on-premises.
ms.openlocfilehash: bbc7fb83537621a47a866bf0ca129a38e21f055e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289125"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Exchange 2010 einde van de ondersteuningsroutekaart

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Exchange Server 2010 heeft het einde van de ondersteuning bereikt op **13 oktober 2020**. Als u nog niet bent begonnen met de migratie van Exchange 2010 naar Microsoft 365, Office 365 of Exchange 2016, is het nu tijd om te beginnen met plannen.

## <a name="what-does-end-of-support-mean"></a>Wat betekent *het einde van de ondersteuning?*

De meeste Microsoft-producten hebben een ondersteuningslevenscyclus waarin ze nieuwe functies, bugfixes, beveiligingsfixes, en ga zo maar door krijgen. Deze levenscyclus duurt meestal tien jaar vanaf de eerste release van het product. Het einde van deze levenscyclus wordt het einde van de ondersteuning van het product genoemd. Omdat Exchange 2010 op 13 oktober 2020 het einde van de ondersteuning heeft bereikt, biedt Microsoft niet meer:

- Technische ondersteuning voor problemen die kunnen optreden.
- Oplossingen voor problemen die van invloed kunnen zijn op de stabiliteit en bruikbaarheid van de server.
- Beveiligingsfixes voor beveiligingsproblemen die de server kwetsbaar kunnen maken voor beveiligingsinbreuken.
- Tijdzone-updates.

De installatie van Exchange 2010 blijft na deze datum worden uitgevoerd. Maar vanwege de bovenstaande wijzigingen raden we u ten zeerste aan om zo Exchange 2010 te migreren.

Zie Resources om u te helpen een upgrade uit te voeren van Office [2010-servers en -clients](upgrade-from-office-2010-servers-and-products.md)voor meer informatie over het einde van de ondersteuning.

## <a name="what-are-my-options"></a>Wat zijn mijn opties?

Het is een goed moment om uw opties te verkennen en een migratieplan voor te bereiden. U kunt:

- Volledig migreren naar Microsoft 365. Postvakken migreren met cutover, minimale hybride of volledige hybride migratie. Verwijder vervolgens on-premises Exchange servers en Active Directory.
- Migreert Exchange 2010-servers naar Exchange 2016 op uw on-premises servers.

> [!IMPORTANT]
> Als uw organisatie ervoor kiest om postvakken te migreren naar Microsoft 365, maar dirSync of Azure AD Verbinding maken wilt behouden om gebruikersaccounts te blijven beheren vanuit on-premises Active Directory, moet u ten minste één Microsoft-Exchange-server on-premises houden. Als u alle Exchange-servers verwijdert, kunt u geen wijzigingen aanbrengen in Exchange-geadresseerden in Exchange Online omdat de bron van autoriteit in uw on-premises Active Directory blijft staan. Daar moeten wijzigingen worden aangebracht. In dit scenario hebt u de volgende opties:
>
>- *Aanbevolen:* Als u uw postvakken hebt gemigreerd naar Microsoft 365 en uw servers hebt bijgewerkt op 13 oktober 2020, gebruikt u Exchange 2010 om verbinding te maken met Microsoft 365 en postvakken te migreren. Vervolgens migreert Exchange 2010 naar Exchange 2016 en ontmantelt u alle resterende Exchange 2010-servers.
>- Als u de postvakmigratie en on-premises server-upgrade niet hebt voltooid op 13 oktober 2020, upgradet u eerst uw on-premises Exchange 2010-servers naar Exchange 2016. Gebruik vervolgens Exchange 2016 om verbinding te maken met Microsoft 365 en postvakken te migreren.

> [!NOTE]
> Het is iets ingewikkelder, maar u kunt ook postvakken migreren naar Microsoft 365 terwijl u uw on-premises Exchange 2010-servers migreert naar Exchange 2016.

Hier volgen de drie paden die u kunt volgen om het einde van de ondersteuning voor Exchange Server 2010 te voorkomen.

![Exchange Server upgradepaden voor 2010](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

In de volgende secties wordt elke optie uitgebreider verkend.

## <a name="migrate-to-microsoft-365"></a>Migreren naar Microsoft 365

Het migreren van uw e-mail naar Microsoft 365 is de beste en eenvoudigste optie om u te helpen uw implementatie Exchange 2010 te stoppen. Met een migratie naar Microsoft 365 kunt u één hop maken van oude technologie naar huidige functies, waaronder:

- Compliancemogelijkheden, zoals bewaarbeleid, In-Place en bewaring van rechtszaken, in-place eDiscovery en meer.
- Microsoft Teams.
- Power BI.
- Postvak IN met focus.
- MyAnalytics.

Microsoft 365 krijgt ook eerst nieuwe functies en ervaringen, zodat uw organisatie ze meteen kan gaan gebruiken. U hoeft zich ook geen zorgen te maken over:

- Hardware aanschaffen en onderhouden.
- Betalen om uw servers te warmen en af te koelen.
- Up-to-date blijven op het gebied van beveiligings-, product- en tijdzone-oplossingen.
- Opslag en software onderhouden ter ondersteuning van nalevingsvereisten.
- Een upgrade uitvoeren naar een nieuwe versie van Exchange. U bent altijd op de nieuwste versie van Exchange in Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>Hoe moet ik migreren naar Microsoft 365?

Afhankelijk van uw organisatie hebt u een aantal opties om uw Microsoft 365. Eerst moet u rekening houden met een paar dingen, zoals:

- Het aantal stoelen of postvakken dat u moet verplaatsen.
- Hoe lang wilt u de migratie laten duren?
- Of u een naadloze integratie nodig hebt tussen uw on-premises installatie en Microsoft 365 tijdens de migratie.

In deze tabel ziet u de migratieopties en de belangrijkste factoren die bepalen welke methode moet worden gebruikt.

<br>

****

|Migratieoptie|Grootte van organisatie|Duur|
|---|---|---|
|Cutover-migratie|Minder dan 150 zitplaatsen|Een week of minder|
|Minimale hybride migratie|Minder dan 150 zitplaatsen|Een paar weken of minder|
|Volledige hybride migratie|Meer dan 150 zitplaatsen|Een paar weken of meer|
|

In de volgende secties ziet u een overzicht van deze methoden. Zie Beslissen over een migratiepad voor [meer informatie.](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)

### <a name="cutover-migration"></a>Cutover-migratie

In een cutover-migratie migreert u al uw postvakken, distributiegroepen, contactpersonen, Office 365 op een bepaalde datum en tijd. Wanneer u klaar bent, sluit u uw on-premises Exchange en gebruikt u Microsoft 365 alleen.

Cutover-migratie is zeer belangrijk voor kleine organisaties die niet veel postvakken hebben, snel naar Microsoft 365 willen gaan en niet willen omgaan met de complexiteit van de andere methoden. Maar het moet over een week of minder zijn voltooid. En gebruikers moeten hun profiel opnieuw Outlook configureren. Cutover-migratie kan maximaal 2000 postvakken migreren, maar u wordt aangeraden deze te gebruiken voor maximaal 150. Als u meer probeert te migreren, hebt u mogelijk geen tijd meer om alle postvakken vóór uw deadline over te dragen en kunnen uw IT-ondersteuningsmedewerkers overstelpt raken met verzoeken om gebruikers te helpen hun postvakken opnieuw Outlook.

Hier zijn dingen die u moet overwegen over cutover-migratie:

- Microsoft 365 moet verbinding maken met uw Exchange 2010-servers met behulp van Outlook Anywhere via TCP-poort 443.
- Alle on-premises postvakken worden verplaatst naar Microsoft 365.
- U hebt een on-premises beheerdersaccount nodig dat toegang heeft tot de postvakken van uw gebruikers.
- De Exchange 2010 geaccepteerde domeinen die u wilt gebruiken in Microsoft 365 moeten worden toegevoegd als geverifieerde domeinen in de service.
- Tussen wanneer u de migratie start en wanneer u de voltooiingsfase start, worden Microsoft 365 regelmatig de Microsoft 365 en on-premises postvakken gesynchroniseerd. Hiermee kunt u de migratie voltooien zonder dat u zich zorgen hoeft te maken dat e-mail achterblijft in uw on-premises postvakken.
- Gebruikers ontvangen nieuwe tijdelijke wachtwoorden voor hun Microsoft 365 account. Ze moeten deze wijzigen wanneer ze zich voor de eerste keer aanmelden bij hun postvakken.
- U hebt een licentie Microsoft 365 nodig met Exchange Online voor elk gebruikerspostvak dat u migreert.
- Gebruikers moeten een nieuw profiel Outlook op elk van hun apparaten instellen en hun e-mail opnieuw downloaden. De hoeveelheid e-mail die Outlook wordt gedownload, kan variëren. Zie Offline werken [in Outlook.](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633)

Zie voor meer informatie over cutover-migratie:

- [Wat u moet weten over een cutover-e-mailmigratie](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Een cutover-migratie van e-mail naar Office 365](/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Minimale hybride migratie

In een minimale hybride of express-migratie verplaatst u een paar honderd postvakken naar Microsoft 365 binnen enkele weken. Deze methode biedt geen ondersteuning voor geavanceerde functies voor hybride migratie, zoals gedeelde gratis/drukke agendagegevens.

Minimale hybride migratie is zeer belangrijk voor organisaties die meer tijd nodig hebben om hun postvakken te migreren naar Microsoft 365, maar nog steeds van plan zijn om de migratie binnen enkele weken te voltooien. U krijgt enkele van de voordelen van de meer geavanceerde *volledig hybride migratie* zonder veel complexiteit. U kunt bepalen hoeveel postvakken en welke postvakken op een bepaald moment moeten worden gemigreerd. Microsoft 365 postvakken worden gemaakt met de gebruikersnamen en wachtwoorden van de on-premises accounts. En in tegenstelling tot cutover-migraties hoeven uw gebruikers hun profiel niet opnieuw Outlook maken.

Hier zijn dingen die u moet overwegen over minimale hybride migratie:

- U moet een een-time adreslijstsynchronisatie tussen uw on-premises Active Directory-servers en -Microsoft 365.
- Gebruikers kunnen zich aanmelden bij hun Microsoft 365 postvak met dezelfde gebruikersnaam en hetzelfde wachtwoord als vóór hun postvak.
- U hebt een licentie Microsoft 365 met Exchange Online voor elk gebruikerspostvak dat u migreert.
- Gebruikers hoeven op de meeste apparaten geen nieuw Outlook in te stellen, hoewel sommige oudere Android-telefoons mogelijk een nieuw profiel nodig hebben. Gebruikers hoeven hun e-mail niet opnieuw te downloaden.

Zie Minimale hybride gebruiken om snel Exchange postvakken te migreren naar [Office 365.](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)

### <a name="full-hybrid"></a>Volledig hybride

In een volledige hybride migratie hebt u vele honderden, tot tienduizenden postvakken en verplaatst u sommige of alle postvakken naar Microsoft 365. Omdat deze migraties meestal op langere termijn zijn, kunnen hybride migraties het volgende doen:

- On-premises gebruikers de gratis/bezet agendagegevens voor gebruikers in Microsoft 365 en vice versa.
- Zie een geïntegreerde algemene adreslijst met geadresseerden in zowel on-premises als Microsoft 365.
- Volledige Outlook voor alle gebruikers weergeven, ongeacht of ze on-premises of in Microsoft 365.
- Beveilig e-mailcommunicatie tussen on-premises Exchange servers en Office 365 met TLS en certificaten.
- Berichten die worden verzonden tussen on-premises Exchange servers en Microsoft 365 behandelen als intern, zodat ze het volgende kunnen doen:
  - Correct worden geëvalueerd en verwerkt door transport- en complianceagenten die zich richten op interne berichten.
  - Antispamfilters omzeilen.

Volledige hybride migraties zijn het beste voor organisaties die verwachten dat ze maanden of langer in een hybride configuratie blijven. U krijgt de functies die eerder in deze sectie worden vermeld, plus adreslijstsynchronisatie, betere geïntegreerde compliancefuncties en de mogelijkheid om postvakken te verplaatsen van en naar Microsoft 365 met onlinepostvakbewegingen. Microsoft 365 wordt een uitbreiding van uw on-premises organisatie.

Dingen waar u rekening mee moet houden bij volledig hybride migratie:

- Ze zijn niet geschikt voor alle organisaties. Vanwege de complexiteit van volledig hybride migraties zien organisaties met minder dan een paar honderd postvakken meestal geen voordelen die de inspanning en kosten rechtvaardigen. In dergelijke gevallen raden we u aan in plaats daarvan een cutover of minimale hybride migratie te overwegen.
- U moet adreslijstsynchronisatie instellen met Azure Active Directory (Azure AD) Verbinding maken tussen uw on-premises Active Directory-servers en Microsoft 365.
- Gebruikers kunnen zich aanmelden bij hun Microsoft 365 met dezelfde gebruikersnaam en hetzelfde wachtwoord als wanneer ze zich aanmelden bij het lokale netwerk. (Voor deze functionaliteit is Azure AD Verbinding maken met wachtwoordsynchronisatie en/of Active Directory Federation Services).
- U hebt een Microsoft 365 nodig met Exchange Online voor elk gebruikerspostvak dat u migreert.
- Gebruikers hoeven op de meeste apparaten geen nieuw Outlook instellen, hoewel sommige oudere Android-telefoons mogelijk een nieuw profiel nodig hebben. Gebruikers hoeven hun e-mail niet opnieuw te downloaden.

> [!IMPORTANT]
> Als uw organisatie ervoor kiest om postvakken te migreren naar Microsoft 365, maar dirSync of Azure AD Verbinding maken wilt behouden om gebruikersaccounts te blijven beheren vanuit on-premises Active Directory, moet u ten minste één Exchange-server on-premises houden. Als alle Exchange servers worden verwijderd, kunt u geen wijzigingen aanbrengen in Exchange geadresseerden in Exchange Online. Dit komt omdat de bron van autoriteit in uw on-premises Active Directory blijft en er wijzigingen moeten worden aangebracht.

Als een volledige hybride migratie voor u goed klinkt, bekijkt u de volgende nuttige bronnen:

- [Exchange Implementatieassistent](/exchange/exchange-deployment-assistant)
- [Exchange Server Hybride implementaties](/exchange/exchange-hybrid)
- [Wizard Hybride configuratie](/exchange/hybrid-configuration-wizard)
- [Veelgestelde vragen over de wizard Hybride configuratie](/exchange/hybrid-configuration-wizard-faqs)
- [Vereisten voor hybride implementatie](/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Upgraden naar een nieuwere versie van Exchange Server on-premises

We zijn ervan overtuigd dat u de beste waarde en gebruikerservaring krijgt door volledig te migreren naar Microsoft 365. We begrijpen echter dat sommige organisaties bepaalde servers on-premises Exchange moeten houden. Dit kan komen door wettelijke vereisten, om te garanderen dat gegevens niet worden opgeslagen in een buitenlands datacenter, omdat u unieke instellingen of vereisten hebt die niet kunnen worden voldaan in de cloud, of omdat u Exchange nodig hebt om cloudpostvakken te beheren, omdat u active directory nog steeds on-premises gebruikt. Als u uw Exchange in elk geval on-premises houdt, moet u ervoor zorgen dat uw Exchange 2010-omgeving wordt bijgewerkt naar ten minste Exchange 2013 of Exchange 2016.

Voor de beste ervaring raden we u aan uw resterende on-premises omgeving te upgraden naar Exchange 2016. U hoeft Exchange Server 2013 niet te installeren als u rechtstreeks van Exchange Server 2010 naar Exchange Server 2016 wilt gaan.

Exchange 2016 bevat alle functies van eerdere versies van Exchange. Het komt het meest overeen met de ervaring die beschikbaar is met Microsoft 365, hoewel sommige functies alleen beschikbaar zijn in Microsoft 365. Bekijk een paar dingen die u hebt gemist:

<br>

****

|Exchange release|Functies|
|---|---|
|**Exchange 2013**|Vereenvoudigde architectuur vermindert het aantal serverrollen tot drie (Postvak, Clienttoegang, Edge Transport)|
||Beleid voor preventie van gegevensverlies (DLP) om te voorkomen dat gevoelige informatie lekt|
||Verbeterde Outlook Web App ervaring|
|**Exchange 2016**|*Functies uit Exchange 2013 en ...*|
||Verder vereenvoudigde serverrollen naar alleen Postvak en Edge Transport|
||Verbeterde DLP samen met integratie met SharePoint|
||Verbeterde databaseweerbaarheid|
||Online documentsamenwerking|
|

<br>

****

|Overweging|Meer informatie|
|---|---|
|Einde van ondersteuningsdatums|Net Exchange 2010 heeft elke versie van Exchange een eigen einddatum voor ondersteuning: <p> Exchange 2013 - april 2023 <p> Exchange 2016 - oktober 2025 <p> Hoe eerder de einddatum van de ondersteuning is, hoe eerder u een andere migratie moet uitvoeren. April 2023 is veel dichterbij dan u denkt!|
|Migratiepad naar Exchange 2013 of 2016|Het migratiepad van Exchange 2010 naar een nieuwere versie is hetzelfde, ongeacht of u Exchange 2013 of Exchange 2016: <p> Installeer Exchange 2013 of 2016 in uw bestaande Exchange 2010-organisatie. <p> Services en andere infrastructuur verplaatsen naar Exchange 2013 of 2016. <p> Postvakken en openbare mappen verplaatsen naar Exchange 2013 of 2016 De resterende resterende Exchange 2010-servers.|
|Coëxistentie van versie|Wanneer u migreert naar Exchange 2013 of Exchange 2016, kunt u een van de versies installeren in een bestaande Exchange 2010-organisatie. Hiermee kunt u een of meer servers Exchange 2013 of Exchange 2016 installeren en uw migratie doen.|
|Serverhardware|De vereisten voor serverhardware zijn gewijzigd Exchange 2010. Zorg ervoor dat uw hardware compatibel is. Meer informatie over hardwarevereisten voor elke versie vindt u hier: <p> [Exchange systeemvereisten voor 2016](/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016&preserve-view=true) <p> [Exchange systeemvereisten voor 2013](/Exchange/exchange-2013-system-requirements-exchange-2013-help) <p> Met de aanzienlijke verbeteringen in Exchange prestaties en de toegenomen rekenkracht en opslagcapaciteit in nieuwere servers, hebt u waarschijnlijk minder servers nodig om hetzelfde aantal postvakken te ondersteunen.|
|Versie van besturingssysteem|De minimaal ondersteunde besturingssysteemversies voor elke versie zijn: <p> Exchange 2016 - Windows Server 2012 <p> Exchange 2013 - Windows Server 2008 R2 SP1 <p> U vindt meer informatie over de ondersteuning van het besturingssysteem [Exchange Ondersteuningsmatrix.](/exchange/plan-and-deploy/supportability-matrix)|
|Active Directory-forestfunctionaliteitsniveau|De minimaal ondersteunde active directory-forestfunctionaliteitsniveaus voor elke versie zijn: <p> Exchange 2016 - Windows Server 2008 R2 SP1 <p> Exchange 2013 - Windows Server 2003 <p> U vindt meer informatie over ondersteuning voor forestfunctionaliteit op [Exchange Ondersteuningsmatrix.](/exchange/plan-and-deploy/supportability-matrix)|
|Office clientversies|De minimaal ondersteunde Office clientversies voor elke versie zijn: <p> Exchange 2016 - Office 2010 (met de meest recente updates) <p> Exchange 2013 - Office 2007 SP3 <p> Meer informatie over Office clientondersteuning vindt [u Exchange Ondersteuningsmatrix.](/exchange/plan-and-deploy/supportability-matrix)|
|

Gebruik de volgende bronnen om te helpen bij uw migratie:

- [Exchange Implementatieassistent](/exchange/exchange-deployment-assistant)
- Active Directory-schemawijzigingen voor Exchange [2016](/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016&preserve-view=true), [2013](/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- Systeemvereisten voor Exchange [2016](/exchange/plan-and-deploy/system-requirements?view=exchserver-2016&preserve-view=true), [2013](/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Vereisten voor Exchange [2016](/exchange/plan-and-deploy/prerequisites?view=exchserver-2016&preserve-view=true), [2013](/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Overzicht van opties voor Office 2010-client en -servers en Windows 7

Zie het einde van de ondersteuningsposter voor een visueel overzicht van de upgrade, migreren en verplaatsen naar de [](../downloads/Office2010Windows7EndOfSupport.pdf)cloudopties voor Office 2010-clients en -servers en Windows 7.

[![Einde van ondersteuning voor Office 2010-clients en -servers en Windows 7 poster](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Deze poster met één pagina illustreert de verschillende paden die u kunt volgen om te reageren op Office 2010-client- en serverproducten en Windows 7 die het einde van de ondersteuning bereiken, met voorkeurspaden en optieondersteuning in Microsoft 365 Enterprise gemarkeerd.

U kunt deze [poster ook](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) downloaden en afdrukken in de notatie letter, legal of tabloid (11 x 17).

## <a name="what-if-i-need-help"></a>Wat moet ik doen als ik hulp nodig heb?

Als u migreert naar Microsoft 365, komt u mogelijk in aanmerking voor het gebruik van onze Microsoft FastTrack-service. FastTrack biedt best practices, hulpprogramma's en resources om uw migratie zo Microsoft 365 mogelijk te maken. Het beste van alles is dat u door een ondersteuningstechnicus wordt lopen, van planning en ontwerp tot het migreren van uw laatste postvak. Zie Microsoft FastTrack voor meer informatie [over FastTrack.](https://fasttrack.microsoft.com/)

Als u problemen hebt tijdens de migratie naar Microsoft 365 en u geen FastTrack gebruikt of als u migreert naar een nieuwere versie van Exchange Server, zijn hier enkele bronnen die u kunt gebruiken:

- [Technische community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Klantondersteuning](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>Verwante artikelen

[Resources om u te helpen bij het upgraden van Office 2010-servers en -clients](upgrade-from-office-2010-servers-and-products.md)
