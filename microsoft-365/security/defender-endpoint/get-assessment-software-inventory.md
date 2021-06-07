---
title: Beoordeling van de softwarevoorraad per apparaat exporteren
description: Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.
keywords: api's, api's, exportbeoordeling, per apparaat, rapport over kwetsbaarheidsbeoordeling, beoordeling van kwetsbaarheid van apparaten, rapport over apparaatproblemen, beveiligingsprobleemrapport, secure configuration report, software vulnerabilities assessment, software vulnerability report, vulnerability report by machine,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 3a65fb6d5d3e5c6e68e100aa3ea2b4cf896dc281
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789346"
---
# <a name="export-software-inventory-assessment-per-device"></a><span data-ttu-id="2930d-104">Beoordeling van de softwarevoorraad per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="2930d-104">Export software inventory assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2930d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2930d-105">**Applies to:**</span></span>

- [<span data-ttu-id="2930d-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="2930d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2930d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2930d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2930d-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="2930d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2930d-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="2930d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="2930d-110">Er zijn verschillende API-oproepen om verschillende typen gegevens op te halen.</span><span class="sxs-lookup"><span data-stu-id="2930d-110">There are different API calls to get different types of data.</span></span> <span data-ttu-id="2930d-111">Omdat de hoeveelheid gegevens groot kan zijn, kunnen deze op twee manieren worden opgehaald:</span><span class="sxs-lookup"><span data-stu-id="2930d-111">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="2930d-112">[OData-evaluatie van **softwarevoorraad exporteren**](#1-export-software-inventory-assessment-odata)  De API haalt alle gegevens in uw organisatie op als Json-antwoorden, volgens het OData-protocol.</span><span class="sxs-lookup"><span data-stu-id="2930d-112">[Export software inventory assessment **OData**](#1-export-software-inventory-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="2930d-113">Deze methode is het beste _voor kleine organisaties met minder dan 100 K-apparaten._</span><span class="sxs-lookup"><span data-stu-id="2930d-113">This method is best for _small organizations with less than 100-K devices_.</span></span> <span data-ttu-id="2930d-114">Het antwoord is paginated, zodat u het veld odata.nextLink uit het antwoord kunt gebruiken \@ om de volgende resultaten op te halen.</span><span class="sxs-lookup"><span data-stu-id="2930d-114">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="2930d-115">[Beoordeling van softwarevoorraad **exporteren via bestanden**](#2-export-software-inventory-assessment-via-files)  Met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen.</span><span class="sxs-lookup"><span data-stu-id="2930d-115">[Export software inventory assessment **via files**](#2-export-software-inventory-assessment-via-files)  This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="2930d-116">Daarom wordt het aanbevolen voor grote organisaties, met meer dan 100 K-apparaten.</span><span class="sxs-lookup"><span data-stu-id="2930d-116">Therefore, it is recommended for large organizations, with more than 100-K devices.</span></span> <span data-ttu-id="2930d-117">Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="2930d-117">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="2930d-118">Het antwoord bevat URL's om alle gegevens uit de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="2930d-118">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="2930d-119">Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden:</span><span class="sxs-lookup"><span data-stu-id="2930d-119">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="2930d-120">Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens.</span><span class="sxs-lookup"><span data-stu-id="2930d-120">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="2930d-121">Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.</span><span class="sxs-lookup"><span data-stu-id="2930d-121">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="2930d-122">Gegevens die worden verzameld (met _OData_ of _via_ bestanden) zijn de huidige momentopname van de huidige status en bevatten geen historische gegevens.</span><span class="sxs-lookup"><span data-stu-id="2930d-122">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="2930d-123">Om historische gegevens te verzamelen, moeten klanten de gegevens opslaan in hun eigen gegevensopslag.</span><span class="sxs-lookup"><span data-stu-id="2930d-123">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="2930d-124">Tenzij anders aangegeven, zijn alle vermelde exportbeoordelingsmethoden volledig **_geëxporteerd_** en **_per apparaat_** (ook wel per **_apparaat genoemd)._**</span><span class="sxs-lookup"><span data-stu-id="2930d-124">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-inventory-assessment-odata"></a><span data-ttu-id="2930d-125">1. Evaluatie van de softwarevoorraad exporteren (OData)</span><span class="sxs-lookup"><span data-stu-id="2930d-125">1. Export software inventory assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="2930d-126">Beschrijving van API-methode 1.1</span><span class="sxs-lookup"><span data-stu-id="2930d-126">1.1 API method description</span></span>

<span data-ttu-id="2930d-127">Deze API-reactie bevat alle gegevens van geïnstalleerde software per apparaat.</span><span class="sxs-lookup"><span data-stu-id="2930d-127">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="2930d-128">Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span><span class="sxs-lookup"><span data-stu-id="2930d-128">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="limitations"></a><span data-ttu-id="2930d-129">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="2930d-129">Limitations</span></span>

- <span data-ttu-id="2930d-130">De maximale paginagrootte is 200.000.</span><span class="sxs-lookup"><span data-stu-id="2930d-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="2930d-131">Tariefbeperkingen voor deze API zijn 30 oproepen per minuut en 1000 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="2930d-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="2930d-132">1.2 Machtigingen</span><span class="sxs-lookup"><span data-stu-id="2930d-132">1.2 Permissions</span></span>

<span data-ttu-id="2930d-133">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="2930d-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2930d-134">Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2930d-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="2930d-135">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="2930d-135">Permission type</span></span> | <span data-ttu-id="2930d-136">Machtiging</span><span class="sxs-lookup"><span data-stu-id="2930d-136">Permission</span></span> | <span data-ttu-id="2930d-137">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="2930d-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="2930d-138">Toepassing</span><span class="sxs-lookup"><span data-stu-id="2930d-138">Application</span></span> | <span data-ttu-id="2930d-139">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="2930d-139">Software.Read.All</span></span> | <span data-ttu-id="2930d-140">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="2930d-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="2930d-141">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="2930d-141">Delegated (work or school account)</span></span> | <span data-ttu-id="2930d-142">Software.Lezen</span><span class="sxs-lookup"><span data-stu-id="2930d-142">Software.Read</span></span> | <span data-ttu-id="2930d-143">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="2930d-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="2930d-144">1,3 URL</span><span class="sxs-lookup"><span data-stu-id="2930d-144">1.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="2930d-145">1,4 Parameters</span><span class="sxs-lookup"><span data-stu-id="2930d-145">1.4 Parameters</span></span>

- <span data-ttu-id="2930d-146">pageSize (standaard = 50.000) – aantal resultaten in antwoord.</span><span class="sxs-lookup"><span data-stu-id="2930d-146">pageSize (default = 50,000) – number of results in response.</span></span>

- <span data-ttu-id="2930d-147">$top – aantal resultaten dat moet worden retourneren (wordt niet als resultaat @odata.nextLink en dus niet alle gegevens)</span><span class="sxs-lookup"><span data-stu-id="2930d-147">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="2930d-148">1,5 eigenschappen</span><span class="sxs-lookup"><span data-stu-id="2930d-148">1.5 Properties</span></span>

>[!NOTE]
>
><span data-ttu-id="2930d-149">-Elke record is ongeveer 0,5 KB aan gegevens.</span><span class="sxs-lookup"><span data-stu-id="2930d-149">-Each record is approximately 0.5KB of data.</span></span> <span data-ttu-id="2930d-150">U moet hiermee rekening houden bij het kiezen van de juiste paginaSize-parameter voor u.</span><span class="sxs-lookup"><span data-stu-id="2930d-150">You should take this into account when choosing the correct pageSize parameter for you.</span></span>

><span data-ttu-id="2930d-151">-De eigenschappen die in de volgende tabel zijn gedefinieerd, worden alfabetisch weergegeven op eigenschap-id.</span><span class="sxs-lookup"><span data-stu-id="2930d-151">-The properties defined in the following table are listed alphabetically, by property ID.</span></span> <span data-ttu-id="2930d-152">Bij het uitvoeren van deze API wordt de resulterende uitvoer niet noodzakelijkerwijs geretourneerd in dezelfde volgorde als in deze tabel.</span><span class="sxs-lookup"><span data-stu-id="2930d-152">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
><span data-ttu-id="2930d-153">-Sommige extra kolommen kunnen worden geretourneerd in het antwoord.</span><span class="sxs-lookup"><span data-stu-id="2930d-153">-Some additional columns might be returned in the response.</span></span> <span data-ttu-id="2930d-154">Deze kolommen zijn tijdelijk en kunnen worden verwijderd, gebruik alleen de gedocumenteerde kolommen.</span><span class="sxs-lookup"><span data-stu-id="2930d-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>

<span data-ttu-id="2930d-155">Eigenschap (id)</span><span class="sxs-lookup"><span data-stu-id="2930d-155">Property (ID)</span></span> | <span data-ttu-id="2930d-156">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="2930d-156">Data type</span></span> | <span data-ttu-id="2930d-157">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="2930d-157">Description</span></span> | <span data-ttu-id="2930d-158">Voorbeeld van een geretourneerde waarde</span><span class="sxs-lookup"><span data-stu-id="2930d-158">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="2930d-159">DeviceId</span><span class="sxs-lookup"><span data-stu-id="2930d-159">DeviceId</span></span> | <span data-ttu-id="2930d-160">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2930d-160">string</span></span> | <span data-ttu-id="2930d-161">Unieke id voor het apparaat in de service.</span><span class="sxs-lookup"><span data-stu-id="2930d-161">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="2930d-162">9eaf3a8b5962e0e6b1af9ec75664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="2930d-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="2930d-163">Apparaatnaam</span><span class="sxs-lookup"><span data-stu-id="2930d-163">DeviceName</span></span> | <span data-ttu-id="2930d-164">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2930d-164">string</span></span> | <span data-ttu-id="2930d-165">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="2930d-165">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="2930d-166">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2930d-166">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="2930d-167">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="2930d-167">DiskPaths</span></span> | <span data-ttu-id="2930d-168">Matrix[tekenreeks]</span><span class="sxs-lookup"><span data-stu-id="2930d-168">Array[string]</span></span>  | <span data-ttu-id="2930d-169">Schijf bewijs dat het product is geïnstalleerd op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="2930d-169">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="2930d-170">[ "C: \\ Program Files (x86) \\ Microsoft \\ Silverlight \\ Application \\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="2930d-170">[ "C:\\Program Files (x86)\\Microsoft\\Silverlight\\Application\\silverlight.exe" ]</span></span>
<span data-ttu-id="2930d-171">EndOfSupportDate</span><span class="sxs-lookup"><span data-stu-id="2930d-171">EndOfSupportDate</span></span> | <span data-ttu-id="2930d-172">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2930d-172">string</span></span> | <span data-ttu-id="2930d-173">De datum waarop de ondersteuning voor deze software is of eindigt.</span><span class="sxs-lookup"><span data-stu-id="2930d-173">The date in which support for this software has or will end.</span></span> | <span data-ttu-id="2930d-174">2020-12-30</span><span class="sxs-lookup"><span data-stu-id="2930d-174">2020-12-30</span></span>
<span data-ttu-id="2930d-175">EndOfSupportStatus</span><span class="sxs-lookup"><span data-stu-id="2930d-175">EndOfSupportStatus</span></span> | <span data-ttu-id="2930d-176">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2930d-176">string</span></span> | <span data-ttu-id="2930d-177">Einde van de ondersteuningsstatus.</span><span class="sxs-lookup"><span data-stu-id="2930d-177">End of support status.</span></span> <span data-ttu-id="2930d-178">Kan deze mogelijke waarden bevatten: Geen, EOS-versie, aankomende EOS-versie, EOS-software, aankomende EOS-software.</span><span class="sxs-lookup"><span data-stu-id="2930d-178">Can contain these possible values: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span></span> | <span data-ttu-id="2930d-179">Aankomende EOS</span><span class="sxs-lookup"><span data-stu-id="2930d-179">Upcoming EOS</span></span>
<span data-ttu-id="2930d-180">Id</span><span class="sxs-lookup"><span data-stu-id="2930d-180">Id</span></span> | <span data-ttu-id="2930d-181">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2930d-181">string</span></span> | <span data-ttu-id="2930d-182">Unieke id voor de record.</span><span class="sxs-lookup"><span data-stu-id="2930d-182">Unique identifier for the record.</span></span> | <span data-ttu-id="2930d-183">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="2930d-183">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="2930d-184">NumberOfWeaknesses</span><span class="sxs-lookup"><span data-stu-id="2930d-184">NumberOfWeaknesses</span></span> | <span data-ttu-id="2930d-185">int</span><span class="sxs-lookup"><span data-stu-id="2930d-185">int</span></span> | <span data-ttu-id="2930d-186">Aantal zwakke punten in deze software op dit apparaat</span><span class="sxs-lookup"><span data-stu-id="2930d-186">Number of weaknesses on this software on this device</span></span> | <span data-ttu-id="2930d-187">3</span><span class="sxs-lookup"><span data-stu-id="2930d-187">3</span></span>
<span data-ttu-id="2930d-188">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="2930d-188">OSPlatform</span></span> | <span data-ttu-id="2930d-189">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2930d-189">string</span></span> | <span data-ttu-id="2930d-190">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="2930d-190">Platform of the operating system running on the device.</span></span> <span data-ttu-id="2930d-191">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="2930d-191">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="2930d-192">Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2930d-192">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="2930d-193">Windows10</span><span class="sxs-lookup"><span data-stu-id="2930d-193">Windows10</span></span>
<span data-ttu-id="2930d-194">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="2930d-194">RbacGroupName</span></span> | <span data-ttu-id="2930d-195">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2930d-195">string</span></span> | <span data-ttu-id="2930d-196">De groep Toegangsbeheer (RBAC) op basis van rollen.</span><span class="sxs-lookup"><span data-stu-id="2930d-196">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="2930d-197">Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'.</span><span class="sxs-lookup"><span data-stu-id="2930d-197">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="2930d-198">Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'.</span><span class="sxs-lookup"><span data-stu-id="2930d-198">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="2930d-199">Servers</span><span class="sxs-lookup"><span data-stu-id="2930d-199">Servers</span></span>
<span data-ttu-id="2930d-200">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="2930d-200">RegistryPaths</span></span> | <span data-ttu-id="2930d-201">Matrix[tekenreeks]</span><span class="sxs-lookup"><span data-stu-id="2930d-201">Array[string]</span></span> | <span data-ttu-id="2930d-202">Registergegevens dat het product op het apparaat is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="2930d-202">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="2930d-203">[ "HKEY_LOCAL_MACHINE \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ Uninstall Microsoft \\ Silverlight" ]</span><span class="sxs-lookup"><span data-stu-id="2930d-203">[ "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Silverlight" ]</span></span>
<span data-ttu-id="2930d-204">SoftwareFirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="2930d-204">SoftwareFirstSeenTimestamp</span></span> | <span data-ttu-id="2930d-205">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2930d-205">string</span></span> | <span data-ttu-id="2930d-206">De eerste keer dat deze software op het apparaat werd gezien.</span><span class="sxs-lookup"><span data-stu-id="2930d-206">The first time this software was seen on the device.</span></span> | <span data-ttu-id="2930d-207">2019-04-07 02:06:47</span><span class="sxs-lookup"><span data-stu-id="2930d-207">2019-04-07 02:06:47</span></span>
<span data-ttu-id="2930d-208">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="2930d-208">SoftwareName</span></span> | <span data-ttu-id="2930d-209">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2930d-209">string</span></span> | <span data-ttu-id="2930d-210">Naam van het softwareproduct.</span><span class="sxs-lookup"><span data-stu-id="2930d-210">Name of the software product.</span></span> | <span data-ttu-id="2930d-211">Silverlight</span><span class="sxs-lookup"><span data-stu-id="2930d-211">Silverlight</span></span>
<span data-ttu-id="2930d-212">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="2930d-212">SoftwareVendor</span></span> | <span data-ttu-id="2930d-213">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2930d-213">string</span></span> | <span data-ttu-id="2930d-214">Naam van de softwareleverancier.</span><span class="sxs-lookup"><span data-stu-id="2930d-214">Name of the software vendor.</span></span> | <span data-ttu-id="2930d-215">microsoft</span><span class="sxs-lookup"><span data-stu-id="2930d-215">microsoft</span></span>
<span data-ttu-id="2930d-216">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="2930d-216">SoftwareVersion</span></span> | <span data-ttu-id="2930d-217">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2930d-217">string</span></span> | <span data-ttu-id="2930d-218">Versienummer van het softwareproduct.</span><span class="sxs-lookup"><span data-stu-id="2930d-218">Version number of the software product.</span></span> | <span data-ttu-id="2930d-219">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="2930d-219">81.0.4044.138</span></span>

### <a name="16-examples"></a><span data-ttu-id="2930d-220">1.6 Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="2930d-220">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="2930d-221">1.6.1 Voorbeeld van aanvraag</span><span class="sxs-lookup"><span data-stu-id="2930d-221">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a><span data-ttu-id="2930d-222">1.6.2 Voorbeeld van antwoord</span><span class="sxs-lookup"><span data-stu-id="2930d-222">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a><span data-ttu-id="2930d-223">2. Evaluatie van de softwarevoorraad exporteren (via bestanden)</span><span class="sxs-lookup"><span data-stu-id="2930d-223">2. Export software inventory assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="2930d-224">Beschrijving van API-methode 2.1</span><span class="sxs-lookup"><span data-stu-id="2930d-224">2.1 API method description</span></span>

<span data-ttu-id="2930d-225">Deze API-reactie bevat alle gegevens van geïnstalleerde software per apparaat.</span><span class="sxs-lookup"><span data-stu-id="2930d-225">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="2930d-226">Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span><span class="sxs-lookup"><span data-stu-id="2930d-226">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="211-limitations"></a><span data-ttu-id="2930d-227">2.1.1 Beperkingen</span><span class="sxs-lookup"><span data-stu-id="2930d-227">2.1.1 Limitations</span></span>

<span data-ttu-id="2930d-228">Tariefbeperkingen voor deze API zijn 5 oproepen per minuut en 20 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="2930d-228">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="2930d-229">2.2 Machtigingen</span><span class="sxs-lookup"><span data-stu-id="2930d-229">2.2 Permissions</span></span>

<span data-ttu-id="2930d-230">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="2930d-230">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2930d-231">Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2930d-231">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="2930d-232">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="2930d-232">Permission type</span></span> | <span data-ttu-id="2930d-233">Machtiging</span><span class="sxs-lookup"><span data-stu-id="2930d-233">Permission</span></span> | <span data-ttu-id="2930d-234">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="2930d-234">Permission display name</span></span>
---|---|---
<span data-ttu-id="2930d-235">Toepassing</span><span class="sxs-lookup"><span data-stu-id="2930d-235">Application</span></span> | <span data-ttu-id="2930d-236">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="2930d-236">Software.Read.All</span></span> | <span data-ttu-id="2930d-237">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="2930d-237">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="2930d-238">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="2930d-238">Delegated (work or school account)</span></span> | <span data-ttu-id="2930d-239">Software.Lezen</span><span class="sxs-lookup"><span data-stu-id="2930d-239">Software.Read</span></span> | <span data-ttu-id="2930d-240">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="2930d-240">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="2930d-241">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="2930d-241">2.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a><span data-ttu-id="2930d-242">Parameters</span><span class="sxs-lookup"><span data-stu-id="2930d-242">Parameters</span></span>

- <span data-ttu-id="2930d-243">sasValidHours: het aantal uren dat de download-URL's geldig zijn (maximaal 24 uur)</span><span class="sxs-lookup"><span data-stu-id="2930d-243">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="2930d-244">2,5 eigenschappen</span><span class="sxs-lookup"><span data-stu-id="2930d-244">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="2930d-245">De bestanden zijn gzip gecomprimeerde & in de Json-indeling met meerdere lijnen.</span><span class="sxs-lookup"><span data-stu-id="2930d-245">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="2930d-246">De DOWNLOAD-URL's zijn slechts 3 uur geldig.</span><span class="sxs-lookup"><span data-stu-id="2930d-246">The download URLs are only valid for 3 hours.</span></span> <span data-ttu-id="2930d-247">Anders kunt u de parameter gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2930d-247">Otherwise you can use the parameter.</span></span>
>
><span data-ttu-id="2930d-248">_ Voor een maximale downloadsnelheid van uw gegevens kunt u ervoor zorgen dat u downloadt vanuit dezelfde Azure-regio als uw gegevens.</span><span class="sxs-lookup"><span data-stu-id="2930d-248">_ For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>
<span data-ttu-id="2930d-249">Eigenschap (id)</span><span class="sxs-lookup"><span data-stu-id="2930d-249">Property (ID)</span></span> | <span data-ttu-id="2930d-250">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="2930d-250">Data type</span></span> | <span data-ttu-id="2930d-251">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="2930d-251">Description</span></span> | <span data-ttu-id="2930d-252">Voorbeeld van een geretourneerde waarde</span><span class="sxs-lookup"><span data-stu-id="2930d-252">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="2930d-253">Bestanden exporteren</span><span class="sxs-lookup"><span data-stu-id="2930d-253">Export files</span></span> | <span data-ttu-id="2930d-254">\[matrixreeks\]</span><span class="sxs-lookup"><span data-stu-id="2930d-254">array\[string\]</span></span> | <span data-ttu-id="2930d-255">Een lijst met DOWNLOAD-URL's voor bestanden met de huidige momentopname van de organisatie</span><span class="sxs-lookup"><span data-stu-id="2930d-255">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="2930d-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="2930d-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="2930d-257">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="2930d-257">GeneratedTime</span></span> | <span data-ttu-id="2930d-258">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2930d-258">string</span></span> | <span data-ttu-id="2930d-259">De tijd dat de export is gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="2930d-259">The time that the export was generated.</span></span> | <span data-ttu-id="2930d-260">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="2930d-260">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="2930d-261">2.6 Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="2930d-261">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="2930d-262">2.6.1 Voorbeeld van aanvraag</span><span class="sxs-lookup"><span data-stu-id="2930d-262">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a><span data-ttu-id="2930d-263">2.6.2 Voorbeeld van antwoord</span><span class="sxs-lookup"><span data-stu-id="2930d-263">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="2930d-264">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2930d-264">See also</span></span>

- [<span data-ttu-id="2930d-265">Beoordelingsmethoden en -eigenschappen per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="2930d-265">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="2930d-266">Veilige configuratiebeoordeling per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="2930d-266">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="2930d-267">Beoordeling van beveiligingsproblemen met software per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="2930d-267">Export software vulnerabilities assessment per device</span></span>](get-assessment-software-vulnerabilities.md)

<span data-ttu-id="2930d-268">Andere gerelateerde</span><span class="sxs-lookup"><span data-stu-id="2930d-268">Other related</span></span>

- [<span data-ttu-id="2930d-269">Risicogebaseerd & vulnerability management</span><span class="sxs-lookup"><span data-stu-id="2930d-269">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="2930d-270">Beveiligingslekken in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="2930d-270">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
