---
title: Berichttracering in het Beveiligings- en compliancecentrum
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
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen berichttracering gebruiken in het Security & Compliance Center om erachter te komen wat er met berichten is gebeurd.
ms.openlocfilehash: cb24b9a5f5540f1858ac17b5b4ec3de0c77b47d1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819338"
---
# <a name="message-trace-in-the-security--compliance-center"></a>Berichttracering in het Beveiligings- en compliancecentrum

## <a name="message-trace-features"></a>Functies voor berichttracering

Berichttracering in het Security & Compliance Center volgt e-mailberichten terwijl ze door uw Exchange Online-organisatie reizen. U bepalen of een bericht is ontvangen, afgewezen, uitgesteld of geleverd door de service. Het toont ook welke acties werden ondernomen op het bericht voordat het zijn definitieve status bereikt.

Berichttracering in het Security & Compliance Center verbetert de oorspronkelijke berichttracering die beschikbaar was in het Exchange-beheercentrum (EAC). U de informatie uit berichttracering gebruiken om vragen van gebruikers over wat er met berichten is gebeurd efficiënt te beantwoorden, problemen met de e-mailstroom op te lossen en beleidswijzigingen te valideren.

> [!NOTE]
> • Om een berichttracering uit te voeren, moet u lid zijn van de rolgroepen Organisatiebeheer, Compliance Management of Helpdesk. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie. <br/><br/>• Het maximum aantal berichten dat in de resultaten wordt weergegeven, is afhankelijk van het rapporttype dat u hebt geselecteerd (zie de sectie [Rapporttype kiezen](#choose-report-type) voor meer informatie). De [cmdlet Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) in Exchange Online PowerShell of standalone EOP PowerShell retourneert alle berichten in de resultaten.

## <a name="open-message-trace"></a>Berichttracering openen

1. Open het Security & Compliance Center op <https://protection.office.com> .

2. Vouw **e-mailstroom**uit en selecteer **Vervolgens Berichttracering**.

## <a name="message-trace-page"></a>Berichttraceringspagina

Vanaf hier u een nieuw standaardtraceringsspoor starten door op de knop **Een trace starten te** klikken. Hiermee wordt gezocht naar alle berichten voor alle afzenders en ontvangers van de afgelopen twee dagen. U ook een van de opgeslagen query's uit de beschikbare querycategorieën gebruiken en deze als is uitvoeren of als uitgangspunten gebruiken voor uw eigen query's:

- **Standaardquery's**: Ingebouwde query's van Microsoft 365.

- **Aangepaste query's:** query's die door beheerders in uw organisatie zijn opgeslagen voor toekomstig gebruik.

- **Automatisch opgeslagen query's**: de laatste tien meest recent uitgevoerde query's. Deze lijst maakt het eenvoudig om verder te gaan waar je gebleven was.

Ook op deze pagina is een **downloadbare rapporten** sectie voor de verzoeken die u hebt ingediend, evenals de rapporten zelf wanneer er beschikbaar zijn om te downloaden.

## <a name="options-for-a-new-message-trace"></a>Opties voor een nieuw berichttracering

### <a name="filter-by-senders-and-recipients"></a>Filteren op afzenders en geadresseerden

De standaardwaarden zijn **Alle afzenders** en **Alle geadresseerden,** maar u de volgende velden gebruiken om de resultaten te filteren:

- **Door deze personen**: Klik in dit veld om een of meer afzenders uit uw organisatie te selecteren. U ook beginnen met het typen van een naam en de items in de lijst worden gefilterd op wat u hebt getypt, net als hoe een zoekpagina zich gedraagt.

- **Aan deze personen**: Klik in dit veld om een of meer ontvangers in uw organisatie te selecteren.

> [!NOTE]
> U ook de e-mailadressen van externe afzenders en ontvangers typen. Jokertekens worden ondersteund `*@contoso.com` (bijvoorbeeld), maar u niet meerdere jokeritems tegelijk in hetzelfde veld gebruiken. <br/><br/> U meerdere afzenders of geadresseerdenlijsten plakken, gescheiden door puntkomma's ( `;` ). spaties ( `\s` , vervoer retouren ( `\r` ), of volgende lijnen ( `\n` ).

### <a name="time-range"></a>Tijdsbereik

De standaardwaarde is **2 dagen,** maar u datum-/tijdbereiken van maximaal 90 dagen opgeven. Wanneer u datum-/tijdsbereiken gebruikt, moet u rekening houden met de volgende problemen:

- Standaard selecteert u het tijdsbereik in de **schuifregelaarweergave** met een tijdsregel. U alleen de dag- of tijdinstellingen selecteren die worden weergegeven. Als u een tussenwaarde probeert te selecteren, wordt de begin-/eindbel uitgelijnd op de dichtstbijzijnde weergegeven instelling.

  ![Een schuifregelaartijdbereik in een nieuw berichttracering in het Security & Compliance Center](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  U echter ook overschakelen naar **aangepaste** weergave waar u de **waarden begindatum** en **einddatum** (inclusief tijden) opgeven en u ook de **tijdzone** voor het datum-tijdbereik selecteren. Houd er rekening mee dat de **instelling Tijdzone** van toepassing is op zowel uw query-invoer als uw queryresultaten.

  ![Een aangepast tijdsbereik in een nieuw berichttracering in het Security & Compliance Center](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  Gedurende 10 dagen of minder zijn de resultaten direct beschikbaar als **samenvattend** rapport. Als u een tijdsbereik opgeeft dat zelfs iets groter is dan 10 dagen, worden de resultaten vertraagd omdat ze alleen beschikbaar zijn als een downloadbaar CSV-bestand **(Uitgebreide samenvatting** of **uitgebreide** rapporten).

  Zie de sectie [Rapporttype kiezen](#choose-report-type) in dit onderwerp voor meer informatie over de verschillende rapporttypen.

  **Opmerking**: Uitgebreide overzichts- en uitgebreide rapporten worden opgesteld met behulp van gearchiveerde berichttraceringsgegevens en het kan enkele uren duren voordat uw rapport kan worden gedownload. Afhankelijk van het aantal andere beheerders dat rond dezelfde tijd ook rapportaanvragen heeft ingediend, u ook een vertraging opmerken voordat de verwerking voor uw aanvraag in de wachtrij wordt gestart.

- Als u een query opslaat in de weergave **Schuifregelaar,** wordt het relatieve tijdbereik opgeslagen (bijvoorbeeld 3 dagen vanaf vandaag). Als u een query opslaat in **de aangepaste** weergave, wordt het absolute datum/tijdsbereik opgeslagen (bijvoorbeeld 2018-05-06 13:00 tot 2018-05-08 18:00).

### <a name="more-search-options"></a>Meer zoekopties

#### <a name="delivery-status"></a>Leveringsstatus

U de standaardwaarde **Helemaal** geselecteerd laten of u een van de volgende waarden selecteren om de resultaten te filteren:

- **Geleverd**: Het bericht is geleverd op de beoogde bestemming.

- **In behandeling**: Levering van het bericht wordt geprobeerd of opnieuw geprobeerd.

- **Uitgebreid**: Een ontvanger van een distributiegroep is uitgebreid voordat deze aan de afzonderlijke leden van de groep wordt geleverd.

- **Mislukt:** het bericht is niet bezorgd.

- **In quarantaine**geplaatst : het bericht is in quarantaine geplaatst (als spam, bulkmail of phishing). Zie [EOP in quarantaine geplaatst](quarantine-email-messages.md)voor meer informatie.

- **Gefilterd als spam**: Het bericht is geïdentificeerd spam, en werd afgewezen of geblokkeerd (niet in quarantaine geplaatst).

- **Status krijgen:** Het bericht is onlangs ontvangen door Microsoft 365, maar er zijn nog geen andere statusgegevens beschikbaar. Kom over een paar minuten terug.

**Opmerking:** de waarden **in behandeling,** **in quarantaine geplaatst**en Filter als **spam** zijn alleen beschikbaar voor zoekopdrachten van minder dan 10 dagen. Ook kan er een vertraging van 5 tot 10 minuten tussen de werkelijke en gerapporteerde levering status.

#### <a name="message-id"></a>Bericht-id

Dit is de internetbericht-id (ook wel client-id genoemd) die wordt gevonden in het **veld Message-ID:** koptekst in de berichtkop. Gebruikers kunnen u deze waarde geven om specifieke berichten te onderzoeken.

Deze waarde is constant voor de levensduur van het bericht. Voor berichten die zijn gemaakt in Microsoft 365 of Exchange, is de waarde in de indeling `<GUID@ServerFQDN>` , inclusief de hoekhaakjes ( \< \> ). Bijvoorbeeld `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Andere berichtensystemen kunnen verschillende syntaxis of waarden gebruiken. Deze waarde wordt verondersteld uniek te zijn, maar niet alle e-mailsystemen volgen strikt deze eis. Als het **bericht-ID:** koptekstveld niet bestaat of leeg is voor binnenkomende berichten uit externe bronnen, wordt een willekeurige waarde toegewezen.

Wanneer u **Bericht-id** gebruikt om de resultaten te filteren, moet u de volledige tekenreeks opnemen, inclusief eventuele hoekbeugels.

#### <a name="direction"></a>Richting

U de standaardwaarde **helemaal** geselecteerd laten of u **Binnenkomende** berichten selecteren die naar geadresseerden in uw organisatie zijn verzonden) of **Uitgaande** (berichten die van gebruikers in uw organisatie worden verzonden) om de resultaten te filteren.

#### <a name="original-client-ip-address"></a>Origineel IP-adres voor client

U de resultaten filer door client IP-adres om gehackte computers die grote hoeveelheden spam of malware te onderzoeken. Hoewel de berichten van meerdere afzenders lijken te komen, is het waarschijnlijk dat dezelfde computer alle berichten genereert.

**Opmerking**: De IP-adresgegevens van de client zijn slechts 10 dagen beschikbaar en zijn alleen beschikbaar in het **uitgebreide overzicht** of **uitgebreide** rapporten (downloadbare CSV-bestanden).

### <a name="choose-report-type"></a>Rapporttype kiezen

De beschikbare rapporttypen zijn:

- **Overzicht**: Beschikbaar als het tijdsbereik minder dan 10 dagen is en geen extra filteropties vereist. De resultaten zijn vrijwel direct beschikbaar nadat u op Zoeken hebt **geklikt.** Het rapport retourneert tot 20000 resultaten.

- **Uitgebreide samenvatting** of **Uitgebreid**: Deze rapporten zijn alleen beschikbaar als downloadbare CSV-bestanden en vereisen een of meer van de volgende filteropties, ongeacht het tijdsbereik: **Door deze personen**, Voor deze **personen**of **Message ID**. U wildcards gebruiken voor de afzenders of de ontvangers (bijvoorbeeld \* @contoso.com). Het uitgebreide overzichtsrapport retourneert tot 50000 resultaten. Het uitgebreide rapport retourneert maximaal 1000 resultaten.

**Opmerkingen**:

- Uitgebreide overzichts- en uitgebreide rapporten worden opgesteld met behulp van gearchiveerde berichttraceringsgegevens en het kan enkele uren duren voordat uw rapport beschikbaar is om te downloaden. Afhankelijk van het aantal andere beheerders dat rond dezelfde tijd ook rapportaanvragen heeft ingediend, u ook een vertraging opmerken voordat uw aanvraag in de wachtrij wordt verwerkt.

- Hoewel u een uitgebreide samenvatting of uitgebreid rapport selecteren voor een datum/tijdsbereik, zijn de laatste vier uur gearchiveerde gegevens meestal nog niet beschikbaar voor deze twee typen rapporten.

Wanneer u op **Volgende**klikt, krijgt u een overzichtspagina te zien met de filteropties die u hebt geselecteerd, een unieke (bewerkbare) titel voor het rapport en het e-mailadres dat de melding ontvangt wanneer het bericht wordt voltooid (ook bewerkbaar en moet in een van de geaccepteerde domeinen van uw organisatie staan). Klik **op Rapport voorbereiden** om het berichttracering in te dienen. Op de hoofdpagina **van het bericht tracering** u de status van het rapport zien in de sectie **Downloadbare rapporten.**

Zie de volgende sectie voor meer informatie over de informatie die wordt geretourneerd in de verschillende rapporttypen.

## <a name="message-trace-results"></a>Resultaten van berichttracering

De verschillende rapporttypen geven verschillende informatieniveaus weer. De informatie die beschikbaar is in de verschillende rapporten wordt beschreven in de volgende secties.

### <a name="summary-report-output"></a>Samenvatting rapport output

Na het uitvoeren van de berichttracering worden de resultaten weergegeven, gesorteerd op aflopende datum/tijd (meest recente eerste).

![Resultaten van het overzichtsrapport voor berichttracering in het Security & Compliance Center](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

Het samenvattende rapport bevat de volgende informatie:

- **Datum**: de datum en het tijdstip waarop het bericht door de service is ontvangen, met behulp van de geconfigureerde UTC-tijdzone.

- **Afzender**: Het e-mailadres van de afzender*alias* @ *(aliasdomein).*

- **Ontvanger**: Het e-mailadres van de ontvanger of ontvangers. Voor een bericht dat naar meerdere ontvangers wordt verzonden, is er één regel per ontvanger. Als de ontvanger een distributiegroep, dynamische distributiegroep of beveiligingsgroep met e-mail is, is de groep de eerste ontvanger en staat elk lid van de groep op een aparte regel.

- **Onderwerp**: De eerste 256 tekens van het onderwerp van het **bericht:** veld.

- **Status**: Deze waarden worden beschreven in de sectie [Weergavestatus.](#delivery-status)

Standaard worden de eerste 250 resultaten geladen en direct beschikbaar. Wanneer u naar beneden scrolt, is er een lichte pauze wanneer de volgende batch van de resultaten worden geladen. In plaats van te scrollen, u op **Alles laden** klikken om alle resultaten tot maximaal 10.000 te laden.

U op de kolomkoppen klikken om de resultaten te sorteren op de waarden in die kolom in oplopende of aflopende volgorde.

U op **Resultaten filteren** klikken om de resultaten te filteren op een of meer kolommen.

U de resultaten exporteren nadat u een of meer rijen hebt geselecteerd door op **Exportresultaten** te klikken en vervolgens **Alle resultaten**exporteren, **Geladen resultaten exporteren**of Exporteren **geselecteerd**te selecteren.

#### <a name="find-related-records-for-this-message"></a>Gerelateerde records voor dit bericht zoeken

Gerelateerde berichtrecords zijn records die dezelfde bericht-id hebben gedeeld. Vergeet niet dat zelfs een enkel bericht dat tussen twee personen wordt verzonden, meerdere records kan genereren. Het aantal records neemt toe wanneer het bericht wordt beïnvloed door uitbreiding van de distributiegroep, doorsturen, regels voor e-mailstroom (ook wel transportregels genoemd), enz.

Nadat u het selectievakje van een rij hebt ingecheckt, u gerelateerde records voor het bericht zoeken door te klikken op de knop **Gerelateerde zoeken** die wordt weergegeven of door meer opties meer **More options** ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **zoekgerelateerde records voor dit bericht te**selecteren).

Zie de sectie Bericht-id eerder in dit onderwerp voor meer informatie over de bericht-id.

#### <a name="message-trace-details"></a>Details berichttracering

In de uitvoer van het overzichtsrapport u details over een bericht bekijken met behulp van een van de volgende methoden:

- Schakel de rij in (klik op een willekeurige plaats in de rij, behalve het selectievakje).

- Schakel het selectievakje van de rij in en klik op **Meer opties** ![ Meer ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **berichtdetails weergeven**.

   ![Details na dubbelklikken op een rij in het overzichtsberichtberichttraceren resulteert in het Security & Compliance Center](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

De details van het berichttracering bevatten de volgende aanvullende informatie die niet in het samenvattende rapport aanwezig is:

- **Berichtgebeurtenissen:** deze sectie bevat classificaties die helpen bij het categoriseren van de acties die de service op berichten uitvoert. **Enkele van de meer interessante gebeurtenissen** die je zou kunnen tegenkomen zijn:

  - **Ontvangen**: Het bericht is ontvangen door de service.

  - **Verzenden**: Het bericht is verzonden door de service.

  - **Mislukken:** het bericht kan niet worden bezorgd.

  - **Afleveren**: Het bericht is bezorgd bij een brievenbus.

  - **Uitvouwen**: Het bericht is verzonden naar een distributiegroep die is uitgebreid.

  - **Overdracht**: Ontvangers zijn verplaatst naar een gespleten bericht vanwege inhoudsconversie, limieten voor berichtontvangers of agents.

  - **Uitstellen**: De bezorging van het bericht is uitgesteld en kan later opnieuw worden geprobeerd.

  - **Opgelost**: het bericht is doorgestuurd naar een nieuw adres van de ontvanger op basis van een Active Directory-opzoek. Wanneer dit gebeurt, wordt het oorspronkelijke adres van de ontvanger weergegeven in een aparte rij in het berichtspoor, samen met de uiteindelijke leveringsstatus voor het bericht.

  Opmerkingen:

  - Een saai bericht dat met succes wordt afgeleverd, genereert meerdere **gebeurtenisvermeldingen** in het berichttracering.

  - Deze lijst is niet bedoeld om volledig te zijn. Zie [Gebeurtenistypen in het logboek voor het bijhouden](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)van berichten voor beschrijvingen van meer gebeurtenissen. Houd er rekening mee dat deze koppeling een Exchange Server -onderwerp (on-premises Exchange) is.

- **Meer informatie**: Deze sectie bevat de volgende details:

  - **Bericht-id:** deze waarde wordt eerder in dit onderwerp beschreven in de sectie [Bericht-id.](#message-id) Bijvoorbeeld `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

  - **Berichtgrootte**

  - **Vanaf IP:** Het IP-adres van de computer die het bericht heeft verzonden. Voor uitgaande berichten die vanuit Exchange Online worden verzonden, is deze waarde leeg.

  - **Naar IP:** Het IP-adres of adressen waar de service probeerde het bericht af te leveren. Als het bericht meerdere ontvangers heeft, worden deze weergegeven. Voor binnenkomende berichten die naar Exchange Online worden verzonden, is deze waarde leeg.

### <a name="enhanced-summary-reports"></a>Uitgebreide overzichtsrapporten

Beschikbare (voltooide) uitgebreide overzichtsrapporten zijn beschikbaar in de sectie **Downloadbare rapporten** bij het beginberichttracering. De volgende informatie is beschikbaar in het rapport:

- **origin_timestamp** <sup>*</sup> : De datum en tijd waarop het bericht in eerste instantie door de service is ontvangen, met behulp van de geconfigureerde UTC-tijdzone.

- **sender_address**: Het e-mailadres van de afzender*alias* @ *(aliasdomein).*

- **Recipient_status**: De status van de levering van het bericht aan de ontvanger. Als het bericht naar meerdere ontvangers is verzonden, worden alle geadresseerden en de bijbehorende status voor elk bericht weergegeven in de indeling: \<*email address*\> ## \<*status*\> . Bijvoorbeeld:

  - **##Receive, Verzenden** betekent dat het bericht is ontvangen door de service en naar de beoogde bestemming is verzonden.

  - **##Receive, Fail** betekent dat het bericht is ontvangen door de service, maar de levering aan de beoogde bestemming is mislukt.

  - **##Receive, Deliver** means the message is received by the service and was delivered to the recipient's mailbox.

- **message_subject**: De eerste 256 tekens van het veld **Onderwerp** van het bericht.

- **total_bytes:** de grootte van het bericht in bytes, inclusief bijlagen.

- **message_id**: Deze waarde wordt eerder in dit onderwerp beschreven in de sectie [Bericht-id.](#message-id) Bijvoorbeeld `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

- **network_message_id:** een unieke bericht-ID-waarde die blijft bestaan in alle kopieën van het bericht die mogelijk worden gemaakt als gevolg van uitbreiding van de splitsing of distributiegroep. Een voorbeeldwaarde is `1341ac7b13fb42ab4d4408cf7f55890f` .

- **original_client_ip**: Het IP-adres van de klant van de afzender.

- **directionaliteit**: geeft aan of het bericht binnenkomend (1) naar uw organisatie is verzonden of dat het uitgaande (2) vanuit uw organisatie is verzonden.

- **connector_id**: de naam van de bron- of bestemmingsconnector. Zie [E-mailstroom configureren met connectoren in Office 365 voor](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)meer informatie over connectoren in Exchange Online.

- **delivery_priority** <sup>*</sup> : Of het bericht nu is verzonden met **hoge,** **lage**of **normale** prioriteit.

<sup>*</sup>Deze eigenschappen zijn alleen beschikbaar in uitgebreide overzichtsrapporten.

### <a name="extended-reports"></a>Uitgebreide rapporten

Beschikbare (voltooide) uitgebreide rapporten zijn beschikbaar in de sectie **Downloadbare rapporten** aan het begin van berichttracering. Vrijwel alle informatie uit een uitgebreid samenvattend rapport is beschikbaar in een uitgebreid rapport (met uitzondering van **origin_timestamp** en **delivery_priority).** De volgende aanvullende informatie is alleen beschikbaar in een uitgebreid rapport:

- **client_ip**: het IP-adres van de e-mailserver of berichtenclient die het bericht heeft verzonden.

- **client_hostname**: de hostnaam of FQDN van de e-mailserver of berichtenclient die het bericht heeft verzonden.

- **server_ip**: Het IP-adres van de bron- of doelserver.

- **server_hostname**: De hostnaam of FQDN van de doelserver.

- **source_context**: Extra informatie in verband met het **bronveld.** Bijvoorbeeld:

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **bron**: De Exchange Online-component die verantwoordelijk is voor de gebeurtenis. Bijvoorbeeld:

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id:** deze komen overeen met de **gebeurteniswaarden van het bericht** die worden uitgelegd in de sectie [Gerelateerde records zoeken voor dit bericht.](#find-related-records-for-this-message)

- **internal_message_id:** een bericht-id die is toegewezen door de Exchange Online-server die het bericht momenteel verwerkt.

- **recipient_address**: De e-mailadressen van de ontvangers van het bericht. Meerdere e-mailadressen worden gescheiden door het puntkommateken (;).

- **recipient_count**: het totale aantal ontvangers in het bericht.

- **related_recipient_address**: Gebruikt met `EXPAND` en gebeurtenissen om andere `REDIRECT` `RESOLVE` e-mailadressen van de geadresseerden weer te geven die aan het bericht zijn gekoppeld.

- **referentie**: Dit veld bevat aanvullende informatie voor specifieke soorten gebeurtenissen. Bijvoorbeeld:

  - **DSN**: bevat de rapportkoppeling, de **message_id** waarde van de bijbehorende melding van de leveringsstatus (ook bekend als een DSN-, niet-leveringsrapport, NDR of bouncebericht) als er een DSN wordt gegenereerd na deze gebeurtenis. Als dit een DSN-bericht is, bevat dit veld de **message_id** waarde van het oorspronkelijke bericht waarvoor het DSN is gegenereerd.

  - **UITVOUWEN**: Bevat de **related_recipient_address** waarde van de gerelateerde berichten.

  - **ONTVANGEN**: Kan de **message_id** waarde van het gerelateerde bericht bevatten als het bericht is gegenereerd door andere processen (bijvoorbeeld regels voor Postvak IN).

  - **VERZENDEN**: Bevat de **internal_message_id** waarde van DSN-berichten.

  - **OVERDRACHT**: bevat de **internal_message_id** waarde van het bericht dat wordt gevorkt (bijvoorbeeld door inhoudsconversie, limieten voor berichtontvangers of agents).

  - **MAILBOXRULE**: bevat de **internal_message_id** waarde van het binnenkomende bericht waardoor de regel Postvak IN het uitgaande bericht heeft gegenereerd.

    Voor andere soorten gebeurtenissen is dit veld meestal leeg.

- **return_path**: het e-mailadres voor retouren dat is opgegeven door de opdracht **MAIL FROM** waarmee het bericht is verzonden. Hoewel dit veld nooit leeg is, kan de waarde van het adres null-afzender worden weergegeven als `<>` .

- **message_info**: Aanvullende informatie over het bericht. Bijvoorbeeld:

  - De bericht origination datum-tijd in UTC voor `DELIVER` en `SEND` gebeurtenissen. De datum van oorsprong is het tijdstip waarop het bericht voor het eerst de Exchange Online-organisatie is binnengekomen. De UTC-datumtijd wordt weergegeven in de datumtijdnotatie ISO 8601: `yyyy-mm-ddThh:mm:ss.fffZ` , waarbij `yyyy` = jaar, = `mm` `dd` maand, = dag, `T` het begin van de tijdcomponent aangeeft, `hh` = uur, = `mm` minuut, = `ss` tweede, = fracties van een `fff` seconde, en betekent , wat een `Z` andere manier is om `Zulu` UTC aan te duiden.

  - Verificatiefouten. U ziet bijvoorbeeld de waarde `11a` en het type verificatie dat is gebruikt toen de verificatiefout zich voordeed.

- **tenant_id**: een GUID-waarde die de Exchange Online-organisatie vertegenwoordigt `39238e87-b5ab-4ef6-a559-af54c6b07b42` (bijvoorbeeld).

- **original_server_ip**: Het IP-adres van de oorspronkelijke server.

- **custom_data**: Bevat gegevens met betrekking tot specifieke gebeurtenistypen. Zie de volgende secties voor meer informatie.

#### <a name="custom_data-values"></a>custom_data waarden

Het **custom_data** veld voor een `AGENTINFO` gebeurtenis wordt door verschillende Exchange Online-agents gebruikt om gegevens over de verwerking van berichten te registreren. Enkele van de meer interessante agenten worden beschreven in de volgende secties.

#### <a name="spam-filter-agent"></a>Spamfilteragent

Een **custom_data** waarde die begint met `S:SFA` is van de spam filter agent. De belangrijkste details worden beschreven in de volgende tabel:

|**Value**|**Beschrijving**|
|:-----|:-----|
|`SFV=NSPM`|Het bericht is gemarkeerd als niet-spam en is verzonden naar de beoogde ontvangers.|
|`SFV=SPM`|Het bericht is gemarkeerd als spam door antispamfiltering (ook wel contentfiltering genoemd).|
|`SFV=BLK`|Filtering is overgeslagen en het bericht is geblokkeerd omdat het afkomstig is van een geblokkeerde afzender.|
|`SFV=SKS`|Het bericht is gemarkeerd als spam voordat het werd verwerkt door antispamfiltering. Dit omvat berichten waarin het bericht overeenkomt met een e-mailstroomregel (ook wel een transportregel genoemd) om het automatisch als spam te markeren en alle extra filtering te omzeilen.|
|`SCL=<number>`|Zie [Spamvertrouwensniveaus](spam-confidence-levels.md)voor meer informatie over de verschillende SCL-waarden en wat ze betekenen.|
|`PCL=<number>`|De pcl-waarde (Phishing Confidence Level) van het bericht. Deze kunnen op dezelfde manier worden geïnterpreteerd als de SCL-waarden die zijn gedocumenteerd in [het vertrouwensniveau van spam.](spam-confidence-levels.md)|
|`DI=SB`|De afzender van het bericht is geblokkeerd.|
|`DI=SQ`|Het bericht is in quarantaine geplaatst.|
|`DI=SD`|Het bericht is verwijderd.|
|`DI=SJ`|Het bericht is verzonden naar de map Ongewenste e-mail van de ontvanger.|
|`DI=SN`|Het bericht is doorgestuurd via de normale uitgaande bezorgpool.|
|`DI=SO`|Het bericht is doorgestuurd via de pool met een hoger risico. Zie [Een hoog risicobezorggroep voor uitgaande berichten voor](high-risk-delivery-pool-for-outbound-messages.md)meer informatie.|
|`SFS=[a]|SFS=[b]`|Dit geeft aan dat spamregels zijn afgestemd.|
|`IPV=CAL`|Het bericht is toegestaan via de spamfilters omdat het IP-adres is opgegeven in een IP Allow-lijst in het verbindingsfilter.|
|`H=<EHLOstring>`|De HELO- of EHLO-tekenreeks van de verbindende e-mailserver.|
|`PTR=<ReverseDNS>`|De PTR-record van het verzendende IP-adres, ook wel het omgekeerde DNS-adres genoemd.|

Een voorbeeld **custom_data** waarde voor een bericht dat is gefilterd voor spam als dit:

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>Malwarefilteragent

Een **custom_data** waarde die begint met `S:AMA` is van de malware filter agent. De belangrijkste details worden beschreven in de volgende tabel:

|**Value**|**Beschrijving**|
|:-----|:-----|
|`AMA=SUM|v=1|`Of`AMA=EV|v=1`|Het bericht was vastbesloten om malware te bevatten. `SUM`geeft aan dat de malware kan zijn gedetecteerd door een aantal motoren. `EV`geeft aan dat de malware werd gedetecteerd door een specifieke engine. Wanneer malware wordt gedetecteerd door een engine dit activeert de volgende acties.|
|`Action=r`|Het bericht is vervangen.|
|`Action=p`|Het bericht is omzeild.|
|`Action=d`|Het bericht is uitgesteld.|
|`Action=s`|Het bericht is verwijderd.|
|`Action=st`|Het bericht is omzeild.|
|`Action=sy`|Het bericht is omzeild.|
|`Action=ni`|Het bericht is afgewezen.|
|`Action=ne`|Het bericht is afgewezen.|
|`Action=b`|Het bericht is geblokkeerd.|
|`Name=<malware>`|De naam van de malware die werd gedetecteerd.|
|`File=<filename>`|De naam van het bestand dat de malware bevatte.|

Een voorbeeld **custom_data** waarde voor een bericht dat malware bevat ziet er als volgt uit:

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>Transportregel agent

Een **custom_data** waarde die begint met `S:TRA` is van de Transport Rule agent voor e-mail flow regels (ook wel bekend als transportregels). De belangrijkste details worden beschreven in de volgende tabel:

|**Value**|**Beschrijving**|
|:-----|:-----|
|`ETR|ruleId=<guid>`|De regel-ID die is gekoppeld.|
|`St=<datetime>`|De datum en tijd in UTC wanneer de regelmatch heeft plaatsgevonden.|
|`Action=<ActionDefinition>`|De actie die is toegepast. Zie Acties van de [e-mailstroomregel in Exchange Online voor](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)een lijst met beschikbare acties.|
|`Mode=<Mode>`|De wijze van de regel. Geldige waarden zijn: <br/>* **Afdwingen**: Alle acties op de regel worden afgedwongen. <br/>* **Test met beleidstips:**: Er worden beleidstipacties verzonden, maar andere handhavingsacties worden niet uitgevoerd. <br/>* **Test zonder beleidstips**: Acties worden vermeld in een logboekbestand, maar afzenders worden op geen enkele manier op de hoogte gesteld en er wordt niet op handhavingsacties gereageerd.|

Een voorbeeld **custom_data** waarde voor een bericht dat overeenkomt met de voorwaarden van een e-mailstroomregel ziet er als volgt uit:

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
