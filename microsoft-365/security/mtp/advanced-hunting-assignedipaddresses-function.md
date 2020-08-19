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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 72d02bafa168e48c2d588771f5289da09e6d6000
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794229"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="e6503-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="e6503-104">AssignedIPAddresses()</span></span>

<span data-ttu-id="e6503-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e6503-105">**Applies to:**</span></span>
- <span data-ttu-id="e6503-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e6503-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e6503-107">Gebruik de `AssignedIPAddresses()` functie om snel de nieuwste IP-adressen te verkrijgen die zijn toegewezen aan een apparaat of de meest recente IP-adressen vanaf een bepaald moment.</span><span class="sxs-lookup"><span data-stu-id="e6503-107">Use the `AssignedIPAddresses()` function to quickly obtain the latest IP addresses that have been assigned to a device or the most recent IP addresses from a specified point in time.</span></span> <span data-ttu-id="e6503-108">Deze functie retourneert een tabel met de volgende kolommen:</span><span class="sxs-lookup"><span data-stu-id="e6503-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="e6503-109">Kolom</span><span class="sxs-lookup"><span data-stu-id="e6503-109">Column</span></span> | <span data-ttu-id="e6503-110">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="e6503-110">Data type</span></span> | <span data-ttu-id="e6503-111">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e6503-111">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="e6503-112">Tempels</span><span class="sxs-lookup"><span data-stu-id="e6503-112">Timestamp</span></span> | <span data-ttu-id="e6503-113">tijd</span><span class="sxs-lookup"><span data-stu-id="e6503-113">datetime</span></span> | <span data-ttu-id="e6503-114">Laatste keer dat het apparaat is waargenomen met behulp van het IP-adres</span><span class="sxs-lookup"><span data-stu-id="e6503-114">Latest time when the device was observed using the IP address</span></span> |
| <span data-ttu-id="e6503-115">Adressen</span><span class="sxs-lookup"><span data-stu-id="e6503-115">IPAddress</span></span> | <span data-ttu-id="e6503-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e6503-116">string</span></span> | <span data-ttu-id="e6503-117">IP-adres dat door het apparaat wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="e6503-117">IP address used by the device</span></span> |
| <span data-ttu-id="e6503-118">IPType</span><span class="sxs-lookup"><span data-stu-id="e6503-118">IPType</span></span> | <span data-ttu-id="e6503-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e6503-119">string</span></span> | <span data-ttu-id="e6503-120">Geeft aan of het IP-adres een openbaar of privéadres is</span><span class="sxs-lookup"><span data-stu-id="e6503-120">Indicates whether the IP address is a public or private address</span></span> |
| <span data-ttu-id="e6503-121">NetworkAdapterType</span><span class="sxs-lookup"><span data-stu-id="e6503-121">NetworkAdapterType</span></span> | <span data-ttu-id="e6503-122">int</span><span class="sxs-lookup"><span data-stu-id="e6503-122">int</span></span> | <span data-ttu-id="e6503-123">Type netwerkadapter dat wordt gebruikt door het apparaat waaraan het IP-adres is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="e6503-123">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="e6503-124">Voor de mogelijke waarden raadpleegt u [deze inventarisatie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="e6503-124">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span>  |
| <span data-ttu-id="e6503-125">ConnectedNetworks</span><span class="sxs-lookup"><span data-stu-id="e6503-125">ConnectedNetworks</span></span> | <span data-ttu-id="e6503-126">int</span><span class="sxs-lookup"><span data-stu-id="e6503-126">int</span></span> | <span data-ttu-id="e6503-127">Netwerken waarmee de adapter met het toegewezen IP-adres is verbonden.</span><span class="sxs-lookup"><span data-stu-id="e6503-127">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="e6503-128">Elke JSON-matrix bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag waarmee wordt aangegeven of de verbinding openbaar met internet is verbonden.</span><span class="sxs-lookup"><span data-stu-id="e6503-128">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |


## <a name="syntax"></a><span data-ttu-id="e6503-129">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="e6503-129">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="e6503-130">Argumenten</span><span class="sxs-lookup"><span data-stu-id="e6503-130">Arguments</span></span>

- <span data-ttu-id="e6503-131">**x** — `DeviceId` of `DeviceName` waarde die het apparaat identificeert</span><span class="sxs-lookup"><span data-stu-id="e6503-131">**x** — `DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="e6503-132">**y** `Timestamp` de waarde y, (datetime) die het specifieke tijdstip aangeeft waarop de meest recente IP-adressen moeten worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="e6503-132">**y** — `Timestamp` (datetime) value indicating the specific point in time where to get the most recent IP addresses.</span></span> <span data-ttu-id="e6503-133">Als dat niet is opgegeven, retourneert de functie de nieuwste IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="e6503-133">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="e6503-134">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="e6503-134">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-as-of-24-hours-ago"></a><span data-ttu-id="e6503-135">De lijst met IP-adressen die een apparaat 24 uur geleden gebruikt, wordt weergeven</span><span class="sxs-lookup"><span data-stu-id="e6503-135">Get the list of IP addresses used by a device as of 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="e6503-136">IP-adressen van een apparaat achterhalen en apparaten communiceren</span><span class="sxs-lookup"><span data-stu-id="e6503-136">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="e6503-137">Deze query maakt gebruik `AssignedIPAddresses()` van de functie om toegewezen IP-adressen voor het apparaat ( `example-device-name` ) op of vóór een bepaalde datum () te krijgen `example-date` .</span><span class="sxs-lookup"><span data-stu-id="e6503-137">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="e6503-138">Vervolgens gebruikt u de IP-adressen om verbindingen te vinden met het apparaat dat door andere apparaten wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="e6503-138">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="e6503-139">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e6503-139">Related topics</span></span>
- [<span data-ttu-id="e6503-140">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="e6503-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e6503-141">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="e6503-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e6503-142">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="e6503-142">Understand the schema</span></span>](advanced-hunting-schema-tables.md)