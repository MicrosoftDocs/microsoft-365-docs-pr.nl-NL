---
title: DeviceTvmSecureConfigurationAssessment tabel in het geavanceerde jachtschema
description: Meer informatie over beveiligingsbeoordelingsgebeurtenissen voor het & van vulnerability management vindt u in de tabel DeviceTvmSecureConfigurationAssessment van het geavanceerde jachtschema. Deze gebeurtenissen bieden machine-informatie, beveiligingsconfiguratiegegevens, impact en nalevingsinformatie.
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-bedreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, bedreiging & kwetsbaarheidsbeheer, TVM, apparaatbeheer, beveiligingsconfiguratie, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: ade218a440f8e7db223460e95363eae2cb659622
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327951"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="2ecc1-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="2ecc1-105">DeviceTvmSecureConfigurationAssessment</span></span>

<span data-ttu-id="2ecc1-106">**Geldt voor:**</span><span class="sxs-lookup"><span data-stu-id="2ecc1-106">**Applies to:**</span></span>
- <span data-ttu-id="2ecc1-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2ecc1-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="2ecc1-108">Elke rij in de `DeviceTvmSecureConfigurationAssessment` tabel bevat een beoordelingsgebeurtenis voor een specifieke beveiligingsconfiguratie van [Threat & Vulnerability Management.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="2ecc1-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="2ecc1-109">Gebruik deze verwijzing om de meest recente beoordelingsresultaten te controleren en te bepalen of apparaten compatibel zijn.</span><span class="sxs-lookup"><span data-stu-id="2ecc1-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="2ecc1-110">Voor informatie over andere tabellen in de geavanceerde jacht schema, zie [de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2ecc1-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2ecc1-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="2ecc1-111">Column name</span></span> | <span data-ttu-id="2ecc1-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="2ecc1-112">Data type</span></span> | <span data-ttu-id="2ecc1-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2ecc1-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="2ecc1-114">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2ecc1-114">string</span></span> | <span data-ttu-id="2ecc1-115">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="2ecc1-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2ecc1-116">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2ecc1-116">string</span></span> | <span data-ttu-id="2ecc1-117">Volledig gekwalificeerde domeinnaam (FQDN) van de machine</span><span class="sxs-lookup"><span data-stu-id="2ecc1-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="2ecc1-118">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2ecc1-118">string</span></span> | <span data-ttu-id="2ecc1-119">Platform van het besturingssysteem dat op de machine draait.</span><span class="sxs-lookup"><span data-stu-id="2ecc1-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="2ecc1-120">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="2ecc1-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="2ecc1-121">Datetime</span><span class="sxs-lookup"><span data-stu-id="2ecc1-121">datetime</span></span> | <span data-ttu-id="2ecc1-122">Datum en tijd waarop de record is gegenereerd</span><span class="sxs-lookup"><span data-stu-id="2ecc1-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="2ecc1-123">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2ecc1-123">string</span></span> | <span data-ttu-id="2ecc1-124">Unieke id voor een specifieke configuratie</span><span class="sxs-lookup"><span data-stu-id="2ecc1-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="2ecc1-125">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2ecc1-125">string</span></span> | <span data-ttu-id="2ecc1-126">Categorie of groepering waartoe de configuratie behoort: Toepassing, BE, Netwerk, Accounts, Beveiligingsbesturingselementen</span><span class="sxs-lookup"><span data-stu-id="2ecc1-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="2ecc1-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2ecc1-127">string</span></span> | <span data-ttu-id="2ecc1-128">Subcategorie of subgroep waartoe de configuratie behoort.</span><span class="sxs-lookup"><span data-stu-id="2ecc1-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="2ecc1-129">In veel gevallen worden specifieke mogelijkheden of functies beschreven.</span><span class="sxs-lookup"><span data-stu-id="2ecc1-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="2ecc1-130">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2ecc1-130">string</span></span> | <span data-ttu-id="2ecc1-131">Nominale impact van de configuratie op de totale configuratiescore (1-10)</span><span class="sxs-lookup"><span data-stu-id="2ecc1-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="2ecc1-132">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="2ecc1-132">boolean</span></span> | <span data-ttu-id="2ecc1-133">Geeft aan of de configuratie of het beleid correct is geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="2ecc1-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2ecc1-134">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2ecc1-134">Related topics</span></span>

- [<span data-ttu-id="2ecc1-135">Proactief op zoek naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="2ecc1-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2ecc1-136">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="2ecc1-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2ecc1-137">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="2ecc1-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2ecc1-138">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="2ecc1-138">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2ecc1-139">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="2ecc1-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2ecc1-140">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="2ecc1-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="2ecc1-141">Overzicht van Threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="2ecc1-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
