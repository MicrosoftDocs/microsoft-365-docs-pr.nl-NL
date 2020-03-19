---
title: Berichttracering in het Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
description: Beheerders kunnen berichttracering gebruiken in het Security & Compliance Center om erachter te komen wat er met berichten is gebeurd.
ms.openlocfilehash: 463e4ee5b99b1aaf34c91fc9b8976547a6c2edbd
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/29/2020
ms.locfileid: "42805293"
---
# <a name="message-trace-in-the-security--compliance-center"></a>Berichttracering in het Security & Compliance Center

## <a name="overview"></a>Overzicht

Berichttracering in het Office 365 Security & Compliance Center volgt e-mailberichten terwijl ze door uw Exchange Online-organisatie reizen. U bepalen of een bericht is ontvangen, afgewezen, uitgesteld of bezorgd door de service. Het laat ook zien welke acties zijn ondernomen op het bericht voordat het zijn definitieve status bereikte.

Berichttracering in het Security & Compliance Center verbetert het oorspronkelijke berichttrace dat beschikbaar was in het Exchange-beheercentrum (EAC). U de informatie van berichttracering gebruiken om gebruikersvragen over wat er met berichten is gebeurd, problemen met de e-mailstroom op te lossen en beleidswijzigingen te valideren efficiënt te beantwoorden.

> [!NOTE]
> • Als u een berichttracering wilt uitvoeren, moet u lid zijn van de rolgroepen Organisatiebeheer, Compliance Management of Helpdesk. Zie [Machtigingen in het Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie. <br/><br/>• Het maximum aantal berichten dat in de resultaten wordt weergegeven, is afhankelijk van het geselecteerde rapporttype (zie de sectie [Rapporttype kiezen](#choose-report-type) voor meer informatie). De [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/reporting/get-historicalsearch) cmdlet in Exchange Online PowerShell of Exchange Online Protection PowerShell retourneert alle berichten in de resultaten.

## <a name="open-message-trace"></a>Berichttracering openen

1. Open het Office 365 Security <https://protection.office.com>& Compliance Center op .

2. De **e-mailstroom**uitvouwen en vervolgens **Berichttracering**selecteren .

## <a name="message-trace-page"></a>Pagina berichttracering

Vanaf hier u een nieuwe standaardtracering starten door op de knop **Een traceerknop starten** te klikken. Hierwordt gezocht naar alle berichten voor alle afzenders en ontvangers van de afgelopen twee dagen. Of u een van de opgeslagen query's uit de beschikbare querycategorieën gebruiken en deze uitvoeren als is of deze gebruiken als uitgangspuntvoor uw eigen query's:

- **Standaardquery's:** ingebouwde query's die worden geleverd door Office 365.

- **Aangepaste query's:** query's die zijn opgeslagen door beheerders in uw organisatie voor toekomstig gebruik.

- **Automatisch opgeslagen query's**: De laatste tien meest recent uitgevoerd query's. Deze lijst maakt het eenvoudig om verder te gaan waar je gebleven was.

Ook op deze pagina is een **downloadbare rapporten** sectie voor de verzoeken die u hebt ingediend, evenals de rapporten zelf wanneer er beschikbaar zijn om te downloaden.

## <a name="options-for-a-new-message-trace"></a>Opties voor een nieuwe berichttracering

### <a name="filter-by-senders-and-recipients"></a>Filteren op afzenders en ontvangers

De standaardwaarden zijn **Alle afzenders** en Alle **geadresseerden,** maar u de volgende velden gebruiken om de resultaten te filteren:

- **Door deze mensen**: Klik in dit veld om een of meer afzenders uit uw organisatie te selecteren. U ook beginnen met het typen van een naam en de items in de lijst worden gefilterd op wat u hebt getypt, net als hoe een zoekpagina zich gedraagt.

- **Aan deze personen:** Klik in dit veld om een of meer ontvangers in uw organisatie te selecteren.

> [!NOTE]
> U ook de e-mailadressen van externe afzenders en ontvangers typen. Jokertekens worden ondersteund `*@contoso.com`(bijvoorbeeld), maar u niet meerdere wildcardvermeldingen tegelijk in hetzelfde veld gebruiken. <br/><br/> U meerdere afzenders of ontvangerslijsten plakken`;`die gescheiden zijn door puntkomma's ( ). spaties`\s`( ),`\r`vervoer retourneert ( ) of volgende lijnen (`\n`).

### <a name="time-range"></a>Tijdsbereik

De standaardwaarde is **2 dagen,** maar u datum-/tijdbereiken van maximaal 90 dagen opgeven. Wanneer u datum-/tijdbereiken gebruikt, moet u rekening houden met de volgende problemen:

- U selecteert standaard het tijdbereik in de **schuifweergave** met behulp van een tijdlijn. U alleen de dag- of tijdinstellingen selecteren die worden weergegeven. Als u een tussenwaarde probeert te selecteren, wordt de start-/eindbel uitgelijnd op de dichtstbijzijnde weergegeven instelling.

  ![Een tijdbereik voor schuifregelaars in een nieuwe berichttracering in het Security & Compliance Center](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  U echter ook overschakelen naar **aangepaste** weergave waar u de **waarden Begindatum** en **Einddatum** (inclusief tijden) opgeven en u ook de **tijdzone** voor het datum-/tijdbereik selecteren. Houd er rekening mee dat de instelling **Tijdzone** van toepassing is op zowel uw query-invoer als uw queryresultaten.

  ![Een aangepast tijdsbereik in een nieuw berichttrace in het Security & Compliance Center](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  Gedurende 10 dagen of minder zijn de resultaten direct beschikbaar als **samenvattend** rapport. Als u een tijdbereik opgeeft dat zelfs iets groter is dan 10 dagen, worden de resultaten vertraagd omdat ze alleen beschikbaar zijn als downloadbaar CSV-bestand **(Uitgebreide samenvatting** of **uitgebreide** rapporten).

  Zie de sectie [Rapporttype Kiezen](#choose-report-type) in dit onderwerp voor meer informatie over de verschillende rapporttypen.

  **Opmerking:** Uitgebreide samenvatting en uitgebreide rapporten worden voorbereid met behulp van gearchiveerde berichttraceringsgegevens en het kan enkele uren duren voordat uw rapport beschikbaar is om te downloaden. Afhankelijk van het aantal andere beheerders dat rond dezelfde tijd ook rapportaanvragen heeft ingediend, ziet u mogelijk ook een vertraging voordat de verwerking wordt gestart voor uw aanvraag in de wachtrij.

- Als u een query opslaat in de **weergave Slider,** wordt het relatieve tijdbereik (bijvoorbeeld 3 dagen vanaf vandaag) opgeslagen. Als u een query opslaat in de **aangepaste** weergave, wordt het absolute datum-/tijdbereik opgeslagen (bijvoorbeeld 2018-05-06 13:00 tot 2018-05-08 18:00).

### <a name="more-search-options"></a>Meer zoekopties

#### <a name="delivery-status"></a>Leveringsstatus

U de standaardwaarde **Allemaal** geselecteerd laten, of u een van de volgende waarden selecteren om de resultaten te filteren:

- **Bezorgd**: Het bericht is met succes afgeleverd op de beoogde bestemming.

- **In behandeling**: Levering van het bericht wordt geprobeerd of opnieuw geprobeerd.

- **Uitgebreid**: Een ontvanger van een distributiegroep is uitgebreid voordat de afzonderlijke leden van de groep worden geleverd.

- **Mislukt**: Het bericht is niet bezorgd.

- **In quarantaine**: Het bericht is in quarantaine geplaatst (als spam, bulkmail of phishing). Zie [E-mailberichten in quarantaine in Office 365](quarantine-email-messages.md)voor meer informatie.

- **Gefilterd als spam**: Het bericht is geïdentificeerd spam, en werd afgewezen of geblokkeerd (niet in quarantaine geplaatst).

- **Status krijgen:** Het bericht is onlangs ontvangen door Office 365, maar er zijn nog geen andere statusgegevens beschikbaar. Kom over een paar minuten terug.

**Opmerking:** de waarden **in behandeling,** **in quarantaine geplaatst**en filteren als **spam** zijn alleen beschikbaar voor zoekopdrachten van minder dan 10 dagen. Ook kan er een 5 tot 10 minuten vertraging tussen de werkelijke en gerapporteerde leveringsstatus.

#### <a name="message-id"></a>Bericht-id

Dit is de internetbericht-id (ook wel de client-id genoemd) die is gevonden in de **Message-ID:** koptekstveld in de berichtkop. Gebruikers kunnen u deze waarde geven om specifieke berichten te onderzoeken.

Deze waarde is constant voor de levensduur van het bericht. Voor berichten die zijn gemaakt in Office 365 `<GUID@ServerFQDN>`of Exchange, bevindt\< \>de waarde zich in de indeling , inclusief de hoekhaakjes ( ). Bijvoorbeeld `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Andere berichtensystemen kunnen verschillende syntaxis of waarden gebruiken. Deze waarde wordt verondersteld uniek te zijn, maar niet alle e-mailsystemen volgen strikt aan deze eis. Als het **bericht-ID:** kopveld niet bestaat of leeg is voor binnenkomende berichten van externe bronnen, wordt een willekeurige waarde toegewezen.

Wanneer u **Message ID** gebruikt om de resultaten te filteren, moet u de volledige tekenreeks, inclusief eventuele hoekhaakjes, opnemen.

#### <a name="direction"></a>Richting

U de standaardwaarde **Allemaal** geselecteerd laten of u **Binnenkomend** (berichten die naar ontvangers in uw organisatie worden verzonden) of **Uitgaande** (berichten die van gebruikers in uw organisatie worden verzonden) selecteren om de resultaten te filteren.

#### <a name="original-client-ip-address"></a>Origineel IP-adres van de client

U de resultaten per IP-adres van de klant indienen om gehackte computers te onderzoeken die grote hoeveelheden spam of malware verzenden. Hoewel de berichten mogelijk afkomstig lijken te zijn van meerdere afzenders, is het waarschijnlijk dat dezelfde computer alle berichten genereert.

**Opmerking:** De IP-adresgegevens van de client zijn slechts 10 dagen beschikbaar en zijn alleen beschikbaar in het **uitgebreide overzicht** of **uitgebreide** rapporten (downloadbare CSV-bestanden).

### <a name="choose-report-type"></a>Rapporttype kiezen

De beschikbare rapporttypen zijn:

- **Overzicht**: Beschikbaar als het tijdbereik minder dan 10 dagen is en geen extra filteropties vereist. De resultaten zijn vrijwel direct beschikbaar nadat u op **Zoeken**hebt geklikt. Het rapport geeft resultaten tot 20000 terug.

- **Uitgebreide samenvatting** of **uitgebreid**: Deze rapporten zijn alleen beschikbaar als downloadbare CSV-bestanden en vereisen een of meer van de volgende filteropties, ongeacht het tijdsbereik: **Door deze mensen**, voor deze **mensen**, of **Message ID**. U wildcards gebruiken voor de afzenders \*of de ontvangers (bijvoorbeeld @contoso.com). Het uitgebreide overzichtsrapport retourneert maximaal 50000 resultaten. Het rapport Uitgebreid retourneert maximaal 1000 resultaten.

**Toelichting**:

- Uitgebreide samenvatting en uitgebreide rapporten worden voorbereid met behulp van gearchiveerde berichttraceringsgegevens en het kan enkele uren duren voordat uw rapport beschikbaar is om te downloaden. Afhankelijk van het aantal andere beheerders dat rond dezelfde tijd ook rapportaanvragen heeft ingediend, ziet u mogelijk ook een vertraging voordat uw aanvraag in de wachtrij wordt verwerkt.

- Hoewel u een uitgebreid overzicht of uitgebreid rapport voor elk datum-/tijdbereik selecteren, zijn de laatste vier uur gearchiveerde gegevens meestal nog niet beschikbaar voor deze twee typen rapporten.

Wanneer u op **Volgende**klikt, krijgt u een overzichtspagina met de filteropties die u hebt geselecteerd, een unieke (bewerkbare) titel voor het rapport en het e-mailadres dat de melding ontvangt wanneer de berichttracering is voltooid (ook bewerkbaar en moet zich in een van de geaccepteerde domeinen van uw organisatie bevinden). Klik **op Rapport voorbereiden** om de berichttracering in te dienen. Op de hoofdpagina **berichttracering** u de status van het rapport zien in de sectie **Downloadbare rapporten.**

Zie de volgende sectie voor meer informatie over de informatie die is geretourneerd in de verschillende rapporttypen.

## <a name="message-trace-results"></a>Resultaten van berichttracering

De verschillende rapporttypen geven verschillende informatieniveaus weer. De informatie die beschikbaar is in de verschillende rapporten wordt beschreven in de volgende secties.

### <a name="summary-report-output"></a>Uitvoer van overzichtsrapport

Na het uitvoeren van de berichttracering worden de resultaten weergegeven, gesorteerd op aflopende datum/tijd (meest recente eerst).

![Resultaten van het overzichtsrapport voor berichttracering in het Security & Compliance Center](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

Het samenvattende rapport bevat de volgende informatie:

- **Datum**: De datum en het tijdstip waarop het bericht door de service is ontvangen, met behulp van de geconfigureerde UTC-tijdzone.

- **Afzender**: Het e-mailadres van de afzender *(alias*@*domein).*

- **Ontvanger**: het e-mailadres van de ontvanger of ontvangers. Voor een bericht dat naar meerdere ontvangers wordt verzonden, is er één regel per ontvanger. Als de ontvanger een distributiegroep, dynamische distributiegroep of een beveiligde groep met e-mail is, is de groep de eerste ontvanger en bevindt elk lid van de groep zich op een aparte regel.

- **Onderwerp**: De eerste 256 tekens van het onderwerp van het **bericht:** veld.

- **Status:** Deze waarden worden beschreven in de sectie [Leveringsstatus.](#delivery-status)

Standaard worden de eerste 250 resultaten geladen en direct beschikbaar. Wanneer u naar beneden scrolt, is er een lichte pauze als de volgende batch van de resultaten worden geladen. In plaats van te scrollen, u op **Alles laden** klikken om alle resultaten tot een maximum van 10.000 te laden.

U op de kolomkoppen klikken om de resultaten te sorteren op de waarden in die kolom in oplopende of aflopende volgorde.

U op **Filterresultaten** klikken om de resultaten te filteren op een of meer kolommen.

U de resultaten exporteren nadat u een of meer rijen hebt geselecteerd door op **Exportresultaten** te klikken en vervolgens **alle resultaten exporteren,** **Geladen resultaten exporteren**of Geselecteerd **exporteren**selecteren te selecteren.

#### <a name="find-related-records-for-this-message"></a>Gerelateerde records voor dit bericht zoeken

Gerelateerde berichtrecords zijn records die dezelfde bericht-id hebben gedeeld. Vergeet niet dat zelfs één bericht dat tussen twee personen wordt verzonden, meerdere records kan genereren. Het aantal records neemt toe wanneer het bericht wordt beïnvloed door uitbreiding van de distributiegroep, doorsturen, regels voor de mailstroom (ook wel transportregels genoemd), enz.

Nadat u het selectievakje van een rij hebt ingekozen, u gerelateerde records voor het bericht](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> vinden door te klikken op de knop **Gerelateerde** zoeken die wordt weergegeven of door **Meer opties** ![meer **gerelateerde records voor dit bericht**zoeken in te schakelen).

Zie eerder in dit onderwerp de sectie Bericht-id voor meer informatie over de bericht-id.

#### <a name="message-trace-details"></a>Details voor berichttracering

In de uitvoer van het overzichtsrapport u details over een bericht weergeven met behulp van een van de volgende methoden:

- Schakel de rij in (klik ergens in de rij behalve het selectievakje).

- Schakel het selectievakje rij in en](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> klik op **Meer opties** ![Meer **berichtgegevens weergeven**.

   ![Details na dubbelklikken op een rij in de resultaten van het overzichtsrapportbericht in het Security & Compliance Center](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

De informatie over de berichttracering bevat de volgende aanvullende informatie die niet in het samenvattende rapport aanwezig is:

- **Berichtgebeurtenissen:** deze sectie bevat classificaties die helpen bij het categoriseren van de acties die de service ontvangt voor berichten. **Enkele van de meer interessante gebeurtenissen** die je zou kunnen tegenkomen zijn:

  - **Ontvangen**: Het bericht is ontvangen door de service.

  - **Verzenden**: Het bericht is verzonden door de service.

  - **Mislukt:** het bericht kan niet worden bezorgd.

  - **Afleveren**: Het bericht is in een postvak bezorgd.

  - **Uitvouwen**: Het bericht is verzonden naar een distributiegroep die is uitgebreid.

  - **Overdracht**: Ontvangers zijn verplaatst naar een tweeledig bericht vanwege de conversie van inhoud, limieten voor geadresseerden of agents.

  - **Uitstellen**: De bezorging van het bericht is uitgesteld en mogelijk later opnieuw geprobeerd.

  - **Opgelost**: het bericht is doorgestuurd naar een nieuw adres van de geadresseerde op basis van een Active Directory-opzoeken. Wanneer dit gebeurt, wordt het oorspronkelijke adres van de geadresseerde in een aparte rij in de berichttracering weergegeven, samen met de uiteindelijke leveringsstatus voor het bericht.

  Notities:

  - Een saai bericht dat met succes is afgeleverd, genereert meerdere **gebeurtenisvermeldingen** in de berichttracering.

  - Deze lijst is niet bedoeld om volledig te zijn. Zie [Gebeurtenistypen in het logboek van het bijhouden](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)van berichten voor beschrijvingen van meer gebeurtenissen. Houd er rekening mee dat deze koppeling een onderwerp Exchange Server (on-premises Exchange) is.

- **Meer informatie**: Deze sectie bevat de volgende details:

  - **Bericht-id:** deze waarde wordt eerder in dit onderwerp beschreven in de sectie [Bericht-id.](#message-id) Bijvoorbeeld `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

  - **Berichtgrootte**

  - **Van IP**: Het IP-adres van de computer die het bericht heeft verzonden. Voor uitgaande berichten die vanuit Exchange Online worden verzonden, is deze waarde leeg.

  - **Naar IP**: Het IP-adres of de adressen waar de service heeft geprobeerd het bericht af te leveren. Als het bericht meerdere ontvangers heeft, worden deze weergegeven. Voor binnenkomende berichten die naar Exchange Online worden verzonden, is deze waarde leeg.

### <a name="enhanced-summary-reports"></a>Uitgebreide overzichtsrapporten

Beschikbaar (voltooid) Uitgebreide overzichtsrapporten zijn beschikbaar in de sectie **Downloadbare rapporten** aan het begin van het bericht. De volgende informatie is beschikbaar in het rapport:

- **origin_timestamp:**<sup>*</sup>De datum en tijd waarop het bericht in eerste instantie door de service werd ontvangen, met behulp van de geconfigureerde UTC-tijdzone.

- **sender_address**: Het e-mailadres van de afzender *(alias*@*domein).*

- **Recipient_status**: De status van de levering van het bericht aan de ontvanger. Als het bericht naar meerdere geadresseerden is verzonden, worden alle ontvangers en \<de bijbehorende status voor elk weergegeven in de indeling: de*status*\> *van het e-mailadres*\>##\<. Bijvoorbeeld:

  - **##Receive, Verzenden** betekent dat het bericht is ontvangen door de service en naar de beoogde bestemming is verzonden.

  - **##Receive betekent Mislukk** dat het bericht is ontvangen door de service, maar dat de levering aan de beoogde bestemming is mislukt.

  - **##Receive, Deliver** betekent dat het bericht is ontvangen door de service en is afgeleverd in het postvak van de ontvanger.

- **message_subject**: De eerste 256 tekens van het onderwerpveld **van** het bericht.

- **total_bytes:** de grootte van het bericht in bytes, inclusief bijlagen.

- **message_id**: Deze waarde wordt eerder in dit onderwerp beschreven in de sectie [Bericht-id.](#message-id) Bijvoorbeeld `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

- **network_message_id:** een unieke waarde voor bericht-id's die blijft bestaan in alle kopieën van het bericht dat kan worden gemaakt als gevolg van splitsing of uitbreiding van de distributiegroep. Een voorbeeldwaarde `1341ac7b13fb42ab4d4408cf7f55890f`is .

- **original_client_ip**: Het IP-adres van de client van de afzender.

- **directionaliteit**: geeft aan of het bericht binnenkomend (1) naar uw organisatie is verzonden of dat het vanuit uw organisatie is verzonden.directionity : Indicates whether the message was sent inbound (1) to your organization, or of it was sent outbound (2) from your organization.

- **connector_id**: De naam van de bron- of bestemmingsconnector. Zie [E-mailstroom configureren met connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)voor meer informatie over connectors in Exchange Online.

- **delivery_priority**<sup>*</sup>: Of het bericht is verzonden met **hoge,** **lage**of **normale** prioriteit.

<sup>*</sup>Deze eigenschappen zijn alleen beschikbaar in uitgebreide overzichtsrapporten.

### <a name="extended-reports"></a>Uitgebreide rapporten

Beschikbare (voltooide) uitgebreide rapporten zijn beschikbaar in de sectie **Downloadbare rapporten** aan het begin van het berichttracering. Vrijwel alle informatie uit een uitgebreid samenvattend rapport is beschikbaar in een uitgebreid rapport (met uitzondering van **origin_timestamp** en **delivery_priority).** De volgende aanvullende informatie is alleen beschikbaar in een uitgebreid rapport:

- **client_ip**: Het IP-adres van de e-mailserver of berichtenclient die het bericht heeft ingediend.

- **client_hostname**: De hostnaam of FQDN van de e-mailserver of berichtenclient die het bericht heeft ingediend.

- **server_ip**: Het IP-adres van de bron- of doelserver.

- **server_hostname**: De hostnaam of FQDN van de doelserver.

- **source_context**: Extra informatie die is gekoppeld aan het **bronveld.** Bijvoorbeeld:

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **bron**: De Exchange Online component die verantwoordelijk is voor de gebeurtenis. Bijvoorbeeld:

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id**: Deze komen overeen met de **gebeurteniswaarden van bericht** die worden uitgelegd in de sectie [Gerelateerde records zoeken voor dit bericht.](#find-related-records-for-this-message)

- **internal_message_id:** een bericht-id die is toegewezen door de Exchange Online-server die het bericht momenteel verwerkt.

- **recipient_address**: De e-mailadressen van de ontvangers van het bericht. Meerdere e-mailadressen worden gescheiden door het puntkommateken (;).

- **recipient_count**: Het totale aantal ontvangers in het bericht.

- **related_recipient_address:** Worden `EXPAND` `REDIRECT`gebruikt `RESOLVE` met , en gebeurtenissen om andere e-mailadressen van geadresseerden weer te geven die aan het bericht zijn gekoppeld.

- **referentie**: Dit veld bevat aanvullende informatie voor specifieke soorten gebeurtenissen. Bijvoorbeeld:

  - **DSN**: Bevat de rapportkoppeling, de **message_id** waarde van de bijbehorende melding van de leveringsstatus (ook bekend als een DSN-, niet-leveringsrapport, NDR of bouncebericht) als er na deze gebeurtenis een DSN wordt gegenereerd. Als dit een DSN-bericht is, bevat dit veld de **message_id** waarde van het oorspronkelijke bericht waarvoor de DSN is gegenereerd.

  - **UITVOUWEN:** Bevat de **related_recipient_address** waarde van de gerelateerde berichten.

  - **ONTVANGEN**: Kan de **message_id** waarde van het gerelateerde bericht bevatten als het bericht is gegenereerd door andere processen (bijvoorbeeld Inbox-regels).

  - **VERZENDEN**: Bevat de **internal_message_id** waarde van eventuele DSN-berichten.

  - **OVERDRACHT**: Bevat de **internal_message_id** waarde van het bericht dat wordt gevorkt (bijvoorbeeld door contentconversie, limieten voor ontvangers van berichten of agents).

  - **POSTVAKREGEL**: Bevat de **internal_message_id** waarde van het binnenkomende bericht waardoor de regel Postvak in het uitgaande bericht is gegenereerd.

    Voor andere soorten gebeurtenissen is dit veld meestal leeg.

- **return_path**: Het e-mailadres voor retourneren dat is opgegeven door de **opdracht E-mail van** die het bericht heeft verzonden. Hoewel dit veld nooit leeg is, kan de waarde `<>`van het null-afzenderadres worden weergegeven als .

- **message_info**: Aanvullende informatie over het bericht. Bijvoorbeeld:

  - De datum-time van de `DELIVER` datum `SEND` van de oorsprong van het bericht in UTC voor en gebeurtenissen. De oorsprongsdatum is het moment waarop het bericht voor het eerst de Exchange Online-organisatie binnenkwam. De `yyyy-mm-ddThh:mm:ss.fffZ`UTC-datumtijd wordt weergegeven in de ISO 8601-datum-tijdnotatie: , waar `yyyy` = jaar, `mm` = `hh` maand, `mm` `dd` = dag, `T` `fff` het begin van de tijdcomponent aangeeft, = uur, = minuut, `ss` = seconde, = fracties van een seconde, en `Z` geeft aan `Zulu`, wat een andere manier is om UTC aan te duiden.

  - Verificatiefouten. U ziet bijvoorbeeld de `11a` waarde en het type verificatie dat is gebruikt toen de verificatiefout zich voordeed.

- **tenant_id**: Een GUID-waarde die de Exchange `39238e87-b5ab-4ef6-a559-af54c6b07b42`Online-organisatie vertegenwoordigt (bijvoorbeeld).

- **original_server_ip**: Het IP-adres van de oorspronkelijke server.

- **custom_data**: Bevat gegevens met betrekking tot specifieke gebeurtenistypen. Zie de volgende secties voor meer informatie.

#### <a name="custom_data-values"></a>custom_data waarden

Het **custom_data** veld `AGENTINFO` voor een gebeurtenis wordt gebruikt door verschillende Exchange Online-agents om gegevens over de verwerking van berichten te registreren. Enkele van de meer interessante agenten worden beschreven in de volgende secties.

#### <a name="spam-filter-agent"></a>Spamfilteragent

Een **custom_data** waarde `S:SFA` die begint met is van de spam filter agent. De belangrijkste details worden beschreven in de volgende tabel:

|**Value**|**Beschrijving**|
|:-----|:-----|
|`SFV=NSPM`|Het bericht is gemarkeerd als niet-spam en is verzonden naar de beoogde ontvangers.|
|`SFV=SPM`|Het bericht is gemarkeerd als spam door het inhoudsfilter.|
|`SFV=BLK`|Filteren is overgeslagen en het bericht is geblokkeerd omdat het afkomstig is van een geblokkeerde afzender.|
|`SFV=SKS`|Het bericht is gemarkeerd als spam voordat het werd verwerkt door het inhoudsfilter. Dit geldt ook voor berichten waarbij het bericht overeenkomt met een transportregel om het automatisch als spam te markeren en alle aanvullende filtering te omzeilen.|
|`SCL=<number>`|Voor meer informatie over de verschillende SCL-waarden en wat ze betekenen, zie [Spam vertrouwen niveaus](spam-confidence-levels.md).|
|`PCL=<number>`|De pcl-waarde (Phishing Confidence Level) van het bericht. Deze kunnen worden geïnterpreteerd op dezelfde manier als de SCL waarden gedocumenteerd in [Spam vertrouwen niveaus](spam-confidence-levels.md).|
|`DI=SB`|De afzender van het bericht is geblokkeerd.|
|`DI=SQ`|Het bericht was in quarantaine geplaatst.|
|`DI=SD`|Het bericht is verwijderd.|
|`DI=SJ`|Het bericht is verzonden naar de map Ongewenste e-mail van de ontvanger.|
|`DI=SN`|Het bericht is doorgestuurd via de normale uitgaande bezorggroep.|
|`DI=SO`|Het bericht werd doorgestuurd door de groep met een hogere risicolevering. Zie [Een groep met een hoog risico voor uitgaande berichten](high-risk-delivery-pool-for-outbound-messages.md)voor meer informatie.|
|`SFS=[a]|SFS=[b]`|Dit geeft aan dat de spamregels zijn afgestemd.|
|`IPV=CAL`|Het bericht is toegestaan via de spamfilters omdat het IP-adres is opgegeven in een IP-lijst toestaan in het verbindingsfilter.|
|`H=<EHLOstring>`|De HELO- of EHLO-reeks van de aansluitende e-mailserver.|
|`PTR=<ReverseDNS>`|De PTR-record van het verzendende IP-adres, ook wel het omgekeerde DNS-adres genoemd.|

Een voorbeeld **custom_data** waarde voor een bericht dat is gefilterd op spam als volgt:

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>Malwarefilteragent

Een **custom_data** waarde `S:AMA` die begint met is van de malware filter agent. De belangrijkste details worden beschreven in de volgende tabel:

|**Value**|**Beschrijving**|
|:-----|:-----|
|`AMA=SUM|v=1|`Of`AMA=EV|v=1`|Het bericht werd bepaald om malware te bevatten. `SUM`geeft aan dat de malware kan zijn gedetecteerd door een aantal motoren. `EV`geeft aan dat de malware is gedetecteerd door een specifieke engine. Wanneer malware wordt gedetecteerd door een engine, activeert dit de daaropvolgende acties.|
|`Action=r`|Het bericht is vervangen.|
|`Action=p`|Het bericht werd omzeild.|
|`Action=d`|Het bericht is uitgesteld.|
|`Action=s`|Het bericht is verwijderd.|
|`Action=st`|Het bericht werd omzeild.|
|`Action=sy`|Het bericht werd omzeild.|
|`Action=ni`|Het bericht is afgewezen.|
|`Action=ne`|Het bericht is afgewezen.|
|`Action=b`|Het bericht is geblokkeerd.|
|`Name=<malware>`|De naam van de malware die werd gedetecteerd.|
|`File=<filename>`|De naam van het bestand dat de malware bevatte.|

Een voorbeeld **custom_data** waarde voor een bericht dat malware bevat, ziet er als volgt uit:

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>Transportregelagent

Een **custom_data** waarde`S:TRA` die begint met is van de Transport Rule agent voor mail flow regels (ook wel bekend als transport regels). De belangrijkste details worden beschreven in de volgende tabel:

|**Value**|**Beschrijving**|
|:-----|:-----|
|`ETR|ruleId=<guid>`|De regel-ID die is gekoppeld.|
|`St=<datetime>`|De datum en tijd in UTC wanneer de regelovereenkomst heeft plaatsgevonden.|
|`Action=<ActionDefinition>`|De actie die werd toegepast. Zie Acties van de [regelvan de mailstroomregel in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor een lijst met beschikbare acties.|
|`Mode=<Mode>`|De modus van de regel. Geldige waarden zijn: <br/>• **Afdwingen:** Alle acties op de regel worden afgedwongen. <br/>• **Test met beleidstips:**: Er worden beleidstips verzonden, maar er wordt geen actie onder nomen om andere handhavingsacties te ondernemen. <br/>• **Test zonder beleidstips**: Acties worden vermeld in een logbestand, maar afzenders worden op geen enkele manier op de hoogte gesteld en er wordt geen handhavingsacties uitgevoerd.|

Een voorbeeld **custom_data** waarde voor een berichten die overeenkomt met de voorwaarden van een e-mailstroomregel, ziet er als volgt uit:

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
