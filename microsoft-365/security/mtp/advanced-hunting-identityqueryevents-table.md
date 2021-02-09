---
title: De tabel IdentityQueryEvents in het geavanceerde schema voor zoeken
description: Meer informatie over Active Directory-querygebeurtenissen in de tabel IdentityQueryEvents van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identities, LDAP queries
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
ms.openlocfilehash: 48a1520e9fc6239fd3105f01a32a03e5e58df174
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145282"
---
# <a name="identityqueryevents"></a><span data-ttu-id="bb691-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="bb691-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bb691-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bb691-105">**Applies to:**</span></span>
- <span data-ttu-id="bb691-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb691-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bb691-107">De tabel in het geavanceerde zoekschema bevat informatie over query's die worden uitgevoerd op `IdentityQueryEvents` Active Directory-objecten, zoals gebruikers, groepen, apparaten [](advanced-hunting-overview.md) en domeinen.</span><span class="sxs-lookup"><span data-stu-id="bb691-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="bb691-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="bb691-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="bb691-109">Voor gedetailleerde informatie over de gebeurtenistypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` [ingebouwde schemaverwijzing in](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) het beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="bb691-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="bb691-110">Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="bb691-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="bb691-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="bb691-111">Column name</span></span> | <span data-ttu-id="bb691-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="bb691-112">Data type</span></span> | <span data-ttu-id="bb691-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="bb691-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="bb691-114">datetime</span><span class="sxs-lookup"><span data-stu-id="bb691-114">datetime</span></span> | <span data-ttu-id="bb691-115">Datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="bb691-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="bb691-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-116">string</span></span> | <span data-ttu-id="bb691-117">Het type activiteit dat de gebeurtenis heeft geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="bb691-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="bb691-118">Zie de [schemaverwijzing in de portal voor](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) meer informatie</span><span class="sxs-lookup"><span data-stu-id="bb691-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="bb691-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-119">string</span></span> | <span data-ttu-id="bb691-120">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="bb691-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="bb691-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-121">string</span></span> | <span data-ttu-id="bb691-122">Type query, zoals QueryGroup, QueryUser of EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="bb691-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="bb691-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-123">string</span></span> | <span data-ttu-id="bb691-124">Naam van gebruiker, groep, apparaat, domein of ander entiteitstype dat wordt opgevraagd</span><span class="sxs-lookup"><span data-stu-id="bb691-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="bb691-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-125">string</span></span> | <span data-ttu-id="bb691-126">Tekenreeks die wordt gebruikt om de query uit te voeren</span><span class="sxs-lookup"><span data-stu-id="bb691-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="bb691-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-127">string</span></span> | <span data-ttu-id="bb691-128">Protocol dat is gebruikt tijdens de communicatie</span><span class="sxs-lookup"><span data-stu-id="bb691-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="bb691-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-129">string</span></span> | <span data-ttu-id="bb691-130">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="bb691-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="bb691-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-131">string</span></span> | <span data-ttu-id="bb691-132">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="bb691-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="bb691-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-133">string</span></span> | <span data-ttu-id="bb691-134">UPN (User Principal Name) van het account</span><span class="sxs-lookup"><span data-stu-id="bb691-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="bb691-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-135">string</span></span> | <span data-ttu-id="bb691-136">Security Identifier (SID) van het account</span><span class="sxs-lookup"><span data-stu-id="bb691-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="bb691-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-137">string</span></span> | <span data-ttu-id="bb691-138">Unieke id voor het account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="bb691-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="bb691-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-139">string</span></span> | <span data-ttu-id="bb691-140">De naam van de accountgebruiker die wordt weergegeven in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="bb691-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="bb691-141">Meestal een combinatie van een bepaalde of voornaam, een middelste start en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="bb691-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="bb691-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-142">string</span></span> | <span data-ttu-id="bb691-143">FQDN (Fully Qualified Domain Name) van het eindpunt</span><span class="sxs-lookup"><span data-stu-id="bb691-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="bb691-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-144">string</span></span> | <span data-ttu-id="bb691-145">IP-adres dat aan het eindpunt is toegewezen en dat is gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="bb691-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="bb691-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-146">string</span></span> | <span data-ttu-id="bb691-147">TCP-poort gebruikt tijdens communicatie</span><span class="sxs-lookup"><span data-stu-id="bb691-147">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="bb691-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-148">string</span></span> | <span data-ttu-id="bb691-149">Naam van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="bb691-149">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="bb691-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-150">string</span></span> | <span data-ttu-id="bb691-151">Het IP-adres van het apparaat met de servertoepassing dat de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="bb691-151">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="bb691-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-152">string</span></span> | <span data-ttu-id="bb691-153">Bestemmingspoort van gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="bb691-153">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="bb691-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-154">string</span></span> | <span data-ttu-id="bb691-155">FQDN (Fully Qualified Domain Name) van het apparaat waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="bb691-155">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="bb691-156">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-156">string</span></span> | <span data-ttu-id="bb691-157">UPN (User Principal Name) van het account waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="bb691-157">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="bb691-158">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-158">string</span></span> | <span data-ttu-id="bb691-159">Weergavenaam van het account waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="bb691-159">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="bb691-160">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-160">string</span></span> | <span data-ttu-id="bb691-161">Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="bb691-161">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="bb691-162">lang</span><span class="sxs-lookup"><span data-stu-id="bb691-162">long</span></span> | <span data-ttu-id="bb691-163">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="bb691-163">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="bb691-164">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb691-164">string</span></span> | <span data-ttu-id="bb691-165">Aanvullende informatie over de entiteit of gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="bb691-165">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="bb691-166">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="bb691-166">Related topics</span></span>
- [<span data-ttu-id="bb691-167">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="bb691-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bb691-168">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="bb691-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bb691-169">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="bb691-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="bb691-170">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="bb691-170">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="bb691-171">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="bb691-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bb691-172">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="bb691-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
