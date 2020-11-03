---
title: AlertInfo-tabel in het geavanceerde jacht schema
description: Meer informatie over gebeurtenissen voor het genereren van waarschuwingen in de tabel AlertInfo van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema Reference, kusto, Table, Column, datatype, Description, AlertInfo, alert,, categorie, Mitre,&ATT, de versie van Microsoft-apps, MDATP, Office 365, MCAS
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
ms.openlocfilehash: 7672d974666a381a48da15e0917a46c97df88895
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847666"
---
# <a name="alertinfo"></a><span data-ttu-id="095a9-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="095a9-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="095a9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="095a9-105">**Applies to:**</span></span>
- <span data-ttu-id="095a9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="095a9-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="095a9-107">De `AlertInfo` tabel in het [Geavanceerde bejachts](advanced-hunting-overview.md) schema bevat informatie over waarschuwingen van Microsoft Defender for endpoints, Microsoft defender for Office 365, Microsoft Cloud app Security en Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="095a9-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="095a9-108">Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="095a9-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="095a9-109">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="095a9-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="095a9-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="095a9-110">Column name</span></span> | <span data-ttu-id="095a9-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="095a9-111">Data type</span></span> | <span data-ttu-id="095a9-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="095a9-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="095a9-113">tijd</span><span class="sxs-lookup"><span data-stu-id="095a9-113">datetime</span></span> | <span data-ttu-id="095a9-114">De datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="095a9-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="095a9-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="095a9-115">string</span></span> | <span data-ttu-id="095a9-116">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="095a9-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="095a9-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="095a9-117">string</span></span> | <span data-ttu-id="095a9-118">Titel van de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="095a9-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="095a9-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="095a9-119">string</span></span> | <span data-ttu-id="095a9-120">Type bedreigings indicator of schendings activiteit aangegeven door de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="095a9-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="095a9-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="095a9-121">string</span></span> | <span data-ttu-id="095a9-122">Hiermee wordt de potentiële impact (hoog, normaal of laag) aangegeven van de bedreigings indicator of de melding over de overtreding, aangegeven door de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="095a9-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="095a9-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="095a9-123">string</span></span> | <span data-ttu-id="095a9-124">Het product of de service die de waarschuwingsinformatie heeft verstrekt</span><span class="sxs-lookup"><span data-stu-id="095a9-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="095a9-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="095a9-125">string</span></span> | <span data-ttu-id="095a9-126">Detectie-technologie of-sensor waarmee de opmerkelijke component of activiteit wordt aangegeven</span><span class="sxs-lookup"><span data-stu-id="095a9-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="095a9-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="095a9-127">string</span></span> | <span data-ttu-id="095a9-128">MITRE ATT&verzonken technieken die zijn gekoppeld aan de activiteit waarmee de waarschuwing is geactiveerd</span><span class="sxs-lookup"><span data-stu-id="095a9-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="095a9-129">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="095a9-129">Related topics</span></span>
- [<span data-ttu-id="095a9-130">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="095a9-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="095a9-131">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="095a9-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="095a9-132">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="095a9-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="095a9-133">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="095a9-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="095a9-134">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="095a9-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="095a9-135">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="095a9-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
