---
title: DeviceInfo-tabel in het geavanceerde schema voor zoeken
description: Meer informatie over het besturingssysteem, de computernaam en andere computergegevens vindt u in de tabel DeviceInfo van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machineinfo, DeviceInfo, device, machine, OS, platform, users
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: e445902ee83b734f84d02607905413a14c016b8f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931276"
---
# <a name="deviceinfo"></a><span data-ttu-id="aec26-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="aec26-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="aec26-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="aec26-105">**Applies to:**</span></span>
- <span data-ttu-id="aec26-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aec26-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="aec26-107">De `DeviceInfo` tabel in het geavanceerde [zoekschema](advanced-hunting-overview.md) bevat informatie over machines in de organisatie, zoals de versie van het besturingssysteem, actieve gebruikers en de naam van de computer.</span><span class="sxs-lookup"><span data-stu-id="aec26-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="aec26-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="aec26-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="aec26-109">Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="aec26-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="aec26-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="aec26-110">Column name</span></span> | <span data-ttu-id="aec26-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="aec26-111">Data type</span></span> | <span data-ttu-id="aec26-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="aec26-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="aec26-113">datetime</span><span class="sxs-lookup"><span data-stu-id="aec26-113">datetime</span></span> | <span data-ttu-id="aec26-114">Datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="aec26-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="aec26-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aec26-115">string</span></span> | <span data-ttu-id="aec26-116">Unieke id voor de computer in de service</span><span class="sxs-lookup"><span data-stu-id="aec26-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="aec26-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aec26-117">string</span></span> | <span data-ttu-id="aec26-118">FQDN (Fully Qualified Domain Name) van de computer</span><span class="sxs-lookup"><span data-stu-id="aec26-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="aec26-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aec26-119">string</span></span> | <span data-ttu-id="aec26-120">Versie van de eindpuntagent of sensor die op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="aec26-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="aec26-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aec26-121">string</span></span> | <span data-ttu-id="aec26-122">Het openbare IP-adres dat door de onboarded-computer wordt gebruikt om verbinding te maken met de Microsoft Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="aec26-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="aec26-123">Dit kan het IP-adres zijn van de computer zelf, een NAT-apparaat of een proxy</span><span class="sxs-lookup"><span data-stu-id="aec26-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="aec26-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aec26-124">string</span></span> | <span data-ttu-id="aec26-125">Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="aec26-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="aec26-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aec26-126">string</span></span> | <span data-ttu-id="aec26-127">Platform van het besturingssysteem dat op de computer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="aec26-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="aec26-128">Dit geeft specifieke besturingssystemen aan, inclusief variaties binnen dezelfde familie, zoals Windows 10 en Windows 7</span><span class="sxs-lookup"><span data-stu-id="aec26-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="aec26-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aec26-129">string</span></span> | <span data-ttu-id="aec26-130">Buildversie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="aec26-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="aec26-131">boolean</span><span class="sxs-lookup"><span data-stu-id="aec26-131">boolean</span></span> | <span data-ttu-id="aec26-132">Booleaanse indicator of de computer is verbonden met Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="aec26-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="aec26-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aec26-133">string</span></span> | <span data-ttu-id="aec26-134">Lijst met alle gebruikers die op de computer zijn aangemeld op het moment van de gebeurtenis in de JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="aec26-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="aec26-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aec26-135">string</span></span> | <span data-ttu-id="aec26-136">Machinetag toegevoegd via het register</span><span class="sxs-lookup"><span data-stu-id="aec26-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="aec26-137">lang</span><span class="sxs-lookup"><span data-stu-id="aec26-137">long</span></span> | <span data-ttu-id="aec26-138">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="aec26-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="aec26-139">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen Apparaatnaam en Tijdstempel</span><span class="sxs-lookup"><span data-stu-id="aec26-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="aec26-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aec26-140">string</span></span> | <span data-ttu-id="aec26-141">Versie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="aec26-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="aec26-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="aec26-142">string</span></span> | <span data-ttu-id="aec26-143">De machinegroep van de computer.</span><span class="sxs-lookup"><span data-stu-id="aec26-143">Machine group of the machine.</span></span> <span data-ttu-id="aec26-144">Deze groep wordt gebruikt door toegangsbeheer op basis van rollen om de toegang tot de computer te bepalen</span><span class="sxs-lookup"><span data-stu-id="aec26-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="aec26-145">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="aec26-145">Related topics</span></span>
- [<span data-ttu-id="aec26-146">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="aec26-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="aec26-147">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="aec26-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="aec26-148">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="aec26-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="aec26-149">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="aec26-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="aec26-150">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="aec26-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="aec26-151">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="aec26-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
