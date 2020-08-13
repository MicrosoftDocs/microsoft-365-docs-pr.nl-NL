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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: cf2038a15242139817eb073ec2a6408905824123
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649317"
---
# <a name="identityqueryevents"></a><span data-ttu-id="b4d80-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="b4d80-104">IdentityQueryEvents</span></span>

<span data-ttu-id="b4d80-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b4d80-105">**Applies to:**</span></span>
- <span data-ttu-id="b4d80-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b4d80-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b4d80-107">De `IdentityQueryEvents` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat informatie over query's die zijn uitgevoerd voor Active Directory-objecten, zoals gebruikers, groepen, apparaten en domeinen.</span><span class="sxs-lookup"><span data-stu-id="b4d80-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="b4d80-108">Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="b4d80-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="b4d80-109">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="b4d80-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b4d80-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="b4d80-110">Column name</span></span> | <span data-ttu-id="b4d80-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="b4d80-111">Data type</span></span> | <span data-ttu-id="b4d80-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b4d80-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b4d80-113">tijd</span><span class="sxs-lookup"><span data-stu-id="b4d80-113">datetime</span></span> | <span data-ttu-id="b4d80-114">De datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="b4d80-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="b4d80-115">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-115">string</span></span> | <span data-ttu-id="b4d80-116">Type activiteit waarmee de gebeurtenis wordt geactiveerd</span><span class="sxs-lookup"><span data-stu-id="b4d80-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="b4d80-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-117">string</span></span> | <span data-ttu-id="b4d80-118">De toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="b4d80-118">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="b4d80-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-119">string</span></span> | <span data-ttu-id="b4d80-120">Type query, zoals QueryGroup, QueryUser of EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="b4d80-120">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="b4d80-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-121">string</span></span> | <span data-ttu-id="b4d80-122">De naam van de gebruiker, groep, het apparaat, het domein of een ander entiteitstype dat wordt opgevraagd</span><span class="sxs-lookup"><span data-stu-id="b4d80-122">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="b4d80-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-123">string</span></span> | <span data-ttu-id="b4d80-124">Tekenreeks die wordt gebruikt om de query uit te voeren</span><span class="sxs-lookup"><span data-stu-id="b4d80-124">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="b4d80-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-125">string</span></span> | <span data-ttu-id="b4d80-126">Gebruikte protocol tijdens de communicatie</span><span class="sxs-lookup"><span data-stu-id="b4d80-126">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="b4d80-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-127">string</span></span> | <span data-ttu-id="b4d80-128">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="b4d80-128">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="b4d80-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-129">string</span></span> | <span data-ttu-id="b4d80-130">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="b4d80-130">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="b4d80-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-131">string</span></span> | <span data-ttu-id="b4d80-132">UPN (User Principal Name) van het account</span><span class="sxs-lookup"><span data-stu-id="b4d80-132">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="b4d80-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-133">string</span></span> | <span data-ttu-id="b4d80-134">SID (Security Identifier) van het account</span><span class="sxs-lookup"><span data-stu-id="b4d80-134">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="b4d80-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-135">string</span></span> | <span data-ttu-id="b4d80-136">Unieke id voor het account in azure AD</span><span class="sxs-lookup"><span data-stu-id="b4d80-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="b4d80-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-137">string</span></span> | <span data-ttu-id="b4d80-138">Naam van de account gebruiker die in het adresboek wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b4d80-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="b4d80-139">Meestal een combinatie van een bepaalde of voornaam, een tweede opening en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="b4d80-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="b4d80-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-140">string</span></span> | <span data-ttu-id="b4d80-141">FQDN-naam (Fully Qualified Domain Name) van het eindpunt</span><span class="sxs-lookup"><span data-stu-id="b4d80-141">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="b4d80-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-142">string</span></span> | <span data-ttu-id="b4d80-143">Het IP-adres dat is toegewezen aan het eindpunt en die wordt gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="b4d80-143">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="b4d80-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-144">string</span></span> | <span data-ttu-id="b4d80-145">Naam van het apparaat waarop de servertoepassing wordt uitgevoerd die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="b4d80-145">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="b4d80-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-146">string</span></span> | <span data-ttu-id="b4d80-147">IP-adres van het apparaat waarop de servertoepassing wordt uitgevoerd die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="b4d80-147">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="b4d80-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-148">string</span></span> | <span data-ttu-id="b4d80-149">FQDN-naam (Fully Qualified Domain Name) van het apparaat waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="b4d80-149">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="b4d80-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-150">string</span></span> | <span data-ttu-id="b4d80-151">De UPN (User Principal Name) van het account waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="b4d80-151">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="b4d80-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-152">string</span></span> | <span data-ttu-id="b4d80-153">Weergavenaam van het account waarop de opgenomen actie is toegepast</span><span class="sxs-lookup"><span data-stu-id="b4d80-153">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="b4d80-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-154">string</span></span> | <span data-ttu-id="b4d80-155">Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="b4d80-155">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="b4d80-156">lang</span><span class="sxs-lookup"><span data-stu-id="b4d80-156">long</span></span> | <span data-ttu-id="b4d80-157">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="b4d80-157">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="b4d80-158">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b4d80-158">string</span></span> | <span data-ttu-id="b4d80-159">Aanvullende informatie over de entiteit of gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="b4d80-159">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b4d80-160">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b4d80-160">Related topics</span></span>
- [<span data-ttu-id="b4d80-161">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b4d80-161">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b4d80-162">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="b4d80-162">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b4d80-163">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="b4d80-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b4d80-164">Jacht op apparaten, e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="b4d80-164">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b4d80-165">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="b4d80-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b4d80-166">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="b4d80-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
