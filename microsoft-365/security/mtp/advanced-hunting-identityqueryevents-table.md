---
title: Tabel IdentityQueryEvents in het geavanceerde jachtschema
description: Meer informatie over Active Directory-querygebeurtenissen in de tabel IdentityQueryEvents van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-bedreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemaverwijzing, kusto, tabel, kolom, gegevenstype, beschrijving, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identiteiten, LDAP-query's
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
ms.openlocfilehash: b2fc94d6ac6606c97b4824bc556b7299a2bd8ec7
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929166"
---
# <a name="identityqueryevents"></a><span data-ttu-id="9e2e6-104">IdentityQueryGebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="9e2e6-104">IdentityQueryEvents</span></span>

<span data-ttu-id="9e2e6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9e2e6-105">**Applies to:**</span></span>
- <span data-ttu-id="9e2e6-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="9e2e6-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="9e2e6-107">De `IdentityQueryEvents` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over query's die zijn uitgevoerd met Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen.</span><span class="sxs-lookup"><span data-stu-id="9e2e6-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="9e2e6-108">Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="9e2e6-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="9e2e6-109">Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="9e2e6-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9e2e6-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="9e2e6-110">Column name</span></span> | <span data-ttu-id="9e2e6-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="9e2e6-111">Data type</span></span> | <span data-ttu-id="9e2e6-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="9e2e6-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9e2e6-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="9e2e6-113">datetime</span></span> | <span data-ttu-id="9e2e6-114">Datum en tijdstip waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="9e2e6-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="9e2e6-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e2e6-115">string</span></span> | <span data-ttu-id="9e2e6-116">Type activiteit dat de gebeurtenis heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="9e2e6-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="9e2e6-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e2e6-117">string</span></span> | <span data-ttu-id="9e2e6-118">Toepassing die de geregistreerde actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="9e2e6-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="9e2e6-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e2e6-119">string</span></span> | <span data-ttu-id="9e2e6-120">Type query: QueryGroep, QueryUser of Gebruikers opsommen</span><span class="sxs-lookup"><span data-stu-id="9e2e6-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="9e2e6-121">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e2e6-121">string</span></span> | <span data-ttu-id="9e2e6-122">Naam van de gebruiker, groep, apparaat, domein of een ander entiteitstype dat wordt opgevraagd</span><span class="sxs-lookup"><span data-stu-id="9e2e6-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="9e2e6-123">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e2e6-123">string</span></span> | <span data-ttu-id="9e2e6-124">Protocol dat tijdens de communicatie wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="9e2e6-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="9e2e6-125">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e2e6-125">string</span></span> | <span data-ttu-id="9e2e6-126">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="9e2e6-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="9e2e6-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e2e6-127">string</span></span> | <span data-ttu-id="9e2e6-128">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="9e2e6-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="9e2e6-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e2e6-129">string</span></span> | <span data-ttu-id="9e2e6-130">Gebruikersnaam (UPN) van het account</span><span class="sxs-lookup"><span data-stu-id="9e2e6-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="9e2e6-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e2e6-131">string</span></span> | <span data-ttu-id="9e2e6-132">Beveiligings-id (SID) van het account</span><span class="sxs-lookup"><span data-stu-id="9e2e6-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="9e2e6-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e2e6-133">string</span></span> | <span data-ttu-id="9e2e6-134">Unieke id voor het account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="9e2e6-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="9e2e6-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e2e6-135">string</span></span> | <span data-ttu-id="9e2e6-136">Naam van de accountgebruiker die in het adresboek wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9e2e6-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="9e2e6-137">Typisch een combinatie van een bepaalde of voornaam, een middelste initiatie, en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="9e2e6-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="9e2e6-138">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e2e6-138">string</span></span> | <span data-ttu-id="9e2e6-139">Volledig gekwalificeerde domeinnaam (FQDN) van het eindpunt</span><span class="sxs-lookup"><span data-stu-id="9e2e6-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="9e2e6-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e2e6-140">string</span></span> | <span data-ttu-id="9e2e6-141">IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="9e2e6-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="9e2e6-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9e2e6-142">string</span></span> | <span data-ttu-id="9e2e6-143">Stad, land of andere geografische locatie die aan de gebeurtenis is gekoppeld</span><span class="sxs-lookup"><span data-stu-id="9e2e6-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9e2e6-144">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="9e2e6-144">Related topics</span></span>
- [<span data-ttu-id="9e2e6-145">Proactief op zoek naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="9e2e6-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9e2e6-146">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="9e2e6-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9e2e6-147">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="9e2e6-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9e2e6-148">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="9e2e6-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9e2e6-149">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="9e2e6-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9e2e6-150">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="9e2e6-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
