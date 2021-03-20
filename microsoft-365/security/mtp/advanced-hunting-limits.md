---
title: Geavanceerde jachtquota en gebruiksparameters in Microsoft 365 Defender
description: Inzicht in verschillende quota en gebruiksparameters (servicelimieten) die ervoor zorgen dat de geavanceerde huntingservice reageert
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results, quota, parameters, allocation
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
ms.openlocfilehash: 862d295739f952a6a5db06f5cfdfbc5aa481de9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909020"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="81769-104">Geavanceerde jachtquota en gebruiksparameters</span><span class="sxs-lookup"><span data-stu-id="81769-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="81769-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="81769-105">**Applies to:**</span></span>
- <span data-ttu-id="81769-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81769-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="81769-107">Als u de service performant en responsief wilt houden, stelt geavanceerd zoeken verschillende quota's en gebruiksparameters in (ook wel 'servicelimieten' genoemd).</span><span class="sxs-lookup"><span data-stu-id="81769-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="81769-108">Deze quota's en parameters zijn van toepassing op query's die handmatig en volgens [aangepaste detectieregels worden uitgevoerd.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="81769-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="81769-109">Klanten die regelmatig meerdere query's uitvoeren, moeten het verbruik bijhouden en [optimalisatie-best practices](advanced-hunting-best-practices.md) toepassen om onderbrekingen te minimaliseren.</span><span class="sxs-lookup"><span data-stu-id="81769-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="81769-110">Raadpleeg de volgende tabel om inzicht te krijgen in bestaande quota en gebruiksparameters.</span><span class="sxs-lookup"><span data-stu-id="81769-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="81769-111">Quotum of parameter</span><span class="sxs-lookup"><span data-stu-id="81769-111">Quota or parameter</span></span> | <span data-ttu-id="81769-112">Grootte</span><span class="sxs-lookup"><span data-stu-id="81769-112">Size</span></span> | <span data-ttu-id="81769-113">Vernieuwingscyclus</span><span class="sxs-lookup"><span data-stu-id="81769-113">Refresh cycle</span></span> | <span data-ttu-id="81769-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="81769-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="81769-115">Gegevensbereik</span><span class="sxs-lookup"><span data-stu-id="81769-115">Data range</span></span> | <span data-ttu-id="81769-116">30 dagen</span><span class="sxs-lookup"><span data-stu-id="81769-116">30 days</span></span> | <span data-ttu-id="81769-117">Elke query</span><span class="sxs-lookup"><span data-stu-id="81769-117">Every query</span></span> | <span data-ttu-id="81769-118">Elke query kan gegevens opvragen van maximaal de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="81769-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="81769-119">Resultatenset</span><span class="sxs-lookup"><span data-stu-id="81769-119">Result set</span></span> | <span data-ttu-id="81769-120">10.000 rijen</span><span class="sxs-lookup"><span data-stu-id="81769-120">10,000 rows</span></span> | <span data-ttu-id="81769-121">Elke query</span><span class="sxs-lookup"><span data-stu-id="81769-121">Every query</span></span> | <span data-ttu-id="81769-122">Elke query kan maximaal 10.000 records retourneren.</span><span class="sxs-lookup"><span data-stu-id="81769-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="81769-123">Time-out</span><span class="sxs-lookup"><span data-stu-id="81769-123">Timeout</span></span> | <span data-ttu-id="81769-124">10 minuten</span><span class="sxs-lookup"><span data-stu-id="81769-124">10 minutes</span></span> | <span data-ttu-id="81769-125">Elke query</span><span class="sxs-lookup"><span data-stu-id="81769-125">Every query</span></span> | <span data-ttu-id="81769-126">Elke query kan maximaal 10 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="81769-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="81769-127">Als de service niet binnen 10 minuten is voltooid, wordt er een fout weergegeven in de service.</span><span class="sxs-lookup"><span data-stu-id="81769-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="81769-128">CPU-resources</span><span class="sxs-lookup"><span data-stu-id="81769-128">CPU resources</span></span> | <span data-ttu-id="81769-129">Op basis van tenantgrootte</span><span class="sxs-lookup"><span data-stu-id="81769-129">Based on tenant size</span></span> | <span data-ttu-id="81769-130">- Op het uur en vervolgens om de 15 minuten</span><span class="sxs-lookup"><span data-stu-id="81769-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="81769-131">- Dagelijks om 12:00 uur</span><span class="sxs-lookup"><span data-stu-id="81769-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="81769-132">De service dwingt het dagelijkse quotum en het quotum van 15 minuten afzonderlijk af.</span><span class="sxs-lookup"><span data-stu-id="81769-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="81769-133">Voor elk quotum wordt in [de portal](advanced-hunting-errors.md) een fout weergegeven wanneer een query wordt uitgevoerd en de tenant meer dan 10% van de toegewezen resources heeft verbruikt.</span><span class="sxs-lookup"><span data-stu-id="81769-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="81769-134">Query's worden geblokkeerd als de tenant 100% heeft bereikt tot na de volgende dagelijkse cyclus of 15 minuten.</span><span class="sxs-lookup"><span data-stu-id="81769-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="81769-135">Er is een aparte set quota's en parameters van toepassing op geavanceerde query's die via de API worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="81769-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="81769-136">Meer informatie over geavanceerde api's voor jagen</span><span class="sxs-lookup"><span data-stu-id="81769-136">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="81769-137">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="81769-137">Related topics</span></span>

- [<span data-ttu-id="81769-138">Geavanceerde best practices voor jagen</span><span class="sxs-lookup"><span data-stu-id="81769-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="81769-139">Geavanceerde zoekfouten verwerken</span><span class="sxs-lookup"><span data-stu-id="81769-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="81769-140">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="81769-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="81769-141">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="81769-141">Custom detections overview</span></span>](custom-detections-overview.md)