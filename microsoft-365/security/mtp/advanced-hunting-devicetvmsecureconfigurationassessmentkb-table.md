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
ms.openlocfilehash: 3960d877ed1807d2e8ac13512f9bdbb1625fc371
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198119"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="5d1e1-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="5d1e1-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5d1e1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5d1e1-105">**Applies to:**</span></span>
- <span data-ttu-id="5d1e1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5d1e1-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="5d1e1-107">De `DeviceTvmSecureConfigurationAssessmentKB` tabel in het geavanceerde jacht-schema bevat informatie over de verschillende veilige configuraties, zoals het feit of een apparaat automatische updates bevat, gecontroleerd op [bedreiging & beveiligingsbeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="5d1e1-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="5d1e1-108">Dit omvat ook risico informatie, verwante branche benchmarks en toepasselijke MITRE ATT&e technieken en tactieken.</span><span class="sxs-lookup"><span data-stu-id="5d1e1-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="5d1e1-109">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="5d1e1-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="5d1e1-110">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="5d1e1-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5d1e1-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="5d1e1-111">Column name</span></span> | <span data-ttu-id="5d1e1-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="5d1e1-112">Data type</span></span> | <span data-ttu-id="5d1e1-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="5d1e1-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="5d1e1-114">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5d1e1-114">string</span></span> | <span data-ttu-id="5d1e1-115">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="5d1e1-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="5d1e1-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5d1e1-116">string</span></span> | <span data-ttu-id="5d1e1-117">Geclassificeerde impact van de configuratie voor de totale configuratie Score (1-10)</span><span class="sxs-lookup"><span data-stu-id="5d1e1-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="5d1e1-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5d1e1-118">string</span></span> | <span data-ttu-id="5d1e1-119">Naam van de configuratie weergeven</span><span class="sxs-lookup"><span data-stu-id="5d1e1-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="5d1e1-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5d1e1-120">string</span></span> | <span data-ttu-id="5d1e1-121">Beschrijving van de configuratie</span><span class="sxs-lookup"><span data-stu-id="5d1e1-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="5d1e1-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5d1e1-122">string</span></span> | <span data-ttu-id="5d1e1-123">Beschrijving van het bijbehorende risico</span><span class="sxs-lookup"><span data-stu-id="5d1e1-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="5d1e1-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5d1e1-124">string</span></span> | <span data-ttu-id="5d1e1-125">Categorie of groepering waartoe de configuratie behoort: toepassing, besturingssysteem, netwerk, accounts, beveiliging besturingselement</span><span class="sxs-lookup"><span data-stu-id="5d1e1-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="5d1e1-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5d1e1-126">string</span></span> |<span data-ttu-id="5d1e1-127">Subcategorie of subgroep waartoe de configuratie behoort.</span><span class="sxs-lookup"><span data-stu-id="5d1e1-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="5d1e1-128">In veel gevallen bevat dit een beschrijving van specifieke functies of functies.</span><span class="sxs-lookup"><span data-stu-id="5d1e1-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="5d1e1-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5d1e1-129">string</span></span> | <span data-ttu-id="5d1e1-130">Lijst met onderliggend verzekeringen met dezelfde of dezelfde configuratie</span><span class="sxs-lookup"><span data-stu-id="5d1e1-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="5d1e1-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5d1e1-131">string</span></span> | <span data-ttu-id="5d1e1-132">Lijst met Mitre ATT&e Framework-technieken met betrekking tot de configuratie</span><span class="sxs-lookup"><span data-stu-id="5d1e1-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="5d1e1-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5d1e1-133">string</span></span> | <span data-ttu-id="5d1e1-134">Lijst met Mitre ATT&e Framework tactiek met betrekking tot de configuratie</span><span class="sxs-lookup"><span data-stu-id="5d1e1-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5d1e1-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="5d1e1-135">Related topics</span></span>

- [<span data-ttu-id="5d1e1-136">Proactief zoeken naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="5d1e1-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5d1e1-137">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="5d1e1-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5d1e1-138">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="5d1e1-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5d1e1-139">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="5d1e1-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5d1e1-140">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="5d1e1-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5d1e1-141">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="5d1e1-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="5d1e1-142">Overzicht van Threat & beveiligingslek</span><span class="sxs-lookup"><span data-stu-id="5d1e1-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
