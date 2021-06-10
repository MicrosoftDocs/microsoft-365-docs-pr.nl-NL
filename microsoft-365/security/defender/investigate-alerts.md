---
title: Waarschuwingen onderzoeken in Microsoft 365 Defender
description: Onderzoeken van waarschuwingen die worden gezien op apparaten, gebruikers en postvakken.
keywords: incidenten, waarschuwingen, onderzoeken, analyseren, reactie, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365
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
ms.openlocfilehash: a6e11aea14a7b8d99c0098b68951790328ec593e
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782907"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="b3f9e-104">Waarschuwingen onderzoeken in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3f9e-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b3f9e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b3f9e-105">**Applies to:**</span></span>
- <span data-ttu-id="b3f9e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3f9e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b3f9e-107">Waarschuwingen vormen de basis van alle incidenten en geven aan dat er schadelijke of verdachte gebeurtenissen in uw omgeving voorkomen.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="b3f9e-108">Waarschuwingen maken meestal deel uit van een bredere aanval en geven aanwijzingen over een incident.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="b3f9e-109">In Microsoft 365 Defender worden gerelateerde waarschuwingen samengevoegd tot [incidenten.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b3f9e-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="b3f9e-110">Incidenten bieden altijd de bredere context van een aanval, maar het analyseren van waarschuwingen kan waardevol zijn wanneer een diepere analyse is vereist.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="b3f9e-111">In **de wachtrij Waarschuwingen** ziet u de huidige set waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="b3f9e-112">U krijgt toegang tot de waarschuwingenwachtrij van **Incidenten & waarschuwingen > Waarschuwingen** bij de snelle start van het Microsoft 365 beveiligingscentrum [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b3f9e-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Voorbeeld van de waarschuwingenwachtrij":::

<span data-ttu-id="b3f9e-114">Waarschuwingen van verschillende Microsoft-beveiligingsoplossingen, zoals Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365 en Microsoft 365 Defender, worden hier weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="b3f9e-115">Standaard worden in de waarschuwingenwachtrij in Microsoft 365 beveiligingscentrum de nieuwe waarschuwingen van de afgelopen 30 dagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="b3f9e-116">De meest recente waarschuwing staat boven aan de lijst, zodat u deze als eerste kunt zien.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="b3f9e-117">In de wachtrij met standaardwaarschuwingen kunt u **Filters** selecteren om een deelvenster **Filters** te zien, waaruit u een subset van de waarschuwingen kunt opgeven.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="b3f9e-118">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Voorbeeld van het filtervenster voor de waarschuwingenwachtrij":::

<span data-ttu-id="b3f9e-120">U kunt waarschuwingen filteren op basis van deze criteria:</span><span class="sxs-lookup"><span data-stu-id="b3f9e-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="b3f9e-121">Ernst</span><span class="sxs-lookup"><span data-stu-id="b3f9e-121">Severity</span></span>
- <span data-ttu-id="b3f9e-122">Status</span><span class="sxs-lookup"><span data-stu-id="b3f9e-122">Status</span></span>
- <span data-ttu-id="b3f9e-123">Categorie</span><span class="sxs-lookup"><span data-stu-id="b3f9e-123">Category</span></span>
- <span data-ttu-id="b3f9e-124">Detectiebron</span><span class="sxs-lookup"><span data-stu-id="b3f9e-124">Detection source</span></span>
- <span data-ttu-id="b3f9e-125">Tags</span><span class="sxs-lookup"><span data-stu-id="b3f9e-125">Tags</span></span>
- <span data-ttu-id="b3f9e-126">Beleid</span><span class="sxs-lookup"><span data-stu-id="b3f9e-126">Policy</span></span>
- <span data-ttu-id="b3f9e-127">Beïnvloede activa</span><span class="sxs-lookup"><span data-stu-id="b3f9e-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="b3f9e-128">Een waarschuwing analyseren</span><span class="sxs-lookup"><span data-stu-id="b3f9e-128">Analyze an alert</span></span>

<span data-ttu-id="b3f9e-129">Als u de hoofdwaarschuwingspagina wilt zien, selecteert u de naam van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="b3f9e-130">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Voorbeeld van de detailspagina van een waarschuwing in het Microsoft 365 beveiligingscentrum":::

<span data-ttu-id="b3f9e-132">U kunt ook de actie **De hoofdwaarschuwingspagina openen** selecteren in **het deelvenster Waarschuwing** beheren.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="b3f9e-133">Een waarschuwingspagina bestaat uit deze secties:</span><span class="sxs-lookup"><span data-stu-id="b3f9e-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="b3f9e-134">Waarschuwingsverhaal, de reeks gebeurtenissen en waarschuwingen met betrekking tot deze waarschuwing in chronologische volgorde</span><span class="sxs-lookup"><span data-stu-id="b3f9e-134">Alert story, which is the chain of events and alerts related to this alert in chronological order</span></span>
- <span data-ttu-id="b3f9e-135">Overzichtsdetails</span><span class="sxs-lookup"><span data-stu-id="b3f9e-135">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Voorbeeld van de detailspagina van een waarschuwing in het Microsoft 365 beveiligingscentrum":::

<span data-ttu-id="b3f9e-137">Op een waarschuwingspagina kunt u de drie puntjes **(...)** naast een entiteit selecteren om beschikbare acties te bekijken, zoals het openen van de waarschuwingspagina of het koppelen van de waarschuwing aan een ander incident.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-137">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the alert page or linking the alert to another incident.</span></span>

### <a name="alert-sources"></a><span data-ttu-id="b3f9e-138">Waarschuwingsbronnen</span><span class="sxs-lookup"><span data-stu-id="b3f9e-138">Alert sources</span></span>
<span data-ttu-id="b3f9e-139">Microsoft 365 Defender-waarschuwingen kunnen afkomstig zijn van oplossingen zoals Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365 en Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-139">Microsoft 365 Defender alerts may come from solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft Cloud App Security.</span></span> <span data-ttu-id="b3f9e-140">U ziet mogelijk waarschuwingen met voorbereide tekens in de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-140">You may notice alerts with prepended characters in the alert.</span></span> <span data-ttu-id="b3f9e-141">De volgende tabel bevat richtlijnen om inzicht te krijgen in de toewijzing van waarschuwingsbronnen op basis van het voorbereide teken op de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-141">The following table provides guidance to help you understand the mapping of alert sources based on the prepended character on the alert.</span></span>

> [!NOTE]
> - <span data-ttu-id="b3f9e-142">De voorbereide GUID's zijn alleen specifiek voor geïntegreerde ervaringen, zoals unified alerts queue, unified alerts page, unified investigation en unified incident.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-142">The prepended GUIDs are specific only to unified experiences such as unified alerts queue, unified alerts page, unified investigation, and unified incident.</span></span><br>
> - <span data-ttu-id="b3f9e-143">Het voorbereide teken wijzigt de GUID van de waarschuwing niet.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-143">The prepended character does not change the GUID of the alert.</span></span> <span data-ttu-id="b3f9e-144">De enige wijziging in de GUID is het voorbereide onderdeel.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-144">The only change to the GUID is the prepended component.</span></span><br>


<span data-ttu-id="b3f9e-145">Waarschuwingsbron</span><span class="sxs-lookup"><span data-stu-id="b3f9e-145">Alert source</span></span> | <span data-ttu-id="b3f9e-146">Voorbereidend teken</span><span class="sxs-lookup"><span data-stu-id="b3f9e-146">Prepended character</span></span> 
:---|:---
<span data-ttu-id="b3f9e-147">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="b3f9e-147">Microsoft Defender for Office 365</span></span> | `fa{GUID}` <br> <span data-ttu-id="b3f9e-148">Voorbeeld: `fa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="b3f9e-148">Example: `fa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="b3f9e-149">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b3f9e-149">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="b3f9e-150">`da` of `ed` voor aangepaste detectiewaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="b3f9e-150">`da` or `ed` for custom detection alerts</span></span> <br> 
<span data-ttu-id="b3f9e-151">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="b3f9e-151">Microsoft Defender for Identity</span></span> | `aa{GUID}` <br> <span data-ttu-id="b3f9e-152">Voorbeeld: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="b3f9e-152">Example: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="b3f9e-153">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b3f9e-153">Microsoft Cloud App Security</span></span> |`ca{GUID}` <br> <span data-ttu-id="b3f9e-154">Voorbeeld: `ca123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="b3f9e-154">Example: `ca123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 



### <a name="analyze-affected-assets"></a><span data-ttu-id="b3f9e-155">Beïnvloede activa analyseren</span><span class="sxs-lookup"><span data-stu-id="b3f9e-155">Analyze affected assets</span></span>

<span data-ttu-id="b3f9e-156">De **sectie Acties ondernomen** heeft een lijst met beïnvloede activa, zoals postvakken, apparaten en gebruikers die door deze waarschuwing worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-156">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="b3f9e-157">U kunt ook Weergeven in het  **actiecentrum** selecteren om het tabblad Geschiedenis van het **actiecentrum** in het Microsoft 365 te bekijken.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-157">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="b3f9e-158">De rol van een waarschuwing in het waarschuwingsverhaal traceren</span><span class="sxs-lookup"><span data-stu-id="b3f9e-158">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="b3f9e-159">In het waarschuwingsverhaal worden alle activa of entiteiten weergegeven die betrekking hebben op de waarschuwing in een processtructuurweergave.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-159">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="b3f9e-160">De waarschuwing in de titel is de waarschuwing in focus wanneer u voor het eerst op de pagina van de geselecteerde waarschuwing komt.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-160">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="b3f9e-161">Activa in het waarschuwingsverhaal kunnen worden uitvuwbaar en kunnen worden geklikt.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-161">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="b3f9e-162">Ze bieden extra informatie en versnellen uw antwoord doordat u direct actie kunt ondernemen in de context van de waarschuwingspagina.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-162">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="b3f9e-163">De sectie Waarschuwingsverhaal kan meer dan één waarschuwing bevatten, met aanvullende waarschuwingen die betrekking hebben op dezelfde uitvoeringsstructuur die wordt weergegeven vóór of na de waarschuwing die u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-163">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="b3f9e-164">Meer informatie over waarschuwingen weergeven op de detailspagina</span><span class="sxs-lookup"><span data-stu-id="b3f9e-164">View more alert information on the details page</span></span>

<span data-ttu-id="b3f9e-165">Op de detailspagina ziet u de details van de geselecteerde waarschuwing, met details en acties die daaraan zijn gerelateerd.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-165">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="b3f9e-166">Als u een van de getroffen activa of entiteiten in het waarschuwingsverhaal selecteert, wordt de pagina details gewijzigd in contextuele informatie en acties voor het geselecteerde object.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-166">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="b3f9e-167">Nadat u een entiteit van belang hebt geselecteerd, wordt op de detailspagina informatie weergegeven over het geselecteerde entiteitstype, historische informatie wanneer deze beschikbaar is en opties om rechtstreeks vanaf de waarschuwingspagina actie te ondernemen op deze entiteit.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-167">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="b3f9e-168">Waarschuwingen beheren</span><span class="sxs-lookup"><span data-stu-id="b3f9e-168">Manage alerts</span></span>

<span data-ttu-id="b3f9e-169">Als u een waarschuwing wilt beheren, selecteert u de waarschuwing in de waarschuwingenwachtrij in de rij om het deelvenster **Waarschuwing beheren te** zien.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-169">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="b3f9e-170">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-170">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Voorbeeld van het overzichtsvenster voor een waarschuwing":::

<span data-ttu-id="b3f9e-172">In **het deelvenster Waarschuwing beheren** kunt u het volgende opgeven:</span><span class="sxs-lookup"><span data-stu-id="b3f9e-172">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="b3f9e-173">De status van de waarschuwing (Nieuw, Opgelost, In uitvoering).</span><span class="sxs-lookup"><span data-stu-id="b3f9e-173">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="b3f9e-174">De classificatie van de waarschuwing (Niet ingesteld, Waar-waarschuwing, Foutmelding).</span><span class="sxs-lookup"><span data-stu-id="b3f9e-174">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="b3f9e-175">Voor de classificatie als een echte waarschuwing, het type bedreiging voor de waarschuwing in **het veld Bepaling.**</span><span class="sxs-lookup"><span data-stu-id="b3f9e-175">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="b3f9e-176">Een opmerking over de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-176">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="b3f9e-177">Een manier om waarschuwingen te beheren via het gebruik van tags.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-177">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="b3f9e-178">De labelfunctie voor Microsoft Defender voor Office 365 wordt stapsgewijs uitgerold en wordt momenteel in preview uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-178">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="b3f9e-179">Op dit moment worden gewijzigde tagnamen alleen toegepast op waarschuwingen die *na de* update zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-179">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="b3f9e-180">Waarschuwingen die zijn gegenereerd vóór de wijziging, geven niet de naam van de bijgewerkte tag weer.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-180">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="b3f9e-181">In dit deelvenster kunt u ook de volgende aanvullende acties uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="b3f9e-181">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="b3f9e-182">De hoofdwaarschuwingspagina openen</span><span class="sxs-lookup"><span data-stu-id="b3f9e-182">Open the main alert page</span></span>
- <span data-ttu-id="b3f9e-183">Een Bedreigingsexpert van Microsoft raadplegen</span><span class="sxs-lookup"><span data-stu-id="b3f9e-183">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="b3f9e-184">Inzending weergeven</span><span class="sxs-lookup"><span data-stu-id="b3f9e-184">View submission</span></span>
- <span data-ttu-id="b3f9e-185">Koppeling maken naar een ander incident</span><span class="sxs-lookup"><span data-stu-id="b3f9e-185">Link to another incident</span></span>
- <span data-ttu-id="b3f9e-186">De waarschuwing in een tijdlijn bekijken</span><span class="sxs-lookup"><span data-stu-id="b3f9e-186">See the alert in a timeline</span></span>
- <span data-ttu-id="b3f9e-187">Een onderdrukkingsregel maken</span><span class="sxs-lookup"><span data-stu-id="b3f9e-187">Create a suppression rule</span></span>

<span data-ttu-id="b3f9e-188">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-188">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Voorbeeld van de acties op een waarschuwing in het Microsoft 365 beveiligingscentrum":::

<span data-ttu-id="b3f9e-190">De lijst met aanvullende acties is afhankelijk van het type waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-190">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="b3f9e-191">Een waarschuwing oplossen</span><span class="sxs-lookup"><span data-stu-id="b3f9e-191">Resolve an alert</span></span>

<span data-ttu-id="b3f9e-192">Wanneer u klaar bent met het analyseren van een waarschuwing en deze kan worden opgelost,  gaat u naar het  deelvenster Waarschuwing beheren voor de waarschuwing en markeert u de status van de waarschuwing als Opgelost en classificeert u deze als een foutmelding of **True-waarschuwing.** </span><span class="sxs-lookup"><span data-stu-id="b3f9e-192">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="b3f9e-193">Geef voor echte waarschuwingen het bedreigingstype van de waarschuwing op in **het veld Bepaling.**</span><span class="sxs-lookup"><span data-stu-id="b3f9e-193">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="b3f9e-194">Als u waarschuwingen classificeert en de bepaling opgeeft, Microsoft 365 Defender meer waar waarschuwingen en minder onwaar waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="b3f9e-194">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b3f9e-195">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="b3f9e-195">Next steps</span></span>

<span data-ttu-id="b3f9e-196">Ga zo nodig door met uw onderzoek als dit nodig is voor incidenten in [de procedure.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="b3f9e-196">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b3f9e-197">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b3f9e-197">See also</span></span>

- [<span data-ttu-id="b3f9e-198">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="b3f9e-198">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b3f9e-199">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="b3f9e-199">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="b3f9e-200">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="b3f9e-200">Investigate incidents</span></span>](investigate-incidents.md)
