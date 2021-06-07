---
title: Beoordeling van beveiligingsproblemen met software per apparaat exporteren
description: De API-reactie is per apparaat en bevat kwetsbare software die is geïnstalleerd op uw blootgestelde apparaten en eventuele bekende beveiligingslekken in deze softwareproducten. Deze tabel bevat ook informatie over het besturingssysteem, CVE-ID's en ernst van de kwetsbaarheid.
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
ms.openlocfilehash: 951f78ba361a12e404a5cce2071f931eab30c43f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778324"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="53cae-105">Beoordeling van beveiligingsproblemen met software per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="53cae-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="53cae-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="53cae-106">**Applies to:**</span></span>

- [<span data-ttu-id="53cae-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="53cae-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="53cae-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="53cae-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="53cae-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="53cae-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="53cae-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="53cae-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="53cae-111">Retourneert alle bekende softwareproblemen en hun gegevens voor alle apparaten, per apparaat.</span><span class="sxs-lookup"><span data-stu-id="53cae-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="53cae-112">Er zijn verschillende API-oproepen om verschillende typen gegevens op te halen.</span><span class="sxs-lookup"><span data-stu-id="53cae-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="53cae-113">Omdat de hoeveelheid gegevens erg groot kan zijn, kunnen deze op twee manieren worden opgehaald:</span><span class="sxs-lookup"><span data-stu-id="53cae-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="53cae-114">[Beoordeling van beveiligingsproblemen met software exporteren OData](#1-export-software-vulnerabilities-assessment-odata)  De API haalt alle gegevens in uw organisatie op als Json-antwoorden, volgens het OData-protocol.</span><span class="sxs-lookup"><span data-stu-id="53cae-114">[Export software vulnerabilities assessment OData](#1-export-software-vulnerabilities-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="53cae-115">Deze methode is het beste _voor kleine organisaties met minder dan 100 K-apparaten._</span><span class="sxs-lookup"><span data-stu-id="53cae-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="53cae-116">Het antwoord is paginated, zodat u het veld odata.nextLink uit het antwoord kunt gebruiken \@ om de volgende resultaten op te halen.</span><span class="sxs-lookup"><span data-stu-id="53cae-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="53cae-117">[Beoordeling van beveiligingsproblemen met software via bestanden exporteren](#2-export-software-vulnerabilities-assessment-via-files) Met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen.</span><span class="sxs-lookup"><span data-stu-id="53cae-117">[Export software vulnerabilities assessment via files](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="53cae-118">Daarom wordt het aanbevolen voor grote organisaties, met meer dan 100 K-apparaten.</span><span class="sxs-lookup"><span data-stu-id="53cae-118">Therefore, it is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="53cae-119">Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="53cae-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="53cae-120">Het antwoord bevat URL's om alle gegevens uit de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="53cae-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="53cae-121">Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden:</span><span class="sxs-lookup"><span data-stu-id="53cae-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="53cae-122">Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens.</span><span class="sxs-lookup"><span data-stu-id="53cae-122">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="53cae-123">Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.</span><span class="sxs-lookup"><span data-stu-id="53cae-123">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="53cae-124">Gegevens die worden verzameld (met _OData_ of _via_ bestanden) zijn de huidige momentopname van de huidige status en bevatten geen historische gegevens.</span><span class="sxs-lookup"><span data-stu-id="53cae-124">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="53cae-125">Om historische gegevens te verzamelen, moeten klanten de gegevens opslaan in hun eigen gegevensopslag.</span><span class="sxs-lookup"><span data-stu-id="53cae-125">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="53cae-126">Tenzij anders aangegeven, zijn alle vermelde exportbeoordelingsmethoden volledig **_geëxporteerd_** en **_per apparaat_** (ook wel per **_apparaat genoemd)._**</span><span class="sxs-lookup"><span data-stu-id="53cae-126">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="53cae-127">1. Evaluatie van softwareproblemen exporteren (OData)</span><span class="sxs-lookup"><span data-stu-id="53cae-127">1. Export software vulnerabilities assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="53cae-128">Beschrijving van API-methode 1.1</span><span class="sxs-lookup"><span data-stu-id="53cae-128">1.1 API method description</span></span>

<span data-ttu-id="53cae-129">Deze API-reactie bevat alle gegevens van geïnstalleerde software per apparaat.</span><span class="sxs-lookup"><span data-stu-id="53cae-129">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="53cae-130">Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="53cae-130">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="limitations"></a><span data-ttu-id="53cae-131">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="53cae-131">Limitations</span></span>

>- <span data-ttu-id="53cae-132">De maximale paginagrootte is 200.000.</span><span class="sxs-lookup"><span data-stu-id="53cae-132">Maximum page size is 200,000.</span></span>
>
>- <span data-ttu-id="53cae-133">Tariefbeperkingen voor deze API zijn 30 oproepen per minuut en 1000 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="53cae-133">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="53cae-134">1.2 Machtigingen</span><span class="sxs-lookup"><span data-stu-id="53cae-134">1.2 Permissions</span></span>

<span data-ttu-id="53cae-135">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="53cae-135">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="53cae-136">Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="53cae-136">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="53cae-137">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="53cae-137">Permission type</span></span> | <span data-ttu-id="53cae-138">Machtiging</span><span class="sxs-lookup"><span data-stu-id="53cae-138">Permission</span></span> | <span data-ttu-id="53cae-139">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="53cae-139">Permission display name</span></span>
---|---|---
<span data-ttu-id="53cae-140">Toepassing</span><span class="sxs-lookup"><span data-stu-id="53cae-140">Application</span></span> | <span data-ttu-id="53cae-141">Kwetsbaarheid.Read.All</span><span class="sxs-lookup"><span data-stu-id="53cae-141">Vulnerability.Read.All</span></span> | <span data-ttu-id="53cae-142">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="53cae-142">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="53cae-143">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="53cae-143">Delegated (work or school account)</span></span> | <span data-ttu-id="53cae-144">Kwetsbaarheid.Lezen</span><span class="sxs-lookup"><span data-stu-id="53cae-144">Vulnerability.Read</span></span> | <span data-ttu-id="53cae-145">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="53cae-145">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="53cae-146">1,3 URL</span><span class="sxs-lookup"><span data-stu-id="53cae-146">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="53cae-147">1,4 Parameters</span><span class="sxs-lookup"><span data-stu-id="53cae-147">1.4 Parameters</span></span>

- <span data-ttu-id="53cae-148">pageSize (standaard = 50.000) – aantal resultaten in antwoord</span><span class="sxs-lookup"><span data-stu-id="53cae-148">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="53cae-149">$top – aantal resultaten dat moet worden retourneren (wordt niet als resultaat @odata.nextLink en dus niet alle gegevens)</span><span class="sxs-lookup"><span data-stu-id="53cae-149">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="53cae-150">1,5 eigenschappen</span><span class="sxs-lookup"><span data-stu-id="53cae-150">1.5 Properties</span></span>
>
>[!Note]
>
>- <span data-ttu-id="53cae-151">Elke record is ongeveer 1 KB aan gegevens.</span><span class="sxs-lookup"><span data-stu-id="53cae-151">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="53cae-152">U moet hiermee rekening houden bij het kiezen van de juiste paginaSize-parameter voor u.</span><span class="sxs-lookup"><span data-stu-id="53cae-152">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="53cae-153">Sommige extra kolommen kunnen worden geretourneerd in het antwoord.</span><span class="sxs-lookup"><span data-stu-id="53cae-153">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="53cae-154">Deze kolommen zijn tijdelijk en kunnen worden verwijderd, gebruik alleen de gedocumenteerde kolommen.</span><span class="sxs-lookup"><span data-stu-id="53cae-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="53cae-155">De eigenschappen die in de volgende tabel zijn gedefinieerd, worden alfabetisch weergegeven op eigenschap-id.</span><span class="sxs-lookup"><span data-stu-id="53cae-155">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="53cae-156">Bij het uitvoeren van deze API wordt de resulterende uitvoer niet noodzakelijkerwijs geretourneerd in dezelfde volgorde als in deze tabel.</span><span class="sxs-lookup"><span data-stu-id="53cae-156">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>

<span data-ttu-id="53cae-157">Eigenschap (id)</span><span class="sxs-lookup"><span data-stu-id="53cae-157">Property (ID)</span></span> | <span data-ttu-id="53cae-158">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="53cae-158">Data type</span></span> | <span data-ttu-id="53cae-159">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="53cae-159">Description</span></span> | <span data-ttu-id="53cae-160">Voorbeeld van een geretourneerde waarde</span><span class="sxs-lookup"><span data-stu-id="53cae-160">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="53cae-161">CveId</span><span class="sxs-lookup"><span data-stu-id="53cae-161">CveId</span></span> | <span data-ttu-id="53cae-162">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-162">string</span></span> | <span data-ttu-id="53cae-163">Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures).</span><span class="sxs-lookup"><span data-stu-id="53cae-163">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="53cae-164">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="53cae-164">CVE-2020-15992</span></span>
<span data-ttu-id="53cae-165">CvssScore</span><span class="sxs-lookup"><span data-stu-id="53cae-165">CvssScore</span></span> | <span data-ttu-id="53cae-166">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-166">string</span></span> | <span data-ttu-id="53cae-167">De CVSS-score van de CVE.</span><span class="sxs-lookup"><span data-stu-id="53cae-167">The CVSS score of the CVE.</span></span> | <span data-ttu-id="53cae-168">6.2</span><span class="sxs-lookup"><span data-stu-id="53cae-168">6.2</span></span>
<span data-ttu-id="53cae-169">DeviceId</span><span class="sxs-lookup"><span data-stu-id="53cae-169">DeviceId</span></span> | <span data-ttu-id="53cae-170">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-170">string</span></span> | <span data-ttu-id="53cae-171">Unieke id voor het apparaat in de service.</span><span class="sxs-lookup"><span data-stu-id="53cae-171">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="53cae-172">9eaf3a8b5962e0e6b1af9ec75664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="53cae-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="53cae-173">Apparaatnaam</span><span class="sxs-lookup"><span data-stu-id="53cae-173">DeviceName</span></span> | <span data-ttu-id="53cae-174">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-174">string</span></span> | <span data-ttu-id="53cae-175">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="53cae-175">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="53cae-176">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="53cae-176">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="53cae-177">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="53cae-177">DiskPaths</span></span>  | <span data-ttu-id="53cae-178">\[Matrixreeks\]</span><span class="sxs-lookup"><span data-stu-id="53cae-178">Array\[string\]</span></span> | <span data-ttu-id="53cae-179">Schijf bewijs dat het product is geïnstalleerd op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="53cae-179">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="53cae-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="53cae-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="53cae-181">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="53cae-181">ExploitabilityLevel</span></span> | <span data-ttu-id="53cae-182">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-182">string</span></span> | <span data-ttu-id="53cae-183">Het gebruiksniveau van dit beveiligingsprobleem (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="53cae-183">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="53cae-184">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="53cae-184">ExploitIsInKit</span></span>
<span data-ttu-id="53cae-185">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="53cae-185">FirstSeenTimestamp</span></span> | <span data-ttu-id="53cae-186">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-186">string</span></span> | <span data-ttu-id="53cae-187">De eerste keer dat de CVE van dit product op het apparaat werd gezien.</span><span class="sxs-lookup"><span data-stu-id="53cae-187">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="53cae-188">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="53cae-188">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="53cae-189">Id</span><span class="sxs-lookup"><span data-stu-id="53cae-189">Id</span></span> | <span data-ttu-id="53cae-190">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-190">string</span></span> | <span data-ttu-id="53cae-191">Unieke id voor de record.</span><span class="sxs-lookup"><span data-stu-id="53cae-191">Unique identifier for the record.</span></span> | <span data-ttu-id="53cae-192">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="53cae-192">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="53cae-193">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="53cae-193">LastSeenTimestamp</span></span> | <span data-ttu-id="53cae-194">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-194">string</span></span> | <span data-ttu-id="53cae-195">De laatste keer dat de CVE werd gezien op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="53cae-195">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="53cae-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="53cae-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="53cae-197">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="53cae-197">OSPlatform</span></span> | <span data-ttu-id="53cae-198">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-198">string</span></span> | <span data-ttu-id="53cae-199">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="53cae-199">Platform of the operating system running on the device.</span></span> <span data-ttu-id="53cae-200">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="53cae-200">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="53cae-201">Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="53cae-201">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="53cae-202">Windows10</span><span class="sxs-lookup"><span data-stu-id="53cae-202">Windows10</span></span>
<span data-ttu-id="53cae-203">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="53cae-203">RbacGroupName</span></span>  | <span data-ttu-id="53cae-204">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-204">string</span></span> | <span data-ttu-id="53cae-205">De groep Toegangsbeheer (RBAC) op basis van rollen.</span><span class="sxs-lookup"><span data-stu-id="53cae-205">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="53cae-206">Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'.</span><span class="sxs-lookup"><span data-stu-id="53cae-206">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="53cae-207">Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'.</span><span class="sxs-lookup"><span data-stu-id="53cae-207">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="53cae-208">Servers</span><span class="sxs-lookup"><span data-stu-id="53cae-208">Servers</span></span>
<span data-ttu-id="53cae-209">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="53cae-209">RecommendationReference</span></span> | <span data-ttu-id="53cae-210">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-210">string</span></span> | <span data-ttu-id="53cae-211">Een verwijzing naar de aanbevelings-id met betrekking tot deze software.</span><span class="sxs-lookup"><span data-stu-id="53cae-211">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="53cae-212">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="53cae-212">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="53cae-213">RecommendedSecurityUpdate (optioneel)</span><span class="sxs-lookup"><span data-stu-id="53cae-213">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="53cae-214">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-214">string</span></span> | <span data-ttu-id="53cae-215">Naam of beschrijving van de beveiligingsupdate die door de softwareleverancier wordt geleverd om het beveiligingsprobleem aan te pakken.</span><span class="sxs-lookup"><span data-stu-id="53cae-215">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="53cae-216">Beveiligingsupdates van april 2020</span><span class="sxs-lookup"><span data-stu-id="53cae-216">April 2020 Security Updates</span></span>
<span data-ttu-id="53cae-217">AanbevolenSecurityUpdateId (optioneel)</span><span class="sxs-lookup"><span data-stu-id="53cae-217">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="53cae-218">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-218">string</span></span> | <span data-ttu-id="53cae-219">Id van de toepasselijke beveiligingsupdates of -id voor de bijbehorende richtlijnen of KB-artikelen (Knowledge Base)</span><span class="sxs-lookup"><span data-stu-id="53cae-219">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="53cae-220">4550961</span><span class="sxs-lookup"><span data-stu-id="53cae-220">4550961</span></span>
<span data-ttu-id="53cae-221">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="53cae-221">RegistryPaths</span></span>  | <span data-ttu-id="53cae-222">\[Matrixreeks\]</span><span class="sxs-lookup"><span data-stu-id="53cae-222">Array\[string\]</span></span> | <span data-ttu-id="53cae-223">Registergegevens dat het product op het apparaat is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="53cae-223">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="53cae-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="53cae-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="53cae-225">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="53cae-225">SoftwareName</span></span> | <span data-ttu-id="53cae-226">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-226">string</span></span> | <span data-ttu-id="53cae-227">Naam van het softwareproduct.</span><span class="sxs-lookup"><span data-stu-id="53cae-227">Name of the software product.</span></span> | <span data-ttu-id="53cae-228">chrome</span><span class="sxs-lookup"><span data-stu-id="53cae-228">chrome</span></span>
<span data-ttu-id="53cae-229">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="53cae-229">SoftwareVendor</span></span> | <span data-ttu-id="53cae-230">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-230">string</span></span> | <span data-ttu-id="53cae-231">Naam van de softwareleverancier.</span><span class="sxs-lookup"><span data-stu-id="53cae-231">Name of the software vendor.</span></span> | <span data-ttu-id="53cae-232">google</span><span class="sxs-lookup"><span data-stu-id="53cae-232">google</span></span>
<span data-ttu-id="53cae-233">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="53cae-233">SoftwareVersion</span></span> | <span data-ttu-id="53cae-234">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-234">string</span></span> | <span data-ttu-id="53cae-235">Versienummer van het softwareproduct.</span><span class="sxs-lookup"><span data-stu-id="53cae-235">Version number of the software product.</span></span> | <span data-ttu-id="53cae-236">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="53cae-236">81.0.4044.138</span></span>
<span data-ttu-id="53cae-237">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="53cae-237">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="53cae-238">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-238">string</span></span> | <span data-ttu-id="53cae-239">Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap.</span><span class="sxs-lookup"><span data-stu-id="53cae-239">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="53cae-240">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="53cae-240">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="53cae-241">1.6 Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="53cae-241">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="53cae-242">1.6.1 Voorbeeld van aanvraag</span><span class="sxs-lookup"><span data-stu-id="53cae-242">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="53cae-243">1.6.2 Voorbeeld van antwoord</span><span class="sxs-lookup"><span data-stu-id="53cae-243">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="53cae-244">2. Evaluatie van softwareproblemen exporteren (via bestanden)</span><span class="sxs-lookup"><span data-stu-id="53cae-244">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="53cae-245">Beschrijving van API-methode 2.1</span><span class="sxs-lookup"><span data-stu-id="53cae-245">2.1 API method description</span></span>

<span data-ttu-id="53cae-246">Deze API-reactie bevat alle gegevens van geïnstalleerde software per apparaat.</span><span class="sxs-lookup"><span data-stu-id="53cae-246">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="53cae-247">Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="53cae-247">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="53cae-248">2.1.2 Beperkingen</span><span class="sxs-lookup"><span data-stu-id="53cae-248">2.1.2 Limitations</span></span>

<span data-ttu-id="53cae-249">Tariefbeperkingen voor deze API zijn 5 oproepen per minuut en 20 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="53cae-249">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="53cae-250">2.2 Machtigingen</span><span class="sxs-lookup"><span data-stu-id="53cae-250">2.2 Permissions</span></span>

<span data-ttu-id="53cae-251">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="53cae-251">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="53cae-252">Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="53cae-252">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="53cae-253">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="53cae-253">Permission type</span></span> | <span data-ttu-id="53cae-254">Machtiging</span><span class="sxs-lookup"><span data-stu-id="53cae-254">Permission</span></span> | <span data-ttu-id="53cae-255">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="53cae-255">Permission display name</span></span>
---|---|---
<span data-ttu-id="53cae-256">Toepassing</span><span class="sxs-lookup"><span data-stu-id="53cae-256">Application</span></span> | <span data-ttu-id="53cae-257">Kwetsbaarheid.Read.All</span><span class="sxs-lookup"><span data-stu-id="53cae-257">Vulnerability.Read.All</span></span> | <span data-ttu-id="53cae-258">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="53cae-258">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="53cae-259">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="53cae-259">Delegated (work or school account)</span></span> | <span data-ttu-id="53cae-260">Kwetsbaarheid.Lezen</span><span class="sxs-lookup"><span data-stu-id="53cae-260">Vulnerability.Read</span></span> | <span data-ttu-id="53cae-261">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="53cae-261">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="53cae-262">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="53cae-262">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="53cae-263">2.4 Parameters</span><span class="sxs-lookup"><span data-stu-id="53cae-263">2.4 Parameters</span></span>

- <span data-ttu-id="53cae-264">sasValidHours: het aantal uren dat de download-URL's geldig zijn (maximaal 24 uur)</span><span class="sxs-lookup"><span data-stu-id="53cae-264">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="53cae-265">2,5 eigenschappen</span><span class="sxs-lookup"><span data-stu-id="53cae-265">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="53cae-266">De bestanden zijn gzip gecomprimeerde & in de Json-indeling met meerdere lijnen.</span><span class="sxs-lookup"><span data-stu-id="53cae-266">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="53cae-267">De DOWNLOAD-URL's zijn slechts 3 uur geldig. anders kunt u de parameter gebruiken.</span><span class="sxs-lookup"><span data-stu-id="53cae-267">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="53cae-268">Voor maximale downloadsnelheid van uw gegevens kunt u ervoor zorgen dat u downloadt vanuit dezelfde Azure-regio als uw gegevens.</span><span class="sxs-lookup"><span data-stu-id="53cae-268">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="53cae-269">Elke record is ongeveer 1 KB aan gegevens.</span><span class="sxs-lookup"><span data-stu-id="53cae-269">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="53cae-270">U moet hiermee rekening houden bij het kiezen van de juiste paginaSize-parameter voor u.</span><span class="sxs-lookup"><span data-stu-id="53cae-270">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="53cae-271">Sommige extra kolommen kunnen worden geretourneerd in het antwoord.</span><span class="sxs-lookup"><span data-stu-id="53cae-271">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="53cae-272">Deze kolommen zijn tijdelijk en kunnen worden verwijderd, gebruik alleen de gedocumenteerde kolommen.</span><span class="sxs-lookup"><span data-stu-id="53cae-272">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="53cae-273">Eigenschap (id)</span><span class="sxs-lookup"><span data-stu-id="53cae-273">Property (ID)</span></span> | <span data-ttu-id="53cae-274">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="53cae-274">Data type</span></span> | <span data-ttu-id="53cae-275">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="53cae-275">Description</span></span> | <span data-ttu-id="53cae-276">Voorbeeld van een geretourneerde waarde</span><span class="sxs-lookup"><span data-stu-id="53cae-276">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="53cae-277">Bestanden exporteren</span><span class="sxs-lookup"><span data-stu-id="53cae-277">Export files</span></span> | <span data-ttu-id="53cae-278">\[matrixreeks\]</span><span class="sxs-lookup"><span data-stu-id="53cae-278">array\[string\]</span></span>  | <span data-ttu-id="53cae-279">Een lijst met download-URL's voor bestanden met de huidige momentopname van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="53cae-279">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="53cae-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="53cae-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="53cae-281">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="53cae-281">GeneratedTime</span></span> | <span data-ttu-id="53cae-282">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="53cae-282">string</span></span> | <span data-ttu-id="53cae-283">De tijd dat de export is gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="53cae-283">The time that the export was generated.</span></span> | <span data-ttu-id="53cae-284">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="53cae-284">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="53cae-285">2.6 Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="53cae-285">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="53cae-286">2.6.1 Voorbeeld van aanvraag</span><span class="sxs-lookup"><span data-stu-id="53cae-286">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="53cae-287">2.6.2 Voorbeeld van antwoord</span><span class="sxs-lookup"><span data-stu-id="53cae-287">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="53cae-288">Zie ook</span><span class="sxs-lookup"><span data-stu-id="53cae-288">See also</span></span>

- [<span data-ttu-id="53cae-289">Beoordelingsmethoden en -eigenschappen per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="53cae-289">Export assessment methods and properties per device</span></span>](get-assessmnt-1methods-properties.md)

- [<span data-ttu-id="53cae-290">Veilige configuratiebeoordeling per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="53cae-290">Export secure configuration assessment per device</span></span>](get-assessmnt-secure-cfg.md)

- [<span data-ttu-id="53cae-291">Beoordeling van de softwarevoorraad per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="53cae-291">Export software inventory assessment per device</span></span>](get-assessmnt-software-inventory.md)

<span data-ttu-id="53cae-292">Andere gerelateerde</span><span class="sxs-lookup"><span data-stu-id="53cae-292">Other related</span></span>

- [<span data-ttu-id="53cae-293">Risicogebaseerd & vulnerability management</span><span class="sxs-lookup"><span data-stu-id="53cae-293">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="53cae-294">Beveiligingslekken in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="53cae-294">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
