---
title: AssignedIPAddresses() functie in advanced hunting for Microsoft 365 Defender
description: Meer informatie over het gebruik van de functie AssignedIPAddresses() om de meest recente IP-adressen aan een apparaat te krijgen
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
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
ms.openlocfilehash: be638141e205946be18d6a718470e7b92b18b1e7
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500409"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="6a2fe-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="6a2fe-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6a2fe-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6a2fe-105">**Applies to:**</span></span>
- <span data-ttu-id="6a2fe-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a2fe-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6a2fe-107">Gebruik de `AssignedIPAddresses()` functie in uw geavanceerde [zoekquery's](advanced-hunting-overview.md) om snel de meest recente IP-adressen te verkrijgen die aan een apparaat zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="6a2fe-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="6a2fe-108">Als u een tijdstempelargument opgeeft, verkrijgt deze functie de meest recente IP-adressen op de opgegeven tijd.</span><span class="sxs-lookup"><span data-stu-id="6a2fe-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="6a2fe-109">Deze functie retourneert een tabel met de volgende kolommen:</span><span class="sxs-lookup"><span data-stu-id="6a2fe-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="6a2fe-110">Kolom</span><span class="sxs-lookup"><span data-stu-id="6a2fe-110">Column</span></span> | <span data-ttu-id="6a2fe-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="6a2fe-111">Data type</span></span> | <span data-ttu-id="6a2fe-112">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="6a2fe-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="6a2fe-113">datetime</span><span class="sxs-lookup"><span data-stu-id="6a2fe-113">datetime</span></span> | <span data-ttu-id="6a2fe-114">De laatste keer dat het apparaat werd waargenomen met behulp van het IP-adres</span><span class="sxs-lookup"><span data-stu-id="6a2fe-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="6a2fe-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6a2fe-115">string</span></span> | <span data-ttu-id="6a2fe-116">IP-adres dat door het apparaat wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="6a2fe-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="6a2fe-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6a2fe-117">string</span></span> | <span data-ttu-id="6a2fe-118">Geeft aan of het IP-adres een openbaar of privéadres is</span><span class="sxs-lookup"><span data-stu-id="6a2fe-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="6a2fe-119">int</span><span class="sxs-lookup"><span data-stu-id="6a2fe-119">int</span></span> | <span data-ttu-id="6a2fe-120">Netwerkadaptertype dat wordt gebruikt door het apparaat dat aan het IP-adres is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="6a2fe-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="6a2fe-121">Voor de mogelijke waarden raadpleegt u [deze enumeratie](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="6a2fe-121">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="6a2fe-122">int</span><span class="sxs-lookup"><span data-stu-id="6a2fe-122">int</span></span> | <span data-ttu-id="6a2fe-123">Netwerken waar de adapter met het toegewezen IP-adres op is aangesloten.</span><span class="sxs-lookup"><span data-stu-id="6a2fe-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="6a2fe-124">Elke JSON-matrix bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeeft of deze openbaar is verbonden met internet</span><span class="sxs-lookup"><span data-stu-id="6a2fe-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="6a2fe-125">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="6a2fe-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="6a2fe-126">Argumenten</span><span class="sxs-lookup"><span data-stu-id="6a2fe-126">Arguments</span></span>

- <span data-ttu-id="6a2fe-127">**x** of `DeviceId` waarde die het apparaat `DeviceName` identificeert</span><span class="sxs-lookup"><span data-stu-id="6a2fe-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="6a2fe-128">**y-**(datetime) waarde die de functie instrueert om de meest recente toegewezen IP-adressen te verkrijgen `Timestamp` vanaf een bepaalde tijd.</span><span class="sxs-lookup"><span data-stu-id="6a2fe-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="6a2fe-129">Als dit niet is opgegeven, retourneert de functie de meest recente IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="6a2fe-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="6a2fe-130">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="6a2fe-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="6a2fe-131">De lijst met IP-adressen die 24 uur geleden door een apparaat zijn gebruikt</span><span class="sxs-lookup"><span data-stu-id="6a2fe-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="6a2fe-132">IP-adressen krijgen die door een apparaat worden gebruikt en apparaten zoeken waarmee wordt gecommuniceerd</span><span class="sxs-lookup"><span data-stu-id="6a2fe-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="6a2fe-133">Deze query gebruikt de functie om toegewezen IP-adressen voor het apparaat () op of vóór een bepaalde datum `AssignedIPAddresses()` `example-device-name` () te `example-date` krijgen.</span><span class="sxs-lookup"><span data-stu-id="6a2fe-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="6a2fe-134">Vervolgens worden de IP-adressen gebruikt om verbindingen te zoeken met het apparaat dat door andere apparaten is gestart.</span><span class="sxs-lookup"><span data-stu-id="6a2fe-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a><span data-ttu-id="6a2fe-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6a2fe-135">Related topics</span></span>
- [<span data-ttu-id="6a2fe-136">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="6a2fe-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6a2fe-137">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="6a2fe-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6a2fe-138">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="6a2fe-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)