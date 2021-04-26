---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over de softwareproblemen die door Threat & Vulnerability Management zijn bijgespoord in de tabel DeviceTvmSoftwareVulnerabilitiesKB van het geavanceerde schema voor de jacht.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema, reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: afcd6bcd81e1a8635be9ced766c533ea4195334f
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023795"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="bcebc-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="bcebc-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bcebc-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bcebc-105">**Applies to:**</span></span>
- <span data-ttu-id="bcebc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bcebc-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="bcebc-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="bcebc-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="bcebc-108">De tabel in het geavanceerde schema voor de jacht bevat de lijst met beveiligingsproblemen `DeviceTvmSoftwareVulnerabilitiesKB` [& kwetsbaarheidsbeheer](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) apparaten beoordeelt voor.</span><span class="sxs-lookup"><span data-stu-id="bcebc-108">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="bcebc-109">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="bcebc-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="bcebc-110">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="bcebc-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="bcebc-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="bcebc-111">Column name</span></span> | <span data-ttu-id="bcebc-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="bcebc-112">Data type</span></span> | <span data-ttu-id="bcebc-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="bcebc-113">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="bcebc-114">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bcebc-114">string</span></span> | <span data-ttu-id="bcebc-115">Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="bcebc-115">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="bcebc-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bcebc-116">string</span></span> | <span data-ttu-id="bcebc-117">Ernstscore die is toegewezen aan het beveiligingsprobleem onder het Common Vulnerability Scoring System (CVSS)</span><span class="sxs-lookup"><span data-stu-id="bcebc-117">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="bcebc-118">booleaanse</span><span class="sxs-lookup"><span data-stu-id="bcebc-118">boolean</span></span> | <span data-ttu-id="bcebc-119">Geeft aan of exploitcode voor het beveiligingsprobleem openbaar beschikbaar is</span><span class="sxs-lookup"><span data-stu-id="bcebc-119">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="bcebc-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bcebc-120">string</span></span> | <span data-ttu-id="bcebc-121">Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap</span><span class="sxs-lookup"><span data-stu-id="bcebc-121">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="bcebc-122">datetime</span><span class="sxs-lookup"><span data-stu-id="bcebc-122">datetime</span></span> | <span data-ttu-id="bcebc-123">Datum en tijd waarop het item of de gerelateerde metagegevens voor het laatst zijn gewijzigd</span><span class="sxs-lookup"><span data-stu-id="bcebc-123">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="bcebc-124">datetime</span><span class="sxs-lookup"><span data-stu-id="bcebc-124">datetime</span></span> | <span data-ttu-id="bcebc-125">Datumprobleem is openbaar gemaakt</span><span class="sxs-lookup"><span data-stu-id="bcebc-125">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="bcebc-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bcebc-126">string</span></span> | <span data-ttu-id="bcebc-127">Beschrijving van kwetsbaarheid en bijbehorende risico's</span><span class="sxs-lookup"><span data-stu-id="bcebc-127">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="bcebc-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bcebc-128">string</span></span> | <span data-ttu-id="bcebc-129">Lijst met alle softwareproducten die door het beveiligingsprobleem zijn beïnvloed</span><span class="sxs-lookup"><span data-stu-id="bcebc-129">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="bcebc-130">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="bcebc-130">Related topics</span></span>

- [<span data-ttu-id="bcebc-131">Proactief op bedreigingen zoeken</span><span class="sxs-lookup"><span data-stu-id="bcebc-131">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bcebc-132">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="bcebc-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bcebc-133">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="bcebc-133">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="bcebc-134">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="bcebc-134">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="bcebc-135">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="bcebc-135">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bcebc-136">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="bcebc-136">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="bcebc-137">Overzicht van threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="bcebc-137">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)