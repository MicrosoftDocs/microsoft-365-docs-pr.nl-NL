---
title: DeviceTvmSecureConfigurationAssessmentKB-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over de verschillende beveiligde configuraties die zijn beoordeeld door Threat & Vulnerability Management in de tabel DeviceTvmSecureConfigurationAssessmentKB van het geavanceerde schema voor de jacht.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, MITRE ATT&CK framework, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 1dfa710b86afdcfd8a5643555564a0f34c7b4702
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024239"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="3109e-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="3109e-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3109e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3109e-105">**Applies to:**</span></span>
- <span data-ttu-id="3109e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3109e-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="3109e-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="3109e-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="3109e-108">De tabel in het geavanceerde schema bevat informatie over de verschillende beveiligde configuraties, zoals of een apparaat automatische updates heeft ingeschakeld, gecontroleerd door `DeviceTvmSecureConfigurationAssessmentKB` Threat & Vulnerability [Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="3109e-108">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="3109e-109">Het omvat ook risicogegevens, gerelateerde industriebenchmarks en toepasselijke MITRE ATT-&CK-technieken en -tactieken.</span><span class="sxs-lookup"><span data-stu-id="3109e-109">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="3109e-110">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="3109e-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="3109e-111">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="3109e-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3109e-112">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="3109e-112">Column name</span></span> | <span data-ttu-id="3109e-113">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="3109e-113">Data type</span></span> | <span data-ttu-id="3109e-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3109e-114">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="3109e-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3109e-115">string</span></span> | <span data-ttu-id="3109e-116">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="3109e-116">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="3109e-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3109e-117">string</span></span> | <span data-ttu-id="3109e-118">Beoordeelde invloed van de configuratie op de algemene configuratiescore (1-10)</span><span class="sxs-lookup"><span data-stu-id="3109e-118">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="3109e-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3109e-119">string</span></span> | <span data-ttu-id="3109e-120">Weergavenaam van de configuratie</span><span class="sxs-lookup"><span data-stu-id="3109e-120">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="3109e-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3109e-121">string</span></span> | <span data-ttu-id="3109e-122">Beschrijving van de configuratie</span><span class="sxs-lookup"><span data-stu-id="3109e-122">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="3109e-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3109e-123">string</span></span> | <span data-ttu-id="3109e-124">Beschrijving van het bijbehorende risico</span><span class="sxs-lookup"><span data-stu-id="3109e-124">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="3109e-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3109e-125">string</span></span> | <span data-ttu-id="3109e-126">Categorie of groepering waarvan de configuratie deel uitmaken: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen</span><span class="sxs-lookup"><span data-stu-id="3109e-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="3109e-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3109e-127">string</span></span> |<span data-ttu-id="3109e-128">Subcategorie of subgroepering waarvan de configuratie deel uitmaken.</span><span class="sxs-lookup"><span data-stu-id="3109e-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="3109e-129">In veel gevallen worden hier specifieke mogelijkheden of functies beschreven.</span><span class="sxs-lookup"><span data-stu-id="3109e-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="3109e-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3109e-130">string</span></span> | <span data-ttu-id="3109e-131">Lijst met industriebenchmarks die dezelfde of vergelijkbare configuratie aanbevelen</span><span class="sxs-lookup"><span data-stu-id="3109e-131">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="3109e-132">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3109e-132">string</span></span> | <span data-ttu-id="3109e-133">Labels met verschillende kenmerken die worden gebruikt om een beveiligingsconfiguratie te identificeren of te categoriseren</span><span class="sxs-lookup"><span data-stu-id="3109e-133">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="3109e-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3109e-134">string</span></span> | <span data-ttu-id="3109e-135">Aanbevolen acties om eventuele bijbehorende risico's te beperken of aan te pakken</span><span class="sxs-lookup"><span data-stu-id="3109e-135">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3109e-136">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="3109e-136">Related topics</span></span>

- [<span data-ttu-id="3109e-137">Proactief op bedreigingen zoeken</span><span class="sxs-lookup"><span data-stu-id="3109e-137">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3109e-138">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="3109e-138">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3109e-139">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="3109e-139">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3109e-140">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="3109e-140">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3109e-141">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="3109e-141">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3109e-142">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="3109e-142">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="3109e-143">Overzicht van threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="3109e-143">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)