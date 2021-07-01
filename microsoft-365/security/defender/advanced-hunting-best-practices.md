---
title: Geavanceerde best practices voor query's in Microsoft 365 Defender
description: Meer informatie over het maken van snelle, efficiënte en foutloze zoekquery's voor bedreigingen met geavanceerde jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema, kusto, avoid timeout, command lines, process id, optimize, best practice, parse, join, summarize
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae2e7fb960dd8ce2a42ce62fe0b8da7675e00ce5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228373"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="3d027-104">Geavanceerde best practices voor query's</span><span class="sxs-lookup"><span data-stu-id="3d027-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3d027-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3d027-105">**Applies to:**</span></span>
- <span data-ttu-id="3d027-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3d027-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3d027-107">Pas deze aanbevelingen toe om sneller resultaten te krijgen en time-outs te vermijden tijdens het uitvoeren van complexe query's.</span><span class="sxs-lookup"><span data-stu-id="3d027-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="3d027-108">Lees [Kusto query best practices](/azure/kusto/query/best-practices)voor meer informatie over het verbeteren van queryprestaties.</span><span class="sxs-lookup"><span data-stu-id="3d027-108">For more guidance on improving query performance, read [Kusto query best practices](/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-quotas"></a><span data-ttu-id="3d027-109">Informatie over CPU-resourcequota's</span><span class="sxs-lookup"><span data-stu-id="3d027-109">Understand CPU resource quotas</span></span>
<span data-ttu-id="3d027-110">Afhankelijk van de grootte heeft elke tenant toegang tot een bepaalde hoeveelheid CPU-resources die is toegewezen voor het uitvoeren van geavanceerde query's.</span><span class="sxs-lookup"><span data-stu-id="3d027-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="3d027-111">Meer informatie over verschillende servicelimieten vindt [u in geavanceerde jachtquota's en gebruiksparameters.](advanced-hunting-limits.md)</span><span class="sxs-lookup"><span data-stu-id="3d027-111">For detailed information about various service limits, [read about advanced hunting quotas and usage parameters](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="3d027-112">Klanten die regelmatig meerdere query's uitvoeren, moeten het verbruik bijhouden en de optimalisatie-richtlijnen in dit artikel toepassen om verstoringen als gevolg van het overschrijden van quota of gebruiksparameters tot een minimum te beperken.</span><span class="sxs-lookup"><span data-stu-id="3d027-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding quotas or usage parameters.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="3d027-113">Tips voor algemene optimalisatie</span><span class="sxs-lookup"><span data-stu-id="3d027-113">General optimization tips</span></span>

- <span data-ttu-id="3d027-114">**Grootte van nieuwe query's:** als u vermoedt dat een query een grote resultatenset retourneert, beoordeelt u deze eerst met de [operator aantal.](/azure/data-explorer/kusto/query/countoperator)</span><span class="sxs-lookup"><span data-stu-id="3d027-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="3d027-115">Gebruik [limiet](/azure/data-explorer/kusto/query/limitoperator) of het synoniem om `take` grote resultatensets te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="3d027-115">Use [limit](/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="3d027-116">Filters vroeg toepassen **:** pas tijdfilters en andere filters toe om de gegevensset te verminderen, met name voordat u transformatie- en parsingsfuncties gebruikt, zoals [subteken()](/azure/data-explorer/kusto/query/substringfunction), [vervangen()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction) [of parse_json().](/azure/data-explorer/kusto/query/parsejsonfunction)</span><span class="sxs-lookup"><span data-stu-id="3d027-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="3d027-117">In het onderstaande voorbeeld wordt de parsingsfunctie [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) gebruikt nadat filteroperatoren het aantal records hebben verminderd.</span><span class="sxs-lookup"><span data-stu-id="3d027-117">In the example below, the parsing function [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount"
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="3d027-118">**Bevat verslaat**-Als u wilt voorkomen dat u onnodig subtekens in woorden zoekt, gebruikt u de `has` operator in plaats van `contains` .</span><span class="sxs-lookup"><span data-stu-id="3d027-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="3d027-119">Meer informatie over tekenreeksoperatoren</span><span class="sxs-lookup"><span data-stu-id="3d027-119">Learn about string operators</span></span>](/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="3d027-120">**Zoeken in specifieke kolommen:** kijk in een specifieke kolom in plaats van volledige tekst te zoeken in alle kolommen.</span><span class="sxs-lookup"><span data-stu-id="3d027-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="3d027-121">Gebruik niet om `*` alle kolommen te controleren.</span><span class="sxs-lookup"><span data-stu-id="3d027-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="3d027-122">**Case-sensitive for speed**:Case-sensitive searches are more specific and generally more performant.</span><span class="sxs-lookup"><span data-stu-id="3d027-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="3d027-123">Namen van case-sensitive [tekenreeksoperatoren,](/azure/data-explorer/kusto/query/datatypes-string-operators)zoals `has_cs` en , eindigen meestal op `contains_cs` `_cs` .</span><span class="sxs-lookup"><span data-stu-id="3d027-123">Names of case-sensitive [string operators](/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="3d027-124">U kunt ook de operator case-sensitive equals `==` gebruiken in plaats van `=~` .</span><span class="sxs-lookup"><span data-stu-id="3d027-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="3d027-125">**Parseren, niet extraheren**: gebruik indien mogelijk de [parse-operator](/azure/data-explorer/kusto/query/parseoperator) of een parsingsfunctie zoals [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="3d027-125">**Parse, don't extract**—Whenever possible, use the [parse operator](/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="3d027-126">Vermijd de `matches regex` tekenreeksoperator of [de functie extract(),](/azure/data-explorer/kusto/query/extractfunction)die beide een normale expressie gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3d027-126">Avoid the `matches regex` string operator or the [extract() function](/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="3d027-127">Reserveer het gebruik van reguliere expressie voor complexere scenario's.</span><span class="sxs-lookup"><span data-stu-id="3d027-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="3d027-128">Meer informatie over parsingsfuncties</span><span class="sxs-lookup"><span data-stu-id="3d027-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="3d027-129">**Tabellen filteren zonder expressies:** filter niet op een berekende kolom als u kunt filteren op een tabelkolom.</span><span class="sxs-lookup"><span data-stu-id="3d027-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="3d027-130">**Geen termen met drie tekens:** vermijd het vergelijken of filteren met termen met drie tekens of minder.</span><span class="sxs-lookup"><span data-stu-id="3d027-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="3d027-131">Deze termen worden niet geïndexeerd en er zijn meer resources voor nodig.</span><span class="sxs-lookup"><span data-stu-id="3d027-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="3d027-132">**Project selectief:** maak uw resultaten begrijpelijker door alleen de kolommen te projecteren die u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="3d027-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="3d027-133">Als u specifieke kolommen projecteert vóór het uitvoeren van [join-](/azure/data-explorer/kusto/query/joinoperator) of soortgelijke bewerkingen, worden de prestaties ook verbeterd.</span><span class="sxs-lookup"><span data-stu-id="3d027-133">Projecting specific columns prior to running [join](/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="3d027-134">De `join` operator optimaliseren</span><span class="sxs-lookup"><span data-stu-id="3d027-134">Optimize the `join` operator</span></span>
<span data-ttu-id="3d027-135">De [joinoperator](/azure/data-explorer/kusto/query/joinoperator) voegt rijen uit twee tabellen samen door waarden in opgegeven kolommen te koppelen.</span><span class="sxs-lookup"><span data-stu-id="3d027-135">The [join operator](/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="3d027-136">Pas deze tips toe om query's te optimaliseren die deze operator gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3d027-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="3d027-137">**Kleinere tabel aan de linkerkant:** de operator komt overeen met records in de tabel aan de linkerkant van de `join` join-instructie voor records aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="3d027-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="3d027-138">Door de kleinere tabel aan de linkerkant te hebben, hoeven er minder records te worden gematcht, waardoor de query sneller wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="3d027-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span>

    <span data-ttu-id="3d027-139">In de onderstaande tabel beperken we de linkertabel tot slechts drie specifieke apparaten voordat we er met `DeviceLogonEvents` `IdentityLogonEvents` account-SID's aan deelnemen.</span><span class="sxs-lookup"><span data-stu-id="3d027-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>

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

- <span data-ttu-id="3d027-140">**Gebruik de inner-join-smaak**: de standaard join-smaak of de [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rijen in de linkertabel door de join-toets voordat u een rij voor elke overeenkomst terugstuurt naar de rechtertabel. [](/azure/data-explorer/kusto/query/joinoperator#join-flavors)</span><span class="sxs-lookup"><span data-stu-id="3d027-140">**Use the inner-join flavor**—The default [join flavor](/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="3d027-141">Als de linkertabel meerdere rijen heeft met dezelfde waarde voor de sleutel, worden deze rijen gededuplicaeerd om één willekeurige rij achter te laten `join` voor elke unieke waarde.</span><span class="sxs-lookup"><span data-stu-id="3d027-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="3d027-142">Dit standaardgedrag kan belangrijke informatie weg laten uit de linkertabel die nuttig inzicht kan bieden.</span><span class="sxs-lookup"><span data-stu-id="3d027-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="3d027-143">In de onderstaande query wordt bijvoorbeeld slechts één e-mailbericht met een bepaalde bijlage weergegeven, zelfs als dezelfde bijlage is verzonden met meerdere e-mailberichten:</span><span class="sxs-lookup"><span data-stu-id="3d027-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

    <span data-ttu-id="3d027-144">Om deze beperking aan te pakken, passen we de [inner-join-smaak](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) toe door op te geven om alle rijen in de linkertabel weer te geven met overeenkomende `kind=inner` waarden aan de rechterkant:</span><span class="sxs-lookup"><span data-stu-id="3d027-144">To address this limitation, we apply the [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```
- <span data-ttu-id="3d027-145">**Deelnemen aan records vanuit een tijdvenster:** bij het onderzoeken van beveiligingsgebeurtenissen zoeken analisten naar gerelateerde gebeurtenissen die zich rond dezelfde periode voordoen.</span><span class="sxs-lookup"><span data-stu-id="3d027-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="3d027-146">Door dezelfde benadering toe te passen bij het gebruik van ook de prestaties, vermindert u het `join` aantal records dat u moet controleren.</span><span class="sxs-lookup"><span data-stu-id="3d027-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>

    <span data-ttu-id="3d027-147">In de onderstaande query wordt gecontroleerd op aanmeldingsgebeurtenissen binnen 30 minuten na ontvangst van een schadelijk bestand:</span><span class="sxs-lookup"><span data-stu-id="3d027-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

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
- <span data-ttu-id="3d027-148">**Tijdfilters** aan beide zijden toepassen: zelfs als u geen specifiek tijdvenster onderzoekt, kan het toepassen van tijdfilters op zowel de linker- als rechtertabellen het aantal records verminderen om de prestaties te controleren en te `join` verbeteren.</span><span class="sxs-lookup"><span data-stu-id="3d027-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="3d027-149">De onderstaande query is van toepassing op beide tabellen, zodat alleen records uit het afgelopen uur `Timestamp > ago(1h)` worden joins:</span><span class="sxs-lookup"><span data-stu-id="3d027-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256
    ```

- <span data-ttu-id="3d027-150">**Gebruik hints voor prestaties:** gebruik hints met de operator om de backend te instrueren om de belasting te verdelen tijdens het uitvoeren van `join` resourceintensieve bewerkingen.</span><span class="sxs-lookup"><span data-stu-id="3d027-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="3d027-151">Meer informatie over tips voor deelnemen</span><span class="sxs-lookup"><span data-stu-id="3d027-151">Learn more about join hints</span></span>](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="3d027-152">Met de **[hint](/azure/data-explorer/kusto/query/shufflequery)** voor shuffle kunt u bijvoorbeeld de prestaties van query's verbeteren wanneer u aan tabellen deelt met behulp van een toets met een hoge kardinaliteit, een sleutel met veel unieke waarden, zoals `AccountObjectId` de in de onderstaande query:</span><span class="sxs-lookup"><span data-stu-id="3d027-152">For example, the **[shuffle hint](/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId
    ```

    <span data-ttu-id="3d027-153">De **[hint voor uitzending](/azure/data-explorer/kusto/query/broadcastjoin)** helpt wanneer de linkertabel klein is (maximaal 100.000 records) en de rechtertabel zeer groot is.</span><span class="sxs-lookup"><span data-stu-id="3d027-153">The **[broadcast hint](/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="3d027-154">In de onderstaande query wordt bijvoorbeeld geprobeerd deel te  nemen aan een paar e-mailberichten met specifieke onderwerpen met alle berichten met koppelingen in de `EmailUrlInfo` tabel:</span><span class="sxs-lookup"><span data-stu-id="3d027-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="3d027-155">De `summarize` operator optimaliseren</span><span class="sxs-lookup"><span data-stu-id="3d027-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="3d027-156">De [samenvattende operator](/azure/data-explorer/kusto/query/summarizeoperator) aggregeert de inhoud van een tabel.</span><span class="sxs-lookup"><span data-stu-id="3d027-156">The [summarize operator](/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="3d027-157">Pas deze tips toe om query's te optimaliseren die deze operator gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3d027-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="3d027-158">**Afzonderlijke waarden zoeken:** in het algemeen kunt u verschillende waarden `summarize` zoeken die herhalend kunnen zijn.</span><span class="sxs-lookup"><span data-stu-id="3d027-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="3d027-159">Het kan onnodig zijn om het te gebruiken om kolommen te aggregeren die geen terugkerende waarden hebben.</span><span class="sxs-lookup"><span data-stu-id="3d027-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="3d027-160">Hoewel één e-mailbericht deel kan uitmaken van meerdere gebeurtenissen, _is_ het onderstaande voorbeeld niet efficiënt omdat een netwerkbericht-id voor een afzonderlijke e-mail altijd wordt geleverd met een uniek `summarize` afzenderadres.</span><span class="sxs-lookup"><span data-stu-id="3d027-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress
    ```
    <span data-ttu-id="3d027-161">De operator kan eenvoudig worden vervangen door , wat mogelijk dezelfde resultaten oplevert en minder `summarize` `project` resources verbruikt:</span><span class="sxs-lookup"><span data-stu-id="3d027-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress
    ```
    <span data-ttu-id="3d027-162">Het volgende voorbeeld is een efficiënter gebruik van omdat er meerdere afzonderlijke exemplaren kunnen zijn van een afzenderadres dat e-mail naar hetzelfde adres `summarize` van de geadresseerde verstuurt.</span><span class="sxs-lookup"><span data-stu-id="3d027-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="3d027-163">Dergelijke combinaties zijn minder verschillend en hebben waarschijnlijk dubbele waarden.</span><span class="sxs-lookup"><span data-stu-id="3d027-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress
    ```

- <span data-ttu-id="3d027-164">**Schuif de query door** elkaar: hoewel deze het beste wordt gebruikt in kolommen met terugkerende waarden, kunnen dezelfde kolommen ook een hoge kardinaliteit of grote `summarize` aantallen unieke waarden  hebben.</span><span class="sxs-lookup"><span data-stu-id="3d027-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="3d027-165">Net als de operator kunt u ook de schuifelhint toepassen om de verwerkingsbelasting te verdelen en de prestaties mogelijk te verbeteren wanneer u werkt op `join` kolommen met een hoge [](/azure/data-explorer/kusto/query/shufflequery) `summarize` kardinaliteit.</span><span class="sxs-lookup"><span data-stu-id="3d027-165">Like the `join` operator, you can also apply the [shuffle hint](/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="3d027-166">In de onderstaande query wordt het afzonderlijke e-mailadres van de geadresseerde geteld, dat kan worden uitgevoerd in de `summarize` honderdduizenden in grote organisaties.</span><span class="sxs-lookup"><span data-stu-id="3d027-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="3d027-167">Om de prestaties te verbeteren, bevat het `hint.shufflekey` de volgende elementen:</span><span class="sxs-lookup"><span data-stu-id="3d027-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="3d027-168">Queryscenario's</span><span class="sxs-lookup"><span data-stu-id="3d027-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="3d027-169">Unieke processen identificeren met proces-eds</span><span class="sxs-lookup"><span data-stu-id="3d027-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="3d027-170">Proces-ID's (PID's) worden in de Windows hergebruikt voor nieuwe processen.</span><span class="sxs-lookup"><span data-stu-id="3d027-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="3d027-171">Op zichzelf kunnen ze niet fungeren als unieke id's voor specifieke processen.</span><span class="sxs-lookup"><span data-stu-id="3d027-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="3d027-172">Als u een unieke id wilt krijgen voor een proces op een specifieke computer, gebruikt u de proces-id samen met de tijd voor het maken van het proces.</span><span class="sxs-lookup"><span data-stu-id="3d027-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="3d027-173">Wanneer u gegevens rond processen bij elkaar voegt of samenvatten, kunt u kolommen opnemen voor de machine-id (of), de proces-id (of), en de tijd voor het maken `DeviceId` `DeviceName` van het proces `ProcessId` `InitiatingProcessId` `ProcessCreationTime` (of `InitiatingProcessCreationTime` )</span><span class="sxs-lookup"><span data-stu-id="3d027-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="3d027-174">In de volgende voorbeeldquery worden processen gevonden die toegang hebben tot meer dan 10 IP-adressen via poort 445 (SMB), mogelijk scannen op bestandsaandelen.</span><span class="sxs-lookup"><span data-stu-id="3d027-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="3d027-175">Voorbeeldquery:</span><span class="sxs-lookup"><span data-stu-id="3d027-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="3d027-176">De query wordt op beide manieren samengevat, zodat er naar één proces wordt ge kijkt, zonder dat meerdere processen met dezelfde `InitiatingProcessId` `InitiatingProcessCreationTime` proces-id worden vermengd.</span><span class="sxs-lookup"><span data-stu-id="3d027-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="3d027-177">Opdrachtregels voor query's</span><span class="sxs-lookup"><span data-stu-id="3d027-177">Query command lines</span></span>
<span data-ttu-id="3d027-178">Er zijn verschillende manieren om een opdrachtregel te maken om een taak uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="3d027-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="3d027-179">Een aanvaller kan bijvoorbeeld verwijzen naar een afbeeldingsbestand zonder pad, zonder bestandsextensie, met omgevingsvariabelen of met aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="3d027-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="3d027-180">De aanvaller kan ook de volgorde van parameters wijzigen of meerdere aanhalingstekens en spaties toevoegen.</span><span class="sxs-lookup"><span data-stu-id="3d027-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="3d027-181">Als u duurzamere query's wilt maken rond opdrachtlijnen, moet u de volgende procedures toepassen:</span><span class="sxs-lookup"><span data-stu-id="3d027-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="3d027-182">Identificeer de bekende processen (zoalsnet.exe *of* *psexec.exe)* door op de bestandsnaamvelden te matchen in plaats van te filteren op de opdrachtregel zelf.</span><span class="sxs-lookup"><span data-stu-id="3d027-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="3d027-183">Opdrachtregelsecties parseren met de [functie parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="3d027-183">Parse command-line sections using the [parse_command_line() function](/azure/data-explorer/kusto/query/parse-command-line)</span></span>
- <span data-ttu-id="3d027-184">Wanneer u query's uitvoert voor opdrachtregelargumenten, moet u niet zoeken naar een exacte overeenkomst voor meerdere niet-gerelateerde argumenten in een bepaalde volgorde.</span><span class="sxs-lookup"><span data-stu-id="3d027-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="3d027-185">Gebruik in plaats daarvan gewone expressies of gebruik meerdere afzonderlijke operatoren.</span><span class="sxs-lookup"><span data-stu-id="3d027-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="3d027-186">Gebruik case insensitive matches.</span><span class="sxs-lookup"><span data-stu-id="3d027-186">Use case insensitive matches.</span></span> <span data-ttu-id="3d027-187">Gebruik bijvoorbeeld `=~` , `in~` en in plaats van , en `contains` `==` `in` `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="3d027-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="3d027-188">Als u obfuscationtechnieken voor opdrachtregelen wilt beperken, kunt u aanhalingstekens verwijderen, komma's vervangen door spaties en meerdere opeenvolgende spaties vervangen door één spatie.</span><span class="sxs-lookup"><span data-stu-id="3d027-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="3d027-189">Er zijn complexere obfuscation-technieken waarvoor andere methoden nodig zijn, maar deze aanpassingen kunnen helpen bij het aanpakken van veelvoorkomende technieken.</span><span class="sxs-lookup"><span data-stu-id="3d027-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="3d027-190">In de volgende voorbeelden ziet u verschillende manieren  om een query te maken die zoekt naar het bestandnet.exeom de firewallservice "MpsSvc" te stoppen:</span><span class="sxs-lookup"><span data-stu-id="3d027-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="3d027-191">Gegevens uit externe bronnen opnemen</span><span class="sxs-lookup"><span data-stu-id="3d027-191">Ingest data from external sources</span></span>
<span data-ttu-id="3d027-192">Als u lange lijsten of grote tabellen wilt opnemen in uw query, gebruikt u de [operator externaldata om](/azure/data-explorer/kusto/query/externaldata-operator) gegevens uit een opgegeven URI op te nemen.</span><span class="sxs-lookup"><span data-stu-id="3d027-192">To incorporate long lists or large tables into your query, use the [externaldata operator](/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="3d027-193">U kunt gegevens opmaken uit bestanden in TXT, CSV, JSON [of andere indelingen.](/azure/data-explorer/ingestion-supported-formats)</span><span class="sxs-lookup"><span data-stu-id="3d027-193">You can get data from files in TXT, CSV, JSON, or [other formats](/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="3d027-194">In het onderstaande voorbeeld ziet u hoe u de uitgebreide lijst met malware SHA-256-hashes van MalwareBazaar (abuse.ch) kunt gebruiken om bijlagen in e-mailberichten te controleren:</span><span class="sxs-lookup"><span data-stu-id="3d027-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string)
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

### <a name="parse-strings"></a><span data-ttu-id="3d027-195">Tekenreeksen parseren</span><span class="sxs-lookup"><span data-stu-id="3d027-195">Parse strings</span></span>
<span data-ttu-id="3d027-196">Er zijn verschillende functies die u kunt gebruiken om efficiënt om te gaan met tekenreeksen die parsing of conversie nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="3d027-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span>

| <span data-ttu-id="3d027-197">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3d027-197">String</span></span> | <span data-ttu-id="3d027-198">Functie</span><span class="sxs-lookup"><span data-stu-id="3d027-198">Function</span></span> | <span data-ttu-id="3d027-199">Gebruiksvoorbeeld</span><span class="sxs-lookup"><span data-stu-id="3d027-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="3d027-200">Opdrachtlijnen</span><span class="sxs-lookup"><span data-stu-id="3d027-200">Command-lines</span></span> | [<span data-ttu-id="3d027-201">parse_command_line()</span><span class="sxs-lookup"><span data-stu-id="3d027-201">parse_command_line()</span></span>](/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="3d027-202">Haal de opdracht en alle argumenten op.</span><span class="sxs-lookup"><span data-stu-id="3d027-202">Extract the command and all arguments.</span></span> |
| <span data-ttu-id="3d027-203">Paden</span><span class="sxs-lookup"><span data-stu-id="3d027-203">Paths</span></span> | [<span data-ttu-id="3d027-204">parse_path()</span><span class="sxs-lookup"><span data-stu-id="3d027-204">parse_path()</span></span>](/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="3d027-205">Haal de secties van een bestands- of mappad op.</span><span class="sxs-lookup"><span data-stu-id="3d027-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="3d027-206">Versienummers</span><span class="sxs-lookup"><span data-stu-id="3d027-206">Version numbers</span></span> | [<span data-ttu-id="3d027-207">parse_version()</span><span class="sxs-lookup"><span data-stu-id="3d027-207">parse_version()</span></span>](/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="3d027-208">Deconstructie van een versienummer met maximaal vier secties en maximaal acht tekens per sectie.</span><span class="sxs-lookup"><span data-stu-id="3d027-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="3d027-209">Gebruik de geparseerde gegevens om versieleeftijd te vergelijken.</span><span class="sxs-lookup"><span data-stu-id="3d027-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="3d027-210">IPv4-adressen</span><span class="sxs-lookup"><span data-stu-id="3d027-210">IPv4 addresses</span></span> | [<span data-ttu-id="3d027-211">parse_ipv4()</span><span class="sxs-lookup"><span data-stu-id="3d027-211">parse_ipv4()</span></span>](/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="3d027-212">Een IPv4-adres converteren naar een lang geheel getal.</span><span class="sxs-lookup"><span data-stu-id="3d027-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="3d027-213">Als u IPv4-adressen wilt vergelijken zonder deze te converteren, gebruikt [u ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="3d027-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="3d027-214">IPv6-adressen</span><span class="sxs-lookup"><span data-stu-id="3d027-214">IPv6 addresses</span></span> | [<span data-ttu-id="3d027-215">parse_ipv6()</span><span class="sxs-lookup"><span data-stu-id="3d027-215">parse_ipv6()</span></span>](/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="3d027-216">Converteert een IPv4- of IPv6-adres naar de canonieke IPv6-notatie.</span><span class="sxs-lookup"><span data-stu-id="3d027-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="3d027-217">Als u IPv6-adressen wilt vergelijken, gebruikt [u ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="3d027-217">To compare IPv6 addresses, use [ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="3d027-218">Als u meer wilt weten over alle ondersteunde parsingsfuncties, [leest u meer over kusto-tekenreeksfuncties.](/azure/data-explorer/kusto/query/scalarfunctions#string-functions)</span><span class="sxs-lookup"><span data-stu-id="3d027-218">To learn about all supported parsing functions, [read about Kusto string functions](/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span>

>[!NOTE]
><span data-ttu-id="3d027-219">Sommige tabellen in dit artikel zijn mogelijk niet beschikbaar in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="3d027-219">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3d027-220">[Schakel de Microsoft 365 Defender](m365d-enable.md) in om te zoeken naar bedreigingen met behulp van meer gegevensbronnen.</span><span class="sxs-lookup"><span data-stu-id="3d027-220">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="3d027-221">U kunt uw geavanceerde werkstromen voor jagen verplaatsen van Microsoft Defender voor Eindpunt naar Microsoft 365 Defender door de stappen in Geavanceerde zoekquery's migreren uit [Microsoft Defender voor Eindpunt te volgen.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="3d027-221">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3d027-222">Gerelateerde onderwerpen</span><span class="sxs-lookup"><span data-stu-id="3d027-222">Related topics</span></span>
- [<span data-ttu-id="3d027-223">Documentatie van kustoquerytaal</span><span class="sxs-lookup"><span data-stu-id="3d027-223">Kusto query language documentation</span></span>](/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="3d027-224">Quota en gebruiksparameters</span><span class="sxs-lookup"><span data-stu-id="3d027-224">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="3d027-225">Geavanceerde zoekfouten verwerken</span><span class="sxs-lookup"><span data-stu-id="3d027-225">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="3d027-226">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="3d027-226">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3d027-227">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="3d027-227">Learn the query language</span></span>](advanced-hunting-query-language.md)