---
title: Best practices voor geavanceerde zoekactie in Microsoft Threat Protection
description: Ontdek hoe u Fast, efficient en error-free Threat queries kunt maken met geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema, kusto, timeout, opdrachtregels, proces-id, optimaliseren, aanbevolen oefenen, parseren, samenvatting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: e3b29a8182e38fa05e5f791478157c978632fb13
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477003"
---
# <a name="advanced-hunting-query-best-practices"></a>Best practices voor geavanceerde zoekactie

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

Pas deze aanbevelingen toe om resultaten sneller te vinden en time-outs te voorkomen tijdens het uitvoeren van complexe query's. Lees voor meer informatie over het verbeteren van de prestaties van query's het artikel [Best practices voor Kusto query](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-limits"></a>Meer informatie over de limieten voor CPU-bronnen
Afhankelijk van de grootte, heeft elke Tenant toegang tot een ingestelde hoeveelheid processorbronnen die zijn toegewezen voor het uitvoeren van geavanceerde jacht-query's. Meer informatie over de verschillende service limieten vindt u in meer informatie [over geavanceerde jacht-limieten](advanced-hunting-limits.md).

Klanten die regelmatig meerdere query's uitvoeren, moeten het verbruik bijhouden en de optimaliserings richtlijnen toepassen in dit artikel om te voorkomen dat het minder storing oplevert dan de limieten.

## <a name="general-optimization-tips"></a>Algemene optimaliserings tips

- **Grootte van nieuwe query's**: als u vermoedt dat een query een grote resultatenset oplevert, moet u deze eerst beoordelen met de [operator Count](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator). Gebruik [Limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) of het synoniem `take` om grote resultaatsets te voorkomen.
- **Filters eerst toepassen**: tijdfilters en andere filters toepassen om de gegevensverzameling te beperken, vooral voordat u functies voor transformeren en parseren gebruikt, zoals de [subtekenreeks ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [vervangen (](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction)), [Trim (](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction)), [ToUpper (](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)) of [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). In het onderstaande voorbeeld wordt de functie voor parseren [(extractjson)](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) gebruikt nadat gefilterde operatoren het aantal records hebben verminderd.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Heeft maten bevat**: als u wilt voorkomen dat er in woorden in subtekenreeksen wordt gezocht, gebruikt u de `has` operator in plaats van `contains` . [Meer informatie over tekenreeks operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Zoeken in specifieke kolommen**: Bekijk in een specifieke kolom of de zoekfunctie voor volledige tekst in alle kolommen niet wordt uitgevoerd. Niet gebruiken `*` voor het controleren van alle kolommen.
- **Onderscheid tussen hoofdletters**en kleine letters: Hoofdlettergevoelige zoekopdrachten zijn specifieker en algemeenere prestaties. Namen van hoofdlettergevoelige [tekenreeks operatoren](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), zoals `has_cs` en `contains_cs` , meestal eindigt op `_cs` . U kunt ook de operator voor hoofdlettergevoelige gelijktekens gebruiken `==` in plaats van `=~` .
- **Parseren**: gebruik indien mogelijk de [operator voor parseren](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) of een functie voor parseren, zoals [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). Vermijd de `matches regex` tekenreeks operator of de [functie extraheren ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), waarvan beide de reguliere expressie gebruiken. Het gebruik van een reguliere expressie reserveren voor complexere scenario's. [Lees meer over het verdelen van functies](#parse-strings)
- **Tabellen niet op expressies**filteren: u hoeft niet op een berekende kolom te filteren als u een tabelkolom kunt filteren.
- **Geen voorwaarden van drie**tekens: vergelijkt of filteren met termen met drie tekens of minder. Deze voorwaarden worden niet geïndexeerd en hieraan voldoen meer resources nodig.
- **Project selectief**Maak uw resultaten eenvoudiger te begrijpen door alleen de gewenste kolommen te delen. Wanneer u specifieke kolommen vergelijkt voordat u [deelneemt](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) of vergelijkbare bewerkingen uitvoert, kunt u ook de prestaties verbeteren.

## <a name="optimize-the-join-operator"></a>De `join` operator optimaliseren
Met de [operator JOIN worden](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) rijen uit twee tabellen samengevoegd met de waarden in de opgegeven kolommen. Deze tips toepassen om query's met deze operator te optimaliseren.

- **Kleinere tabel aan de linkerkant**: de `join` operator komt overeen met records in de tabel aan de linkerkant van de JOIN-instructie, zodat ze aan de rechterkant van de join worden vastgelegd. Als u de kleinere tabel aan de linkerkant wilt hebben, moeten minder records worden vergeleken, zodat de query sneller wordt. 

    In de onderstaande tabel verkleint u de linkertabel, `DeviceLogonEvents` zodat er slechts drie specifieke apparaten worden ondergebracht voordat ze worden toegevoegd aan de `IdentityLogonEvents` sid's van uw account.
 
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

- **Gebruik de inwendige koppeling**-reeks, de standaard [koppelings](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) -of innerunique, en de join [-join-](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) rijen in de linkertabel dedupliceert. Als de linkertabel meerdere rijen met dezelfde waarde voor de `join` sleutel bevat, worden deze rijen ontdubbeld om één willekeurige rij voor elke unieke waarde te verlaten.

    Dit standaardgedrag kan belangrijke informatie uit de linkertabel verlaten die nuttige inzichten kan geven. Met de query hieronder wordt bijvoorbeeld slechts één e-mailbericht weergegeven met een bepaalde bijlage, zelfs als de bijlage meerdere e-mailberichten heeft verzonden:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    Als u deze beperking wilt gebruiken, past u de [binnenste deel-deel-de-deel-](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) de waarde toe door het `kind=inner` volgende op te geven om alle rijen in de linkertabel weer te geven met overeenkomende waarden in de rechter
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Records van een tijdvenster samenvoegen in**de analisten van beveiligingsgebeurtenissen wordt gezocht naar gerelateerde gebeurtenissen die zich in dezelfde tijdsperiode voordoen. Het toepassen van dezelfde aanpak wanneer u de `join` prestaties van de voordelen ervan beperkt, door het aantal te controleren records te verminderen.
    
    Met de query onder wordt gecontroleerd op Aanmeldingsgebeurtenissen binnen 30 minuten na ontvangst van een schadelijk bestand:

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
- **Filter tijdfilters toepassen**, ook als u geen specifiek tijdsvenster beonderzoekt en u geen specifiek tijdsvenster beoordeelt, kunt u het aantal records in de linker-en rechtertabel verkleinen om de prestaties te controleren en de prestaties te verbeteren `join` . De query hieronder geldt `Timestamp > ago(1h)` voor beide tabellen, zodat alleen records van het afgelopen uur worden samengevoegd:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Gebruik hints voor prestaties**— gebruik hints met de `join` operator om de backend te laten verdelen bij het uitvoeren van bronnen die intensief gebruikmaken van bronnen. [Meer informatie over join-hints](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Met de hint voor een **[willekeurige volgorde](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** kunt u de queryprestaties voor de samenvoeging van tabellen met een hoge kardinaliteit verbeteren, een sleutel met veel unieke waarden, zoals de `AccountObjectId` query hieronder:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    De **[Hint voor uitzending](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helpt wanneer de linkertabel klein (maximaal 100.000 records) is en de juiste tabel zeer groot is. Met de onderstaande query probeert u bijvoorbeeld deel te nemen aan een paar e-mailberichten met specifieke onderwerpen met _alle_ berichten in de `EmailUrlInfo` tabel:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>De `summarize` operator optimaliseren
Met de [operator samenvatten](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) wordt de inhoud van een tabel geaggregeerd. Deze tips toepassen om query's met deze operator te optimaliseren.

- **Distinct values zoeken**: in het algemeen `summarize` kunt u zoeken naar unieke waarden die herhaald kunnen zijn. Het is niet mogelijk om kolommen te gebruiken die geen herhalings waarden bevatten.

    Hoewel één e-mailbericht deel kan uitmaken van meerdere gebeurtenissen, vormt het voorbeeld hieronder _geen_ efficiënt gebruik `summarize` omdat een netwerkbericht-id voor een apart e-mailbericht altijd een uniek adres van de afzender bevat.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    U `summarize` kunt eenvoudig de operator vervangen door `project` de resultaten van het gebruik van minder bronnen te brengen:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    Het volgende voorbeeld is een efficiëntere manier van `summarize` omdat er meerdere verschillende exemplaren van een afzender e-mailadres aan hetzelfde adres van de geadresseerde kunnen worden verzonden. Deze combinaties zijn minder verschillend en zijn waarschijnlijk dubbele waarden.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- U kunt **de query in een willekeurige volgorde**plaatsen, terwijl u `summarize` het beste kunt gebruiken in kolommen met herhalende waarden, kan dezelfde kolom ook _hoge kardinaliteit_ of grote getallen met unieke waarden bevatten. Net als `join` bij de operator kunt u ook de [Hint van een willekeurige volgorde](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) toepassen `summarize` om de verwerkingsbelasting te verdelen en de prestaties te verbeteren wanneer u op kolommen met een hoge kardinaliteit werkt.

    Met de onderstaande query `summarize` kunt u het e-mailadres van een verschillend e-mailadres tellen, dat kan worden uitgevoerd in de honderden duizenden in grote organisaties. Ter verbetering van de prestaties `hint.shufflekey` :

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>Query scenario's

### <a name="identify-unique-processes-with-process-ids"></a>Unieke processen identificeren met proces-Id's
Proces-Id's in Windows worden gerecycled en opnieuw gebruikt voor nieuwe processen. Ze kunnen op hun eigen manier geen unieke id's voor specifieke processen gebruiken.

Als u een unieke aanduiding wilt krijgen voor een proces op een specifieke computer, gebruikt u de proces-ID samen met de Aanmaaktijd van het proces. Wanneer u gegevens rond processen samenvoegt of samenvoegt, neemt u kolommen op voor de machine-id (of `DeviceId` `DeviceName` ), de proces-id ( `ProcessId` of `InitiatingProcessId` ) en de tijd waarop het proces is gemaakt ( `ProcessCreationTime` of `InitiatingProcessCreationTime` ).

Met de volgende voorbeeldquery vindt u processen die toegang hebben tot meer dan 10 IP-adressen via poort 445 (SMB), mogelijk met de scanfunctie voor bestandsshares.

Voorbeeldquery:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

De query geeft een samenvatting van beide `InitiatingProcessId` `InitiatingProcessCreationTime` processen weer, zodat de query één proces uitziet, zonder meerdere processen met hetzelfde proces-id te kunnen combineren.

### <a name="query-command-lines"></a>Opdrachtregels van query
U kunt op verschillende manieren een opdrachtregel maken om een taak uit te voeren. Een aanvaller kan bijvoorbeeld verwijzen naar een afbeeldingsbestand zonder een pad zonder bestandsextensie, omgevingsvariabelen of met aanhalingstekens gebruiken. De aanvaller kan ook de volgorde van parameters wijzigen of meerdere aanhalingstekens en spaties toevoegen.

U kunt de volgende procedures toepassen als u meer duurzame query's wilt maken rond opdrachtregels:

- Identificeer de bekende processen (zoals *net.exe* of *psexec.exe*) door te zoeken in de velden voor de bestandsnaam, in plaats van te filteren op de opdrachtregel zelf.
- Opdrachtregel secties parseren met behulp van de [functie parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- Wanneer u een query uitvoert voor opdrachtregelargumenten, zoekt u niet naar een exacte overeenkomst voor meerdere niet-gerelateerde argumenten in een bepaalde volgorde. Gebruik in plaats daarvan reguliere expressies of gebruik van meerdere aparte operatoren.
- Gebruik hoofdlettergevoelige overeenkomsten. Gebruik bijvoorbeeld, `=~` `in~` en `contains` in plaats van `==` , `in` en `contains_cs` .
- Als u de opdrachtregel wilt beperken, kunt u aanhalingstekens verwijderen, komma's vervangen door spaties en meerdere opeenvolgende spaties vervangen door één spatie. U kunt meer complexe methoden voor het maken van donkere en donkere kolommen waarvoor u andere benaderingen nodig hebt, maar deze kunnen door u gemeenschappelijke oplossingen worden gebruikt.

In de volgende voorbeelden ziet u verschillende manieren om een query te maken waarmee wordt gezocht naar het bestand dat *net.exe* de firewall service ' MpsSvc ' niet meer nodig hebt:

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

### <a name="ingest-data-from-external-sources"></a>Ingestie gegevens uit externe bronnen
Als u in uw query lange lijsten of grote tabellen wilt opnemen, gebruikt u de [externaldata-operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) om gegevens op te nemen uit een bepaalde URI. U kunt gegevens uit bestanden vinden in TXT-, CSV-, JSON-of [andere indelingen](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats). In het onderstaande voorbeeld ziet u hoe u de uitgebreide lijst met malware-256-hashwaarden van MalwareBazaar (abuse.ch) kunt gebruiken voor het controleren van bijlagen op e-mailberichten:

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

### <a name="parse-strings"></a>Parserings tekenreeksen
Er zijn verschillende functies die u kunt gebruiken om de tekenreeksen die moeten worden geparseerd of geconverteerd, op efficiënte wijze af te handelen. 

| Tekenreeks | Optie | Voorbeeld van gebruik |
|--|--|--|
| Opdrachtregel | [parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | De opdracht en alle argumenten extraheren. | 
| Routes | [parse_path ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | De secties van een pad naar een bestand of map extraheren. |
| Versienummers | [parse_version ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Ontconstrueren van een versienummer met maximaal vier secties en maximaal acht tekens per sectie. Gebruik de geparseerde gegevens om de versie ouderdom te vergelijken. |
| IPv4-adressen | [parse_ipv4 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | Converteer een IPv4-adres naar een lang geheel getal. Als u IPv4-adressen wilt vergelijken zonder ze te converteren, gebruikt u [ipv4_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| IPv6-adressen | [parse_ipv6 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | Converteer een IPv4-of IPv6-adres naar de canonieke IPv6-notatie. Gebruik [ipv6_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)om IPv6-adressen te vergelijken. |

Meer informatie over alle ondersteunde functies voor het parseren van functies vindt u in [Kusto tekenreeksfuncties](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions). 

## <a name="related-topics"></a>Verwante onderwerpen
- [Kusto querytaal documentatie](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [Servicelimieten](advanced-hunting-limits.md)
- [Geavanceerde jacht-fouten verwerken](advanced-hunting-errors.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
