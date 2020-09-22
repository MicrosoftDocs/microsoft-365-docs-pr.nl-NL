---
title: Brontype voor incidenten in Microsoft Threat Protection API
description: Meer informatie over de methoden en eigenschappen van het brontype incident in Microsoft Threat Protection
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
ms.openlocfilehash: ac149ca7263b8ef8bb37a7dd18bf0787a3114b37
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201301"
---
# <a name="incident-resource-type"></a><span data-ttu-id="7167d-104">Brontype incident</span><span class="sxs-lookup"><span data-stu-id="7167d-104">Incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7167d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7167d-105">**Applies to:**</span></span>
- <span data-ttu-id="7167d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7167d-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="7167d-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="7167d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7167d-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="7167d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="7167d-109">Methode</span><span class="sxs-lookup"><span data-stu-id="7167d-109">Methods</span></span>

<span data-ttu-id="7167d-110">Methode</span><span class="sxs-lookup"><span data-stu-id="7167d-110">Method</span></span> |<span data-ttu-id="7167d-111">Type resultaat</span><span class="sxs-lookup"><span data-stu-id="7167d-111">Return Type</span></span> |<span data-ttu-id="7167d-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="7167d-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="7167d-113">Lijst met incidenten</span><span class="sxs-lookup"><span data-stu-id="7167d-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="7167d-114">Lijst met [incidenten](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="7167d-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="7167d-115">Een lijst met incidenten weergeven.</span><span class="sxs-lookup"><span data-stu-id="7167d-115">Get a list of incidents.</span></span>
[<span data-ttu-id="7167d-116">Incident bijwerken</span><span class="sxs-lookup"><span data-stu-id="7167d-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="7167d-117">Voorval</span><span class="sxs-lookup"><span data-stu-id="7167d-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="7167d-118">Update specifiek incident.</span><span class="sxs-lookup"><span data-stu-id="7167d-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="7167d-119">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="7167d-119">Properties</span></span>

<span data-ttu-id="7167d-120">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="7167d-120">Property</span></span> |    <span data-ttu-id="7167d-121">Type</span><span class="sxs-lookup"><span data-stu-id="7167d-121">Type</span></span>    |    <span data-ttu-id="7167d-122">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="7167d-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="7167d-123">incidentId</span><span class="sxs-lookup"><span data-stu-id="7167d-123">incidentId</span></span> | <span data-ttu-id="7167d-124">lang</span><span class="sxs-lookup"><span data-stu-id="7167d-124">long</span></span> | <span data-ttu-id="7167d-125">Unieke ID van incident.</span><span class="sxs-lookup"><span data-stu-id="7167d-125">Incident unique ID.</span></span>
<span data-ttu-id="7167d-126">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="7167d-126">redirectIncidentId</span></span> | <span data-ttu-id="7167d-127">met nullen lang</span><span class="sxs-lookup"><span data-stu-id="7167d-127">nullable long</span></span> | <span data-ttu-id="7167d-128">De incident-ID waarmee het huidige incident is samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="7167d-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="7167d-129">voorval</span><span class="sxs-lookup"><span data-stu-id="7167d-129">incidentName</span></span> | <span data-ttu-id="7167d-130">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7167d-130">string</span></span> | <span data-ttu-id="7167d-131">De naam van het incident.</span><span class="sxs-lookup"><span data-stu-id="7167d-131">The name of the Incident.</span></span>
<span data-ttu-id="7167d-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="7167d-132">createdTime</span></span> | <span data-ttu-id="7167d-133">Offset</span><span class="sxs-lookup"><span data-stu-id="7167d-133">DateTimeOffset</span></span> | <span data-ttu-id="7167d-134">De datum en tijd (in UTC) waarop het incident is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="7167d-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="7167d-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="7167d-135">lastUpdateTime</span></span> | <span data-ttu-id="7167d-136">Offset</span><span class="sxs-lookup"><span data-stu-id="7167d-136">DateTimeOffset</span></span> | <span data-ttu-id="7167d-137">De datum en tijd (in UTC) waarop het incident voor het laatst is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="7167d-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="7167d-138">ToegewezenAan</span><span class="sxs-lookup"><span data-stu-id="7167d-138">assignedTo</span></span> | <span data-ttu-id="7167d-139">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="7167d-139">string</span></span> | <span data-ttu-id="7167d-140">Eigenaar van het incident.</span><span class="sxs-lookup"><span data-stu-id="7167d-140">Owner of the Incident.</span></span>
<span data-ttu-id="7167d-141">Ernst</span><span class="sxs-lookup"><span data-stu-id="7167d-141">severity</span></span> | <span data-ttu-id="7167d-142">Opsommings</span><span class="sxs-lookup"><span data-stu-id="7167d-142">Enum</span></span> | <span data-ttu-id="7167d-143">Ernst van het incident.</span><span class="sxs-lookup"><span data-stu-id="7167d-143">Severity of the Incident.</span></span> <span data-ttu-id="7167d-144">Mogelijke waarden zijn: ```UnSpecified``` , ```Informational``` , ```Low``` ```Medium``` en ```High``` .</span><span class="sxs-lookup"><span data-stu-id="7167d-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="7167d-145">status</span><span class="sxs-lookup"><span data-stu-id="7167d-145">status</span></span> | <span data-ttu-id="7167d-146">Opsommings</span><span class="sxs-lookup"><span data-stu-id="7167d-146">Enum</span></span> | <span data-ttu-id="7167d-147">Geeft de huidige status van het incident aan.</span><span class="sxs-lookup"><span data-stu-id="7167d-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="7167d-148">Mogelijke waarden zijn: ```Active``` , ```Resolved``` en ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="7167d-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="7167d-149">Contactpersoonclassificatie</span><span class="sxs-lookup"><span data-stu-id="7167d-149">classification</span></span> | <span data-ttu-id="7167d-150">Opsommings</span><span class="sxs-lookup"><span data-stu-id="7167d-150">Enum</span></span> | <span data-ttu-id="7167d-151">Specificatie van het incident.</span><span class="sxs-lookup"><span data-stu-id="7167d-151">Specification of the incident.</span></span> <span data-ttu-id="7167d-152">Mogelijke waarden zijn: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="7167d-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="7167d-153">relevant</span><span class="sxs-lookup"><span data-stu-id="7167d-153">determination</span></span> | <span data-ttu-id="7167d-154">Opsommings</span><span class="sxs-lookup"><span data-stu-id="7167d-154">Enum</span></span> | <span data-ttu-id="7167d-155">Hiermee wordt het bepalen van het incident aangegeven.</span><span class="sxs-lookup"><span data-stu-id="7167d-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="7167d-156">Mogelijke waarden zijn: ```NotAvailable``` , ```Apt``` ,,, ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="7167d-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="7167d-157">Tags</span><span class="sxs-lookup"><span data-stu-id="7167d-157">tags</span></span> | <span data-ttu-id="7167d-158">Lijst met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="7167d-158">string List</span></span> | <span data-ttu-id="7167d-159">Lijst met incident Tags.</span><span class="sxs-lookup"><span data-stu-id="7167d-159">List of Incident tags.</span></span>
<span data-ttu-id="7167d-160">kennisgeving</span><span class="sxs-lookup"><span data-stu-id="7167d-160">alerts</span></span> | <span data-ttu-id="7167d-161">Lijst met waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="7167d-161">Alert List</span></span> | <span data-ttu-id="7167d-162">Lijst met verwante meldingen.</span><span class="sxs-lookup"><span data-stu-id="7167d-162">List of related alerts.</span></span> <span data-ttu-id="7167d-163">Zie voorbeelden in API-documentatie voor [lijst incidenten](api-list-incidents.md) .</span><span class="sxs-lookup"><span data-stu-id="7167d-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>
