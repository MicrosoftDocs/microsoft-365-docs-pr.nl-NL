---
title: DeviceFileCertificateInfoBeta tabel in de geavanceerde jacht schema
description: Meer informatie over gegevens over het ondertekenen van bestanden in de DeviceFileCertificateInfoBeta-tabel van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreigingjacht, cyberdreigingsjacht, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, digitale handtekening, certificaat, bestandsondertekening, DeviceFileCertificateInfoBeta
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
ms.openlocfilehash: c1d6b9170f0cc236f2656ce2adb596c31d9ee2bd
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811681"
---
# <a name="devicefilecertificateinfobeta"></a><span data-ttu-id="da8f7-104">DeviceFileCertificateInfoBeta</span><span class="sxs-lookup"><span data-stu-id="da8f7-104">DeviceFileCertificateInfoBeta</span></span>

<span data-ttu-id="da8f7-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="da8f7-105">**Applies to:**</span></span>
- <span data-ttu-id="da8f7-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="da8f7-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="da8f7-107">De `DeviceFileCertificateInfoBeta` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over certificaten voor het ondertekenen van bestanden.</span><span class="sxs-lookup"><span data-stu-id="da8f7-107">The `DeviceFileCertificateInfoBeta` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="da8f7-108">Deze tabel gebruikt gegevens die zijn verkregen uit certificeringsverificatieactiviteiten die regelmatig worden uitgevoerd in bestanden op eindpunten.</span><span class="sxs-lookup"><span data-stu-id="da8f7-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="da8f7-109">Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.</span><span class="sxs-lookup"><span data-stu-id="da8f7-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="da8f7-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="da8f7-110">Column name</span></span> | <span data-ttu-id="da8f7-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="da8f7-111">Data type</span></span> | <span data-ttu-id="da8f7-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="da8f7-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="da8f7-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="da8f7-113">datetime</span></span> | <span data-ttu-id="da8f7-114">Datum en tijd waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="da8f7-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="da8f7-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da8f7-115">string</span></span> | <span data-ttu-id="da8f7-116">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="da8f7-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="da8f7-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da8f7-117">string</span></span> | <span data-ttu-id="da8f7-118">Volledig gekwalificeerde domeinnaam (FQDN) van de machine</span><span class="sxs-lookup"><span data-stu-id="da8f7-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="da8f7-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da8f7-119">string</span></span> | <span data-ttu-id="da8f7-120">SHA-1 van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="da8f7-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="da8f7-121">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="da8f7-121">boolean</span></span> | <span data-ttu-id="da8f7-122">Geeft aan of het bestand is ondertekend</span><span class="sxs-lookup"><span data-stu-id="da8f7-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="da8f7-123">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da8f7-123">string</span></span> | <span data-ttu-id="da8f7-124">Geeft aan of handtekeninggegevens zijn gelezen als ingesloten inhoud in het bestand zelf of uit een extern catalogusbestand zijn gelezen</span><span class="sxs-lookup"><span data-stu-id="da8f7-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="da8f7-125">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da8f7-125">string</span></span> | <span data-ttu-id="da8f7-126">Informatie over de ondertekenaar van het bestand</span><span class="sxs-lookup"><span data-stu-id="da8f7-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="da8f7-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da8f7-127">string</span></span> | <span data-ttu-id="da8f7-128">Unieke hashwaarde die de ondertekenaar identificeert</span><span class="sxs-lookup"><span data-stu-id="da8f7-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="da8f7-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da8f7-129">string</span></span> | <span data-ttu-id="da8f7-130">Informatie over de instantie van afgifte certificaat (CA)</span><span class="sxs-lookup"><span data-stu-id="da8f7-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="da8f7-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da8f7-131">string</span></span> | <span data-ttu-id="da8f7-132">Unieke hashwaarde die de instantie van afgiftecertificaat (CA) identificeert</span><span class="sxs-lookup"><span data-stu-id="da8f7-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="da8f7-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da8f7-133">string</span></span> | <span data-ttu-id="da8f7-134">Identificatiecode voor het certificaat dat uniek is voor de instantie van afgifte van certificaten (CA)</span><span class="sxs-lookup"><span data-stu-id="da8f7-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="da8f7-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da8f7-135">string</span></span> |  <span data-ttu-id="da8f7-136">JSON-array met de URL's van netwerkshares die certificaten en certificaatintrekkingslijsten (CRL's) bevatten</span><span class="sxs-lookup"><span data-stu-id="da8f7-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="da8f7-137">Datetime</span><span class="sxs-lookup"><span data-stu-id="da8f7-137">datetime</span></span> | <span data-ttu-id="da8f7-138">Datum en tijd dat het certificaat is gemaakt</span><span class="sxs-lookup"><span data-stu-id="da8f7-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="da8f7-139">Datetime</span><span class="sxs-lookup"><span data-stu-id="da8f7-139">datetime</span></span> | <span data-ttu-id="da8f7-140">Datum en tijd dat het certificaat is verlopen</span><span class="sxs-lookup"><span data-stu-id="da8f7-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="da8f7-141">Datetime</span><span class="sxs-lookup"><span data-stu-id="da8f7-141">datetime</span></span> | <span data-ttu-id="da8f7-142">Datum en tijd dat het certificaat is tegengetekend</span><span class="sxs-lookup"><span data-stu-id="da8f7-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="da8f7-143">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="da8f7-143">boolean</span></span> | <span data-ttu-id="da8f7-144">Hiermee geeft u aan of het bestand wordt vertrouwd op basis van de resultaten van de functie WinVerifyTrust, die controleert op onbekende basiscertificaatgegevens, ongeldige handtekeningen, ingetrokken certificaten en andere twijfelachtige kenmerken</span><span class="sxs-lookup"><span data-stu-id="da8f7-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="da8f7-145">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="da8f7-145">boolean</span></span> | <span data-ttu-id="da8f7-146">Geeft aan of de ondertekenaar van het basiscertificaat Microsoft is</span><span class="sxs-lookup"><span data-stu-id="da8f7-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="da8f7-147">Lange</span><span class="sxs-lookup"><span data-stu-id="da8f7-147">long</span></span> | <span data-ttu-id="da8f7-148">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="da8f7-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="da8f7-149">Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp.</span><span class="sxs-lookup"><span data-stu-id="da8f7-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="da8f7-150">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="da8f7-150">Related topics</span></span>
- [<span data-ttu-id="da8f7-151">Proactief jagen op bedreigingen</span><span class="sxs-lookup"><span data-stu-id="da8f7-151">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="da8f7-152">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="da8f7-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="da8f7-153">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="da8f7-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="da8f7-154">Op zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="da8f7-154">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="da8f7-155">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="da8f7-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="da8f7-156">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="da8f7-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
