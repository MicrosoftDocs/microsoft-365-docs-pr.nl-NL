---
title: Naamgevingswijzigingen in het Geavanceerde schema voor zoeken van Microsoft 365 Defender
description: Wijzigingen in tabellen en kolommen in het geavanceerde schema voor zoeken bijhouden en bekijken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, data, naming changes, rename, Microsoft Threat Protection
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
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932200"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="1c45a-104">Geavanceerd schema voor zoeken : naamgevingswijzigingen</span><span class="sxs-lookup"><span data-stu-id="1c45a-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1c45a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1c45a-105">**Applies to:**</span></span>
- <span data-ttu-id="1c45a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c45a-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="1c45a-107">Het [geavanceerde schema voor zoeken](advanced-hunting-schema-tables.md) wordt regelmatig bijgewerkt om nieuwe tabellen en kolommen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="1c45a-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="1c45a-108">In sommige gevallen worden bestaande kolomnamen gewijzigd of vervangen om de gebruikerservaring te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="1c45a-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="1c45a-109">Raadpleeg dit artikel voor meer informatie over naamgevingswijzigingen die van invloed kunnen zijn op uw query's.</span><span class="sxs-lookup"><span data-stu-id="1c45a-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="1c45a-110">Naamwijzigingen worden automatisch toegepast op query's die worden opgeslagen in het beveiligingscentrum, inclusief query's die worden gebruikt door aangepaste detectieregels.</span><span class="sxs-lookup"><span data-stu-id="1c45a-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="1c45a-111">U hoeft deze query's niet handmatig bij te werken.</span><span class="sxs-lookup"><span data-stu-id="1c45a-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="1c45a-112">U moet echter de volgende query's bijwerken:</span><span class="sxs-lookup"><span data-stu-id="1c45a-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="1c45a-113">Query's die worden uitgevoerd met de API</span><span class="sxs-lookup"><span data-stu-id="1c45a-113">Queries that are run using the API</span></span>
- <span data-ttu-id="1c45a-114">Query's die ergens anders buiten het beveiligingscentrum worden opgeslagen</span><span class="sxs-lookup"><span data-stu-id="1c45a-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="1c45a-115">December 2020</span><span class="sxs-lookup"><span data-stu-id="1c45a-115">December 2020</span></span>

| <span data-ttu-id="1c45a-116">Tabelnaam</span><span class="sxs-lookup"><span data-stu-id="1c45a-116">Table name</span></span> | <span data-ttu-id="1c45a-117">Oorspronkelijke kolomnaam</span><span class="sxs-lookup"><span data-stu-id="1c45a-117">Original column name</span></span> | <span data-ttu-id="1c45a-118">Nieuwe kolomnaam</span><span class="sxs-lookup"><span data-stu-id="1c45a-118">New column name</span></span> | <span data-ttu-id="1c45a-119">Reden voor wijziging</span><span class="sxs-lookup"><span data-stu-id="1c45a-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="1c45a-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="1c45a-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="1c45a-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="1c45a-121">FinalEmailAction</span></span> | <span data-ttu-id="1c45a-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="1c45a-122">EmailAction</span></span> | <span data-ttu-id="1c45a-123">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="1c45a-123">Customer feedback</span></span> |
| [<span data-ttu-id="1c45a-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="1c45a-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="1c45a-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="1c45a-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="1c45a-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="1c45a-126">EmailActionPolicy</span></span> | <span data-ttu-id="1c45a-127">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="1c45a-127">Customer feedback</span></span> |
| [<span data-ttu-id="1c45a-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="1c45a-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="1c45a-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="1c45a-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="1c45a-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="1c45a-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="1c45a-131">Feedback van klanten</span><span class="sxs-lookup"><span data-stu-id="1c45a-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="1c45a-132">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="1c45a-132">Related topics</span></span>
- [<span data-ttu-id="1c45a-133">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="1c45a-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1c45a-134">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="1c45a-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)