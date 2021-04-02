---
title: FileProfile() functie in advanced hunting for Microsoft Defender for Endpoint
description: Meer informatie over het gebruik van FileProfile() om informatie over bestanden in de geavanceerde resultaten van de query te verrijken
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, Microsoft Defender ATP, Microsoft Defender for Endpoint, Windows Defender, Windows Defender ATP, Windows Defender Advanced Threat Protection, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
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
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 6c828418d27db24cbd6e87f040486b3abc45e6c6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499558"
---
# <a name="fileprofile"></a><span data-ttu-id="f9dd9-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="f9dd9-104">FileProfile()</span></span>

<span data-ttu-id="f9dd9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f9dd9-105">**Applies to:**</span></span>
- [<span data-ttu-id="f9dd9-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f9dd9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

<span data-ttu-id="f9dd9-107">De `FileProfile()` functie is een verrijkingsfunctie in geavanceerde [zoekopdrachten](advanced-hunting-overview.md) die de volgende gegevens toevoegt aan bestanden die door de query worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="f9dd9-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

<span data-ttu-id="f9dd9-108">Kolom</span><span class="sxs-lookup"><span data-stu-id="f9dd9-108">Column</span></span> | <span data-ttu-id="f9dd9-109">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="f9dd9-109">Data type</span></span> | <span data-ttu-id="f9dd9-110">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="f9dd9-110">Description</span></span>
-|-|-
<span data-ttu-id="f9dd9-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="f9dd9-111">SHA1</span></span> | <span data-ttu-id="f9dd9-112">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9dd9-112">string</span></span> | <span data-ttu-id="f9dd9-113">SHA-1 van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="f9dd9-113">SHA-1 of the file that the recorded action was applied to</span></span>
<span data-ttu-id="f9dd9-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="f9dd9-114">SHA256</span></span> | <span data-ttu-id="f9dd9-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9dd9-115">string</span></span> | <span data-ttu-id="f9dd9-116">SHA-256 van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="f9dd9-116">SHA-256 of the file that the recorded action was applied to</span></span>
<span data-ttu-id="f9dd9-117">MD5</span><span class="sxs-lookup"><span data-stu-id="f9dd9-117">MD5</span></span> | <span data-ttu-id="f9dd9-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9dd9-118">string</span></span> | <span data-ttu-id="f9dd9-119">MD5-hash van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="f9dd9-119">MD5 hash of the file that the recorded action was applied to</span></span>
<span data-ttu-id="f9dd9-120">Bestandsgrootte</span><span class="sxs-lookup"><span data-stu-id="f9dd9-120">FileSize</span></span> | <span data-ttu-id="f9dd9-121">int</span><span class="sxs-lookup"><span data-stu-id="f9dd9-121">int</span></span> | <span data-ttu-id="f9dd9-122">Grootte van het bestand in bytes</span><span class="sxs-lookup"><span data-stu-id="f9dd9-122">Size of the file in bytes</span></span>
<span data-ttu-id="f9dd9-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="f9dd9-123">GlobalPrevalence</span></span> | <span data-ttu-id="f9dd9-124">int</span><span class="sxs-lookup"><span data-stu-id="f9dd9-124">int</span></span> | <span data-ttu-id="f9dd9-125">Aantal exemplaren van de entiteit die wereldwijd door Microsoft is waargenomen</span><span class="sxs-lookup"><span data-stu-id="f9dd9-125">Number of instances of the entity observed by Microsoft globally</span></span>
<span data-ttu-id="f9dd9-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="f9dd9-126">GlobalFirstSeen</span></span> | <span data-ttu-id="f9dd9-127">datetime</span><span class="sxs-lookup"><span data-stu-id="f9dd9-127">datetime</span></span> | <span data-ttu-id="f9dd9-128">Datum en tijd waarop de entiteit voor het eerst wereldwijd door Microsoft is waargenomen</span><span class="sxs-lookup"><span data-stu-id="f9dd9-128">Date and time when the entity was first observed by Microsoft globally</span></span>
<span data-ttu-id="f9dd9-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="f9dd9-129">GlobalLastSeen</span></span> | <span data-ttu-id="f9dd9-130">datetime</span><span class="sxs-lookup"><span data-stu-id="f9dd9-130">datetime</span></span> | <span data-ttu-id="f9dd9-131">Datum en tijd waarop de entiteit voor het laatst wereldwijd is waargenomen door Microsoft</span><span class="sxs-lookup"><span data-stu-id="f9dd9-131">Date and time when the entity was last observed by Microsoft globally</span></span>
<span data-ttu-id="f9dd9-132">Ondertekenaar</span><span class="sxs-lookup"><span data-stu-id="f9dd9-132">Signer</span></span> | <span data-ttu-id="f9dd9-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9dd9-133">string</span></span> | <span data-ttu-id="f9dd9-134">Informatie over de ondertekenaar van het bestand</span><span class="sxs-lookup"><span data-stu-id="f9dd9-134">Information about the signer of the file</span></span>
<span data-ttu-id="f9dd9-135">Uitgevende gever</span><span class="sxs-lookup"><span data-stu-id="f9dd9-135">Issuer</span></span> | <span data-ttu-id="f9dd9-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9dd9-136">string</span></span> | <span data-ttu-id="f9dd9-137">Informatie over de certificeringsinstantie voor afgifte (CA)</span><span class="sxs-lookup"><span data-stu-id="f9dd9-137">Information about the issuing certificate authority (CA)</span></span>
<span data-ttu-id="f9dd9-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="f9dd9-138">SignerHash</span></span> | <span data-ttu-id="f9dd9-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9dd9-139">string</span></span> | <span data-ttu-id="f9dd9-140">Unieke hashwaarde die de ondertekenaar identificeert</span><span class="sxs-lookup"><span data-stu-id="f9dd9-140">Unique hash value identifying the signer</span></span>
<span data-ttu-id="f9dd9-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="f9dd9-141">IsCertificateValid</span></span> | <span data-ttu-id="f9dd9-142">booleaanse</span><span class="sxs-lookup"><span data-stu-id="f9dd9-142">boolean</span></span> | <span data-ttu-id="f9dd9-143">Of het certificaat dat wordt gebruikt om het bestand te ondertekenen geldig is</span><span class="sxs-lookup"><span data-stu-id="f9dd9-143">Whether the certificate used to sign the file is valid</span></span>
<span data-ttu-id="f9dd9-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="f9dd9-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="f9dd9-145">booleaanse</span><span class="sxs-lookup"><span data-stu-id="f9dd9-145">boolean</span></span> | <span data-ttu-id="f9dd9-146">Geeft aan of de ondertekenaar van het hoofdcertificaat Microsoft is</span><span class="sxs-lookup"><span data-stu-id="f9dd9-146">Indicates whether the signer of the root certificate is Microsoft</span></span>
<span data-ttu-id="f9dd9-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="f9dd9-147">IsExecutable</span></span> | <span data-ttu-id="f9dd9-148">booleaanse</span><span class="sxs-lookup"><span data-stu-id="f9dd9-148">boolean</span></span> | <span data-ttu-id="f9dd9-149">Of het bestand een PE-bestand (Portable Executable) is</span><span class="sxs-lookup"><span data-stu-id="f9dd9-149">Whether the file is a Portable Executable (PE) file</span></span>
<span data-ttu-id="f9dd9-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="f9dd9-150">ThreatName</span></span> | <span data-ttu-id="f9dd9-151">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9dd9-151">string</span></span> | <span data-ttu-id="f9dd9-152">Detectienaam voor malware of andere gevonden bedreigingen</span><span class="sxs-lookup"><span data-stu-id="f9dd9-152">Detection name for any malware or other threats found</span></span>
<span data-ttu-id="f9dd9-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="f9dd9-153">Publisher</span></span> | <span data-ttu-id="f9dd9-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9dd9-154">string</span></span> | <span data-ttu-id="f9dd9-155">Naam van de organisatie die het bestand heeft gepubliceerd</span><span class="sxs-lookup"><span data-stu-id="f9dd9-155">Name of the organization that published the file</span></span>
<span data-ttu-id="f9dd9-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="f9dd9-156">SoftwareName</span></span> | <span data-ttu-id="f9dd9-157">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9dd9-157">string</span></span> | <span data-ttu-id="f9dd9-158">Naam van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="f9dd9-158">Name of the software product</span></span>

## <a name="syntax"></a><span data-ttu-id="f9dd9-159">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="f9dd9-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="f9dd9-160">Argumenten</span><span class="sxs-lookup"><span data-stu-id="f9dd9-160">Arguments</span></span>

- <span data-ttu-id="f9dd9-161">**x** : kolom `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` bestands-id die u wilt gebruiken: , of ; functie gebruikt indien niet gespecificeerd</span><span class="sxs-lookup"><span data-stu-id="f9dd9-161">**x** — file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1` or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="f9dd9-162">**y:** limiet voor het aantal records dat moet worden verrijken, 1-1000; functie gebruikt 100 als niet-gespecificeerd</span><span class="sxs-lookup"><span data-stu-id="f9dd9-162">**y** — limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="f9dd9-163">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="f9dd9-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="f9dd9-164">Project alleen de kolom SHA1 en verrijk deze</span><span class="sxs-lookup"><span data-stu-id="f9dd9-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="f9dd9-165">Verrijk de eerste 500 records en vermeld bestanden met lage prevalentie</span><span class="sxs-lookup"><span data-stu-id="f9dd9-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="f9dd9-166">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f9dd9-166">Related topics</span></span>

- [<span data-ttu-id="f9dd9-167">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="f9dd9-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f9dd9-168">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="f9dd9-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f9dd9-169">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="f9dd9-169">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
