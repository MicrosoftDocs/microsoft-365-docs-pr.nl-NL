---
title: Relevante informatie over een entiteit aanvragen met behulp van Go
description: Meer informatie over het gebruik van het hulpprogramma ' go go ' om snel de benodigde informatie over een entiteit of gebeurtenis te doorzoeken met behulp van geavanceerde jacht.
keywords: geavanceerde jacht, incident, Pivot, entiteit, zoeken, relevante evenementen, bedreigings jacht, Cyber Threat jacht, zoeken, query, telemetrie, Microsoft 365, Microsoft Threat Protection
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: e381793caf49318074bcd096e4301cdf49d12e88
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412188"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="d8389-104">Snel zoeken naar informatie over entiteiten of evenementen met Go Go</span><span class="sxs-lookup"><span data-stu-id="d8389-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d8389-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d8389-105">**Applies to:**</span></span>
- <span data-ttu-id="d8389-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d8389-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d8389-107">Met de actie *Go jacht* kunt u snel gebeurtenissen en verschillende entiteitstypen met [krachtige zoekfuncties op basis](advanced-hunting-overview.md) van query's.</span><span class="sxs-lookup"><span data-stu-id="d8389-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="d8389-108">Met deze actie voert u automatisch een geavanceerde zoekopdracht uit om relevante informatie over de geselecteerde gebeurtenis of entiteit te zoeken.</span><span class="sxs-lookup"><span data-stu-id="d8389-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="d8389-109">De actie *Go* -actie is beschikbaar in diverse secties van het Beveiligingscentrum wanneer de details van een gebeurtenis of entiteit worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d8389-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="d8389-110">U kunt bijvoorbeeld de volgende secties gebruiken om te *zoeken* :</span><span class="sxs-lookup"><span data-stu-id="d8389-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="d8389-111">Op de [pagina incident](investigate-incidents.md#incident-overview)kunt u Details bekijken van gebruikers, apparaten en vele andere entiteiten die aan een incident zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="d8389-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="d8389-112">Wanneer u een entiteit selecteert, vindt u aanvullende informatie en verschillende acties die u kunt uitvoeren op die entitity.</span><span class="sxs-lookup"><span data-stu-id="d8389-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="d8389-113">In het onderstaande voorbeeld is er een postvak geselecteerd, met details over het postvak en de optie om te zoeken naar meer informatie over het postvak.</span><span class="sxs-lookup"><span data-stu-id="d8389-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Afbeelding met details postvak met de optie Ga naar](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="d8389-115">Op de pagina incidenten kunt u ook een lijst met entiteiten openen op het tabblad bewijs. Het selecteren van een van deze entiteiten biedt een mogelijkheid snel te zoeken naar informatie over die entiteit.</span><span class="sxs-lookup"><span data-stu-id="d8389-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Afbeelding van een geselecteerd bestand met de optie Ga naar het tabblad gegevens](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="d8389-117">Wanneer u de tijdlijn voor een apparaat bekijkt, kunt u een gebeurtenis selecteren in de tijdlijn om aanvullende informatie over die gebeurtenis te bekijken.</span><span class="sxs-lookup"><span data-stu-id="d8389-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="d8389-118">Als u een gebeurtenis hebt geselecteerd, kunt u de optie voor het zoeken naar andere relevante gebeurtenissen in de geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="d8389-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Afbeelding met gebeurtenisdetails met de optie Ga naar](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="d8389-120">Wanneer u **Ga start of zoeken** **naar gerelateerde gebeurtenissen** selecteert, worden andere query's uitgevoerd, afhankelijk van of u een entiteit of een gebeurtenis hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="d8389-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="d8389-121">Query voor entiteits informatie</span><span class="sxs-lookup"><span data-stu-id="d8389-121">Query for entity information</span></span>
<span data-ttu-id="d8389-122">Wanneer u *Go* -zoekopdracht gebruikt om informatie te lezen over een gebruiker, apparaat of ander type entiteit, controleert de query alle relevante schema tabellen voor gebeurtenissen die betrekking hebben op die entiteit.</span><span class="sxs-lookup"><span data-stu-id="d8389-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="d8389-123">Om de resultaten beheersbaar te houden, is de query in de loop van de vroegste periode in de afgelopen 30 dagen in de afgelopen 30 dagen voor de laatste 30 dagen die de entiteit omvat, in de afgelopen 30 dagen voor de laatste dertig dagen van de entiteit met het incident.</span><span class="sxs-lookup"><span data-stu-id="d8389-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="d8389-124">Hier ziet u een voorbeeld van de zoekopdracht Go voor een apparaat:</span><span class="sxs-lookup"><span data-stu-id="d8389-124">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="d8389-125">Ondersteunde entiteittypen</span><span class="sxs-lookup"><span data-stu-id="d8389-125">Supported entity types</span></span>
<span data-ttu-id="d8389-126">Wanneer u een van de volgende entiteittypen selecteert, kunt u de *overgaan* gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d8389-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="d8389-127">Bestanden</span><span class="sxs-lookup"><span data-stu-id="d8389-127">Files</span></span>
- <span data-ttu-id="d8389-128">Sturen</span><span class="sxs-lookup"><span data-stu-id="d8389-128">Emails</span></span>
- <span data-ttu-id="d8389-129">E-mail clusters</span><span class="sxs-lookup"><span data-stu-id="d8389-129">Email clusters</span></span>
- <span data-ttu-id="d8389-130">Postbus</span><span class="sxs-lookup"><span data-stu-id="d8389-130">Mailboxes</span></span>
- <span data-ttu-id="d8389-131">Gebruikers</span><span class="sxs-lookup"><span data-stu-id="d8389-131">Users</span></span>
- <span data-ttu-id="d8389-132">Apparaten</span><span class="sxs-lookup"><span data-stu-id="d8389-132">Devices</span></span>
- <span data-ttu-id="d8389-133">IP-adressen</span><span class="sxs-lookup"><span data-stu-id="d8389-133">IP addresses</span></span>
- <span data-ttu-id="d8389-134">URLs</span><span class="sxs-lookup"><span data-stu-id="d8389-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="d8389-135">Query voor informatie over gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="d8389-135">Query for event information</span></span>
<span data-ttu-id="d8389-136">Wanneer u *Ga* naar de query voor het maken van een tijdlijn gaat, controleert de query alle relevante schema tabellen op andere gebeurtenissen over de tijd van de geselecteerde gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="d8389-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="d8389-137">De volgende query bevat bijvoorbeeld een overzicht van gebeurtenissen in verschillende schema tabellen die in dezelfde periode plaatsvonden op hetzelfde apparaat:</span><span class="sxs-lookup"><span data-stu-id="d8389-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

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

## <a name="adjust-the-query"></a><span data-ttu-id="d8389-138">De query aanpassen</span><span class="sxs-lookup"><span data-stu-id="d8389-138">Adjust the query</span></span>
<span data-ttu-id="d8389-139">Met enige kennis van de [querytaal](advanced-hunting-query-language.md)kunt u de query aanpassen aan uw voorkeur.</span><span class="sxs-lookup"><span data-stu-id="d8389-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="d8389-140">U kunt bijvoorbeeld de volgende regel aanpassen om de grootte van het tijdvenster te bepalen:</span><span class="sxs-lookup"><span data-stu-id="d8389-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="d8389-141">Naast het wijzigen van de query om meer relevante resultaten te bereiken, kunt u ook het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="d8389-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="d8389-142">Het resultaat weergeven als grafiek</span><span class="sxs-lookup"><span data-stu-id="d8389-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="d8389-143">Een aangepaste detectieregel maken</span><span class="sxs-lookup"><span data-stu-id="d8389-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="d8389-144">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d8389-144">Related topics</span></span>
- [<span data-ttu-id="d8389-145">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="d8389-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d8389-146">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="d8389-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d8389-147">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="d8389-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="d8389-148">Aangepaste detectieregels</span><span class="sxs-lookup"><span data-stu-id="d8389-148">Custom detection rules</span></span>](custom-detection-rules.md)
