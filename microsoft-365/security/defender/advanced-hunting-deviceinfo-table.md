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
ms.openlocfilehash: f97947c2c9f02720facae4f0c3c29ff702416261
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023127"
---
# <a name="deviceinfo"></a><span data-ttu-id="94fad-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="94fad-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="94fad-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="94fad-105">**Applies to:**</span></span>
- <span data-ttu-id="94fad-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94fad-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="94fad-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="94fad-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="94fad-108">De tabel in het geavanceerde schema voor de jacht bevat informatie over apparaten in de organisatie, waaronder `DeviceInfo` besturingssysteemversie, actieve gebruikers en computernaam. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="94fad-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="94fad-109">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="94fad-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="94fad-110">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="94fad-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="94fad-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="94fad-111">Column name</span></span> | <span data-ttu-id="94fad-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="94fad-112">Data type</span></span> | <span data-ttu-id="94fad-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="94fad-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="94fad-114">datetime</span><span class="sxs-lookup"><span data-stu-id="94fad-114">datetime</span></span> | <span data-ttu-id="94fad-115">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="94fad-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="94fad-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="94fad-116">string</span></span> | <span data-ttu-id="94fad-117">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="94fad-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="94fad-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="94fad-118">string</span></span> | <span data-ttu-id="94fad-119">Volledig gekwalificeerde domeinnaam (FQDN) van de computer</span><span class="sxs-lookup"><span data-stu-id="94fad-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="94fad-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="94fad-120">string</span></span> | <span data-ttu-id="94fad-121">Versie van de eindpuntagent of -sensor die op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="94fad-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="94fad-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="94fad-122">string</span></span> | <span data-ttu-id="94fad-123">Openbaar IP-adres dat door de onboarded-computer wordt gebruikt om verbinding te maken met de Microsoft Defender voor Eindpunt-service.</span><span class="sxs-lookup"><span data-stu-id="94fad-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="94fad-124">Dit kan het IP-adres van de computer zelf, een NAT-apparaat of een proxy zijn</span><span class="sxs-lookup"><span data-stu-id="94fad-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="94fad-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="94fad-125">string</span></span> | <span data-ttu-id="94fad-126">Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="94fad-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="94fad-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="94fad-127">string</span></span> | <span data-ttu-id="94fad-128">Platform van het besturingssysteem dat op de computer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="94fad-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="94fad-129">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7</span><span class="sxs-lookup"><span data-stu-id="94fad-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="94fad-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="94fad-130">string</span></span> | <span data-ttu-id="94fad-131">Build-versie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="94fad-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="94fad-132">booleaanse</span><span class="sxs-lookup"><span data-stu-id="94fad-132">boolean</span></span> | <span data-ttu-id="94fad-133">Booleaanse indicator van de vraag of de computer is verbonden met de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="94fad-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="94fad-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="94fad-134">string</span></span> | <span data-ttu-id="94fad-135">Unieke id voor het apparaat in Azure AD</span><span class="sxs-lookup"><span data-stu-id="94fad-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="94fad-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="94fad-136">string</span></span> | <span data-ttu-id="94fad-137">Lijst met alle gebruikers die zijn aangemeld op de computer op het moment van de gebeurtenis in de JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="94fad-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="94fad-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="94fad-138">string</span></span> | <span data-ttu-id="94fad-139">Machinetag toegevoegd via het register</span><span class="sxs-lookup"><span data-stu-id="94fad-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="94fad-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="94fad-140">string</span></span> | <span data-ttu-id="94fad-141">Versie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="94fad-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="94fad-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="94fad-142">string</span></span> | <span data-ttu-id="94fad-143">Machinegroep van de machine.</span><span class="sxs-lookup"><span data-stu-id="94fad-143">Machine group of the machine.</span></span> <span data-ttu-id="94fad-144">Deze groep wordt gebruikt door op rollen gebaseerd toegangsbeheer om de toegang tot de computer te bepalen</span><span class="sxs-lookup"><span data-stu-id="94fad-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="94fad-145">lang</span><span class="sxs-lookup"><span data-stu-id="94fad-145">long</span></span> | <span data-ttu-id="94fad-146">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="94fad-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="94fad-147">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp</span><span class="sxs-lookup"><span data-stu-id="94fad-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="94fad-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="94fad-148">string</span></span> | <span data-ttu-id="94fad-149">Aanvullende informatie over de gebeurtenis in de JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="94fad-149">Additional information about the event in JSON array format</span></span> |

<span data-ttu-id="94fad-150">De `DeviceInfo` tabel bevat apparaatgegevens op basis van hartslagen, die periodieke rapporten of signalen van een apparaat zijn.</span><span class="sxs-lookup"><span data-stu-id="94fad-150">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="94fad-151">Om de vijftien minuten verzendt het apparaat een gedeeltelijke hartslag die vaak wisselende kenmerken bevat, zoals `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="94fad-151">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="94fad-152">Eenmaal per dag wordt een volledige hartslag verzonden met de kenmerken van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="94fad-152">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="94fad-153">U kunt de volgende voorbeeldquery gebruiken om de meest recente status van een apparaat te krijgen:</span><span class="sxs-lookup"><span data-stu-id="94fad-153">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="94fad-154">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="94fad-154">Related topics</span></span>
- [<span data-ttu-id="94fad-155">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="94fad-155">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="94fad-156">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="94fad-156">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="94fad-157">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="94fad-157">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="94fad-158">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="94fad-158">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="94fad-159">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="94fad-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="94fad-160">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="94fad-160">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
