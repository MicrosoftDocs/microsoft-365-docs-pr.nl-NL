---
title: FileProfile (), functie in geavanceerde jacht voor Microsoft 365 Defender
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 31959ed146df52aa6568f7aa60617b74ab8dd4db
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847450"
---
# <a name="fileprofile"></a><span data-ttu-id="48e87-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="48e87-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="48e87-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="48e87-105">**Applies to:**</span></span>
- <span data-ttu-id="48e87-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48e87-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="48e87-107">De `FileProfile()` functie is een verrijkings functie in de [geavanceerde jacht](advanced-hunting-overview.md) waarmee de volgende gegevens worden toegevoegd aan bestanden die door de query zijn gevonden.</span><span class="sxs-lookup"><span data-stu-id="48e87-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="48e87-108">Kolom</span><span class="sxs-lookup"><span data-stu-id="48e87-108">Column</span></span> | <span data-ttu-id="48e87-109">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="48e87-109">Data type</span></span> | <span data-ttu-id="48e87-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="48e87-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="48e87-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="48e87-111">SHA1</span></span> | <span data-ttu-id="48e87-112">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48e87-112">string</span></span> | <span data-ttu-id="48e87-113">SHA-1 van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="48e87-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="48e87-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="48e87-114">SHA256</span></span> | <span data-ttu-id="48e87-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48e87-115">string</span></span> | <span data-ttu-id="48e87-116">SHA-256 van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="48e87-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="48e87-117">MD5 ()</span><span class="sxs-lookup"><span data-stu-id="48e87-117">MD5</span></span> | <span data-ttu-id="48e87-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48e87-118">string</span></span> | <span data-ttu-id="48e87-119">MD5-hash van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="48e87-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="48e87-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="48e87-120">FileSize</span></span> | <span data-ttu-id="48e87-121">int</span><span class="sxs-lookup"><span data-stu-id="48e87-121">int</span></span> | <span data-ttu-id="48e87-122">Bestandsgrootte in bytes</span><span class="sxs-lookup"><span data-stu-id="48e87-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="48e87-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="48e87-123">GlobalPrevalence</span></span> | <span data-ttu-id="48e87-124">int</span><span class="sxs-lookup"><span data-stu-id="48e87-124">int</span></span> | <span data-ttu-id="48e87-125">Aantal exemplaren van de entiteit die is waargenomen door Microsoft Global</span><span class="sxs-lookup"><span data-stu-id="48e87-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="48e87-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="48e87-126">GlobalFirstSeen</span></span> | <span data-ttu-id="48e87-127">tijd</span><span class="sxs-lookup"><span data-stu-id="48e87-127">datetime</span></span> | <span data-ttu-id="48e87-128">De datum en tijd waarop de entiteit voor het eerst werd gevolgd door Microsoft Global</span><span class="sxs-lookup"><span data-stu-id="48e87-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="48e87-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="48e87-129">GlobalLastSeen</span></span> | <span data-ttu-id="48e87-130">tijd</span><span class="sxs-lookup"><span data-stu-id="48e87-130">datetime</span></span> | <span data-ttu-id="48e87-131">De datum en tijd waarop de entiteit voor het laatst is geobserveerd door Microsoft Global</span><span class="sxs-lookup"><span data-stu-id="48e87-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="48e87-132">Ondertekenaar</span><span class="sxs-lookup"><span data-stu-id="48e87-132">Signer</span></span> | <span data-ttu-id="48e87-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48e87-133">string</span></span> | <span data-ttu-id="48e87-134">Informatie over de ondertekenaar van het bestand</span><span class="sxs-lookup"><span data-stu-id="48e87-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="48e87-135">Verstrekker</span><span class="sxs-lookup"><span data-stu-id="48e87-135">Issuer</span></span> | <span data-ttu-id="48e87-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48e87-136">string</span></span> | <span data-ttu-id="48e87-137">Informatie over de uitgevende certificeringsinstantie (CA)</span><span class="sxs-lookup"><span data-stu-id="48e87-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="48e87-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="48e87-138">SignerHash</span></span> | <span data-ttu-id="48e87-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48e87-139">string</span></span> | <span data-ttu-id="48e87-140">Unieke hash-waarde die de ondertekenaar identificeert</span><span class="sxs-lookup"><span data-stu-id="48e87-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="48e87-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="48e87-141">IsCertificateValid</span></span> | <span data-ttu-id="48e87-142">Boolean</span><span class="sxs-lookup"><span data-stu-id="48e87-142">boolean</span></span> | <span data-ttu-id="48e87-143">Opgeven of het certificaat dat wordt gebruikt om het bestand te ondertekenen geldig is</span><span class="sxs-lookup"><span data-stu-id="48e87-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="48e87-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="48e87-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="48e87-145">Boolean</span><span class="sxs-lookup"><span data-stu-id="48e87-145">boolean</span></span> | <span data-ttu-id="48e87-146">Geeft aan of de ondertekenaar van het basiscertificaat Microsoft is</span><span class="sxs-lookup"><span data-stu-id="48e87-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="48e87-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="48e87-147">IsExecutable</span></span> | <span data-ttu-id="48e87-148">Boolean</span><span class="sxs-lookup"><span data-stu-id="48e87-148">boolean</span></span> | <span data-ttu-id="48e87-149">Opgeven of het bestand een bestand is van een Portable Executable (PE)</span><span class="sxs-lookup"><span data-stu-id="48e87-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="48e87-150">Bedreiging</span><span class="sxs-lookup"><span data-stu-id="48e87-150">ThreatName</span></span> | <span data-ttu-id="48e87-151">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48e87-151">string</span></span> | <span data-ttu-id="48e87-152">Detectie naam voor malware of andere bedreigingen gevonden</span><span class="sxs-lookup"><span data-stu-id="48e87-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="48e87-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="48e87-153">Publisher</span></span> | <span data-ttu-id="48e87-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48e87-154">string</span></span> | <span data-ttu-id="48e87-155">Naam van de organisatie die het bestand heeft gepubliceerd</span><span class="sxs-lookup"><span data-stu-id="48e87-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="48e87-156">Softwarenaam</span><span class="sxs-lookup"><span data-stu-id="48e87-156">SoftwareName</span></span> | <span data-ttu-id="48e87-157">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="48e87-157">string</span></span> | <span data-ttu-id="48e87-158">Naam van het SOFTWAREPRODUCT</span><span class="sxs-lookup"><span data-stu-id="48e87-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="48e87-159">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="48e87-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="48e87-160">Argumenten</span><span class="sxs-lookup"><span data-stu-id="48e87-160">Arguments</span></span>

- <span data-ttu-id="48e87-161">**x** — kolom met bestands-id die moet worden gebruikt: `SHA1` , `SHA256` , `InitiatingProcessSHA1` of `InitiatingProcessSHA256` ; functie gebruikt `SHA1` indien niet opgegeven.</span><span class="sxs-lookup"><span data-stu-id="48e87-161">**x** —file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="48e87-162">**y** : Beperk het aantal records tot rijk, 1-1000; functie gebruikt 100 indien niet opgegeven</span><span class="sxs-lookup"><span data-stu-id="48e87-162">**y** —limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="48e87-163">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="48e87-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="48e87-164">Project only the SHA1-kolom en verrijken</span><span class="sxs-lookup"><span data-stu-id="48e87-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="48e87-165">De eerste 500 records verrijken en bestanden met lage prevalentie verrijken</span><span class="sxs-lookup"><span data-stu-id="48e87-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="48e87-166">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="48e87-166">Related topics</span></span>
- [<span data-ttu-id="48e87-167">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="48e87-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="48e87-168">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="48e87-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="48e87-169">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="48e87-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="48e87-170">Voorbeelden van meer query</span><span class="sxs-lookup"><span data-stu-id="48e87-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
