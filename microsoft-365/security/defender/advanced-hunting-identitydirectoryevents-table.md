---
title: Tabel IdentityDirectoryEvents in het geavanceerde schema voor de jacht
description: Meer informatie over domeincontrollers en Active Directory-gebeurtenissen in de tabel IdentityDirectoryEvents van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, IdentityDirectoryEvents, domain controller, Active Directory, Azure ATP, identits
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
ms.openlocfilehash: 73018bb65c011d10234ec9c02fc61bfb93fa125a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501134"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="79156-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="79156-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="79156-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="79156-105">**Applies to:**</span></span>
- <span data-ttu-id="79156-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="79156-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="79156-107">De tabel in het geavanceerde schema bevat gebeurtenissen met een `IdentityDirectoryEvents` on-premises [](advanced-hunting-overview.md) domeincontroller met Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="79156-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="79156-108">Deze tabel legt verschillende identiteitsgerelateerde gebeurtenissen vast, zoals wachtwoordwijzigingen, wachtwoordverloop en upn-wijzigingen (User Principal Name).</span><span class="sxs-lookup"><span data-stu-id="79156-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="79156-109">Ook worden systeemgebeurtenissen op de domeincontroller vastge leggen, zoals het plannen van taken en PowerShell-activiteiten.</span><span class="sxs-lookup"><span data-stu-id="79156-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="79156-110">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="79156-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="79156-111">Voor gedetailleerde informatie over de gebeurtenissentypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing die beschikbaar is in het beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="79156-111">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="79156-112">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="79156-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="79156-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="79156-113">Column name</span></span> | <span data-ttu-id="79156-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="79156-114">Data type</span></span> | <span data-ttu-id="79156-115">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="79156-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="79156-116">datetime</span><span class="sxs-lookup"><span data-stu-id="79156-116">datetime</span></span> | <span data-ttu-id="79156-117">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="79156-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="79156-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-118">string</span></span> | <span data-ttu-id="79156-119">Type activiteit dat de gebeurtenis heeft geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="79156-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="79156-120">Zie de [in-portal schemaverwijzing voor](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) meer informatie</span><span class="sxs-lookup"><span data-stu-id="79156-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="79156-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-121">string</span></span> | <span data-ttu-id="79156-122">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="79156-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="79156-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-123">string</span></span> | <span data-ttu-id="79156-124">User principal name (UPN) of the account that the recorded action was applied to</span><span class="sxs-lookup"><span data-stu-id="79156-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="79156-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-125">string</span></span> | <span data-ttu-id="79156-126">Weergavenaam van het account waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="79156-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="79156-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-127">string</span></span> | <span data-ttu-id="79156-128">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat waar de opgenomen actie op is toegepast</span><span class="sxs-lookup"><span data-stu-id="79156-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="79156-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-129">string</span></span> | <span data-ttu-id="79156-130">Naam van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="79156-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="79156-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-131">string</span></span> | <span data-ttu-id="79156-132">IP-adres van het apparaat met de servertoepassing die de opgenomen actie heeft verwerkt</span><span class="sxs-lookup"><span data-stu-id="79156-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="79156-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-133">string</span></span> | <span data-ttu-id="79156-134">Bestemmingspoort van de activiteit</span><span class="sxs-lookup"><span data-stu-id="79156-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="79156-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-135">string</span></span> | <span data-ttu-id="79156-136">Protocol dat tijdens de communicatie wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="79156-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="79156-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-137">string</span></span> | <span data-ttu-id="79156-138">Gebruikersnaam van het account</span><span class="sxs-lookup"><span data-stu-id="79156-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="79156-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-139">string</span></span> | <span data-ttu-id="79156-140">Domein van het account</span><span class="sxs-lookup"><span data-stu-id="79156-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="79156-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-141">string</span></span> | <span data-ttu-id="79156-142">Gebruikersnaam (UPN) van het account</span><span class="sxs-lookup"><span data-stu-id="79156-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="79156-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-143">string</span></span> | <span data-ttu-id="79156-144">Beveiligings-id (SID) van het account</span><span class="sxs-lookup"><span data-stu-id="79156-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="79156-145">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-145">string</span></span> | <span data-ttu-id="79156-146">Unieke id voor het account in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="79156-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="79156-147">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-147">string</span></span> | <span data-ttu-id="79156-148">Naam van de accountgebruiker die wordt weergegeven in het adresboek.</span><span class="sxs-lookup"><span data-stu-id="79156-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="79156-149">Meestal een combinatie van een bepaalde of voornaam, een middelste initiatie en een achternaam of achternaam.</span><span class="sxs-lookup"><span data-stu-id="79156-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="79156-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-150">string</span></span> | <span data-ttu-id="79156-151">Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat</span><span class="sxs-lookup"><span data-stu-id="79156-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="79156-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-152">string</span></span> | <span data-ttu-id="79156-153">IP-adres dat tijdens communicatie aan het apparaat is toegewezen</span><span class="sxs-lookup"><span data-stu-id="79156-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="79156-154">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-154">string</span></span> | <span data-ttu-id="79156-155">TCP-poort die tijdens communicatie wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="79156-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="79156-156">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-156">string</span></span> | <span data-ttu-id="79156-157">Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="79156-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="79156-158">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-158">string</span></span> | <span data-ttu-id="79156-159">Internetprovider die is gekoppeld aan het IP-adres</span><span class="sxs-lookup"><span data-stu-id="79156-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="79156-160">lang</span><span class="sxs-lookup"><span data-stu-id="79156-160">long</span></span> | <span data-ttu-id="79156-161">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="79156-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="79156-162">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="79156-162">string</span></span> | <span data-ttu-id="79156-163">Aanvullende informatie over de entiteit of gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="79156-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="79156-164">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="79156-164">Related topics</span></span>
- [<span data-ttu-id="79156-165">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="79156-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="79156-166">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="79156-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="79156-167">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="79156-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="79156-168">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="79156-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="79156-169">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="79156-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="79156-170">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="79156-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
