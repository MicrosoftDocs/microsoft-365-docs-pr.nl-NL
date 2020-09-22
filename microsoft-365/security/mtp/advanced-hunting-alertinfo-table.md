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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 61efedf8323833b65a5f0b0b857cd83a5c5b085a
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198257"
---
# <a name="alertinfo"></a><span data-ttu-id="b0f7a-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="b0f7a-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b0f7a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b0f7a-105">**Applies to:**</span></span>
- <span data-ttu-id="b0f7a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b0f7a-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="b0f7a-107">De `AlertInfo` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat informatie over waarschuwingen uit Microsoft Defender atp, Office 365 ATP, Microsoft Cloud app Security en Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="b0f7a-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="b0f7a-108">Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="b0f7a-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="b0f7a-109">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="b0f7a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b0f7a-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="b0f7a-110">Column name</span></span> | <span data-ttu-id="b0f7a-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="b0f7a-111">Data type</span></span> | <span data-ttu-id="b0f7a-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b0f7a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b0f7a-113">tijd</span><span class="sxs-lookup"><span data-stu-id="b0f7a-113">datetime</span></span> | <span data-ttu-id="b0f7a-114">De datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="b0f7a-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="b0f7a-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b0f7a-115">string</span></span> | <span data-ttu-id="b0f7a-116">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="b0f7a-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="b0f7a-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b0f7a-117">string</span></span> | <span data-ttu-id="b0f7a-118">Titel van de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="b0f7a-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="b0f7a-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b0f7a-119">string</span></span> | <span data-ttu-id="b0f7a-120">Type bedreigings indicator of schendings activiteit aangegeven door de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="b0f7a-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="b0f7a-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b0f7a-121">string</span></span> | <span data-ttu-id="b0f7a-122">Hiermee wordt de potentiële impact (hoog, normaal of laag) aangegeven van de bedreigings indicator of de melding over de overtreding, aangegeven door de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="b0f7a-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="b0f7a-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b0f7a-123">string</span></span> | <span data-ttu-id="b0f7a-124">Het product of de service die de waarschuwingsinformatie heeft verstrekt</span><span class="sxs-lookup"><span data-stu-id="b0f7a-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="b0f7a-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b0f7a-125">string</span></span> | <span data-ttu-id="b0f7a-126">Detectie-technologie of-sensor waarmee de opmerkelijke component of activiteit wordt aangegeven</span><span class="sxs-lookup"><span data-stu-id="b0f7a-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="b0f7a-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b0f7a-127">string</span></span> | <span data-ttu-id="b0f7a-128">MITRE ATT&verzonken technieken die zijn gekoppeld aan de activiteit waarmee de waarschuwing is geactiveerd</span><span class="sxs-lookup"><span data-stu-id="b0f7a-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b0f7a-129">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b0f7a-129">Related topics</span></span>
- [<span data-ttu-id="b0f7a-130">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b0f7a-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b0f7a-131">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="b0f7a-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b0f7a-132">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="b0f7a-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b0f7a-133">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="b0f7a-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b0f7a-134">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="b0f7a-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b0f7a-135">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="b0f7a-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
