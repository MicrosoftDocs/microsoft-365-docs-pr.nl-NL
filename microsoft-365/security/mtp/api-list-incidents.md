---
title: API voor lijst incidenten in Microsoft 365 Defender
description: Meer informatie over het opnemen van de API voor incidenten in Microsoft 365 Defender
keywords: lijst, incident, incidenten, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 13508d3ad9d61797517ccb55a27152883947843a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719426"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="afdf0-104">API voor lijst incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="afdf0-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="afdf0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="afdf0-105">**Applies to:**</span></span>

- <span data-ttu-id="afdf0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="afdf0-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="afdf0-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="afdf0-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="afdf0-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="afdf0-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="afdf0-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="afdf0-109">API description</span></span>

<span data-ttu-id="afdf0-110">Met de API List incidents kunt u sorteren op incidenten om een weloverwogen Cyber Security-antwoord te maken.</span><span class="sxs-lookup"><span data-stu-id="afdf0-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="afdf0-111">Met deze functie wordt een verzameling incidenten getoond die zijn gemarkeerd in uw netwerk, binnen het opgegeven tijdsbereik in het bewaarbeleid voor de omgeving.</span><span class="sxs-lookup"><span data-stu-id="afdf0-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="afdf0-112">De meest recente incidenten worden bovenaan de lijst weergegeven.</span><span class="sxs-lookup"><span data-stu-id="afdf0-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="afdf0-113">Elk incident bevat een matrix met gerelateerde waarschuwingen en de gerelateerde entiteiten.</span><span class="sxs-lookup"><span data-stu-id="afdf0-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="afdf0-114">De API biedt ondersteuning voor de volgende **OData** -operatoren:</span><span class="sxs-lookup"><span data-stu-id="afdf0-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="afdf0-115">`$filter` in het `lastUpdateTime` `createdTime` `status` `assignedTo` dialoogvenster Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="afdf0-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="afdf0-116">`$top`met een maximumwaarde van **100**</span><span class="sxs-lookup"><span data-stu-id="afdf0-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="afdf0-117">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="afdf0-117">Limitations</span></span>

1. <span data-ttu-id="afdf0-118">Het maximale paginaformaat is **100 incidenten**.</span><span class="sxs-lookup"><span data-stu-id="afdf0-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="afdf0-119">Het maximale aantal aanvragen is **50 oproepen per minuut** en **1500-oproepen per uur**.</span><span class="sxs-lookup"><span data-stu-id="afdf0-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="afdf0-120">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="afdf0-120">Permissions</span></span>

<span data-ttu-id="afdf0-121">U moet een van de volgende machtigingen hebben om deze API te kunnen bellen.</span><span class="sxs-lookup"><span data-stu-id="afdf0-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="afdf0-122">Zie voor meer informatie, waaronder de manier waarop u machtigingen kiest, [toegang tot Microsoft 365 Defender-api's](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="afdf0-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="afdf0-123">Type machtiging</span><span class="sxs-lookup"><span data-stu-id="afdf0-123">Permission type</span></span> | <span data-ttu-id="afdf0-124">Machtigingsset</span><span class="sxs-lookup"><span data-stu-id="afdf0-124">Permission</span></span> | <span data-ttu-id="afdf0-125">Weergavenaam van de machtiging</span><span class="sxs-lookup"><span data-stu-id="afdf0-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="afdf0-126">Toepassing</span><span class="sxs-lookup"><span data-stu-id="afdf0-126">Application</span></span> | <span data-ttu-id="afdf0-127">Incident. Read. all</span><span class="sxs-lookup"><span data-stu-id="afdf0-127">Incident.Read.All</span></span> | <span data-ttu-id="afdf0-128">Alle incidenten lezen</span><span class="sxs-lookup"><span data-stu-id="afdf0-128">Read all incidents</span></span>
<span data-ttu-id="afdf0-129">Toepassing</span><span class="sxs-lookup"><span data-stu-id="afdf0-129">Application</span></span> | <span data-ttu-id="afdf0-130">Incident. ReadWrite. all</span><span class="sxs-lookup"><span data-stu-id="afdf0-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="afdf0-131">Alle incidenten lezen en schrijven</span><span class="sxs-lookup"><span data-stu-id="afdf0-131">Read and write all incidents</span></span>
<span data-ttu-id="afdf0-132">Gedelegeerd (werk-of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="afdf0-132">Delegated (work or school account)</span></span> | <span data-ttu-id="afdf0-133">Incident. Read</span><span class="sxs-lookup"><span data-stu-id="afdf0-133">Incident.Read</span></span> | <span data-ttu-id="afdf0-134">Lees incidenten</span><span class="sxs-lookup"><span data-stu-id="afdf0-134">Read incidents</span></span>
<span data-ttu-id="afdf0-135">Gedelegeerd (werk-of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="afdf0-135">Delegated (work or school account)</span></span> | <span data-ttu-id="afdf0-136">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="afdf0-136">Incident.ReadWrite</span></span> | <span data-ttu-id="afdf0-137">Lees-en schrijf incidenten</span><span class="sxs-lookup"><span data-stu-id="afdf0-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="afdf0-138">Bij het verkrijgen van een token met behulp van gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="afdf0-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="afdf0-139">De gebruiker moet de machtiging voor weergeven voor incidenten in de portal hebben.</span><span class="sxs-lookup"><span data-stu-id="afdf0-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="afdf0-140">Het antwoord bevat alleen incidenten waaraan de gebruiker is blootgesteld.</span><span class="sxs-lookup"><span data-stu-id="afdf0-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="afdf0-141">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="afdf0-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="afdf0-142">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="afdf0-142">Request headers</span></span>

<span data-ttu-id="afdf0-143">Naam</span><span class="sxs-lookup"><span data-stu-id="afdf0-143">Name</span></span> | <span data-ttu-id="afdf0-144">Type</span><span class="sxs-lookup"><span data-stu-id="afdf0-144">Type</span></span> | <span data-ttu-id="afdf0-145">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="afdf0-145">Description</span></span>
-|-|-
<span data-ttu-id="afdf0-146">Bevoegdheid</span><span class="sxs-lookup"><span data-stu-id="afdf0-146">Authorization</span></span> | <span data-ttu-id="afdf0-147">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="afdf0-147">String</span></span> | <span data-ttu-id="afdf0-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="afdf0-148">Bearer {token}.</span></span> <span data-ttu-id="afdf0-149">**Vereist**</span><span class="sxs-lookup"><span data-stu-id="afdf0-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="afdf0-150">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="afdf0-150">Request body</span></span>

<span data-ttu-id="afdf0-151">Zonder.</span><span class="sxs-lookup"><span data-stu-id="afdf0-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="afdf0-152">Na</span><span class="sxs-lookup"><span data-stu-id="afdf0-152">Response</span></span>

<span data-ttu-id="afdf0-153">Als dit slaagt, retourneert deze methode `200 OK` en een lijst met [incidenten](api-incident.md) in de tekst van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="afdf0-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="afdf0-154">Schema toewijzingen</span><span class="sxs-lookup"><span data-stu-id="afdf0-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="afdf0-155">Metagegevens van incident</span><span class="sxs-lookup"><span data-stu-id="afdf0-155">Incident metadata</span></span>

<span data-ttu-id="afdf0-156">Veld naam</span><span class="sxs-lookup"><span data-stu-id="afdf0-156">Field name</span></span> | <span data-ttu-id="afdf0-157">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="afdf0-157">Description</span></span> | <span data-ttu-id="afdf0-158">Voorbeeldwaarde</span><span class="sxs-lookup"><span data-stu-id="afdf0-158">Example value</span></span>
-|-|-
<span data-ttu-id="afdf0-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="afdf0-159">incidentId</span></span> | <span data-ttu-id="afdf0-160">Unieke id die het incident voorstelt</span><span class="sxs-lookup"><span data-stu-id="afdf0-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="afdf0-161">924565</span><span class="sxs-lookup"><span data-stu-id="afdf0-161">924565</span></span>
<span data-ttu-id="afdf0-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="afdf0-162">redirectIncidentId</span></span> | <span data-ttu-id="afdf0-163">Wordt alleen ingevuld wanneer een incident wordt gegroepeerd met een ander incident, als onderdeel van de logica voor het verwerken van incidenten.</span><span class="sxs-lookup"><span data-stu-id="afdf0-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="afdf0-164">924569</span><span class="sxs-lookup"><span data-stu-id="afdf0-164">924569</span></span>
<span data-ttu-id="afdf0-165">voorval</span><span class="sxs-lookup"><span data-stu-id="afdf0-165">incidentName</span></span> | <span data-ttu-id="afdf0-166">De tekenreekswaarde voor elk incident.</span><span class="sxs-lookup"><span data-stu-id="afdf0-166">String value available for every incident.</span></span> | <span data-ttu-id="afdf0-167">Ransomware-activiteit</span><span class="sxs-lookup"><span data-stu-id="afdf0-167">Ransomware activity</span></span>
<span data-ttu-id="afdf0-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="afdf0-168">createdTime</span></span> | <span data-ttu-id="afdf0-169">Tijdstip waarop het incident voor het eerst is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="afdf0-169">Time when incident was first created.</span></span> | <span data-ttu-id="afdf0-170">2020-09-06T14:46:57.0733333 Z</span><span class="sxs-lookup"><span data-stu-id="afdf0-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="afdf0-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="afdf0-171">lastUpdateTime</span></span> | <span data-ttu-id="afdf0-172">De tijd waarop het incident voor het laatst is bijgewerkt op de backend.</span><span class="sxs-lookup"><span data-stu-id="afdf0-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="afdf0-173">Dit veld kan worden gebruikt wanneer u de parameter Request instelt voor het bereik van de tijd waarop incidenten worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="afdf0-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="afdf0-174">2020-09-06T14:46:57.29 Z</span><span class="sxs-lookup"><span data-stu-id="afdf0-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="afdf0-175">ToegewezenAan</span><span class="sxs-lookup"><span data-stu-id="afdf0-175">assignedTo</span></span> | <span data-ttu-id="afdf0-176">Eigenaar van het incident, of *Null* als er geen eigenaar wordt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="afdf0-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="afdf0-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="afdf0-177">secop2@contoso.com</span></span>
<span data-ttu-id="afdf0-178">Contactpersoonclassificatie</span><span class="sxs-lookup"><span data-stu-id="afdf0-178">classification</span></span> | <span data-ttu-id="afdf0-179">De specificatie van het incident.</span><span class="sxs-lookup"><span data-stu-id="afdf0-179">The specification for the incident.</span></span> <span data-ttu-id="afdf0-180">De eigenschapwaarden zijn: *onbekend*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="afdf0-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="afdf0-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="afdf0-181">Unknown</span></span>
<span data-ttu-id="afdf0-182">relevant</span><span class="sxs-lookup"><span data-stu-id="afdf0-182">determination</span></span> | <span data-ttu-id="afdf0-183">Hiermee wordt het bepalen van het incident aangegeven.</span><span class="sxs-lookup"><span data-stu-id="afdf0-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="afdf0-184">De eigenschapwaarden zijn: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Overig*</span><span class="sxs-lookup"><span data-stu-id="afdf0-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="afdf0-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="afdf0-185">NotAvailable</span></span>
<span data-ttu-id="afdf0-186">status</span><span class="sxs-lookup"><span data-stu-id="afdf0-186">status</span></span> | <span data-ttu-id="afdf0-187">Incidenten categoriseren (als *actief* of *opgelost*).</span><span class="sxs-lookup"><span data-stu-id="afdf0-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="afdf0-188">Met deze functie kunt u uw antwoord op incidenten organiseren en beheren.</span><span class="sxs-lookup"><span data-stu-id="afdf0-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="afdf0-189">Actief</span><span class="sxs-lookup"><span data-stu-id="afdf0-189">Active</span></span>
<span data-ttu-id="afdf0-190">Ernst</span><span class="sxs-lookup"><span data-stu-id="afdf0-190">severity</span></span> | <span data-ttu-id="afdf0-191">Geeft de mogelijke gevolgen voor activa aan.</span><span class="sxs-lookup"><span data-stu-id="afdf0-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="afdf0-192">Hoe hoger de ernst, hoe groter de impact.</span><span class="sxs-lookup"><span data-stu-id="afdf0-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="afdf0-193">Meestal hebt u de meest directe aandacht nodig voor hogere prioriteits items.</span><span class="sxs-lookup"><span data-stu-id="afdf0-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="afdf0-194">Een van de volgende waarden: *informatie*, *laag*, \* medium en *hoog*.</span><span class="sxs-lookup"><span data-stu-id="afdf0-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="afdf0-195">Medium</span><span class="sxs-lookup"><span data-stu-id="afdf0-195">Medium</span></span>
<span data-ttu-id="afdf0-196">Tags</span><span class="sxs-lookup"><span data-stu-id="afdf0-196">tags</span></span> | <span data-ttu-id="afdf0-197">Matrix van aangepaste labels die zijn gekoppeld aan een incident, bijvoorbeeld om een groep incidenten met een gemeenschappelijk kenmerk te markeren.</span><span class="sxs-lookup"><span data-stu-id="afdf0-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="afdf0-198">kennisgeving</span><span class="sxs-lookup"><span data-stu-id="afdf0-198">alerts</span></span> | <span data-ttu-id="afdf0-199">Matrix met alle waarschuwingen die betrekking hebben op het incident, plus andere informatie, zoals Ernst, entiteiten die betrokken zijn bij de waarschuwing en de bron van de waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="afdf0-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="afdf0-200">\[\] (Zie Details over waarschuwingsvelden hieronder)</span><span class="sxs-lookup"><span data-stu-id="afdf0-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="afdf0-201">Metagegevens van waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="afdf0-201">Alerts metadata</span></span>

<span data-ttu-id="afdf0-202">Veld naam</span><span class="sxs-lookup"><span data-stu-id="afdf0-202">Field name</span></span> | <span data-ttu-id="afdf0-203">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="afdf0-203">Description</span></span> | <span data-ttu-id="afdf0-204">Voorbeeldwaarde</span><span class="sxs-lookup"><span data-stu-id="afdf0-204">Example value</span></span>
-|-|-
<span data-ttu-id="afdf0-205">alertId</span><span class="sxs-lookup"><span data-stu-id="afdf0-205">alertId</span></span> | <span data-ttu-id="afdf0-206">Unieke id die de waarschuwing voorstelt</span><span class="sxs-lookup"><span data-stu-id="afdf0-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="afdf0-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="afdf0-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="afdf0-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="afdf0-208">incidentId</span></span> | <span data-ttu-id="afdf0-209">Unieke id waarmee het incident wordt aangegeven waaraan deze waarschuwing is gekoppeld</span><span class="sxs-lookup"><span data-stu-id="afdf0-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="afdf0-210">924565</span><span class="sxs-lookup"><span data-stu-id="afdf0-210">924565</span></span>
<span data-ttu-id="afdf0-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="afdf0-211">serviceSource</span></span> | <span data-ttu-id="afdf0-212">De service waaruit de melding afkomstig is, zoals Microsoft Defender for Endpoint, Microsoft Cloud app Security, Microsoft Defender for Identity of Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="afdf0-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="afdf0-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="afdf0-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="afdf0-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="afdf0-214">creationTime</span></span> | <span data-ttu-id="afdf0-215">Tijdstip waarop de waarschuwing voor het eerst is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="afdf0-215">Time when alert was first created.</span></span> | <span data-ttu-id="afdf0-216">2020-09-06T14:46:55.7182276 Z</span><span class="sxs-lookup"><span data-stu-id="afdf0-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="afdf0-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="afdf0-217">lastUpdatedTime</span></span> | <span data-ttu-id="afdf0-218">Tijdstip waarop de waarschuwing voor het laatst is bijgewerkt op de backend.</span><span class="sxs-lookup"><span data-stu-id="afdf0-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="afdf0-219">2020-09-06T14:46:57.2433333 Z</span><span class="sxs-lookup"><span data-stu-id="afdf0-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="afdf0-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="afdf0-220">resolvedTime</span></span> | <span data-ttu-id="afdf0-221">Tijdstip waarop de waarschuwing is opgelost.</span><span class="sxs-lookup"><span data-stu-id="afdf0-221">Time when alert was resolved.</span></span> | <span data-ttu-id="afdf0-222">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="afdf0-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="afdf0-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="afdf0-223">firstActivity</span></span> | <span data-ttu-id="afdf0-224">Tijd waarop de waarschuwing voor het eerst werd gerapporteerd dat de activiteit op de backend werd bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="afdf0-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="afdf0-225">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="afdf0-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="afdf0-226">begin</span><span class="sxs-lookup"><span data-stu-id="afdf0-226">title</span></span> | <span data-ttu-id="afdf0-227">Kort herkenbare identificatiewaarde voor elke waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="afdf0-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="afdf0-228">Ransomware-activiteit</span><span class="sxs-lookup"><span data-stu-id="afdf0-228">Ransomware activity</span></span>
<span data-ttu-id="afdf0-229">beschrijving</span><span class="sxs-lookup"><span data-stu-id="afdf0-229">description</span></span> | <span data-ttu-id="afdf0-230">De tekenreekswaarde waarmee wordt gewaarschuwd.</span><span class="sxs-lookup"><span data-stu-id="afdf0-230">String value describing each alert.</span></span> | <span data-ttu-id="afdf0-231">De testUser2@contoso.com-bestanden () die zijn 99 bewerkt met een niet-gemeenschappelijke uitbreiding *herunterladen*</span><span class="sxs-lookup"><span data-stu-id="afdf0-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="afdf0-232">Dit is een ongebruikelijk aantal bestandsbewerkingen en is een aanwijzing voor een potentiële aanval van Ransomware.</span><span class="sxs-lookup"><span data-stu-id="afdf0-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="afdf0-233">Categorie</span><span class="sxs-lookup"><span data-stu-id="afdf0-233">category</span></span> | <span data-ttu-id="afdf0-234">Visuele en numerieke weergave van de hoeveelheid aanval op de Kill-ketting.</span><span class="sxs-lookup"><span data-stu-id="afdf0-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="afdf0-235">Uitgelijnd op de [Mitre ATT&a™ Framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="afdf0-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="afdf0-236">Gevolg</span><span class="sxs-lookup"><span data-stu-id="afdf0-236">Impact</span></span>
<span data-ttu-id="afdf0-237">status</span><span class="sxs-lookup"><span data-stu-id="afdf0-237">status</span></span> | <span data-ttu-id="afdf0-238">Waarschuwingen categoriseren (als *Nieuw*, *actief* of *opgelost*)</span><span class="sxs-lookup"><span data-stu-id="afdf0-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="afdf0-239">Met deze functie kunt u uw antwoord op waarschuwingen organiseren en beheren.</span><span class="sxs-lookup"><span data-stu-id="afdf0-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="afdf0-240">Nieuw</span><span class="sxs-lookup"><span data-stu-id="afdf0-240">New</span></span>
<span data-ttu-id="afdf0-241">Ernst</span><span class="sxs-lookup"><span data-stu-id="afdf0-241">severity</span></span> | <span data-ttu-id="afdf0-242">Geeft de mogelijke gevolgen voor activa aan.</span><span class="sxs-lookup"><span data-stu-id="afdf0-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="afdf0-243">Hoe hoger de ernst, hoe groter de impact.</span><span class="sxs-lookup"><span data-stu-id="afdf0-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="afdf0-244">Meestal hebt u de meest directe aandacht nodig voor hogere prioriteits items.</span><span class="sxs-lookup"><span data-stu-id="afdf0-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="afdf0-245">Een van de volgende waarden: *informatie*, *laag*, \* medium en *hoog*.</span><span class="sxs-lookup"><span data-stu-id="afdf0-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="afdf0-246">Medium</span><span class="sxs-lookup"><span data-stu-id="afdf0-246">Medium</span></span>
<span data-ttu-id="afdf0-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="afdf0-247">investigationId</span></span> | <span data-ttu-id="afdf0-248">De geautomatiseerde onderzoek-ID die door deze melding wordt geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="afdf0-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="afdf0-249">1234</span><span class="sxs-lookup"><span data-stu-id="afdf0-249">1234</span></span>
<span data-ttu-id="afdf0-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="afdf0-250">investigationState</span></span> | <span data-ttu-id="afdf0-251">Informatie over de huidige status van het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="afdf0-251">Information on the investigation's current status.</span></span> <span data-ttu-id="afdf0-252">Een van de volgende waarden: *onbekend*, *beëindigd*, *SuccessfullyRemediated*, *aardige*, *mislukt*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, SuppressedAlert *.*</span><span class="sxs-lookup"><span data-stu-id="afdf0-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="afdf0-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="afdf0-253">UnsupportedAlertType</span></span>
<span data-ttu-id="afdf0-254">Contactpersoonclassificatie</span><span class="sxs-lookup"><span data-stu-id="afdf0-254">classification</span></span> | <span data-ttu-id="afdf0-255">De specificatie van het incident.</span><span class="sxs-lookup"><span data-stu-id="afdf0-255">The specification for the incident.</span></span> <span data-ttu-id="afdf0-256">De eigenschapwaarden zijn: *onbekend*, *FalsePositive*, *TruePositive* of *Null*</span><span class="sxs-lookup"><span data-stu-id="afdf0-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="afdf0-257">Unknown</span><span class="sxs-lookup"><span data-stu-id="afdf0-257">Unknown</span></span>
<span data-ttu-id="afdf0-258">relevant</span><span class="sxs-lookup"><span data-stu-id="afdf0-258">determination</span></span> | <span data-ttu-id="afdf0-259">Hiermee wordt het bepalen van het incident aangegeven.</span><span class="sxs-lookup"><span data-stu-id="afdf0-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="afdf0-260">De eigenschapwaarden zijn: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other* of  *Null*</span><span class="sxs-lookup"><span data-stu-id="afdf0-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="afdf0-261">Apt</span><span class="sxs-lookup"><span data-stu-id="afdf0-261">Apt</span></span>
<span data-ttu-id="afdf0-262">ToegewezenAan</span><span class="sxs-lookup"><span data-stu-id="afdf0-262">assignedTo</span></span> | <span data-ttu-id="afdf0-263">Eigenaar van het incident, of *Null* als er geen eigenaar wordt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="afdf0-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="afdf0-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="afdf0-264">secop2@contoso.com</span></span>
<span data-ttu-id="afdf0-265">actor</span><span class="sxs-lookup"><span data-stu-id="afdf0-265">actorName</span></span> | <span data-ttu-id="afdf0-266">De groep activiteit, indien van toepassing, de koppeling met deze waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="afdf0-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="afdf0-267">EQUIVALENT</span><span class="sxs-lookup"><span data-stu-id="afdf0-267">BORON</span></span>
<span data-ttu-id="afdf0-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="afdf0-268">threatFamilyName</span></span> | <span data-ttu-id="afdf0-269">Bedreigings familie van deze melding.</span><span class="sxs-lookup"><span data-stu-id="afdf0-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="afdf0-270">waarden</span><span class="sxs-lookup"><span data-stu-id="afdf0-270">null</span></span>
<span data-ttu-id="afdf0-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="afdf0-271">mitreTechniques</span></span> | <span data-ttu-id="afdf0-272">De aantastings methoden, zoals afgestemd op de [Mitre ATT&a](https://attack.mitre.org/)™ Framework.</span><span class="sxs-lookup"><span data-stu-id="afdf0-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="afdf0-273">apparaten</span><span class="sxs-lookup"><span data-stu-id="afdf0-273">devices</span></span> | <span data-ttu-id="afdf0-274">Alle apparaten waarop meldingen met betrekking tot het incident zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="afdf0-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="afdf0-275">\[\] (Zie Details van de onderstaande entiteits velden)</span><span class="sxs-lookup"><span data-stu-id="afdf0-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="afdf0-276">Indeling van apparaat</span><span class="sxs-lookup"><span data-stu-id="afdf0-276">Device format</span></span>

<span data-ttu-id="afdf0-277">Veld naam</span><span class="sxs-lookup"><span data-stu-id="afdf0-277">Field name</span></span> | <span data-ttu-id="afdf0-278">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="afdf0-278">Description</span></span> | <span data-ttu-id="afdf0-279">Voorbeeldwaarde</span><span class="sxs-lookup"><span data-stu-id="afdf0-279">Example value</span></span>
-|-|-
<span data-ttu-id="afdf0-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="afdf0-280">DeviceId</span></span> | <span data-ttu-id="afdf0-281">De apparaat-ID zoals aangegeven in Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="afdf0-281">The device ID as designated in Microsoft Defender ATP.</span></span> | <span data-ttu-id="afdf0-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="afdf0-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="afdf0-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="afdf0-283">aadDeviceId</span></span> |  <span data-ttu-id="afdf0-284">De apparaat-ID zoals aangegeven in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="afdf0-284">The device ID as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="afdf0-285">Alleen beschikbaar voor apparaten die lid zijn van een domein.</span><span class="sxs-lookup"><span data-stu-id="afdf0-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="afdf0-286">waarden</span><span class="sxs-lookup"><span data-stu-id="afdf0-286">null</span></span>
<span data-ttu-id="afdf0-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="afdf0-287">deviceDnsName</span></span> | <span data-ttu-id="afdf0-288">De FQDN-naam (Fully Qualified Domain Name) voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="afdf0-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="afdf0-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="afdf0-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="afdf0-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="afdf0-290">osPlatform</span></span> | <span data-ttu-id="afdf0-291">Het OS-platform waarop het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="afdf0-291">The OS platform the device is running.</span></span>| <span data-ttu-id="afdf0-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="afdf0-292">WindowsServer2016</span></span>
<span data-ttu-id="afdf0-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="afdf0-293">osBuild</span></span> | <span data-ttu-id="afdf0-294">De build-versie van het besturingssysteem dat het apparaat uitvoert.</span><span class="sxs-lookup"><span data-stu-id="afdf0-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="afdf0-295">14393</span><span class="sxs-lookup"><span data-stu-id="afdf0-295">14393</span></span>
<span data-ttu-id="afdf0-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="afdf0-296">rbacGroupName</span></span> | <span data-ttu-id="afdf0-297">De groep [toegangsbeheer op basis van rollen](https://docs.microsoft.com/azure/role-based-access-control/overview) die is gekoppeld aan het apparaat.</span><span class="sxs-lookup"><span data-stu-id="afdf0-297">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="afdf0-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="afdf0-298">WDATP-Ring0</span></span>
<span data-ttu-id="afdf0-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="afdf0-299">firstSeen</span></span> | <span data-ttu-id="afdf0-300">Tijdstip waarop apparaat voor het eerst werd gezien.</span><span class="sxs-lookup"><span data-stu-id="afdf0-300">Time when device was first seen.</span></span> | <span data-ttu-id="afdf0-301">2020-02-06T14:16:01.9330135 Z</span><span class="sxs-lookup"><span data-stu-id="afdf0-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="afdf0-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="afdf0-302">healthStatus</span></span> | <span data-ttu-id="afdf0-303">De status van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="afdf0-303">The health state of the device.</span></span> | <span data-ttu-id="afdf0-304">Actief</span><span class="sxs-lookup"><span data-stu-id="afdf0-304">Active</span></span>
<span data-ttu-id="afdf0-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="afdf0-305">riskScore</span></span> | <span data-ttu-id="afdf0-306">De risicoscore voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="afdf0-306">The risk score for the  device.</span></span> | <span data-ttu-id="afdf0-307">Hoog</span><span class="sxs-lookup"><span data-stu-id="afdf0-307">High</span></span>
<span data-ttu-id="afdf0-308">onderzoeksinstellingen</span><span class="sxs-lookup"><span data-stu-id="afdf0-308">entities</span></span> | <span data-ttu-id="afdf0-309">Alle entiteiten die zijn geïdentificeerd om deel te nemen aan, of gerelateerd zijn aan een bepaalde melding.</span><span class="sxs-lookup"><span data-stu-id="afdf0-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="afdf0-310">\[\] (Zie Details van de onderstaande entiteits velden)</span><span class="sxs-lookup"><span data-stu-id="afdf0-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="afdf0-311">Entiteits indeling</span><span class="sxs-lookup"><span data-stu-id="afdf0-311">Entity Format</span></span>

<span data-ttu-id="afdf0-312">Veld naam</span><span class="sxs-lookup"><span data-stu-id="afdf0-312">Field name</span></span> | <span data-ttu-id="afdf0-313">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="afdf0-313">Description</span></span> | <span data-ttu-id="afdf0-314">Voorbeeldwaarde</span><span class="sxs-lookup"><span data-stu-id="afdf0-314">Example value</span></span>
-|-|-
<span data-ttu-id="afdf0-315">entityType</span><span class="sxs-lookup"><span data-stu-id="afdf0-315">entityType</span></span> | <span data-ttu-id="afdf0-316">Entiteiten die zijn geïdentificeerd om deel te nemen aan een bepaalde melding, of betrekking hebben op een bepaalde melding.</span><span class="sxs-lookup"><span data-stu-id="afdf0-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="afdf0-317">De eigenschappen waarden zijn: *gebruiker*, *IP*, *URL*, *bestand*, *proces*, *Postvak*, *e-mailbericht, e-mail* *cluster*, *register*</span><span class="sxs-lookup"><span data-stu-id="afdf0-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="afdf0-318">Gebruiker</span><span class="sxs-lookup"><span data-stu-id="afdf0-318">User</span></span>
<span data-ttu-id="afdf0-319">SHA1</span><span class="sxs-lookup"><span data-stu-id="afdf0-319">sha1</span></span> | <span data-ttu-id="afdf0-320">Beschikbaar als entityType een *bestand* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="afdf0-321">De bestands-hash voor waarschuwingen die zijn gekoppeld aan een bestand of proces.</span><span class="sxs-lookup"><span data-stu-id="afdf0-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="afdf0-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="afdf0-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="afdf0-323">sha256</span><span class="sxs-lookup"><span data-stu-id="afdf0-323">sha256</span></span> | <span data-ttu-id="afdf0-324">Beschikbaar als entityType een *bestand* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="afdf0-325">De bestands-hash voor waarschuwingen die zijn gekoppeld aan een bestand of proces.</span><span class="sxs-lookup"><span data-stu-id="afdf0-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="afdf0-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="afdf0-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="afdf0-327">Namen</span><span class="sxs-lookup"><span data-stu-id="afdf0-327">fileName</span></span> | <span data-ttu-id="afdf0-328">Beschikbaar als entityType een *bestand* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="afdf0-329">De bestandsnaam van waarschuwingen die zijn gekoppeld aan een bestand of proces</span><span class="sxs-lookup"><span data-stu-id="afdf0-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="afdf0-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="afdf0-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="afdf0-331">Bestandspad</span><span class="sxs-lookup"><span data-stu-id="afdf0-331">filePath</span></span> | <span data-ttu-id="afdf0-332">Beschikbaar als entityType een *bestand* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="afdf0-333">Het bestandspad voor waarschuwingen die zijn gekoppeld aan een bestand of proces</span><span class="sxs-lookup"><span data-stu-id="afdf0-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="afdf0-334">C: \\ \ agent_work_temp \deploy\system\2020-09-06 12_14_54 \ out</span><span class="sxs-lookup"><span data-stu-id="afdf0-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="afdf0-335">Proces</span><span class="sxs-lookup"><span data-stu-id="afdf0-335">processId</span></span> | <span data-ttu-id="afdf0-336">Beschikbaar als entityType *proces* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="afdf0-337">24348</span><span class="sxs-lookup"><span data-stu-id="afdf0-337">24348</span></span>
<span data-ttu-id="afdf0-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="afdf0-338">processCommandLine</span></span> | <span data-ttu-id="afdf0-339">Beschikbaar als entityType *proces* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="afdf0-340">' Het bestand kan worden gedownload \_1911150169.exe '</span><span class="sxs-lookup"><span data-stu-id="afdf0-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="afdf0-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="afdf0-341">processCreationTime</span></span> | <span data-ttu-id="afdf0-342">Beschikbaar als entityType *proces* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="afdf0-343">2020-7-18T03:25:38.5269993 Z</span><span class="sxs-lookup"><span data-stu-id="afdf0-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="afdf0-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="afdf0-344">parentProcessId</span></span> | <span data-ttu-id="afdf0-345">Beschikbaar als entityType *proces* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="afdf0-346">16840</span><span class="sxs-lookup"><span data-stu-id="afdf0-346">16840</span></span>
<span data-ttu-id="afdf0-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="afdf0-347">parentProcessCreationTime</span></span> | <span data-ttu-id="afdf0-348">Beschikbaar als entityType *proces* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="afdf0-349">2020-7-18T02:12:32.8616797 Z</span><span class="sxs-lookup"><span data-stu-id="afdf0-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="afdf0-350">Adressen</span><span class="sxs-lookup"><span data-stu-id="afdf0-350">ipAddress</span></span> | <span data-ttu-id="afdf0-351">Beschikbaar als entityType een *IP-adres* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="afdf0-352">IP-adres voor waarschuwingen die zijn gekoppeld aan netwerkgebeurtenissen, zoals *communicatie met een kwaadaardige bestemming*.</span><span class="sxs-lookup"><span data-stu-id="afdf0-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="afdf0-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="afdf0-353">62.216.203.204</span></span>
<span data-ttu-id="afdf0-354">URL</span><span class="sxs-lookup"><span data-stu-id="afdf0-354">url</span></span> | <span data-ttu-id="afdf0-355">Beschikbaar als entityType de *URL* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="afdf0-356">URL voor meldingen die zijn gekoppeld aan netwerkgebeurtenissen, zoals *communicatie met een kwaadaardige bestemming*.</span><span class="sxs-lookup"><span data-stu-id="afdf0-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="afdf0-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="afdf0-357">down.esales360.cn</span></span>
<span data-ttu-id="afdf0-358">accountName</span><span class="sxs-lookup"><span data-stu-id="afdf0-358">accountName</span></span> | <span data-ttu-id="afdf0-359">Beschikbaar als entityType een *gebruiker* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="afdf0-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="afdf0-360">testUser2</span></span>
<span data-ttu-id="afdf0-361">Domeinnaam</span><span class="sxs-lookup"><span data-stu-id="afdf0-361">domainName</span></span> | <span data-ttu-id="afdf0-362">Beschikbaar als entityType een *gebruiker* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="afdf0-363">Europe. Corp. contoso</span><span class="sxs-lookup"><span data-stu-id="afdf0-363">europe.corp.contoso</span></span>
<span data-ttu-id="afdf0-364">userSid</span><span class="sxs-lookup"><span data-stu-id="afdf0-364">userSid</span></span> | <span data-ttu-id="afdf0-365">Beschikbaar als entityType een *gebruiker* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="afdf0-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="afdf0-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="afdf0-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="afdf0-367">aadUserId</span></span> | <span data-ttu-id="afdf0-368">Beschikbaar als entityType een *gebruiker* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="afdf0-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="afdf0-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="afdf0-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="afdf0-370">userPrincipalName</span></span> | <span data-ttu-id="afdf0-371">Beschikbaar als entityType de e-mail van het postvak van een *gebruiker* is /  / .</span><span class="sxs-lookup"><span data-stu-id="afdf0-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="afdf0-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="afdf0-372">testUser2@contoso.com</span></span>
<span data-ttu-id="afdf0-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="afdf0-373">mailboxDisplayName</span></span> | <span data-ttu-id="afdf0-374">Beschikbaar als entityType het *Postvak* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="afdf0-375">opmonsterset</span><span class="sxs-lookup"><span data-stu-id="afdf0-375">test User2</span></span>
<span data-ttu-id="afdf0-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="afdf0-376">mailboxAddress</span></span> | <span data-ttu-id="afdf0-377">Beschikbaar als entityType de e-mail van het postvak van een *gebruiker* is /  / .</span><span class="sxs-lookup"><span data-stu-id="afdf0-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="afdf0-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="afdf0-378">testUser2@contoso.com</span></span>
<span data-ttu-id="afdf0-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="afdf0-379">clusterBy</span></span> | <span data-ttu-id="afdf0-380">Beschikbaar als entityType een  *mailcluster* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="afdf0-381">Onderwerp P2SenderDomain; Invoer</span><span class="sxs-lookup"><span data-stu-id="afdf0-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="afdf0-382">weet</span><span class="sxs-lookup"><span data-stu-id="afdf0-382">sender</span></span> | <span data-ttu-id="afdf0-383">Beschikbaar als entityType de e-mail van het postvak van een *gebruiker* is /  / .</span><span class="sxs-lookup"><span data-stu-id="afdf0-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="afdf0-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="afdf0-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="afdf0-385">faxontvanger</span><span class="sxs-lookup"><span data-stu-id="afdf0-385">recipient</span></span> | <span data-ttu-id="afdf0-386">Beschikbaar als entityType een *e-mailbericht* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="afdf0-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="afdf0-387">testUser2@contoso.com</span></span>
<span data-ttu-id="afdf0-388">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="afdf0-388">subject</span></span> | <span data-ttu-id="afdf0-389">Beschikbaar als entityType een *e-mailbericht* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="afdf0-390">\[EXTERNE \] aandacht</span><span class="sxs-lookup"><span data-stu-id="afdf0-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="afdf0-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="afdf0-391">deliveryAction</span></span> | <span data-ttu-id="afdf0-392">Beschikbaar als entityType een *e-mailbericht* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="afdf0-393">Aflevering</span><span class="sxs-lookup"><span data-stu-id="afdf0-393">Delivered</span></span>
<span data-ttu-id="afdf0-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="afdf0-394">securityGroupId</span></span> | <span data-ttu-id="afdf0-395">Beschikbaar als entityType  *SecurityGroup* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="afdf0-396">301c47c8-e15f-4059-AB09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="afdf0-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="afdf0-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="afdf0-397">securityGroupName</span></span> | <span data-ttu-id="afdf0-398">Beschikbaar als entityType  *SecurityGroup* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="afdf0-399">Netwerkconfiguratieoperators</span><span class="sxs-lookup"><span data-stu-id="afdf0-399">Network Configuration Operators</span></span>
<span data-ttu-id="afdf0-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="afdf0-400">registryHive</span></span> | <span data-ttu-id="afdf0-401">Beschikbaar als entityType de  *registersleutel* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="afdf0-402">\_lokale \_ machine van HKEY</span><span class="sxs-lookup"><span data-stu-id="afdf0-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="afdf0-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="afdf0-403">registryKey</span></span> | <span data-ttu-id="afdf0-404">Beschikbaar als entityType de  *registersleutel* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="afdf0-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="afdf0-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="afdf0-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="afdf0-406">registryValueType</span></span> | <span data-ttu-id="afdf0-407">Beschikbaar als entityType de  *registersleutel* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="afdf0-408">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="afdf0-408">String</span></span>
<span data-ttu-id="afdf0-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="afdf0-409">registryValue</span></span> | <span data-ttu-id="afdf0-410">Beschikbaar als entityType de  *registersleutel* is.</span><span class="sxs-lookup"><span data-stu-id="afdf0-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="afdf0-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="afdf0-411">31-00-00-00</span></span>
<span data-ttu-id="afdf0-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="afdf0-412">deviceId</span></span> | <span data-ttu-id="afdf0-413">De ID, indien van toepassing, van het apparaat dat is gekoppeld aan de entiteit.</span><span class="sxs-lookup"><span data-stu-id="afdf0-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="afdf0-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="afdf0-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="afdf0-415">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="afdf0-415">Example</span></span>

<span data-ttu-id="afdf0-416">**Webonderdeelverzoek**</span><span class="sxs-lookup"><span data-stu-id="afdf0-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="afdf0-417">**Na**</span><span class="sxs-lookup"><span data-stu-id="afdf0-417">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="afdf0-418">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="afdf0-418">Related articles</span></span>

- [<span data-ttu-id="afdf0-419">Toegang tot de Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="afdf0-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="afdf0-420">Meer informatie over API-limieten en licenties</span><span class="sxs-lookup"><span data-stu-id="afdf0-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="afdf0-421">Meer informatie over foutcodes</span><span class="sxs-lookup"><span data-stu-id="afdf0-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="afdf0-422">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="afdf0-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="afdf0-423">API's voor incidenten</span><span class="sxs-lookup"><span data-stu-id="afdf0-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="afdf0-424">Update incident-API</span><span class="sxs-lookup"><span data-stu-id="afdf0-424">Update incident API</span></span>](api-update-incidents.md)
