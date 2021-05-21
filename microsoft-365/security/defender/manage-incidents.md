---
title: Incidenten beheren in Microsoft 365 Defender
description: Informatie over het toewijzen, bijwerken van de status,
keywords: incident, incidenten, analyseren, antwoord, waarschuwingen, gecorreleerd waarschuwingen, toewijzen, bijwerken, status, beheren, classificatie, microsoft, 365, m365
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
ms.openlocfilehash: 9cb3cc67c3992773897ea8178f261d25dcd87da0
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594146"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="72862-104">Incidenten beheren in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72862-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="72862-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="72862-105">**Applies to:**</span></span>
- <span data-ttu-id="72862-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72862-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="72862-107">Incidentbeheer is essentieel om ervoor te zorgen dat bedreigingen worden opgenomen en aangepakt.</span><span class="sxs-lookup"><span data-stu-id="72862-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="72862-108">U beheert incidenten van **incidenten & waarschuwingen > incidenten** tijdens de snelle start van het Microsoft 365 beveiligingscentrum [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="72862-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="72862-109">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="72862-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Voorbeeld van de incidentwachtrij":::

<span data-ttu-id="72862-111">Dit zijn de manieren waarop u uw incidenten kunt beheren:</span><span class="sxs-lookup"><span data-stu-id="72862-111">Here are the ways you can manage your incidents:</span></span>

- [<span data-ttu-id="72862-112">De naam van het incident bewerken</span><span class="sxs-lookup"><span data-stu-id="72862-112">Edit the incident name</span></span>](#edit-the-incident-name)
- [<span data-ttu-id="72862-113">Incidentlabels toevoegen</span><span class="sxs-lookup"><span data-stu-id="72862-113">Add incident tags</span></span>](#add-incident-tags)
- [<span data-ttu-id="72862-114">Het incident aan uzelf toewijzen</span><span class="sxs-lookup"><span data-stu-id="72862-114">Assign the incident to yourself</span></span>](#assign-incidents)
- [<span data-ttu-id="72862-115">Deze oplossen</span><span class="sxs-lookup"><span data-stu-id="72862-115">Resolve them</span></span>](#resolve-an-incident)
- [<span data-ttu-id="72862-116">De classificatie en bepaling ervan instellen</span><span class="sxs-lookup"><span data-stu-id="72862-116">Set its classification and determination</span></span>](#set-the-classification-and-determination)
- [<span data-ttu-id="72862-117">Opmerkingen toevoegen</span><span class="sxs-lookup"><span data-stu-id="72862-117">Add comments</span></span>](#add-comments)

<span data-ttu-id="72862-118">U kunt incidenten beheren vanuit het deelvenster **Incident beheren** voor een incident.</span><span class="sxs-lookup"><span data-stu-id="72862-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="72862-119">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="72862-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Voorbeeld van het deelvenster Incident beheren van een incident":::

<span data-ttu-id="72862-121">U kunt dit deelvenster weergeven via de koppeling **Incident beheren** op het volgende:</span><span class="sxs-lookup"><span data-stu-id="72862-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="72862-122">Deelvenster Eigenschappen van een incident in de incidentwachtrij.</span><span class="sxs-lookup"><span data-stu-id="72862-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="72862-123">**Overzichtspagina** van een incident.</span><span class="sxs-lookup"><span data-stu-id="72862-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="72862-124">In gevallen waarin u waarschuwingen van het ene incident naar  het andere wilt verplaatsen, kunt u dit ook doen via het tabblad Waarschuwingen, waardoor een groter of kleiner incident wordt gemaakt met alle relevante waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="72862-124">In cases where you want to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="72862-125">De naam van het incident bewerken</span><span class="sxs-lookup"><span data-stu-id="72862-125">Edit the incident name</span></span>

<span data-ttu-id="72862-126">Microsoft 365 Defender wijst automatisch een naam toe op basis van waarschuwingskenmerken, zoals het aantal getroffen eindpunten, beïnvloede gebruikers, detectiebronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="72862-126">Microsoft 365 Defender automatically assigns a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="72862-127">Hierdoor kunt u snel inzicht krijgen in het bereik van het incident.</span><span class="sxs-lookup"><span data-stu-id="72862-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="72862-128">Bijvoorbeeld: *incident met meerdere fases op meerdere eindpunten die door meerdere bronnen zijn gerapporteerd.*</span><span class="sxs-lookup"><span data-stu-id="72862-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="72862-129">U kunt de naam van het incident bewerken vanuit het **veld Incidentnaam** in **het deelvenster Incident** beheren.</span><span class="sxs-lookup"><span data-stu-id="72862-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="72862-130">Incidenten die vóór de implementatie van de functie voor automatische naamgeving van incidenten hebben bestaan, behouden hun naam.</span><span class="sxs-lookup"><span data-stu-id="72862-130">Incidents that existed before the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="72862-131">Incidentlabels toevoegen</span><span class="sxs-lookup"><span data-stu-id="72862-131">Add incident tags</span></span>

<span data-ttu-id="72862-132">U kunt aangepaste tags toevoegen aan een incident, bijvoorbeeld om een vlag toe te voegen aan een groep incidenten met een gemeenschappelijke eigenschap.</span><span class="sxs-lookup"><span data-stu-id="72862-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="72862-133">U kunt de wachtrij voor incidenten later filteren op alle incidenten die een specifieke tag bevatten.</span><span class="sxs-lookup"><span data-stu-id="72862-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="72862-134">Wanneer u begint te typen, hebt u de optie om te selecteren in een lijst met geselecteerde tags.</span><span class="sxs-lookup"><span data-stu-id="72862-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="72862-135">Incidenten toewijzen</span><span class="sxs-lookup"><span data-stu-id="72862-135">Assign incidents</span></span>

<span data-ttu-id="72862-136">Als u een incident wilt toewijzen, **selecteert u Toewijzen aan mij.**</span><span class="sxs-lookup"><span data-stu-id="72862-136">To assign an incident, select **Assign to me**.</span></span> <span data-ttu-id="72862-137">Als u dit doet, worden de eigenaar van het incident en alle waarschuwingen die aan het incident zijn gekoppeld, toegewezen aan uw gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="72862-137">Doing so assigns ownership of the incident and all the alerts associated with it to your user account.</span></span>

<span data-ttu-id="72862-138">U kunt een lijst met incidenten krijgen die aan u zijn toegewezen door de wachtrij voor incidenten te filteren.</span><span class="sxs-lookup"><span data-stu-id="72862-138">You can get a list of incidents assigned to you by filtering the incident queue.</span></span> 

1. <span data-ttu-id="72862-139">Selecteer filters in de wachtrij voor **incidenten.**</span><span class="sxs-lookup"><span data-stu-id="72862-139">From the incident queue, select **Filters**.</span></span>
2. <span data-ttu-id="72862-140">schakel in **de sectie Incidenttoewijzing** **alles selecteren uit** en selecteer Toegewezen aan **mij.**</span><span class="sxs-lookup"><span data-stu-id="72862-140">in the **Incident assignment** section, clear **Select all** and select **Assigned to me**.</span></span>
3. <span data-ttu-id="72862-141">Selecteer **Toepassen** en sluit het **deelvenster** Filters.</span><span class="sxs-lookup"><span data-stu-id="72862-141">Select **Apply**, and then close the **Filters** pane.</span></span>

<span data-ttu-id="72862-142">Vervolgens kunt u de resulterende URL in uw browser opslaan als bladwijzer om snel de lijst met incidenten weer te geven die aan u zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="72862-142">You can then save the resulting URL in your browser as a bookmark to quickly see the list of incidents assigned to you.</span></span>

## <a name="resolve-an-incident"></a><span data-ttu-id="72862-143">Een incident oplossen</span><span class="sxs-lookup"><span data-stu-id="72862-143">Resolve an incident</span></span>

<span data-ttu-id="72862-144">Als het incident is opgelost, selecteert u **Incident oplossen** om de schakelknop naar rechts te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="72862-144">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="72862-145">Het oplossen van een incident lost ook alle gekoppelde en actieve waarschuwingen met betrekking tot het incident op.</span><span class="sxs-lookup"><span data-stu-id="72862-145">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="72862-146">Een incident dat niet is opgelost, wordt weergegeven als **Actief**.</span><span class="sxs-lookup"><span data-stu-id="72862-146">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="72862-147">De classificatie en bepaling instellen</span><span class="sxs-lookup"><span data-stu-id="72862-147">Set the classification and determination</span></span>

<span data-ttu-id="72862-148">De incidentclassificatie is of het een echte waarschuwing of een onwaar waarschuwing was, die u configureert vanuit het **veld Classificatie.**</span><span class="sxs-lookup"><span data-stu-id="72862-148">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="72862-149">Als het een echte waarschuwing was, moet u ook opgeven welk type bedreiging het was met het **veld Bepaling.**</span><span class="sxs-lookup"><span data-stu-id="72862-149">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="72862-150">Als u het type bedreiging opgeeft, kan uw beveiligingsteam bedreigingspatronen zien en uw organisatie tegen hen beschermen.</span><span class="sxs-lookup"><span data-stu-id="72862-150">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="72862-151">Opmerkingen toevoegen</span><span class="sxs-lookup"><span data-stu-id="72862-151">Add comments</span></span>

<span data-ttu-id="72862-152">U kunt meerdere opmerkingen toevoegen aan een incident met **het** veld Opmerking.</span><span class="sxs-lookup"><span data-stu-id="72862-152">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="72862-153">Elke opmerking wordt toegevoegd aan de historische gebeurtenissen van het incident.</span><span class="sxs-lookup"><span data-stu-id="72862-153">Each comment gets added to the historical events of the incident.</span></span> <span data-ttu-id="72862-154">U kunt de opmerkingen en geschiedenis van een incident zien via de koppeling **Opmerkingen en geschiedenis** op de **pagina** Overzicht.</span><span class="sxs-lookup"><span data-stu-id="72862-154">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="72862-155">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="72862-155">Next steps</span></span>

<span data-ttu-id="72862-156">Voor nieuwe incidenten start u uw [onderzoek.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="72862-156">For new incidents, begin your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="72862-157">Ga voor incidenten in proces verder met uw [onderzoek.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="72862-157">For in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="72862-158">Voer voor opgeloste incidenten een [beoordeling na het incident uit.](first-incident-post.md)</span><span class="sxs-lookup"><span data-stu-id="72862-158">For resolved incidents, perform a [post-incident review](first-incident-post.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="72862-159">Zie ook</span><span class="sxs-lookup"><span data-stu-id="72862-159">See also</span></span>

- [<span data-ttu-id="72862-160">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="72862-160">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="72862-161">Prioriteit geven aan incidenten</span><span class="sxs-lookup"><span data-stu-id="72862-161">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="72862-162">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="72862-162">Investigate incidents</span></span>](investigate-incidents.md)
