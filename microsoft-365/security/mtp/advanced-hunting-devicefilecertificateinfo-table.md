---
title: DeviceFileCertificateInfo-tabel in het geavanceerde schema voor zoeken
description: Meer informatie over bestands ondertekeningsgegevens in de tabel DeviceFileCertificateInfo van het geavanceerde schema voor zoeken
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e35e8e86f6814a5f90a7921f71ccab7247fcc1bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931312"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="5be29-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="5be29-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5be29-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5be29-105">**Applies to:**</span></span>
- <span data-ttu-id="5be29-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5be29-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5be29-107">De `DeviceFileCertificateInfo` tabel in het geavanceerde schema voor [zoeken](advanced-hunting-overview.md) bevat informatie over certificaten voor bestands ondertekening.</span><span class="sxs-lookup"><span data-stu-id="5be29-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="5be29-108">In deze tabel worden gegevens gebruikt die zijn verkregen uit verificatieactiviteiten van certificaten die regelmatig worden uitgevoerd voor bestanden op eindpunten.</span><span class="sxs-lookup"><span data-stu-id="5be29-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="5be29-109">Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="5be29-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5be29-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="5be29-110">Column name</span></span> | <span data-ttu-id="5be29-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="5be29-111">Data type</span></span> | <span data-ttu-id="5be29-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="5be29-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="5be29-113">datetime</span><span class="sxs-lookup"><span data-stu-id="5be29-113">datetime</span></span> | <span data-ttu-id="5be29-114">Datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="5be29-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="5be29-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5be29-115">string</span></span> | <span data-ttu-id="5be29-116">Unieke id voor de computer in de service</span><span class="sxs-lookup"><span data-stu-id="5be29-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5be29-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5be29-117">string</span></span> | <span data-ttu-id="5be29-118">FQDN (Fully Qualified Domain Name) van de computer</span><span class="sxs-lookup"><span data-stu-id="5be29-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="5be29-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5be29-119">string</span></span> | <span data-ttu-id="5be29-120">SHA-1 van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="5be29-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="5be29-121">boolean</span><span class="sxs-lookup"><span data-stu-id="5be29-121">boolean</span></span> | <span data-ttu-id="5be29-122">Hiermee wordt aangegeven of het bestand is ondertekend</span><span class="sxs-lookup"><span data-stu-id="5be29-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="5be29-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5be29-123">string</span></span> | <span data-ttu-id="5be29-124">Geeft aan of handtekeninginformatie is gelezen als ingesloten inhoud in het bestand zelf of is gelezen vanuit een extern catalogusbestand</span><span class="sxs-lookup"><span data-stu-id="5be29-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="5be29-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5be29-125">string</span></span> | <span data-ttu-id="5be29-126">Informatie over de ondertekenaar van het bestand</span><span class="sxs-lookup"><span data-stu-id="5be29-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="5be29-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5be29-127">string</span></span> | <span data-ttu-id="5be29-128">Unieke hashwaarde die de ondertekenaar identificeert</span><span class="sxs-lookup"><span data-stu-id="5be29-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="5be29-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5be29-129">string</span></span> | <span data-ttu-id="5be29-130">Informatie over de certificeringsinstantie (CA)</span><span class="sxs-lookup"><span data-stu-id="5be29-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="5be29-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5be29-131">string</span></span> | <span data-ttu-id="5be29-132">Unieke hashwaarde identificerende certificeringsinstantie (CA)</span><span class="sxs-lookup"><span data-stu-id="5be29-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="5be29-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5be29-133">string</span></span> | <span data-ttu-id="5be29-134">Id voor het certificaat dat uniek is voor de certificeringsinstantie (CA)</span><span class="sxs-lookup"><span data-stu-id="5be29-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="5be29-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="5be29-135">string</span></span> |  <span data-ttu-id="5be29-136">JSON-matrix met de URL's van netwerk shares die certificaten en certificaatverroepingslijsten (CRL's) bevatten</span><span class="sxs-lookup"><span data-stu-id="5be29-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="5be29-137">datetime</span><span class="sxs-lookup"><span data-stu-id="5be29-137">datetime</span></span> | <span data-ttu-id="5be29-138">Datum en tijd waarop het certificaat is gemaakt</span><span class="sxs-lookup"><span data-stu-id="5be29-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="5be29-139">datetime</span><span class="sxs-lookup"><span data-stu-id="5be29-139">datetime</span></span> | <span data-ttu-id="5be29-140">Datum en tijd waarop het certificaat is ingesteld om te verlopen</span><span class="sxs-lookup"><span data-stu-id="5be29-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="5be29-141">datetime</span><span class="sxs-lookup"><span data-stu-id="5be29-141">datetime</span></span> | <span data-ttu-id="5be29-142">Datum en tijd waarop het certificaat is ondertekend</span><span class="sxs-lookup"><span data-stu-id="5be29-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="5be29-143">boolean</span><span class="sxs-lookup"><span data-stu-id="5be29-143">boolean</span></span> | <span data-ttu-id="5be29-144">Hiermee wordt aangegeven of het bestand wordt vertrouwd op basis van de resultaten van de functie WinVerifyTrust, waarmee wordt gecontroleerd op onbekende basiscertificaatgegevens, ongeldige handtekeningen, ingetrokken certificaten en andere twijfelachtige kenmerken.</span><span class="sxs-lookup"><span data-stu-id="5be29-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="5be29-145">boolean</span><span class="sxs-lookup"><span data-stu-id="5be29-145">boolean</span></span> | <span data-ttu-id="5be29-146">Hiermee wordt aangegeven of Microsoft de ondertekenaar van het basiscertificaat is</span><span class="sxs-lookup"><span data-stu-id="5be29-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="5be29-147">lang</span><span class="sxs-lookup"><span data-stu-id="5be29-147">long</span></span> | <span data-ttu-id="5be29-148">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="5be29-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="5be29-149">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp.</span><span class="sxs-lookup"><span data-stu-id="5be29-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="5be29-150">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="5be29-150">Related topics</span></span>
- [<span data-ttu-id="5be29-151">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="5be29-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5be29-152">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="5be29-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5be29-153">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="5be29-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5be29-154">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="5be29-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5be29-155">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="5be29-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5be29-156">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="5be29-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
