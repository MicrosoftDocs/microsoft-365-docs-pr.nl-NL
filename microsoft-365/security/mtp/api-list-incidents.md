---
title: API voor lijst incidenten in Microsoft Threat Protection
description: Ontdek hoe u met API kunt vermelden in Microsoft Threat Protection
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
ms.openlocfilehash: 9defc9c0f8fa04e019c0108ca0f4111de54edb5f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195377"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a><span data-ttu-id="82f4a-104">API voor lijst incidenten in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="82f4a-104">List incidents API in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="82f4a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="82f4a-105">**Applies to:**</span></span>

- <span data-ttu-id="82f4a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="82f4a-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82f4a-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="82f4a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="82f4a-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="82f4a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="82f4a-109">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="82f4a-109">API description</span></span>

<span data-ttu-id="82f4a-110">Met behulp van de incident-API kunt u sorteren op een weloverwogen Cyber Security-antwoord, zodat u deze kunt voorzien van een prioriteit.</span><span class="sxs-lookup"><span data-stu-id="82f4a-110">The Incident API allows you to sort through incidents to prioritize and create an informed cybersecurity response.</span></span> <span data-ttu-id="82f4a-111">Dit maakt een verzameling van incidenten die zijn gemarkeerd vanaf apparaten, e-mailaccounts en gebruikers in uw netwerk, binnen de periode die u hebt opgegeven in het bewaarbeleid voor de omgeving.</span><span class="sxs-lookup"><span data-stu-id="82f4a-111">It exposes a collection of incidents that were flagged from devices, email accounts, and users in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="82f4a-112">De meest recente incidenten worden bovenaan de lijst weergegeven.</span><span class="sxs-lookup"><span data-stu-id="82f4a-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="82f4a-113">Elk incident bevat een matrix met gerelateerde waarschuwingen en de gerelateerde entiteiten.</span><span class="sxs-lookup"><span data-stu-id="82f4a-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<br><span data-ttu-id="82f4a-114">De API biedt ondersteuning voor de volgende **OData** -operatoren:</span><span class="sxs-lookup"><span data-stu-id="82f4a-114">The API supports the following **OData** operators:</span></span>
<br><span data-ttu-id="82f4a-115">```$filter``` op: ```lastUpdateTime``` , ```createdTime``` ```status``` en ```assignedTo``` Eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="82f4a-115">```$filter``` on: ```lastUpdateTime```, ```createdTime```, ```status``` and ```assignedTo``` properties.</span></span>
<br><span data-ttu-id="82f4a-116">```$top``` met de maximale waarde van **100**</span><span class="sxs-lookup"><span data-stu-id="82f4a-116">```$top``` with max value of **100**</span></span>
<br>```$skip```

## <a name="limitations"></a><span data-ttu-id="82f4a-117">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="82f4a-117">Limitations</span></span>

1. <span data-ttu-id="82f4a-118">Het maximale paginaformaat is **100 incidenten**.</span><span class="sxs-lookup"><span data-stu-id="82f4a-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="82f4a-119">Het maximale aantal aanvragen is **50 oproepen per minuut** en **1500-oproepen per uur**.</span><span class="sxs-lookup"><span data-stu-id="82f4a-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="82f4a-120">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="82f4a-120">Permissions</span></span>

<span data-ttu-id="82f4a-121">U moet een van de volgende machtigingen hebben om deze API te kunnen bellen.</span><span class="sxs-lookup"><span data-stu-id="82f4a-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="82f4a-122">Zie [Microsoft Threat Protection-Api's openen](api-access.md) voor meer informatie, waaronder de manier waarop u machtigingen kiest.</span><span class="sxs-lookup"><span data-stu-id="82f4a-122">To learn more, including how to choose permissions, see [Access Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="82f4a-123">Type machtiging</span><span class="sxs-lookup"><span data-stu-id="82f4a-123">Permission type</span></span> |   <span data-ttu-id="82f4a-124">Machtigingsset</span><span class="sxs-lookup"><span data-stu-id="82f4a-124">Permission</span></span>  |   <span data-ttu-id="82f4a-125">Weergavenaam van de machtiging</span><span class="sxs-lookup"><span data-stu-id="82f4a-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="82f4a-126">Toepassing</span><span class="sxs-lookup"><span data-stu-id="82f4a-126">Application</span></span> |   <span data-ttu-id="82f4a-127">Incident. Read. all</span><span class="sxs-lookup"><span data-stu-id="82f4a-127">Incident.Read.All</span></span> | <span data-ttu-id="82f4a-128">' Alle incidenten lezen '</span><span class="sxs-lookup"><span data-stu-id="82f4a-128">'Read all incidents'</span></span>
<span data-ttu-id="82f4a-129">Toepassing</span><span class="sxs-lookup"><span data-stu-id="82f4a-129">Application</span></span> |   <span data-ttu-id="82f4a-130">Incident. ReadWrite. all</span><span class="sxs-lookup"><span data-stu-id="82f4a-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="82f4a-131">' Alle incidenten lezen en schrijven '</span><span class="sxs-lookup"><span data-stu-id="82f4a-131">'Read and write all incidents'</span></span>
<span data-ttu-id="82f4a-132">Gedelegeerd (werk-of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="82f4a-132">Delegated (work or school account)</span></span> | <span data-ttu-id="82f4a-133">Incident. Read</span><span class="sxs-lookup"><span data-stu-id="82f4a-133">Incident.Read</span></span> | <span data-ttu-id="82f4a-134">' Lees incidenten '</span><span class="sxs-lookup"><span data-stu-id="82f4a-134">'Read incidents'</span></span>
<span data-ttu-id="82f4a-135">Gedelegeerd (werk-of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="82f4a-135">Delegated (work or school account)</span></span> | <span data-ttu-id="82f4a-136">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="82f4a-136">Incident.ReadWrite</span></span> | <span data-ttu-id="82f4a-137">' Lees-en schrijf incident '</span><span class="sxs-lookup"><span data-stu-id="82f4a-137">'Read and write incidents'</span></span>

> [!Note]
> <span data-ttu-id="82f4a-138">Bij het verkrijgen van een token met behulp van gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="82f4a-138">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="82f4a-139">De gebruiker moet de machtiging voor weergeven voor incidenten in de portal hebben.</span><span class="sxs-lookup"><span data-stu-id="82f4a-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="82f4a-140">Het antwoord bevat alleen incidenten waaraan de gebruiker is blootgesteld.</span><span class="sxs-lookup"><span data-stu-id="82f4a-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="82f4a-141">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="82f4a-141">HTTP request</span></span>

```
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="82f4a-142">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="82f4a-142">Request headers</span></span>

<span data-ttu-id="82f4a-143">Naam</span><span class="sxs-lookup"><span data-stu-id="82f4a-143">Name</span></span> | <span data-ttu-id="82f4a-144">Type</span><span class="sxs-lookup"><span data-stu-id="82f4a-144">Type</span></span> | <span data-ttu-id="82f4a-145">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="82f4a-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="82f4a-146">Bevoegdheid</span><span class="sxs-lookup"><span data-stu-id="82f4a-146">Authorization</span></span> | <span data-ttu-id="82f4a-147">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="82f4a-147">String</span></span> | <span data-ttu-id="82f4a-148">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="82f4a-148">Bearer {token}.</span></span> <span data-ttu-id="82f4a-149">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="82f4a-149">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="82f4a-150">Aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="82f4a-150">Request body</span></span>
<span data-ttu-id="82f4a-151">Zonder.</span><span class="sxs-lookup"><span data-stu-id="82f4a-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="82f4a-152">Na</span><span class="sxs-lookup"><span data-stu-id="82f4a-152">Response</span></span>
<span data-ttu-id="82f4a-153">Als dit is gelukt, retourneert deze methode 200 OK en een lijst met [incidenten](api-incident.md) in de tekst van het antwoord.</span><span class="sxs-lookup"><span data-stu-id="82f4a-153">If successful, this method returns 200 OK, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="82f4a-154">Schema toewijzingen</span><span class="sxs-lookup"><span data-stu-id="82f4a-154">Schema mapping</span></span>

| <span data-ttu-id="82f4a-155">Veld naam</span><span class="sxs-lookup"><span data-stu-id="82f4a-155">Field name</span></span>                                | <span data-ttu-id="82f4a-156">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="82f4a-156">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="82f4a-157">Voorbeeldwaarde</span><span class="sxs-lookup"><span data-stu-id="82f4a-157">Example value</span></span>                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="82f4a-158">**Metagegevens van incident**</span><span class="sxs-lookup"><span data-stu-id="82f4a-158">**Incident metadata**</span></span>                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="82f4a-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="82f4a-159">incidentId</span></span>                                | <span data-ttu-id="82f4a-160">Unieke id die het incident voorstelt.</span><span class="sxs-lookup"><span data-stu-id="82f4a-160">Unique identifier to represent the incident.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="82f4a-161">924565</span><span class="sxs-lookup"><span data-stu-id="82f4a-161">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="82f4a-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="82f4a-162">redirectIncidentId</span></span>                        | <span data-ttu-id="82f4a-163">Wordt alleen ingevuld wanneer een incident wordt gegroepeerd met een ander incident, als onderdeel van de logica voor het verwerken van incidenten.</span><span class="sxs-lookup"><span data-stu-id="82f4a-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span>                                                                                                                                                                                                                                                           | <span data-ttu-id="82f4a-164">924569</span><span class="sxs-lookup"><span data-stu-id="82f4a-164">924569</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="82f4a-165">voorval</span><span class="sxs-lookup"><span data-stu-id="82f4a-165">incidentName</span></span>                              | <span data-ttu-id="82f4a-166">De tekenreekswaarde voor elk incident.</span><span class="sxs-lookup"><span data-stu-id="82f4a-166">String value available for every incident.</span></span>                                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="82f4a-167">Ransomware-activiteit</span><span class="sxs-lookup"><span data-stu-id="82f4a-167">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="82f4a-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="82f4a-168">createdTime</span></span>                               | <span data-ttu-id="82f4a-169">Tijdstip waarop het incident voor het eerst is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="82f4a-169">Time when incident was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                      | <span data-ttu-id="82f4a-170">2020-09-06T14:46:57.0733333 Z</span><span class="sxs-lookup"><span data-stu-id="82f4a-170">2020-09-06T14:46:57.0733333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="82f4a-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="82f4a-171">lastUpdateTime</span></span>                            | <span data-ttu-id="82f4a-172">Tijdstip waarop het incident voor het laatst is bijgewerkt op de backend.</span><span class="sxs-lookup"><span data-stu-id="82f4a-172">Time when incident was last updated at the backend.</span></span><br> <span data-ttu-id="82f4a-173">Dit veld kan worden gebruikt voor het instellen van de parameter Request voor het tijdsbereik dat incidenten worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="82f4a-173">This field can be used when setting the request parameter for the range of time that incidents are retrieved.</span></span>                                                                                                                                                                                                                      | <span data-ttu-id="82f4a-174">2020-09-06T14:46:57.29 Z</span><span class="sxs-lookup"><span data-stu-id="82f4a-174">2020-09-06T14:46:57.29Z</span></span>                                                                                                                                                                                                                           |
| <span data-ttu-id="82f4a-175">ToegewezenAan</span><span class="sxs-lookup"><span data-stu-id="82f4a-175">assignedTo</span></span>                                | <span data-ttu-id="82f4a-176">Eigenaar van het incident, of *Null* als er geen eigenaar wordt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="82f4a-176">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="82f4a-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="82f4a-177">secop2@contoso.com</span></span>                                                                                                                                                                                                |
| <span data-ttu-id="82f4a-178">Contactpersoonclassificatie</span><span class="sxs-lookup"><span data-stu-id="82f4a-178">classification</span></span>                            | <span data-ttu-id="82f4a-179">De specificatie van het incident.</span><span class="sxs-lookup"><span data-stu-id="82f4a-179">The specification for the incident.</span></span> <span data-ttu-id="82f4a-180">De eigenschapwaarden zijn: *onbekend*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="82f4a-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span>                                                                                                                                                                                                                                                                           | <span data-ttu-id="82f4a-181">Unknown</span><span class="sxs-lookup"><span data-stu-id="82f4a-181">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="82f4a-182">relevant</span><span class="sxs-lookup"><span data-stu-id="82f4a-182">determination</span></span>                             | <span data-ttu-id="82f4a-183">Hiermee wordt het bepalen van het incident aangegeven.</span><span class="sxs-lookup"><span data-stu-id="82f4a-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="82f4a-184">De eigenschapwaarden zijn: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Overig*</span><span class="sxs-lookup"><span data-stu-id="82f4a-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span>                                                                                                                                                                                                                | <span data-ttu-id="82f4a-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="82f4a-185">NotAvailable</span></span>                                                                                                                                                                                                                                      |
| <span data-ttu-id="82f4a-186">status</span><span class="sxs-lookup"><span data-stu-id="82f4a-186">status</span></span>                                    | <span data-ttu-id="82f4a-187">Incidenten categoriseren (als *actief*of *opgelost*).</span><span class="sxs-lookup"><span data-stu-id="82f4a-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="82f4a-188">Hiermee kunt u uw antwoord op incidenten organiseren en beheren.</span><span class="sxs-lookup"><span data-stu-id="82f4a-188">This helps you organize and manage your response to incidents.</span></span>                                                                                                                                                                                                                                                                  | <span data-ttu-id="82f4a-189">Actief</span><span class="sxs-lookup"><span data-stu-id="82f4a-189">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="82f4a-190">Ernst</span><span class="sxs-lookup"><span data-stu-id="82f4a-190">severity</span></span>                                  | <span data-ttu-id="82f4a-191">Geeft de mogelijke gevolgen voor activa aan.</span><span class="sxs-lookup"><span data-stu-id="82f4a-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="82f4a-192">Hoe hoger de ernst, hoe groter de impact.</span><span class="sxs-lookup"><span data-stu-id="82f4a-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="82f4a-193">Meestal hebt u de meest directe aandacht nodig voor hogere prioriteits items.</span><span class="sxs-lookup"><span data-stu-id="82f4a-193">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="82f4a-194">Een van de volgende waarden: *informatie*, *laag*, \* medium en *hoog*.</span><span class="sxs-lookup"><span data-stu-id="82f4a-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                | <span data-ttu-id="82f4a-195">Medium</span><span class="sxs-lookup"><span data-stu-id="82f4a-195">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="82f4a-196">Tags</span><span class="sxs-lookup"><span data-stu-id="82f4a-196">tags</span></span>                                      | <span data-ttu-id="82f4a-197">Matrix van aangepaste labels die zijn gekoppeld aan een incident, bijvoorbeeld om een groep incidenten met een gemeenschappelijk kenmerk te markeren.</span><span class="sxs-lookup"><span data-stu-id="82f4a-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span>                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="82f4a-198">kennisgeving</span><span class="sxs-lookup"><span data-stu-id="82f4a-198">alerts</span></span>                                    | <span data-ttu-id="82f4a-199">Matrix van alle meldingen met betrekking tot het incident en andere informatie, zoals Ernst, entiteiten die betrokken zijn bij de waarschuwing, de bron van de meldingen.</span><span class="sxs-lookup"><span data-stu-id="82f4a-199">Array of all the alerts related to the incident and other information, such as severity, entities that were involved in the alert, the source of the alerts.</span></span>                                                                                                                                                                                                                     | <span data-ttu-id="82f4a-200">\[\] (Zie Details over waarschuwingsvelden hieronder)</span><span class="sxs-lookup"><span data-stu-id="82f4a-200">\[\] (see details on alert fields below)</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="82f4a-201">**Metagegevens van waarschuwingen**</span><span class="sxs-lookup"><span data-stu-id="82f4a-201">**Alerts metadata**</span></span>                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="82f4a-202">alertId</span><span class="sxs-lookup"><span data-stu-id="82f4a-202">alertId</span></span>                                   | <span data-ttu-id="82f4a-203">Unieke id die de waarschuwing voorstelt</span><span class="sxs-lookup"><span data-stu-id="82f4a-203">Unique identifier to represent the alert</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="82f4a-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="82f4a-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>                                                                                                                                                                                                            |
| <span data-ttu-id="82f4a-205">incidentId</span><span class="sxs-lookup"><span data-stu-id="82f4a-205">incidentId</span></span>                                | <span data-ttu-id="82f4a-206">Unieke id waarmee het incident wordt aangegeven waaraan deze waarschuwing is gekoppeld</span><span class="sxs-lookup"><span data-stu-id="82f4a-206">Unique identifier to represent the incident this alert is associated with</span></span>                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="82f4a-207">924565</span><span class="sxs-lookup"><span data-stu-id="82f4a-207">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="82f4a-208">serviceSource</span><span class="sxs-lookup"><span data-stu-id="82f4a-208">serviceSource</span></span>                             | <span data-ttu-id="82f4a-209">Dienst waarvan de waarschuwing afkomstig is, zoals Microsoft Defender ATP, beveiliging van Microsoft Cloud-app, Azure ATP of Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="82f4a-209">Service that the alert originates from, such as Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, or Office 365 ATP.</span></span>                                                                                                                                                                                                                                                                     | <span data-ttu-id="82f4a-210">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="82f4a-210">MicrosoftCloudAppSecurity</span></span>                                                                                                                                                                                                                         |
| <span data-ttu-id="82f4a-211">creationTime</span><span class="sxs-lookup"><span data-stu-id="82f4a-211">creationTime</span></span>                              | <span data-ttu-id="82f4a-212">Tijdstip waarop de waarschuwing voor het eerst is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="82f4a-212">Time when alert was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="82f4a-213">2020-09-06T14:46:55.7182276 Z</span><span class="sxs-lookup"><span data-stu-id="82f4a-213">2020-09-06T14:46:55.7182276Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="82f4a-214">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="82f4a-214">lastUpdatedTime</span></span>                           | <span data-ttu-id="82f4a-215">Tijdstip waarop de waarschuwing voor het laatst is bijgewerkt op de backend.</span><span class="sxs-lookup"><span data-stu-id="82f4a-215">Time when alert was last updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="82f4a-216">2020-09-06T14:46:57.2433333 Z</span><span class="sxs-lookup"><span data-stu-id="82f4a-216">2020-09-06T14:46:57.2433333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="82f4a-217">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="82f4a-217">resolvedTime</span></span>                              | <span data-ttu-id="82f4a-218">Tijdstip waarop de waarschuwing is opgelost.</span><span class="sxs-lookup"><span data-stu-id="82f4a-218">Time when alert was resolved.</span></span>                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="82f4a-219">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="82f4a-219">2020-09-10T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="82f4a-220">firstActivity</span><span class="sxs-lookup"><span data-stu-id="82f4a-220">firstActivity</span></span>                             | <span data-ttu-id="82f4a-221">Tijd waarop de waarschuwing voor het eerst werd gerapporteerd dat de activiteit op de backend werd bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="82f4a-221">Time when alert first reported that activity was updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="82f4a-222">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="82f4a-222">2020-09-04T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="82f4a-223">begin</span><span class="sxs-lookup"><span data-stu-id="82f4a-223">title</span></span>                                     | <span data-ttu-id="82f4a-224">Kort herkenbare identificatiewaarde voor elke waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="82f4a-224">Brief identifying string value available for each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="82f4a-225">Ransomware-activiteit</span><span class="sxs-lookup"><span data-stu-id="82f4a-225">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="82f4a-226">beschrijving</span><span class="sxs-lookup"><span data-stu-id="82f4a-226">description</span></span>                               | <span data-ttu-id="82f4a-227">De tekenreekswaarde waarmee wordt gewaarschuwd.</span><span class="sxs-lookup"><span data-stu-id="82f4a-227">String value describing each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="82f4a-228">De testUser2@contoso.com-bestanden () die zijn 99 bewerkt met een niet-gemeenschappelijke uitbreiding *herunterladen*</span><span class="sxs-lookup"><span data-stu-id="82f4a-228">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="82f4a-229">Dit is een ongebruikelijk aantal bestandsbewerkingen en is een aanwijzing voor een potentiële aanval van Ransomware.</span><span class="sxs-lookup"><span data-stu-id="82f4a-229">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span> |
| <span data-ttu-id="82f4a-230">Categorie</span><span class="sxs-lookup"><span data-stu-id="82f4a-230">category</span></span>                                  | <span data-ttu-id="82f4a-231">Visuele en numerieke weergave van de hoeveelheid aanval op de Kill-ketting.</span><span class="sxs-lookup"><span data-stu-id="82f4a-231">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="82f4a-232">Uitgelijnd op de [Mitre ATT&a™ Framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="82f4a-232">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span>                                                                                                                                                                                                                           | <span data-ttu-id="82f4a-233">Gevolg</span><span class="sxs-lookup"><span data-stu-id="82f4a-233">Impact</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="82f4a-234">status</span><span class="sxs-lookup"><span data-stu-id="82f4a-234">status</span></span>                                    | <span data-ttu-id="82f4a-235">Waarschuwingen categoriseren (als *Nieuw*, *actief*of *opgelost*)</span><span class="sxs-lookup"><span data-stu-id="82f4a-235">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="82f4a-236">Hiermee kunt u uw antwoord op waarschuwingen organiseren en beheren.</span><span class="sxs-lookup"><span data-stu-id="82f4a-236">This helps you organize and manage your response to alerts.</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="82f4a-237">Nieuw</span><span class="sxs-lookup"><span data-stu-id="82f4a-237">New</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="82f4a-238">Ernst</span><span class="sxs-lookup"><span data-stu-id="82f4a-238">severity</span></span>                                  | <span data-ttu-id="82f4a-239">Geeft de mogelijke gevolgen voor activa aan.</span><span class="sxs-lookup"><span data-stu-id="82f4a-239">Indicates the possible impact on assets.</span></span> <span data-ttu-id="82f4a-240">Hoe hoger de ernst, hoe groter de impact.</span><span class="sxs-lookup"><span data-stu-id="82f4a-240">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="82f4a-241">Meestal hebt u de meest directe aandacht nodig voor hogere prioriteits items.</span><span class="sxs-lookup"><span data-stu-id="82f4a-241">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="82f4a-242">Een van de volgende waarden: *informatie*, *laag*, \* medium en *hoog*.</span><span class="sxs-lookup"><span data-stu-id="82f4a-242">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                   | <span data-ttu-id="82f4a-243">Medium</span><span class="sxs-lookup"><span data-stu-id="82f4a-243">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="82f4a-244">investigationId</span><span class="sxs-lookup"><span data-stu-id="82f4a-244">investigationId</span></span>                           | <span data-ttu-id="82f4a-245">De geautomatiseerde onderzoek-id die door deze melding wordt geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="82f4a-245">The automated investigation id triggered by this alert.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="82f4a-246">1234</span><span class="sxs-lookup"><span data-stu-id="82f4a-246">1234</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="82f4a-247">investigationState</span><span class="sxs-lookup"><span data-stu-id="82f4a-247">investigationState</span></span>                        | <span data-ttu-id="82f4a-248">Informatie over de huidige status van het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="82f4a-248">Information on the investigation's current status.</span></span> <span data-ttu-id="82f4a-249">Een van de volgende: *onbekend*, *beëindigd*, *SuccessfullyRemediated*, *ongeluk, mislukt*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert.* *Benign*</span><span class="sxs-lookup"><span data-stu-id="82f4a-249">One of the following: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="82f4a-250">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="82f4a-250">UnsupportedAlertType</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="82f4a-251">Contactpersoonclassificatie</span><span class="sxs-lookup"><span data-stu-id="82f4a-251">classification</span></span>                            | <span data-ttu-id="82f4a-252">De specificatie van het incident.</span><span class="sxs-lookup"><span data-stu-id="82f4a-252">The specification for the incident.</span></span> <span data-ttu-id="82f4a-253">De eigenschapwaarden zijn: *onbekend*, *FalsePositive*, *TruePositive* of *Null*</span><span class="sxs-lookup"><span data-stu-id="82f4a-253">The property values are: *Unknown*, *FalsePositive*, *TruePositive* or *null*</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="82f4a-254">Unknown</span><span class="sxs-lookup"><span data-stu-id="82f4a-254">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="82f4a-255">relevant</span><span class="sxs-lookup"><span data-stu-id="82f4a-255">determination</span></span>                             | <span data-ttu-id="82f4a-256">Hiermee wordt het bepalen van het incident aangegeven.</span><span class="sxs-lookup"><span data-stu-id="82f4a-256">Specifies the determination of the incident.</span></span> <span data-ttu-id="82f4a-257">De eigenschapwaarden zijn: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other* of  *Null*</span><span class="sxs-lookup"><span data-stu-id="82f4a-257">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="82f4a-258">Apt</span><span class="sxs-lookup"><span data-stu-id="82f4a-258">Apt</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="82f4a-259">ToegewezenAan</span><span class="sxs-lookup"><span data-stu-id="82f4a-259">assignedTo</span></span>                                | <span data-ttu-id="82f4a-260">Eigenaar van het incident, of *Null* als er geen eigenaar wordt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="82f4a-260">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                            | <span data-ttu-id="82f4a-261">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="82f4a-261">secop2@contoso.com</span></span>                                                                                                                                                                                                 |
| <span data-ttu-id="82f4a-262">actor</span><span class="sxs-lookup"><span data-stu-id="82f4a-262">actorName</span></span>                                 | <span data-ttu-id="82f4a-263">De groep activiteit, indien van toepassing, de koppeling met deze waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="82f4a-263">The activity group, if any, the  associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="82f4a-264">EQUIVALENT</span><span class="sxs-lookup"><span data-stu-id="82f4a-264">BORON</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="82f4a-265">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="82f4a-265">threatFamilyName</span></span>                          | <span data-ttu-id="82f4a-266">Bedreigings familie van deze melding.</span><span class="sxs-lookup"><span data-stu-id="82f4a-266">Threat family associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="82f4a-267">waarden</span><span class="sxs-lookup"><span data-stu-id="82f4a-267">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="82f4a-268">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="82f4a-268">mitreTechniques</span></span>                           | <span data-ttu-id="82f4a-269">De aantastings methoden, zoals afgestemd op de [Mitre ATT&a](https://attack.mitre.org/)™ Framework.</span><span class="sxs-lookup"><span data-stu-id="82f4a-269">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span>                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="82f4a-270">apparaten</span><span class="sxs-lookup"><span data-stu-id="82f4a-270">devices</span></span>                                   | <span data-ttu-id="82f4a-271">Alle apparaten waarop meldingen met betrekking tot het incident zijn verzonden.</span><span class="sxs-lookup"><span data-stu-id="82f4a-271">All devices where alerts related to the incident were sent.</span></span>                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="82f4a-272">\[\] (Zie Details van de onderstaande entiteits velden)</span><span class="sxs-lookup"><span data-stu-id="82f4a-272">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="82f4a-273">**Indeling van apparaat**</span><span class="sxs-lookup"><span data-stu-id="82f4a-273">**Device format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="82f4a-274">DeviceId</span><span class="sxs-lookup"><span data-stu-id="82f4a-274">DeviceId</span></span>                                  | <span data-ttu-id="82f4a-275">De apparaat-ID zoals aangegeven in Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="82f4a-275">The device ID as designated in Microsoft Defender ATP.</span></span>                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="82f4a-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="82f4a-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="82f4a-277">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="82f4a-277">aadDeviceId</span></span>                               |  <span data-ttu-id="82f4a-278">De apparaat-id zoals aangegeven in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (Aad).</span><span class="sxs-lookup"><span data-stu-id="82f4a-278">The device Id as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span></span> <span data-ttu-id="82f4a-279">Alleen beschikbaar voor apparaten die lid zijn van een domein.</span><span class="sxs-lookup"><span data-stu-id="82f4a-279">Only available for domain-joined devices.</span></span>                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="82f4a-280">waarden</span><span class="sxs-lookup"><span data-stu-id="82f4a-280">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="82f4a-281">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="82f4a-281">deviceDnsName</span></span>                             | <span data-ttu-id="82f4a-282">De FQDN-naam (Fully Qualified Domain Name) voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="82f4a-282">The fully qualified domain name for the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="82f4a-283">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="82f4a-283">user5cx.middleeast.corp.contoso.com</span></span>                                                                                                                                                                                                    |
| <span data-ttu-id="82f4a-284">osPlatform</span><span class="sxs-lookup"><span data-stu-id="82f4a-284">osPlatform</span></span>                                | <span data-ttu-id="82f4a-285">Het OS-platform waarop het apparaat wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="82f4a-285">The OS platform the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="82f4a-286">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="82f4a-286">WindowsServer2016</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="82f4a-287">osBuild</span><span class="sxs-lookup"><span data-stu-id="82f4a-287">osBuild</span></span>                                   | <span data-ttu-id="82f4a-288">De build-versie van het besturingssysteem dat het apparaat uitvoert.</span><span class="sxs-lookup"><span data-stu-id="82f4a-288">The build version for the OS the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="82f4a-289">14393</span><span class="sxs-lookup"><span data-stu-id="82f4a-289">14393</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="82f4a-290">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="82f4a-290">rbacGroupName</span></span>                             | <span data-ttu-id="82f4a-291">De groep [toegangsbeheer op basis van rollen](https://docs.microsoft.com/azure/role-based-access-control/overview) die is gekoppeld aan het apparaat.</span><span class="sxs-lookup"><span data-stu-id="82f4a-291">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="82f4a-292">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="82f4a-292">WDATP-Ring0</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="82f4a-293">firstSeen</span><span class="sxs-lookup"><span data-stu-id="82f4a-293">firstSeen</span></span>                                 | <span data-ttu-id="82f4a-294">Tijdstip waarop apparaat voor het eerst werd gezien.</span><span class="sxs-lookup"><span data-stu-id="82f4a-294">Time when device was first seen.</span></span>                                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="82f4a-295">2020-02-06T14:16:01.9330135 Z</span><span class="sxs-lookup"><span data-stu-id="82f4a-295">2020-02-06T14:16:01.9330135Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="82f4a-296">healthStatus</span><span class="sxs-lookup"><span data-stu-id="82f4a-296">healthStatus</span></span>                              | <span data-ttu-id="82f4a-297">De status van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="82f4a-297">The health state of the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="82f4a-298">Actief</span><span class="sxs-lookup"><span data-stu-id="82f4a-298">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="82f4a-299">riskScore</span><span class="sxs-lookup"><span data-stu-id="82f4a-299">riskScore</span></span>                                 | <span data-ttu-id="82f4a-300">De risicoscore voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="82f4a-300">The risk score for the  device.</span></span>                                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="82f4a-301">Hoog</span><span class="sxs-lookup"><span data-stu-id="82f4a-301">High</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="82f4a-302">onderzoeksinstellingen</span><span class="sxs-lookup"><span data-stu-id="82f4a-302">entities</span></span>                                  | <span data-ttu-id="82f4a-303">Alle entiteiten die zijn geïdentificeerd om deel te nemen aan, of gerelateerd zijn aan een bepaalde melding.</span><span class="sxs-lookup"><span data-stu-id="82f4a-303">All entities that have been identified to be part of, or related to, a given alert.</span></span>                                                                                                                                                                                                                                                                                | <span data-ttu-id="82f4a-304">\[\] (Zie Details van de onderstaande entiteits velden)</span><span class="sxs-lookup"><span data-stu-id="82f4a-304">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="82f4a-305">**Entiteits indeling**</span><span class="sxs-lookup"><span data-stu-id="82f4a-305">**Entity Format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="82f4a-306">entityType</span><span class="sxs-lookup"><span data-stu-id="82f4a-306">entityType</span></span>                                | <span data-ttu-id="82f4a-307">Entiteiten die zijn geïdentificeerd om deel te nemen aan een bepaalde melding, of betrekking hebben op een bepaalde melding.</span><span class="sxs-lookup"><span data-stu-id="82f4a-307">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="82f4a-308">De eigenschappen waarden zijn: *gebruiker*, *IP*, *URL*, *bestand*, *proces*, *Postvak*, *e-mailbericht, e-mail* *cluster*, *register*</span><span class="sxs-lookup"><span data-stu-id="82f4a-308">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="82f4a-309">Gebruiker</span><span class="sxs-lookup"><span data-stu-id="82f4a-309">User</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="82f4a-310">SHA1</span><span class="sxs-lookup"><span data-stu-id="82f4a-310">sha1</span></span>                                      | <span data-ttu-id="82f4a-311">Beschikbaar als entityType een *bestand*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-311">Available if entityType is *File*.</span></span><br><span data-ttu-id="82f4a-312">De bestands-hash voor waarschuwingen die zijn gekoppeld aan een bestand of proces.</span><span class="sxs-lookup"><span data-stu-id="82f4a-312">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="82f4a-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="82f4a-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="82f4a-314">sha256</span><span class="sxs-lookup"><span data-stu-id="82f4a-314">sha256</span></span>                                    | <span data-ttu-id="82f4a-315">Beschikbaar als entityType een *bestand*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-315">Available if entityType is *File*.</span></span><br><span data-ttu-id="82f4a-316">De bestands-hash voor waarschuwingen die zijn gekoppeld aan een bestand of proces.</span><span class="sxs-lookup"><span data-stu-id="82f4a-316">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="82f4a-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="82f4a-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="82f4a-318">Namen</span><span class="sxs-lookup"><span data-stu-id="82f4a-318">fileName</span></span>                                  | <span data-ttu-id="82f4a-319">Beschikbaar als entityType een *bestand*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-319">Available if entityType is *File*.</span></span><br><span data-ttu-id="82f4a-320">De bestandsnaam van waarschuwingen die zijn gekoppeld aan een bestand of proces</span><span class="sxs-lookup"><span data-stu-id="82f4a-320">The file name for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="82f4a-321">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="82f4a-321">Detector.UnitTests.dll</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="82f4a-322">Bestandspad</span><span class="sxs-lookup"><span data-stu-id="82f4a-322">filePath</span></span>                                  | <span data-ttu-id="82f4a-323">Beschikbaar als entityType een *bestand*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-323">Available if entityType is *File*.</span></span><br><span data-ttu-id="82f4a-324">Het bestandspad voor waarschuwingen die zijn gekoppeld aan een bestand of proces</span><span class="sxs-lookup"><span data-stu-id="82f4a-324">The file path for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="82f4a-325">C: werk van de \\ \\ agent voor \\ \\ \_ \\ \\ \_ tijdelijke \\ \\ distributie van \_ systeem 2020-09-06 12 \_ 14 \_ 54 \\ \\ uit</span><span class="sxs-lookup"><span data-stu-id="82f4a-325">C:\\\\Agent\\\\\_work\\\\\_temp\\\\Deploy\_SYSTEM 2020-09-06 12\_14\_54\\\\Out</span></span>                                                                                                                                                                    |
| <span data-ttu-id="82f4a-326">Proces</span><span class="sxs-lookup"><span data-stu-id="82f4a-326">processId</span></span>                                 | <span data-ttu-id="82f4a-327">Beschikbaar als entityType *proces*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-327">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="82f4a-328">24348</span><span class="sxs-lookup"><span data-stu-id="82f4a-328">24348</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="82f4a-329">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="82f4a-329">processCommandLine</span></span>                        | <span data-ttu-id="82f4a-330">Beschikbaar als entityType *proces*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-330">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="82f4a-331">" \\ " Het bestand kan worden gedownload \_1911150169.exe\\ ""</span><span class="sxs-lookup"><span data-stu-id="82f4a-331">"\\"Your File Is Ready To Download\_1911150169.exe\\" "</span></span>                                                                                                                                                                                           |
| <span data-ttu-id="82f4a-332">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="82f4a-332">processCreationTime</span></span>                       | <span data-ttu-id="82f4a-333">Beschikbaar als entityType *proces*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-333">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="82f4a-334">2020-7-18T03:25:38.5269993 Z</span><span class="sxs-lookup"><span data-stu-id="82f4a-334">2020-07-18T03:25:38.5269993Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="82f4a-335">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="82f4a-335">parentProcessId</span></span>                           | <span data-ttu-id="82f4a-336">Beschikbaar als entityType *proces*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-336">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="82f4a-337">16840</span><span class="sxs-lookup"><span data-stu-id="82f4a-337">16840</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="82f4a-338">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="82f4a-338">parentProcessCreationTime</span></span>                 | <span data-ttu-id="82f4a-339">Beschikbaar als entityType *proces*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-339">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="82f4a-340">2020-7-18T02:12:32.8616797 Z</span><span class="sxs-lookup"><span data-stu-id="82f4a-340">2020-07-18T02:12:32.8616797Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="82f4a-341">Adressen</span><span class="sxs-lookup"><span data-stu-id="82f4a-341">ipAddress</span></span>                                 | <span data-ttu-id="82f4a-342">Beschikbaar als entityType een *IP-adres*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-342">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="82f4a-343">IP-adres voor waarschuwingen die zijn gekoppeld aan netwerkgebeurtenissen, zoals *communicatie met een kwaadaardige bestemming*.</span><span class="sxs-lookup"><span data-stu-id="82f4a-343">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                   | <span data-ttu-id="82f4a-344">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="82f4a-344">62.216.203.204</span></span>                                                                                                                                                                                                                                    |
| <span data-ttu-id="82f4a-345">URL</span><span class="sxs-lookup"><span data-stu-id="82f4a-345">url</span></span>                                       | <span data-ttu-id="82f4a-346">Beschikbaar als entityType de *URL*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-346">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="82f4a-347">URL voor meldingen die zijn gekoppeld aan netwerkgebeurtenissen, zoals *communicatie met een kwaadaardige bestemming*.</span><span class="sxs-lookup"><span data-stu-id="82f4a-347">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                  | <span data-ttu-id="82f4a-348">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="82f4a-348">down.esales360.cn</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="82f4a-349">accountName</span><span class="sxs-lookup"><span data-stu-id="82f4a-349">accountName</span></span>                               | <span data-ttu-id="82f4a-350">Beschikbaar als entityType een *gebruiker*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-350">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="82f4a-351">testUser2</span><span class="sxs-lookup"><span data-stu-id="82f4a-351">testUser2</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="82f4a-352">Domeinnaam</span><span class="sxs-lookup"><span data-stu-id="82f4a-352">domainName</span></span>                                | <span data-ttu-id="82f4a-353">Beschikbaar als entityType een *gebruiker*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-353">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="82f4a-354">Europe. Corp. contoso</span><span class="sxs-lookup"><span data-stu-id="82f4a-354">europe.corp.contoso</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="82f4a-355">userSid</span><span class="sxs-lookup"><span data-stu-id="82f4a-355">userSid</span></span>                                   | <span data-ttu-id="82f4a-356">Beschikbaar als entityType een *gebruiker*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-356">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="82f4a-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="82f4a-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="82f4a-358">aadUserId</span><span class="sxs-lookup"><span data-stu-id="82f4a-358">aadUserId</span></span>                                 | <span data-ttu-id="82f4a-359">Beschikbaar als entityType een *gebruiker*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-359">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="82f4a-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="82f4a-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="82f4a-361">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="82f4a-361">userPrincipalName</span></span>                         | <span data-ttu-id="82f4a-362">Beschikbaar als entityType de e-mail van het postvak van een *gebruiker*is / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="82f4a-362">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="82f4a-363">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="82f4a-363">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="82f4a-364">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="82f4a-364">mailboxDisplayName</span></span>                        | <span data-ttu-id="82f4a-365">Beschikbaar als entityType het *Postvak*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-365">Available if entityType is *MailBox*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="82f4a-366">opmonsterset</span><span class="sxs-lookup"><span data-stu-id="82f4a-366">test User2</span></span>                                                                                                                                                                                                                                        |
| <span data-ttu-id="82f4a-367">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="82f4a-367">mailboxAddress</span></span>                            | <span data-ttu-id="82f4a-368">Beschikbaar als entityType de e-mail van het postvak van een *gebruiker*is / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="82f4a-368">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="82f4a-369">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="82f4a-369">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="82f4a-370">clusterBy</span><span class="sxs-lookup"><span data-stu-id="82f4a-370">clusterBy</span></span>                                 | <span data-ttu-id="82f4a-371">Beschikbaar als entityType een  *mailcluster*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-371">Available if entityType is  *MailCluster*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="82f4a-372">Onderwerp P2SenderDomain; Invoer</span><span class="sxs-lookup"><span data-stu-id="82f4a-372">Subject;P2SenderDomain;ContentType</span></span>                                                                                                                                                                                                                |
| <span data-ttu-id="82f4a-373">weet</span><span class="sxs-lookup"><span data-stu-id="82f4a-373">sender</span></span>                                    | <span data-ttu-id="82f4a-374">Beschikbaar als entityType de e-mail van het postvak van een *gebruiker*is / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="82f4a-374">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="82f4a-375">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="82f4a-375">user.abc@mail.contoso.co.in</span></span>                                                                                                                                                                 |
| <span data-ttu-id="82f4a-376">faxontvanger</span><span class="sxs-lookup"><span data-stu-id="82f4a-376">recipient</span></span>                                 | <span data-ttu-id="82f4a-377">Beschikbaar als entityType een *e-mailbericht*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-377">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="82f4a-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="82f4a-378">testUser2@contoso.com</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="82f4a-379">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="82f4a-379">subject</span></span>                                   | <span data-ttu-id="82f4a-380">Beschikbaar als entityType een *e-mailbericht*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-380">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="82f4a-381">\[EXTERNE \] aandacht</span><span class="sxs-lookup"><span data-stu-id="82f4a-381">\[EXTERNAL\] Attention</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="82f4a-382">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="82f4a-382">deliveryAction</span></span>                            | <span data-ttu-id="82f4a-383">Beschikbaar als entityType een *e-mailbericht*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-383">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="82f4a-384">Aflevering</span><span class="sxs-lookup"><span data-stu-id="82f4a-384">Delivered</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="82f4a-385">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="82f4a-385">securityGroupId</span></span>                           | <span data-ttu-id="82f4a-386">Beschikbaar als entityType  *SecurityGroup*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-386">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="82f4a-387">301c47c8-e15f-4059-AB09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="82f4a-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="82f4a-388">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="82f4a-388">securityGroupName</span></span>                         | <span data-ttu-id="82f4a-389">Beschikbaar als entityType  *SecurityGroup*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-389">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="82f4a-390">Netwerkconfiguratieoperators</span><span class="sxs-lookup"><span data-stu-id="82f4a-390">Network Configuration Operators</span></span>                                                                                                                                                                                                                   |
| <span data-ttu-id="82f4a-391">registryHive</span><span class="sxs-lookup"><span data-stu-id="82f4a-391">registryHive</span></span>                              | <span data-ttu-id="82f4a-392">Beschikbaar als entityType de  *registersleutel*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-392">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="82f4a-393">\_lokale \_ machine van HKEY</span><span class="sxs-lookup"><span data-stu-id="82f4a-393">HKEY\_LOCAL\_MACHINE</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="82f4a-394">registryKey</span><span class="sxs-lookup"><span data-stu-id="82f4a-394">registryKey</span></span>                               | <span data-ttu-id="82f4a-395">Beschikbaar als entityType de  *registersleutel*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-395">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="82f4a-396">SOFTWARE \\ \\ Microsoft \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon</span><span class="sxs-lookup"><span data-stu-id="82f4a-396">SOFTWARE\\\\Microsoft\\\\Windows NT\\\\CurrentVersion\\\\Winlogon</span></span>                                                                                                                                                                                 |
| <span data-ttu-id="82f4a-397">registryValueType</span><span class="sxs-lookup"><span data-stu-id="82f4a-397">registryValueType</span></span>                         | <span data-ttu-id="82f4a-398">Beschikbaar als entityType de  *registersleutel*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-398">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="82f4a-399">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="82f4a-399">String</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="82f4a-400">registryValue</span><span class="sxs-lookup"><span data-stu-id="82f4a-400">registryValue</span></span>                             | <span data-ttu-id="82f4a-401">Beschikbaar als entityType de  *registersleutel*is.</span><span class="sxs-lookup"><span data-stu-id="82f4a-401">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="82f4a-402">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="82f4a-402">31-00-00-00</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="82f4a-403">deviceId</span><span class="sxs-lookup"><span data-stu-id="82f4a-403">deviceId</span></span>                                  | <span data-ttu-id="82f4a-404">De ID, indien van toepassing, van het apparaat dat is gekoppeld aan de entiteit.</span><span class="sxs-lookup"><span data-stu-id="82f4a-404">The ID, if any, of the device related to the entity.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="82f4a-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="82f4a-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>                                                                                                                                                                                                          |



## <a name="example"></a><span data-ttu-id="82f4a-406">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="82f4a-406">Example</span></span>

<span data-ttu-id="82f4a-407">**Webonderdeelverzoek**</span><span class="sxs-lookup"><span data-stu-id="82f4a-407">**Request**</span></span>

```
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="82f4a-408">**Na**</span><span class="sxs-lookup"><span data-stu-id="82f4a-408">**Response**</span></span>
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

## <a name="related-topic"></a><span data-ttu-id="82f4a-409">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="82f4a-409">Related topic</span></span>
- [<span data-ttu-id="82f4a-410">API's voor incidenten</span><span class="sxs-lookup"><span data-stu-id="82f4a-410">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="82f4a-411">Incident bijwerken</span><span class="sxs-lookup"><span data-stu-id="82f4a-411">Update incident</span></span>](api-update-incidents.md)
