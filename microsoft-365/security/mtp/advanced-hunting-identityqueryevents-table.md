---
title: IdentityQueryEvents-tabel in het geavanceerde schema voor zoeken
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
ms.openlocfilehash: 7016127a75bca48103f5325ce169faa3d7c31c85
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929812"
---
# <a name="identityqueryevents"></a><span data-ttu-id="055a3-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="055a3-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="055a3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="055a3-105">**Applies to:**</span></span>
- <span data-ttu-id="055a3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="055a3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="055a3-107">De tabel in het geavanceerde zoekschema bevat informatie over query's die worden uitgevoerd op `IdentityQueryEvents` Active Directory-objecten, zoals gebruikers, groepen, apparaten [](advanced-hunting-overview.md) en domeinen.</span><span class="sxs-lookup"><span data-stu-id="055a3-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="055a3-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="055a3-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="055a3-109">Voor gedetailleerde informatie over de gebeurtenistypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` [ingebouwde schemaverwijzing in](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) het beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="055a3-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="055a3-110">Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="055a3-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="055a3-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="055a3-111">Column name</span></span> | <span data-ttu-id="055a3-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="055a3-112">Data type</span></span> | <span data-ttu-id="055a3-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="055a3-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="055a3-114">datetime</span><span class="sxs-lookup"><span data-stu-id="055a3-114">datetime</span></span> | <span data-ttu-id="055a3-115">Datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="055a3-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="055a3-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-116">string</span></span> | <span data-ttu-id="055a3-117">Het type activiteit dat de gebeurtenis heeft geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="055a3-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="055a3-118">Zie de [schemaverwijzing in de portal voor](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) meer informatie</span><span class="sxs-lookup"><span data-stu-id="055a3-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="055a3-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-119">string</span></span> | <span data-ttu-id="055a3-120">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="055a3-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="055a3-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-121">string</span></span> | <span data-ttu-id="055a3-122">Type query, zoals QueryGroup, QueryUser of EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="055a3-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="055a3-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-123">string</span></span> | <span data-ttu-id="055a3-124">Naam van gebruiker, groep, apparaat, domein of ander entiteitstype dat wordt opgevraagd</span><span class="sxs-lookup"><span data-stu-id="055a3-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="055a3-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-125">string</span></span> | <span data-ttu-id="055a3-126">Tekenreeks die wordt gebruikt om de query uit te voeren</span><span class="sxs-lookup"><span data-stu-id="055a3-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="055a3-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-127">string</span></span> | <span data-ttu-id="055a3-128">Protocol dat is gebruikt tijdens de communicatie</span><span class="sxs-lookup"><span data-stu-id="055a3-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="055a3-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-129">string</span></span> | <span data-ttu-id="055a3-130">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="055a3-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="055a3-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-131">string</span></span> | <span data-ttu-id="055a3-132">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="055a3-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="055a3-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-133">string</span></span> | <span data-ttu-id="055a3-134">UPN (User Principal Name) van het account</span><span class="sxs-lookup"><span data-stu-id="055a3-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="055a3-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-135">string</span></span> | <span data-ttu-id="055a3-136">Security Identifier (SID) van het account</span><span class="sxs-lookup"><span data-stu-id="055a3-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="055a3-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-137">string</span></span> | <span data-ttu-id="055a3-138">Unieke id voor het account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="055a3-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="055a3-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-139">string</span></span> | <span data-ttu-id="055a3-140">De naam van de accountgebruiker die wordt weergegeven in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="055a3-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="055a3-141">Meestal een combinatie van een bepaalde of voornaam, een middelste start en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="055a3-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="055a3-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-142">string</span></span> | <span data-ttu-id="055a3-143">FQDN (Fully Qualified Domain Name) van het eindpunt</span><span class="sxs-lookup"><span data-stu-id="055a3-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="055a3-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-144">string</span></span> | <span data-ttu-id="055a3-145">IP-adres dat aan het eindpunt is toegewezen en dat is gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="055a3-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="055a3-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-146">string</span></span> | <span data-ttu-id="055a3-147">Naam van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="055a3-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="055a3-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-148">string</span></span> | <span data-ttu-id="055a3-149">Het IP-adres van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="055a3-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="055a3-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-150">string</span></span> | <span data-ttu-id="055a3-151">FQDN (Fully Qualified Domain Name) van het apparaat waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="055a3-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="055a3-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-152">string</span></span> | <span data-ttu-id="055a3-153">UPN (User Principal Name) van het account waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="055a3-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="055a3-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-154">string</span></span> | <span data-ttu-id="055a3-155">Weergavenaam van het account waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="055a3-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="055a3-156">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-156">string</span></span> | <span data-ttu-id="055a3-157">Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="055a3-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="055a3-158">lang</span><span class="sxs-lookup"><span data-stu-id="055a3-158">long</span></span> | <span data-ttu-id="055a3-159">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="055a3-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="055a3-160">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="055a3-160">string</span></span> | <span data-ttu-id="055a3-161">Aanvullende informatie over de entiteit of gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="055a3-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="055a3-162">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="055a3-162">Related topics</span></span>
- [<span data-ttu-id="055a3-163">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="055a3-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="055a3-164">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="055a3-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="055a3-165">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="055a3-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="055a3-166">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="055a3-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="055a3-167">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="055a3-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="055a3-168">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="055a3-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
