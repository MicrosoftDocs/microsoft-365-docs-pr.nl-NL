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
description: Beheerders kunnen berichttracering gebruiken in het Security & Compliance Center om erachter te komen wat er met berichten is gebeurd.
ms.openlocfilehash: 12600eeb5242f0de5fc187be81b9311d4f9cb645
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635314"
---
# <a name="message-trace-in-the-security--compliance-center"></a>Berichttracering in het Beveiligings- en compliancecentrum

## <a name="overview"></a>Overzicht

Berichttracering in het Security & Compliance Center volgt e-mailberichten terwijl ze door uw Exchange Online-organisatie reizen. U bepalen of een bericht is ontvangen, geweigerd, uitgesteld of geleverd door de service. Het laat ook zien welke acties werden ondernomen op het bericht voordat het zijn definitieve status bereikte.

Berichttracering in het Beveiligings& Compliance Center verbetert de oorspronkelijke berichttracering die beschikbaar was in het Exchange-beheercentrum (EAC). U de informatie uit berichttracering gebruiken om vragen van gebruikers over wat er met berichten is gebeurd efficiënt te beantwoorden, problemen met de e-mailstroom op te lossen en beleidswijzigingen te valideren.

> [!NOTE]
> * Als u een berichttracering wilt uitvoeren, moet u lid zijn van de rolgroepen Organisatiebeheer, Compliance Management of Helpdesk. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie. <br/><br/>* Het maximum aantal berichten dat in de resultaten wordt weergegeven, is afhankelijk van het geselecteerde rapporttype (zie de sectie [Rapporttype kiezen](#choose-report-type) voor meer informatie). De [Get-HistoricalSearch-cmdlet](https://docs.microsoft.com/powershell/module/exchange/reporting/get-historicalsearch) in Exchange Online PowerShell of Exchange Online Protection PowerShell retourneert alle berichten in de resultaten.

## <a name="open-message-trace"></a>Berichttracering openen

1. Open het Security & <https://protection.office.com>Compliance Center op .

2. Vouw **de e-mailstroom**uit en selecteer **vervolgens Berichttracering**.

## <a name="message-trace-page"></a>Berichttraceringspagina

Vanaf hier u een nieuw standaardtraceringsspoor starten door op de knop **Een traceerknop starten** te klikken. Hiermee wordt gezocht naar alle berichten voor alle afzenders en ontvangers van de afgelopen twee dagen. U ook een van de opgeslagen query's uit de beschikbare querycategorieën gebruiken en deze uitvoeren als uitgangspunt of deze gebruiken als uitgangspunt voor uw eigen query's:

- **Standaardquery's:** ingebouwde query's van Office 365.

- **Aangepaste query's:** query's die zijn opgeslagen door beheerders in uw organisatie voor toekomstig gebruik.

- **Automatisch opgeslagen query's**: De laatste tien meest recent uitgevoerd query's. Deze lijst maakt het eenvoudig om verder te gaan waar je gebleven was.

Ook op deze pagina is een **downloadbare rapporten** sectie voor de verzoeken die u hebt ingediend, evenals de rapporten zelf wanneer er beschikbaar zijn om te downloaden.

## <a name="options-for-a-new-message-trace"></a>Opties voor een nieuw berichttracering

### <a name="filter-by-senders-and-recipients"></a>Filteren op afzenders en ontvangers

De standaardwaarden zijn **Alle afzenders** en Alle **geadresseerden**, maar u de volgende velden gebruiken om de resultaten te filteren:

- **Door deze personen**: Klik in dit veld om een of meer afzenders uit uw organisatie te selecteren. U ook beginnen met het typen van een naam en de items in de lijst worden gefilterd op wat u hebt getypt, net als hoe een zoekpagina zich gedraagt.

- **Voor deze personen**: Klik in dit veld om een of meer ontvangers in uw organisatie te selecteren.

> [!NOTE]
> U ook de e-mailadressen van externe afzenders en ontvangers typen. Jokertekens worden ondersteund (bijvoorbeeld `*@contoso.com`), maar u niet meerdere wildcard-items tegelijk in hetzelfde veld gebruiken. <br/><br/> U meerdere afzenders of ontvangerslijsten plakken, gescheiden door puntkomma's (`;`). spaties`\s`( ),`\r`vervoer keert`\n`terug ( ) of volgende regels ( ).

### <a name="time-range"></a>Tijdbereik

De standaardwaarde is **2 dagen,** maar u datum-/tijdbereiken van maximaal 90 dagen opgeven. Wanneer u datum-/tijdsbereiken gebruikt, moet u rekening houden met de volgende problemen:

- Standaard selecteert u het tijdsbereik in de **schuifregelaarweergave** met behulp van een tijdregel. U alleen de dag- of tijdinstellingen selecteren die worden weergegeven. Als u een tussenwaarde probeert te selecteren, wordt de start-/eindbel uitgelijnd op de dichtstbijzijnde weergegeven instelling.

  ![Een tijdsbereik voor schuifregelaars in een nieuw berichttracering in het Beveiligings& Compliance Center](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  U echter ook overschakelen naar **aangepaste** weergave waar u de **waarden begindatum** en **einddatum** (inclusief tijden) opgeven en u ook de **tijdzone** voor het datum-/tijdbereik selecteren. Houd er rekening mee dat de instelling **Tijdzone** van toepassing is op zowel uw query-invoer als uw queryresultaten.

  ![Een aangepast tijdsbereik in een nieuw berichttracering in het Beveiligingscentrum & Compliance Center](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  Gedurende 10 dagen of minder zijn de resultaten direct beschikbaar als **overzichtsrapport.** Als u een tijdsbereik opgeeft dat zelfs iets langer is dan 10 dagen, worden de resultaten vertraagd omdat ze alleen beschikbaar zijn als een downloadbaar CSV-bestand **(uitgebreide samenvatting** of **uitgebreide** rapporten).

  Zie de sectie [Rapporttype kiezen](#choose-report-type) in dit onderwerp voor meer informatie over de verschillende rapporttypen.

  **Opmerking:** Uitgebreide samenvattingen en uitgebreide rapporten worden opgesteld met behulp van gearchiveerde berichttraceringsgegevens en het kan enkele uren duren voordat uw rapport kan worden gedownload. Afhankelijk van het aantal andere beheerders dat rond dezelfde tijd ook rapportaanvragen heeft ingediend, u ook een vertraging opmerken voordat de verwerking voor uw aanvraag in de wachtrij wordt gestart.

- Als u een query opslaat in de **weergave Schuifregelaar,** wordt het relatieve tijdsbereik opgeslagen (bijvoorbeeld drie dagen vanaf vandaag). Als u een query opslaat in **de aangepaste** weergave, wordt het absolute datum-/tijdbereik opgeslagen (bijvoorbeeld 2018-05-06 13:00 tot 2018-05-08 18:00).

### <a name="more-search-options"></a>Meer zoekopties

#### <a name="delivery-status"></a>Leveringsstatus

U de standaardwaarde **Alles** geselecteerd laten of u een van de volgende waarden selecteren om de resultaten te filteren:

- **Geleverd**: Het bericht is met succes afgeleverd op de beoogde bestemming.

- **In behandeling**: Levering van het bericht wordt geprobeerd of opnieuw geprobeerd.

- **Uitgebreid**: Een ontvanger van een distributiegroep is uitgebreid voordat deze werd geleverd aan de afzonderlijke leden van de groep.

- **Mislukt:** het bericht is niet bezorgd.

- **In quarantaine :** het bericht is in quarantaine geplaatst (als spam, bulkmail of phishing). Zie [E-mailberichten in quarantaine in Office 365](quarantine-email-messages.md)voor meer informatie.

- **Gefilterd als spam**: het bericht is geïdentificeerd als spam en is geweigerd of geblokkeerd (niet in quarantaine geplaatst).

- **Status verkrijgen:** Het bericht is onlangs ontvangen door Office 365, maar er zijn nog geen andere statusgegevens beschikbaar. Kom over een paar minuten terug.

**Opmerking:** De waarden **in behandeling,** **in quarantaine**en filter als **spam** zijn alleen beschikbaar voor zoekopdrachten van minder dan 10 dagen. Ook kan er een 5 tot 10 minuten vertraging tussen de werkelijke en gerapporteerde leveringsstatus.

#### <a name="message-id"></a>Bericht-id

Dit is de internetbericht-id (ook wel client-id genoemd) die wordt gevonden in het **veld Message-ID:** header in de berichtkop. Gebruikers kunnen u deze waarde geven om specifieke berichten te onderzoeken.

Deze waarde is constant voor de levensduur van het bericht. Voor berichten die zijn gemaakt in Microsoft 365 `<GUID@ServerFQDN>`of Exchange, is\< \>de waarde in de indeling , inclusief de hoekhaakjes ( ). Bijvoorbeeld `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Andere berichtensystemen kunnen verschillende syntaxis of waarden gebruiken. Deze waarde wordt verondersteld uniek te zijn, maar niet alle e-mailsystemen strikt volgen deze eis. Als het **veld Message-ID:** header niet bestaat of leeg is voor binnenkomende berichten van externe bronnen, wordt een willekeurige waarde toegewezen.

Wanneer u **Message ID** gebruikt om de resultaten te filteren, moet u de volledige tekenreeks opnemen, inclusief eventuele hoekhaakjes.

#### <a name="direction"></a>Richting

U de standaardwaarde **All** selected laten, of u **Binnenkomend** (berichten die naar ontvangers in uw organisatie worden verzonden) of **Uitgaand** (berichten verzonden van gebruikers in uw organisatie) selecteren om de resultaten te filteren.

#### <a name="original-client-ip-address"></a>Oorspronkelijke IP-adres van de client

U de resultaten per IP-adres van de client bestanden om gehackte computers die het verzenden van grote hoeveelheden spam of malware te onderzoeken. Hoewel de berichten mogelijk afkomstig lijken te zijn van meerdere afzenders, is het waarschijnlijk dat dezelfde computer alle berichten genereert.

**Opmerking:** De IP-adresgegevens van de client zijn slechts 10 dagen beschikbaar en zijn alleen beschikbaar in de **uitgebreide samenvatting** of **uitgebreide** rapporten (downloadbare CSV-bestanden).

### <a name="choose-report-type"></a>Rapporttype kiezen

De beschikbare rapporttypen zijn:

- **Samenvatting**: Beschikbaar als het tijdsbereik minder dan 10 dagen is en geen extra filteropties vereist. De resultaten zijn vrijwel direct na het klikken op **Zoeken**beschikbaar. Het rapport levert tot 20000 resultaten op.

- **Verbeterd overzicht** of **uitgebreid:** deze rapporten zijn alleen beschikbaar als downloadbare CSV-bestanden en vereisen een of meer van de volgende filteropties, ongeacht het tijdsbereik: **Door deze personen**, Aan deze **personen**of **Bericht-ID**. U jokertekens gebruiken voor de afzenders \*of de ontvangers (bijvoorbeeld @contoso.com). Het uitgebreide overzichtsrapport retourneert tot 50000 resultaten. Het uitgebreide rapport retourneert maximaal 1000 resultaten.

**Opmerkingen**:

- Verbeterde samenvatting en uitgebreide rapporten worden opgesteld met behulp van gearchiveerde berichttraceringsgegevens en het kan enkele uren duren voordat uw rapport beschikbaar is om te downloaden. Afhankelijk van het aantal andere beheerders dat rond dezelfde tijd ook rapportaanvragen heeft ingediend, ziet u mogelijk ook een vertraging voordat uw aanvraag in de wachtrij wordt verwerkt.

- Hoewel u een uitgebreid overzicht of uitgebreid rapport selecteren voor een datum/tijdsbereik, zijn de laatste vier uur van gearchiveerde gegevens meestal nog niet beschikbaar voor deze twee typen rapporten.

Wanneer u op **Volgende**klikt, krijgt u een overzichtspagina te zien met de filteropties die u hebt geselecteerd, een unieke (bewerkbare) titel voor het rapport en het e-mailadres dat de melding ontvangt wanneer de berichttracering is voltooid (ook bewerkbaar en moet deze zich in een van de geaccepteerde domeinen van uw organisatie bevinden). Klik **op Rapport voorbereiden** om de berichttracering in te dienen. Op de hoofdpagina **van berichttracering** ziet u de status van het rapport in de sectie **Downloadbare rapporten.**

Zie de volgende sectie voor meer informatie over de informatie die is geretourneerd in de verschillende rapporttypen.

## <a name="message-trace-results"></a>Resultaten van berichttracering

De verschillende rapporttypen geven verschillende niveaus van informatie weer. De informatie die beschikbaar is in de verschillende rapporten wordt beschreven in de volgende secties.

### <a name="summary-report-output"></a>Samenvatting rapport uitvoer

Na het uitvoeren van de berichttracering worden de resultaten weergegeven, gesorteerd op aflopende datum/tijd (meest recente eerste).

![Overzichtsrapportresultaten voor berichttracering in het Security & Compliance Center](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

Het samenvattende rapport bevat de volgende informatie:

- **Datum**: de datum en het tijdstip waarop het bericht door de service is ontvangen, met behulp van de geconfigureerde UTC-tijdzone.

- **Afzender**: Het e-mailadres van de afzender *(aliasdomein).*@*domain*

- **Ontvanger:** het e-mailadres van de ontvanger of ontvangers. Voor een bericht dat naar meerdere ontvangers wordt verzonden, is er één regel per ontvanger. Als de ontvanger een distributiegroep, dynamische distributiegroep of beveiligingsgroep met e-mail is, is de groep de eerste ontvanger en bevindt elk lid van de groep zich op een aparte regel.

- **Onderwerp**: De eerste 256 tekens van het onderwerp van het **bericht:** veld.

- **Status:** deze waarden worden beschreven in de sectie [Leveringsstatus.](#delivery-status)

Standaard worden de eerste 250 resultaten geladen en direct beschikbaar. Wanneer u naar beneden scrolt, is er een kleine pauze als de volgende batch van de resultaten worden geladen. In plaats van te scrollen, u op **Alles laden** klikken om alle resultaten tot maximaal 10.000 te laden.

U op de kolomkoppen klikken om de resultaten te sorteren op de waarden in die kolom in oplopende of aflopende volgorde.

U op **Resultaten filteren** klikken om de resultaten te filteren op een of meer kolommen.

U de resultaten exporteren nadat u een of meer rijen hebt geselecteerd door op **Resultaten exporteren** te klikken en vervolgens Alle **resultaten exporteren,** **Geladen resultaten exporteren**of **Geselecteerd exporteren**.

#### <a name="find-related-records-for-this-message"></a>Gerelateerde records voor dit bericht zoeken

Gerelateerde berichtenrecords zijn records die dezelfde Berichten-id hebben gedeeld. Vergeet niet dat zelfs een enkel bericht dat tussen twee personen wordt verzonden, meerdere records kan genereren. Het aantal records neemt toe wanneer het bericht wordt beïnvloed door uitbreiding van de distributiegroep, doorsturen, regels voor e-mailstromen (ook wel transportregels genoemd), enz.

Nadat u het selectievakje Een rij hebt inschakelt, u gerelateerde records voor het bericht zoeken](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> door te klikken op de knop **Gerelateerde zoeken** die wordt weergegeven of door Meer **opties** ![te selecteren Meer Gerelateerde records zoeken voor dit **bericht**).

Zie de sectie Bericht-id eerder in dit onderwerp voor meer informatie over de Berichten-id.

#### <a name="message-trace-details"></a>Details van berichttracering

In de uitvoer van het overzichtsrapport u details over een bericht weergeven met behulp van een van de volgende methoden:

- Schakel de rij in (klik ergens in de rij behalve in het selectievakje).

- Schakel het selectievakje rij in en](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> klik op **Meer opties** ![ **Meer berichtdetails weergeven**.

   ![Details na het dubbelklikken op een rij in het overzichtsrapport traceerresultaten in het Security & Compliance Center](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

De details van de berichttracering bevatten de volgende aanvullende informatie die niet in het samenvattende rapport aanwezig is:

- **Berichtgebeurtenissen:** deze sectie bevat classificaties die helpen bij het categoriseren van de acties die de service onderneemt op berichten. **Enkele van de meer interessante gebeurtenissen** die u zou kunnen tegenkomen zijn:

  - **Ontvangen**: Het bericht is ontvangen door de service.

  - **Verzenden:** het bericht is verzonden door de service.

  - **Mislukt:** het bericht kan niet worden bezorgd.

  - **Leveren:** het bericht is bezorgd in een postvak.

  - **Uitvouwen:** het bericht is verzonden naar een distributiegroep die is uitgebreid.

  - **Overdracht:** ontvangers zijn verplaatst naar een dubbelcated bericht vanwege inhoudsconversie, limieten voor berichtontvangers of agents.

  - **Uitstellen**: De bezorging van het bericht is uitgesteld en kan later opnieuw worden geprobeerd.

  - **Opgelost:** het bericht is doorgestuurd naar een nieuw adres voor geadresseerden op basis van een Active Directory-opzoekadres. Wanneer dit gebeurt, wordt het oorspronkelijke geadresseerdeadres in een afzonderlijke rij in het berichttrace met de uiteindelijke leveringsstatus voor het bericht weergegeven.

  Opmerkingen:

  - Een saai bericht dat is afgeleverd, genereert meerdere **gebeurtenisvermeldingen** in het berichttracering.

  - Deze lijst is niet bedoeld als volledig. Zie [Gebeurtenistypen in het logboek voor het bijhouden](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)van berichten voor beschrijvingen van meer gebeurtenissen . Houd er rekening mee dat deze koppeling een Exchange Server-onderwerp (on-premises Exchange) is.

- **Meer informatie**: Deze sectie bevat de volgende details:

  - **Bericht-id:** deze waarde wordt eerder in dit onderwerp beschreven in de sectie [Bericht-id.](#message-id) Bijvoorbeeld `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

  - **Berichtgrootte**

  - **Vanaf IP**: Het IP-adres van de computer die het bericht heeft verzonden. Voor uitgaande berichten die vanuit Exchange Online worden verzonden, is deze waarde leeg.

  - **Naar IP:** het IP-adres of adressen waar de service het bericht probeerde af te leveren. Als het bericht meerdere geadresseerden heeft, worden deze weergegeven. Voor binnenkomende berichten die naar Exchange Online worden verzonden, is deze waarde leeg.

### <a name="enhanced-summary-reports"></a>Uitgebreide overzichtsrapporten

Beschikbare (voltooide) uitgebreide overzichtsrapporten zijn beschikbaar in de sectie **Downloadbare rapporten** bij het traceren van het beginbericht. De volgende informatie is beschikbaar in het rapport:

- **origin_timestamp**<sup>*</sup>: De datum en tijd waarop het bericht in eerste instantie door de service is ontvangen, met behulp van de geconfigureerde UTC-tijdzone.

- **sender_address**: Het e-mailadres van de afzender *(aliasdomein).*@*domain*

- **Recipient_status**: De status van de levering van het bericht aan de ontvanger. Als het bericht naar meerdere ontvangers is verzonden, worden alle ontvangers en \<de bijbehorende status voor elk bericht weergegeven in de indeling:\>##\< *e-mailadresstatus**status*\>. Bijvoorbeeld:

  - **##Receive, Verzenden** betekent dat het bericht is ontvangen door de service en naar de beoogde bestemming is verzonden.

  - **##Receive, betekent mislukt** dat het bericht is ontvangen door de service, maar de levering aan de beoogde bestemming is mislukt.

  - **##Receive, Deliver** betekent dat het bericht is ontvangen door de service en is bezorgd in de mailbox van de ontvanger.

- **message_subject**: De eerste 256 tekens van het **veld Onderwerp** van het bericht.

- **total_bytes:** de grootte van het bericht in bytes, inclusief bijlagen.

- **message_id:** Deze waarde wordt eerder in dit onderwerp beschreven in de sectie [Bericht-id.](#message-id) Bijvoorbeeld `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

- **network_message_id:** een unieke bericht-id-waarde die vooralle kopieën van het bericht blijft bestaan dat mogelijk wordt gemaakt vanwege uitbreiding van de splitsing of distributiegroep. Een voorbeeldwaarde `1341ac7b13fb42ab4d4408cf7f55890f`is .

- **original_client_ip**: Het IP-adres van de client van de afzender.

- **directionaliteit:** geeft aan of het bericht binnenkomend (1) naar uw organisatie is verzonden of dat het uitgaande (2) is verzonden vanuit uw organisatie.

- **connector_id**: De naam van de bron- of doelconnector. Zie [E-mailstroom configureren met connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)voor meer informatie over connectors in Exchange Online.

- **delivery_priority:**<sup>*</sup>Of het bericht is verzonden met **de**hoogste, **lage**of **normale** prioriteit.

<sup>*</sup>Deze eigenschappen zijn alleen beschikbaar in uitgebreide overzichtsrapporten.

### <a name="extended-reports"></a>Uitgebreide rapporten

Beschikbare (voltooide) uitgebreide rapporten zijn beschikbaar in de sectie **Downloadbare rapporten** aan het begin van de berichtentracering. Vrijwel alle informatie uit een uitgebreid samenvattend rapport is beschikbaar in een uitgebreid rapport (met uitzondering van **origin_timestamp** en **delivery_priority).** De volgende aanvullende informatie is alleen beschikbaar in een uitgebreid rapport:

- **client_ip:** het IP-adres van de e-mailserver of berichtenclient die het bericht heeft verzonden.

- **client_hostname:** de hostnaam of FQDN van de e-mailserver of berichtenclient die het bericht heeft verzonden.

- **server_ip**: Het IP-adres van de bron- of doelserver.

- **server_hostname**: De hostnaam of FQDN van de doelserver.

- **source_context**: Extra informatie in verband met het **bronveld.** Bijvoorbeeld:

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **bron:** De Exchange Online-component die verantwoordelijk is voor het evenement. Bijvoorbeeld:

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id:** deze komen overeen met de waarden van de **gebeurtenis Bericht** die worden uitgelegd in de sectie Gerelateerde records zoeken voor [dit bericht.](#find-related-records-for-this-message)

- **internal_message_id:** een bericht-id die is toegewezen door de Exchange Online-server die het bericht momenteel verwerkt.

- **recipient_address**: De e-mailadressen van de geadresseerden van het bericht. Meerdere e-mailadressen worden gescheiden door het puntkommateken (;).

- **recipient_count:** het totale aantal ontvangers in het bericht.

- **related_recipient_address**: `EXPAND`Wordt `REDIRECT`gebruikt `RESOLVE` met , en gebeurtenissen om andere e-mailadressen van ontvangers weer te geven die aan het bericht zijn gekoppeld.

- **referentie**: Dit veld bevat aanvullende informatie voor specifieke soorten gebeurtenissen. Bijvoorbeeld:

  - **DSN**: Bevat de rapportkoppeling, de **message_id** waarde van de bijbehorende melding van de leveringsstatus (ook wel dsn, niet-leveringsrapport, NDR of bouncebericht genoemd) als een DSN na deze gebeurtenis wordt gegenereerd. Als dit een DSN-bericht is, bevat dit veld de **message_id** waarde van het oorspronkelijke bericht waarvoor het DSN is gegenereerd.

  - **UITvouwen**: Bevat de **related_recipient_address** waarde van de gerelateerde berichten.

  - **ONTVANGEN:** Kan de **message_id** waarde van het gerelateerde bericht bevatten als het bericht is gegenereerd door andere processen (bijvoorbeeld regels in postvak IN).

  - **SEND:** Bevat de **internal_message_id** waarde van alle DSN-berichten.

  - **OVERDRACHT:** bevat de **internal_message_id** waarde van het bericht dat wordt gevorkt (bijvoorbeeld door inhoudsconversie, limieten voor berichtontvangers of agents).

  - **POSTVAKREGEL:** bevat de **internal_message_id** waarde van het binnenkomende bericht waardoor de regel Postvak IN het uitgaande bericht genereert.

    Voor andere soorten gebeurtenissen is dit veld meestal leeg.

- **return_path:** het retoure-mailadres dat is opgegeven door de opdracht **MAIL FROM** die het bericht heeft verzonden. Hoewel dit veld nooit leeg is, kan de waarde `<>`van het null-afzenderadres worden weergegeven als .

- **message_info**: Aanvullende informatie over het bericht. Bijvoorbeeld:

  - De datumdatum van het bericht `DELIVER` `SEND` in UTC voor en gebeurtenissen. De datumvan oorsprong is het tijdstip waarop het bericht voor het eerst de Exchange Online-organisatie is binnengekomen. De UTC-datumtijd `yyyy-mm-ddThh:mm:ss.fffZ`wordt weergegeven in de datumtijdnotatie ISO `yyyy` 8601: , waar `mm` = jaar, = maand, `dd` = `T` dag, het begin van de tijdcomponent aangeeft, `hh` = uur, `mm` = minuut, `ss` = seconde, `fff` = fracties van een seconde, en `Z` betekent , wat een andere manier is om UTC aan te duiden. `Zulu`

  - Verificatiefouten. U ziet bijvoorbeeld de `11a` waarde en het type verificatie dat is gebruikt toen de verificatiefout is opgetreden.

- **tenant_id**: een GUID-waarde die de Exchange `39238e87-b5ab-4ef6-a559-af54c6b07b42`Online-organisatie vertegenwoordigt (bijvoorbeeld ).

- **original_server_ip**: Het IP-adres van de oorspronkelijke server.

- **custom_data**: Bevat gegevens met betrekking tot specifieke gebeurtenistypen. Zie de volgende secties voor meer informatie.

#### <a name="custom_data-values"></a>custom_data waarden

Het **custom_data** veld `AGENTINFO` voor een gebeurtenis wordt gebruikt door verschillende Exchange Online-medewerkers om gegevens te registreren over het verwerken van berichten. Enkele van de meer interessante agenten worden beschreven in de volgende secties.

#### <a name="spam-filter-agent"></a>Spamfilteragent

Een **custom_data** waarde `S:SFA` die begint met is van de spam filter agent. De belangrijkste details worden beschreven in de volgende tabel:

|**Value**|**Beschrijving**|
|:-----|:-----|
|`SFV=NSPM`|Het bericht is gemarkeerd als niet-spam en is verzonden naar de beoogde ontvangers.|
|`SFV=SPM`|Het bericht is gemarkeerd als spam door het inhoudsfilter.|
|`SFV=BLK`|Filteren is overgeslagen en het bericht is geblokkeerd omdat het afkomstig is van een geblokkeerde afzender.|
|`SFV=SKS`|Het bericht is gemarkeerd als spam voordat het werd verwerkt door het inhoudsfilter. Dit geldt ook voor berichten waarin het bericht overeenging met een transportregel om het automatisch te markeren als spam en alle extra filtering te omzeilen.|
|`SCL=<number>`|Zie [Spamvertrouwensniveaus](spam-confidence-levels.md)voor meer informatie over de verschillende SCL-waarden en wat ze betekenen.|
|`PCL=<number>`|De waarde van het phishingvertrouwensniveau (PCL) van het bericht. Deze kunnen op dezelfde manier worden geïnterpreteerd als de SCL-waarden die zijn gedocumenteerd in [het vertrouwen van spamniveaus.](spam-confidence-levels.md)|
|`DI=SB`|De afzender van het bericht is geblokkeerd.|
|`DI=SQ`|Het bericht is in quarantaine geplaatst.|
|`DI=SD`|Het bericht is verwijderd.|
|`DI=SJ`|Het bericht is verzonden naar de map Ongewenste e-mail van de ontvanger.|
|`DI=SN`|Het bericht is doorgestuurd via de normale uitgaande bezorgpool.|
|`DI=SO`|Het bericht is doorgestuurd via de groep voor levering met een hoger risico. Zie groep voor levering met [een hoog risico voor uitgaande berichten voor](high-risk-delivery-pool-for-outbound-messages.md)meer informatie .|
|`SFS=[a]|SFS=[b]`|Dit geeft aan dat spamregels zijn geëvenaard.|
|`IPV=CAL`|Het bericht is toegestaan via de spamfilters omdat het IP-adres is opgegeven in een lijst met IP-toestaan in het verbindingsfilter.|
|`H=<EHLOstring>`|De HELO- of EHLO-tekenreeks van de verbindende e-mailserver.|
|`PTR=<ReverseDNS>`|De PTR-record van het verzendende IP-adres, ook wel bekend als het omgekeerde DNS-adres.|

Een voorbeeld **custom_data** waarde voor een bericht dat is gefilterd op spam als volgt:

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>Malwarefilteragent

Een **custom_data** waarde `S:AMA` die begint met is van de malware filter agent. De belangrijkste details worden beschreven in de volgende tabel:

|**Value**|**Beschrijving**|
|:-----|:-----|
|`AMA=SUM|v=1|`Of`AMA=EV|v=1`|Het bericht was vastbesloten om malware te bevatten. `SUM`geeft aan dat de malware kan zijn gedetecteerd door een willekeurig aantal motoren. `EV`geeft aan dat de malware is gedetecteerd door een specifieke engine. Wanneer malware wordt gedetecteerd door een motor activeert dit de volgende acties.|
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

Een **custom_data** waarde`S:TRA` die begint met is van de transportregel agent voor mail flow regels (ook wel bekend als transport regels). De belangrijkste details worden beschreven in de volgende tabel:

|**Value**|**Beschrijving**|
|:-----|:-----|
|`ETR|ruleId=<guid>`|De regel-ID die is geëvenaard.|
|`St=<datetime>`|De datum en tijd in UTC wanneer de regelovereenkomst heeft plaatsgevonden.|
|`Action=<ActionDefinition>`|De actie die werd toegepast. Zie Acties voor [e-mailstroomregel in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor een lijst met beschikbare acties.|
|`Mode=<Mode>`|De wijze van de regel. Geldige waarden zijn: <br/>* **Handhaving:** Alle acties op de regel worden afgedwongen. <br/>* **Test met beleidstips:**: Acties met beleidstips worden verzonden, maar er wordt niet op andere handhavingsacties gereageerd. <br/>* **Test zonder beleidstips:** Acties worden weergegeven in een logboekbestand, maar afzenders worden op geen enkele manier op de hoogte gebracht en er wordt niet op handhavingsacties gereageerd.|

Een voorbeeld **custom_data** waarde voor een bericht dat overeenkomt met de voorwaarden van een regel voor e-mailstroom, ziet er als volgt uit:

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
