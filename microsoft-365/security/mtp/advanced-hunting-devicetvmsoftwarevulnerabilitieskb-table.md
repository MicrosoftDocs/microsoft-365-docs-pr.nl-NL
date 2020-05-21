---
title: DeviceTvmSoftwareVulnerabilitiesKB tabel in de geavanceerde jacht schema
description: Meer informatie over de software kwetsbaarheden bijgehouden door Threat & Vulnerability Management in de DeviceTvmSoftwareVulnerabilitiesKB tabel van de geavanceerde jacht schema.
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoeken, query, telemetrie, schema, referentie, kusto, tabel, kolom, gegevenstype, beschrijving, bedreiging & kwetsbaarheidsbeheer, TVM, apparaatbeheer, software, inventaris, kwetsbaarheden, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 378ffee34a24af225b1b6deebd7cc514c62e1926
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327950"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="f511e-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="f511e-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

<span data-ttu-id="f511e-105">**Geldt voor:**</span><span class="sxs-lookup"><span data-stu-id="f511e-105">**Applies to:**</span></span>
- <span data-ttu-id="f511e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f511e-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="f511e-107">De `DeviceTvmSoftwareVulnerabilitiesKB` tabel in het geavanceerde jachtschema bevat de lijst met kwetsbaarheden Threat & Vulnerability [Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) beoordeelt apparaten voor.</span><span class="sxs-lookup"><span data-stu-id="f511e-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="f511e-108">Gebruik deze verwijzing om query's te construeren die informatie uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="f511e-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="f511e-109">Voor informatie over andere tabellen in de geavanceerde jacht schema, zie [de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f511e-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f511e-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="f511e-110">Column name</span></span> | <span data-ttu-id="f511e-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="f511e-111">Data type</span></span> | <span data-ttu-id="f511e-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f511e-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="f511e-113">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f511e-113">string</span></span> | <span data-ttu-id="f511e-114">Unieke id die is toegewezen aan het beveiligingslek onder het CVE-systeem (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="f511e-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="f511e-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f511e-115">string</span></span> | <span data-ttu-id="f511e-116">Ernstscore toegewezen aan het beveiligingslek onder het Common Vulnerability Scoring System (CVSS)</span><span class="sxs-lookup"><span data-stu-id="f511e-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="f511e-117">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="f511e-117">boolean</span></span> | <span data-ttu-id="f511e-118">Geeft aan of exploitcode voor het beveiligingslek openbaar beschikbaar is</span><span class="sxs-lookup"><span data-stu-id="f511e-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="f511e-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f511e-119">string</span></span> | <span data-ttu-id="f511e-120">Ernstniveau toegewezen aan het beveiligingslek op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het dreigingslandschap</span><span class="sxs-lookup"><span data-stu-id="f511e-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="f511e-121">Datetime</span><span class="sxs-lookup"><span data-stu-id="f511e-121">datetime</span></span> | <span data-ttu-id="f511e-122">Datum en tijd dat het item of gerelateerde metagegevens voor het laatst zijn gewijzigd</span><span class="sxs-lookup"><span data-stu-id="f511e-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="f511e-123">Datetime</span><span class="sxs-lookup"><span data-stu-id="f511e-123">datetime</span></span> | <span data-ttu-id="f511e-124">Datum kwetsbaarheid werd openbaar gemaakt</span><span class="sxs-lookup"><span data-stu-id="f511e-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="f511e-125">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f511e-125">string</span></span> | <span data-ttu-id="f511e-126">Beschrijving van kwetsbaarheid en bijbehorende risico's</span><span class="sxs-lookup"><span data-stu-id="f511e-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="f511e-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f511e-127">string</span></span> | <span data-ttu-id="f511e-128">Lijst van alle softwareproducten die door het beveiligingslek zijn getroffen</span><span class="sxs-lookup"><span data-stu-id="f511e-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f511e-129">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f511e-129">Related topics</span></span>

- [<span data-ttu-id="f511e-130">Proactief op zoek naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="f511e-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f511e-131">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="f511e-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f511e-132">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="f511e-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f511e-133">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="f511e-133">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f511e-134">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="f511e-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f511e-135">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="f511e-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="f511e-136">Overzicht van Threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="f511e-136">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
