---
title: AppFileEvents-tabel in het geavanceerde jacht schema
description: Meer informatie over bestanden die zijn gekoppeld aan Cloud-apps en-services in de tabel AppFileEvents van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, AppFileEvents, Cloud app Security, MCAS
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
ms.openlocfilehash: 1a7f523e96c0a46c29098f7e5bb2fbb83a4db4bb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847654"
---
# <a name="appfileevents"></a><span data-ttu-id="202b4-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="202b4-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="202b4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="202b4-105">**Applies to:**</span></span>
- <span data-ttu-id="202b4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="202b4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="202b4-107">De `AppFileEvents` tabel in het [Geavanceerde bejachts](advanced-hunting-overview.md) schema bevat informatie over Bestandsactiviteiten in Cloud-apps en services die worden gecontroleerd in de beveiliging van de Microsoft Cloud-app.</span><span class="sxs-lookup"><span data-stu-id="202b4-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="202b4-108">Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="202b4-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="202b4-109">Voor gedetailleerde informatie over de typen gebeurtenissen ( `ActionType` waarden) die door een tabel worden ondersteund, gebruikt u de [ingebouwde schema verwijzing](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) die beschikbaar is in het Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="202b4-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="202b4-110">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="202b4-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="202b4-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="202b4-111">Column name</span></span> | <span data-ttu-id="202b4-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="202b4-112">Data type</span></span> | <span data-ttu-id="202b4-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="202b4-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="202b4-114">tijd</span><span class="sxs-lookup"><span data-stu-id="202b4-114">datetime</span></span> | <span data-ttu-id="202b4-115">De datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="202b4-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="202b4-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-116">string</span></span> | <span data-ttu-id="202b4-117">Type activiteit waarmee de gebeurtenis wordt geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="202b4-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="202b4-118">Zie de [verwijzingen naar het portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) voor Details</span><span class="sxs-lookup"><span data-stu-id="202b4-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="202b4-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-119">string</span></span> | <span data-ttu-id="202b4-120">De toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="202b4-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="202b4-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-121">string</span></span> | <span data-ttu-id="202b4-122">De naam van het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="202b4-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="202b4-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-123">string</span></span> | <span data-ttu-id="202b4-124">Map met het bestand waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="202b4-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="202b4-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-125">string</span></span> | <span data-ttu-id="202b4-126">De oorspronkelijke naam van het bestand dat de naam van het bestand heeft gewijzigd en waarvan de naam is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="202b4-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="202b4-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-127">string</span></span> | <span data-ttu-id="202b4-128">De oorspronkelijke map met het bestand voordat de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="202b4-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="202b4-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-129">string</span></span> | <span data-ttu-id="202b4-130">Gebruikte netwerkprotocollen</span><span class="sxs-lookup"><span data-stu-id="202b4-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="202b4-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-131">string</span></span> | <span data-ttu-id="202b4-132">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="202b4-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="202b4-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-133">string</span></span> | <span data-ttu-id="202b4-134">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="202b4-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="202b4-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-135">string</span></span> | <span data-ttu-id="202b4-136">UPN (User Principal Name) van het account</span><span class="sxs-lookup"><span data-stu-id="202b4-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="202b4-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-137">string</span></span> | <span data-ttu-id="202b4-138">Unieke id voor het account in azure AD</span><span class="sxs-lookup"><span data-stu-id="202b4-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="202b4-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-139">string</span></span> | <span data-ttu-id="202b4-140">Naam van de account gebruiker die in het adresboek wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="202b4-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="202b4-141">Meestal een combinatie van een bepaalde of voornaam, een tweede opening en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="202b4-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="202b4-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-142">string</span></span> | <span data-ttu-id="202b4-143">FQDN (Fully Qualified Domain Name) van het apparaat</span><span class="sxs-lookup"><span data-stu-id="202b4-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="202b4-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-144">string</span></span> | <span data-ttu-id="202b4-145">Type apparaat</span><span class="sxs-lookup"><span data-stu-id="202b4-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="202b4-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-146">string</span></span> | <span data-ttu-id="202b4-147">Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="202b4-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="202b4-148">Dit geeft specifieke besturingssystemen aan, met inbegrip van variaties in dezelfde familie, zoals Windows 10 en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="202b4-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="202b4-149">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-149">string</span></span> | <span data-ttu-id="202b4-150">Het IP-adres dat is toegewezen aan het eindpunt en die wordt gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="202b4-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="202b4-151">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-151">string</span></span> | <span data-ttu-id="202b4-152">Naam van het apparaat waarop de servertoepassing wordt uitgevoerd die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="202b4-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="202b4-153">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-153">string</span></span> | <span data-ttu-id="202b4-154">IP-adres van het apparaat waarop de servertoepassing wordt uitgevoerd die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="202b4-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="202b4-155">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-155">string</span></span> | <span data-ttu-id="202b4-156">Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="202b4-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="202b4-157">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-157">string</span></span> | <span data-ttu-id="202b4-158">Internetprovider (ISP) die is gekoppeld aan het IP-adres van het eindpunt</span><span class="sxs-lookup"><span data-stu-id="202b4-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="202b4-159">lang</span><span class="sxs-lookup"><span data-stu-id="202b4-159">long</span></span> | <span data-ttu-id="202b4-160">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="202b4-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="202b4-161">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="202b4-161">string</span></span> | <span data-ttu-id="202b4-162">Aanvullende informatie over de entiteit of gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="202b4-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="202b4-163">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="202b4-163">Related topics</span></span>
- [<span data-ttu-id="202b4-164">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="202b4-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="202b4-165">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="202b4-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="202b4-166">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="202b4-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="202b4-167">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="202b4-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="202b4-168">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="202b4-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="202b4-169">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="202b4-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
