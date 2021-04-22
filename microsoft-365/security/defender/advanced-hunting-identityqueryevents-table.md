---
title: Tabel IdentityQueryEvents in het geavanceerde schema voor de jacht
description: Meer informatie over Active Directory-querygebeurtenissen in de tabel IdentityQueryEvents van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityQueryEvents, Azure AD, Active Directory, Microsoft Defender for Identity, identits, LDAP query's
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
ms.openlocfilehash: 89f6f83112bc6bea57a3b5f7703353adb9d87a30
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935795"
---
# <a name="identityqueryevents"></a><span data-ttu-id="f9273-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="f9273-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f9273-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f9273-105">**Applies to:**</span></span>
- <span data-ttu-id="f9273-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9273-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f9273-107">De tabel in het geavanceerde schema bevat informatie over query's die worden uitgevoerd met `IdentityQueryEvents` Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f9273-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="f9273-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="f9273-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="f9273-109">Voor gedetailleerde informatie over de gebeurtenissentypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing die beschikbaar is in het beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="f9273-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="f9273-110">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="f9273-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f9273-111">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="f9273-111">Column name</span></span> | <span data-ttu-id="f9273-112">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="f9273-112">Data type</span></span> | <span data-ttu-id="f9273-113">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f9273-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f9273-114">datetime</span><span class="sxs-lookup"><span data-stu-id="f9273-114">datetime</span></span> | <span data-ttu-id="f9273-115">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="f9273-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="f9273-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-116">string</span></span> | <span data-ttu-id="f9273-117">Type activiteit dat de gebeurtenis heeft geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="f9273-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="f9273-118">Zie de [in-portal schemaverwijzing voor](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) meer informatie</span><span class="sxs-lookup"><span data-stu-id="f9273-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="f9273-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-119">string</span></span> | <span data-ttu-id="f9273-120">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="f9273-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="f9273-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-121">string</span></span> | <span data-ttu-id="f9273-122">Type query, zoals Querygroep, QueryUser of EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="f9273-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="f9273-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-123">string</span></span> | <span data-ttu-id="f9273-124">Naam van gebruiker, groep, apparaat, domein of een ander entiteitstype dat wordt opgevraagd</span><span class="sxs-lookup"><span data-stu-id="f9273-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="f9273-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-125">string</span></span> | <span data-ttu-id="f9273-126">Tekenreeks die wordt gebruikt om de query uit te voeren</span><span class="sxs-lookup"><span data-stu-id="f9273-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="f9273-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-127">string</span></span> | <span data-ttu-id="f9273-128">Protocol dat tijdens de communicatie wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="f9273-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="f9273-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-129">string</span></span> | <span data-ttu-id="f9273-130">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="f9273-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="f9273-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-131">string</span></span> | <span data-ttu-id="f9273-132">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="f9273-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="f9273-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-133">string</span></span> | <span data-ttu-id="f9273-134">Gebruikersnaam (UPN) van het account</span><span class="sxs-lookup"><span data-stu-id="f9273-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="f9273-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-135">string</span></span> | <span data-ttu-id="f9273-136">Beveiligings-id (SID) van het account</span><span class="sxs-lookup"><span data-stu-id="f9273-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="f9273-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-137">string</span></span> | <span data-ttu-id="f9273-138">Unieke id voor het account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="f9273-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="f9273-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-139">string</span></span> | <span data-ttu-id="f9273-140">Naam van de accountgebruiker die wordt weergegeven in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="f9273-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="f9273-141">Meestal een combinatie van een bepaalde of voornaam, een middelste initiatie en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="f9273-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="f9273-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-142">string</span></span> | <span data-ttu-id="f9273-143">Volledig gekwalificeerde domeinnaam (FQDN) van het eindpunt</span><span class="sxs-lookup"><span data-stu-id="f9273-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="f9273-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-144">string</span></span> | <span data-ttu-id="f9273-145">IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="f9273-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="f9273-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-146">string</span></span> | <span data-ttu-id="f9273-147">TCP-poort die tijdens communicatie wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="f9273-147">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="f9273-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-148">string</span></span> | <span data-ttu-id="f9273-149">Naam van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="f9273-149">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="f9273-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-150">string</span></span> | <span data-ttu-id="f9273-151">IP-adres van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="f9273-151">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="f9273-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-152">string</span></span> | <span data-ttu-id="f9273-153">Doelpoort van gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="f9273-153">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="f9273-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-154">string</span></span> | <span data-ttu-id="f9273-155">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="f9273-155">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="f9273-156">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-156">string</span></span> | <span data-ttu-id="f9273-157">User principal name (UPN) of the account that the recorded action was applied to</span><span class="sxs-lookup"><span data-stu-id="f9273-157">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="f9273-158">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-158">string</span></span> | <span data-ttu-id="f9273-159">Weergavenaam van het account waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="f9273-159">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="f9273-160">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-160">string</span></span> | <span data-ttu-id="f9273-161">Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="f9273-161">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="f9273-162">lang</span><span class="sxs-lookup"><span data-stu-id="f9273-162">long</span></span> | <span data-ttu-id="f9273-163">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="f9273-163">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="f9273-164">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f9273-164">string</span></span> | <span data-ttu-id="f9273-165">Aanvullende informatie over de entiteit of gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="f9273-165">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f9273-166">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f9273-166">Related topics</span></span>
- [<span data-ttu-id="f9273-167">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="f9273-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f9273-168">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="f9273-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f9273-169">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="f9273-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f9273-170">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="f9273-170">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f9273-171">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="f9273-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f9273-172">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="f9273-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
