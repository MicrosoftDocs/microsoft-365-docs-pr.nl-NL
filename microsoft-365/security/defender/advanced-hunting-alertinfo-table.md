---
title: Tabel AlertInfo in het geavanceerde schema voor de jacht
description: Meer informatie over gebeurtenissen bij het genereren van waarschuwingen in de tabel AlertInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, ernst, category, MITRE, ATT&CK, Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, MCAS en Microsoft Defender for Identity
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
ms.openlocfilehash: 69c9201dbc3458cd4ad09a72f2ea0d7ea3bb2d2a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933695"
---
# <a name="alertinfo"></a><span data-ttu-id="6eb90-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="6eb90-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6eb90-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6eb90-105">**Applies to:**</span></span>
- <span data-ttu-id="6eb90-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6eb90-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="6eb90-107">De tabel in het geavanceerde schema bevat informatie over waarschuwingen van Microsoft Defender voor Eindpunt, Microsoft Defender voor `AlertInfo` Office 365, Microsoft Cloud App Security en Microsoft Defender voor identiteit. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6eb90-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="6eb90-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="6eb90-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="6eb90-109">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="6eb90-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6eb90-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="6eb90-110">Column name</span></span> | <span data-ttu-id="6eb90-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="6eb90-111">Data type</span></span> | <span data-ttu-id="6eb90-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6eb90-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6eb90-113">datetime</span><span class="sxs-lookup"><span data-stu-id="6eb90-113">datetime</span></span> | <span data-ttu-id="6eb90-114">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="6eb90-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="6eb90-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb90-115">string</span></span> | <span data-ttu-id="6eb90-116">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="6eb90-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="6eb90-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb90-117">string</span></span> | <span data-ttu-id="6eb90-118">Titel van de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="6eb90-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="6eb90-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb90-119">string</span></span> | <span data-ttu-id="6eb90-120">Type bedreigingsindicator of inbreukactiviteit die door de waarschuwing is geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="6eb90-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="6eb90-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb90-121">string</span></span> | <span data-ttu-id="6eb90-122">Geeft het mogelijke effect (hoog, gemiddeld of laag) aan van de bedreigingsindicator of inbreukactiviteit die door de waarschuwing is geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="6eb90-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="6eb90-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb90-123">string</span></span> | <span data-ttu-id="6eb90-124">Product of service met de waarschuwingsgegevens</span><span class="sxs-lookup"><span data-stu-id="6eb90-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="6eb90-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb90-125">string</span></span> | <span data-ttu-id="6eb90-126">Detectietechnologie of -sensor die het opmerkelijke onderdeel of de activiteit heeft geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="6eb90-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="6eb90-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb90-127">string</span></span> | <span data-ttu-id="6eb90-128">MITRE ATT&CK-technieken die zijn gekoppeld aan de activiteit die de waarschuwing heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="6eb90-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6eb90-129">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6eb90-129">Related topics</span></span>
- [<span data-ttu-id="6eb90-130">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="6eb90-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6eb90-131">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="6eb90-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6eb90-132">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="6eb90-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6eb90-133">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="6eb90-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6eb90-134">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="6eb90-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6eb90-135">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="6eb90-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
