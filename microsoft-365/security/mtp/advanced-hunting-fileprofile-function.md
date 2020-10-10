---
title: FileProfile (), functie in geavanceerde jacht voor Microsoft Threat Protection
description: Meer informatie over het gebruik van de FileProfile () om informatie te verrijken over bestanden in uw geavanceerde zoekresultaten voor de jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, FileProfile, bestands profiel, functie, verrijking
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: a89622206917c6b343ce47638c443b789513367b
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412176"
---
# <a name="fileprofile"></a><span data-ttu-id="90584-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="90584-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="90584-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="90584-105">**Applies to:**</span></span>
- <span data-ttu-id="90584-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="90584-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="90584-107">De `FileProfile()` functie is een verrijkings functie in de [geavanceerde jacht](advanced-hunting-overview.md) waarmee de volgende gegevens worden toegevoegd aan bestanden die door de query zijn gevonden.</span><span class="sxs-lookup"><span data-stu-id="90584-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="90584-108">Kolom</span><span class="sxs-lookup"><span data-stu-id="90584-108">Column</span></span> | <span data-ttu-id="90584-109">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="90584-109">Data type</span></span> | <span data-ttu-id="90584-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="90584-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="90584-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="90584-111">SHA1</span></span> | <span data-ttu-id="90584-112">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="90584-112">string</span></span> | <span data-ttu-id="90584-113">SHA-1 van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="90584-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="90584-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="90584-114">SHA256</span></span> | <span data-ttu-id="90584-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="90584-115">string</span></span> | <span data-ttu-id="90584-116">SHA-256 van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="90584-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="90584-117">MD5 ()</span><span class="sxs-lookup"><span data-stu-id="90584-117">MD5</span></span> | <span data-ttu-id="90584-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="90584-118">string</span></span> | <span data-ttu-id="90584-119">MD5-hash van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="90584-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="90584-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="90584-120">FileSize</span></span> | <span data-ttu-id="90584-121">int</span><span class="sxs-lookup"><span data-stu-id="90584-121">int</span></span> | <span data-ttu-id="90584-122">Bestandsgrootte in bytes</span><span class="sxs-lookup"><span data-stu-id="90584-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="90584-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="90584-123">GlobalPrevalence</span></span> | <span data-ttu-id="90584-124">int</span><span class="sxs-lookup"><span data-stu-id="90584-124">int</span></span> | <span data-ttu-id="90584-125">Aantal exemplaren van de entiteit die is waargenomen door Microsoft Global</span><span class="sxs-lookup"><span data-stu-id="90584-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="90584-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="90584-126">GlobalFirstSeen</span></span> | <span data-ttu-id="90584-127">tijd</span><span class="sxs-lookup"><span data-stu-id="90584-127">datetime</span></span> | <span data-ttu-id="90584-128">De datum en tijd waarop de entiteit voor het eerst werd gevolgd door Microsoft Global</span><span class="sxs-lookup"><span data-stu-id="90584-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="90584-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="90584-129">GlobalLastSeen</span></span> | <span data-ttu-id="90584-130">tijd</span><span class="sxs-lookup"><span data-stu-id="90584-130">datetime</span></span> | <span data-ttu-id="90584-131">De datum en tijd waarop de entiteit voor het laatst is geobserveerd door Microsoft Global</span><span class="sxs-lookup"><span data-stu-id="90584-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="90584-132">Ondertekenaar</span><span class="sxs-lookup"><span data-stu-id="90584-132">Signer</span></span> | <span data-ttu-id="90584-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="90584-133">string</span></span> | <span data-ttu-id="90584-134">Informatie over de ondertekenaar van het bestand</span><span class="sxs-lookup"><span data-stu-id="90584-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="90584-135">Verstrekker</span><span class="sxs-lookup"><span data-stu-id="90584-135">Issuer</span></span> | <span data-ttu-id="90584-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="90584-136">string</span></span> | <span data-ttu-id="90584-137">Informatie over de uitgevende certificeringsinstantie (CA)</span><span class="sxs-lookup"><span data-stu-id="90584-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="90584-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="90584-138">SignerHash</span></span> | <span data-ttu-id="90584-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="90584-139">string</span></span> | <span data-ttu-id="90584-140">Unieke hash-waarde die de ondertekenaar identificeert</span><span class="sxs-lookup"><span data-stu-id="90584-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="90584-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="90584-141">IsCertificateValid</span></span> | <span data-ttu-id="90584-142">Boolean</span><span class="sxs-lookup"><span data-stu-id="90584-142">boolean</span></span> | <span data-ttu-id="90584-143">Opgeven of het certificaat dat wordt gebruikt om het bestand te ondertekenen geldig is</span><span class="sxs-lookup"><span data-stu-id="90584-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="90584-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="90584-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="90584-145">Boolean</span><span class="sxs-lookup"><span data-stu-id="90584-145">boolean</span></span> | <span data-ttu-id="90584-146">Geeft aan of de ondertekenaar van het basiscertificaat Microsoft is</span><span class="sxs-lookup"><span data-stu-id="90584-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="90584-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="90584-147">IsExecutable</span></span> | <span data-ttu-id="90584-148">Boolean</span><span class="sxs-lookup"><span data-stu-id="90584-148">boolean</span></span> | <span data-ttu-id="90584-149">Opgeven of het bestand een bestand is van een Portable Executable (PE)</span><span class="sxs-lookup"><span data-stu-id="90584-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="90584-150">Bedreiging</span><span class="sxs-lookup"><span data-stu-id="90584-150">ThreatName</span></span> | <span data-ttu-id="90584-151">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="90584-151">string</span></span> | <span data-ttu-id="90584-152">Detectie naam voor malware of andere bedreigingen gevonden</span><span class="sxs-lookup"><span data-stu-id="90584-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="90584-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="90584-153">Publisher</span></span> | <span data-ttu-id="90584-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="90584-154">string</span></span> | <span data-ttu-id="90584-155">Naam van de organisatie die het bestand heeft gepubliceerd</span><span class="sxs-lookup"><span data-stu-id="90584-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="90584-156">Softwarenaam</span><span class="sxs-lookup"><span data-stu-id="90584-156">SoftwareName</span></span> | <span data-ttu-id="90584-157">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="90584-157">string</span></span> | <span data-ttu-id="90584-158">Naam van het SOFTWAREPRODUCT</span><span class="sxs-lookup"><span data-stu-id="90584-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="90584-159">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="90584-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="90584-160">Argumenten</span><span class="sxs-lookup"><span data-stu-id="90584-160">Arguments</span></span>

- <span data-ttu-id="90584-161">**x**— kolom met bestands-id die moet worden gebruikt: `SHA1` , `SHA256` , `InitiatingProcessSHA1` of `InitiatingProcessSHA256` ; functie gebruikt `SHA1` indien niet opgegeven.</span><span class="sxs-lookup"><span data-stu-id="90584-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="90584-162">**y**: Beperk het aantal records tot rijk, 1-1000; functie gebruikt 100 indien niet opgegeven</span><span class="sxs-lookup"><span data-stu-id="90584-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="90584-163">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="90584-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="90584-164">Project only the SHA1-kolom en verrijken</span><span class="sxs-lookup"><span data-stu-id="90584-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="90584-165">De eerste 500 records verrijken en bestanden met lage prevalentie verrijken</span><span class="sxs-lookup"><span data-stu-id="90584-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="90584-166">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="90584-166">Related topics</span></span>
- [<span data-ttu-id="90584-167">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="90584-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="90584-168">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="90584-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="90584-169">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="90584-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="90584-170">Voorbeelden van meer query</span><span class="sxs-lookup"><span data-stu-id="90584-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
