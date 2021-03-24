---
title: DeviceTvmSoftwareVulnerabilities table in the advanced hunting schema
description: Meer informatie over softwareproblemen die zijn gevonden op apparaten en de lijst met beschikbare beveiligingsupdates die elk beveiligingsprobleem in de tabel DeviceTvmSoftwareVulnerabilities van het geavanceerde schema voor de jacht verhelpen.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b38297cd0fa2e931619ff9c0557d2ae868c7aa4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060261"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="04ec3-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="04ec3-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="04ec3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="04ec3-105">**Applies to:**</span></span>
- [<span data-ttu-id="04ec3-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="04ec3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="04ec3-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="04ec3-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="04ec3-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="04ec3-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="04ec3-109">De `DeviceTvmSoftwareVulnerabilities` tabel in het geavanceerde schema bevat de lijst Threat & Vulnerability [Management](next-gen-threat-and-vuln-mgt.md) met beveiligingslekken in geïnstalleerde softwareproducten.</span><span class="sxs-lookup"><span data-stu-id="04ec3-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="04ec3-110">Deze tabel bevat ook informatie over het besturingssysteem, CVE-ID's en ernst van de kwetsbaarheid.</span><span class="sxs-lookup"><span data-stu-id="04ec3-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="04ec3-111">U kunt deze tabel bijvoorbeeld gebruiken om te zoeken naar gebeurtenissen met apparaten met ernstige beveiligingsproblemen in hun software.</span><span class="sxs-lookup"><span data-stu-id="04ec3-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="04ec3-112">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="04ec3-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="04ec3-113">De `DeviceTvmSoftwareInventory` tabel en de tabellen zijn `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` vervangen.</span><span class="sxs-lookup"><span data-stu-id="04ec3-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="04ec3-114">De eerste twee tabellen bevatten samen meer kolommen die u kunt gebruiken om uw activiteiten op het gebied van kwetsbaarheidsbeheer te informeren.</span><span class="sxs-lookup"><span data-stu-id="04ec3-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="04ec3-115">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)</span><span class="sxs-lookup"><span data-stu-id="04ec3-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="04ec3-116">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="04ec3-116">Column name</span></span> | <span data-ttu-id="04ec3-117">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="04ec3-117">Data type</span></span> | <span data-ttu-id="04ec3-118">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="04ec3-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="04ec3-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="04ec3-119">string</span></span> | <span data-ttu-id="04ec3-120">Unieke id voor het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="04ec3-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="04ec3-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="04ec3-121">string</span></span> | <span data-ttu-id="04ec3-122">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat</span><span class="sxs-lookup"><span data-stu-id="04ec3-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="04ec3-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="04ec3-123">string</span></span> | <span data-ttu-id="04ec3-124">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="04ec3-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="04ec3-125">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="04ec3-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="04ec3-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="04ec3-126">string</span></span> | <span data-ttu-id="04ec3-127">Versie van het besturingssysteem dat op het apparaat wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="04ec3-127">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="04ec3-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="04ec3-128">string</span></span> | <span data-ttu-id="04ec3-129">Architectuur van het besturingssysteem dat op het apparaat wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="04ec3-129">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="04ec3-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="04ec3-130">string</span></span> | <span data-ttu-id="04ec3-131">Naam van de softwareleverancier</span><span class="sxs-lookup"><span data-stu-id="04ec3-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="04ec3-132">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="04ec3-132">string</span></span> | <span data-ttu-id="04ec3-133">Naam van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="04ec3-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="04ec3-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="04ec3-134">string</span></span> | <span data-ttu-id="04ec3-135">Versienummer van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="04ec3-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="04ec3-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="04ec3-136">string</span></span> | <span data-ttu-id="04ec3-137">Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="04ec3-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="04ec3-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="04ec3-138">string</span></span> | <span data-ttu-id="04ec3-139">Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap</span><span class="sxs-lookup"><span data-stu-id="04ec3-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="04ec3-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="04ec3-140">string</span></span> | <span data-ttu-id="04ec3-141">Naam of beschrijving van de beveiligingsupdate die door de softwareleverancier wordt geleverd om het beveiligingsprobleem aan te pakken</span><span class="sxs-lookup"><span data-stu-id="04ec3-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="04ec3-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="04ec3-142">string</span></span> | <span data-ttu-id="04ec3-143">Id van de toepasselijke beveiligingsupdates of -id voor de bijbehorende richtlijnen of KB-artikelen (Knowledge Base)</span><span class="sxs-lookup"><span data-stu-id="04ec3-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="04ec3-144">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="04ec3-144">Related topics</span></span>

- [<span data-ttu-id="04ec3-145">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="04ec3-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="04ec3-146">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="04ec3-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="04ec3-147">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="04ec3-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="04ec3-148">Overzicht van threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="04ec3-148">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
