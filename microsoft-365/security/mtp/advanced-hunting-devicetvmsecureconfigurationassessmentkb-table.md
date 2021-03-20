---
title: DeviceTvmSecureConfigurationAssessmentKB-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over de verschillende beveiligde configuraties die zijn beoordeeld door Threat & Vulnerability Management in de tabel DeviceTvmSecureConfigurationAssessmentKB van het geavanceerde schema voor de jacht.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, MITRE ATT&CK framework, knowledge base, KB, DeviceTvmSecureConfigurationAssesmentKBB
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
ms.openlocfilehash: 23b109ee5c149ecf9015f8c1622e03b20bdf243c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907326"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="abee0-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="abee0-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="abee0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="abee0-105">**Applies to:**</span></span>
- <span data-ttu-id="abee0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="abee0-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="abee0-107">De tabel in het geavanceerde schema bevat informatie over de verschillende beveiligde configuraties, zoals of een apparaat automatische updates heeft ingeschakeld, gecontroleerd door `DeviceTvmSecureConfigurationAssessmentKB` Threat & Vulnerability [Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="abee0-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="abee0-108">Het omvat ook risicogegevens, gerelateerde industriebenchmarks en toepasselijke MITRE ATT-&CK-technieken en -tactieken.</span><span class="sxs-lookup"><span data-stu-id="abee0-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="abee0-109">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="abee0-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="abee0-110">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="abee0-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="abee0-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="abee0-111">Column name</span></span> | <span data-ttu-id="abee0-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="abee0-112">Data type</span></span> | <span data-ttu-id="abee0-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="abee0-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="abee0-114">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="abee0-114">string</span></span> | <span data-ttu-id="abee0-115">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="abee0-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="abee0-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="abee0-116">string</span></span> | <span data-ttu-id="abee0-117">Beoordeelde invloed van de configuratie op de algemene configuratiescore (1-10)</span><span class="sxs-lookup"><span data-stu-id="abee0-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="abee0-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="abee0-118">string</span></span> | <span data-ttu-id="abee0-119">Weergavenaam van de configuratie</span><span class="sxs-lookup"><span data-stu-id="abee0-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="abee0-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="abee0-120">string</span></span> | <span data-ttu-id="abee0-121">Beschrijving van de configuratie</span><span class="sxs-lookup"><span data-stu-id="abee0-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="abee0-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="abee0-122">string</span></span> | <span data-ttu-id="abee0-123">Beschrijving van het bijbehorende risico</span><span class="sxs-lookup"><span data-stu-id="abee0-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="abee0-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="abee0-124">string</span></span> | <span data-ttu-id="abee0-125">Categorie of groepering waarvan de configuratie deel uitmaken: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen</span><span class="sxs-lookup"><span data-stu-id="abee0-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="abee0-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="abee0-126">string</span></span> |<span data-ttu-id="abee0-127">Subcategorie of subgroepering waarvan de configuratie deel uitmaken.</span><span class="sxs-lookup"><span data-stu-id="abee0-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="abee0-128">In veel gevallen worden hier specifieke mogelijkheden of functies beschreven.</span><span class="sxs-lookup"><span data-stu-id="abee0-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="abee0-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="abee0-129">string</span></span> | <span data-ttu-id="abee0-130">Lijst met industriebenchmarks die dezelfde of vergelijkbare configuratie aanbevelen</span><span class="sxs-lookup"><span data-stu-id="abee0-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="abee0-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="abee0-131">string</span></span> | <span data-ttu-id="abee0-132">Labels met verschillende kenmerken die worden gebruikt om een beveiligingsconfiguratie te identificeren of te categoriseren</span><span class="sxs-lookup"><span data-stu-id="abee0-132">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="abee0-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="abee0-133">string</span></span> | <span data-ttu-id="abee0-134">Aanbevolen acties om eventuele bijbehorende risico's te beperken of aan te pakken</span><span class="sxs-lookup"><span data-stu-id="abee0-134">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="abee0-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="abee0-135">Related topics</span></span>

- [<span data-ttu-id="abee0-136">Proactief op bedreigingen zoeken</span><span class="sxs-lookup"><span data-stu-id="abee0-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="abee0-137">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="abee0-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="abee0-138">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="abee0-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="abee0-139">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="abee0-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="abee0-140">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="abee0-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="abee0-141">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="abee0-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="abee0-142">Overzicht van threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="abee0-142">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)