---
title: IdentityQueryEvents-tabel in het geavanceerde jacht schema
description: Meer informatie over Active Directory-querygebeurtenissen in de tabel IdentityQueryEvents van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, Identities, LDAP-query's
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
ms.openlocfilehash: 2b163dc39e56c82ef177b71d197c431c744b12d7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847402"
---
# <a name="identityqueryevents"></a><span data-ttu-id="246c5-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="246c5-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="246c5-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="246c5-105">**Applies to:**</span></span>
- <span data-ttu-id="246c5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="246c5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="246c5-107">De `IdentityQueryEvents` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat informatie over query's die zijn uitgevoerd voor Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen.</span><span class="sxs-lookup"><span data-stu-id="246c5-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="246c5-108">Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="246c5-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="246c5-109">Voor gedetailleerde informatie over de typen gebeurtenissen ( `ActionType` waarden) die door een tabel worden ondersteund, gebruikt u de [ingebouwde schema verwijzing](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) die beschikbaar is in het Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="246c5-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="246c5-110">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="246c5-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="246c5-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="246c5-111">Column name</span></span> | <span data-ttu-id="246c5-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="246c5-112">Data type</span></span> | <span data-ttu-id="246c5-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="246c5-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="246c5-114">tijd</span><span class="sxs-lookup"><span data-stu-id="246c5-114">datetime</span></span> | <span data-ttu-id="246c5-115">De datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="246c5-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="246c5-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-116">string</span></span> | <span data-ttu-id="246c5-117">Type activiteit waarmee de gebeurtenis wordt geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="246c5-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="246c5-118">Zie de [verwijzingen naar het portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) voor Details</span><span class="sxs-lookup"><span data-stu-id="246c5-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="246c5-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-119">string</span></span> | <span data-ttu-id="246c5-120">De toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="246c5-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="246c5-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-121">string</span></span> | <span data-ttu-id="246c5-122">Type query, zoals QueryGroup, QueryUser of EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="246c5-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="246c5-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-123">string</span></span> | <span data-ttu-id="246c5-124">De naam van de gebruiker, groep, het apparaat, het domein of een ander entiteitstype dat wordt opgevraagd</span><span class="sxs-lookup"><span data-stu-id="246c5-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="246c5-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-125">string</span></span> | <span data-ttu-id="246c5-126">Tekenreeks die wordt gebruikt om de query uit te voeren</span><span class="sxs-lookup"><span data-stu-id="246c5-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="246c5-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-127">string</span></span> | <span data-ttu-id="246c5-128">Gebruikte protocol tijdens de communicatie</span><span class="sxs-lookup"><span data-stu-id="246c5-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="246c5-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-129">string</span></span> | <span data-ttu-id="246c5-130">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="246c5-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="246c5-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-131">string</span></span> | <span data-ttu-id="246c5-132">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="246c5-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="246c5-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-133">string</span></span> | <span data-ttu-id="246c5-134">UPN (User Principal Name) van het account</span><span class="sxs-lookup"><span data-stu-id="246c5-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="246c5-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-135">string</span></span> | <span data-ttu-id="246c5-136">SID (Security Identifier) van het account</span><span class="sxs-lookup"><span data-stu-id="246c5-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="246c5-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-137">string</span></span> | <span data-ttu-id="246c5-138">Unieke id voor het account in azure AD</span><span class="sxs-lookup"><span data-stu-id="246c5-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="246c5-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-139">string</span></span> | <span data-ttu-id="246c5-140">Naam van de account gebruiker die in het adresboek wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="246c5-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="246c5-141">Meestal een combinatie van een bepaalde of voornaam, een tweede opening en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="246c5-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="246c5-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-142">string</span></span> | <span data-ttu-id="246c5-143">FQDN-naam (Fully Qualified Domain Name) van het eindpunt</span><span class="sxs-lookup"><span data-stu-id="246c5-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="246c5-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-144">string</span></span> | <span data-ttu-id="246c5-145">Het IP-adres dat is toegewezen aan het eindpunt en die wordt gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="246c5-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="246c5-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-146">string</span></span> | <span data-ttu-id="246c5-147">Naam van het apparaat waarop de servertoepassing wordt uitgevoerd die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="246c5-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="246c5-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-148">string</span></span> | <span data-ttu-id="246c5-149">IP-adres van het apparaat waarop de servertoepassing wordt uitgevoerd die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="246c5-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="246c5-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-150">string</span></span> | <span data-ttu-id="246c5-151">FQDN-naam (Fully Qualified Domain Name) van het apparaat waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="246c5-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="246c5-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-152">string</span></span> | <span data-ttu-id="246c5-153">De UPN (User Principal Name) van het account waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="246c5-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="246c5-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-154">string</span></span> | <span data-ttu-id="246c5-155">Weergavenaam van het account waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="246c5-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="246c5-156">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-156">string</span></span> | <span data-ttu-id="246c5-157">Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="246c5-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="246c5-158">lang</span><span class="sxs-lookup"><span data-stu-id="246c5-158">long</span></span> | <span data-ttu-id="246c5-159">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="246c5-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="246c5-160">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="246c5-160">string</span></span> | <span data-ttu-id="246c5-161">Aanvullende informatie over de entiteit of gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="246c5-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="246c5-162">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="246c5-162">Related topics</span></span>
- [<span data-ttu-id="246c5-163">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="246c5-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="246c5-164">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="246c5-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="246c5-165">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="246c5-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="246c5-166">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="246c5-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="246c5-167">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="246c5-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="246c5-168">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="246c5-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
