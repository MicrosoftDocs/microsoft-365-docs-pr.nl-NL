---
title: DeviceTvmSecureConfigurationAssessment-tabel in het geavanceerde jacht schema
description: Meer informatie over beveiligings evaluatie gebeurtenissen in de tabel DeviceTvmSecureConfigurationAssessment van het schema geavanceerde jacht. Deze bedreiging & gebeurtenissen voor het beheer van het beveiligingslek biedt informatie over de beveiliging van apparaten, evenals informatie over de beveiligingsconfiguratie, informatie over de impact en de naleving.
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat-jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema Reference, kusto, Table, Column, datatype, een beschrijving, bedreiging & beveiligingsconfiguratie, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 356548c3115aacce8c76d7fbc552811c168750ed
ms.sourcegitcommit: e8b3855302fc34d09b6df6c737033a2f326d6eee
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2020
ms.locfileid: "48770071"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="f2d4c-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="f2d4c-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f2d4c-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f2d4c-106">**Applies to:**</span></span>
- <span data-ttu-id="f2d4c-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f2d4c-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="f2d4c-108">Elke rij in de `DeviceTvmSecureConfigurationAssessment` tabel bevat een beoordelings gebeurtenis voor een bepaalde beveiligingsconfiguratie, van [bedreiging & beveiligingsbeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="f2d4c-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="f2d4c-109">Gebruik deze naslag voor de laatste beoordelings resultaten en bepaal of apparaten compatibel zijn.</span><span class="sxs-lookup"><span data-stu-id="f2d4c-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="f2d4c-110">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="f2d4c-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f2d4c-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="f2d4c-111">Column name</span></span> | <span data-ttu-id="f2d4c-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="f2d4c-112">Data type</span></span> | <span data-ttu-id="f2d4c-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f2d4c-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="f2d4c-114">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f2d4c-114">string</span></span> | <span data-ttu-id="f2d4c-115">Unieke id van het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="f2d4c-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f2d4c-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f2d4c-116">string</span></span> | <span data-ttu-id="f2d4c-117">FQDN (Fully Qualified Domain Name) van het apparaat</span><span class="sxs-lookup"><span data-stu-id="f2d4c-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="f2d4c-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f2d4c-118">string</span></span> | <span data-ttu-id="f2d4c-119">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="f2d4c-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="f2d4c-120">Dit geeft specifieke besturingssystemen aan, met inbegrip van variaties in dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="f2d4c-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="f2d4c-121">tijd</span><span class="sxs-lookup"><span data-stu-id="f2d4c-121">datetime</span></span> | <span data-ttu-id="f2d4c-122">De datum en tijd waarop de record is gegenereerd</span><span class="sxs-lookup"><span data-stu-id="f2d4c-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="f2d4c-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f2d4c-123">string</span></span> | <span data-ttu-id="f2d4c-124">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="f2d4c-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="f2d4c-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f2d4c-125">string</span></span> | <span data-ttu-id="f2d4c-126">Categorie of groepering waartoe de configuratie behoort: toepassing, besturingssysteem, netwerk, accounts, beveiliging besturingselement</span><span class="sxs-lookup"><span data-stu-id="f2d4c-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="f2d4c-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f2d4c-127">string</span></span> | <span data-ttu-id="f2d4c-128">Subcategorie of subgroep waartoe de configuratie behoort.</span><span class="sxs-lookup"><span data-stu-id="f2d4c-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="f2d4c-129">In veel gevallen bevat dit een beschrijving van specifieke functies of functies.</span><span class="sxs-lookup"><span data-stu-id="f2d4c-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="f2d4c-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f2d4c-130">string</span></span> | <span data-ttu-id="f2d4c-131">Geclassificeerde impact van de configuratie voor de totale configuratie Score (1-10)</span><span class="sxs-lookup"><span data-stu-id="f2d4c-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="f2d4c-132">Boolean</span><span class="sxs-lookup"><span data-stu-id="f2d4c-132">boolean</span></span> | <span data-ttu-id="f2d4c-133">Geeft aan of de configuratie of het beleid correct is geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="f2d4c-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="f2d4c-134">Boolean</span><span class="sxs-lookup"><span data-stu-id="f2d4c-134">boolean</span></span> | <span data-ttu-id="f2d4c-135">Geeft aan of de configuratie of het beleid van toepassing is op het apparaat</span><span class="sxs-lookup"><span data-stu-id="f2d4c-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="f2d4c-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f2d4c-136">string</span></span> | <span data-ttu-id="f2d4c-137">Aanvullende contextuele informatie over de configuratie of het beleid</span><span class="sxs-lookup"><span data-stu-id="f2d4c-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="f2d4c-138">Boolean</span><span class="sxs-lookup"><span data-stu-id="f2d4c-138">boolean</span></span> | <span data-ttu-id="f2d4c-139">Geeft aan of de gebruiker van invloed is op de toepassing als de configuratie of het beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="f2d4c-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f2d4c-140">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f2d4c-140">Related topics</span></span>

- [<span data-ttu-id="f2d4c-141">Proactief zoeken naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="f2d4c-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f2d4c-142">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="f2d4c-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f2d4c-143">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="f2d4c-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f2d4c-144">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="f2d4c-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f2d4c-145">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="f2d4c-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f2d4c-146">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="f2d4c-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="f2d4c-147">Overzicht van Threat & beveiligingslek</span><span class="sxs-lookup"><span data-stu-id="f2d4c-147">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
