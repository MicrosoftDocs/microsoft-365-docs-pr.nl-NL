---
title: Tabel DeviceInfo in het geavanceerde schema voor de jacht
description: Meer informatie over besturingssysteem, computernaam en andere computergegevens in de tabel DeviceInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machineinfo, DeviceInfo, device, machine, OS, platform, users
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
ms.openlocfilehash: e3686099606ec1cdab756bd4991cf61289299b43
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934883"
---
# <a name="deviceinfo"></a><span data-ttu-id="44c48-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="44c48-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="44c48-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="44c48-105">**Applies to:**</span></span>
- <span data-ttu-id="44c48-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="44c48-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="44c48-107">De tabel in het geavanceerde schema voor de jacht bevat informatie over apparaten in de organisatie, waaronder `DeviceInfo` besturingssysteemversie, actieve gebruikers en computernaam. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="44c48-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="44c48-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="44c48-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="44c48-109">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="44c48-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="44c48-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="44c48-110">Column name</span></span> | <span data-ttu-id="44c48-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="44c48-111">Data type</span></span> | <span data-ttu-id="44c48-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="44c48-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="44c48-113">datetime</span><span class="sxs-lookup"><span data-stu-id="44c48-113">datetime</span></span> | <span data-ttu-id="44c48-114">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="44c48-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="44c48-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44c48-115">string</span></span> | <span data-ttu-id="44c48-116">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="44c48-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="44c48-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44c48-117">string</span></span> | <span data-ttu-id="44c48-118">Volledig gekwalificeerde domeinnaam (FQDN) van de computer</span><span class="sxs-lookup"><span data-stu-id="44c48-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="44c48-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44c48-119">string</span></span> | <span data-ttu-id="44c48-120">Versie van de eindpuntagent of -sensor die op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="44c48-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="44c48-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44c48-121">string</span></span> | <span data-ttu-id="44c48-122">Openbaar IP-adres dat door de onboarded-computer wordt gebruikt om verbinding te maken met de Microsoft Defender voor Eindpunt-service.</span><span class="sxs-lookup"><span data-stu-id="44c48-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="44c48-123">Dit kan het IP-adres van de computer zelf, een NAT-apparaat of een proxy zijn</span><span class="sxs-lookup"><span data-stu-id="44c48-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="44c48-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44c48-124">string</span></span> | <span data-ttu-id="44c48-125">Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="44c48-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="44c48-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44c48-126">string</span></span> | <span data-ttu-id="44c48-127">Platform van het besturingssysteem dat op de computer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="44c48-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="44c48-128">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7</span><span class="sxs-lookup"><span data-stu-id="44c48-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="44c48-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44c48-129">string</span></span> | <span data-ttu-id="44c48-130">Build-versie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="44c48-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="44c48-131">booleaanse</span><span class="sxs-lookup"><span data-stu-id="44c48-131">boolean</span></span> | <span data-ttu-id="44c48-132">Booleaanse indicator van de vraag of de computer is verbonden met de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="44c48-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="44c48-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44c48-133">string</span></span> | <span data-ttu-id="44c48-134">Unieke id voor het apparaat in Azure AD</span><span class="sxs-lookup"><span data-stu-id="44c48-134">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="44c48-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44c48-135">string</span></span> | <span data-ttu-id="44c48-136">Lijst met alle gebruikers die zijn aangemeld op de computer op het moment van de gebeurtenis in de JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="44c48-136">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="44c48-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44c48-137">string</span></span> | <span data-ttu-id="44c48-138">Machinetag toegevoegd via het register</span><span class="sxs-lookup"><span data-stu-id="44c48-138">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="44c48-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44c48-139">string</span></span> | <span data-ttu-id="44c48-140">Versie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="44c48-140">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="44c48-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44c48-141">string</span></span> | <span data-ttu-id="44c48-142">Machinegroep van de machine.</span><span class="sxs-lookup"><span data-stu-id="44c48-142">Machine group of the machine.</span></span> <span data-ttu-id="44c48-143">Deze groep wordt gebruikt door op rollen gebaseerd toegangsbeheer om de toegang tot de computer te bepalen</span><span class="sxs-lookup"><span data-stu-id="44c48-143">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="44c48-144">lang</span><span class="sxs-lookup"><span data-stu-id="44c48-144">long</span></span> | <span data-ttu-id="44c48-145">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="44c48-145">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="44c48-146">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp</span><span class="sxs-lookup"><span data-stu-id="44c48-146">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="44c48-147">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="44c48-147">string</span></span> | <span data-ttu-id="44c48-148">Aanvullende informatie over de gebeurtenis in de JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="44c48-148">Additional information about the event in JSON array format</span></span> |

<span data-ttu-id="44c48-149">De `DeviceInfo` tabel bevat apparaatgegevens op basis van hartslagen, die periodieke rapporten of signalen van een apparaat zijn.</span><span class="sxs-lookup"><span data-stu-id="44c48-149">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="44c48-150">Om de vijftien minuten verzendt het apparaat een gedeeltelijke hartslag die vaak wisselende kenmerken bevat, zoals `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="44c48-150">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="44c48-151">Eenmaal per dag wordt een volledige hartslag verzonden met de kenmerken van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="44c48-151">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="44c48-152">U kunt de volgende voorbeeldquery gebruiken om de meest recente status van een apparaat te krijgen:</span><span class="sxs-lookup"><span data-stu-id="44c48-152">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="44c48-153">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="44c48-153">Related topics</span></span>
- [<span data-ttu-id="44c48-154">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="44c48-154">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="44c48-155">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="44c48-155">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="44c48-156">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="44c48-156">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="44c48-157">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="44c48-157">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="44c48-158">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="44c48-158">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="44c48-159">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="44c48-159">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
