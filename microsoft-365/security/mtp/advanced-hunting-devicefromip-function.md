---
title: DeviceFromIP() functie in geavanceerd zoeken naar Microsoft 365 Defender
description: Informatie over het gebruik van de functie DeviceFromIP() om de apparaten te krijgen aan welke een specifiek IP-adres is toegewezen
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, device, devicefromIP, function, enrichment
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 86373c903252fde4ab71c80a81404428a7366da7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931300"
---
# <a name="devicefromip"></a><span data-ttu-id="8af95-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="8af95-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8af95-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8af95-105">**Applies to:**</span></span>
- <span data-ttu-id="8af95-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8af95-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="8af95-107">Gebruik de functie in uw geavanceerde zoekquery's om snel een lijst te verkrijgen met apparaten die op een bepaald moment aan een bepaald `DeviceFromIP()` IP-adres [](advanced-hunting-overview.md) zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="8af95-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="8af95-108">Deze functie retourneert een tabel met de volgende kolommen:</span><span class="sxs-lookup"><span data-stu-id="8af95-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="8af95-109">Kolom</span><span class="sxs-lookup"><span data-stu-id="8af95-109">Column</span></span> | <span data-ttu-id="8af95-110">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="8af95-110">Data type</span></span> | <span data-ttu-id="8af95-111">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="8af95-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="8af95-112">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8af95-112">string</span></span> | <span data-ttu-id="8af95-113">IP-adres</span><span class="sxs-lookup"><span data-stu-id="8af95-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="8af95-114">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8af95-114">string</span></span> | <span data-ttu-id="8af95-115">Unieke id voor het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="8af95-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="8af95-116">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="8af95-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="8af95-117">Argumenten</span><span class="sxs-lookup"><span data-stu-id="8af95-117">Arguments</span></span>

<span data-ttu-id="8af95-118">Deze functie wordt aangeroepen als onderdeel van een query.</span><span class="sxs-lookup"><span data-stu-id="8af95-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="8af95-119">**x:** de eerste parameter is meestal al een kolom in de query.</span><span class="sxs-lookup"><span data-stu-id="8af95-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="8af95-120">In dit geval is het de kolom met de naam , het IP-adres waarvoor u een lijst wilt zien met apparaten `IP` die aan het adres zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="8af95-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="8af95-121">Het moet een lokaal IP-adres zijn.</span><span class="sxs-lookup"><span data-stu-id="8af95-121">It should be a local IP address.</span></span> <span data-ttu-id="8af95-122">Externe IP-adressen worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="8af95-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="8af95-123">**y:** een tweede optionele parameter is de , die de functie opdracht geeft om de meest recente toegewezen apparaten op `Timestamp` een bepaald moment op te halen.</span><span class="sxs-lookup"><span data-stu-id="8af95-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="8af95-124">Als deze niet is opgegeven, worden met de functie de laatst beschikbare records als retourneert.</span><span class="sxs-lookup"><span data-stu-id="8af95-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="8af95-125">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="8af95-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="8af95-126">Haal de meest recente apparaten op die specifieke IP-adressen hebben gekregen</span><span class="sxs-lookup"><span data-stu-id="8af95-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="8af95-127">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8af95-127">Related topics</span></span>
- [<span data-ttu-id="8af95-128">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="8af95-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8af95-129">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="8af95-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8af95-130">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="8af95-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
