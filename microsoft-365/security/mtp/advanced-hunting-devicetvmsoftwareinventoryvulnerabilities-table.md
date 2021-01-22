---
title: DeviceTvmSoftwareInventoryVulnerabilities table in the advanced hunting schema
description: Meer informatie over de inventaris van software op uw apparaten en de beveiligingslekken in de tabel DeviceTvmSoftwareInventoryVulnerabilities van het geavanceerde schema voor zoeken.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 517f974657032a1a4b7fee5888b0c681ec8063d7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931072"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="c236b-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="c236b-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c236b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c236b-105">**Applies to:**</span></span>
- <span data-ttu-id="c236b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c236b-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="c236b-107">De tabel in het geavanceerde schema voor zoeken bevat de inventaris van `DeviceTvmSoftwareInventoryVulnerabilities` bedreigings- &-beveiligingslekken van software op uw apparaten, evenals bekende beveiligingsproblemen in deze softwareproducten. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="c236b-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="c236b-108">Deze tabel bevat ook informatie over het besturingssysteem, CVE-identiteiten en gegevens over ernst van beveiligingslees.</span><span class="sxs-lookup"><span data-stu-id="c236b-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="c236b-109">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="c236b-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="c236b-110">Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="c236b-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c236b-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="c236b-111">Column name</span></span> | <span data-ttu-id="c236b-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="c236b-112">Data type</span></span> | <span data-ttu-id="c236b-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c236b-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="c236b-114">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c236b-114">string</span></span> | <span data-ttu-id="c236b-115">Unieke id voor de computer in de service</span><span class="sxs-lookup"><span data-stu-id="c236b-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c236b-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c236b-116">string</span></span> | <span data-ttu-id="c236b-117">FQDN (Fully Qualified Domain Name) van de computer</span><span class="sxs-lookup"><span data-stu-id="c236b-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="c236b-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c236b-118">string</span></span> | <span data-ttu-id="c236b-119">Platform van het besturingssysteem dat op de computer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="c236b-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="c236b-120">Dit geeft specifieke besturingssystemen aan, inclusief variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="c236b-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="c236b-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c236b-121">string</span></span> | <span data-ttu-id="c236b-122">Versie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="c236b-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="c236b-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c236b-123">string</span></span> | <span data-ttu-id="c236b-124">Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="c236b-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="c236b-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c236b-125">string</span></span> | <span data-ttu-id="c236b-126">Naam van de softwareleverancier</span><span class="sxs-lookup"><span data-stu-id="c236b-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="c236b-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c236b-127">string</span></span> | <span data-ttu-id="c236b-128">Naam van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="c236b-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="c236b-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c236b-129">string</span></span> | <span data-ttu-id="c236b-130">Versienummer van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="c236b-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="c236b-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c236b-131">string</span></span> | <span data-ttu-id="c236b-132">Unieke id die is toegewezen aan het beveiligingsprobleem onder het cve-systeem (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="c236b-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="c236b-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c236b-133">string</span></span> | <span data-ttu-id="c236b-134">Niveau van ernst dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingsland</span><span class="sxs-lookup"><span data-stu-id="c236b-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="c236b-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c236b-135">Related topics</span></span>

- [<span data-ttu-id="c236b-136">Proactief zoeken naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="c236b-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c236b-137">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="c236b-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c236b-138">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="c236b-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c236b-139">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="c236b-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c236b-140">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="c236b-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c236b-141">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="c236b-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c236b-142">Overzicht van risicobeheer & beveiligingsprobleem</span><span class="sxs-lookup"><span data-stu-id="c236b-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
