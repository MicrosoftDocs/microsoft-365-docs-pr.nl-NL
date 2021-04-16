---
title: Waarschuwingen onderzoeken in Microsoft 365 Defender
description: Onderzoeken van waarschuwingen die worden gezien op apparaten, gebruikers en postvakken.
keywords: incidenten, waarschuwingen, onderzoeken, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365
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
ms.openlocfilehash: 77b30e8a8eee70470115bcd61f081863fa5a41ee
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861991"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="54ee5-104">Waarschuwingen onderzoeken in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54ee5-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="54ee5-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="54ee5-105">**Applies to:**</span></span>
- <span data-ttu-id="54ee5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="54ee5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="54ee5-107">Waarschuwingen vormen de basis van alle incidenten en geven aan dat er schadelijke of verdachte gebeurtenissen in uw omgeving voorkomen.</span><span class="sxs-lookup"><span data-stu-id="54ee5-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="54ee5-108">Waarschuwingen maken meestal deel uit van een bredere aanval en geven aanwijzingen over een incident.</span><span class="sxs-lookup"><span data-stu-id="54ee5-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="54ee5-109">In Microsoft 365 Defender worden gerelateerde waarschuwingen samengevoegd tot [incidenten.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="54ee5-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="54ee5-110">Incidenten bieden altijd de bredere context van een aanval, maar het onderzoeken van waarschuwingen kan waardevol zijn wanneer een diepere analyse is vereist.</span><span class="sxs-lookup"><span data-stu-id="54ee5-110">Incidents will always provide the broader context of an attack, however, investigating alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="54ee5-111">In **de wachtrij Waarschuwingen** ziet u de huidige set waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="54ee5-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="54ee5-112">U krijgt toegang tot de waarschuwingenwachtrij van **Incidenten & waarschuwingen > Waarschuwingen** bij de snelle start van het Microsoft 365-beveiligingscentrum [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="54ee5-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Voorbeeld van de waarschuwingenwachtrij":::

<span data-ttu-id="54ee5-114">Waarschuwingen van verschillende Microsoft-beveiligingsoplossingen, zoals Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365 en Microsoft 365 Defender, worden hier weergegeven.</span><span class="sxs-lookup"><span data-stu-id="54ee5-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="54ee5-115">Standaard worden in de waarschuwingenwachtrij in het Microsoft 365-beveiligingscentrum de nieuwe waarschuwingen van de afgelopen 30 dagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="54ee5-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="54ee5-116">De meest recente waarschuwing staat boven aan de lijst, zodat u deze als eerste kunt zien.</span><span class="sxs-lookup"><span data-stu-id="54ee5-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="54ee5-117">In de wachtrij met standaardwaarschuwingen kunt u **Filters** selecteren om een deelvenster **Filters** te zien, waaruit u een subset van de waarschuwingen kunt opgeven.</span><span class="sxs-lookup"><span data-stu-id="54ee5-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="54ee5-118">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="54ee5-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Voorbeeld van het filtervenster voor de waarschuwingenwachtrij":::

<span data-ttu-id="54ee5-120">U kunt waarschuwingen filteren op basis van deze criteria:</span><span class="sxs-lookup"><span data-stu-id="54ee5-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="54ee5-121">Ernst</span><span class="sxs-lookup"><span data-stu-id="54ee5-121">Severity</span></span>
- <span data-ttu-id="54ee5-122">Status</span><span class="sxs-lookup"><span data-stu-id="54ee5-122">Status</span></span>
- <span data-ttu-id="54ee5-123">Categorie</span><span class="sxs-lookup"><span data-stu-id="54ee5-123">Category</span></span>
- <span data-ttu-id="54ee5-124">Detectiebron</span><span class="sxs-lookup"><span data-stu-id="54ee5-124">Detection source</span></span>
- <span data-ttu-id="54ee5-125">Tags</span><span class="sxs-lookup"><span data-stu-id="54ee5-125">Tags</span></span>
- <span data-ttu-id="54ee5-126">Beleid</span><span class="sxs-lookup"><span data-stu-id="54ee5-126">Policy</span></span>
- <span data-ttu-id="54ee5-127">Beïnvloede activa</span><span class="sxs-lookup"><span data-stu-id="54ee5-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="54ee5-128">Een waarschuwing analyseren</span><span class="sxs-lookup"><span data-stu-id="54ee5-128">Analyze an alert</span></span>

<span data-ttu-id="54ee5-129">Als u de hoofdwaarschuwingspagina wilt zien, selecteert u de naam van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="54ee5-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="54ee5-130">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="54ee5-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Voorbeeld van de detailspagina van een waarschuwing in het Microsoft 365-beveiligingscentrum":::

<span data-ttu-id="54ee5-132">U kunt ook de actie **De hoofdwaarschuwingspagina openen** selecteren in **het deelvenster Waarschuwing** beheren.</span><span class="sxs-lookup"><span data-stu-id="54ee5-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="54ee5-133">Een waarschuwingspagina bestaat uit deze secties:</span><span class="sxs-lookup"><span data-stu-id="54ee5-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="54ee5-134">Waarschuwingsverhaal</span><span class="sxs-lookup"><span data-stu-id="54ee5-134">Alert story</span></span>
- <span data-ttu-id="54ee5-135">Acties die zijn ondernomen (inclusief beïnvloede activa)</span><span class="sxs-lookup"><span data-stu-id="54ee5-135">Actions taken (including impacted assets)</span></span>
- <span data-ttu-id="54ee5-136">Gerelateerde gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="54ee5-136">Related events</span></span>
- <span data-ttu-id="54ee5-137">Overzichtsdetails</span><span class="sxs-lookup"><span data-stu-id="54ee5-137">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Voorbeeld van de detailspagina van een waarschuwing in het Microsoft 365-beveiligingscentrum":::

<span data-ttu-id="54ee5-139">Op een waarschuwingspagina kunt u de beletsels **(...)** naast een entiteit selecteren om beschikbare acties weer te geven, zoals het openen van de specifieke activapagina of het uitvoeren van specifieke herstelstappen.</span><span class="sxs-lookup"><span data-stu-id="54ee5-139">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the specific asset page or taking specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="54ee5-140">Beïnvloede activa analyseren</span><span class="sxs-lookup"><span data-stu-id="54ee5-140">Analyze affected assets</span></span>

<span data-ttu-id="54ee5-141">De **sectie Acties ondernomen** heeft een lijst met beïnvloede activa, zoals postvakken, apparaten en gebruikers die door deze waarschuwing worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="54ee5-141">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="54ee5-142">U kunt ook **Weergeven in het actiecentrum selecteren** om het tabblad Geschiedenis van het **Actiecentrum** in het Microsoft 365-beveiligingscentrum te bekijken. </span><span class="sxs-lookup"><span data-stu-id="54ee5-142">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="54ee5-143">De rol van een waarschuwing in het waarschuwingsverhaal traceren</span><span class="sxs-lookup"><span data-stu-id="54ee5-143">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="54ee5-144">In het waarschuwingsverhaal worden alle activa of entiteiten weergegeven die betrekking hebben op de waarschuwing in een processtructuurweergave.</span><span class="sxs-lookup"><span data-stu-id="54ee5-144">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="54ee5-145">De waarschuwing in de titel is de waarschuwing in focus wanneer u voor het eerst op de pagina van de geselecteerde waarschuwing komt.</span><span class="sxs-lookup"><span data-stu-id="54ee5-145">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="54ee5-146">Activa in het waarschuwingsverhaal kunnen worden uitvuwbaar en kunnen worden geklikt.</span><span class="sxs-lookup"><span data-stu-id="54ee5-146">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="54ee5-147">Ze bieden extra informatie en versnellen uw antwoord doordat u direct actie kunt ondernemen in de context van de waarschuwingspagina.</span><span class="sxs-lookup"><span data-stu-id="54ee5-147">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="54ee5-148">De sectie Waarschuwingsverhaal kan meer dan één waarschuwing bevatten, met aanvullende waarschuwingen die betrekking hebben op dezelfde uitvoeringsstructuur die wordt weergegeven vóór of na de waarschuwing die u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="54ee5-148">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="54ee5-149">Meer informatie over waarschuwingen weergeven op de detailspagina</span><span class="sxs-lookup"><span data-stu-id="54ee5-149">View more alert information on the details page</span></span>

<span data-ttu-id="54ee5-150">Op de detailspagina ziet u de details van de geselecteerde waarschuwing, met details en acties die daaraan zijn gerelateerd.</span><span class="sxs-lookup"><span data-stu-id="54ee5-150">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="54ee5-151">Als u een van de getroffen activa of entiteiten in het waarschuwingsverhaal selecteert, wordt de pagina details gewijzigd in contextuele informatie en acties voor het geselecteerde object.</span><span class="sxs-lookup"><span data-stu-id="54ee5-151">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="54ee5-152">Nadat u een entiteit van belang hebt geselecteerd, wordt op de detailspagina informatie weergegeven over het geselecteerde entiteitstype, historische informatie wanneer deze beschikbaar is en opties om rechtstreeks vanaf de waarschuwingspagina actie te ondernemen op deze entiteit.</span><span class="sxs-lookup"><span data-stu-id="54ee5-152">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="54ee5-153">Waarschuwingen beheren</span><span class="sxs-lookup"><span data-stu-id="54ee5-153">Manage alerts</span></span>

<span data-ttu-id="54ee5-154">Als u een waarschuwing wilt beheren, selecteert u de waarschuwing in de waarschuwingenwachtrij in de rij om het deelvenster **Waarschuwing beheren te** zien.</span><span class="sxs-lookup"><span data-stu-id="54ee5-154">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="54ee5-155">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="54ee5-155">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Voorbeeld van het overzichtsvenster voor een waarschuwing":::

<span data-ttu-id="54ee5-157">In **het deelvenster Waarschuwing beheren** kunt u het volgende opgeven:</span><span class="sxs-lookup"><span data-stu-id="54ee5-157">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="54ee5-158">De status van de waarschuwing (Nieuw, Opgelost, In uitvoering).</span><span class="sxs-lookup"><span data-stu-id="54ee5-158">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="54ee5-159">De classificatie van de waarschuwing (Niet ingesteld, Waar-waarschuwing, Foutmelding).</span><span class="sxs-lookup"><span data-stu-id="54ee5-159">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="54ee5-160">Voor de classificatie als een echte waarschuwing, het type bedreiging voor de waarschuwing in **het veld Bepaling.**</span><span class="sxs-lookup"><span data-stu-id="54ee5-160">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="54ee5-161">Een opmerking over de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="54ee5-161">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="54ee5-162">Een manier om waarschuwingen te beheren via het gebruik van tags.</span><span class="sxs-lookup"><span data-stu-id="54ee5-162">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="54ee5-163">De labelfunctie voor Microsoft Defender voor Office 365 wordt stapsgewijs uitgerold en wordt momenteel in preview uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="54ee5-163">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="54ee5-164">Op dit moment worden gewijzigde tagnamen alleen toegepast op waarschuwingen die *na de* update zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="54ee5-164">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="54ee5-165">Waarschuwingen die zijn gegenereerd vóór de wijziging, geven niet de naam van de bijgewerkte tag weer.</span><span class="sxs-lookup"><span data-stu-id="54ee5-165">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="54ee5-166">In dit deelvenster kunt u ook de volgende aanvullende acties uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="54ee5-166">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="54ee5-167">De hoofdwaarschuwingspagina openen</span><span class="sxs-lookup"><span data-stu-id="54ee5-167">Open the main alert page</span></span>
- <span data-ttu-id="54ee5-168">Een Bedreigingsexpert van Microsoft raadplegen</span><span class="sxs-lookup"><span data-stu-id="54ee5-168">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="54ee5-169">Inzending weergeven</span><span class="sxs-lookup"><span data-stu-id="54ee5-169">View submission</span></span>
- <span data-ttu-id="54ee5-170">Koppeling maken naar een ander incident</span><span class="sxs-lookup"><span data-stu-id="54ee5-170">Link to another incident</span></span>
- <span data-ttu-id="54ee5-171">De waarschuwing in een tijdlijn bekijken</span><span class="sxs-lookup"><span data-stu-id="54ee5-171">See the alert in a timeline</span></span>
- <span data-ttu-id="54ee5-172">Een onderdrukkingsregel maken</span><span class="sxs-lookup"><span data-stu-id="54ee5-172">Create a suppression rule</span></span>

<span data-ttu-id="54ee5-173">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="54ee5-173">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Voorbeeld van de acties voor een waarschuwing in het Microsoft 365-beveiligingscentrum":::

<span data-ttu-id="54ee5-175">De lijst met aanvullende acties is afhankelijk van het type waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="54ee5-175">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="54ee5-176">Een waarschuwing oplossen</span><span class="sxs-lookup"><span data-stu-id="54ee5-176">Resolve an alert</span></span>

<span data-ttu-id="54ee5-177">Nadat u klaar bent met het onderzoeken van een  waarschuwing en deze kan worden opgelost, gaat u naar het  deelvenster Waarschuwing beheren voor de waarschuwing en markeert u de status van de waarschuwing als Opgelost en classificeert u deze als een foutmelding of een  waar-waarschuwing. </span><span class="sxs-lookup"><span data-stu-id="54ee5-177">Once you're done investigating an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="54ee5-178">Geef voor echte waarschuwingen het bedreigingstype van de waarschuwing op in **het veld Bepaling.**</span><span class="sxs-lookup"><span data-stu-id="54ee5-178">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="54ee5-179">Als u waarschuwingen classificeert en de bepaling opgeeft, kunt u Microsoft 365 Defender afstemmen om meer waargebeurde waarschuwingen en minder foutmeldingen te geven.</span><span class="sxs-lookup"><span data-stu-id="54ee5-179">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="see-also"></a><span data-ttu-id="54ee5-180">Zie ook</span><span class="sxs-lookup"><span data-stu-id="54ee5-180">See also</span></span>

- [<span data-ttu-id="54ee5-181">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="54ee5-181">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="54ee5-182">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="54ee5-182">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="54ee5-183">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="54ee5-183">Manage incidents</span></span>](manage-incidents.md)
