---
title: Geavanceerde jachtquota en gebruiksparameters in Microsoft 365 Defender
description: Inzicht in verschillende quota en gebruiksparameters (servicelimieten) die ervoor zorgen dat de geavanceerde huntingservice reageert
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results, quota, parameters, allocation
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
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245598"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="b430c-104">Geavanceerde jachtquota en gebruiksparameters</span><span class="sxs-lookup"><span data-stu-id="b430c-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b430c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b430c-105">**Applies to:**</span></span>
- <span data-ttu-id="b430c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b430c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b430c-107">Als u de service performant en responsief wilt houden, stelt geavanceerd zoeken verschillende quota's en gebruiksparameters in (ook wel 'servicelimieten' genoemd).</span><span class="sxs-lookup"><span data-stu-id="b430c-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="b430c-108">Deze quota's en parameters zijn afzonderlijk van toepassing op query's die handmatig worden uitgevoerd en op query's die worden uitgevoerd met [aangepaste detectieregels.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="b430c-108">These quotas and parameters apply separately to queries run manually and to queries run using [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="b430c-109">Klanten die regelmatig meerdere query's uitvoeren, moeten rekening houden met deze limieten en [optimalisatie-best practices](advanced-hunting-best-practices.md) toepassen om onderbrekingen te minimaliseren.</span><span class="sxs-lookup"><span data-stu-id="b430c-109">Customers who run multiple queries regularly should be mindful of these limits and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="b430c-110">Raadpleeg de volgende tabel om inzicht te krijgen in bestaande quota en gebruiksparameters.</span><span class="sxs-lookup"><span data-stu-id="b430c-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="b430c-111">Quotum of parameter</span><span class="sxs-lookup"><span data-stu-id="b430c-111">Quota or parameter</span></span> | <span data-ttu-id="b430c-112">Grootte</span><span class="sxs-lookup"><span data-stu-id="b430c-112">Size</span></span> | <span data-ttu-id="b430c-113">Vernieuwingscyclus</span><span class="sxs-lookup"><span data-stu-id="b430c-113">Refresh cycle</span></span> | <span data-ttu-id="b430c-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b430c-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="b430c-115">Gegevensbereik</span><span class="sxs-lookup"><span data-stu-id="b430c-115">Data range</span></span> | <span data-ttu-id="b430c-116">30 dagen</span><span class="sxs-lookup"><span data-stu-id="b430c-116">30 days</span></span> | <span data-ttu-id="b430c-117">Elke query</span><span class="sxs-lookup"><span data-stu-id="b430c-117">Every query</span></span> | <span data-ttu-id="b430c-118">Elke query kan gegevens opvragen van maximaal de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="b430c-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="b430c-119">Resultatenset</span><span class="sxs-lookup"><span data-stu-id="b430c-119">Result set</span></span> | <span data-ttu-id="b430c-120">10.000 rijen</span><span class="sxs-lookup"><span data-stu-id="b430c-120">10,000 rows</span></span> | <span data-ttu-id="b430c-121">Elke query</span><span class="sxs-lookup"><span data-stu-id="b430c-121">Every query</span></span> | <span data-ttu-id="b430c-122">Elke query kan maximaal 10.000 records retourneren.</span><span class="sxs-lookup"><span data-stu-id="b430c-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="b430c-123">Time-out</span><span class="sxs-lookup"><span data-stu-id="b430c-123">Timeout</span></span> | <span data-ttu-id="b430c-124">10 minuten</span><span class="sxs-lookup"><span data-stu-id="b430c-124">10 minutes</span></span> | <span data-ttu-id="b430c-125">Elke query</span><span class="sxs-lookup"><span data-stu-id="b430c-125">Every query</span></span> | <span data-ttu-id="b430c-126">Elke query kan maximaal 10 minuten duren.</span><span class="sxs-lookup"><span data-stu-id="b430c-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="b430c-127">Als de service niet binnen 10 minuten is voltooid, wordt er een fout weergegeven in de service.</span><span class="sxs-lookup"><span data-stu-id="b430c-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="b430c-128">CPU-resources</span><span class="sxs-lookup"><span data-stu-id="b430c-128">CPU resources</span></span> | <span data-ttu-id="b430c-129">Op basis van tenantgrootte</span><span class="sxs-lookup"><span data-stu-id="b430c-129">Based on tenant size</span></span> | <span data-ttu-id="b430c-130">Elke 15 minuten</span><span class="sxs-lookup"><span data-stu-id="b430c-130">Every 15 minutes</span></span> | <span data-ttu-id="b430c-131">De [portal geeft een fout weer](advanced-hunting-errors.md) wanneer een query wordt uitgevoerd en de tenant meer dan 10% van de toegewezen resources heeft verbruikt.</span><span class="sxs-lookup"><span data-stu-id="b430c-131">The [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="b430c-132">Query's worden geblokkeerd als de tenant 100% heeft bereikt tot na de volgende cyclus van 15 minuten.</span><span class="sxs-lookup"><span data-stu-id="b430c-132">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="b430c-133">Er is een aparte set quota's en parameters van toepassing op geavanceerde query's die via de API worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b430c-133">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="b430c-134">Meer informatie over geavanceerde api's voor jagen</span><span class="sxs-lookup"><span data-stu-id="b430c-134">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="b430c-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b430c-135">Related topics</span></span>

- [<span data-ttu-id="b430c-136">Geavanceerde best practices voor jagen</span><span class="sxs-lookup"><span data-stu-id="b430c-136">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b430c-137">Geavanceerde zoekfouten verwerken</span><span class="sxs-lookup"><span data-stu-id="b430c-137">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="b430c-138">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b430c-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b430c-139">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="b430c-139">Custom detections overview</span></span>](custom-detections-overview.md)