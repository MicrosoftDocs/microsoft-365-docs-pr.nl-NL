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
ms.openlocfilehash: 87fb5c62b520168a686cc0b95a321becdd4656ba
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2021
ms.locfileid: "53052961"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="8bee2-105">Beoordeling van beveiligingsproblemen met software per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="8bee2-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8bee2-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8bee2-106">**Applies to:**</span></span>

- [<span data-ttu-id="8bee2-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8bee2-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8bee2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8bee2-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8bee2-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8bee2-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8bee2-110">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="8bee2-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="8bee2-111">Retourneert alle bekende softwareproblemen en hun gegevens voor alle apparaten, per apparaat.</span><span class="sxs-lookup"><span data-stu-id="8bee2-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="8bee2-112">Er zijn verschillende API-oproepen om verschillende typen gegevens op te halen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="8bee2-113">Omdat de hoeveelheid gegevens erg groot kan zijn, kunnen deze op twee manieren worden opgehaald:</span><span class="sxs-lookup"><span data-stu-id="8bee2-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

1. <span data-ttu-id="8bee2-114">[Beoordeling van **JSON-reactie** bij](#1-export-software-vulnerabilities-assessment-json-response) het exporteren van softwareproblemen  De API haalt alle gegevens in uw organisatie op als Json-antwoorden.</span><span class="sxs-lookup"><span data-stu-id="8bee2-114">[Export software vulnerabilities assessment **JSON response**](#1-export-software-vulnerabilities-assessment-json-response)  The API pulls all data in your organization as Json responses.</span></span> <span data-ttu-id="8bee2-115">Deze methode is het beste _voor kleine organisaties met minder dan 100 K-apparaten._</span><span class="sxs-lookup"><span data-stu-id="8bee2-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="8bee2-116">Het antwoord is paginated, zodat u het veld odata.nextLink uit het antwoord kunt gebruiken \@ om de volgende resultaten op te halen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

2. <span data-ttu-id="8bee2-117">[Beoordeling van beveiligingsproblemen met software **via bestanden exporteren**](#2-export-software-vulnerabilities-assessment-via-files) Met deze API-oplossing kunt u sneller en betrouwbaarder grotere hoeveelheden gegevens verzamelen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-117">[Export software vulnerabilities assessment **via files**](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="8bee2-118">Via-bestanden wordt aanbevolen voor grote organisaties, met meer dan 100 K-apparaten.</span><span class="sxs-lookup"><span data-stu-id="8bee2-118">Via-files is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="8bee2-119">Met deze API worden alle gegevens in uw organisatie als downloadbestanden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="8bee2-120">Het antwoord bevat URL's om alle gegevens uit de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="8bee2-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="8bee2-121">Met deze API kunt u al uw gegevens als volgt Azure Storage downloaden:</span><span class="sxs-lookup"><span data-stu-id="8bee2-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

   - <span data-ttu-id="8bee2-122">Bel de API om een lijst met url's te downloaden met al uw organisatiegegevens.</span><span class="sxs-lookup"><span data-stu-id="8bee2-122">Call the API to get a list of download URLs with all your organization data.</span></span>

   - <span data-ttu-id="8bee2-123">Download alle bestanden met de download-URL's en verwerkt de gegevens naar eigen goed gebruik.</span><span class="sxs-lookup"><span data-stu-id="8bee2-123">Download all the files using the download URLs and process the data as you like.</span></span>

3. <span data-ttu-id="8bee2-124">[Delta Export software vulnerabilities assessment **JSON response**](#3-delta-export-software-vulnerabilities-assessment-json-response)  Retourneert een tabel met een vermelding voor elke unieke combinatie van: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId en EventTimestamp.</span><span class="sxs-lookup"><span data-stu-id="8bee2-124">[Delta export software vulnerabilities assessment **JSON response**](#3-delta-export-software-vulnerabilities-assessment-json-response)  Returns a table with an entry for every unique combination of: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId, and EventTimestamp.</span></span>
<span data-ttu-id="8bee2-125">De API haalt gegevens in uw organisatie op als Json-antwoorden.</span><span class="sxs-lookup"><span data-stu-id="8bee2-125">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="8bee2-126">Het antwoord is paginated, zodat u het veld @odata.nextLink uit het antwoord kunt gebruiken om de volgende resultaten op te halen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-126">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <br><br> <span data-ttu-id="8bee2-127">In tegenstelling tot de volledige beoordeling van softwareproblemen (JSON-antwoord) - die wordt gebruikt om een volledige momentopname van de beoordeling van de beveiligingsproblemen van de software van uw organisatie per apparaat te verkrijgen - wordt de delta export API-oproep gebruikt om alleen de wijzigingen op te halen die zijn gebeurd tussen een geselecteerde datum en de huidige datum (de 'delta' API-oproep).</span><span class="sxs-lookup"><span data-stu-id="8bee2-127">Unlike the full "software vulnerabilities assessment (JSON response)" - which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device - the delta export API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="8bee2-128">In plaats van elke keer een volledige export met een grote hoeveelheid gegevens te krijgen, krijgt u alleen specifieke informatie over nieuwe, opgeloste en bijgewerkte beveiligingslekken.</span><span class="sxs-lookup"><span data-stu-id="8bee2-128">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="8bee2-129">Delta export JSON response API call can also be used to calculate different KPI's such as "how many vulnerabilities were fixed?"</span><span class="sxs-lookup"><span data-stu-id="8bee2-129">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="8bee2-130">of 'hoeveel nieuwe beveiligingslekken zijn toegevoegd aan mijn organisatie?'</span><span class="sxs-lookup"><span data-stu-id="8bee2-130">or “how many new vulnerabilities were added to my organization?”</span></span> <br><br> <span data-ttu-id="8bee2-131">Omdat de Delta Export JSON response API call for software vulnerabilities data returns for only a targeted date range, it is not considered a _full export_.</span><span class="sxs-lookup"><span data-stu-id="8bee2-131">Because the Delta export JSON response API call for software vulnerabilities returns data for only a targeted date range, it is not considered a _full export_.</span></span>

<span data-ttu-id="8bee2-132">Gegevens die worden verzameld (met _Json-antwoord_ of _via_ bestanden) zijn de huidige momentopname van de huidige status en bevatten geen historische gegevens.</span><span class="sxs-lookup"><span data-stu-id="8bee2-132">Data that is collected (using either _Json response_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="8bee2-133">Om historische gegevens te verzamelen, moeten klanten de gegevens opslaan in hun eigen gegevensopslag.</span><span class="sxs-lookup"><span data-stu-id="8bee2-133">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="8bee2-134">Tenzij anders aangegeven, zijn alle vermelde exportbeoordelingsmethoden volledig **_geëxporteerd_** en **_per apparaat_** (ook wel per **_apparaat genoemd)._**</span><span class="sxs-lookup"><span data-stu-id="8bee2-134">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="8bee2-135">1. Evaluatie van softwareproblemen exporteren (JSON-antwoord)</span><span class="sxs-lookup"><span data-stu-id="8bee2-135">1. Export software vulnerabilities assessment (JSON response)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="8bee2-136">Beschrijving van API-methode 1.1</span><span class="sxs-lookup"><span data-stu-id="8bee2-136">1.1 API method description</span></span>

<span data-ttu-id="8bee2-137">Deze API-reactie bevat alle gegevens van geïnstalleerde software per apparaat.</span><span class="sxs-lookup"><span data-stu-id="8bee2-137">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="8bee2-138">Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="8bee2-138">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="8bee2-139">1.1.1 Beperkingen</span><span class="sxs-lookup"><span data-stu-id="8bee2-139">1.1.1 Limitations</span></span>

- <span data-ttu-id="8bee2-140">De maximale paginagrootte is 200.000.</span><span class="sxs-lookup"><span data-stu-id="8bee2-140">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="8bee2-141">Tariefbeperkingen voor deze API zijn 30 oproepen per minuut en 1000 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="8bee2-141">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="8bee2-142">1.2 Machtigingen</span><span class="sxs-lookup"><span data-stu-id="8bee2-142">1.2 Permissions</span></span>

<span data-ttu-id="8bee2-143">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-143">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8bee2-144">Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8bee2-144">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="8bee2-145">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="8bee2-145">Permission type</span></span> | <span data-ttu-id="8bee2-146">Machtiging</span><span class="sxs-lookup"><span data-stu-id="8bee2-146">Permission</span></span> | <span data-ttu-id="8bee2-147">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="8bee2-147">Permission display name</span></span>
---|---|---
<span data-ttu-id="8bee2-148">Toepassing</span><span class="sxs-lookup"><span data-stu-id="8bee2-148">Application</span></span> | <span data-ttu-id="8bee2-149">Kwetsbaarheid.Read.All</span><span class="sxs-lookup"><span data-stu-id="8bee2-149">Vulnerability.Read.All</span></span> | <span data-ttu-id="8bee2-150">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="8bee2-150">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="8bee2-151">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="8bee2-151">Delegated (work or school account)</span></span> | <span data-ttu-id="8bee2-152">Kwetsbaarheid.Lezen</span><span class="sxs-lookup"><span data-stu-id="8bee2-152">Vulnerability.Read</span></span> | <span data-ttu-id="8bee2-153">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="8bee2-153">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="8bee2-154">1,3 URL</span><span class="sxs-lookup"><span data-stu-id="8bee2-154">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="8bee2-155">1,4 Parameters</span><span class="sxs-lookup"><span data-stu-id="8bee2-155">1.4 Parameters</span></span>

- <span data-ttu-id="8bee2-156">pageSize (standaard = 50.000) – aantal resultaten in antwoord</span><span class="sxs-lookup"><span data-stu-id="8bee2-156">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="8bee2-157">$top – aantal resultaten dat moet worden retourneren (wordt niet als resultaat @odata.nextLink en dus niet alle gegevens)</span><span class="sxs-lookup"><span data-stu-id="8bee2-157">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="8bee2-158">1,5 eigenschappen</span><span class="sxs-lookup"><span data-stu-id="8bee2-158">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="8bee2-159">Elke record is ongeveer 1 KB aan gegevens.</span><span class="sxs-lookup"><span data-stu-id="8bee2-159">Each record is approximately 1 KB of data.</span></span> <span data-ttu-id="8bee2-160">U moet hiermee rekening houden bij het kiezen van de juiste paginaSize-parameter voor u.</span><span class="sxs-lookup"><span data-stu-id="8bee2-160">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="8bee2-161">Sommige extra kolommen kunnen worden geretourneerd in het antwoord.</span><span class="sxs-lookup"><span data-stu-id="8bee2-161">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="8bee2-162">Deze kolommen zijn tijdelijk en kunnen worden verwijderd, gebruik alleen de gedocumenteerde kolommen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-162">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="8bee2-163">De eigenschappen die in de volgende tabel zijn gedefinieerd, worden alfabetisch weergegeven op eigenschap-id.</span><span class="sxs-lookup"><span data-stu-id="8bee2-163">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="8bee2-164">Bij het uitvoeren van deze API wordt de resulterende uitvoer niet noodzakelijkerwijs geretourneerd in dezelfde volgorde als in deze tabel.</span><span class="sxs-lookup"><span data-stu-id="8bee2-164">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>

<br/>

<span data-ttu-id="8bee2-165">Eigenschap (id)</span><span class="sxs-lookup"><span data-stu-id="8bee2-165">Property (ID)</span></span> | <span data-ttu-id="8bee2-166">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="8bee2-166">Data type</span></span> | <span data-ttu-id="8bee2-167">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="8bee2-167">Description</span></span> | <span data-ttu-id="8bee2-168">Voorbeeld van een geretourneerde waarde</span><span class="sxs-lookup"><span data-stu-id="8bee2-168">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="8bee2-169">CveId</span><span class="sxs-lookup"><span data-stu-id="8bee2-169">CveId</span></span> | <span data-ttu-id="8bee2-170">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-170">string</span></span> | <span data-ttu-id="8bee2-171">Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures).</span><span class="sxs-lookup"><span data-stu-id="8bee2-171">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="8bee2-172">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="8bee2-172">CVE-2020-15992</span></span>
<span data-ttu-id="8bee2-173">CvssScore</span><span class="sxs-lookup"><span data-stu-id="8bee2-173">CvssScore</span></span> | <span data-ttu-id="8bee2-174">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-174">string</span></span> | <span data-ttu-id="8bee2-175">De CVSS-score van de CVE.</span><span class="sxs-lookup"><span data-stu-id="8bee2-175">The CVSS score of the CVE.</span></span> | <span data-ttu-id="8bee2-176">6.2</span><span class="sxs-lookup"><span data-stu-id="8bee2-176">6.2</span></span>
<span data-ttu-id="8bee2-177">DeviceId</span><span class="sxs-lookup"><span data-stu-id="8bee2-177">DeviceId</span></span> | <span data-ttu-id="8bee2-178">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-178">string</span></span> | <span data-ttu-id="8bee2-179">Unieke id voor het apparaat in de service.</span><span class="sxs-lookup"><span data-stu-id="8bee2-179">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="8bee2-180">9eaf3a8b5962e0e6b1af9ec75664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="8bee2-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="8bee2-181">Apparaatnaam</span><span class="sxs-lookup"><span data-stu-id="8bee2-181">DeviceName</span></span> | <span data-ttu-id="8bee2-182">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-182">string</span></span> | <span data-ttu-id="8bee2-183">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="8bee2-183">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="8bee2-184">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8bee2-184">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="8bee2-185">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="8bee2-185">DiskPaths</span></span>  | <span data-ttu-id="8bee2-186">\[Matrixreeks\]</span><span class="sxs-lookup"><span data-stu-id="8bee2-186">Array\[string\]</span></span> | <span data-ttu-id="8bee2-187">Schijf bewijs dat het product is geïnstalleerd op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="8bee2-187">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="8bee2-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="8bee2-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="8bee2-189">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="8bee2-189">ExploitabilityLevel</span></span> | <span data-ttu-id="8bee2-190">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-190">string</span></span> | <span data-ttu-id="8bee2-191">Het gebruiksniveau van dit beveiligingsprobleem (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="8bee2-191">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="8bee2-192">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="8bee2-192">ExploitIsInKit</span></span>
<span data-ttu-id="8bee2-193">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="8bee2-193">FirstSeenTimestamp</span></span> | <span data-ttu-id="8bee2-194">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-194">string</span></span> | <span data-ttu-id="8bee2-195">De eerste keer dat de CVE van dit product op het apparaat werd gezien.</span><span class="sxs-lookup"><span data-stu-id="8bee2-195">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="8bee2-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="8bee2-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="8bee2-197">Id</span><span class="sxs-lookup"><span data-stu-id="8bee2-197">Id</span></span> | <span data-ttu-id="8bee2-198">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-198">string</span></span> | <span data-ttu-id="8bee2-199">Unieke id voor de record.</span><span class="sxs-lookup"><span data-stu-id="8bee2-199">Unique identifier for the record.</span></span> | <span data-ttu-id="8bee2-200">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="8bee2-200">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="8bee2-201">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="8bee2-201">LastSeenTimestamp</span></span> | <span data-ttu-id="8bee2-202">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-202">string</span></span> | <span data-ttu-id="8bee2-203">De laatste keer dat de CVE werd gezien op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="8bee2-203">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="8bee2-204">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="8bee2-204">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="8bee2-205">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="8bee2-205">OSPlatform</span></span> | <span data-ttu-id="8bee2-206">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-206">string</span></span> | <span data-ttu-id="8bee2-207">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="8bee2-207">Platform of the operating system running on the device.</span></span> <span data-ttu-id="8bee2-208">Deze eigenschap geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="8bee2-208">This property indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="8bee2-209">Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8bee2-209">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="8bee2-210">Windows10</span><span class="sxs-lookup"><span data-stu-id="8bee2-210">Windows10</span></span>
<span data-ttu-id="8bee2-211">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="8bee2-211">RbacGroupName</span></span>  | <span data-ttu-id="8bee2-212">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-212">string</span></span> | <span data-ttu-id="8bee2-213">De groep Toegangsbeheer (RBAC) op basis van rollen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-213">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="8bee2-214">Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'.</span><span class="sxs-lookup"><span data-stu-id="8bee2-214">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="8bee2-215">Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'.</span><span class="sxs-lookup"><span data-stu-id="8bee2-215">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="8bee2-216">Servers</span><span class="sxs-lookup"><span data-stu-id="8bee2-216">Servers</span></span>
<span data-ttu-id="8bee2-217">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="8bee2-217">RecommendationReference</span></span> | <span data-ttu-id="8bee2-218">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-218">string</span></span> | <span data-ttu-id="8bee2-219">Een verwijzing naar de aanbevelings-id met betrekking tot deze software.</span><span class="sxs-lookup"><span data-stu-id="8bee2-219">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="8bee2-220">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="8bee2-220">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="8bee2-221">RecommendedSecurityUpdate (optioneel)</span><span class="sxs-lookup"><span data-stu-id="8bee2-221">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="8bee2-222">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-222">string</span></span> | <span data-ttu-id="8bee2-223">Naam of beschrijving van de beveiligingsupdate die door de softwareleverancier wordt geleverd om het beveiligingsprobleem aan te pakken.</span><span class="sxs-lookup"><span data-stu-id="8bee2-223">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="8bee2-224">Beveiligingsupdates van april 2020</span><span class="sxs-lookup"><span data-stu-id="8bee2-224">April 2020 Security Updates</span></span>
<span data-ttu-id="8bee2-225">AanbevolenSecurityUpdateId (optioneel)</span><span class="sxs-lookup"><span data-stu-id="8bee2-225">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="8bee2-226">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-226">string</span></span> | <span data-ttu-id="8bee2-227">Id van de toepasselijke beveiligingsupdates of -id voor de bijbehorende richtlijnen of KB-artikelen (Knowledge Base)</span><span class="sxs-lookup"><span data-stu-id="8bee2-227">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="8bee2-228">4550961</span><span class="sxs-lookup"><span data-stu-id="8bee2-228">4550961</span></span>
<span data-ttu-id="8bee2-229">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="8bee2-229">RegistryPaths</span></span>  | <span data-ttu-id="8bee2-230">\[Matrixreeks\]</span><span class="sxs-lookup"><span data-stu-id="8bee2-230">Array\[string\]</span></span> | <span data-ttu-id="8bee2-231">Registergegevens dat het product op het apparaat is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="8bee2-231">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="8bee2-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="8bee2-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="8bee2-233">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="8bee2-233">SoftwareName</span></span> | <span data-ttu-id="8bee2-234">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-234">string</span></span> | <span data-ttu-id="8bee2-235">Naam van het softwareproduct.</span><span class="sxs-lookup"><span data-stu-id="8bee2-235">Name of the software product.</span></span> | <span data-ttu-id="8bee2-236">chrome</span><span class="sxs-lookup"><span data-stu-id="8bee2-236">chrome</span></span>
<span data-ttu-id="8bee2-237">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="8bee2-237">SoftwareVendor</span></span> | <span data-ttu-id="8bee2-238">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-238">string</span></span> | <span data-ttu-id="8bee2-239">Naam van de softwareleverancier.</span><span class="sxs-lookup"><span data-stu-id="8bee2-239">Name of the software vendor.</span></span> | <span data-ttu-id="8bee2-240">google</span><span class="sxs-lookup"><span data-stu-id="8bee2-240">google</span></span>
<span data-ttu-id="8bee2-241">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="8bee2-241">SoftwareVersion</span></span> | <span data-ttu-id="8bee2-242">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-242">string</span></span> | <span data-ttu-id="8bee2-243">Versienummer van het softwareproduct.</span><span class="sxs-lookup"><span data-stu-id="8bee2-243">Version number of the software product.</span></span> | <span data-ttu-id="8bee2-244">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="8bee2-244">81.0.4044.138</span></span>
<span data-ttu-id="8bee2-245">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="8bee2-245">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="8bee2-246">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-246">string</span></span> | <span data-ttu-id="8bee2-247">Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap.</span><span class="sxs-lookup"><span data-stu-id="8bee2-247">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="8bee2-248">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="8bee2-248">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="8bee2-249">1.6 Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="8bee2-249">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="8bee2-250">1.6.1 Voorbeeld van aanvraag</span><span class="sxs-lookup"><span data-stu-id="8bee2-250">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="8bee2-251">1.6.2 Voorbeeld van antwoord</span><span class="sxs-lookup"><span data-stu-id="8bee2-251">1.6.2 Response example</span></span>

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

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="8bee2-252">2. Evaluatie van softwareproblemen exporteren (via bestanden)</span><span class="sxs-lookup"><span data-stu-id="8bee2-252">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="8bee2-253">Beschrijving van API-methode 2.1</span><span class="sxs-lookup"><span data-stu-id="8bee2-253">2.1 API method description</span></span>

<span data-ttu-id="8bee2-254">Deze API-reactie bevat alle gegevens van geïnstalleerde software per apparaat.</span><span class="sxs-lookup"><span data-stu-id="8bee2-254">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="8bee2-255">Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="8bee2-255">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="8bee2-256">2.1.2 Beperkingen</span><span class="sxs-lookup"><span data-stu-id="8bee2-256">2.1.2 Limitations</span></span>

<span data-ttu-id="8bee2-257">Tariefbeperkingen voor deze API zijn 5 oproepen per minuut en 20 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="8bee2-257">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="8bee2-258">2.2 Machtigingen</span><span class="sxs-lookup"><span data-stu-id="8bee2-258">2.2 Permissions</span></span>

<span data-ttu-id="8bee2-259">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-259">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8bee2-260">Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8bee2-260">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="8bee2-261">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="8bee2-261">Permission type</span></span> | <span data-ttu-id="8bee2-262">Machtiging</span><span class="sxs-lookup"><span data-stu-id="8bee2-262">Permission</span></span> | <span data-ttu-id="8bee2-263">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="8bee2-263">Permission display name</span></span>
---|---|---
<span data-ttu-id="8bee2-264">Toepassing</span><span class="sxs-lookup"><span data-stu-id="8bee2-264">Application</span></span> | <span data-ttu-id="8bee2-265">Kwetsbaarheid.Read.All</span><span class="sxs-lookup"><span data-stu-id="8bee2-265">Vulnerability.Read.All</span></span> | <span data-ttu-id="8bee2-266">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="8bee2-266">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="8bee2-267">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="8bee2-267">Delegated (work or school account)</span></span> | <span data-ttu-id="8bee2-268">Kwetsbaarheid.Lezen</span><span class="sxs-lookup"><span data-stu-id="8bee2-268">Vulnerability.Read</span></span> | <span data-ttu-id="8bee2-269">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="8bee2-269">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="8bee2-270">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="8bee2-270">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="8bee2-271">2.4 Parameters</span><span class="sxs-lookup"><span data-stu-id="8bee2-271">2.4 Parameters</span></span>

- <span data-ttu-id="8bee2-272">sasValidHours: het aantal uren dat de download-URL's geldig zijn (maximaal 24 uur)</span><span class="sxs-lookup"><span data-stu-id="8bee2-272">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="8bee2-273">2,5 eigenschappen</span><span class="sxs-lookup"><span data-stu-id="8bee2-273">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="8bee2-274">De bestanden zijn gzip gecomprimeerde & in de Json-indeling met meerdere lijnen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-274">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="8bee2-275">De DOWNLOAD-URL's zijn slechts 3 uur geldig. anders kunt u de parameter gebruiken.</span><span class="sxs-lookup"><span data-stu-id="8bee2-275">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="8bee2-276">Voor maximale downloadsnelheid van uw gegevens kunt u ervoor zorgen dat u downloadt vanuit dezelfde Azure-regio als uw gegevens.</span><span class="sxs-lookup"><span data-stu-id="8bee2-276">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="8bee2-277">Elke record is ongeveer 1 KB aan gegevens.</span><span class="sxs-lookup"><span data-stu-id="8bee2-277">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="8bee2-278">U moet hiermee rekening houden bij het kiezen van de juiste paginaSize-parameter voor u.</span><span class="sxs-lookup"><span data-stu-id="8bee2-278">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="8bee2-279">Sommige extra kolommen kunnen worden geretourneerd in het antwoord.</span><span class="sxs-lookup"><span data-stu-id="8bee2-279">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="8bee2-280">Deze kolommen zijn tijdelijk en kunnen worden verwijderd, gebruik alleen de gedocumenteerde kolommen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-280">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="8bee2-281">Eigenschap (id)</span><span class="sxs-lookup"><span data-stu-id="8bee2-281">Property (ID)</span></span> | <span data-ttu-id="8bee2-282">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="8bee2-282">Data type</span></span> | <span data-ttu-id="8bee2-283">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="8bee2-283">Description</span></span> | <span data-ttu-id="8bee2-284">Voorbeeld van een geretourneerde waarde</span><span class="sxs-lookup"><span data-stu-id="8bee2-284">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="8bee2-285">Bestanden exporteren</span><span class="sxs-lookup"><span data-stu-id="8bee2-285">Export files</span></span> | <span data-ttu-id="8bee2-286">\[matrixreeks\]</span><span class="sxs-lookup"><span data-stu-id="8bee2-286">array\[string\]</span></span>  | <span data-ttu-id="8bee2-287">Een lijst met download-URL's voor bestanden met de huidige momentopname van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="8bee2-287">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="8bee2-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="8bee2-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="8bee2-289">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="8bee2-289">GeneratedTime</span></span> | <span data-ttu-id="8bee2-290">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-290">string</span></span> | <span data-ttu-id="8bee2-291">De tijd dat de export is gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="8bee2-291">The time that the export was generated.</span></span> | <span data-ttu-id="8bee2-292">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="8bee2-292">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="8bee2-293">2.6 Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="8bee2-293">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="8bee2-294">2.6.1 Voorbeeld van aanvraag</span><span class="sxs-lookup"><span data-stu-id="8bee2-294">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="8bee2-295">2.6.2 Voorbeeld van antwoord</span><span class="sxs-lookup"><span data-stu-id="8bee2-295">2.6.2 Response example</span></span>

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

## <a name="3-delta-export-software-vulnerabilities-assessment-json-response"></a><span data-ttu-id="8bee2-296">3. Evaluatie van beveiligingsproblemen bij Delta-exportsoftware (JSON-antwoord)</span><span class="sxs-lookup"><span data-stu-id="8bee2-296">3. Delta export software vulnerabilities assessment (JSON response)</span></span>

### <a name="31-api-method-description"></a><span data-ttu-id="8bee2-297">Beschrijving van API-methode 3.1</span><span class="sxs-lookup"><span data-stu-id="8bee2-297">3.1 API method description</span></span>

<span data-ttu-id="8bee2-298">Retourneert een tabel met een vermelding voor elke unieke combinatie van DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span><span class="sxs-lookup"><span data-stu-id="8bee2-298">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span></span> <span data-ttu-id="8bee2-299">De API haalt gegevens in uw organisatie op als Json-antwoorden.</span><span class="sxs-lookup"><span data-stu-id="8bee2-299">The API pulls data in your organization as Json responses.</span></span> <span data-ttu-id="8bee2-300">Het antwoord is paginated, zodat u het veld @odata.nextLink uit het antwoord kunt gebruiken om de volgende resultaten op te halen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-300">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <span data-ttu-id="8bee2-301">In tegenstelling tot de evaluatie van de volledige softwareproblemen (JSON-antwoord), die wordt gebruikt om een volledige momentopname van de beoordeling van de beveiligingsproblemen in de software van uw organisatie per apparaat te verkrijgen, wordt de delta export JSON-antwoord-API-oproep gebruikt om alleen de wijzigingen op te halen die zijn gebeurd tussen een geselecteerde datum en de huidige datum (de 'delta' API-oproep).</span><span class="sxs-lookup"><span data-stu-id="8bee2-301">Unlike the full software vulnerabilities assessment (JSON response)—which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device—the delta export JSON response API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="8bee2-302">In plaats van elke keer een volledige export met een grote hoeveelheid gegevens te krijgen, krijgt u alleen specifieke informatie over nieuwe, opgeloste en bijgewerkte beveiligingslekken.</span><span class="sxs-lookup"><span data-stu-id="8bee2-302">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="8bee2-303">Delta export JSON response API call can also be used to calculate different KPI's such as "how many vulnerabilities were fixed?"</span><span class="sxs-lookup"><span data-stu-id="8bee2-303">Delta export JSON response API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="8bee2-304">of 'hoeveel nieuwe beveiligingslekken zijn toegevoegd aan mijn organisatie?'</span><span class="sxs-lookup"><span data-stu-id="8bee2-304">or “how many new vulnerabilities were added to my organization?”</span></span>

>[!NOTE]
>
><span data-ttu-id="8bee2-305">Het wordt ten zeerste aangeraden om ten minste één keer per week de volledige evaluatie van beveiligingsproblemen met de exportsoftware te gebruiken per apparaat-API-oproep, en deze extra exportsoftwareproblemen worden op alle andere dagen van de week gewijzigd door de apparaat-API(delta)-API- oproep.</span><span class="sxs-lookup"><span data-stu-id="8bee2-305">It is highly recommended you use the full export software vulnerabilities assessment by device API call at least once a week, and this additional export software vulnerabilities changes by device (delta) API call all the other days of the week.</span></span>  <span data-ttu-id="8bee2-306">In tegenstelling tot de andere beoordelings-JSON-antwoord-API's, is de 'delta-export' geen volledige export.</span><span class="sxs-lookup"><span data-stu-id="8bee2-306">Unlike the other Assessments JSON response APIs, the “delta export” is not a full export.</span></span> <span data-ttu-id="8bee2-307">De delta-export bevat alleen de wijzigingen tussen een geselecteerde datum en de huidige datum (de 'delta'-API-oproep).</span><span class="sxs-lookup"><span data-stu-id="8bee2-307">The delta export includes only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span>

#### <a name="311-limitations"></a><span data-ttu-id="8bee2-308">3.1.1 Beperkingen</span><span class="sxs-lookup"><span data-stu-id="8bee2-308">3.1.1 Limitations</span></span>

- <span data-ttu-id="8bee2-309">De maximale paginagrootte is 200.000.</span><span class="sxs-lookup"><span data-stu-id="8bee2-309">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="8bee2-310">De parameter sinceTime heeft een maximum van 14 dagen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-310">The sinceTime parameter has a maximum of 14 days.</span></span>

- <span data-ttu-id="8bee2-311">Tariefbeperkingen voor deze API zijn 30 oproepen per minuut en 1000 oproepen per uur.</span><span class="sxs-lookup"><span data-stu-id="8bee2-311">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="32-permissions"></a><span data-ttu-id="8bee2-312">3.2 Machtigingen</span><span class="sxs-lookup"><span data-stu-id="8bee2-312">3.2 Permissions</span></span>

<span data-ttu-id="8bee2-313">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-313">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8bee2-314">Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8bee2-314">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="8bee2-315">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="8bee2-315">Permission type</span></span> | <span data-ttu-id="8bee2-316">Machtiging</span><span class="sxs-lookup"><span data-stu-id="8bee2-316">Permission</span></span> | <span data-ttu-id="8bee2-317">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="8bee2-317">Permission display name</span></span>
---|---|---
<span data-ttu-id="8bee2-318">Toepassing</span><span class="sxs-lookup"><span data-stu-id="8bee2-318">Application</span></span> | <span data-ttu-id="8bee2-319">Kwetsbaarheid.Read.All</span><span class="sxs-lookup"><span data-stu-id="8bee2-319">Vulnerability.Read.All</span></span> | <span data-ttu-id="8bee2-320">'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="8bee2-320">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="8bee2-321">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="8bee2-321">Delegated (work or school account)</span></span> | <span data-ttu-id="8bee2-322">Kwetsbaarheid.Lezen</span><span class="sxs-lookup"><span data-stu-id="8bee2-322">Vulnerability.Read</span></span> | <span data-ttu-id="8bee2-323">'Informatie over kwetsbaarheidsinformatie over bedreigings- en kwetsbaarheidsbeheer lezen'</span><span class="sxs-lookup"><span data-stu-id="8bee2-323">'Read Threat and Vulnerability Management vulnerability information'</span></span>

### <a name="33-url"></a><span data-ttu-id="8bee2-324">URL van 3,3</span><span class="sxs-lookup"><span data-stu-id="8bee2-324">3.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a><span data-ttu-id="8bee2-325">3.4 Parameters</span><span class="sxs-lookup"><span data-stu-id="8bee2-325">3.4 Parameters</span></span>

- <span data-ttu-id="8bee2-326">sinceTime (vereist) – De gegevens tussen een geselecteerde tijd en vandaag.</span><span class="sxs-lookup"><span data-stu-id="8bee2-326">sinceTime (required) – The data between a selected time and today.</span></span>
- <span data-ttu-id="8bee2-327">pageSize (standaard = 50.000) – aantal resultaten in antwoord</span><span class="sxs-lookup"><span data-stu-id="8bee2-327">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="8bee2-328">$top – aantal resultaten dat moet worden retourneren (wordt niet als resultaat @odata.nextLink en dus niet alle gegevens)</span><span class="sxs-lookup"><span data-stu-id="8bee2-328">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="35-properties"></a><span data-ttu-id="8bee2-329">3,5 eigenschappen</span><span class="sxs-lookup"><span data-stu-id="8bee2-329">3.5 Properties</span></span>

<span data-ttu-id="8bee2-330">Elke geretourneerde record bevat alle gegevens van de volledige evaluatie van beveiligingsproblemen met software via de apparaat-API, plus twee extra velden: _**EventTimestamp**_ en _**Status.**_</span><span class="sxs-lookup"><span data-stu-id="8bee2-330">Each returned record contains all the data from the full export software vulnerabilities assessment by device API, plus two additional fields:  _**EventTimestamp**_ and _**Status**_.</span></span>

>[!NOTE]
>- <span data-ttu-id="8bee2-331">Sommige extra kolommen kunnen worden geretourneerd in het antwoord.</span><span class="sxs-lookup"><span data-stu-id="8bee2-331">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="8bee2-332">Deze kolommen zijn tijdelijk en kunnen worden verwijderd, dus gebruik alleen de gedocumenteerde kolommen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-332">These columns are temporary and might be removed, so please use only the documented columns.</span></span>
>
>- <span data-ttu-id="8bee2-333">De eigenschappen die in de volgende tabel zijn gedefinieerd, worden alfabetisch weergegeven op eigenschap-id.</span><span class="sxs-lookup"><span data-stu-id="8bee2-333">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="8bee2-334">Bij het uitvoeren van deze API wordt de resulterende uitvoer niet noodzakelijkerwijs geretourneerd in dezelfde volgorde als in deze tabel.</span><span class="sxs-lookup"><span data-stu-id="8bee2-334">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
<br><br/>

<span data-ttu-id="8bee2-335">Eigenschap (id)</span><span class="sxs-lookup"><span data-stu-id="8bee2-335">Property (ID)</span></span> | <span data-ttu-id="8bee2-336">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="8bee2-336">Data type</span></span> | <span data-ttu-id="8bee2-337">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="8bee2-337">Description</span></span> | <span data-ttu-id="8bee2-338">Voorbeeld van geretourneerde waarde</span><span class="sxs-lookup"><span data-stu-id="8bee2-338">Example of returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="8bee2-339">CveId</span><span class="sxs-lookup"><span data-stu-id="8bee2-339">CveId</span></span> | <span data-ttu-id="8bee2-340">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-340">string</span></span> | <span data-ttu-id="8bee2-341">Unieke id die is toegewezen aan het beveiligingsprobleem onder het CVE-systeem (Common Vulnerabilities and Exposures).</span><span class="sxs-lookup"><span data-stu-id="8bee2-341">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="8bee2-342">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="8bee2-342">CVE-2020-15992</span></span>  
<span data-ttu-id="8bee2-343">CvssScore</span><span class="sxs-lookup"><span data-stu-id="8bee2-343">CvssScore</span></span> | <span data-ttu-id="8bee2-344">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-344">string</span></span> | <span data-ttu-id="8bee2-345">De CVSS-score van de CVE.</span><span class="sxs-lookup"><span data-stu-id="8bee2-345">The CVSS score of the CVE.</span></span> | <span data-ttu-id="8bee2-346">6.2</span><span class="sxs-lookup"><span data-stu-id="8bee2-346">6.2</span></span>  
<span data-ttu-id="8bee2-347">DeviceId</span><span class="sxs-lookup"><span data-stu-id="8bee2-347">DeviceId</span></span> | <span data-ttu-id="8bee2-348">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-348">string</span></span> | <span data-ttu-id="8bee2-349">Unieke id voor het apparaat in de service.</span><span class="sxs-lookup"><span data-stu-id="8bee2-349">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="8bee2-350">9eaf3a8b5962e0e6b1af9ec75664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="8bee2-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>  
<span data-ttu-id="8bee2-351">Apparaatnaam</span><span class="sxs-lookup"><span data-stu-id="8bee2-351">DeviceName</span></span> | <span data-ttu-id="8bee2-352">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-352">string</span></span> | <span data-ttu-id="8bee2-353">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="8bee2-353">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="8bee2-354">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8bee2-354">johnlaptop.europe.contoso.com</span></span>  
<span data-ttu-id="8bee2-355">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="8bee2-355">DiskPaths</span></span> | <span data-ttu-id="8bee2-356">Matrix[tekenreeks]</span><span class="sxs-lookup"><span data-stu-id="8bee2-356">Array[string]</span></span> | <span data-ttu-id="8bee2-357">Schijf bewijs dat het product is geïnstalleerd op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="8bee2-357">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="8bee2-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="8bee2-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>  
<span data-ttu-id="8bee2-359">EventTimestamp</span><span class="sxs-lookup"><span data-stu-id="8bee2-359">EventTimestamp</span></span> | <span data-ttu-id="8bee2-360">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8bee2-360">String</span></span> | <span data-ttu-id="8bee2-361">De tijd dat deze deltagebeurtenis is gevonden.</span><span class="sxs-lookup"><span data-stu-id="8bee2-361">The time this delta event was found.</span></span> | <span data-ttu-id="8bee2-362">2021-01-11T11:06:08.291Z</span><span class="sxs-lookup"><span data-stu-id="8bee2-362">2021-01-11T11:06:08.291Z</span></span>
<span data-ttu-id="8bee2-363">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="8bee2-363">ExploitabilityLevel</span></span> | <span data-ttu-id="8bee2-364">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-364">string</span></span> | <span data-ttu-id="8bee2-365">Het gebruiksniveau van dit beveiligingsprobleem (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="8bee2-365">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="8bee2-366">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="8bee2-366">ExploitIsInKit</span></span>  
<span data-ttu-id="8bee2-367">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="8bee2-367">FirstSeenTimestamp</span></span> | <span data-ttu-id="8bee2-368">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-368">string</span></span> | <span data-ttu-id="8bee2-369">De eerste keer dat de CVE van dit product op het apparaat werd gezien.</span><span class="sxs-lookup"><span data-stu-id="8bee2-369">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="8bee2-370">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="8bee2-370">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="8bee2-371">Id</span><span class="sxs-lookup"><span data-stu-id="8bee2-371">Id</span></span> | <span data-ttu-id="8bee2-372">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-372">string</span></span> | <span data-ttu-id="8bee2-373">Unieke id voor de record.</span><span class="sxs-lookup"><span data-stu-id="8bee2-373">Unique identifier for the record.</span></span> | <span data-ttu-id="8bee2-374">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="8bee2-374">123ABG55_573AG&mnp!</span></span>  
<span data-ttu-id="8bee2-375">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="8bee2-375">LastSeenTimestamp</span></span> | <span data-ttu-id="8bee2-376">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-376">string</span></span> | <span data-ttu-id="8bee2-377">De laatste keer dat de CVE werd gezien op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="8bee2-377">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="8bee2-378">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="8bee2-378">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="8bee2-379">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="8bee2-379">OSPlatform</span></span> | <span data-ttu-id="8bee2-380">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-380">string</span></span> | <span data-ttu-id="8bee2-381">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="8bee2-381">Platform of the operating system running on the device.</span></span> <span data-ttu-id="8bee2-382">Dit geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="8bee2-382">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="8bee2-383">Zie ondersteunde besturingssystemen en platforms van tvm voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8bee2-383">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="8bee2-384">Windows10</span><span class="sxs-lookup"><span data-stu-id="8bee2-384">Windows10</span></span>  
<span data-ttu-id="8bee2-385">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="8bee2-385">RbacGroupName</span></span> | <span data-ttu-id="8bee2-386">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-386">string</span></span> | <span data-ttu-id="8bee2-387">De groep Toegangsbeheer (RBAC) op basis van rollen.</span><span class="sxs-lookup"><span data-stu-id="8bee2-387">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="8bee2-388">Als dit apparaat niet is toegewezen aan een RBAC-groep, is de waarde 'Niet toegewezen'.</span><span class="sxs-lookup"><span data-stu-id="8bee2-388">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="8bee2-389">Als de organisatie geen RBAC-groepen bevat, is de waarde 'Geen'.</span><span class="sxs-lookup"><span data-stu-id="8bee2-389">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="8bee2-390">Servers</span><span class="sxs-lookup"><span data-stu-id="8bee2-390">Servers</span></span>  
<span data-ttu-id="8bee2-391">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="8bee2-391">RecommendationReference</span></span> | <span data-ttu-id="8bee2-392">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-392">string</span></span> | <span data-ttu-id="8bee2-393">Een verwijzing naar de aanbevelings-id met betrekking tot deze software.</span><span class="sxs-lookup"><span data-stu-id="8bee2-393">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="8bee2-394">va--microsoft--silverlight</span><span class="sxs-lookup"><span data-stu-id="8bee2-394">va--microsoft--silverlight</span></span>  
<span data-ttu-id="8bee2-395">AanbevolenSecurityUpdate</span><span class="sxs-lookup"><span data-stu-id="8bee2-395">RecommendedSecurityUpdate</span></span>  | <span data-ttu-id="8bee2-396">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-396">string</span></span> | <span data-ttu-id="8bee2-397">Naam of beschrijving van de beveiligingsupdate die door de softwareleverancier wordt geleverd om het beveiligingsprobleem aan te pakken.</span><span class="sxs-lookup"><span data-stu-id="8bee2-397">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="8bee2-398">Beveiligingsupdates van april 2020</span><span class="sxs-lookup"><span data-stu-id="8bee2-398">April 2020 Security Updates</span></span>  
<span data-ttu-id="8bee2-399">AanbevolenSecurityUpdateId</span><span class="sxs-lookup"><span data-stu-id="8bee2-399">RecommendedSecurityUpdateId</span></span>  | <span data-ttu-id="8bee2-400">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-400">string</span></span> | <span data-ttu-id="8bee2-401">Id van de toepasselijke beveiligingsupdates of -id voor de bijbehorende richtlijnen of KB-artikelen (Knowledge Base)</span><span class="sxs-lookup"><span data-stu-id="8bee2-401">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="8bee2-402">4550961</span><span class="sxs-lookup"><span data-stu-id="8bee2-402">4550961</span></span>  
<span data-ttu-id="8bee2-403">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="8bee2-403">RegistryPaths</span></span>  | <span data-ttu-id="8bee2-404">Matrix[tekenreeks]</span><span class="sxs-lookup"><span data-stu-id="8bee2-404">Array[string]</span></span> | <span data-ttu-id="8bee2-405">Registergegevens dat het product op het apparaat is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="8bee2-405">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="8bee2-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span><span class="sxs-lookup"><span data-stu-id="8bee2-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span></span>  
<span data-ttu-id="8bee2-407">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="8bee2-407">SoftwareName</span></span> | <span data-ttu-id="8bee2-408">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-408">string</span></span> | <span data-ttu-id="8bee2-409">Naam van het softwareproduct.</span><span class="sxs-lookup"><span data-stu-id="8bee2-409">Name of the software product.</span></span> | <span data-ttu-id="8bee2-410">chrome</span><span class="sxs-lookup"><span data-stu-id="8bee2-410">chrome</span></span>  
<span data-ttu-id="8bee2-411">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="8bee2-411">SoftwareVendor</span></span> | <span data-ttu-id="8bee2-412">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-412">string</span></span> | <span data-ttu-id="8bee2-413">Naam van de softwareleverancier.</span><span class="sxs-lookup"><span data-stu-id="8bee2-413">Name of the software vendor.</span></span> | <span data-ttu-id="8bee2-414">google</span><span class="sxs-lookup"><span data-stu-id="8bee2-414">google</span></span>  
<span data-ttu-id="8bee2-415">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="8bee2-415">SoftwareVersion</span></span> | <span data-ttu-id="8bee2-416">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-416">string</span></span> | <span data-ttu-id="8bee2-417">Versienummer van het softwareproduct.</span><span class="sxs-lookup"><span data-stu-id="8bee2-417">Version number of the software product.</span></span> | <span data-ttu-id="8bee2-418">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="8bee2-418">81.0.4044.138</span></span>  
<span data-ttu-id="8bee2-419">Status</span><span class="sxs-lookup"><span data-stu-id="8bee2-419">Status</span></span> | <span data-ttu-id="8bee2-420">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8bee2-420">String</span></span> | <span data-ttu-id="8bee2-421">**Nieuw**   (voor een nieuw beveiligingsprobleem dat is geïntroduceerd op een apparaat)  (1) **Opgelost**(als dit beveiligingsprobleem niet meer bestaat op het apparaat, wat betekent dat het   is hersteld).</span><span class="sxs-lookup"><span data-stu-id="8bee2-421">**New** (for a new vulnerability introduced on a device)  (1) **Fixed** (if this vulnerability doesn’t exist anymore on the device, which means it was remediated).</span></span> <span data-ttu-id="8bee2-422">(2)  **Bijgewerkt**   (als een beveiligingsprobleem op een apparaat is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="8bee2-422">(2) **Updated** (if a vulnerability on a device has changed.</span></span> <span data-ttu-id="8bee2-423">De mogelijke wijzigingen zijn: CVSS-score, exploitabilityniveau, ernstniveau, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span><span class="sxs-lookup"><span data-stu-id="8bee2-423">The possible changes are: CVSS score, exploitability level, severity level, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span></span> | <span data-ttu-id="8bee2-424">Opgelost</span><span class="sxs-lookup"><span data-stu-id="8bee2-424">Fixed</span></span>
<span data-ttu-id="8bee2-425">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="8bee2-425">VulnerabilitySeverityLevel</span></span> | <span data-ttu-id="8bee2-426">string</span><span class="sxs-lookup"><span data-stu-id="8bee2-426">string</span></span> | <span data-ttu-id="8bee2-427">Ernstniveau dat is toegewezen aan het beveiligingsprobleem op basis van de CVSS-score en dynamische factoren die worden beïnvloed door het bedreigingslandschap.</span><span class="sxs-lookup"><span data-stu-id="8bee2-427">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="8bee2-428">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="8bee2-428">Medium</span></span>  

#### <a name="clarifications"></a><span data-ttu-id="8bee2-429">Verduidelijkingen</span><span class="sxs-lookup"><span data-stu-id="8bee2-429">Clarifications</span></span>

- <span data-ttu-id="8bee2-430">Als de software is bijgewerkt van versie 1.0 naar versie 2.0 en beide versies worden blootgesteld aan CVE-A, ontvangt u twee afzonderlijke gebeurtenissen:</span><span class="sxs-lookup"><span data-stu-id="8bee2-430">If the software was updated from version 1.0 to version 2.0, and both versions are exposed to CVE-A, you will receive 2 separate events:</span></span>  
   1. <span data-ttu-id="8bee2-431">Opgelost : CVE-A op versie 1.0 is opgelost</span><span class="sxs-lookup"><span data-stu-id="8bee2-431">Fixed – CVE-A on version 1.0 was fixed</span></span>  
   1. <span data-ttu-id="8bee2-432">Nieuw : CVE-A op versie 2.0 is toegevoegd</span><span class="sxs-lookup"><span data-stu-id="8bee2-432">New – CVE-A on version 2.0 was added</span></span>

- <span data-ttu-id="8bee2-433">Als een specifiek beveiligingsprobleem (bijvoorbeeld CVE-A) voor het eerst werd gezien op een specifiek tijdstip (bijvoorbeeld 10 januari) op software met versie 1.0 en een paar dagen later die software is bijgewerkt naar versie 2.0 die ook aan dezelfde CVE-A is blootgesteld, ontvangt u deze twee gescheiden gebeurtenissen:</span><span class="sxs-lookup"><span data-stu-id="8bee2-433">If a specific vulnerability (for example, CVE-A) was first seen at a specific time (for example, January 10) on software with version 1.0, and a few days later that software was updated to version 2.0 which also exposed to the same CVE-A, you will receive these two separated events:</span></span>  
   1. <span data-ttu-id="8bee2-434">Opgelost: CVE-X, FirstSeenTimestamp 10 januari, versie 1,0.</span><span class="sxs-lookup"><span data-stu-id="8bee2-434">Fixed – CVE-X, FirstSeenTimestamp January 10, version 1,0.</span></span>  
   1. <span data-ttu-id="8bee2-435">Nieuw : CVE-X, FirstSeenTimestamp 10 januari, versie 2.0.</span><span class="sxs-lookup"><span data-stu-id="8bee2-435">New – CVE-X, FirstSeenTimestamp January 10, version 2.0.</span></span>

### <a name="36-examples"></a><span data-ttu-id="8bee2-436">3.6 Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="8bee2-436">3.6 Examples</span></span>

#### <a name="361-request-example"></a><span data-ttu-id="8bee2-437">3.6.1 Voorbeeld van aanvraag</span><span class="sxs-lookup"><span data-stu-id="8bee2-437">3.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a><span data-ttu-id="8bee2-438">3.6.2 Voorbeeld van antwoord</span><span class="sxs-lookup"><span data-stu-id="8bee2-438">3.6.2 Response example</span></span>

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a><span data-ttu-id="8bee2-439">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8bee2-439">See also</span></span>

- [<span data-ttu-id="8bee2-440">Beoordelingsmethoden en -eigenschappen per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="8bee2-440">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="8bee2-441">Veilige configuratiebeoordeling per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="8bee2-441">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="8bee2-442">Beoordeling van de softwarevoorraad per apparaat exporteren</span><span class="sxs-lookup"><span data-stu-id="8bee2-442">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

<span data-ttu-id="8bee2-443">Andere gerelateerde</span><span class="sxs-lookup"><span data-stu-id="8bee2-443">Other related</span></span>

- [<span data-ttu-id="8bee2-444">Risicogebaseerd & vulnerability management</span><span class="sxs-lookup"><span data-stu-id="8bee2-444">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="8bee2-445">Beveiligingslekken in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="8bee2-445">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
