---
title: Incidenten beheren in Microsoft Threat Protection
description: Meer informatie over het toewijzen, bijwerken van de status,
keywords: incident, incidenten, waarschuwingen, gecorreleerde waarschuwingen, toewijzen, bijwerken, status, beheren, classificatie, Microsoft, 365, m365
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
ms.openlocfilehash: f711cc2ff38f15dfd22097e37a1dec42719eb5aa
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148112"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="5fa60-104">Incidenten beheren in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5fa60-104">Manage incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="5fa60-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5fa60-105">**Applies to:**</span></span>
- <span data-ttu-id="5fa60-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5fa60-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="5fa60-107">Het beheren van incidenten is essentieel om ervoor te zorgen dat bedreigingen worden beperkt en aangepakt.</span><span class="sxs-lookup"><span data-stu-id="5fa60-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="5fa60-108">In Microsoft Threat Protection hebt u toegang tot het beheren van incidenten op apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="5fa60-108">In Microsoft Threat Protection, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="5fa60-109">U incidenten beheren door een incident te selecteren in de **wachtrij Incidenten**.</span><span class="sxs-lookup"><span data-stu-id="5fa60-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="5fa60-110">U de naam van een incident bewerken, oplossen, de classificatie en bepaling instellen.</span><span class="sxs-lookup"><span data-stu-id="5fa60-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="5fa60-111">U het incident ook aan uzelf toewijzen, incidenttags en opmerkingen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="5fa60-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="5fa60-112">In gevallen waarin u tijdens het onderzoek waarschuwingen van het ene incident naar het andere wilt verplaatsen, u dit ook doen vanaf het tabblad Waarschuwingen, waardoor een groter of kleiner incident ontstaat dat alle relevante waarschuwingen bevat.</span><span class="sxs-lookup"><span data-stu-id="5fa60-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="5fa60-113">Incidentnaam bewerken</span><span class="sxs-lookup"><span data-stu-id="5fa60-113">Edit incident name</span></span>
<span data-ttu-id="5fa60-114">Standaard krijgt een incident een getal toegewezen.</span><span class="sxs-lookup"><span data-stu-id="5fa60-114">By default, an incident is assigned a number.</span></span> <span data-ttu-id="5fa60-115">U de naam van het incident wijzigen om beter af te stemmen op uw voorkeursnaamgevingsconventie.</span><span class="sxs-lookup"><span data-stu-id="5fa60-115">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!TIP]
> <span data-ttu-id="5fa60-116">Voor extra zichtbaarheid in één oogopslag genereert automatische incidentnaamgeving, die momenteel in openbare preview is, incidentnamen op basis van waarschuwingskenmerken, zoals het aantal getroffen eindpunten, de getroffen gebruikers, detectiebronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="5fa60-116">For additional visibility at-a-glance, automatic incident naming, currently in public preview, generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="5fa60-117">Hierdoor u snel inzicht krijgen in de omvang van het incident.</span><span class="sxs-lookup"><span data-stu-id="5fa60-117">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="5fa60-118">Bijvoorbeeld: *Multi-stage incident op meerdere eindpunten gerapporteerd door meerdere bronnen.*</span><span class="sxs-lookup"><span data-stu-id="5fa60-118">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="5fa60-119">Incidenten die vóór de uitrol van automatische incidentnaamgeving bestonden, worden niet gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="5fa60-119">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>
>
> <span data-ttu-id="5fa60-120">Meer informatie over [het inschakelen van voorbeeldfuncties](preview.md#turn-on-preview-features).</span><span class="sxs-lookup"><span data-stu-id="5fa60-120">Learn more about [turning on preview features](preview.md#turn-on-preview-features).</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="5fa60-121">Incidenten toewijzen</span><span class="sxs-lookup"><span data-stu-id="5fa60-121">Assign incidents</span></span>
<span data-ttu-id="5fa60-122">Als er nog geen incident is toegewezen, u **Toewijzen aan mij** selecteren om het incident aan uzelf toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="5fa60-122">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="5fa60-123">Daarbij neemt eigendom van niet alleen het incident, maar ook alle waarschuwingen in verband met het.</span><span class="sxs-lookup"><span data-stu-id="5fa60-123">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="5fa60-124">Status en classificatie instellen</span><span class="sxs-lookup"><span data-stu-id="5fa60-124">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="5fa60-125">Incidentstatus</span><span class="sxs-lookup"><span data-stu-id="5fa60-125">Incident status</span></span>
<span data-ttu-id="5fa60-126">U incidenten categoriseren (als **Actief**of **Opgelost)** door hun status te wijzigen naarmate uw onderzoek vordert.</span><span class="sxs-lookup"><span data-stu-id="5fa60-126">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="5fa60-127">Zo u organiseren en beheren hoe uw team kan reageren op incidenten.</span><span class="sxs-lookup"><span data-stu-id="5fa60-127">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="5fa60-128">Uw SOC-analist kan bijvoorbeeld de urgente **Actieve** incidenten voor de dag bekijken en besluiten deze aan zichzelf toe te wijzen voor onderzoek.</span><span class="sxs-lookup"><span data-stu-id="5fa60-128">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="5fa60-129">Als alternatief kan uw SOC-analist het incident instellen als **Opgelost** als het incident is verholpen.</span><span class="sxs-lookup"><span data-stu-id="5fa60-129">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="5fa60-130">Als u een incident op lost, worden automatisch alle waarschuwingen gesloten die deel uitmaken van het incident en nog steeds worden geopend.</span><span class="sxs-lookup"><span data-stu-id="5fa60-130">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="5fa60-131">Indeling en bepaling</span><span class="sxs-lookup"><span data-stu-id="5fa60-131">Classification and determination</span></span>
<span data-ttu-id="5fa60-132">U ervoor kiezen om geen classificatie in te stellen of te beslissen om aan te geven of een incident waar of onwaar is.</span><span class="sxs-lookup"><span data-stu-id="5fa60-132">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="5fa60-133">Hierdoor helpt het team patronen te zien en ervan te leren.</span><span class="sxs-lookup"><span data-stu-id="5fa60-133">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="5fa60-134">Opmerkingen toevoegen</span><span class="sxs-lookup"><span data-stu-id="5fa60-134">Add comments</span></span>
<span data-ttu-id="5fa60-135">U opmerkingen toevoegen en historische gebeurtenissen over een incident bekijken om eerdere wijzigingen te zien.</span><span class="sxs-lookup"><span data-stu-id="5fa60-135">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="5fa60-136">Wanneer een wijziging of opmerking wordt aangebracht in een waarschuwing, wordt deze opgenomen in de sectie Opmerkingen en geschiedenis.</span><span class="sxs-lookup"><span data-stu-id="5fa60-136">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="5fa60-137">Toegevoegde opmerkingen verschijnen direct in het deelvenster.</span><span class="sxs-lookup"><span data-stu-id="5fa60-137">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="5fa60-138">Incidenttags toevoegen</span><span class="sxs-lookup"><span data-stu-id="5fa60-138">Add incident tags</span></span>
<span data-ttu-id="5fa60-139">U aangepaste tags toevoegen aan een incident, bijvoorbeeld om een groep incidenten met een gemeenschappelijke kenmerken te markeren.</span><span class="sxs-lookup"><span data-stu-id="5fa60-139">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="5fa60-140">U later de wachtrij voor incidenten filteren op alle incidenten die een specifieke tag bevatten.</span><span class="sxs-lookup"><span data-stu-id="5fa60-140">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>