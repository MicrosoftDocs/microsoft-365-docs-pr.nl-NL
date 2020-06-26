---
title: DeviceInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over besturingssysteem, computernaam en andere machine-informatie in de DeviceInfo-tabel van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, machineinfo, DeviceInfo, apparaat, machine, OS, platform, gebruikers
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
ms.openlocfilehash: 526e210a472862593f2652e9b2b21957702c48f0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899277"
---
# <a name="deviceinfo"></a><span data-ttu-id="985da-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="985da-104">DeviceInfo</span></span>

<span data-ttu-id="985da-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="985da-105">**Applies to:**</span></span>
- <span data-ttu-id="985da-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="985da-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="985da-107">De `DeviceInfo` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over machines in de organisatie, waaronder de OS-versie, actieve gebruikers en de computernaam.</span><span class="sxs-lookup"><span data-stu-id="985da-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="985da-108">Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="985da-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="985da-109">Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.</span><span class="sxs-lookup"><span data-stu-id="985da-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="985da-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="985da-110">Column name</span></span> | <span data-ttu-id="985da-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="985da-111">Data type</span></span> | <span data-ttu-id="985da-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="985da-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="985da-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="985da-113">datetime</span></span> | <span data-ttu-id="985da-114">Datum en tijdstip waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="985da-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="985da-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="985da-115">string</span></span> | <span data-ttu-id="985da-116">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="985da-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="985da-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="985da-117">string</span></span> | <span data-ttu-id="985da-118">Volledig gekwalificeerde domeinnaam (FQDN) van de machine</span><span class="sxs-lookup"><span data-stu-id="985da-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="985da-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="985da-119">string</span></span> | <span data-ttu-id="985da-120">Versie van de eindpuntagent of -sensor die op de machine wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="985da-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="985da-121">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="985da-121">string</span></span> | <span data-ttu-id="985da-122">Openbaar IP-adres dat door de ingebouwde machine wordt gebruikt om verbinding te maken met de Microsoft Defender ATP-service.</span><span class="sxs-lookup"><span data-stu-id="985da-122">Public IP address used by the onboarded machine to connect to the Microsoft Defender ATP service.</span></span> <span data-ttu-id="985da-123">Dit kan het IP-adres zijn van de machine zelf, een NAT-apparaat of een proxy</span><span class="sxs-lookup"><span data-stu-id="985da-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="985da-124">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="985da-124">string</span></span> | <span data-ttu-id="985da-125">Architectuur van het besturingssysteem dat op de machine draait</span><span class="sxs-lookup"><span data-stu-id="985da-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="985da-126">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="985da-126">string</span></span> | <span data-ttu-id="985da-127">Platform van het besturingssysteem dat op de machine draait.</span><span class="sxs-lookup"><span data-stu-id="985da-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="985da-128">Dit duidt op specifieke besturingssystemen, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7</span><span class="sxs-lookup"><span data-stu-id="985da-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="985da-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="985da-129">string</span></span> | <span data-ttu-id="985da-130">Bouwversie van het besturingssysteem dat op de machine draait</span><span class="sxs-lookup"><span data-stu-id="985da-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="985da-131">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="985da-131">boolean</span></span> | <span data-ttu-id="985da-132">Booleaanse indicator van de vraag of de machine is verbonden met de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="985da-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="985da-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="985da-133">string</span></span> | <span data-ttu-id="985da-134">Lijst van alle gebruikers die op het moment van de gebeurtenis op de machine zijn aangemeld in de JSON-arrayindeling</span><span class="sxs-lookup"><span data-stu-id="985da-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="985da-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="985da-135">string</span></span> | <span data-ttu-id="985da-136">Machinetag toegevoegd via het register</span><span class="sxs-lookup"><span data-stu-id="985da-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="985da-137">Lange</span><span class="sxs-lookup"><span data-stu-id="985da-137">long</span></span> | <span data-ttu-id="985da-138">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="985da-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="985da-139">Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp</span><span class="sxs-lookup"><span data-stu-id="985da-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="985da-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="985da-140">string</span></span> | <span data-ttu-id="985da-141">Versie van het besturingssysteem dat op de machine draait</span><span class="sxs-lookup"><span data-stu-id="985da-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="985da-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="985da-142">string</span></span> | <span data-ttu-id="985da-143">Machinegroep van de machine.</span><span class="sxs-lookup"><span data-stu-id="985da-143">Machine group of the machine.</span></span> <span data-ttu-id="985da-144">Deze groep wordt gebruikt door op rollen gebaseerde toegangscontrole om de toegang tot de machine te bepalen</span><span class="sxs-lookup"><span data-stu-id="985da-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="985da-145">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="985da-145">Related topics</span></span>
- [<span data-ttu-id="985da-146">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="985da-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="985da-147">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="985da-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="985da-148">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="985da-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="985da-149">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="985da-149">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="985da-150">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="985da-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="985da-151">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="985da-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
