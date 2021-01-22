---
title: Geavanceerde zoekquery's in Microsoft 365 Defender
description: Meer informatie over het bouwen van snelle, efficiënte en foutloze zoekquery's voor bedreigingen met geavanceerde zoekopdrachten
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, kusto, avoid timeout, command lines, process id, optimize, best practice, parse, join, summarize
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: cc6110cdd7dd71f80f6897cfbb0026ccce301cf7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928472"
---
# <a name="advanced-hunting-query-best-practices"></a>Geavanceerde best practices voor zoekquery's

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Pas deze aanbevelingen toe om sneller resultaten te krijgen en time-outs te vermijden bij het uitvoeren van complexe query's. Lees de best practices voor [kusto-query's](https://docs.microsoft.com/azure/kusto/query/best-practices)voor meer informatie over het verbeteren van de queryprestaties.

## <a name="understand-cpu-resource-quotas"></a>Informatie over quota voor CPU-bronnen
Afhankelijk van de grootte heeft elke tenant toegang tot een bepaalde hoeveelheid CPU-bronnen die zijn toegewezen voor het uitvoeren van geavanceerde zoekquery's. Lees meer over geavanceerde zoekquota's [en gebruiksparameters voor meer informatie](advanced-hunting-limits.md)over verschillende servicelimieten.

Klanten die regelmatig meerdere query's uitvoeren, moeten het gebruik bijhouden en de optimalisatie-richtlijnen in dit artikel toepassen om verstoringen die het gevolg zijn van overschrijding van quota of gebruiksparameters tot een minimum te beperken.

## <a name="general-optimization-tips"></a>Algemene tips voor optimalisatie

- **Grootte van nieuwe query's:** als u vermoedt dat een query een grote resultatenset retourneert, moet u deze eerst beoordelen met behulp van de [operator Count.](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator) Gebruik [de limiet](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) of het synoniem ervan om grote `take` resultatensets te voorkomen.
- Pas **filters** vroeg toe: pas tijdfilters en andere filters toe om de gegevensset te beperken, met name voordat u transformatie- en parseerfuncties gebruikt, zoals [subtekenreeks()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)of [parse_json().](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction) In het onderstaande voorbeeld wordt de parsingsfunctie [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) gebruikt nadat de filteroperatoren het aantal records hebben beperkt.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Bevat bevat het aantal** herhalingen. Gebruik de operator in plaats van de operator in plaats van de woorden om te voorkomen dat u onnodig naar subtekenreeksen in `has` woorden `contains` zoekt. [Meer informatie over tekenreeksoperatoren](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Kijk in specifieke kolommen:** kijk in een specifieke kolom in plaats van volledige tekst te zoeken in alle kolommen. Gebruik niet om `*` alle kolommen te controleren.
- **Case-sensitive for speed—** Case-sensitive searches are more specific and generally more performant. Namen van casegevoelige [tekenreeksoperatoren,](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)zoals `has_cs` `contains_cs` en, die over het algemeen eindigen op `_cs` . U kunt ook de operator voor issys-gevoelige is gelijk aan gebruiken `==` in plaats van `=~` .
- **Parseren, niet extraheren**— gebruik waar mogelijk de [parseroperator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) of een parserende functie zoals [parse_json().](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction) Vermijd de `matches regex` tekenreeksoperator of [de extractiefunctie(),](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)die beide een reguliere expressie gebruiken. Reserveer het gebruik van reguliere expressies voor complexere scenario's. [Meer informatie over parseringsfuncties](#parse-strings)
- **Filter tabellen niet op expressies.** Filter niet op een berekende kolom als u op een tabelkolom kunt filteren.
- **Geen termen met drie tekens.** Vermijd het vergelijken of filteren van termen met drie tekens of minder. Deze voorwaarden worden niet geïndexeerd en voor een aanpassing aan deze voorwaarden zijn meer resources nodig.
- **Projecteren selectief**: maak uw resultaten begrijpelijker door alleen de kolommen te projecteren die u nodig hebt. Door specifieke kolommen te projecteren vóór het uitvoeren [van joins](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) of vergelijkbare bewerkingen, worden ook de prestaties verbeterd.

## <a name="optimize-the-join-operator"></a>De `join` operator optimaliseren
De [join-operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) voegt rijen uit twee tabellen samen door overeenkomende waarden in opgegeven kolommen. Pas deze tips toe om query's te optimaliseren die deze operator gebruiken.

- **Kleinere tabel aan de linkerkant:** de operator matcht records in de tabel aan de linkerkant van uw join-instructie met `join` records aan de rechterkant. Als u de kleinere tabel aan de linkerkant hebt, hoeven er minder records aan te worden gematcht, waardoor de query sneller wordt. 

    In de onderstaande tabel wordt de linkertabel verkleind tot slechts drie specifieke apparaten voordat we deze via `DeviceLogonEvents` `IdentityLogonEvents` account-SID's gebruiken.
 
    ```kusto
    DeviceLogonEvents 
    | where DeviceName in ("device-1.domain.com", "device-2.domain.com", "device-3.domain.com")
    | where ActionType == "LogonFailed"
    | join
        (IdentityLogonEvents
        | where ActionType == "LogonFailed"
        | where Protocol == "Kerberos")
    on AccountSid
    ```

- Gebruik de **inner-join-smaak**: de standaard join-smaak of de [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rijen in de linkertabel door de join-toets voordat u een rij voor elke overeenkomst in de rechtertabel retourneert. Als de linkertabel meerdere rijen heeft met dezelfde waarde voor de sleutel, worden deze rijen gededuplicaeerd om één willekeurige rij achter te laten `join` voor elke unieke waarde.

    Bij dit standaardgedrag kan belangrijke informatie uit de linkertabel weggelaten worden die een nuttig inzicht kan geven. In de onderstaande query wordt bijvoorbeeld slechts één e-mailbericht met een bepaalde bijlage weergegeven, zelfs als dezelfde bijlage is verzonden via meerdere e-mailberichten:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    Om deze beperking aan te pakken, passen we de [inner-join-smaak](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) toe door op te geven dat alle rijen in de linkertabel moeten worden weergeven met overeenkomende `kind=inner` waarden in de rechtertabel:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Neem deel aan records vanuit een tijdvenster.** Bij het onderzoeken van beveiligingsgebeurtenissen zoeken analisten naar gerelateerde gebeurtenissen die zich rond dezelfde periode voordoen. Door dezelfde benadering toe te passen bij het gebruik van voordelen, vermindert u `join` het aantal te controleren records.
    
    Met de onderstaande query wordt gecontroleerd op aanmeldingsgebeurtenissen binnen 30 minuten na ontvangst van een schadelijk bestand:

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where MalwareFilterVerdict == "Malware" 
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- **U kunt tijdfilters** aan beide zijden toepassen, zelfs als u niet bezig bent met het onderzoeken van een bepaald tijdvenster, kunt u het aantal records verminderen dat kan worden gebruikt om de prestaties te controleren en te verbeteren door tijdfilters toe te passen op zowel de linker- als de rechtertabellen. `join` De onderstaande query is van toepassing op beide tabellen, zodat `Timestamp > ago(1h)` alleen records van het afgelopen uur worden joins:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Gebruik hints voor de prestaties**. Gebruik hints met de operator om de back-end zo in te delen dat belasting wordt verdeeld tijdens het uitvoeren van `join` resource-intensieve bewerkingen. [Meer informatie over tips voor deelnemen](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    De willekeurige **[](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** hint helpt bijvoorbeeld bij het samenvoegen van queryprestaties bij het samenvoegen van tabellen met een sleutel met hoge kardinaliteit (een sleutel met veel unieke waarden) zoals in de onderstaande `AccountObjectId` query:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    De **[hint voor uitzending](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** is nuttig wanneer de linkertabel klein is (maximaal 100.000 records) en de rechtertabel zeer groot is. Met de onderstaande query probeert u bijvoorbeeld een paar  e-mailberichten met specifieke onderwerpen samen te stellen, met alle berichten met koppelingen in de `EmailUrlInfo` tabel:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>De `summarize` operator optimaliseren
Met [de samenvattende operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) wordt de inhoud van een tabel samengevoegd. Pas deze tips toe om query's te optimaliseren die deze operator gebruiken.

- **Unieke waarden zoeken.** Over het algemeen kunt u dit gebruiken `summarize` om unieke waarden te vinden die vaak worden herhaald. Het kan onnodig zijn om dit te gebruiken voor het aggregeren van kolommen die geen terugkerende waarden hebben.

    Hoewel één e-mailbericht deel kan uitmaken van meerdere gebeurtenissen, _is_ het onderstaande voorbeeld niet efficiënt omdat een netwerkbericht-id voor een afzonderlijke e-mail altijd wordt geleverd met een uniek `summarize` afzenderadres.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    De operator kan eenvoudig worden vervangen door, wat in potentieel dezelfde resultaten resulteert `summarize` terwijl er minder resources worden `project` verbruikt:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    Het volgende voorbeeld is efficiënter te gebruiken omdat er meerdere afzonderlijke exemplaren kunnen zijn van een afzenderadres dat e-mail naar hetzelfde `summarize` adres van de geadresseerde verstuurt. Dergelijke combinaties zijn minder uniek en hebben waarschijnlijk dubbele waarden.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **Verschuif de query** opnieuw. Deze kan het beste worden gebruikt in kolommen met terugkerende waarden, maar dezelfde kolommen kunnen ook een hoge kardinaliteit hebben of grote `summarize` aantallen unieke waarden  hebben. Net als de operator kunt u ook de willekeurige hint toepassen om de verwerkingsbelasting te verdelen en de prestaties te verbeteren wanneer u kolommen met hoge kardinaliteit `join` [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` gebruikt.

    De onderstaande query wordt gebruikt om het unieke e-mailadres van geadresseerden te tellen, dat kan worden uitgevoerd in de honderden `summarize` duizenden grote organisaties. In dit onderdeel zijn de volgende elementen opgenomen om de prestaties te `hint.shufflekey` verbeteren:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>Queryscenario's

### <a name="identify-unique-processes-with-process-ids"></a>Unieke processen identificeren met proces-ids
Proces-inds (PID's) worden in Windows vernietigd en hergebruikt voor nieuwe processen. Ze kunnen niet als unieke id's fungeren voor specifieke processen.

Als u een unieke id wilt krijgen voor een proces op een specifieke computer, gebruikt u de proces-id samen met de aanmaaktijd van het proces. Wanneer u gegevens rond processen joint of samenvatten, voegt u kolommen toe voor de computer-id (of), de proces-id (of), en de aanmaaktijd van het proces `DeviceId` `DeviceName` `ProcessId` `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` (of)

Met de volgende voorbeeldquery worden processen gevonden die toegang krijgen tot meer dan tien IP-adressen via poort 445 (SMB), mogelijk zoeken naar bestands shares.

Voorbeeldquery:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

De query is een samenvatting van beide processen, waarbij wordt uitgemaakt van één proces, zonder dat meerdere processen met dezelfde `InitiatingProcessId` proces-id worden door elkaar `InitiatingProcessCreationTime` gebruikt.

### <a name="query-command-lines"></a>Opdrachtlijnen voor query's
Er zijn talloze manieren om een opdrachtregel te maken om een taak uit te voeren. Een aanvaller kan bijvoorbeeld verwijzen naar een afbeeldingsbestand zonder pad, zonder bestandsextensie, met behulp van omgevingsvariabelen of met aanhalingstekens. De aanvaller kan ook de volgorde van parameters wijzigen of meerdere aanhalingstekens en spaties toevoegen.

Als u meer query's met een strakker beleid rond opdrachtlijnen wilt maken, moet u de volgende procedures toepassen:

- Identificeer de bekende processen  (zoalsnet.exeof *psexec.exe)* door op de bestandsnaamvelden te matchen in plaats van op de opdrachtregel zelf te filteren.
- Opdrachtregelsecties parseren met de functie [parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- Zoek bij het opvragen van opdrachtregelargumenten niet naar een exacte overeenkomst voor meerdere niet-gerelateerde argumenten in een bepaalde volgorde. Gebruik in plaats daarvan reguliere expressies of gebruik meerdere afzonderlijke expressies met operatoren.
- Niet-opsitieve overeenkomsten voor case's gebruiken. Gebruik bijvoorbeeld `=~` , `in~` en in plaats van , en `contains` `==` `in` `contains_cs` .
- U kunt technieken voor het obliceren van opdrachten voorkomen door aanhalingstekens te verwijderen, komma's te vervangen door spaties en meerdere opeenvolgende spaties te vervangen door één spatie. Er zijn complexere obfusatietechnieken die andere benaderingen vereisen, maar deze aanpassingen kunnen u helpen algemene technieken aan te pakken.

In de volgende voorbeelden ziet u verschillende manieren  om een query te maken die zoekt naar het bestandnet.exeom de firewallservice MpsSvc te stoppen:

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on file name, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

### <a name="ingest-data-from-external-sources"></a>Gegevens uit externe bronnen insgest maken
Als u lange lijsten of grote tabellen wilt opnemen in uw query, gebruikt u de [externaldata-operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) om gegevens uit een opgegeven URI over te nemen. U kunt gegevens op halen uit bestanden in TXT, CSV, JSON of [andere indelingen.](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats) In het onderstaande voorbeeld ziet u hoe u de uitgebreide lijst met malware SHA-256-hashes van MalwareBazaar (abuse.ch) kunt gebruiken om bijlagen bij e-mailberichten te controleren:

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string )
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo 
| where Timestamp > ago(1d) 
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,MalwareFilterVerdict,MalwareDetectionMethod
```

### <a name="parse-strings"></a>Parseren-tekenreeksen
Er zijn verschillende functies die u kunt gebruiken om efficiënt om te gaan met tekenreeksen die moeten worden geparseren of geconveriseerd. 

| Tekenreeks | Functie | Gebruiksvoorbeeld |
|--|--|--|
| Opdrachtregels | [parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | De opdracht en alle argumenten extraheren. | 
| Paden | [parse_path()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | Extraheren de secties van een bestand of mappad. |
| Versienummers | [parse_version()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Deconstructer een versienummer met maximaal vier secties en maximaal acht tekens per sectie. Gebruik de geparseerde gegevens om de leeftijd van de versie te vergelijken. |
| IPv4-adressen | [parse_ipv4()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | Converteert een IPv4-adres naar een lang geheel getal. Als u IPv4-adressen wilt vergelijken zonder deze te converteren, gebruikt [u ipv4_compare().](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction) |
| IPv6-adressen | [parse_ipv6()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | Converteert een IPv4- of IPv6-adres naar de canonieke IPv6-notatie. Als u IPv6-adressen wilt vergelijken, gebruikt [ipv6_compare().](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction) |

Voor meer informatie over alle ondersteunde parseringsfuncties leest [u meer over Kusto-tekenreeksfuncties.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions) 

## <a name="related-topics"></a>Verwante onderwerpen
- [Taaldocumentatie voor kusto-query's](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [Quota en gebruiksparameters](advanced-hunting-limits.md)
- [Geavanceerde zoekfouten verwerken](advanced-hunting-errors.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
