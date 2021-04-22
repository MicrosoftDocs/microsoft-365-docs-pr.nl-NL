---
title: CloudAppEvents-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over gebeurtenissen uit cloud-apps en -services in de tabel CloudAppEvents van het geavanceerde schema voor het zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 17f424d368c0df2f07cda41917f005e4163e5750
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935867"
---
# <a name="cloudappevents"></a><span data-ttu-id="9e80d-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="9e80d-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9e80d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9e80d-105">**Applies to:**</span></span>
- <span data-ttu-id="9e80d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e80d-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="9e80d-107">De `CloudAppEvents` tabel in het geavanceerde schema [bevat](advanced-hunting-overview.md) informatie over activiteiten in verschillende cloud-apps en -services die worden gedekt door Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="9e80d-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security.</span></span> <span data-ttu-id="9e80d-108">Voor een volledige lijst gaat u naar [Apps en services die worden behandeld.](#apps-and-services-covered)</span><span class="sxs-lookup"><span data-stu-id="9e80d-108">For a complete list, jump to [Apps and services covered](#apps-and-services-covered).</span></span> <span data-ttu-id="9e80d-109">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="9e80d-109">Use this reference to construct queries that return information from this table.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="9e80d-110">Deze tabel bevat informatie die beschikbaar was in de `AppFileEvents` tabel.</span><span class="sxs-lookup"><span data-stu-id="9e80d-110">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="9e80d-111">Vanaf 7 maart 2021 moeten gebruikers die op zoek zijn naar bestandsgerelateerde activiteiten in cloudservices op en na deze datum, de tabel `CloudAppEvents` gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9e80d-111">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="9e80d-112">Zoek naar query's en aangepaste detectieregels die de tabel nog steeds gebruiken en bewerk ze om `AppFileEvents` de tabel te `CloudAppEvents` gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9e80d-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="9e80d-113">Meer richtlijnen over het converteren van beïnvloede query's vindt u in [Hunt voor cloud-app-activiteiten met microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span><span class="sxs-lookup"><span data-stu-id="9e80d-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="9e80d-114">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="9e80d-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9e80d-115">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="9e80d-115">Column name</span></span> | <span data-ttu-id="9e80d-116">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="9e80d-116">Data type</span></span> | <span data-ttu-id="9e80d-117">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="9e80d-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9e80d-118">datetime</span><span class="sxs-lookup"><span data-stu-id="9e80d-118">datetime</span></span> | <span data-ttu-id="9e80d-119">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="9e80d-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="9e80d-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-120">string</span></span> | <span data-ttu-id="9e80d-121">Type activiteit dat de gebeurtenis heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="9e80d-121">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="9e80d-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-122">string</span></span> | <span data-ttu-id="9e80d-123">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="9e80d-123">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="9e80d-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-124">string</span></span> | <span data-ttu-id="9e80d-125">Unieke id voor de toepassing</span><span class="sxs-lookup"><span data-stu-id="9e80d-125">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="9e80d-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-126">string</span></span> | <span data-ttu-id="9e80d-127">Unieke id voor het account in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9e80d-127">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="9e80d-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-128">string</span></span> | <span data-ttu-id="9e80d-129">Naam van de accountgebruiker die wordt weergegeven in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="9e80d-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="9e80d-130">Meestal een combinatie van een bepaalde of voornaam, een middelste initiatie en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="9e80d-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="9e80d-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-131">string</span></span> | <span data-ttu-id="9e80d-132">Geeft aan of de activiteit is uitgevoerd door een beheerder</span><span class="sxs-lookup"><span data-stu-id="9e80d-132">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="9e80d-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-133">string</span></span> | <span data-ttu-id="9e80d-134">Type apparaat op basis van doel en functionaliteit, zoals 'Netwerkapparaat', 'Workstation', 'Server', 'Mobile', 'Gaming console' of 'Printer'</span><span class="sxs-lookup"><span data-stu-id="9e80d-134">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="9e80d-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-135">string</span></span> | <span data-ttu-id="9e80d-136">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="9e80d-136">Platform of the operating system running on the device.</span></span> <span data-ttu-id="9e80d-137">Deze kolom geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="9e80d-137">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="9e80d-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-138">string</span></span> | <span data-ttu-id="9e80d-139">IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="9e80d-139">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="9e80d-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-140">string</span></span> | <span data-ttu-id="9e80d-141">Geeft aan of het IP-adres behoort tot een bekende anonieme proxy</span><span class="sxs-lookup"><span data-stu-id="9e80d-141">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="9e80d-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-142">string</span></span> | <span data-ttu-id="9e80d-143">Code met twee letters waarmee het land wordt aangegeven waar het IP-adres van de client is geloceerd</span><span class="sxs-lookup"><span data-stu-id="9e80d-143">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="9e80d-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-144">string</span></span> | <span data-ttu-id="9e80d-145">Plaats waar het IP-adres van de client geolocatie is</span><span class="sxs-lookup"><span data-stu-id="9e80d-145">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="9e80d-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-146">string</span></span> | <span data-ttu-id="9e80d-147">Internetprovider die is gekoppeld aan het IP-adres</span><span class="sxs-lookup"><span data-stu-id="9e80d-147">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="9e80d-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-148">string</span></span> | <span data-ttu-id="9e80d-149">Gebruikersagentgegevens uit de webbrowser of een andere clienttoepassing</span><span class="sxs-lookup"><span data-stu-id="9e80d-149">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="9e80d-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-150">string</span></span> | <span data-ttu-id="9e80d-151">Type activiteit dat de gebeurtenis heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="9e80d-151">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="9e80d-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-152">string</span></span> | <span data-ttu-id="9e80d-153">Lijst met objecten, zoals bestanden of mappen, die betrokken waren bij de opgenomen activiteit</span><span class="sxs-lookup"><span data-stu-id="9e80d-153">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="9e80d-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-154">string</span></span> | <span data-ttu-id="9e80d-155">Naam van het object waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="9e80d-155">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="9e80d-156">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-156">string</span></span> | <span data-ttu-id="9e80d-157">Type object, zoals een bestand of map, waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="9e80d-157">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="9e80d-158">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-158">string</span></span> | <span data-ttu-id="9e80d-159">Unieke id van het object waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="9e80d-159">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="9e80d-160">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-160">string</span></span> | <span data-ttu-id="9e80d-161">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="9e80d-161">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="9e80d-162">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-162">string</span></span> | <span data-ttu-id="9e80d-163">Onbewerkte gebeurtenisgegevens uit de brontoepassing of -service in JSON-indeling</span><span class="sxs-lookup"><span data-stu-id="9e80d-163">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="9e80d-164">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e80d-164">string</span></span> | <span data-ttu-id="9e80d-165">Aanvullende informatie over de entiteit of gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="9e80d-165">Additional information about the entity or event</span></span> |

## <a name="apps-and-services-covered"></a><span data-ttu-id="9e80d-166">Apps en services die worden behandeld</span><span class="sxs-lookup"><span data-stu-id="9e80d-166">Apps and services covered</span></span>

- <span data-ttu-id="9e80d-167">Dropbox</span><span class="sxs-lookup"><span data-stu-id="9e80d-167">Dropbox</span></span>
- <span data-ttu-id="9e80d-168">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="9e80d-168">Dynamics 365</span></span>
- <span data-ttu-id="9e80d-169">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9e80d-169">Exchange Online</span></span>
- <span data-ttu-id="9e80d-170">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e80d-170">Microsoft Teams</span></span>
- <span data-ttu-id="9e80d-171">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="9e80d-171">OneDrive for Business</span></span>
- <span data-ttu-id="9e80d-172">Power Automate</span><span class="sxs-lookup"><span data-stu-id="9e80d-172">Power Automate</span></span>
- <span data-ttu-id="9e80d-173">Power BI</span><span class="sxs-lookup"><span data-stu-id="9e80d-173">Power BI</span></span>
- <span data-ttu-id="9e80d-174">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9e80d-174">SharePoint Online</span></span>
- <span data-ttu-id="9e80d-175">Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="9e80d-175">Skype for Business</span></span>
- <span data-ttu-id="9e80d-176">Office 365</span><span class="sxs-lookup"><span data-stu-id="9e80d-176">Office 365</span></span>
- <span data-ttu-id="9e80d-177">Yammer</span><span class="sxs-lookup"><span data-stu-id="9e80d-177">Yammer</span></span> 

## <a name="related-topics"></a><span data-ttu-id="9e80d-178">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="9e80d-178">Related topics</span></span>
- [<span data-ttu-id="9e80d-179">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="9e80d-179">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9e80d-180">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="9e80d-180">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9e80d-181">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="9e80d-181">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9e80d-182">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="9e80d-182">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9e80d-183">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="9e80d-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9e80d-184">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="9e80d-184">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
