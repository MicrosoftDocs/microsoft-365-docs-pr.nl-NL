---
title: Wijzigingen aanbrengen in het Microsoft 365 Defender Advanced jacht schema
description: Naam wijzigen en tabellen en kolommen wijzigen in het geavanceerde jacht schema
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, gegevens, naam wijzigen, naam wijzigen, Microsoft Threat Protection
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
ms.openlocfilehash: 0bef5f4abcaf0d57af9c160ff31f859c2536ccd2
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780783"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="59fb5-104">Naamwijzigingen in het schema voor geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="59fb5-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="59fb5-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="59fb5-105">**Applies to:**</span></span>
- <span data-ttu-id="59fb5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59fb5-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="59fb5-107">Het [schema geavanceerde jacht](advanced-hunting-schema-tables.md) wordt regelmatig bijgewerkt om nieuwe tabellen en kolommen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="59fb5-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="59fb5-108">In sommige gevallen worden namen van bestaande kolommen gewijzigd of vervangen ter verbetering van de gebruikerservaring.</span><span class="sxs-lookup"><span data-stu-id="59fb5-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="59fb5-109">Raadpleeg dit artikel om de naamwijzigingen te bekijken die van invloed kunnen zijn op uw query's.</span><span class="sxs-lookup"><span data-stu-id="59fb5-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="59fb5-110">Gewijzigde namen worden automatisch toegepast op query's die zijn opgeslagen in het Beveiligingscentrum, waaronder query's die worden gebruikt door aangepaste detectieregels.</span><span class="sxs-lookup"><span data-stu-id="59fb5-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="59fb5-111">U hoeft deze query's niet handmatig bij te werken.</span><span class="sxs-lookup"><span data-stu-id="59fb5-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="59fb5-112">U moet echter de volgende query's bijwerken:</span><span class="sxs-lookup"><span data-stu-id="59fb5-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="59fb5-113">Query's die worden uitgevoerd met de API</span><span class="sxs-lookup"><span data-stu-id="59fb5-113">Queries that are run using the API</span></span>
- <span data-ttu-id="59fb5-114">Query's die elders buiten het Beveiligingscentrum worden opgeslagen</span><span class="sxs-lookup"><span data-stu-id="59fb5-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="59fb5-115">December 2020</span><span class="sxs-lookup"><span data-stu-id="59fb5-115">December 2020</span></span>

| <span data-ttu-id="59fb5-116">Tabelnaam</span><span class="sxs-lookup"><span data-stu-id="59fb5-116">Table name</span></span> | <span data-ttu-id="59fb5-117">Naam van oorspronkelijke kolom</span><span class="sxs-lookup"><span data-stu-id="59fb5-117">Original column name</span></span> | <span data-ttu-id="59fb5-118">Naam van nieuwe kolom</span><span class="sxs-lookup"><span data-stu-id="59fb5-118">New column name</span></span> | <span data-ttu-id="59fb5-119">Reden voor wijziging</span><span class="sxs-lookup"><span data-stu-id="59fb5-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="59fb5-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="59fb5-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="59fb5-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="59fb5-121">FinalEmailAction</span></span> | <span data-ttu-id="59fb5-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="59fb5-122">EmailAction</span></span> | <span data-ttu-id="59fb5-123">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="59fb5-123">Customer feedback</span></span> |
| [<span data-ttu-id="59fb5-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="59fb5-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="59fb5-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="59fb5-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="59fb5-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="59fb5-126">EmailActionPolicy</span></span> | <span data-ttu-id="59fb5-127">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="59fb5-127">Customer feedback</span></span> |
| [<span data-ttu-id="59fb5-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="59fb5-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="59fb5-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="59fb5-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="59fb5-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="59fb5-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="59fb5-131">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="59fb5-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="59fb5-132">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="59fb5-132">Related topics</span></span>
- [<span data-ttu-id="59fb5-133">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="59fb5-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="59fb5-134">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="59fb5-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)