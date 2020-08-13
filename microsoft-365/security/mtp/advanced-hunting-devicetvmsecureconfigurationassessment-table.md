---
title: DeviceTvmSecureConfigurationAssessment-tabel in het geavanceerde jacht schema
description: Meer informatie over bedreiging & beveiligings evaluatie gebeurtenissen in de tabel DeviceTvmSecureConfigurationAssessment van het schema geavanceerde jacht. Deze gebeurtenissen geven informatie over de computer en ook van Beveiligingsconfiguratie Details, van invloed tot informatie over naleving.
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 38f5cefb9095ca6c1f628f25a5ed374516c2b0a4
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648999"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="b08f5-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="b08f5-105">DeviceTvmSecureConfigurationAssessment</span></span>

<span data-ttu-id="b08f5-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b08f5-106">**Applies to:**</span></span>
- <span data-ttu-id="b08f5-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b08f5-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="b08f5-108">Elke rij in de `DeviceTvmSecureConfigurationAssessment` tabel bevat een beoordelings gebeurtenis voor een bepaalde beveiligingsconfiguratie, van [bedreiging & beveiligingsbeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="b08f5-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="b08f5-109">Gebruik deze naslag voor de laatste beoordelings resultaten en bepaal of apparaten compatibel zijn.</span><span class="sxs-lookup"><span data-stu-id="b08f5-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="b08f5-110">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="b08f5-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b08f5-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="b08f5-111">Column name</span></span> | <span data-ttu-id="b08f5-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="b08f5-112">Data type</span></span> | <span data-ttu-id="b08f5-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b08f5-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="b08f5-114">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b08f5-114">string</span></span> | <span data-ttu-id="b08f5-115">Unieke id voor de computer in de service</span><span class="sxs-lookup"><span data-stu-id="b08f5-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b08f5-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b08f5-116">string</span></span> | <span data-ttu-id="b08f5-117">FQDN-naam (Fully Qualified Domain Name) van de computer</span><span class="sxs-lookup"><span data-stu-id="b08f5-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="b08f5-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b08f5-118">string</span></span> | <span data-ttu-id="b08f5-119">Platform van het besturingssysteem dat op de computer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b08f5-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="b08f5-120">Dit geeft specifieke besturingssystemen aan, met inbegrip van variaties in dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="b08f5-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="b08f5-121">tijd</span><span class="sxs-lookup"><span data-stu-id="b08f5-121">datetime</span></span> | <span data-ttu-id="b08f5-122">De datum en tijd waarop de record is gegenereerd</span><span class="sxs-lookup"><span data-stu-id="b08f5-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="b08f5-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b08f5-123">string</span></span> | <span data-ttu-id="b08f5-124">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="b08f5-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="b08f5-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b08f5-125">string</span></span> | <span data-ttu-id="b08f5-126">Categorie of groepering waartoe de configuratie behoort: toepassing, besturingssysteem, netwerk, accounts, beveiliging besturingselement</span><span class="sxs-lookup"><span data-stu-id="b08f5-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="b08f5-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b08f5-127">string</span></span> | <span data-ttu-id="b08f5-128">Subcategorie of subgroep waartoe de configuratie behoort.</span><span class="sxs-lookup"><span data-stu-id="b08f5-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="b08f5-129">In veel gevallen bevat dit een beschrijving van specifieke functies of functies.</span><span class="sxs-lookup"><span data-stu-id="b08f5-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="b08f5-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b08f5-130">string</span></span> | <span data-ttu-id="b08f5-131">Geclassificeerde impact van de configuratie voor de totale configuratie Score (1-10)</span><span class="sxs-lookup"><span data-stu-id="b08f5-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="b08f5-132">Boolean</span><span class="sxs-lookup"><span data-stu-id="b08f5-132">boolean</span></span> | <span data-ttu-id="b08f5-133">Geeft aan of de configuratie of het beleid correct is geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="b08f5-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b08f5-134">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b08f5-134">Related topics</span></span>

- [<span data-ttu-id="b08f5-135">Proactief zoeken naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="b08f5-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b08f5-136">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="b08f5-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b08f5-137">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="b08f5-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b08f5-138">Jacht op apparaten, e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="b08f5-138">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b08f5-139">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="b08f5-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b08f5-140">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="b08f5-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b08f5-141">Overzicht van Threat & beveiligingslek</span><span class="sxs-lookup"><span data-stu-id="b08f5-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
