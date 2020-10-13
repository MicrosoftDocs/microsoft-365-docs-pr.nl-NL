---
title: IdentityInfo-tabel in het geavanceerde jacht schema
description: Meer informatie over gegevens van gebruikersaccounts in de tabel IdentityInfo van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, AccountInfo, IdentityInfo, account
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 38a7e6600c682b1edef5320ef4de296b5943952d
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430477"
---
# <a name="identityinfo"></a><span data-ttu-id="2853e-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="2853e-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2853e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2853e-105">**Applies to:**</span></span>
- <span data-ttu-id="2853e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2853e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2853e-107">De `IdentityInfo` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat informatie over gebruikersaccounts die zijn verkregen van diverse services, waaronder Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2853e-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="2853e-108">Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="2853e-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="2853e-109">Naam van de tabel werd gewijzigd `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="2853e-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="2853e-110">Bij hernoemen worden alle query's die zijn opgeslagen in de portal automatisch bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="2853e-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="2853e-111">Controleer de query's die u elders hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="2853e-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="2853e-112">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="2853e-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2853e-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="2853e-113">Column name</span></span> | <span data-ttu-id="2853e-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="2853e-114">Data type</span></span> | <span data-ttu-id="2853e-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2853e-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="2853e-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2853e-116">string</span></span> | <span data-ttu-id="2853e-117">Unieke id voor het account in azure AD</span><span class="sxs-lookup"><span data-stu-id="2853e-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="2853e-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2853e-118">string</span></span> | <span data-ttu-id="2853e-119">UPN (User Principal Name) van het account</span><span class="sxs-lookup"><span data-stu-id="2853e-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="2853e-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2853e-120">string</span></span> | <span data-ttu-id="2853e-121">SID (on-premises Security Identifier) van het account</span><span class="sxs-lookup"><span data-stu-id="2853e-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="2853e-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2853e-122">string</span></span> | <span data-ttu-id="2853e-123">Cloud beveiligings-id van het account</span><span class="sxs-lookup"><span data-stu-id="2853e-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="2853e-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2853e-124">string</span></span> | <span data-ttu-id="2853e-125">Opgegeven naam of voornaam van de account gebruiker</span><span class="sxs-lookup"><span data-stu-id="2853e-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="2853e-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2853e-126">string</span></span> | <span data-ttu-id="2853e-127">Naam, familienaam of achternaam van de gebruiker van het account</span><span class="sxs-lookup"><span data-stu-id="2853e-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="2853e-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2853e-128">string</span></span> | <span data-ttu-id="2853e-129">Naam van de account gebruiker die in het adresboek wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2853e-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="2853e-130">Meestal een combinatie van een bepaalde of voornaam, een tweede opening en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="2853e-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="2853e-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2853e-131">string</span></span> | <span data-ttu-id="2853e-132">Naam van de afdeling waartoe de account gebruiker behoort</span><span class="sxs-lookup"><span data-stu-id="2853e-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="2853e-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2853e-133">string</span></span> | <span data-ttu-id="2853e-134">Functienaam van de account gebruiker</span><span class="sxs-lookup"><span data-stu-id="2853e-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="2853e-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2853e-135">string</span></span> | <span data-ttu-id="2853e-136">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="2853e-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="2853e-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2853e-137">string</span></span> | <span data-ttu-id="2853e-138">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="2853e-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="2853e-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2853e-139">string</span></span> | <span data-ttu-id="2853e-140">SMTP-adres van het account</span><span class="sxs-lookup"><span data-stu-id="2853e-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="2853e-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2853e-141">string</span></span> | <span data-ttu-id="2853e-142">Voice over IP (VOIP)-adres van het Start Protocol (SIP) van de rekening</span><span class="sxs-lookup"><span data-stu-id="2853e-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="2853e-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2853e-143">string</span></span> | <span data-ttu-id="2853e-144">Plaats waar de account gebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="2853e-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="2853e-145">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2853e-145">string</span></span> | <span data-ttu-id="2853e-146">Het land of de regio waar het account van de gebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="2853e-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="2853e-147">Boolean</span><span class="sxs-lookup"><span data-stu-id="2853e-147">boolean</span></span> | <span data-ttu-id="2853e-148">Geeft aan of het account is ingeschakeld of niet</span><span class="sxs-lookup"><span data-stu-id="2853e-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2853e-149">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2853e-149">Related topics</span></span>
- [<span data-ttu-id="2853e-150">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="2853e-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2853e-151">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="2853e-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2853e-152">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="2853e-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2853e-153">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="2853e-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2853e-154">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="2853e-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2853e-155">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="2853e-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
