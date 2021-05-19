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
ms.openlocfilehash: 725e6226a56b3aae3670cde18969afdda1ec1940
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530836"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="aac3c-104">Incidenten beheren in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aac3c-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="aac3c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="aac3c-105">**Applies to:**</span></span>
- <span data-ttu-id="aac3c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aac3c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="aac3c-107">Incidentbeheer is essentieel om ervoor te zorgen dat bedreigingen worden opgenomen en aangepakt.</span><span class="sxs-lookup"><span data-stu-id="aac3c-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="aac3c-108">U beheert incidenten van **incidenten & waarschuwingen > incidenten** tijdens de snelle start van het Microsoft 365 beveiligingscentrum [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="aac3c-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="aac3c-109">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="aac3c-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Voorbeeld van de incidentwachtrij":::

<span data-ttu-id="aac3c-111">Dit zijn de manieren waarop u uw incidenten kunt beheren:</span><span class="sxs-lookup"><span data-stu-id="aac3c-111">Here are the ways you can manage your incidents:</span></span>

- [<span data-ttu-id="aac3c-112">De naam van het incident bewerken</span><span class="sxs-lookup"><span data-stu-id="aac3c-112">Edit the incident name</span></span>](#edit-the-incident-name)
- [<span data-ttu-id="aac3c-113">Incidentlabels toevoegen</span><span class="sxs-lookup"><span data-stu-id="aac3c-113">Add incident tags</span></span>](#add-incident-tags)
- [<span data-ttu-id="aac3c-114">Het incident toewijzen aan een gebruikersaccount</span><span class="sxs-lookup"><span data-stu-id="aac3c-114">Assign the incident to a user account</span></span>](#assign-incidents)
- [<span data-ttu-id="aac3c-115">Deze oplossen</span><span class="sxs-lookup"><span data-stu-id="aac3c-115">Resolve them</span></span>](#resolve-an-incident)
- [<span data-ttu-id="aac3c-116">De classificatie en bepaling ervan instellen</span><span class="sxs-lookup"><span data-stu-id="aac3c-116">Set its classification and determination</span></span>](#set-the-classification-and-determination)
- [<span data-ttu-id="aac3c-117">Opmerkingen toevoegen</span><span class="sxs-lookup"><span data-stu-id="aac3c-117">Add comments</span></span>](#add-comments)

<span data-ttu-id="aac3c-118">U kunt incidenten beheren vanuit het deelvenster **Incident beheren** voor een incident.</span><span class="sxs-lookup"><span data-stu-id="aac3c-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="aac3c-119">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="aac3c-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Voorbeeld van het deelvenster Incident beheren van een incident":::

<span data-ttu-id="aac3c-121">U kunt dit deelvenster weergeven via de koppeling **Incident beheren** op het volgende:</span><span class="sxs-lookup"><span data-stu-id="aac3c-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="aac3c-122">Deelvenster Eigenschappen van een incident in de incidentwachtrij.</span><span class="sxs-lookup"><span data-stu-id="aac3c-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="aac3c-123">**Overzichtspagina** van een incident.</span><span class="sxs-lookup"><span data-stu-id="aac3c-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="aac3c-124">In gevallen waarin u waarschuwingen van het ene incident naar  het andere wilt verplaatsen, kunt u dit ook doen via het tabblad Waarschuwingen, waardoor een groter of kleiner incident wordt gemaakt met alle relevante waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="aac3c-124">In cases where you want to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="aac3c-125">De naam van het incident bewerken</span><span class="sxs-lookup"><span data-stu-id="aac3c-125">Edit the incident name</span></span>

<span data-ttu-id="aac3c-126">Microsoft 365 Defender wijst automatisch een naam toe op basis van waarschuwingskenmerken, zoals het aantal getroffen eindpunten, beïnvloede gebruikers, detectiebronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="aac3c-126">Microsoft 365 Defender automatically assigns a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="aac3c-127">Hierdoor kunt u snel inzicht krijgen in het bereik van het incident.</span><span class="sxs-lookup"><span data-stu-id="aac3c-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="aac3c-128">Bijvoorbeeld: *incident met meerdere fases op meerdere eindpunten die door meerdere bronnen zijn gerapporteerd.*</span><span class="sxs-lookup"><span data-stu-id="aac3c-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="aac3c-129">U kunt de naam van het incident bewerken vanuit het **veld Incidentnaam** in **het deelvenster Incident** beheren.</span><span class="sxs-lookup"><span data-stu-id="aac3c-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="aac3c-130">Incidenten die vóór de implementatie van de functie voor automatische naamgeving van incidenten hebben bestaan, behouden hun naam.</span><span class="sxs-lookup"><span data-stu-id="aac3c-130">Incidents that existed before the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="aac3c-131">Incidentlabels toevoegen</span><span class="sxs-lookup"><span data-stu-id="aac3c-131">Add incident tags</span></span>

<span data-ttu-id="aac3c-132">U kunt aangepaste tags toevoegen aan een incident, bijvoorbeeld om een vlag toe te voegen aan een groep incidenten met een gemeenschappelijke eigenschap.</span><span class="sxs-lookup"><span data-stu-id="aac3c-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="aac3c-133">U kunt de wachtrij voor incidenten later filteren op alle incidenten die een specifieke tag bevatten.</span><span class="sxs-lookup"><span data-stu-id="aac3c-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="aac3c-134">Wanneer u begint te typen, hebt u de optie om te selecteren in een lijst met geselecteerde tags.</span><span class="sxs-lookup"><span data-stu-id="aac3c-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="aac3c-135">Incidenten toewijzen</span><span class="sxs-lookup"><span data-stu-id="aac3c-135">Assign incidents</span></span>

<span data-ttu-id="aac3c-136">Als er nog geen incident is toegewezen, kunt u Toewijzen **aan** selecteren en het gebruikersaccount opgeven.</span><span class="sxs-lookup"><span data-stu-id="aac3c-136">If an incident has not yet been assigned, you can select **Assign to** and specify the user account.</span></span> <span data-ttu-id="aac3c-137">Als u dit doet, worden de eigenaar van het incident en alle waarschuwingen die aan het incident zijn gekoppeld, toegewezen.</span><span class="sxs-lookup"><span data-stu-id="aac3c-137">Doing so assigns ownership of the incident and all the alerts associated with it.</span></span>

## <a name="resolve-an-incident"></a><span data-ttu-id="aac3c-138">Een incident oplossen</span><span class="sxs-lookup"><span data-stu-id="aac3c-138">Resolve an incident</span></span>

<span data-ttu-id="aac3c-139">Als het incident is opgelost, selecteert u **Incident oplossen** om de schakelknop naar rechts te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="aac3c-139">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="aac3c-140">Het oplossen van een incident lost ook alle gekoppelde en actieve waarschuwingen met betrekking tot het incident op.</span><span class="sxs-lookup"><span data-stu-id="aac3c-140">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="aac3c-141">Een incident dat niet is opgelost, wordt weergegeven als **Actief**.</span><span class="sxs-lookup"><span data-stu-id="aac3c-141">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="aac3c-142">De classificatie en bepaling instellen</span><span class="sxs-lookup"><span data-stu-id="aac3c-142">Set the classification and determination</span></span>

<span data-ttu-id="aac3c-143">De incidentclassificatie is of het een echte waarschuwing of een onwaar waarschuwing was, die u configureert vanuit het **veld Classificatie.**</span><span class="sxs-lookup"><span data-stu-id="aac3c-143">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="aac3c-144">Als het een echte waarschuwing was, moet u ook opgeven welk type bedreiging het was met het **veld Bepaling.**</span><span class="sxs-lookup"><span data-stu-id="aac3c-144">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="aac3c-145">Als u het type bedreiging opgeeft, kan uw beveiligingsteam bedreigingspatronen zien en uw organisatie tegen hen beschermen.</span><span class="sxs-lookup"><span data-stu-id="aac3c-145">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="aac3c-146">Opmerkingen toevoegen</span><span class="sxs-lookup"><span data-stu-id="aac3c-146">Add comments</span></span>

<span data-ttu-id="aac3c-147">U kunt meerdere opmerkingen toevoegen aan een incident met **het** veld Opmerking.</span><span class="sxs-lookup"><span data-stu-id="aac3c-147">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="aac3c-148">Elke opmerking wordt toegevoegd aan de historische gebeurtenissen van het incident.</span><span class="sxs-lookup"><span data-stu-id="aac3c-148">Each comment gets added to the historical events of the incident.</span></span> <span data-ttu-id="aac3c-149">U kunt de opmerkingen en geschiedenis van een incident zien via de koppeling **Opmerkingen en geschiedenis** op de **pagina** Overzicht.</span><span class="sxs-lookup"><span data-stu-id="aac3c-149">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aac3c-150">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="aac3c-150">Next steps</span></span>

<span data-ttu-id="aac3c-151">Voor nieuwe incidenten start u uw [onderzoek.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="aac3c-151">For new incidents, begin your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="aac3c-152">Ga voor incidenten in proces verder met uw [onderzoek.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="aac3c-152">For in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="aac3c-153">Voer voor opgeloste incidenten een [beoordeling na het incident uit.](first-incident-post.md)</span><span class="sxs-lookup"><span data-stu-id="aac3c-153">For resolved incidents, perform a [post-incident review](first-incident-post.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aac3c-154">Zie ook</span><span class="sxs-lookup"><span data-stu-id="aac3c-154">See also</span></span>

- [<span data-ttu-id="aac3c-155">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="aac3c-155">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="aac3c-156">Prioriteit geven aan incidenten</span><span class="sxs-lookup"><span data-stu-id="aac3c-156">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="aac3c-157">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="aac3c-157">Investigate incidents</span></span>](investigate-incidents.md)
