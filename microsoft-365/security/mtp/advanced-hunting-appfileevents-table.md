---
title: Tabel AppFileEvents in het geavanceerde schema voor zoeken
description: Meer informatie over bestandsgerelateerde gebeurtenissen die zijn gekoppeld aan cloud-apps en -services in de tabel AppFileEvents van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 8406d1f9e3d56555b1699d191933c6f9735c9574
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145485"
---
# <a name="appfileevents"></a><span data-ttu-id="2a3e6-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="2a3e6-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2a3e6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2a3e6-105">**Applies to:**</span></span>
- <span data-ttu-id="2a3e6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a3e6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2a3e6-107">De tabel in het geavanceerde zoekschema bevat informatie over activiteiten in verband met bestanden in cloud-apps en services die worden gecontroleerd `AppFileEvents` door Microsoft Cloud App Security. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="2a3e6-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="2a3e6-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="2a3e6-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="2a3e6-109">Voor gedetailleerde informatie over de gebeurtenistypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` [ingebouwde schemaverwijzing in](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) het beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="2a3e6-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="2a3e6-110">Zie het geavanceerde zoekschema voor informatie over andere tabellen in het geavanceerde schema voor [het zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="2a3e6-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2a3e6-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="2a3e6-111">Column name</span></span> | <span data-ttu-id="2a3e6-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="2a3e6-112">Data type</span></span> | <span data-ttu-id="2a3e6-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2a3e6-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2a3e6-114">datetime</span><span class="sxs-lookup"><span data-stu-id="2a3e6-114">datetime</span></span> | <span data-ttu-id="2a3e6-115">Datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="2a3e6-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="2a3e6-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-116">string</span></span> | <span data-ttu-id="2a3e6-117">Het type activiteit dat de gebeurtenis heeft geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="2a3e6-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="2a3e6-118">Zie de [schemaverwijzing in de portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="2a3e6-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="2a3e6-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-119">string</span></span> | <span data-ttu-id="2a3e6-120">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="2a3e6-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="2a3e6-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-121">string</span></span> | <span data-ttu-id="2a3e6-122">De naam van het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="2a3e6-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="2a3e6-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-123">string</span></span> | <span data-ttu-id="2a3e6-124">Map met het bestand waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="2a3e6-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="2a3e6-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-125">string</span></span> | <span data-ttu-id="2a3e6-126">Oorspronkelijke naam van het bestand dat is hernoemd als gevolg van de actie</span><span class="sxs-lookup"><span data-stu-id="2a3e6-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="2a3e6-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-127">string</span></span> | <span data-ttu-id="2a3e6-128">Oorspronkelijke map met het bestand voordat de opgenomen actie werd toegepast</span><span class="sxs-lookup"><span data-stu-id="2a3e6-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="2a3e6-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-129">string</span></span> | <span data-ttu-id="2a3e6-130">Netwerkprotocol gebruikt</span><span class="sxs-lookup"><span data-stu-id="2a3e6-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="2a3e6-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-131">string</span></span> | <span data-ttu-id="2a3e6-132">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="2a3e6-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="2a3e6-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-133">string</span></span> | <span data-ttu-id="2a3e6-134">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="2a3e6-134">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="2a3e6-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-135">string</span></span> | <span data-ttu-id="2a3e6-136">Security Identifier (SID) van het account</span><span class="sxs-lookup"><span data-stu-id="2a3e6-136">Security Identifier (SID) of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="2a3e6-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-137">string</span></span> | <span data-ttu-id="2a3e6-138">UPN (User Principal Name) van het account</span><span class="sxs-lookup"><span data-stu-id="2a3e6-138">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="2a3e6-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-139">string</span></span> | <span data-ttu-id="2a3e6-140">Unieke id voor het account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="2a3e6-140">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="2a3e6-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-141">string</span></span> | <span data-ttu-id="2a3e6-142">De naam van de accountgebruiker die wordt weergegeven in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="2a3e6-142">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="2a3e6-143">Meestal een combinatie van een bepaalde of voornaam, een middelste start en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="2a3e6-143">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="2a3e6-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-144">string</span></span> | <span data-ttu-id="2a3e6-145">FQDN (Fully Qualified Domain Name) van het apparaat</span><span class="sxs-lookup"><span data-stu-id="2a3e6-145">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="2a3e6-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-146">string</span></span> | <span data-ttu-id="2a3e6-147">Type apparaat</span><span class="sxs-lookup"><span data-stu-id="2a3e6-147">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="2a3e6-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-148">string</span></span> | <span data-ttu-id="2a3e6-149">Platform van het besturingssysteem dat wordt uitgevoerd op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="2a3e6-149">Platform of the operating system running on the device.</span></span> <span data-ttu-id="2a3e6-150">Dit geeft specifieke besturingssystemen aan, inclusief variaties binnen dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="2a3e6-150">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="2a3e6-151">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-151">string</span></span> | <span data-ttu-id="2a3e6-152">IP-adres dat aan het eindpunt is toegewezen en dat is gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="2a3e6-152">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="2a3e6-153">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-153">string</span></span> | <span data-ttu-id="2a3e6-154">TCP-poort gebruikt tijdens communicatie</span><span class="sxs-lookup"><span data-stu-id="2a3e6-154">TCP port used during communication</span></span>  |
| `DestinationDeviceName` | <span data-ttu-id="2a3e6-155">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-155">string</span></span> | <span data-ttu-id="2a3e6-156">Naam van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="2a3e6-156">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="2a3e6-157">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-157">string</span></span> | <span data-ttu-id="2a3e6-158">Het IP-adres van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="2a3e6-158">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="2a3e6-159">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-159">string</span></span> | <span data-ttu-id="2a3e6-160">Bestemmingspoort van gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="2a3e6-160">Destination port of related network communications</span></span> |
| `Location` | <span data-ttu-id="2a3e6-161">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-161">string</span></span> | <span data-ttu-id="2a3e6-162">Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="2a3e6-162">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="2a3e6-163">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-163">string</span></span> | <span data-ttu-id="2a3e6-164">Internetprovider (ISP) die is gekoppeld aan het IP-adres van het eindpunt</span><span class="sxs-lookup"><span data-stu-id="2a3e6-164">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="2a3e6-165">lang</span><span class="sxs-lookup"><span data-stu-id="2a3e6-165">long</span></span> | <span data-ttu-id="2a3e6-166">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="2a3e6-166">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="2a3e6-167">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2a3e6-167">string</span></span> | <span data-ttu-id="2a3e6-168">Aanvullende informatie over de entiteit of gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="2a3e6-168">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2a3e6-169">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2a3e6-169">Related topics</span></span>
- [<span data-ttu-id="2a3e6-170">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="2a3e6-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2a3e6-171">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="2a3e6-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2a3e6-172">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="2a3e6-172">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2a3e6-173">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="2a3e6-173">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2a3e6-174">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="2a3e6-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2a3e6-175">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="2a3e6-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
