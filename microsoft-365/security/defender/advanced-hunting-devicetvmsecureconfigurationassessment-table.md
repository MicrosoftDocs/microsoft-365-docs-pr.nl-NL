---
title: DeviceTvmSecureConfigurationAssessment table in the advanced hunting schema
description: Meer informatie over beveiligingsbeoordelingsgebeurtenissen in de tabel DeviceTvmSecureConfigurationAssessment van het geavanceerde schema voor de jacht. Deze bedreigingen & beveiligingsrisico's bevatten apparaatgegevens, evenals beveiligingsconfiguratiegegevens, impact- en compliancegegevens.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 1c4b71139a0fba84928c3f604e3c770d140d9e2b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499748"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="1b5ef-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="1b5ef-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1b5ef-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1b5ef-106">**Applies to:**</span></span>
- <span data-ttu-id="1b5ef-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b5ef-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="1b5ef-108">Elke rij in de `DeviceTvmSecureConfigurationAssessment` tabel bevat een beoordelingsgebeurtenis voor een specifieke beveiligingsconfiguratie van [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="1b5ef-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="1b5ef-109">Gebruik deze verwijzing om de meest recente evaluatieresultaten te controleren en te bepalen of apparaten compatibel zijn.</span><span class="sxs-lookup"><span data-stu-id="1b5ef-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="1b5ef-110">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="1b5ef-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="1b5ef-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="1b5ef-111">Column name</span></span> | <span data-ttu-id="1b5ef-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="1b5ef-112">Data type</span></span> | <span data-ttu-id="1b5ef-113">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="1b5ef-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="1b5ef-114">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1b5ef-114">string</span></span> | <span data-ttu-id="1b5ef-115">Unieke id voor het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="1b5ef-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="1b5ef-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1b5ef-116">string</span></span> | <span data-ttu-id="1b5ef-117">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat</span><span class="sxs-lookup"><span data-stu-id="1b5ef-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="1b5ef-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1b5ef-118">string</span></span> | <span data-ttu-id="1b5ef-119">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="1b5ef-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="1b5ef-120">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="1b5ef-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="1b5ef-121">datetime</span><span class="sxs-lookup"><span data-stu-id="1b5ef-121">datetime</span></span> | <span data-ttu-id="1b5ef-122">Datum en tijd waarop de record is gegenereerd</span><span class="sxs-lookup"><span data-stu-id="1b5ef-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="1b5ef-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1b5ef-123">string</span></span> | <span data-ttu-id="1b5ef-124">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="1b5ef-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="1b5ef-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1b5ef-125">string</span></span> | <span data-ttu-id="1b5ef-126">Categorie of groepering waarvan de configuratie deel uitmaken: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen</span><span class="sxs-lookup"><span data-stu-id="1b5ef-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="1b5ef-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1b5ef-127">string</span></span> | <span data-ttu-id="1b5ef-128">Subcategorie of subgroepering waarvan de configuratie deel uitmaken.</span><span class="sxs-lookup"><span data-stu-id="1b5ef-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="1b5ef-129">In veel gevallen worden hier specifieke mogelijkheden of functies beschreven.</span><span class="sxs-lookup"><span data-stu-id="1b5ef-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="1b5ef-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1b5ef-130">string</span></span> | <span data-ttu-id="1b5ef-131">Beoordeelde invloed van de configuratie op de algemene configuratiescore (1-10)</span><span class="sxs-lookup"><span data-stu-id="1b5ef-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="1b5ef-132">booleaanse</span><span class="sxs-lookup"><span data-stu-id="1b5ef-132">boolean</span></span> | <span data-ttu-id="1b5ef-133">Geeft aan of de configuratie of het beleid juist is geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="1b5ef-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="1b5ef-134">booleaanse</span><span class="sxs-lookup"><span data-stu-id="1b5ef-134">boolean</span></span> | <span data-ttu-id="1b5ef-135">Geeft aan of de configuratie of het beleid van toepassing is op het apparaat</span><span class="sxs-lookup"><span data-stu-id="1b5ef-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="1b5ef-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="1b5ef-136">string</span></span> | <span data-ttu-id="1b5ef-137">Aanvullende contextuele informatie over de configuratie of het beleid</span><span class="sxs-lookup"><span data-stu-id="1b5ef-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpact` | <span data-ttu-id="1b5ef-138">booleaanse</span><span class="sxs-lookup"><span data-stu-id="1b5ef-138">boolean</span></span> | <span data-ttu-id="1b5ef-139">Geeft aan of er gevolgen voor de gebruiker zijn als de configuratie of het beleid wordt toegepast</span><span class="sxs-lookup"><span data-stu-id="1b5ef-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="1b5ef-140">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="1b5ef-140">Related topics</span></span>

- [<span data-ttu-id="1b5ef-141">Proactief op bedreigingen zoeken</span><span class="sxs-lookup"><span data-stu-id="1b5ef-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1b5ef-142">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="1b5ef-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1b5ef-143">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="1b5ef-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="1b5ef-144">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="1b5ef-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="1b5ef-145">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="1b5ef-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1b5ef-146">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="1b5ef-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="1b5ef-147">Overzicht van threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="1b5ef-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)