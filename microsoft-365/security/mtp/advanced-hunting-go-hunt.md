---
title: Krijg relevante informatie over een entiteit met zoeken
description: Meer informatie over het gebruik van het hulpprogramma voor zoeken naar onderweg om snel te zoeken naar relevante informatie over een entiteit of gebeurtenis met behulp van geavanceerd zoeken.
keywords: advanced hunt, incident, pivot, entity, go hunt, relevant events, threat hunt, cyber threat hunt, search, query, telemetry, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 9e707fe8b3dff40d0698630cd0592b297042e5fb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929503"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="38acc-104">Snel zoeken naar entiteits- of gebeurtenisgegevens met zoeken</span><span class="sxs-lookup"><span data-stu-id="38acc-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="38acc-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="38acc-105">**Applies to:**</span></span>
- <span data-ttu-id="38acc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38acc-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="38acc-107">Met de *zoekactie kunt* u snel gebeurtenissen en verschillende entiteitstypen onderzoeken met behulp van krachtige geavanceerde zoekmogelijkheden op basis van query's. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="38acc-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="38acc-108">Met deze actie wordt automatisch een geavanceerde zoekquery uitgevoerd om relevante informatie over de geselecteerde gebeurtenis of entiteit te vinden.</span><span class="sxs-lookup"><span data-stu-id="38acc-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="38acc-109">De *zoekactie* is beschikbaar in verschillende secties van het beveiligingscentrum wanneer details van gebeurtenissen of entiteiten worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="38acc-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="38acc-110">U kunt bijvoorbeeld zoeken in *de* volgende secties:</span><span class="sxs-lookup"><span data-stu-id="38acc-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="38acc-111">Op de [incidentpagina](investigate-incidents.md#incident-overview)kunt u details bekijken over gebruikers, apparaten en vele andere entiteiten die aan een incident zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="38acc-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="38acc-112">Als u een entiteit selecteert, krijgt u aanvullende informatie en verschillende acties die u op die entiteit kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="38acc-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="38acc-113">In het onderstaande voorbeeld is een postvak geselecteerd, met informatie over het postvak en de optie om te zoeken naar meer informatie over het postvak.</span><span class="sxs-lookup"><span data-stu-id="38acc-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Afbeelding met postvakdetails met de optie voor zoeken naar onderweg](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="38acc-115">Op de pagina met incidenten kunt u ook een lijst met entiteiten openen op het tabblad Bewijs. Als u een van deze entiteiten selecteert, kunt u snel zoeken naar informatie over die entiteit.</span><span class="sxs-lookup"><span data-stu-id="38acc-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Afbeelding van geselecteerd bestand met de optie Zoeken naar onderweg op het tabblad Bewijs](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="38acc-117">Wanneer u de tijdlijn van een apparaat bekijkt, kunt u een gebeurtenis selecteren in de tijdlijn om aanvullende informatie over die gebeurtenis weer te geven.</span><span class="sxs-lookup"><span data-stu-id="38acc-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="38acc-118">Wanneer een gebeurtenis is geselecteerd, krijgt u de mogelijkheid om te zoeken naar andere relevante gebeurtenissen in geavanceerd zoeken.</span><span class="sxs-lookup"><span data-stu-id="38acc-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Afbeelding met gebeurtenisdetails met de optie om te zoeken](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="38acc-120">Als **u Zoeken naar** of Zoeken naar gerelateerde **gebeurtenissen** selecteert, worden verschillende query's doorstaat, afhankelijk van of u een entiteit of gebeurtenis hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="38acc-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="38acc-121">Query voor entiteitsinformatie</span><span class="sxs-lookup"><span data-stu-id="38acc-121">Query for entity information</span></span>
<span data-ttu-id="38acc-122">Wanneer u *zoeken gebruikt om* te zoeken naar informatie over een gebruiker, apparaat of ander type entiteit, controleert de query alle relevante schematabellen op gebeurtenissen die betrekking hebben op die entiteit.</span><span class="sxs-lookup"><span data-stu-id="38acc-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="38acc-123">Om de resultaten beheersbaar te houden, heeft de query een bereik van ongeveer dezelfde periode als de eerste activiteit in de afgelopen 30 dagen waarbij de entiteit betrokken is en is gerelateerd aan het incident.</span><span class="sxs-lookup"><span data-stu-id="38acc-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="38acc-124">Hier is een voorbeeld van de zoekquery voor een apparaat:</span><span class="sxs-lookup"><span data-stu-id="38acc-124">Here is an example of the go hunt query for a device:</span></span>

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a><span data-ttu-id="38acc-125">Ondersteunde entiteitstypen</span><span class="sxs-lookup"><span data-stu-id="38acc-125">Supported entity types</span></span>
<span data-ttu-id="38acc-126">U kunt zoeken *gebruiken nadat* u een van deze entiteitstypen hebt geselecteerd:</span><span class="sxs-lookup"><span data-stu-id="38acc-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="38acc-127">Bestanden</span><span class="sxs-lookup"><span data-stu-id="38acc-127">Files</span></span>
- <span data-ttu-id="38acc-128">E-mailberichten</span><span class="sxs-lookup"><span data-stu-id="38acc-128">Emails</span></span>
- <span data-ttu-id="38acc-129">E-mailclusters</span><span class="sxs-lookup"><span data-stu-id="38acc-129">Email clusters</span></span>
- <span data-ttu-id="38acc-130">Postvakken</span><span class="sxs-lookup"><span data-stu-id="38acc-130">Mailboxes</span></span>
- <span data-ttu-id="38acc-131">Gebruikers</span><span class="sxs-lookup"><span data-stu-id="38acc-131">Users</span></span>
- <span data-ttu-id="38acc-132">Apparaten</span><span class="sxs-lookup"><span data-stu-id="38acc-132">Devices</span></span>
- <span data-ttu-id="38acc-133">IP-adressen</span><span class="sxs-lookup"><span data-stu-id="38acc-133">IP addresses</span></span>
- <span data-ttu-id="38acc-134">URL's</span><span class="sxs-lookup"><span data-stu-id="38acc-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="38acc-135">Query voor gebeurtenisgegevens</span><span class="sxs-lookup"><span data-stu-id="38acc-135">Query for event information</span></span>
<span data-ttu-id="38acc-136">Wanneer u *zoeken gebruikt om* te zoeken naar informatie over een tijdlijngebeurtenis, controleert de query alle relevante schematabellen op andere gebeurtenissen rond de tijd van de geselecteerde gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="38acc-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="38acc-137">De volgende query bevat bijvoorbeeld gebeurtenissen in verschillende schematabellen die hebben plaatsgevonden rond dezelfde periode op hetzelfde apparaat:</span><span class="sxs-lookup"><span data-stu-id="38acc-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="38acc-138">De query aanpassen</span><span class="sxs-lookup"><span data-stu-id="38acc-138">Adjust the query</span></span>
<span data-ttu-id="38acc-139">Met enige kennis van de [querytaal](advanced-hunting-query-language.md)kunt u de query aan uw voorkeur aanpassen.</span><span class="sxs-lookup"><span data-stu-id="38acc-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="38acc-140">U kunt bijvoorbeeld deze regel aanpassen, die de grootte van het tijdvenster bepaalt:</span><span class="sxs-lookup"><span data-stu-id="38acc-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="38acc-141">Naast het wijzigen van de query om relevantere resultaten te krijgen, kunt u ook:</span><span class="sxs-lookup"><span data-stu-id="38acc-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="38acc-142">De resultaten weergeven als grafieken</span><span class="sxs-lookup"><span data-stu-id="38acc-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="38acc-143">Een aangepaste detectieregel maken</span><span class="sxs-lookup"><span data-stu-id="38acc-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="38acc-144">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="38acc-144">Related topics</span></span>
- [<span data-ttu-id="38acc-145">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="38acc-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="38acc-146">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="38acc-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="38acc-147">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="38acc-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="38acc-148">Aangepaste detectieregels</span><span class="sxs-lookup"><span data-stu-id="38acc-148">Custom detection rules</span></span>](custom-detection-rules.md)
