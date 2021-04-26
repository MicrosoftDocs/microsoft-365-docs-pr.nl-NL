---
title: DeviceTvmSoftwareInventory-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over de inventaris van software op uw apparaten in de tabel DeviceTvmSoftwareInventory van het geavanceerde schema voor de jacht.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 5f82684ebb10b72ff83a6789c010f5ec9fa099e7
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024227"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="76740-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="76740-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="76740-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="76740-105">**Applies to:**</span></span>
- <span data-ttu-id="76740-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76740-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="76740-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="76740-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="76740-108">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="76740-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="76740-109">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="76740-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="76740-110">De tabel in het geavanceerde schema bevat de inventaris & Threat & Vulnerability Management van software die momenteel is geïnstalleerd op apparaten in uw netwerk, inclusief informatie over het einde `DeviceTvmSoftwareInventory` van de ondersteuning. [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="76740-110">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="76740-111">U kunt bijvoorbeeld zoeken naar gebeurtenissen met apparaten die zijn geïnstalleerd met een momenteel kwetsbare softwareversie.</span><span class="sxs-lookup"><span data-stu-id="76740-111">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="76740-112">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="76740-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="76740-113">De `DeviceTvmSoftwareInventory` tabel en de tabellen zijn `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` vervangen.</span><span class="sxs-lookup"><span data-stu-id="76740-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="76740-114">De eerste twee tabellen bevatten meer kolommen die u kunt gebruiken om uw vulnerablity-beheeractiviteiten te informeren of om te zoeken naar kwetsbare apparaten.</span><span class="sxs-lookup"><span data-stu-id="76740-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="76740-115">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="76740-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="76740-116">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="76740-116">Column name</span></span> | <span data-ttu-id="76740-117">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="76740-117">Data type</span></span> | <span data-ttu-id="76740-118">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="76740-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="76740-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="76740-119">string</span></span> | <span data-ttu-id="76740-120">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="76740-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="76740-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="76740-121">string</span></span> | <span data-ttu-id="76740-122">Volledig gekwalificeerde domeinnaam (FQDN) van de computer</span><span class="sxs-lookup"><span data-stu-id="76740-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="76740-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="76740-123">string</span></span> | <span data-ttu-id="76740-124">Platform van het besturingssysteem dat op de computer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="76740-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="76740-125">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="76740-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="76740-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="76740-126">string</span></span> | <span data-ttu-id="76740-127">Versie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="76740-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="76740-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="76740-128">string</span></span> | <span data-ttu-id="76740-129">Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="76740-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="76740-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="76740-130">string</span></span> | <span data-ttu-id="76740-131">Naam van de softwareleverancier</span><span class="sxs-lookup"><span data-stu-id="76740-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="76740-132">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="76740-132">string</span></span> | <span data-ttu-id="76740-133">Naam van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="76740-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="76740-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="76740-134">string</span></span> | <span data-ttu-id="76740-135">Versienummer van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="76740-135">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="76740-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="76740-136">string</span></span> | <span data-ttu-id="76740-137">Geeft de levenscyclusfase van het softwareproduct aan ten opzichte van de opgegeven einddatum (EOS) of de einddatum van het softwareproduct (EOL)</span><span class="sxs-lookup"><span data-stu-id="76740-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="76740-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="76740-138">string</span></span> | <span data-ttu-id="76740-139">End-of-support (EOS) of end-of-life (EOL) datum van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="76740-139">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="76740-140">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="76740-140">Related topics</span></span>

- [<span data-ttu-id="76740-141">Proactief op bedreigingen zoeken</span><span class="sxs-lookup"><span data-stu-id="76740-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="76740-142">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="76740-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="76740-143">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="76740-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="76740-144">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="76740-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="76740-145">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="76740-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="76740-146">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="76740-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="76740-147">Overzicht van threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="76740-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)