---
title: AlertInfo-tabel in het geavanceerde schema voor zoeken
description: Meer informatie over het genereren van waarschuwingen in de tabel AlertInfo van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, ernst, category, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS en Azure ATP
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
ms.openlocfilehash: ac1e28987a944a8f7786af4f10a85362f2f92a80
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929968"
---
# <a name="alertinfo"></a><span data-ttu-id="4a5ce-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="4a5ce-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4a5ce-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4a5ce-105">**Applies to:**</span></span>
- <span data-ttu-id="4a5ce-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a5ce-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="4a5ce-107">De tabel in het geavanceerde schema voor zoeken bevat informatie over waarschuwingen van Microsoft Defender voor Eindpunt, Microsoft Defender voor `AlertInfo` Office 365, Microsoft Cloud App-beveiliging en Microsoft Defender voor identiteit. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4a5ce-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="4a5ce-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="4a5ce-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="4a5ce-109">Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="4a5ce-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4a5ce-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="4a5ce-110">Column name</span></span> | <span data-ttu-id="4a5ce-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="4a5ce-111">Data type</span></span> | <span data-ttu-id="4a5ce-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="4a5ce-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4a5ce-113">datetime</span><span class="sxs-lookup"><span data-stu-id="4a5ce-113">datetime</span></span> | <span data-ttu-id="4a5ce-114">Datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="4a5ce-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="4a5ce-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4a5ce-115">string</span></span> | <span data-ttu-id="4a5ce-116">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="4a5ce-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="4a5ce-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4a5ce-117">string</span></span> | <span data-ttu-id="4a5ce-118">Titel van de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="4a5ce-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="4a5ce-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4a5ce-119">string</span></span> | <span data-ttu-id="4a5ce-120">Type bedreigingsindicator of inbreukactiviteit die wordt geïdentificeerd door de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="4a5ce-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="4a5ce-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4a5ce-121">string</span></span> | <span data-ttu-id="4a5ce-122">Geeft de potentiële impact (hoog, gemiddeld of laag) aan van de bedreigingsindicator of inbreukactiviteit die wordt geïdentificeerd in de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="4a5ce-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="4a5ce-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4a5ce-123">string</span></span> | <span data-ttu-id="4a5ce-124">Product of service dat de waarschuwingsgegevens heeft verstrekt</span><span class="sxs-lookup"><span data-stu-id="4a5ce-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="4a5ce-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4a5ce-125">string</span></span> | <span data-ttu-id="4a5ce-126">Detectietechnologie of sensor die de belangrijkste component of activiteit heeft geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="4a5ce-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="4a5ce-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4a5ce-127">string</span></span> | <span data-ttu-id="4a5ce-128">MITRE ATT&CK-technieken die zijn gekoppeld aan de activiteit die de waarschuwing heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="4a5ce-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4a5ce-129">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4a5ce-129">Related topics</span></span>
- [<span data-ttu-id="4a5ce-130">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="4a5ce-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4a5ce-131">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="4a5ce-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4a5ce-132">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="4a5ce-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4a5ce-133">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="4a5ce-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4a5ce-134">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="4a5ce-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4a5ce-135">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="4a5ce-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
