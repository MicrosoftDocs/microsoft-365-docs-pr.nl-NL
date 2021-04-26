---
title: Tabel DeviceFileCertificateInfo in het geavanceerde schema voor de jacht
description: Meer informatie over bestands ondertekeningsgegevens in de tabel DeviceFileCertificateInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, digital signature, certificate, file signing, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1f894f3fc8cff2113004ff9c9e34ec2ca0144799
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023211"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="a6fe6-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="a6fe6-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a6fe6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a6fe6-105">**Applies to:**</span></span>
- <span data-ttu-id="a6fe6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6fe6-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="a6fe6-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a6fe6-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="a6fe6-108">De `DeviceFileCertificateInfo` tabel in het geavanceerde schema voor de [jacht](advanced-hunting-overview.md) bevat informatie over certificaat voor bestands ondertekening.</span><span class="sxs-lookup"><span data-stu-id="a6fe6-108">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="a6fe6-109">In deze tabel worden gegevens gebruikt die zijn verkregen uit activiteiten voor certificaatverificatie die regelmatig worden uitgevoerd op bestanden op eindpunten.</span><span class="sxs-lookup"><span data-stu-id="a6fe6-109">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="a6fe6-110">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="a6fe6-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a6fe6-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="a6fe6-111">Column name</span></span> | <span data-ttu-id="a6fe6-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="a6fe6-112">Data type</span></span> | <span data-ttu-id="a6fe6-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="a6fe6-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a6fe6-114">datetime</span><span class="sxs-lookup"><span data-stu-id="a6fe6-114">datetime</span></span> | <span data-ttu-id="a6fe6-115">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="a6fe6-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="a6fe6-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a6fe6-116">string</span></span> | <span data-ttu-id="a6fe6-117">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="a6fe6-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a6fe6-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a6fe6-118">string</span></span> | <span data-ttu-id="a6fe6-119">Volledig gekwalificeerde domeinnaam (FQDN) van de computer</span><span class="sxs-lookup"><span data-stu-id="a6fe6-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="a6fe6-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a6fe6-120">string</span></span> | <span data-ttu-id="a6fe6-121">SHA-1 van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="a6fe6-121">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="a6fe6-122">booleaanse</span><span class="sxs-lookup"><span data-stu-id="a6fe6-122">boolean</span></span> | <span data-ttu-id="a6fe6-123">Geeft aan of het bestand is ondertekend</span><span class="sxs-lookup"><span data-stu-id="a6fe6-123">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="a6fe6-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a6fe6-124">string</span></span> | <span data-ttu-id="a6fe6-125">Geeft aan of handtekeninggegevens zijn gelezen als ingesloten inhoud in het bestand zelf of gelezen uit een extern catalogusbestand</span><span class="sxs-lookup"><span data-stu-id="a6fe6-125">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="a6fe6-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a6fe6-126">string</span></span> | <span data-ttu-id="a6fe6-127">Informatie over de ondertekenaar van het bestand</span><span class="sxs-lookup"><span data-stu-id="a6fe6-127">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="a6fe6-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a6fe6-128">string</span></span> | <span data-ttu-id="a6fe6-129">Unieke hashwaarde die de ondertekenaar identificeert</span><span class="sxs-lookup"><span data-stu-id="a6fe6-129">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="a6fe6-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a6fe6-130">string</span></span> | <span data-ttu-id="a6fe6-131">Informatie over de certificeringsinstantie voor afgifte (CA)</span><span class="sxs-lookup"><span data-stu-id="a6fe6-131">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="a6fe6-132">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a6fe6-132">string</span></span> | <span data-ttu-id="a6fe6-133">Unieke hashwaarde voor het identificeren van certificeringsinstantie (CA)</span><span class="sxs-lookup"><span data-stu-id="a6fe6-133">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="a6fe6-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a6fe6-134">string</span></span> | <span data-ttu-id="a6fe6-135">Id voor het certificaat dat uniek is voor de certificeringsinstantie voor afgifte (CA)</span><span class="sxs-lookup"><span data-stu-id="a6fe6-135">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="a6fe6-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="a6fe6-136">string</span></span> |  <span data-ttu-id="a6fe6-137">JSON-matrix met de URL's van netwerkaandelen die certificaten en certificaatteroeplijsten (CRL's) bevatten</span><span class="sxs-lookup"><span data-stu-id="a6fe6-137">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="a6fe6-138">datetime</span><span class="sxs-lookup"><span data-stu-id="a6fe6-138">datetime</span></span> | <span data-ttu-id="a6fe6-139">Datum en tijd waarop het certificaat is gemaakt</span><span class="sxs-lookup"><span data-stu-id="a6fe6-139">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="a6fe6-140">datetime</span><span class="sxs-lookup"><span data-stu-id="a6fe6-140">datetime</span></span> | <span data-ttu-id="a6fe6-141">Datum en tijd waarop het certificaat is ingesteld op verlopen</span><span class="sxs-lookup"><span data-stu-id="a6fe6-141">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="a6fe6-142">datetime</span><span class="sxs-lookup"><span data-stu-id="a6fe6-142">datetime</span></span> | <span data-ttu-id="a6fe6-143">Datum en tijd waarop het certificaat is ondertekend</span><span class="sxs-lookup"><span data-stu-id="a6fe6-143">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="a6fe6-144">booleaanse</span><span class="sxs-lookup"><span data-stu-id="a6fe6-144">boolean</span></span> | <span data-ttu-id="a6fe6-145">Geeft aan of het bestand wordt vertrouwd op basis van de resultaten van de functie WinVerifyTrust, die controleert op onbekende basiscertificaatgegevens, ongeldige handtekeningen, ingetrokken certificaten en andere twijfelachtige kenmerken</span><span class="sxs-lookup"><span data-stu-id="a6fe6-145">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="a6fe6-146">booleaanse</span><span class="sxs-lookup"><span data-stu-id="a6fe6-146">boolean</span></span> | <span data-ttu-id="a6fe6-147">Geeft aan of de ondertekenaar van het hoofdcertificaat Microsoft is</span><span class="sxs-lookup"><span data-stu-id="a6fe6-147">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="a6fe6-148">lang</span><span class="sxs-lookup"><span data-stu-id="a6fe6-148">long</span></span> | <span data-ttu-id="a6fe6-149">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="a6fe6-149">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="a6fe6-150">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp.</span><span class="sxs-lookup"><span data-stu-id="a6fe6-150">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="a6fe6-151">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a6fe6-151">Related topics</span></span>
- [<span data-ttu-id="a6fe6-152">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="a6fe6-152">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a6fe6-153">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="a6fe6-153">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a6fe6-154">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="a6fe6-154">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a6fe6-155">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="a6fe6-155">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a6fe6-156">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="a6fe6-156">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a6fe6-157">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="a6fe6-157">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
