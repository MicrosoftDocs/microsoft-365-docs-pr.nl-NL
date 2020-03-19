---
title: DeviceInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over besturingssysteem, computernaam en andere machine-informatie in de tabel DeviceInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreiging jacht, cyber dreiging jacht, Microsoft bedreiging bescherming, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, machineinfo, DeviceInfo, apparaat, machine, OS, platform Gebruikers
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
ms.openlocfilehash: 71bd9e9ff1dfb17e4a9266d9ee351799e18888c9
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42809538"
---
# <a name="deviceinfo"></a><span data-ttu-id="44ee6-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="44ee6-104">DeviceInfo</span></span>

<span data-ttu-id="44ee6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="44ee6-105">**Applies to:**</span></span>
- <span data-ttu-id="44ee6-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="44ee6-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="44ee6-107">De `DeviceInfo` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over machines in de organisatie, waaronder de OS-versie, actieve gebruikers en de naam van de computer.</span><span class="sxs-lookup"><span data-stu-id="44ee6-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="44ee6-108">Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="44ee6-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="44ee6-109">Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="44ee6-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="44ee6-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="44ee6-110">Column name</span></span> | <span data-ttu-id="44ee6-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="44ee6-111">Data type</span></span> | <span data-ttu-id="44ee6-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="44ee6-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="44ee6-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="44ee6-113">datetime</span></span> | <span data-ttu-id="44ee6-114">Datum en tijdstip waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="44ee6-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="44ee6-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44ee6-115">string</span></span> | <span data-ttu-id="44ee6-116">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="44ee6-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="44ee6-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44ee6-117">string</span></span> | <span data-ttu-id="44ee6-118">Volledig gekwalificeerde domeinnaam (FQDN) van de machine</span><span class="sxs-lookup"><span data-stu-id="44ee6-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="44ee6-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44ee6-119">string</span></span> | <span data-ttu-id="44ee6-120">Versie van de endpoint-agent of sensor die op de machine wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="44ee6-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="44ee6-121">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44ee6-121">string</span></span> | <span data-ttu-id="44ee6-122">Openbaar IP-adres dat door de aanboordmachine wordt gebruikt om verbinding te maken met de Microsoft Defender ATP-service.</span><span class="sxs-lookup"><span data-stu-id="44ee6-122">Public IP address used by the onboarded machine to connect to the Microsoft Defender ATP service.</span></span> <span data-ttu-id="44ee6-123">Dit kan het IP-adres van de machine zelf, een NAT-apparaat of een proxy zijn</span><span class="sxs-lookup"><span data-stu-id="44ee6-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="44ee6-124">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44ee6-124">string</span></span> | <span data-ttu-id="44ee6-125">Architectuur van het besturingssysteem dat op de machine draait</span><span class="sxs-lookup"><span data-stu-id="44ee6-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="44ee6-126">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44ee6-126">string</span></span> | <span data-ttu-id="44ee6-127">Platform van het besturingssysteem dat op de machine draait.</span><span class="sxs-lookup"><span data-stu-id="44ee6-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="44ee6-128">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7</span><span class="sxs-lookup"><span data-stu-id="44ee6-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="44ee6-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44ee6-129">string</span></span> | <span data-ttu-id="44ee6-130">Build versie van het besturingssysteem draait op de machine</span><span class="sxs-lookup"><span data-stu-id="44ee6-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="44ee6-131">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="44ee6-131">boolean</span></span> | <span data-ttu-id="44ee6-132">Booleaanse indicator of de machine is verbonden met de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="44ee6-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="44ee6-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44ee6-133">string</span></span> | <span data-ttu-id="44ee6-134">Lijst met alle gebruikers die op het moment van de gebeurtenis op de machine zijn aangemeld in JSON-arrayindeling</span><span class="sxs-lookup"><span data-stu-id="44ee6-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="44ee6-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44ee6-135">string</span></span> | <span data-ttu-id="44ee6-136">Machinetag toegevoegd via het register</span><span class="sxs-lookup"><span data-stu-id="44ee6-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="44ee6-137">Lange</span><span class="sxs-lookup"><span data-stu-id="44ee6-137">long</span></span> | <span data-ttu-id="44ee6-138">Gebeurtenis-id op basis van een herhalingsteller.</span><span class="sxs-lookup"><span data-stu-id="44ee6-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="44ee6-139">Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp</span><span class="sxs-lookup"><span data-stu-id="44ee6-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="44ee6-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44ee6-140">string</span></span> | <span data-ttu-id="44ee6-141">Versie van het besturingssysteem die op de machine draait</span><span class="sxs-lookup"><span data-stu-id="44ee6-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="44ee6-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44ee6-142">string</span></span> | <span data-ttu-id="44ee6-143">Machinegroep van de machine.</span><span class="sxs-lookup"><span data-stu-id="44ee6-143">Machine group of the machine.</span></span> <span data-ttu-id="44ee6-144">Deze groep wordt gebruikt door op rollen gebaseerd toegangscontrole om de toegang tot de machine te bepalen</span><span class="sxs-lookup"><span data-stu-id="44ee6-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="44ee6-145">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="44ee6-145">Related topics</span></span>
- [<span data-ttu-id="44ee6-146">Proactief op zoek naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="44ee6-146">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="44ee6-147">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="44ee6-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="44ee6-148">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="44ee6-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="44ee6-149">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="44ee6-149">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="44ee6-150">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="44ee6-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="44ee6-151">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="44ee6-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
