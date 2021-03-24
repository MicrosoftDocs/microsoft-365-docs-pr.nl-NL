---
title: Tabel DeviceFileCertificateInfo in het geavanceerde schema voor de jacht
description: Meer informatie over bestands ondertekeningsgegevens in de tabel DeviceFileCertificateInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, digital signature, certificate, file signing, DeviceFileCertificateInfo
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
ms.openlocfilehash: 00e10c84c4bcb20f2e018bf05033b5b2235fd9ae
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058030"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="7a7c0-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="7a7c0-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7a7c0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7a7c0-105">**Applies to:**</span></span>
- <span data-ttu-id="7a7c0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7a7c0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7a7c0-107">De `DeviceFileCertificateInfo` tabel in het geavanceerde schema voor de [jacht](advanced-hunting-overview.md) bevat informatie over certificaat voor bestands ondertekening.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="7a7c0-108">In deze tabel worden gegevens gebruikt die zijn verkregen uit activiteiten voor certificaatverificatie die regelmatig worden uitgevoerd op bestanden op eindpunten.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="7a7c0-109">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="7a7c0-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7a7c0-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="7a7c0-110">Column name</span></span> | <span data-ttu-id="7a7c0-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="7a7c0-111">Data type</span></span> | <span data-ttu-id="7a7c0-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="7a7c0-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7a7c0-113">datetime</span><span class="sxs-lookup"><span data-stu-id="7a7c0-113">datetime</span></span> | <span data-ttu-id="7a7c0-114">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="7a7c0-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="7a7c0-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a7c0-115">string</span></span> | <span data-ttu-id="7a7c0-116">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="7a7c0-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="7a7c0-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a7c0-117">string</span></span> | <span data-ttu-id="7a7c0-118">Volledig gekwalificeerde domeinnaam (FQDN) van de computer</span><span class="sxs-lookup"><span data-stu-id="7a7c0-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="7a7c0-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a7c0-119">string</span></span> | <span data-ttu-id="7a7c0-120">SHA-1 van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="7a7c0-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="7a7c0-121">booleaanse</span><span class="sxs-lookup"><span data-stu-id="7a7c0-121">boolean</span></span> | <span data-ttu-id="7a7c0-122">Geeft aan of het bestand is ondertekend</span><span class="sxs-lookup"><span data-stu-id="7a7c0-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="7a7c0-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a7c0-123">string</span></span> | <span data-ttu-id="7a7c0-124">Geeft aan of handtekeninggegevens zijn gelezen als ingesloten inhoud in het bestand zelf of gelezen uit een extern catalogusbestand</span><span class="sxs-lookup"><span data-stu-id="7a7c0-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="7a7c0-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a7c0-125">string</span></span> | <span data-ttu-id="7a7c0-126">Informatie over de ondertekenaar van het bestand</span><span class="sxs-lookup"><span data-stu-id="7a7c0-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="7a7c0-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a7c0-127">string</span></span> | <span data-ttu-id="7a7c0-128">Unieke hashwaarde die de ondertekenaar identificeert</span><span class="sxs-lookup"><span data-stu-id="7a7c0-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="7a7c0-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a7c0-129">string</span></span> | <span data-ttu-id="7a7c0-130">Informatie over de certificeringsinstantie voor afgifte (CA)</span><span class="sxs-lookup"><span data-stu-id="7a7c0-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="7a7c0-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a7c0-131">string</span></span> | <span data-ttu-id="7a7c0-132">Unieke hashwaarde voor het identificeren van certificeringsinstantie (CA)</span><span class="sxs-lookup"><span data-stu-id="7a7c0-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="7a7c0-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a7c0-133">string</span></span> | <span data-ttu-id="7a7c0-134">Id voor het certificaat dat uniek is voor de certificeringsinstantie voor afgifte (CA)</span><span class="sxs-lookup"><span data-stu-id="7a7c0-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="7a7c0-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7a7c0-135">string</span></span> |  <span data-ttu-id="7a7c0-136">JSON-matrix met de URL's van netwerkaandelen die certificaten en certificaatteroeplijsten (CRL's) bevatten</span><span class="sxs-lookup"><span data-stu-id="7a7c0-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="7a7c0-137">datetime</span><span class="sxs-lookup"><span data-stu-id="7a7c0-137">datetime</span></span> | <span data-ttu-id="7a7c0-138">Datum en tijd waarop het certificaat is gemaakt</span><span class="sxs-lookup"><span data-stu-id="7a7c0-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="7a7c0-139">datetime</span><span class="sxs-lookup"><span data-stu-id="7a7c0-139">datetime</span></span> | <span data-ttu-id="7a7c0-140">Datum en tijd waarop het certificaat is ingesteld op verlopen</span><span class="sxs-lookup"><span data-stu-id="7a7c0-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="7a7c0-141">datetime</span><span class="sxs-lookup"><span data-stu-id="7a7c0-141">datetime</span></span> | <span data-ttu-id="7a7c0-142">Datum en tijd waarop het certificaat is ondertekend</span><span class="sxs-lookup"><span data-stu-id="7a7c0-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="7a7c0-143">booleaanse</span><span class="sxs-lookup"><span data-stu-id="7a7c0-143">boolean</span></span> | <span data-ttu-id="7a7c0-144">Geeft aan of het bestand wordt vertrouwd op basis van de resultaten van de functie WinVerifyTrust, die controleert op onbekende basiscertificaatgegevens, ongeldige handtekeningen, ingetrokken certificaten en andere twijfelachtige kenmerken</span><span class="sxs-lookup"><span data-stu-id="7a7c0-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="7a7c0-145">booleaanse</span><span class="sxs-lookup"><span data-stu-id="7a7c0-145">boolean</span></span> | <span data-ttu-id="7a7c0-146">Geeft aan of de ondertekenaar van het hoofdcertificaat Microsoft is</span><span class="sxs-lookup"><span data-stu-id="7a7c0-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="7a7c0-147">lang</span><span class="sxs-lookup"><span data-stu-id="7a7c0-147">long</span></span> | <span data-ttu-id="7a7c0-148">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="7a7c0-149">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="7a7c0-150">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7a7c0-150">Related topics</span></span>
- [<span data-ttu-id="7a7c0-151">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="7a7c0-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7a7c0-152">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="7a7c0-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7a7c0-153">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="7a7c0-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7a7c0-154">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="7a7c0-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7a7c0-155">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="7a7c0-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7a7c0-156">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="7a7c0-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
