---
title: Lijstincidenten-API in Microsoft 365 Defender
description: Informatie over het lijst maken van incidenten-API in Microsoft 365 Defender
keywords: lijst, incident, incidenten, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7fb0de4f8dc67331e7acca59e70d061fe7c19493
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935735"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="856a6-104">Lijstincidenten-API in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="856a6-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="856a6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="856a6-105">**Applies to:**</span></span>

- <span data-ttu-id="856a6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="856a6-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="856a6-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="856a6-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="856a6-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="856a6-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="856a6-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="856a6-109">API description</span></span>

<span data-ttu-id="856a6-110">Met de LIJSTincidenten-API kunt u incidenten sorteren om een geïnformeerd antwoord op cyberbeveiliging te maken.</span><span class="sxs-lookup"><span data-stu-id="856a6-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="856a6-111">Het toont een verzameling incidenten die zijn gemarkeerd in uw netwerk, binnen het tijdbereik dat u hebt opgegeven in uw beleid voor het bewaren van de omgeving.</span><span class="sxs-lookup"><span data-stu-id="856a6-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="856a6-112">De meest recente incidenten worden boven aan de lijst weergegeven.</span><span class="sxs-lookup"><span data-stu-id="856a6-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="856a6-113">Elk incident bevat een matrix met gerelateerde waarschuwingen en de bijbehorende entiteiten.</span><span class="sxs-lookup"><span data-stu-id="856a6-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="856a6-114">De API ondersteunt de volgende **OData-operatoren:**</span><span class="sxs-lookup"><span data-stu-id="856a6-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="856a6-115">`$filter`op `lastUpdateTime` de , `createdTime` , en `status` eigenschappen `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="856a6-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="856a6-116">`$top`, met een maximumwaarde **van 100**</span><span class="sxs-lookup"><span data-stu-id="856a6-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="856a6-117">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="856a6-117">Limitations</span></span>

1. <span data-ttu-id="856a6-118">De maximale paginagrootte is **100 incidenten.**</span><span class="sxs-lookup"><span data-stu-id="856a6-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="856a6-119">Het maximumtarief voor aanvragen is **50 oproepen per minuut** en **1500 oproepen per uur.**</span><span class="sxs-lookup"><span data-stu-id="856a6-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="856a6-120">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="856a6-120">Permissions</span></span>

<span data-ttu-id="856a6-121">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="856a6-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="856a6-122">Zie [Access Microsoft 365 Defender API's](api-access.md) voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="856a6-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="856a6-123">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="856a6-123">Permission type</span></span> | <span data-ttu-id="856a6-124">Machtiging</span><span class="sxs-lookup"><span data-stu-id="856a6-124">Permission</span></span> | <span data-ttu-id="856a6-125">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="856a6-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="856a6-126">Toepassing</span><span class="sxs-lookup"><span data-stu-id="856a6-126">Application</span></span> | <span data-ttu-id="856a6-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="856a6-127">Incident.Read.All</span></span> | <span data-ttu-id="856a6-128">Alle incidenten lezen</span><span class="sxs-lookup"><span data-stu-id="856a6-128">Read all incidents</span></span>
<span data-ttu-id="856a6-129">Toepassing</span><span class="sxs-lookup"><span data-stu-id="856a6-129">Application</span></span> | <span data-ttu-id="856a6-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="856a6-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="856a6-131">Alle incidenten lezen en schrijven</span><span class="sxs-lookup"><span data-stu-id="856a6-131">Read and write all incidents</span></span>
<span data-ttu-id="856a6-132">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="856a6-132">Delegated (work or school account)</span></span> | <span data-ttu-id="856a6-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="856a6-133">Incident.Read</span></span> | <span data-ttu-id="856a6-134">Incidenten lezen</span><span class="sxs-lookup"><span data-stu-id="856a6-134">Read incidents</span></span>
<span data-ttu-id="856a6-135">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="856a6-135">Delegated (work or school account)</span></span> | <span data-ttu-id="856a6-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="856a6-136">Incident.ReadWrite</span></span> | <span data-ttu-id="856a6-137">Incidenten lezen en schrijven</span><span class="sxs-lookup"><span data-stu-id="856a6-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="856a6-138">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="856a6-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="856a6-139">De gebruiker moet weergavemachtigingen hebben voor incidenten in de portal.</span><span class="sxs-lookup"><span data-stu-id="856a6-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="856a6-140">Het antwoord bevat alleen incidenten waar de gebruiker aan wordt blootgesteld.</span><span class="sxs-lookup"><span data-stu-id="856a6-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="856a6-141">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="856a6-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="856a6-142">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="856a6-142">Request headers</span></span>

<span data-ttu-id="856a6-143">Naam</span><span class="sxs-lookup"><span data-stu-id="856a6-143">Name</span></span> | <span data-ttu-id="856a6-144">Type</span><span class="sxs-lookup"><span data-stu-id="856a6-144">Type</span></span> | <span data-ttu-id="856a6-145">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="856a6-145">Description</span></span>
-|-|-
<span data-ttu-id="856a6-146">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="856a6-146">Authorization</span></span> | <span data-ttu-id="856a6-147">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="856a6-147">String</span></span> | <span data-ttu-id="856a6-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="856a6-148">Bearer {token}.</span></span> <span data-ttu-id="856a6-149">**Vereist**</span><span class="sxs-lookup"><span data-stu-id="856a6-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="856a6-150">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="856a6-150">Request body</span></span>

<span data-ttu-id="856a6-151">Geen.</span><span class="sxs-lookup"><span data-stu-id="856a6-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="856a6-152">Antwoord</span><span class="sxs-lookup"><span data-stu-id="856a6-152">Response</span></span>

<span data-ttu-id="856a6-153">Als dit is gelukt, retourneert deze `200 OK` methode en een lijst met [incidenten](api-incident.md) in de antwoord-body.</span><span class="sxs-lookup"><span data-stu-id="856a6-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="856a6-154">Schematoewijzing</span><span class="sxs-lookup"><span data-stu-id="856a6-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="856a6-155">Metagegevens voor incidenten</span><span class="sxs-lookup"><span data-stu-id="856a6-155">Incident metadata</span></span>

<span data-ttu-id="856a6-156">Veldnaam</span><span class="sxs-lookup"><span data-stu-id="856a6-156">Field name</span></span> | <span data-ttu-id="856a6-157">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="856a6-157">Description</span></span> | <span data-ttu-id="856a6-158">Voorbeeldwaarde</span><span class="sxs-lookup"><span data-stu-id="856a6-158">Example value</span></span>
-|-|-
<span data-ttu-id="856a6-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="856a6-159">incidentId</span></span> | <span data-ttu-id="856a6-160">Unieke id voor het incident</span><span class="sxs-lookup"><span data-stu-id="856a6-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="856a6-161">924565</span><span class="sxs-lookup"><span data-stu-id="856a6-161">924565</span></span>
<span data-ttu-id="856a6-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="856a6-162">redirectIncidentId</span></span> | <span data-ttu-id="856a6-163">Alleen ingevuld als een incident wordt gegroepeerd met een ander incident, als onderdeel van de logica voor het verwerken van incidenten.</span><span class="sxs-lookup"><span data-stu-id="856a6-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="856a6-164">924569</span><span class="sxs-lookup"><span data-stu-id="856a6-164">924569</span></span>
<span data-ttu-id="856a6-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="856a6-165">incidentName</span></span> | <span data-ttu-id="856a6-166">Tekenreekswaarde beschikbaar voor elk incident.</span><span class="sxs-lookup"><span data-stu-id="856a6-166">String value available for every incident.</span></span> | <span data-ttu-id="856a6-167">Ransomware-activiteit</span><span class="sxs-lookup"><span data-stu-id="856a6-167">Ransomware activity</span></span>
<span data-ttu-id="856a6-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="856a6-168">createdTime</span></span> | <span data-ttu-id="856a6-169">Tijd waarop het incident voor het eerst is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="856a6-169">Time when incident was first created.</span></span> | <span data-ttu-id="856a6-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="856a6-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="856a6-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="856a6-171">lastUpdateTime</span></span> | <span data-ttu-id="856a6-172">Tijd waarop het incident voor het laatst is bijgewerkt op de back-backend.</span><span class="sxs-lookup"><span data-stu-id="856a6-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="856a6-173">Dit veld kan worden gebruikt wanneer u de aanvraagparameter instelt voor de periode waarin incidenten worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="856a6-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="856a6-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="856a6-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="856a6-175">toegewezenTo</span><span class="sxs-lookup"><span data-stu-id="856a6-175">assignedTo</span></span> | <span data-ttu-id="856a6-176">Eigenaar van het incident of *null als* er geen eigenaar is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="856a6-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="856a6-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="856a6-177">secop2@contoso.com</span></span>
<span data-ttu-id="856a6-178">classificatie</span><span class="sxs-lookup"><span data-stu-id="856a6-178">classification</span></span> | <span data-ttu-id="856a6-179">De specificatie voor het incident.</span><span class="sxs-lookup"><span data-stu-id="856a6-179">The specification for the incident.</span></span> <span data-ttu-id="856a6-180">De eigenschapswaarden zijn: *Onbekend*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="856a6-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="856a6-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="856a6-181">Unknown</span></span>
<span data-ttu-id="856a6-182">bepaling</span><span class="sxs-lookup"><span data-stu-id="856a6-182">determination</span></span> | <span data-ttu-id="856a6-183">Hiermee geeft u de bepaling van het incident op.</span><span class="sxs-lookup"><span data-stu-id="856a6-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="856a6-184">De eigenschapswaarden zijn: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span><span class="sxs-lookup"><span data-stu-id="856a6-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="856a6-185">Niet beschikbaar</span><span class="sxs-lookup"><span data-stu-id="856a6-185">NotAvailable</span></span>
<span data-ttu-id="856a6-186">status</span><span class="sxs-lookup"><span data-stu-id="856a6-186">status</span></span> | <span data-ttu-id="856a6-187">Categoriseer incidenten *(zoals Actief* of *Opgelost).*</span><span class="sxs-lookup"><span data-stu-id="856a6-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="856a6-188">Het kan u helpen bij het organiseren en beheren van uw reactie op incidenten.</span><span class="sxs-lookup"><span data-stu-id="856a6-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="856a6-189">Actief</span><span class="sxs-lookup"><span data-stu-id="856a6-189">Active</span></span>
<span data-ttu-id="856a6-190">ernst</span><span class="sxs-lookup"><span data-stu-id="856a6-190">severity</span></span> | <span data-ttu-id="856a6-191">Geeft de mogelijke impact op activa aan.</span><span class="sxs-lookup"><span data-stu-id="856a6-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="856a6-192">Hoe hoger de ernst, hoe groter de impact.</span><span class="sxs-lookup"><span data-stu-id="856a6-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="856a6-193">Meestal hebben items met een hogere ernst de meest directe aandacht nodig.</span><span class="sxs-lookup"><span data-stu-id="856a6-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="856a6-194">Een van de volgende waarden: *Informatief*, *Laag*, \*Gemiddeld en *Hoog*.</span><span class="sxs-lookup"><span data-stu-id="856a6-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="856a6-195">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="856a6-195">Medium</span></span>
<span data-ttu-id="856a6-196">tags</span><span class="sxs-lookup"><span data-stu-id="856a6-196">tags</span></span> | <span data-ttu-id="856a6-197">Matrix met aangepaste tags die zijn gekoppeld aan een incident, bijvoorbeeld om een vlag toe te voegen aan een groep incidenten met een gemeenschappelijke eigenschap.</span><span class="sxs-lookup"><span data-stu-id="856a6-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="856a6-198">waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="856a6-198">alerts</span></span> | <span data-ttu-id="856a6-199">Matrix met alle waarschuwingen die betrekking hebben op het incident, plus andere informatie, zoals ernst, entiteiten die betrokken waren bij de waarschuwing en de bron van de waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="856a6-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="856a6-200">\[\] (zie details over waarschuwingsvelden hieronder)</span><span class="sxs-lookup"><span data-stu-id="856a6-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="856a6-201">Metagegevens voor waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="856a6-201">Alerts metadata</span></span>

<span data-ttu-id="856a6-202">Veldnaam</span><span class="sxs-lookup"><span data-stu-id="856a6-202">Field name</span></span> | <span data-ttu-id="856a6-203">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="856a6-203">Description</span></span> | <span data-ttu-id="856a6-204">Voorbeeldwaarde</span><span class="sxs-lookup"><span data-stu-id="856a6-204">Example value</span></span>
-|-|-
<span data-ttu-id="856a6-205">alertId</span><span class="sxs-lookup"><span data-stu-id="856a6-205">alertId</span></span> | <span data-ttu-id="856a6-206">Unieke id om de waarschuwing weer te geven</span><span class="sxs-lookup"><span data-stu-id="856a6-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="856a6-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="856a6-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="856a6-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="856a6-208">incidentId</span></span> | <span data-ttu-id="856a6-209">Unieke id voor het incident waar deze waarschuwing aan is gekoppeld</span><span class="sxs-lookup"><span data-stu-id="856a6-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="856a6-210">924565</span><span class="sxs-lookup"><span data-stu-id="856a6-210">924565</span></span>
<span data-ttu-id="856a6-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="856a6-211">serviceSource</span></span> | <span data-ttu-id="856a6-212">Service waar de waarschuwing vandaan komt, zoals Microsoft Defender voor Eindpunt, Microsoft Cloud App Security, Microsoft Defender voor identiteit of Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="856a6-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="856a6-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="856a6-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="856a6-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="856a6-214">creationTime</span></span> | <span data-ttu-id="856a6-215">Tijd waarop de waarschuwing voor het eerst is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="856a6-215">Time when alert was first created.</span></span> | <span data-ttu-id="856a6-216">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="856a6-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="856a6-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="856a6-217">lastUpdatedTime</span></span> | <span data-ttu-id="856a6-218">Tijd waarop de waarschuwing voor het laatst is bijgewerkt bij de back-end.</span><span class="sxs-lookup"><span data-stu-id="856a6-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="856a6-219">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="856a6-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="856a6-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="856a6-220">resolvedTime</span></span> | <span data-ttu-id="856a6-221">Tijd waarop de waarschuwing is opgelost.</span><span class="sxs-lookup"><span data-stu-id="856a6-221">Time when alert was resolved.</span></span> | <span data-ttu-id="856a6-222">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="856a6-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="856a6-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="856a6-223">firstActivity</span></span> | <span data-ttu-id="856a6-224">Tijd waarop de waarschuwing voor het eerst heeft gemeld dat de activiteit is bijgewerkt bij de backend.</span><span class="sxs-lookup"><span data-stu-id="856a6-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="856a6-225">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="856a6-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="856a6-226">titel</span><span class="sxs-lookup"><span data-stu-id="856a6-226">title</span></span> | <span data-ttu-id="856a6-227">Korte beschrijving van de tekenreekswaarde die beschikbaar is voor elke waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="856a6-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="856a6-228">Ransomware-activiteit</span><span class="sxs-lookup"><span data-stu-id="856a6-228">Ransomware activity</span></span>
<span data-ttu-id="856a6-229">beschrijving</span><span class="sxs-lookup"><span data-stu-id="856a6-229">description</span></span> | <span data-ttu-id="856a6-230">Tekenreekswaarde die elke waarschuwing beschrijft.</span><span class="sxs-lookup"><span data-stu-id="856a6-230">String value describing each alert.</span></span> | <span data-ttu-id="856a6-231">De gebruiker Test User2 (testUser2@contoso.com) heeft 99 bestanden gemanipuleerd met meerdere extensies die eindigen op de ongewone *extensie herunterladen.*</span><span class="sxs-lookup"><span data-stu-id="856a6-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="856a6-232">Dit is een ongebruikelijk aantal bestandsmanipulaties en is een indicatie van een mogelijke ransomware-aanval.</span><span class="sxs-lookup"><span data-stu-id="856a6-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="856a6-233">categorie</span><span class="sxs-lookup"><span data-stu-id="856a6-233">category</span></span> | <span data-ttu-id="856a6-234">Visuele en numerieke weergave van de voortgang van de aanval in de kill chain.</span><span class="sxs-lookup"><span data-stu-id="856a6-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="856a6-235">Uitgelijnd op het [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="856a6-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="856a6-236">Gevolg</span><span class="sxs-lookup"><span data-stu-id="856a6-236">Impact</span></span>
<span data-ttu-id="856a6-237">status</span><span class="sxs-lookup"><span data-stu-id="856a6-237">status</span></span> | <span data-ttu-id="856a6-238">Waarschuwingen categoriseren *(als Nieuw,* *Actief* of *Opgelost).*</span><span class="sxs-lookup"><span data-stu-id="856a6-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="856a6-239">Het kan u helpen bij het organiseren en beheren van uw antwoord op waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="856a6-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="856a6-240">Nieuw</span><span class="sxs-lookup"><span data-stu-id="856a6-240">New</span></span>
<span data-ttu-id="856a6-241">ernst</span><span class="sxs-lookup"><span data-stu-id="856a6-241">severity</span></span> | <span data-ttu-id="856a6-242">Geeft de mogelijke impact op activa aan.</span><span class="sxs-lookup"><span data-stu-id="856a6-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="856a6-243">Hoe hoger de ernst, hoe groter de impact.</span><span class="sxs-lookup"><span data-stu-id="856a6-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="856a6-244">Meestal hebben items met een hogere ernst de meest directe aandacht nodig.</span><span class="sxs-lookup"><span data-stu-id="856a6-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="856a6-245">Een van de volgende waarden: *Informatief*, *Laag*, \*Gemiddeld en *Hoog*.</span><span class="sxs-lookup"><span data-stu-id="856a6-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="856a6-246">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="856a6-246">Medium</span></span>
<span data-ttu-id="856a6-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="856a6-247">investigationId</span></span> | <span data-ttu-id="856a6-248">De automatische onderzoeks-id die door deze waarschuwing wordt geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="856a6-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="856a6-249">1234</span><span class="sxs-lookup"><span data-stu-id="856a6-249">1234</span></span>
<span data-ttu-id="856a6-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="856a6-250">investigationState</span></span> | <span data-ttu-id="856a6-251">Informatie over de huidige status van het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="856a6-251">Information on the investigation's current status.</span></span> <span data-ttu-id="856a6-252">Een van de volgende waarden: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Goedign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, PartiallyInvestigated , *TerminatedByUser*, *TerminatedBySystem*, *Queued* , *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="856a6-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="856a6-253">Niet-ondersteundAlertType</span><span class="sxs-lookup"><span data-stu-id="856a6-253">UnsupportedAlertType</span></span>
<span data-ttu-id="856a6-254">classificatie</span><span class="sxs-lookup"><span data-stu-id="856a6-254">classification</span></span> | <span data-ttu-id="856a6-255">De specificatie voor het incident.</span><span class="sxs-lookup"><span data-stu-id="856a6-255">The specification for the incident.</span></span> <span data-ttu-id="856a6-256">De eigenschapswaarden zijn: *Onbekend,* *FalsePositive,* *TruePositive* of *null*</span><span class="sxs-lookup"><span data-stu-id="856a6-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="856a6-257">Unknown</span><span class="sxs-lookup"><span data-stu-id="856a6-257">Unknown</span></span>
<span data-ttu-id="856a6-258">bepaling</span><span class="sxs-lookup"><span data-stu-id="856a6-258">determination</span></span> | <span data-ttu-id="856a6-259">Hiermee geeft u de bepaling van het incident op.</span><span class="sxs-lookup"><span data-stu-id="856a6-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="856a6-260">De eigenschapswaarden zijn: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span><span class="sxs-lookup"><span data-stu-id="856a6-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="856a6-261">Apt</span><span class="sxs-lookup"><span data-stu-id="856a6-261">Apt</span></span>
<span data-ttu-id="856a6-262">toegewezenTo</span><span class="sxs-lookup"><span data-stu-id="856a6-262">assignedTo</span></span> | <span data-ttu-id="856a6-263">Eigenaar van het incident of *null als* er geen eigenaar is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="856a6-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="856a6-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="856a6-264">secop2@contoso.com</span></span>
<span data-ttu-id="856a6-265">actorName</span><span class="sxs-lookup"><span data-stu-id="856a6-265">actorName</span></span> | <span data-ttu-id="856a6-266">De groep activiteit, indien van de groep, de groep die aan deze waarschuwing is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="856a6-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="856a6-267">BORON</span><span class="sxs-lookup"><span data-stu-id="856a6-267">BORON</span></span>
<span data-ttu-id="856a6-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="856a6-268">threatFamilyName</span></span> | <span data-ttu-id="856a6-269">Bedreigingsfamilie die aan deze waarschuwing is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="856a6-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="856a6-270">null</span><span class="sxs-lookup"><span data-stu-id="856a6-270">null</span></span>
<span data-ttu-id="856a6-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="856a6-271">mitreTechniques</span></span> | <span data-ttu-id="856a6-272">De aanvalstechnieken, zoals uitgelijnd met de [MITRE ATT-&CK](https://attack.mitre.org/)™ framework.</span><span class="sxs-lookup"><span data-stu-id="856a6-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="856a6-273">apparaten</span><span class="sxs-lookup"><span data-stu-id="856a6-273">devices</span></span> | <span data-ttu-id="856a6-274">Alle apparaten waar waarschuwingen met betrekking tot het incident zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="856a6-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="856a6-275">\[\] (zie details over entiteitsvelden hieronder)</span><span class="sxs-lookup"><span data-stu-id="856a6-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="856a6-276">Apparaatindeling</span><span class="sxs-lookup"><span data-stu-id="856a6-276">Device format</span></span>

<span data-ttu-id="856a6-277">Veldnaam</span><span class="sxs-lookup"><span data-stu-id="856a6-277">Field name</span></span> | <span data-ttu-id="856a6-278">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="856a6-278">Description</span></span> | <span data-ttu-id="856a6-279">Voorbeeldwaarde</span><span class="sxs-lookup"><span data-stu-id="856a6-279">Example value</span></span>
-|-|-
<span data-ttu-id="856a6-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="856a6-280">DeviceId</span></span> | <span data-ttu-id="856a6-281">De apparaat-id zoals aangegeven in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="856a6-281">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="856a6-282">24c22b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="856a6-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="856a6-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="856a6-283">aadDeviceId</span></span> |  <span data-ttu-id="856a6-284">De apparaat-id zoals aangegeven in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="856a6-284">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="856a6-285">Alleen beschikbaar voor apparaten met een domein.</span><span class="sxs-lookup"><span data-stu-id="856a6-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="856a6-286">null</span><span class="sxs-lookup"><span data-stu-id="856a6-286">null</span></span>
<span data-ttu-id="856a6-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="856a6-287">deviceDnsName</span></span> | <span data-ttu-id="856a6-288">De volledig gekwalificeerde domeinnaam voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="856a6-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="856a6-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="856a6-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="856a6-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="856a6-290">osPlatform</span></span> | <span data-ttu-id="856a6-291">Het besturingssysteemplatform waarop het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="856a6-291">The OS platform the device is running.</span></span>| <span data-ttu-id="856a6-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="856a6-292">WindowsServer2016</span></span>
<span data-ttu-id="856a6-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="856a6-293">osBuild</span></span> | <span data-ttu-id="856a6-294">De buildversie voor het besturingssysteem dat op het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="856a6-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="856a6-295">14393</span><span class="sxs-lookup"><span data-stu-id="856a6-295">14393</span></span>
<span data-ttu-id="856a6-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="856a6-296">rbacGroupName</span></span> | <span data-ttu-id="856a6-297">De [RBAC-groep](/azure/role-based-access-control/overview) (Role Based Access Control) die is gekoppeld aan het apparaat.</span><span class="sxs-lookup"><span data-stu-id="856a6-297">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="856a6-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="856a6-298">WDATP-Ring0</span></span>
<span data-ttu-id="856a6-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="856a6-299">firstSeen</span></span> | <span data-ttu-id="856a6-300">Tijd waarop het apparaat voor het eerst werd gezien.</span><span class="sxs-lookup"><span data-stu-id="856a6-300">Time when device was first seen.</span></span> | <span data-ttu-id="856a6-301">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="856a6-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="856a6-302">statusStatus</span><span class="sxs-lookup"><span data-stu-id="856a6-302">healthStatus</span></span> | <span data-ttu-id="856a6-303">De status van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="856a6-303">The health state of the device.</span></span> | <span data-ttu-id="856a6-304">Actief</span><span class="sxs-lookup"><span data-stu-id="856a6-304">Active</span></span>
<span data-ttu-id="856a6-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="856a6-305">riskScore</span></span> | <span data-ttu-id="856a6-306">De risicoscore voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="856a6-306">The risk score for the  device.</span></span> | <span data-ttu-id="856a6-307">Hoog</span><span class="sxs-lookup"><span data-stu-id="856a6-307">High</span></span>
<span data-ttu-id="856a6-308">entiteiten</span><span class="sxs-lookup"><span data-stu-id="856a6-308">entities</span></span> | <span data-ttu-id="856a6-309">Alle entiteiten die zijn geïdentificeerd als onderdeel van of gerelateerd aan een bepaalde waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="856a6-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="856a6-310">\[\] (zie details over entiteitsvelden hieronder)</span><span class="sxs-lookup"><span data-stu-id="856a6-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="856a6-311">Entiteitsindeling</span><span class="sxs-lookup"><span data-stu-id="856a6-311">Entity Format</span></span>

<span data-ttu-id="856a6-312">Veldnaam</span><span class="sxs-lookup"><span data-stu-id="856a6-312">Field name</span></span> | <span data-ttu-id="856a6-313">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="856a6-313">Description</span></span> | <span data-ttu-id="856a6-314">Voorbeeldwaarde</span><span class="sxs-lookup"><span data-stu-id="856a6-314">Example value</span></span>
-|-|-
<span data-ttu-id="856a6-315">entityType</span><span class="sxs-lookup"><span data-stu-id="856a6-315">entityType</span></span> | <span data-ttu-id="856a6-316">Entiteiten die zijn geïdentificeerd als onderdeel van of gerelateerd aan een bepaalde waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="856a6-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="856a6-317">De eigenschappenwaarden zijn: *Gebruiker*, *Ip*, *Url*, *Bestand*, *Proces*, *MailBox*, *MailMessage*, *MailCluster*, *Register*</span><span class="sxs-lookup"><span data-stu-id="856a6-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="856a6-318">Gebruiker</span><span class="sxs-lookup"><span data-stu-id="856a6-318">User</span></span>
<span data-ttu-id="856a6-319">sha1</span><span class="sxs-lookup"><span data-stu-id="856a6-319">sha1</span></span> | <span data-ttu-id="856a6-320">Beschikbaar als entityType *Bestand* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="856a6-321">De bestandshash voor waarschuwingen die zijn gekoppeld aan een bestand of proces.</span><span class="sxs-lookup"><span data-stu-id="856a6-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="856a6-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="856a6-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="856a6-323">sha256</span><span class="sxs-lookup"><span data-stu-id="856a6-323">sha256</span></span> | <span data-ttu-id="856a6-324">Beschikbaar als entityType *Bestand* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="856a6-325">De bestandshash voor waarschuwingen die zijn gekoppeld aan een bestand of proces.</span><span class="sxs-lookup"><span data-stu-id="856a6-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="856a6-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="856a6-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="856a6-327">bestandsnaam</span><span class="sxs-lookup"><span data-stu-id="856a6-327">fileName</span></span> | <span data-ttu-id="856a6-328">Beschikbaar als entityType *Bestand* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="856a6-329">De bestandsnaam voor waarschuwingen die zijn gekoppeld aan een bestand of proces</span><span class="sxs-lookup"><span data-stu-id="856a6-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="856a6-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="856a6-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="856a6-331">filePath</span><span class="sxs-lookup"><span data-stu-id="856a6-331">filePath</span></span> | <span data-ttu-id="856a6-332">Beschikbaar als entityType *Bestand* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="856a6-333">Het bestandspad voor waarschuwingen die zijn gekoppeld aan een bestand of proces</span><span class="sxs-lookup"><span data-stu-id="856a6-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="856a6-334">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="856a6-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="856a6-335">processId</span><span class="sxs-lookup"><span data-stu-id="856a6-335">processId</span></span> | <span data-ttu-id="856a6-336">Beschikbaar als entityType *Process* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="856a6-337">24348</span><span class="sxs-lookup"><span data-stu-id="856a6-337">24348</span></span>
<span data-ttu-id="856a6-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="856a6-338">processCommandLine</span></span> | <span data-ttu-id="856a6-339">Beschikbaar als entityType *Process* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="856a6-340">"Uw bestand is klaar om de \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="856a6-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="856a6-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="856a6-341">processCreationTime</span></span> | <span data-ttu-id="856a6-342">Beschikbaar als entityType *Process* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="856a6-343">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="856a6-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="856a6-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="856a6-344">parentProcessId</span></span> | <span data-ttu-id="856a6-345">Beschikbaar als entityType *Process* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="856a6-346">16840</span><span class="sxs-lookup"><span data-stu-id="856a6-346">16840</span></span>
<span data-ttu-id="856a6-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="856a6-347">parentProcessCreationTime</span></span> | <span data-ttu-id="856a6-348">Beschikbaar als entityType *Process* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="856a6-349">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="856a6-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="856a6-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="856a6-350">ipAddress</span></span> | <span data-ttu-id="856a6-351">Beschikbaar als entityType *Ip* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="856a6-352">IP-adres voor waarschuwingen die zijn gekoppeld aan netwerkgebeurtenissen, zoals *Communicatie naar een schadelijke netwerkbestemming.*</span><span class="sxs-lookup"><span data-stu-id="856a6-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="856a6-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="856a6-353">62.216.203.204</span></span>
<span data-ttu-id="856a6-354">url</span><span class="sxs-lookup"><span data-stu-id="856a6-354">url</span></span> | <span data-ttu-id="856a6-355">Beschikbaar als entityType *Url* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="856a6-356">Url voor waarschuwingen die zijn gekoppeld aan netwerkgebeurtenissen, zoals Communicatie *naar een schadelijke netwerkbestemming.*</span><span class="sxs-lookup"><span data-stu-id="856a6-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="856a6-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="856a6-357">down.esales360.cn</span></span>
<span data-ttu-id="856a6-358">accountName</span><span class="sxs-lookup"><span data-stu-id="856a6-358">accountName</span></span> | <span data-ttu-id="856a6-359">Beschikbaar als entityType *gebruiker* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="856a6-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="856a6-360">testUser2</span></span>
<span data-ttu-id="856a6-361">domainName</span><span class="sxs-lookup"><span data-stu-id="856a6-361">domainName</span></span> | <span data-ttu-id="856a6-362">Beschikbaar als entityType *gebruiker* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="856a6-363">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="856a6-363">europe.corp.contoso</span></span>
<span data-ttu-id="856a6-364">userSid</span><span class="sxs-lookup"><span data-stu-id="856a6-364">userSid</span></span> | <span data-ttu-id="856a6-365">Beschikbaar als entityType *gebruiker* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="856a6-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="856a6-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="856a6-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="856a6-367">aadUserId</span></span> | <span data-ttu-id="856a6-368">Beschikbaar als entityType *gebruiker* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="856a6-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="856a6-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="856a6-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="856a6-370">userPrincipalName</span></span> | <span data-ttu-id="856a6-371">Beschikbaar als entityType *User* / *MailBox* / *MailMessage is.*</span><span class="sxs-lookup"><span data-stu-id="856a6-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="856a6-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="856a6-372">testUser2@contoso.com</span></span>
<span data-ttu-id="856a6-373">postvakDisplayName</span><span class="sxs-lookup"><span data-stu-id="856a6-373">mailboxDisplayName</span></span> | <span data-ttu-id="856a6-374">Beschikbaar als entityType *MailBox* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="856a6-375">gebruiker testen2</span><span class="sxs-lookup"><span data-stu-id="856a6-375">test User2</span></span>
<span data-ttu-id="856a6-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="856a6-376">mailboxAddress</span></span> | <span data-ttu-id="856a6-377">Beschikbaar als entityType *User* / *MailBox* / *MailMessage is.*</span><span class="sxs-lookup"><span data-stu-id="856a6-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="856a6-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="856a6-378">testUser2@contoso.com</span></span>
<span data-ttu-id="856a6-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="856a6-379">clusterBy</span></span> | <span data-ttu-id="856a6-380">Beschikbaar als entityType  *MailCluster* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="856a6-381">Onderwerp; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="856a6-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="856a6-382">afzender</span><span class="sxs-lookup"><span data-stu-id="856a6-382">sender</span></span> | <span data-ttu-id="856a6-383">Beschikbaar als entityType *User* / *MailBox* / *MailMessage is.*</span><span class="sxs-lookup"><span data-stu-id="856a6-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="856a6-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="856a6-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="856a6-385">geadresseerde</span><span class="sxs-lookup"><span data-stu-id="856a6-385">recipient</span></span> | <span data-ttu-id="856a6-386">Beschikbaar als entityType *MailMessage is.*</span><span class="sxs-lookup"><span data-stu-id="856a6-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="856a6-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="856a6-387">testUser2@contoso.com</span></span>
<span data-ttu-id="856a6-388">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="856a6-388">subject</span></span> | <span data-ttu-id="856a6-389">Beschikbaar als entityType *MailMessage is.*</span><span class="sxs-lookup"><span data-stu-id="856a6-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="856a6-390">\[EXTERNE \] aandacht</span><span class="sxs-lookup"><span data-stu-id="856a6-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="856a6-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="856a6-391">deliveryAction</span></span> | <span data-ttu-id="856a6-392">Beschikbaar als entityType *MailMessage is.*</span><span class="sxs-lookup"><span data-stu-id="856a6-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="856a6-393">Geleverd</span><span class="sxs-lookup"><span data-stu-id="856a6-393">Delivered</span></span>
<span data-ttu-id="856a6-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="856a6-394">securityGroupId</span></span> | <span data-ttu-id="856a6-395">Beschikbaar als entityType  *SecurityGroup* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="856a6-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="856a6-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="856a6-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="856a6-397">securityGroupName</span></span> | <span data-ttu-id="856a6-398">Beschikbaar als entityType  *SecurityGroup* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="856a6-399">Netwerkconfiguratieoperatoren</span><span class="sxs-lookup"><span data-stu-id="856a6-399">Network Configuration Operators</span></span>
<span data-ttu-id="856a6-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="856a6-400">registryHive</span></span> | <span data-ttu-id="856a6-401">Beschikbaar als entityType  *register* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="856a6-402">LOKALE \_ \_ HKEY-COMPUTER</span><span class="sxs-lookup"><span data-stu-id="856a6-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="856a6-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="856a6-403">registryKey</span></span> | <span data-ttu-id="856a6-404">Beschikbaar als entityType  *register* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="856a6-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="856a6-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="856a6-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="856a6-406">registryValueType</span></span> | <span data-ttu-id="856a6-407">Beschikbaar als entityType  *register* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="856a6-408">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="856a6-408">String</span></span>
<span data-ttu-id="856a6-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="856a6-409">registryValue</span></span> | <span data-ttu-id="856a6-410">Beschikbaar als entityType  *register* is.</span><span class="sxs-lookup"><span data-stu-id="856a6-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="856a6-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="856a6-411">31-00-00-00</span></span>
<span data-ttu-id="856a6-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="856a6-412">deviceId</span></span> | <span data-ttu-id="856a6-413">De id, indien van de persoon, van het apparaat dat aan de entiteit is gerelateerd.</span><span class="sxs-lookup"><span data-stu-id="856a6-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="856a6-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="856a6-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="856a6-415">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="856a6-415">Example</span></span>

<span data-ttu-id="856a6-416">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="856a6-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="856a6-417">**Antwoord**</span><span class="sxs-lookup"><span data-stu-id="856a6-417">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="856a6-418">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="856a6-418">Related articles</span></span>

- [<span data-ttu-id="856a6-419">De Microsoft 365 Defender-API's openen</span><span class="sxs-lookup"><span data-stu-id="856a6-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="856a6-420">Meer informatie over API-limieten en -licenties</span><span class="sxs-lookup"><span data-stu-id="856a6-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="856a6-421">Foutcodes begrijpen</span><span class="sxs-lookup"><span data-stu-id="856a6-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="856a6-422">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="856a6-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="856a6-423">API's voor incidenten</span><span class="sxs-lookup"><span data-stu-id="856a6-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="856a6-424">Api voor incidenten bijwerken</span><span class="sxs-lookup"><span data-stu-id="856a6-424">Update incident API</span></span>](api-update-incidents.md)