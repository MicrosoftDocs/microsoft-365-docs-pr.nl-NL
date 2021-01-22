---
title: De tabel AlertEvidence in het geavanceerde schema voor zoeken
description: Meer informatie over de informatie die is gekoppeld aan waarschuwingen in de tabel AlertEvidence van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account
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
ms.openlocfilehash: c01b0aae1eff3d9b4add632aff0f13cb56941a30
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932302"
---
# <a name="alertevidence"></a><span data-ttu-id="14f9c-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="14f9c-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="14f9c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="14f9c-105">**Applies to:**</span></span>
- <span data-ttu-id="14f9c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="14f9c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="14f9c-107">De tabel in het geavanceerde zoekschema bevat informatie over verschillende entiteiten `AlertEvidence` (bestanden, [](advanced-hunting-overview.md) IP-adressen, URL's, gebruikers of apparaten) die zijn gekoppeld aan waarschuwingen van Microsoft Defender voor eindpunt, Microsoft Defender voor Office 365, Microsoft Cloud App Security en Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="14f9c-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="14f9c-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="14f9c-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="14f9c-109">Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="14f9c-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="14f9c-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="14f9c-110">Column name</span></span> | <span data-ttu-id="14f9c-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="14f9c-111">Data type</span></span> | <span data-ttu-id="14f9c-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="14f9c-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="14f9c-113">datetime</span><span class="sxs-lookup"><span data-stu-id="14f9c-113">datetime</span></span> | <span data-ttu-id="14f9c-114">Datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="14f9c-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="14f9c-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-115">string</span></span> | <span data-ttu-id="14f9c-116">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="14f9c-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="14f9c-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-117">string</span></span> | <span data-ttu-id="14f9c-118">Product of service dat de waarschuwingsgegevens heeft verstrekt</span><span class="sxs-lookup"><span data-stu-id="14f9c-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="14f9c-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-119">string</span></span> | <span data-ttu-id="14f9c-120">Type object, zoals een bestand, een proces, een apparaat of een gebruiker</span><span class="sxs-lookup"><span data-stu-id="14f9c-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="14f9c-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-121">string</span></span> | <span data-ttu-id="14f9c-122">Hoe de entiteit is betrokken bij een waarschuwing, om aan te geven of deze van invloed is of alleen is gerelateerd</span><span class="sxs-lookup"><span data-stu-id="14f9c-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="14f9c-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-123">string</span></span> | <span data-ttu-id="14f9c-124">Geeft aan of de entiteit de bron of het doel van een netwerkverbinding is</span><span class="sxs-lookup"><span data-stu-id="14f9c-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="14f9c-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-125">string</span></span> | <span data-ttu-id="14f9c-126">Naam van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="14f9c-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="14f9c-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-127">string</span></span> | <span data-ttu-id="14f9c-128">Map met het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="14f9c-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="14f9c-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-129">string</span></span> | <span data-ttu-id="14f9c-130">SHA-1 van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="14f9c-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="14f9c-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-131">string</span></span> | <span data-ttu-id="14f9c-132">SHA-256 van het bestand waar de opgenomen actie op is toegepast.</span><span class="sxs-lookup"><span data-stu-id="14f9c-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="14f9c-133">Dit veld wordt meestal niet ingevuld. Gebruik de kolom SHA1 indien beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="14f9c-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="14f9c-134">int</span><span class="sxs-lookup"><span data-stu-id="14f9c-134">int</span></span> | <span data-ttu-id="14f9c-135">Grootte van het bestand in bytes</span><span class="sxs-lookup"><span data-stu-id="14f9c-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="14f9c-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-136">string</span></span> | <span data-ttu-id="14f9c-137">Malwarefamilie waarbij het verdachte of schadelijke bestand of proces is geclassificeerd onder</span><span class="sxs-lookup"><span data-stu-id="14f9c-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="14f9c-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-138">string</span></span> | <span data-ttu-id="14f9c-139">IP-adres dat werd gekoppeld aan</span><span class="sxs-lookup"><span data-stu-id="14f9c-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="14f9c-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-140">string</span></span> | <span data-ttu-id="14f9c-141">URL of FQDN (Fully Qualified Domain Name) die werd verbonden met</span><span class="sxs-lookup"><span data-stu-id="14f9c-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="14f9c-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-142">string</span></span> | <span data-ttu-id="14f9c-143">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="14f9c-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="14f9c-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-144">string</span></span> | <span data-ttu-id="14f9c-145">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="14f9c-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="14f9c-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-146">string</span></span> | <span data-ttu-id="14f9c-147">Security Identifier (SID) van het account</span><span class="sxs-lookup"><span data-stu-id="14f9c-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="14f9c-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-148">string</span></span> | <span data-ttu-id="14f9c-149">Unieke id voor het account in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="14f9c-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="14f9c-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-150">string</span></span> | <span data-ttu-id="14f9c-151">Unieke id voor het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="14f9c-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="14f9c-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-152">string</span></span> | <span data-ttu-id="14f9c-153">FQDN (Fully Qualified Domain Name) van de computer</span><span class="sxs-lookup"><span data-stu-id="14f9c-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="14f9c-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-154">string</span></span> | <span data-ttu-id="14f9c-155">IP-adres dat is toegewezen aan het lokale apparaat dat tijdens communicatie wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="14f9c-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="14f9c-156">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-156">string</span></span> | <span data-ttu-id="14f9c-157">Unieke id voor het e-mailbericht, gegenereerd door Office 365</span><span class="sxs-lookup"><span data-stu-id="14f9c-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="14f9c-158">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-158">string</span></span> | <span data-ttu-id="14f9c-159">Onderwerp van de e-mail</span><span class="sxs-lookup"><span data-stu-id="14f9c-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="14f9c-160">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-160">string</span></span> | <span data-ttu-id="14f9c-161">Unieke id voor de toepassing</span><span class="sxs-lookup"><span data-stu-id="14f9c-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="14f9c-162">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-162">string</span></span> | <span data-ttu-id="14f9c-163">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="14f9c-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="14f9c-164">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-164">string</span></span> | <span data-ttu-id="14f9c-165">Opdrachtregel die wordt gebruikt om het nieuwe proces te maken</span><span class="sxs-lookup"><span data-stu-id="14f9c-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="14f9c-166">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="14f9c-166">string</span></span> | <span data-ttu-id="14f9c-167">Aanvullende informatie over de gebeurtenis in de JSON-matrixindeling</span><span class="sxs-lookup"><span data-stu-id="14f9c-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="14f9c-168">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="14f9c-168">Related topics</span></span>
- [<span data-ttu-id="14f9c-169">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="14f9c-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="14f9c-170">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="14f9c-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="14f9c-171">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="14f9c-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="14f9c-172">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="14f9c-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="14f9c-173">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="14f9c-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="14f9c-174">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="14f9c-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
