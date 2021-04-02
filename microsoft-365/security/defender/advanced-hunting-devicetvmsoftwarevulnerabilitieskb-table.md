---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over de softwareproblemen die door Threat & Vulnerability Management zijn bijgespoord in de tabel DeviceTvmSoftwareVulnerabilitiesKB van het geavanceerde schema voor de jacht.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 4b5d11788f0914749edaa58b927ef6d4bcc1a3f4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498942"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="8dbad-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="8dbad-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8dbad-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8dbad-105">**Applies to:**</span></span>
- <span data-ttu-id="8dbad-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8dbad-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="8dbad-107">De tabel in het geavanceerde schema voor de jacht bevat de lijst met beveiligingsproblemen `DeviceTvmSoftwareVulnerabilitiesKB` [& kwetsbaarheidsbeheer](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) apparaten beoordeelt voor.</span><span class="sxs-lookup"><span data-stu-id="8dbad-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="8dbad-108">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="8dbad-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="8dbad-109">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="8dbad-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8dbad-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="8dbad-110">Column name</span></span> | <span data-ttu-id="8dbad-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="8dbad-111">Data type</span></span> | <span data-ttu-id="8dbad-112">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="8dbad-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="8dbad-113">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8dbad-113">string</span></span> | <span data-ttu-id="8dbad-114">Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="8dbad-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="8dbad-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8dbad-115">string</span></span> | <span data-ttu-id="8dbad-116">Ernstscore die is toegewezen aan het beveiligingsprobleem onder het Common Vulnerability Scoring System (CVSS)</span><span class="sxs-lookup"><span data-stu-id="8dbad-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="8dbad-117">booleaanse</span><span class="sxs-lookup"><span data-stu-id="8dbad-117">boolean</span></span> | <span data-ttu-id="8dbad-118">Geeft aan of exploitcode voor het beveiligingsprobleem openbaar beschikbaar is</span><span class="sxs-lookup"><span data-stu-id="8dbad-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="8dbad-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8dbad-119">string</span></span> | <span data-ttu-id="8dbad-120">Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap</span><span class="sxs-lookup"><span data-stu-id="8dbad-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="8dbad-121">datetime</span><span class="sxs-lookup"><span data-stu-id="8dbad-121">datetime</span></span> | <span data-ttu-id="8dbad-122">Datum en tijd waarop het item of de gerelateerde metagegevens voor het laatst zijn gewijzigd</span><span class="sxs-lookup"><span data-stu-id="8dbad-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="8dbad-123">datetime</span><span class="sxs-lookup"><span data-stu-id="8dbad-123">datetime</span></span> | <span data-ttu-id="8dbad-124">Datumprobleem is openbaar gemaakt</span><span class="sxs-lookup"><span data-stu-id="8dbad-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="8dbad-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8dbad-125">string</span></span> | <span data-ttu-id="8dbad-126">Beschrijving van kwetsbaarheid en bijbehorende risico's</span><span class="sxs-lookup"><span data-stu-id="8dbad-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="8dbad-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8dbad-127">string</span></span> | <span data-ttu-id="8dbad-128">Lijst met alle softwareproducten die door het beveiligingsprobleem zijn beïnvloed</span><span class="sxs-lookup"><span data-stu-id="8dbad-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8dbad-129">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8dbad-129">Related topics</span></span>

- [<span data-ttu-id="8dbad-130">Proactief op bedreigingen zoeken</span><span class="sxs-lookup"><span data-stu-id="8dbad-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8dbad-131">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="8dbad-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8dbad-132">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="8dbad-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8dbad-133">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="8dbad-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8dbad-134">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="8dbad-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8dbad-135">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="8dbad-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="8dbad-136">Overzicht van threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="8dbad-136">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)