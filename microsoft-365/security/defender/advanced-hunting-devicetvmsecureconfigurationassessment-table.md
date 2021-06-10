---
title: DeviceTvmSecureConfigurationAssessment table in the advanced hunting schema
description: Meer informatie over beveiligingsbeoordelingsgebeurtenissen in de tabel DeviceTvmSecureConfigurationAssessment van het geavanceerde schema voor de jacht. Deze bedreigingsgebeurtenissen & vulnerability management apparaatgegevens, evenals beveiligingsconfiguratiegegevens, impact- en compliancegegevens.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssesment
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
ms.openlocfilehash: 2e3e649911cb2ce63c2a49be0ebc93e35e8055d6
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024215"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="6b4d1-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="6b4d1-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6b4d1-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6b4d1-106">**Applies to:**</span></span>
- <span data-ttu-id="6b4d1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b4d1-107">Microsoft 365 Defender</span></span>
- <span data-ttu-id="6b4d1-108">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="6b4d1-108">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="6b4d1-109">Elke rij in de `DeviceTvmSecureConfigurationAssessment` tabel bevat een beoordelingsgebeurtenis voor een specifieke beveiligingsconfiguratie van [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="6b4d1-109">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="6b4d1-110">Gebruik deze verwijzing om de meest recente evaluatieresultaten te controleren en te bepalen of apparaten compatibel zijn.</span><span class="sxs-lookup"><span data-stu-id="6b4d1-110">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="6b4d1-111">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="6b4d1-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6b4d1-112">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="6b4d1-112">Column name</span></span> | <span data-ttu-id="6b4d1-113">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="6b4d1-113">Data type</span></span> | <span data-ttu-id="6b4d1-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6b4d1-114">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="6b4d1-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6b4d1-115">string</span></span> | <span data-ttu-id="6b4d1-116">Unieke id voor het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="6b4d1-116">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6b4d1-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6b4d1-117">string</span></span> | <span data-ttu-id="6b4d1-118">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat</span><span class="sxs-lookup"><span data-stu-id="6b4d1-118">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="6b4d1-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6b4d1-119">string</span></span> | <span data-ttu-id="6b4d1-120">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="6b4d1-120">Platform of the operating system running on the device.</span></span> <span data-ttu-id="6b4d1-121">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="6b4d1-121">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="6b4d1-122">datetime</span><span class="sxs-lookup"><span data-stu-id="6b4d1-122">datetime</span></span> | <span data-ttu-id="6b4d1-123">Datum en tijd waarop de record is gegenereerd</span><span class="sxs-lookup"><span data-stu-id="6b4d1-123">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="6b4d1-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6b4d1-124">string</span></span> | <span data-ttu-id="6b4d1-125">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="6b4d1-125">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="6b4d1-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6b4d1-126">string</span></span> | <span data-ttu-id="6b4d1-127">Categorie of groepering waarvan de configuratie deel uitmaken: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen</span><span class="sxs-lookup"><span data-stu-id="6b4d1-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="6b4d1-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6b4d1-128">string</span></span> | <span data-ttu-id="6b4d1-129">Subcategorie of subgroepering waarvan de configuratie deel uitmaken.</span><span class="sxs-lookup"><span data-stu-id="6b4d1-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="6b4d1-130">In veel gevallen worden hier specifieke mogelijkheden of functies beschreven.</span><span class="sxs-lookup"><span data-stu-id="6b4d1-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="6b4d1-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6b4d1-131">string</span></span> | <span data-ttu-id="6b4d1-132">Beoordeelde invloed van de configuratie op de algemene configuratiescore (1-10)</span><span class="sxs-lookup"><span data-stu-id="6b4d1-132">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="6b4d1-133">booleaanse</span><span class="sxs-lookup"><span data-stu-id="6b4d1-133">boolean</span></span> | <span data-ttu-id="6b4d1-134">Geeft aan of de configuratie of het beleid juist is geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="6b4d1-134">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="6b4d1-135">booleaanse</span><span class="sxs-lookup"><span data-stu-id="6b4d1-135">boolean</span></span> | <span data-ttu-id="6b4d1-136">Geeft aan of de configuratie of het beleid van toepassing is op het apparaat</span><span class="sxs-lookup"><span data-stu-id="6b4d1-136">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="6b4d1-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6b4d1-137">string</span></span> | <span data-ttu-id="6b4d1-138">Aanvullende contextuele informatie over de configuratie of het beleid</span><span class="sxs-lookup"><span data-stu-id="6b4d1-138">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpact` | <span data-ttu-id="6b4d1-139">booleaanse</span><span class="sxs-lookup"><span data-stu-id="6b4d1-139">boolean</span></span> | <span data-ttu-id="6b4d1-140">Geeft aan of er gevolgen voor de gebruiker zijn als de configuratie of het beleid wordt toegepast</span><span class="sxs-lookup"><span data-stu-id="6b4d1-140">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6b4d1-141">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6b4d1-141">Related topics</span></span>

- [<span data-ttu-id="6b4d1-142">Proactief op bedreigingen zoeken</span><span class="sxs-lookup"><span data-stu-id="6b4d1-142">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6b4d1-143">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="6b4d1-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6b4d1-144">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="6b4d1-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6b4d1-145">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="6b4d1-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6b4d1-146">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="6b4d1-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6b4d1-147">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="6b4d1-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="6b4d1-148">Overzicht van threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="6b4d1-148">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)