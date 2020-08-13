---
title: AlertEvidence-tabel in het geavanceerde jacht schema
description: Meer informatie over bestands-, netwerkadres-, gebruikers-of apparaatgegevens die zijn gekoppeld aan gegenereerde waarschuwingen in de tabel AlertEvidence van het schema geavanceerde jacht
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 8fc713db33b0e40adcd0975d26c10daece636ab1
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649509"
---
# <a name="alertevidence"></a><span data-ttu-id="7b61f-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="7b61f-104">AlertEvidence</span></span>

<span data-ttu-id="7b61f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7b61f-105">**Applies to:**</span></span>
- <span data-ttu-id="7b61f-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7b61f-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="7b61f-107">De `AlertEvidence` tabel in het [Geavanceerde opjacht](advanced-hunting-overview.md) -schema bevat informatie over diverse entiteiten, zoals bestanden, IP-adressen, url's, gebruikers of apparaten, gekoppeld aan waarschuwingen uit Microsoft Defender atp, Office 365 ATP, Microsoft Cloud app Security en Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="7b61f-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities — files, IP addresses, URLs, users, or devices — associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="7b61f-108">Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="7b61f-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="7b61f-109">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="7b61f-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7b61f-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="7b61f-110">Column name</span></span> | <span data-ttu-id="7b61f-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="7b61f-111">Data type</span></span> | <span data-ttu-id="7b61f-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="7b61f-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7b61f-113">tijd</span><span class="sxs-lookup"><span data-stu-id="7b61f-113">datetime</span></span> | <span data-ttu-id="7b61f-114">De datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="7b61f-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="7b61f-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7b61f-115">string</span></span> | <span data-ttu-id="7b61f-116">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="7b61f-116">Unique identifier for the alert</span></span> |
| `EntityType` | <span data-ttu-id="7b61f-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7b61f-117">string</span></span> | <span data-ttu-id="7b61f-118">Type object, zoals een bestand, een proces, een apparaat of een gebruiker</span><span class="sxs-lookup"><span data-stu-id="7b61f-118">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="7b61f-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7b61f-119">string</span></span> | <span data-ttu-id="7b61f-120">Hoe de entiteit deel uitmaakt van een melding, geeft aan of het niet wordt beïnvloed</span><span class="sxs-lookup"><span data-stu-id="7b61f-120">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `SHA1` | <span data-ttu-id="7b61f-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7b61f-121">string</span></span> | <span data-ttu-id="7b61f-122">SHA-1 van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="7b61f-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="7b61f-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7b61f-123">string</span></span> | <span data-ttu-id="7b61f-124">SHA-256 van het bestand waarop de opgenomen actie is toegepast.</span><span class="sxs-lookup"><span data-stu-id="7b61f-124">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="7b61f-125">Dit veld wordt meestal niet ingevuld, met behulp van de SHA1-kolom.</span><span class="sxs-lookup"><span data-stu-id="7b61f-125">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `RemoteIP` | <span data-ttu-id="7b61f-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7b61f-126">string</span></span> | <span data-ttu-id="7b61f-127">IP-adres waarop verbinding is gemaakt</span><span class="sxs-lookup"><span data-stu-id="7b61f-127">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="7b61f-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7b61f-128">string</span></span> | <span data-ttu-id="7b61f-129">URL of FQDN (Fully Qualified Domain Name) waarmee verbinding is gemaakt</span><span class="sxs-lookup"><span data-stu-id="7b61f-129">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="7b61f-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7b61f-130">string</span></span> | <span data-ttu-id="7b61f-131">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="7b61f-131">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="7b61f-132">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7b61f-132">string</span></span> | <span data-ttu-id="7b61f-133">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="7b61f-133">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="7b61f-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7b61f-134">string</span></span> | <span data-ttu-id="7b61f-135">SID (Security Identifier) van het account</span><span class="sxs-lookup"><span data-stu-id="7b61f-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="7b61f-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7b61f-136">string</span></span> | <span data-ttu-id="7b61f-137">Unieke id voor het account in azure AD</span><span class="sxs-lookup"><span data-stu-id="7b61f-137">Unique identifier for the account in Azure AD</span></span> |
| `DeviceId` | <span data-ttu-id="7b61f-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7b61f-138">string</span></span> | <span data-ttu-id="7b61f-139">Unieke id voor de computer in de service</span><span class="sxs-lookup"><span data-stu-id="7b61f-139">Unique identifier for the machine in the service</span></span> |
| `ThreatFamily` | <span data-ttu-id="7b61f-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7b61f-140">string</span></span> | <span data-ttu-id="7b61f-141">De familie van de malware waarmee het verdachte of schadelijke bestand of proces is geclassificeerd.</span><span class="sxs-lookup"><span data-stu-id="7b61f-141">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `EvidenceDirection` | <span data-ttu-id="7b61f-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7b61f-142">string</span></span> | <span data-ttu-id="7b61f-143">Geeft aan of de entiteit de bron is of de bestemming van een netwerkverbinding</span><span class="sxs-lookup"><span data-stu-id="7b61f-143">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `AdditionalFields` | <span data-ttu-id="7b61f-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7b61f-144">string</span></span> | <span data-ttu-id="7b61f-145">Aanvullende informatie over de gebeurtenis in de JSON-matrix indeling</span><span class="sxs-lookup"><span data-stu-id="7b61f-145">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7b61f-146">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7b61f-146">Related topics</span></span>
- [<span data-ttu-id="7b61f-147">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="7b61f-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7b61f-148">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="7b61f-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7b61f-149">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="7b61f-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7b61f-150">Jacht op apparaten, e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="7b61f-150">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7b61f-151">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="7b61f-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7b61f-152">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="7b61f-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
