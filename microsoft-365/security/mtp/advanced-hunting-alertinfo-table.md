---
title: AlertInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over gebeurtenissen voor het genereren van waarschuwingen in de AlertInfo-tabel van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, AlertInfo, alert, ernst, categorie, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS, en Azure ATP
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
ms.openlocfilehash: a1290ee415073a9cb3948bc4b0cc6bb3ae13285b
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899015"
---
# <a name="alertinfo"></a><span data-ttu-id="5a7d9-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="5a7d9-104">AlertInfo</span></span>

<span data-ttu-id="5a7d9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5a7d9-105">**Applies to:**</span></span>
- <span data-ttu-id="5a7d9-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5a7d9-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="5a7d9-107">De `AlertInfo` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over waarschuwingen van Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security en Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="5a7d9-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="5a7d9-108">Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="5a7d9-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="5a7d9-109">Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.</span><span class="sxs-lookup"><span data-stu-id="5a7d9-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5a7d9-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="5a7d9-110">Column name</span></span> | <span data-ttu-id="5a7d9-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="5a7d9-111">Data type</span></span> | <span data-ttu-id="5a7d9-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="5a7d9-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="5a7d9-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="5a7d9-113">datetime</span></span> | <span data-ttu-id="5a7d9-114">Datum en tijdstip waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="5a7d9-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="5a7d9-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5a7d9-115">string</span></span> | <span data-ttu-id="5a7d9-116">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="5a7d9-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="5a7d9-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5a7d9-117">string</span></span> | <span data-ttu-id="5a7d9-118">Titel van de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="5a7d9-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="5a7d9-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5a7d9-119">string</span></span> | <span data-ttu-id="5a7d9-120">Type bedreigingsindicator of inbreukactiviteit die door de waarschuwing wordt geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="5a7d9-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="5a7d9-121">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5a7d9-121">string</span></span> | <span data-ttu-id="5a7d9-122">Geeft de potentiële impact (hoog, gemiddeld of laag) aan van de dreigingsindicator of inbreukactiviteit die door de waarschuwing wordt geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="5a7d9-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="5a7d9-123">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5a7d9-123">string</span></span> | <span data-ttu-id="5a7d9-124">Product of dienst die de waarschuwingsinformatie heeft verstrekt</span><span class="sxs-lookup"><span data-stu-id="5a7d9-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="5a7d9-125">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5a7d9-125">string</span></span> | <span data-ttu-id="5a7d9-126">Detectietechnologie of sensor die de opmerkelijke component of activiteit identificeerde</span><span class="sxs-lookup"><span data-stu-id="5a7d9-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="5a7d9-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5a7d9-127">string</span></span> | <span data-ttu-id="5a7d9-128">MITRE ATT&CK-technieken die zijn gekoppeld aan de activiteit die de waarschuwing heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="5a7d9-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5a7d9-129">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="5a7d9-129">Related topics</span></span>
- [<span data-ttu-id="5a7d9-130">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="5a7d9-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5a7d9-131">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="5a7d9-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5a7d9-132">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="5a7d9-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5a7d9-133">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="5a7d9-133">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5a7d9-134">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="5a7d9-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5a7d9-135">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="5a7d9-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
