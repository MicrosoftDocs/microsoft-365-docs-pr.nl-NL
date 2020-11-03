---
title: Geavanceerde jacht-quota's en gebruiks parameters in Microsoft 365 Defender
description: Meer informatie over diverse quota's en gebruiks parameters (Service limieten) waarmee de Advanced USMT-service kan reageren
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema, kusto, processorlimiet, query limiet, bronnen, maximum resultaten, quota, parameters, toewijzing
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: bab63d9e5939f87f6a1edbf62d256b82552e4fe9
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847366"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="854ca-104">Geavanceerde jacht-quota's en gebruiks parameters</span><span class="sxs-lookup"><span data-stu-id="854ca-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="854ca-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="854ca-105">**Applies to:**</span></span>
- <span data-ttu-id="854ca-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="854ca-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="854ca-107">Als u de service wilt blijven gebruiken, stelt u in geavanceerde jacht diverse quota's en gebruiks parameters in (ook wel ' service limieten ' genoemd).</span><span class="sxs-lookup"><span data-stu-id="854ca-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="854ca-108">Deze quota's en parameters zijn van toepassing op handmatig en door [aangepaste detectieregels](custom-detection-rules.md)worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="854ca-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="854ca-109">Klanten die regelmatig meerdere query's uitvoeren, moeten verbruik bijhouden en [Best practices toepassen](advanced-hunting-best-practices.md) om onderbrekingen te beperken.</span><span class="sxs-lookup"><span data-stu-id="854ca-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="854ca-110">Raadpleeg de volgende tabel voor meer informatie over bestaande quota's en gebruiks parameters.</span><span class="sxs-lookup"><span data-stu-id="854ca-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="854ca-111">Target of parameter</span><span class="sxs-lookup"><span data-stu-id="854ca-111">Quota or parameter</span></span> | <span data-ttu-id="854ca-112">Grootte</span><span class="sxs-lookup"><span data-stu-id="854ca-112">Size</span></span> | <span data-ttu-id="854ca-113">Vernieuwingscyclus</span><span class="sxs-lookup"><span data-stu-id="854ca-113">Refresh cycle</span></span> | <span data-ttu-id="854ca-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="854ca-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="854ca-115">Gegevensbereik</span><span class="sxs-lookup"><span data-stu-id="854ca-115">Data range</span></span> | <span data-ttu-id="854ca-116">30 dagen</span><span class="sxs-lookup"><span data-stu-id="854ca-116">30 days</span></span> | <span data-ttu-id="854ca-117">Elke query</span><span class="sxs-lookup"><span data-stu-id="854ca-117">Every query</span></span> | <span data-ttu-id="854ca-118">Met elke query kunnen gegevens worden opgezocht van de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="854ca-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="854ca-119">Resultatenset</span><span class="sxs-lookup"><span data-stu-id="854ca-119">Result set</span></span> | <span data-ttu-id="854ca-120">rijen in 10.000</span><span class="sxs-lookup"><span data-stu-id="854ca-120">10,000 rows</span></span> | <span data-ttu-id="854ca-121">Elke query</span><span class="sxs-lookup"><span data-stu-id="854ca-121">Every query</span></span> | <span data-ttu-id="854ca-122">Elke query kan resulteren in 10.000-records.</span><span class="sxs-lookup"><span data-stu-id="854ca-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="854ca-123">Waar</span><span class="sxs-lookup"><span data-stu-id="854ca-123">Timeout</span></span> | <span data-ttu-id="854ca-124">10 minuten</span><span class="sxs-lookup"><span data-stu-id="854ca-124">10 minutes</span></span> | <span data-ttu-id="854ca-125">Elke query</span><span class="sxs-lookup"><span data-stu-id="854ca-125">Every query</span></span> | <span data-ttu-id="854ca-126">Een query kan maximaal 10 minuten worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="854ca-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="854ca-127">Als de service niet binnen 10 minuten wordt voltooid, wordt er een fout weergegeven.</span><span class="sxs-lookup"><span data-stu-id="854ca-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="854ca-128">CPU-resources</span><span class="sxs-lookup"><span data-stu-id="854ca-128">CPU resources</span></span> | <span data-ttu-id="854ca-129">Gebaseerd op Tenant grootte</span><span class="sxs-lookup"><span data-stu-id="854ca-129">Based on tenant size</span></span> | <span data-ttu-id="854ca-130">-Op het uur en vervolgens elke 15 minuten</span><span class="sxs-lookup"><span data-stu-id="854ca-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="854ca-131">-Dagelijks voor 12 middernacht</span><span class="sxs-lookup"><span data-stu-id="854ca-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="854ca-132">De service belegt de dagelijkse en de quota voor 15 minuten apart af.</span><span class="sxs-lookup"><span data-stu-id="854ca-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="854ca-133">Voor elk quotum wordt in de [Portal een fout weergegeven](advanced-hunting-errors.md) wanneer een query wordt uitgevoerd en de Tenant is geverbruikt op 10% van toegewezen resources.</span><span class="sxs-lookup"><span data-stu-id="854ca-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="854ca-134">Query's worden geblokkeerd als de Tenant 100% heeft bereikt tot na de volgende dag of een cyclus van 15 minuten.</span><span class="sxs-lookup"><span data-stu-id="854ca-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="854ca-135">Er gelden een aparte set quota's en parameters voor geavanceerde zoekopdrachten die via de API worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="854ca-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="854ca-136">Meer informatie over geavanceerde jacht-Api's</span><span class="sxs-lookup"><span data-stu-id="854ca-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="854ca-137">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="854ca-137">Related topics</span></span>

- [<span data-ttu-id="854ca-138">Best practices voor geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="854ca-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="854ca-139">Geavanceerde jacht-fouten verwerken</span><span class="sxs-lookup"><span data-stu-id="854ca-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="854ca-140">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="854ca-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="854ca-141">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="854ca-141">Custom detections overview</span></span>](custom-detections-overview.md)