---
title: CloudAppEvents-tabel in het geavanceerde jacht schema
description: Meer informatie over gebeurtenissen van Cloud-apps en-services in de tabel CloudAppEvents van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, CloudAppEvents, Cloud app Security, MCAS
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
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087764"
---
# <a name="cloudappevents"></a><span data-ttu-id="7fb26-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="7fb26-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7fb26-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7fb26-105">**Applies to:**</span></span>
- <span data-ttu-id="7fb26-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fb26-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="7fb26-107">Op dit moment is er een voorvertoning, de `CloudAppEvents` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) schema bevat informatie over activiteiten in diverse Cloud-apps en-services, met name Microsoft teams en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7fb26-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="7fb26-108">Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="7fb26-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="7fb26-109">Deze tabel wordt uitgebreid met meer activiteiten gecontroleerd op de beveiliging van de Microsoft Cloud-app.</span><span class="sxs-lookup"><span data-stu-id="7fb26-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="7fb26-110">Deze tabel bevat uiteindelijk ook Bestandsactiviteit die is opgeslagen in de tabel [AppFileEvents](advanced-hunting-appfileevents-table.md) .</span><span class="sxs-lookup"><span data-stu-id="7fb26-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="7fb26-111">Microsoft biedt extra richtlijnen, zodat meer gegevens naar deze tabel worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="7fb26-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="7fb26-112">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="7fb26-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7fb26-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="7fb26-113">Column name</span></span> | <span data-ttu-id="7fb26-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="7fb26-114">Data type</span></span> | <span data-ttu-id="7fb26-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="7fb26-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7fb26-116">tijd</span><span class="sxs-lookup"><span data-stu-id="7fb26-116">datetime</span></span> | <span data-ttu-id="7fb26-117">De datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="7fb26-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="7fb26-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-118">string</span></span> | <span data-ttu-id="7fb26-119">Type activiteit waarmee de gebeurtenis wordt geactiveerd</span><span class="sxs-lookup"><span data-stu-id="7fb26-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="7fb26-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-120">string</span></span> | <span data-ttu-id="7fb26-121">De toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="7fb26-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="7fb26-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-122">string</span></span> | <span data-ttu-id="7fb26-123">Unieke id voor de toepassing</span><span class="sxs-lookup"><span data-stu-id="7fb26-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="7fb26-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-124">string</span></span> | <span data-ttu-id="7fb26-125">Unieke id voor het account in azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7fb26-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="7fb26-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-126">string</span></span> | <span data-ttu-id="7fb26-127">Naam van de account gebruiker die in het adresboek wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7fb26-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="7fb26-128">Meestal een combinatie van een bepaalde of voornaam, een tweede opening en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="7fb26-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="7fb26-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-129">string</span></span> | <span data-ttu-id="7fb26-130">Geeft aan of de activiteit is uitgevoerd door een beheerder</span><span class="sxs-lookup"><span data-stu-id="7fb26-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="7fb26-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-131">string</span></span> | <span data-ttu-id="7fb26-132">Type apparaat op basis van doel en functionaliteit, zoals ' netwerkapparaat ', ' werkstation ', ' server ', ' Mobiel ', ' gaming console ' of ' printer '</span><span class="sxs-lookup"><span data-stu-id="7fb26-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="7fb26-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-133">string</span></span> | <span data-ttu-id="7fb26-134">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="7fb26-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="7fb26-135">In deze kolom worden specifieke besturingssystemen aangegeven, waaronder variaties in dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="7fb26-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="7fb26-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-136">string</span></span> | <span data-ttu-id="7fb26-137">Het IP-adres dat is toegewezen aan het eindpunt en die wordt gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="7fb26-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="7fb26-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-138">string</span></span> | <span data-ttu-id="7fb26-139">Geeft aan of het IP-adres bij een bekende anonieme proxy behoort</span><span class="sxs-lookup"><span data-stu-id="7fb26-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="7fb26-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-140">string</span></span> | <span data-ttu-id="7fb26-141">Tweeletterige code die het land aangeeft waarin het IP-adres van de client geolocatie is</span><span class="sxs-lookup"><span data-stu-id="7fb26-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="7fb26-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-142">string</span></span> | <span data-ttu-id="7fb26-143">Plaats waar het IP-adres van de client geolocatie is</span><span class="sxs-lookup"><span data-stu-id="7fb26-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="7fb26-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-144">string</span></span> | <span data-ttu-id="7fb26-145">Internetprovider (ISP) die is gekoppeld aan het IP-adres</span><span class="sxs-lookup"><span data-stu-id="7fb26-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="7fb26-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-146">string</span></span> | <span data-ttu-id="7fb26-147">Gegevens van de gebruikersagent van de webbrowser of een andere clienttoepassing</span><span class="sxs-lookup"><span data-stu-id="7fb26-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="7fb26-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-148">string</span></span> | <span data-ttu-id="7fb26-149">Type activiteit waarmee de gebeurtenis wordt geactiveerd</span><span class="sxs-lookup"><span data-stu-id="7fb26-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="7fb26-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-150">string</span></span> | <span data-ttu-id="7fb26-151">Lijst met objecten, zoals bestanden of mappen, die zijn betrokken bij de opgenomen activiteit</span><span class="sxs-lookup"><span data-stu-id="7fb26-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="7fb26-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-152">string</span></span> | <span data-ttu-id="7fb26-153">Naam van het object waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="7fb26-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="7fb26-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-154">string</span></span> | <span data-ttu-id="7fb26-155">Type object, zoals een bestand of een map, waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="7fb26-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="7fb26-156">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-156">string</span></span> | <span data-ttu-id="7fb26-157">Unieke id van het object waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="7fb26-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="7fb26-158">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-158">string</span></span> | <span data-ttu-id="7fb26-159">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="7fb26-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="7fb26-160">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-160">string</span></span> | <span data-ttu-id="7fb26-161">Gegevens van onbewerkte gebeurtenissen uit de brontoepassing of service in de JSON-indeling</span><span class="sxs-lookup"><span data-stu-id="7fb26-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="7fb26-162">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7fb26-162">string</span></span> | <span data-ttu-id="7fb26-163">Aanvullende informatie over de entiteit of gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="7fb26-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7fb26-164">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7fb26-164">Related topics</span></span>
- [<span data-ttu-id="7fb26-165">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="7fb26-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7fb26-166">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="7fb26-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7fb26-167">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="7fb26-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7fb26-168">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="7fb26-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7fb26-169">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="7fb26-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7fb26-170">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="7fb26-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
