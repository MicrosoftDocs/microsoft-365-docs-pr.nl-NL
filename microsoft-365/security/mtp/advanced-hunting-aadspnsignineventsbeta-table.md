---
title: AADSpnSignInEventsBeta-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over informatie die is gekoppeld aan de azure Active Directory-service principal en de tabel met beheerde identiteitsgegevens van het geavanceerde schema voor het zoeken
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
ms.openlocfilehash: 5050f4f91d61369e927eae15ca7c156a17792c24
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924538"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="bd9ab-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="bd9ab-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="bd9ab-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bd9ab-105">**Applies to:**</span></span>

- <span data-ttu-id="bd9ab-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd9ab-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="bd9ab-107">De tabel is momenteel in bètaversie en wordt op korte termijn aangeboden, zodat u kunt zoeken in `AADSpnSignInEventsBeta` azure Active Directory (AAD) service principal en managed identity sign-in events.</span><span class="sxs-lookup"><span data-stu-id="bd9ab-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="bd9ab-108">Uiteindelijk worden alle aanmeldingsschemagegevens naar de tabel `IdentityLogonEvents` verplaatst.</span><span class="sxs-lookup"><span data-stu-id="bd9ab-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="bd9ab-109">Klanten die toegang hebben tot Microsoft 365 Defender via de geïntegreerde Microsoft Defender voor Eindpunt-oplossing van het Azure Security Center, maar geen licenties hebben voor Microsoft Defender voor Office, Microsoft Defender voor identiteit of Microsoft Cloud App Security, kunnen dit schema niet bekijken.</span><span class="sxs-lookup"><span data-stu-id="bd9ab-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="bd9ab-110">De `AADSpnSignInEventsBeta` tabel in het geavanceerde schema bevat informatie over azure Active Directory-service principal en beheerde identiteits aanmelden. U kunt meer informatie krijgen over de verschillende soorten aanmeldingen in [Azure Active Directory-aanmeldingsactiviteitsrapporten - preview.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)</span><span class="sxs-lookup"><span data-stu-id="bd9ab-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="bd9ab-111">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="bd9ab-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="bd9ab-112">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)</span><span class="sxs-lookup"><span data-stu-id="bd9ab-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="bd9ab-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="bd9ab-113">Column name</span></span>     | <span data-ttu-id="bd9ab-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="bd9ab-114">Data type</span></span> | <span data-ttu-id="bd9ab-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="bd9ab-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="bd9ab-116">datetime</span><span class="sxs-lookup"><span data-stu-id="bd9ab-116">datetime</span></span>      | <span data-ttu-id="bd9ab-117">Datum en tijd waarop de record is gegenereerd</span><span class="sxs-lookup"><span data-stu-id="bd9ab-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="bd9ab-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-118">string</span></span>        | <span data-ttu-id="bd9ab-119">Toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="bd9ab-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="bd9ab-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-120">string</span></span>        | <span data-ttu-id="bd9ab-121">Unieke id voor de toepassing</span><span class="sxs-lookup"><span data-stu-id="bd9ab-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="bd9ab-122">booleaanse</span><span class="sxs-lookup"><span data-stu-id="bd9ab-122">boolean</span></span>       | <span data-ttu-id="bd9ab-123">Geeft aan of de aanmelding is gestart door een beheerde identiteit</span><span class="sxs-lookup"><span data-stu-id="bd9ab-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="bd9ab-124">int</span><span class="sxs-lookup"><span data-stu-id="bd9ab-124">int</span></span>        | <span data-ttu-id="bd9ab-125">Bevat de foutcode als er een aanmeldingsfout optreedt.</span><span class="sxs-lookup"><span data-stu-id="bd9ab-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="bd9ab-126">Als u een beschrijving van een specifieke foutcode wilt zoeken, gaat u naar <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="bd9ab-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="bd9ab-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-127">string</span></span>        | <span data-ttu-id="bd9ab-128">Unieke id van de aanmeldingsgebeurtenis</span><span class="sxs-lookup"><span data-stu-id="bd9ab-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="bd9ab-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-129">string</span></span>        | <span data-ttu-id="bd9ab-130">Naam van de serviceprincipaal die de aanmelding heeft gestart</span><span class="sxs-lookup"><span data-stu-id="bd9ab-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="bd9ab-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-131">string</span></span>        | <span data-ttu-id="bd9ab-132">Unieke id van de serviceprincipaal die de aanmelding heeft gestart</span><span class="sxs-lookup"><span data-stu-id="bd9ab-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="bd9ab-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-133">string</span></span>        | <span data-ttu-id="bd9ab-134">Weergavenaam van de resource die wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="bd9ab-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="bd9ab-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-135">string</span></span>        | <span data-ttu-id="bd9ab-136">Unieke id van de resource die wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="bd9ab-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="bd9ab-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-137">string</span></span>        | <span data-ttu-id="bd9ab-138">Unieke id van de tenant van de resource die wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="bd9ab-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="bd9ab-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-139">string</span></span>        | <span data-ttu-id="bd9ab-140">IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="bd9ab-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `Country`          | <span data-ttu-id="bd9ab-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-141">string</span></span>        | <span data-ttu-id="bd9ab-142">Code met twee letters waarmee het land wordt aangegeven waar het IP-adres van de client is geloceerd</span><span class="sxs-lookup"><span data-stu-id="bd9ab-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="bd9ab-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-143">string</span></span>        | <span data-ttu-id="bd9ab-144">Geef aan waar de aanmelding heeft plaatsgevonden, indien beschikbaar</span><span class="sxs-lookup"><span data-stu-id="bd9ab-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="bd9ab-145">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-145">string</span></span>        | <span data-ttu-id="bd9ab-146">Plaats waar de accountgebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="bd9ab-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="bd9ab-147">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-147">string</span></span>        | <span data-ttu-id="bd9ab-148">De coördinaten van noord naar zuid van de aanmeldingslocatie</span><span class="sxs-lookup"><span data-stu-id="bd9ab-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="bd9ab-149">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-149">string</span></span>        | <span data-ttu-id="bd9ab-150">De coördinaten van de aanmeldingslocatie</span><span class="sxs-lookup"><span data-stu-id="bd9ab-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="bd9ab-151">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-151">string</span></span>        | <span data-ttu-id="bd9ab-152">Unieke id van de aanvraag</span><span class="sxs-lookup"><span data-stu-id="bd9ab-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="bd9ab-153">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="bd9ab-153">string</span></span> | <span data-ttu-id="bd9ab-154">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="bd9ab-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="bd9ab-155">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="bd9ab-155">Related articles</span></span>

-   [<span data-ttu-id="bd9ab-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="bd9ab-156">AADSignInEventsBeta</span></span>](./advanced-hunting-aadsignineventsbeta-table.md)
-   [<span data-ttu-id="bd9ab-157">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="bd9ab-157">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="bd9ab-158">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="bd9ab-158">Learn the query language</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="bd9ab-159">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="bd9ab-159">Understand the schema</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)