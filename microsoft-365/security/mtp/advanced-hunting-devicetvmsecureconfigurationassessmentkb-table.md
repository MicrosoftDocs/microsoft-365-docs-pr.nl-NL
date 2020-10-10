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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: f2642a46f952d3324cec4936aeb813d4ee5507d1
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412992"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="b9a2e-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="b9a2e-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b9a2e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b9a2e-105">**Applies to:**</span></span>
- <span data-ttu-id="b9a2e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b9a2e-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="b9a2e-107">De `DeviceTvmSecureConfigurationAssessmentKB` tabel in het geavanceerde jacht-schema bevat informatie over de verschillende veilige configuraties, zoals het feit of een apparaat automatische updates bevat, gecontroleerd op [bedreiging & beveiligingsbeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="b9a2e-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="b9a2e-108">Dit omvat ook risico informatie, verwante branche benchmarks en toepasselijke MITRE ATT&e technieken en tactieken.</span><span class="sxs-lookup"><span data-stu-id="b9a2e-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="b9a2e-109">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="b9a2e-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="b9a2e-110">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="b9a2e-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b9a2e-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="b9a2e-111">Column name</span></span> | <span data-ttu-id="b9a2e-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="b9a2e-112">Data type</span></span> | <span data-ttu-id="b9a2e-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b9a2e-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="b9a2e-114">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b9a2e-114">string</span></span> | <span data-ttu-id="b9a2e-115">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="b9a2e-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="b9a2e-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b9a2e-116">string</span></span> | <span data-ttu-id="b9a2e-117">Geclassificeerde impact van de configuratie voor de totale configuratie Score (1-10)</span><span class="sxs-lookup"><span data-stu-id="b9a2e-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="b9a2e-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b9a2e-118">string</span></span> | <span data-ttu-id="b9a2e-119">Naam van de configuratie weergeven</span><span class="sxs-lookup"><span data-stu-id="b9a2e-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="b9a2e-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b9a2e-120">string</span></span> | <span data-ttu-id="b9a2e-121">Beschrijving van de configuratie</span><span class="sxs-lookup"><span data-stu-id="b9a2e-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="b9a2e-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b9a2e-122">string</span></span> | <span data-ttu-id="b9a2e-123">Beschrijving van het bijbehorende risico</span><span class="sxs-lookup"><span data-stu-id="b9a2e-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="b9a2e-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b9a2e-124">string</span></span> | <span data-ttu-id="b9a2e-125">Categorie of groepering waartoe de configuratie behoort: toepassing, besturingssysteem, netwerk, accounts, beveiliging besturingselement</span><span class="sxs-lookup"><span data-stu-id="b9a2e-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="b9a2e-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b9a2e-126">string</span></span> |<span data-ttu-id="b9a2e-127">Subcategorie of subgroep waartoe de configuratie behoort.</span><span class="sxs-lookup"><span data-stu-id="b9a2e-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="b9a2e-128">In veel gevallen bevat dit een beschrijving van specifieke functies of functies.</span><span class="sxs-lookup"><span data-stu-id="b9a2e-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="b9a2e-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b9a2e-129">string</span></span> | <span data-ttu-id="b9a2e-130">Lijst met onderliggend verzekeringen met dezelfde of dezelfde configuratie</span><span class="sxs-lookup"><span data-stu-id="b9a2e-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="b9a2e-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b9a2e-131">string</span></span> | <span data-ttu-id="b9a2e-132">Lijst met Mitre ATT&e Framework-technieken met betrekking tot de configuratie</span><span class="sxs-lookup"><span data-stu-id="b9a2e-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="b9a2e-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b9a2e-133">string</span></span> | <span data-ttu-id="b9a2e-134">Lijst met Mitre ATT&e Framework tactiek met betrekking tot de configuratie</span><span class="sxs-lookup"><span data-stu-id="b9a2e-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b9a2e-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b9a2e-135">Related topics</span></span>

- [<span data-ttu-id="b9a2e-136">Proactief zoeken naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="b9a2e-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b9a2e-137">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="b9a2e-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b9a2e-138">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="b9a2e-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b9a2e-139">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="b9a2e-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b9a2e-140">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="b9a2e-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b9a2e-141">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="b9a2e-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b9a2e-142">Overzicht van Threat & beveiligingslek</span><span class="sxs-lookup"><span data-stu-id="b9a2e-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
