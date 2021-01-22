---
title: FileProfile() in geavanceerd zoeken naar Microsoft 365 Defender
description: Informatie over het gebruik van FileProfile() voor het verbeteren van informatie over bestanden in uw geavanceerde queryresultaten
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929548"
---
# <a name="fileprofile"></a><span data-ttu-id="9ad5e-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="9ad5e-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9ad5e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9ad5e-105">**Applies to:**</span></span>
- <span data-ttu-id="9ad5e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ad5e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9ad5e-107">De `FileProfile()` functie is een verrijkingsfunctie in geavanceerde [zoekopdrachten](advanced-hunting-overview.md) die de volgende gegevens toevoegt aan bestanden die met de query worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="9ad5e-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="9ad5e-108">Kolom</span><span class="sxs-lookup"><span data-stu-id="9ad5e-108">Column</span></span> | <span data-ttu-id="9ad5e-109">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="9ad5e-109">Data type</span></span> | <span data-ttu-id="9ad5e-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="9ad5e-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="9ad5e-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="9ad5e-111">SHA1</span></span> | <span data-ttu-id="9ad5e-112">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9ad5e-112">string</span></span> | <span data-ttu-id="9ad5e-113">SHA-1 van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="9ad5e-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="9ad5e-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="9ad5e-114">SHA256</span></span> | <span data-ttu-id="9ad5e-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9ad5e-115">string</span></span> | <span data-ttu-id="9ad5e-116">SHA-256 van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="9ad5e-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="9ad5e-117">MD5</span><span class="sxs-lookup"><span data-stu-id="9ad5e-117">MD5</span></span> | <span data-ttu-id="9ad5e-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9ad5e-118">string</span></span> | <span data-ttu-id="9ad5e-119">MD5-hash van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="9ad5e-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="9ad5e-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="9ad5e-120">FileSize</span></span> | <span data-ttu-id="9ad5e-121">int</span><span class="sxs-lookup"><span data-stu-id="9ad5e-121">int</span></span> | <span data-ttu-id="9ad5e-122">Grootte van het bestand in bytes</span><span class="sxs-lookup"><span data-stu-id="9ad5e-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="9ad5e-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="9ad5e-123">GlobalPrevalence</span></span> | <span data-ttu-id="9ad5e-124">int</span><span class="sxs-lookup"><span data-stu-id="9ad5e-124">int</span></span> | <span data-ttu-id="9ad5e-125">Aantal instanties van de entiteit die wereldwijd door Microsoft wordt waargenomen</span><span class="sxs-lookup"><span data-stu-id="9ad5e-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="9ad5e-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="9ad5e-126">GlobalFirstSeen</span></span> | <span data-ttu-id="9ad5e-127">datetime</span><span class="sxs-lookup"><span data-stu-id="9ad5e-127">datetime</span></span> | <span data-ttu-id="9ad5e-128">Datum en tijd waarop de entiteit voor het eerst door Microsoft globaal is waargenomen</span><span class="sxs-lookup"><span data-stu-id="9ad5e-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="9ad5e-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="9ad5e-129">GlobalLastSeen</span></span> | <span data-ttu-id="9ad5e-130">datetime</span><span class="sxs-lookup"><span data-stu-id="9ad5e-130">datetime</span></span> | <span data-ttu-id="9ad5e-131">Datum en tijd waarop de entiteit voor het laatst door Microsoft wereldwijd is waargenomen</span><span class="sxs-lookup"><span data-stu-id="9ad5e-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="9ad5e-132">Ondertekenaar</span><span class="sxs-lookup"><span data-stu-id="9ad5e-132">Signer</span></span> | <span data-ttu-id="9ad5e-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9ad5e-133">string</span></span> | <span data-ttu-id="9ad5e-134">Informatie over de ondertekenaar van het bestand</span><span class="sxs-lookup"><span data-stu-id="9ad5e-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="9ad5e-135">Gever</span><span class="sxs-lookup"><span data-stu-id="9ad5e-135">Issuer</span></span> | <span data-ttu-id="9ad5e-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9ad5e-136">string</span></span> | <span data-ttu-id="9ad5e-137">Informatie over de certificeringsinstantie (CA)</span><span class="sxs-lookup"><span data-stu-id="9ad5e-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="9ad5e-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="9ad5e-138">SignerHash</span></span> | <span data-ttu-id="9ad5e-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9ad5e-139">string</span></span> | <span data-ttu-id="9ad5e-140">Unieke hashwaarde die de ondertekenaar identificeert</span><span class="sxs-lookup"><span data-stu-id="9ad5e-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="9ad5e-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="9ad5e-141">IsCertificateValid</span></span> | <span data-ttu-id="9ad5e-142">boolean</span><span class="sxs-lookup"><span data-stu-id="9ad5e-142">boolean</span></span> | <span data-ttu-id="9ad5e-143">Of het certificaat waarmee het bestand is ondertekenen, geldig is</span><span class="sxs-lookup"><span data-stu-id="9ad5e-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="9ad5e-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="9ad5e-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="9ad5e-145">boolean</span><span class="sxs-lookup"><span data-stu-id="9ad5e-145">boolean</span></span> | <span data-ttu-id="9ad5e-146">Hiermee wordt aangegeven of Microsoft de ondertekenaar van het basiscertificaat is</span><span class="sxs-lookup"><span data-stu-id="9ad5e-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="9ad5e-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="9ad5e-147">IsExecutable</span></span> | <span data-ttu-id="9ad5e-148">boolean</span><span class="sxs-lookup"><span data-stu-id="9ad5e-148">boolean</span></span> | <span data-ttu-id="9ad5e-149">Of het bestand een PE-bestand (Portable Executable) is</span><span class="sxs-lookup"><span data-stu-id="9ad5e-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="9ad5e-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="9ad5e-150">ThreatName</span></span> | <span data-ttu-id="9ad5e-151">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9ad5e-151">string</span></span> | <span data-ttu-id="9ad5e-152">Naam van detectie voor malware of andere bedreigingen gevonden</span><span class="sxs-lookup"><span data-stu-id="9ad5e-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="9ad5e-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="9ad5e-153">Publisher</span></span> | <span data-ttu-id="9ad5e-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9ad5e-154">string</span></span> | <span data-ttu-id="9ad5e-155">Naam van de organisatie die het bestand heeft gepubliceerd</span><span class="sxs-lookup"><span data-stu-id="9ad5e-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="9ad5e-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="9ad5e-156">SoftwareName</span></span> | <span data-ttu-id="9ad5e-157">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9ad5e-157">string</span></span> | <span data-ttu-id="9ad5e-158">Naam van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="9ad5e-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="9ad5e-159">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="9ad5e-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="9ad5e-160">Argumenten</span><span class="sxs-lookup"><span data-stu-id="9ad5e-160">Arguments</span></span>

- <span data-ttu-id="9ad5e-161">**x**—kolom bestands-id voor gebruik: , , of ; functie gebruikt `SHA1` `SHA256` indien niet `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` gespecificeerd</span><span class="sxs-lookup"><span data-stu-id="9ad5e-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="9ad5e-162">**y:** beperk het aantal records dat u wilt verrijken, 1-1000; de functie gebruikt 100 indien niet gespecificeerd</span><span class="sxs-lookup"><span data-stu-id="9ad5e-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="9ad5e-163">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="9ad5e-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="9ad5e-164">Alleen de kolom SHA1 projecten en deze verrijken</span><span class="sxs-lookup"><span data-stu-id="9ad5e-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="9ad5e-165">De eerste 500 records verrijken en bestanden met weinig bestanden in een lijst zetten</span><span class="sxs-lookup"><span data-stu-id="9ad5e-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="9ad5e-166">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="9ad5e-166">Related topics</span></span>
- [<span data-ttu-id="9ad5e-167">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="9ad5e-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9ad5e-168">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="9ad5e-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9ad5e-169">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="9ad5e-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9ad5e-170">Meer queryvoorbeelden bekijken</span><span class="sxs-lookup"><span data-stu-id="9ad5e-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
