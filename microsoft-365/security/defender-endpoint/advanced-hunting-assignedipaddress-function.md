---
title: AssignedIPAddresses() functie in advanced hunting for Microsoft Defender for Endpoint
description: Meer informatie over het gebruik van de functie AssignedIPAddresses() om de meest recente IP-adressen aan een apparaat te krijgen
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, Microsoft Defender ATP, Microsoft Defender for Endpoint, Windows Defender, Windows Defender ATP, Windows Defender Advanced Threat Protection, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 08ab7ff5bac917a027e4380a46ab1cb2cf0a1312
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058461"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="6a50a-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="6a50a-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

><span data-ttu-id="6a50a-105">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="6a50a-105">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6a50a-106">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="6a50a-106">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="6a50a-107">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6a50a-107">**Applies to:**</span></span>
- [<span data-ttu-id="6a50a-108">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="6a50a-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="6a50a-109">Gebruik de `AssignedIPAddresses()` functie in uw geavanceerde zoekquery's om snel de meest recente IP-adressen te verkrijgen die aan een apparaat zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="6a50a-109">Use the `AssignedIPAddresses()` function in your advanced hunting queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="6a50a-110">Als u een tijdstempelargument opgeeft, verkrijgt deze functie de meest recente IP-adressen op de opgegeven tijd.</span><span class="sxs-lookup"><span data-stu-id="6a50a-110">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span>

<span data-ttu-id="6a50a-111">Deze functie retourneert een tabel met de volgende kolommen:</span><span class="sxs-lookup"><span data-stu-id="6a50a-111">This function returns a table with the following columns:</span></span>

<span data-ttu-id="6a50a-112">Kolom</span><span class="sxs-lookup"><span data-stu-id="6a50a-112">Column</span></span> | <span data-ttu-id="6a50a-113">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="6a50a-113">Data type</span></span> | <span data-ttu-id="6a50a-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6a50a-114">Description</span></span>
-|-|-
`Timestamp` | <span data-ttu-id="6a50a-115">datetime</span><span class="sxs-lookup"><span data-stu-id="6a50a-115">datetime</span></span> | <span data-ttu-id="6a50a-116">De laatste keer dat het apparaat werd waargenomen met behulp van het IP-adres</span><span class="sxs-lookup"><span data-stu-id="6a50a-116">Latest time when the device was observed using the IP address</span></span>
`IPAddress` | <span data-ttu-id="6a50a-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6a50a-117">string</span></span> | <span data-ttu-id="6a50a-118">IP-adres dat door het apparaat wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="6a50a-118">IP address used by the device</span></span>
`IPType` | <span data-ttu-id="6a50a-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6a50a-119">string</span></span> | <span data-ttu-id="6a50a-120">Geeft aan of het IP-adres een openbaar of privéadres is</span><span class="sxs-lookup"><span data-stu-id="6a50a-120">Indicates whether the IP address is a public or private address</span></span>
`NetworkAdapterType` | <span data-ttu-id="6a50a-121">int</span><span class="sxs-lookup"><span data-stu-id="6a50a-121">int</span></span> | <span data-ttu-id="6a50a-122">Netwerkadaptertype dat wordt gebruikt door het apparaat dat aan het IP-adres is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="6a50a-122">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="6a50a-123">Voor de mogelijke waarden raadpleegt u [deze enumeratie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="6a50a-123">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span>
`ConnectedNetworks` | <span data-ttu-id="6a50a-124">int</span><span class="sxs-lookup"><span data-stu-id="6a50a-124">int</span></span> | <span data-ttu-id="6a50a-125">Netwerken waar de adapter met het toegewezen IP-adres op is aangesloten.</span><span class="sxs-lookup"><span data-stu-id="6a50a-125">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="6a50a-126">Elke JSON-matrix bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeeft of deze openbaar is verbonden met internet</span><span class="sxs-lookup"><span data-stu-id="6a50a-126">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span>

## <a name="syntax"></a><span data-ttu-id="6a50a-127">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="6a50a-127">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="6a50a-128">Argumenten</span><span class="sxs-lookup"><span data-stu-id="6a50a-128">Arguments</span></span>

- <span data-ttu-id="6a50a-129">**x** of `DeviceId` waarde die het apparaat `DeviceName` identificeert</span><span class="sxs-lookup"><span data-stu-id="6a50a-129">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="6a50a-130">**y-**(datetime) waarde die de functie instrueert om de meest recente toegewezen IP-adressen te verkrijgen `Timestamp` vanaf een bepaalde tijd.</span><span class="sxs-lookup"><span data-stu-id="6a50a-130">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="6a50a-131">Als dit niet is opgegeven, retourneert de functie de meest recente IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="6a50a-131">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="6a50a-132">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="6a50a-132">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="6a50a-133">De lijst met IP-adressen die 24 uur geleden door een apparaat zijn gebruikt</span><span class="sxs-lookup"><span data-stu-id="6a50a-133">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="6a50a-134">IP-adressen krijgen die door een apparaat worden gebruikt en apparaten zoeken waarmee wordt gecommuniceerd</span><span class="sxs-lookup"><span data-stu-id="6a50a-134">Get IP addresses used by a device and find devices communicating with it</span></span>

<span data-ttu-id="6a50a-135">Deze query gebruikt de functie om toegewezen IP-adressen voor het apparaat () op of vóór een bepaalde datum `AssignedIPAddresses()` `example-device-name` () te `example-date` krijgen.</span><span class="sxs-lookup"><span data-stu-id="6a50a-135">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="6a50a-136">Vervolgens worden de IP-adressen gebruikt om verbindingen te zoeken met het apparaat dat door andere apparaten is gestart.</span><span class="sxs-lookup"><span data-stu-id="6a50a-136">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="6a50a-137">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6a50a-137">Related topics</span></span>

- [<span data-ttu-id="6a50a-138">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="6a50a-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6a50a-139">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="6a50a-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6a50a-140">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="6a50a-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
