---
title: IdentityQueryEvents tabel in de geavanceerde jacht schema
description: Meer informatie over Active Directory-querygebeurtenissen in de tabel IdentityQueryEvents van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identiteiten, LDAP query's
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
ms.openlocfilehash: 436c4d7306f9f5febd614489090a0a10929ba3c9
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204873"
---
# <a name="identityqueryevents"></a><span data-ttu-id="dd65b-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="dd65b-104">IdentityQueryEvents</span></span>

<span data-ttu-id="dd65b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="dd65b-105">**Applies to:**</span></span>
- <span data-ttu-id="dd65b-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="dd65b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="dd65b-107">De `IdentityQueryEvents` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over query's die zijn uitgevoerd op Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen.</span><span class="sxs-lookup"><span data-stu-id="dd65b-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="dd65b-108">Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="dd65b-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="dd65b-109">Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.</span><span class="sxs-lookup"><span data-stu-id="dd65b-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="dd65b-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="dd65b-110">Column name</span></span> | <span data-ttu-id="dd65b-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="dd65b-111">Data type</span></span> | <span data-ttu-id="dd65b-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="dd65b-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="dd65b-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="dd65b-113">datetime</span></span> | <span data-ttu-id="dd65b-114">Datum en tijdstip waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="dd65b-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="dd65b-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-115">string</span></span> | <span data-ttu-id="dd65b-116">Type activiteit dat de gebeurtenis heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="dd65b-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="dd65b-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-117">string</span></span> | <span data-ttu-id="dd65b-118">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="dd65b-118">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="dd65b-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-119">string</span></span> | <span data-ttu-id="dd65b-120">Type query, zoals QueryGroup, QueryUser of EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="dd65b-120">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="dd65b-121">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-121">string</span></span> | <span data-ttu-id="dd65b-122">Naam van gebruiker, groep, apparaat, domein of ander entiteitstype dat wordt opgevraagd</span><span class="sxs-lookup"><span data-stu-id="dd65b-122">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="dd65b-123">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-123">string</span></span> | <span data-ttu-id="dd65b-124">Tekenreeks die wordt gebruikt om de query uit te voeren</span><span class="sxs-lookup"><span data-stu-id="dd65b-124">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="dd65b-125">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-125">string</span></span> | <span data-ttu-id="dd65b-126">Protocol dat tijdens de communicatie wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="dd65b-126">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="dd65b-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-127">string</span></span> | <span data-ttu-id="dd65b-128">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="dd65b-128">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="dd65b-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-129">string</span></span> | <span data-ttu-id="dd65b-130">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="dd65b-130">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="dd65b-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-131">string</span></span> | <span data-ttu-id="dd65b-132">Gebruikersnaam (UPN) van het account</span><span class="sxs-lookup"><span data-stu-id="dd65b-132">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="dd65b-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-133">string</span></span> | <span data-ttu-id="dd65b-134">Beveiligings-id (SID) van het account</span><span class="sxs-lookup"><span data-stu-id="dd65b-134">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="dd65b-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-135">string</span></span> | <span data-ttu-id="dd65b-136">Unieke id voor het account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="dd65b-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="dd65b-137">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-137">string</span></span> | <span data-ttu-id="dd65b-138">Naam van de accountgebruiker die in het adresboek wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="dd65b-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="dd65b-139">Typisch een combinatie van een bepaalde of voornaam, een middelste initiatie, en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="dd65b-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="dd65b-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-140">string</span></span> | <span data-ttu-id="dd65b-141">Volledig gekwalificeerde domeinnaam (FQDN) van het eindpunt</span><span class="sxs-lookup"><span data-stu-id="dd65b-141">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="dd65b-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-142">string</span></span> | <span data-ttu-id="dd65b-143">IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="dd65b-143">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="dd65b-144">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-144">string</span></span> | <span data-ttu-id="dd65b-145">Naam van het apparaat waarop de servertoepassing wordt uitgevoerd die de geregistreerde actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="dd65b-145">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="dd65b-146">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-146">string</span></span> | <span data-ttu-id="dd65b-147">IP-adres van het apparaat waarop de servertoepassing wordt uitgevoerd die de geregistreerde actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="dd65b-147">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="dd65b-148">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-148">string</span></span> | <span data-ttu-id="dd65b-149">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat waarop de geregistreerde actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="dd65b-149">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="dd65b-150">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-150">string</span></span> | <span data-ttu-id="dd65b-151">Gebruikersnaam (UPN) van het account waarop de geregistreerde actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="dd65b-151">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="dd65b-152">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-152">string</span></span> | <span data-ttu-id="dd65b-153">De naam weergeven van het account waarop de geregistreerde actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="dd65b-153">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="dd65b-154">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-154">string</span></span> | <span data-ttu-id="dd65b-155">Plaats, land of andere geografische locatie die aan het evenement is gekoppeld</span><span class="sxs-lookup"><span data-stu-id="dd65b-155">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="dd65b-156">Lange</span><span class="sxs-lookup"><span data-stu-id="dd65b-156">long</span></span> | <span data-ttu-id="dd65b-157">Unieke id voor het evenement</span><span class="sxs-lookup"><span data-stu-id="dd65b-157">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="dd65b-158">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="dd65b-158">string</span></span> | <span data-ttu-id="dd65b-159">Aanvullende informatie over de entiteit of gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="dd65b-159">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="dd65b-160">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="dd65b-160">Related topics</span></span>
- [<span data-ttu-id="dd65b-161">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="dd65b-161">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="dd65b-162">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="dd65b-162">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="dd65b-163">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="dd65b-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="dd65b-164">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="dd65b-164">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="dd65b-165">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="dd65b-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="dd65b-166">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="dd65b-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
