---
title: DeviceTvmSoftwareInventory-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over de inventaris van software op uw apparaten in de tabel DeviceTvmSoftwareInventory van het geavanceerde schema voor de jacht.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fc9e5fb29518207c5360d5fbe29b8b4848d350e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060014"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="a0da3-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="a0da3-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a0da3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a0da3-105">**Applies to:**</span></span>
- [<span data-ttu-id="a0da3-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="a0da3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="a0da3-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="a0da3-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a0da3-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="a0da3-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="a0da3-109">De tabel in het geavanceerde schema bevat de inventaris & Threat & Vulnerability Management van software die momenteel is geïnstalleerd op apparaten in uw netwerk, inclusief informatie over het einde `DeviceTvmSoftwareInventory` van de ondersteuning. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="a0da3-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="a0da3-110">U kunt bijvoorbeeld zoeken naar gebeurtenissen met apparaten die zijn geïnstalleerd met een momenteel kwetsbare softwareversie.</span><span class="sxs-lookup"><span data-stu-id="a0da3-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="a0da3-111">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="a0da3-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="a0da3-112">De `DeviceTvmSoftwareInventory` tabel en de tabellen zijn `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` vervangen.</span><span class="sxs-lookup"><span data-stu-id="a0da3-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="a0da3-113">De eerste twee tabellen bevatten samen meer kolommen die u kunt gebruiken om uw activiteiten op het gebied van kwetsbaarheidsbeheer te informeren.</span><span class="sxs-lookup"><span data-stu-id="a0da3-113">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="a0da3-114">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)</span><span class="sxs-lookup"><span data-stu-id="a0da3-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="a0da3-115">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="a0da3-115">Column name</span></span> | <span data-ttu-id="a0da3-116">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="a0da3-116">Data type</span></span> | <span data-ttu-id="a0da3-117">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="a0da3-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="a0da3-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a0da3-118">string</span></span> | <span data-ttu-id="a0da3-119">Unieke id voor het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="a0da3-119">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a0da3-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a0da3-120">string</span></span> | <span data-ttu-id="a0da3-121">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat</span><span class="sxs-lookup"><span data-stu-id="a0da3-121">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="a0da3-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a0da3-122">string</span></span> | <span data-ttu-id="a0da3-123">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a0da3-123">Platform of the operating system running on the device.</span></span> <span data-ttu-id="a0da3-124">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="a0da3-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="a0da3-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a0da3-125">string</span></span> | <span data-ttu-id="a0da3-126">Versie van het besturingssysteem dat op het apparaat wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="a0da3-126">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="a0da3-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a0da3-127">string</span></span> | <span data-ttu-id="a0da3-128">Architectuur van het besturingssysteem dat op het apparaat wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="a0da3-128">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="a0da3-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a0da3-129">string</span></span> | <span data-ttu-id="a0da3-130">Naam van de softwareleverancier</span><span class="sxs-lookup"><span data-stu-id="a0da3-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="a0da3-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a0da3-131">string</span></span> | <span data-ttu-id="a0da3-132">Naam van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="a0da3-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="a0da3-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a0da3-133">string</span></span> | <span data-ttu-id="a0da3-134">Versienummer van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="a0da3-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="a0da3-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a0da3-135">string</span></span> | <span data-ttu-id="a0da3-136">Geeft de levenscyclusfase van het softwareproduct aan ten opzichte van de opgegeven einddatum (EOS) of de einddatum van het softwareproduct (EOL)</span><span class="sxs-lookup"><span data-stu-id="a0da3-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="a0da3-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a0da3-137">string</span></span> | <span data-ttu-id="a0da3-138">End-of-support (EOS) of end-of-life (EOL) datum van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="a0da3-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="a0da3-139">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a0da3-139">Related topics</span></span>

- [<span data-ttu-id="a0da3-140">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="a0da3-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a0da3-141">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="a0da3-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a0da3-142">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="a0da3-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="a0da3-143">Overzicht van threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="a0da3-143">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)

