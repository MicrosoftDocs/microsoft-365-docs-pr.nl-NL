---
title: Geavanceerde jacht limieten in Microsoft Threat Protection
description: Meer informatie over de verschillende service limieten waarmee de Advanced jacht-service kan reageren
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema, kusto, processorlimiet, query limiet, bronnen, maximum resultaten
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
ms.openlocfilehash: e3fbe29076d541df68dc39754960386fe935c7bc
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950921"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="b7940-104">Geavanceerde jacht-service limieten</span><span class="sxs-lookup"><span data-stu-id="b7940-104">Advanced hunting service limits</span></span>

<span data-ttu-id="b7940-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b7940-105">**Applies to:**</span></span>
- <span data-ttu-id="b7940-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b7940-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b7940-107">Om de dienst in werking te houden en op de hoogte te houden, worden in geavanceerde jacht diverse limieten ingesteld voor query's handmatig en op basis van [aangepaste detectieregels](custom-detection-rules.md).</span><span class="sxs-lookup"><span data-stu-id="b7940-107">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="b7940-108">Raadpleeg de volgende tabel voor meer informatie over deze limieten.</span><span class="sxs-lookup"><span data-stu-id="b7940-108">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="b7940-109">Limiet</span><span class="sxs-lookup"><span data-stu-id="b7940-109">Limit</span></span> | <span data-ttu-id="b7940-110">Grootte</span><span class="sxs-lookup"><span data-stu-id="b7940-110">Size</span></span> | <span data-ttu-id="b7940-111">Vernieuwingscyclus</span><span class="sxs-lookup"><span data-stu-id="b7940-111">Refresh cycle</span></span> | <span data-ttu-id="b7940-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b7940-112">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="b7940-113">Gegevensbereik</span><span class="sxs-lookup"><span data-stu-id="b7940-113">Data range</span></span> | <span data-ttu-id="b7940-114">30 dagen</span><span class="sxs-lookup"><span data-stu-id="b7940-114">30 days</span></span> | <span data-ttu-id="b7940-115">Elke query</span><span class="sxs-lookup"><span data-stu-id="b7940-115">Every query</span></span> | <span data-ttu-id="b7940-116">Met elke query kunnen gegevens worden opgezocht van de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="b7940-116">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="b7940-117">Resultatenset</span><span class="sxs-lookup"><span data-stu-id="b7940-117">Result set</span></span> | <span data-ttu-id="b7940-118">rijen in 10.000</span><span class="sxs-lookup"><span data-stu-id="b7940-118">10,000 rows</span></span> | <span data-ttu-id="b7940-119">Elke query</span><span class="sxs-lookup"><span data-stu-id="b7940-119">Every query</span></span> | <span data-ttu-id="b7940-120">Elke query kan resulteren in 10.000-records.</span><span class="sxs-lookup"><span data-stu-id="b7940-120">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="b7940-121">Waar</span><span class="sxs-lookup"><span data-stu-id="b7940-121">Timeout</span></span> | <span data-ttu-id="b7940-122">10 minuten</span><span class="sxs-lookup"><span data-stu-id="b7940-122">10 minutes</span></span> | <span data-ttu-id="b7940-123">Elke query</span><span class="sxs-lookup"><span data-stu-id="b7940-123">Every query</span></span> | <span data-ttu-id="b7940-124">Een query kan maximaal 10 minuten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b7940-124">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="b7940-125">Als de service niet binnen 10 minuten wordt voltooid, wordt er een fout weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b7940-125">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="b7940-126">CPU-resources</span><span class="sxs-lookup"><span data-stu-id="b7940-126">CPU resources</span></span> | <span data-ttu-id="b7940-127">Gebaseerd op Tenant grootte</span><span class="sxs-lookup"><span data-stu-id="b7940-127">Based on tenant size</span></span> | <span data-ttu-id="b7940-128">-Op het uur en vervolgens elke 15 minuten</span><span class="sxs-lookup"><span data-stu-id="b7940-128">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="b7940-129">-Dagelijks voor 12 middernacht</span><span class="sxs-lookup"><span data-stu-id="b7940-129">- Daily at 12 midnight</span></span> | <span data-ttu-id="b7940-130">De service dwingt de dagelijkse en de limiet van 15 minuten apart af.</span><span class="sxs-lookup"><span data-stu-id="b7940-130">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="b7940-131">Voor elke limiet wordt in de [Portal een fout weergegeven](advanced-hunting-errors.md) wanneer een query wordt uitgevoerd en de Tenant heeft gekostd via 10% van toegewezen resources.</span><span class="sxs-lookup"><span data-stu-id="b7940-131">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="b7940-132">Query's worden geblokkeerd als de Tenant 100% heeft bereikt tot na de volgende dag of een cyclus van 15 minuten.</span><span class="sxs-lookup"><span data-stu-id="b7940-132">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="b7940-133">Er is een aparte set beperkingen van toepassing op geavanceerde zoekopdrachten die via de API worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b7940-133">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="b7940-134">Meer informatie over geavanceerde jacht-Api's</span><span class="sxs-lookup"><span data-stu-id="b7940-134">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

<span data-ttu-id="b7940-135">Klanten die regelmatig meerdere query's uitvoeren, moeten de optie verbruik bijhouden en [Best practices toepassen](advanced-hunting-best-practices.md) om onderbrekingen te beperken die het gevolg zijn van het overschrijden van deze limieten.</span><span class="sxs-lookup"><span data-stu-id="b7940-135">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b7940-136">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b7940-136">Related topics</span></span>

- [<span data-ttu-id="b7940-137">Best practices voor geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="b7940-137">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b7940-138">Geavanceerde jacht-fouten verwerken</span><span class="sxs-lookup"><span data-stu-id="b7940-138">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="b7940-139">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b7940-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b7940-140">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="b7940-140">Custom detections overview</span></span>](custom-detections-overview.md)
