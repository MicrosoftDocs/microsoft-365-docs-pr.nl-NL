---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabel in het geavanceerde jacht schema
description: Meer informatie over de beveiligingsproblemen die worden bijgehouden door risico & het beveiligingsbeheer in de tabel DeviceTvmSoftwareVulnerabilitiesKB van het schema Advanced jacht.
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat-jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema, Reference, kusto, Table, Column, Reference,, Table, Column, datatype, Description, Threat &, software
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
ms.openlocfilehash: d4969cdfa2851acc6f94e5e1a903a9b59f73489e
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648919"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="dd083-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="dd083-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

<span data-ttu-id="dd083-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="dd083-105">**Applies to:**</span></span>
- <span data-ttu-id="dd083-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="dd083-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="dd083-107">De `DeviceTvmSoftwareVulnerabilitiesKB` tabel in het geavanceerde jacht-schema bevat de lijst met problemen die zich voordoen [& risicobeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) apparatuur beoordeelt.</span><span class="sxs-lookup"><span data-stu-id="dd083-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="dd083-108">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="dd083-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="dd083-109">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="dd083-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="dd083-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="dd083-110">Column name</span></span> | <span data-ttu-id="dd083-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="dd083-111">Data type</span></span> | <span data-ttu-id="dd083-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="dd083-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="dd083-113">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd083-113">string</span></span> | <span data-ttu-id="dd083-114">Unieke id die is toegewezen aan het beveiligingsprobleem onder het systeem veelvoorkomende problemen en blootstellingen (CVE)</span><span class="sxs-lookup"><span data-stu-id="dd083-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="dd083-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd083-115">string</span></span> | <span data-ttu-id="dd083-116">Prioriteitsscore die is toegewezen aan het beveiligingsprobleem onder de informatie over het algemene beveiligingslek (CVSS)</span><span class="sxs-lookup"><span data-stu-id="dd083-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="dd083-117">Boolean</span><span class="sxs-lookup"><span data-stu-id="dd083-117">boolean</span></span> | <span data-ttu-id="dd083-118">Geeft aan of de beschikbare code voor het beveiligingslek openbaar verkrijgbaar is</span><span class="sxs-lookup"><span data-stu-id="dd083-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="dd083-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd083-119">string</span></span> | <span data-ttu-id="dd083-120">Prioriteitsniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-Score en dynamische factoren die worden beïnvloed door de bedreigings niveau liggend</span><span class="sxs-lookup"><span data-stu-id="dd083-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="dd083-121">tijd</span><span class="sxs-lookup"><span data-stu-id="dd083-121">datetime</span></span> | <span data-ttu-id="dd083-122">De datum en tijd waarop het item of de bijbehorende metagegevens voor het laatst zijn gewijzigd</span><span class="sxs-lookup"><span data-stu-id="dd083-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="dd083-123">tijd</span><span class="sxs-lookup"><span data-stu-id="dd083-123">datetime</span></span> | <span data-ttu-id="dd083-124">De datum waarop het beveiligingslek openbaar is gemaakt</span><span class="sxs-lookup"><span data-stu-id="dd083-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="dd083-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd083-125">string</span></span> | <span data-ttu-id="dd083-126">Beschrijving van het risico en de gekoppelde Risico's</span><span class="sxs-lookup"><span data-stu-id="dd083-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="dd083-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd083-127">string</span></span> | <span data-ttu-id="dd083-128">Lijst van alle softwareproducten die worden beïnvloed door het beveiligingslek</span><span class="sxs-lookup"><span data-stu-id="dd083-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="dd083-129">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="dd083-129">Related topics</span></span>

- [<span data-ttu-id="dd083-130">Proactief zoeken naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="dd083-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="dd083-131">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="dd083-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="dd083-132">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="dd083-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="dd083-133">Jacht op apparaten, e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="dd083-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="dd083-134">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="dd083-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="dd083-135">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="dd083-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="dd083-136">Overzicht van Threat & beveiligingslek</span><span class="sxs-lookup"><span data-stu-id="dd083-136">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
