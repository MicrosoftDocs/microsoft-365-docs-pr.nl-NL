---
title: DeviceTvmSecureConfigurationAssessmentKB-tabel in het geavanceerde jacht schema
description: Meer informatie over de diverse beveiligde configuraties die zijn goedgekeurd door risico & in de tabel DeviceTvmSecureConfigurationAssessmentKB van het schema geavanceerde jacht.
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema verwijzing, kusto, Table, Column, datatype, Description &, beveiliging, beveiliging, MITRE ATT&verzwakken, Knowledge Base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 2c16929555b3923086e249db61cebb3cf7af17c8
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648963"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="7484a-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="7484a-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="7484a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7484a-105">**Applies to:**</span></span>
- <span data-ttu-id="7484a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7484a-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="7484a-107">De `DeviceTvmSecureConfigurationAssessmentKB` tabel in het geavanceerde jacht-schema bevat informatie over de verschillende veilige configuraties, zoals het feit of een apparaat automatische updates bevat, gecontroleerd op [bedreiging & beveiligingsbeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="7484a-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="7484a-108">Dit omvat ook risico informatie, verwante branche benchmarks en toepasselijke MITRE ATT&e technieken en tactieken.</span><span class="sxs-lookup"><span data-stu-id="7484a-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="7484a-109">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="7484a-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="7484a-110">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="7484a-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7484a-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="7484a-111">Column name</span></span> | <span data-ttu-id="7484a-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="7484a-112">Data type</span></span> | <span data-ttu-id="7484a-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="7484a-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="7484a-114">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7484a-114">string</span></span> | <span data-ttu-id="7484a-115">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="7484a-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="7484a-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7484a-116">string</span></span> | <span data-ttu-id="7484a-117">Geclassificeerde impact van de configuratie voor de totale configuratie Score (1-10)</span><span class="sxs-lookup"><span data-stu-id="7484a-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="7484a-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7484a-118">string</span></span> | <span data-ttu-id="7484a-119">Naam van de configuratie weergeven</span><span class="sxs-lookup"><span data-stu-id="7484a-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="7484a-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7484a-120">string</span></span> | <span data-ttu-id="7484a-121">Beschrijving van de configuratie</span><span class="sxs-lookup"><span data-stu-id="7484a-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="7484a-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7484a-122">string</span></span> | <span data-ttu-id="7484a-123">Beschrijving van het bijbehorende risico</span><span class="sxs-lookup"><span data-stu-id="7484a-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="7484a-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7484a-124">string</span></span> | <span data-ttu-id="7484a-125">Categorie of groepering waartoe de configuratie behoort: toepassing, besturingssysteem, netwerk, accounts, beveiliging besturingselement</span><span class="sxs-lookup"><span data-stu-id="7484a-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="7484a-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7484a-126">string</span></span> |<span data-ttu-id="7484a-127">Subcategorie of subgroep waartoe de configuratie behoort.</span><span class="sxs-lookup"><span data-stu-id="7484a-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="7484a-128">In veel gevallen bevat dit een beschrijving van specifieke functies of functies.</span><span class="sxs-lookup"><span data-stu-id="7484a-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="7484a-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7484a-129">string</span></span> | <span data-ttu-id="7484a-130">Lijst met onderliggend verzekeringen met dezelfde of dezelfde configuratie</span><span class="sxs-lookup"><span data-stu-id="7484a-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="7484a-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7484a-131">string</span></span> | <span data-ttu-id="7484a-132">Lijst met Mitre ATT&e Framework-technieken met betrekking tot de configuratie</span><span class="sxs-lookup"><span data-stu-id="7484a-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="7484a-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7484a-133">string</span></span> | <span data-ttu-id="7484a-134">Lijst met Mitre ATT&e Framework tactiek met betrekking tot de configuratie</span><span class="sxs-lookup"><span data-stu-id="7484a-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7484a-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7484a-135">Related topics</span></span>

- [<span data-ttu-id="7484a-136">Proactief zoeken naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="7484a-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7484a-137">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="7484a-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7484a-138">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="7484a-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7484a-139">Jacht op apparaten, e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="7484a-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7484a-140">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="7484a-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7484a-141">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="7484a-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="7484a-142">Overzicht van Threat & beveiligingslek</span><span class="sxs-lookup"><span data-stu-id="7484a-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
