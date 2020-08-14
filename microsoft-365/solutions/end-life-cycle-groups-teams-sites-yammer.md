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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Opties voor het einde van de levenscyclus voor groepen, teams en Yammer.
ms.openlocfilehash: ab06f06cc65614ee313892a026c2f482d641791f
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662559"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Opties voor het einde van de levenscyclus voor groepen, teams en Yammer

Microsoft 365-groepen en Microsoft teams werken met diverse verbonden services. Wanneer een groep of team wordt verwijderd, worden de meeste gegevens in de verbonden services ook verwijderd. In dit artikel worden de opties beschreven voor het behouden van informatie door deze uit de groep of het team te verplaatsen voordat u ze verwijdert.

Een veelvoorkomende procedure voor groepen of teams die niet meer nodig zijn, is om de bestanden uit het team te verplaatsen en deze op een andere locatie op te slaan, zoals een SharePoint-documentbibliotheek die fungeert als een bibliotheek of een archief. Dit is een goede manier van werken op basis van een oudere stijl voor de manier waarop informatie wordt opgeslagen in bestanden en mappen, en de communicatie via e-mail wordt uitgevoerd.

In de volgende tabel vindt u een overzicht van de services die zijn gekoppeld aan groepen en teams en de belangrijkste typen inhoud die u in elk van deze tabellen vindt:

|Service|Inhoudstypen|
|:------|:---------------|
|Teams|Kanaal gesprekken, bestanden in kanalen|
|Vormen|Structuur en resultaten van enquête|
|OneNote|Terechtkom|
|Outlook|E-mail en agenda|
|Planner|Project status en taakgegevens|
|Automatisch aan de macht|Workflowtypen|
|Power BI|Gegevens, rapporten en dashboards|
|Project op het web|Project plannen|
|Routekaart|Roadmaps|
|SharePoint|Bestanden, lijsten, wiki-kanaal gegevens voor teams|
|Stream|Video's|
|Yammer|Communicatie|

Wanneer u een groep of team verwijdert, worden de meeste gekoppelde resources ook verwijderd. Enkele uitzonderingen op dit zijn Video's in stream, en zijn eigendom van de persoon die deze heeft geüpload/opgenomen, as-stromen in Power Automatiseer. Project-en routekaart gegevens in project op Internet blijven op de cd staan en kunnen afzonderlijk worden hersteld.

Groepen en teams blijven 30 dagen binnen de dag van de Soft-versie en kunnen worden hersteld. Na de dertig dagen en alle bijbehorende bronnen, zoals services en inhoud, worden de producten volledig verwijderd uit de Microsoft 365-omgeving. Inhoud die met een bewaarbeleid is beveiligd blijft beschikbaar via eDiscovery-zoekopdrachten.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Aandachtspunten voor het einde van de levenscyclus van met groepen verbonden services

Er zijn drie belangrijke gebieden waarmee eigenaren van team-en groepseigenaren en IT-beheerders rekening moeten houden bij het verwijderen van een groep of team.

**Content**

Moet de inhoud worden bewaard nadat het team niet langer functioneel of niet beschikbaar is? Is het voldoende om Bewaar mogelijkheden van Microsoft 365 te vertrouwen, of is een deel van de inhoud in apps en services die geen behoud bieden? Dient de inhoud te worden bewaard voor recordbeheer doeleinden, voor archiveringsdoeleinden of voor toekomstig gebruik en verwijzings doeleinden?

Voordat u potentiële gegevensverlies kunt vermijden, moet u eerst eerst vragen om een team te bevestigen of te verwijderen.

**Reparatie**

Voor de inhoud van diverse apps en services moet de inhoud in het huidige werk formulier blijven staan? Als u bijvoorbeeld het Power BI-rapport toegankelijker wilt maken, moet u de formulierresultaten beschikbaar maken in de weergave visuele samenvatting, zijn de lijsten in SharePoint gekoppeld aan of worden ingesloten.

Net als bij de overwegingen voor de inhoud moet u eerst eerst vragen om de onderliggende groep te laten verwijderen, aangezien het exporteren van de inhoud mogelijk niet voldoende hoeft te zijn.

**Gast**

Wanneer gasten worden uitgenodigd voor een team, maakt de werkstroom hun identiteit in de Azure Active Directory van de gastheer organisatie voordat ze aan het team worden toegevoegd. Wanneer een team wordt verwijderd, worden de gasten niet verwijderd uit Azure Active Directory, maar ook in de Microsoft teams-omgeving. Hoewel gasten geen toegang hebben tot groepen, sites, teams of inhoud die niet met hen zijn gedeeld, kunnen ze de functies in Microsoft teams nog steeds gebruiken, bijvoorbeeld om te beginnen met chatten, telefoon-en videogesprekken en apps.

Een team-of groepseigenaar kan een externe gebruiker uitnodigen om een gast te worden in azure Active Directory, ze aan het team toe te voegen en ze ook verwijderen van het team. De eigenaar van een team kan de gast niet verwijderen uit Azure Active Directory, maar kan alleen worden uitgevoerd door een globale beheerder of gebruikersbeheerder.

Daarom is het belangrijk dat u gast beoordelingen uitvoert en begrijpt of gasten uit Azure Active Directory moeten worden verwijderd wanneer het team is verwijderd. Mogelijk zijn er een geldige zaak voor gasten in de adreslijst, zoals een lid van een of meer andere teams of het gebruik van andere Microsoft 365-of Azure-Services.

## <a name="teams"></a>Teams

Specifieke inhoud voor teams is hoofdzakelijk de vorm van gesprekken.

Gesprekken in kanalen kunnen niet worden gekopieerd of verplaatst met de functies van de native Microsoft teams-functionaliteit. Ze kunnen wel worden geëxporteerd met de grafiek-API.

Als u een bewaarbeleid toepast op teams, worden de gesprekken bewaard en beschikbaar via eDiscovery-zoekopdrachten. (Items die zijn gevonden in eDiscovery-zoekopdrachten kunnen wel worden geëxporteerd, maar er zijn geen context of structuur van de oorspronkelijke bron meer, maar afzonderlijke berichten.

### <a name="archiving-a-team"></a>Een team archiveren

Het voordeel van het [archiveren van een team](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team) is dat het volledige toegang tot het team biedt, zodat gebruikers zich nog steeds kunnen bladeren door kanaal gesprekken en bestanden openen, zelfs als ze niet actief zijn. Daarnaast kunnen teams niet worden gearchiveerd als er nog steeds moet worden gewerkt (zoals in het geval van een project extensie).

Wanneer een team is gearchiveerd door een eigenaar, wordt dit ingesteld op alleen-lezen voor leden voor de inhoud in het team en indien geselecteerd, de bijbehorende SharePoint-site. Het doel van deze actie is om ervoor te zorgen dat gesprekken in kanalen bewaard blijven in de bestaande status, samen met inhoud op basis van SharePoint, zoals bestanden en wiki's.

Op de SharePoint-site zijn er geen wijzigingen in de weergave van de SharePoint-site, maar u kunt geen wijzigingen aanbrengen in bestanden of lijsten als de SharePoint-groep machtigingen voor de groep Microsoft 365 is ingesteld op sitebezoekers niveau. Dit omvat het OneNote-notitieblok voor het team, omdat dit is opgeslagen in de bibliotheek site activa van de SharePoint-site.

Wanneer een team is gearchiveerd, blijft de onderliggende groep Microsoft 365 onder het verloopbeleid vallen (indien ingesteld) en moet de eigenaar het team verder verlengen.

Hoewel de inhoud van de kanaal gesprekken en de inhoud van de SharePoint-site wordt ingesteld op alleen-lezen, wordt dit niet toegepast op andere gekoppelde services:

- Planner-buckets en-taken kunnen nog steeds worden gemaakt, gewijzigd en verwijderd
- Formulier kan nog steeds ingediende items ontvangen
- Postvak in van Outlook kan nog steeds e-mail ontvangen
- Power BI-dashboards,-rapporten en-gegevens kunnen nog steeds worden gewijzigd
- Projecten en route plannen kunnen nog steeds worden bewerkt in de webversie van project
- Video's kunnen nog steeds worden geüpload, gewijzigd en verwijderd in de stream
- Stromen in Power Automatiseer kunnen nog steeds worden gemaakt, gewijzigd, verwijderd en worden uitgevoerd (ze kunnen echter niet worden uitgevoerd, indien nodig een bericht plaatsen in een kanaal van het gearchiveerde team)

## <a name="forms"></a>Vormen

Hoewel een formulier van een ander account naar een groep kan worden verplaatst, kan het niet worden verplaatst of gekopieerd van de ene groep naar de andere. Er zijn drie opties beschikbaar voor een formulier wanneer een team wordt verwijderd.

**Het formulier dupliceren**

U kunt formulieren [delen als sjablonen](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f), zodat andere gebruikers deze kunnen kopiëren naar hun eigen account of een groep. Dit houdt niet in dat de gegevens van ingediende resultaten worden bewaard; alleen formulierstructuur zoals vragen en instellingen.

**Resultaten exporteren naar een werkblad**

Als de gegevens van de formulier antwoorden moeten worden bewaard, kunt u dit bereiken door [de resultaten te exporteren naar een Excel-werkblad](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af). Hiermee exporteert u alleen de vragen en hun antwoorden als gegevens, maar niet de door formulieren gemaakte grafieken.


**Het formulier verwijderen**

Tijdens het verwijderen van de groep zal ook het verwijderen van gekoppelde formulieren resulteren, groepsleden kunnen [ze rechtstreeks verwijderen](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) zonder dat ze een eigenaar van de groep zijn, maar dit is een handmatige stap waarbij geen extra voordeel wordt geboden.

## <a name="onenote"></a>OneNote

Het OneNote-notitieblok dat in een groep is opgenomen, wordt opgeslagen in de bibliotheek site activa binnen de gekoppelde SharePoint-site. Hoewel notitieblokbestanden soms niet tegelijkertijd kunnen worden verspreid over meerdere bestanden, kunnen ze niet afzonderlijk worden gekopieerd en geopend. In plaats daarvan moet de inhoud van het OneNote-notitieblok worden verplaatst of geëxporteerd met behulp van OneNote 2016.

**Pagina's en secties naar een ander notitieblok verplaatsen**

Door [pagina's of secties afzonderlijk te verplaatsen naar een ander notitieblok](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) biedt u eigenaren van de mogelijkheid hun gegevens op te schonen en uitsluitend wat ze moeten bewaren.

**Het hele notitieblok als een pakket exporteren**

Als het hele notitieblok moet worden bewaard met de bestaande structuur, kan het worden [geëxporteerd als een OneNote-pakket](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) bestand en vervolgens worden geïmporteerd naar een nieuwe locatie. U kunt dit ook gebruiken als een methode om de inhoud in één bestand te behouden in plaats van de bestaande structuur met meerdere bestanden.

**Afdrukken naar PDF**

In scenario's waarbij een deel van de inhoud van het notitieblok alleen moet worden bewaard voor de verwijzingen of als records, kunnen afzonderlijke pagina's worden [afgedrukt in PDF en ergens anders worden opgeslagen](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd).

## <a name="mailbox-and-calendar"></a>Postvak en agenda

Het gebruik van het door de groep gekoppelde postvak is niet ongebruikelijk, ook al zijn er ook veel gesprekken binnen de team kanalen gehouden. In het postvak worden alleen e-mailberichten opgeslagen die rechtstreeks naar de e-mail waren verzonden en geen e-mailberichten bevatten die rechtstreeks naar kanalen zijn verzonden.

In sommige gevallen zijn de e-mailberichten die zijn opgeslagen in het postvak mogelijk een melding van vergaderingen, updates van planner en andere door de toepassing gemaakte berichten. Het is belangrijk dat de inhoud van het postvak wordt gecontroleerd om te bepalen of de inhoud moet worden bewaard of verwijderd.

Als u een bewaarbeleid toepast op Exchange, worden de e-mailberichten en agenda-items bewaard en beschikbaar via eDiscovery-zoekopdrachten.

**E-mail en agenda exporteren**

Leden van het team of de groep kunnen [de inhoud van het postvak en de agenda exporteren naar een PST-bestand (Outlook Data/Personal Storage)](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91). Dit bestand kan vervolgens ergens anders worden opgeslagen, of de inhoud kan worden geïmporteerd in een ander postvak. De voormalig wordt niet aanbevolen als de inhoud van het PST-bestand kan niet worden doorzocht zonder deze te openen in Outlook, en het bestand kan na verloop van tijd beschadigd raken.

**Inhouds migratie**

Beheerders kunnen hulpprogramma's van derden gebruiken om de inhoud van de e-mail en de agenda tussen postvakken te migreren zonder tussenkomst van de gebruiker. Een potentiële opslaglocatie kon een gedeeld postvak zijn dat alleen als een ' Archief ' van de inhoud van het postvak van de groep fungeert.

## <a name="planner"></a>Planner

Een groep of team kan meerdere abonnementen hebben. Het is belangrijk dat u zich in het offboarding-proces bevindt om ervoor te zorgen dat elk abonnement wordt gebruikt om de inhoud van de inhoud te behouden. Zoals de andere producten, zijn er in planner verschillende benaderingen voor het maken van verwijderen-inhoud.

**Een abonnement exporteren naar een werkblad**

Als u een kopie van het plan voor het bewaren van record behoud moet bewaren, kunt u dit het beste doen door [het abonnement naar een Excel-werkblad te exporteren](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a). Dit is een eenrichtings actie, aangezien er geen optie is om plannen van een spreadsheet te importeren.

> [!IMPORTANT]
> Als u een abonnement exporteert naar Excel, worden de meeste informatie binnen het abonnement opgenomen, maar u kunt geen opmerkingen, koppelingen of bestanden toevoegen.

**Taken naar een ander plan kopiëren en verplaatsen**

Hoewel dit een oplossing is, kunnen afzonderlijke taken niet worden [gekopieerd en verplaatst tussen plannen](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) binnen dezelfde groep, waardoor de vergoeding wordt opgeheven als de groep die aan het abonnement is gekoppeld, wordt verwijderd.

**Geheel abonnement kopiëren**

U kunt ook [het hele abonnement kopiëren](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4). Dit kan echter geen bestaande groep of zelfs binnen dezelfde groep zijn. Met het kopiëren van het plan wordt een nieuwe groep gemaakt. Daarnaast bevat het kopiëren van het hele abonnement geen opmerkingen, toewijzingen, koppelingen, bijlagen of datums.

## <a name="power-automate"></a>Automatisch aan de macht

Stromen die zijn gemaakt in Powers Automatiseer en die zijn gekoppeld aan een groep of team, behoren niet tot de groep en zijn eigendom van de maker en worden alleen gedeeld met andere gebruikers en groepen. Dit heeft geen invloed op de toepassing als een groep of team wordt verwijderd.

**De eigenaar van de stroom wijzigen**

Als de werkstroom moet blijven werken, kunnen eigenaren gewoon andere gebruikers of Microsoft 365-groepen toevoegen als eigenaren.

**De stroom exporteren**

Als de werkstroom niet hoeft te blijven werken, maar deze moet worden bewaard voor potentiële toekomstig gebruik, kan de werkstroom worden [geëxporteerd als een bestand](https://flow.microsoft.com/blog/import-export-bap-packages/) en later opnieuw worden geïmporteerd.

## <a name="power-bi"></a>Power BI

Power BI-gegevens en-werkruimten kunnen onafhankelijk van groepen en teams werken, en de aanbod van andere werkbelastingen op verschillende manieren om te offboarded.

**Rapporten kopiëren naar een andere werkruimte**

Als het rapport in de functionele stand van de groep of het team moet blijven staan, kan het worden [gekopieerd van de bestaande werkruimte naar een andere werkruimte binnen Power bi](https://docs.microsoft.com/power-bi/connect-data/service-datasets-copy-reports).

**Gegevens van een dashboard of rapport exporteren**

Als het rapport niet langer actief hoeft te zijn, maar de gegevens moeten worden bewaard, kan het worden [geëxporteerd naar Excel](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).

## <a name="project"></a>Projector

Projecten en route plannen die zijn gemaakt in de webversie van project, kunnen worden gekoppeld aan Microsoft 365 groepen en bieden methoden voor offboarding die vergelijkbaar is met Power BI.

**Een project toewijzen aan een andere groep**

Als het project de functionele status van de groep of het team moet behouden, kunt u dit [toewijzen aan een andere Microsoft 365-groep](https://docs.microsoft.com/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) met behulp van het Dynamics 365 Beheercentrum.

**Gegevens uit het project of de routekaart exporteren**

Met het Dynamics 365 Beheercentrum is het mogelijk om [Gebruikersgegevens van het project](https://docs.microsoft.com/project-for-the-web/export-user-data-from-project-for-the-web) naar een spreadsheet te exporteren, of als u een PowerShell-script gebruikt, kunnen de gegevens worden geëxporteerd naar het projectbestand. MPP) en XML-bestandsindelingen.

## <a name="sharepoint"></a>SharePoint
Alle bestanden in team kanalen worden opgeslagen in de documentbibliotheek op de SharePoint-site van de gekoppelde groep. In sommige gevallen kunnen andere inhoud dan documenten bestaan in SharePoint, bijvoorbeeld lijsten of pagina's.
Bestanden zijn doorgaans opgeslagen op drie primaire locaties binnen een SharePoint-site:

- Pagina's-bibliotheek met site pagina's
- Afbeeldingen gebruikt in pagina's-bibliotheek site activa
- Bestanden in kanalen: documentenbibliotheek
- Wikipagina's: Wikigegevens bibliotheek van teams

Als op de site een of meer subsites zijn genest en eronder, moet het offboarding-proces voor elke subsite worden herhaald. Als het team persoonlijke kanalen bevat, is er een afzonderlijke SharePoint-site voor elk kanaal.

Het is belangrijk dat u bestanden verwijdert van een groep of team om te zien of ze kunnen worden gedeeld met gebruikers die geen lid zijn van de groep of het team (zowel intern als extern voor de organisatie), en aangezien dit de beste wijziging kan zijn.

**Bestanden downloaden**

Wanneer bestanden in SharePoint zijn opgeslagen in een van de bovenstaande Bibliotheken, kunt [u deze downloaden naar een lokale computer](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05).

**Bestanden verplaatsen**

U kunt bestanden ook verplaatsen naar een andere locatie in SharePoint, zoals een bibliotheek op een andere site.
Kruisverwijzingsnr https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc

**Lijst exporteren** Gegevens die zijn opgeslagen in SharePoint-lijsten kunnen worden [geëxporteerd naar een Excel-werkblad](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9), en opnieuw worden geïmporteerd naar een lijst op een andere site.

U kunt ook een programma van derden gebruiken om de lijst te migreren tussen sites, zodat u functies, lijstweergaven, opmaak en andere kenmerken kunt behouden.

**Wiki-bestanden exporteren**

Wiki-inhoud binnen team kanalen wordt opgeslagen in een HTML-bestand dat is opgemaakt in een speciale bibliotheek van de bijbehorende SharePoint-site. Ze kunnen niet direct worden geëxporteerd naar een andere kanaal-wiki, maar kunnen worden geconverteerd naar een HTML-bestand en geopend als een webpagina.

## <a name="microsoft-stream"></a>Microsoft Stream

Net als bij het automatiseren van de functies van Power link zijn Video's in streams die zijn gekoppeld aan een groep of team, niet echt eigendom van de groep en worden niet verwijderd wanneer de groep wordt verwijderd. Video's in stream zijn eigendom van de persoon die de video heeft geüpload of gemaakt, zelfs als ze gebruikers of groepen toevoegen als eigenaren. Dit is ook het geval voor vergaderingen die zijn opgenomen in een teams-kanaal; het eigendom is van de persoon die de opname heeft gestart.

**Andere eigenaren toevoegen**

Wanneer de video wordt bewaard in stream, ongeacht het verwijderen van een groep, kan de oorspronkelijke eigenaar [de video delen met andere gebruikers en groepen, zelfs toevoegen als eigenaren](https://docs.microsoft.com/stream/portal-edit-video).

**Download de video**

In scenario's waarbij de video niet in de stream hoeft te blijven staan of moet worden opgeslagen op een andere locatie, zoals een record beheersysteem, kan een eigenaar [deze lokaal downloaden](https://docs.microsoft.com/stream/portal-download-video)

## <a name="yammer"></a>Yammer

In tegenstelling tot gesprekken in Microsoft teams biedt Yammer zowel gebruikers als beheerders opties voor het verplaatsen of exporteren van gesprekken.

**Gesprekken verplaatsen naar een andere groep of Community**

Gesprekken kunnen door iedere gebruiker worden verplaatst naar een andere Yammer-groep, niet alleen eigenaren of beheerders. Dit is mogelijk in de [klassieke Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872), evenals de [nieuwe Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) -interfaces.

**Netwerkgegevens exporteren**

Yammer-netwerkbeheerders kunnen een [Netwerkgegevens exporteren](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data), maar wel wel alle gesprekken voor het hele netwerk exporteren. Voor de resultaten van de groeps-ID wordt er echter een groeps-ID weergegeven, zodat u gesprekken kunt filteren op basis van dit.
