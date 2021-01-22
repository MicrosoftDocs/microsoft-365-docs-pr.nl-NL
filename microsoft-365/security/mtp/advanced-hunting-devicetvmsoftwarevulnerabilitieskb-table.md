---
title: DeviceTvmSoftwareVulnerabilitiesKB table in the advanced hunting schema
description: Meer informatie over de door Threat & Vulnerability Management bij te houden beveiligingsproblemen in de tabel DeviceTvmSoftwareVulnerabilitiesKB van het geavanceerde schema voor zoeken.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKBB
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
ms.openlocfilehash: 00474ac13f88cd9a00ea2ba4a53a6e30ddd664c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931048"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="c2b9b-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="c2b9b-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c2b9b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c2b9b-105">**Applies to:**</span></span>
- <span data-ttu-id="c2b9b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2b9b-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="c2b9b-107">De tabel in het geavanceerde schema voor zoeken bevat de lijst met `DeviceTvmSoftwareVulnerabilitiesKB` [beveiligingsproblemen Bedreiging & Beveiligingsprobleembeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) evalueert apparaten voor.</span><span class="sxs-lookup"><span data-stu-id="c2b9b-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="c2b9b-108">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="c2b9b-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="c2b9b-109">Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="c2b9b-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c2b9b-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="c2b9b-110">Column name</span></span> | <span data-ttu-id="c2b9b-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="c2b9b-111">Data type</span></span> | <span data-ttu-id="c2b9b-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c2b9b-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="c2b9b-113">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c2b9b-113">string</span></span> | <span data-ttu-id="c2b9b-114">Unieke id die is toegewezen aan het beveiligingsprobleem onder het cve-systeem (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="c2b9b-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="c2b9b-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c2b9b-115">string</span></span> | <span data-ttu-id="c2b9b-116">De ernstscore die is toegewezen aan het beveiligingsprobleem onder het Common Vulnerability Scoring System (CVSS)</span><span class="sxs-lookup"><span data-stu-id="c2b9b-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="c2b9b-117">boolean</span><span class="sxs-lookup"><span data-stu-id="c2b9b-117">boolean</span></span> | <span data-ttu-id="c2b9b-118">Hiermee wordt aangegeven of misbruik van code voor het beveiligingsprobleem openbaar beschikbaar is</span><span class="sxs-lookup"><span data-stu-id="c2b9b-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="c2b9b-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c2b9b-119">string</span></span> | <span data-ttu-id="c2b9b-120">Niveau van ernst dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingsland</span><span class="sxs-lookup"><span data-stu-id="c2b9b-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="c2b9b-121">datetime</span><span class="sxs-lookup"><span data-stu-id="c2b9b-121">datetime</span></span> | <span data-ttu-id="c2b9b-122">Datum en tijd waarop het item of de gerelateerde metagegevens het laatst zijn gewijzigd</span><span class="sxs-lookup"><span data-stu-id="c2b9b-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="c2b9b-123">datetime</span><span class="sxs-lookup"><span data-stu-id="c2b9b-123">datetime</span></span> | <span data-ttu-id="c2b9b-124">Datumprobleem is openbaar gemaakt</span><span class="sxs-lookup"><span data-stu-id="c2b9b-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="c2b9b-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c2b9b-125">string</span></span> | <span data-ttu-id="c2b9b-126">Beschrijving van beveiligingsrisico's en bijbehorende risico's</span><span class="sxs-lookup"><span data-stu-id="c2b9b-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="c2b9b-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c2b9b-127">string</span></span> | <span data-ttu-id="c2b9b-128">Lijst met alle softwareproducten die door dit beveiligingsprobleem worden beïnvloed</span><span class="sxs-lookup"><span data-stu-id="c2b9b-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c2b9b-129">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c2b9b-129">Related topics</span></span>

- [<span data-ttu-id="c2b9b-130">Proactief zoeken naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="c2b9b-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c2b9b-131">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="c2b9b-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c2b9b-132">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="c2b9b-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c2b9b-133">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="c2b9b-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c2b9b-134">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="c2b9b-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c2b9b-135">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="c2b9b-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c2b9b-136">Overzicht van risicobeheer & beveiligingsprobleem</span><span class="sxs-lookup"><span data-stu-id="c2b9b-136">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
