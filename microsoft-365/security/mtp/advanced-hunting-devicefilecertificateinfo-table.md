---
title: DeviceFileCertificateInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over informatie over het ondertekenen van bestanden vindt u in de tabel DeviceFileCertificateInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, digitale handtekening, certificaat, bestand ondertekening, DeviceFileCertificateInfo
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
ms.openlocfilehash: cba27b5b43141c8c90f9a8bc7f70c55aabc1979d
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899313"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="b4f6d-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="b4f6d-104">DeviceFileCertificateInfo</span></span>

<span data-ttu-id="b4f6d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b4f6d-105">**Applies to:**</span></span>
- <span data-ttu-id="b4f6d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b4f6d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b4f6d-107">De `DeviceFileCertificateInfo` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over certificaten voor het ondertekenen van bestanden.</span><span class="sxs-lookup"><span data-stu-id="b4f6d-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="b4f6d-108">Deze tabel maakt gebruik van gegevens die zijn verkregen uit certificaatverificatieactiviteiten die regelmatig worden uitgevoerd in bestanden op eindpunten.</span><span class="sxs-lookup"><span data-stu-id="b4f6d-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="b4f6d-109">Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.</span><span class="sxs-lookup"><span data-stu-id="b4f6d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b4f6d-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="b4f6d-110">Column name</span></span> | <span data-ttu-id="b4f6d-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="b4f6d-111">Data type</span></span> | <span data-ttu-id="b4f6d-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b4f6d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b4f6d-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="b4f6d-113">datetime</span></span> | <span data-ttu-id="b4f6d-114">Datum en tijdstip waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="b4f6d-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="b4f6d-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4f6d-115">string</span></span> | <span data-ttu-id="b4f6d-116">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="b4f6d-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b4f6d-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4f6d-117">string</span></span> | <span data-ttu-id="b4f6d-118">Volledig gekwalificeerde domeinnaam (FQDN) van de machine</span><span class="sxs-lookup"><span data-stu-id="b4f6d-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="b4f6d-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4f6d-119">string</span></span> | <span data-ttu-id="b4f6d-120">SHA-1 van het bestand waarop de geregistreerde actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="b4f6d-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="b4f6d-121">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="b4f6d-121">boolean</span></span> | <span data-ttu-id="b4f6d-122">Geeft aan of het bestand is ondertekend</span><span class="sxs-lookup"><span data-stu-id="b4f6d-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="b4f6d-123">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4f6d-123">string</span></span> | <span data-ttu-id="b4f6d-124">Geeft aan of handtekeninggegevens zijn gelezen als ingesloten inhoud in het bestand zelf of gelezen vanuit een extern catalogusbestand</span><span class="sxs-lookup"><span data-stu-id="b4f6d-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="b4f6d-125">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4f6d-125">string</span></span> | <span data-ttu-id="b4f6d-126">Informatie over de ondertekenaar van het bestand</span><span class="sxs-lookup"><span data-stu-id="b4f6d-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="b4f6d-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4f6d-127">string</span></span> | <span data-ttu-id="b4f6d-128">Unieke hashwaarde die de ondertekenaar identificeert</span><span class="sxs-lookup"><span data-stu-id="b4f6d-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="b4f6d-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4f6d-129">string</span></span> | <span data-ttu-id="b4f6d-130">Informatie over de instantie van afgiftecertificaat (CA)</span><span class="sxs-lookup"><span data-stu-id="b4f6d-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="b4f6d-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4f6d-131">string</span></span> | <span data-ttu-id="b4f6d-132">Unieke hashwaarde die de uitgiftecertificaatautoriteit (CA) identificeert</span><span class="sxs-lookup"><span data-stu-id="b4f6d-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="b4f6d-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4f6d-133">string</span></span> | <span data-ttu-id="b4f6d-134">Identificatienummer voor het certificaat dat uniek is voor de instantie van afgiftecertificaat (CA)</span><span class="sxs-lookup"><span data-stu-id="b4f6d-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="b4f6d-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4f6d-135">string</span></span> |  <span data-ttu-id="b4f6d-136">JSON-array met de URL's van netwerkshares die certificaten en certificaatintrekkingslijsten (CRL's) bevatten</span><span class="sxs-lookup"><span data-stu-id="b4f6d-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="b4f6d-137">Datetime</span><span class="sxs-lookup"><span data-stu-id="b4f6d-137">datetime</span></span> | <span data-ttu-id="b4f6d-138">Datum en tijd waarop het certificaat is gemaakt</span><span class="sxs-lookup"><span data-stu-id="b4f6d-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="b4f6d-139">Datetime</span><span class="sxs-lookup"><span data-stu-id="b4f6d-139">datetime</span></span> | <span data-ttu-id="b4f6d-140">Datum en tijd waarop het certificaat is ingesteld om te verlopen</span><span class="sxs-lookup"><span data-stu-id="b4f6d-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="b4f6d-141">Datetime</span><span class="sxs-lookup"><span data-stu-id="b4f6d-141">datetime</span></span> | <span data-ttu-id="b4f6d-142">Datum en tijd waarop het certificaat is ondertekend</span><span class="sxs-lookup"><span data-stu-id="b4f6d-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="b4f6d-143">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="b4f6d-143">boolean</span></span> | <span data-ttu-id="b4f6d-144">Geeft aan of het bestand wordt vertrouwd op basis van de resultaten van de functie WinVerifyTrust, die controleert op onbekende basiscertificaatgegevens, ongeldige handtekeningen, ingetrokken certificaten en andere twijfelachtige kenmerken</span><span class="sxs-lookup"><span data-stu-id="b4f6d-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="b4f6d-145">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="b4f6d-145">boolean</span></span> | <span data-ttu-id="b4f6d-146">Geeft aan of de ondertekenaar van het basiscertificaat Microsoft is</span><span class="sxs-lookup"><span data-stu-id="b4f6d-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="b4f6d-147">Lange</span><span class="sxs-lookup"><span data-stu-id="b4f6d-147">long</span></span> | <span data-ttu-id="b4f6d-148">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="b4f6d-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="b4f6d-149">Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp.</span><span class="sxs-lookup"><span data-stu-id="b4f6d-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="b4f6d-150">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b4f6d-150">Related topics</span></span>
- [<span data-ttu-id="b4f6d-151">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b4f6d-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b4f6d-152">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="b4f6d-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b4f6d-153">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="b4f6d-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b4f6d-154">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="b4f6d-154">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b4f6d-155">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="b4f6d-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b4f6d-156">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="b4f6d-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
