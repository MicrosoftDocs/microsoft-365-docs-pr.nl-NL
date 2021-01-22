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
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="e6126-104">Geavanceerde best practices voor zoekquery's</span><span class="sxs-lookup"><span data-stu-id="e6126-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e6126-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e6126-105">**Applies to:**</span></span>
- <span data-ttu-id="e6126-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6126-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e6126-107">Pas deze aanbevelingen toe om sneller resultaten te krijgen en time-outs te vermijden bij het uitvoeren van complexe query's.</span><span class="sxs-lookup"><span data-stu-id="e6126-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="e6126-108">Lees de best practices voor [kusto-query's](https://docs.microsoft.com/azure/kusto/query/best-practices)voor meer informatie over het verbeteren van de queryprestaties.</span><span class="sxs-lookup"><span data-stu-id="e6126-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-quotas"></a><span data-ttu-id="e6126-109">Informatie over quota voor CPU-bronnen</span><span class="sxs-lookup"><span data-stu-id="e6126-109">Understand CPU resource quotas</span></span>
<span data-ttu-id="e6126-110">Afhankelijk van de grootte heeft elke tenant toegang tot een bepaalde hoeveelheid CPU-bronnen die zijn toegewezen voor het uitvoeren van geavanceerde zoekquery's.</span><span class="sxs-lookup"><span data-stu-id="e6126-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="e6126-111">Lees meer over geavanceerde zoekquota's [en gebruiksparameters voor meer informatie](advanced-hunting-limits.md)over verschillende servicelimieten.</span><span class="sxs-lookup"><span data-stu-id="e6126-111">For detailed information about various service limits, [read about advanced hunting quotas and usage parameters](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="e6126-112">Klanten die regelmatig meerdere query's uitvoeren, moeten het gebruik bijhouden en de optimalisatie-richtlijnen in dit artikel toepassen om verstoringen die het gevolg zijn van overschrijding van quota of gebruiksparameters tot een minimum te beperken.</span><span class="sxs-lookup"><span data-stu-id="e6126-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding quotas or usage parameters.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="e6126-113">Algemene tips voor optimalisatie</span><span class="sxs-lookup"><span data-stu-id="e6126-113">General optimization tips</span></span>

- <span data-ttu-id="e6126-114">**Grootte van nieuwe query's:** als u vermoedt dat een query een grote resultatenset retourneert, moet u deze eerst beoordelen met behulp van de [operator Count.](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator)</span><span class="sxs-lookup"><span data-stu-id="e6126-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="e6126-115">Gebruik [de limiet](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) of het synoniem ervan om grote `take` resultatensets te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="e6126-115">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="e6126-116">Pas **filters** vroeg toe: pas tijdfilters en andere filters toe om de gegevensset te beperken, met name voordat u transformatie- en parseerfuncties gebruikt, zoals [subtekenreeks()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)of [parse_json().](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)</span><span class="sxs-lookup"><span data-stu-id="e6126-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="e6126-117">In het onderstaande voorbeeld wordt de parsingsfunctie [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) gebruikt nadat de filteroperatoren het aantal records hebben beperkt.</span><span class="sxs-lookup"><span data-stu-id="e6126-117">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="e6126-118">**Bevat bevat het aantal** herhalingen. Gebruik de operator in plaats van de operator in plaats van de woorden om te voorkomen dat u onnodig naar subtekenreeksen in `has` woorden `contains` zoekt.</span><span class="sxs-lookup"><span data-stu-id="e6126-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="e6126-119">Meer informatie over tekenreeksoperatoren</span><span class="sxs-lookup"><span data-stu-id="e6126-119">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="e6126-120">**Kijk in specifieke kolommen:** kijk in een specifieke kolom in plaats van volledige tekst te zoeken in alle kolommen.</span><span class="sxs-lookup"><span data-stu-id="e6126-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="e6126-121">Gebruik niet om `*` alle kolommen te controleren.</span><span class="sxs-lookup"><span data-stu-id="e6126-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="e6126-122">**Case-sensitive for speed—** Case-sensitive searches are more specific and generally more performant.</span><span class="sxs-lookup"><span data-stu-id="e6126-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="e6126-123">Namen van casegevoelige [tekenreeksoperatoren,](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)zoals `has_cs` `contains_cs` en, die over het algemeen eindigen op `_cs` .</span><span class="sxs-lookup"><span data-stu-id="e6126-123">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="e6126-124">U kunt ook de operator voor issys-gevoelige is gelijk aan gebruiken `==` in plaats van `=~` .</span><span class="sxs-lookup"><span data-stu-id="e6126-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="e6126-125">**Parseren, niet extraheren**— gebruik waar mogelijk de [parseroperator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) of een parserende functie zoals [parse_json().](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction)</span><span class="sxs-lookup"><span data-stu-id="e6126-125">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="e6126-126">Vermijd de `matches regex` tekenreeksoperator of [de extractiefunctie(),](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)die beide een reguliere expressie gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e6126-126">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="e6126-127">Reserveer het gebruik van reguliere expressies voor complexere scenario's.</span><span class="sxs-lookup"><span data-stu-id="e6126-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="e6126-128">Meer informatie over parseringsfuncties</span><span class="sxs-lookup"><span data-stu-id="e6126-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="e6126-129">**Filter tabellen niet op expressies.** Filter niet op een berekende kolom als u op een tabelkolom kunt filteren.</span><span class="sxs-lookup"><span data-stu-id="e6126-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="e6126-130">**Geen termen met drie tekens.** Vermijd het vergelijken of filteren van termen met drie tekens of minder.</span><span class="sxs-lookup"><span data-stu-id="e6126-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="e6126-131">Deze voorwaarden worden niet geïndexeerd en voor een aanpassing aan deze voorwaarden zijn meer resources nodig.</span><span class="sxs-lookup"><span data-stu-id="e6126-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="e6126-132">**Projecteren selectief**: maak uw resultaten begrijpelijker door alleen de kolommen te projecteren die u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="e6126-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="e6126-133">Door specifieke kolommen te projecteren vóór het uitvoeren [van joins](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) of vergelijkbare bewerkingen, worden ook de prestaties verbeterd.</span><span class="sxs-lookup"><span data-stu-id="e6126-133">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="e6126-134">De `join` operator optimaliseren</span><span class="sxs-lookup"><span data-stu-id="e6126-134">Optimize the `join` operator</span></span>
<span data-ttu-id="e6126-135">De [join-operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) voegt rijen uit twee tabellen samen door overeenkomende waarden in opgegeven kolommen.</span><span class="sxs-lookup"><span data-stu-id="e6126-135">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="e6126-136">Pas deze tips toe om query's te optimaliseren die deze operator gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e6126-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="e6126-137">**Kleinere tabel aan de linkerkant:** de operator matcht records in de tabel aan de linkerkant van uw join-instructie met `join` records aan de rechterkant.</span><span class="sxs-lookup"><span data-stu-id="e6126-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="e6126-138">Als u de kleinere tabel aan de linkerkant hebt, hoeven er minder records aan te worden gematcht, waardoor de query sneller wordt.</span><span class="sxs-lookup"><span data-stu-id="e6126-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="e6126-139">In de onderstaande tabel wordt de linkertabel verkleind tot slechts drie specifieke apparaten voordat we deze via `DeviceLogonEvents` `IdentityLogonEvents` account-SID's gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e6126-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
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

- <span data-ttu-id="e6126-140">Gebruik de **inner-join-smaak**: de standaard join-smaak of de [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rijen in de linkertabel door de join-toets voordat u een rij voor elke overeenkomst in de rechtertabel retourneert.</span><span class="sxs-lookup"><span data-stu-id="e6126-140">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="e6126-141">Als de linkertabel meerdere rijen heeft met dezelfde waarde voor de sleutel, worden deze rijen gededuplicaeerd om één willekeurige rij achter te laten `join` voor elke unieke waarde.</span><span class="sxs-lookup"><span data-stu-id="e6126-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="e6126-142">Bij dit standaardgedrag kan belangrijke informatie uit de linkertabel weggelaten worden die een nuttig inzicht kan geven.</span><span class="sxs-lookup"><span data-stu-id="e6126-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="e6126-143">In de onderstaande query wordt bijvoorbeeld slechts één e-mailbericht met een bepaalde bijlage weergegeven, zelfs als dezelfde bijlage is verzonden via meerdere e-mailberichten:</span><span class="sxs-lookup"><span data-stu-id="e6126-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="e6126-144">Om deze beperking aan te pakken, passen we de [inner-join-smaak](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) toe door op te geven dat alle rijen in de linkertabel moeten worden weergeven met overeenkomende `kind=inner` waarden in de rechtertabel:</span><span class="sxs-lookup"><span data-stu-id="e6126-144">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="e6126-145">**Neem deel aan records vanuit een tijdvenster.** Bij het onderzoeken van beveiligingsgebeurtenissen zoeken analisten naar gerelateerde gebeurtenissen die zich rond dezelfde periode voordoen.</span><span class="sxs-lookup"><span data-stu-id="e6126-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="e6126-146">Door dezelfde benadering toe te passen bij het gebruik van voordelen, vermindert u `join` het aantal te controleren records.</span><span class="sxs-lookup"><span data-stu-id="e6126-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="e6126-147">Met de onderstaande query wordt gecontroleerd op aanmeldingsgebeurtenissen binnen 30 minuten na ontvangst van een schadelijk bestand:</span><span class="sxs-lookup"><span data-stu-id="e6126-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

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
- <span data-ttu-id="e6126-148">**U kunt tijdfilters** aan beide zijden toepassen, zelfs als u niet bezig bent met het onderzoeken van een bepaald tijdvenster, kunt u het aantal records verminderen dat kan worden gebruikt om de prestaties te controleren en te verbeteren door tijdfilters toe te passen op zowel de linker- als de rechtertabellen. `join`</span><span class="sxs-lookup"><span data-stu-id="e6126-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="e6126-149">De onderstaande query is van toepassing op beide tabellen, zodat `Timestamp > ago(1h)` alleen records van het afgelopen uur worden joins:</span><span class="sxs-lookup"><span data-stu-id="e6126-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="e6126-150">**Gebruik hints voor de prestaties**. Gebruik hints met de operator om de back-end zo in te delen dat belasting wordt verdeeld tijdens het uitvoeren van `join` resource-intensieve bewerkingen.</span><span class="sxs-lookup"><span data-stu-id="e6126-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="e6126-151">Meer informatie over tips voor deelnemen</span><span class="sxs-lookup"><span data-stu-id="e6126-151">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="e6126-152">De willekeurige **[](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** hint helpt bijvoorbeeld bij het samenvoegen van queryprestaties bij het samenvoegen van tabellen met een sleutel met hoge kardinaliteit (een sleutel met veel unieke waarden) zoals in de onderstaande `AccountObjectId` query:</span><span class="sxs-lookup"><span data-stu-id="e6126-152">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="e6126-153">De **[hint voor uitzending](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** is nuttig wanneer de linkertabel klein is (maximaal 100.000 records) en de rechtertabel zeer groot is.</span><span class="sxs-lookup"><span data-stu-id="e6126-153">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="e6126-154">Met de onderstaande query probeert u bijvoorbeeld een paar  e-mailberichten met specifieke onderwerpen samen te stellen, met alle berichten met koppelingen in de `EmailUrlInfo` tabel:</span><span class="sxs-lookup"><span data-stu-id="e6126-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="e6126-155">De `summarize` operator optimaliseren</span><span class="sxs-lookup"><span data-stu-id="e6126-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="e6126-156">Met [de samenvattende operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) wordt de inhoud van een tabel samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="e6126-156">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="e6126-157">Pas deze tips toe om query's te optimaliseren die deze operator gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e6126-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="e6126-158">**Unieke waarden zoeken.** Over het algemeen kunt u dit gebruiken `summarize` om unieke waarden te vinden die vaak worden herhaald.</span><span class="sxs-lookup"><span data-stu-id="e6126-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="e6126-159">Het kan onnodig zijn om dit te gebruiken voor het aggregeren van kolommen die geen terugkerende waarden hebben.</span><span class="sxs-lookup"><span data-stu-id="e6126-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="e6126-160">Hoewel één e-mailbericht deel kan uitmaken van meerdere gebeurtenissen, _is_ het onderstaande voorbeeld niet efficiënt omdat een netwerkbericht-id voor een afzonderlijke e-mail altijd wordt geleverd met een uniek `summarize` afzenderadres.</span><span class="sxs-lookup"><span data-stu-id="e6126-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="e6126-161">De operator kan eenvoudig worden vervangen door, wat in potentieel dezelfde resultaten resulteert `summarize` terwijl er minder resources worden `project` verbruikt:</span><span class="sxs-lookup"><span data-stu-id="e6126-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="e6126-162">Het volgende voorbeeld is efficiënter te gebruiken omdat er meerdere afzonderlijke exemplaren kunnen zijn van een afzenderadres dat e-mail naar hetzelfde `summarize` adres van de geadresseerde verstuurt.</span><span class="sxs-lookup"><span data-stu-id="e6126-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="e6126-163">Dergelijke combinaties zijn minder uniek en hebben waarschijnlijk dubbele waarden.</span><span class="sxs-lookup"><span data-stu-id="e6126-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="e6126-164">**Verschuif de query** opnieuw. Deze kan het beste worden gebruikt in kolommen met terugkerende waarden, maar dezelfde kolommen kunnen ook een hoge kardinaliteit hebben of grote `summarize` aantallen unieke waarden  hebben.</span><span class="sxs-lookup"><span data-stu-id="e6126-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="e6126-165">Net als de operator kunt u ook de willekeurige hint toepassen om de verwerkingsbelasting te verdelen en de prestaties te verbeteren wanneer u kolommen met hoge kardinaliteit `join` [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` gebruikt.</span><span class="sxs-lookup"><span data-stu-id="e6126-165">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="e6126-166">De onderstaande query wordt gebruikt om het unieke e-mailadres van geadresseerden te tellen, dat kan worden uitgevoerd in de honderden `summarize` duizenden grote organisaties.</span><span class="sxs-lookup"><span data-stu-id="e6126-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="e6126-167">In dit onderdeel zijn de volgende elementen opgenomen om de prestaties te `hint.shufflekey` verbeteren:</span><span class="sxs-lookup"><span data-stu-id="e6126-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="e6126-168">Queryscenario's</span><span class="sxs-lookup"><span data-stu-id="e6126-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="e6126-169">Unieke processen identificeren met proces-ids</span><span class="sxs-lookup"><span data-stu-id="e6126-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="e6126-170">Proces-inds (PID's) worden in Windows vernietigd en hergebruikt voor nieuwe processen.</span><span class="sxs-lookup"><span data-stu-id="e6126-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="e6126-171">Ze kunnen niet als unieke id's fungeren voor specifieke processen.</span><span class="sxs-lookup"><span data-stu-id="e6126-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="e6126-172">Als u een unieke id wilt krijgen voor een proces op een specifieke computer, gebruikt u de proces-id samen met de aanmaaktijd van het proces.</span><span class="sxs-lookup"><span data-stu-id="e6126-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="e6126-173">Wanneer u gegevens rond processen joint of samenvatten, voegt u kolommen toe voor de computer-id (of), de proces-id (of), en de aanmaaktijd van het proces `DeviceId` `DeviceName` `ProcessId` `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` (of)</span><span class="sxs-lookup"><span data-stu-id="e6126-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="e6126-174">Met de volgende voorbeeldquery worden processen gevonden die toegang krijgen tot meer dan tien IP-adressen via poort 445 (SMB), mogelijk zoeken naar bestands shares.</span><span class="sxs-lookup"><span data-stu-id="e6126-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="e6126-175">Voorbeeldquery:</span><span class="sxs-lookup"><span data-stu-id="e6126-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="e6126-176">De query is een samenvatting van beide processen, waarbij wordt uitgemaakt van één proces, zonder dat meerdere processen met dezelfde `InitiatingProcessId` proces-id worden door elkaar `InitiatingProcessCreationTime` gebruikt.</span><span class="sxs-lookup"><span data-stu-id="e6126-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="e6126-177">Opdrachtlijnen voor query's</span><span class="sxs-lookup"><span data-stu-id="e6126-177">Query command lines</span></span>
<span data-ttu-id="e6126-178">Er zijn talloze manieren om een opdrachtregel te maken om een taak uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="e6126-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="e6126-179">Een aanvaller kan bijvoorbeeld verwijzen naar een afbeeldingsbestand zonder pad, zonder bestandsextensie, met behulp van omgevingsvariabelen of met aanhalingstekens.</span><span class="sxs-lookup"><span data-stu-id="e6126-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="e6126-180">De aanvaller kan ook de volgorde van parameters wijzigen of meerdere aanhalingstekens en spaties toevoegen.</span><span class="sxs-lookup"><span data-stu-id="e6126-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="e6126-181">Als u meer query's met een strakker beleid rond opdrachtlijnen wilt maken, moet u de volgende procedures toepassen:</span><span class="sxs-lookup"><span data-stu-id="e6126-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="e6126-182">Identificeer de bekende processen  (zoalsnet.exeof *psexec.exe)* door op de bestandsnaamvelden te matchen in plaats van op de opdrachtregel zelf te filteren.</span><span class="sxs-lookup"><span data-stu-id="e6126-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="e6126-183">Opdrachtregelsecties parseren met de functie [parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="e6126-183">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="e6126-184">Zoek bij het opvragen van opdrachtregelargumenten niet naar een exacte overeenkomst voor meerdere niet-gerelateerde argumenten in een bepaalde volgorde.</span><span class="sxs-lookup"><span data-stu-id="e6126-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="e6126-185">Gebruik in plaats daarvan reguliere expressies of gebruik meerdere afzonderlijke expressies met operatoren.</span><span class="sxs-lookup"><span data-stu-id="e6126-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="e6126-186">Niet-opsitieve overeenkomsten voor case's gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e6126-186">Use case insensitive matches.</span></span> <span data-ttu-id="e6126-187">Gebruik bijvoorbeeld `=~` , `in~` en in plaats van , en `contains` `==` `in` `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="e6126-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="e6126-188">U kunt technieken voor het obliceren van opdrachten voorkomen door aanhalingstekens te verwijderen, komma's te vervangen door spaties en meerdere opeenvolgende spaties te vervangen door één spatie.</span><span class="sxs-lookup"><span data-stu-id="e6126-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="e6126-189">Er zijn complexere obfusatietechnieken die andere benaderingen vereisen, maar deze aanpassingen kunnen u helpen algemene technieken aan te pakken.</span><span class="sxs-lookup"><span data-stu-id="e6126-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="e6126-190">In de volgende voorbeelden ziet u verschillende manieren  om een query te maken die zoekt naar het bestandnet.exeom de firewallservice MpsSvc te stoppen:</span><span class="sxs-lookup"><span data-stu-id="e6126-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="e6126-191">Gegevens uit externe bronnen insgest maken</span><span class="sxs-lookup"><span data-stu-id="e6126-191">Ingest data from external sources</span></span>
<span data-ttu-id="e6126-192">Als u lange lijsten of grote tabellen wilt opnemen in uw query, gebruikt u de [externaldata-operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) om gegevens uit een opgegeven URI over te nemen.</span><span class="sxs-lookup"><span data-stu-id="e6126-192">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="e6126-193">U kunt gegevens op halen uit bestanden in TXT, CSV, JSON of [andere indelingen.](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats)</span><span class="sxs-lookup"><span data-stu-id="e6126-193">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="e6126-194">In het onderstaande voorbeeld ziet u hoe u de uitgebreide lijst met malware SHA-256-hashes van MalwareBazaar (abuse.ch) kunt gebruiken om bijlagen bij e-mailberichten te controleren:</span><span class="sxs-lookup"><span data-stu-id="e6126-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

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

### <a name="parse-strings"></a><span data-ttu-id="e6126-195">Parseren-tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="e6126-195">Parse strings</span></span>
<span data-ttu-id="e6126-196">Er zijn verschillende functies die u kunt gebruiken om efficiënt om te gaan met tekenreeksen die moeten worden geparseren of geconveriseerd.</span><span class="sxs-lookup"><span data-stu-id="e6126-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="e6126-197">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e6126-197">String</span></span> | <span data-ttu-id="e6126-198">Functie</span><span class="sxs-lookup"><span data-stu-id="e6126-198">Function</span></span> | <span data-ttu-id="e6126-199">Gebruiksvoorbeeld</span><span class="sxs-lookup"><span data-stu-id="e6126-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="e6126-200">Opdrachtregels</span><span class="sxs-lookup"><span data-stu-id="e6126-200">Command-lines</span></span> | [<span data-ttu-id="e6126-201">parse_command_line()</span><span class="sxs-lookup"><span data-stu-id="e6126-201">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="e6126-202">De opdracht en alle argumenten extraheren.</span><span class="sxs-lookup"><span data-stu-id="e6126-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="e6126-203">Paden</span><span class="sxs-lookup"><span data-stu-id="e6126-203">Paths</span></span> | [<span data-ttu-id="e6126-204">parse_path()</span><span class="sxs-lookup"><span data-stu-id="e6126-204">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="e6126-205">Extraheren de secties van een bestand of mappad.</span><span class="sxs-lookup"><span data-stu-id="e6126-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="e6126-206">Versienummers</span><span class="sxs-lookup"><span data-stu-id="e6126-206">Version numbers</span></span> | [<span data-ttu-id="e6126-207">parse_version()</span><span class="sxs-lookup"><span data-stu-id="e6126-207">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="e6126-208">Deconstructer een versienummer met maximaal vier secties en maximaal acht tekens per sectie.</span><span class="sxs-lookup"><span data-stu-id="e6126-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="e6126-209">Gebruik de geparseerde gegevens om de leeftijd van de versie te vergelijken.</span><span class="sxs-lookup"><span data-stu-id="e6126-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="e6126-210">IPv4-adressen</span><span class="sxs-lookup"><span data-stu-id="e6126-210">IPv4 addresses</span></span> | [<span data-ttu-id="e6126-211">parse_ipv4()</span><span class="sxs-lookup"><span data-stu-id="e6126-211">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="e6126-212">Converteert een IPv4-adres naar een lang geheel getal.</span><span class="sxs-lookup"><span data-stu-id="e6126-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="e6126-213">Als u IPv4-adressen wilt vergelijken zonder deze te converteren, gebruikt [u ipv4_compare().](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)</span><span class="sxs-lookup"><span data-stu-id="e6126-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="e6126-214">IPv6-adressen</span><span class="sxs-lookup"><span data-stu-id="e6126-214">IPv6 addresses</span></span> | [<span data-ttu-id="e6126-215">parse_ipv6()</span><span class="sxs-lookup"><span data-stu-id="e6126-215">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="e6126-216">Converteert een IPv4- of IPv6-adres naar de canonieke IPv6-notatie.</span><span class="sxs-lookup"><span data-stu-id="e6126-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="e6126-217">Als u IPv6-adressen wilt vergelijken, gebruikt [ipv6_compare().](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)</span><span class="sxs-lookup"><span data-stu-id="e6126-217">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="e6126-218">Voor meer informatie over alle ondersteunde parseringsfuncties leest [u meer over Kusto-tekenreeksfuncties.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions)</span><span class="sxs-lookup"><span data-stu-id="e6126-218">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="e6126-219">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e6126-219">Related topics</span></span>
- [<span data-ttu-id="e6126-220">Taaldocumentatie voor kusto-query's</span><span class="sxs-lookup"><span data-stu-id="e6126-220">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="e6126-221">Quota en gebruiksparameters</span><span class="sxs-lookup"><span data-stu-id="e6126-221">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="e6126-222">Geavanceerde zoekfouten verwerken</span><span class="sxs-lookup"><span data-stu-id="e6126-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="e6126-223">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="e6126-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e6126-224">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="e6126-224">Learn the query language</span></span>](advanced-hunting-query-language.md)
