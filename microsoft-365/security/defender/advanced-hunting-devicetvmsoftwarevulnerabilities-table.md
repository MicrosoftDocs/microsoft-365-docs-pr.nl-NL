---
title: DeviceTvmSoftwareVulnerabilities table in the advanced hunting schema
description: Meer informatie over de softwareproblemen die zijn gevonden op apparaten en de lijst met beschikbare beveiligingsupdates die elk beveiligingsprobleem verhelpen in de tabel DeviceTvmSoftwareVulnerabilities van het geavanceerde schema voor het zoeken.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 24da8f556fe9f8a3b8172afe87ea9a87e4522d44
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934823"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="0eb67-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="0eb67-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0eb67-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0eb67-105">**Applies to:**</span></span>
- <span data-ttu-id="0eb67-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0eb67-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="0eb67-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="0eb67-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="0eb67-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="0eb67-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="0eb67-109">De `DeviceTvmSoftwareVulnerabilities` tabel in het geavanceerde schema bevat de lijst Threat & Vulnerability [Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) met beveiligingslekken in geïnstalleerde softwareproducten.</span><span class="sxs-lookup"><span data-stu-id="0eb67-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="0eb67-110">Deze tabel bevat ook informatie over het besturingssysteem, CVE-ID's en ernst van de kwetsbaarheid.</span><span class="sxs-lookup"><span data-stu-id="0eb67-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="0eb67-111">U kunt deze tabel bijvoorbeeld gebruiken om te zoeken naar gebeurtenissen met apparaten met ernstige beveiligingsproblemen in hun software.</span><span class="sxs-lookup"><span data-stu-id="0eb67-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="0eb67-112">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="0eb67-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="0eb67-113">De `DeviceTvmSoftwareInventory` tabel en de tabellen zijn `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` vervangen.</span><span class="sxs-lookup"><span data-stu-id="0eb67-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="0eb67-114">De eerste twee tabellen bevatten meer kolommen die u kunt gebruiken om uw vulnerablity-beheeractiviteiten te informeren of om te zoeken naar kwetsbare apparaten.</span><span class="sxs-lookup"><span data-stu-id="0eb67-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="0eb67-115">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="0eb67-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0eb67-116">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="0eb67-116">Column name</span></span> | <span data-ttu-id="0eb67-117">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="0eb67-117">Data type</span></span> | <span data-ttu-id="0eb67-118">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="0eb67-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="0eb67-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0eb67-119">string</span></span> | <span data-ttu-id="0eb67-120">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="0eb67-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="0eb67-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0eb67-121">string</span></span> | <span data-ttu-id="0eb67-122">Volledig gekwalificeerde domeinnaam (FQDN) van de computer</span><span class="sxs-lookup"><span data-stu-id="0eb67-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="0eb67-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0eb67-123">string</span></span> | <span data-ttu-id="0eb67-124">Platform van het besturingssysteem dat op de computer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0eb67-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="0eb67-125">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="0eb67-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="0eb67-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0eb67-126">string</span></span> | <span data-ttu-id="0eb67-127">Versie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="0eb67-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="0eb67-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0eb67-128">string</span></span> | <span data-ttu-id="0eb67-129">Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="0eb67-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="0eb67-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0eb67-130">string</span></span> | <span data-ttu-id="0eb67-131">Naam van de softwareleverancier</span><span class="sxs-lookup"><span data-stu-id="0eb67-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="0eb67-132">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0eb67-132">string</span></span> | <span data-ttu-id="0eb67-133">Naam van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="0eb67-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="0eb67-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0eb67-134">string</span></span> | <span data-ttu-id="0eb67-135">Versienummer van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="0eb67-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="0eb67-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0eb67-136">string</span></span> | <span data-ttu-id="0eb67-137">Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="0eb67-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="0eb67-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0eb67-138">string</span></span> | <span data-ttu-id="0eb67-139">Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap</span><span class="sxs-lookup"><span data-stu-id="0eb67-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="0eb67-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0eb67-140">string</span></span> | <span data-ttu-id="0eb67-141">Naam of beschrijving van de beveiligingsupdate die door de softwareleverancier wordt geleverd om het beveiligingsprobleem aan te pakken</span><span class="sxs-lookup"><span data-stu-id="0eb67-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="0eb67-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0eb67-142">string</span></span> | <span data-ttu-id="0eb67-143">Id van de toepasselijke beveiligingsupdates of -id voor de bijbehorende richtlijnen of KB-artikelen (Knowledge Base)</span><span class="sxs-lookup"><span data-stu-id="0eb67-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="0eb67-144">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0eb67-144">Related topics</span></span>

- [<span data-ttu-id="0eb67-145">Proactief op bedreigingen zoeken</span><span class="sxs-lookup"><span data-stu-id="0eb67-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0eb67-146">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="0eb67-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0eb67-147">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="0eb67-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0eb67-148">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="0eb67-148">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0eb67-149">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="0eb67-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0eb67-150">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="0eb67-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="0eb67-151">Overzicht van threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="0eb67-151">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)