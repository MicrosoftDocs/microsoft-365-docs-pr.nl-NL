---
title: Berichttracering in het Beveiligings- en compliancecentrum
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen de functie voor bericht tracering gebruiken in het beveiligings & nalevings centrum om erachter te komen wat er is gebeurd met berichten.
ms.openlocfilehash: 46aa454ff709e9b17c3b18992757a9a4c3a51247
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616750"
---
# <a name="message-trace-in-the-security--compliance-center"></a>Berichttracering in het Beveiligings- en compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="message-trace-features"></a>Functies voor bericht tracering

Bericht tracering in het beveiligings & compliance volgen worden e-mailberichten verzonden wanneer ze worden verzonden via uw Exchange Online-organisatie. U kunt bepalen of een bericht is ontvangen, afgewezen, uitgesteld of geleverd door de service. Ook ziet u welke acties zijn uitgevoerd op het bericht voordat het de definitieve status bereikte.

Bericht tracering in het nalevings centrum voor beveiliging & verbetert de oorspronkelijke bericht tracering die beschikbaar is in het Exchange Admin Center (SBV). U kunt de gegevens van de bericht tracering gebruiken om op efficiënte wijze vragen van gebruikers te beantwoorden over wat er is gebeurd met berichten, problemen met de e-mail stroom oplossen en beleidswijzigingen valideren.

> [!NOTE]
>
> - Als u een bericht tracering wilt uitvoeren, moet u lid zijn van de rollen groepen Organisatiebeheer, Compliance Management of Help Desk. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.
>
> - De maximale hoeveelheid berichten die in de resultaten worden weergegeven, is afhankelijk van het type rapport dat u hebt geselecteerd (Zie de sectie [Rapporttype kiezen](#choose-report-type) voor meer informatie). Met de cmdlet [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) in Exchange Online PowerShell of zelfstandige EOP PowerShell worden alle berichten in de resultaten als resultaat gegeven.

## <a name="open-message-trace"></a>Bericht tracering openen

1. Open het beveiligings & nalevings centrum op <https://protection.office.com> .

2. Vouw de **e-mail stroom** uit en selecteer vervolgens **bericht traceren**.

## <a name="message-trace-page"></a>Pagina bericht traceren

Van hieruit kunt u een nieuwe standaardtracering starten door te klikken op de knop **een spoor starten** . Hiermee wordt gezocht naar alle berichten voor alle afzenders en geadresseerden voor de afgelopen twee dagen. U kunt ook een van de opgeslagen query's uit de beschikbare query categorieën gebruiken en deze vervolgens als uitgangspunt gebruiken als uitgangspunt voor uw eigen query's:

- **Standaardquery's**: ingebouwde Query's van microsoft 365.

- **Aangepaste query's**: query's die zijn opgeslagen door beheerders in uw organisatie voor toekomstig gebruik.

- Voor het uitvoeren van **query's die niet zijn opgeslagen**: de laatste tien meest recente query's. In deze lijst kunt u eenvoudig verdergaan waar u gebleven was.

Op deze pagina vindt u een sectie met **downloadbare rapporten** voor de verzoeken die u hebt ingediend, en de rapporten zelf wanneer ze kunnen worden gedownload.

## <a name="options-for-a-new-message-trace"></a>Opties voor een nieuwe bericht tracering

### <a name="filter-by-senders-and-recipients"></a>Filteren op afzenders en geadresseerden

De standaardwaarden zijn **alle afzenders** en **alle geadresseerden**, maar u kunt de volgende velden gebruiken om de resultaten te filteren:

- **Door deze personen**: Klik in dit veld om een of meer afzenders van uw organisatie te selecteren. U kunt ook een naam typen en de items in de lijst worden gefilterd door wat u hebt getypt, net zoals een zoekpagina.

- **Voor deze personen**: Klik in dit veld om een of meer geadresseerden in uw organisatie te selecteren.

> [!NOTE]
>
> - U kunt ook de e-mailadressen van externe afzenders en geadresseerden typen. Jokertekens worden ondersteund (bijvoorbeeld `*@contoso.com` ), maar u kunt niet meerdere jokertekens gebruiken in hetzelfde veld.
>
> - U kunt meerdere lijsten van afzenders of geadresseerden plakken, gescheiden door puntkomma's ( `;` ). spaties ( `\s` ), regeleinden ( `\r` ) of volgende regels ( `\n` ).

### <a name="time-range"></a>Tijdsbereik

De standaardwaarde is **2 dagen**, maar u kunt datum/tijd-bereiken opgeven van maximaal 90 dagen. Wanneer u datum/tijd-bereiken gebruikt, kunt u het volgende doen:

- Standaard selecteert u het tijdsbereik in de **schuifregelaar** met een tijdlijn. U kunt alleen de dag-en tijdinstellingen selecteren die worden weergegeven. Als u probeert een in-tussen waarde te selecteren, wordt de Bel begin/einde uitgelijnd met de dichtstbijzijnde weergegeven instelling.

  ![Een bereik van de schuifregelaar in het beveiligings & nalevings centrum](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  U kunt ook overschakelen naar een **aangepaste** weergave, waarin u de waarden voor de **begindatum** en de **einddatum** kunt opgeven (waaronder tijden), en u kunt ook de **Tijdzone** voor het datum/tijd-bereik selecteren. Houd er rekening mee dat de **Tijdzone** instelling van toepassing is op zowel de query-invoer als de queryresultaten.

  ![Een aangepast tijdsbereik in een nieuwe bericht tracering in het nalevings centrum voor beveiligings &](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  Voor 10 dagen of minder zijn de resultaten direct beschikbaar als **overzichts** rapport. Als u een tijdsbereik opgeeft dat nog iets langer is dan 10 dagen, wordt het resultaat vertraagd omdat dit alleen beschikbaar is als het downloadbare CSV-bestand ( **uitgebreide samenvatting** of **uitgebreide** rapporten).

  Zie voor meer informatie over de verschillende soorten rapporten de sectie [Rapporttype kiezen](#choose-report-type) in dit onderwerp.

  **Opmerking**: een uitgebreide samenvatting en uitgebreide rapporten worden gemaakt met behulp van gearchiveerde berichten traceringsgegevens, en het kan tot enkele uren duren voordat het rapport kan worden gedownload. Afhankelijk van het aantal andere beheerders heeft ook een vertraging ingediend voor het uitvoeren van de verwerking voor uw aanvraag in de wachtrij, voordoend.

- Wanneer u een query opslaat in de **Schuif** weergave, wordt het relatieve tijdsbereik opgeslagen (bijvoorbeeld 3 dagen na vandaag). Wanneer u een query opslaat in de **aangepaste** weergave, wordt het absolute datum/tijdbereik opgeslagen, bijvoorbeeld 2018-05-06 13:00 in 2018-05-08 18:00).

### <a name="more-search-options"></a>Meer zoekopties

#### <a name="delivery-status"></a>Leveringsstatus

U kunt de standaardwaarde voor **alle** geselecteerde waarden wijzigen of een van de volgende waarden selecteren om de resultaten te filteren:

- **Bezorgd**: het bericht is afgeleverd op de bestemming.

- **In behandeling**: de bezorging van het bericht wordt (opnieuw) geprobeerd.

- **Uitgebreid**: een ontvanger van een distributiegroep is uitgebreid vóór de levering aan de afzonderlijke leden van de groep.

- **Mislukt**: het bericht is niet bezorgd.

- **Quarantaine**: het bericht is in quarantaine geplaatst (als spam, bulkmail of phishing). Zie voor meer informatie [Gequarantinee e-mailberichten in EOP](quarantine-email-messages.md).

- **Gefilterd als spam**: het bericht heeft spam genoemd, en is geweigerd of geblokkeerd (niet quarantaine).

- **Status verkrijgen:** Het bericht is onlangs ontvangen door Microsoft 365, maar er zijn nog geen statusgegevens beschikbaar. Kom over enkele minuten terug.

**Opmerking**: de waarden **die in behandeling** **zijn**, worden weergegeven en **als spam filteren** , zijn alleen beschikbaar voor zoekopdrachten van minder dan 10 dagen. Er kan ook een 5 tot 10 minuut vertraging zijn tussen de werkelijke en gemelde afleverings status.

#### <a name="message-id"></a>Bericht-id

Dit is de internetbericht-ID (ook wel bekend als de client-ID) die wordt gevonden in het veld **bericht-id:** koptekst in de kop van het bericht. Gebruikers kunnen u deze waarde geven om specifieke berichten te onderzoeken.

Deze waarde is constant voor de levenscyclus van het bericht. Voor berichten die zijn gemaakt in Microsoft 365 of Exchange, heeft de waarde de notatie `<GUID@ServerFQDN>` , inclusief de punthaken ( \< \> ). Bijvoorbeeld `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Voor andere berichtensystemen kunnen verschillende syntaxis waarden worden gebruikt. Deze waarde moet uniek zijn, maar niet op alle e-mail systemen voldoet aan deze vereiste. Als het veld **bericht-id:** geen koptekst bevat of leeg is voor inkomende berichten van externe bronnen, wordt een willekeurige waarde toegewezen.

Wanneer u de **bericht-id** gebruikt om de resultaten te filteren, moet u ervoor zorgen dat u de volledige tekenreeks opneemt, ook geen punthaken.

#### <a name="direction"></a>Richting

U kunt de standaardwaarde **allemaal** selecteren, of u kunt **inkomende** berichten (berichten verzonden naar geadresseerden in uw organisatie) of **uitgaande** berichten (berichten die zijn verzonden door gebruikers in uw organisatie) selecteren om de resultaten te filteren.

#### <a name="original-client-ip-address"></a>Oorspronkelijk IP-adres van client

U kunt de resultaten van client IP addressiseren om gehacke computers te onderzoeken die grote hoeveelheden spam of malware verzenden. Hoewel het lijkt alsof de berichten afkomstig zijn van meerdere afzenders, is het mogelijk dat dezelfde computer alle berichten genereert.

**Opmerking**: de IP-adresgegevens van de client zijn slechts tien dagen beschikbaar en zijn alleen beschikbaar in de **uitgebreide samenvatting** of **uitgebreide** rapporten (downloadbare CSV-bestanden).

### <a name="choose-report-type"></a>Rapporttype kiezen

De beschikbare rapporttypen zijn:

- **Overzicht**: beschikbaar als het tijdsbereik kleiner is dan 10 dagen en geen extra filteropties vereist. De resultaten zijn bijna direct beschikbaar nadat u op **zoeken** hebt geklikt. Het rapport levert tot 20000 resultaten.

- **Uitgebreid overzicht** of **uitgebreid**: deze rapporten zijn alleen beschikbaar als CSV-bestanden die kunnen worden gedownload en u hebt een of meer van de volgende filteropties, ongeacht het tijdsbereik: **door deze personen**, **voor deze personen** of **bericht-id** vereist. U kunt jokertekens gebruiken voor de afzenders of de geadresseerden (bijvoorbeeld \* @contoso. com). Het verbeterde overzichtsrapport levert tot 50000 resultaten. Het uitgebreide rapport levert tot 1000 resultaten.

**Opmerkingen**:

- Uitgebreide samenvattings-en uitgebreide rapporten worden gemaakt met behulp van gearchiveerde berichten traceringsgegevens, en het kan tot enkele uren duren voordat het rapport kan worden gedownload. Afhankelijk van het aantal andere beheerders heeft ook een vertraging voor het verzenden van een aanvraag ingediend, maar u kunt ook een vertraging doen voordat uw aanvraag in de wachtrij wordt verwerkt.

- Hoewel u een uitgebreid overzicht of uitgebreid rapport voor datum/tijd-bereik kunt selecteren, zijn meestal de laatste vier uur gearchiveerde gegevens niet beschikbaar voor deze twee typen rapporten.

Wanneer u op **volgende** klikt, wordt er een overzichtspagina weergegeven met de filteropties die u hebt geselecteerd, een unieke (bewerkbaar) titel voor het rapport en het e-mailadres dat de melding ontvangt wanneer de bericht tracering wordt voltooid (ook in een van de geaccepteerde domeinen van uw organisatie). Klik op **rapport voorbereiden** voor het verzenden van de bericht tracering. Op de hoofdpagina van **bericht tracering** ziet u de status van het rapport in de sectie **downloadbare rapporten** .

Zie de volgende sectie voor meer informatie over de gegevens die worden geretourneerd in de verschillende rapporttypen.

## <a name="message-trace-results"></a>Resultaten van bericht tracering

De verschillende soorten rapporten retourneren verschillende niveaus met informatie. In de volgende secties vindt u een beschrijving van de informatie die beschikbaar is in de verschillende rapporten.

### <a name="summary-report-output"></a>Uitvoer van overzichtsrapport

Na het uitvoeren van de bericht tracering, worden de resultaten weergegeven, gesorteerd op aflopende datum/tijd (nieuwste eerst).

![Resultaten van het overzichtsrapport voor bericht tracering in het Beveiligingscentrum beveiligings &](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

Het overzichtsrapport bevat de volgende informatie:

- **Datum**: de datum en tijd waarop het bericht is ontvangen door de service, volgens de geconfigureerde UTC-tijdzone.

- **Afzender**: het e-mailadres van de afzender (*alias* @ *domein*).

- **Geadresseerde**: het e-mailadres van de ontvanger of geadresseerden. Voor een bericht dat naar meerdere geadresseerden is verzonden, staat er één regel per geadresseerde. Als de ontvanger een distributiegroep, een dynamische distributiegroep of een beveiligingsgroep met e-mail is, is de groep de eerste geadresseerde en moet elk lid van de groep op een afzonderlijke regel worden ingesteld.

- **Onderwerp**: de eerste 256 tekens van het veld **onderwerp:** van het bericht.

- **Status**: deze waarden worden beschreven in de sectie [bezorgings status](#delivery-status) .

De eerste 250 resultaten worden standaard geladen en direct verkrijgbaar. Wanneer u omlaag schuift, wordt er een kleine onderbreking met de volgende batch resultaten geladen. In plaats van schuiven, kunt u op **Alles laden** klikken om alle resultaten van maximaal 10.000 te laden.

U kunt op de kolomkoppen klikken om de resultaten te sorteren op de waarden in deze kolom in oplopende of aflopende volgorde.

U kunt op **resultaten filteren** klikken om de resultaten te filteren op een of meer kolommen.

U kunt de resultaten exporteren nadat u een of meer rijen hebt geselecteerd door te klikken op **resultaten exporteren** en vervolgens **alle resultaten exporteren**, **geladen resultaten exporteren** of **exporteren** selecteren.

#### <a name="find-related-records-for-this-message"></a>Gerelateerde records zoeken voor dit bericht

Gerelateerde berichten records zijn records die dezelfde bericht-ID hebben. Vergeet niet dat er slechts één bericht tussen twee personen kan worden gegenereerd. Het aantal records is groter als het bericht van invloed is op de expansie van distributiegroepen, doorstuur berichten, e-mail stroom regels (ook wel een zogenaamde transportregels genoemd), enzovoort.

Nadat u het selectievakje van een rij hebt geselecteerd, kunt u verwante records voor het bericht vinden door te klikken op de knop **gerelateerde zoeken** die wordt weergegeven, of door **meer opties** ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **voor het zoeken naar gerelateerde records zoeken voor dit bericht** te selecteren.

Zie voor meer informatie over de bericht-ID de sectie bericht-ID eerder in dit onderwerp.

#### <a name="message-trace-details"></a>Details van bericht tracering

U kunt in de uitvoer van het overzichtsrapport Details van een bericht weergeven door een van de volgende methoden te gebruiken:

- Selecteer de rij (Klik ergens in de rij, behalve het selectievakje).

- Schakel het selectievakje van de rij in en klik op meer **Opties** ![ Details van het ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **bericht weergeven**.

   ![Details wanneer u dubbelklikt op een rij in de resultaten van de bericht tracering van het overzichtsrapport in het Beveiligingscentrum voor beveiliging &](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

De details van de bericht tracering bevatten de volgende aanvullende informatie die niet aanwezig is in het overzichtsrapport:

- **Berichtgebeurtenissen**: deze sectie bevat classificaties waarmee de acties worden gecategoriseerd die de service bij berichten aanneemt. **Enkele van de interessantste gebeurtenissen** die u mogelijk ondervindt, zijn:

  - **Ontvangen**: het bericht is ontvangen door de service.

  - **Verzenden**: het bericht is verzonden door de service.

  - **Mislukt**: het bericht kan niet worden bezorgd.

  - **Delivery**: het bericht is afgeleverd in een postvak.

  - **Expand**: het bericht is verzonden naar een distributiegroep die is uitgevouwen.

  - **Overdracht**: geadresseerden zijn verplaatst naar een gesplitst bericht vanwege inhoudsconversie, limieten voor geadresseerden van berichten of agenten.

  - **Defer**: de bezorging van het bericht is uitgesteld en er wordt later mogelijk een nieuwe poging gedaan.

  - **Opgelost**: het bericht wordt doorgestuurd naar een nieuw adres voor de ontvanger op basis van een zoekactie in Active Directory. Wanneer dit wordt weergegeven, wordt het oorspronkelijke adres van de ontvanger in een aparte rij in de bericht tracering weergegeven, samen met de laatste bezorgingsstatus van het bericht.

  Opmerkingen:

  - Als een bericht wordt weergegeven dat met succesvol is afgeleverd, worden er meerdere **gebeurtenissen** in de bericht tracering gegenereerd.

  - Deze lijst is niet volledig bedoeld. Zie [gebeurtenistypen in het logboek voor het bijhouden van berichten](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log)voor beschrijvingen van meer gebeurtenissen. Let op: deze koppeling is een Exchange-Server (on-premises Exchange) onderwerp.

- **Meer informatie**: deze sectie bevat de volgende informatie:

  - **Bericht-id**: deze waarde wordt beschreven in de sectie [bericht-id](#message-id) , eerder in dit onderwerp. Bijvoorbeeld `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

  - **Berichtgrootte**

  - **Van IP**: het IP-adres van de computer die het bericht heeft verzonden. Voor uitgaande berichten verzonden via Exchange Online is deze waarde leeg.

  - **Naar IP**: het IP-adres of de adressen waarop de service heeft geprobeerd het bericht te bezorgen. Als het bericht meerdere geadresseerden heeft, worden deze weergegeven. Voor inkomende berichten die naar Exchange Online worden verzonden, is deze waarde leeg.

### <a name="enhanced-summary-reports"></a>Verbeterde overzichtsrapporten

In het gedeelte **downloadbare rapporten** kunnen beschikbare (voltooide) verbeterde overzichtsrapporten worden weergegeven wanneer u begint met het traceren van berichten. De volgende informatie is beschikbaar in het rapport:

- **origin_timestamp** <sup>*</sup> : de datum en tijd waarop het bericht oorspronkelijk is ontvangen door de service, volgens de geconfigureerde UTC-tijdzone.

- **sender_address**: het e-mailadres van de afzender (*alias* @ *domein*).

- **Recipient_status**: de status van de bezorging van het bericht aan de geadresseerde. Als het bericht naar meerdere geadresseerden is verzonden, worden alle geadresseerden en de bijbehorende status weergegeven in de indeling: \<*email address*\> ## \<*status*\> . Bijvoorbeeld:

  - **# #Receive, verzenden** betekent dat het bericht is ontvangen door de service en naar de bestemming is verzonden.

  - **# #Receive, mislukt** betekent dat het bericht is ontvangen door de service, maar dat de levering voor de bestemming mislukt.

  - **# #Receive, delivert** dit betekent dat het bericht is ontvangen door de service en is bezorgd in het postvak van de geadresseerde.

- **message_subject**: de eerste 256 tekens van het veld **onderwerp** van het bericht.

- **total_bytes**: de grootte van het bericht in bytes, inclusief bijlagen.

- **message_id**: deze waarde wordt beschreven in de sectie [bericht-id](#message-id) , eerder in dit onderwerp. Bijvoorbeeld `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

- **network_message_id**: een unieke id voor de bericht-id die wordt doorgevoerd in alle kopieën van het bericht dat kan worden gemaakt vanwege bifurcation of distributiegroepen. Een voorbeeld van een waarde is `1341ac7b13fb42ab4d4408cf7f55890f` .

- **original_client_ip**: het IP-adres van de client van de afzender.

- **richting**: Hiermee wordt aangegeven of het bericht inkomende (1) naar uw organisatie is verzonden of uitgaande (2) uit uw organisatie is verzonden.

- **connector_id**: de naam van de bron-of doel verbindingslijn. Zie voor meer informatie over connectors in Exchange Online de [e-mail stroom configureren met connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

- **delivery_priority** <sup>*</sup> : of het bericht is verzonden met de prioriteit **hoog**, **laag** of **normaal** .

<sup>*</sup> Deze eigenschappen zijn alleen beschikbaar in uitgebreide overzichtsrapporten.

### <a name="extended-reports"></a>Uitgebreide rapporten

Beschikbare (voltooide) uitgebreide rapporten zijn beschikbaar in de sectie **downloadbare rapporten** , aan het begin van de bericht tracering. Vrijwel alle informatie in een uitgebreid overzichtsrapport is beschikbaar in een uitgebreid rapport (met uitzondering van **origin_timestamp** en **delivery_priority**). De volgende aanvullende informatie is alleen beschikbaar in een uitgebreid rapport:

- **client_ip**: het IP-adres van de e-mailserver of Messaging-client die het bericht heeft ingediend.

- **client_hostname**: de hostnaam of de FQDN-naam van de e-mailserver of de Messaging-client die het bericht heeft ingediend.

- **server_IP**: het IP-adres van de bron-of doelserver.

- **server_hostname**: de HOSTNAAM of FQDN-naam van de doelserver.

- **source_context**: extra informatie die is gekoppeld aan het **bron** veld. Bijvoorbeeld:

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **bron**: het onderdeel Exchange Online dat verantwoordelijk is voor de gebeurtenis. Bijvoorbeeld:

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id**: deze corresponderen met de waarden van de **bericht gebeurtenis** die worden beschreven in de sectie [gerelateerde records zoeken voor dit bericht](#find-related-records-for-this-message) .

- **internal_message_id**: een bericht-id die is toegewezen door de Exchange Online-server die het bericht momenteel verwerkt.

- **recipient_address**: de e-mailadressen van de geadresseerden van het bericht. Meerdere e-mailadressen worden gescheiden door puntkomma's (;).

- **recipient_count**: het totale aantal geadresseerden in het bericht.

- **related_recipient_address**: gebruikt met `EXPAND` , `REDIRECT` en `RESOLVE` gebeurtenissen om andere e-mailadressen van de geadresseerde weer te geven die aan het bericht zijn gekoppeld.

- **naslag**: dit veld bevat aanvullende informatie over specifieke typen gebeurtenissen. Bijvoorbeeld:

  - **DSN**: bevat de koppeling van het rapport, dit is de **message_id** waarde van de bijbehorende melding voor de afleverings status (ook wel bekend als DSN, bericht over niet-uitgevoerde bezorging, NDR of stuiteren) als er een DSN wordt gegenereerd voor deze gebeurtenis. Als dit een DSN-bericht is, bevat dit veld de **message_id** waarde van het oorspronkelijke bericht waarvoor de DSN is gegenereerd.

  - **Expand**: bevat de **related_recipient_address** waarde van de gerelateerde berichten.

  - **Receive**: kan de **message_id** waarde van het bijbehorende bericht bevatten als het bericht is gegenereerd door andere processen (bijvoorbeeld regels voor Postvak in).

  - **Verzenden**: bevat de **internal_message_id** waarde van eventuele DSN-berichten.

  - **Transfer**: bevat de **internal_message_id** waarde van het bericht dat wordt gevorkeerd (bijvoorbeeld via inhoudsconversie, limieten voor geadresseerden van berichten of agenten).

  - **MAILBOXRULE**: bevat de **internal_message_id** waarde van het inkomende bericht waarmee de regel voor Postvak in het uitgaande bericht heeft gegenereerd.

    Voor andere typen gebeurtenissen is dit veld meestal leeg.

- **return_path**: het retour-e-mailadres dat is opgegeven met de opdracht **mail from en** die het bericht heeft verzonden. Hoewel dit veld nooit leeg is, kan de waarde van het adres voor de null-afzender worden weergegeven `<>` .

- **message_info**: aanvullende informatie over het bericht. Bijvoorbeeld:

  - De datum en tijd van het bericht voor de oorsprong van de gebeurtenissen in UTC voor `DELIVER` en `SEND` gebeurtenissen. De datum en tijd van de origine is de tijd waarop het bericht de Exchange Online-organisatie voor het eerst heeft ingevoerd. De UTC-datum en-tijd worden weergegeven in de ISO 8601-notatie voor datum-/tijdnotatie: `yyyy-mm-ddThh:mm:ss.fffZ` , waarbij `yyyy` = jaar, `mm` = maand, `dd` = dag, `T` de waarde van het begin van de tijdcomponent, = `hh` Hour, `mm` = minuut, `ss` = seconde, `fff` = fracties van een seconde en `Z` `Zulu` een andere manier om UTC aan te duiden.

  - Verificatiefouten. U kunt bijvoorbeeld de waarde `11a` en het type verificatie zien dat is gebruikt toen de verificatiefout optrad.

- **tenant_id**: een GUID-waarde die staat voor de Exchange Online-organisatie (bijvoorbeeld `39238e87-b5ab-4ef6-a559-af54c6b07b42` ).

- **original_server_ip**: het IP-adres van de oorspronkelijke server.

- **custom_data**: bevat gegevens met betrekking tot specifieke gebeurtenistypen. Zie de volgende secties voor meer informatie.

#### <a name="custom_data-values"></a>waarden custom_data

Het **custom_data** veld voor een `AGENTINFO` gebeurtenis wordt gebruikt door diverse Exchange Online-agenten om gegevens in te voeren voor het verwerken van berichten. De volgende secties bevatten een beschrijving van de meest interessante medewerkers.

#### <a name="spam-filter-agent"></a>Spam filter agent

Een **custom_data** waarde waarmee begint met `S:SFA` van de spamfilter agent. De belangrijkste gegevens worden beschreven in de volgende tabel:

****

|Value|Beschrijving|
|---|---|
|`SFV=NSPM`|Het bericht is gemarkeerd als niet-spam en is verzonden naar de geadresseerden.|
|`SFV=SPM`|Het bericht is gemarkeerd als spam door antispam filteren (ook wel het filteren van inhoud genoemd).|
|`SFV=BLK`|Filteren is overgeslagen en het bericht is geblokkeerd, omdat het afkomstig is van een geblokkeerde afzender.|
|`SFV=SKS`|Het bericht is gemarkeerd als spam voordat ze werden verwerkt door antispam filters. Dit omvat berichten die het bericht heeft vergeleken met een e-mail stroom regel (ook wel een transportregel genoemd) om deze automatisch als spam te markeren en alle extra filters over te slaan.|
|`SCL=<number>`|Voor meer informatie over de verschillende SCL-waarden en wat ze betekenen, raadpleegt u [spam niveaus](spam-confidence-levels.md).|
|`PCL=<number>`|De waarde van het PCL-betrouwbaarheidsniveau van het bericht. Dit kan op dezelfde manier worden geïnterpreteerd als de waarden van SCL die worden beschreven in de [betrouwbaarheid van spam niveaus](spam-confidence-levels.md).|
|`DI=SB`|De afzender van het bericht is geblokkeerd.|
|`DI=SQ`|Het bericht is in quarantaine geplaatst.|
|`DI=SD`|Het bericht is verwijderd.|
|`DI=SJ`|Het bericht is verzonden naar de map Ongewenste E-mail van de geadresseerde.|
|`DI=SN`|Het bericht is gerouteerd via de normale uitgaande bezorgings groep.|
|`DI=SO`|Het bericht is gerouteerd via de meer bezorgings pool voor risico risico. Zie voor meer informatie de [groep hoog risico voor uitgaande berichten](high-risk-delivery-pool-for-outbound-messages.md).|
|`SFS=[a]|SFS=[b]`|Dit betekent dat de spam regels overeenkomen.|
|`IPV=CAL`|Het bericht is toegestaan door de spamfilters, omdat het IP-adres is opgegeven in een lijst met toegestane IP-adressen in het verbindings filter.|
|`H=<EHLOstring>`|De HELO- of EHLO-tekenreeks van de verbindende e-mailserver.|
|`PTR=<ReverseDNS>`|De PTR-record van het verzendende IP-adres, ook wel het omgekeerde DNS-adres genoemd.|
|

Een voorbeeld **custom_data** waarde voor een bericht dat is gefilterd op spam als volgt:

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>Filter agent voor schadelijke software

Een **custom_data** waarde waarmee begint met `S:AMA` van de malware-filter agent. De belangrijkste gegevens worden beschreven in de volgende tabel:

****

|Value|Beschrijving|
|---|---|
|`AMA=SUM|v=1|` wel `AMA=EV|v=1`|Het bericht is gevonden voor het opnemen van malware. `SUM` Hiermee wordt aangegeven dat de malware is gedetecteerd door een aantal motoren. `EV` Hiermee wordt aangegeven dat de malware is gedetecteerd door een bepaalde engine. Wanneer malware wordt gedetecteerd door een engine, worden de volgende acties geactiveerd.|
|`Action=r`|Het bericht is vervangen.|
|`Action=p`|Het bericht is overgeslagen.|
|`Action=d`|Het bericht is uitgesteld.|
|`Action=s`|Het bericht is verwijderd.|
|`Action=st`|Het bericht is overgeslagen.|
|`Action=sy`|Het bericht is overgeslagen.|
|`Action=ni`|Het bericht is geweigerd.|
|`Action=ne`|Het bericht is geweigerd.|
|`Action=b`|Het bericht is geblokkeerd.|
|`Name=<malware>`|De naam van de schadelijke software die is gedetecteerd.|
|`File=<filename>`|De naam van het bestand dat de schadelijke software bevat.|
|

Een voorbeeld **custom_data** waarde voor een bericht dat schadelijke software bevat, ziet er als volgt uit:

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>Transport regel agent

Een **custom_data** waarde die begint met `S:TRA` , is afkomstig van de transport regel agent voor de regels voor de e-mail stroom (ook wel een transportregel genoemd). De belangrijkste gegevens worden beschreven in de volgende tabel:

****

|Value|Beschrijving|
|---|---|
|`ETR|ruleId=<guid>`|De regel-ID die overeenkomt.|
|`St=<datetime>`|De datum en tijd in UTC waarop de regel overeenkomst is opgetreden.|
|`Action=<ActionDefinition>`|De actie die is toegepast. Zie [acties voor e-mail stroom regels in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor een lijst met beschikbare acties.|
|`Mode=<Mode>`|De modus van de regel. Geldige waarden zijn:<ul><li>**Afdwingen**: alle acties op de regel worden afgedwongen.</li><li>**Test met beleids tips:**: alle acties voor beleidsregels worden verzonden, maar andere afdwing acties worden niet uitgevoerd.</li><li>**Test zonder beleids tips**: acties worden weergegeven in een logboekbestand, maar afzenders worden op geen enkele manier op de hoogte gesteld en handhavings acties worden niet uitgevoerd.</li></ul>|
|

Een voorbeeld **custom_data** waarde voor een bericht die voldoet aan de voorwaarden van een e-mail stroom regel, ziet er als volgt uit:

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
