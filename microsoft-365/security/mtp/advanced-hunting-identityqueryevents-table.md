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
ms.openlocfilehash: bec7f13d49e2ccf4e3a9121d5e5a2fecd1b10aa2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899111"
---
# <a name="identityqueryevents"></a><span data-ttu-id="6eb14-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="6eb14-104">IdentityQueryEvents</span></span>

<span data-ttu-id="6eb14-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6eb14-105">**Applies to:**</span></span>
- <span data-ttu-id="6eb14-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6eb14-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="6eb14-107">De `IdentityQueryEvents` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over query's die zijn uitgevoerd op Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen.</span><span class="sxs-lookup"><span data-stu-id="6eb14-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="6eb14-108">Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="6eb14-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="6eb14-109">Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.</span><span class="sxs-lookup"><span data-stu-id="6eb14-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6eb14-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="6eb14-110">Column name</span></span> | <span data-ttu-id="6eb14-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="6eb14-111">Data type</span></span> | <span data-ttu-id="6eb14-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6eb14-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6eb14-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="6eb14-113">datetime</span></span> | <span data-ttu-id="6eb14-114">Datum en tijdstip waarop de gebeurtenis is geregistreerd</span><span class="sxs-lookup"><span data-stu-id="6eb14-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="6eb14-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb14-115">string</span></span> | <span data-ttu-id="6eb14-116">Type activiteit dat de gebeurtenis heeft geactiveerd</span><span class="sxs-lookup"><span data-stu-id="6eb14-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="6eb14-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb14-117">string</span></span> | <span data-ttu-id="6eb14-118">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="6eb14-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="6eb14-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb14-119">string</span></span> | <span data-ttu-id="6eb14-120">Type query: QueryGroep, QueryUser of EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="6eb14-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="6eb14-121">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb14-121">string</span></span> | <span data-ttu-id="6eb14-122">Naam van de gebruiker, groep, apparaat, domein of een ander entiteitstype dat wordt opgevraagd</span><span class="sxs-lookup"><span data-stu-id="6eb14-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="6eb14-123">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb14-123">string</span></span> | <span data-ttu-id="6eb14-124">Protocol dat tijdens de communicatie wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="6eb14-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="6eb14-125">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb14-125">string</span></span> | <span data-ttu-id="6eb14-126">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="6eb14-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="6eb14-127">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb14-127">string</span></span> | <span data-ttu-id="6eb14-128">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="6eb14-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="6eb14-129">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb14-129">string</span></span> | <span data-ttu-id="6eb14-130">Gebruikersnaam (UPN) van het account</span><span class="sxs-lookup"><span data-stu-id="6eb14-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="6eb14-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb14-131">string</span></span> | <span data-ttu-id="6eb14-132">Beveiligings-id (SID) van het account</span><span class="sxs-lookup"><span data-stu-id="6eb14-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="6eb14-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb14-133">string</span></span> | <span data-ttu-id="6eb14-134">Unieke id voor het account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="6eb14-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="6eb14-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb14-135">string</span></span> | <span data-ttu-id="6eb14-136">Naam van de accountgebruiker die in het adresboek wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6eb14-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="6eb14-137">Typisch een combinatie van een bepaalde of voornaam, een middelste initiatie, en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="6eb14-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="6eb14-138">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb14-138">string</span></span> | <span data-ttu-id="6eb14-139">Volledig gekwalificeerde domeinnaam (FQDN) van het eindpunt</span><span class="sxs-lookup"><span data-stu-id="6eb14-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="6eb14-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb14-140">string</span></span> | <span data-ttu-id="6eb14-141">IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="6eb14-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="6eb14-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6eb14-142">string</span></span> | <span data-ttu-id="6eb14-143">Plaats, land of andere geografische locatie die aan het evenement is gekoppeld</span><span class="sxs-lookup"><span data-stu-id="6eb14-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6eb14-144">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6eb14-144">Related topics</span></span>
- [<span data-ttu-id="6eb14-145">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="6eb14-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6eb14-146">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="6eb14-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6eb14-147">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="6eb14-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6eb14-148">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="6eb14-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6eb14-149">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="6eb14-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6eb14-150">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="6eb14-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
