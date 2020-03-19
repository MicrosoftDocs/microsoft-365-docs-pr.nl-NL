---
title: AlertEvents tabel in de geavanceerde jacht schema
description: Meer informatie over gebeurtenissen voor het genereren van waarschuwingen in de tabel AlertEvents van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreigingjacht, cyberdreigingsjacht, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, waarschuwingsgebeurtenissen, alert, ernst, categorie
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9f341705d8247183b7e8a5271231c82faf8b386a
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806323"
---
# <a name="alertevents"></a><span data-ttu-id="3a22e-104">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="3a22e-104">AlertEvents</span></span>

<span data-ttu-id="3a22e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="3a22e-105">**Applies to:**</span></span>
- <span data-ttu-id="3a22e-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="3a22e-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="3a22e-107">De `AlertEvents` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over Microsoft Defender ATP-waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="3a22e-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="3a22e-108">Gebruik deze verwijzing om query's te maken die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="3a22e-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="3a22e-109">Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.</span><span class="sxs-lookup"><span data-stu-id="3a22e-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3a22e-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="3a22e-110">Column name</span></span> | <span data-ttu-id="3a22e-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="3a22e-111">Data type</span></span> | <span data-ttu-id="3a22e-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3a22e-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="3a22e-113">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3a22e-113">string</span></span> | <span data-ttu-id="3a22e-114">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="3a22e-114">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="3a22e-115">Datetime</span><span class="sxs-lookup"><span data-stu-id="3a22e-115">datetime</span></span> | <span data-ttu-id="3a22e-116">Datum en tijd waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="3a22e-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="3a22e-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3a22e-117">string</span></span> | <span data-ttu-id="3a22e-118">Unieke id voor de machine in de service</span><span class="sxs-lookup"><span data-stu-id="3a22e-118">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="3a22e-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3a22e-119">string</span></span> | <span data-ttu-id="3a22e-120">Volledig gekwalificeerde domeinnaam (FQDN) van de machine</span><span class="sxs-lookup"><span data-stu-id="3a22e-120">Fully qualified domain name (FQDN) of the machine</span></span> |
| `Severity` | <span data-ttu-id="3a22e-121">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3a22e-121">string</span></span> | <span data-ttu-id="3a22e-122">Geeft de potentiële impact (hoog, gemiddeld of laag) van de dreigingsindicator of inbreukactiviteit aan die door de waarschuwing wordt geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="3a22e-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="3a22e-123">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3a22e-123">string</span></span> | <span data-ttu-id="3a22e-124">Type bedreigingsindicator of inbreukactiviteit die door de waarschuwing wordt geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="3a22e-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="3a22e-125">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3a22e-125">string</span></span> | <span data-ttu-id="3a22e-126">Titel van de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="3a22e-126">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="3a22e-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3a22e-127">string</span></span> | <span data-ttu-id="3a22e-128">Naam van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="3a22e-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="3a22e-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3a22e-129">string</span></span> | <span data-ttu-id="3a22e-130">SHA-1 van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="3a22e-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="3a22e-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3a22e-131">string</span></span> | <span data-ttu-id="3a22e-132">URL of volledig gekwalificeerde domeinnaam (FQDN) die werd verbonden met</span><span class="sxs-lookup"><span data-stu-id="3a22e-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="3a22e-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3a22e-133">string</span></span> | <span data-ttu-id="3a22e-134">IP-adres dat werd verbonden met</span><span class="sxs-lookup"><span data-stu-id="3a22e-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="3a22e-135">Lange</span><span class="sxs-lookup"><span data-stu-id="3a22e-135">long</span></span> | <span data-ttu-id="3a22e-136">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="3a22e-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="3a22e-137">Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp</span><span class="sxs-lookup"><span data-stu-id="3a22e-137">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `Table` | <span data-ttu-id="3a22e-138">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3a22e-138">string</span></span> | <span data-ttu-id="3a22e-139">Tabel met de details van de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="3a22e-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3a22e-140">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="3a22e-140">Related topics</span></span>
- [<span data-ttu-id="3a22e-141">Proactief jagen op bedreigingen</span><span class="sxs-lookup"><span data-stu-id="3a22e-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3a22e-142">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="3a22e-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3a22e-143">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="3a22e-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3a22e-144">Op zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="3a22e-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3a22e-145">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="3a22e-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3a22e-146">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="3a22e-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
