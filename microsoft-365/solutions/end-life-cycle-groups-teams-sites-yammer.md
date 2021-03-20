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
ms.openlocfilehash: 405d87c645118cf0ef318d4d68802d17da8c5673
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916128"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Opties voor het einde van de levenscyclus voor groepen, teams en Yammer

Microsoft 365 Groepen en Microsoft Teams werken met diverse verbonden services. Wanneer een groep of team wordt verwijderd, worden de meeste gegevens in de verbonden services ook verwijderd. In dit artikel worden opties beschreven voor het behouden van gegevens door deze vóór verwijdering uit de groep of het team te verplaatsen.

Een veelgebruikte gewoonte voor groepen of teams die niet meer nodig zijn, is om de bestanden uit het team te verplaatsen en op te slaan op een andere locatie, zoals een SharePoint-documentbibliotheek die optreedt als opslagplaats of archief. Deze praktijk is gebaseerd op een oude manier van werken waarbij gegevens worden opgeslagen in bestanden en mappen en communicatie via e-mail wordt uitgevoerd.

In de volgende tabel worden de services beschreven die zijn gekoppeld aan groepen en teams en de belangrijkste typen inhoud die in elk van deze groepen zijn gevonden:

|Service|Inhoudstypen|
|:------|:---------------|
|Teams|Kanaalgesprekken, bestanden in kanalen|
|Forms|Enquêtestructuur en -resultaten|
|OneNote|Notitieblok|
|Outlook|E-mail en agenda|
|Planner|Projectstatus en taakgegevens|
|Power Automate|Werkstromen|
|Power BI|Gegevens, rapporten en dashboards|
|Project op het web|Projectplannen|
|Roadmap|Routekaarten|
|SharePoint|Bestanden, lijsten, Wikigegevens van Teams-kanaal|
|Stream|Video's|
|Yammer|Gesprekken|

Bij het verwijderen van een groep of team worden de meeste bijbehorende resources ook verwijderd. Enkele uitzonderingen hierop zijn video's in Stream: deze blijven en zijn nog steeds eigendom van de persoon die ze heeft geüpload/opgenomen, net als stromen in Power Automate. Project- en routekaartgegevens in het web van Project blijven in de CDS staan en kunnen afzonderlijk worden hersteld.

Groepen en teams blijven 30 dagen in een soft-delete-status staan en kunnen op elk moment worden hersteld. Na 30 dagen worden ze echter volledig verwijderd uit de Microsoft 365-omgeving en alle bijbehorende bronnen, zoals services en inhoud. Inhoud die wordt beschermd door een bewaarbeleid, blijft beschikbaar via eDiscovery-zoekopdrachten.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Overwegingen voor het einde van de levenscyclus voor services die zijn verbonden met een groep

Er zijn drie belangrijke gebieden waar team- en groepseigenaren en IT-beheerders rekening mee moeten houden bij het verwijderen van een groep of team.

**Content**

Moet de inhoud behouden blijven nadat het team niet meer werkt of bestaat? Is het voldoende om te vertrouwen op de bewaarmogelijkheden van Microsoft 365 of is een deel van de inhoud in apps en services die geen bewaarmogelijkheden bieden? Moet de inhoud worden bewaard voor recordbeheerdoeleinden, voor archiveringsdoeleinden of voor toekomstig gebruik en verwijzingsdoeleinden?

Deze vragen moeten worden gesteld voordat een team wordt gearchiveerd of verwijderd, om mogelijk gegevensverlies te voorkomen.

**Services**

Moeten ze boven op de inhoud van verschillende apps en services in hun huidige werkformulier blijven? Moet het Power BI-rapport bijvoorbeeld toegankelijk blijven, moeten de formulierresultaten beschikbaar zijn in de visuele overzichtsweergave, zijn de lijsten in SharePoint gekoppeld aan of ergens ingesloten?

Net als bij de inhoudsoverwegingen moeten deze vragen worden gesteld voordat de onderliggende groep wordt verwijderd, omdat het exporteren van de inhoud mogelijk niet voldoende is.

**Gasten**

Wanneer gasten worden uitgenodigd voor een team, wordt in de werkstroom hun identiteit gemaakt in de Azure Active Directory van de hostorganisatie voordat ze aan het team worden toegevoegd. Wanneer een team wordt verwijderd, worden gasten niet verwijderd uit Azure Active Directory en bestaan ze nog steeds in de Microsoft Teams-omgeving. Hoewel gasten geen toegang hebben tot groepen, sites, teams of inhoud die niet met hen is gedeeld, kunnen ze mogelijk nog steeds gebruikmaken van functies in Microsoft Teams, zoals het starten van chats, spraak- en videogesprekken en het gebruik van apps.

Een team- of groepseigenaar kan een externe gebruiker uitnodigen om gast te worden in Azure Active Directory, deze toe te voegen aan het team en deze uit het team te verwijderen. Een teameigenaar kan de gast echter niet verwijderen uit Azure Active Directory. Dit kan alleen worden uitgevoerd door een globale beheerder of gebruikerbeheerder.

Daarom is het belangrijk om gastbeoordelingen uit te voeren en om te begrijpen of gasten moeten worden verwijderd uit Azure Active Directory bij het verwijderen van het team. Er kan een geldig geval zijn dat gasten in de adreslijst blijven, zoals lid zijn van een of meer andere teams of andere Microsoft 365- of Azure-services gebruiken.

## <a name="teams"></a>Teams

Teams-specifieke inhoud is voornamelijk in de vorm van gesprekken.

Gesprekken in kanalen kunnen niet worden gekopieerd of verplaatst met de standaardfunctionaliteit van Microsoft Teams. Ze kunnen echter worden geëxporteerd met behulp van de Graph API.

Als een bewaarbeleid wordt toegepast op Teams, blijven de gesprekken behouden en beschikbaar via eDiscovery-zoekopdrachten. (Items die in eDiscovery-zoekopdrachten worden gevonden, kunnen worden geëxporteerd, maar er is geen context of structuur van de oorspronkelijke bron over, het zijn gewoon afzonderlijke berichten.)

### <a name="archiving-a-team"></a>Een team archiveren

Het voordeel van [het archiveren](/microsoftteams/archive-or-delete-a-team) van een team is dat het volledige toegang biedt tot het team zoals het was, zodat gebruikers nog steeds door kanaalgesprekken kunnen bladeren en bestanden kunnen openen, zelfs als ze niet actief zijn. Bovendien kunnen teams niet worden gearchiveerd als het nodig is om er aan te blijven werken (bijvoorbeeld in het geval van een projectextensie).

Wanneer een team wordt gearchiveerd door een eigenaar, is het ingesteld op alleen-lezen voor leden, zowel voor inhoud binnen het team als geselecteerd, de bijbehorende SharePoint-site. Het doel van deze actie is ervoor te zorgen dat gesprekken in kanalen in hun bestaande status worden bewaard, samen met op SharePoint gebaseerde inhoud, zoals bestanden en wiki's.

Op de SharePoint-site zijn er geen zichtbare wijzigingen, maar er kunnen geen wijzigingen worden aangebracht in bestanden of lijsten, aangezien de sharePoint-machtigingengroep voor de Microsoft 365-groep is ingesteld op sitebezoekersniveau. Dit omvat het OneNote-notitieblok voor het team, omdat dit is opgeslagen in de bibliotheek Siteactiva op de SharePoint-site.

Wanneer een team wordt gearchiveerd, is de onderliggende Microsoft 365-groep nog steeds onderworpen aan het verloopbeleid (indien ingesteld) en moet de eigenaar het team blijven verlengen.

Hoewel de kanaalgesprekken van het team en de inhoud van de SharePoint-site zijn ingesteld op alleen-lezen, wordt hetzelfde niet toegepast op andere gekoppelde services:

- Planner buckets en taken kunnen nog steeds worden gemaakt, gewijzigd en verwijderd
- Formulieren kunnen nog steeds inzendingen ontvangen
- Het Outlook-postvak kan nog steeds e-mailberichten ontvangen
- Power BI-dashboards, rapporten en gegevens kunnen nog steeds worden gewijzigd
- Projecten en routekaarten kunnen nog steeds worden bewerkt in de webwinkel van Project
- Video's kunnen nog steeds worden geüpload, gewijzigd en verwijderd in Stream
- Stromen in Power Automate kunnen nog steeds worden gemaakt, gewijzigd, verwijderd en blijven worden uitgevoerd (ze mislukken echter, indien nodig om een bericht te posten op een kanaal van het gearchiveerde team)

## <a name="forms"></a>Forms

Hoewel een formulier van een afzonderlijk account naar een groep kan worden verplaatst, kan het niet van de ene groep naar de andere worden verplaatst of gekopieerd. Er zijn drie opties beschikbaar voor een formulier wanneer een team wordt verwijderd.

**Het formulier dupliceren**

Formulieren kunnen worden [gedeeld als sjablonen,](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)zodat andere gebruikers deze kunnen kopiëren naar hun eigen account of een groep. Hierdoor blijven de gegevens uit resultaatinzendingen niet behouden. alleen formulierstructuur zoals vragen en instellingen.

**Resultaten exporteren naar een spreadsheet**

Als de gegevens van de formulierreacties moeten worden bewaard, kan dit worden bereikt door de resultaten te exporteren [naar een Excel-spreadsheet.](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af) Hiermee worden alleen de vragen en hun antwoorden als gegevens geëxporteerd, maar worden geen grafieken gebruikt die door Formulieren zijn gemaakt.


**Het formulier verwijderen**

Hoewel het verwijderen van de groep ook resulteert in het [](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) verwijderen van gekoppelde formulieren, kunnen groepsleden deze rechtstreeks verwijderen zonder eigenaar van de groep te zijn, maar dit is een handmatige stap die geen extra voordeel biedt.

## <a name="onenote"></a>OneNote

Het OneNote-notitieblok dat is opgenomen in een groep, wordt opgeslagen in de bibliotheek Siteactiva op de bijbehorende SharePoint-site. Hoewel notitieblokbestanden soms over meerdere afzonderlijke bestanden kunnen worden verspreid, kunnen ze niet alleen afzonderlijk worden gekopieerd en geopend. In plaats daarvan moet de inhoud van het OneNote-notitieblok worden verplaatst of geëxporteerd met OneNote 2016.

**Pagina's en secties naar een ander notitieblok verplaatsen**

[Door pagina's of secties](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) afzonderlijk naar een ander notitieblok te verplaatsen, kunnen eigenaren hun gegevens ops schonen en alleen de gegevens gebruiken die moeten worden bewaard.

**Het hele notitieblok exporteren als een pakket**

Als het hele notitieblok moet worden behouden met de bestaande structuur, kan het worden geëxporteerd als [een OneNote-pakketbestand](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) en vervolgens worden geïmporteerd naar een nieuwe locatie. U kunt dit ook gebruiken als een methode om de inhoud in één bestand te behouden in plaats van de bestaande structuur met meerdere bestanden.

**Afdrukken naar PDF**

In scenario's waarin een deel van de inhoud van het notitieblok alleen moet worden bewaard voor verwijzing of als records, kunnen afzonderlijke pagina's worden afgedrukt naar PDF en elders [worden opgeslagen.](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)

## <a name="mailbox-and-calendar"></a>Postvak en agenda

Het is niet ongebruikelijk dat het aan de groep gekoppelde postvak wordt gebruikt, ook al zijn er veel gesprekken gevoerd binnen teamkanalen. Het postvak slaat alleen e-mailberichten op die rechtstreeks naar het postvak zijn verzonden en bevatten geen e-mailberichten die rechtstreeks naar kanalen zijn verzonden.

In sommige gevallen zijn de e-mailberichten die in het postvak zijn opgeslagen, alleen meldingen van vergaderingen, Planner-taakupdates en andere app- of systeem gegenereerde berichten. Het is belangrijk dat de inhoud van het postvak wordt gecontroleerd om te bepalen of de inhoud moet worden bewaard of verwijderd.

Als een bewaarbeleid wordt toegepast op Exchange, blijven de e-mailberichten en agenda-items behouden en beschikbaar via eDiscovery-zoekopdrachten.

**E-mail en agenda exporteren**

Team- of groepsleden kunnen de inhoud van het postvak en de [agenda exporteren naar een PST-bestand (Outlook Data / Personal Storage).](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91) Dit bestand kan vervolgens ergens anders worden opgeslagen of de inhoud kan worden geïmporteerd in een ander postvak. Het eerste wordt niet aanbevolen, omdat de inhoud van het PST-bestand niet kan worden doorzocht zonder het te openen in Outlook en het bestand zelf na een tijd beschadigd kan raken.

**It-uitgevoerde inhoudsmigratie**

Beheerders kunnen hulpprogramma's van derden gebruiken om e-mail en agenda-inhoud tussen postvakken te migreren zonder tussenkomst van de gebruiker. Een mogelijke opslaglocatie kan een gedeeld postvak zijn dat alleen is gemaakt om te fungeren als een 'archief' van de inhoud van het groepspostvak.

## <a name="planner"></a>Planner

Elke groep of elk team kan meerdere abonnementen hebben. Het is belangrijk tijdens het offboardingproces ervoor te zorgen dat elk plan wordt gericht op de vraag of de inhoud ervan behouden blijft. Net als de andere producten zijn er verschillende methoden voor offboard-inhoud in Planner.

**Het plan exporteren naar een spreadsheet**

Als het alleen nodig is om een kopie van het plan te bewaren voor het bewaren van records, is de eenvoudigste methode om het plan te exporteren naar [een Excel-spreadsheet.](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a) Dit is een een-wegactie, omdat er geen optie is om plannen uit een spreadsheet te importeren.

> [!IMPORTANT]
> Als u een plan exporteert naar Excel, wordt de meeste informatie in het plan opgeslagen, maar worden opmerkingen, koppelingen of bestanden niet vermeld.

**Taken kopiëren en verplaatsen naar een ander plan**

Hoewel dit een oplossing lijkt, kunnen afzonderlijke taken alleen worden gekopieerd of verplaatst tussen plannen [binnen](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) dezelfde groep, waardoor het voordeel wordt uitgesloten als de groep die aan het plan is gekoppeld, wordt verwijderd.

**Het hele plan kopiëren**

Het is ook mogelijk om [het hele plan te kopiëren.](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4) Dit kan echter niet voor een bestaande groep of zelfs binnen dezelfde groep zijn. Als u het plan kopieert, wordt er een nieuwe groep gemaakt. Bovendien bevat het kopiëren van het hele plan geen opmerkingen, opdrachten, koppelingen, bijlagen of datums.

## <a name="power-automate"></a>Power Automate

Stromen die zijn gemaakt in Power Automate en die zijn gekoppeld aan een groep of team, behoren niet tot de groep en zijn in plaats daarvan eigendom van de maker en worden alleen gedeeld met andere gebruikers en groepen. Als zodanig worden ze niet beïnvloed als een groep of team wordt verwijderd.

**Eigenaar van de stroom wijzigen**

Als de werkstroom moet blijven werken, kunnen eigenaren gewoon andere gebruikers of Microsoft 365-groepen toevoegen als eigenaren.

**De stroom exporteren**

Als de werkstroom niet hoeft te blijven werken, maar deze moet [](https://flow.microsoft.com/blog/import-export-bap-packages/) worden bewaard voor mogelijk toekomstig gebruik, kan de werkstroom als bestand worden geëxporteerd en later opnieuw worden geïmporteerd.

## <a name="power-bi"></a>Power BI

Power BI-gegevens en werkruimten kunnen onafhankelijk van groepen en teams werken en bieden net als andere werkbelastingen verschillende manieren om buiten het bord te worden gezet.

**Rapporten kopiëren naar een andere werkruimte**

Als het rapport buiten de levensduur van de groep of het team in de functionele staat moet blijven, kan het vanuit de bestaande werkruimte worden gekopieerd naar een andere werkruimte [in Power BI.](/power-bi/connect-data/service-datasets-copy-reports)

**Gegevens exporteren vanuit een dashboard of rapport**

Als het rapport niet langer actief hoeft te zijn, maar de gegevens moeten worden bewaard, kan het ook worden geëxporteerd [naar Excel.](/power-bi/visuals/power-bi-visualization-export-data)

## <a name="project"></a>Project

Projecten en routekaarten die zijn gemaakt in project op het web, kunnen worden gekoppeld aan Microsoft 365-groepen en bieden benaderingen voor offboarding, vergelijkbaar met Power BI.

**Het project toewijzen aan een andere groep**

Als het project buiten de levensduur van de groep of het team in de functionele staat moet blijven, kan het worden toegewezen aan een andere [Microsoft 365-groep](/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) met behulp van het Dynamics 365-beheercentrum.

**Gegevens exporteren uit het project of de routekaart**

Met behulp van het Dynamics 365-beheercentrum is het mogelijk om gebruikersgegevens uit het [project](/project-for-the-web/export-user-data-from-project-for-the-web) te exporteren naar een spreadsheet of als u een PowerShell-script gebruikt, kunnen de gegevens worden geëxporteerd naar Project-bestand (. MPP) en XML-bestandsindelingen.

## <a name="sharepoint"></a>SharePoint
Alle bestanden in teamkanalen worden opgeslagen in de documentbibliotheek op de SharePoint-site van de gekoppelde groep. In sommige gevallen kan er andere inhoud dan documenten aanwezig zijn in SharePoint, zoals lijsten of pagina's.
Bestanden worden over het algemeen opgeslagen op drie primaire locaties op een SharePoint-site:

- Pagina's - Bibliotheek sitepagina's
- Afbeeldingen die in pagina's worden gebruikt: bibliotheek siteactiva
- Bestanden in kanalen : documentenbibliotheek
- Wikipagina's : teams wikigegevensbibliotheek

Als de site een of meer subsites eronder heeft geneste, moet het offboardingproces voor elke subsite worden herhaald. Als het team privékanalen bevat, is er een aparte SharePoint-site voor elk kanaal.

Het is belangrijk dat u bij het verwijderen van bestanden uit een groep of team bedenkt dat ze kunnen worden gedeeld met gebruikers die geen lid zijn van de groep of het team (intern of extern binnen de organisatie), en als zodanig kan het de moeite waard zijn om de aanstaande wijziging aan hen door te geven.

**Bestanden downloaden**

In het geval van bestanden die zijn opgeslagen in SharePoint in een van de hierboven genoemde bibliotheken, kunnen deze worden [gedownload naar een lokale computer.](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)

**Bestanden verplaatsen**

Daarnaast kunnen bestanden worden verplaatst naar een andere locatie in SharePoint, zoals een bibliotheek op een andere site.
Verwijzing: https://support.office.com/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc

**Exportlijst** Gegevens die zijn opgeslagen in SharePoint-lijsten, kunnen worden geëxporteerd naar een [Excel-spreadsheet](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)en opnieuw worden geïmporteerd naar een lijst op een andere site.

U kunt ook een hulpprogramma van derden gebruiken om de lijst tussen sites te migreren om functie, lijstweergaven, opmaak en andere kenmerken te behouden.

**Wikibestanden exporteren**

Wiki-inhoud binnen teamkanalen wordt opgeslagen in een HTML-bestand dat is opgemaakt in een speciale bibliotheek van de bijbehorende SharePoint-site. Ze kunnen niet direct worden geëxporteerd en geïmporteerd naar een andere kanaalwiki, maar kunnen worden geconverteerd naar een HTML-bestand en worden geopend als webpagina.

## <a name="microsoft-stream"></a>Microsoft Stream

Video's in Stream die zijn gekoppeld aan een groep of team, zijn net als Power Automate niet eigendom van de groep en worden niet verwijderd wanneer de groep wordt verwijderd. Video's in Stream zijn eigendom van de persoon die de video heeft geüpload of gemaakt, zelfs als ze gebruikers of groepen als eigenaren toevoegen. Dit is ook het geval voor vergaderingen die zijn opgenomen in een Teams-kanaal. deze zijn eigendom van de persoon die de opname heeft gestart.

**Andere eigenaren toevoegen**

Aangezien de video behouden blijft in Stream, ongeacht het verwijderen van groepen, kan de oorspronkelijke eigenaar de video delen met andere gebruikers en [groepen,](/stream/portal-edit-video)zelfs als eigenaars.

**De video downloaden**

In scenario's waarin de video niet hoeft te worden bewaard in Stream of moet worden opgeslagen op een alternatieve locatie, zoals een recordbeheersysteem, kan een eigenaar deze lokaal [downloaden](/stream/portal-download-video)

## <a name="yammer"></a>Yammer

In tegenstelling tot gesprekken in Microsoft Teams, biedt Yammer zowel gebruikers als beheerders opties om gesprekken te verplaatsen of te exporteren.

**Gesprekken verplaatsen naar een andere groep of community**

Gesprekken kunnen door elke gebruiker worden verplaatst naar een andere Yammer-groep, niet alleen door eigenaren of beheerders. Dit is mogelijk in zowel de [klassieke Yammer-](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)als de [nieuwe Yammer-interfaces.](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680)

**Netwerkgegevens exporteren**

Yammer-netwerkbeheerders kunnen een [export van](/yammer/manage-security-and-compliance/export-yammer-enterprise-data)netwerkgegevens uitvoeren, maar hierdoor worden alle gesprekken voor het hele netwerk geëxporteerd. De resulterende export bevat echter de groeps-id, zodat u gesprekken op basis van deze gegevens kunt filteren.