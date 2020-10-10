---
title: DeviceFileCertificateInfo-tabel in het geavanceerde jacht schema
description: Meer informatie over informatie over bestands ondertekening in de tabel DeviceFileCertificateInfo van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema verwijzing, kusto, tabel, kolom, gegevenstype, digitale handtekening, certificaat, bestands ondertekening, DeviceFileCertificateInfo
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 3c9ee14fc316f767ad57fe32920dd3034a1cd795
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412236"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="d596d-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="d596d-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d596d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d596d-105">**Applies to:**</span></span>
- <span data-ttu-id="d596d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d596d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d596d-107">De `DeviceFileCertificateInfo` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat informatie over het ondertekenen van certificaten.</span><span class="sxs-lookup"><span data-stu-id="d596d-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="d596d-108">In deze tabel worden de gegevens gebruikt die zijn verkregen van activiteiten voor certificaatverificatie, die regelmatig worden uitgevoerd voor bestanden op eindpunten.</span><span class="sxs-lookup"><span data-stu-id="d596d-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="d596d-109">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="d596d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d596d-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="d596d-110">Column name</span></span> | <span data-ttu-id="d596d-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="d596d-111">Data type</span></span> | <span data-ttu-id="d596d-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="d596d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d596d-113">tijd</span><span class="sxs-lookup"><span data-stu-id="d596d-113">datetime</span></span> | <span data-ttu-id="d596d-114">De datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="d596d-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="d596d-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d596d-115">string</span></span> | <span data-ttu-id="d596d-116">Unieke id voor de computer in de service</span><span class="sxs-lookup"><span data-stu-id="d596d-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d596d-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d596d-117">string</span></span> | <span data-ttu-id="d596d-118">FQDN-naam (Fully Qualified Domain Name) van de computer</span><span class="sxs-lookup"><span data-stu-id="d596d-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="d596d-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d596d-119">string</span></span> | <span data-ttu-id="d596d-120">SHA-1 van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="d596d-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="d596d-121">Boolean</span><span class="sxs-lookup"><span data-stu-id="d596d-121">boolean</span></span> | <span data-ttu-id="d596d-122">Geeft aan of het bestand is ondertekend</span><span class="sxs-lookup"><span data-stu-id="d596d-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="d596d-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d596d-123">string</span></span> | <span data-ttu-id="d596d-124">Hiermee wordt aangegeven of de gegevens in het bestand zelf zijn ingesloten in het bestand zelf en uit een extern catalogusbestand gelezen.</span><span class="sxs-lookup"><span data-stu-id="d596d-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="d596d-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d596d-125">string</span></span> | <span data-ttu-id="d596d-126">Informatie over de ondertekenaar van het bestand</span><span class="sxs-lookup"><span data-stu-id="d596d-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="d596d-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d596d-127">string</span></span> | <span data-ttu-id="d596d-128">Unieke hash-waarde die de ondertekenaar identificeert</span><span class="sxs-lookup"><span data-stu-id="d596d-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="d596d-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d596d-129">string</span></span> | <span data-ttu-id="d596d-130">Informatie over de uitgevende certificeringsinstantie (CA)</span><span class="sxs-lookup"><span data-stu-id="d596d-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="d596d-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d596d-131">string</span></span> | <span data-ttu-id="d596d-132">Unieke hashwaarde die een certificeringsinstantie (CA) identificeert</span><span class="sxs-lookup"><span data-stu-id="d596d-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="d596d-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d596d-133">string</span></span> | <span data-ttu-id="d596d-134">De id van het certificaat dat uniek is voor de uitgevende certificeringsinstantie (CA)</span><span class="sxs-lookup"><span data-stu-id="d596d-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="d596d-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="d596d-135">string</span></span> |  <span data-ttu-id="d596d-136">JSON-matrix met de Url's van netwerkshares die certificaten en certificaatintrekkingslijsten (Crl's) bevatten</span><span class="sxs-lookup"><span data-stu-id="d596d-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="d596d-137">tijd</span><span class="sxs-lookup"><span data-stu-id="d596d-137">datetime</span></span> | <span data-ttu-id="d596d-138">De datum en tijd waarop het certificaat is gemaakt</span><span class="sxs-lookup"><span data-stu-id="d596d-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="d596d-139">tijd</span><span class="sxs-lookup"><span data-stu-id="d596d-139">datetime</span></span> | <span data-ttu-id="d596d-140">Datum en tijd waarop het certificaat is ingesteld op verloopt</span><span class="sxs-lookup"><span data-stu-id="d596d-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="d596d-141">tijd</span><span class="sxs-lookup"><span data-stu-id="d596d-141">datetime</span></span> | <span data-ttu-id="d596d-142">De datum en tijd waarop het certificaat is ondertekend</span><span class="sxs-lookup"><span data-stu-id="d596d-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="d596d-143">Boolean</span><span class="sxs-lookup"><span data-stu-id="d596d-143">boolean</span></span> | <span data-ttu-id="d596d-144">Hiermee wordt aangegeven of het bestand wordt vertrouwd op basis van de resultaten van de functie WinVerifyTrust, waarmee wordt gecontroleerd op onbekende basis certificerings informatie, ongeldige handtekeningen, ingetrokken certificaten en andere betrouwbare kenmerken</span><span class="sxs-lookup"><span data-stu-id="d596d-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="d596d-145">Boolean</span><span class="sxs-lookup"><span data-stu-id="d596d-145">boolean</span></span> | <span data-ttu-id="d596d-146">Geeft aan of de ondertekenaar van het basiscertificaat Microsoft is</span><span class="sxs-lookup"><span data-stu-id="d596d-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="d596d-147">lang</span><span class="sxs-lookup"><span data-stu-id="d596d-147">long</span></span> | <span data-ttu-id="d596d-148">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="d596d-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="d596d-149">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de de naam van het apparaat en de timestamp-kolommen.</span><span class="sxs-lookup"><span data-stu-id="d596d-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="d596d-150">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d596d-150">Related topics</span></span>
- [<span data-ttu-id="d596d-151">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="d596d-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d596d-152">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="d596d-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d596d-153">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="d596d-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d596d-154">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="d596d-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d596d-155">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="d596d-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d596d-156">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="d596d-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
