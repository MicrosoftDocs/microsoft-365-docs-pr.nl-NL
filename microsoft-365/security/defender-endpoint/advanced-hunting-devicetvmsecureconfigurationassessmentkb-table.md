---
title: DeviceTvmSecureConfigurationAssessmentKB-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over de verschillende beveiligde configuraties die zijn beoordeeld door Threat & Vulnerability Management in de DeviceTvmSecureConfigurationAssessmentKB-tabel van het advanced hunting schema.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, MITRE ATT&CK framework, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 3ba0d90fae872eff209b41b7ba62baeccfe62808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059765"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="6599a-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="6599a-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6599a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6599a-105">**Applies to:**</span></span>
- [<span data-ttu-id="6599a-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="6599a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="6599a-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="6599a-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6599a-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="6599a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6599a-109">De tabel in het geavanceerde schema bevat informatie over de verschillende beveiligde configuraties, zoals of een apparaat automatische updates heeft ingeschakeld, gecontroleerd door `DeviceTvmSecureConfigurationAssessmentKB` Threat & Vulnerability [Management](next-gen-threat-and-vuln-mgt.md).</span><span class="sxs-lookup"><span data-stu-id="6599a-109">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="6599a-110">Het omvat ook risicogegevens, gerelateerde industriebenchmarks en toepasselijke MITRE ATT-&CK-technieken en -tactieken.</span><span class="sxs-lookup"><span data-stu-id="6599a-110">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="6599a-111">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="6599a-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="6599a-112">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)</span><span class="sxs-lookup"><span data-stu-id="6599a-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="6599a-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="6599a-113">Column name</span></span> | <span data-ttu-id="6599a-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="6599a-114">Data type</span></span> | <span data-ttu-id="6599a-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6599a-115">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="6599a-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6599a-116">string</span></span> | <span data-ttu-id="6599a-117">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="6599a-117">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="6599a-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6599a-118">string</span></span> | <span data-ttu-id="6599a-119">Beoordeelde invloed van de configuratie op de algemene configuratiescore (1-10)</span><span class="sxs-lookup"><span data-stu-id="6599a-119">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="6599a-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6599a-120">string</span></span> | <span data-ttu-id="6599a-121">Weergavenaam van de configuratie</span><span class="sxs-lookup"><span data-stu-id="6599a-121">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="6599a-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6599a-122">string</span></span> | <span data-ttu-id="6599a-123">Beschrijving van de configuratie</span><span class="sxs-lookup"><span data-stu-id="6599a-123">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="6599a-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6599a-124">string</span></span> | <span data-ttu-id="6599a-125">Beschrijving van het bijbehorende risico</span><span class="sxs-lookup"><span data-stu-id="6599a-125">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="6599a-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6599a-126">string</span></span> | <span data-ttu-id="6599a-127">Categorie of groepering waarvan de configuratie deel uitmaken: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen</span><span class="sxs-lookup"><span data-stu-id="6599a-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="6599a-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6599a-128">string</span></span> |<span data-ttu-id="6599a-129">Subcategorie of subgroepering waarvan de configuratie deel uitmaken.</span><span class="sxs-lookup"><span data-stu-id="6599a-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="6599a-130">In veel gevallen worden hier specifieke mogelijkheden of functies beschreven.</span><span class="sxs-lookup"><span data-stu-id="6599a-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="6599a-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6599a-131">string</span></span> | <span data-ttu-id="6599a-132">Lijst met industriebenchmarks die dezelfde of vergelijkbare configuratie aanbevelen</span><span class="sxs-lookup"><span data-stu-id="6599a-132">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="6599a-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6599a-133">string</span></span> | <span data-ttu-id="6599a-134">Lijst met Mitre ATT-&CK-frameworktechnieken met betrekking tot de configuratie</span><span class="sxs-lookup"><span data-stu-id="6599a-134">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="6599a-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6599a-135">string</span></span> | <span data-ttu-id="6599a-136">Lijst met Mitre ATT-&CK-frameworktactieken met betrekking tot de configuratie</span><span class="sxs-lookup"><span data-stu-id="6599a-136">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6599a-137">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6599a-137">Related topics</span></span>

- [<span data-ttu-id="6599a-138">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="6599a-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6599a-139">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="6599a-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6599a-140">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="6599a-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="6599a-141">Overzicht van threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="6599a-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
