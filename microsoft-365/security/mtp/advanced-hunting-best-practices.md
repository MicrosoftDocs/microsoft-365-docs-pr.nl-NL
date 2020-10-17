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
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="2d8ac-104">Best practices voor geavanceerde zoekactie</span><span class="sxs-lookup"><span data-stu-id="2d8ac-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2d8ac-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2d8ac-105">**Applies to:**</span></span>
- <span data-ttu-id="2d8ac-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2d8ac-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2d8ac-107">Pas deze aanbevelingen toe om resultaten sneller te vinden en time-outs te voorkomen tijdens het uitvoeren van complexe query's.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="2d8ac-108">Lees voor meer informatie over het verbeteren van de prestaties van query's het artikel [Best practices voor Kusto query](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="2d8ac-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-limits"></a><span data-ttu-id="2d8ac-109">Meer informatie over de limieten voor CPU-bronnen</span><span class="sxs-lookup"><span data-stu-id="2d8ac-109">Understand CPU resource limits</span></span>
<span data-ttu-id="2d8ac-110">Afhankelijk van de grootte, heeft elke Tenant toegang tot een ingestelde hoeveelheid processorbronnen die zijn toegewezen voor het uitvoeren van geavanceerde jacht-query's.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="2d8ac-111">Meer informatie over de verschillende service limieten vindt u in meer informatie [over geavanceerde jacht-limieten](advanced-hunting-limits.md).</span><span class="sxs-lookup"><span data-stu-id="2d8ac-111">For detailed information about various service limits, [read about advanced hunting limits](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="2d8ac-112">Klanten die regelmatig meerdere query's uitvoeren, moeten het verbruik bijhouden en de optimaliserings richtlijnen toepassen in dit artikel om te voorkomen dat het minder storing oplevert dan de limieten.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding the limits.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="2d8ac-113">Algemene optimaliserings tips</span><span class="sxs-lookup"><span data-stu-id="2d8ac-113">General optimization tips</span></span>

- <span data-ttu-id="2d8ac-114">**Grootte van nieuwe query's**: als u vermoedt dat een query een grote resultatenset oplevert, moet u deze eerst beoordelen met de [operator Count](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span><span class="sxs-lookup"><span data-stu-id="2d8ac-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="2d8ac-115">Gebruik [Limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) of het synoniem `take` om grote resultaatsets te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-115">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="2d8ac-116">**Filters eerst toepassen**: tijdfilters en andere filters toepassen om de gegevensverzameling te beperken, vooral voordat u functies voor transformeren en parseren gebruikt, zoals de [subtekenreeks ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [vervangen (](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction)), [Trim (](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction)), [ToUpper (](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)) of [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="2d8ac-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="2d8ac-117">In het onderstaande voorbeeld wordt de functie voor parseren [(extractjson)](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) gebruikt nadat gefilterde operatoren het aantal records hebben verminderd.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-117">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="2d8ac-118">**Heeft maten bevat**: als u wilt voorkomen dat er in woorden in subtekenreeksen wordt gezocht, gebruikt u de `has` operator in plaats van `contains` .</span><span class="sxs-lookup"><span data-stu-id="2d8ac-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="2d8ac-119">Meer informatie over tekenreeks operators</span><span class="sxs-lookup"><span data-stu-id="2d8ac-119">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="2d8ac-120">**Zoeken in specifieke kolommen**: Bekijk in een specifieke kolom of de zoekfunctie voor volledige tekst in alle kolommen niet wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="2d8ac-121">Niet gebruiken `*` voor het controleren van alle kolommen.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="2d8ac-122">**Onderscheid tussen hoofdletters**en kleine letters: Hoofdlettergevoelige zoekopdrachten zijn specifieker en algemeenere prestaties.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="2d8ac-123">Namen van hoofdlettergevoelige [tekenreeks operatoren](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), zoals `has_cs` en `contains_cs` , meestal eindigt op `_cs` .</span><span class="sxs-lookup"><span data-stu-id="2d8ac-123">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="2d8ac-124">U kunt ook de operator voor hoofdlettergevoelige gelijktekens gebruiken `==` in plaats van `=~` .</span><span class="sxs-lookup"><span data-stu-id="2d8ac-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="2d8ac-125">**Parseren**: gebruik indien mogelijk de [operator voor parseren](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) of een functie voor parseren, zoals [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="2d8ac-125">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="2d8ac-126">Vermijd de `matches regex` tekenreeks operator of de [functie extraheren ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), waarvan beide de reguliere expressie gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-126">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="2d8ac-127">Het gebruik van een reguliere expressie reserveren voor complexere scenario's.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="2d8ac-128">Lees meer over het verdelen van functies</span><span class="sxs-lookup"><span data-stu-id="2d8ac-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="2d8ac-129">**Tabellen niet op expressies**filteren: u hoeft niet op een berekende kolom te filteren als u een tabelkolom kunt filteren.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="2d8ac-130">**Geen voorwaarden van drie**tekens: vergelijkt of filteren met termen met drie tekens of minder.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="2d8ac-131">Deze voorwaarden worden niet geïndexeerd en hieraan voldoen meer resources nodig.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="2d8ac-132">**Project selectief**Maak uw resultaten eenvoudiger te begrijpen door alleen de gewenste kolommen te delen.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="2d8ac-133">Wanneer u specifieke kolommen vergelijkt voordat u [deelneemt](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) of vergelijkbare bewerkingen uitvoert, kunt u ook de prestaties verbeteren.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-133">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="2d8ac-134">De `join` operator optimaliseren</span><span class="sxs-lookup"><span data-stu-id="2d8ac-134">Optimize the `join` operator</span></span>
<span data-ttu-id="2d8ac-135">Met de [operator JOIN worden](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) rijen uit twee tabellen samengevoegd met de waarden in de opgegeven kolommen.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-135">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="2d8ac-136">Deze tips toepassen om query's met deze operator te optimaliseren.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="2d8ac-137">**Kleinere tabel aan de linkerkant**: de `join` operator komt overeen met records in de tabel aan de linkerkant van de JOIN-instructie, zodat ze aan de rechterkant van de join worden vastgelegd.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="2d8ac-138">Als u de kleinere tabel aan de linkerkant wilt hebben, moeten minder records worden vergeleken, zodat de query sneller wordt.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="2d8ac-139">In de onderstaande tabel verkleint u de linkertabel, `DeviceLogonEvents` zodat er slechts drie specifieke apparaten worden ondergebracht voordat ze worden toegevoegd aan de `IdentityLogonEvents` sid's van uw account.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
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

- <span data-ttu-id="2d8ac-140">**Gebruik de inwendige koppeling**-reeks, de standaard [koppelings](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) -of innerunique, en de join [-join-](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) rijen in de linkertabel dedupliceert.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-140">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="2d8ac-141">Als de linkertabel meerdere rijen met dezelfde waarde voor de `join` sleutel bevat, worden deze rijen ontdubbeld om één willekeurige rij voor elke unieke waarde te verlaten.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="2d8ac-142">Dit standaardgedrag kan belangrijke informatie uit de linkertabel verlaten die nuttige inzichten kan geven.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="2d8ac-143">Met de query hieronder wordt bijvoorbeeld slechts één e-mailbericht weergegeven met een bepaalde bijlage, zelfs als de bijlage meerdere e-mailberichten heeft verzonden:</span><span class="sxs-lookup"><span data-stu-id="2d8ac-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="2d8ac-144">Als u deze beperking wilt gebruiken, past u de [binnenste deel-deel-de-deel-](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) de waarde toe door het `kind=inner` volgende op te geven om alle rijen in de linkertabel weer te geven met overeenkomende waarden in de rechter</span><span class="sxs-lookup"><span data-stu-id="2d8ac-144">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="2d8ac-145">**Records van een tijdvenster samenvoegen in**de analisten van beveiligingsgebeurtenissen wordt gezocht naar gerelateerde gebeurtenissen die zich in dezelfde tijdsperiode voordoen.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="2d8ac-146">Het toepassen van dezelfde aanpak wanneer u de `join` prestaties van de voordelen ervan beperkt, door het aantal te controleren records te verminderen.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="2d8ac-147">Met de query onder wordt gecontroleerd op Aanmeldingsgebeurtenissen binnen 30 minuten na ontvangst van een schadelijk bestand:</span><span class="sxs-lookup"><span data-stu-id="2d8ac-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

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
- <span data-ttu-id="2d8ac-148">**Filter tijdfilters toepassen**, ook als u geen specifiek tijdsvenster beonderzoekt en u geen specifiek tijdsvenster beoordeelt, kunt u het aantal records in de linker-en rechtertabel verkleinen om de prestaties te controleren en de prestaties te verbeteren `join` .</span><span class="sxs-lookup"><span data-stu-id="2d8ac-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="2d8ac-149">De query hieronder geldt `Timestamp > ago(1h)` voor beide tabellen, zodat alleen records van het afgelopen uur worden samengevoegd:</span><span class="sxs-lookup"><span data-stu-id="2d8ac-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="2d8ac-150">**Gebruik hints voor prestaties**— gebruik hints met de `join` operator om de backend te laten verdelen bij het uitvoeren van bronnen die intensief gebruikmaken van bronnen.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="2d8ac-151">Meer informatie over join-hints</span><span class="sxs-lookup"><span data-stu-id="2d8ac-151">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="2d8ac-152">Met de hint voor een **[willekeurige volgorde](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** kunt u de queryprestaties voor de samenvoeging van tabellen met een hoge kardinaliteit verbeteren, een sleutel met veel unieke waarden, zoals de `AccountObjectId` query hieronder:</span><span class="sxs-lookup"><span data-stu-id="2d8ac-152">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="2d8ac-153">De **[Hint voor uitzending](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helpt wanneer de linkertabel klein (maximaal 100.000 records) is en de juiste tabel zeer groot is.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-153">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="2d8ac-154">Met de onderstaande query probeert u bijvoorbeeld deel te nemen aan een paar e-mailberichten met specifieke onderwerpen met _alle_ berichten in de `EmailUrlInfo` tabel:</span><span class="sxs-lookup"><span data-stu-id="2d8ac-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="2d8ac-155">De `summarize` operator optimaliseren</span><span class="sxs-lookup"><span data-stu-id="2d8ac-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="2d8ac-156">Met de [operator samenvatten](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) wordt de inhoud van een tabel geaggregeerd.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-156">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="2d8ac-157">Deze tips toepassen om query's met deze operator te optimaliseren.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="2d8ac-158">**Distinct values zoeken**: in het algemeen `summarize` kunt u zoeken naar unieke waarden die herhaald kunnen zijn.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="2d8ac-159">Het is niet mogelijk om kolommen te gebruiken die geen herhalings waarden bevatten.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="2d8ac-160">Hoewel één e-mailbericht deel kan uitmaken van meerdere gebeurtenissen, vormt het voorbeeld hieronder _geen_ efficiënt gebruik `summarize` omdat een netwerkbericht-id voor een apart e-mailbericht altijd een uniek adres van de afzender bevat.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="2d8ac-161">U `summarize` kunt eenvoudig de operator vervangen door `project` de resultaten van het gebruik van minder bronnen te brengen:</span><span class="sxs-lookup"><span data-stu-id="2d8ac-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="2d8ac-162">Het volgende voorbeeld is een efficiëntere manier van `summarize` omdat er meerdere verschillende exemplaren van een afzender e-mailadres aan hetzelfde adres van de geadresseerde kunnen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="2d8ac-163">Deze combinaties zijn minder verschillend en zijn waarschijnlijk dubbele waarden.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="2d8ac-164">U kunt **de query in een willekeurige volgorde**plaatsen, terwijl u `summarize` het beste kunt gebruiken in kolommen met herhalende waarden, kan dezelfde kolom ook _hoge kardinaliteit_ of grote getallen met unieke waarden bevatten.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="2d8ac-165">Net als `join` bij de operator kunt u ook de [Hint van een willekeurige volgorde](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) toepassen `summarize` om de verwerkingsbelasting te verdelen en de prestaties te verbeteren wanneer u op kolommen met een hoge kardinaliteit werkt.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-165">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="2d8ac-166">Met de onderstaande query `summarize` kunt u het e-mailadres van een verschillend e-mailadres tellen, dat kan worden uitgevoerd in de honderden duizenden in grote organisaties.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="2d8ac-167">Ter verbetering van de prestaties `hint.shufflekey` :</span><span class="sxs-lookup"><span data-stu-id="2d8ac-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="2d8ac-168">Query scenario's</span><span class="sxs-lookup"><span data-stu-id="2d8ac-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="2d8ac-169">Unieke processen identificeren met proces-Id's</span><span class="sxs-lookup"><span data-stu-id="2d8ac-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="2d8ac-170">Proces-Id's in Windows worden gerecycled en opnieuw gebruikt voor nieuwe processen.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="2d8ac-171">Ze kunnen op hun eigen manier geen unieke id's voor specifieke processen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="2d8ac-172">Als u een unieke aanduiding wilt krijgen voor een proces op een specifieke computer, gebruikt u de proces-ID samen met de Aanmaaktijd van het proces.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="2d8ac-173">Wanneer u gegevens rond processen samenvoegt of samenvoegt, neemt u kolommen op voor de machine-id (of `DeviceId` `DeviceName` ), de proces-id ( `ProcessId` of `InitiatingProcessId` ) en de tijd waarop het proces is gemaakt ( `ProcessCreationTime` of `InitiatingProcessCreationTime` ).</span><span class="sxs-lookup"><span data-stu-id="2d8ac-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="2d8ac-174">Met de volgende voorbeeldquery vindt u processen die toegang hebben tot meer dan 10 IP-adressen via poort 445 (SMB), mogelijk met de scanfunctie voor bestandsshares.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="2d8ac-175">Voorbeeldquery:</span><span class="sxs-lookup"><span data-stu-id="2d8ac-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="2d8ac-176">De query geeft een samenvatting van beide `InitiatingProcessId` `InitiatingProcessCreationTime` processen weer, zodat de query één proces uitziet, zonder meerdere processen met hetzelfde proces-id te kunnen combineren.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="2d8ac-177">Opdrachtregels van query</span><span class="sxs-lookup"><span data-stu-id="2d8ac-177">Query command lines</span></span>
<span data-ttu-id="2d8ac-178">U kunt op verschillende manieren een opdrachtregel maken om een taak uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="2d8ac-179">Een aanvaller kan bijvoorbeeld verwijzen naar een afbeeldingsbestand zonder een pad zonder bestandsextensie, omgevingsvariabelen of met aanhalingstekens gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="2d8ac-180">De aanvaller kan ook de volgorde van parameters wijzigen of meerdere aanhalingstekens en spaties toevoegen.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="2d8ac-181">U kunt de volgende procedures toepassen als u meer duurzame query's wilt maken rond opdrachtregels:</span><span class="sxs-lookup"><span data-stu-id="2d8ac-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="2d8ac-182">Identificeer de bekende processen (zoals *net.exe* of *psexec.exe*) door te zoeken in de velden voor de bestandsnaam, in plaats van te filteren op de opdrachtregel zelf.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="2d8ac-183">Opdrachtregel secties parseren met behulp van de [functie parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="2d8ac-183">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="2d8ac-184">Wanneer u een query uitvoert voor opdrachtregelargumenten, zoekt u niet naar een exacte overeenkomst voor meerdere niet-gerelateerde argumenten in een bepaalde volgorde.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="2d8ac-185">Gebruik in plaats daarvan reguliere expressies of gebruik van meerdere aparte operatoren.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="2d8ac-186">Gebruik hoofdlettergevoelige overeenkomsten.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-186">Use case insensitive matches.</span></span> <span data-ttu-id="2d8ac-187">Gebruik bijvoorbeeld, `=~` `in~` en `contains` in plaats van `==` , `in` en `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="2d8ac-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="2d8ac-188">Als u de opdrachtregel wilt beperken, kunt u aanhalingstekens verwijderen, komma's vervangen door spaties en meerdere opeenvolgende spaties vervangen door één spatie.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="2d8ac-189">U kunt meer complexe methoden voor het maken van donkere en donkere kolommen waarvoor u andere benaderingen nodig hebt, maar deze kunnen door u gemeenschappelijke oplossingen worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="2d8ac-190">In de volgende voorbeelden ziet u verschillende manieren om een query te maken waarmee wordt gezocht naar het bestand dat *net.exe* de firewall service ' MpsSvc ' niet meer nodig hebt:</span><span class="sxs-lookup"><span data-stu-id="2d8ac-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="2d8ac-191">Ingestie gegevens uit externe bronnen</span><span class="sxs-lookup"><span data-stu-id="2d8ac-191">Ingest data from external sources</span></span>
<span data-ttu-id="2d8ac-192">Als u in uw query lange lijsten of grote tabellen wilt opnemen, gebruikt u de [externaldata-operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) om gegevens op te nemen uit een bepaalde URI.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-192">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="2d8ac-193">U kunt gegevens uit bestanden vinden in TXT-, CSV-, JSON-of [andere indelingen](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span><span class="sxs-lookup"><span data-stu-id="2d8ac-193">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="2d8ac-194">In het onderstaande voorbeeld ziet u hoe u de uitgebreide lijst met malware-256-hashwaarden van MalwareBazaar (abuse.ch) kunt gebruiken voor het controleren van bijlagen op e-mailberichten:</span><span class="sxs-lookup"><span data-stu-id="2d8ac-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

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

### <a name="parse-strings"></a><span data-ttu-id="2d8ac-195">Parserings tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="2d8ac-195">Parse strings</span></span>
<span data-ttu-id="2d8ac-196">Er zijn verschillende functies die u kunt gebruiken om de tekenreeksen die moeten worden geparseerd of geconverteerd, op efficiënte wijze af te handelen.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="2d8ac-197">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2d8ac-197">String</span></span> | <span data-ttu-id="2d8ac-198">Optie</span><span class="sxs-lookup"><span data-stu-id="2d8ac-198">Function</span></span> | <span data-ttu-id="2d8ac-199">Voorbeeld van gebruik</span><span class="sxs-lookup"><span data-stu-id="2d8ac-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="2d8ac-200">Opdrachtregel</span><span class="sxs-lookup"><span data-stu-id="2d8ac-200">Command-lines</span></span> | [<span data-ttu-id="2d8ac-201">parse_command_line ()</span><span class="sxs-lookup"><span data-stu-id="2d8ac-201">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="2d8ac-202">De opdracht en alle argumenten extraheren.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="2d8ac-203">Routes</span><span class="sxs-lookup"><span data-stu-id="2d8ac-203">Paths</span></span> | [<span data-ttu-id="2d8ac-204">parse_path ()</span><span class="sxs-lookup"><span data-stu-id="2d8ac-204">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="2d8ac-205">De secties van een pad naar een bestand of map extraheren.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="2d8ac-206">Versienummers</span><span class="sxs-lookup"><span data-stu-id="2d8ac-206">Version numbers</span></span> | [<span data-ttu-id="2d8ac-207">parse_version ()</span><span class="sxs-lookup"><span data-stu-id="2d8ac-207">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="2d8ac-208">Ontconstrueren van een versienummer met maximaal vier secties en maximaal acht tekens per sectie.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="2d8ac-209">Gebruik de geparseerde gegevens om de versie ouderdom te vergelijken.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="2d8ac-210">IPv4-adressen</span><span class="sxs-lookup"><span data-stu-id="2d8ac-210">IPv4 addresses</span></span> | [<span data-ttu-id="2d8ac-211">parse_ipv4 ()</span><span class="sxs-lookup"><span data-stu-id="2d8ac-211">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="2d8ac-212">Converteer een IPv4-adres naar een lang geheel getal.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="2d8ac-213">Als u IPv4-adressen wilt vergelijken zonder ze te converteren, gebruikt u [ipv4_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="2d8ac-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="2d8ac-214">IPv6-adressen</span><span class="sxs-lookup"><span data-stu-id="2d8ac-214">IPv6 addresses</span></span> | [<span data-ttu-id="2d8ac-215">parse_ipv6 ()</span><span class="sxs-lookup"><span data-stu-id="2d8ac-215">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="2d8ac-216">Converteer een IPv4-of IPv6-adres naar de canonieke IPv6-notatie.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="2d8ac-217">Gebruik [ipv6_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)om IPv6-adressen te vergelijken.</span><span class="sxs-lookup"><span data-stu-id="2d8ac-217">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="2d8ac-218">Meer informatie over alle ondersteunde functies voor het parseren van functies vindt u in [Kusto tekenreeksfuncties](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span><span class="sxs-lookup"><span data-stu-id="2d8ac-218">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="2d8ac-219">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2d8ac-219">Related topics</span></span>
- [<span data-ttu-id="2d8ac-220">Kusto querytaal documentatie</span><span class="sxs-lookup"><span data-stu-id="2d8ac-220">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="2d8ac-221">Servicelimieten</span><span class="sxs-lookup"><span data-stu-id="2d8ac-221">Service limits</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="2d8ac-222">Geavanceerde jacht-fouten verwerken</span><span class="sxs-lookup"><span data-stu-id="2d8ac-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="2d8ac-223">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="2d8ac-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2d8ac-224">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="2d8ac-224">Learn the query language</span></span>](advanced-hunting-query-language.md)
