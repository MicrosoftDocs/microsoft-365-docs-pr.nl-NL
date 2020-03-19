---
title: Overzicht van geavanceerde jacht in Microsoft Threat Protection
description: Meer informatie over geavanceerde jachtquery's in Microsoft 365 en hoe u deze gebruiken om bedreigingen en zwakke punten in uw netwerk proactief te vinden
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-bedreigingen, microsoft 365, mtp, m365, zoeken, query, telemetrie, aangepaste detecties, schema, kusto, microsoft 365, Microsoft Threat Protection
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 598ef669e95081ef098dfa9cfdb5473b21b28306
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42810454"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a><span data-ttu-id="3d92c-104">Proactief op zoek naar bedreigingen met geavanceerde jacht in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3d92c-104">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>

<span data-ttu-id="3d92c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3d92c-105">**Applies to:**</span></span>
- <span data-ttu-id="3d92c-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="3d92c-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="3d92c-107">Geavanceerde jacht is een query-gebaseerde bedreiging-jacht tool waarmee u verkennen tot 30 dagen van ruwe gegevens.</span><span class="sxs-lookup"><span data-stu-id="3d92c-107">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="3d92c-108">U gebeurtenissen in uw netwerk proactief inspecteren om interessante indicatoren en entiteiten te vinden.</span><span class="sxs-lookup"><span data-stu-id="3d92c-108">You can proactively inspect events in your network to locate interesting indicators and entities.</span></span> <span data-ttu-id="3d92c-109">De flexibele toegang tot gegevens vergemakkelijkt de ongedwongen jacht op zowel bekende als potentiële bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="3d92c-109">The flexible access to data facilitates unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="3d92c-110">In het Microsoft 365-beveiligingscentrum ondersteunt advanced hunting query's die gegevens van zowel Microsoft Defender ATP, die gegevens van apparaten aan boord bevatten, als Office 365 ATP, die gegevens uit e-mails verstrekken.</span><span class="sxs-lookup"><span data-stu-id="3d92c-110">In the Microsoft 365 security center, advanced hunting supports queries that look into data from both Microsoft Defender ATP, covering data from onboarded devices, and Office 365 ATP, providing data from emails.</span></span> <span data-ttu-id="3d92c-111">Als u geavanceerde jacht wilt gebruiken, [schakelt u Microsoft Threat Protection in.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="3d92c-111">To use advanced hunting, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="get-started-with-advanced-hunting"></a><span data-ttu-id="3d92c-112">Aan de slag met geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="3d92c-112">Get started with advanced hunting</span></span>

<span data-ttu-id="3d92c-113">We raden aan om verschillende stappen te doorlopen om snel aan de slag te gaan met geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="3d92c-113">We recommend going through several steps to quickly get up and running with advanced hunting.</span></span>

| <span data-ttu-id="3d92c-114">Leerdoel</span><span class="sxs-lookup"><span data-stu-id="3d92c-114">Learning goal</span></span> | <span data-ttu-id="3d92c-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3d92c-115">Description</span></span> | <span data-ttu-id="3d92c-116">Resource</span><span class="sxs-lookup"><span data-stu-id="3d92c-116">Resource</span></span> |
|--|--|--|
| <span data-ttu-id="3d92c-117">**Krijg een gevoel voor de taal**</span><span class="sxs-lookup"><span data-stu-id="3d92c-117">**Get a feel for the language**</span></span> | <span data-ttu-id="3d92c-118">Geavanceerde jacht is gebaseerd op de [Kusto-querytaal,](https://docs.microsoft.com/azure/kusto/query/)die dezelfde syntaxis en operatoren ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="3d92c-118">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/), supporting the same syntax and operators.</span></span> <span data-ttu-id="3d92c-119">Begin met het leren van de querytaal door uw eerste query uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="3d92c-119">Start learning the query language by running your first query.</span></span> | [<span data-ttu-id="3d92c-120">Overzicht van querytalen</span><span class="sxs-lookup"><span data-stu-id="3d92c-120">Query language overview</span></span>](advanced-hunting-query-language.md) |
| <span data-ttu-id="3d92c-121">**Het schema begrijpen**</span><span class="sxs-lookup"><span data-stu-id="3d92c-121">**Understand the schema**</span></span> | <span data-ttu-id="3d92c-122">Krijg een goed, hoog niveau inzicht in de tabellen in het schema en hun kolommen.</span><span class="sxs-lookup"><span data-stu-id="3d92c-122">Get a good, high-level understanding of the tables in the schema and their columns.</span></span> <span data-ttu-id="3d92c-123">Zo u bepalen waar u naar gegevens moet zoeken en hoe u uw query's samenstellen.</span><span class="sxs-lookup"><span data-stu-id="3d92c-123">This will help you determine where to look for data and how to construct your queries.</span></span> | [<span data-ttu-id="3d92c-124">Schemaverwijzing</span><span class="sxs-lookup"><span data-stu-id="3d92c-124">Schema reference</span></span>](advanced-hunting-schema-tables.md) |
| <span data-ttu-id="3d92c-125">**Vooraf gedefinieerde query's gebruiken**</span><span class="sxs-lookup"><span data-stu-id="3d92c-125">**Use predefined queries**</span></span> | <span data-ttu-id="3d92c-126">Bekijk verzamelingen van vooraf gedefinieerde query's die verschillende scenario's voor bedreigingsjacht behandelen.</span><span class="sxs-lookup"><span data-stu-id="3d92c-126">Explore collections of predefined queries covering different threat hunting scenarios.</span></span> | [<span data-ttu-id="3d92c-127">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="3d92c-127">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
| <span data-ttu-id="3d92c-128">**Query's optimaliseren**</span><span class="sxs-lookup"><span data-stu-id="3d92c-128">**Optimize queries**</span></span> | <span data-ttu-id="3d92c-129">Meer informatie over het maken van efficiënte query's en query's die gegevens van e-mails en apparaten combineren.</span><span class="sxs-lookup"><span data-stu-id="3d92c-129">Understand how to create efficient queries and queries that combine data from emails and devices.</span></span> | <span data-ttu-id="3d92c-130">[Best practices opvragen,](advanced-hunting-shared-queries.md) [op zoek naar apparaten en e-mails](advanced-hunting-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="3d92c-130">[Query best practices](advanced-hunting-shared-queries.md), [Hunt across devices and emails](advanced-hunting-best-practices.md)</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="3d92c-131">Hulp krijgen bij het schrijven van query's</span><span class="sxs-lookup"><span data-stu-id="3d92c-131">Get help as you write queries</span></span>
<span data-ttu-id="3d92c-132">Profiteer van de volgende functionaliteit om sneller query's te schrijven:</span><span class="sxs-lookup"><span data-stu-id="3d92c-132">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="3d92c-133">**Autosuggest** - als je query's schrijft, geavanceerde jacht biedt suggesties.</span><span class="sxs-lookup"><span data-stu-id="3d92c-133">**Autosuggest** — as you write queries, advanced hunting provides suggestions.</span></span> 
- <span data-ttu-id="3d92c-134">**Schemaverwijzing** : naast uw werkgebied wordt een schemaverwijzing weergegeven met de lijst met tabellen en hun kolommen.</span><span class="sxs-lookup"><span data-stu-id="3d92c-134">**Schema reference** — a schema reference that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="3d92c-135">Voor meer informatie, zweven over een item.</span><span class="sxs-lookup"><span data-stu-id="3d92c-135">For more information, hover over an item.</span></span> <span data-ttu-id="3d92c-136">Dubbelklik op een item om het in te voegen in de queryeditor.</span><span class="sxs-lookup"><span data-stu-id="3d92c-136">Double-click an item to insert it to the query editor.</span></span>

## <a name="drilldown-from-query-results"></a><span data-ttu-id="3d92c-137">Drilldown van queryresultaten</span><span class="sxs-lookup"><span data-stu-id="3d92c-137">Drilldown from query results</span></span>
<span data-ttu-id="3d92c-138">Als u meer informatie wilt weergeven over entiteiten, zoals machines, bestanden, gebruikers, IP-adressen en URL's, klikt u in uw queryresultaten op de entiteits-id.</span><span class="sxs-lookup"><span data-stu-id="3d92c-138">To view more information about entities, such as machines, files, users, IP addresses, and URLs, in your query results, simply click the entity identifier.</span></span> <span data-ttu-id="3d92c-139">Hiermee wordt een gedetailleerde profielpagina geopend voor de geselecteerde entiteit in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="3d92c-139">This opens a detailed profile page for the selected entity in Microsoft Defender Security Center.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="3d92c-140">Uw query's aanpassen aan de resultaten</span><span class="sxs-lookup"><span data-stu-id="3d92c-140">Tweak your queries from the results</span></span>
<span data-ttu-id="3d92c-141">Klik met de rechtermuisknop op een waarde in de resultatenset om uw query snel te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="3d92c-141">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="3d92c-142">U de opties gebruiken om:</span><span class="sxs-lookup"><span data-stu-id="3d92c-142">You can use the options to:</span></span>

- <span data-ttu-id="3d92c-143">Expliciet zoeken naar de`==`geselecteerde waarde ( )</span><span class="sxs-lookup"><span data-stu-id="3d92c-143">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="3d92c-144">De geselecteerde waarde uitsluiten`!=`van de query ( )</span><span class="sxs-lookup"><span data-stu-id="3d92c-144">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="3d92c-145">Meer geavanceerde operators voor het toevoegen van `contains`de `starts with` waarde aan uw query, zoals , en`ends with`</span><span class="sxs-lookup"><span data-stu-id="3d92c-145">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Afbeelding van Microsoft Defender ATP geavanceerde jacht resultaat set](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="3d92c-147">De queryresultaten filteren</span><span class="sxs-lookup"><span data-stu-id="3d92c-147">Filter the query results</span></span>
<span data-ttu-id="3d92c-148">De filters die rechts worden weergegeven, geven een overzicht van de resultatenset.</span><span class="sxs-lookup"><span data-stu-id="3d92c-148">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="3d92c-149">Elke kolom heeft een eigen sectie met de verschillende waarden die voor die kolom zijn gevonden en het aantal exemplaren.</span><span class="sxs-lookup"><span data-stu-id="3d92c-149">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="3d92c-150">Verfijn uw query door de knoppen '+' of '-' te selecteren op de waarden die u wilt opnemen of uit te sluiten en vervolgens **Query uitvoeren**te selecteren .</span><span class="sxs-lookup"><span data-stu-id="3d92c-150">Refine your query by selecting the "+" or "-" buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Beeld van geavanceerd jachtfilter](../../media/advanced-hunting-filter.png)

<span data-ttu-id="3d92c-152">Zodra u het filter toepast om de query te wijzigen en de query vervolgens uit te voeren, worden de resultaten dienovereenkomstig bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="3d92c-152">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3d92c-153">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="3d92c-153">Related topics</span></span>
- [<span data-ttu-id="3d92c-154">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="3d92c-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3d92c-155">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="3d92c-155">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3d92c-156">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="3d92c-156">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3d92c-157">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="3d92c-157">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3d92c-158">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="3d92c-158">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
