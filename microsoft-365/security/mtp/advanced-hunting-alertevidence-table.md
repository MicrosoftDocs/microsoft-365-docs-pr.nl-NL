---
title: AlertEvidence tabel in het geavanceerde jachtschema
description: Meer informatie over bestands-, netwerkadres-, gebruikers- of apparaatgegevens die zijn gekoppeld aan gegenereerde waarschuwingen in de tabel AlertEvidence van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, AlertInfo, alert, entiteiten, bewijs, bestand, IP-adres, apparaat, machine, gebruiker, account
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
ms.openlocfilehash: 1a58d1e5db2ea8689d4909e6e9c47b08a6e94d34
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929148"
---
# <a name="alertevidence"></a><span data-ttu-id="e5a72-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="e5a72-104">AlertEvidence</span></span>

<span data-ttu-id="e5a72-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e5a72-105">**Applies to:**</span></span>
- <span data-ttu-id="e5a72-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="e5a72-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="e5a72-107">De `AlertEvidence` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over verschillende entiteiten - bestanden, IP-adressen, URL's, gebruikers of apparaten - die zijn gekoppeld aan waarschuwingen van Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security en ATP Azure.</span><span class="sxs-lookup"><span data-stu-id="e5a72-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities — files, IP addresses, URLs, users, or devices — associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="e5a72-108">Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="e5a72-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="e5a72-109">Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="e5a72-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e5a72-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="e5a72-110">Column name</span></span> | <span data-ttu-id="e5a72-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="e5a72-111">Data type</span></span> | <span data-ttu-id="e5a72-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e5a72-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e5a72-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="e5a72-113">datetime</span></span> | <span data-ttu-id="e5a72-114">Datum en tijdstip waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="e5a72-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="e5a72-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e5a72-115">string</span></span> | <span data-ttu-id="e5a72-116">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="e5a72-116">Unique identifier for the alert</span></span> |
| `EntityType` | <span data-ttu-id="e5a72-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e5a72-117">string</span></span> | <span data-ttu-id="e5a72-118">Type object, zoals een bestand, een proces, een apparaat of een gebruiker</span><span class="sxs-lookup"><span data-stu-id="e5a72-118">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="e5a72-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e5a72-119">string</span></span> | <span data-ttu-id="e5a72-120">Hoe de entiteit betrokken is bij een waarschuwing, die aangeeft of deze wordt beïnvloed of slechts gerelateerd is</span><span class="sxs-lookup"><span data-stu-id="e5a72-120">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `SHA1` | <span data-ttu-id="e5a72-121">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e5a72-121">string</span></span> | <span data-ttu-id="e5a72-122">SHA-1 van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="e5a72-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="e5a72-123">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e5a72-123">string</span></span> | <span data-ttu-id="e5a72-124">SHA-256 van het bestand waarop de opgenomen actie is toegepast.</span><span class="sxs-lookup"><span data-stu-id="e5a72-124">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="e5a72-125">Dit veld is meestal niet gevuld: gebruik de SHA1-kolom indien beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e5a72-125">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `RemoteIP` | <span data-ttu-id="e5a72-126">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e5a72-126">string</span></span> | <span data-ttu-id="e5a72-127">IP-adres dat werd verbonden met</span><span class="sxs-lookup"><span data-stu-id="e5a72-127">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="e5a72-128">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e5a72-128">string</span></span> | <span data-ttu-id="e5a72-129">URL of volledig gekwalificeerde domeinnaam (FQDN) die werd verbonden met</span><span class="sxs-lookup"><span data-stu-id="e5a72-129">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="e5a72-130">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e5a72-130">string</span></span> | <span data-ttu-id="e5a72-131">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="e5a72-131">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="e5a72-132">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e5a72-132">string</span></span> | <span data-ttu-id="e5a72-133">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="e5a72-133">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="e5a72-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e5a72-134">string</span></span> | <span data-ttu-id="e5a72-135">Beveiligings-id (SID) van het account</span><span class="sxs-lookup"><span data-stu-id="e5a72-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="e5a72-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e5a72-136">string</span></span> | <span data-ttu-id="e5a72-137">Unieke id voor het account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="e5a72-137">Unique identifier for the account in Azure AD</span></span> |
| `DeviceId` | <span data-ttu-id="e5a72-138">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e5a72-138">string</span></span> | <span data-ttu-id="e5a72-139">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="e5a72-139">Unique identifier for the machine in the service</span></span> |
| `ThreatFamily` | <span data-ttu-id="e5a72-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e5a72-140">string</span></span> | <span data-ttu-id="e5a72-141">Malware familie dat de verdachte of kwaadaardige bestand of proces is geclassificeerd onder</span><span class="sxs-lookup"><span data-stu-id="e5a72-141">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `EvidenceDirection` | <span data-ttu-id="e5a72-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e5a72-142">string</span></span> | <span data-ttu-id="e5a72-143">Geeft aan of de entiteit de bron of de bestemming van een netwerkverbinding is</span><span class="sxs-lookup"><span data-stu-id="e5a72-143">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `AdditionalFields` | <span data-ttu-id="e5a72-144">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e5a72-144">string</span></span> | <span data-ttu-id="e5a72-145">Aanvullende informatie over de gebeurtenis in JSON-arrayindeling</span><span class="sxs-lookup"><span data-stu-id="e5a72-145">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e5a72-146">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e5a72-146">Related topics</span></span>
- [<span data-ttu-id="e5a72-147">Proactief op zoek naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="e5a72-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e5a72-148">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="e5a72-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e5a72-149">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="e5a72-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e5a72-150">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="e5a72-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e5a72-151">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="e5a72-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e5a72-152">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="e5a72-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
