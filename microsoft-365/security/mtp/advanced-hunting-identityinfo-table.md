---
title: IdentityInfo tabel in het geavanceerde jachtschema
description: Meer informatie over gebruikersaccountgegevens in de tabel IdentityInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, AccountInfo, IdentityInfo, account
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
ms.openlocfilehash: 12f8d0995d00daffe8a1ca1c2c8d9dfe25a11581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209773"
---
# <a name="identityinfo"></a><span data-ttu-id="3fe87-104">Identiteitsinfo</span><span class="sxs-lookup"><span data-stu-id="3fe87-104">IdentityInfo</span></span>

<span data-ttu-id="3fe87-105">**Geldt voor:**</span><span class="sxs-lookup"><span data-stu-id="3fe87-105">**Applies to:**</span></span>
- <span data-ttu-id="3fe87-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3fe87-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="3fe87-107">De `IdentityInfo` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over gebruikersaccounts die zijn verkregen uit verschillende services, waaronder Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3fe87-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="3fe87-108">Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="3fe87-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="3fe87-109">Deze tabel is hernoemd van `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="3fe87-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="3fe87-110">Tijdens het hernoemen worden alle query's die in de portal zijn opgeslagen, automatisch bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="3fe87-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="3fe87-111">Controleer query's die u elders hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="3fe87-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="3fe87-112">Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="3fe87-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3fe87-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="3fe87-113">Column name</span></span> | <span data-ttu-id="3fe87-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="3fe87-114">Data type</span></span> | <span data-ttu-id="3fe87-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3fe87-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="3fe87-116">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3fe87-116">string</span></span> | <span data-ttu-id="3fe87-117">Unieke id voor het account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="3fe87-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="3fe87-118">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3fe87-118">string</span></span> | <span data-ttu-id="3fe87-119">Gebruikersnaam (UPN) van het account</span><span class="sxs-lookup"><span data-stu-id="3fe87-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="3fe87-120">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3fe87-120">string</span></span> | <span data-ttu-id="3fe87-121">On-premises beveiligingsidentificatie (SID) van de rekening</span><span class="sxs-lookup"><span data-stu-id="3fe87-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="3fe87-122">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3fe87-122">string</span></span> | <span data-ttu-id="3fe87-123">Cloudbeveiligings-id van het account</span><span class="sxs-lookup"><span data-stu-id="3fe87-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="3fe87-124">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3fe87-124">string</span></span> | <span data-ttu-id="3fe87-125">Voornaam of voornaam van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="3fe87-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="3fe87-126">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3fe87-126">string</span></span> | <span data-ttu-id="3fe87-127">Achternaam, familienaam of achternaam van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="3fe87-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="3fe87-128">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3fe87-128">string</span></span> | <span data-ttu-id="3fe87-129">Naam van de accountgebruiker die in het adresboek wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3fe87-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="3fe87-130">Typisch een combinatie van een bepaalde of voornaam, een middelste initiatie, en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="3fe87-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="3fe87-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3fe87-131">string</span></span> | <span data-ttu-id="3fe87-132">Naam van de afdeling waartoe de accountgebruiker behoort</span><span class="sxs-lookup"><span data-stu-id="3fe87-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="3fe87-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3fe87-133">string</span></span> | <span data-ttu-id="3fe87-134">Functietitel van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="3fe87-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="3fe87-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3fe87-135">string</span></span> | <span data-ttu-id="3fe87-136">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="3fe87-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="3fe87-137">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3fe87-137">string</span></span> | <span data-ttu-id="3fe87-138">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="3fe87-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="3fe87-139">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3fe87-139">string</span></span> | <span data-ttu-id="3fe87-140">SMTP-adres van het account</span><span class="sxs-lookup"><span data-stu-id="3fe87-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="3fe87-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3fe87-141">string</span></span> | <span data-ttu-id="3fe87-142">Voice of over IP (VOIP) sessie initiatie protocol (SIP) adres van het account</span><span class="sxs-lookup"><span data-stu-id="3fe87-142">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="3fe87-143">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3fe87-143">string</span></span> | <span data-ttu-id="3fe87-144">Plaats waar de accountgebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="3fe87-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="3fe87-145">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="3fe87-145">string</span></span> | <span data-ttu-id="3fe87-146">Land/regio waar de accountgebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="3fe87-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="3fe87-147">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="3fe87-147">boolean</span></span> | <span data-ttu-id="3fe87-148">Geeft aan of het account is ingeschakeld of niet</span><span class="sxs-lookup"><span data-stu-id="3fe87-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3fe87-149">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="3fe87-149">Related topics</span></span>
- [<span data-ttu-id="3fe87-150">Proactief op zoek naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="3fe87-150">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3fe87-151">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="3fe87-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3fe87-152">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="3fe87-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3fe87-153">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="3fe87-153">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3fe87-154">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="3fe87-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3fe87-155">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="3fe87-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
