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
ms.openlocfilehash: a9ca0af0c522205309ffdcbfd1ac28638bd197c7
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382791"
---
# <a name="fileprofile"></a><span data-ttu-id="bbac7-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="bbac7-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bbac7-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bbac7-105">**Applies to:**</span></span>
- <span data-ttu-id="bbac7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbac7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bbac7-107">De `FileProfile()` functie is een verrijkingsfunctie in geavanceerde [zoekopdrachten](advanced-hunting-overview.md) die de volgende gegevens toevoegt aan bestanden die door de query worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="bbac7-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="bbac7-108">Kolom</span><span class="sxs-lookup"><span data-stu-id="bbac7-108">Column</span></span> | <span data-ttu-id="bbac7-109">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="bbac7-109">Data type</span></span> | <span data-ttu-id="bbac7-110">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="bbac7-110">Description</span></span> |
|------------|---------------|-------------|
| `SHA1` | <span data-ttu-id="bbac7-111">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bbac7-111">string</span></span> | <span data-ttu-id="bbac7-112">SHA-1 van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="bbac7-112">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="bbac7-113">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bbac7-113">string</span></span> | <span data-ttu-id="bbac7-114">SHA-256 van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="bbac7-114">SHA-256 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="bbac7-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bbac7-115">string</span></span> | <span data-ttu-id="bbac7-116">MD5-hash van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="bbac7-116">MD5 hash of the file that the recorded action was applied to</span></span> |
| `FileSize` | <span data-ttu-id="bbac7-117">int</span><span class="sxs-lookup"><span data-stu-id="bbac7-117">int</span></span> | <span data-ttu-id="bbac7-118">Grootte van het bestand in bytes</span><span class="sxs-lookup"><span data-stu-id="bbac7-118">Size of the file in bytes</span></span> |
| `GlobalPrevalence` | <span data-ttu-id="bbac7-119">int</span><span class="sxs-lookup"><span data-stu-id="bbac7-119">int</span></span> | <span data-ttu-id="bbac7-120">Aantal exemplaren van de entiteit die wereldwijd door Microsoft is waargenomen</span><span class="sxs-lookup"><span data-stu-id="bbac7-120">Number of instances of the entity observed by Microsoft globally</span></span> |
| `GlobalFirstSeen` | <span data-ttu-id="bbac7-121">datetime</span><span class="sxs-lookup"><span data-stu-id="bbac7-121">datetime</span></span> | <span data-ttu-id="bbac7-122">Datum en tijd waarop de entiteit voor het eerst wereldwijd door Microsoft is waargenomen</span><span class="sxs-lookup"><span data-stu-id="bbac7-122">Date and time when the entity was first observed by Microsoft globally</span></span> |
| `GlobalLastSeen` | <span data-ttu-id="bbac7-123">datetime</span><span class="sxs-lookup"><span data-stu-id="bbac7-123">datetime</span></span> | <span data-ttu-id="bbac7-124">Datum en tijd waarop de entiteit voor het laatst wereldwijd is waargenomen door Microsoft</span><span class="sxs-lookup"><span data-stu-id="bbac7-124">Date and time when the entity was last observed by Microsoft globally</span></span> |
| `Signer` | <span data-ttu-id="bbac7-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bbac7-125">string</span></span> | <span data-ttu-id="bbac7-126">Informatie over de ondertekenaar van het bestand</span><span class="sxs-lookup"><span data-stu-id="bbac7-126">Information about the signer of the file</span></span> |
| `Issuer` | <span data-ttu-id="bbac7-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bbac7-127">string</span></span> | <span data-ttu-id="bbac7-128">Informatie over de certificeringsinstantie voor afgifte (CA)</span><span class="sxs-lookup"><span data-stu-id="bbac7-128">Information about the issuing certificate authority (CA)</span></span> |
| `SignerHash` | <span data-ttu-id="bbac7-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bbac7-129">string</span></span> | <span data-ttu-id="bbac7-130">Unieke hashwaarde die de ondertekenaar identificeert</span><span class="sxs-lookup"><span data-stu-id="bbac7-130">Unique hash value identifying the signer</span></span> |
| `IsCertificateValid` | <span data-ttu-id="bbac7-131">booleaanse</span><span class="sxs-lookup"><span data-stu-id="bbac7-131">boolean</span></span> | <span data-ttu-id="bbac7-132">Of het certificaat dat wordt gebruikt om het bestand te ondertekenen geldig is</span><span class="sxs-lookup"><span data-stu-id="bbac7-132">Whether the certificate used to sign the file is valid</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="bbac7-133">booleaanse</span><span class="sxs-lookup"><span data-stu-id="bbac7-133">boolean</span></span> | <span data-ttu-id="bbac7-134">Geeft aan of de ondertekenaar van het hoofdcertificaat Microsoft is</span><span class="sxs-lookup"><span data-stu-id="bbac7-134">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `SignatureState` | <span data-ttu-id="bbac7-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bbac7-135">string</span></span> | <span data-ttu-id="bbac7-136">Status van de bestandshandtekening: SignedValid - het bestand is ondertekend met een geldige handtekening, SignedInvalid - het bestand is ondertekend, maar het certificaat is ongeldig, Niet ondertekend - het bestand is niet ondertekend, Onbekend - informatie over het bestand kan niet worden opgehaald</span><span class="sxs-lookup"><span data-stu-id="bbac7-136">State of the file signature: SignedValid - the file is signed with a valid signature, SignedInvalid - the file is signed but the certificate is invalid, Unsigned - the file is not signed, Unknown - information about the file cannot be retrieved</span></span>
| `IsExecutable` | <span data-ttu-id="bbac7-137">booleaanse</span><span class="sxs-lookup"><span data-stu-id="bbac7-137">boolean</span></span> | <span data-ttu-id="bbac7-138">Of het bestand een PE-bestand (Portable Executable) is</span><span class="sxs-lookup"><span data-stu-id="bbac7-138">Whether the file is a Portable Executable (PE) file</span></span> |
| `ThreatName` | <span data-ttu-id="bbac7-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bbac7-139">string</span></span> | <span data-ttu-id="bbac7-140">Detectienaam voor malware of andere gevonden bedreigingen</span><span class="sxs-lookup"><span data-stu-id="bbac7-140">Detection name for any malware or other threats found</span></span> |
| `Publisher` | <span data-ttu-id="bbac7-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bbac7-141">string</span></span> | <span data-ttu-id="bbac7-142">Naam van de organisatie die het bestand heeft gepubliceerd</span><span class="sxs-lookup"><span data-stu-id="bbac7-142">Name of the organization that published the file</span></span> |
| `SoftwareName` | <span data-ttu-id="bbac7-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bbac7-143">string</span></span> | <span data-ttu-id="bbac7-144">Naam van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="bbac7-144">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="bbac7-145">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="bbac7-145">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="bbac7-146">Argumenten</span><span class="sxs-lookup"><span data-stu-id="bbac7-146">Arguments</span></span>

- <span data-ttu-id="bbac7-147">**x**-kolom `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` bestands-id voor gebruik: , , of ; functie gebruikt indien niet gespecificeerd</span><span class="sxs-lookup"><span data-stu-id="bbac7-147">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="bbac7-148">**y**: limiet voor het aantal records dat moet worden verrijken, 1-1000; functie gebruikt 100 als niet-gespecificeerd</span><span class="sxs-lookup"><span data-stu-id="bbac7-148">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="bbac7-149">Verrijkingsfuncties bevatten alleen aanvullende informatie wanneer ze beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="bbac7-149">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="bbac7-150">De beschikbaarheid van informatie is gevarieerd en is afhankelijk van een groot aantal factoren.</span><span class="sxs-lookup"><span data-stu-id="bbac7-150">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="bbac7-151">Houd hier rekening mee bij het gebruik van FileProfile() in uw query's of bij het maken van aangepaste detecties.</span><span class="sxs-lookup"><span data-stu-id="bbac7-151">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="bbac7-152">Voor de beste resultaten wordt u aangeraden de functie FileProfile() te gebruiken met SHA1.</span><span class="sxs-lookup"><span data-stu-id="bbac7-152">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="bbac7-153">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="bbac7-153">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="bbac7-154">Project alleen de kolom SHA1 en verrijk deze</span><span class="sxs-lookup"><span data-stu-id="bbac7-154">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="bbac7-155">Verrijk de eerste 500 records en vermeld bestanden met lage prevalentie</span><span class="sxs-lookup"><span data-stu-id="bbac7-155">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="bbac7-156">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="bbac7-156">Related topics</span></span>
- [<span data-ttu-id="bbac7-157">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="bbac7-157">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bbac7-158">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="bbac7-158">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bbac7-159">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="bbac7-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bbac7-160">Meer queryvoorbeelden</span><span class="sxs-lookup"><span data-stu-id="bbac7-160">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
