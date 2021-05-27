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
ms.openlocfilehash: 99a07b1517058b0e5ab241aaae9c6899e2994432
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689107"
---
# <a name="deviceinfo"></a><span data-ttu-id="4ed0f-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="4ed0f-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4ed0f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4ed0f-105">**Applies to:**</span></span>
- <span data-ttu-id="4ed0f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ed0f-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="4ed0f-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4ed0f-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="4ed0f-108">De tabel in het geavanceerde schema voor de jacht bevat informatie over apparaten in de organisatie, waaronder `DeviceInfo` besturingssysteemversie, actieve gebruikers en computernaam. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4ed0f-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="4ed0f-109">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="4ed0f-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="4ed0f-110">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="4ed0f-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4ed0f-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="4ed0f-111">Column name</span></span> | <span data-ttu-id="4ed0f-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="4ed0f-112">Data type</span></span> | <span data-ttu-id="4ed0f-113">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="4ed0f-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4ed0f-114">datetime</span><span class="sxs-lookup"><span data-stu-id="4ed0f-114">datetime</span></span> | <span data-ttu-id="4ed0f-115">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="4ed0f-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="4ed0f-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-116">string</span></span> | <span data-ttu-id="4ed0f-117">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="4ed0f-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="4ed0f-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-118">string</span></span> | <span data-ttu-id="4ed0f-119">Volledig gekwalificeerde domeinnaam (FQDN) van de computer</span><span class="sxs-lookup"><span data-stu-id="4ed0f-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="4ed0f-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-120">string</span></span> | <span data-ttu-id="4ed0f-121">Versie van de eindpuntagent of -sensor die op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="4ed0f-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="4ed0f-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-122">string</span></span> | <span data-ttu-id="4ed0f-123">Openbaar IP-adres dat door de onboarded-computer wordt gebruikt om verbinding te maken met de Microsoft Defender voor Eindpunt-service.</span><span class="sxs-lookup"><span data-stu-id="4ed0f-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="4ed0f-124">Dit kan het IP-adres van de computer zelf, een NAT-apparaat of een proxy zijn</span><span class="sxs-lookup"><span data-stu-id="4ed0f-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="4ed0f-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-125">string</span></span> | <span data-ttu-id="4ed0f-126">Architectuur van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="4ed0f-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="4ed0f-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-127">string</span></span> | <span data-ttu-id="4ed0f-128">Platform van het besturingssysteem dat op de computer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="4ed0f-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="4ed0f-129">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7</span><span class="sxs-lookup"><span data-stu-id="4ed0f-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="4ed0f-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-130">string</span></span> | <span data-ttu-id="4ed0f-131">Build-versie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="4ed0f-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="4ed0f-132">booleaanse</span><span class="sxs-lookup"><span data-stu-id="4ed0f-132">boolean</span></span> | <span data-ttu-id="4ed0f-133">Booleaanse indicator van de vraag of de machine is verbonden met de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4ed0f-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="4ed0f-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-134">string</span></span> | <span data-ttu-id="4ed0f-135">Unieke id voor het apparaat in Azure AD</span><span class="sxs-lookup"><span data-stu-id="4ed0f-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="4ed0f-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-136">string</span></span> | <span data-ttu-id="4ed0f-137">Lijst met alle gebruikers die zijn aangemeld op de computer op het moment van de gebeurtenis in de JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="4ed0f-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="4ed0f-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-138">string</span></span> | <span data-ttu-id="4ed0f-139">Machinetag toegevoegd via het register</span><span class="sxs-lookup"><span data-stu-id="4ed0f-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="4ed0f-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-140">string</span></span> | <span data-ttu-id="4ed0f-141">Versie van het besturingssysteem dat op de computer wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="4ed0f-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="4ed0f-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-142">string</span></span> | <span data-ttu-id="4ed0f-143">Machinegroep van de machine.</span><span class="sxs-lookup"><span data-stu-id="4ed0f-143">Machine group of the machine.</span></span> <span data-ttu-id="4ed0f-144">Deze groep wordt gebruikt door op rollen gebaseerd toegangsbeheer om de toegang tot de computer te bepalen</span><span class="sxs-lookup"><span data-stu-id="4ed0f-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="4ed0f-145">lang</span><span class="sxs-lookup"><span data-stu-id="4ed0f-145">long</span></span> | <span data-ttu-id="4ed0f-146">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="4ed0f-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="4ed0f-147">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp</span><span class="sxs-lookup"><span data-stu-id="4ed0f-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OnboardingStatus` | <span data-ttu-id="4ed0f-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-148">string</span></span> | <span data-ttu-id="4ed0f-149">Geeft aan of het apparaat al dan niet is onboarded bij Microsoft Defender For Endpoint of dat het apparaat niet wordt ondersteund</span><span class="sxs-lookup"><span data-stu-id="4ed0f-149">Indicates whether the device is currently onboarded or not to Microsoft Defender For Endpoint or if the device is not supported</span></span> |
|`AdditionalFields` | <span data-ttu-id="4ed0f-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-150">string</span></span> | <span data-ttu-id="4ed0f-151">Aanvullende informatie over de gebeurtenis in de JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="4ed0f-151">Additional information about the event in JSON array format</span></span> |
|`DeviceCategory` | <span data-ttu-id="4ed0f-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-152">string</span></span> | <span data-ttu-id="4ed0f-153">Bredere classificatie die bepaalde apparaattypen groept onder de volgende categorieën: Eindpunt, Netwerkapparaat, IoT, Onbekend</span><span class="sxs-lookup"><span data-stu-id="4ed0f-153">Broader classification that groups certain device types under the following categories: Endpoint, Network device, IoT, Unknown</span></span> |
|`DeviceType` | <span data-ttu-id="4ed0f-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-154">string</span></span> | <span data-ttu-id="4ed0f-155">Type apparaat op basis van doel en functionaliteit, zoals netwerkapparaat, werkstation, server, mobiel, gameconsole of printer</span><span class="sxs-lookup"><span data-stu-id="4ed0f-155">Type of device based on purpose and functionality, such as network device, workstation, server, mobile, gaming console, or printer</span></span> |
|`DeviceSubType` | <span data-ttu-id="4ed0f-156">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-156">string</span></span> | <span data-ttu-id="4ed0f-157">Extra modifier voor bepaalde typen apparaten, bijvoorbeeld een mobiel apparaat kan een tablet of smartphone zijn</span><span class="sxs-lookup"><span data-stu-id="4ed0f-157">Additional modifier for certain types of devices, for example, a mobile device can be a tablet or a smartphone</span></span> |
|`Model` | <span data-ttu-id="4ed0f-158">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-158">string</span></span> | <span data-ttu-id="4ed0f-159">Modelnaam of nummer van het product van de leverancier of fabrikant</span><span class="sxs-lookup"><span data-stu-id="4ed0f-159">Model name or number of the product from the vendor or manufacturer</span></span> |
|`Vendor` | <span data-ttu-id="4ed0f-160">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-160">string</span></span> | <span data-ttu-id="4ed0f-161">Naam van de leverancier of fabrikant van het product</span><span class="sxs-lookup"><span data-stu-id="4ed0f-161">Name of the product vendor or manufacturer</span></span> |
|`OSDistribution` | <span data-ttu-id="4ed0f-162">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-162">string</span></span> | <span data-ttu-id="4ed0f-163">Distributie van het besturingssysteemplatform, zoals Ubuntu of RedHat voor Linux-platforms</span><span class="sxs-lookup"><span data-stu-id="4ed0f-163">Distribution of the OS platform, such as Ubuntu or RedHat for Linux platforms</span></span> |
|`OSVersionInfo` | <span data-ttu-id="4ed0f-164">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-164">string</span></span> | <span data-ttu-id="4ed0f-165">Aanvullende informatie over de besturingssysteemversie, zoals de populaire naam, codenaam of versienummer</span><span class="sxs-lookup"><span data-stu-id="4ed0f-165">Additional information about the OS version, such as the popular name, code name, or version number</span></span> |
|`MergedDeviceIds` | <span data-ttu-id="4ed0f-166">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-166">string</span></span> | <span data-ttu-id="4ed0f-167">Vorige apparaat-ID's die aan hetzelfde apparaat zijn toegewezen</span><span class="sxs-lookup"><span data-stu-id="4ed0f-167">Previous device IDs that have been assigned to the same device</span></span> |
|`MergedToDeviceId` | <span data-ttu-id="4ed0f-168">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4ed0f-168">string</span></span> | <span data-ttu-id="4ed0f-169">De meest recente apparaat-id die is toegewezen aan een apparaat</span><span class="sxs-lookup"><span data-stu-id="4ed0f-169">The most recent device ID assigned to a device</span></span> |

<span data-ttu-id="4ed0f-170">De `DeviceInfo` tabel bevat apparaatgegevens op basis van hartslagen, die periodieke rapporten of signalen van een apparaat zijn.</span><span class="sxs-lookup"><span data-stu-id="4ed0f-170">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="4ed0f-171">Om de vijftien minuten verzendt het apparaat een gedeeltelijke hartslag die vaak wisselende kenmerken bevat, zoals `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="4ed0f-171">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="4ed0f-172">Eenmaal per dag wordt een volledige hartslag verzonden met de kenmerken van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="4ed0f-172">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="4ed0f-173">U kunt de volgende voorbeeldquery gebruiken om de meest recente status van een apparaat te krijgen:</span><span class="sxs-lookup"><span data-stu-id="4ed0f-173">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="4ed0f-174">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4ed0f-174">Related topics</span></span>
- [<span data-ttu-id="4ed0f-175">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="4ed0f-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4ed0f-176">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="4ed0f-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4ed0f-177">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="4ed0f-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4ed0f-178">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="4ed0f-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4ed0f-179">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="4ed0f-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4ed0f-180">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="4ed0f-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
