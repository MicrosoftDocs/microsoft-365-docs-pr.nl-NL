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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 6186bd37735b5225fd33905395055228972fc27c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847582"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="ec75f-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="ec75f-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ec75f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ec75f-105">**Applies to:**</span></span>
- <span data-ttu-id="ec75f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec75f-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="ec75f-107">De `DeviceTvmSecureConfigurationAssessmentKB` tabel in het geavanceerde jacht-schema bevat informatie over de verschillende veilige configuraties, zoals het feit of een apparaat automatische updates bevat, gecontroleerd op [bedreiging & beveiligingsbeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="ec75f-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="ec75f-108">Dit omvat ook risico informatie, verwante branche benchmarks en toepasselijke MITRE ATT&e technieken en tactieken.</span><span class="sxs-lookup"><span data-stu-id="ec75f-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="ec75f-109">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="ec75f-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="ec75f-110">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="ec75f-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ec75f-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="ec75f-111">Column name</span></span> | <span data-ttu-id="ec75f-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="ec75f-112">Data type</span></span> | <span data-ttu-id="ec75f-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="ec75f-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="ec75f-114">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ec75f-114">string</span></span> | <span data-ttu-id="ec75f-115">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="ec75f-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="ec75f-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ec75f-116">string</span></span> | <span data-ttu-id="ec75f-117">Geclassificeerde impact van de configuratie voor de totale configuratie Score (1-10)</span><span class="sxs-lookup"><span data-stu-id="ec75f-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="ec75f-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ec75f-118">string</span></span> | <span data-ttu-id="ec75f-119">Naam van de configuratie weergeven</span><span class="sxs-lookup"><span data-stu-id="ec75f-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="ec75f-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ec75f-120">string</span></span> | <span data-ttu-id="ec75f-121">Beschrijving van de configuratie</span><span class="sxs-lookup"><span data-stu-id="ec75f-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="ec75f-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ec75f-122">string</span></span> | <span data-ttu-id="ec75f-123">Beschrijving van het bijbehorende risico</span><span class="sxs-lookup"><span data-stu-id="ec75f-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="ec75f-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ec75f-124">string</span></span> | <span data-ttu-id="ec75f-125">Categorie of groepering waartoe de configuratie behoort: toepassing, besturingssysteem, netwerk, accounts, beveiliging besturingselement</span><span class="sxs-lookup"><span data-stu-id="ec75f-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="ec75f-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ec75f-126">string</span></span> |<span data-ttu-id="ec75f-127">Subcategorie of subgroep waartoe de configuratie behoort.</span><span class="sxs-lookup"><span data-stu-id="ec75f-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="ec75f-128">In veel gevallen bevat dit een beschrijving van specifieke functies of functies.</span><span class="sxs-lookup"><span data-stu-id="ec75f-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="ec75f-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ec75f-129">string</span></span> | <span data-ttu-id="ec75f-130">Lijst met onderliggend verzekeringen met dezelfde of dezelfde configuratie</span><span class="sxs-lookup"><span data-stu-id="ec75f-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="ec75f-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ec75f-131">string</span></span> | <span data-ttu-id="ec75f-132">Lijst met Mitre ATT&e Framework-technieken met betrekking tot de configuratie</span><span class="sxs-lookup"><span data-stu-id="ec75f-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="ec75f-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ec75f-133">string</span></span> | <span data-ttu-id="ec75f-134">Lijst met Mitre ATT&e Framework tactiek met betrekking tot de configuratie</span><span class="sxs-lookup"><span data-stu-id="ec75f-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ec75f-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ec75f-135">Related topics</span></span>

- [<span data-ttu-id="ec75f-136">Proactief zoeken naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="ec75f-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ec75f-137">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="ec75f-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ec75f-138">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="ec75f-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ec75f-139">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="ec75f-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ec75f-140">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="ec75f-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ec75f-141">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="ec75f-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ec75f-142">Overzicht van Threat & beveiligingslek</span><span class="sxs-lookup"><span data-stu-id="ec75f-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
