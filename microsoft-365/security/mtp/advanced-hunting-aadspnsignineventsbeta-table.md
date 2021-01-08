---
title: AADSpnSignInEventsBeta-tabel in het geavanceerde jacht schema
description: Meer informatie over informatie die is gekoppeld aan de Azure Active Directory-Service Principal en de lijst met aanmeld gebeurtenissen van de beheerde identiteit van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, Column, datatype, beschrijving, AlertInfo, waarschuwing, entiteit, bewijs, bestand, IP-adres, apparaat, computer, gebruiker, account, identiteit, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 42acf24ce9b941fffb1ce0ed4b67216bd8c1de47
ms.sourcegitcommit: 4482c174e0e68e0fbbc7ad9ef6b0e78dc34ac85a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/08/2021
ms.locfileid: "49784297"
---
# <a name="aadspnsignineventsbeta"></a><span data-ttu-id="b471f-104">AADSpnSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="b471f-104">AADSpnSignInEventsBeta</span></span>

<span data-ttu-id="b471f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b471f-105">**Applies to:**</span></span>

- <span data-ttu-id="b471f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b471f-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="b471f-107">De `AADSpnSignInEventsBeta` tabel bevindt zich momenteel in de bètaversie en wordt kort weer geboden, zodat u de service-principal van Azure Active Directory (Aad) en de aanmeldingsgebeurtenissen van de beheerde identiteit kunt zoeken.</span><span class="sxs-lookup"><span data-stu-id="b471f-107">The `AADSpnSignInEventsBeta` table is currently in beta and is being offered on a short-term basis to allow you to hunt through Azure Active Directory (AAD) service principal and managed identity sign-in events.</span></span> <span data-ttu-id="b471f-108">We zullen uiteindelijk alle gegevens van het aanmeldings schema naar de `IdentityLogonEvents` tabel verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="b471f-108">We will eventually move all sign-in schema information to the `IdentityLogonEvents` table.</span></span><br><br>
> <span data-ttu-id="b471f-109">Klanten die de Microsoft 365-app hebben geopend via de geïntegreerde Microsoft-app voor eindpunten van het Azure-Beveiligingscentrum, maar geen licenties voor Microsoft Defender for Office, Microsoft Defender for Identity, of Microsoft Cloud app Security, kunnen dit schema niet weergeven.</span><span class="sxs-lookup"><span data-stu-id="b471f-109">Customers who can access Microsoft 365 Defender through the Azure Security Center’s integrated Microsoft Defender for Endpoint solution, but do not have licenses for Microsoft Defender for Office, Microsoft Defender for Identity, or Microsoft Cloud App Security, will not be able to view this schema.</span></span> 



<span data-ttu-id="b471f-110">De `AADSpnSignInEventsBeta` tabel in het geavanceerde begeleidende schema bevat informatie over het aanmelden van Azure Active Directory-service en invoegtoepassingen voor beheerde id's. U vindt meer informatie over de verschillende soorten aanmeldinformatie in [Azure Active Directory-aanmeldings activiteitenrapporten-preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span><span class="sxs-lookup"><span data-stu-id="b471f-110">The `AADSpnSignInEventsBeta` table in the advanced hunting schema contains information about Azure Active Directory service principal and managed identity sign-ins. You can learn more about the different kinds of sign-ins in [Azure Active Directory sign-in activity reports - preview](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins).</span></span>

<span data-ttu-id="b471f-111">Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="b471f-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="b471f-112">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)zoeken.</span><span class="sxs-lookup"><span data-stu-id="b471f-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).</span></span>





| <span data-ttu-id="b471f-113">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="b471f-113">Column name</span></span>     | <span data-ttu-id="b471f-114">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="b471f-114">Data type</span></span> | <span data-ttu-id="b471f-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b471f-115">Description</span></span>   |
| ----- | ----- | ---- |
| `Timestamp` | <span data-ttu-id="b471f-116">tijd</span><span class="sxs-lookup"><span data-stu-id="b471f-116">datetime</span></span>      | <span data-ttu-id="b471f-117">De datum en tijd waarop de record is gegenereerd</span><span class="sxs-lookup"><span data-stu-id="b471f-117">Date and time when the record was generated</span></span>                                                                                                     |
| `Application`          | <span data-ttu-id="b471f-118">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-118">string</span></span>        | <span data-ttu-id="b471f-119">De toepassing die de opgenomen actie heeft uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="b471f-119">Application that performed the recorded action</span></span>                                                                                                   |
| `ApplicationId`        | <span data-ttu-id="b471f-120">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-120">string</span></span>        | <span data-ttu-id="b471f-121">Unieke id voor de toepassing</span><span class="sxs-lookup"><span data-stu-id="b471f-121">Unique identifier for the application</span></span>                                                                                                           |
| `IsManagedIdentity`    | <span data-ttu-id="b471f-122">Boolean</span><span class="sxs-lookup"><span data-stu-id="b471f-122">boolean</span></span>       | <span data-ttu-id="b471f-123">Geeft aan of de aanmelding is gestart door een beheerde identiteit</span><span class="sxs-lookup"><span data-stu-id="b471f-123">Indicates whether the sign-in was initiated by a managed identity</span></span>                                                                               |
| `ErrorCode`            | <span data-ttu-id="b471f-124">int</span><span class="sxs-lookup"><span data-stu-id="b471f-124">int</span></span>        | <span data-ttu-id="b471f-125">Bevat de foutcode als een aanmeldingsfout optreedt.</span><span class="sxs-lookup"><span data-stu-id="b471f-125">Contains the error code if a sign-in error occurs.</span></span> <span data-ttu-id="b471f-126">Ga naar voor een beschrijving van een bepaalde foutcode <https://aka.ms/AADsigninsErrorCodes> .</span><span class="sxs-lookup"><span data-stu-id="b471f-126">To find a description of a specific error code, visit <https://aka.ms/AADsigninsErrorCodes>.</span></span> |
| `CorrelationId`        | <span data-ttu-id="b471f-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-127">string</span></span>        | <span data-ttu-id="b471f-128">Unieke id van de aanmeld gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="b471f-128">Unique identifier of the sign-in event</span></span>                                                                                                          |
| `ServicePrincipalName` | <span data-ttu-id="b471f-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-129">string</span></span>        | <span data-ttu-id="b471f-130">Naam van de service-principal waarmee de aanmelding is gestart</span><span class="sxs-lookup"><span data-stu-id="b471f-130">Name of the service principal that initiated the sign-in</span></span>                                                                                        |
| `ServicePrincipalId`   | <span data-ttu-id="b471f-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-131">string</span></span>        | <span data-ttu-id="b471f-132">Unieke id van de service-principal waarmee de aanmelding werd geïnitieerd</span><span class="sxs-lookup"><span data-stu-id="b471f-132">Unique identifier of the service principal that initiated the sign-in</span></span>                                                                           |
| `ResourceDisplayName`  | <span data-ttu-id="b471f-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-133">string</span></span>        | <span data-ttu-id="b471f-134">De weergavenaam van de resource die wordt geopend</span><span class="sxs-lookup"><span data-stu-id="b471f-134">Display name of the resource accessed</span></span>                                                                                                           |
| `ResourceId`           | <span data-ttu-id="b471f-135">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-135">string</span></span>        | <span data-ttu-id="b471f-136">Unieke id van de geopente resource</span><span class="sxs-lookup"><span data-stu-id="b471f-136">Unique identifier of the resource accessed</span></span>                                                                                                      |
| `ResourceTenantId`     | <span data-ttu-id="b471f-137">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-137">string</span></span>        | <span data-ttu-id="b471f-138">Unieke id van de Tenant van de geopente bron</span><span class="sxs-lookup"><span data-stu-id="b471f-138">Unique identifier of the tenant of the resource accessed</span></span>                                                                                        |
| `IPAddress`            | <span data-ttu-id="b471f-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-139">string</span></span>        | <span data-ttu-id="b471f-140">Het IP-adres dat is toegewezen aan het eindpunt en die wordt gebruikt tijdens gerelateerde netwerkcommunicatie</span><span class="sxs-lookup"><span data-stu-id="b471f-140">IP address assigned to the endpoint and used during related network communications</span></span>                                                              |
| `CountryCode`          | <span data-ttu-id="b471f-141">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-141">string</span></span>        | <span data-ttu-id="b471f-142">Tweeletterige code die het land aangeeft waarin het IP-adres van de client geolocatie is</span><span class="sxs-lookup"><span data-stu-id="b471f-142">Two-letter code indicating the country where the client IP address is geolocated</span></span>                                                                |
| `State`                | <span data-ttu-id="b471f-143">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-143">string</span></span>        | <span data-ttu-id="b471f-144">De status van de aanmelding, indien beschikbaar</span><span class="sxs-lookup"><span data-stu-id="b471f-144">State where the sign-in occurred, if available</span></span>                                                                                                  |
| `City`                 | <span data-ttu-id="b471f-145">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-145">string</span></span>        | <span data-ttu-id="b471f-146">Plaats waar de account gebruiker zich bevindt</span><span class="sxs-lookup"><span data-stu-id="b471f-146">City where the account user is located</span></span>                                                                                                          |
| `Latitude`             | <span data-ttu-id="b471f-147">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-147">string</span></span>        | <span data-ttu-id="b471f-148">De Noord-to-Zuid-coördinaten van de aanmeldingslocatie</span><span class="sxs-lookup"><span data-stu-id="b471f-148">The north to south coordinates of the sign-in location</span></span>                                                                                          |
| `Longitude`            | <span data-ttu-id="b471f-149">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-149">string</span></span>        | <span data-ttu-id="b471f-150">De Oost-en West-coördinaten van de aanmeldingslocatie</span><span class="sxs-lookup"><span data-stu-id="b471f-150">The east to west coordinates of the sign-in location</span></span>                                                                                            |
| `RequestId`            | <span data-ttu-id="b471f-151">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-151">string</span></span>        | <span data-ttu-id="b471f-152">Unieke id van de aanvraag</span><span class="sxs-lookup"><span data-stu-id="b471f-152">Unique identifier of the request</span></span>                                                                                                                |
|`ReportId` | <span data-ttu-id="b471f-153">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="b471f-153">string</span></span> | <span data-ttu-id="b471f-154">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="b471f-154">Unique identifier for the event</span></span> | 

 

## <a name="related-articles"></a><span data-ttu-id="b471f-155">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="b471f-155">Related articles</span></span>

-   [<span data-ttu-id="b471f-156">AADSignInEventsBeta</span><span class="sxs-lookup"><span data-stu-id="b471f-156">AADSignInEventsBeta</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [<span data-ttu-id="b471f-157">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="b471f-157">Advanced hunting overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [<span data-ttu-id="b471f-158">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="b471f-158">Learn the query language</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [<span data-ttu-id="b471f-159">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="b471f-159">Understand the schema</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

