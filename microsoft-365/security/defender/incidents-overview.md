---
title: Incidenten in Microsoft 365 Defender
description: Incidenten op verschillende apparaten, gebruikers en postvakken in de Microsoft 365 Defender onderzoeken.
keywords: incidenten, waarschuwingen, onderzoeken, analyseren, reactie, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365, incidentrespons, cyberaanvallen
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
ms.openlocfilehash: b6830c77a0c5cc93ea202844a8793c5f69f07650
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028521"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="4e911-104">Incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e911-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4e911-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4e911-105">**Applies to:**</span></span>
- <span data-ttu-id="4e911-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e911-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="4e911-107">Wilt u Microsoft 365 Defender ervaren?</span><span class="sxs-lookup"><span data-stu-id="4e911-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="4e911-108">U kunt het [evalueren in een testomgeving](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) of [uw pilotproject uitvoeren in een productieomgeving](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="4e911-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="4e911-109">Een incident in Microsoft 365 Defender is een verzameling van gecorreleerde waarschuwingen en bijbehorende gegevens die het verhaal van een aanval bevatten.</span><span class="sxs-lookup"><span data-stu-id="4e911-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="4e911-110">Microsoft 365 services en apps maken waarschuwingen wanneer ze een verdachte of schadelijke gebeurtenis of activiteit detecteren.</span><span class="sxs-lookup"><span data-stu-id="4e911-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="4e911-111">Afzonderlijke waarschuwingen geven waardevolle aanwijzingen over een voltooide of lopende aanval.</span><span class="sxs-lookup"><span data-stu-id="4e911-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="4e911-112">Aanvallen gebruiken echter meestal verschillende technieken voor verschillende typen entiteiten, zoals apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="4e911-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="4e911-113">Het resultaat is meerdere waarschuwingen voor meerdere entiteiten in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="4e911-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="4e911-114">Omdat het lastig en tijdrovend kan zijn om de afzonderlijke waarschuwingen samen te cirkelen om inzicht te krijgen in een aanval Microsoft 365 Defender, worden de waarschuwingen en de bijbehorende informatie automatisch samengevoegd tot een incident.</span><span class="sxs-lookup"><span data-stu-id="4e911-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Hoe Microsoft 365 Defender gebeurtenissen van entiteiten correleert in een incident":::

<span data-ttu-id="4e911-116">Bekijk dit korte overzicht van incidenten in Microsoft 365 Defender (4 minuten).</span><span class="sxs-lookup"><span data-stu-id="4e911-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="4e911-117">Door gerelateerde waarschuwingen in een incident te groeperen, krijgt u een uitgebreide weergave van een aanval.</span><span class="sxs-lookup"><span data-stu-id="4e911-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="4e911-118">U kunt bijvoorbeeld het volgende zien:</span><span class="sxs-lookup"><span data-stu-id="4e911-118">For example, you can see:</span></span>

- <span data-ttu-id="4e911-119">Waar de aanval is begonnen.</span><span class="sxs-lookup"><span data-stu-id="4e911-119">Where the attack started.</span></span>
- <span data-ttu-id="4e911-120">Welke tactieken zijn gebruikt.</span><span class="sxs-lookup"><span data-stu-id="4e911-120">What tactics were used.</span></span>
- <span data-ttu-id="4e911-121">Hoe ver de aanval is gegaan in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="4e911-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="4e911-122">Het bereik van de aanval, zoals het aantal apparaten, gebruikers en postvakken dat is beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="4e911-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="4e911-123">Alle gegevens die aan de aanval zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="4e911-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="4e911-124">Als [dit is ingeschakeld,](m365d-enable.md)Microsoft 365 Defender [waarschuwingen automatisch](m365d-autoir.md) onderzoeken en oplossen via automatisering en kunstmatige intelligentie.</span><span class="sxs-lookup"><span data-stu-id="4e911-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can [automatically investigate and resolve](m365d-autoir.md) alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="4e911-125">U kunt ook aanvullende herstelstappen uitvoeren om de aanval op te lossen.</span><span class="sxs-lookup"><span data-stu-id="4e911-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="4e911-126">Incidenten en waarschuwingen in de Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="4e911-126">Incidents and alerts in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="4e911-127">U beheert incidenten vanuit **Incidenten & waarschuwingen > incidenten** op de snelle start van de Microsoft 365 Defender portal [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4e911-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="4e911-128">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="4e911-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="De pagina Incidenten in de Microsoft 365 Defender portal":::

<span data-ttu-id="4e911-130">Als u een incidentnaam selecteert, wordt een overzicht van het incident weergegeven en krijgt u toegang tot tabbladen met aanvullende informatie.</span><span class="sxs-lookup"><span data-stu-id="4e911-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Voorbeeld van de pagina Overzicht voor een incident in de Microsoft 365 Defender portal":::

<span data-ttu-id="4e911-132">De extra tabbladen voor een incident zijn:</span><span class="sxs-lookup"><span data-stu-id="4e911-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="4e911-133">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="4e911-133">Alerts</span></span> 

  <span data-ttu-id="4e911-134">Alle waarschuwingen met betrekking tot het incident en de bijbehorende informatie.</span><span class="sxs-lookup"><span data-stu-id="4e911-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="4e911-135">Apparaten</span><span class="sxs-lookup"><span data-stu-id="4e911-135">Devices</span></span>

  <span data-ttu-id="4e911-136">Alle apparaten die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.</span><span class="sxs-lookup"><span data-stu-id="4e911-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="4e911-137">Gebruikers</span><span class="sxs-lookup"><span data-stu-id="4e911-137">Users</span></span>

  <span data-ttu-id="4e911-138">Alle gebruikers die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.</span><span class="sxs-lookup"><span data-stu-id="4e911-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="4e911-139">Postvakken</span><span class="sxs-lookup"><span data-stu-id="4e911-139">Mailboxes</span></span>

  <span data-ttu-id="4e911-140">Alle postvakken die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.</span><span class="sxs-lookup"><span data-stu-id="4e911-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="4e911-141">Onderzoeken</span><span class="sxs-lookup"><span data-stu-id="4e911-141">Investigations</span></span>

  <span data-ttu-id="4e911-142">Alle automatische [onderzoeken die worden veroorzaakt](m365d-autoir.md) door waarschuwingen bij het incident.</span><span class="sxs-lookup"><span data-stu-id="4e911-142">All the [automated investigations](m365d-autoir.md) triggered by alerts in the incident.</span></span>

- <span data-ttu-id="4e911-143">Bewijs en antwoord</span><span class="sxs-lookup"><span data-stu-id="4e911-143">Evidence and Response</span></span>

  <span data-ttu-id="4e911-144">Alle ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen in het incident.</span><span class="sxs-lookup"><span data-stu-id="4e911-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

- <span data-ttu-id="4e911-145">Graph (in voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="4e911-145">Graph (in preview)</span></span>

  <span data-ttu-id="4e911-146">Een afbeelding met de verbinding van waarschuwingen met de beïnvloede activa in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="4e911-146">A figure showing the connection of alerts to the impacted assets in your organization.</span></span>

<span data-ttu-id="4e911-147">Hier is de relatie tussen een incident en de gegevens en de tabbladen van een incident in de Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="4e911-147">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="De relatie van een incident en de gegevens ervan met de tabbladen van een incident in de Microsoft 365 Defender portal":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="4e911-149">Voorbeeld van de werkstroom incidentrespons voor Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e911-149">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="4e911-150">Hier is een voorbeeldwerkstroom voor het reageren op incidenten in Microsoft 365 met de Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="4e911-150">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Voorbeeld van een werkstroom voor incidentrespons voor Microsoft 365":::

<span data-ttu-id="4e911-152">Identificeer doorlopend de incidenten met de hoogste prioriteit voor analyse en oplossing in de incidentwachtrij en maak ze klaar voor reactie.</span><span class="sxs-lookup"><span data-stu-id="4e911-152">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="4e911-153">Dit is een combinatie van:</span><span class="sxs-lookup"><span data-stu-id="4e911-153">This is a combination of:</span></span>

- <span data-ttu-id="4e911-154">[Triaging](incident-queue.md) om de incidenten met de hoogste prioriteit te bepalen door de wachtrij voor incidenten te filteren en te sorteren.</span><span class="sxs-lookup"><span data-stu-id="4e911-154">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="4e911-155">[U](manage-incidents.md) kunt incidenten beheren door de titel te wijzigen, deze toe te wijzen aan een analist en tags en opmerkingen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="4e911-155">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="4e911-156">Voor elk incident start u een [aanval en een waarschuwingsonderzoek en -analyse:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="4e911-156">For each incident, begin an [attack and alert investigation and analysis](investigate-incidents.md):</span></span>
 
   1. <span data-ttu-id="4e911-157">Bekijk de samenvatting van het incident om te begrijpen wat het bereik en de ernst is en welke entiteiten worden beïnvloed (het **tabblad** Overzicht).</span><span class="sxs-lookup"><span data-stu-id="4e911-157">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   1. <span data-ttu-id="4e911-158">Begin met het analyseren van de waarschuwingen om de herkomst, het bereik en de ernst ervan te begrijpen (het **tabblad** Waarschuwingen).</span><span class="sxs-lookup"><span data-stu-id="4e911-158">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   1. <span data-ttu-id="4e911-159">Verzamel zo nodig informatie over beïnvloede apparaten, gebruikers en postvakken **(de** tabbladen **Apparaten,** Gebruikers en **Postvakken).**</span><span class="sxs-lookup"><span data-stu-id="4e911-159">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   1. <span data-ttu-id="4e911-160">Bekijk hoe Microsoft 365 Defender [waarschuwingen automatisch](m365d-autoir.md) heeft opgelost (het **tabblad** Onderzoeken).</span><span class="sxs-lookup"><span data-stu-id="4e911-160">See how Microsoft 365 Defender has [automatically resolved some alerts](m365d-autoir.md) (the **Investigations** tab).</span></span>
   
   1. <span data-ttu-id="4e911-161">Gebruik zo nodig informatie in de gegevensset voor het incident voor meer informatie (het **tabblad Bewijs en** antwoord).</span><span class="sxs-lookup"><span data-stu-id="4e911-161">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="4e911-162">Voer na of tijdens uw analyse insluiting uit om eventuele extra gevolgen van de aanval en de uitbanning van de beveiligingsrisico's te beperken.</span><span class="sxs-lookup"><span data-stu-id="4e911-162">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="4e911-163">Herstel zoveel mogelijk van de aanval door de tenantbronnen te herstellen in de status waarin ze zich vóór het incident hebben voordeden.</span><span class="sxs-lookup"><span data-stu-id="4e911-163">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="4e911-164">[Los](manage-incidents.md#resolve-an-incident) het incident op en neem de tijd om na het incident te leren:</span><span class="sxs-lookup"><span data-stu-id="4e911-164">[Resolve](manage-incidents.md#resolve-an-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="4e911-165">Inzicht in het type van de aanval en de impact ervan.</span><span class="sxs-lookup"><span data-stu-id="4e911-165">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="4e911-166">Onderzoek de aanval in [Threat Analytics](threat-analytics.md) en de beveiligingsgemeenschap voor een beveiligingsaanvaltrend.</span><span class="sxs-lookup"><span data-stu-id="4e911-166">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="4e911-167">De werkstroom inroepen die u hebt gebruikt om het incident op te lossen en uw standaardwerkstromen, processen, beleidsregels en playbooks zo nodig bij te werken.</span><span class="sxs-lookup"><span data-stu-id="4e911-167">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="4e911-168">Bepaal of wijzigingen in uw beveiligingsconfiguratie nodig zijn en implementeert deze.</span><span class="sxs-lookup"><span data-stu-id="4e911-168">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="4e911-169">Als u nog niet bekend bent met beveiligingsanalyse, bekijkt u de inleiding tot het reageren op uw eerste [incident](incidents-overview.md) voor meer informatie en een voorbeeldincident door te nemen.</span><span class="sxs-lookup"><span data-stu-id="4e911-169">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

<span data-ttu-id="4e911-170">Zie dit artikel voor meer informatie over de reactie op incidenten [in Microsoft-producten.](/security/compass/incident-response-overview)</span><span class="sxs-lookup"><span data-stu-id="4e911-170">For more information about incident response across Microsoft products, see [this article](/security/compass/incident-response-overview).</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="4e911-171">Voorbeeld van beveiligingsbewerkingen voor Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e911-171">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="4e911-172">Hier volgen een voorbeeld van beveiligingsbewerkingen (SecOps) voor Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4e911-172">Here's an example of security operations (SecOps) for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Een voorbeeld van beveiligingsbewerkingen voor Microsoft 365 Defender":::

<span data-ttu-id="4e911-174">Dagelijkse taken kunnen bestaan uit:</span><span class="sxs-lookup"><span data-stu-id="4e911-174">Daily tasks can include:</span></span>

- <span data-ttu-id="4e911-175">[Incidenten](manage-incidents.md) beheren</span><span class="sxs-lookup"><span data-stu-id="4e911-175">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="4e911-176">Acties voor [automatisch onderzoek en antwoord (AIR)](m365d-action-center.md) bekijken in het Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="4e911-176">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions in the Action center</span></span>
- <span data-ttu-id="4e911-177">De meest recente [Threat Analytics bekijken](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="4e911-177">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="4e911-178">[Reageren op](investigate-incidents.md) incidenten</span><span class="sxs-lookup"><span data-stu-id="4e911-178">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="4e911-179">Maandelijkse taken kunnen bestaan uit:</span><span class="sxs-lookup"><span data-stu-id="4e911-179">Monthly tasks can include:</span></span>

- <span data-ttu-id="4e911-180">[Air-instellingen controleren](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="4e911-180">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="4e911-181">Secure [Score and](microsoft-secure-score-improvement-actions.md) [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="4e911-181">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="4e911-182">Rapporteren aan uw IT-beveiligingsbeheerketen</span><span class="sxs-lookup"><span data-stu-id="4e911-182">Reporting to your IT security management chain</span></span>

<span data-ttu-id="4e911-183">Driemaandelijkse taken kunnen een rapport en een briefing van beveiligingsresultaten bevatten aan de Ciso (Chief Information Security Officer).</span><span class="sxs-lookup"><span data-stu-id="4e911-183">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="4e911-184">Jaarlijkse taken kunnen bestaan uit het uitvoeren van een grote incident- of inbreukoefening om uw personeel, systemen en processen te testen.</span><span class="sxs-lookup"><span data-stu-id="4e911-184">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="4e911-185">Dagelijkse, maandelijkse, kwartaal- en jaarlijkse taken kunnen worden gebruikt om processen, beleidsregels en beveiligingsconfiguraties bij te werken of te verfijnen.</span><span class="sxs-lookup"><span data-stu-id="4e911-185">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

### <a name="secops-resources-across-microsoft-products"></a><span data-ttu-id="4e911-186">SecOps-resources voor Microsoft-producten</span><span class="sxs-lookup"><span data-stu-id="4e911-186">SecOps resources across Microsoft products</span></span>

<span data-ttu-id="4e911-187">Zie de volgende bronnen voor meer informatie over SecOps voor alle Microsoft-producten:</span><span class="sxs-lookup"><span data-stu-id="4e911-187">For more information about SecOps across Microsoft's products, see these resources:</span></span>

- [<span data-ttu-id="4e911-188">Mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="4e911-188">Capabilities</span></span>](/security/compass/security-operations-capabilities)
- [<span data-ttu-id="4e911-189">Aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="4e911-189">Best practices</span></span>](/security/compass/security-operations)
- [<span data-ttu-id="4e911-190">Video's en dia's</span><span class="sxs-lookup"><span data-stu-id="4e911-190">Videos and slides</span></span>](/security/compass/security-operations-videos-and-decks)

## <a name="next-steps"></a><span data-ttu-id="4e911-191">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="4e911-191">Next steps</span></span>

<span data-ttu-id="4e911-192">**Als u nog niet bekend bent** met beveiligingsanalyse en incidentrespons:</span><span class="sxs-lookup"><span data-stu-id="4e911-192">**If you are new** to security analysis and incident response:</span></span>

- <span data-ttu-id="4e911-193">Zie de [walkthrough](first-incident-overview.md) Reageren op uw eerste incident om een rondleiding te krijgen van een typisch proces van analyse, herstel en beoordeling na het incident in de Microsoft 365 Defender portal met een voorbeeldaanval.</span><span class="sxs-lookup"><span data-stu-id="4e911-193">See the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review in the Microsoft 365 Defender portal with an example attack.</span></span>

<span data-ttu-id="4e911-194">**Als u ervaring hebt met** beveiligingsanalyse en incidentrespons:</span><span class="sxs-lookup"><span data-stu-id="4e911-194">**If you have experience** with security analysis and incident response:</span></span>

- <span data-ttu-id="4e911-195">Ga aan de slag met de incidentwachtrij vanaf **de pagina Incidenten** van de Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="4e911-195">Get started with the incident queue from the **Incidents** page of the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="4e911-196">Hier kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="4e911-196">From here, you can:</span></span>

  - <span data-ttu-id="4e911-197">Bekijk welke incidenten prioriteit [moeten krijgen op](incident-queue.md) basis van ernst en andere factoren.</span><span class="sxs-lookup"><span data-stu-id="4e911-197">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 

  - <span data-ttu-id="4e911-198">[Beheer incidenten,](manage-incidents.md)waaronder het wijzigen van de naam, het toewijzen, classificeren en toevoegen van tags en opmerkingen op basis van uw werkstroom voor incidentbeheer.</span><span class="sxs-lookup"><span data-stu-id="4e911-198">[Manage incidents](manage-incidents.md), which includes renaming, assigning, classifying, and adding tags and comments based on your incident management workflow.</span></span>

  - <span data-ttu-id="4e911-199">Voer [onderzoeken van](investigate-incidents.md) incidenten uit.</span><span class="sxs-lookup"><span data-stu-id="4e911-199">Perform [investigations](investigate-incidents.md) of incidents.</span></span>

- <span data-ttu-id="4e911-200">Bekijk deze [playbooks voor incidentreacties](/security/compass/incident-response-playbooks) voor gedetailleerde richtlijnen voor phishing- en wachtwoordincidenten en app-toestemmingsverleningsaanvallen.</span><span class="sxs-lookup"><span data-stu-id="4e911-200">See these [incident response playbooks](/security/compass/incident-response-playbooks) for detailed guidance for phishing, password spray, and app consent grant attacks.</span></span>

