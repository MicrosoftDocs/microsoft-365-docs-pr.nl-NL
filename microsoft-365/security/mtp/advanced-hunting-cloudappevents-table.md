---
title: Tabel CloudAppEvents in het geavanceerde schema voor zoeken
description: Meer informatie over gebeurtenissen in cloud-apps en -services in de tabel CloudAppEvents van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928451"
---
# <a name="cloudappevents"></a><span data-ttu-id="0be4d-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="0be4d-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0be4d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0be4d-105">**Applies to:**</span></span>
- <span data-ttu-id="0be4d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0be4d-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="0be4d-107">De tabel in het geavanceerde schema voor zoeken is momenteel beschikbaar in de preview-versie en bevat informatie over activiteiten in verschillende cloud-apps en -services, met name `CloudAppEvents` Microsoft Teams en Exchange Online. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0be4d-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="0be4d-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="0be4d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="0be4d-109">Deze tabel wordt uitgebreid met meer activiteiten die worden gecontroleerd door Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="0be4d-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="0be4d-110">Uiteindelijk bevat deze tabel bestandsactiviteit die momenteel is opgeslagen in de [tabel AppFileEvents.](advanced-hunting-appfileevents-table.md)</span><span class="sxs-lookup"><span data-stu-id="0be4d-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="0be4d-111">Microsoft begeleidt u wanneer er meer gegevens naar deze tabel worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="0be4d-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="0be4d-112">Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="0be4d-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0be4d-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="0be4d-113">Column name</span></span> | <span data-ttu-id="0be4d-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="0be4d-114">Data type</span></span> | <span data-ttu-id="0be4d-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="0be4d-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0be4d-116">datetime</span><span class="sxs-lookup"><span data-stu-id="0be4d-116">datetime</span></span> | <span data-ttu-id="0be4d-117">Datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="0be4d-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="0be4d-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-118">string</span></span> | <span data-ttu-id="0be4d-119">Het type activiteit dat de gebeurtenis heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="0be4d-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="0be4d-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-120">string</span></span> | <span data-ttu-id="0be4d-121">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="0be4d-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="0be4d-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-122">string</span></span> | <span data-ttu-id="0be4d-123">Unieke id voor de toepassing</span><span class="sxs-lookup"><span data-stu-id="0be4d-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="0be4d-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-124">string</span></span> | <span data-ttu-id="0be4d-125">Unieke id voor het account in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0be4d-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="0be4d-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-126">string</span></span> | <span data-ttu-id="0be4d-127">De naam van de accountgebruiker die wordt weergegeven in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="0be4d-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="0be4d-128">Meestal een combinatie van een bepaalde of voornaam, een middelste start en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="0be4d-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="0be4d-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-129">string</span></span> | <span data-ttu-id="0be4d-130">Geeft aan of de activiteit is uitgevoerd door een beheerder</span><span class="sxs-lookup"><span data-stu-id="0be4d-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="0be4d-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-131">string</span></span> | <span data-ttu-id="0be4d-132">Type apparaat op basis van doel en functionaliteit, zoals 'Netwerkapparaat', 'Werkstation', 'Server', 'Mobiel', 'Gamingconsole' of 'Printer'</span><span class="sxs-lookup"><span data-stu-id="0be4d-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="0be4d-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-133">string</span></span> | <span data-ttu-id="0be4d-134">Platform van het besturingssysteem dat wordt uitgevoerd op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="0be4d-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="0be4d-135">Deze kolom geeft specifieke besturingssystemen aan, inclusief variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="0be4d-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="0be4d-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-136">string</span></span> | <span data-ttu-id="0be4d-137">IP-adres dat aan het eindpunt is toegewezen en dat is gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="0be4d-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="0be4d-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-138">string</span></span> | <span data-ttu-id="0be4d-139">Geeft aan of het IP-adres behoort tot een bekende anonieme proxy</span><span class="sxs-lookup"><span data-stu-id="0be4d-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="0be4d-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-140">string</span></span> | <span data-ttu-id="0be4d-141">Tweeletterige code die het land aangeeft waar het IP-adres van de client geo-toegewezen is</span><span class="sxs-lookup"><span data-stu-id="0be4d-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="0be4d-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-142">string</span></span> | <span data-ttu-id="0be4d-143">Plaats waar het IP-adres van de client geolocatie is</span><span class="sxs-lookup"><span data-stu-id="0be4d-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="0be4d-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-144">string</span></span> | <span data-ttu-id="0be4d-145">Internetprovider (ISP) die is gekoppeld aan het IP-adres</span><span class="sxs-lookup"><span data-stu-id="0be4d-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="0be4d-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-146">string</span></span> | <span data-ttu-id="0be4d-147">Gegevens van de gebruikersagent vanuit de webbrowser of een andere clienttoepassing</span><span class="sxs-lookup"><span data-stu-id="0be4d-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="0be4d-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-148">string</span></span> | <span data-ttu-id="0be4d-149">Het type activiteit dat de gebeurtenis heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="0be4d-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="0be4d-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-150">string</span></span> | <span data-ttu-id="0be4d-151">Lijst met objecten, zoals bestanden of mappen, die zijn betrokken bij de vastgelegde activiteit</span><span class="sxs-lookup"><span data-stu-id="0be4d-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="0be4d-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-152">string</span></span> | <span data-ttu-id="0be4d-153">De naam van het object waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="0be4d-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="0be4d-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-154">string</span></span> | <span data-ttu-id="0be4d-155">Het type object, zoals een bestand of map, waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="0be4d-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="0be4d-156">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-156">string</span></span> | <span data-ttu-id="0be4d-157">Unieke id van het object waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="0be4d-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="0be4d-158">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-158">string</span></span> | <span data-ttu-id="0be4d-159">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="0be4d-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="0be4d-160">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-160">string</span></span> | <span data-ttu-id="0be4d-161">Onbewerkte gebeurtenisgegevens uit de brontoepassing of service in JSON-indeling</span><span class="sxs-lookup"><span data-stu-id="0be4d-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="0be4d-162">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0be4d-162">string</span></span> | <span data-ttu-id="0be4d-163">Aanvullende informatie over de entiteit of gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="0be4d-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0be4d-164">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0be4d-164">Related topics</span></span>
- [<span data-ttu-id="0be4d-165">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="0be4d-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0be4d-166">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="0be4d-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0be4d-167">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="0be4d-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0be4d-168">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="0be4d-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0be4d-169">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="0be4d-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0be4d-170">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="0be4d-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
