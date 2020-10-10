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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ec6fe3d080efb396ce0ecacadd3d5d9a8fa9f8d1
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413196"
---
# <a name="alertevidence"></a><span data-ttu-id="615cc-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="615cc-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="615cc-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="615cc-105">**Applies to:**</span></span>
- <span data-ttu-id="615cc-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="615cc-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="615cc-107">De `AlertEvidence` tabel in het [Geavanceerde opjacht](advanced-hunting-overview.md) -schema bevat informatie over diverse entiteiten, zoals bestanden, IP-adressen, url's, gebruikers of apparaten, gekoppeld aan waarschuwingen uit Microsoft Defender atp, Office 365 ATP, Microsoft Cloud app Security en Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="615cc-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="615cc-108">Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="615cc-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="615cc-109">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="615cc-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="615cc-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="615cc-110">Column name</span></span> | <span data-ttu-id="615cc-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="615cc-111">Data type</span></span> | <span data-ttu-id="615cc-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="615cc-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="615cc-113">tijd</span><span class="sxs-lookup"><span data-stu-id="615cc-113">datetime</span></span> | <span data-ttu-id="615cc-114">De datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="615cc-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="615cc-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-115">string</span></span> | <span data-ttu-id="615cc-116">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="615cc-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="615cc-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-117">string</span></span> | <span data-ttu-id="615cc-118">Het product of de service die de waarschuwingsinformatie heeft verstrekt</span><span class="sxs-lookup"><span data-stu-id="615cc-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="615cc-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-119">string</span></span> | <span data-ttu-id="615cc-120">Type object, zoals een bestand, een proces, een apparaat of een gebruiker</span><span class="sxs-lookup"><span data-stu-id="615cc-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="615cc-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-121">string</span></span> | <span data-ttu-id="615cc-122">Hoe de entiteit deel uitmaakt van een melding, geeft aan of het niet wordt beïnvloed</span><span class="sxs-lookup"><span data-stu-id="615cc-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="615cc-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-123">string</span></span> | <span data-ttu-id="615cc-124">Geeft aan of de entiteit de bron is of de bestemming van een netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="615cc-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="615cc-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-125">string</span></span> | <span data-ttu-id="615cc-126">De naam van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="615cc-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="615cc-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-127">string</span></span> | <span data-ttu-id="615cc-128">Map met het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="615cc-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="615cc-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-129">string</span></span> | <span data-ttu-id="615cc-130">SHA-1 van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="615cc-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="615cc-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-131">string</span></span> | <span data-ttu-id="615cc-132">SHA-256 van het bestand waarop de opgenomen actie is toegepast.</span><span class="sxs-lookup"><span data-stu-id="615cc-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="615cc-133">Dit veld wordt meestal niet ingevuld, met behulp van de SHA1-kolom.</span><span class="sxs-lookup"><span data-stu-id="615cc-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="615cc-134">int</span><span class="sxs-lookup"><span data-stu-id="615cc-134">int</span></span> | <span data-ttu-id="615cc-135">Bestandsgrootte in bytes</span><span class="sxs-lookup"><span data-stu-id="615cc-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="615cc-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-136">string</span></span> | <span data-ttu-id="615cc-137">De familie van de malware waarmee het verdachte of schadelijke bestand of proces is geclassificeerd.</span><span class="sxs-lookup"><span data-stu-id="615cc-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="615cc-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-138">string</span></span> | <span data-ttu-id="615cc-139">IP-adres waarop verbinding is gemaakt</span><span class="sxs-lookup"><span data-stu-id="615cc-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="615cc-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-140">string</span></span> | <span data-ttu-id="615cc-141">URL of FQDN (Fully Qualified Domain Name) waarmee verbinding is gemaakt</span><span class="sxs-lookup"><span data-stu-id="615cc-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="615cc-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-142">string</span></span> | <span data-ttu-id="615cc-143">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="615cc-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="615cc-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-144">string</span></span> | <span data-ttu-id="615cc-145">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="615cc-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="615cc-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-146">string</span></span> | <span data-ttu-id="615cc-147">SID (Security Identifier) van het account</span><span class="sxs-lookup"><span data-stu-id="615cc-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="615cc-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-148">string</span></span> | <span data-ttu-id="615cc-149">Unieke id voor het account in azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="615cc-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="615cc-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-150">string</span></span> | <span data-ttu-id="615cc-151">Unieke id van het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="615cc-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="615cc-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-152">string</span></span> | <span data-ttu-id="615cc-153">FQDN-naam (Fully Qualified Domain Name) van de computer</span><span class="sxs-lookup"><span data-stu-id="615cc-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="615cc-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-154">string</span></span> | <span data-ttu-id="615cc-155">Het IP-adres dat is toegewezen aan het lokale apparaat dat wordt gebruikt tijdens de communicatie</span><span class="sxs-lookup"><span data-stu-id="615cc-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="615cc-156">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-156">string</span></span> | <span data-ttu-id="615cc-157">Unieke id voor de e-mail, gegenereerd door Office 365</span><span class="sxs-lookup"><span data-stu-id="615cc-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="615cc-158">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-158">string</span></span> | <span data-ttu-id="615cc-159">Onderwerp van de e-mail</span><span class="sxs-lookup"><span data-stu-id="615cc-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="615cc-160">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-160">string</span></span> | <span data-ttu-id="615cc-161">Unieke id voor de toepassing</span><span class="sxs-lookup"><span data-stu-id="615cc-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="615cc-162">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-162">string</span></span> | <span data-ttu-id="615cc-163">De toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="615cc-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="615cc-164">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-164">string</span></span> | <span data-ttu-id="615cc-165">Opdrachtregel voor het maken van het nieuwe proces</span><span class="sxs-lookup"><span data-stu-id="615cc-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="615cc-166">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="615cc-166">string</span></span> | <span data-ttu-id="615cc-167">Aanvullende informatie over de gebeurtenis in de JSON-matrix indeling</span><span class="sxs-lookup"><span data-stu-id="615cc-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="615cc-168">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="615cc-168">Related topics</span></span>
- [<span data-ttu-id="615cc-169">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="615cc-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="615cc-170">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="615cc-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="615cc-171">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="615cc-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="615cc-172">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="615cc-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="615cc-173">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="615cc-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="615cc-174">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="615cc-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
