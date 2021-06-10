---
title: Tabel IdentityInfo in het geavanceerde schema voor de jacht
description: Meer informatie over gebruikersaccountgegevens in de tabel IdentityInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AccountInfo, IdentityInfo, account
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
ms.openlocfilehash: ce1a3d5153d324d008d2d46048838351eb7bc047
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935819"
---
# <a name="identityinfo"></a><span data-ttu-id="da010-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="da010-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="da010-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="da010-105">**Applies to:**</span></span>
- <span data-ttu-id="da010-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da010-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="da010-107">De `IdentityInfo` tabel in het geavanceerde schema [bevat](advanced-hunting-overview.md) informatie over gebruikersaccounts die zijn verkregen uit verschillende services, waaronder Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="da010-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="da010-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="da010-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="da010-109">De naam van deze tabel is gewijzigd in `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="da010-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="da010-110">Tijdens de naamsnoemingen worden alle query's die in de portal zijn opgeslagen, automatisch bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="da010-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="da010-111">Controleer query's die u ergens anders hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="da010-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="da010-112">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="da010-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="da010-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="da010-113">Column name</span></span> | <span data-ttu-id="da010-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="da010-114">Data type</span></span> | <span data-ttu-id="da010-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="da010-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="da010-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da010-116">string</span></span> | <span data-ttu-id="da010-117">Unieke id voor het account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="da010-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="da010-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da010-118">string</span></span> | <span data-ttu-id="da010-119">Gebruikersnaam (UPN) van het account</span><span class="sxs-lookup"><span data-stu-id="da010-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="da010-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da010-120">string</span></span> | <span data-ttu-id="da010-121">On-premises beveiligingsaanduiding (SID) van het account</span><span class="sxs-lookup"><span data-stu-id="da010-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="da010-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da010-122">string</span></span> | <span data-ttu-id="da010-123">Cloudbeveiligingsaanduiding van het account</span><span class="sxs-lookup"><span data-stu-id="da010-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="da010-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da010-124">string</span></span> | <span data-ttu-id="da010-125">Opgegeven naam of voornaam van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="da010-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="da010-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da010-126">string</span></span> | <span data-ttu-id="da010-127">Achternaam, familienaam of achternaam van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="da010-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="da010-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da010-128">string</span></span> | <span data-ttu-id="da010-129">Naam van de accountgebruiker die wordt weergegeven in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="da010-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="da010-130">Meestal een combinatie van een bepaalde of voornaam, een middelste initiatie en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="da010-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="da010-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da010-131">string</span></span> | <span data-ttu-id="da010-132">Naam van de afdeling van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="da010-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="da010-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da010-133">string</span></span> | <span data-ttu-id="da010-134">Functie van de accountgebruiker</span><span class="sxs-lookup"><span data-stu-id="da010-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="da010-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da010-135">string</span></span> | <span data-ttu-id="da010-136">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="da010-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="da010-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da010-137">string</span></span> | <span data-ttu-id="da010-138">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="da010-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="da010-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da010-139">string</span></span> | <span data-ttu-id="da010-140">SMTP-adres van het account</span><span class="sxs-lookup"><span data-stu-id="da010-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="da010-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da010-141">string</span></span> | <span data-ttu-id="da010-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span><span class="sxs-lookup"><span data-stu-id="da010-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="da010-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da010-143">string</span></span> | <span data-ttu-id="da010-144">Plaats waar de accountgebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="da010-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="da010-145">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="da010-145">string</span></span> | <span data-ttu-id="da010-146">Land/regio waar de accountgebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="da010-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="da010-147">booleaanse</span><span class="sxs-lookup"><span data-stu-id="da010-147">boolean</span></span> | <span data-ttu-id="da010-148">Geeft aan of het account is ingeschakeld of niet</span><span class="sxs-lookup"><span data-stu-id="da010-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="da010-149">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="da010-149">Related topics</span></span>
- [<span data-ttu-id="da010-150">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="da010-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="da010-151">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="da010-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="da010-152">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="da010-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="da010-153">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="da010-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="da010-154">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="da010-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="da010-155">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="da010-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
