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
ms.openlocfilehash: 7f6a4f7592e6a8fde0b7ae6269f07ce7f76a5730
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430161"
---
# <a name="alertevidence"></a><span data-ttu-id="f252b-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="f252b-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f252b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f252b-105">**Applies to:**</span></span>
- <span data-ttu-id="f252b-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f252b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f252b-107">De `AlertEvidence` tabel in het [Geavanceerde opjacht](advanced-hunting-overview.md) -schema bevat informatie over diverse entiteiten, zoals bestanden, IP-adressen, url's, gebruikers of apparaten, gekoppeld aan waarschuwingen uit Microsoft Defender atp, Office 365 ATP, Microsoft Cloud app Security en Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="f252b-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="f252b-108">Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="f252b-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="f252b-109">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="f252b-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f252b-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="f252b-110">Column name</span></span> | <span data-ttu-id="f252b-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="f252b-111">Data type</span></span> | <span data-ttu-id="f252b-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f252b-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f252b-113">tijd</span><span class="sxs-lookup"><span data-stu-id="f252b-113">datetime</span></span> | <span data-ttu-id="f252b-114">De datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="f252b-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="f252b-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-115">string</span></span> | <span data-ttu-id="f252b-116">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="f252b-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="f252b-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-117">string</span></span> | <span data-ttu-id="f252b-118">Het product of de service die de waarschuwingsinformatie heeft verstrekt</span><span class="sxs-lookup"><span data-stu-id="f252b-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="f252b-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-119">string</span></span> | <span data-ttu-id="f252b-120">Type object, zoals een bestand, een proces, een apparaat of een gebruiker</span><span class="sxs-lookup"><span data-stu-id="f252b-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="f252b-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-121">string</span></span> | <span data-ttu-id="f252b-122">Hoe de entiteit deel uitmaakt van een melding, geeft aan of het niet wordt beïnvloed</span><span class="sxs-lookup"><span data-stu-id="f252b-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="f252b-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-123">string</span></span> | <span data-ttu-id="f252b-124">Geeft aan of de entiteit de bron is of de bestemming van een netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="f252b-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="f252b-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-125">string</span></span> | <span data-ttu-id="f252b-126">De naam van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="f252b-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="f252b-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-127">string</span></span> | <span data-ttu-id="f252b-128">Map met het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="f252b-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="f252b-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-129">string</span></span> | <span data-ttu-id="f252b-130">SHA-1 van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="f252b-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="f252b-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-131">string</span></span> | <span data-ttu-id="f252b-132">SHA-256 van het bestand waarop de opgenomen actie is toegepast.</span><span class="sxs-lookup"><span data-stu-id="f252b-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="f252b-133">Dit veld wordt meestal niet ingevuld, met behulp van de SHA1-kolom.</span><span class="sxs-lookup"><span data-stu-id="f252b-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="f252b-134">int</span><span class="sxs-lookup"><span data-stu-id="f252b-134">int</span></span> | <span data-ttu-id="f252b-135">Bestandsgrootte in bytes</span><span class="sxs-lookup"><span data-stu-id="f252b-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="f252b-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-136">string</span></span> | <span data-ttu-id="f252b-137">De familie van de malware waarmee het verdachte of schadelijke bestand of proces is geclassificeerd.</span><span class="sxs-lookup"><span data-stu-id="f252b-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="f252b-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-138">string</span></span> | <span data-ttu-id="f252b-139">IP-adres waarop verbinding is gemaakt</span><span class="sxs-lookup"><span data-stu-id="f252b-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="f252b-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-140">string</span></span> | <span data-ttu-id="f252b-141">URL of FQDN (Fully Qualified Domain Name) waarmee verbinding is gemaakt</span><span class="sxs-lookup"><span data-stu-id="f252b-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="f252b-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-142">string</span></span> | <span data-ttu-id="f252b-143">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="f252b-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="f252b-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-144">string</span></span> | <span data-ttu-id="f252b-145">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="f252b-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="f252b-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-146">string</span></span> | <span data-ttu-id="f252b-147">SID (Security Identifier) van het account</span><span class="sxs-lookup"><span data-stu-id="f252b-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="f252b-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-148">string</span></span> | <span data-ttu-id="f252b-149">Unieke id voor het account in azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f252b-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="f252b-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-150">string</span></span> | <span data-ttu-id="f252b-151">Unieke id van het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="f252b-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f252b-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-152">string</span></span> | <span data-ttu-id="f252b-153">FQDN-naam (Fully Qualified Domain Name) van de computer</span><span class="sxs-lookup"><span data-stu-id="f252b-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="f252b-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-154">string</span></span> | <span data-ttu-id="f252b-155">Het IP-adres dat is toegewezen aan het lokale apparaat dat wordt gebruikt tijdens de communicatie</span><span class="sxs-lookup"><span data-stu-id="f252b-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="f252b-156">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-156">string</span></span> | <span data-ttu-id="f252b-157">Unieke id voor de e-mail, gegenereerd door Office 365</span><span class="sxs-lookup"><span data-stu-id="f252b-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="f252b-158">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-158">string</span></span> | <span data-ttu-id="f252b-159">Onderwerp van de e-mail</span><span class="sxs-lookup"><span data-stu-id="f252b-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="f252b-160">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-160">string</span></span> | <span data-ttu-id="f252b-161">Unieke id voor de toepassing</span><span class="sxs-lookup"><span data-stu-id="f252b-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="f252b-162">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-162">string</span></span> | <span data-ttu-id="f252b-163">De toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="f252b-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="f252b-164">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-164">string</span></span> | <span data-ttu-id="f252b-165">Opdrachtregel voor het maken van het nieuwe proces</span><span class="sxs-lookup"><span data-stu-id="f252b-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="f252b-166">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f252b-166">string</span></span> | <span data-ttu-id="f252b-167">Aanvullende informatie over de gebeurtenis in de JSON-matrix indeling</span><span class="sxs-lookup"><span data-stu-id="f252b-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f252b-168">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f252b-168">Related topics</span></span>
- [<span data-ttu-id="f252b-169">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="f252b-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f252b-170">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="f252b-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f252b-171">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="f252b-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f252b-172">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="f252b-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f252b-173">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="f252b-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f252b-174">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="f252b-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
