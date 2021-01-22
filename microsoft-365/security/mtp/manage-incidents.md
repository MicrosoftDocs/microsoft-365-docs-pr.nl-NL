---
title: Incidenten beheren in Microsoft 365 Defender
description: Informatie over het toewijzen, bijwerken van de status,
keywords: incident, incidenten, waarschuwingen, correleren waarschuwingen, toewijzen, bijwerken, status, beheren, classificatie, microsoft, 365, m365
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 90d9d397b8baf0ffdb9844a0f068f142a5c7fd48
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930628"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="f2015-104">Incidenten beheren in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2015-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f2015-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f2015-105">**Applies to:**</span></span>
- <span data-ttu-id="f2015-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2015-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="f2015-107">Het beheren van incidenten is essentieel om ervoor te zorgen dat bedreigingen worden opgenomen en aangepakt.</span><span class="sxs-lookup"><span data-stu-id="f2015-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="f2015-108">In Microsoft 365 Defender hebt u toegang tot het beheren van incidenten op apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="f2015-108">In Microsoft 365 Defender, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="f2015-109">U kunt incidenten beheren door een incident te selecteren in de **wachtrij Incidenten.**</span><span class="sxs-lookup"><span data-stu-id="f2015-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="f2015-110">U kunt de naam van een incident bewerken, deze oplossen en de classificatie en bepalingen bepalen.</span><span class="sxs-lookup"><span data-stu-id="f2015-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="f2015-111">U kunt het incident ook aan uzelf toewijzen en incidentlabels en opmerkingen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="f2015-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="f2015-112">In gevallen waarin u tijdens het onderzoeken waarschuwingen tussen twee incidenten wilt verplaatsen, kunt u dit ook doen vanaf het tabblad Waarschuwingen, waardoor een groter of kleiner incident wordt gemaakt dat alle relevante waarschuwingen bevat.</span><span class="sxs-lookup"><span data-stu-id="f2015-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="f2015-113">Naam van incident bewerken</span><span class="sxs-lookup"><span data-stu-id="f2015-113">Edit incident name</span></span>
<span data-ttu-id="f2015-114">Incidenten krijgen automatisch een naam toegewezen op basis van waarschuwingskenmerken, zoals het aantal beïnvloede eindpunten, betrokken gebruikers, detectiebronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="f2015-114">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="f2015-115">Op deze manier kunt u snel de omvang van het incident begrijpen.</span><span class="sxs-lookup"><span data-stu-id="f2015-115">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="f2015-116">Bijvoorbeeld: *Incident met meerdere stadiums voor meerdere eindpunten gerapporteerd door meerdere bronnen.*</span><span class="sxs-lookup"><span data-stu-id="f2015-116">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="f2015-117">U kunt de naam van het incident aanpassen om deze beter aan te passen aan de naamconventie van uw voorkeur.</span><span class="sxs-lookup"><span data-stu-id="f2015-117">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!NOTE]
> <span data-ttu-id="f2015-118">Incidenten die bestond vóór de implementatie van de functie voor automatische naamgeving van incidenten behouden hun naam.</span><span class="sxs-lookup"><span data-stu-id="f2015-118">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>



## <a name="assign-incidents"></a><span data-ttu-id="f2015-119">Incidenten toewijzen</span><span class="sxs-lookup"><span data-stu-id="f2015-119">Assign incidents</span></span>
<span data-ttu-id="f2015-120">Als een incident nog niet is toegewezen, kunt u Aan mij toewijzen selecteren om **het** incident aan uzelf toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="f2015-120">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="f2015-121">Als u dit doet, wordt ervan uit gegaan dat u niet alleen eigenaar bent van het incident, maar ook van alle waarschuwingen die aan het incident zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="f2015-121">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="f2015-122">Status en classificatie instellen</span><span class="sxs-lookup"><span data-stu-id="f2015-122">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="f2015-123">Incidentstatus</span><span class="sxs-lookup"><span data-stu-id="f2015-123">Incident status</span></span>
<span data-ttu-id="f2015-124">U kunt incidenten categoriseren (als **Actief** of **Opgelost)** door de status te wijzigen naarmate het onderzoek vordert.</span><span class="sxs-lookup"><span data-stu-id="f2015-124">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="f2015-125">Zo kunt u organiseren en beheren hoe uw team op incidenten kan reageren.</span><span class="sxs-lookup"><span data-stu-id="f2015-125">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="f2015-126">Uw SOC-analist kan bijvoorbeeld  de urgent actieve incidenten voor die dag beoordelen en deze toewijzen voor onderzoek.</span><span class="sxs-lookup"><span data-stu-id="f2015-126">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="f2015-127">Uw SOC-analist kan het  incident ook instellen als Opgelost als het incident is opgelost.</span><span class="sxs-lookup"><span data-stu-id="f2015-127">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="f2015-128">Door een incident op te lossen, worden automatisch alle waarschuwingen gesloten die deel uitmaken van het incident en nog steeds zijn geopend.</span><span class="sxs-lookup"><span data-stu-id="f2015-128">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="f2015-129">Classificatie en bepalingen</span><span class="sxs-lookup"><span data-stu-id="f2015-129">Classification and determination</span></span>
<span data-ttu-id="f2015-130">U kunt ervoor kiezen geen classificatie in te stellen of te bepalen of een incident waar of onwaar is.</span><span class="sxs-lookup"><span data-stu-id="f2015-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="f2015-131">Hierdoor kan het team patronen zien en van deze patronen leren.</span><span class="sxs-lookup"><span data-stu-id="f2015-131">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="f2015-132">Opmerkingen toevoegen</span><span class="sxs-lookup"><span data-stu-id="f2015-132">Add comments</span></span>
<span data-ttu-id="f2015-133">U kunt opmerkingen toevoegen en historische gebeurtenissen over een incident bekijken om eerdere wijzigingen in het incident te bekijken.</span><span class="sxs-lookup"><span data-stu-id="f2015-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="f2015-134">Wanneer een wijziging of opmerking wordt aangebracht in een waarschuwing, wordt deze vastgelegd in de sectie Opmerkingen en geschiedenis.</span><span class="sxs-lookup"><span data-stu-id="f2015-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="f2015-135">Toegevoegde opmerkingen worden direct weergegeven in het deelvenster.</span><span class="sxs-lookup"><span data-stu-id="f2015-135">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="f2015-136">Incidentlabels toevoegen</span><span class="sxs-lookup"><span data-stu-id="f2015-136">Add incident tags</span></span>
<span data-ttu-id="f2015-137">U kunt aangepaste tags toevoegen aan een incident, bijvoorbeeld om een groep incidenten met gemeenschappelijke kenmerken te markeren.</span><span class="sxs-lookup"><span data-stu-id="f2015-137">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="f2015-138">U kunt de wachtrij met incidenten later filteren op alle incidenten die een specifieke tag bevatten.</span><span class="sxs-lookup"><span data-stu-id="f2015-138">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>
