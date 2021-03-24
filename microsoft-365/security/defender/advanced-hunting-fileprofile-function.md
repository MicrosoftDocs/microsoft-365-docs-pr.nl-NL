---
title: FileProfile() functie in advanced hunting for Microsoft 365 Defender
description: Meer informatie over het gebruik van FileProfile() om informatie over bestanden in de geavanceerde resultaten van de query te verrijken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e511c12240512af772b3552f63ad9ed98ff105af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057302"
---
# <a name="fileprofile"></a><span data-ttu-id="2aeee-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="2aeee-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2aeee-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2aeee-105">**Applies to:**</span></span>
- <span data-ttu-id="2aeee-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2aeee-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2aeee-107">De `FileProfile()` functie is een verrijkingsfunctie in geavanceerde [zoekopdrachten](advanced-hunting-overview.md) die de volgende gegevens toevoegt aan bestanden die door de query worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="2aeee-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="2aeee-108">Kolom</span><span class="sxs-lookup"><span data-stu-id="2aeee-108">Column</span></span> | <span data-ttu-id="2aeee-109">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="2aeee-109">Data type</span></span> | <span data-ttu-id="2aeee-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2aeee-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="2aeee-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="2aeee-111">SHA1</span></span> | <span data-ttu-id="2aeee-112">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2aeee-112">string</span></span> | <span data-ttu-id="2aeee-113">SHA-1 van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="2aeee-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="2aeee-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="2aeee-114">SHA256</span></span> | <span data-ttu-id="2aeee-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2aeee-115">string</span></span> | <span data-ttu-id="2aeee-116">SHA-256 van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="2aeee-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="2aeee-117">MD5</span><span class="sxs-lookup"><span data-stu-id="2aeee-117">MD5</span></span> | <span data-ttu-id="2aeee-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2aeee-118">string</span></span> | <span data-ttu-id="2aeee-119">MD5-hash van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="2aeee-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="2aeee-120">Bestandsgrootte</span><span class="sxs-lookup"><span data-stu-id="2aeee-120">FileSize</span></span> | <span data-ttu-id="2aeee-121">int</span><span class="sxs-lookup"><span data-stu-id="2aeee-121">int</span></span> | <span data-ttu-id="2aeee-122">Grootte van het bestand in bytes</span><span class="sxs-lookup"><span data-stu-id="2aeee-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="2aeee-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="2aeee-123">GlobalPrevalence</span></span> | <span data-ttu-id="2aeee-124">int</span><span class="sxs-lookup"><span data-stu-id="2aeee-124">int</span></span> | <span data-ttu-id="2aeee-125">Aantal exemplaren van de entiteit die wereldwijd door Microsoft is waargenomen</span><span class="sxs-lookup"><span data-stu-id="2aeee-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="2aeee-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="2aeee-126">GlobalFirstSeen</span></span> | <span data-ttu-id="2aeee-127">datetime</span><span class="sxs-lookup"><span data-stu-id="2aeee-127">datetime</span></span> | <span data-ttu-id="2aeee-128">Datum en tijd waarop de entiteit voor het eerst wereldwijd door Microsoft is waargenomen</span><span class="sxs-lookup"><span data-stu-id="2aeee-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="2aeee-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="2aeee-129">GlobalLastSeen</span></span> | <span data-ttu-id="2aeee-130">datetime</span><span class="sxs-lookup"><span data-stu-id="2aeee-130">datetime</span></span> | <span data-ttu-id="2aeee-131">Datum en tijd waarop de entiteit voor het laatst wereldwijd is waargenomen door Microsoft</span><span class="sxs-lookup"><span data-stu-id="2aeee-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="2aeee-132">Ondertekenaar</span><span class="sxs-lookup"><span data-stu-id="2aeee-132">Signer</span></span> | <span data-ttu-id="2aeee-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2aeee-133">string</span></span> | <span data-ttu-id="2aeee-134">Informatie over de ondertekenaar van het bestand</span><span class="sxs-lookup"><span data-stu-id="2aeee-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="2aeee-135">Uitgevende gever</span><span class="sxs-lookup"><span data-stu-id="2aeee-135">Issuer</span></span> | <span data-ttu-id="2aeee-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2aeee-136">string</span></span> | <span data-ttu-id="2aeee-137">Informatie over de certificeringsinstantie voor afgifte (CA)</span><span class="sxs-lookup"><span data-stu-id="2aeee-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="2aeee-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="2aeee-138">SignerHash</span></span> | <span data-ttu-id="2aeee-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2aeee-139">string</span></span> | <span data-ttu-id="2aeee-140">Unieke hashwaarde die de ondertekenaar identificeert</span><span class="sxs-lookup"><span data-stu-id="2aeee-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="2aeee-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="2aeee-141">IsCertificateValid</span></span> | <span data-ttu-id="2aeee-142">booleaanse</span><span class="sxs-lookup"><span data-stu-id="2aeee-142">boolean</span></span> | <span data-ttu-id="2aeee-143">Of het certificaat dat wordt gebruikt om het bestand te ondertekenen geldig is</span><span class="sxs-lookup"><span data-stu-id="2aeee-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="2aeee-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="2aeee-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="2aeee-145">booleaanse</span><span class="sxs-lookup"><span data-stu-id="2aeee-145">boolean</span></span> | <span data-ttu-id="2aeee-146">Geeft aan of de ondertekenaar van het hoofdcertificaat Microsoft is</span><span class="sxs-lookup"><span data-stu-id="2aeee-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="2aeee-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="2aeee-147">IsExecutable</span></span> | <span data-ttu-id="2aeee-148">booleaanse</span><span class="sxs-lookup"><span data-stu-id="2aeee-148">boolean</span></span> | <span data-ttu-id="2aeee-149">Of het bestand een PE-bestand (Portable Executable) is</span><span class="sxs-lookup"><span data-stu-id="2aeee-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="2aeee-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="2aeee-150">ThreatName</span></span> | <span data-ttu-id="2aeee-151">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2aeee-151">string</span></span> | <span data-ttu-id="2aeee-152">Detectienaam voor malware of andere gevonden bedreigingen</span><span class="sxs-lookup"><span data-stu-id="2aeee-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="2aeee-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="2aeee-153">Publisher</span></span> | <span data-ttu-id="2aeee-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2aeee-154">string</span></span> | <span data-ttu-id="2aeee-155">Naam van de organisatie die het bestand heeft gepubliceerd</span><span class="sxs-lookup"><span data-stu-id="2aeee-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="2aeee-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="2aeee-156">SoftwareName</span></span> | <span data-ttu-id="2aeee-157">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2aeee-157">string</span></span> | <span data-ttu-id="2aeee-158">Naam van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="2aeee-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="2aeee-159">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="2aeee-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="2aeee-160">Argumenten</span><span class="sxs-lookup"><span data-stu-id="2aeee-160">Arguments</span></span>

- <span data-ttu-id="2aeee-161">**x**-kolom `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` bestands-id voor gebruik: , , of ; functie gebruikt indien niet gespecificeerd</span><span class="sxs-lookup"><span data-stu-id="2aeee-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="2aeee-162">**y**: limiet voor het aantal records dat moet worden verrijken, 1-1000; functie gebruikt 100 als niet-gespecificeerd</span><span class="sxs-lookup"><span data-stu-id="2aeee-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="2aeee-163">Verrijkingsfuncties bevatten alleen aanvullende informatie wanneer ze beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="2aeee-163">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="2aeee-164">De beschikbaarheid van informatie is gevarieerd en is afhankelijk van een groot aantal factoren.</span><span class="sxs-lookup"><span data-stu-id="2aeee-164">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="2aeee-165">Houd hier rekening mee bij het gebruik van FileProfile() in uw query's of bij het maken van aangepaste detecties.</span><span class="sxs-lookup"><span data-stu-id="2aeee-165">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="2aeee-166">Voor de beste resultaten wordt u aangeraden de functie FileProfile() te gebruiken met SHA1.</span><span class="sxs-lookup"><span data-stu-id="2aeee-166">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="2aeee-167">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="2aeee-167">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="2aeee-168">Project alleen de kolom SHA1 en verrijk deze</span><span class="sxs-lookup"><span data-stu-id="2aeee-168">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="2aeee-169">Verrijk de eerste 500 records en vermeld bestanden met lage prevalentie</span><span class="sxs-lookup"><span data-stu-id="2aeee-169">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="2aeee-170">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2aeee-170">Related topics</span></span>
- [<span data-ttu-id="2aeee-171">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="2aeee-171">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2aeee-172">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="2aeee-172">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2aeee-173">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="2aeee-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2aeee-174">Meer queryvoorbeelden</span><span class="sxs-lookup"><span data-stu-id="2aeee-174">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
