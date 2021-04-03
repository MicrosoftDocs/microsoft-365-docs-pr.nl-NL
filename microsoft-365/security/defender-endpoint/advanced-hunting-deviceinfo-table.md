---
title: Tabel DeviceInfo in het geavanceerde schema voor de jacht
description: Meer informatie over besturingssysteem, computernaam en andere apparaatgegevens in de tabel DeviceInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, deviceinfo, device, OS, platform, users, DeviceInfo
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
ms.openlocfilehash: e6a11af94a5d2b2099d14b660cf65c846532ebd1
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500833"
---
# <a name="deviceinfo"></a><span data-ttu-id="bd18e-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="bd18e-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bd18e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bd18e-105">**Applies to:**</span></span>
- [<span data-ttu-id="bd18e-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="bd18e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="bd18e-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="bd18e-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bd18e-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="bd18e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="bd18e-109">De tabel in het geavanceerde schema bevat informatie over apparaten in de organisatie, waaronder de `DeviceInfo` besturingssysteemversie, actieve gebruikers en de computernaam. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bd18e-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="bd18e-110">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="bd18e-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="bd18e-111">Zie de geavanceerde verwijzing naar het schema voor de jacht voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="bd18e-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="bd18e-112">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="bd18e-112">Column name</span></span> | <span data-ttu-id="bd18e-113">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="bd18e-113">Data type</span></span> | <span data-ttu-id="bd18e-114">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="bd18e-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="bd18e-115">datetime</span><span class="sxs-lookup"><span data-stu-id="bd18e-115">datetime</span></span> | <span data-ttu-id="bd18e-116">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="bd18e-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="bd18e-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd18e-117">string</span></span> | <span data-ttu-id="bd18e-118">Unieke id voor het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="bd18e-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="bd18e-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd18e-119">string</span></span> | <span data-ttu-id="bd18e-120">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat</span><span class="sxs-lookup"><span data-stu-id="bd18e-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="bd18e-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd18e-121">string</span></span> | <span data-ttu-id="bd18e-122">Versie van de eindpuntagent of -sensor die op het apparaat wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="bd18e-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="bd18e-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd18e-123">string</span></span> | <span data-ttu-id="bd18e-124">Openbaar IP-adres dat door het onboarded-apparaat wordt gebruikt om verbinding te maken met de Defender voor Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="bd18e-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="bd18e-125">Dit kan het IP-adres van het apparaat zelf, een NAT-apparaat of een proxy zijn</span><span class="sxs-lookup"><span data-stu-id="bd18e-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="bd18e-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd18e-126">string</span></span> | <span data-ttu-id="bd18e-127">Architectuur van het besturingssysteem dat op het apparaat wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="bd18e-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="bd18e-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd18e-128">string</span></span> | <span data-ttu-id="bd18e-129">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="bd18e-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="bd18e-130">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7</span><span class="sxs-lookup"><span data-stu-id="bd18e-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="bd18e-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd18e-131">string</span></span> | <span data-ttu-id="bd18e-132">Build-versie van het besturingssysteem dat op het apparaat wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="bd18e-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="bd18e-133">booleaanse</span><span class="sxs-lookup"><span data-stu-id="bd18e-133">boolean</span></span> | <span data-ttu-id="bd18e-134">Booleaanse indicator van of het apparaat is verbonden met de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bd18e-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="bd18e-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd18e-135">string</span></span> | <span data-ttu-id="bd18e-136">Lijst met alle gebruikers die zijn aangemeld op het apparaat op het moment van de gebeurtenis in de JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="bd18e-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="bd18e-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd18e-137">string</span></span> | <span data-ttu-id="bd18e-138">Apparaatlabel toegevoegd via het register</span><span class="sxs-lookup"><span data-stu-id="bd18e-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="bd18e-139">lang</span><span class="sxs-lookup"><span data-stu-id="bd18e-139">long</span></span> | <span data-ttu-id="bd18e-140">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="bd18e-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="bd18e-141">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp</span><span class="sxs-lookup"><span data-stu-id="bd18e-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="bd18e-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd18e-142">string</span></span> | <span data-ttu-id="bd18e-143">Versie van het besturingssysteem dat op het apparaat wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="bd18e-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="bd18e-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd18e-144">string</span></span> | <span data-ttu-id="bd18e-145">Machinegroep van de machine.</span><span class="sxs-lookup"><span data-stu-id="bd18e-145">Machine group of the machine.</span></span> <span data-ttu-id="bd18e-146">Deze groep wordt gebruikt door op rollen gebaseerd toegangsbeheer om de toegang tot de computer te bepalen</span><span class="sxs-lookup"><span data-stu-id="bd18e-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="bd18e-147">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="bd18e-147">Related topics</span></span>
- [<span data-ttu-id="bd18e-148">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="bd18e-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bd18e-149">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="bd18e-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bd18e-150">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="bd18e-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
