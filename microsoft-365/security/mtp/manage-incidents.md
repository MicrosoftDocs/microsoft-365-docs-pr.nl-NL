---
title: Incidenten beheren in Microsoft Threat Protection
description: Meer informatie over toewijzen, bijwerken van de status,
keywords: incidenten, waarschuwingen, gecorreleerde waarschuwingen, toewijzen, bijwerken, status, beheren, classificeren, microsoft, 365, m365
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
ms.openlocfilehash: b8f7e3bbb6d2348c3f19e8df251d700d8adf8e33
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807338"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="e6d03-104">Incidenten beheren in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e6d03-104">Manage incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="e6d03-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e6d03-105">**Applies to:**</span></span>
- <span data-ttu-id="e6d03-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="e6d03-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="e6d03-107">Het beheren van incidenten is van cruciaal belang om ervoor te zorgen dat bedreigingen worden ingeperkt en aangepakt.</span><span class="sxs-lookup"><span data-stu-id="e6d03-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="e6d03-108">In Microsoft Threat Protection hebt u toegang tot het beheren van incidenten op apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="e6d03-108">In Microsoft Threat Protection, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="e6d03-109">U incidenten beheren door een incident te selecteren in de **wachtrij Incidenten.**</span><span class="sxs-lookup"><span data-stu-id="e6d03-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="e6d03-110">U de naam van een incident bewerken, oplossen, de classificatie en bepaling ervan instellen.</span><span class="sxs-lookup"><span data-stu-id="e6d03-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="e6d03-111">U het incident ook aan uzelf toewijzen, incidenttags en opmerkingen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="e6d03-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="e6d03-112">In gevallen waarin u tijdens het onderzoek waarschuwingen van het ene incident naar het andere wilt verplaatsen, u dit ook doen vanaf het tabblad Waarschuwingen, waardoor een groter of kleiner incident ontstaat dat alle relevante waarschuwingen bevat.</span><span class="sxs-lookup"><span data-stu-id="e6d03-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="e6d03-113">De naam van incidenten bewerken</span><span class="sxs-lookup"><span data-stu-id="e6d03-113">Edit incident name</span></span>
<span data-ttu-id="e6d03-114">Standaard krijgt een incident een nummer toegewezen.</span><span class="sxs-lookup"><span data-stu-id="e6d03-114">By default, an incident is assigned a number.</span></span> <span data-ttu-id="e6d03-115">U de naam van het incident wijzigen om beter af te stemmen op uw voorkeursnaamgevingsconventie.</span><span class="sxs-lookup"><span data-stu-id="e6d03-115">You can modify the incident name to better align with your preferred naming convention.</span></span>
 
## <a name="assign-incidents"></a><span data-ttu-id="e6d03-116">Incidenten toewijzen</span><span class="sxs-lookup"><span data-stu-id="e6d03-116">Assign incidents</span></span>
<span data-ttu-id="e6d03-117">Als een incident nog niet is toegewezen, u **Toewijzen aan mij** selecteren om het incident aan uzelf toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="e6d03-117">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="e6d03-118">Daarbij neemt de eigendom van niet alleen het incident, maar ook alle waarschuwingen in verband met het.</span><span class="sxs-lookup"><span data-stu-id="e6d03-118">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="e6d03-119">Status en classificatie instellen</span><span class="sxs-lookup"><span data-stu-id="e6d03-119">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="e6d03-120">Incidentstatus</span><span class="sxs-lookup"><span data-stu-id="e6d03-120">Incident status</span></span>
<span data-ttu-id="e6d03-121">U incidenten (als **Actief**of **Opgelost) categoriseren**door hun status te wijzigen naarmate uw onderzoek vordert.</span><span class="sxs-lookup"><span data-stu-id="e6d03-121">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="e6d03-122">Zo u organiseren en beheren hoe uw team kan reageren op incidenten.</span><span class="sxs-lookup"><span data-stu-id="e6d03-122">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="e6d03-123">Uw SOC-analist kan bijvoorbeeld de dringende **Actieve** incidenten voor de dag bekijken en besluiten deze aan zichzelf toe te wijzen voor onderzoek.</span><span class="sxs-lookup"><span data-stu-id="e6d03-123">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="e6d03-124">Als u ook uw SOC-analist het incident als **opgelost** als het incident is verholpen.</span><span class="sxs-lookup"><span data-stu-id="e6d03-124">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="e6d03-125">Als u een incident oplost, worden automatisch alle waarschuwingen gesloten die deel uitmaken van het incident en nog steeds worden geopend.</span><span class="sxs-lookup"><span data-stu-id="e6d03-125">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="e6d03-126">Indeling en bepaling</span><span class="sxs-lookup"><span data-stu-id="e6d03-126">Classification and determination</span></span>
<span data-ttu-id="e6d03-127">U ervoor kiezen om geen classificatie in te stellen of om aan te geven of een incident waar of onwaar is.</span><span class="sxs-lookup"><span data-stu-id="e6d03-127">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="e6d03-128">Hierdoor kan het team patronen zien en ervan leren.</span><span class="sxs-lookup"><span data-stu-id="e6d03-128">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="e6d03-129">Opmerkingen toevoegen</span><span class="sxs-lookup"><span data-stu-id="e6d03-129">Add comments</span></span>
<span data-ttu-id="e6d03-130">U opmerkingen toevoegen en historische gebeurtenissen over een incident weergeven om eerdere wijzigingen in het incident te bekijken.</span><span class="sxs-lookup"><span data-stu-id="e6d03-130">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="e6d03-131">Wanneer een wijziging of opmerking wordt gemaakt in een waarschuwing, wordt deze opgenomen in de sectie Opmerkingen en geschiedenis.</span><span class="sxs-lookup"><span data-stu-id="e6d03-131">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="e6d03-132">Toegevoegde opmerkingen verschijnen direct in het deelvenster.</span><span class="sxs-lookup"><span data-stu-id="e6d03-132">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="e6d03-133">Incidenttags toevoegen</span><span class="sxs-lookup"><span data-stu-id="e6d03-133">Add incident tags</span></span>
<span data-ttu-id="e6d03-134">U aangepaste tags toevoegen aan een incident, bijvoorbeeld om een groep incidenten met een gemeenschappelijke kenmerken te markeren.</span><span class="sxs-lookup"><span data-stu-id="e6d03-134">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="e6d03-135">U later de wachtrij voor incidenten filteren voor alle incidenten die een specifieke tag bevatten.</span><span class="sxs-lookup"><span data-stu-id="e6d03-135">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>

