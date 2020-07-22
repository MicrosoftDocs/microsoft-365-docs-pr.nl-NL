---
title: FileProfile() functie in geavanceerde jacht op Microsoft Threat Protection
description: Meer informatie over het gebruik van de FileProfile() om informatie over bestanden te verrijken in uw geavanceerde resultaten voor jachtquery's
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, FileProfile, bestandsprofiel, functie, verrijking
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 6465821ff1b8e8ea23cc5cf6b205f65a483bbe82
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204945"
---
# <a name="fileprofile"></a><span data-ttu-id="b34da-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="b34da-104">FileProfile()</span></span>

<span data-ttu-id="b34da-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b34da-105">**Applies to:**</span></span>
- <span data-ttu-id="b34da-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b34da-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b34da-107">De `FileProfile()` functie is een verrijkingsfunctie in geavanceerde [jacht](advanced-hunting-overview.md) die de volgende gegevens toevoegt aan bestanden die door de query worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="b34da-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="b34da-108">Kolom</span><span class="sxs-lookup"><span data-stu-id="b34da-108">Column</span></span> | <span data-ttu-id="b34da-109">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="b34da-109">Data type</span></span> | <span data-ttu-id="b34da-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b34da-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="b34da-111">SHA1 SHA1</span><span class="sxs-lookup"><span data-stu-id="b34da-111">SHA1</span></span> | <span data-ttu-id="b34da-112">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b34da-112">string</span></span> | <span data-ttu-id="b34da-113">SHA-1 van het bestand waarop de geregistreerde actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="b34da-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="b34da-114">SHA256 SHA256</span><span class="sxs-lookup"><span data-stu-id="b34da-114">SHA256</span></span> | <span data-ttu-id="b34da-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b34da-115">string</span></span> | <span data-ttu-id="b34da-116">SHA-256 van het bestand waarop de geregistreerde actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="b34da-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="b34da-117">MD5 MD5</span><span class="sxs-lookup"><span data-stu-id="b34da-117">MD5</span></span> | <span data-ttu-id="b34da-118">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b34da-118">string</span></span> | <span data-ttu-id="b34da-119">MD5-hash van het bestand waarop de geregistreerde actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="b34da-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="b34da-120">Bestandsgrootte</span><span class="sxs-lookup"><span data-stu-id="b34da-120">FileSize</span></span> | <span data-ttu-id="b34da-121">Int</span><span class="sxs-lookup"><span data-stu-id="b34da-121">int</span></span> | <span data-ttu-id="b34da-122">Grootte van het bestand in bytes</span><span class="sxs-lookup"><span data-stu-id="b34da-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="b34da-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="b34da-123">GlobalPrevalence</span></span> | <span data-ttu-id="b34da-124">Int</span><span class="sxs-lookup"><span data-stu-id="b34da-124">int</span></span> | <span data-ttu-id="b34da-125">Aantal exemplaren van de entiteit die wereldwijd door Microsoft wordt waargenomen</span><span class="sxs-lookup"><span data-stu-id="b34da-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="b34da-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="b34da-126">GlobalFirstSeen</span></span> | <span data-ttu-id="b34da-127">Datetime</span><span class="sxs-lookup"><span data-stu-id="b34da-127">datetime</span></span> | <span data-ttu-id="b34da-128">Datum en tijd waarop de entiteit wereldwijd voor het eerst werd waargenomen door Microsoft</span><span class="sxs-lookup"><span data-stu-id="b34da-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="b34da-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="b34da-129">GlobalLastSeen</span></span> | <span data-ttu-id="b34da-130">Datetime</span><span class="sxs-lookup"><span data-stu-id="b34da-130">datetime</span></span> | <span data-ttu-id="b34da-131">Datum en tijd waarop de entiteit wereldwijd voor het laatst door Microsoft is waargenomen</span><span class="sxs-lookup"><span data-stu-id="b34da-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="b34da-132">Ondertekenaar</span><span class="sxs-lookup"><span data-stu-id="b34da-132">Signer</span></span> | <span data-ttu-id="b34da-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b34da-133">string</span></span> | <span data-ttu-id="b34da-134">Informatie over de ondertekenaar van het bestand</span><span class="sxs-lookup"><span data-stu-id="b34da-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="b34da-135">Uitgevende instelling</span><span class="sxs-lookup"><span data-stu-id="b34da-135">Issuer</span></span> | <span data-ttu-id="b34da-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b34da-136">string</span></span> | <span data-ttu-id="b34da-137">Informatie over de instantie van afgiftecertificaat (CA)</span><span class="sxs-lookup"><span data-stu-id="b34da-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="b34da-138">OndertekenaarHash</span><span class="sxs-lookup"><span data-stu-id="b34da-138">SignerHash</span></span> | <span data-ttu-id="b34da-139">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b34da-139">string</span></span> | <span data-ttu-id="b34da-140">Unieke hashwaarde die de ondertekenaar identificeert</span><span class="sxs-lookup"><span data-stu-id="b34da-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="b34da-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="b34da-141">IsCertificateValid</span></span> | <span data-ttu-id="b34da-142">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="b34da-142">boolean</span></span> | <span data-ttu-id="b34da-143">Of het certificaat dat wordt gebruikt om het bestand te ondertekenen geldig is</span><span class="sxs-lookup"><span data-stu-id="b34da-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="b34da-144">IsRootSignerMicrosoft IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="b34da-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="b34da-145">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="b34da-145">boolean</span></span> | <span data-ttu-id="b34da-146">Geeft aan of de ondertekenaar van het basiscertificaat Microsoft is</span><span class="sxs-lookup"><span data-stu-id="b34da-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="b34da-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="b34da-147">IsExecutable</span></span> | <span data-ttu-id="b34da-148">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="b34da-148">boolean</span></span> | <span data-ttu-id="b34da-149">Of het bestand een PE-bestand (Portable Executable) is</span><span class="sxs-lookup"><span data-stu-id="b34da-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="b34da-150">ThreatName ThreatName</span><span class="sxs-lookup"><span data-stu-id="b34da-150">ThreatName</span></span> | <span data-ttu-id="b34da-151">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b34da-151">string</span></span> | <span data-ttu-id="b34da-152">Detectienaam voor malware of andere bedreigingen gevonden</span><span class="sxs-lookup"><span data-stu-id="b34da-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="b34da-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="b34da-153">Publisher</span></span> | <span data-ttu-id="b34da-154">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b34da-154">string</span></span> | <span data-ttu-id="b34da-155">Naam van de organisatie die het bestand heeft gepubliceerd</span><span class="sxs-lookup"><span data-stu-id="b34da-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="b34da-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="b34da-156">SoftwareName</span></span> | <span data-ttu-id="b34da-157">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b34da-157">string</span></span> | <span data-ttu-id="b34da-158">Naam van het softwareproduct</span><span class="sxs-lookup"><span data-stu-id="b34da-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="b34da-159">Syntaxis</span><span class="sxs-lookup"><span data-stu-id="b34da-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="b34da-160">Argumenten</span><span class="sxs-lookup"><span data-stu-id="b34da-160">Arguments</span></span>

- <span data-ttu-id="b34da-161">**x** — kolom bestands-id om te gebruiken: `SHA1` , , of , functie gebruikt als `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` niet-gespecificeerd</span><span class="sxs-lookup"><span data-stu-id="b34da-161">**x** — file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1` or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="b34da-162">**y** — beperking van het aantal records om te verrijken, 1-1000; functie gebruikt 100 als niet-gespecificeerd</span><span class="sxs-lookup"><span data-stu-id="b34da-162">**y** — limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="b34da-163">Voorbeelden</span><span class="sxs-lookup"><span data-stu-id="b34da-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="b34da-164">Projecteer alleen de SHA1-kolom en verrijk deze</span><span class="sxs-lookup"><span data-stu-id="b34da-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="b34da-165">De eerste 500 records verrijken en lage prevalentiebestanden aanbieden</span><span class="sxs-lookup"><span data-stu-id="b34da-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="b34da-166">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b34da-166">Related topics</span></span>
- [<span data-ttu-id="b34da-167">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b34da-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b34da-168">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="b34da-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b34da-169">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="b34da-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)