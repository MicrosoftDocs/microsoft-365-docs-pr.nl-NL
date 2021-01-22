---
title: De tabel IdentityDirectoryEvents in het geavanceerde schema voor zoeken
description: Meer informatie over domeincontroller- en Active Directory-gebeurtenissen in de tabel IdentityDirectoryEvents van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityDirectoryEvents, domain controller, Active Directory, Azure ATP, identities
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
ms.openlocfilehash: 95090b0f4abe0b0f0552c81495936f4f2261cf8e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929932"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="f505b-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="f505b-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f505b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f505b-105">**Applies to:**</span></span>
- <span data-ttu-id="f505b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f505b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f505b-107">De tabel in het geavanceerde zoekschema bevat gebeurtenissen waarbij een `IdentityDirectoryEvents` on-premises [](advanced-hunting-overview.md) domeincontroller met Active Directory (AD) wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="f505b-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="f505b-108">Deze tabel legt diverse identiteitsgerelateerde gebeurtenissen vast, zoals wachtwoordwijzigingen, wachtwoordverloop en UPN-wijzigingen (User Principal Name).</span><span class="sxs-lookup"><span data-stu-id="f505b-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="f505b-109">Het legt ook systeemgebeurtenissen vast op de domeincontroller, zoals het plannen van taken en PowerShell-activiteit.</span><span class="sxs-lookup"><span data-stu-id="f505b-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="f505b-110">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="f505b-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="f505b-111">Voor gedetailleerde informatie over de gebeurtenistypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` [ingebouwde schemaverwijzing in](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) het beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="f505b-111">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="f505b-112">Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="f505b-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f505b-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="f505b-113">Column name</span></span> | <span data-ttu-id="f505b-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="f505b-114">Data type</span></span> | <span data-ttu-id="f505b-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="f505b-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f505b-116">datetime</span><span class="sxs-lookup"><span data-stu-id="f505b-116">datetime</span></span> | <span data-ttu-id="f505b-117">Datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="f505b-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="f505b-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-118">string</span></span> | <span data-ttu-id="f505b-119">Het type activiteit dat de gebeurtenis heeft geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="f505b-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="f505b-120">Zie de [schemaverwijzing in de portal voor](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) meer informatie</span><span class="sxs-lookup"><span data-stu-id="f505b-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="f505b-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-121">string</span></span> | <span data-ttu-id="f505b-122">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="f505b-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="f505b-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-123">string</span></span> | <span data-ttu-id="f505b-124">UPN (User Principal Name) van het account waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="f505b-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="f505b-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-125">string</span></span> | <span data-ttu-id="f505b-126">Weergavenaam van het account waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="f505b-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="f505b-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-127">string</span></span> | <span data-ttu-id="f505b-128">FQDN (Fully Qualified Domain Name) van het apparaat waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="f505b-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="f505b-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-129">string</span></span> | <span data-ttu-id="f505b-130">Naam van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="f505b-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="f505b-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-131">string</span></span> | <span data-ttu-id="f505b-132">Het IP-adres van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="f505b-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="f505b-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-133">string</span></span> | <span data-ttu-id="f505b-134">Bestemmingspoort van de activiteit</span><span class="sxs-lookup"><span data-stu-id="f505b-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="f505b-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-135">string</span></span> | <span data-ttu-id="f505b-136">Protocol dat is gebruikt tijdens de communicatie</span><span class="sxs-lookup"><span data-stu-id="f505b-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="f505b-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-137">string</span></span> | <span data-ttu-id="f505b-138">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="f505b-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="f505b-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-139">string</span></span> | <span data-ttu-id="f505b-140">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="f505b-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="f505b-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-141">string</span></span> | <span data-ttu-id="f505b-142">UPN (User Principal Name) van het account</span><span class="sxs-lookup"><span data-stu-id="f505b-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="f505b-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-143">string</span></span> | <span data-ttu-id="f505b-144">Security Identifier (SID) van het account</span><span class="sxs-lookup"><span data-stu-id="f505b-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="f505b-145">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-145">string</span></span> | <span data-ttu-id="f505b-146">Unieke id voor het account in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f505b-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="f505b-147">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-147">string</span></span> | <span data-ttu-id="f505b-148">De naam van de accountgebruiker die wordt weergegeven in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="f505b-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="f505b-149">Meestal een combinatie van een bepaalde of voornaam, een middelste start en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="f505b-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="f505b-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-150">string</span></span> | <span data-ttu-id="f505b-151">FQDN (Fully Qualified Domain Name) van het apparaat</span><span class="sxs-lookup"><span data-stu-id="f505b-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="f505b-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-152">string</span></span> | <span data-ttu-id="f505b-153">IP-adres dat tijdens communicatie aan het apparaat is toegewezen</span><span class="sxs-lookup"><span data-stu-id="f505b-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="f505b-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-154">string</span></span> | <span data-ttu-id="f505b-155">TCP-poort gebruikt tijdens communicatie</span><span class="sxs-lookup"><span data-stu-id="f505b-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="f505b-156">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-156">string</span></span> | <span data-ttu-id="f505b-157">Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="f505b-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="f505b-158">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-158">string</span></span> | <span data-ttu-id="f505b-159">Internetprovider die is gekoppeld aan het IP-adres</span><span class="sxs-lookup"><span data-stu-id="f505b-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="f505b-160">lang</span><span class="sxs-lookup"><span data-stu-id="f505b-160">long</span></span> | <span data-ttu-id="f505b-161">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="f505b-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="f505b-162">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f505b-162">string</span></span> | <span data-ttu-id="f505b-163">Aanvullende informatie over de entiteit of gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="f505b-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f505b-164">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f505b-164">Related topics</span></span>
- [<span data-ttu-id="f505b-165">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="f505b-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f505b-166">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="f505b-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f505b-167">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="f505b-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f505b-168">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="f505b-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f505b-169">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="f505b-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f505b-170">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="f505b-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
