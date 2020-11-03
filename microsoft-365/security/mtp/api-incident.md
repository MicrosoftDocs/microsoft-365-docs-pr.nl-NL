---
title: Type incident bron in Microsoft 365 Defender API
description: Meer informatie over de methoden en eigenschappen van het type incident bron in Microsoft 365 Defender
keywords: incident, incidenten, API
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
ms.openlocfilehash: 68bee647cdd5687dbaad08ce3cd01b427dabf030
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844018"
---
# <a name="incident-resource-type"></a><span data-ttu-id="801b1-104">Brontype incident</span><span class="sxs-lookup"><span data-stu-id="801b1-104">Incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="801b1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="801b1-105">**Applies to:**</span></span>
- <span data-ttu-id="801b1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="801b1-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="801b1-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="801b1-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="801b1-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="801b1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="801b1-109">Methode</span><span class="sxs-lookup"><span data-stu-id="801b1-109">Methods</span></span>

<span data-ttu-id="801b1-110">Methode</span><span class="sxs-lookup"><span data-stu-id="801b1-110">Method</span></span> |<span data-ttu-id="801b1-111">Type resultaat</span><span class="sxs-lookup"><span data-stu-id="801b1-111">Return Type</span></span> |<span data-ttu-id="801b1-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="801b1-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="801b1-113">Lijst met incidenten</span><span class="sxs-lookup"><span data-stu-id="801b1-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="801b1-114">Lijst met [incidenten](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="801b1-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="801b1-115">Een lijst met incidenten weergeven.</span><span class="sxs-lookup"><span data-stu-id="801b1-115">Get a list of incidents.</span></span>
[<span data-ttu-id="801b1-116">Incident bijwerken</span><span class="sxs-lookup"><span data-stu-id="801b1-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="801b1-117">Voorval</span><span class="sxs-lookup"><span data-stu-id="801b1-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="801b1-118">Update specifiek incident.</span><span class="sxs-lookup"><span data-stu-id="801b1-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="801b1-119">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="801b1-119">Properties</span></span>

<span data-ttu-id="801b1-120">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="801b1-120">Property</span></span> |    <span data-ttu-id="801b1-121">Type</span><span class="sxs-lookup"><span data-stu-id="801b1-121">Type</span></span>    |    <span data-ttu-id="801b1-122">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="801b1-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="801b1-123">incidentId</span><span class="sxs-lookup"><span data-stu-id="801b1-123">incidentId</span></span> | <span data-ttu-id="801b1-124">lang</span><span class="sxs-lookup"><span data-stu-id="801b1-124">long</span></span> | <span data-ttu-id="801b1-125">Unieke ID van incident.</span><span class="sxs-lookup"><span data-stu-id="801b1-125">Incident unique ID.</span></span>
<span data-ttu-id="801b1-126">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="801b1-126">redirectIncidentId</span></span> | <span data-ttu-id="801b1-127">met nullen lang</span><span class="sxs-lookup"><span data-stu-id="801b1-127">nullable long</span></span> | <span data-ttu-id="801b1-128">De incident-ID waarmee het huidige incident is samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="801b1-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="801b1-129">voorval</span><span class="sxs-lookup"><span data-stu-id="801b1-129">incidentName</span></span> | <span data-ttu-id="801b1-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="801b1-130">string</span></span> | <span data-ttu-id="801b1-131">De naam van het incident.</span><span class="sxs-lookup"><span data-stu-id="801b1-131">The name of the Incident.</span></span>
<span data-ttu-id="801b1-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="801b1-132">createdTime</span></span> | <span data-ttu-id="801b1-133">Offset</span><span class="sxs-lookup"><span data-stu-id="801b1-133">DateTimeOffset</span></span> | <span data-ttu-id="801b1-134">De datum en tijd (in UTC) waarop het incident is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="801b1-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="801b1-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="801b1-135">lastUpdateTime</span></span> | <span data-ttu-id="801b1-136">Offset</span><span class="sxs-lookup"><span data-stu-id="801b1-136">DateTimeOffset</span></span> | <span data-ttu-id="801b1-137">De datum en tijd (in UTC) waarop het incident voor het laatst is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="801b1-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="801b1-138">ToegewezenAan</span><span class="sxs-lookup"><span data-stu-id="801b1-138">assignedTo</span></span> | <span data-ttu-id="801b1-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="801b1-139">string</span></span> | <span data-ttu-id="801b1-140">Eigenaar van het incident.</span><span class="sxs-lookup"><span data-stu-id="801b1-140">Owner of the Incident.</span></span>
<span data-ttu-id="801b1-141">Ernst</span><span class="sxs-lookup"><span data-stu-id="801b1-141">severity</span></span> | <span data-ttu-id="801b1-142">Opsommings</span><span class="sxs-lookup"><span data-stu-id="801b1-142">Enum</span></span> | <span data-ttu-id="801b1-143">Ernst van het incident.</span><span class="sxs-lookup"><span data-stu-id="801b1-143">Severity of the Incident.</span></span> <span data-ttu-id="801b1-144">Mogelijke waarden zijn: ```UnSpecified``` , ```Informational``` , ```Low``` ```Medium``` en ```High``` .</span><span class="sxs-lookup"><span data-stu-id="801b1-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="801b1-145">status</span><span class="sxs-lookup"><span data-stu-id="801b1-145">status</span></span> | <span data-ttu-id="801b1-146">Opsommings</span><span class="sxs-lookup"><span data-stu-id="801b1-146">Enum</span></span> | <span data-ttu-id="801b1-147">Geeft de huidige status van het incident aan.</span><span class="sxs-lookup"><span data-stu-id="801b1-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="801b1-148">Mogelijke waarden zijn: ```Active``` , ```Resolved``` en ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="801b1-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="801b1-149">Contactpersoonclassificatie</span><span class="sxs-lookup"><span data-stu-id="801b1-149">classification</span></span> | <span data-ttu-id="801b1-150">Opsommings</span><span class="sxs-lookup"><span data-stu-id="801b1-150">Enum</span></span> | <span data-ttu-id="801b1-151">Specificatie van het incident.</span><span class="sxs-lookup"><span data-stu-id="801b1-151">Specification of the incident.</span></span> <span data-ttu-id="801b1-152">Mogelijke waarden zijn: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="801b1-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="801b1-153">relevant</span><span class="sxs-lookup"><span data-stu-id="801b1-153">determination</span></span> | <span data-ttu-id="801b1-154">Opsommings</span><span class="sxs-lookup"><span data-stu-id="801b1-154">Enum</span></span> | <span data-ttu-id="801b1-155">Hiermee wordt het bepalen van het incident aangegeven.</span><span class="sxs-lookup"><span data-stu-id="801b1-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="801b1-156">Mogelijke waarden zijn: ```NotAvailable``` , ```Apt``` ,,, ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="801b1-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="801b1-157">Tags</span><span class="sxs-lookup"><span data-stu-id="801b1-157">tags</span></span> | <span data-ttu-id="801b1-158">Lijst met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="801b1-158">string List</span></span> | <span data-ttu-id="801b1-159">Lijst met incident Tags.</span><span class="sxs-lookup"><span data-stu-id="801b1-159">List of Incident tags.</span></span>
<span data-ttu-id="801b1-160">kennisgeving</span><span class="sxs-lookup"><span data-stu-id="801b1-160">alerts</span></span> | <span data-ttu-id="801b1-161">Lijst met waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="801b1-161">Alert List</span></span> | <span data-ttu-id="801b1-162">Lijst met verwante meldingen.</span><span class="sxs-lookup"><span data-stu-id="801b1-162">List of related alerts.</span></span> <span data-ttu-id="801b1-163">Zie voorbeelden in API-documentatie voor [lijst incidenten](api-list-incidents.md) .</span><span class="sxs-lookup"><span data-stu-id="801b1-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>
