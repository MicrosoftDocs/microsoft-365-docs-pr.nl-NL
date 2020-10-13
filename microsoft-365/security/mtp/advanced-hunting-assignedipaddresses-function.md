---
title: AssignedIPAddresses (), functie in geavanceerde jacht voor Microsoft Threat Protection
description: Meer informatie over het gebruik van de functie AssignedIPAddresses () om de meest recente IP-adressen aan een apparaat te krijgen
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, FileProfile, bestands profiel, functie, verrijking
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
ms.openlocfilehash: 462a4884e2b17f9ae75ea3bdc1531b180dcc5934
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430125"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="850bb-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="850bb-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="850bb-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="850bb-105">**Applies to:**</span></span>
- <span data-ttu-id="850bb-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="850bb-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="850bb-107">Gebruik de `AssignedIPAddresses()` functie in uw [geavanceerde jacht](advanced-hunting-overview.md) -query's om snel de nieuwste IP-adressen te verkrijgen die aan een apparaat zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="850bb-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="850bb-108">Als u een argument voor een tijdstempel opgeeft, worden voor deze functie de meest recente IP-adressen op de opgegeven tijd opgehaald.</span><span class="sxs-lookup"><span data-stu-id="850bb-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="850bb-109">Deze functie retourneert een tabel met de volgende kolommen:</span><span class="sxs-lookup"><span data-stu-id="850bb-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="850bb-110">Kolom</span><span class="sxs-lookup"><span data-stu-id="850bb-110">Column</span></span> | <span data-ttu-id="850bb-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="850bb-111">Data type</span></span> | <span data-ttu-id="850bb-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="850bb-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="850bb-113">tijd</span><span class="sxs-lookup"><span data-stu-id="850bb-113">datetime</span></span> | <span data-ttu-id="850bb-114">Laatste keer dat het apparaat is waargenomen met behulp van het IP-adres</span><span class="sxs-lookup"><span data-stu-id="850bb-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="850bb-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="850bb-115">string</span></span> | <span data-ttu-id="850bb-116">IP-adres dat door het apparaat wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="850bb-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="850bb-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="850bb-117">string</span></span> | <span data-ttu-id="850bb-118">Geeft aan of het IP-adres een openbaar of privéadres is</span><span class="sxs-lookup"><span data-stu-id="850bb-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="850bb-119">int</span><span class="sxs-lookup"><span data-stu-id="850bb-119">int</span></span> | <span data-ttu-id="850bb-120">Type netwerkadapter dat wordt gebruikt door het apparaat waaraan het IP-adres is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="850bb-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="850bb-121">Voor de mogelijke waarden raadpleegt u [deze inventarisatie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="850bb-121">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="850bb-122">int</span><span class="sxs-lookup"><span data-stu-id="850bb-122">int</span></span> | <span data-ttu-id="850bb-123">Netwerken waarmee de adapter met het toegewezen IP-adres is verbonden.</span><span class="sxs-lookup"><span data-stu-id="850bb-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="850bb-124">Elke JSON-matrix bevat de naam van een netwerk, categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeven of de verbinding openbaar met internet is.</span><span class="sxs-lookup"><span data-stu-id="850bb-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="850bb-125">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="850bb-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="850bb-126">Argumenten</span><span class="sxs-lookup"><span data-stu-id="850bb-126">Arguments</span></span>

- <span data-ttu-id="850bb-127">**x**— `DeviceId` of `DeviceName` waarde die het apparaat identificeert</span><span class="sxs-lookup"><span data-stu-id="850bb-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="850bb-128">**y** `Timestamp` de waarde y (datetime) die de functie vraagt om de meest recente IP-adressen van een specifieke tijd te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="850bb-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="850bb-129">Als dat niet is opgegeven, retourneert de functie de nieuwste IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="850bb-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="850bb-130">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="850bb-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="850bb-131">De lijst met IP-adressen die worden gebruikt door een apparaat, 24 uur geleden weergeven</span><span class="sxs-lookup"><span data-stu-id="850bb-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="850bb-132">IP-adressen van een apparaat achterhalen en apparaten communiceren</span><span class="sxs-lookup"><span data-stu-id="850bb-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="850bb-133">Deze query maakt gebruik `AssignedIPAddresses()` van de functie om toegewezen IP-adressen voor het apparaat ( `example-device-name` ) op of vóór een bepaalde datum () te krijgen `example-date` .</span><span class="sxs-lookup"><span data-stu-id="850bb-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="850bb-134">Vervolgens gebruikt u de IP-adressen om verbindingen te vinden met het apparaat dat door andere apparaten wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="850bb-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="850bb-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="850bb-135">Related topics</span></span>
- [<span data-ttu-id="850bb-136">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="850bb-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="850bb-137">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="850bb-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="850bb-138">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="850bb-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
