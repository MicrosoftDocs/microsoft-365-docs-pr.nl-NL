---
title: Tabel IdentityInfo in het geavanceerde schema voor zoeken
description: Meer informatie over gebruikersaccountgegevens in de tabel IdentityInfo van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AccountInfo, IdentityInfo, account
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
ms.openlocfilehash: 6604e6d48e277e840b87ddc461580bcb69dd1bc7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929908"
---
# <a name="identityinfo"></a><span data-ttu-id="200c8-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="200c8-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="200c8-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="200c8-105">**Applies to:**</span></span>
- <span data-ttu-id="200c8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="200c8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="200c8-107">De `IdentityInfo` tabel in het geavanceerde [zoekschema](advanced-hunting-overview.md) bevat informatie over gebruikersaccounts die zijn verkregen uit diverse services, waaronder Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="200c8-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="200c8-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="200c8-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="200c8-109">De naam van deze tabel is `AccountInfo` gewijzigd in .</span><span class="sxs-lookup"><span data-stu-id="200c8-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="200c8-110">Tijdens het wijzigen van namen worden alle query's die zijn opgeslagen in de portal, automatisch bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="200c8-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="200c8-111">Controleer de query's die u ergens anders hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="200c8-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="200c8-112">Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="200c8-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="200c8-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="200c8-113">Column name</span></span> | <span data-ttu-id="200c8-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="200c8-114">Data type</span></span> | <span data-ttu-id="200c8-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="200c8-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="200c8-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="200c8-116">string</span></span> | <span data-ttu-id="200c8-117">Unieke id voor het account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="200c8-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="200c8-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="200c8-118">string</span></span> | <span data-ttu-id="200c8-119">UPN (User Principal Name) van het account</span><span class="sxs-lookup"><span data-stu-id="200c8-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="200c8-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="200c8-120">string</span></span> | <span data-ttu-id="200c8-121">On-premises beveiligings-id (SID) van het account</span><span class="sxs-lookup"><span data-stu-id="200c8-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="200c8-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="200c8-122">string</span></span> | <span data-ttu-id="200c8-123">Cloudbeveiligings-id van het account</span><span class="sxs-lookup"><span data-stu-id="200c8-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="200c8-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="200c8-124">string</span></span> | <span data-ttu-id="200c8-125">Gegeven naam of voornaam van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="200c8-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="200c8-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="200c8-126">string</span></span> | <span data-ttu-id="200c8-127">Achternaam, familienaam of achternaam van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="200c8-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="200c8-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="200c8-128">string</span></span> | <span data-ttu-id="200c8-129">De naam van de accountgebruiker die wordt weergegeven in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="200c8-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="200c8-130">Meestal een combinatie van een bepaalde of voornaam, een middelste start en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="200c8-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="200c8-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="200c8-131">string</span></span> | <span data-ttu-id="200c8-132">Naam van de afdeling van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="200c8-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="200c8-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="200c8-133">string</span></span> | <span data-ttu-id="200c8-134">Functie van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="200c8-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="200c8-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="200c8-135">string</span></span> | <span data-ttu-id="200c8-136">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="200c8-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="200c8-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="200c8-137">string</span></span> | <span data-ttu-id="200c8-138">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="200c8-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="200c8-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="200c8-139">string</span></span> | <span data-ttu-id="200c8-140">SMTP-adres van het account</span><span class="sxs-lookup"><span data-stu-id="200c8-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="200c8-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="200c8-141">string</span></span> | <span data-ttu-id="200c8-142">VOIP-adres (Voice over IP) voor DE SIP-sessie (Session Initiation Protocol) van het account</span><span class="sxs-lookup"><span data-stu-id="200c8-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="200c8-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="200c8-143">string</span></span> | <span data-ttu-id="200c8-144">Plaats waar de accountgebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="200c8-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="200c8-145">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="200c8-145">string</span></span> | <span data-ttu-id="200c8-146">Land/regio waar de accountgebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="200c8-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="200c8-147">boolean</span><span class="sxs-lookup"><span data-stu-id="200c8-147">boolean</span></span> | <span data-ttu-id="200c8-148">Geeft aan of het account is ingeschakeld of niet</span><span class="sxs-lookup"><span data-stu-id="200c8-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="200c8-149">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="200c8-149">Related topics</span></span>
- [<span data-ttu-id="200c8-150">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="200c8-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="200c8-151">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="200c8-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="200c8-152">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="200c8-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="200c8-153">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="200c8-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="200c8-154">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="200c8-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="200c8-155">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="200c8-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
