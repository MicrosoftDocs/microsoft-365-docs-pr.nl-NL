---
title: CloudAppEvents-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over gebeurtenissen uit cloud-apps en -services in de tabel CloudAppEvents van het geavanceerde schema voor het zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, CloudAppEvents, Cloud App Security, MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 2aa592e70bce7bb469f851bedc542ee58cac0037
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498666"
---
# <a name="cloudappevents"></a><span data-ttu-id="da55b-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="da55b-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="da55b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="da55b-105">**Applies to:**</span></span>
- <span data-ttu-id="da55b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da55b-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="da55b-107">De tabel in het geavanceerde schema bevat informatie over activiteiten in verschillende cloud-apps en -services die worden bestreken door Microsoft Cloud App Security, met name `CloudAppEvents` Dropbox, Exchange Online, [](advanced-hunting-overview.md) OneDrive, Microsoft Teams en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="da55b-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security, specifically Dropbox, Exchange Online, OneDrive, Microsoft Teams, and SharePoint.</span></span> <span data-ttu-id="da55b-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="da55b-108">Use this reference to construct queries that return information from this table.</span></span>

>[!IMPORTANT]
><span data-ttu-id="da55b-109">Deze tabel bevat informatie die beschikbaar was in de `AppFileEvents` tabel.</span><span class="sxs-lookup"><span data-stu-id="da55b-109">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="da55b-110">Vanaf 7 maart 2021 moeten gebruikers die op zoek zijn naar bestandsgerelateerde activiteiten in cloudservices op en na deze datum, de tabel `CloudAppEvents` gebruiken.</span><span class="sxs-lookup"><span data-stu-id="da55b-110">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="da55b-111">Zoek naar query's en aangepaste detectieregels die de tabel nog steeds gebruiken en bewerk ze om `AppFileEvents` de tabel te `CloudAppEvents` gebruiken.</span><span class="sxs-lookup"><span data-stu-id="da55b-111">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="da55b-112">Meer richtlijnen over het converteren van beïnvloede query's vindt u in [Hunt voor cloud-app-activiteiten met microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span><span class="sxs-lookup"><span data-stu-id="da55b-112">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="da55b-113">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="da55b-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="da55b-114">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="da55b-114">Column name</span></span> | <span data-ttu-id="da55b-115">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="da55b-115">Data type</span></span> | <span data-ttu-id="da55b-116">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="da55b-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="da55b-117">datetime</span><span class="sxs-lookup"><span data-stu-id="da55b-117">datetime</span></span> | <span data-ttu-id="da55b-118">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="da55b-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="da55b-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-119">string</span></span> | <span data-ttu-id="da55b-120">Type activiteit dat de gebeurtenis heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="da55b-120">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="da55b-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-121">string</span></span> | <span data-ttu-id="da55b-122">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="da55b-122">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="da55b-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-123">string</span></span> | <span data-ttu-id="da55b-124">Unieke id voor de toepassing</span><span class="sxs-lookup"><span data-stu-id="da55b-124">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="da55b-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-125">string</span></span> | <span data-ttu-id="da55b-126">Unieke id voor het account in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="da55b-126">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="da55b-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-127">string</span></span> | <span data-ttu-id="da55b-128">Naam van de accountgebruiker die wordt weergegeven in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="da55b-128">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="da55b-129">Meestal een combinatie van een bepaalde of voornaam, een middelste initiatie en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="da55b-129">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="da55b-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-130">string</span></span> | <span data-ttu-id="da55b-131">Geeft aan of de activiteit is uitgevoerd door een beheerder</span><span class="sxs-lookup"><span data-stu-id="da55b-131">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="da55b-132">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-132">string</span></span> | <span data-ttu-id="da55b-133">Type apparaat op basis van doel en functionaliteit, zoals 'Netwerkapparaat', 'Workstation', 'Server', 'Mobile', 'Gaming console' of 'Printer'</span><span class="sxs-lookup"><span data-stu-id="da55b-133">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="da55b-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-134">string</span></span> | <span data-ttu-id="da55b-135">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="da55b-135">Platform of the operating system running on the device.</span></span> <span data-ttu-id="da55b-136">Deze kolom geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="da55b-136">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="da55b-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-137">string</span></span> | <span data-ttu-id="da55b-138">IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="da55b-138">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="da55b-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-139">string</span></span> | <span data-ttu-id="da55b-140">Geeft aan of het IP-adres behoort tot een bekende anonieme proxy</span><span class="sxs-lookup"><span data-stu-id="da55b-140">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="da55b-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-141">string</span></span> | <span data-ttu-id="da55b-142">Code met twee letters waarmee het land wordt aangegeven waar het IP-adres van de client is geloceerd</span><span class="sxs-lookup"><span data-stu-id="da55b-142">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="da55b-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-143">string</span></span> | <span data-ttu-id="da55b-144">Plaats waar het IP-adres van de client geolocatie is</span><span class="sxs-lookup"><span data-stu-id="da55b-144">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="da55b-145">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-145">string</span></span> | <span data-ttu-id="da55b-146">Internetprovider die is gekoppeld aan het IP-adres</span><span class="sxs-lookup"><span data-stu-id="da55b-146">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="da55b-147">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-147">string</span></span> | <span data-ttu-id="da55b-148">Gebruikersagentgegevens uit de webbrowser of een andere clienttoepassing</span><span class="sxs-lookup"><span data-stu-id="da55b-148">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="da55b-149">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-149">string</span></span> | <span data-ttu-id="da55b-150">Type activiteit dat de gebeurtenis heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="da55b-150">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="da55b-151">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-151">string</span></span> | <span data-ttu-id="da55b-152">Lijst met objecten, zoals bestanden of mappen, die betrokken waren bij de opgenomen activiteit</span><span class="sxs-lookup"><span data-stu-id="da55b-152">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="da55b-153">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-153">string</span></span> | <span data-ttu-id="da55b-154">Naam van het object waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="da55b-154">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="da55b-155">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-155">string</span></span> | <span data-ttu-id="da55b-156">Type object, zoals een bestand of map, waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="da55b-156">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="da55b-157">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-157">string</span></span> | <span data-ttu-id="da55b-158">Unieke id van het object waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="da55b-158">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="da55b-159">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-159">string</span></span> | <span data-ttu-id="da55b-160">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="da55b-160">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="da55b-161">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-161">string</span></span> | <span data-ttu-id="da55b-162">Onbewerkte gebeurtenisgegevens uit de brontoepassing of -service in JSON-indeling</span><span class="sxs-lookup"><span data-stu-id="da55b-162">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="da55b-163">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da55b-163">string</span></span> | <span data-ttu-id="da55b-164">Aanvullende informatie over de entiteit of gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="da55b-164">Additional information about the entity or event</span></span> |


## <a name="related-topics"></a><span data-ttu-id="da55b-165">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="da55b-165">Related topics</span></span>
- [<span data-ttu-id="da55b-166">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="da55b-166">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="da55b-167">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="da55b-167">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="da55b-168">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="da55b-168">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="da55b-169">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="da55b-169">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="da55b-170">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="da55b-170">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="da55b-171">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="da55b-171">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
