---
title: DeviceFileCertificateInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over bestandsondertekeningsgegevens in de tabel DeviceFileCertificateInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, digitale handtekening, certificaat, bestandsondertekening, DeviceFileCertificateInfo
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
ms.openlocfilehash: fcbd487aeed633176c86fd22bfcd156be02fea22
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2020
ms.locfileid: "43900787"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="b7c54-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="b7c54-104">DeviceFileCertificateInfo</span></span>

<span data-ttu-id="b7c54-105">**Geldt voor:**</span><span class="sxs-lookup"><span data-stu-id="b7c54-105">**Applies to:**</span></span>
- <span data-ttu-id="b7c54-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b7c54-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b7c54-107">De `DeviceFileCertificateInfo` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over certificaten voor het ondertekenen van bestanden.</span><span class="sxs-lookup"><span data-stu-id="b7c54-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="b7c54-108">In deze tabel worden gegevens gebruikt die zijn verkregen uit certificaatverificatieactiviteiten die regelmatig worden uitgevoerd op bestanden op eindpunten.</span><span class="sxs-lookup"><span data-stu-id="b7c54-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="b7c54-109">Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b7c54-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b7c54-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="b7c54-110">Column name</span></span> | <span data-ttu-id="b7c54-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="b7c54-111">Data type</span></span> | <span data-ttu-id="b7c54-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b7c54-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b7c54-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="b7c54-113">datetime</span></span> | <span data-ttu-id="b7c54-114">Datum en tijdstip waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="b7c54-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="b7c54-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b7c54-115">string</span></span> | <span data-ttu-id="b7c54-116">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="b7c54-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b7c54-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b7c54-117">string</span></span> | <span data-ttu-id="b7c54-118">Volledig gekwalificeerde domeinnaam (FQDN) van de machine</span><span class="sxs-lookup"><span data-stu-id="b7c54-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="b7c54-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b7c54-119">string</span></span> | <span data-ttu-id="b7c54-120">SHA-1 van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="b7c54-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="b7c54-121">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="b7c54-121">boolean</span></span> | <span data-ttu-id="b7c54-122">Geeft aan of het bestand is ondertekend</span><span class="sxs-lookup"><span data-stu-id="b7c54-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="b7c54-123">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b7c54-123">string</span></span> | <span data-ttu-id="b7c54-124">Geeft aan of handtekeninggegevens zijn gelezen als ingesloten inhoud in het bestand zelf of is gelezen uit een extern catalogusbestand</span><span class="sxs-lookup"><span data-stu-id="b7c54-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="b7c54-125">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b7c54-125">string</span></span> | <span data-ttu-id="b7c54-126">Informatie over de ondertekenaar van het bestand</span><span class="sxs-lookup"><span data-stu-id="b7c54-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="b7c54-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b7c54-127">string</span></span> | <span data-ttu-id="b7c54-128">Unieke hashwaarde die de ondertekenaar identificeert</span><span class="sxs-lookup"><span data-stu-id="b7c54-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="b7c54-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b7c54-129">string</span></span> | <span data-ttu-id="b7c54-130">Informatie over de instantie van afgifte van certificaten (CA)</span><span class="sxs-lookup"><span data-stu-id="b7c54-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="b7c54-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b7c54-131">string</span></span> | <span data-ttu-id="b7c54-132">Unieke hashwaarde die de instantie voor afgifte van certificaten (CA) identificeert</span><span class="sxs-lookup"><span data-stu-id="b7c54-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="b7c54-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b7c54-133">string</span></span> | <span data-ttu-id="b7c54-134">Identificatienummer voor het certificaat dat uniek is voor de instantie van afgifte van certificaten (CA)</span><span class="sxs-lookup"><span data-stu-id="b7c54-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="b7c54-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b7c54-135">string</span></span> |  <span data-ttu-id="b7c54-136">JSON-array met de URL's van netwerkshares die certificaten en certificaatintrekkingslijsten (CRL's) bevatten</span><span class="sxs-lookup"><span data-stu-id="b7c54-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="b7c54-137">Datetime</span><span class="sxs-lookup"><span data-stu-id="b7c54-137">datetime</span></span> | <span data-ttu-id="b7c54-138">Datum en tijd van het certificaat is gemaakt</span><span class="sxs-lookup"><span data-stu-id="b7c54-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="b7c54-139">Datetime</span><span class="sxs-lookup"><span data-stu-id="b7c54-139">datetime</span></span> | <span data-ttu-id="b7c54-140">Datum en tijd dat het certificaat verloopt</span><span class="sxs-lookup"><span data-stu-id="b7c54-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="b7c54-141">Datetime</span><span class="sxs-lookup"><span data-stu-id="b7c54-141">datetime</span></span> | <span data-ttu-id="b7c54-142">Datum en tijd waarop het certificaat is ondertekend</span><span class="sxs-lookup"><span data-stu-id="b7c54-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="b7c54-143">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="b7c54-143">boolean</span></span> | <span data-ttu-id="b7c54-144">Geeft aan of het bestand wordt vertrouwd op basis van de resultaten van de functie WinVerifyTrust, die controleert op onbekende basiscertificaatgegevens, ongeldige handtekeningen, ingetrokken certificaten en andere twijfelachtige kenmerken</span><span class="sxs-lookup"><span data-stu-id="b7c54-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="b7c54-145">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="b7c54-145">boolean</span></span> | <span data-ttu-id="b7c54-146">Geeft aan of de ondertekenaar van het hoofdcertificaat Microsoft is</span><span class="sxs-lookup"><span data-stu-id="b7c54-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="b7c54-147">Lange</span><span class="sxs-lookup"><span data-stu-id="b7c54-147">long</span></span> | <span data-ttu-id="b7c54-148">Gebeurtenis-id op basis van een herhalingsteller.</span><span class="sxs-lookup"><span data-stu-id="b7c54-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="b7c54-149">Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp.</span><span class="sxs-lookup"><span data-stu-id="b7c54-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="b7c54-150">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b7c54-150">Related topics</span></span>
- [<span data-ttu-id="b7c54-151">Proactief op zoek naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="b7c54-151">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b7c54-152">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="b7c54-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b7c54-153">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="b7c54-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b7c54-154">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="b7c54-154">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b7c54-155">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="b7c54-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b7c54-156">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="b7c54-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
