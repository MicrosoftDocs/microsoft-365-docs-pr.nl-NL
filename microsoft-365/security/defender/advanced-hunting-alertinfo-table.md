---
title: Tabel AlertInfo in het geavanceerde schema voor de jacht
description: Meer informatie over gebeurtenissen bij het genereren van waarschuwingen in de tabel AlertInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, ernst, category, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS en Azure ATP
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
ms.openlocfilehash: 1386830a4b3e05009b19a7d0e3a4ea62ce3321f2
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499829"
---
# <a name="alertinfo"></a><span data-ttu-id="aae36-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="aae36-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="aae36-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="aae36-105">**Applies to:**</span></span>
- <span data-ttu-id="aae36-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aae36-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="aae36-107">De tabel in het geavanceerde schema bevat informatie over waarschuwingen van Microsoft Defender voor Eindpunt, Microsoft Defender voor `AlertInfo` Office 365, Microsoft Cloud App Security en Microsoft Defender voor identiteit. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="aae36-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="aae36-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="aae36-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="aae36-109">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="aae36-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="aae36-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="aae36-110">Column name</span></span> | <span data-ttu-id="aae36-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="aae36-111">Data type</span></span> | <span data-ttu-id="aae36-112">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="aae36-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="aae36-113">datetime</span><span class="sxs-lookup"><span data-stu-id="aae36-113">datetime</span></span> | <span data-ttu-id="aae36-114">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="aae36-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="aae36-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aae36-115">string</span></span> | <span data-ttu-id="aae36-116">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="aae36-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="aae36-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aae36-117">string</span></span> | <span data-ttu-id="aae36-118">Titel van de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="aae36-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="aae36-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aae36-119">string</span></span> | <span data-ttu-id="aae36-120">Type bedreigingsindicator of inbreukactiviteit die door de waarschuwing is geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="aae36-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="aae36-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aae36-121">string</span></span> | <span data-ttu-id="aae36-122">Geeft het mogelijke effect (hoog, gemiddeld of laag) aan van de bedreigingsindicator of inbreukactiviteit die door de waarschuwing is geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="aae36-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="aae36-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aae36-123">string</span></span> | <span data-ttu-id="aae36-124">Product of service met de waarschuwingsgegevens</span><span class="sxs-lookup"><span data-stu-id="aae36-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="aae36-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aae36-125">string</span></span> | <span data-ttu-id="aae36-126">Detectietechnologie of -sensor die het opmerkelijke onderdeel of de activiteit heeft geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="aae36-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="aae36-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aae36-127">string</span></span> | <span data-ttu-id="aae36-128">MITRE ATT&CK-technieken die zijn gekoppeld aan de activiteit die de waarschuwing heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="aae36-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="aae36-129">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="aae36-129">Related topics</span></span>
- [<span data-ttu-id="aae36-130">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="aae36-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="aae36-131">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="aae36-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="aae36-132">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="aae36-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="aae36-133">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="aae36-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="aae36-134">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="aae36-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="aae36-135">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="aae36-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
