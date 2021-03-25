---
title: DeviceTvmSoftwareInventoryVulnerabilities table in the advanced hunting schema
description: Meer informatie over de inventaris van software op uw apparaten en de beveiligingslekken in de tabel DeviceTvmSoftwareInventoryVulnerabilities van het geavanceerde schema voor de jacht.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: bbb535aa3f106c8569edb3c64ba95bba9bf36186
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163457"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="47508-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="47508-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="47508-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="47508-105">**Applies to:**</span></span>

- [<span data-ttu-id="47508-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="47508-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="47508-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="47508-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="47508-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="47508-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="47508-109">De tabel in het geavanceerde schema bevat de inventaris & Beveiligingsprobleembeheer van software op uw apparaten en eventuele bekende beveiligingslekken `DeviceTvmSoftwareInventoryVulnerabilities` in deze [](next-gen-threat-and-vuln-mgt.md) softwareproducten.</span><span class="sxs-lookup"><span data-stu-id="47508-109">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="47508-110">Deze tabel bevat ook informatie over het besturingssysteem, CVE-ID's en ernst van de kwetsbaarheid.</span><span class="sxs-lookup"><span data-stu-id="47508-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="47508-111">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="47508-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="47508-112">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)</span><span class="sxs-lookup"><span data-stu-id="47508-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="47508-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="47508-113">Column name</span></span> | <span data-ttu-id="47508-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="47508-114">Data type</span></span> | <span data-ttu-id="47508-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="47508-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="47508-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="47508-116">string</span></span> | <span data-ttu-id="47508-117">Unieke id voor het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="47508-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="47508-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="47508-118">string</span></span> | <span data-ttu-id="47508-119">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat</span><span class="sxs-lookup"><span data-stu-id="47508-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="47508-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="47508-120">string</span></span> | <span data-ttu-id="47508-121">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="47508-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="47508-122">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="47508-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="47508-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="47508-123">string</span></span> | <span data-ttu-id="47508-124">Versie van het besturingssysteem dat op het apparaat wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="47508-124">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="47508-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="47508-125">string</span></span> | <span data-ttu-id="47508-126">Architectuur van het besturingssysteem dat op het apparaat wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="47508-126">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="47508-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="47508-127">string</span></span> | <span data-ttu-id="47508-128">Naam van de softwareleverancier</span><span class="sxs-lookup"><span data-stu-id="47508-128">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="47508-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="47508-129">string</span></span> | <span data-ttu-id="47508-130">Naam van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="47508-130">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="47508-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="47508-131">string</span></span> | <span data-ttu-id="47508-132">Versienummer van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="47508-132">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="47508-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="47508-133">string</span></span> | <span data-ttu-id="47508-134">Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="47508-134">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="47508-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="47508-135">string</span></span> | <span data-ttu-id="47508-136">Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap</span><span class="sxs-lookup"><span data-stu-id="47508-136">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="47508-137">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="47508-137">Related topics</span></span>

- [<span data-ttu-id="47508-138">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="47508-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="47508-139">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="47508-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="47508-140">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="47508-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="47508-141">Overzicht van threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="47508-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
