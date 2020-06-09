---
title: AlertEvidence tabel in het geavanceerde jachtschema
description: Meer informatie over bestands-, netwerkadres-, gebruikers- of apparaatgegevens die zijn gekoppeld aan gegenereerde waarschuwingen in de tabel AlertEvidence van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, AlertInfo, alert, entiteiten, bewijs, bestand, IP-adres, apparaat, machine, gebruiker, account
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
ms.openlocfilehash: da6e84725aa391e4cb6056fadd327fdba2436214
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617084"
---
# <a name="alertevidence"></a><span data-ttu-id="70d8d-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="70d8d-104">AlertEvidence</span></span>

<span data-ttu-id="70d8d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="70d8d-105">**Applies to:**</span></span>
- <span data-ttu-id="70d8d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="70d8d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="70d8d-107">De `AlertEvidence` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over verschillende entiteiten — bestanden, IP-adressen, URL's, gebruikers of apparaten — die zijn gekoppeld aan waarschuwingen van Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security en Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="70d8d-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities — files, IP addresses, URLs, users, or devices — associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="70d8d-108">Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="70d8d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="70d8d-109">Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.</span><span class="sxs-lookup"><span data-stu-id="70d8d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="70d8d-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="70d8d-110">Column name</span></span> | <span data-ttu-id="70d8d-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="70d8d-111">Data type</span></span> | <span data-ttu-id="70d8d-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="70d8d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="70d8d-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="70d8d-113">datetime</span></span> | <span data-ttu-id="70d8d-114">Datum en tijdstip waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="70d8d-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="70d8d-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="70d8d-115">string</span></span> | <span data-ttu-id="70d8d-116">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="70d8d-116">Unique identifier for the alert</span></span> |
| `EntityType` | <span data-ttu-id="70d8d-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="70d8d-117">string</span></span> | <span data-ttu-id="70d8d-118">Type object, zoals een bestand, een proces, een apparaat of een gebruiker</span><span class="sxs-lookup"><span data-stu-id="70d8d-118">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="70d8d-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="70d8d-119">string</span></span> | <span data-ttu-id="70d8d-120">Hoe de entiteit betrokken is bij een waarschuwing, die aangeeft of deze is beïnvloed of alleen</span><span class="sxs-lookup"><span data-stu-id="70d8d-120">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `SHA1` | <span data-ttu-id="70d8d-121">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="70d8d-121">string</span></span> | <span data-ttu-id="70d8d-122">SHA-1 van het bestand waarop de geregistreerde actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="70d8d-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="70d8d-123">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="70d8d-123">string</span></span> | <span data-ttu-id="70d8d-124">SHA-256 van het bestand waarop de geregistreerde actie is toegepast.</span><span class="sxs-lookup"><span data-stu-id="70d8d-124">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="70d8d-125">Dit veld wordt meestal niet ingevuld - gebruik de SHA1-kolom indien beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="70d8d-125">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `RemoteIP` | <span data-ttu-id="70d8d-126">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="70d8d-126">string</span></span> | <span data-ttu-id="70d8d-127">IP-adres waarmee werd verbonden</span><span class="sxs-lookup"><span data-stu-id="70d8d-127">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="70d8d-128">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="70d8d-128">string</span></span> | <span data-ttu-id="70d8d-129">URL of volledig gekwalificeerde domeinnaam (FQDN) die werd verbonden met</span><span class="sxs-lookup"><span data-stu-id="70d8d-129">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="70d8d-130">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="70d8d-130">string</span></span> | <span data-ttu-id="70d8d-131">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="70d8d-131">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="70d8d-132">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="70d8d-132">string</span></span> | <span data-ttu-id="70d8d-133">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="70d8d-133">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="70d8d-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="70d8d-134">string</span></span> | <span data-ttu-id="70d8d-135">Beveiligings-id (SID) van het account</span><span class="sxs-lookup"><span data-stu-id="70d8d-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="70d8d-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="70d8d-136">string</span></span> | <span data-ttu-id="70d8d-137">Unieke id voor het account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="70d8d-137">Unique identifier for the account in Azure AD</span></span> |
| `DeviceId` | <span data-ttu-id="70d8d-138">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="70d8d-138">string</span></span> | <span data-ttu-id="70d8d-139">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="70d8d-139">Unique identifier for the machine in the service</span></span> |
| `ThreatFamily` | <span data-ttu-id="70d8d-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="70d8d-140">string</span></span> | <span data-ttu-id="70d8d-141">Malwarefamilie waar het verdachte of kwaadwillige bestand of proces onder is ingedeeld</span><span class="sxs-lookup"><span data-stu-id="70d8d-141">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `EvidenceDirection` | <span data-ttu-id="70d8d-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="70d8d-142">string</span></span> | <span data-ttu-id="70d8d-143">Geeft aan of de entiteit de bron of de bestemming van een netwerkverbinding is</span><span class="sxs-lookup"><span data-stu-id="70d8d-143">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `AdditionalFields` | <span data-ttu-id="70d8d-144">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="70d8d-144">string</span></span> | <span data-ttu-id="70d8d-145">Aanvullende informatie over de gebeurtenis in de JSON-arrayindeling</span><span class="sxs-lookup"><span data-stu-id="70d8d-145">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="70d8d-146">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="70d8d-146">Related topics</span></span>
- [<span data-ttu-id="70d8d-147">Proactief op zoek naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="70d8d-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="70d8d-148">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="70d8d-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="70d8d-149">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="70d8d-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="70d8d-150">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="70d8d-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="70d8d-151">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="70d8d-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="70d8d-152">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="70d8d-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
