---
title: Tabel DeviceFileCertificateInfo in het geavanceerde schema voor de jacht
description: Meer informatie over bestands ondertekeningsgegevens in de tabel DeviceFileCertificateInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, digital signature, certificate, file signing, DeviceFileCertificateInfo
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
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: f693c54828d8ede1d21167817f77b875ab5680ce
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499172"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="8f1d8-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="8f1d8-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8f1d8-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8f1d8-105">**Applies to:**</span></span>
- [<span data-ttu-id="8f1d8-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8f1d8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="8f1d8-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8f1d8-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8f1d8-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8f1d8-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="8f1d8-109">De `DeviceFileCertificateInfo` tabel in het geavanceerde schema voor de [jacht](advanced-hunting-overview.md) bevat informatie over certificaat voor bestands ondertekening.</span><span class="sxs-lookup"><span data-stu-id="8f1d8-109">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="8f1d8-110">In deze tabel worden gegevens gebruikt die zijn verkregen uit activiteiten voor certificaatverificatie die regelmatig worden uitgevoerd op bestanden op eindpunten.</span><span class="sxs-lookup"><span data-stu-id="8f1d8-110">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="8f1d8-111">Zie de geavanceerde verwijzing naar het schema voor de jacht voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="8f1d8-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="8f1d8-112">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="8f1d8-112">Column name</span></span> | <span data-ttu-id="8f1d8-113">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="8f1d8-113">Data type</span></span> | <span data-ttu-id="8f1d8-114">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="8f1d8-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="8f1d8-115">datetime</span><span class="sxs-lookup"><span data-stu-id="8f1d8-115">datetime</span></span> | <span data-ttu-id="8f1d8-116">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="8f1d8-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="8f1d8-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8f1d8-117">string</span></span> | <span data-ttu-id="8f1d8-118">Unieke id voor het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="8f1d8-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="8f1d8-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8f1d8-119">string</span></span> | <span data-ttu-id="8f1d8-120">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat</span><span class="sxs-lookup"><span data-stu-id="8f1d8-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `SHA1` | <span data-ttu-id="8f1d8-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8f1d8-121">string</span></span> | <span data-ttu-id="8f1d8-122">SHA-1 van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="8f1d8-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="8f1d8-123">booleaanse</span><span class="sxs-lookup"><span data-stu-id="8f1d8-123">boolean</span></span> | <span data-ttu-id="8f1d8-124">Geeft aan of het bestand is ondertekend</span><span class="sxs-lookup"><span data-stu-id="8f1d8-124">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="8f1d8-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8f1d8-125">string</span></span> | <span data-ttu-id="8f1d8-126">Geeft aan of handtekeninggegevens zijn gelezen als ingesloten inhoud in het bestand zelf of gelezen uit een extern catalogusbestand</span><span class="sxs-lookup"><span data-stu-id="8f1d8-126">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="8f1d8-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8f1d8-127">string</span></span> | <span data-ttu-id="8f1d8-128">Informatie over de ondertekenaar van het bestand</span><span class="sxs-lookup"><span data-stu-id="8f1d8-128">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="8f1d8-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8f1d8-129">string</span></span> | <span data-ttu-id="8f1d8-130">Unieke hashwaarde die de ondertekenaar identificeert</span><span class="sxs-lookup"><span data-stu-id="8f1d8-130">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="8f1d8-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8f1d8-131">string</span></span> | <span data-ttu-id="8f1d8-132">Informatie over de certificeringsinstantie voor afgifte (CA)</span><span class="sxs-lookup"><span data-stu-id="8f1d8-132">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="8f1d8-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8f1d8-133">string</span></span> | <span data-ttu-id="8f1d8-134">Unieke hashwaarde voor het identificeren van certificeringsinstantie (CA)</span><span class="sxs-lookup"><span data-stu-id="8f1d8-134">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="8f1d8-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8f1d8-135">string</span></span> | <span data-ttu-id="8f1d8-136">Id voor het certificaat dat uniek is voor de certificeringsinstantie voor afgifte (CA)</span><span class="sxs-lookup"><span data-stu-id="8f1d8-136">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="8f1d8-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8f1d8-137">string</span></span> |  <span data-ttu-id="8f1d8-138">JSON-matrix met de URL's van netwerkaandelen die certificaten en certificaatteroeplijsten (CRL's) bevatten</span><span class="sxs-lookup"><span data-stu-id="8f1d8-138">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="8f1d8-139">datetime</span><span class="sxs-lookup"><span data-stu-id="8f1d8-139">datetime</span></span> | <span data-ttu-id="8f1d8-140">Datum en tijd waarop het certificaat is gemaakt</span><span class="sxs-lookup"><span data-stu-id="8f1d8-140">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="8f1d8-141">datetime</span><span class="sxs-lookup"><span data-stu-id="8f1d8-141">datetime</span></span> | <span data-ttu-id="8f1d8-142">Datum en tijd waarop het certificaat is ingesteld op verlopen</span><span class="sxs-lookup"><span data-stu-id="8f1d8-142">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="8f1d8-143">datetime</span><span class="sxs-lookup"><span data-stu-id="8f1d8-143">datetime</span></span> | <span data-ttu-id="8f1d8-144">Datum en tijd waarop het certificaat is ondertekend</span><span class="sxs-lookup"><span data-stu-id="8f1d8-144">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="8f1d8-145">booleaanse</span><span class="sxs-lookup"><span data-stu-id="8f1d8-145">boolean</span></span> | <span data-ttu-id="8f1d8-146">Geeft aan of het bestand wordt vertrouwd op basis van de resultaten van de functie WinVerifyTrust, die controleert op onbekende basiscertificaatgegevens, ongeldige handtekeningen, ingetrokken certificaten en andere twijfelachtige kenmerken</span><span class="sxs-lookup"><span data-stu-id="8f1d8-146">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="8f1d8-147">booleaanse</span><span class="sxs-lookup"><span data-stu-id="8f1d8-147">boolean</span></span> | <span data-ttu-id="8f1d8-148">Geeft aan of de ondertekenaar van het hoofdcertificaat Microsoft is</span><span class="sxs-lookup"><span data-stu-id="8f1d8-148">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="8f1d8-149">lang</span><span class="sxs-lookup"><span data-stu-id="8f1d8-149">long</span></span> | <span data-ttu-id="8f1d8-150">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="8f1d8-150">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="8f1d8-151">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp.</span><span class="sxs-lookup"><span data-stu-id="8f1d8-151">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |


## <a name="related-topics"></a><span data-ttu-id="8f1d8-152">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8f1d8-152">Related topics</span></span>
- [<span data-ttu-id="8f1d8-153">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="8f1d8-153">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8f1d8-154">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="8f1d8-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8f1d8-155">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="8f1d8-155">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
