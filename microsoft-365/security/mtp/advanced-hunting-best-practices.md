---
title: Geavanceerde best practices voor query's in Microsoft 365 Defender
description: Meer informatie over het maken van snelle, efficiënte en foutloze zoekquery's voor bedreigingen met geavanceerde jacht
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
ms.openlocfilehash: e838ce873a1c3ecc0f437f96e75cc2a40d3af79d
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727269"
---
# <a name="advanced-hunting-query-best-practices"></a>Geavanceerde best practices voor query's

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Pas deze aanbevelingen toe om sneller resultaten te krijgen en time-outs te vermijden tijdens het uitvoeren van complexe query's. Lees [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices)voor meer informatie over het verbeteren van queryprestaties.

## <a name="understand-cpu-resource-quotas"></a>Informatie over CPU-resourcequota's
Afhankelijk van de grootte heeft elke tenant toegang tot een bepaalde hoeveelheid CPU-resources die is toegewezen voor het uitvoeren van geavanceerde query's. Meer informatie over verschillende servicelimieten vindt [u in geavanceerde jachtquota's en gebruiksparameters.](advanced-hunting-limits.md)

Klanten die regelmatig meerdere query's uitvoeren, moeten het verbruik bijhouden en de optimalisatie-richtlijnen in dit artikel toepassen om verstoringen als gevolg van het overschrijden van quota of gebruiksparameters tot een minimum te beperken.

## <a name="general-optimization-tips"></a>Tips voor algemene optimalisatie

- **Grootte van nieuwe query's:** als u vermoedt dat een query een grote resultatenset retourneert, beoordeelt u deze eerst met de [operator aantal.](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator) Gebruik [limiet](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) of het synoniem om `take` grote resultatensets te voorkomen.
- Filters vroeg toepassen **:** pas tijdfilters en andere filters toe om de gegevensset te verminderen, met name voordat u transformatie- en parsingsfuncties gebruikt, zoals [subteken()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [vervangen()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction) [of parse_json().](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction) In het onderstaande voorbeeld wordt de parsingsfunctie [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) gebruikt nadat filteroperatoren het aantal records hebben verminderd.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Bevat verslaat**-Als u wilt voorkomen dat u onnodig subtekens in woorden zoekt, gebruikt u de `has` operator in plaats van `contains` . [Meer informatie over tekenreeksoperatoren](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Zoeken in specifieke kolommen:** kijk in een specifieke kolom in plaats van volledige tekst te zoeken in alle kolommen. Gebruik niet om `*` alle kolommen te controleren.
- **Case-sensitive for speed**:Case-sensitive searches are more specific and generally more performant. Namen van case-sensitive [tekenreeksoperatoren,](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)zoals `has_cs` en , eindigen meestal op `contains_cs` `_cs` . U kunt ook de operator case-sensitive equals `==` gebruiken in plaats van `=~` .
- **Parseren, niet extraheren**: gebruik indien mogelijk de [parse-operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) of een parsingsfunctie zoals [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). Vermijd de `matches regex` tekenreeksoperator of [de functie extract(),](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)die beide een normale expressie gebruiken. Reserveer het gebruik van reguliere expressie voor complexere scenario's. [Meer informatie over parsingsfuncties](#parse-strings)
- **Tabellen filteren zonder expressies:** filter niet op een berekende kolom als u kunt filteren op een tabelkolom.
- **Geen termen met drie tekens:** vermijd het vergelijken of filteren met termen met drie tekens of minder. Deze termen worden niet geïndexeerd en er zijn meer resources voor nodig.
- **Project selectief:** maak uw resultaten begrijpelijker door alleen de kolommen te projecteren die u nodig hebt. Als u specifieke kolommen projecteert vóór het uitvoeren van [join-](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) of soortgelijke bewerkingen, worden de prestaties ook verbeterd.

## <a name="optimize-the-join-operator"></a>De `join` operator optimaliseren
De [joinoperator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) voegt rijen uit twee tabellen samen door waarden in opgegeven kolommen te koppelen. Pas deze tips toe om query's te optimaliseren die deze operator gebruiken.

- **Kleinere tabel aan de linkerkant:** de operator komt overeen met records in de tabel aan de linkerkant van de `join` join-instructie voor records aan de rechterkant. Door de kleinere tabel aan de linkerkant te hebben, hoeven er minder records te worden gematcht, waardoor de query sneller wordt uitgevoerd. 

    In de onderstaande tabel beperken we de linkertabel tot slechts drie specifieke apparaten voordat we er met `DeviceLogonEvents` `IdentityLogonEvents` account-SID's aan deelnemen.
 
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

- **Gebruik de inner-join-smaak**: de standaard join-smaak of de [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rijen in de linkertabel door de join-toets voordat u een rij voor elke overeenkomst terugstuurt naar de rechtertabel. [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) Als de linkertabel meerdere rijen heeft met dezelfde waarde voor de sleutel, worden deze rijen gededuplicaeerd om één willekeurige rij achter te laten `join` voor elke unieke waarde.

    Dit standaardgedrag kan belangrijke informatie weg laten uit de linkertabel die nuttig inzicht kan bieden. In de onderstaande query wordt bijvoorbeeld slechts één e-mailbericht met een bepaalde bijlage weergegeven, zelfs als dezelfde bijlage is verzonden met meerdere e-mailberichten:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    Om deze beperking aan te pakken, passen we de [inner-join-smaak](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) toe door op te geven om alle rijen in de linkertabel weer te geven met overeenkomende `kind=inner` waarden aan de rechterkant:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Deelnemen aan records vanuit een tijdvenster:** bij het onderzoeken van beveiligingsgebeurtenissen zoeken analisten naar gerelateerde gebeurtenissen die zich rond dezelfde periode voordoen. Door dezelfde benadering toe te passen bij het gebruik van ook de prestaties, vermindert u het `join` aantal records dat u moet controleren.
    
    In de onderstaande query wordt gecontroleerd op aanmeldingsgebeurtenissen binnen 30 minuten na ontvangst van een schadelijk bestand:

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where ThreatTypes has "Malware"
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- **Tijdfilters** aan beide zijden toepassen: zelfs als u geen specifiek tijdvenster onderzoekt, kan het toepassen van tijdfilters op zowel de linker- als rechtertabellen het aantal records verminderen om de prestaties te controleren en te `join` verbeteren. De onderstaande query is van toepassing op beide tabellen, zodat alleen records uit het afgelopen uur `Timestamp > ago(1h)` worden joins:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Gebruik hints voor prestaties:** gebruik hints met de operator om de backend te instrueren om de belasting te verdelen tijdens het uitvoeren van `join` resourceintensieve bewerkingen. [Meer informatie over tips voor deelnemen](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Met de **[hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** voor shuffle kunt u bijvoorbeeld de prestaties van query's verbeteren wanneer u aan tabellen deelt met behulp van een toets met een hoge kardinaliteit, een sleutel met veel unieke waarden, zoals `AccountObjectId` de in de onderstaande query:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    De **[hint voor uitzending](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helpt wanneer de linkertabel klein is (maximaal 100.000 records) en de rechtertabel zeer groot is. In de onderstaande query wordt bijvoorbeeld geprobeerd deel te  nemen aan een paar e-mailberichten met specifieke onderwerpen met alle berichten met koppelingen in de `EmailUrlInfo` tabel:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>De `summarize` operator optimaliseren
De [samenvattende operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregeert de inhoud van een tabel. Pas deze tips toe om query's te optimaliseren die deze operator gebruiken.

- **Afzonderlijke waarden zoeken:** in het algemeen kunt u verschillende waarden `summarize` zoeken die herhalend kunnen zijn. Het kan onnodig zijn om het te gebruiken om kolommen te aggregeren die geen terugkerende waarden hebben.

    Hoewel één e-mailbericht deel kan uitmaken van meerdere gebeurtenissen, _is_ het onderstaande voorbeeld niet efficiënt omdat een netwerkbericht-id voor een afzonderlijke e-mail altijd wordt geleverd met een uniek `summarize` afzenderadres.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    De operator kan eenvoudig worden vervangen door , wat mogelijk dezelfde resultaten oplevert en minder `summarize` `project` resources verbruikt:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    Het volgende voorbeeld is een efficiënter gebruik van omdat er meerdere afzonderlijke exemplaren kunnen zijn van een afzenderadres dat e-mail naar hetzelfde adres `summarize` van de geadresseerde verstuurt. Dergelijke combinaties zijn minder verschillend en hebben waarschijnlijk dubbele waarden.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **Schuif de query door** elkaar: hoewel deze het beste wordt gebruikt in kolommen met terugkerende waarden, kunnen dezelfde kolommen ook een hoge kardinaliteit of grote `summarize` aantallen unieke waarden  hebben. Net als de operator kunt u ook de schuifelhint toepassen om de verwerkingsbelasting te verdelen en de prestaties mogelijk te verbeteren wanneer u werkt op `join` kolommen met een hoge [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` kardinaliteit.

    In de onderstaande query wordt het afzonderlijke e-mailadres van de geadresseerde geteld, dat kan worden uitgevoerd in de `summarize` honderdduizenden in grote organisaties. Om de prestaties te verbeteren, bevat het `hint.shufflekey` de volgende elementen:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>Queryscenario's

### <a name="identify-unique-processes-with-process-ids"></a>Unieke processen identificeren met proces-eds
Proces-ID's (PID's) worden in Windows hergebruikt en opnieuw gebruikt voor nieuwe processen. Op zichzelf kunnen ze niet fungeren als unieke id's voor specifieke processen.

Als u een unieke id wilt krijgen voor een proces op een specifieke computer, gebruikt u de proces-id samen met de tijd voor het maken van het proces. Wanneer u gegevens rond processen bij elkaar voegt of samenvatten, kunt u kolommen opnemen voor de machine-id (of), de proces-id (of), en de tijd voor het maken `DeviceId` `DeviceName` van het proces `ProcessId` `InitiatingProcessId` `ProcessCreationTime` (of `InitiatingProcessCreationTime` )

In de volgende voorbeeldquery worden processen gevonden die toegang hebben tot meer dan 10 IP-adressen via poort 445 (SMB), mogelijk scannen op bestandsaandelen.

Voorbeeldquery:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

De query wordt op beide manieren samengevat, zodat er naar één proces wordt ge kijkt, zonder dat meerdere processen met dezelfde `InitiatingProcessId` `InitiatingProcessCreationTime` proces-id worden vermengd.

### <a name="query-command-lines"></a>Opdrachtregels voor query's
Er zijn verschillende manieren om een opdrachtregel te maken om een taak uit te voeren. Een aanvaller kan bijvoorbeeld verwijzen naar een afbeeldingsbestand zonder pad, zonder bestandsextensie, met omgevingsvariabelen of met aanhalingstekens. De aanvaller kan ook de volgorde van parameters wijzigen of meerdere aanhalingstekens en spaties toevoegen.

Als u duurzamere query's wilt maken rond opdrachtlijnen, moet u de volgende procedures toepassen:

- Identificeer de bekende processen (zoalsnet.exe *of* *psexec.exe)* door op de bestandsnaamvelden te matchen in plaats van te filteren op de opdrachtregel zelf.
- Opdrachtregelsecties parseren met de [functie parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- Wanneer u query's uitvoert voor opdrachtregelargumenten, moet u niet zoeken naar een exacte overeenkomst voor meerdere niet-gerelateerde argumenten in een bepaalde volgorde. Gebruik in plaats daarvan gewone expressies of gebruik meerdere afzonderlijke operatoren.
- Gebruik case insensitive matches. Gebruik bijvoorbeeld `=~` , `in~` en in plaats van , en `contains` `==` `in` `contains_cs` .
- Als u obfuscationtechnieken voor opdrachtregelen wilt beperken, kunt u aanhalingstekens verwijderen, komma's vervangen door spaties en meerdere opeenvolgende spaties vervangen door één spatie. Er zijn complexere obfuscation-technieken waarvoor andere methoden nodig zijn, maar deze aanpassingen kunnen helpen bij het aanpakken van veelvoorkomende technieken.

In de volgende voorbeelden ziet u verschillende manieren  om een query te maken die zoekt naar het bestandnet.exeom de firewallservice "MpsSvc" te stoppen:

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

### <a name="ingest-data-from-external-sources"></a>Gegevens uit externe bronnen opnemen
Als u lange lijsten of grote tabellen wilt opnemen in uw query, gebruikt u de [operator externaldata om](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) gegevens uit een opgegeven URI op te nemen. U kunt gegevens opmaken uit bestanden in TXT, CSV, JSON [of andere indelingen.](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats) In het onderstaande voorbeeld ziet u hoe u de uitgebreide lijst met malware SHA-256-hashes van MalwareBazaar (abuse.ch) kunt gebruiken om bijlagen in e-mailberichten te controleren:

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
SHA256,ThreatTypes,DetectionMethods
```

### <a name="parse-strings"></a>Tekenreeksen parseren
Er zijn verschillende functies die u kunt gebruiken om efficiënt om te gaan met tekenreeksen die parsing of conversie nodig hebben. 

| Tekenreeks | Functie | Gebruiksvoorbeeld |
|--|--|--|
| Opdrachtlijnen | [parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | Haal de opdracht en alle argumenten op. | 
| Paden | [parse_path()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | Haal de secties van een bestands- of mappad op. |
| Versienummers | [parse_version()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Deconstructie van een versienummer met maximaal vier secties en maximaal acht tekens per sectie. Gebruik de geparseerde gegevens om versieleeftijd te vergelijken. |
| IPv4-adressen | [parse_ipv4()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | Een IPv4-adres converteren naar een lang geheel getal. Als u IPv4-adressen wilt vergelijken zonder deze te converteren, gebruikt [u ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| IPv6-adressen | [parse_ipv6()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | Converteert een IPv4- of IPv6-adres naar de canonieke IPv6-notatie. Als u IPv6-adressen wilt vergelijken, gebruikt [u ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Als u meer wilt weten over alle ondersteunde parsingsfuncties, [leest u meer over kusto-tekenreeksfuncties.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions) 

## <a name="related-topics"></a>Verwante onderwerpen
- [Documentatie van kustoquerytaal](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [Quota en gebruiksparameters](advanced-hunting-limits.md)
- [Geavanceerde zoekfouten verwerken](advanced-hunting-errors.md)
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
