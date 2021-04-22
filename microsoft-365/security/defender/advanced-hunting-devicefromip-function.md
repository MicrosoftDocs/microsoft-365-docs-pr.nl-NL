---
title: DeviceFromIP() functie in advanced hunting for Microsoft 365 Defender
description: Meer informatie over het gebruik van de functie DeviceFromIP() om de apparaten te krijgen die aan een specifiek IP-adres zijn toegewezen
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, device, devicefromIP, function, enrichment
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
ms.openlocfilehash: 3ea951e35555721a989001b2a5235df5b89a8a55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933179"
---
# <a name="devicefromip"></a><span data-ttu-id="a827b-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="a827b-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a827b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a827b-105">**Applies to:**</span></span>
- <span data-ttu-id="a827b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a827b-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="a827b-107">Gebruik de `DeviceFromIP()` functie in uw geavanceerde [query's](advanced-hunting-overview.md) om snel de lijst met apparaten te verkrijgen die op een bepaald moment aan een bepaald IP-adres zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="a827b-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="a827b-108">Deze functie retourneert een tabel met de volgende kolommen:</span><span class="sxs-lookup"><span data-stu-id="a827b-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="a827b-109">Kolom</span><span class="sxs-lookup"><span data-stu-id="a827b-109">Column</span></span> | <span data-ttu-id="a827b-110">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="a827b-110">Data type</span></span> | <span data-ttu-id="a827b-111">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="a827b-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="a827b-112">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a827b-112">string</span></span> | <span data-ttu-id="a827b-113">IP-adres</span><span class="sxs-lookup"><span data-stu-id="a827b-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="a827b-114">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a827b-114">string</span></span> | <span data-ttu-id="a827b-115">Unieke id voor het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="a827b-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="a827b-116">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="a827b-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="a827b-117">Argumenten</span><span class="sxs-lookup"><span data-stu-id="a827b-117">Arguments</span></span>

<span data-ttu-id="a827b-118">Deze functie wordt aangeroepen als onderdeel van een query.</span><span class="sxs-lookup"><span data-stu-id="a827b-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="a827b-119">**x:** de eerste parameter is meestal al een kolom in de query.</span><span class="sxs-lookup"><span data-stu-id="a827b-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="a827b-120">In dit geval is het de kolom met de naam , het IP-adres waarvoor u een lijst met apparaten wilt zien die aan de kolom `IP` zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="a827b-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="a827b-121">Het moet een lokaal IP-adres zijn.</span><span class="sxs-lookup"><span data-stu-id="a827b-121">It should be a local IP address.</span></span> <span data-ttu-id="a827b-122">Externe IP-adressen worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="a827b-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="a827b-123">**y**: een tweede optionele parameter is de , die de functie instrueert om de meest recente toegewezen apparaten te verkrijgen `Timestamp` vanaf een bepaalde tijd.</span><span class="sxs-lookup"><span data-stu-id="a827b-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="a827b-124">Als dit niet is opgegeven, retourneert de functie de meest recente beschikbare records.</span><span class="sxs-lookup"><span data-stu-id="a827b-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="a827b-125">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="a827b-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="a827b-126">De nieuwste apparaten krijgen die aan specifieke IP-adressen zijn toegewezen</span><span class="sxs-lookup"><span data-stu-id="a827b-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="a827b-127">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a827b-127">Related topics</span></span>
- [<span data-ttu-id="a827b-128">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="a827b-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a827b-129">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="a827b-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a827b-130">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="a827b-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
