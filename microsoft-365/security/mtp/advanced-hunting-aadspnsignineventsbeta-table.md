---
title: AADSpnSignInEventsBeta-tabel in het geavanceerde schema voor zoeken
description: Meer informatie over informatie die is gekoppeld aan Azure Active Directory service principal en de tabel met beheerde identiteitsgegevens van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account, identity, AAD
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 172c400df3adea70a2e2d2e37547fa39e0d3b9cf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928616"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="36354-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="36354-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="36354-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="36354-105">**Applies to:**</span></span>

- <span data-ttu-id="36354-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36354-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="36354-107">De tabel is momenteel beschikbaar in de bètaversie en wordt op korte termijn aangeboden zodat u kunt zoeken in `AADSpnSignInEventsBeta` azure Active Directory (AAD)-service-principal en beheerde aanmeldingsgebeurtenissen voor identiteiten.</span><span class="sxs-lookup"><span data-stu-id="36354-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="36354-108">Uiteindelijk worden alle gegevens van het aanmeldingsschema naar de tabel `IdentityLogonEvents` verplaatst.</span><span class="sxs-lookup"><span data-stu-id="36354-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="36354-109">Klanten die toegang hebben tot Microsoft 365 Defender via de geïntegreerde oplossing microsoft Defender for Endpoint van het Azure-beveiligingscentrum, maar geen licenties hebben voor Microsoft Defender voor Office, Microsoft Defender voor identiteit of Microsoft Cloud App-beveiliging, kunnen dit schema niet bekijken.</span><span class="sxs-lookup"><span data-stu-id="36354-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="36354-110">De `AADSpnSignInEventsBeta` tabel in het geavanceerde schema voor zoeken bevat informatie over Azure Active Directory-service-principal en beheerde identiteitsgegevens. U kunt meer informatie krijgen over de verschillende soorten aanmeldingsrapporten in [Azure Active Directory-activiteitsrapporten - preview.](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)</span><span class="sxs-lookup"><span data-stu-id="36354-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="36354-111">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="36354-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="36354-112">Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)</span><span class="sxs-lookup"><span data-stu-id="36354-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="36354-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="36354-113">Column name</span></span>     | <span data-ttu-id="36354-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="36354-114">Data type</span></span> | <span data-ttu-id="36354-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="36354-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="36354-116">datetime</span><span class="sxs-lookup"><span data-stu-id="36354-116">datetime</span></span>      | <span data-ttu-id="36354-117">Datum en tijd waarop de record is gegenereerd</span><span class="sxs-lookup"><span data-stu-id="36354-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="36354-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-118">string</span></span>        | <span data-ttu-id="36354-119">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="36354-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="36354-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-120">string</span></span>        | <span data-ttu-id="36354-121">Unieke id voor de toepassing</span><span class="sxs-lookup"><span data-stu-id="36354-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="36354-122">boolean</span><span class="sxs-lookup"><span data-stu-id="36354-122">boolean</span></span>       | <span data-ttu-id="36354-123">Geeft aan of de aanmelding is gestart met een beheerde identiteit</span><span class="sxs-lookup"><span data-stu-id="36354-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="36354-124">int</span><span class="sxs-lookup"><span data-stu-id="36354-124">int</span></span>        | <span data-ttu-id="36354-125">Bevat de foutcode als er een aanmeldingsfout optreedt.</span><span class="sxs-lookup"><span data-stu-id="36354-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="36354-126">Als u een beschrijving van een specifieke foutcode wilt vinden, gaat u naar <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="36354-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="36354-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-127">string</span></span>        | <span data-ttu-id="36354-128">Unieke id van de aanmeldingsgebeurtenis</span><span class="sxs-lookup"><span data-stu-id="36354-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="36354-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-129">string</span></span>        | <span data-ttu-id="36354-130">Naam van de service-principal die de aanmelding heeft geïnitieerd</span><span class="sxs-lookup"><span data-stu-id="36354-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="36354-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-131">string</span></span>        | <span data-ttu-id="36354-132">Unieke id van de service-principal die de aanmelding heeft geïnitieerd</span><span class="sxs-lookup"><span data-stu-id="36354-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="36354-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-133">string</span></span>        | <span data-ttu-id="36354-134">Weergavenaam van de bron die is gebruikt</span><span class="sxs-lookup"><span data-stu-id="36354-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="36354-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-135">string</span></span>        | <span data-ttu-id="36354-136">Unieke id van de bron die wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="36354-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="36354-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-137">string</span></span>        | <span data-ttu-id="36354-138">Unieke id van de tenant van de bron die is gebruikt</span><span class="sxs-lookup"><span data-stu-id="36354-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="36354-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-139">string</span></span>        | <span data-ttu-id="36354-140">IP-adres dat aan het eindpunt is toegewezen en dat is gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="36354-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `CountryCode`          | <span data-ttu-id="36354-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-141">string</span></span>        | <span data-ttu-id="36354-142">Tweeletterige code die het land aangeeft waar het IP-adres van de client geo-toegewezen is</span><span class="sxs-lookup"><span data-stu-id="36354-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="36354-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-143">string</span></span>        | <span data-ttu-id="36354-144">Provincie waar de aanmelding heeft plaatsgevonden, indien beschikbaar</span><span class="sxs-lookup"><span data-stu-id="36354-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="36354-145">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-145">string</span></span>        | <span data-ttu-id="36354-146">Plaats waar de accountgebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="36354-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="36354-147">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-147">string</span></span>        | <span data-ttu-id="36354-148">De coördinaten van de aanmeldingslocatie van Noord naar Zuid</span><span class="sxs-lookup"><span data-stu-id="36354-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="36354-149">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-149">string</span></span>        | <span data-ttu-id="36354-150">De coördinaten van Oost naar West van de aanmeldingslocatie</span><span class="sxs-lookup"><span data-stu-id="36354-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="36354-151">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-151">string</span></span>        | <span data-ttu-id="36354-152">Unieke id van de aanvraag</span><span class="sxs-lookup"><span data-stu-id="36354-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="36354-153">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="36354-153">string</span></span> | <span data-ttu-id="36354-154">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="36354-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="36354-155">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="36354-155">Related articles</span></span>

-   [<span data-ttu-id="36354-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="36354-156">AADSignInEventsBeta</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [<span data-ttu-id="36354-157">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="36354-157">Advanced hunting overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="36354-158">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="36354-158">Learn the query language</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="36354-159">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="36354-159">Understand the schema</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

