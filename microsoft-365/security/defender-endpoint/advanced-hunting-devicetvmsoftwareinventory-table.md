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
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408621"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="e0cdd-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="e0cdd-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e0cdd-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e0cdd-105">**Applies to:**</span></span>
- [<span data-ttu-id="e0cdd-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e0cdd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="e0cdd-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="e0cdd-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e0cdd-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e0cdd-109">De tabel in het geavanceerde schema bevat de inventaris voor bedreigings- en kwetsbaarheidsbeheer van software die momenteel is geïnstalleerd op apparaten in uw netwerk, inclusief informatie over het einde `DeviceTvmSoftwareInventory` van de ondersteuning. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="e0cdd-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="e0cdd-110">U kunt bijvoorbeeld zoeken naar gebeurtenissen met apparaten die zijn geïnstalleerd met een momenteel kwetsbare softwareversie.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="e0cdd-111">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="e0cdd-112">DeviceTVMSoftwareInventory bevat alle software die bedreigings- en kwetsbaarheidsbeheer kon matchen met een Common Platform Enumeration (CPE), ongeacht of deze kwetsbaar is of niet.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-112">DeviceTVMSoftwareInventory contains all the software which threat and vulnerability management was able to match to a Common Platform Enumeration (CPE) – whether it is vulnerable or not.</span></span>

>[!NOTE]
><span data-ttu-id="e0cdd-113">De `DeviceTvmSoftwareInventory` tabel en de tabellen zijn `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` vervangen.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="e0cdd-114">De eerste twee tabellen bevatten samen meer kolommen die u kunt gebruiken om uw activiteiten op het gebied van kwetsbaarheidsbeheer te informeren.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="e0cdd-115">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)</span><span class="sxs-lookup"><span data-stu-id="e0cdd-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="e0cdd-116">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="e0cdd-116">Column name</span></span> | <span data-ttu-id="e0cdd-117">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="e0cdd-117">Data type</span></span> | <span data-ttu-id="e0cdd-118">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="e0cdd-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="e0cdd-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e0cdd-119">string</span></span> | <span data-ttu-id="e0cdd-120">Unieke id voor het apparaat in de service.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-120">Unique identifier for the device in the service.</span></span> |
| `DeviceName` | <span data-ttu-id="e0cdd-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e0cdd-121">string</span></span> | <span data-ttu-id="e0cdd-122">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-122">Fully qualified domain name (FQDN) of the device.</span></span> |
| `OSPlatform` | <span data-ttu-id="e0cdd-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e0cdd-123">string</span></span> | <span data-ttu-id="e0cdd-124">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="e0cdd-125">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="e0cdd-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e0cdd-126">string</span></span> | <span data-ttu-id="e0cdd-127">Versie van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-127">Version of the operating system running on the device.</span></span> |
| `OSArchitecture` | <span data-ttu-id="e0cdd-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e0cdd-128">string</span></span> | <span data-ttu-id="e0cdd-129">Architectuur van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-129">Architecture of the operating system running on the device.</span></span> |
| `SoftwareVendor` | <span data-ttu-id="e0cdd-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e0cdd-130">string</span></span> | <span data-ttu-id="e0cdd-131">Naam van de softwareleverancier.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-131">Name of the software vendor.</span></span> |
| `SoftwareName` | <span data-ttu-id="e0cdd-132">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e0cdd-132">string</span></span> | <span data-ttu-id="e0cdd-133">Naam van het softwareproduct.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-133">Name of the software product.</span></span> |
| `SoftwareVersion` | <span data-ttu-id="e0cdd-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e0cdd-134">string</span></span> | <span data-ttu-id="e0cdd-135">Versienummer van het softwareproduct.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-135">Version number of the software product.</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="e0cdd-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e0cdd-136">string</span></span> | <span data-ttu-id="e0cdd-137">Geeft de levenscyclusfase van het softwareproduct aan ten opzichte van de opgegeven einddatum (EOS) of de einddatum (EOL).</span><span class="sxs-lookup"><span data-stu-id="e0cdd-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date.</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="e0cdd-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e0cdd-138">string</span></span> | <span data-ttu-id="e0cdd-139">End-of-support (EOS) of end-of-life (EOL) datum van het softwareproduct.</span><span class="sxs-lookup"><span data-stu-id="e0cdd-139">End-of-support (EOS) or end-of-life (EOL) date of the software product.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e0cdd-140">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e0cdd-140">Related topics</span></span>

- [<span data-ttu-id="e0cdd-141">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="e0cdd-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e0cdd-142">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="e0cdd-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e0cdd-143">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="e0cdd-143">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="e0cdd-144">Overzicht van threat & Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="e0cdd-144">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
