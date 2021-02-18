---
title: Berichttracering in het Beveiligings- en compliancecentrum
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen bericht traceren in het beveiligings- & compliancecentrum om erachter te komen wat er is gebeurd met berichten.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ce26f7a6cdad15019e2b40eb6f8746e5723d4f0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290655"
---
# <a name="message-trace-in-the-security--compliance-center"></a>Berichttracering in het Beveiligings- en compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

## <a name="message-trace-features"></a>Functies voor bericht traceren

Bericht traceren in het beveiligings- & Compliancecentrum volgt e-mailberichten op het adres van uw Exchange Online-organisatie. U kunt bepalen of een bericht is ontvangen, geweigerd, uitgesteld of bezorgd door de service. U ziet ook welke acties er zijn uitgevoerd op het bericht voordat het de uiteindelijke status heeft bereikt.

Bericht traceren in het beveiligings- & compliancecentrum verbetert de oorspronkelijke bericht traceer die beschikbaar was in het Exchange-beheercentrum (EAC). U kunt de informatie uit bericht traceren gebruiken om op efficiënte wijze gebruikersvragen te beantwoorden over wat er is gebeurd met berichten, problemen met de e-mailstroom op te lossen en beleidswijzigingen te valideren.

> [!NOTE]
>
> - Als u een bericht wilt traceren, moet u lid zijn van de rollengroepen Organisatiebeheer, Compliancebeheer of Helpdesk. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.
>
> - Het maximum aantal berichten dat in de resultaten wordt weergegeven, is afhankelijk van het rapporttype dat u hebt geselecteerd (zie de sectie [Rapporttype](#choose-report-type) kiezen voor meer informatie). De [cmdlet Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) in Exchange Online PowerShell of de zelfstandige EOP PowerShell retourneert alle berichten in de resultaten.

## <a name="open-message-trace"></a>Bericht traceren openen

1. Open het & compliancecentrum <https://protection.office.com> op.

2. Vouw **de e-mailstroom** uit en selecteer **Bericht traceren.**

## <a name="message-trace-page"></a>Bericht traceren-pagina

Hier kunt u een nieuwe standaard trace starten door te klikken op de **knop Een trace starten.** Hiermee wordt gezocht naar alle berichten voor alle afzenders en geadresseerden van de afgelopen twee dagen. U kunt ook een van de opgeslagen query's uit de beschikbare querycategorieën gebruiken en deze direct uitvoeren of als uitgangspunt voor uw eigen query's gebruiken:

- **Standaardquery's:** ingebouwde query's van Microsoft 365.

- **Aangepaste query's:** query's die zijn opgeslagen door beheerders in uw organisatie voor toekomstig gebruik.

- **Automatisch opgeslagen query's:** de laatste tien laatst uitgevoerde query's. Deze lijst maakt het eenvoudig om door te gaan waar u was gebleven.

Op deze pagina vindt u ook een **sectie** met downloadbare rapporten voor de aanvragen die u hebt ingediend, evenals de rapporten zelf wanneer deze beschikbaar zijn om te downloaden.

## <a name="options-for-a-new-message-trace"></a>Opties voor een nieuwe bericht traceren

### <a name="filter-by-senders-and-recipients"></a>Filteren op afzenders en geadresseerden

De standaardwaarden zijn **Alle afzenders en** **Alle** geadresseerden, maar u kunt de volgende velden gebruiken om de resultaten te filteren:

- **Door deze personen:** klik in dit veld om een of meer afzenders in uw organisatie te selecteren. U kunt ook een naam beginnen te typen en de items in de lijst worden gefilterd op wat u hebt getypt, net zoals op de manier waarop een zoekpagina werkt.

- **Voor deze personen:** klik in dit veld om een of meer geadresseerden in uw organisatie te selecteren.

> [!NOTE]
>
> - U kunt ook de e-mailadressen van externe afzenders en geadresseerden typen. Jokertekens worden ondersteund (bijvoorbeeld), maar u kunt niet meerdere jokertekens in hetzelfde veld `*@contoso.com` tegelijk gebruiken.
>
> - U kunt meerdere afzenders of lijsten met geadresseerden plakken, gescheiden door puntkomma's `;` (). spaties ( `\s` ), carriage returns ( `\r` ), of volgende regels ( `\n` ).

### <a name="time-range"></a>Tijdsbereik

De standaardwaarde is **twee dagen,** maar u kunt een datum/tijdsbereik van maximaal 90 dagen opgeven. Houd rekening met de volgende punten wanneer u datum-/tijdbereiken gebruikt:

- Standaard selecteert u het tijdsbereik in de **schuifregelaarweergave** met een tijdlijn. U kunt alleen de weergegeven dag- of tijdinstellingen selecteren. Als u een tussenwaarde probeert te selecteren, wordt de start-/eindballon vastgelijnd op de dichtstbijzijnde weergegeven instelling.

  ![Een schuifregelaartijdbereik in een nieuwe bericht traceren in het beveiligings- & compliancecentrum](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  U kunt echter ook  overschakelen naar de aangepaste weergave  waar u de waarden voor de begin- en einddatum (inclusief tijden) kunt opgeven en waar u ook de **tijdzone** voor het datum-/tijdbereik kunt selecteren.  De instelling **Tijdzone is** van toepassing op zowel uw queryinvoer als uw queryresultaten.

  ![Een aangepast tijdsbereik in een nieuwe bericht trace in het beveiligings- & compliancecentrum](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  De resultaten zijn tien dagen of minder direct beschikbaar als **overzichtsrapport.** Als u een tijdsbereik opgeeft dat zelfs iets groter is dan tien dagen, worden de resultaten vertraagd omdat ze  alleen beschikbaar zijn als een downloadbaar CSV-bestand **(Verbeterd** overzicht of Uitgebreide rapporten).

  Zie de sectie Rapporttype kiezen in dit artikel voor meer informatie over de verschillende [rapporttypen.](#choose-report-type)

  > [!NOTE]
  > Verbeterde samenvatting en uitgebreide rapporten worden voorbereid met gearchiveerde bericht traceren van gegevens en het kan enkele uren duren voordat uw rapport kan worden gedownload. Afhankelijk van hoeveel andere beheerders ook rond hetzelfde tijdstip rapportaanvragen hebben ingediend, kan er ook een vertraging zijn voordat de verwerking van de aanvraag in de wachtrij begint.

- Door een query op te slaan in de **schuifregelaarweergave** wordt het relatieve tijdsbereik op slaan (bijvoorbeeld drie dagen vanaf vandaag). Als u een query **op** slaan in de aangepaste weergave, wordt het absolute datum-/tijdbereik op slaan (bijvoorbeeld 05-05-06 13:00 tot 2018-05-08 18:00).

### <a name="more-search-options"></a>Meer zoekopties

#### <a name="delivery-status"></a>Bezorgingsstatus

U kunt de standaardwaarde **Alle geselecteerd** laten of u kunt een van de volgende waarden selecteren om de resultaten te filteren:

- **Bezorgd:** het bericht is bezorgd op de beoogde bestemming.

- **In** behandeling: Bezorging van het bericht wordt geprobeerd of opnieuw geprobeerd.

- **Uitvóón:** de geadresseerde van een distributiegroep is uitvór de bezorging bij de afzonderlijke leden van de groep.

- **Mislukt:** het bericht is niet bezorgd.

- **In quarantaine** geplaatst: het bericht is in quarantaine geplaatst (als spam, bulkmail of phishing). Zie In quarantaine [geplaatste e-mailberichten in EOP voor meer informatie.](quarantine-email-messages.md)

- **Gefilterd als spam:** Het bericht is gemarkeerd als spam en is geweigerd of geblokkeerd (niet in quarantaine geplaatst).

- **Status verkrijgen:** Het bericht is onlangs ontvangen door Microsoft 365, maar er zijn nog geen andere statusgegevens beschikbaar. Controleer het over een paar minuten opnieuw.

> [!NOTE]
> De waarden **In behandeling,** **In quarantaine** geplaatst en Filteren als **spam** zijn alleen beschikbaar voor zoekopdrachten die minder dan tien dagen duren. Er kan ook een vertraging van 5 tot 10 minuten zijn tussen de werkelijke en gerapporteerde bezorgingsstatus.

#### <a name="message-id"></a>Bericht-id

Dit is de internetbericht-id (ook wel bekend als de client-id) die is gevonden in de **bericht-id:** koptekstveld in de berichtkop. Gebruikers kunnen u deze waarde geven om specifieke berichten te onderzoeken.

Deze waarde is constante voor de levensduur van het bericht. Voor berichten die zijn gemaakt in Microsoft 365 of Exchange, heeft de waarde de `<GUID@ServerFQDN>` notatie, inclusief de hoekhaken ( \< \> ). Bijvoorbeeld `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. In andere berichtsystemen worden mogelijk verschillende syntaxis of waarden gebruikt. Deze waarde hoort uniek te zijn, maar niet alle e-mailsystemen volgen deze vereiste strikt. Als de **bericht-id:** het koptekstveld niet bestaat of leeg is voor inkomende berichten van externe bronnen, wordt een willekeurige waarde toegewezen.

Wanneer u **bericht-id gebruikt om** de resultaten te filteren, moet u de volledige tekenreeks opnemen, inclusief de hoekhaken.

#### <a name="direction"></a>Richting

U kunt de  standaardwaarde Alles geselecteerd laten of **inkomende** (berichten die zijn verzonden naar geadresseerden in uw organisatie) of Uitgaand **(berichten** die zijn verzonden van gebruikers in uw organisatie) selecteren om de resultaten te filteren.

#### <a name="original-client-ip-address"></a>Oorspronkelijk IP-adres van client

U kunt de resultaten per client-IP-adres bestandsgegevens indienen om gehackte computers te onderzoeken die grote hoeveelheden spam of malware verzenden. Hoewel het lijkt alsof de berichten afkomstig zijn van meerdere afzenders, is het waarschijnlijk dat op dezelfde computer alle berichten worden gegenereerd.

> [!NOTE]
> De ip-adresgegevens van de client zijn slechts tien dagen  beschikbaar en  zijn alleen beschikbaar in het uitgebreide overzicht of uitgebreide rapporten (downloadbare CSV-bestanden).

### <a name="choose-report-type"></a>Rapporttype kiezen

De beschikbare rapporttypen zijn:

- **Overzicht:** beschikbaar als het tijdsbereik kleiner is dan tien dagen en er geen extra filteropties zijn vereist. De resultaten zijn vrijwel direct beschikbaar nadat u op **Zoeken hebt geklikt.** Het rapport levert maximaal 20.000 resultaten op.

- **Verbeterd** overzicht of **Uitgebreid:** deze rapporten zijn alleen beschikbaar als downloadbare CSV-bestanden en vereisen een of meer van de volgende filteropties, ongeacht het tijdsbereik: Voor deze **personen,** Deze personen of **Bericht-id.** U kunt jokertekens gebruiken voor de afzenders of geadresseerden (bijvoorbeeld \* @contoso.com). Het verbeterde overzichtsrapport retourneert maximaal 50.000 resultaten. Het uitgebreide rapport levert maximaal 1000 resultaten op.

> [!NOTE]
> 
> - Uitgebreide overzichtsrapporten en uitgebreide rapporten worden voorbereid met gearchiveerde bericht traceringsgegevens en het kan enkele uren duren voordat uw rapport kan worden gedownload. Afhankelijk van hoeveel andere beheerders ook rond hetzelfde tijdstip rapportaanvragen hebben ingediend, kan er ook een vertraging zijn voordat de aanvraag in de wachtrij wordt verwerkt.
> 
> - Hoewel u voor elk datum/tijdsbereik een uitgebreide samenvatting of uitgebreid rapport kunt selecteren, zijn meestal de laatste vier uur aan gearchiveerde gegevens nog niet beschikbaar voor deze twee typen rapporten.

Wanneer u op Volgende **klikt,** wordt er een overzichtspagina weergegeven met de filteropties die u hebt geselecteerd, een unieke (bewerkbare) titel voor het rapport en het e-mailadres dat de melding ontvangt wanneer de bericht traceren is voltooid (kan ook worden bewerkt en moet zich in een van de geaccepteerde domeinen van uw organisatie) plaatsen. Klik **op Rapport voorbereiden** om de bericht trace te verzenden. Op de **hoofdpagina bericht** traceren kunt u de status van het rapport bekijken in de sectie **Downloadbare** rapporten.

Zie de volgende sectie voor meer informatie over de gegevens die worden geretourneerd in de verschillende rapporttypen.

## <a name="message-trace-results"></a>Resultaten bericht traceren

De verschillende rapporttypen retourneren verschillende gegevensniveaus. De informatie die beschikbaar is in de verschillende rapporten, wordt in de volgende secties beschreven.

### <a name="summary-report-output"></a>Uitvoer van overzichtsrapport

Nadat u de bericht trace heeft uitgevoerd, worden de resultaten weergegeven, gesorteerd op aflopende datum/tijd (meest recente datum/tijd eerst).

![Resultaten van overzichtsrapport voor bericht traceren in het beveiligings- & compliancecentrum](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

Het overzichtsrapport bevat de volgende informatie:

- **Datum:** de datum en tijd waarop het bericht is ontvangen door de service, met behulp van de geconfigureerde UTC-tijdzone.

- **Afzender:** het e-mailadres van de afzender @ *(aliasdomein).*

- **Geadresseerde:** het e-mailadres van de geadresseerde of geadresseerden. Voor een bericht dat naar meerdere geadresseerden is verzonden, bestaat er één regel per geadresseerde. Als de geadresseerde een distributiegroep, dynamische distributiegroep of beveiligingsgroep met e-mail is, wordt de groep de eerste geadresseerde en staat elk lid van de groep op een aparte regel.

- **Onderwerp:** De eerste 256 tekens van het onderwerp van het **bericht:** veld.

- **Status:** deze waarden worden beschreven in de sectie [Bezorgingsstatus.](#delivery-status)

Standaard worden de eerste 250 resultaten geladen en direct beschikbaar. Wanneer u omlaag schuift, wordt de volgende reeks resultaten met een kleine pauze geladen. In plaats van schuiven  kunt u op Alles laden klikken om alle resultaten tot een maximum van 10.000 te laden.

U kunt op de kolomkoppen klikken om de resultaten te sorteren op de waarden in die kolom in oplopende of aflopende volgorde.

U kunt klikken op **Resultaten filteren** om de resultaten te filteren op een of meer kolommen.

U kunt de resultaten exporteren nadat u een of  meer rijen hebt geselecteerd door te klikken op Resultaten exporteren en vervolgens Alle resultaten **exporteren,** Geladen resultaten exporteren of Exporteren geselecteerd te **selecteren.**

#### <a name="find-related-records-for-this-message"></a>Gerelateerde records zoeken voor dit bericht

Gerelateerde berichtrecords zijn records die dezelfde bericht-id hebben gedeeld. Vergeet niet dat zelfs één bericht dat wordt verzonden tussen twee personen meerdere records kan genereren. Het aantal records neemt toe wanneer het bericht wordt beïnvloed door uitbreiding van een distributiegroep, doorsturen, regels voor de e-mailstroom (ook wel transportregels genoemd) enzovoort.

Nadat u het selectievakje van een rij hebt geselecteerd, kunt u  gerelateerde records voor het bericht  zoeken door te klikken op de knop Verwante zoeken die wordt weergegeven of door Meer opties meer gerelateerde records zoeken voor dit bericht te ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> selecteren.

Zie de sectie Bericht-id eerder in dit artikel voor meer informatie over de bericht-id.

#### <a name="message-trace-details"></a>Details van bericht traceren

In de uitvoer van het overzichtsrapport kunt u op een van de volgende manieren details over een bericht weergeven:

- Selecteer de rij (klik ergens in de rij behalve het selectievakje).

- Schakel het selectievakje van de rij in en klik **op Meer opties** Meer ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **berichtgegevens weergeven.**

   ![Details na dubbelklikken op een rij in bericht traceren samenvattingsrapport in het beveiligings- & Compliancecentrum](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

De bericht tracerendetails bevatten de volgende aanvullende informatie die niet aanwezig is in het overzichtsrapport:

- **Berichtgebeurtenissen:** deze sectie bevat classificaties die helpen bij het categoriseren van de acties die door de service worden genomen op berichten. **Enkele van de interessantste gebeurtenissen die** u kunt tegenkomen zijn:

  - **Ontvangen:** het bericht is ontvangen door de service.

  - **Verzenden:** het bericht is verzonden door de service.

  - **Mislukt:** het bericht kan niet worden bezorgd.

  - **Bezorgen:** het bericht is bezorgd in een postvak.

  - **Uitv** vouwen: het bericht is verzonden naar een distributiegroep die is uitverbreed.

  - **Overdracht:** geadresseerden zijn verplaatst naar een geconversie van inhoud, limieten voor geadresseerden van berichten of agenten.

  - **Uitstellen:** de bezorging van het bericht is uitgesteld en kan later opnieuw worden geprobeerd.

  - **Opgelost:** het bericht is omgeleid naar het adres van een nieuwe ontvanger op basis van een zoeker in Active Directory. Als dit gebeurt, wordt het oorspronkelijke adres van de geadresseerde weergegeven in een aparte rij in de bericht traceren, samen met de uiteindelijke bezorgingsstatus van het bericht.

  > [!NOTE]
  > 
  > - Een onregelmatig bericht dat zonder succes wordt afgeleverd, genereert meerdere **gebeurtenisgegevens** in de bericht trace.
  > 
  > - Deze lijst is niet bedoeld om volledig te zijn. Zie gebeurtenistypen in het logboek voor het bijhouden van berichten voor [beschrijvingen van meer gebeurtenissen.](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log) Deze koppeling is een Exchange Server-onderwerp (on-premises Exchange).

- **Meer informatie:** deze sectie bevat de volgende details:

  - **Bericht-id:** deze waarde wordt beschreven in de [sectie Bericht-id](#message-id) eerder in dit artikel. Bijvoorbeeld `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

  - **Berichtgrootte**

  - **Vanuit IP:** het IP-adres van de computer die het bericht heeft verzonden. Voor uitgaande berichten die vanuit Exchange Online worden verzonden, is deze waarde leeg.

  - **Om IP:** het IP-adres of de adressen waar de service heeft geprobeerd het bericht te bezorgen. Als het bericht meerdere geadresseerden heeft, worden deze weergegeven. Deze waarde is leeg voor inkomende berichten die naar Exchange Online worden verzonden.

### <a name="enhanced-summary-reports"></a>Verbeterde overzichtsrapporten

Beschikbare (voltooide) uitgebreide overzichtsrapporten zijn beschikbaar in de sectie **Downloadbare** rapporten aan het begin van bericht traceren. De volgende informatie is beschikbaar in het rapport:

- **origin_timestamp:** de datum en tijd waarop het bericht oorspronkelijk door de service is ontvangen, met behulp van de <sup>*</sup> geconfigureerde UTC-tijdzone.

- **sender_address:** het e-mailadres *(aliasdomein)* van @ *de afzender.*

- **Recipient_status:** de bezorgingsstatus van het bericht bij de geadresseerde. Als het bericht naar meerdere geadresseerden is verzonden, worden alle geadresseerden en de bijbehorende status voor elk bericht weergegeven in de volgende \<*email address*\> indeling: ## \<*status*\> Bijvoorbeeld:

  - **##Receive, betekent Verzenden** dat het bericht is ontvangen door de service en naar de beoogde bestemming is verzonden.

  - **##Receive, mislukt** betekent dit dat het bericht is ontvangen door de service, maar dat bezorging op de beoogde bestemming is mislukt.

  - **##Receive, betekent Bezorgen** dat het bericht is ontvangen door de service en is bezorgd in het postvak van de geadresseerde.

- **message_subject:** de eerste 256 tekens van het veld **Onderwerp van het** bericht.

- **total_bytes:** de grootte van het bericht in bytes, inclusief bijlagen.

- **message_id:** Deze waarde wordt beschreven in de [sectie Bericht-id](#message-id) eerder in dit artikel. Bijvoorbeeld `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

- **network_message_id:** een unieke bericht-id-waarde die wordt weergegeven in alle kopieën van het bericht die mogelijk worden gemaakt als gevolg van een bifurcation of uitbreiding van een distributiegroep. Een voorbeeldwaarde is `1341ac7b13fb42ab4d4408cf7f55890f` .

- **original_client_ip:** het IP-adres van de client van de afzender.

- **directionality:** geeft aan of het bericht is verzonden inkomende (1) naar uw organisatie, of dat het is verzonden uitgaande (2) van uw organisatie.

- **connector_id:** de naam van de bron- of doelconnector. Zie E-mailstroom configureren met [connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)voor meer informatie over connectors in Exchange Online.

- **delivery_priority:** ongeacht of het bericht is verzonden met de prioriteit <sup>*</sup> **Hoog,** Laag **of Normaal.** 

<sup>*</sup> Deze eigenschappen zijn alleen beschikbaar in uitgebreide overzichtsrapporten.

### <a name="extended-reports"></a>Uitgebreide rapporten

Beschikbare (voltooide) uitgebreide rapporten zijn beschikbaar in de **sectie Downloadbare** rapporten aan het begin van bericht traceren. Vrijwel alle informatie uit een uitgebreid overzichtsrapport is beschikbaar in een uitgebreid rapport (met uitzondering van origin_timestamp **en** **delivery_priority).** De volgende aanvullende informatie is alleen beschikbaar in een uitgebreid rapport:

- **client_ip:** het IP-adres van de e-mailserver of de berichtenclient die het bericht heeft verzonden.

- **client_hostname:** de hostnaam of FQDN van de e-mailserver of berichtenclient die het bericht heeft verzonden.

- **server_ip:** het IP-adres van de bronserver of doelserver.

- **server_hostname:** de hostnaam of de FQDN van de doelserver.

- **source_context:** extra informatie die is gekoppeld aan het **bronveld.** Bijvoorbeeld:

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **bron:** het Exchange Online-onderdeel dat verantwoordelijk is voor de gebeurtenis. Bijvoorbeeld:

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id:** Deze komen overeen  met de waarden voor berichtgebeurtenissen die worden uitgelegd in de sectie Verwante [records zoeken voor dit](#find-related-records-for-this-message) bericht.

- **internal_message_id:** een bericht-id die is toegewezen door de Exchange Online-server die het bericht momenteel verwerkt.

- **recipient_address:** de e-mailadressen van de geadresseerden van het bericht. Meerdere e-mailadressen worden gescheiden door een puntkomma (;).

- **recipient_count:** het totale aantal geadresseerden in het bericht.

- **related_recipient_address:** wordt gebruikt met , en gebeurtenissen om e-mailadressen van andere geadresseerden weer te `EXPAND` geven die aan het bericht zijn `REDIRECT` `RESOLVE` gekoppeld.

- **verwijzing:** dit veld bevat aanvullende informatie voor specifieke soorten gebeurtenissen. Bijvoorbeeld:

  - **DSN:** bevat de rapportkoppeling, de **waarde van de message_id-waarde** van de bijbehorende melding van de bezorgingsstatus (ook wel een DSN, rapport over niet-bezorging, NDR of niet-bezorgdbericht genoemd) als een DSN na deze gebeurtenis wordt gegenereerd. Als dit een DSN-bericht is, bevat dit veld de message_id **waarde** van het oorspronkelijke bericht waar de DSN voor is gegenereerd.

  - **EXPAND:** bevat **de related_recipient_address** waarde van de gerelateerde berichten.

  - **RECEIVE:** bevat mogelijk de **message_id** waarde van het bijbehorende bericht als het bericht is gegenereerd door andere processen (bijvoorbeeld regels voor Postvak IN).

  - **SEND:** bevat **de internal_message_id** waarde van DSN-berichten.

  - **TRANSFER:** bevat **de internal_message_id** waarde van het bericht dat wordt gevorkt (bijvoorbeeld door inhoudsconversie, limieten voor geadresseerden van berichten of agenten).

  - **MAILBOXRULE:** bevat **internal_message_id** waarde van het binnenkomende bericht waardoor het uitgaande bericht is gegenereerd door de regel voor Postvak IN.

    Voor andere typen gebeurtenissen is dit veld meestal leeg.

- **return_path:** het retour-e-mailadres dat is opgegeven met de **opdracht MAIL FROM** die het bericht heeft verzonden. Hoewel dit veld nooit leeg is, kan de waarde van het null-afzenderadres worden weergegeven `<>` als.

- **message_info:** aanvullende informatie over het bericht. Bijvoorbeeld:

  - De datum-tijd van de origin-time van het bericht in UTC voor `DELIVER` en `SEND` gebeurtenissen. De oorspronkelijke datum-tijd is het tijdstip waarop het bericht voor het eerst in de Exchange Online-organisatie is ingevoerd. De UTC-datum-tijd wordt weergegeven in de ISO 8601-datum-tijdnotatie: waarbij = jaar, = maand, = dag, het begin van de tijdcomponent `yyyy-mm-ddThh:mm:ss.fffZ` `yyyy` `mm` `dd` `T` aangeeft, `hh` = uur, `mm` = minuut, = seconde, `ss` = `fff` `Z` `Zulu` breuken van een seconde, en betekent dit een andere manier om UTC aan te duiden.

  - Verificatiefouten. U ziet bijvoorbeeld de waarde en het type verificatie dat is gebruikt `11a` toen de verificatiefout zich voordeed.

- **tenant_id:** een GUID-waarde die de Exchange Online-organisatie vertegenwoordigt `39238e87-b5ab-4ef6-a559-af54c6b07b42` (bijvoorbeeld).

- **original_server_ip:** het IP-adres van de oorspronkelijke server.

- **custom_data:** bevat gegevens met betrekking tot specifieke gebeurtenistypen. Zie de volgende secties voor meer informatie.

#### <a name="custom_data-values"></a>custom_data waarden

Het **custom_data** veld voor een gebeurtenis wordt gebruikt door een groot aantal Exchange Online-agenten om informatie over de verwerking van `AGENTINFO` berichten te logboeken. In de volgende secties worden enkele interessantere agenten beschreven.

#### <a name="spam-filter-agent"></a>Agent voor het filteren van ongewenste e-mail

Een **custom_data** die begint met `S:SFA` is van de agent die het spamfilter gebruikt. De belangrijkste details worden in de volgende tabel beschreven:

****

|Value|Beschrijving|
|---|---|
|`SFV=NSPM`|Het bericht is gemarkeerd als niet-spam en is verzonden naar de geadresseerden.|
|`SFV=SPM`|Het bericht is gemarkeerd als spam door antispamfilters (ook wel bekend als inhoudsfilters).|
|`SFV=BLK`|Filteren is overgeslagen en het bericht is geblokkeerd omdat het afkomstig is van een geblokkeerde afzender.|
|`SFV=SKS`|Het bericht is gemarkeerd als spam voordat het werd verwerkt door spamfilters. Dit geldt ook voor berichten die overeenkomen met een regel voor de e-mailstroom (ook wel een transportregel genoemd) om het bericht automatisch als spam te markeren en alle extra filters te omzeilen.|
|`SCL=<number>`|Zie de betrouwbaarheidsniveaus van spam voor meer informatie over de verschillende SCL-waarden en wat [deze betekenen.](spam-confidence-levels.md)|
|`PCL=<number>`|De waarde van het Phishing-betrouwbaarheidsniveau (PCL) van het bericht. Deze kunnen op dezelfde manier worden geïnterpreteerd als de SCL-waarden die worden beschreven in [het betrouwbaarheidsniveau voor spam.](spam-confidence-levels.md)|
|`DI=SB`|De afzender van het bericht is geblokkeerd.|
|`DI=SQ`|Het bericht is in quarantaine geplaatst.|
|`DI=SD`|Het bericht is verwijderd.|
|`DI=SJ`|Het bericht is verzonden naar de map Ongewenste e-mail van de geadresseerde.|
|`DI=SN`|Het bericht is omgeleid via de normale uitgaande bezorgingsgroep.|
|`DI=SO`|Het bericht is omgeleid via de bezorgingsgroep met een hoger risico. Zie de [bezorgingsgroep met hoog risico voor uitgaande berichten voor meer informatie.](high-risk-delivery-pool-for-outbound-messages.md)|
|`SFS=[a]|SFS=[b]`|Hiermee wordt aangegeven dat spamregels aan elkaar zijn voldoen.|
|`IPV=CAL`|Het bericht is toegestaan via de spamfilters omdat het IP-adres is opgegeven in een lijst met toegestane IP-adressen in het verbindingsfilter.|
|`H=<EHLOstring>`|De HELO- of EHLO-tekenreeks van de verbindende e-mailserver.|
|`PTR=<ReverseDNS>`|De PTR-record van het verzendende IP-adres, ook wel bekend als het omgekeerde DNS-adres.|
|

Een voorbeeld **custom_data** waarde voor een bericht dat op spam is gefilterd, zoals hier:

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>Agent voor malwarefilter

Een **custom_data** die begint met `S:AMA` is afkomstig van de malwarefilteragent. De belangrijkste details worden in de volgende tabel beschreven:

****

|Value|Beschrijving|
|---|---|
|`AMA=SUM|v=1|` of `AMA=EV|v=1`|Het bericht werd vastgesteld dat het malware bevat. `SUM` geeft aan dat de malware door een groot aantal engines kan zijn gedetecteerd. `EV` geeft aan dat de malware door een specifieke engine is gedetecteerd. Wanneer malware door een engine wordt gedetecteerd, worden hiermee de volgende acties activeert.|
|`Action=r`|Het bericht is vervangen.|
|`Action=p`|Het bericht is overgeslagen.|
|`Action=d`|Het bericht is uitgesteld.|
|`Action=s`|Het bericht is verwijderd.|
|`Action=st`|Het bericht is overgeslagen.|
|`Action=sy`|Het bericht is overgeslagen.|
|`Action=ni`|Het bericht is geweigerd.|
|`Action=ne`|Het bericht is geweigerd.|
|`Action=b`|Het bericht is geblokkeerd.|
|`Name=<malware>`|De naam van de malware die is gedetecteerd.|
|`File=<filename>`|De naam van het bestand dat de malware bevat.|
|

Een voorbeeld **custom_data** waarde voor een bericht dat malware bevat, ziet er zo uit:

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>Transport Rule agent

Een **custom_data** die begint met is afkomstig van de transportregelagent voor regels voor de `S:TRA` e-mailstroom (ook wel transportregels genoemd). De belangrijkste details worden in de volgende tabel beschreven:

****

|Value|Beschrijving|
|---|---|
|`ETR|ruleId=<guid>`|De regel-id die is gematcht.|
|`St=<datetime>`|De datum en tijd in UTC waarop de regel heeft plaatsgevonden.|
|`Action=<ActionDefinition>`|De actie die is toegepast. Zie E-mailstroomregelacties in Exchange Online voor een lijst met beschikbare [acties.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)|
|`Mode=<Mode>`|De modus van de regel. Geldige waarden zijn:<ul><li>**Afdwingen:** alle acties op de regel worden afgedwongen.</li><li>**Testen met beleidstips:** Alle acties voor beleidstips worden verzonden, maar er wordt geen actie ondernomen door andere afdwingingsacties.</li><li>**Testen zonder** beleidstips: acties worden weergegeven in een logboekbestand, maar afzenders worden op geen enkele manier op de hoogte gesteld en afdwingingsacties worden niet uitgevoerd.</li></ul>|
|

Een voorbeeld **custom_data** waarde voor een bericht dat overeenkomt met de voorwaarden van een regel voor de e-mailstroom, ziet er zo uit:

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
