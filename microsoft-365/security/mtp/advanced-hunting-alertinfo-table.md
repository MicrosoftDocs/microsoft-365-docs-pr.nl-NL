---
title: Tabel AlertInfo in het geavanceerde jachtschema
description: Meer informatie over gebeurtenissen voor het genereren van waarschuwingen in de tabel AlertInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, AlertInfo, waarschuwing, ernst, categorie, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS en Azure ATP
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
ms.openlocfilehash: e4d7ec213a4b4d1108c06784fb5e6675c79429c1
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929514"
---
# <a name="alertinfo"></a><span data-ttu-id="a65b6-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="a65b6-104">AlertInfo</span></span>

<span data-ttu-id="a65b6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a65b6-105">**Applies to:**</span></span>
- <span data-ttu-id="a65b6-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="a65b6-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="a65b6-107">De `AlertInfo` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over waarschuwingen van Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security en Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="a65b6-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="a65b6-108">Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="a65b6-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="a65b6-109">Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a65b6-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a65b6-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="a65b6-110">Column name</span></span> | <span data-ttu-id="a65b6-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="a65b6-111">Data type</span></span> | <span data-ttu-id="a65b6-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="a65b6-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a65b6-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="a65b6-113">datetime</span></span> | <span data-ttu-id="a65b6-114">Datum en tijdstip waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="a65b6-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="a65b6-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a65b6-115">string</span></span> | <span data-ttu-id="a65b6-116">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="a65b6-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="a65b6-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a65b6-117">string</span></span> | <span data-ttu-id="a65b6-118">Titel van de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="a65b6-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="a65b6-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a65b6-119">string</span></span> | <span data-ttu-id="a65b6-120">Type bedreigingsindicator of inbreukactiviteit die door de waarschuwing wordt geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="a65b6-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="a65b6-121">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a65b6-121">string</span></span> | <span data-ttu-id="a65b6-122">Geeft de potentiële impact (hoog, gemiddeld of laag) van de bedreigingsindicator of inbreukactiviteit aan die door de waarschuwing wordt geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="a65b6-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="a65b6-123">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a65b6-123">string</span></span> | <span data-ttu-id="a65b6-124">Product of dienst die de waarschuwingsinformatie heeft verstrekt</span><span class="sxs-lookup"><span data-stu-id="a65b6-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="a65b6-125">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a65b6-125">string</span></span> | <span data-ttu-id="a65b6-126">Detectietechnologie of sensor die de opmerkelijke component of activiteit identificeerde</span><span class="sxs-lookup"><span data-stu-id="a65b6-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="a65b6-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a65b6-127">string</span></span> | <span data-ttu-id="a65b6-128">MITRE ATT&CK-technieken die verband houden met de activiteit die de waarschuwing heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="a65b6-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a65b6-129">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a65b6-129">Related topics</span></span>
- [<span data-ttu-id="a65b6-130">Proactief op zoek naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="a65b6-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a65b6-131">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="a65b6-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a65b6-132">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="a65b6-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a65b6-133">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="a65b6-133">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a65b6-134">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="a65b6-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a65b6-135">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="a65b6-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
