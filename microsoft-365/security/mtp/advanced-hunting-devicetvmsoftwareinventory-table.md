---
title: DeviceTvmSoftwareInventory table in the advanced hunting schema
description: Meer informatie over de voorraad van software op uw apparaten kunt u vinden in de tabel DeviceTvmSoftwareInventory van het geavanceerde schema voor het zoeken.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: maccruz
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5edb6205e0392441163060aa7181ca031e1fbb0d
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50416786"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="7ee91-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="7ee91-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7ee91-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7ee91-105">**Applies to:**</span></span>
- <span data-ttu-id="7ee91-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ee91-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="7ee91-107">Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht.</span><span class="sxs-lookup"><span data-stu-id="7ee91-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7ee91-108">Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.</span><span class="sxs-lookup"><span data-stu-id="7ee91-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="7ee91-109">De tabel in het geavanceerde schema voor zoeken bevat de inventaris van & Beveiligingsprobleembeheer van software die momenteel is geïnstalleerd op apparaten in uw netwerk, inclusief informatie over het beëindigen van `DeviceTvmSoftwareInventory` de ondersteuning. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="7ee91-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="7ee91-110">U kunt bijvoorbeeld zoeken naar gebeurtenissen met apparaten die zijn geïnstalleerd met een momenteel kwetsbaar softwareversie.</span><span class="sxs-lookup"><span data-stu-id="7ee91-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="7ee91-111">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="7ee91-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="7ee91-112">De `DeviceTvmSoftwareInventory` tabel is vervangen door de `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabellen.</span><span class="sxs-lookup"><span data-stu-id="7ee91-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="7ee91-113">De eerste twee tabellen bevatten meer kolommen die u kunt gebruiken om uw activiteiten in het beheer van vulnerabliteit te informeren of te zoeken naar kwetsbaar apparaten.</span><span class="sxs-lookup"><span data-stu-id="7ee91-113">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="7ee91-114">Zie het geavanceerde zoekschema voor informatie over andere tabellen in het geavanceerde schema voor [het zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="7ee91-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7ee91-115">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="7ee91-115">Column name</span></span> | <span data-ttu-id="7ee91-116">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="7ee91-116">Data type</span></span> | <span data-ttu-id="7ee91-117">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="7ee91-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="7ee91-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7ee91-118">string</span></span> | <span data-ttu-id="7ee91-119">Unieke id voor de computer in de service</span><span class="sxs-lookup"><span data-stu-id="7ee91-119">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="7ee91-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7ee91-120">string</span></span> | <span data-ttu-id="7ee91-121">FQDN (Fully Qualified Domain Name) van de computer</span><span class="sxs-lookup"><span data-stu-id="7ee91-121">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="7ee91-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7ee91-122">string</span></span> | <span data-ttu-id="7ee91-123">Platform van het besturingssysteem dat op de computer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="7ee91-123">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="7ee91-124">Dit geeft specifieke besturingssystemen aan, inclusief variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="7ee91-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="7ee91-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7ee91-125">string</span></span> | <span data-ttu-id="7ee91-126">Versie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="7ee91-126">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="7ee91-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7ee91-127">string</span></span> | <span data-ttu-id="7ee91-128">Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="7ee91-128">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="7ee91-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7ee91-129">string</span></span> | <span data-ttu-id="7ee91-130">Naam van de softwareleverancier</span><span class="sxs-lookup"><span data-stu-id="7ee91-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="7ee91-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7ee91-131">string</span></span> | <span data-ttu-id="7ee91-132">Naam van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="7ee91-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="7ee91-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7ee91-133">string</span></span> | <span data-ttu-id="7ee91-134">Versienummer van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="7ee91-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="7ee91-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7ee91-135">string</span></span> | <span data-ttu-id="7ee91-136">Geeft de levenscyclus van het softwareproduct aan ten opzichte van de opgegeven einddatum (EOS) of het einde van de levensduur (EOL)</span><span class="sxs-lookup"><span data-stu-id="7ee91-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="7ee91-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7ee91-137">string</span></span> | <span data-ttu-id="7ee91-138">Einde van de ondersteuning (EOS) of einddatum (EOL) van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="7ee91-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="7ee91-139">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7ee91-139">Related topics</span></span>

- [<span data-ttu-id="7ee91-140">Proactief zoeken naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="7ee91-140">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7ee91-141">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="7ee91-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7ee91-142">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="7ee91-142">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7ee91-143">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="7ee91-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7ee91-144">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="7ee91-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7ee91-145">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="7ee91-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="7ee91-146">Overzicht van risicobeheer & beveiligingsprobleem</span><span class="sxs-lookup"><span data-stu-id="7ee91-146">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
