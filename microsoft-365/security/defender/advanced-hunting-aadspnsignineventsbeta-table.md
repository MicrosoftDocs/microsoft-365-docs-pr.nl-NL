---
title: AADSpnSignInEventsBeta-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over informatie die is gekoppeld aan Azure Active Directory en de tabel met beheerde identiteitsgegevens van het geavanceerde schema voor het zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account, identity, AAD
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
ms.openlocfilehash: f74972bcd5d0ddaab58d82b72a55991fda44e3b1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583542"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="bb8a2-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="bb8a2-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="bb8a2-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bb8a2-105">**Applies to:**</span></span>

- <span data-ttu-id="bb8a2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb8a2-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="bb8a2-107">De tabel is momenteel in bètaversie en wordt op korte termijn aangeboden, zodat u kunt zoeken in `AADSpnSignInEventsBeta` Azure Active Directory (AAD) service principal en managed identity sign-in events.</span><span class="sxs-lookup"><span data-stu-id="bb8a2-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="bb8a2-108">Uiteindelijk worden alle aanmeldingsschemagegevens naar de tabel `IdentityLogonEvents` verplaatst.</span><span class="sxs-lookup"><span data-stu-id="bb8a2-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span>



<span data-ttu-id="bb8a2-109">De tabel in het geavanceerde schema voor het zoeken bevat `AADSpnSignInEventsBeta` informatie Azure Active Directory service principal en beheerde identiteits aanmelden. U kunt meer informatie over de verschillende soorten aanmeldingen in Azure Active Directory [aanmeldingsactiviteitsrapporten - preview.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)</span><span class="sxs-lookup"><span data-stu-id="bb8a2-109">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="bb8a2-110">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="bb8a2-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="bb8a2-111">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)</span><span class="sxs-lookup"><span data-stu-id="bb8a2-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="bb8a2-112">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="bb8a2-112">Column name</span></span>     | <span data-ttu-id="bb8a2-113">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="bb8a2-113">Data type</span></span> | <span data-ttu-id="bb8a2-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="bb8a2-114">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="bb8a2-115">datetime</span><span class="sxs-lookup"><span data-stu-id="bb8a2-115">datetime</span></span>      | <span data-ttu-id="bb8a2-116">Datum en tijd waarop de record is gegenereerd</span><span class="sxs-lookup"><span data-stu-id="bb8a2-116">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="bb8a2-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-117">string</span></span>        | <span data-ttu-id="bb8a2-118">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="bb8a2-118">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="bb8a2-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-119">string</span></span>        | <span data-ttu-id="bb8a2-120">Unieke id voor de toepassing</span><span class="sxs-lookup"><span data-stu-id="bb8a2-120">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="bb8a2-121">booleaanse</span><span class="sxs-lookup"><span data-stu-id="bb8a2-121">boolean</span></span>       | <span data-ttu-id="bb8a2-122">Geeft aan of de aanmelding is gestart door een beheerde identiteit</span><span class="sxs-lookup"><span data-stu-id="bb8a2-122">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="bb8a2-123">int</span><span class="sxs-lookup"><span data-stu-id="bb8a2-123">int</span></span>        | <span data-ttu-id="bb8a2-124">Bevat de foutcode als er een aanmeldingsfout optreedt.</span><span class="sxs-lookup"><span data-stu-id="bb8a2-124">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="bb8a2-125">Als u een beschrijving van een specifieke foutcode wilt zoeken, gaat u naar <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="bb8a2-125">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="bb8a2-126">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-126">string</span></span>        | <span data-ttu-id="bb8a2-127">Unieke id van de aanmeldingsgebeurtenis</span><span class="sxs-lookup"><span data-stu-id="bb8a2-127">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="bb8a2-128">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-128">string</span></span>        | <span data-ttu-id="bb8a2-129">Naam van de serviceprincipaal die de aanmelding heeft gestart</span><span class="sxs-lookup"><span data-stu-id="bb8a2-129">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="bb8a2-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-130">string</span></span>        | <span data-ttu-id="bb8a2-131">Unieke id van de serviceprincipaal die de aanmelding heeft gestart</span><span class="sxs-lookup"><span data-stu-id="bb8a2-131">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="bb8a2-132">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-132">string</span></span>        | <span data-ttu-id="bb8a2-133">Weergavenaam van de resource die wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="bb8a2-133">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="bb8a2-134">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-134">string</span></span>        | <span data-ttu-id="bb8a2-135">Unieke id van de resource die wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="bb8a2-135">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="bb8a2-136">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-136">string</span></span>        | <span data-ttu-id="bb8a2-137">Unieke id van de tenant van de resource die wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="bb8a2-137">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="bb8a2-138">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-138">string</span></span>        | <span data-ttu-id="bb8a2-139">IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="bb8a2-139">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="bb8a2-140">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-140">string</span></span>        | <span data-ttu-id="bb8a2-141">Code met twee letters waarmee het land wordt aangegeven waar het IP-adres van de client is geloceerd</span><span class="sxs-lookup"><span data-stu-id="bb8a2-141">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="bb8a2-142">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-142">string</span></span>        | <span data-ttu-id="bb8a2-143">Geef aan waar de aanmelding heeft plaatsgevonden, indien beschikbaar</span><span class="sxs-lookup"><span data-stu-id="bb8a2-143">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="bb8a2-144">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-144">string</span></span>        | <span data-ttu-id="bb8a2-145">Plaats waar de accountgebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="bb8a2-145">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="bb8a2-146">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-146">string</span></span>        | <span data-ttu-id="bb8a2-147">De coördinaten van noord naar zuid van de aanmeldingslocatie</span><span class="sxs-lookup"><span data-stu-id="bb8a2-147">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="bb8a2-148">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-148">string</span></span>        | <span data-ttu-id="bb8a2-149">De coördinaten van de aanmeldingslocatie</span><span class="sxs-lookup"><span data-stu-id="bb8a2-149">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="bb8a2-150">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-150">string</span></span>        | <span data-ttu-id="bb8a2-151">Unieke id van de aanvraag</span><span class="sxs-lookup"><span data-stu-id="bb8a2-151">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="bb8a2-152">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bb8a2-152">string</span></span> | <span data-ttu-id="bb8a2-153">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="bb8a2-153">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="bb8a2-154">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="bb8a2-154">Related articles</span></span>

-   [<span data-ttu-id="bb8a2-155">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="bb8a2-155">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="bb8a2-156">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="bb8a2-156">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="bb8a2-157">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="bb8a2-157">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="bb8a2-158">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="bb8a2-158">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)