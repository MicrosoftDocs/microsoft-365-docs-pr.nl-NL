---
title: DeviceFromIP (), functie in geavanceerde jacht voor Microsoft 365 Defender
description: Meer informatie over het gebruik van de functie DeviceFromIP () om de apparaten te krijgen aan wie een specifiek IP-adres is toegewezen
keywords: geavanceerde jacht, Threat jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, devicefromIP,, functie, verrijking
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 65409dd93f3703f1af115178c4cd9fa470fb7497
ms.sourcegitcommit: 25ac2736a66bb72c0d574c3fbde7472ac98d5321
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/31/2020
ms.locfileid: "49741106"
---
# <a name="devicefromip"></a><span data-ttu-id="90147-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="90147-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="90147-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="90147-105">**Applies to:**</span></span>
- <span data-ttu-id="90147-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90147-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="90147-107">Gebruik de `DeviceFromIP()` functie in uw [geavanceerde jacht](advanced-hunting-overview.md) -query's om snel de lijst te verkrijgen met apparaten die op een bepaald moment aan een bepaald IP-adres zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="90147-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="90147-108">Deze functie retourneert een tabel met de volgende kolommen:</span><span class="sxs-lookup"><span data-stu-id="90147-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="90147-109">Kolom</span><span class="sxs-lookup"><span data-stu-id="90147-109">Column</span></span> | <span data-ttu-id="90147-110">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="90147-110">Data type</span></span> | <span data-ttu-id="90147-111">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="90147-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="90147-112">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="90147-112">string</span></span> | <span data-ttu-id="90147-113">IP-adres</span><span class="sxs-lookup"><span data-stu-id="90147-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="90147-114">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="90147-114">string</span></span> | <span data-ttu-id="90147-115">Unieke id van het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="90147-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="90147-116">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="90147-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="90147-117">Argumenten</span><span class="sxs-lookup"><span data-stu-id="90147-117">Arguments</span></span>

<span data-ttu-id="90147-118">Deze functie wordt geactiveerd als onderdeel van een query.</span><span class="sxs-lookup"><span data-stu-id="90147-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="90147-119">**x**— de eerste parameter is meestal al een kolom in de query.</span><span class="sxs-lookup"><span data-stu-id="90147-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="90147-120">Dit is de kolom genaamd `IP` , het IP-adres waarvan u een lijst wilt weergeven met apparaten die aan de lijst zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="90147-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="90147-121">Dit moet een lokaal IP-adres zijn.</span><span class="sxs-lookup"><span data-stu-id="90147-121">It should be a local IP address.</span></span> <span data-ttu-id="90147-122">Externe IP-adressen worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="90147-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="90147-123">**y**: een tweede optionele parameter is de `Timestamp` functie, die de functie vraagt om de nieuwste, toegewezen apparaten uit een bepaalde tijd te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="90147-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="90147-124">Als dit niet wordt opgegeven, geeft de functie de laatste beschikbare records als resultaat.</span><span class="sxs-lookup"><span data-stu-id="90147-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="90147-125">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="90147-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="90147-126">Schaf de nieuwste apparaten aan waaraan specifiek IP-adressen zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="90147-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="90147-127">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="90147-127">Related topics</span></span>
- [<span data-ttu-id="90147-128">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="90147-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="90147-129">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="90147-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="90147-130">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="90147-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
