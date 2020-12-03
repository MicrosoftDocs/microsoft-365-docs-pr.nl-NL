---
title: Bedreigings Verkenner en real-time ontdekken
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Meer informatie over het gebruik van de Verkenner en de realtime-detectie in de beveiligings & nalevings centrum om bedreigingen effectiever en efficiënt te onderzoeken en te beantwoorden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 021810a4d64dc3a8d9089a3b7174a1b5f536745a
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561397"
---
# <a name="threat-explorer-and-real-time-detections"></a>Bedreigings Verkenner en real-time ontdekken

Als uw organisatie [Microsoft Defender voor Office 365](office-365-atp.md)heeft en u de [benodigde machtigingen](#required-licenses-and-permissions)hebt, hebt u de keuze uit de **Verkenner** of de **realtime** (voorheen *realtime-rapporten* ), [Zie wat is er nieuw](#new-features-in-threat-explorer-and-real-time-detections)!. Ga in het beveiligings & nalevings centrum naar **Threat Management** en kies vervolgens **Verkenner** _of_ **realtime-detecties**.

|Met Microsoft Defender voor Office 365 abonnement 2 ziet u het volgende:|Met Microsoft Defender voor Office 365 abonnement 1 ziet u het volgende:|
|---|---|
|![Bedreigings Verkenner](../../media/threatmgmt-explorer.png)|![Detecties in realtime](../../media/threatmgmt-realtimedetections.png)|
|

Met de Verkenner (of realtime detectie) hebt u een krachtig rapport waarmee uw beveiligingsactiviteiten team op hun eigen en efficiënte manier kunnen onderzoeken en beantwoorden. Het rapport is vergelijkbaar met de volgende afbeelding:

![Ga naar Threat Management \> Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Met dit rapport kunt u:

- [Zie malware die door Microsoft 365 beveiligingsfuncties is gedetecteerd.](#see-malware-detected-in-email-by-technology)
- [Bekijk gegevens over phishingberichten en klik op Verdict](#view-data-about-phishing-urls-and-click-verdict)
- [Een automatisch onderzoek en antwoord proces starten vanuit een weergave in Verkenner](#start-automated-investigation-and-response) (alleen voor Office 365, abonnement 2)
- ... [Onderzoek kwaadaardige e-mail en nog veel meer](#more-ways-to-use-explorer-or-real-time-detections).

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a>Ervaar verbeteringen in de weergave van de bedreiging en de real-time detectie

### <a name="tags-in-threat-explorer"></a>Labels in de Threat Explorer

> [!NOTE]
> De functie gebruikers Tags is in voorbeeld, is niet beschikbaar voor iedereen, en kan veranderen. Voor informatie over de release planning raadpleegt u het Microsoft 365-wegwijzer.

Gebruikers Tags zijn id's voor specifieke groepen gebruikers in Microsoft Defender voor Office 365. Zie voor meer informatie over tags, licenties en het configureren van tags de [gebruikers Tags](user-tags.md).

In de bedreigings Verkenner kunt u informatie weergeven over gebruikers Tags in de volgende toepassingen:

#### <a name="email-grid-view"></a>Weergave van e-mail raster

De kolom Tags die in het raster van de e-mail worden weergegeven, bevat alle labels die zijn toegepast op de afzender of de postvakken van de geadresseerde. Standaard worden in systeem Tags zoals prioritaire accounts eerst weergegeven.

> [!div class="mx-imgBorder"]
> ![Labels filteren in de weergave e-mail raster](../../media/tags-grid.png)

#### <a name="filtering"></a>Bewerkingen

We hebben nu labels als een filter, zodat u precies achter de prioriteits accounts kunt, of specifieke scenario's voor gebruikers Tags, en zelfs resultaten met bepaalde Tags uitsluit als onderdeel van deze ervaring. U kunt deze functie combineren met de verschillende filters die we bieden en helpt u om uw onderzoek bereik te beperken

[![Labels ](../../media/tags-filter-normal.png) filteren](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Geen labels filteren](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>Flyout e-mail Details
Als u de afzonderlijke labels voor afzender en geadresseerde wilt weergeven, klikt u op het onderwerp. De vervolgmenu berichtdetails wordt geopend. Op het tabblad Samenvatting worden de labels voor de afzender en de geadresseerden apart weergegeven, als deze beschikbaar zijn voor een e-mailbericht.
De informatie over de afzonderlijke Tags voor afzender en geadresseerde, wordt ook uitgebreid naar geëxporteerde CSV, waar u deze details in twee afzonderlijke kolommen kunt zien.

> [!div class="mx-imgBorder"]
> ![Tags voor e-mail gegevens](../../media/tags-flyout.png)

Informatie over labels wordt ook weergegeven in de vervolgmenu URL-klikken. Als u wilt zoeken naar de URL klikken op flyout, gaat u naar de weergave voor phishing of alle E-mail en klikt u vervolgens op de tab Url's of URL op de tab-toets. Als u op een enkele URL-vervolg optie klikt, wordt er meer informatie weergegeven over de klikken voor die URL

> [!div class="mx-imgBorder"]
> ![URL-Tags](../../media/tags-urls.png)

## <a name="improvements-to-threat-hunting-experience-upcoming"></a>Verbeteringen in de ervaring voor de jacht-ervaring (binnenkort)

### <a name="updated-threat-information-for-emails"></a>Update van bedreigings informatie voor e-mailberichten

We hebben ons gefocust over verbeteringen in platform en gegevenskwaliteit om de nauwkeurigheid en consistentie van de gegevens te verbeteren. Deze set updates omvat een consolidatie van pre-leveringsinformatie (de actie die is uitgevoerd voor een e-mailbericht als onderdeel van het ZAP-proces) tot één record, met een opvallende veroudering, zoals spam Verdict, niveau bedreigingen op entiteitsniveau (zoals de URL is schadelijk) en de nieuwste bezorgingslocaties.

Na deze updates ziet u één vermelding voor elk bericht, ongeacht de diverse gebeurtenissen na de levering die op het bericht plaatsvonden. U kunt ook ZAP, handmatig herstel (dat wil zeggen beheerdersactie), dynamische levering, etc.

Naast malware en phishing is het ook mogelijk om spam verdict te zien die zijn gekoppeld aan een e-mailbericht. In het e-mailbericht ziet u alle bedreigingen van de e-mail, samen met de bijbehorende detectie technologieën. U kunt elk e-mailbericht 0, 1 of meerdere bedreigingen hebben. In het gedeelte Details van de E-mail flyout ziet u de huidige bedreigingen. Daarnaast zou voor meerdere bedreigingen (bijvoorbeeld een e-mailbericht met malware en phishing) de Threat-Detection-toewijzing geven, wat betekent dat de detectie tech leidde tot het identificeren van de bedreiging.

De set detectie technologieën is bijgewerkt met nieuwe detectiemethoden, en ook voor de detectie technologieën van spam, en overal in de verschillende e-mail weergaven (malware, phishing, alle e-mailberichten) hebt u dezelfde, consistente set detectie technologieën om de resultaten te filteren.

> [!NOTE]
> Verdict-analyse kan niet noodzakelijkerwijs aan entiteiten zijn gebonden. Voorbeeld: een e-mailbericht kan als phishing of spam worden geclassificeerd, maar er zijn geen Url's die een phishing-of spam Verdict. Dit komt doordat de filters ook inhoud en andere details van een e-mailbericht evalueren voordat ze een verdict toewijzen.

#### <a name="threats-in-urls"></a>Bedreigingen in Url's

In de vervolgmenu e-mail-> tabblad Details ziet u nu een specifieke bedreiging voor de URL (de bedreiging voor een URL kan malware, phishing, spam of geen) worden weergegeven.

> [!div class="mx-imgBorder"]
> ![URL-bedreigingen](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a>Bijgewerkte tijdlijnweergave (binnenkort)

> [!div class="mx-imgBorder"]
> ![Bijgewerkte tijdlijnweergave](../../media/Email_Timeline.png)

Naast het identificeren van alle activiteiten met betrekking tot bezorging en na levering, biedt de tijdlijnweergave ook informatie over de bedreiging die op dat moment is geïdentificeerd voor een subset van deze gebeurtenissen. Ook krijgt u meer informatie over extra acties (bijvoorbeeld, ZAP, handmatig herstel), samen met het resultaat van die actie. De tijdlijnweergave bevat informatie over de oorspronkelijke bezorgings periode en daaropvolgende gebeurtenissen na de bezorging van een e-mailbericht.

- Bron: dit kan de beheerder/het systeem/de gebruiker zijn op basis van de bron van de gebeurtenis.
- Gebeurtenis: Dit omvat gebeurtenissen op het hoogste niveau zoals de oorspronkelijke levering, handmatig herbemiddeling, ZAP, inzendingen en dynamische bezorging.
- Actie: Dit geldt voor de specifieke actie die is uitgevoerd als onderdeel van ZAP-of beheerdersactie (zoals een tijdelijke verwijdering).
- Threats: behandelt de bedreigingen (malware, phishing en spam) die op dat moment identificeren.
- Resultaat/informatie: Hier vindt u meer informatie over het resultaat van de actie, ongeacht of de actie is uitgevoerd als onderdeel van ZAP/admin.

### <a name="original-and-latest-delivery-location"></a>Oorspronkelijke en meest recente bezorgingslocatie

De bezorgingslocatie bevindt zich nu in het raster en de e-mail flyout van de e-mail. Doorgaan wordt de naam van het veld bezorgingslocatie gewijzigd in oorspronkelijke bezorgingslocatie. Daarnaast wordt ook een ander veld met de naam meest recente bezorgingslocatie geïntroduceerd.

Op de oorspronkelijke bezorgingslocatie vindt u meer informatie over de locatie van een e-mailbericht dat u aanvankelijk ontvangt. De meest recente bezorgingslocatie bevat locaties waar een e-mailbericht mogelijk is gelost na systeemacties zoals ZAP-of beheeracties, zoals **verplaatsen naar verwijderde items**. Nieuwste bezorgingslocatie is bedoeld om beheerders op de hoogte te stellen van de laatste locatie van de publicatie na de bezorging van het bericht of van systeem/beheer-acties. Op basis van ontwerpen bevat dit geen activiteiten met betrekking tot de eindgebruikers van de e-mail. Bijvoorbeeld: als een gebruiker een bericht verwijdert of het bericht verplaatst naar archief-of PST-bestand, wordt het bericht ' bezorgingslocatie ' niet bijgewerkt. Als een systeemactie de locatie echter heeft bijgewerkt (bijvoorbeeld ZAP resulteerde in een e-mailbericht dat overstapt naar Quarantine), ziet u de nieuwste bezorgingslocatie in quarantaine.

> [!div class="mx-imgBorder"]
> ![Bijgewerkte bezorgingslocaties](../../media/Updated_Delivery_Location.png)

> [!NOTE]
> In sommige gevallen wordt de bezorgingslocatie en de bezorgings actie weergegeven als de waarde:
>
> - U ziet mogelijk de bezorgingslocatie als afgeleverd, en de bezorgingslocatie is onbekend. Dit gebeurt als het bericht is bezorgd, maar een regel voor Postvak in het bericht heeft verplaatst naar een standaardmap (concept, archief, etc.) in plaats van het postvak in of de map Ongewenste E-mail.
>
> - De meest recente bezorgingslocatie kan niet worden herkend als een beheerder/systeemactie (bijvoorbeeld, ZAP, admin actie) wordt geprobeerd, maar het bericht niet is gevonden. Meestal gebeurt de actie wanneer de gebruiker het bericht heeft verplaatst of verwijderd. In dergelijke gevallen controleert u de kolom resultaat/Details in de tijdlijnweergave. Zoek het bericht: bericht is verplaatst of verwijderd door de gebruiker.

> [!div class="mx-imgBorder"]
> ![Bezorgingslocaties voor tijdlijn](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a>Aanvullende acties

Aanvullende acties bestaan uit de acties die zijn toegepast op de bezorging van de E-mail, en kunnen ZAP, handmatig herstel (actie die worden uitgevoerd door een beheerder, zoals een tijdelijke verwijdering), dynamische bezorging en opnieuw verwerkte (een e-mailbericht dat via een e-mailbericht is verzonden.

> [!NOTE]
>
> - Als onderdeel van deze wijziging wordt de verwijderde naam van de ZAP-waarde die op dat moment is geoppereerd in het bezorgings filter weggegooid. U kunt ook zoeken naar alle e-mailberichten met de ZAP-poging via de aanvullende acties.
>
> - Er worden nieuwe velden en waarden weergegeven voor detectie technologieën en extra acties (met name voor ZAP-scenario's). Evalueer uw bestaande opgeslagen Query's en bijgehouden query's om ervoor te zorgen dat ze werken met de nieuwe waarden.

> [!div class="mx-imgBorder"]
> ![Additional_Actions](../../media/Additional_Actions.png)

### <a name="system-overrides"></a>Systeem overschrijvingen

Systeem overschrijvingen zijn een methode voor het aanstellen van uitzonderingen op de beoogde bezorgingslocatie van een bericht door de bezorgingslocatie van het systeem te vervangen (op basis van de bedreigingen en andere detecties die worden aangegeven door de filter stapel). Door systeem overschrijvingen kan worden ingesteld via Tenant of gebruikersbeleid om het bericht op te geven dat door het beleid wordt voorgesteld. Overschrijvingen zijn handig voor het identificeren van een onbedoelde aflevering van schadelijke berichten vanwege bezorgings hiaten (bijvoorbeeld een zeer algemeen beleid voor het veilig afzenderset dat door een gebruiker is ingesteld). Deze opheffings waarden kunnen zijn:

- Toegestaan door gebruikersbeleid: dit is wanneer een gebruiker domeinen of afzenders toestaat door beleidsregels op Postvak niveau te maken.
- Geblokkeerd door gebruikersbeleid: dit is wanneer een gebruiker domeinen of afzenders blokkeert door beleidsregels op het postvak niveau te maken.
- Toegestaan door het beleid van de organisatie: dit doet zich voor als de beveiligings teams van de organisatie beleidsregels voor de organisatie of Exchange-e-mail stroom regels (ook wel transport regels genoemd) hebben voor het toestaan van afzenders en domeinen voor gebruikers in hun organisatie. Dit kan bestaan voor een set gebruikers of de hele organisatie.
- Toegestaan door het beleid voor de organisatie: Dit houdt in dat de beveiligings teams van de organisatie beleidsregels of e-mail stroom regels instellen voor het blokkeren van afzenders, domeinen, berichten talen of bron-IPs voor gebruikers in hun organisatie. Dit kan ook voor een reeks gebruikers of de hele organisatie.
- Bestandsextensie wordt geblokkeerd door het organisatiebeleid: dit doet zich voor als een bestandsextensie wordt geblokkeerd door de beveiligings teams van een organisatie via de beleidsinstellingen voor anti-malware. Deze waarden worden nu weergegeven in e-mail gegevens om onderzoek te doen. Secops teams kunnen ook filteren op geblokkeerde bestandsextensies met behulp van de functies voor uitgebreid filteren.

[![System_Overrides ](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> ![System_Overrides_Grid](../../media/System_Overrides_Grid.png)

### <a name="improvements-around-url-and-clicks-experience"></a>Verbeteringen rond URL'S en klikken

De reeks verbeteringen die zijn gericht op URL en URL klikken op gegevens zijn:

- Het weergeven van de volledige geklikt URL (waaronder query parameters die deel uitmaken van de URL) binnen de Click-sectie in URL-flyout. Op dit moment wordt het URL-domein en pad weergegeven op de titelbalk. We verlengen deze informatie om de volledige URL weer te geven.

- Oplossingen voor URL-filters (URL versus URL Domain versus URL Domain en Path): er zijn updates voor het zoeken naar berichten die een URL bevatten/Klik op Verdict. Daarom hebben we ondersteuning ingeschakeld voor protocol agnostic-zoekopdrachten (dat wil zeggen dat u rechtstreeks kunt zoeken naar een URL zonder http). Standaard wordt via URL'S gezocht naar http, tenzij expliciet is opgegeven. Bijvoorbeeld:

  1. Zoek met en zonder het `http://` voorvoegsel in de URL-, het URL-domein en de url's-domein en-pad filtervelden. Dit gedrag is consistent en moet hetzelfde resultaat weergeven.

  1. Zoek het `https://` voorvoegsel in URL. Wanneer u dit niet doet, `http://` wordt uitgegaan van het voorvoegsel.

  1. `/` aan het begin en einde van de velden URL-pad, URL-domein en pad, wordt genegeerd. `/` aan het einde van het veld URL wordt genegeerd.

### <a name="phish-confidence-level"></a>Betrouwbaarheidsniveau voor phishing

Met betrouwbaarheid van phishing kunt u de mate van betrouwbaarheid identificeren, waarbij een e-mailbericht als phishing werd gecategoriseerd. De twee mogelijke waarden zijn hoog en normaal. In de eerste fase is dit filter alleen beschikbaar in de weergave phishing van de Threat Explorer.

[![Phish_Confidence_Level ](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>ZAP-URL-signaal

Dit wordt meestal gebruikt voor het melden van scenario's van ZAP-phishing, waarbij een e-mailbericht als phishing is geïdentificeerd en na levering is verwijderd Dit wordt gebruikt om de waarschuwing te verbinden met de overeenkomstige resultaten in Explorer. Het is een van de IOCs voor de waarschuwing.

Als onderdeel van de verbetering van de jacht, hebben we enkele updates gemaakt voor de bedreigings Verkenner en de realtime detectie. Dit zijn de verbeteringen van de ervaring, met de focus op de beleving van de jacht consistent. Hieronder ziet u een overzicht van deze wijzigingen:

- [Tijdzone verbeteringen](#timezone-improvements)
- [Bijwerken in het vernieuwingsproces](#update-in-the-refresh-process)
- [DrillDown voor de grafiek om toe te voegen aan filters](#chart-drilldown-to-add-to-filters)
- [Updates voor productgegevens](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>Filteren op gebruikers Tags

U kunt nu sorteren en filteren op een systeem of aangepaste gebruikers Tags om snel de reikwijdte van bedreigingen te begrijpt. Zie [gebruikers Tags](user-tags.md) voor meer informatie.

> [!IMPORTANT]
> Filteren en sorteren op gebruikerscodes bevindt zich momenteel in de openbare preview-versie.
> Dit kan ingrijpend veranderd voordat het commercieel uitkomt. Microsoft verbiedt geen garanties, uitdrukkelijke of impliciete informatie met betrekking tot de verstrekte informatie.

![Kolom Tags in Verkenner](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a>Tijdzone verbeteringen

U ziet de tijdzone voor de e-mail records binnen de portal en voor de geëxporteerde gegevens. De tijdzone is zichtbaar in functies zoals E-mail raster, Details flyout, e-mail tijdlijn en soortgelijke E-mail, zodat de tijdzone voor de resultatenset duidelijk is voor de gebruiker.

> [!div class="mx-imgBorder"]
> ![Tijdzone weergeven in Verkenner](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>Bijwerken in het vernieuwingsproces

We hebben uw feedback om verwarring met automatisch vernieuwen (bijvoorbeeld voor datum nadat u de datum hebt gewijzigd nadat u de pagina hebt gewijzigd) en handmatig vernieuwen (voor andere filters). Evenzo verwijdert filters potentiële klanten naar automatisch vernieuwen, dan wordt er een situatie waarbij het wijzigen van de verschillende filters tijdens het wijzigen van de query inconsistentie van de zoekfuncties kan veroorzaken. Om dit op te lossen, gaan we overstappen op een handmatig filtermechanisme.

Vanuit het oogpunt van de ervaring kan de gebruiker een verschillend bereik van filters (uit de filtersset en datum) toepassen en verwijderen en vervolgens op de knop Vernieuwen klikken om de resultaten te filteren nadat deze zijn uitgevoerd met het definiëren van de query. De knop Vernieuwen is ook bijgewerkt, zodat deze duidelijk op het scherm wordt weergegeven. We hebben ook Scherminfo en documentatie ter informatie bijgewerkt.

> [!div class="mx-imgBorder"]
> ![Klik op vernieuwen om resultaten te filteren](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>DrillDown voor de grafiek om toe te voegen aan filters

U kunt nu op de waarden van de grafieklegenda klikken om deze waarde als een filter toe te voegen. Houd er rekening mee dat u altijd op de knop Vernieuwen hoeft te klikken om de resultaten te filteren als onderdeel van de hierboven beschreven wijziging.

> [!div class="mx-imgBorder"]
> ![DrillDown via grafieken om te filteren](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>Updates voor productgegevens

U moet ook aanvullende informatie binnen het product zien. Bijvoorbeeld het totale aantal zoekresultaten in het raster (zie hieronder), en verbeteringen rond labels, foutberichten en Scherminfo, voor meer informatie over filters, zoekervaring en resultatensets.

> [!div class="mx-imgBorder"]
> ![Info over product weergeven](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>Uitgebreide mogelijkheden in de bedreigings Verkenner

### <a name="top-targeted-users"></a>Belangrijkste gerichte gebruikers

De lijst met de belangrijkste gebruikers wordt nu weergegeven in de malware-weergave voor e-mailberichten (binnen de sectie belangrijkste Malware-families). Deze weergave wordt ook binnen phishing en alle e-mail weergaven uitgebreid, waar u de vijf beste bedoelende gebruikers kunt zien, samen met het aantal pogingen voor elke gebruiker voor de bijbehorende weergave (bijvoorbeeld voor de phishing-weergave).
U kunt de lijst met gerichte gebruikers ook exporteren naar een limiet van 3000, samen met het aantal pogingen tot offline analyse voor elke e-mail weergave. U kunt ook Nee selecteren. met pogingen (met uitzonde maal 13 pogingen) opent u een gefilterde weergave in de bedreigings Verkenner, zodat u meer details kunt bekijken voor e-mailberichten en bedreigingen voor die gebruiker.

> [!div class="mx-imgBorder"]
> ![Belangrijkste gerichte gebruikers](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>Exchange-transportregels

Als onderdeel van gegevens verrijking dient u ook alle verschillende transportregels te zien die zijn toegepast op een bericht. Deze informatie wordt weergegeven in de weergave voor het weergeven van de E-mail (als u dit wilt bekijken, selecteert u kolom opties in het raster en voegt u een Exchange-Transport regel toe via de kolom opties in het raster) en de flyout Details in het e-mailbericht.
U kunt zowel de GUID als de naam van de transportregels zien die op het bericht zijn toegepast. U kunt ook zoeken naar de berichten met behulp van de naam van de transportregel. Dit is een ' contain '-zoekopdracht, wat betekent dat u kunt zoeken met gedeeltelijke zoekopdrachten.

#### <a name="important-note"></a>Belangrijke opmerking:

De ETR toe zoeken en de beschikbaarheid van namen is afhankelijk van de specifieke rol die aan u is toegewezen. U moet beschikken over een van de volgende rollen/machtigingen om de namen en zoekopdrachten van ETR toe te kunnen bekijken.  Als u niet beschikt over de volgende rollen die aan u zijn toegewezen, kunt u niet de namen van de transportregels zien en de naam van de berichten zoeken met behulp van de namen van de ETR toe. U kunt echter het ETR toe-label en de GUID-informatie in de e-mail gegevens zien. Uw andere ervaring rond het weergeven van records in e-mail rasters, e-mail flyout, filters en exporteren worden niet beïnvloed.

- Alleen EXO-preventie van gegevensverlies: alles
- Alleen EXO: O365SupportViewConfig: all
- AAD of EXO-beveiligingsbeheerder: alle
- AAD of EXO-beveiligings lezer: alles
- Alleen EXO-transport regels: alle
- EXO only-View-Only configuratie: alle

In het raster, het detail menu van de e-mail en de geëxporteerde CSV-gegevens, worden de Etr's weergegeven met een naam/GUID zoals hieronder weergegeven.

> [!div class="mx-imgBorder"]
> ![Exchange-Transport regels](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>Binnenkomende connectors

Connectors zijn een verzameling instructies waarmee u de manier kunt wijzigen waarop uw e-mailberichten overlopen van en naar uw Microsoft 365-of Office 365-organisatie, en de mogelijkheid om beveiligingsbeperkingen of besturingselementen toe te passen. U kunt in de Threat Explorer nu de verbindingslijnen weergeven die zijn gerelateerd aan een e-mailbericht en zoeken naar e-mailberichten met de namen van de verbindingslijnen.
De zoekfunctie van connectors is ' bevat ', wat betekent dat u ook gepaarde trefwoord zoekopdrachten werkt.
In de hoofdweergave voor details, de vervolgkeuze info en de geëxporteerde CSV-indeling, worden de connectors weergegeven in de indeling naam/GUID, zoals hieronder wordt weergegeven:

> [!div class="mx-imgBorder"]
> ![Details van connector](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nieuwe functies in de bedreigings Verkenner en de real-time detectie

Drie nieuwe functies toegevoegd aan de bedreigings Verkenner en de real-time detecties:

- [Voorbeeld van e-mailkop tekst](#preview-email-header-and-download-email-body)
- [E-mail tijdlijn](#email-timeline)
- [URL exporteren Klik op gegevens](#export-url-click-data)

Hieronder ziet u een overzicht van de nieuwe functies.

### <a name="preview-email-header-and-download-email-body"></a>Voorbeeld van e-mailkop tekst

De mogelijkheid om een voorbeeld van een e-mailbericht te bekijken en de tekst van het bericht te downloaden zijn nieuwe functies die beschikbaar zijn in de Threat Explorer Beheerders kunnen gedownloade berichtkoppen/e-mailberichten analyseren voor bedreigingen. Aangezien het downloaden van e-mailberichten de blootstelling van gegevens kan betekenen, wordt dit proces bepaald door toegangsbeheer op basis van rollen. Een nieuwe rol, *Preview*, moet worden toegevoegd aan een andere rolgroep (zoals beveiligingsactiviteiten of beveiligingsbeheerder) om de mogelijkheid om e-mailberichten te downloaden en voorbeelden van kopteksten weer te geven in de weergave alle e-mailberichten.

Maar in de Verkenner (en realtime-detectie) worden ook nieuwe velden toegevoegd waarmee u een beter beeld kunt krijgen van de locatie van uw e-mailberichten. Onderdeel van het doel van deze wijziging is om de jacht eenvoudiger te maken voor mensen met een hoeveelheid werk, maar het resultaat van de e-mail is in één oogopslag de locatie van de problematische e-mailberichten.

Hoe is dit gebeurd? De bezorgings status is nu uitgebroken in twee kolommen:

- **Bezorgings actie** : wat is de status van dit e-mailbericht?
- **Bezorgingslocatie** : waar werd dit e-mailbericht rondgestuurd als resultaat?

De bezorgings actie is de actie die op een e-mail is uitgevoerd vanwege bestaande beleidsregels of detecties. Dit zijn de mogelijke acties waarmee een e-mail kan worden verzonden:

|Aflevering|Ongewenst|Blokkeert|Gekomen|
|---|---|---|---|
|E-mail is bezorgd in het postvak in of de map van een gebruiker en de gebruiker kan deze rechtstreeks openen.|E-mail verzonden naar de map Ongewenste E-mail van de gebruiker of de map die is verwijderd, en de gebruiker heeft toegang tot e-mailberichten in die mappen.|Alle e-mailberichten die zijn gequarantined, dat niet is gelukt of zijn verwijderd. Dit is helemaal niet toegankelijk voor de gebruiker.|Alle e-mailberichten waarin schadelijke bijlagen worden vervangen door txt-bestanden die aangeven dat de bijlage schadelijk is.|

|Aflevering|Ongewenst|Blokkeert|Gekomen|
|---|---|---|---|
|E-mail is bezorgd in het postvak in van de gebruiker of een andere map, en de gebruiker kan deze rechtstreeks openen.|E-mail is verzonden naar de map Ongewenste E-mail van de gebruiker of de map die is verwijderd, en de gebruiker heeft toegang tot e-mailberichten in die mappen.|Alle e-mailberichten die zijn overgezet, die niet kunnen worden verwijderd en die niet toegankelijk zijn voor de gebruiker.|Alle e-mailberichten waarin schadelijke bijlagen zijn vervangen door txt-bestanden, waarbij de bijlage is beschadigd.|
|

En wat ze niet kan zien en wat ze niet kan doen:

|Toegankelijk voor eindgebruikers|Niet toegankelijk voor eindgebruikers|
|---|---|
|Aflevering|Blokkeert|
|Ongewenst|Gekomen|

Locatie van levering toont de resultaten van beleidsregels en detecties die na levering worden uitgevoerd. Het is gekoppeld aan een bezorgings actie. Dit veld is toegevoegd om inzicht te krijgen in de actie die optreedt wanneer er een probleem met de e-mail is gevonden. Dit zijn de mogelijke waarden van de lever locatie:

- **Postvak in of map**: het e-mailbericht bevindt zich in het postvak in of een map (volgens uw e-mail regels).
- **On-premises of extern**: het postvak bestaat niet in de Cloud, maar is on-premises.
- **Map Ongewenste e-mail**: de e-mail bevindt zich in de map Ongewenste e-mail van een gebruiker.
- **Map Verwijderde items**: het e-mailbericht in de map Verwijderde items van een gebruiker.
- **Quarantine**: het e-mailbericht in quarantaine, dat zich niet in het postvak van een gebruiker bevindt.
- **Mislukt**: het e-mailadres is niet bereikbaar voor het postvak.
- **Neergezet**: de e-mail wordt ergens in de e-mail stroom verwijderd.

### <a name="email-timeline"></a>E-mail tijdlijn

De **e-mail tijdlijn** is een andere nieuwe Explorer-functie, die bedoeld is voor een betere beleving van de jacht van de beheerder. Dit houdt in dat u een willekeurige functie uitvoert omdat er minder tijd is besteed aan het controleren van verschillende locaties om de gebeurtenis te leren kennen. Wanneer meerdere gebeurtenissen plaatsvinden aan of sluiten op een e-mail, worden deze gebeurtenissen weergegeven in een tijdlijnweergave. In werkelijkheid worden bepaalde gebeurtenissen die plaatsvinden na levering van uw e-mail, vastgelegd in de kolom ' speciale actie '. Als u de gegevens van de tijdlijn van dat e-mailbericht combineert met de speciale actie die u hebt uitgevoerd voor de bezorging van e-mail, geven beheerders beheerders inzicht in hoe hun beleidsregels werken, waarbij de e-mail uiteindelijk is gerouteerd, en in sommige gevallen, wat de laatste beoordeling was.

Zie voor meer informatie over het onderzoeken van kwaadaardige e-mailberichten een [kwaadaardige e-mailbericht dat is bezorgd in Office 365](investigate-malicious-email-that-was-delivered.md).

### <a name="export-url-click-data"></a>URL exporteren Klik op gegevens

Daarnaast is het ook mogelijk om rapporten voor URL-klikken te exporteren naar Microsoft Excel, zodat u de netwerkbericht-ID kunt bekijken, en ze klikken op Verdict, zodat u kunt zien waar de URL op het verkeer verloopt. Dit werkt als volgt: Vanaf de werkbalk Snel starten van Office 365 kunt u op de volgende keten klikken:

**Verkenner** \> **Phishing** \> weergeven **Klikken op** \> **Belangrijkste url's of URL-klikken** \> **Klik op een record om de URL-flyout te openen**

Wanneer u op een URL in de lijst klikt, ziet u in het deelvenster uitvullen een nieuwe knop exporteren. Gebruik deze knop om gegevens te verplaatsen naar een Excel-spreadsheet, zodat u deze eenvoudiger kunt rapporteren.

U kunt in het rapport realtime detecties de volgende keer naar dezelfde locatie gaan:

**Verkenner** \> **Detectie** \> van realtime **Phishing** \> weergeven **Url's** \> **Belangrijkste url's of bovenste klikken** \> **Klik op een record om de URL-flyout** \> te openen **Ga naar het tabblad klikken.**

> [!TIP]
> Netwerkbericht-ID Hiermee wordt de Klik terug naar specifieke e-mailberichten verzonden wanneer u in Verkenner of aan de hulpmiddelen van derden via netwerkbericht-ID zoekt. Door de netwerkbericht-ID te zoeken, leveren beheerders de specifieke e-mail die is gekoppeld aan een klik resultaat. Met de correlatie-id van de netwerkbericht-ID is bij export een snellere en krachtige analyse.

> [!div class="mx-imgBorder"]
> ![Klikken op tab in Verkenner](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Malware van de malware van een e-mail weergeven

U wilt malware van de malware in een e-mail weergeven, door Microsoft 365-technologie. Als u dit wilt doen, gebruikt u de [e-mail >](threat-explorer-views.md#email--malware) weergave voor malware van Explorer (of realtime gedetecteerde).

1. Kies in het beveiligings & conformiteitscentrum ( [https://protection.office.com](https://protection.office.com) ) de optie **Threat Management**  >  **Explorer** (of **realtime-detectie**). (In dit voorbeeld wordt Explorer gebruikt.)

2. Kies in het menu **weergave** de optie **e-mail**  >  **malware**.

   > [!div class="mx-imgBorder"]
   > ![Menu Beeld voor Verkenner](../../media/ExplorerViewEmailMalwareMenu.png)

3. Klik op **afzender** en kies vervolgens **Basic**  >  **Detection Technology**.

   Uw detectie technologieën zijn nu beschikbaar als filters voor het rapport.

   > [!div class="mx-imgBorder"]
   > ![Detectie technologieën voor malware](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Selecteer een optie en klik vervolgens op de knop **vernieuwen** om het filter toe te passen.

   > [!div class="mx-imgBorder"]
   > ![Geselecteerde detectietechnologie](../../media/ExplorerEmailMalwareDetectionTechATP.png)

Het rapport wordt vernieuwd om de resultaten van malware in een e-mail te tonen met behulp van de technologie optie die u hebt geselecteerd. U kunt hier verdere analyses uitvoeren.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Bekijk gegevens over phishingberichten en klik op Verdict

Stel dat u phishingberichten via Url's wilt weergeven in een e-mail, waaronder een lijst met Url's die zijn toegestaan, geblokkeerd en genegeerd. Voor het identificeren van Url's waarop geklikt, moeten [veilige koppelingen](atp-safe-links.md) zijn geconfigureerd. Zorg ervoor dat u [beleidsregels voor veilige koppelingen](set-up-atp-safe-links-policies.md) hebt ingesteld voor beveiliging van de tijd van klikken en logboekregistratie van Verdicts via veilige koppelingen.

Als u de Url's van de phishing in berichten en op Url's in phishingberichten wilt bekijken, gebruikt u de [e-mail > phishing-](threat-explorer-views.md#email--phish) weergave van Explorer (of realtime-detecties).

1. Kies in het beveiligings & conformiteitscentrum ( [https://protection.office.com](https://protection.office.com) ) de optie **Threat Management**  >  **Explorer** (of **realtime-detectie**). (In dit voorbeeld wordt Explorer gebruikt.)

2. Kies in het menu **weergave** de optie **e-mail**  >  **phishing**.

   > [!div class="mx-imgBorder"]
   > ![Het menu Beeld voor Explorer in de Phishingfilter-context](../../media/ExplorerViewEmailPhishMenu.png)

3. Klik op **afzender** en kies vervolgens **url's**  >  **op Verdict**.

4. Selecteer een of meer opties, zoals **geblokkeerde** en **geblokkeerde overschreven**, en klik vervolgens op de knop **vernieuwen** die zich op dezelfde regel bevindt als de opties om dat filter toe te passen. (Vernieuw het browservenster niet.)

   > [!div class="mx-imgBorder"]
   > ![Url's en klik op Verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   Het rapport wordt vernieuwd om twee verschillende URL-tabellen weer te geven op het tabblad URL onder het rapport:

   - **Url's** voor de bovenkant zijn de url's in de berichten waarop u hebt gefilterd en de actie voor de bezorging van de e-mail telt voor elke URL. In de weergave phishing-e-mail bevat deze lijst meestal geldige Url's. Hackers bestaan uit een combinatie van goede en onjuiste Url's in hun berichten om te proberen ze te ontvangen, maar ze maken de kwaadwillende koppelingen interessanter voor de gebruiker. De tabel met Url's wordt gesorteerd op totaal aantal e-mailberichten (maar deze kolom is verborgen om de weergave te vereenvoudigen).

   - Met de rechter **muisknop zijn de** gewrappte url's voor de beveiligde koppelingen waarop u hebt geklikt, gesorteerd op totale aantal klikken (deze kolom wordt ook niet weergegeven om de weergave te vereenvoudigen). Het totaal aantal per kolom geeft de veilige koppelingen aan voor elke geklikt URL. In de weergave phishing-e-mail zijn deze vaak verdachte of schadelijke Url's, maar mogelijk ook Url's die geen bedreiging zijn maar wel in phishingberichten. URL-klikken op niet-vastgemaakte koppelingen worden hier niet weergegeven.

   De twee URL-tabellen bevatten Url's voor e-mailberichten op de bezorgings actie en de locatie van de geadresseerde, en de getoonde URL-geblokte (of een waarschuwing ondanks een waarschuwing), zodat u kunt zien welke onjuiste koppelingen zijn ontvangen door gebruikers en door gebruikers te gebruiken. U kunt hier verdere analyses uitvoeren. Onder de grafiek ziet u bijvoorbeeld de belangrijkste Url's in e-mailberichten die zijn geblokkeerd in de omgeving van uw organisatie.

   > [!div class="mx-imgBorder"]
   > ![Verkenner-Url's die zijn geblokkeerd](../../media/ExplorerPhishClickVerdictURLs.png)

   Selecteer een URL om meer gedetailleerde informatie weer te geven.

   > [!NOTE]
   > In het dialoogvenster URL-flyout worden de filters voor e-mailberichten verwijderd om de volledige weergave van de belichtings van de URL in uw omgeving te zien. Hiermee kunt u e-mailberichten in Explorer filteren, zodat u specifieke Url's kunt zoeken die potentiële bedreigingen zijn en vervolgens uw inzicht krijgen in de URL-belichting in uw omgeving (via het dialoogvenster URL-details) zonder dat u URL-filters hoeft toe te voegen aan de Verkenner-weergave.

### <a name="interpretation-of-different-click-verdicts"></a>Interpretatie van verschillende klikken op Verdicts

Binnen de E-mail-of URL-flyout, met de bovenste klikken en in onze filter ervaring, ziet u verschillende waarden als onderdeel van de jacht-ervaring. Hieronder ziet u de mogelijke waarden van klik Verdicts en de interpretatie ervan:

- **Geen**: de verdict voor de URL is niet vastgelegd. De gebruiker heeft mogelijk geklikt door de URL.
- **Toegestaan**: de gebruiker heeft toegestaan om naar de URL te navigeren.
- **Geblokkeerd**: de gebruiker is geblokkeerd om naar de URL te navigeren.
- **In behandeling verdict**: de gebruiker heeft weergegeven met de pagina detonatie in behandeling.
- **Geblokkeerde overschreven**: de gebruiker is geblokkeerd en navigeert niet naar de URL. de gebruiker overrode het blok echter om naar de URL te gaan.
- **Verdict in behandeling**: de gebruiker heeft weergegeven met de detonatie pagina. de gebruiker overrode echter de pagina om naar de URL te navigeren.
- **Fout**: de gebruiker heeft de foutpagina weergegeven. Dit kan ook betekenen dat er een fout is opgetreden bij het vastleggen van de Verdict.
- **Fout**: er is een onbekende uitzondering opgetreden tijdens het vastleggen van de Verdict. De gebruiker heeft mogelijk geklikt door de URL.

## <a name="review-email-messages-reported-by-users"></a>Door gebruikers verzonden e-mailberichten bekijken

Stel dat u e-mailberichten wilt zien die gebruikers in uw organisatie als ongewenste E-mail hebben gerapporteerd, geen ongewenste E-mail of phishing via de [invoegtoepassing bericht rapporteren voor Outlook en de webversie van Outlook](enable-the-report-message-add-in.md). Als u dit wilt doen, gebruikt u de bewerkingsweergave voor [e-mail > ingediend](threat-explorer-views.md#email--submissions) van Explorer (of realtime-detecties).

1. Kies in het beveiligings & conformiteitscentrum ( [https://protection.office.com](https://protection.office.com) ) de optie **Threat Management**  >  **Explorer** (of **realtime-detectie**). (In dit voorbeeld wordt Explorer gebruikt.)

2. Kies in het menu **weergave** de optie **e-mail**  >  **inzendingen**.

   > [!div class="mx-imgBorder"]
   > ![Menu weergeven voor Explorer voor e-mailberichten](../../media/explorer-view-menu-email-user-reported.png)

3. Klik op **afzender** en kies type **basis**  >  **rapport**.

4. Selecteer een optie, zoals **phishing**, en klik vervolgens op de knop **vernieuwen** .

   > [!div class="mx-imgBorder"]
   > ![Door de gebruiker gerapporteerde phishing](../../media/EmailUserReportedReportType.png)

Het rapport wordt vernieuwd om gegevens weer te geven over e-mailberichten die gebruikers in uw organisatie hebben gerapporteerd als een phishing-poging. U kunt deze gegevens gebruiken om verdere analyse uit te voeren en uw [anti-phishing te wijzigen in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md).

## <a name="start-automated-investigation-and-response"></a>Automatisch onderzoek en antwoord starten

> [!NOTE]
> De mogelijkheden voor automatisch onderzoek en antwoord zijn beschikbaar in **Microsoft Defender voor Office 365, abonnement 2** en **Office 365 E5**.

(Nieuw!) Met [geautomatiseerd onderzoek en reactie](automated-investigation-response-office.md) kunnen uw beveiligingsactiviteiten team veel tijd in beslag houden en te zorgen voor een onderzoek en beperking van cyberattacks. U kunt niet alleen waarschuwingen configureren die een beveiligings Playbook, maar u kunt wel een automatisch onderzoek en antwoord proces starten vanuit een weergave in Explorer.

Zie voor meer informatie [: een beveiligingsbeheerder activeert een onderzoek vanuit Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>Meer manieren om Explorer te gebruiken (of realtime-detecties)

Naast de scenario's die in dit artikel worden beschreven, hebt u veel meer opties voor het rapporteren van de Verkenner (of realtime-detectie).

- [Schadelijke e-mailberichten zoeken en onderzoeken die zijn afgeleverd](investigate-malicious-email-that-was-delivered.md)
- [Schadelijke bestanden weergeven die zijn gevonden in SharePoint Online, OneDrive en Microsoft teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Een overzicht van de weergaven in het bedreigings Verkenner-object (en realtime-detectie)](threat-explorer-views.md)
- [Statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)
- [Geautomatiseerd onderzoek en antwoord in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>Vereiste licenties en machtigingen

U moet beschikken over [Microsoft Defender voor Office 365](office-365-atp.md) om Explorer of realtime-detectie te kunnen krijgen.

- Explorer maakt deel uit van de werkruimte voor Office 365, abonnement 2.
- Het rapport realtime detectie is opgenomen in de lijst met Defender voor Office 365, abonnement 1.
- Het toewijzen van licenties aan alle gebruikers die moeten worden beveiligd door Defender voor Office 365. (Verkenner of realtime-detectie laat detectiegegevens zien voor gebruikers met een licentie.)

Als u Verkenner of realtime-detectie wilt weergeven en gebruiken, moet u de juiste machtigingen hebben, zoals de machtigingen die zijn toegewezen aan een beveiligingsbeheerder of beveiligings lezer.

- Voor het beveiligings & nalevings centrum moet een van de volgende rollen zijn toegewezen:

  - Organisatiebeheer
  - Beveiligingsbeheerder (deze kan worden toegewezen in het Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))
  - Beveiligings lezer

- Voor Exchange Online moet u beschikken over een van de volgende rollen die zijn toegewezen in het Exchange-Beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) of met PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):

  - Organisatiebeheer
  - Organisatiebeheer alleen weergeven
  - Rollen View-Only geadresseerden
  - Nalevings beheer

Zie de volgende bronnen voor meer informatie over rollen en machtigingen:

- [Machtigingen in het Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md)
- [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a>Enkele verschillen tussen de bedreigings Verkenner en de real-time detectie

- Het rapport **realtime-detecties** is beschikbaar in de Defender for Office 365-abonnement 1, terwijl de **bedreigings Verkenner** beschikbaar is in de Defender for Office 365-abonnement 2.
- Met het rapport **realtime detectie** kunt u detecties in realtime weergeven. U kunt dit ook doen met **risico Verkenner** , maar u kunt ook aanvullende Details voor een bepaalde aanval weergeven.
- De weergave **alle e-mail** is beschikbaar in de **Threat Explorer** (en komt niet voor in het rapport **realtime detectie** ).
- U vindt meer filterfuncties en de beschikbare acties in de **Threat Explorer**.

Zie voor meer informatie [Microsoft Defender for Office 365 Service Description: beschikbaarheid van functies in office 365-abonnementen](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).
