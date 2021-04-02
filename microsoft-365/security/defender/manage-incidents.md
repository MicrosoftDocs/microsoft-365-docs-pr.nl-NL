---
title: Incidenten beheren in Microsoft 365 Defender
description: Informatie over het toewijzen, bijwerken van de status,
keywords: incident, incidenten, waarschuwingen, gecorreleerde waarschuwingen, toewijzen, bijwerken, status, beheren, classificatie, microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: 72d368cd92739e191dcb292000b8429a472aa981
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498438"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="88d9d-104">Incidenten beheren in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88d9d-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="88d9d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="88d9d-105">**Applies to:**</span></span>
- <span data-ttu-id="88d9d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88d9d-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="88d9d-107">Het beheren van incidenten is essentieel om ervoor te zorgen dat bedreigingen worden opgenomen en aangepakt.</span><span class="sxs-lookup"><span data-stu-id="88d9d-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="88d9d-108">In Microsoft 365 Defender hebt u toegang tot het beheren van incidenten op apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="88d9d-108">In Microsoft 365 Defender, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="88d9d-109">U kunt incidenten beheren door een incident te selecteren in de **wachtrij Incidenten.**</span><span class="sxs-lookup"><span data-stu-id="88d9d-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="88d9d-110">U kunt de naam van een incident bewerken, oplossen, de classificatie en bepaling ervan instellen.</span><span class="sxs-lookup"><span data-stu-id="88d9d-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="88d9d-111">U kunt het incident ook aan uzelf toewijzen, incidentlabels en opmerkingen toevoegen.</span><span class="sxs-lookup"><span data-stu-id="88d9d-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="88d9d-112">In gevallen waarin u tijdens het onderzoeken waarschuwingen van het ene incident naar het andere wilt verplaatsen, kunt u dit ook doen via het tabblad Waarschuwingen, waardoor een groter of kleiner incident wordt gemaakt met alle relevante waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="88d9d-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="88d9d-113">Naam van incident bewerken</span><span class="sxs-lookup"><span data-stu-id="88d9d-113">Edit incident name</span></span>
<span data-ttu-id="88d9d-114">Incidenten krijgen automatisch een naam toegewezen op basis van waarschuwingskenmerken, zoals het aantal betrokken eindpunten, beïnvloede gebruikers, detectiebronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="88d9d-114">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="88d9d-115">Hierdoor kunt u snel inzicht krijgen in het bereik van het incident.</span><span class="sxs-lookup"><span data-stu-id="88d9d-115">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="88d9d-116">Bijvoorbeeld: *incident met meerdere fases op meerdere eindpunten die door meerdere bronnen zijn gerapporteerd.*</span><span class="sxs-lookup"><span data-stu-id="88d9d-116">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="88d9d-117">U kunt de naam van het incident wijzigen om beter af te stemmen op de naamgevingsconventie van uw voorkeur.</span><span class="sxs-lookup"><span data-stu-id="88d9d-117">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!NOTE]
> <span data-ttu-id="88d9d-118">Incidenten die vóór de implementatie van de functie voor automatische naamgeving van incidenten hebben bestaan, behouden hun naam.</span><span class="sxs-lookup"><span data-stu-id="88d9d-118">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>



## <a name="assign-incidents"></a><span data-ttu-id="88d9d-119">Incidenten toewijzen</span><span class="sxs-lookup"><span data-stu-id="88d9d-119">Assign incidents</span></span>
<span data-ttu-id="88d9d-120">Als er nog geen incident is toegewezen, kunt u Toewijzen aan **mij** selecteren om het incident aan uzelf toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="88d9d-120">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="88d9d-121">Als u dit doet, wordt ervan uit gegaan dat u niet alleen eigenaar bent van het incident, maar ook van alle waarschuwingen die aan het incident zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="88d9d-121">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="88d9d-122">Status en classificatie instellen</span><span class="sxs-lookup"><span data-stu-id="88d9d-122">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="88d9d-123">Incidentstatus</span><span class="sxs-lookup"><span data-stu-id="88d9d-123">Incident status</span></span>
<span data-ttu-id="88d9d-124">U kunt incidenten categoriseren (als **Actief** of **Opgelost)** door hun status te wijzigen naarmate het onderzoek vordert.</span><span class="sxs-lookup"><span data-stu-id="88d9d-124">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="88d9d-125">Op deze manier kunt u organiseren en beheren hoe uw team kan reageren op incidenten.</span><span class="sxs-lookup"><span data-stu-id="88d9d-125">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="88d9d-126">Uw SOC-analist kan bijvoorbeeld de **urgente** Actieve incidenten van vandaag bekijken en besluiten deze aan zichzelf toe te wijzen voor onderzoek.</span><span class="sxs-lookup"><span data-stu-id="88d9d-126">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="88d9d-127">Uw SOC-analist kan het incident ook instellen als **Opgelost** als het incident is opgelost.</span><span class="sxs-lookup"><span data-stu-id="88d9d-127">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="88d9d-128">Door een incident op te lossen, worden automatisch alle waarschuwingen gesloten die deel uitmaken van het incident en worden ze nog steeds geopend.</span><span class="sxs-lookup"><span data-stu-id="88d9d-128">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="88d9d-129">Classificatie en bepaling</span><span class="sxs-lookup"><span data-stu-id="88d9d-129">Classification and determination</span></span>
<span data-ttu-id="88d9d-130">U kunt ervoor kiezen geen classificatie in te stellen of te bepalen of een incident waar of onwaar is.</span><span class="sxs-lookup"><span data-stu-id="88d9d-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="88d9d-131">Als u dit doet, kan het team patronen zien en er van leren.</span><span class="sxs-lookup"><span data-stu-id="88d9d-131">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="88d9d-132">Opmerkingen toevoegen</span><span class="sxs-lookup"><span data-stu-id="88d9d-132">Add comments</span></span>
<span data-ttu-id="88d9d-133">U kunt opmerkingen toevoegen en historische gebeurtenissen over een incident bekijken om eerdere wijzigingen in het incident weer te geven.</span><span class="sxs-lookup"><span data-stu-id="88d9d-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="88d9d-134">Wanneer een wijziging of opmerking wordt aangebracht in een waarschuwing, wordt deze opgenomen in de sectie Opmerkingen en geschiedenis.</span><span class="sxs-lookup"><span data-stu-id="88d9d-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="88d9d-135">Toegevoegde opmerkingen worden direct weergegeven in het deelvenster.</span><span class="sxs-lookup"><span data-stu-id="88d9d-135">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="88d9d-136">Incidentlabels toevoegen</span><span class="sxs-lookup"><span data-stu-id="88d9d-136">Add incident tags</span></span>
<span data-ttu-id="88d9d-137">U kunt aangepaste tags toevoegen aan een incident, bijvoorbeeld om een vlag toe te voegen aan een groep incidenten met een gemeenschappelijke eigenschap.</span><span class="sxs-lookup"><span data-stu-id="88d9d-137">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="88d9d-138">U kunt later de wachtrij voor incidenten filteren op alle incidenten die een specifieke tag bevatten.</span><span class="sxs-lookup"><span data-stu-id="88d9d-138">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>
