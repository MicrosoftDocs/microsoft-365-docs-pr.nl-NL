---
title: DeviceTvmSoftwareInventoryVulnerabilities-tabel in het geavanceerde jacht schema
description: Meer informatie over de inventarisatie van de software op uw apparaten en de zwakke plekken in de tabel DeviceTvmSoftwareInventoryVulnerabilities van het schema geavanceerde jacht.
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat-jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema Reference, kusto, tabel, Column, datatype, beschrijving, beveiliging & beveiligingslek, TVM, Apparaatbeheer, software, inventarisatie,
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
ms.openlocfilehash: 4571b5bb22ef8aa800607f81cc00f15c28172548
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429852"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="c9bc3-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="c9bc3-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c9bc3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c9bc3-105">**Applies to:**</span></span>
- <span data-ttu-id="c9bc3-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c9bc3-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="c9bc3-107">De `DeviceTvmSoftwareInventoryVulnerabilities` tabel in het geavanceerde jacht-schema bevat de bedreiging voor de & bedreiging van de software voor het [beveiligingsbeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) van de software op uw apparaten en bekende beveiligingsproblemen in deze softwareproducten.</span><span class="sxs-lookup"><span data-stu-id="c9bc3-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="c9bc3-108">Deze tabel bevat ook informatie over het besturingssysteem, CVE-Id's en informatie over het beveiligingsniveau.</span><span class="sxs-lookup"><span data-stu-id="c9bc3-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="c9bc3-109">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="c9bc3-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="c9bc3-110">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="c9bc3-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c9bc3-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="c9bc3-111">Column name</span></span> | <span data-ttu-id="c9bc3-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="c9bc3-112">Data type</span></span> | <span data-ttu-id="c9bc3-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c9bc3-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="c9bc3-114">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c9bc3-114">string</span></span> | <span data-ttu-id="c9bc3-115">Unieke id voor de computer in de service</span><span class="sxs-lookup"><span data-stu-id="c9bc3-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c9bc3-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c9bc3-116">string</span></span> | <span data-ttu-id="c9bc3-117">FQDN-naam (Fully Qualified Domain Name) van de computer</span><span class="sxs-lookup"><span data-stu-id="c9bc3-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="c9bc3-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c9bc3-118">string</span></span> | <span data-ttu-id="c9bc3-119">Platform van het besturingssysteem dat op de computer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="c9bc3-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="c9bc3-120">Dit geeft specifieke besturingssystemen aan, met inbegrip van variaties in dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="c9bc3-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="c9bc3-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c9bc3-121">string</span></span> | <span data-ttu-id="c9bc3-122">Versie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="c9bc3-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="c9bc3-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c9bc3-123">string</span></span> | <span data-ttu-id="c9bc3-124">Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="c9bc3-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="c9bc3-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c9bc3-125">string</span></span> | <span data-ttu-id="c9bc3-126">Naam van de softwareleverancier</span><span class="sxs-lookup"><span data-stu-id="c9bc3-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="c9bc3-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c9bc3-127">string</span></span> | <span data-ttu-id="c9bc3-128">Naam van het SOFTWAREPRODUCT</span><span class="sxs-lookup"><span data-stu-id="c9bc3-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="c9bc3-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c9bc3-129">string</span></span> | <span data-ttu-id="c9bc3-130">Versienummer van het SOFTWAREPRODUCT</span><span class="sxs-lookup"><span data-stu-id="c9bc3-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="c9bc3-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c9bc3-131">string</span></span> | <span data-ttu-id="c9bc3-132">Unieke id die is toegewezen aan het beveiligingsprobleem onder het systeem veelvoorkomende problemen en blootstellingen (CVE)</span><span class="sxs-lookup"><span data-stu-id="c9bc3-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="c9bc3-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c9bc3-133">string</span></span> | <span data-ttu-id="c9bc3-134">Prioriteitsniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-Score en dynamische factoren die worden beïnvloed door de bedreigings niveau liggend</span><span class="sxs-lookup"><span data-stu-id="c9bc3-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="c9bc3-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c9bc3-135">Related topics</span></span>

- [<span data-ttu-id="c9bc3-136">Proactief zoeken naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="c9bc3-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c9bc3-137">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="c9bc3-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c9bc3-138">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="c9bc3-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c9bc3-139">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="c9bc3-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c9bc3-140">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="c9bc3-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c9bc3-141">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="c9bc3-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c9bc3-142">Overzicht van Threat & beveiligingslek</span><span class="sxs-lookup"><span data-stu-id="c9bc3-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
