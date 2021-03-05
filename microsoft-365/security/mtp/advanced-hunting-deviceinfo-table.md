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
ms.openlocfilehash: 53948f3d470fb85ddfda8dbcf5b64024755ca50e
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461614"
---
# <a name="deviceinfo"></a><span data-ttu-id="8eb45-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="8eb45-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8eb45-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8eb45-105">**Applies to:**</span></span>
- <span data-ttu-id="8eb45-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8eb45-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="8eb45-107">De tabel in het geavanceerde zoekschema bevat informatie over apparaten in de organisatie, zoals de `DeviceInfo` besturingssysteemversie, actieve gebruikers en de naam van de computer. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8eb45-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="8eb45-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="8eb45-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="8eb45-109">Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="8eb45-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8eb45-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="8eb45-110">Column name</span></span> | <span data-ttu-id="8eb45-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="8eb45-111">Data type</span></span> | <span data-ttu-id="8eb45-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="8eb45-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8eb45-113">datetime</span><span class="sxs-lookup"><span data-stu-id="8eb45-113">datetime</span></span> | <span data-ttu-id="8eb45-114">Datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="8eb45-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="8eb45-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8eb45-115">string</span></span> | <span data-ttu-id="8eb45-116">Unieke id voor de computer in de service</span><span class="sxs-lookup"><span data-stu-id="8eb45-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="8eb45-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8eb45-117">string</span></span> | <span data-ttu-id="8eb45-118">FQDN (Fully Qualified Domain Name) van de computer</span><span class="sxs-lookup"><span data-stu-id="8eb45-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="8eb45-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8eb45-119">string</span></span> | <span data-ttu-id="8eb45-120">Versie van de eindpuntagent of sensor die op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="8eb45-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="8eb45-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8eb45-121">string</span></span> | <span data-ttu-id="8eb45-122">Het openbare IP-adres dat door de onboarded-computer wordt gebruikt om verbinding te maken met de Microsoft Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="8eb45-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="8eb45-123">Dit kan het IP-adres zijn van de computer zelf, een NAT-apparaat of een proxy</span><span class="sxs-lookup"><span data-stu-id="8eb45-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="8eb45-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8eb45-124">string</span></span> | <span data-ttu-id="8eb45-125">Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="8eb45-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="8eb45-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8eb45-126">string</span></span> | <span data-ttu-id="8eb45-127">Platform van het besturingssysteem dat op de computer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="8eb45-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="8eb45-128">Dit geeft specifieke besturingssystemen aan, inclusief variaties binnen dezelfde familie, zoals Windows 10 en Windows 7</span><span class="sxs-lookup"><span data-stu-id="8eb45-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="8eb45-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8eb45-129">string</span></span> | <span data-ttu-id="8eb45-130">Buildversie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="8eb45-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="8eb45-131">boolean</span><span class="sxs-lookup"><span data-stu-id="8eb45-131">boolean</span></span> | <span data-ttu-id="8eb45-132">Booleaanse indicator of de computer is verbonden met Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8eb45-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="8eb45-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8eb45-133">string</span></span> | <span data-ttu-id="8eb45-134">Unieke id voor het apparaat in Azure AD</span><span class="sxs-lookup"><span data-stu-id="8eb45-134">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="8eb45-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8eb45-135">string</span></span> | <span data-ttu-id="8eb45-136">Lijst met alle gebruikers die op de computer zijn aangemeld op het moment van de gebeurtenis in de JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="8eb45-136">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="8eb45-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8eb45-137">string</span></span> | <span data-ttu-id="8eb45-138">Machinetag toegevoegd via het register</span><span class="sxs-lookup"><span data-stu-id="8eb45-138">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="8eb45-139">lang</span><span class="sxs-lookup"><span data-stu-id="8eb45-139">long</span></span> | <span data-ttu-id="8eb45-140">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="8eb45-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="8eb45-141">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen Apparaatnaam en Tijdstempel</span><span class="sxs-lookup"><span data-stu-id="8eb45-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="8eb45-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8eb45-142">string</span></span> | <span data-ttu-id="8eb45-143">Aanvullende informatie over de gebeurtenis in de JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="8eb45-143">Additional information about the event in JSON array format</span></span> |
| `OSVersion` | <span data-ttu-id="8eb45-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8eb45-144">string</span></span> | <span data-ttu-id="8eb45-145">Versie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="8eb45-145">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="8eb45-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8eb45-146">string</span></span> | <span data-ttu-id="8eb45-147">De machinegroep van de computer.</span><span class="sxs-lookup"><span data-stu-id="8eb45-147">Machine group of the machine.</span></span> <span data-ttu-id="8eb45-148">Deze groep wordt gebruikt door toegangsbeheer op basis van rollen om de toegang tot de computer te bepalen</span><span class="sxs-lookup"><span data-stu-id="8eb45-148">This group is used by role-based access control to determine access to the machine</span></span> |

<span data-ttu-id="8eb45-149">De `DeviceInfo` tabel bevat apparaatinformatie op basis van heartbeats. Dit zijn periodieke rapporten of signalen van een apparaat.</span><span class="sxs-lookup"><span data-stu-id="8eb45-149">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="8eb45-150">Elke vijftien minuten verzendt het apparaat een gedeeltelijke heartbeat die kenmerken bevat die vaak worden veranderd, zoals `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="8eb45-150">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="8eb45-151">Eén keer per dag wordt een volledige heartbeat met de kenmerken van het apparaat verzonden.</span><span class="sxs-lookup"><span data-stu-id="8eb45-151">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="8eb45-152">U kunt de volgende voorbeeldquery gebruiken om de meest recente status van een apparaat op te halen:</span><span class="sxs-lookup"><span data-stu-id="8eb45-152">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="8eb45-153">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8eb45-153">Related topics</span></span>
- [<span data-ttu-id="8eb45-154">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="8eb45-154">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8eb45-155">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="8eb45-155">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8eb45-156">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="8eb45-156">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8eb45-157">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="8eb45-157">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8eb45-158">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="8eb45-158">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8eb45-159">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="8eb45-159">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
