---
title: DeviceInfo-tabel in het geavanceerde jacht schema
description: Meer informatie over het besturingssysteem, de computernaam en andere informatie over de computer in de tabel DeviceInfo van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, machineinfo, DeviceInfo, apparaat, computer, systeem, platform, gebruikers
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
ms.openlocfilehash: 1bb48b4332bc9d60de15bb513f04a503d6a6913b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842712"
---
# <a name="deviceinfo"></a><span data-ttu-id="b8dd7-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="b8dd7-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b8dd7-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b8dd7-105">**Applies to:**</span></span>
- <span data-ttu-id="b8dd7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8dd7-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="b8dd7-107">De `DeviceInfo` tabel in het [Geavanceerde bejachts](advanced-hunting-overview.md) schema bevat informatie over de computers in de organisatie, waaronder versie van het besturingssysteem, actieve gebruikers en computernaam.</span><span class="sxs-lookup"><span data-stu-id="b8dd7-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="b8dd7-108">Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="b8dd7-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="b8dd7-109">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="b8dd7-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b8dd7-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="b8dd7-110">Column name</span></span> | <span data-ttu-id="b8dd7-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="b8dd7-111">Data type</span></span> | <span data-ttu-id="b8dd7-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b8dd7-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b8dd7-113">tijd</span><span class="sxs-lookup"><span data-stu-id="b8dd7-113">datetime</span></span> | <span data-ttu-id="b8dd7-114">De datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="b8dd7-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="b8dd7-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b8dd7-115">string</span></span> | <span data-ttu-id="b8dd7-116">Unieke id voor de computer in de service</span><span class="sxs-lookup"><span data-stu-id="b8dd7-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b8dd7-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b8dd7-117">string</span></span> | <span data-ttu-id="b8dd7-118">FQDN-naam (Fully Qualified Domain Name) van de computer</span><span class="sxs-lookup"><span data-stu-id="b8dd7-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="b8dd7-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b8dd7-119">string</span></span> | <span data-ttu-id="b8dd7-120">Versie van de eindpunt-agent of-sensor die op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="b8dd7-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="b8dd7-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b8dd7-121">string</span></span> | <span data-ttu-id="b8dd7-122">Openbaar IP-adres dat wordt gebruikt door de gehoste computer om verbinding te maken met de Microsoft Defender voor eindpunt-service.</span><span class="sxs-lookup"><span data-stu-id="b8dd7-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="b8dd7-123">Dit kan het IP-adres van de computer, een NAT-apparaat of een proxy zijn</span><span class="sxs-lookup"><span data-stu-id="b8dd7-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="b8dd7-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b8dd7-124">string</span></span> | <span data-ttu-id="b8dd7-125">Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="b8dd7-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="b8dd7-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b8dd7-126">string</span></span> | <span data-ttu-id="b8dd7-127">Platform van het besturingssysteem dat op de computer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b8dd7-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="b8dd7-128">Dit geeft specifieke besturingssystemen aan, waaronder variaties in dezelfde familie, zoals Windows 10 en Windows 7</span><span class="sxs-lookup"><span data-stu-id="b8dd7-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="b8dd7-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b8dd7-129">string</span></span> | <span data-ttu-id="b8dd7-130">Build-versie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="b8dd7-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="b8dd7-131">Boolean</span><span class="sxs-lookup"><span data-stu-id="b8dd7-131">boolean</span></span> | <span data-ttu-id="b8dd7-132">Booleaanse aanduiding of de computer is verbonden met Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b8dd7-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="b8dd7-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b8dd7-133">string</span></span> | <span data-ttu-id="b8dd7-134">Lijst met alle gebruikers die op de computer zijn aangemeld wanneer de gebeurtenis in de JSON-matrix indeling wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="b8dd7-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="b8dd7-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b8dd7-135">string</span></span> | <span data-ttu-id="b8dd7-136">De code van de computer die is toegevoegd via het register</span><span class="sxs-lookup"><span data-stu-id="b8dd7-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="b8dd7-137">lang</span><span class="sxs-lookup"><span data-stu-id="b8dd7-137">long</span></span> | <span data-ttu-id="b8dd7-138">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="b8dd7-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="b8dd7-139">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de naam van het apparaat en de timestamp-kolommen.</span><span class="sxs-lookup"><span data-stu-id="b8dd7-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="b8dd7-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b8dd7-140">string</span></span> | <span data-ttu-id="b8dd7-141">Versie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="b8dd7-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="b8dd7-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b8dd7-142">string</span></span> | <span data-ttu-id="b8dd7-143">Computergroep van de computer.</span><span class="sxs-lookup"><span data-stu-id="b8dd7-143">Machine group of the machine.</span></span> <span data-ttu-id="b8dd7-144">Deze groep wordt gebruikt door toegangsbeheer op basis van rollen om de toegang tot de computer te bepalen.</span><span class="sxs-lookup"><span data-stu-id="b8dd7-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b8dd7-145">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b8dd7-145">Related topics</span></span>
- [<span data-ttu-id="b8dd7-146">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b8dd7-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b8dd7-147">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="b8dd7-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b8dd7-148">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="b8dd7-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b8dd7-149">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="b8dd7-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b8dd7-150">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="b8dd7-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b8dd7-151">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="b8dd7-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
