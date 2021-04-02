---
title: Geavanceerde zoeklimieten in Microsoft Defender ATP
description: Verschillende servicelimieten begrijpen die ervoor zorgen dat de geavanceerde huntingservice snel reageert
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8a9279d1dd2a6465553b576609bb81cdf4e03fa0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499530"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="b1620-104">Geavanceerde limieten voor de jachtservice</span><span class="sxs-lookup"><span data-stu-id="b1620-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b1620-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b1620-105">**Applies to:**</span></span>
- [<span data-ttu-id="b1620-106">Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b1620-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="b1620-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="b1620-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b1620-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="b1620-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="b1620-109">Als u de service performant en responsief wilt houden, stelt geavanceerd zoeken verschillende limieten in voor query's die handmatig en volgens [aangepaste detectieregels worden uitgevoerd.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="b1620-109">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="b1620-110">Raadpleeg de volgende tabel om deze limieten te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="b1620-110">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="b1620-111">Limiet</span><span class="sxs-lookup"><span data-stu-id="b1620-111">Limit</span></span> | <span data-ttu-id="b1620-112">Grootte</span><span class="sxs-lookup"><span data-stu-id="b1620-112">Size</span></span> | <span data-ttu-id="b1620-113">Vernieuwingscyclus</span><span class="sxs-lookup"><span data-stu-id="b1620-113">Refresh cycle</span></span> | <span data-ttu-id="b1620-114">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="b1620-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="b1620-115">Gegevensbereik</span><span class="sxs-lookup"><span data-stu-id="b1620-115">Data range</span></span> | <span data-ttu-id="b1620-116">30 dagen</span><span class="sxs-lookup"><span data-stu-id="b1620-116">30 days</span></span> | <span data-ttu-id="b1620-117">Elke query</span><span class="sxs-lookup"><span data-stu-id="b1620-117">Every query</span></span> | <span data-ttu-id="b1620-118">Elke query kan gegevens opvragen van maximaal de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="b1620-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="b1620-119">Resultatenset</span><span class="sxs-lookup"><span data-stu-id="b1620-119">Result set</span></span> | <span data-ttu-id="b1620-120">10.000 rijen</span><span class="sxs-lookup"><span data-stu-id="b1620-120">10,000 rows</span></span> | <span data-ttu-id="b1620-121">Elke query</span><span class="sxs-lookup"><span data-stu-id="b1620-121">Every query</span></span> | <span data-ttu-id="b1620-122">Elke query kan maximaal 10.000 records retourneren.</span><span class="sxs-lookup"><span data-stu-id="b1620-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="b1620-123">Time-out</span><span class="sxs-lookup"><span data-stu-id="b1620-123">Timeout</span></span> | <span data-ttu-id="b1620-124">10 minuten</span><span class="sxs-lookup"><span data-stu-id="b1620-124">10 minutes</span></span> | <span data-ttu-id="b1620-125">Elke query</span><span class="sxs-lookup"><span data-stu-id="b1620-125">Every query</span></span> | <span data-ttu-id="b1620-126">Elke query kan maximaal 10 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="b1620-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="b1620-127">Als de service niet binnen 10 minuten is voltooid, wordt er een fout weergegeven in de service.</span><span class="sxs-lookup"><span data-stu-id="b1620-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="b1620-128">CPU-resources</span><span class="sxs-lookup"><span data-stu-id="b1620-128">CPU resources</span></span> | <span data-ttu-id="b1620-129">Op basis van tenantgrootte</span><span class="sxs-lookup"><span data-stu-id="b1620-129">Based on tenant size</span></span> | <span data-ttu-id="b1620-130">- Op het uur en vervolgens om de 15 minuten</span><span class="sxs-lookup"><span data-stu-id="b1620-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="b1620-131">- Dagelijks om 12:00 uur</span><span class="sxs-lookup"><span data-stu-id="b1620-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="b1620-132">De service dwingt de dagelijkse limiet en de limiet van 15 minuten afzonderlijk af.</span><span class="sxs-lookup"><span data-stu-id="b1620-132">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="b1620-133">Voor elke limiet wordt in [de portal](advanced-hunting-errors.md) een fout weergegeven wanneer een query wordt uitgevoerd en de tenant meer dan 10% van de toegewezen resources heeft verbruikt.</span><span class="sxs-lookup"><span data-stu-id="b1620-133">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="b1620-134">Query's worden geblokkeerd als de tenant 100% heeft bereikt tot na de volgende dagelijkse cyclus of 15 minuten.</span><span class="sxs-lookup"><span data-stu-id="b1620-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="b1620-135">Er is een aparte set limieten van toepassing op geavanceerde query's die via de API worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b1620-135">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="b1620-136">Meer informatie over geavanceerde api's voor jagen</span><span class="sxs-lookup"><span data-stu-id="b1620-136">Read about advanced hunting APIs</span></span>](run-advanced-query-api.md)

<span data-ttu-id="b1620-137">Klanten die regelmatig meerdere query's uitvoeren, moeten het verbruik bijhouden en [optimalisatie-best practices](advanced-hunting-best-practices.md) toepassen om verstoringen als gevolg van het overschrijden van deze limieten tot een minimum te beperken.</span><span class="sxs-lookup"><span data-stu-id="b1620-137">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1620-138">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b1620-138">Related topics</span></span>

- [<span data-ttu-id="b1620-139">Geavanceerde best practices voor jagen</span><span class="sxs-lookup"><span data-stu-id="b1620-139">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b1620-140">Geavanceerde zoekfouten verwerken</span><span class="sxs-lookup"><span data-stu-id="b1620-140">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="b1620-141">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b1620-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b1620-142">Aangepaste detectieregels</span><span class="sxs-lookup"><span data-stu-id="b1620-142">Custom detections rules</span></span>](custom-detection-rules.md)
