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
description: Gebruik Verkenner en real-time detectie van het beveiligings &amp; conformiteitscentrum om bedreigingen efficiënt te onderzoeken en te beantwoorden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8bca8e39029fe041c0bab59e92d8a653647746ef
ms.sourcegitcommit: 0ecac0387be6b49025b79ce8eb949a8cf62481e2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/21/2020
ms.locfileid: "49724412"
---
# <a name="threat-explorer-and-real-time-detections"></a>Bedreigings Verkenner en real-time ontdekken

Als uw organisatie [Microsoft Defender voor Office 365](office-365-atp.md) heeft en u de [benodigde machtigingen](#required-licenses-and-permissions)hebt, hebt u toegang *tot Explorer* of *realtime-detecties*, die eerder *realtime rapporten* hadden. ([Zie wat is er nieuw.](#new-features-in-threat-explorer-and-real-time-detections)) Ga in het beveiligings & compliance naar **Threat Management** en selecteer vervolgens **Verkenner** _of_ **detectie** van de realtime.

|Met Microsoft Defender voor Office 365 abonnement 2 ziet u het volgende:|Met Microsoft Defender voor Office 365 abonnement 1 ziet u het volgende:|
|---|---|
|![Bedreigings Verkenner](../../media/threatmgmt-explorer.png)|![Detecties in realtime](../../media/threatmgmt-realtimedetections.png)|
|

Met behulp van de Verkenner of realtime-detectie kunnen uw beveiligingsactiviteiten team op efficiënte wijze onderzoeken en reageren op bedreigingen. Het rapport is vergelijkbaar met de volgende afbeelding:

![Ga naar Threat Management \> Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Met dit rapport kunt u:

- [Zie malware die door Microsoft 365 beveiligingsfuncties is gedetecteerd.](#see-malware-detected-in-email-by-technology)
- [Bekijk de phishing-URL en klik op Verdict data.](#view-phishing-url-and-click-verdict-data)
- [Een automatisch onderzoek en antwoord proces starten vanuit een weergave in Verkenner](#start-automated-investigation-and-response) (alleen voor Office 365, abonnement 2)
- [Onderzoek kwaadaardige e-mail en meer](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-explorer-and-real-time-detections"></a>Verbeteringen in de bedreigings Verkenner en de real-time detectie

### <a name="tags-in-threat-explorer"></a>Labels in de Threat Explorer

> [!NOTE]
> De functie gebruikers Tags is in *voorbeeld*, is niet beschikbaar voor iedereen, en kan veranderen. Voor informatie over de release planning raadpleegt u het Microsoft 365-wegwijzer.

Gebruikers Tags identificeren specifieke groepen gebruikers in Microsoft Defender voor Office 365. Zie voor meer informatie over tags, waaronder licentieverlening en configuratie, [gebruikers Tags](user-tags.md).

In de bedreigings Verkenner kunt u informatie weergeven over gebruikers Tags in de volgende toepassingen.

#### <a name="email-grid-view"></a>Weergave van e-mail raster

De kolom **Tags** in het raster e-mail bevat alle labels die zijn toegepast op de postvakken van de afzender of geadresseerde. Standaard worden in systeem Tags zoals prioritaire accounts eerst weergegeven.

> [!div class="mx-imgBorder"]
> ![Labels filteren in de weergave e-mail raster](../../media/tags-grid.png)

#### <a name="filtering"></a>Bewerkingen

U kunt labels gebruiken als filter. Alles over prioriteits accounts of specifieke scenario's voor gebruikers Tags. U kunt ook resultaten met bepaalde Tags uitsluiten. Deze functionaliteit combineren met andere filters om uw onderzoek te beperken.

[![Labels filteren](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Geen labels filteren](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>Flyout e-mail Details
Als u de afzonderlijke labels voor afzender en geadresseerde wilt weergeven, selecteert u het onderwerp voor het openen van het flyout met de berichtdetails. Op het tabblad **Samenvatting** worden de tags voor de afzender en de geadresseerden apart weergegeven, als ze aanwezig zijn voor een e-mailbericht.
De informatie over de afzonderlijke Tags voor de afzender en de geadresseerde wordt ook uitgebreid naar geëxporteerde CSV-gegevens, waar u deze details in twee afzonderlijke kolommen kunt zien.

> [!div class="mx-imgBorder"]
> ![Tags voor e-mail gegevens](../../media/tags-flyout.png)

De code gegevens worden ook weergegeven in de vervolgmenu URL-klikken. Als u de afbeelding wilt weergeven, gaat u naar de weergave phishing of alle E-mail en gaat u naar het tabblad **url's of Url's** **op** de tabtoets. Selecteer een afzonderlijke URL-flyout voor het weergeven van extra details over de klikken voor de URL, inclusief labels die zijn gekoppeld aan die klik.

> [!div class="mx-imgBorder"]
> ![URL-Tags](../../media/tags-urls.png)

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a>Verbeteringen in de ervaring voor de beleving van de bedreiging (binnenkort)

### <a name="updated-threat-information-for-emails"></a>Update van bedreigings informatie voor e-mailberichten

De verbeteringen van platform en gegevenskwaliteit zijn gefocust om gegevens nauwkeuriger en consistentie van e-mail records te verbeteren. Dit omvat verbeteringen voor de consolidatie van pre-leveringsinformatie, zoals acties die op een e-mail als onderdeel van het ZAP-proces zijn uitgevoerd, tot één record. Aanvullende informatie zoals spam Verdict, op het niveau van bedreigingen op het niveau van de persoon (bijvoorbeeld de URL is schadelijk), en de nieuwste bezorgingslocaties worden ook opgenomen.

Na deze updates ziet u één vermelding voor elk bericht, ongeacht de verschillende gebeurtenissen na de bezorging die van invloed zijn op het bericht. U kunt ook ZAP, handmatig herstel (dat wil zeggen beheerdersactie), dynamische bezorging, enzovoort opnemen.

Naast malware en phishingwebsites, ziet u het spam verdict dat is gekoppeld aan een e-mailbericht. Bekijk in het e-mailbericht alle bedreigingen die bij de e-mail horen en de bijbehorende detectie technologieën. Een e-mailbericht kan nul, een of meerdere bedreigingen hebben. In het gedeelte **Details** van de e-mail flyout ziet u de huidige bedreigingen. Voor meerdere bedreigingen (zoals malware en phishing) bevat het veld **Detection tech** de toewijzing van de bedreiging voor de bedreiging.

De set detectie technologieën omvat nu nieuwe detectiemethoden en technologieën voor spam detectie. U kunt dezelfde set detectie technologieën gebruiken om de resultaten in de verschillende e-mail weergaven te filteren (malware, phishing, alle E-mail).

> [!NOTE]
> Verdict-analyse kan niet noodzakelijkerwijs aan entiteiten zijn gebonden. Voorbeeld: een e-mailbericht kan als phishing of spam worden geclassificeerd, maar er zijn geen Url's die zijn voorzien van een phishing-of spam Verdict. Dit komt doordat de filters de inhoud en andere details van een e-mailbericht controleren voordat ze een verdict toewijzen.

#### <a name="threats-in-urls"></a>Bedreigingen in Url's

U kunt nu de specifieke bedreiging voor een URL weergeven op het tabblad **Details** van e-mail flyout. De bedreiging kan *malware*, *phishing*, *spam* of *geen* zijn.

> [!div class="mx-imgBorder"]
> ![URL-bedreigingen](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a>Bijgewerkte tijdlijnweergave (binnenkort)

> [!div class="mx-imgBorder"]
> ![Bijgewerkte tijdlijnweergave](../../media/Email_Timeline.png)

De tijdlijnweergave identificeert alle aflevering en gebeurtenissen die na aflevering plaatsvinden. Dit omvat informatie over de bedreiging die op dat moment wordt aangegeven voor een subset van deze gebeurtenissen. De tijdlijnweergave bevat ook informatie over eventuele extra acties (zoals ZAP of handmatig herstel), samen met het resultaat van die actie. De tijdlijnweergave informatie omvat:

- **Bron:** Bron van de gebeurtenis. Dit kan beheerder/systeem/gebruiker zijn.
- **Gebeurtenis:** Bevat gebeurtenissen op het hoogste niveau zoals oorspronkelijke levering, handmatig herbemiddeling, ZAP, inzendingen en dynamische bezorging.
- **Actie:** De specifieke actie die is uitgevoerd als onderdeel van ZAP-of beheerdersactie (bijvoorbeeld soft delete).
- **Bedreigingen:** Behandelt de bedreigingen (malware, phishing en spam) die op dat moment identificeren.
- **Resultaat/informatie:** Meer informatie over het resultaat van de actie, zoals of de actie is uitgevoerd als onderdeel van de actie ZAP/beheerder.

### <a name="original-and-latest-delivery-location"></a>Oorspronkelijke en meest recente bezorgingslocatie

Op dit moment bezorgt de bezorgingslocatie in het raster en de e-mail flyout van de e-mail. De naam van het veld **bezorgingslocatie** krijgt de naam **_oorspronkelijke bezorgingslocatie_* _. We introduceren een ander veld, namelijk de _*_nieuwste bezorgingslocatie_*_.

Met de *oorspronkelijke bezorgingslocatie** krijgt u meer informatie over waar een e-mail aanvankelijk is bezorgd. Met de **nieuwste bezorgingslocatie** wordt de plaats weergegeven van een e-mailbericht na systeemacties, zoals *ZAP* -of beheeracties, zoals *verplaatsen naar verwijderde items*. Nieuwste bezorgingslocatie is bedoeld om beheerders te informeren over de laatste bekende locatie na de bezorging van het bericht of van systeem/beheeracties. Dit omvat geen activiteiten voor eindgebruikers in het e-mailbericht. Als een gebruiker bijvoorbeeld een bericht heeft verwijderd of het bericht naar archief-of PST-bestand verplaatst, wordt het bericht ' bezorgingslocatie ' niet bijgewerkt. Maar als een systeemactie de locatie heeft bijgewerkt (bijvoorbeeld ZAP die het verplaatsen van een e-mailbericht naar Quarantine verloopt), wordt de **nieuwste bezorgingslocatie** weergegeven als ' Quarantine '.

> [!div class="mx-imgBorder"]
> ![Bijgewerkte bezorgingslocaties](../../media/Updated_Delivery_Location.png)

> [!NOTE]
> In sommige gevallen wordt de **bezorgingslocatie** en de **bezorgings actie** weergegeven als ' onbekend '.
>
> - U ziet mogelijk de **bezorgingslocatie** als ' afgeleverd ' en locatie van de **levering** als het bericht is bezorgd, maar met een regel voor Postvak in verplaatst u het bericht naar een standaard map (zoals concept of archief) in plaats van naar het postvak in of de map Ongewenste e-mail.
>
> - De **meest recente bezorgingslocatie** kan onbekend zijn als een beheerder/systeemactie (zoals ZAP) is geprobeerd, maar het bericht niet is gevonden. Meestal gebeurt de actie wanneer de gebruiker het bericht heeft verplaatst of verwijderd. In dergelijke gevallen controleert u de kolom **resultaat/Details** in de tijdlijnweergave. Zoek naar het bericht dat door de gebruiker is verplaatst of verwijderd.

> [!div class="mx-imgBorder"]
> ![Bezorgingslocaties voor tijdlijn](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a>Aanvullende acties

*Aanvullende acties* zijn toegepast na levering van de e-mail. Ze kunnen *ZAP*, *handmatig herstel* (actie die worden uitgevoerd door een beheerder zoals een tijdelijke verwijdering), *dynamische bezorging* en opnieuw *verwerkte* (voor een e-mailbericht dat met een werkgroep met een werknemer op de juiste manier is gedetecteerd).

> [!NOTE]
> - Als onderdeel van de in behandeling zijnde wijzigingen wordt de waarde ' verwijderd door ZAP ' op dit moment weergegeven in het filter voor bezorgings actie. U kunt ook zoeken naar alle e-mailberichten met de ZAP-poging via **extra acties**.
>
> - Er worden nieuwe velden en waarden weergegeven voor **detectie technologieën** en **extra acties** (met name voor Zap-scenario's). U moet uw bestaande opgeslagen query's en bijgehouden query's evalueren om ervoor te zorgen dat ze met de nieuwe waarden werken.

> [!div class="mx-imgBorder"]

> ![Aanvullende acties in Verkenner](../../media/Additional_Actions.png)

### <a name="system-overrides"></a>Systeem overschrijvingen

Door *systeem overschrijvingen* kunt u uitzonderingen instellen voor de bedoelde bezorgingslocatie van een bericht. U overschrijft de bezorgingslocatie van het systeem, op basis van de bedreigingen en andere detecties die worden geïdentificeerd door de filterstack. Door systeem overschrijvingen kan worden ingesteld via Tenant of gebruikersbeleid om het bericht op te geven dat door het beleid wordt voorgesteld. Door overschrijvingen kan kwaadaardige berichten niet worden bezorgd door de configuraties van een beheerder, zoals een algemeen beleid voor het veilig afleveren van een gebruiker dat door een gebruiker is ingesteld. Deze opheffings waarden kunnen zijn:

- Toegestaan door gebruikersbeleid: een gebruiker maakt beleidsregels op het niveau van het Postvak om domeinen of afzenders toe te staan.
- Geblokkeerd door gebruikersbeleid: een gebruiker maakt beleidsregels op het niveau van het Postvak om domeinen of afzenders te blokkeren.
- Toegestaan per organisatiebeleid: de beveiligings teams voor de organisatie stellen beleidsregels voor de beheerder of Exchange-e-mail stroom (ook wel transport-regels genoemd) voor het toestaan van afzenders en domeinen voor gebruikers in hun organisatie. Dit kan bestaan voor een set gebruikers of de hele organisatie.
- Geblokkeerd door het beleid voor de organisatie: de beveiligings teams van de organisatie stellen beleidsregels of de regels voor de e-mail stroom in voor het blokkeren van afzenders, domeinen, berichten talen of bron-Ip's voor gebruikers in hun organisatie. Dit kan worden toegepast op een set gebruikers of de hele organisatie.
- Bestandsextensie wordt geblokkeerd door het organisatiebeleid: het beveiligingsteam van een organisatie blokkeert een extensie voor bestandsnamen via de beleidsinstellingen voor anti malware. Deze waarden worden nu weergegeven in e-mail gegevens om onderzoek te doen. Secops teams kunnen ook gebruikmaken van de mogelijkheden voor uitgebreid filteren om de geblokkeerde bestandsextensies te filteren.

[![Systeem overschrijvingen in Explorer](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Raster overschrijvingen in Explorer](../../media/System_Overrides_Grid.png)

### <a name="improvements-for-the-url-and-clicks-experience"></a>Verbeteringen voor de URL en klikken op de ervaring

De verbeteringen zijn:

- Geef de volledig geklikt URL weer (inclusief eventuele queryparameters die deel uitmaken van de URL) in de sectie **klikken** van de URL-flyout. Op dit moment worden de URL-domeinen en paden weergegeven op de titelbalk. We verlengen deze informatie om de volledige URL weer te geven.

- Oplossingen voor URL-filters (*URL* versus URL- *domein* *en URL Domain en Path*): de updates beïnvloeden het zoeken naar berichten die een URL bevatten/Klik op Verdict. We hebben ondersteuning ingeschakeld voor protocol-agnostic-zoekopdrachten, zodat u kunt zoeken naar een URL zonder deze te gebruiken `http` . Standaard wordt via URL'S gezocht naar http, tenzij een andere waarde expliciet is opgegeven. Bijvoorbeeld:

   -  Zoek met en zonder het `http://` voorvoegsel in de **url's** domein-, **URL-domein** en URL- **domein en** -filtervelden. De zoekopdrachten moeten dezelfde resultaten weergeven.

   -  Zoek het `https://` voorvoegsel in **URL**. Wanneer er geen waarde is opgegeven, `http://` wordt uitgegaan van het voorvoegsel.

   - `/` wordt genegeerd aan het begin en einde van het **URL-pad**, **URL-domein**, URL- **domein en padgegevens** . `/` aan het einde van het **URL** -veld wordt genegeerd.

### <a name="phish-confidence-level"></a>Betrouwbaarheidsniveau voor phishing

Met betrouwbaarheid van phishing kunt u het vertrouwensniveau identificeren waarmee een e-mailbericht als phishing werd gecategoriseerd. De twee mogelijke waarden zijn *hoog* en *normaal*. In de eerste fase is dit filter alleen beschikbaar in de weergave phishing van de Threat Explorer.

[![Betrouwbaarheidsniveau voor phishing in Explorer](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>ZAP-URL-signaal

Het-signaal van de ZAP-URL wordt meestal gebruikt voor scenario's van een zap-aanval waarbij een e-mailbericht als phishing is geïdentificeerd en na levering is verwijderd. Dit signaal verbindt de waarschuwing met de overeenkomstige resultaten in de Verkenner. Dat is een van de IOCs voor de melding.

Om de jacht te verbeteren, hebben we de bedreigings Verkenner en de real-time detectie functies bijgewerkt om de jacht-ervaring consistenter te maken. De wijzigingen worden hier beschreven:

- [Tijdzone verbeteringen](#timezone-improvements)
- [Bijwerken in het vernieuwingsproces](#update-in-the-refresh-process)
- [DrillDown voor de grafiek om toe te voegen aan filters](#chart-drilldown-to-add-to-filters)
- [Updates voor productgegevens](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>Filteren op gebruikers Tags

U kunt nu sorteren en filteren op systeem of aangepaste gebruikers Tags om snel de reikwijdte van bedreigingen te begrijpt. Zie voor meer informatie [gebruikers Tags](user-tags.md).

> [!IMPORTANT]
> Filteren en sorteren op gebruikerscodes bevindt zich momenteel in de openbare preview-versie. Deze functie kan ingrijpend worden gewijzigd voordat deze commercieel wordt uitgebracht. Microsoft verbiedt geen garanties, uitdrukkelijke of impliciete informatie met betrekking tot de verstrekte informatie.

![Kolom Tags in Verkenner](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a>Tijdzone verbeteringen

U ziet de tijdzone voor de e-mail records in de portal en voor de geëxporteerde gegevens. De site is zichtbaar in de ervaring, zoals e-mail raster, Details flyout, e-mail tijdlijn en soortgelijke E-mails, zodat de tijdzone voor de resultatenset duidelijk is.

> [!div class="mx-imgBorder"]
> ![Tijdzone weergeven in Verkenner](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>Bijwerken in het vernieuwingsproces

Sommige gebruikers hebben een opmerking over verwarring met automatisch vernieuwen (zodra u de datum wijzigt, wordt de pagina vernieuwd) en handmatig vernieuwen (voor andere filters). Op dezelfde manier verwijdert filters potentiële klanten naar automatisch vernieuwen. Het wijzigen van filters tijdens het wijzigen van de query kan leiden tot inconsistente zoekfuncties. Om deze problemen op te lossen, gaan we overstappen op een handmatig filtermechanisme.

Vanuit het oogpunt van de ervaring kan de gebruiker een verschillend bereik van filters toepassen en verwijderen (uit de Filterset en datum) en selecteert u de knop Vernieuwen om de resultaten te filteren nadat deze de query heeft gedefinieerd. De knop Vernieuwen wordt nu ook op het scherm benadrukt. We hebben ook de verwante knopinfo en de documentatie voor de producten bijgewerkt.

> [!div class="mx-imgBorder"]
> ![Selecteer vernieuwen om resultaten te filteren](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>DrillDown voor de grafiek om toe te voegen aan filters

U kunt nu waarden voor de legenda van een grafiek toevoegen om deze als filters toe te voegen. Selecteer de knop **vernieuwen** om de resultaten te filteren.

> [!div class="mx-imgBorder"]
> ![Inzoomen op grafieken om te filteren](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>Updates voor productinformatie

Aanvullende gegevens zijn nu beschikbaar in het product, zoals het totale aantal zoekresultaten in het raster (zie hieronder). We hebben labels, foutberichten en Scherminfo verbeterd om meer informatie te geven over de filters, de zoekervaring en de resultatenset.

> [!div class="mx-imgBorder"]
> ![Informatie over het product weergeven](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>Uitgebreide mogelijkheden in de bedreigings Verkenner

### <a name="top-targeted-users"></a>Belangrijkste gerichte gebruikers

De lijst met de belangrijkste gebruikers wordt nu weergegeven in de malware-weergave voor e-mailberichten in de sectie **populaire families van malware** . Deze weergave wordt ook uitgebreid met de begeleide E-mail en alle e-mail weergaven. U kunt de vijf belangrijkste doelgebruikers zien, samen met het aantal pogingen voor elke gebruiker voor de bijbehorende weergave. Voor de phishing-weergave ziet u bijvoorbeeld het aantal phishing-pogingen.

U kunt de lijst met gerichte gebruikers, een limiet van 3.000, samen met het aantal pogingen tot offline analyses voor elke e-mail weergave exporteren. Daarnaast wordt in het geval van een gefilterde weergave in de bedreigings Verkenner een gefilterde weergave in het deelvenster bedreiging weergegeven, zodat u meer Details voor e-mailberichten en bedreigingen voor die gebruiker kunt zien.

> [!div class="mx-imgBorder"]
> ![Belangrijkste gerichte gebruikers](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>Exchange-transportregels

Als onderdeel van gegevens verrijking ziet u alle verschillende Exchange-transportregels (ETR toe) die zijn toegepast op een bericht. Deze informatie is beschikbaar in de weergave voor de e-mail raster. Als u de tabel wilt weergeven, selecteert u **kolom opties** in het raster en voegt u vervolgens een **Exchange-Transport regel toe** via de kolom opties. De app wordt ook weergegeven in het vervolgmenu **Details** van de e-mail.

U kunt zowel de GUID als de naam van de transportregels zien die zijn toegepast op het bericht. U kunt de berichten zoeken met behulp van de naam van de transportregel. Dit is een ' bevat ' zoeken, wat betekent dat u ook gedeeltelijke zoekopdrachten kunt uitvoeren.

#### <a name="important-note"></a>Belangrijke opmerking:

De beschikbaarheid van zoeken en beschikbaarheid van ETR toe is afhankelijk van de specifieke rol die aan u is toegewezen. U moet beschikken over een van de volgende rollen/machtigingen om de namen en zoekopdrachten van ETR toe te kunnen bekijken. Als u geen van deze rollen aan u hebt toegewezen, kunt u niet de namen van de transportregels zien of berichten zoeken met behulp van ETR toe namen. U kunt echter de ETR toe-label en GUID-informatie in de e-mail gegevens zien. Andere toepassingen voor het weergeven van een record in e-mail rasters, e-mail flyout, filters en exporteren worden niet beïnvloed.

- Alleen EXO-preventie van gegevensverlies: alles
- Alleen EXO: O365SupportViewConfig: all
- Microsoft Azure Active Directory of EXO-beveiligingsbeheerder: alle
- AAD of EXO-beveiligings lezer: alles
- Alleen EXO-transport regels: alle
- EXO only-View-Only configuratie: alle

In het raster, het detail menu van de e-mail en de geëxporteerde CSV-gegevens, worden de Etr's weergegeven met een naam/GUID zoals hieronder weergegeven.

> [!div class="mx-imgBorder"]
> ![Exchange-Transport regels](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>Binnenkomende connectors

Connectors zijn een verzameling instructies die bepalen hoe uw e-mailberichten overlopen van en naar de organisatie Microsoft 365 of Office 365. Hiermee kunt u beveiligingsbeperkingen of besturingselementen toepassen. U kunt nu in de Threat Explorer de connectors weergeven die zijn gerelateerd aan een e-mailbericht en zoeken naar e-mailberichten met behulp van connector namen.

De zoekfunctie van connectors is "bevat", wat betekent dat er ook ook zoekopdrachten naar trefwoorden werken. In de hoofdweergave, het detail menu en de geëxporteerde CSV-mappen, worden de connectors weergegeven in de indeling naam/GUID, zoals hier wordt weergegeven:

> [!div class="mx-imgBorder"]
> ![Details van connector](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nieuwe functies in de bedreigings Verkenner en de real-time detectie

Er zijn drie nieuwe functies beschikbaar in de Threat Explorer en gedetecteerde realtime-detecties:

- [Voorbeeld van e-mailkop tekst](#preview-email-header-and-download-email-body)
- [E-mail tijdlijn](#email-timeline)
- [URL exporteren Klik op gegevens](#export-url-click-data)

Hieronder ziet u een overzicht van de nieuwe functies.

### <a name="preview-email-header-and-download-email-body"></a>Voorbeeld van e-mailkop tekst

U kunt nu een voorbeeld van een e-mailbericht bekijken en het e-mailbericht in de secties van bedreiging Verkenner downloaden om gedownloade berichtkoppen/e-mailberichten te analyseren. Aangezien het downloaden van e-mailberichten kan worden blootgesteld aan informatie, wordt dit proces bepaald op basis van toegangsbeheer op basis van rollen. Een nieuwe rol, *Preview*, moet worden toegevoegd aan een andere rolgroep (zoals beveiligingsactiviteiten of beveiligingsbeheerder) om de mogelijkheid om e-mailberichten te downloaden en voorbeelden van kopteksten weer te geven in de weergave alle e-mailberichten.

In de Verkenner en de realtime-detectie worden ook nieuwe velden weergegeven met een uitgebreide afbeelding van de locatie waar uw e-mailberichten terechtkomen. Met deze wijzigingen kunt u de jacht eenvoudiger maken voor beveiliging OPS. Het belangrijkste resultaat is dat u in één oogopslag de locatie van e-mailberichten voor problemen kent.

Hoe is dit gebeurd? De bezorgingsstatus is nu uitgebroken in twee kolommen:

- **Bezorgings actie** -status van de e-mail.
- De **bezorgingslocatie** : de e-mail waarnaar de e-mail is doorgestuurd.

De *bezorgings actie* is de actie die op een e-mail is uitgevoerd vanwege bestaande beleidsregels of detecties. Dit zijn de mogelijke acties voor een e-mailbericht:

|Aflevering|Ongewenst|Blokkeert|Gekomen|
|---|---|---|---|
|E-mail is bezorgd in het postvak in of de map van een gebruiker, en de gebruiker kan deze openen.|E-mail is verzonden naar de map Ongewenste E-mail of verwijderde map van de gebruiker en de gebruiker kan deze openen.|E-mailberichten die zijn gequarantined, die niet zijn gelukt of zijn verwijderd. Deze e-mailberichten zijn niet toegankelijk voor de gebruiker.|E-mail bevat schadelijke bijlagen vervangen door txt-bestanden waarmee de bijlage werd gemanipuleerd.|

Hier ziet u wat de gebruiker wel en niet kan zien:

|Toegankelijk voor eindgebruikers|Niet toegankelijk voor eindgebruikers|
|---|---|
|Aflevering|Blokkeert|
|Ongewenst|Gekomen|

**Locatie van levering** toont de resultaten van beleidsregels en detecties die na levering worden uitgevoerd. De *_bezorgings actie is gekoppeld aan * bezorgings actie_* _. Dit zijn de mogelijke waarden:

- _Inbox of map *: het e-mailbericht bevindt zich in het postvak in of een map (volgens uw e-mail regels).
- *On-premises of extern*: het postvak bestaat niet in de Cloud, maar is on-premises.
- *Map Ongewenste e-mail*: de e-mail bevindt zich in de map Ongewenste e-mail van een gebruiker.
- *Map Verwijderde items*: het e-mailbericht in de map Verwijderde items van een gebruiker.
- *Quarantaine*: het e-mailbericht is in quarantaine geplaatst en niet in het postvak van een gebruiker.
- *Mislukt*: het e-mailadres is niet bereikbaar voor het postvak.
- *Neergezet*: de e-mail is ergens in de e-mail stroom kwijt.

### <a name="email-timeline"></a>E-mail tijdlijn

De **e-mail tijdlijn** is een nieuwe functie in Excel die de ervaring met de jacht van beheerders verbetert. De tijd die wordt besteed aan het controleren op verschillende locaties om de gebeurtenis te begrijpen. Wanneer er meerdere gebeurtenissen plaatsvinden op of bij het sluiten van een e-mailbericht, worden deze gebeurtenissen weergegeven in een tijdlijnweergave. Sommige gebeurtenissen die zich voordoen voor uw e-mailbericht bezorging, worden vastgelegd in de kolom **speciale actie** . Beheerders kunnen informatie van de tijdlijn combineren met de speciale actie die is ondernomen voor de bezorging van de e-mail om inzicht te krijgen in de manier waarop hun beleidsregels werken, waarbij de e-mail uiteindelijk is gerouteerd, en in sommige gevallen, wat de uiteindelijke beoordeling was.

Zie voor meer informatie [kwaadwillende e-mailberichten onderzoeken en herstellen die zijn bezorgd in Office 365](investigate-malicious-email-that-was-delivered.md).

### <a name="export-url-click-data"></a>URL exporteren Klik op gegevens

U kunt nu rapporten voor URL-klikken exporteren naar Microsoft Excel, zodat u de **netwerk-id** van de e-mail kunt weergeven en **klikt u op Verdict** Dit werkt als volgt: Ga in Threat Management op de werkbalk Snel starten van Office 365 als volgt te werk:

**Verkenner** \> **Phishing** \> weergeven **Klikken op** \> **Belangrijkste url's** of **URL-klikken** \> Selecteer een record om de URL-flyout te openen.

Wanneer u een URL selecteert in de lijst, ziet u in het deelvenster uitvullen een nieuwe knop **exporteren** . Gebruik deze knop om gegevens te verplaatsen naar een Excel-spreadsheet, zodat u deze eenvoudiger kunt rapporteren.

Volg dit pad om naar dezelfde locatie te gaan in het rapport realtime detectie:

**Verkenner** \> **Detectie** \> van realtime **Phishing** \> weergeven **Url's** \> **Belangrijkste url's** of **bovenste klikken** \> Selecteer een record om de URL-flyout te openen en naar \> het tabblad **klikken** te gaan.

> [!TIP]
> De netwerkbericht-ID koppelt de Klik op terug naar specifieke e-mailberichten wanneer u met de ID of met de hulpmiddelen van een derde partij zoekt. Met deze zoekopdrachten wordt gezocht naar het e-mailadres dat is gekoppeld aan een klik resultaat. Wanneer u de bericht-ID van de gecorreleerde netwerkverbinding hebt, kunt u snellere en krachtige analyses uitvoeren.

> [!div class="mx-imgBorder"]
> ![Klikken op tab in Verkenner](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Malware van de malware van een e-mail weergeven

U wilt malware van de malware van Microsoft-365 zien. Als u dit wilt doen, gebruikt u de [e-mail >](threat-explorer-views.md#email--malware) weergave voor malware van Explorer (of realtime gedetecteerde).

1. Kies in het beveiligings & conformiteitscentrum ( <https://protection.office.com> ) de optie **Threat Management** \> **Explorer** (of **realtime-detectie**). (In dit voorbeeld wordt Explorer gebruikt.)

2. Kies in het menu **weergave** de optie **e-mail** \> **malware**.

   > [!div class="mx-imgBorder"]
   > ![Menu Beeld voor Verkenner](../../media/ExplorerViewEmailMalwareMenu.png)

3. Klik op **afzender** en kies vervolgens **Basic** \> **Detection Technology**.

   Uw detectie technologieën zijn nu beschikbaar als filters voor het rapport.

   > [!div class="mx-imgBorder"]
   > ![Detectie technologieën voor malware](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Kies een optie. Selecteer vervolgens de knop **vernieuwen** om het filter toe te passen.

   > [!div class="mx-imgBorder"]
   > ![Geselecteerde detectietechnologie](../../media/ExplorerEmailMalwareDetectionTechATP.png)

Het rapport wordt vernieuwd, zodat de resultaten worden weergegeven die met malware in een e-mail zijn gedetecteerd met behulp van de technologie optie die u hebt geselecteerd. U kunt hier verdere analyses uitvoeren.

## <a name="view-phishing-url-and-click-verdict-data"></a>Bekijk de phishing-URL en klik op Verdict data.

Stel dat u phishingberichten via Url's wilt weergeven in een e-mail, waaronder een lijst met Url's die zijn toegestaan, geblokkeerd en genegeerd. Als u Url's wilt identificeren waarop is geklikt, moet u [veilige koppelingen](atp-safe-links.md) configureren. Zorg ervoor dat u [beleidsregels voor veilige koppelingen](set-up-atp-safe-links-policies.md) instelt voor de bescherming van het tijdstip van de bescherming en logboekregistratie van de Klik op Verdicts via veilige koppelingen.

Als u de url's van de phishing in berichten wilt bekijken en op url's in phishingberichten wilt klikken, gebruikt u de [ **e-mail**  >  **phishing** -](threat-explorer-views.md#email--phish) weergave van de Verkenner of realtime-detecties.

1. Kies in het beveiligings & conformiteitscentrum ( <https://protection.office.com> ) de optie **Threat Management** \> **Explorer** (of **realtime-detectie**). (In dit voorbeeld wordt Explorer gebruikt.)

2. Kies in het menu **weergave** de optie **e-mail** \> **phishing**.

   > [!div class="mx-imgBorder"]
   > ![Het menu Beeld voor Explorer in de Phishingfilter-context](../../media/ExplorerViewEmailPhishMenu.png)

3. Klik op **afzender** en kies vervolgens **url's** \> **op Verdict**.

4. Selecteer een of meer opties, zoals **geblokkeerde** en **geblokkeerde overschreven**, en selecteer vervolgens de knop **vernieuwen** op dezelfde regel als de opties om dat filter toe te passen. (Vernieuw het browservenster niet.)

   > [!div class="mx-imgBorder"]
   > ![Url's en klik op Verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   Het rapport wordt vernieuwd om twee verschillende URL-tabellen weer te geven op het tabblad URL onder het rapport:

   - **Url's** voor de bovenkant zijn de url's in de berichten die u hebt gefilterd en de actie voor de bezorging van de e-mail wordt geteld voor elke URL. In de weergave phishing-e-mail bevat deze lijst meestal originele Url's. Hackers bestaan uit een combinatie van goede en onjuiste Url's in hun berichten om te proberen ze te ontvangen, maar ze maken de kwaadwillende koppelingen meer leuk. De tabel met Url's wordt gesorteerd op totaal aantal e-mailberichten, maar deze kolom is verborgen om de weergave te vereenvoudigen.

   - Met de rechtermuisknop **klikt** u op de pagina met de lijst met veilige koppelingen waarop u hebt geklikt, gesorteerd op aantal klikken. Deze kolom wordt ook niet weergegeven om de weergave te vereenvoudigen. Het totaal aantal per kolom geeft de veilige koppelingen aan voor elke geklikt URL. In de weergave malafide e-mail zijn dit meestal verdachte of schadelijke Url's. De weergave kan ook Url's bevatten die geen bedreigingen zijn maar wel in phishingberichten. URL-klikken op niet-vastgemaakte koppelingen worden hier niet weergegeven.

   De twee URL-tabellen bevatten Url's voor e-mailberichten met een afleverings actie en een locatie. In de tabellen staan de URL'S die zijn geblokkeerd of weergegeven, ondanks een waarschuwing, zodat u kunt zien welke onjuiste koppelingen zijn weergegeven aan gebruikers en waarop de gebruiker heeft geklikt. U kunt hier verdere analyses uitvoeren. Onder de grafiek ziet u bijvoorbeeld de belangrijkste Url's in e-mailberichten die zijn geblokkeerd in de omgeving van uw organisatie.

   > [!div class="mx-imgBorder"]
   > ![Verkenner-Url's die zijn geblokkeerd](../../media/ExplorerPhishClickVerdictURLs.png)

   Selecteer een URL om meer gedetailleerde informatie weer te geven.

   > [!NOTE]
   > In het dialoogvenster URL-flyout worden de filters voor e-mailberichten verwijderd om de volledige weergave van de belichtings van de URL in uw omgeving te tonen. Hiermee kunt u filteren op e-mailberichten in Explorer, zoeken naar specifieke Url's met mogelijke bedreigingen en breiden u inzicht te krijgen in de URL-belichting in uw omgeving (via het dialoogvenster URL-details) zonder dat u URL-filters hoeft toe te voegen aan de Verkenner-weergave.

### <a name="interpretation-of-click-verdicts"></a>Interpretatie van klikken op Verdicts

In de vervolgmenuanker voor E-mail of URL, met de bovenste klikken en in de filter ervaring, ziet u verschillende verdict-waarden:

- **Geen:** Kan de verdict voor de URL niet vastleggen. De gebruiker heeft mogelijk geklikt door de URL.
- **Toegestaan:** De gebruiker is gemachtigd om naar de URL te navigeren.
- **Geblokkeerd:** De gebruiker is geblokkeerd om naar de URL te navigeren.
- **In behandeling verdict:** De gebruiker is weergegeven op de pagina met detonatie in behandeling.
- **Geblokkeerde overschreven:** De gebruiker is geblokkeerd om rechtstreeks naar de URL te navigeren. Maar de gebruiker overrode het blok om naar de URL te navigeren.
- **In behandeling verdict overgeslagen:** De gebruiker is weergegeven met de pagina detonatie. Maar de gebruiker heeft het bericht overrode om toegang te krijgen tot de URL.
- **Fout:** De gebruiker is weergegeven op de foutpagina of er is een fout opgetreden bij het vastleggen van de Verdict.
- **Fout:** Er is een onbekende uitzondering opgetreden tijdens het vastleggen van de Verdict. De gebruiker heeft mogelijk geklikt door de URL.

## <a name="review-email-messages-reported-by-users"></a>Door gebruikers verzonden e-mailberichten bekijken

Stel dat u e-mailberichten wilt zien die gebruikers in uw organisatie als *ongewenste e-mail* hebben gerapporteerd, *geen ongewenste e-mail* of *phishing* via de [invoegtoepassing bericht rapporteren voor Outlook en de webversie van Outlook](enable-the-report-message-add-in.md). U kunt ze weergeven via de weergave voor het [ **Ontvangen van e-mail**  > ](threat-explorer-views.md#email--submissions) van Explorer (of realtime detectie).

1. Kies in het beveiligings & conformiteitscentrum ( <https://protection.office.com> ) de optie **Threat Management** \> **Explorer** (of **realtime-detectie**). (In dit voorbeeld wordt Explorer gebruikt.)

2. Kies in het menu **weergave** de optie **e-mail** \> **inzendingen**.

   > [!div class="mx-imgBorder"]
   > ![Menu weergeven voor Explorer voor e-mailberichten](../../media/explorer-view-menu-email-user-reported.png)

3. Klik op **afzender** en kies type **basis** \> **rapport**.

4. Selecteer een optie, zoals **phishing** en selecteer vervolgens de knop **Refresh** .

   > [!div class="mx-imgBorder"]
   > ![Door de gebruiker gerapporteerde phishing](../../media/EmailUserReportedReportType.png)

Het rapport wordt vernieuwd om gegevens weer te geven over e-mailberichten die deelnemers in uw organisatie als een phishing-poging hebben gerapporteerd. U kunt deze gegevens gebruiken om verdere analyse uit te voeren, en, indien nodig, uw [anti-phishings beleid in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md)aan te passen.

## <a name="start-automated-investigation-and-response"></a>Automatisch onderzoek en antwoord starten

> [!NOTE]
> De mogelijkheden voor automatisch onderzoek en antwoord zijn beschikbaar in *Microsoft Defender voor Office 365, abonnement 2* en *Office 365 E5*.

Met [geautomatiseerd onderzoek en reactie](automated-investigation-response-office.md) kunnen de tijd en de hoeveelheid werk die u hebt besteed aan het onderzoek en de Beperk van cyberattacks, worden opgeslagen. U kunt niet alleen waarschuwingen configureren die een beveiligings Playbook, maar u kunt wel een automatisch onderzoek en antwoord proces starten vanuit een weergave in Explorer. Zie voor meer informatie [: een beveiligingsbeheerder activeert een onderzoek van Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a>Meer manieren om de detectie van de Verkenner en de realtime-detectie te gebruiken

Naast de scenario's die in dit artikel worden beschreven, hebt u veel meer opties voor het rapporteren van de Verkenner (of realtime-detectie). Zie de volgende artikelen:

- [Schadelijke e-mailberichten zoeken en onderzoeken die zijn afgeleverd](investigate-malicious-email-that-was-delivered.md)
- [Schadelijke bestanden weergeven die zijn gevonden in SharePoint Online, OneDrive en Microsoft teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Een overzicht van de weergaven in het bedreigings Verkenner-object (en realtime-detectie)](threat-explorer-views.md)
- [Statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)
- [Geautomatiseerd onderzoek en antwoord in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>Vereiste licenties en machtigingen

U moet [Microsoft Defender voor Office 365](office-365-atp.md) hebben om Explorer of realtime-detecties te kunnen gebruiken.

- Explorer maakt deel uit van de werkruimte voor Office 365, abonnement 2.
- Het rapport realtime detectie is opgenomen in de lijst met Defender voor Office 365, abonnement 1.
- Het toewijzen van licenties aan alle gebruikers die moeten worden beveiligd door Defender voor Office 365. Detectiegegevens voor gebruikers met een licentie voor de Verkenner en de real-time detecteren.

Als u Verkenner of realtime-detectie wilt weergeven en gebruiken, moet u de juiste machtigingen hebben, zoals de machtigingen die zijn toegewezen aan een beveiligingsbeheerder of beveiligings lezer.

- Voor het beveiligings & nalevings centrum moet een van de volgende rollen zijn toegewezen:

  - Organisatiebeheer
  - Beveiligingsbeheerder (deze kan worden toegewezen in het Azure Active Directory-beheercentrum <https://aad.portal.azure.com>
  - Beveiligings lezer

- Voor Exchange Online moet u beschikken over een van de volgende rollen in het Exchange Admin Center ( <https://admin.protection.outlook.com/ecp/> ) of [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell):

  - Organisatiebeheer
  - View-Only Organisatiebeheer
  - Geadresseerden View-Only
  - Nalevings beheer

Zie de volgende bronnen voor meer informatie over rollen en machtigingen:

- [Machtigingen in het Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md)
- [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>Verschillen tussen de bedreigings Verkenner en de real-time detectie

- Het rapport *realtime detectie* is beschikbaar in de Defender voor Office 365-abonnement 1. De *Threat Explorer* is beschikbaar in de Defender for Office 365-abonnement 2.
- Met het rapport realtime detectie kunt u detecties in realtime weergeven. Dit is ook geschikt voor de dreiging van de bedreiging, maar dit biedt ook aanvullende informatie voor een bepaalde aanval.
- De weergave *alle e-mail* is beschikbaar in de bedreigings Verkenner, maar niet in het rapport realtime detectie.
- U vindt meer filterfuncties en de beschikbare acties in de Threat Explorer. Zie voor meer informatie [Microsoft Defender for Office 365 Service Description: beschikbaarheid van functies in office 365-abonnementen](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).
