---
title: DeviceTvmSecureConfigurationAssessmentKB in het geavanceerde schema voor zoeken
description: Meer informatie over de verschillende veilige configuraties die zijn geëvalueerd op basis van Bedreiging & Beveiligingsprobleembeheer in de tabel DeviceTvmSecureConfigurationAssessmentKB van het geavanceerde zoekschema.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, MITRE ATT&CK framework, Knowledge Base, KB, DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: cf4204767843b9a9e0b0bbfecc2d3fc50db531fc
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145449"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="e6d36-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="e6d36-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e6d36-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e6d36-105">**Applies to:**</span></span>
- <span data-ttu-id="e6d36-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6d36-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="e6d36-107">De tabel in het geavanceerde schema voor zoeken bevat informatie over de verschillende veilige configuraties (zoals of op een apparaat automatische updates zijn ingeschakeld) die zijn ingeschakeld door `DeviceTvmSecureConfigurationAssessmentKB` [Threat & Vulnerability Management.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="e6d36-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="e6d36-108">Het omvat ook risicogegevens, gerelateerde industriebe benchmarks en toepasselijke MITRE ATT&CK-technieken en -technieken.</span><span class="sxs-lookup"><span data-stu-id="e6d36-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="e6d36-109">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="e6d36-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="e6d36-110">Zie het geavanceerde zoekschema voor informatie over andere tabellen in het geavanceerde schema voor [het zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="e6d36-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e6d36-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="e6d36-111">Column name</span></span> | <span data-ttu-id="e6d36-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="e6d36-112">Data type</span></span> | <span data-ttu-id="e6d36-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e6d36-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="e6d36-114">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e6d36-114">string</span></span> | <span data-ttu-id="e6d36-115">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="e6d36-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="e6d36-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e6d36-116">string</span></span> | <span data-ttu-id="e6d36-117">Beoordeelde invloed van de configuratie op de totale configuratiescore (1-10)</span><span class="sxs-lookup"><span data-stu-id="e6d36-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="e6d36-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e6d36-118">string</span></span> | <span data-ttu-id="e6d36-119">Weergavenaam van de configuratie</span><span class="sxs-lookup"><span data-stu-id="e6d36-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="e6d36-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e6d36-120">string</span></span> | <span data-ttu-id="e6d36-121">Beschrijving van de configuratie</span><span class="sxs-lookup"><span data-stu-id="e6d36-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="e6d36-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e6d36-122">string</span></span> | <span data-ttu-id="e6d36-123">Beschrijving van het bijbehorende risico</span><span class="sxs-lookup"><span data-stu-id="e6d36-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="e6d36-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e6d36-124">string</span></span> | <span data-ttu-id="e6d36-125">Tot welke categorie of groepering de configuratie behoort: Toepassing, besturingssysteem, netwerk, accounts, beveiligingsbesturingselementen</span><span class="sxs-lookup"><span data-stu-id="e6d36-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="e6d36-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e6d36-126">string</span></span> |<span data-ttu-id="e6d36-127">Subcategorie of subgroepering tot welke de configuratie behoort.</span><span class="sxs-lookup"><span data-stu-id="e6d36-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="e6d36-128">In veel gevallen wordt hier specifieke functionaliteit of functies beschreven.</span><span class="sxs-lookup"><span data-stu-id="e6d36-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="e6d36-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e6d36-129">string</span></span> | <span data-ttu-id="e6d36-130">Lijst met industriebe benchmarks die dezelfde of vergelijkbare configuratie aanbevelen</span><span class="sxs-lookup"><span data-stu-id="e6d36-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="e6d36-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e6d36-131">string</span></span> | <span data-ttu-id="e6d36-132">Labels voor de verschillende kenmerken die worden gebruikt om een beveiligingsconfiguratie te identificeren of te categoriseren</span><span class="sxs-lookup"><span data-stu-id="e6d36-132">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="e6d36-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e6d36-133">string</span></span> | <span data-ttu-id="e6d36-134">Aanbevolen acties om eventuele bijbehorende risico's te beperken of aan te pakken</span><span class="sxs-lookup"><span data-stu-id="e6d36-134">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e6d36-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e6d36-135">Related topics</span></span>

- [<span data-ttu-id="e6d36-136">Proactief zoeken naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="e6d36-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e6d36-137">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="e6d36-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e6d36-138">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="e6d36-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e6d36-139">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="e6d36-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e6d36-140">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="e6d36-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e6d36-141">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="e6d36-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e6d36-142">Overzicht van risicobeheer & beveiligingsprobleem</span><span class="sxs-lookup"><span data-stu-id="e6d36-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
