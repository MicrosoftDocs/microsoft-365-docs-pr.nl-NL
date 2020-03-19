---
title: DeviceTvmSecureConfigurationAssessmentKB-tabel in het geavanceerde jachtschema
description: Lees meer over de verschillende beveiligde configuraties die zijn beoordeeld door Threat & Vulnerability Management in de DeviceTvmSecureConfigurationAssessmentKB-tabel van het geavanceerde jachtschema.
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, bedreiging & kwetsbaarheidsbeheer, TVM, apparaatbeheer, beveiligingsconfiguratie, MITRE ATT&CK-framework, kennisbank, KB, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: a265bb84b0ad59ee56cb0f0670951bab1bcd344a
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806321"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="d2077-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="d2077-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="d2077-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d2077-105">**Applies to:**</span></span>
- <span data-ttu-id="d2077-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="d2077-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="d2077-107">De `DeviceTvmSecureConfigurationAssessmentKB` tabel in het geavanceerde jachtschema bevat informatie over de verschillende beveiligde configuraties - zoals of een apparaat automatische updates heeft ingeschakeld - gecontroleerd door [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="d2077-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="d2077-108">Het omvat ook risico-informatie, gerelateerde industrie benchmarks, en de toepasselijke MITRE ATT&CK technieken en tactieken.</span><span class="sxs-lookup"><span data-stu-id="d2077-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="d2077-109">Gebruik deze verwijzing om query's te construeren die informatie uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="d2077-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="d2077-110">Voor informatie over andere tabellen in de geavanceerde jacht schema, zie [de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="d2077-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d2077-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="d2077-111">Column name</span></span> | <span data-ttu-id="d2077-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="d2077-112">Data type</span></span> | <span data-ttu-id="d2077-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="d2077-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="d2077-114">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d2077-114">string</span></span> | <span data-ttu-id="d2077-115">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="d2077-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="d2077-116">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d2077-116">string</span></span> | <span data-ttu-id="d2077-117">Nominale impact van de configuratie op de totale configuratiescore (1-10)</span><span class="sxs-lookup"><span data-stu-id="d2077-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="d2077-118">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d2077-118">string</span></span> | <span data-ttu-id="d2077-119">Weergavenaam van de configuratie</span><span class="sxs-lookup"><span data-stu-id="d2077-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="d2077-120">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d2077-120">string</span></span> | <span data-ttu-id="d2077-121">Beschrijving van de configuratie</span><span class="sxs-lookup"><span data-stu-id="d2077-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="d2077-122">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d2077-122">string</span></span> | <span data-ttu-id="d2077-123">Beschrijving van het bijbehorende risico</span><span class="sxs-lookup"><span data-stu-id="d2077-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="d2077-124">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d2077-124">string</span></span> | <span data-ttu-id="d2077-125">Categorie of groepering waartoe de configuratie behoort: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen</span><span class="sxs-lookup"><span data-stu-id="d2077-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="d2077-126">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d2077-126">string</span></span> |<span data-ttu-id="d2077-127">Subcategorie of subgroep waartoe de configuratie behoort.</span><span class="sxs-lookup"><span data-stu-id="d2077-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="d2077-128">In veel gevallen worden specifieke mogelijkheden of functies beschreven.</span><span class="sxs-lookup"><span data-stu-id="d2077-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="d2077-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d2077-129">string</span></span> | <span data-ttu-id="d2077-130">Lijst van industriebenchmarks die dezelfde of vergelijkbare configuratie aanbevelen</span><span class="sxs-lookup"><span data-stu-id="d2077-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="d2077-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d2077-131">string</span></span> | <span data-ttu-id="d2077-132">Lijst van Mitre ATT&CK framework technieken met betrekking tot de configuratie</span><span class="sxs-lookup"><span data-stu-id="d2077-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="d2077-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d2077-133">string</span></span> | <span data-ttu-id="d2077-134">Lijst van Mitre ATT&CK framework tactiek met betrekking tot de configuratie</span><span class="sxs-lookup"><span data-stu-id="d2077-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d2077-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d2077-135">Related topics</span></span>

- [<span data-ttu-id="d2077-136">Proactief op zoek naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="d2077-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d2077-137">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="d2077-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d2077-138">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="d2077-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d2077-139">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="d2077-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d2077-140">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="d2077-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d2077-141">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="d2077-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="d2077-142">Overzicht van Threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="d2077-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
