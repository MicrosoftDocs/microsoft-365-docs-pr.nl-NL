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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 6922f50906013cfbfa3bd63c69fff3e89ed46cd5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196819"
---
# <a name="identityinfo"></a><span data-ttu-id="9a699-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="9a699-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9a699-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9a699-105">**Applies to:**</span></span>
- <span data-ttu-id="9a699-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="9a699-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="9a699-107">De `IdentityInfo` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat informatie over gebruikersaccounts die zijn verkregen van diverse services, waaronder Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9a699-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="9a699-108">Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="9a699-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="9a699-109">Naam van de tabel werd gewijzigd `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="9a699-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="9a699-110">Bij hernoemen worden alle query's die zijn opgeslagen in de portal automatisch bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="9a699-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="9a699-111">Controleer de query's die u elders hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="9a699-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="9a699-112">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="9a699-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9a699-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="9a699-113">Column name</span></span> | <span data-ttu-id="9a699-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="9a699-114">Data type</span></span> | <span data-ttu-id="9a699-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="9a699-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="9a699-116">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9a699-116">string</span></span> | <span data-ttu-id="9a699-117">Unieke id voor het account in azure AD</span><span class="sxs-lookup"><span data-stu-id="9a699-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="9a699-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9a699-118">string</span></span> | <span data-ttu-id="9a699-119">UPN (User Principal Name) van het account</span><span class="sxs-lookup"><span data-stu-id="9a699-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="9a699-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9a699-120">string</span></span> | <span data-ttu-id="9a699-121">SID (on-premises Security Identifier) van het account</span><span class="sxs-lookup"><span data-stu-id="9a699-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="9a699-122">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9a699-122">string</span></span> | <span data-ttu-id="9a699-123">Cloud beveiligings-id van het account</span><span class="sxs-lookup"><span data-stu-id="9a699-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="9a699-124">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9a699-124">string</span></span> | <span data-ttu-id="9a699-125">Opgegeven naam of voornaam van de account gebruiker</span><span class="sxs-lookup"><span data-stu-id="9a699-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="9a699-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9a699-126">string</span></span> | <span data-ttu-id="9a699-127">Naam, familienaam of achternaam van de gebruiker van het account</span><span class="sxs-lookup"><span data-stu-id="9a699-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="9a699-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9a699-128">string</span></span> | <span data-ttu-id="9a699-129">Naam van de account gebruiker die in het adresboek wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9a699-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="9a699-130">Meestal een combinatie van een bepaalde of voornaam, een tweede opening en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="9a699-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="9a699-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9a699-131">string</span></span> | <span data-ttu-id="9a699-132">Naam van de afdeling waartoe de account gebruiker behoort</span><span class="sxs-lookup"><span data-stu-id="9a699-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="9a699-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9a699-133">string</span></span> | <span data-ttu-id="9a699-134">Functienaam van de account gebruiker</span><span class="sxs-lookup"><span data-stu-id="9a699-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="9a699-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9a699-135">string</span></span> | <span data-ttu-id="9a699-136">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="9a699-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="9a699-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9a699-137">string</span></span> | <span data-ttu-id="9a699-138">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="9a699-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="9a699-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9a699-139">string</span></span> | <span data-ttu-id="9a699-140">SMTP-adres van het account</span><span class="sxs-lookup"><span data-stu-id="9a699-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="9a699-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9a699-141">string</span></span> | <span data-ttu-id="9a699-142">Voice over IP (VOIP)-adres van het Start Protocol (SIP) van de rekening</span><span class="sxs-lookup"><span data-stu-id="9a699-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="9a699-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9a699-143">string</span></span> | <span data-ttu-id="9a699-144">Plaats waar de account gebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="9a699-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="9a699-145">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="9a699-145">string</span></span> | <span data-ttu-id="9a699-146">Het land of de regio waar het account van de gebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="9a699-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="9a699-147">Boolean</span><span class="sxs-lookup"><span data-stu-id="9a699-147">boolean</span></span> | <span data-ttu-id="9a699-148">Geeft aan of het account is ingeschakeld of niet</span><span class="sxs-lookup"><span data-stu-id="9a699-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9a699-149">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="9a699-149">Related topics</span></span>
- [<span data-ttu-id="9a699-150">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="9a699-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9a699-151">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="9a699-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9a699-152">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="9a699-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9a699-153">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="9a699-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9a699-154">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="9a699-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9a699-155">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="9a699-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
