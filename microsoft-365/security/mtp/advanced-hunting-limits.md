---
title: Geavanceerde zoekquota's en gebruiksparameters in Microsoft 365 Defender
description: Inzicht krijgen in verschillende quota's en gebruiksparameters (servicelimieten) die ervoor zorgen dat de geavanceerde zoekservice snel reageert
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
ms.openlocfilehash: 3d3b1055408b51e8d217f2abcb0e83ef7dd74949
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929788"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="cdf36-104">Geavanceerde zoekquota's en gebruiksparameters</span><span class="sxs-lookup"><span data-stu-id="cdf36-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cdf36-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="cdf36-105">**Applies to:**</span></span>
- <span data-ttu-id="cdf36-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cdf36-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="cdf36-107">Om de service snel en snel te houden, stelt geavanceerd zoeken verschillende quota's en gebruiksparameters in (ook wel 'servicelimieten' genoemd).</span><span class="sxs-lookup"><span data-stu-id="cdf36-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="cdf36-108">Deze quota en parameters zijn van toepassing op query's die handmatig en volgens aangepaste [detectieregels worden uitgevoerd.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="cdf36-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="cdf36-109">Klanten die regelmatig meerdere query's uitvoeren, moeten het verbruik bijhouden en optimalisatieprocedures toepassen [om](advanced-hunting-best-practices.md) onderbrekingen tot een minimum te beperken.</span><span class="sxs-lookup"><span data-stu-id="cdf36-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="cdf36-110">Raadpleeg de volgende tabel om inzicht te krijgen in bestaande quota's en gebruiksparameters.</span><span class="sxs-lookup"><span data-stu-id="cdf36-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="cdf36-111">Quotum of parameter</span><span class="sxs-lookup"><span data-stu-id="cdf36-111">Quota or parameter</span></span> | <span data-ttu-id="cdf36-112">Grootte</span><span class="sxs-lookup"><span data-stu-id="cdf36-112">Size</span></span> | <span data-ttu-id="cdf36-113">Vernieuwingscyclus</span><span class="sxs-lookup"><span data-stu-id="cdf36-113">Refresh cycle</span></span> | <span data-ttu-id="cdf36-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="cdf36-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="cdf36-115">Gegevensbereik</span><span class="sxs-lookup"><span data-stu-id="cdf36-115">Data range</span></span> | <span data-ttu-id="cdf36-116">30 dagen</span><span class="sxs-lookup"><span data-stu-id="cdf36-116">30 days</span></span> | <span data-ttu-id="cdf36-117">Elke query</span><span class="sxs-lookup"><span data-stu-id="cdf36-117">Every query</span></span> | <span data-ttu-id="cdf36-118">Met elke query kunnen gegevens van de afgelopen 30 dagen worden opgevraagd.</span><span class="sxs-lookup"><span data-stu-id="cdf36-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="cdf36-119">Resultaatset</span><span class="sxs-lookup"><span data-stu-id="cdf36-119">Result set</span></span> | <span data-ttu-id="cdf36-120">10.000 rijen</span><span class="sxs-lookup"><span data-stu-id="cdf36-120">10,000 rows</span></span> | <span data-ttu-id="cdf36-121">Elke query</span><span class="sxs-lookup"><span data-stu-id="cdf36-121">Every query</span></span> | <span data-ttu-id="cdf36-122">Elke query kan maximaal 10.000 records retourneren.</span><span class="sxs-lookup"><span data-stu-id="cdf36-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="cdf36-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="cdf36-123">Timeout</span></span> | <span data-ttu-id="cdf36-124">10 minuten</span><span class="sxs-lookup"><span data-stu-id="cdf36-124">10 minutes</span></span> | <span data-ttu-id="cdf36-125">Elke query</span><span class="sxs-lookup"><span data-stu-id="cdf36-125">Every query</span></span> | <span data-ttu-id="cdf36-126">Elke query kan maximaal 10 minuten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="cdf36-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="cdf36-127">Als de taak niet binnen 10 minuten wordt voltooid, wordt er een foutbericht weergegeven.</span><span class="sxs-lookup"><span data-stu-id="cdf36-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="cdf36-128">CPU-bronnen</span><span class="sxs-lookup"><span data-stu-id="cdf36-128">CPU resources</span></span> | <span data-ttu-id="cdf36-129">Op basis van de grootte van de tenant</span><span class="sxs-lookup"><span data-stu-id="cdf36-129">Based on tenant size</span></span> | <span data-ttu-id="cdf36-130">- Op het uur en vervolgens elke 15 minuten</span><span class="sxs-lookup"><span data-stu-id="cdf36-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="cdf36-131">- Dagelijks om 12 middernacht</span><span class="sxs-lookup"><span data-stu-id="cdf36-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="cdf36-132">De service dwingt de dagelijkse limiet en het quotum van 15 minuten afzonderlijk af.</span><span class="sxs-lookup"><span data-stu-id="cdf36-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="cdf36-133">Voor elk quotum wordt [in de portal](advanced-hunting-errors.md) een fout weergegeven wanneer een query wordt uitgevoerd en de tenant meer dan 10% van de toegewezen resources heeft verbruikt.</span><span class="sxs-lookup"><span data-stu-id="cdf36-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="cdf36-134">Query's worden geblokkeerd als de tenant 100% heeft bereikt tot na de volgende dagelijkse cyclus of 15 minuten.</span><span class="sxs-lookup"><span data-stu-id="cdf36-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="cdf36-135">Er is een afzonderlijke set quota's en parameters van toepassing op geavanceerde zoekquery's die worden uitgevoerd via de API.</span><span class="sxs-lookup"><span data-stu-id="cdf36-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="cdf36-136">Meer informatie over geavanceerde api's voor zoeken</span><span class="sxs-lookup"><span data-stu-id="cdf36-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="cdf36-137">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="cdf36-137">Related topics</span></span>

- [<span data-ttu-id="cdf36-138">Geavanceerde best practices voor zoeken</span><span class="sxs-lookup"><span data-stu-id="cdf36-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="cdf36-139">Geavanceerde zoekfouten verwerken</span><span class="sxs-lookup"><span data-stu-id="cdf36-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="cdf36-140">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="cdf36-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cdf36-141">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="cdf36-141">Custom detections overview</span></span>](custom-detections-overview.md)