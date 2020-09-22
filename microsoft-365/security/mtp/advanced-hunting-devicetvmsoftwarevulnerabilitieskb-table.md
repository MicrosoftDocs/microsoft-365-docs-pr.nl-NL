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
ms.openlocfilehash: f486a4187ed904f460d5c2677663a5a6b5513ff5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198131"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="46187-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="46187-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="46187-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="46187-105">**Applies to:**</span></span>
- <span data-ttu-id="46187-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="46187-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="46187-107">De `DeviceTvmSoftwareVulnerabilitiesKB` tabel in het geavanceerde jacht-schema bevat de lijst met problemen die zich voordoen [& risicobeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) apparatuur beoordeelt.</span><span class="sxs-lookup"><span data-stu-id="46187-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="46187-108">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="46187-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="46187-109">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="46187-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="46187-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="46187-110">Column name</span></span> | <span data-ttu-id="46187-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="46187-111">Data type</span></span> | <span data-ttu-id="46187-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="46187-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="46187-113">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="46187-113">string</span></span> | <span data-ttu-id="46187-114">Unieke id die is toegewezen aan het beveiligingsprobleem onder het systeem veelvoorkomende problemen en blootstellingen (CVE)</span><span class="sxs-lookup"><span data-stu-id="46187-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="46187-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="46187-115">string</span></span> | <span data-ttu-id="46187-116">Prioriteitsscore die is toegewezen aan het beveiligingsprobleem onder de informatie over het algemene beveiligingslek (CVSS)</span><span class="sxs-lookup"><span data-stu-id="46187-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="46187-117">Boolean</span><span class="sxs-lookup"><span data-stu-id="46187-117">boolean</span></span> | <span data-ttu-id="46187-118">Geeft aan of de beschikbare code voor het beveiligingslek openbaar verkrijgbaar is</span><span class="sxs-lookup"><span data-stu-id="46187-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="46187-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="46187-119">string</span></span> | <span data-ttu-id="46187-120">Prioriteitsniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-Score en dynamische factoren die worden beïnvloed door de bedreigings niveau liggend</span><span class="sxs-lookup"><span data-stu-id="46187-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="46187-121">tijd</span><span class="sxs-lookup"><span data-stu-id="46187-121">datetime</span></span> | <span data-ttu-id="46187-122">De datum en tijd waarop het item of de bijbehorende metagegevens voor het laatst zijn gewijzigd</span><span class="sxs-lookup"><span data-stu-id="46187-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="46187-123">tijd</span><span class="sxs-lookup"><span data-stu-id="46187-123">datetime</span></span> | <span data-ttu-id="46187-124">De datum waarop het beveiligingslek openbaar is gemaakt</span><span class="sxs-lookup"><span data-stu-id="46187-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="46187-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="46187-125">string</span></span> | <span data-ttu-id="46187-126">Beschrijving van het risico en de gekoppelde Risico's</span><span class="sxs-lookup"><span data-stu-id="46187-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="46187-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="46187-127">string</span></span> | <span data-ttu-id="46187-128">Lijst van alle softwareproducten die worden beïnvloed door het beveiligingslek</span><span class="sxs-lookup"><span data-stu-id="46187-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="46187-129">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="46187-129">Related topics</span></span>

- [<span data-ttu-id="46187-130">Proactief zoeken naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="46187-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="46187-131">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="46187-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="46187-132">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="46187-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="46187-133">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="46187-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="46187-134">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="46187-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="46187-135">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="46187-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="46187-136">Overzicht van Threat & beveiligingslek</span><span class="sxs-lookup"><span data-stu-id="46187-136">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
