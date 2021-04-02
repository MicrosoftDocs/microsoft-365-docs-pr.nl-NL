---
title: Tabel DeviceAlertEvents in het geavanceerde schema voor de jacht
description: Meer informatie over gebeurtenissen bij het genereren van waarschuwingen in de tabel DeviceAlertEvents van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, DeviceAlertEvents, alert, ernst, categorie
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: 66ecdc8fbcde04d78f2deede5f4e296a7f051ef0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499164"
---
# <a name="devicealertevents"></a><span data-ttu-id="4dc9d-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="4dc9d-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4dc9d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4dc9d-105">**Applies to:**</span></span>
- [<span data-ttu-id="4dc9d-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4dc9d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="4dc9d-107">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="4dc9d-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4dc9d-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="4dc9d-109">De `DeviceAlertEvents` tabel in het geavanceerde schema [bevat](advanced-hunting-overview.md) informatie over waarschuwingen in het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="4dc9d-110">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="4dc9d-111">Zie de geavanceerde verwijzing naar het schema voor de jacht voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="4dc9d-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="4dc9d-112">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="4dc9d-112">Column name</span></span> | <span data-ttu-id="4dc9d-113">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="4dc9d-113">Data type</span></span> | <span data-ttu-id="4dc9d-114">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="4dc9d-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="4dc9d-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4dc9d-115">string</span></span> | <span data-ttu-id="4dc9d-116">Unieke id voor de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="4dc9d-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="4dc9d-117">datetime</span><span class="sxs-lookup"><span data-stu-id="4dc9d-117">datetime</span></span> | <span data-ttu-id="4dc9d-118">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="4dc9d-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="4dc9d-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4dc9d-119">string</span></span> | <span data-ttu-id="4dc9d-120">Unieke id voor het apparaat in de service</span><span class="sxs-lookup"><span data-stu-id="4dc9d-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="4dc9d-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4dc9d-121">string</span></span> | <span data-ttu-id="4dc9d-122">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat</span><span class="sxs-lookup"><span data-stu-id="4dc9d-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="4dc9d-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4dc9d-123">string</span></span> | <span data-ttu-id="4dc9d-124">Geeft het mogelijke effect (hoog, gemiddeld of laag) aan van de bedreigingsindicator of inbreukactiviteit die door de waarschuwing is geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="4dc9d-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="4dc9d-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4dc9d-125">string</span></span> | <span data-ttu-id="4dc9d-126">Type bedreigingsindicator of inbreukactiviteit die door de waarschuwing is geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="4dc9d-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="4dc9d-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4dc9d-127">string</span></span> | <span data-ttu-id="4dc9d-128">Titel van de waarschuwing</span><span class="sxs-lookup"><span data-stu-id="4dc9d-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="4dc9d-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4dc9d-129">string</span></span> | <span data-ttu-id="4dc9d-130">Naam van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="4dc9d-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="4dc9d-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4dc9d-131">string</span></span> | <span data-ttu-id="4dc9d-132">SHA-1 van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="4dc9d-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="4dc9d-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4dc9d-133">string</span></span> | <span data-ttu-id="4dc9d-134">URL of volledig gekwalificeerde domeinnaam (FQDN) die werd verbonden met</span><span class="sxs-lookup"><span data-stu-id="4dc9d-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="4dc9d-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4dc9d-135">string</span></span> | <span data-ttu-id="4dc9d-136">IP-adres dat werd verbonden met</span><span class="sxs-lookup"><span data-stu-id="4dc9d-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="4dc9d-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4dc9d-137">string</span></span> | <span data-ttu-id="4dc9d-138">MITRE ATT&CK-technieken die zijn gekoppeld aan de activiteit die de waarschuwing heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="4dc9d-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="4dc9d-139">lang</span><span class="sxs-lookup"><span data-stu-id="4dc9d-139">long</span></span> | <span data-ttu-id="4dc9d-140">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="4dc9d-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="4dc9d-141">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de `DeviceName` kolommen en `Timestamp` de kolommen</span><span class="sxs-lookup"><span data-stu-id="4dc9d-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="4dc9d-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4dc9d-142">string</span></span> | <span data-ttu-id="4dc9d-143">Tabel met de details van de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="4dc9d-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4dc9d-144">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4dc9d-144">Related topics</span></span>
- [<span data-ttu-id="4dc9d-145">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="4dc9d-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4dc9d-146">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="4dc9d-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4dc9d-147">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="4dc9d-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
