---
title: AccountInfo tabel in het geavanceerde jachtschema
description: Meer informatie over gebruikersaccountgegevens in de accountinfo-tabel van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, AlertInfo, alert, entiteiten, bewijs, bestand, IP-adres, apparaat, machine, gebruiker, account
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
ms.openlocfilehash: 9e4503ab297c7a584a548faa36ca6102c1b8dda6
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929526"
---
# <a name="accountinfo"></a><span data-ttu-id="7e3e0-104">Rekeninginfo</span><span class="sxs-lookup"><span data-stu-id="7e3e0-104">AccountInfo</span></span>

<span data-ttu-id="7e3e0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7e3e0-105">**Applies to:**</span></span>
- <span data-ttu-id="7e3e0-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="7e3e0-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="7e3e0-107">De `AccountInfo` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over gebruikersaccounts die zijn verkregen uit verschillende services, waaronder Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7e3e0-107">The `AccountInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="7e3e0-108">Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="7e3e0-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="7e3e0-109">Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7e3e0-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7e3e0-110">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="7e3e0-110">Column name</span></span> | <span data-ttu-id="7e3e0-111">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="7e3e0-111">Data type</span></span> | <span data-ttu-id="7e3e0-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="7e3e0-112">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="7e3e0-113">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7e3e0-113">string</span></span> | <span data-ttu-id="7e3e0-114">Unieke id voor het account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="7e3e0-114">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="7e3e0-115">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7e3e0-115">string</span></span> | <span data-ttu-id="7e3e0-116">Gebruikersnaam (UPN) van het account</span><span class="sxs-lookup"><span data-stu-id="7e3e0-116">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="7e3e0-117">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7e3e0-117">string</span></span> | <span data-ttu-id="7e3e0-118">On-premises beveiligingsidentificatie (SID) van de rekening</span><span class="sxs-lookup"><span data-stu-id="7e3e0-118">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="7e3e0-119">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7e3e0-119">string</span></span> | <span data-ttu-id="7e3e0-120">Cloudbeveiligings-id van het account</span><span class="sxs-lookup"><span data-stu-id="7e3e0-120">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="7e3e0-121">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7e3e0-121">string</span></span> | <span data-ttu-id="7e3e0-122">Voornaam of voornaam van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="7e3e0-122">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="7e3e0-123">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7e3e0-123">string</span></span> | <span data-ttu-id="7e3e0-124">Achternaam, familienaam of achternaam van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="7e3e0-124">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="7e3e0-125">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7e3e0-125">string</span></span> | <span data-ttu-id="7e3e0-126">Naam van de accountgebruiker die in het adresboek wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7e3e0-126">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="7e3e0-127">Typisch een combinatie van een bepaalde of voornaam, een middelste initiatie, en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="7e3e0-127">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="7e3e0-128">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7e3e0-128">string</span></span> | <span data-ttu-id="7e3e0-129">Naam van de afdeling waartoe de accountgebruiker behoort</span><span class="sxs-lookup"><span data-stu-id="7e3e0-129">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="7e3e0-130">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7e3e0-130">string</span></span> | <span data-ttu-id="7e3e0-131">Functietitel van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="7e3e0-131">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="7e3e0-132">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7e3e0-132">string</span></span> | <span data-ttu-id="7e3e0-133">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="7e3e0-133">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="7e3e0-134">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7e3e0-134">string</span></span> | <span data-ttu-id="7e3e0-135">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="7e3e0-135">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="7e3e0-136">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7e3e0-136">string</span></span> | <span data-ttu-id="7e3e0-137">SMTP-adres van het account</span><span class="sxs-lookup"><span data-stu-id="7e3e0-137">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="7e3e0-138">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7e3e0-138">string</span></span> | <span data-ttu-id="7e3e0-139">Voice of over IP (VOIP) sessie initiatie protocol (SIP) adres van het account</span><span class="sxs-lookup"><span data-stu-id="7e3e0-139">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="7e3e0-140">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7e3e0-140">string</span></span> | <span data-ttu-id="7e3e0-141">Plaats waar de accountgebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="7e3e0-141">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="7e3e0-142">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7e3e0-142">string</span></span> | <span data-ttu-id="7e3e0-143">Land/regio waar de accountgebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="7e3e0-143">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="7e3e0-144">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="7e3e0-144">boolean</span></span> | <span data-ttu-id="7e3e0-145">Geeft aan of het account is ingeschakeld of niet</span><span class="sxs-lookup"><span data-stu-id="7e3e0-145">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7e3e0-146">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7e3e0-146">Related topics</span></span>
- [<span data-ttu-id="7e3e0-147">Proactief op zoek naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="7e3e0-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7e3e0-148">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="7e3e0-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7e3e0-149">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="7e3e0-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7e3e0-150">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="7e3e0-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7e3e0-151">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="7e3e0-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7e3e0-152">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="7e3e0-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
