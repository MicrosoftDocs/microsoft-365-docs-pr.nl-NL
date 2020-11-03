---
title: AlertEvidence-tabel in het geavanceerde jacht schema
description: Meer informatie over informatie die is gekoppeld aan waarschuwingen in de tabel AlertEvidence van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, AlertInfo, waarschuwing, entiteit, bewijs, bestand, IP-adres, apparaat, computer, gebruiker
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 549eed005e06a7d52ce2f881820ae9fdeffdfea7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847678"
---
# <a name="alertevidence"></a><span data-ttu-id="72780-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="72780-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="72780-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="72780-105">**Applies to:**</span></span>
- <span data-ttu-id="72780-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72780-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="72780-107">De `AlertEvidence` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat informatie over diverse entiteiten, zoals bestanden, IP-adressen, url's, gebruikers of apparaten, gekoppeld aan waarschuwingen van Microsoft Defender for Endpoint, Microsoft Defender voor Office 365, Microsoft Cloud app Security en Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="72780-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="72780-108">Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="72780-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="72780-109">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="72780-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="72780-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="72780-110">Column name</span></span> | <span data-ttu-id="72780-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="72780-111">Data type</span></span> | <span data-ttu-id="72780-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="72780-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="72780-113">tijd</span><span class="sxs-lookup"><span data-stu-id="72780-113">datetime</span></span> | <span data-ttu-id="72780-114">De datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="72780-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="72780-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-115">string</span></span> | <span data-ttu-id="72780-116">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="72780-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="72780-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-117">string</span></span> | <span data-ttu-id="72780-118">Het product of de service die de waarschuwingsinformatie heeft verstrekt</span><span class="sxs-lookup"><span data-stu-id="72780-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="72780-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-119">string</span></span> | <span data-ttu-id="72780-120">Type object, zoals een bestand, een proces, een apparaat of een gebruiker</span><span class="sxs-lookup"><span data-stu-id="72780-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="72780-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-121">string</span></span> | <span data-ttu-id="72780-122">Hoe de entiteit deel uitmaakt van een melding, geeft aan of het niet wordt beïnvloed</span><span class="sxs-lookup"><span data-stu-id="72780-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="72780-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-123">string</span></span> | <span data-ttu-id="72780-124">Geeft aan of de entiteit de bron is of de bestemming van een netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="72780-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="72780-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-125">string</span></span> | <span data-ttu-id="72780-126">De naam van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="72780-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="72780-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-127">string</span></span> | <span data-ttu-id="72780-128">Map met het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="72780-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="72780-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-129">string</span></span> | <span data-ttu-id="72780-130">SHA-1 van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="72780-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="72780-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-131">string</span></span> | <span data-ttu-id="72780-132">SHA-256 van het bestand waarop de opgenomen actie is toegepast.</span><span class="sxs-lookup"><span data-stu-id="72780-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="72780-133">Dit veld wordt meestal niet ingevuld, met behulp van de SHA1-kolom.</span><span class="sxs-lookup"><span data-stu-id="72780-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="72780-134">int</span><span class="sxs-lookup"><span data-stu-id="72780-134">int</span></span> | <span data-ttu-id="72780-135">Bestandsgrootte in bytes</span><span class="sxs-lookup"><span data-stu-id="72780-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="72780-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-136">string</span></span> | <span data-ttu-id="72780-137">De familie van de malware waarmee het verdachte of schadelijke bestand of proces is geclassificeerd.</span><span class="sxs-lookup"><span data-stu-id="72780-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="72780-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-138">string</span></span> | <span data-ttu-id="72780-139">IP-adres waarop verbinding is gemaakt</span><span class="sxs-lookup"><span data-stu-id="72780-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="72780-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-140">string</span></span> | <span data-ttu-id="72780-141">URL of FQDN (Fully Qualified Domain Name) waarmee verbinding is gemaakt</span><span class="sxs-lookup"><span data-stu-id="72780-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="72780-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-142">string</span></span> | <span data-ttu-id="72780-143">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="72780-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="72780-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-144">string</span></span> | <span data-ttu-id="72780-145">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="72780-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="72780-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-146">string</span></span> | <span data-ttu-id="72780-147">SID (Security Identifier) van het account</span><span class="sxs-lookup"><span data-stu-id="72780-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="72780-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-148">string</span></span> | <span data-ttu-id="72780-149">Unieke id voor het account in azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="72780-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="72780-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-150">string</span></span> | <span data-ttu-id="72780-151">Unieke id van het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="72780-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="72780-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-152">string</span></span> | <span data-ttu-id="72780-153">FQDN-naam (Fully Qualified Domain Name) van de computer</span><span class="sxs-lookup"><span data-stu-id="72780-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="72780-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-154">string</span></span> | <span data-ttu-id="72780-155">Het IP-adres dat is toegewezen aan het lokale apparaat dat wordt gebruikt tijdens de communicatie</span><span class="sxs-lookup"><span data-stu-id="72780-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="72780-156">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-156">string</span></span> | <span data-ttu-id="72780-157">Unieke id voor de e-mail, gegenereerd door Office 365</span><span class="sxs-lookup"><span data-stu-id="72780-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="72780-158">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-158">string</span></span> | <span data-ttu-id="72780-159">Onderwerp van de e-mail</span><span class="sxs-lookup"><span data-stu-id="72780-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="72780-160">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-160">string</span></span> | <span data-ttu-id="72780-161">Unieke id voor de toepassing</span><span class="sxs-lookup"><span data-stu-id="72780-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="72780-162">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-162">string</span></span> | <span data-ttu-id="72780-163">De toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="72780-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="72780-164">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-164">string</span></span> | <span data-ttu-id="72780-165">Opdrachtregel voor het maken van het nieuwe proces</span><span class="sxs-lookup"><span data-stu-id="72780-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="72780-166">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="72780-166">string</span></span> | <span data-ttu-id="72780-167">Aanvullende informatie over de gebeurtenis in de JSON-matrix indeling</span><span class="sxs-lookup"><span data-stu-id="72780-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="72780-168">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="72780-168">Related topics</span></span>
- [<span data-ttu-id="72780-169">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="72780-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="72780-170">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="72780-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="72780-171">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="72780-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="72780-172">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="72780-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="72780-173">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="72780-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="72780-174">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="72780-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
