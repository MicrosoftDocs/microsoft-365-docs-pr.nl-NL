---
title: Api voor lijstincidenten in Microsoft 365 Defender
description: Informatie over het op een lijst zetten van incidenten API in Microsoft 365 Defender
keywords: list, incident, incidents, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 39a170a1845ab33f67d77b2de3d5f298f67fdc99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932068"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="77195-104">Api voor lijstincidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77195-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="77195-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="77195-105">**Applies to:**</span></span>

- <span data-ttu-id="77195-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77195-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77195-107">Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht.</span><span class="sxs-lookup"><span data-stu-id="77195-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="77195-108">Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.</span><span class="sxs-lookup"><span data-stu-id="77195-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="77195-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="77195-109">API description</span></span>

<span data-ttu-id="77195-110">Met de API voor lijstincidenten kunt u incidenten sorteren om een weloverwogen reactie te krijgen.</span><span class="sxs-lookup"><span data-stu-id="77195-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="77195-111">Er wordt een verzameling incidenten beschreven die in uw netwerk zijn gemarkeerd binnen het tijdsbereik dat u hebt opgegeven in het bewaarbeleid voor omgevingen.</span><span class="sxs-lookup"><span data-stu-id="77195-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="77195-112">De meest recente incidenten worden boven aan de lijst weergegeven.</span><span class="sxs-lookup"><span data-stu-id="77195-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="77195-113">Elk incident bevat een matrix met gerelateerde waarschuwingen en de bijbehorende entiteiten.</span><span class="sxs-lookup"><span data-stu-id="77195-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="77195-114">De API ondersteunt de volgende **OData-operators:**</span><span class="sxs-lookup"><span data-stu-id="77195-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="77195-115">`$filter`in de `lastUpdateTime` `createdTime` eigenschappen , `status` en `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="77195-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="77195-116">`$top`, met een maximumwaarde van **100**</span><span class="sxs-lookup"><span data-stu-id="77195-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="77195-117">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="77195-117">Limitations</span></span>

1. <span data-ttu-id="77195-118">Het maximale paginaformaat is **100 incidenten.**</span><span class="sxs-lookup"><span data-stu-id="77195-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="77195-119">Het maximale aantal aanvragen is **50 oproepen per minuut** en **1500 oproepen per uur.**</span><span class="sxs-lookup"><span data-stu-id="77195-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="77195-120">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="77195-120">Permissions</span></span>

<span data-ttu-id="77195-121">Een van de volgende machtigingen is vereist om deze API aan te roepen.</span><span class="sxs-lookup"><span data-stu-id="77195-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="77195-122">Zie [Access Microsoft 365 Defender API's (Access Microsoft 365 Defender-API's)](api-access.md) voor meer informatie, waaronder het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="77195-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="77195-123">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="77195-123">Permission type</span></span> | <span data-ttu-id="77195-124">Machtiging</span><span class="sxs-lookup"><span data-stu-id="77195-124">Permission</span></span> | <span data-ttu-id="77195-125">Weergavenaam van machtiging</span><span class="sxs-lookup"><span data-stu-id="77195-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="77195-126">Toepassing</span><span class="sxs-lookup"><span data-stu-id="77195-126">Application</span></span> | <span data-ttu-id="77195-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="77195-127">Incident.Read.All</span></span> | <span data-ttu-id="77195-128">Alle incidenten lezen</span><span class="sxs-lookup"><span data-stu-id="77195-128">Read all incidents</span></span>
<span data-ttu-id="77195-129">Toepassing</span><span class="sxs-lookup"><span data-stu-id="77195-129">Application</span></span> | <span data-ttu-id="77195-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="77195-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="77195-131">Alle incidenten lezen en schrijven</span><span class="sxs-lookup"><span data-stu-id="77195-131">Read and write all incidents</span></span>
<span data-ttu-id="77195-132">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="77195-132">Delegated (work or school account)</span></span> | <span data-ttu-id="77195-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="77195-133">Incident.Read</span></span> | <span data-ttu-id="77195-134">Incidenten lezen</span><span class="sxs-lookup"><span data-stu-id="77195-134">Read incidents</span></span>
<span data-ttu-id="77195-135">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="77195-135">Delegated (work or school account)</span></span> | <span data-ttu-id="77195-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="77195-136">Incident.ReadWrite</span></span> | <span data-ttu-id="77195-137">Incidenten lezen en schrijven</span><span class="sxs-lookup"><span data-stu-id="77195-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="77195-138">Wanneer u een token verkrijgt met behulp van gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="77195-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="77195-139">De gebruiker moet weergavemachtigingen hebben voor incidenten in de portal.</span><span class="sxs-lookup"><span data-stu-id="77195-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="77195-140">De reactie omvat alleen incidenten die de gebruiker te zien krijgt.</span><span class="sxs-lookup"><span data-stu-id="77195-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="77195-141">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="77195-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="77195-142">Berichtkoppen aanvragen</span><span class="sxs-lookup"><span data-stu-id="77195-142">Request headers</span></span>

<span data-ttu-id="77195-143">Naam</span><span class="sxs-lookup"><span data-stu-id="77195-143">Name</span></span> | <span data-ttu-id="77195-144">Type</span><span class="sxs-lookup"><span data-stu-id="77195-144">Type</span></span> | <span data-ttu-id="77195-145">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="77195-145">Description</span></span>
-|-|-
<span data-ttu-id="77195-146">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="77195-146">Authorization</span></span> | <span data-ttu-id="77195-147">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="77195-147">String</span></span> | <span data-ttu-id="77195-148">Beller {token}.</span><span class="sxs-lookup"><span data-stu-id="77195-148">Bearer {token}.</span></span> <span data-ttu-id="77195-149">**Vereist**</span><span class="sxs-lookup"><span data-stu-id="77195-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="77195-150">Aanvraag in de eerste instantie</span><span class="sxs-lookup"><span data-stu-id="77195-150">Request body</span></span>

<span data-ttu-id="77195-151">Geen.</span><span class="sxs-lookup"><span data-stu-id="77195-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="77195-152">Antwoord</span><span class="sxs-lookup"><span data-stu-id="77195-152">Response</span></span>

<span data-ttu-id="77195-153">Als dit is gelukt, worden met deze methode de incidenten in de antwoord zelf `200 OK` weergegeven. [](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="77195-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="77195-154">Schematoewijzing</span><span class="sxs-lookup"><span data-stu-id="77195-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="77195-155">Metagegevens voor incidenten</span><span class="sxs-lookup"><span data-stu-id="77195-155">Incident metadata</span></span>

<span data-ttu-id="77195-156">Veldnaam</span><span class="sxs-lookup"><span data-stu-id="77195-156">Field name</span></span> | <span data-ttu-id="77195-157">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="77195-157">Description</span></span> | <span data-ttu-id="77195-158">Voorbeeldwaarde</span><span class="sxs-lookup"><span data-stu-id="77195-158">Example value</span></span>
-|-|-
<span data-ttu-id="77195-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="77195-159">incidentId</span></span> | <span data-ttu-id="77195-160">Unieke id die het incident vertegenwoordigt</span><span class="sxs-lookup"><span data-stu-id="77195-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="77195-161">924565</span><span class="sxs-lookup"><span data-stu-id="77195-161">924565</span></span>
<span data-ttu-id="77195-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="77195-162">redirectIncidentId</span></span> | <span data-ttu-id="77195-163">Alleen ingevuld voor het geval een incident wordt gegroepeerd met een ander incident, als onderdeel van de incidentverwerkingslogica.</span><span class="sxs-lookup"><span data-stu-id="77195-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="77195-164">924569</span><span class="sxs-lookup"><span data-stu-id="77195-164">924569</span></span>
<span data-ttu-id="77195-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="77195-165">incidentName</span></span> | <span data-ttu-id="77195-166">De waarde van de tekenreeks die beschikbaar is voor elk incident.</span><span class="sxs-lookup"><span data-stu-id="77195-166">String value available for every incident.</span></span> | <span data-ttu-id="77195-167">Ransomware-activiteit</span><span class="sxs-lookup"><span data-stu-id="77195-167">Ransomware activity</span></span>
<span data-ttu-id="77195-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="77195-168">createdTime</span></span> | <span data-ttu-id="77195-169">Tijdstip waarop het incident voor het eerst is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="77195-169">Time when incident was first created.</span></span> | <span data-ttu-id="77195-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="77195-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="77195-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="77195-171">lastUpdateTime</span></span> | <span data-ttu-id="77195-172">Het tijdstip waarop het incident voor het laatst is bijgewerkt op de back-back</span><span class="sxs-lookup"><span data-stu-id="77195-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="77195-173">Dit veld kan worden gebruikt wanneer u de parameter Aanvraag instelt voor het tijdsbereik waarin incidenten worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="77195-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="77195-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="77195-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="77195-175">toegewezen Aan</span><span class="sxs-lookup"><span data-stu-id="77195-175">assignedTo</span></span> | <span data-ttu-id="77195-176">Eigenaar van het incident of *null* als er geen eigenaar is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="77195-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="77195-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="77195-177">secop2@contoso.com</span></span>
<span data-ttu-id="77195-178">classificatie</span><span class="sxs-lookup"><span data-stu-id="77195-178">classification</span></span> | <span data-ttu-id="77195-179">De specificatie voor het incident.</span><span class="sxs-lookup"><span data-stu-id="77195-179">The specification for the incident.</span></span> <span data-ttu-id="77195-180">De eigenschapswaarden *zijn: Onbekend,* *FalsePositive,* *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="77195-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="77195-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="77195-181">Unknown</span></span>
<span data-ttu-id="77195-182">besluit</span><span class="sxs-lookup"><span data-stu-id="77195-182">determination</span></span> | <span data-ttu-id="77195-183">Bepaalt de vaststelling van het incident.</span><span class="sxs-lookup"><span data-stu-id="77195-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="77195-184">De eigenschapswaarden zijn: *NotAvailable,* *Apt,* *Malware,* *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware,* *Other*</span><span class="sxs-lookup"><span data-stu-id="77195-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="77195-185">Niet beschikbaar</span><span class="sxs-lookup"><span data-stu-id="77195-185">NotAvailable</span></span>
<span data-ttu-id="77195-186">status</span><span class="sxs-lookup"><span data-stu-id="77195-186">status</span></span> | <span data-ttu-id="77195-187">Incidenten categoriseren (als *Actief* of *Opgelost).*</span><span class="sxs-lookup"><span data-stu-id="77195-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="77195-188">Het kan u helpen uw reacties op incidenten te ordenen en te beheren.</span><span class="sxs-lookup"><span data-stu-id="77195-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="77195-189">Actief</span><span class="sxs-lookup"><span data-stu-id="77195-189">Active</span></span>
<span data-ttu-id="77195-190">ernst</span><span class="sxs-lookup"><span data-stu-id="77195-190">severity</span></span> | <span data-ttu-id="77195-191">Geeft de mogelijke invloed op activa aan.</span><span class="sxs-lookup"><span data-stu-id="77195-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="77195-192">Hoe hoger de ernst, hoe groter de impact.</span><span class="sxs-lookup"><span data-stu-id="77195-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="77195-193">Items met een hogere ernst vereisen meestal de meest directe aandacht.</span><span class="sxs-lookup"><span data-stu-id="77195-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="77195-194">Een van de volgende waarden: *Informatief,* \*Laag,\*\*Normaal en *Hoog.*</span><span class="sxs-lookup"><span data-stu-id="77195-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="77195-195">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="77195-195">Medium</span></span>
<span data-ttu-id="77195-196">tags</span><span class="sxs-lookup"><span data-stu-id="77195-196">tags</span></span> | <span data-ttu-id="77195-197">Matrix van aangepaste tags die betrekking hebben op een incident, bijvoorbeeld om een groep incidenten met een gemeenschappelijke kenmerken te markeren.</span><span class="sxs-lookup"><span data-stu-id="77195-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="77195-198">waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="77195-198">alerts</span></span> | <span data-ttu-id="77195-199">Matrix met alle waarschuwingen die betrekking hebben op het incident, plus andere informatie, zoals ernst, entiteiten die zijn betrokken bij de waarschuwing en de bron van de waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="77195-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="77195-200">\[\] (zie de details van waarschuwingsvelden hieronder)</span><span class="sxs-lookup"><span data-stu-id="77195-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="77195-201">Metagegevens waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="77195-201">Alerts metadata</span></span>

<span data-ttu-id="77195-202">Veldnaam</span><span class="sxs-lookup"><span data-stu-id="77195-202">Field name</span></span> | <span data-ttu-id="77195-203">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="77195-203">Description</span></span> | <span data-ttu-id="77195-204">Voorbeeldwaarde</span><span class="sxs-lookup"><span data-stu-id="77195-204">Example value</span></span>
-|-|-
<span data-ttu-id="77195-205">alertId</span><span class="sxs-lookup"><span data-stu-id="77195-205">alertId</span></span> | <span data-ttu-id="77195-206">Unieke id die de waarschuwing vertegenwoordigt</span><span class="sxs-lookup"><span data-stu-id="77195-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="77195-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="77195-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="77195-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="77195-208">incidentId</span></span> | <span data-ttu-id="77195-209">Unieke id die het incident vertegenwoordigt dat aan deze waarschuwing is gekoppeld</span><span class="sxs-lookup"><span data-stu-id="77195-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="77195-210">924565</span><span class="sxs-lookup"><span data-stu-id="77195-210">924565</span></span>
<span data-ttu-id="77195-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="77195-211">serviceSource</span></span> | <span data-ttu-id="77195-212">Service waar de waarschuwing van afkomstig is, zoals Microsoft Defender voor eindpunt, Microsoft Cloud App-beveiliging, Microsoft Defender voor identiteit of Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="77195-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="77195-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="77195-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="77195-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="77195-214">creationTime</span></span> | <span data-ttu-id="77195-215">Het tijdstip waarop de waarschuwing voor het eerst is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="77195-215">Time when alert was first created.</span></span> | <span data-ttu-id="77195-216">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="77195-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="77195-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="77195-217">lastUpdatedTime</span></span> | <span data-ttu-id="77195-218">Het tijdstip waarop de waarschuwing voor het laatst is bijgewerkt bij de back-back</span><span class="sxs-lookup"><span data-stu-id="77195-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="77195-219">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="77195-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="77195-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="77195-220">resolvedTime</span></span> | <span data-ttu-id="77195-221">Het tijdstip waarop de waarschuwing is opgelost.</span><span class="sxs-lookup"><span data-stu-id="77195-221">Time when alert was resolved.</span></span> | <span data-ttu-id="77195-222">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="77195-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="77195-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="77195-223">firstActivity</span></span> | <span data-ttu-id="77195-224">Het tijdstip waarop de waarschuwing de eerste keer heeft gerapporteerd dat de activiteit is bijgewerkt op de back-back-backend.</span><span class="sxs-lookup"><span data-stu-id="77195-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="77195-225">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="77195-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="77195-226">titel</span><span class="sxs-lookup"><span data-stu-id="77195-226">title</span></span> | <span data-ttu-id="77195-227">Kort de waarde die beschikbaar is voor elke waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="77195-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="77195-228">Ransomware-activiteit</span><span class="sxs-lookup"><span data-stu-id="77195-228">Ransomware activity</span></span>
<span data-ttu-id="77195-229">beschrijving</span><span class="sxs-lookup"><span data-stu-id="77195-229">description</span></span> | <span data-ttu-id="77195-230">De waarde van de tekenreeks die elke waarschuwing beschrijft.</span><span class="sxs-lookup"><span data-stu-id="77195-230">String value describing each alert.</span></span> | <span data-ttu-id="77195-231">De gebruiker test gebruiker2 (testUser2@contoso.com) manipuleerde 99 bestanden met meerdere extensies die eindigt op de ongebruikelijke extensie *herunter laden.*</span><span class="sxs-lookup"><span data-stu-id="77195-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="77195-232">Dit is een ongebruikelijk aantal bestandsmanipulaties en wordt beïnvloed door een mogelijke aanval van ransomware.</span><span class="sxs-lookup"><span data-stu-id="77195-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="77195-233">categorie</span><span class="sxs-lookup"><span data-stu-id="77195-233">category</span></span> | <span data-ttu-id="77195-234">Visuele en numerieke weergave van hoe ver de aanval is gegaan langs de kill chain.</span><span class="sxs-lookup"><span data-stu-id="77195-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="77195-235">Afgestemd op de [MITRE ATT&CK™ framework.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="77195-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="77195-236">Gevolg</span><span class="sxs-lookup"><span data-stu-id="77195-236">Impact</span></span>
<span data-ttu-id="77195-237">status</span><span class="sxs-lookup"><span data-stu-id="77195-237">status</span></span> | <span data-ttu-id="77195-238">Waarschuwingen categoriseren *(als Nieuw,* *Actief* *of Opgelost).*</span><span class="sxs-lookup"><span data-stu-id="77195-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="77195-239">Het kan u helpen bij het organiseren en beheren van uw reactie op waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="77195-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="77195-240">Nieuw</span><span class="sxs-lookup"><span data-stu-id="77195-240">New</span></span>
<span data-ttu-id="77195-241">ernst</span><span class="sxs-lookup"><span data-stu-id="77195-241">severity</span></span> | <span data-ttu-id="77195-242">Geeft de mogelijke invloed op activa aan.</span><span class="sxs-lookup"><span data-stu-id="77195-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="77195-243">Hoe hoger de ernst, hoe groter de impact.</span><span class="sxs-lookup"><span data-stu-id="77195-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="77195-244">Items met een hogere ernst vereisen meestal de meest directe aandacht.</span><span class="sxs-lookup"><span data-stu-id="77195-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="77195-245">Een van de volgende waarden: *Informatief,* \*Laag,\*\*Normaal en *Hoog.*</span><span class="sxs-lookup"><span data-stu-id="77195-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="77195-246">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="77195-246">Medium</span></span>
<span data-ttu-id="77195-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="77195-247">investigationId</span></span> | <span data-ttu-id="77195-248">De automatische onderzoeks-id die is geactiveerd door deze waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="77195-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="77195-249">1234</span><span class="sxs-lookup"><span data-stu-id="77195-249">1234</span></span>
<span data-ttu-id="77195-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="77195-250">investigationState</span></span> | <span data-ttu-id="77195-251">Informatie over de huidige status van het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="77195-251">Information on the investigation's current status.</span></span> <span data-ttu-id="77195-252">Een van de volgende waarden: *Unknown,* *Terminated*, *SuccessfullyRemediated,* *Benign,* *Failed,* *PartiallyRemediated,* *Running*, *PendingApproval,* *PendingResource,* *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="77195-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="77195-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="77195-253">UnsupportedAlertType</span></span>
<span data-ttu-id="77195-254">classificatie</span><span class="sxs-lookup"><span data-stu-id="77195-254">classification</span></span> | <span data-ttu-id="77195-255">De specificatie voor het incident.</span><span class="sxs-lookup"><span data-stu-id="77195-255">The specification for the incident.</span></span> <span data-ttu-id="77195-256">De eigenschapswaarden *zijn: Onbekend,* *FalsePositive,* *TruePositive* of *null*</span><span class="sxs-lookup"><span data-stu-id="77195-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="77195-257">Unknown</span><span class="sxs-lookup"><span data-stu-id="77195-257">Unknown</span></span>
<span data-ttu-id="77195-258">besluit</span><span class="sxs-lookup"><span data-stu-id="77195-258">determination</span></span> | <span data-ttu-id="77195-259">Bepaalt de vaststelling van het incident.</span><span class="sxs-lookup"><span data-stu-id="77195-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="77195-260">De eigenschapswaarden zijn: *NotAvailable,* *Apt,* *Malware,* *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware,* *Other* of  *null*</span><span class="sxs-lookup"><span data-stu-id="77195-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="77195-261">Pt</span><span class="sxs-lookup"><span data-stu-id="77195-261">Apt</span></span>
<span data-ttu-id="77195-262">toegewezen Aan</span><span class="sxs-lookup"><span data-stu-id="77195-262">assignedTo</span></span> | <span data-ttu-id="77195-263">Eigenaar van het incident of *null* als er geen eigenaar is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="77195-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="77195-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="77195-264">secop2@contoso.com</span></span>
<span data-ttu-id="77195-265">actorName</span><span class="sxs-lookup"><span data-stu-id="77195-265">actorName</span></span> | <span data-ttu-id="77195-266">De activiteitengroep, indien van gebruik, die is gekoppeld aan deze waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="77195-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="77195-267">BORON</span><span class="sxs-lookup"><span data-stu-id="77195-267">BORON</span></span>
<span data-ttu-id="77195-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="77195-268">threatFamilyName</span></span> | <span data-ttu-id="77195-269">Bedreigingsfamilie gekoppeld aan deze waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="77195-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="77195-270">null</span><span class="sxs-lookup"><span data-stu-id="77195-270">null</span></span>
<span data-ttu-id="77195-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="77195-271">mitreTechniques</span></span> | <span data-ttu-id="77195-272">De technieken voor aanvallen, die zijn uitgelijnd met de [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span><span class="sxs-lookup"><span data-stu-id="77195-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="77195-273">apparaten</span><span class="sxs-lookup"><span data-stu-id="77195-273">devices</span></span> | <span data-ttu-id="77195-274">Alle apparaten waarop waarschuwingen met betrekking tot het incident zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="77195-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="77195-275">\[\] (zie de details van entiteitsvelden hieronder)</span><span class="sxs-lookup"><span data-stu-id="77195-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="77195-276">Apparaatindeling</span><span class="sxs-lookup"><span data-stu-id="77195-276">Device format</span></span>

<span data-ttu-id="77195-277">Veldnaam</span><span class="sxs-lookup"><span data-stu-id="77195-277">Field name</span></span> | <span data-ttu-id="77195-278">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="77195-278">Description</span></span> | <span data-ttu-id="77195-279">Voorbeeldwaarde</span><span class="sxs-lookup"><span data-stu-id="77195-279">Example value</span></span>
-|-|-
<span data-ttu-id="77195-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="77195-280">DeviceId</span></span> | <span data-ttu-id="77195-281">De apparaat-id zoals aangegeven in Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="77195-281">The device ID as designated in Microsoft Defender ATP.</span></span> | <span data-ttu-id="77195-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="77195-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="77195-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="77195-283">aadDeviceId</span></span> |  <span data-ttu-id="77195-284">De apparaat-id zoals aangegeven in [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="77195-284">The device ID as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="77195-285">Alleen beschikbaar voor apparaten die lid zijn van een domein.</span><span class="sxs-lookup"><span data-stu-id="77195-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="77195-286">null</span><span class="sxs-lookup"><span data-stu-id="77195-286">null</span></span>
<span data-ttu-id="77195-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="77195-287">deviceDnsName</span></span> | <span data-ttu-id="77195-288">De volledig gekwalificeerde domeinnaam voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="77195-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="77195-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="77195-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="77195-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="77195-290">osPlatform</span></span> | <span data-ttu-id="77195-291">Het besturingssysteemplatform waarop het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="77195-291">The OS platform the device is running.</span></span>| <span data-ttu-id="77195-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="77195-292">WindowsServer2016</span></span>
<span data-ttu-id="77195-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="77195-293">osBuild</span></span> | <span data-ttu-id="77195-294">De buildversie van het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="77195-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="77195-295">14393</span><span class="sxs-lookup"><span data-stu-id="77195-295">14393</span></span>
<span data-ttu-id="77195-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="77195-296">rbacGroupName</span></span> | <span data-ttu-id="77195-297">De [groep toegangsbeheer](https://docs.microsoft.com/azure/role-based-access-control/overview) op basis van rollen die aan het apparaat is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="77195-297">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="77195-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="77195-298">WDATP-Ring0</span></span>
<span data-ttu-id="77195-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="77195-299">firstSeen</span></span> | <span data-ttu-id="77195-300">Het tijdstip waarop het apparaat voor het eerst werd gezien.</span><span class="sxs-lookup"><span data-stu-id="77195-300">Time when device was first seen.</span></span> | <span data-ttu-id="77195-301">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="77195-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="77195-302">statusstatus</span><span class="sxs-lookup"><span data-stu-id="77195-302">healthStatus</span></span> | <span data-ttu-id="77195-303">De status van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="77195-303">The health state of the device.</span></span> | <span data-ttu-id="77195-304">Actief</span><span class="sxs-lookup"><span data-stu-id="77195-304">Active</span></span>
<span data-ttu-id="77195-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="77195-305">riskScore</span></span> | <span data-ttu-id="77195-306">De risicoscore voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="77195-306">The risk score for the  device.</span></span> | <span data-ttu-id="77195-307">Hoog</span><span class="sxs-lookup"><span data-stu-id="77195-307">High</span></span>
<span data-ttu-id="77195-308">entiteiten</span><span class="sxs-lookup"><span data-stu-id="77195-308">entities</span></span> | <span data-ttu-id="77195-309">Alle entiteiten die zijn geïdentificeerd als onderdeel van, of gerelateerd aan, een bepaalde waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="77195-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="77195-310">\[\] (zie de details van entiteitsvelden hieronder)</span><span class="sxs-lookup"><span data-stu-id="77195-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="77195-311">Entiteitsindeling</span><span class="sxs-lookup"><span data-stu-id="77195-311">Entity Format</span></span>

<span data-ttu-id="77195-312">Veldnaam</span><span class="sxs-lookup"><span data-stu-id="77195-312">Field name</span></span> | <span data-ttu-id="77195-313">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="77195-313">Description</span></span> | <span data-ttu-id="77195-314">Voorbeeldwaarde</span><span class="sxs-lookup"><span data-stu-id="77195-314">Example value</span></span>
-|-|-
<span data-ttu-id="77195-315">entityType</span><span class="sxs-lookup"><span data-stu-id="77195-315">entityType</span></span> | <span data-ttu-id="77195-316">Entiteiten die zijn geïdentificeerd als onderdeel van of gerelateerd aan een bepaalde waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="77195-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="77195-317">De eigenschappenwaarden zijn: *Gebruiker*, *IP*, *URL*, *Bestand*, *Proces*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span><span class="sxs-lookup"><span data-stu-id="77195-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="77195-318">Gebruiker</span><span class="sxs-lookup"><span data-stu-id="77195-318">User</span></span>
<span data-ttu-id="77195-319">sha1</span><span class="sxs-lookup"><span data-stu-id="77195-319">sha1</span></span> | <span data-ttu-id="77195-320">Beschikbaar als entityType *Bestand* is.</span><span class="sxs-lookup"><span data-stu-id="77195-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="77195-321">De bestandshash voor waarschuwingen die zijn gekoppeld aan een bestand of proces.</span><span class="sxs-lookup"><span data-stu-id="77195-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="77195-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="77195-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="77195-323">sha256</span><span class="sxs-lookup"><span data-stu-id="77195-323">sha256</span></span> | <span data-ttu-id="77195-324">Beschikbaar als entityType *Bestand* is.</span><span class="sxs-lookup"><span data-stu-id="77195-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="77195-325">De bestandshash voor waarschuwingen die zijn gekoppeld aan een bestand of proces.</span><span class="sxs-lookup"><span data-stu-id="77195-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="77195-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="77195-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="77195-327">fileName</span><span class="sxs-lookup"><span data-stu-id="77195-327">fileName</span></span> | <span data-ttu-id="77195-328">Beschikbaar als entityType *Bestand* is.</span><span class="sxs-lookup"><span data-stu-id="77195-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="77195-329">De bestandsnaam voor waarschuwingen die zijn gekoppeld aan een bestand of proces</span><span class="sxs-lookup"><span data-stu-id="77195-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="77195-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="77195-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="77195-331">filePath</span><span class="sxs-lookup"><span data-stu-id="77195-331">filePath</span></span> | <span data-ttu-id="77195-332">Beschikbaar als entityType *Bestand* is.</span><span class="sxs-lookup"><span data-stu-id="77195-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="77195-333">Het bestandspad voor waarschuwingen die aan een bestand of proces zijn gekoppeld</span><span class="sxs-lookup"><span data-stu-id="77195-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="77195-334">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="77195-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="77195-335">processId</span><span class="sxs-lookup"><span data-stu-id="77195-335">processId</span></span> | <span data-ttu-id="77195-336">Beschikbaar als entityType *Process* is.</span><span class="sxs-lookup"><span data-stu-id="77195-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="77195-337">24348</span><span class="sxs-lookup"><span data-stu-id="77195-337">24348</span></span>
<span data-ttu-id="77195-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="77195-338">processCommandLine</span></span> | <span data-ttu-id="77195-339">Beschikbaar als entityType *Process* is.</span><span class="sxs-lookup"><span data-stu-id="77195-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="77195-340">"Your File is ready to Download \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="77195-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="77195-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="77195-341">processCreationTime</span></span> | <span data-ttu-id="77195-342">Beschikbaar als entityType *Process* is.</span><span class="sxs-lookup"><span data-stu-id="77195-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="77195-343">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="77195-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="77195-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="77195-344">parentProcessId</span></span> | <span data-ttu-id="77195-345">Beschikbaar als entityType *Process* is.</span><span class="sxs-lookup"><span data-stu-id="77195-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="77195-346">16840</span><span class="sxs-lookup"><span data-stu-id="77195-346">16840</span></span>
<span data-ttu-id="77195-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="77195-347">parentProcessCreationTime</span></span> | <span data-ttu-id="77195-348">Beschikbaar als entityType *Process* is.</span><span class="sxs-lookup"><span data-stu-id="77195-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="77195-349">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="77195-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="77195-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="77195-350">ipAddress</span></span> | <span data-ttu-id="77195-351">Beschikbaar als entityType *Ip* is.</span><span class="sxs-lookup"><span data-stu-id="77195-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="77195-352">HET IP-adres voor waarschuwingen die zijn gekoppeld aan netwerkgebeurtenissen, zoals Communicatie *met een schadelijk netwerkdoel.*</span><span class="sxs-lookup"><span data-stu-id="77195-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="77195-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="77195-353">62.216.203.204</span></span>
<span data-ttu-id="77195-354">url</span><span class="sxs-lookup"><span data-stu-id="77195-354">url</span></span> | <span data-ttu-id="77195-355">Beschikbaar als entityType *URL* is.</span><span class="sxs-lookup"><span data-stu-id="77195-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="77195-356">Url voor waarschuwingen die zijn gekoppeld aan netwerkgebeurtenissen, zoals Communicatie *met een schadelijk netwerkdoel.*</span><span class="sxs-lookup"><span data-stu-id="77195-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="77195-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="77195-357">down.esales360.cn</span></span>
<span data-ttu-id="77195-358">accountName</span><span class="sxs-lookup"><span data-stu-id="77195-358">accountName</span></span> | <span data-ttu-id="77195-359">Beschikbaar als entityType *Gebruiker* is.</span><span class="sxs-lookup"><span data-stu-id="77195-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="77195-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="77195-360">testUser2</span></span>
<span data-ttu-id="77195-361">domainName</span><span class="sxs-lookup"><span data-stu-id="77195-361">domainName</span></span> | <span data-ttu-id="77195-362">Beschikbaar als entityType *Gebruiker* is.</span><span class="sxs-lookup"><span data-stu-id="77195-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="77195-363">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="77195-363">europe.corp.contoso</span></span>
<span data-ttu-id="77195-364">userSid</span><span class="sxs-lookup"><span data-stu-id="77195-364">userSid</span></span> | <span data-ttu-id="77195-365">Beschikbaar als entityType *Gebruiker* is.</span><span class="sxs-lookup"><span data-stu-id="77195-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="77195-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="77195-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="77195-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="77195-367">aadUserId</span></span> | <span data-ttu-id="77195-368">Beschikbaar als entityType *Gebruiker* is.</span><span class="sxs-lookup"><span data-stu-id="77195-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="77195-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="77195-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="77195-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="77195-370">userPrincipalName</span></span> | <span data-ttu-id="77195-371">Beschikbaar als entityType *User* / *MailBox* / *MailMessage is.*</span><span class="sxs-lookup"><span data-stu-id="77195-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="77195-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="77195-372">testUser2@contoso.com</span></span>
<span data-ttu-id="77195-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="77195-373">mailboxDisplayName</span></span> | <span data-ttu-id="77195-374">Beschikbaar als entityType *MailBox* is.</span><span class="sxs-lookup"><span data-stu-id="77195-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="77195-375">gebruiker2 testen</span><span class="sxs-lookup"><span data-stu-id="77195-375">test User2</span></span>
<span data-ttu-id="77195-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="77195-376">mailboxAddress</span></span> | <span data-ttu-id="77195-377">Beschikbaar als entityType *User* / *MailBox* / *MailMessage is.*</span><span class="sxs-lookup"><span data-stu-id="77195-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="77195-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="77195-378">testUser2@contoso.com</span></span>
<span data-ttu-id="77195-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="77195-379">clusterBy</span></span> | <span data-ttu-id="77195-380">Beschikbaar als entityType  *MailCluster* is.</span><span class="sxs-lookup"><span data-stu-id="77195-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="77195-381">Onderwerp; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="77195-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="77195-382">afzender</span><span class="sxs-lookup"><span data-stu-id="77195-382">sender</span></span> | <span data-ttu-id="77195-383">Beschikbaar als entityType *User* / *MailBox* / *MailMessage is.*</span><span class="sxs-lookup"><span data-stu-id="77195-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="77195-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="77195-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="77195-385">geadresseerde</span><span class="sxs-lookup"><span data-stu-id="77195-385">recipient</span></span> | <span data-ttu-id="77195-386">Beschikbaar als entityType *MailMessage* is.</span><span class="sxs-lookup"><span data-stu-id="77195-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="77195-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="77195-387">testUser2@contoso.com</span></span>
<span data-ttu-id="77195-388">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="77195-388">subject</span></span> | <span data-ttu-id="77195-389">Beschikbaar als entityType *MailMessage* is.</span><span class="sxs-lookup"><span data-stu-id="77195-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="77195-390">\[EXTERNE \] aandacht</span><span class="sxs-lookup"><span data-stu-id="77195-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="77195-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="77195-391">deliveryAction</span></span> | <span data-ttu-id="77195-392">Beschikbaar als entityType *MailMessage* is.</span><span class="sxs-lookup"><span data-stu-id="77195-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="77195-393">Geleverd</span><span class="sxs-lookup"><span data-stu-id="77195-393">Delivered</span></span>
<span data-ttu-id="77195-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="77195-394">securityGroupId</span></span> | <span data-ttu-id="77195-395">Beschikbaar als entityType  *SecurityGroup* is.</span><span class="sxs-lookup"><span data-stu-id="77195-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="77195-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="77195-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="77195-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="77195-397">securityGroupName</span></span> | <span data-ttu-id="77195-398">Beschikbaar als entityType  *SecurityGroup* is.</span><span class="sxs-lookup"><span data-stu-id="77195-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="77195-399">Netwerkconfiguratieoperatoren</span><span class="sxs-lookup"><span data-stu-id="77195-399">Network Configuration Operators</span></span>
<span data-ttu-id="77195-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="77195-400">registryHive</span></span> | <span data-ttu-id="77195-401">Beschikbaar als entityType het  *register* is.</span><span class="sxs-lookup"><span data-stu-id="77195-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="77195-402">LOKALE \_ \_ HKEY-COMPUTER</span><span class="sxs-lookup"><span data-stu-id="77195-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="77195-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="77195-403">registryKey</span></span> | <span data-ttu-id="77195-404">Beschikbaar als entityType het  *register* is.</span><span class="sxs-lookup"><span data-stu-id="77195-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="77195-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="77195-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="77195-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="77195-406">registryValueType</span></span> | <span data-ttu-id="77195-407">Beschikbaar als entityType het  *register* is.</span><span class="sxs-lookup"><span data-stu-id="77195-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="77195-408">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="77195-408">String</span></span>
<span data-ttu-id="77195-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="77195-409">registryValue</span></span> | <span data-ttu-id="77195-410">Beschikbaar als entityType het  *register* is.</span><span class="sxs-lookup"><span data-stu-id="77195-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="77195-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="77195-411">31-00-00-00</span></span>
<span data-ttu-id="77195-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="77195-412">deviceId</span></span> | <span data-ttu-id="77195-413">De id van het apparaat dat is gerelateerd aan de entiteit.</span><span class="sxs-lookup"><span data-stu-id="77195-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="77195-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="77195-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="77195-415">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="77195-415">Example</span></span>

<span data-ttu-id="77195-416">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="77195-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="77195-417">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="77195-417">**Response**</span></span>

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="77195-418">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="77195-418">Related articles</span></span>

- [<span data-ttu-id="77195-419">Toegang tot de Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="77195-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="77195-420">Meer informatie over API-limieten en licenties</span><span class="sxs-lookup"><span data-stu-id="77195-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="77195-421">Meer te weten komen over foutcodes</span><span class="sxs-lookup"><span data-stu-id="77195-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="77195-422">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="77195-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="77195-423">API's voor incidenten</span><span class="sxs-lookup"><span data-stu-id="77195-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="77195-424">Update-incident-API</span><span class="sxs-lookup"><span data-stu-id="77195-424">Update incident API</span></span>](api-update-incidents.md)
