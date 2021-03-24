---
title: DeviceTvmSoftwareVulnerabilitiesKB-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over de softwareproblemen die door Threat & Vulnerability Management zijn bijgespoord in de tabel DeviceTvmSoftwareVulnerabilitiesKB van het geavanceerde schema voor de jacht.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 772a287097f0b204eb329d066cdd81c4eef7a755
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057705"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="f32fc-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="f32fc-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f32fc-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f32fc-105">**Applies to:**</span></span>
- [<span data-ttu-id="f32fc-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="f32fc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="f32fc-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f32fc-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f32fc-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f32fc-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f32fc-109">De tabel in het geavanceerde schema voor de jacht bevat de lijst met beveiligingsproblemen `DeviceTvmSoftwareVulnerabilitiesKB` [& kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md) apparaten beoordeelt voor.</span><span class="sxs-lookup"><span data-stu-id="f32fc-109">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) assesses devices for.</span></span> <span data-ttu-id="f32fc-110">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="f32fc-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="f32fc-111">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="f32fc-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="f32fc-112">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="f32fc-112">Column name</span></span> | <span data-ttu-id="f32fc-113">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="f32fc-113">Data type</span></span> | <span data-ttu-id="f32fc-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f32fc-114">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="f32fc-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f32fc-115">string</span></span> | <span data-ttu-id="f32fc-116">Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures)</span><span class="sxs-lookup"><span data-stu-id="f32fc-116">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="f32fc-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f32fc-117">string</span></span> | <span data-ttu-id="f32fc-118">Ernstscore die is toegewezen aan het beveiligingsprobleem onder het Common Vulnerability Scoring System (CVSS)</span><span class="sxs-lookup"><span data-stu-id="f32fc-118">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="f32fc-119">booleaanse</span><span class="sxs-lookup"><span data-stu-id="f32fc-119">boolean</span></span> | <span data-ttu-id="f32fc-120">Geeft aan of exploitcode voor het beveiligingsprobleem openbaar beschikbaar is</span><span class="sxs-lookup"><span data-stu-id="f32fc-120">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="f32fc-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f32fc-121">string</span></span> | <span data-ttu-id="f32fc-122">Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap</span><span class="sxs-lookup"><span data-stu-id="f32fc-122">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="f32fc-123">datetime</span><span class="sxs-lookup"><span data-stu-id="f32fc-123">datetime</span></span> | <span data-ttu-id="f32fc-124">Datum en tijd waarop het item of de gerelateerde metagegevens voor het laatst zijn gewijzigd</span><span class="sxs-lookup"><span data-stu-id="f32fc-124">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="f32fc-125">datetime</span><span class="sxs-lookup"><span data-stu-id="f32fc-125">datetime</span></span> | <span data-ttu-id="f32fc-126">Datumprobleem is openbaar gemaakt</span><span class="sxs-lookup"><span data-stu-id="f32fc-126">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="f32fc-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f32fc-127">string</span></span> | <span data-ttu-id="f32fc-128">Beschrijving van kwetsbaarheid en bijbehorende risico's</span><span class="sxs-lookup"><span data-stu-id="f32fc-128">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="f32fc-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f32fc-129">string</span></span> | <span data-ttu-id="f32fc-130">Lijst met alle softwareproducten die door het beveiligingsprobleem zijn beïnvloed</span><span class="sxs-lookup"><span data-stu-id="f32fc-130">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f32fc-131">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f32fc-131">Related topics</span></span>

- [<span data-ttu-id="f32fc-132">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="f32fc-132">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f32fc-133">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="f32fc-133">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f32fc-134">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="f32fc-134">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="f32fc-135">Overzicht van threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="f32fc-135">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
