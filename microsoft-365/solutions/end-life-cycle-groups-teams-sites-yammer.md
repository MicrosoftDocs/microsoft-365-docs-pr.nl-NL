---
title: Opties voor het einde van de levenscyclus voor groepen, teams en Yammer
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Opties voor het einde van de levenscyclus voor groepen, teams en Yammer.
ms.openlocfilehash: 468f41df747b6cf12d3f6619d79cb97248eba1d1
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346424"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Opties voor het einde van de levenscyclus voor groepen, teams en Yammer

Microsoft 365 Groepen en Microsoft Teams werken met meerdere verbonden services. Wanneer een groep of team wordt verwijderd, worden de meeste gegevens in de verbonden services ook verwijderd. In dit artikel worden opties beschreven voor het bewaren van gegevens door deze vóór verwijdering uit de groep of het team te verplaatsen.

Een veelgebruikte gewoonte voor groepen of teams die niet meer nodig zijn, is om de bestanden uit het team te verplaatsen en ze te archiveren op een andere locatie, zoals een SharePoint documentbibliotheek. Deze praktijk is gebaseerd op een oudere manier van werken waarbij gegevens worden opgeslagen in bestanden en mappen en communicatie via e-mail wordt uitgevoerd.

In de volgende tabel worden de services beschreven die zijn gekoppeld aan groepen en teams en de belangrijkste typen inhoud die in elk van deze groepen zijn gevonden:

|Service|Inhoudstypen|
|:------|:---------------|
|Teams|Kanaalgesprekken, bestanden in kanalen|
|Forms|Enquêtestructuur en -resultaten|
|OneNote|Notitieblok|
|Outlook|E-mail en agenda|
|Planner|Project status en taakgegevens|
|Power Automate|Werkstromen|
|Power BI|Gegevens, rapporten en dashboards|
|Project op het web|Project plannen|
|Roadmap|Routekaarten|
|SharePoint|Bestanden, lijsten, Teams wikigegevens van kanalen|
|Stream|Video's|
|Yammer|Gesprekken|

Bij het verwijderen van een groep of team worden de meeste bijbehorende resources ook verwijderd. Uitzonderingen zijn:

- Video's in Stream blijven en zijn eigendom van de persoon die ze heeft geüpload/opgenomen
- Stromen in Power Automate blijven en zijn eigendom van de persoon die ze heeft gemaakt.
- Project en routekaartgegevens in Project web blijven in de CDS en kunnen afzonderlijk worden hersteld.

Groepen en teams blijven 30 dagen in een soft-delete-status staan en kunnen op elk moment worden hersteld. Na 30 dagen worden ze echter verwijderd uit de Microsoft 365 omgeving. Inhoud die wordt beschermd door een bewaarbeleid, blijft beschikbaar via eDiscovery-zoekopdrachten.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Overwegingen voor het einde van de levenscyclus voor services die zijn verbonden met een groep

Er zijn drie belangrijke gebieden waar team- en groepseigenaren en IT-beheerders rekening mee moeten houden bij het verwijderen van een groep of team.

**Content**

Moet de inhoud worden bewaard nadat het team er niet meer is? Is het voldoende om te vertrouwen op de bewaarmogelijkheden van Microsoft 365 of is een deel van de inhoud in apps en services die geen bewaarmogelijkheden bieden? Moet de inhoud worden bewaard voor recordbeheer, archivering of toekomstig gebruik en verwijzingsdoeleinden?

Om mogelijk gegevensverlies te voorkomen, moeten deze vragen worden gesteld voordat een team wordt gearchiveerd of verwijderd.

**Services**

Moet inhoud in de huidige werkvorm blijven? Moet het rapport Power BI bijvoorbeeld toegankelijk blijven? Moeten de formulierresultaten beschikbaar zijn in de visuele overzichtsweergave? Zijn de lijsten in SharePoint gekoppeld aan of ergens ingesloten?

Deze vragen moeten worden gesteld voordat de onderliggende groep wordt verwijderd, omdat het exporteren van de inhoud mogelijk niet voldoende is.

**Gasten**

Wanneer gasten worden uitgenodigd voor een team, wordt er een gastaccount gemaakt in de Azure Active Directory van de gastorganisatie voordat ze aan het team worden toegevoegd. Wanneer een team wordt verwijderd, worden gasten niet verwijderd uit Azure Active Directory. Hoewel gasten geen toegang hebben tot groepen, sites, teams of inhoud die niet met hen is gedeeld, kunnen ze nog steeds functies binnen Microsoft Teams gebruiken, zoals het starten van chats, spraak- en videogesprekken en het gebruik van apps.

Een team- of groepseigenaar kan iemand van buiten de organisatie uitnodigen om gast te worden in Azure Active Directory door deze toe te voegen aan een team. Een teameigenaar kan de gast echter niet verwijderen uit Azure Active Directory. Het verwijderen van accounts kan alleen worden uitgevoerd door een globale beheerder of gebruikerbeheerder.

Het is belangrijk om gastbeoordelingen uit te voeren en te begrijpen of gasten moeten worden verwijderd uit Azure Active Directory bij teamverhaling. Er kan een geldig geval zijn voor gasten om in de adreslijst te blijven, zoals lid zijn van andere teams of het gebruik van andere Microsoft 365 of Azure-services.

## <a name="teams"></a>Teams

Teams-specifieke inhoud is voornamelijk in de vorm van gesprekken.

Gesprekken in kanalen kunnen niet worden gekopieerd of verplaatst met behulp van de Microsoft Teams functionaliteit. Ze kunnen echter worden geëxporteerd met de Graph API.

Als een bewaarbeleid wordt toegepast op Teams, worden de gesprekken behouden en beschikbaar via eDiscovery-zoekopdrachten. Met behulp van geavanceerde eDiscovery kunt u [een Teams een chatgesprek reconstrueren.](/microsoft-365/compliance/conversation-review-sets)


### <a name="archiving-a-team"></a>Een team archiveren

Het voordeel van [het archiveren van een team](/microsoftteams/archive-or-delete-a-team) is dat het volledige toegang biedt tot het team zoals het was. Gebruikers kunnen nog steeds door kanaalgesprekken bladeren en bestanden openen, zelfs als ze niet actief zijn. Bovendien kunnen teams niet worden gearchiveerd als het nodig is om er aan te blijven werken (bijvoorbeeld als een project wordt uitgebreid).

Wanneer een team wordt gearchiveerd door een eigenaar, is het ingesteld op alleen-lezen voor leden, zowel voor inhoud binnen het team als geselecteerd, de bijbehorende SharePoint site. Het doel van deze actie is ervoor te zorgen dat gesprekken in kanalen behouden blijven in hun bestaande status, samen met SharePoint op basis van inhoud, zoals bestanden en wiki's.

Op de SharePoint zijn er geen zichtbare wijzigingen. Er kunnen echter geen wijzigingen worden aangebracht in bestanden of lijsten omdat SharePoint machtigingen voor de Microsoft 365 groep zijn ingesteld op **Sitebezoekers.** Dit omvat het OneNote notitieblok voor het team, dat is opgeslagen in de bibliotheek Siteactiva op de SharePoint site.

Wanneer een team wordt gearchiveerd, is de onderliggende Microsoft 365 nog steeds onderhevig aan het verloopbeleid (indien ingesteld) en moet de eigenaar het team blijven vernieuwen.

Hoewel de kanaalgesprekken en de SharePoint van het team zijn ingesteld op alleen-lezen, wordt hetzelfde niet toegepast op andere gekoppelde services:

- Planner buckets en taken kunnen nog steeds worden gemaakt, gewijzigd en verwijderd.
- Formulieren kunnen nog steeds inzendingen ontvangen.
- Het Outlook postvak kan nog steeds e-mailberichten ontvangen.
- Power BI dashboards, rapporten en gegevens kunnen nog steeds worden gewijzigd.
- Projecten en routekaarten kunnen nog steeds worden bewerkt in Project web.
- Video's kunnen nog steeds worden geüpload, gewijzigd en verwijderd in Stream.
- Stromen in Power Automate kunnen nog steeds worden gemaakt, gewijzigd, verwijderd en blijven worden uitgevoerd. (Ze mislukken echter, indien nodig om een bericht te posten op een kanaal van het gearchiveerde team.)

## <a name="forms"></a>Forms

Hoewel een formulier van een afzonderlijk account naar een groep kan worden verplaatst, kan het niet van de ene groep naar de andere worden verplaatst of gekopieerd. Er zijn drie opties beschikbaar voor een formulier wanneer een team wordt verwijderd.

**Het formulier dupliceren**

Formulieren kunnen worden [gedeeld als sjablonen,](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)zodat andere gebruikers deze kunnen kopiëren naar hun eigen account of een groep. Hierdoor blijven de gegevens uit resultaatinzendingen niet behouden. alleen formulierstructuur zoals vragen en instellingen.

**Resultaten exporteren naar een spreadsheet**

Als de gegevens van de formulierreacties moeten worden bewaard, kan dit worden bereikt door de resultaten te exporteren naar een [Excel spreadsheet.](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af) Hiermee worden alleen de vragen en hun antwoorden geëxporteerd als gegevens. Dit omvat geen grafieken die door Formulieren zijn gemaakt.

**Het formulier verwijderen**

Hoewel het verwijderen van de groep ook resulteert in het [](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) verwijderen van gekoppelde formulieren, kunnen groepsleden deze rechtstreeks verwijderen zonder eigenaar van de groep te zijn. Dit is echter een handmatige stap die geen extra voordeel biedt.

## <a name="onenote"></a>OneNote

Het OneNote notitieblok dat is opgenomen in een groep, wordt opgeslagen in de bibliotheek Siteactiva binnen de bijbehorende SharePoint site. Hoewel notitieblokbestanden soms over meerdere afzonderlijke bestanden kunnen worden verspreid, kunnen ze niet afzonderlijk worden gekopieerd en geopend. In plaats daarvan moet de inhoud van OneNote notitieblok worden verplaatst of geëxporteerd met OneNote 2016.

**Pagina's en secties naar een ander notitieblok verplaatsen**

[Door pagina's of secties](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) afzonderlijk naar een ander notitieblok te verplaatsen, kunnen eigenaren hun gegevens ops schonen en alleen de gegevens gebruiken die moeten worden bewaard.

**Het hele notitieblok exporteren als een pakket**

Als het hele notitieblok moet worden behouden met de [](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) bestaande structuur, kan het worden geëxporteerd als een OneNote pakketbestand en vervolgens naar een nieuwe locatie worden geïmporteerd. In plaats daarvan kan dit worden gebruikt als een methode om de inhoud in één bestand te behouden in plaats van de bestaande structuur met meerdere bestanden.

**Afdrukken naar PDF**

In scenario's waarin een deel van de inhoud van het notitieblok alleen moet worden bewaard voor verwijzing of als records, kunnen afzonderlijke pagina's worden afgedrukt naar PDF en elders [worden opgeslagen.](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)

## <a name="mailbox-and-calendar"></a>Postvak en agenda

Het is niet ongebruikelijk dat het aan de groep gekoppelde postvak wordt gebruikt, ook al zijn er veel gesprekken gevoerd binnen teamkanalen. Het postvak bevat alleen e-mailberichten die rechtstreeks naar het postvak zijn verzonden en die geen e-mailberichten bevatten die rechtstreeks naar kanalen zijn verzonden.

In sommige gevallen zijn de e-mailberichten die zijn opgeslagen in het postvak mogelijk meldingen van vergaderingen, Planner-taakupdates en andere app- of systeem gegenereerde berichten. het is belangrijk dat de inhoud van het postvak wordt gecontroleerd om te bepalen of de inhoud moet worden bewaard of verwijderd.

Als een bewaarbeleid wordt toegepast in Exchange, blijven de e-mailberichten en agenda-items behouden en beschikbaar via eDiscovery-zoekopdrachten.

**E-mail en agenda exporteren**

Team- of groepsleden kunnen de inhoud van het postvak en de agenda exporteren naar een Outlook [Bestand gegevens/persoonlijke Storage (PST).](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91) Dit bestand kan vervolgens ergens anders worden opgeslagen of de inhoud kan worden geïmporteerd in een ander postvak. De eerste wordt niet aanbevolen omdat de inhoud van het PST-bestand niet kan worden doorzocht zonder het te openen in Outlook en het bestand zelf na een tijd beschadigd kan raken.

**It-uitgevoerde inhoudsmigratie**

Beheerders kunnen hulpprogramma's van derden gebruiken om e-mail en agenda-inhoud tussen postvakken te migreren zonder tussenkomst van de gebruiker. Een mogelijke opslaglocatie kan een gedeeld postvak zijn dat alleen is gemaakt om te fungeren als een 'archief' van de inhoud van het groepspostvak.

## <a name="planner"></a>Planner

Elke groep of elk team kan meerdere abonnementen hebben. Het is belangrijk tijdens het off-boarding proces ervoor te zorgen dat bewaarvereisten voor elk plan worden aangepakt. Net als de andere services zijn er verschillende benaderingen voor inhoud buiten het bord in Planner.

**Het plan exporteren naar een spreadsheet**

Als het alleen nodig is om een kopie van het plan bij te houden voor het bewaren van records, is de eenvoudigste manier om het plan te exporteren naar een [Excel spreadsheet.](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a) Dit is een eenwegactie: er is geen optie om plannen uit een spreadsheet te importeren.

> [!IMPORTANT]
> Als u een plan exporteert Excel de meeste informatie in het plan, maar geen opmerkingen, koppelingen of bestanden bevatten.

**Taken kopiëren en verplaatsen naar een ander plan**

Hoewel het kopiëren of verplaatsen van taken naar een ander plan een oplossing lijkt, kunnen afzonderlijke taken alleen worden gekopieerd of verplaatst tussen [plannen](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) binnen dezelfde groep. Hiermee wordt geen back-up gemaakt van de gegevens als de groep die aan het plan is gekoppeld, wordt verwijderd.

**Het hele plan kopiëren**

Het is ook mogelijk om het [hele plan te kopiëren.](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4) Kopiëren kan niet worden uitgevoerd naar een bestaande groep. Als u het plan kopieert, wordt er een nieuwe groep gemaakt. Bovendien bevat het kopiëren van het hele plan geen opmerkingen, opdrachten, koppelingen, bijlagen of datums.

## <a name="power-automate"></a>Power Automate

Stromen die in Power Automate zijn gemaakt en die zijn gekoppeld aan een groep of team, behoren niet tot de groep. Ze zijn eigendom van de maker en worden alleen gedeeld met andere gebruikers en groepen. Als zodanig worden ze niet beïnvloed als een groep of team wordt verwijderd.

**Eigenaar van de stroom wijzigen**

Als de stroom moet blijven werken, kunnen eigenaren andere gebruikers of Microsoft 365 als eigenaren toevoegen.

**De stroom exporteren**

Als de stroom niet hoeft te blijven werken, maar deze moet worden [](https://flow.microsoft.com/blog/import-export-bap-packages/) bewaard voor toekomstig gebruik, kan de stroom als bestand worden geëxporteerd en later opnieuw worden geïmporteerd.

## <a name="power-bi"></a>Power BI

Power BI gegevens en werkruimten kunnen onafhankelijk van groepen en teams werken en bieden net als andere werkbelastingen verschillende manieren om niet aan boord te gaan.

**Rapporten kopiëren naar een andere werkruimte**

Als u het rapport nodig hebt nadat de groep of het team is verwijderd, kan het vanuit de bestaande werkruimte worden gekopieerd naar een andere [werkruimte binnen Power BI.](/power-bi/connect-data/service-datasets-copy-reports)

**Gegevens exporteren vanuit een dashboard of rapport**

Als het rapport niet langer actief hoeft te zijn, maar de gegevens moeten worden bewaard, kan het worden geëxporteerd naar [Excel.](/power-bi/visuals/power-bi-visualization-export-data)

## <a name="project"></a>Project

Projecten en routekaarten die in Project voor het web zijn gemaakt, zijn gekoppeld aan Microsoft 365 groepen en hebben benaderingen voor off-boarding, vergelijkbaar met Power BI.

**Het project toewijzen aan een andere groep**

Als het project buiten de levensduur van de groep of het team in de functionele staat moet worden bewaard, kan het worden toegewezen aan een [andere Microsoft 365 groep.](/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) U kunt dit doen met het Dynamics 365-beheercentrum.

**Gegevens exporteren uit het project of de routekaart**

Met het Dynamics 365-beheercentrum kunt u gebruikersgegevens uit het [project exporteren](/project-for-the-web/export-user-data-from-project-for-the-web) naar een spreadsheet. De gegevens kunnen ook worden geëxporteerd naar Project bestand (. MPP) en XML-bestandsindelingen met PowerShell.

## <a name="sharepoint"></a>SharePoint

Alle bestanden in teamkanalen worden opgeslagen op de SharePoint site van de gekoppelde groep. In sommige gevallen kan er andere inhoud dan documenten SharePoint, zoals lijsten of pagina's.

Bestanden worden over het algemeen opgeslagen op drie primaire locaties binnen een SharePoint site:

- Pagina's - Bibliotheek sitepagina's
- Afbeeldingen die in pagina's worden gebruikt: bibliotheek siteactiva
- Bestanden in kanalen : documentenbibliotheek
- Wikipagina's : Teams wikigegevensbibliotheek

Als de site een of meer subsites heeft, moet het off-boarding-proces voor elke subsite worden herhaald. Als het team privékanalen bevat, is er een afzonderlijke SharePoint voor elk kanaal.

Het is belangrijk dat u bij het verwijderen van bestanden uit een groep of team bedenkt dat ze kunnen worden gedeeld met gebruikers die geen lid zijn van de groep of het team. Mogelijk wilt u de aanstaande wijziging aan hen laten weten.

**Bestanden downloaden**

Bestanden die zijn opgeslagen in SharePoint in een van de hierboven genoemde bibliotheken, kunnen [worden gedownload naar een lokale computer.](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)

**Bestanden verplaatsen**

Daarnaast kunnen bestanden worden verplaatst naar een andere locatie [SharePoint, zoals een bibliotheek op een andere site.](https://support.office.com/article/00e2f483-4df3-46be-a861-1f5f0c1a87bc)

**Exportlijst**

Gegevens die zijn opgeslagen in SharePoint lijsten kunnen worden geëxporteerd naar een Excel [spreadsheet](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)en opnieuw worden geïmporteerd naar een lijst op een andere site.

U kunt ook een hulpprogramma van derden gebruiken om de lijst tussen sites te migreren om functie, lijstweergaven, opmaak en andere kenmerken te behouden.

**Wikibestanden exporteren**

Wiki-inhoud binnen teamkanalen wordt opgeslagen in een HTML-bestand dat is opgemaakt in een speciale bibliotheek van de bijbehorende SharePoint site. Ze kunnen niet direct worden geëxporteerd en geïmporteerd naar een andere kanaalwiki, maar kunnen worden geconverteerd naar een HTML-bestand en worden geopend als een webpagina.

## <a name="microsoft-stream"></a>Microsoft Stream

Net Power Automate video's in Stream die zijn gekoppeld aan een groep of team, zijn niet echt eigendom van de groep en worden ze niet verwijderd wanneer de groep wordt verwijderd. Video's in Stream zijn eigendom van de persoon die de video heeft geüpload of gemaakt, zelfs als ze gebruikers of groepen als eigenaren toevoegen. Vergaderingen die zijn opgenomen in Teams kanaal, zijn eigendom van de persoon die de opname heeft gestart.

**Andere eigenaren toevoegen**

Omdat de video wordt bewaard in Stream wanneer de groep wordt verwijderd, kan de oorspronkelijke eigenaar de video delen met andere gebruikers en [groepen,](/stream/portal-edit-video)zelfs als eigenaars.

**De video downloaden**

In scenario's waarin de video niet hoeft te worden bewaard in Stream of moet worden opgeslagen op een alternatieve locatie, zoals een recordbeheersysteem, kan een eigenaar deze lokaal [downloaden.](/stream/portal-download-video)

## <a name="yammer"></a>Yammer

In tegenstelling tot gesprekken in Microsoft Teams, Yammer gebruikers en beheerders opties om gesprekken te verplaatsen of te exporteren.

**Gesprekken verplaatsen naar een andere groep of community**

Gesprekken kunnen worden verplaatst naar een andere Yammer door elke gebruiker, niet alleen door eigenaren of beheerders. Dit is mogelijk in zowel de [klassieke Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872) als de [nieuwe Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) interfaces.

**Netwerkgegevens exporteren**

Yammer netwerkbeheerders exporteren [netwerkgegevens](/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Als u dit doet, worden echter alle gesprekken voor het hele netwerk geëxporteerd. De resulterende export bevat de groeps-id. Het is mogelijk om gesprekken te filteren op basis van deze id.
