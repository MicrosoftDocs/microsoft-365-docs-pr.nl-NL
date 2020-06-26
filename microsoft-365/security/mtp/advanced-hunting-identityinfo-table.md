---
title: IdentityInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over gebruikersaccountgegevens in de IdentityInfo-tabel van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, AccountInfo, IdentityInfo, account
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
ms.openlocfilehash: b384e76439ae706520725e7193fa64224b724be0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898955"
---
# <a name="identityinfo"></a><span data-ttu-id="fc349-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="fc349-104">IdentityInfo</span></span>

<span data-ttu-id="fc349-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="fc349-105">**Applies to:**</span></span>
- <span data-ttu-id="fc349-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fc349-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="fc349-107">De `IdentityInfo` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over gebruikersaccounts die zijn verkregen uit verschillende services, waaronder Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc349-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="fc349-108">Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="fc349-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="fc349-109">Deze tabel is hernoemd uit `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="fc349-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="fc349-110">Tijdens de naamswijzigingen worden alle query's die in de portal zijn opgeslagen, automatisch bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="fc349-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="fc349-111">Controleer query's die u elders hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="fc349-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="fc349-112">Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.</span><span class="sxs-lookup"><span data-stu-id="fc349-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="fc349-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="fc349-113">Column name</span></span> | <span data-ttu-id="fc349-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="fc349-114">Data type</span></span> | <span data-ttu-id="fc349-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="fc349-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="fc349-116">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc349-116">string</span></span> | <span data-ttu-id="fc349-117">Unieke id voor het account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="fc349-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="fc349-118">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc349-118">string</span></span> | <span data-ttu-id="fc349-119">Gebruikersnaam (UPN) van het account</span><span class="sxs-lookup"><span data-stu-id="fc349-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="fc349-120">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc349-120">string</span></span> | <span data-ttu-id="fc349-121">On-premises security id (SID) van de rekening</span><span class="sxs-lookup"><span data-stu-id="fc349-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="fc349-122">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc349-122">string</span></span> | <span data-ttu-id="fc349-123">Cloudbeveiligingsidenty-id van het account</span><span class="sxs-lookup"><span data-stu-id="fc349-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="fc349-124">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc349-124">string</span></span> | <span data-ttu-id="fc349-125">Opgegeven naam of voornaam van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="fc349-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="fc349-126">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc349-126">string</span></span> | <span data-ttu-id="fc349-127">Achternaam, familienaam of achternaam van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="fc349-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="fc349-128">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc349-128">string</span></span> | <span data-ttu-id="fc349-129">Naam van de accountgebruiker die in het adresboek wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="fc349-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="fc349-130">Typisch een combinatie van een bepaalde of voornaam, een middelste initiatie, en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="fc349-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="fc349-131">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc349-131">string</span></span> | <span data-ttu-id="fc349-132">Naam van de afdeling waartoe de accountgebruiker behoort</span><span class="sxs-lookup"><span data-stu-id="fc349-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="fc349-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc349-133">string</span></span> | <span data-ttu-id="fc349-134">Functietitel van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="fc349-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="fc349-135">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc349-135">string</span></span> | <span data-ttu-id="fc349-136">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="fc349-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="fc349-137">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc349-137">string</span></span> | <span data-ttu-id="fc349-138">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="fc349-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="fc349-139">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc349-139">string</span></span> | <span data-ttu-id="fc349-140">SMTP-adres van de rekening</span><span class="sxs-lookup"><span data-stu-id="fc349-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="fc349-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc349-141">string</span></span> | <span data-ttu-id="fc349-142">Voice of over IP (VOIP) sessie initiatie protocol (SIP) adres van de rekening</span><span class="sxs-lookup"><span data-stu-id="fc349-142">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="fc349-143">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc349-143">string</span></span> | <span data-ttu-id="fc349-144">Plaats waar de accountgebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="fc349-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="fc349-145">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="fc349-145">string</span></span> | <span data-ttu-id="fc349-146">Land/regio waar de accountgebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="fc349-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="fc349-147">Booleaanse</span><span class="sxs-lookup"><span data-stu-id="fc349-147">boolean</span></span> | <span data-ttu-id="fc349-148">Geeft aan of het account is ingeschakeld of niet</span><span class="sxs-lookup"><span data-stu-id="fc349-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="fc349-149">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="fc349-149">Related topics</span></span>
- [<span data-ttu-id="fc349-150">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="fc349-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fc349-151">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="fc349-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fc349-152">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="fc349-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fc349-153">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="fc349-153">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="fc349-154">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="fc349-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fc349-155">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="fc349-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
