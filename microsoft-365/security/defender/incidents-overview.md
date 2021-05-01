---
title: Incidenten in Microsoft 365 Defender
description: Onderzoek incidenten die worden gezien op verschillende apparaten, gebruikers en postvakken in het Microsoft 365 beveiligingscentrum.
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
ms.openlocfilehash: e2e29015d4cb5e04510577118eb847b9b596a6c5
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114280"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="513ad-104">Incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="513ad-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="513ad-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="513ad-105">**Applies to:**</span></span>
- <span data-ttu-id="513ad-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="513ad-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="513ad-107">Wilt u Microsoft 365 Defender ervaren?</span><span class="sxs-lookup"><span data-stu-id="513ad-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="513ad-108">U kunt het [evalueren in een testomgeving](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) of [uw pilotproject uitvoeren in een productieomgeving](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="513ad-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="513ad-109">Een incident in Microsoft 365 Defender is een verzameling gecorreleerde waarschuwingen en bijbehorende gegevens die het verhaal van een aanval bevatten.</span><span class="sxs-lookup"><span data-stu-id="513ad-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="513ad-110">Microsoft 365 services en apps maken waarschuwingen wanneer ze een verdachte of schadelijke gebeurtenis of activiteit detecteren.</span><span class="sxs-lookup"><span data-stu-id="513ad-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="513ad-111">Afzonderlijke waarschuwingen geven waardevolle aanwijzingen over een voltooide of lopende aanval.</span><span class="sxs-lookup"><span data-stu-id="513ad-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="513ad-112">Aanvallen gebruiken echter meestal verschillende technieken voor verschillende typen entiteiten, zoals apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="513ad-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="513ad-113">Het resultaat is meerdere waarschuwingen voor meerdere entiteiten in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="513ad-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="513ad-114">Omdat het lastig en tijdrovend kan zijn om de afzonderlijke waarschuwingen samen te cirkelen om inzicht te krijgen in een aanval, worden de waarschuwingen en de bijbehorende informatie automatisch samengevoegd tot een incident door Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="513ad-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Hoe Microsoft 365 Defender gebeurtenissen van entiteiten correleert in een incident":::

<span data-ttu-id="513ad-116">Bekijk dit korte overzicht van incidenten in Microsoft 365 Defender (4 minuten).</span><span class="sxs-lookup"><span data-stu-id="513ad-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="513ad-117">Door gerelateerde waarschuwingen in een incident te groeperen, krijgt u een uitgebreide weergave van een aanval.</span><span class="sxs-lookup"><span data-stu-id="513ad-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="513ad-118">U kunt bijvoorbeeld het volgende zien:</span><span class="sxs-lookup"><span data-stu-id="513ad-118">For example, you can see:</span></span>

- <span data-ttu-id="513ad-119">Waar de aanval is begonnen.</span><span class="sxs-lookup"><span data-stu-id="513ad-119">Where the attack started.</span></span>
- <span data-ttu-id="513ad-120">Welke tactieken zijn gebruikt.</span><span class="sxs-lookup"><span data-stu-id="513ad-120">What tactics were used.</span></span>
- <span data-ttu-id="513ad-121">Hoe ver de aanval is gegaan in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="513ad-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="513ad-122">Het bereik van de aanval, zoals het aantal apparaten, gebruikers en postvakken dat is beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="513ad-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="513ad-123">Alle gegevens die aan de aanval zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="513ad-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="513ad-124">Als [dit is ingeschakeld,](m365d-enable.md)Microsoft 365 Defender waarschuwingen automatisch onderzoeken en oplossen via automatisering en kunstmatige intelligentie.</span><span class="sxs-lookup"><span data-stu-id="513ad-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="513ad-125">U kunt ook aanvullende herstelstappen uitvoeren om de aanval op te lossen.</span><span class="sxs-lookup"><span data-stu-id="513ad-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="513ad-126">Incidenten en waarschuwingen in het Microsoft 365 beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="513ad-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="513ad-127">U beheert incidenten van **incidenten & waarschuwingen > incidenten** tijdens de snelle start van het Microsoft 365 beveiligingscentrum [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="513ad-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="513ad-128">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="513ad-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="De pagina Incidenten in het Microsoft 365 beveiligingscentrum":::

<span data-ttu-id="513ad-130">Als u een incidentnaam selecteert, wordt een overzicht van het incident weergegeven en krijgt u toegang tot tabbladen met aanvullende informatie.</span><span class="sxs-lookup"><span data-stu-id="513ad-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Voorbeeld van de pagina Overzicht voor een incident in het Microsoft 365 beveiligingscentrum":::

<span data-ttu-id="513ad-132">De extra tabbladen voor een incident zijn:</span><span class="sxs-lookup"><span data-stu-id="513ad-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="513ad-133">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="513ad-133">Alerts</span></span> 

  <span data-ttu-id="513ad-134">Alle waarschuwingen met betrekking tot het incident en de bijbehorende informatie.</span><span class="sxs-lookup"><span data-stu-id="513ad-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="513ad-135">Apparaten</span><span class="sxs-lookup"><span data-stu-id="513ad-135">Devices</span></span>

  <span data-ttu-id="513ad-136">Alle apparaten die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.</span><span class="sxs-lookup"><span data-stu-id="513ad-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="513ad-137">Gebruikers</span><span class="sxs-lookup"><span data-stu-id="513ad-137">Users</span></span>

  <span data-ttu-id="513ad-138">Alle gebruikers die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.</span><span class="sxs-lookup"><span data-stu-id="513ad-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="513ad-139">Postvakken</span><span class="sxs-lookup"><span data-stu-id="513ad-139">Mailboxes</span></span>

  <span data-ttu-id="513ad-140">Alle postvakken die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.</span><span class="sxs-lookup"><span data-stu-id="513ad-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="513ad-141">Onderzoeken</span><span class="sxs-lookup"><span data-stu-id="513ad-141">Investigations</span></span>

  <span data-ttu-id="513ad-142">Alle automatische onderzoeken die worden veroorzaakt door waarschuwingen bij het incident.</span><span class="sxs-lookup"><span data-stu-id="513ad-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="513ad-143">Bewijs en antwoord</span><span class="sxs-lookup"><span data-stu-id="513ad-143">Evidence and Response</span></span>

  <span data-ttu-id="513ad-144">Alle ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen in het incident.</span><span class="sxs-lookup"><span data-stu-id="513ad-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="513ad-145">Hier is de relatie tussen een incident en de gegevens en de tabbladen van een incident in het Microsoft 365 beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="513ad-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="De relatie van een incident en de gegevens ervan met de tabbladen van een incident in het Microsoft 365 beveiligingscentrum":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="513ad-147">Voorbeeld van de werkstroom incidentrespons voor Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="513ad-147">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="513ad-148">Hier is een voorbeeldwerkstroom voor het reageren op incidenten in Microsoft 365 met het Microsoft 365 beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="513ad-148">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Voorbeeld van een werkstroom voor incidentrespons voor Microsoft 365":::

<span data-ttu-id="513ad-150">Identificeer doorlopend de incidenten met de hoogste prioriteit voor analyse en oplossing in de incidentwachtrij en maak ze klaar voor reactie.</span><span class="sxs-lookup"><span data-stu-id="513ad-150">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="513ad-151">Dit is een combinatie van:</span><span class="sxs-lookup"><span data-stu-id="513ad-151">This is a combination of:</span></span>

- <span data-ttu-id="513ad-152">[Triaging](incident-queue.md) om de incidenten met de hoogste prioriteit te bepalen door de wachtrij voor incidenten te filteren en te sorteren.</span><span class="sxs-lookup"><span data-stu-id="513ad-152">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="513ad-153">[U](manage-incidents.md) kunt incidenten beheren door de titel te wijzigen, deze toe te wijzen aan een analist en tags en opmerkingen toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="513ad-153">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="513ad-154">Voor elk incident start u een [aanvals- en waarschuwingsanalyse:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="513ad-154">For each incident, begin an [attack and alert analysis](investigate-incidents.md):</span></span>
 
   <span data-ttu-id="513ad-155">a.</span><span class="sxs-lookup"><span data-stu-id="513ad-155">a.</span></span> <span data-ttu-id="513ad-156">Bekijk de samenvatting van het incident om te begrijpen wat het bereik en de ernst is en welke entiteiten worden beïnvloed (het **tabblad** Overzicht).</span><span class="sxs-lookup"><span data-stu-id="513ad-156">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="513ad-157">b.</span><span class="sxs-lookup"><span data-stu-id="513ad-157">b.</span></span> <span data-ttu-id="513ad-158">Begin met het analyseren van de waarschuwingen om de herkomst, het bereik en de ernst ervan te begrijpen (het **tabblad** Waarschuwingen).</span><span class="sxs-lookup"><span data-stu-id="513ad-158">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="513ad-159">c.</span><span class="sxs-lookup"><span data-stu-id="513ad-159">c.</span></span> <span data-ttu-id="513ad-160">Verzamel zo nodig informatie over beïnvloede apparaten, gebruikers en postvakken **(de** tabbladen **Apparaten,** Gebruikers en **Postvakken).**</span><span class="sxs-lookup"><span data-stu-id="513ad-160">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="513ad-161">d.</span><span class="sxs-lookup"><span data-stu-id="513ad-161">d.</span></span> <span data-ttu-id="513ad-162">Bekijk hoe Microsoft 365 meldingen automatisch heeft opgelost (het **tabblad** Onderzoeken).</span><span class="sxs-lookup"><span data-stu-id="513ad-162">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="513ad-163">e.</span><span class="sxs-lookup"><span data-stu-id="513ad-163">e.</span></span> <span data-ttu-id="513ad-164">Gebruik zo nodig informatie in de gegevensset voor het incident voor meer informatie (het **tabblad Bewijs en** antwoord).</span><span class="sxs-lookup"><span data-stu-id="513ad-164">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="513ad-165">Voer na of tijdens uw analyse insluiting uit om eventuele extra gevolgen van de aanval en de uitbanning van de beveiligingsrisico's te beperken.</span><span class="sxs-lookup"><span data-stu-id="513ad-165">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="513ad-166">Herstel zoveel mogelijk van de aanval door de tenantbronnen te herstellen in de status waarin ze zich vóór het incident hebben voordeden.</span><span class="sxs-lookup"><span data-stu-id="513ad-166">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="513ad-167">[Los](manage-incidents.md#resolve-incident) het incident op en neem de tijd om na het incident te leren:</span><span class="sxs-lookup"><span data-stu-id="513ad-167">[Resolve](manage-incidents.md#resolve-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="513ad-168">Inzicht in het type van de aanval en de impact ervan.</span><span class="sxs-lookup"><span data-stu-id="513ad-168">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="513ad-169">Onderzoek de aanval in [Threat Analytics](threat-analytics.md) en de beveiligingsgemeenschap voor een beveiligingsaanvaltrend.</span><span class="sxs-lookup"><span data-stu-id="513ad-169">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="513ad-170">De werkstroom inroepen die u hebt gebruikt om het incident op te lossen en uw standaardwerkstromen, processen, beleidsregels en playbooks zo nodig bij te werken.</span><span class="sxs-lookup"><span data-stu-id="513ad-170">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="513ad-171">Bepaal of wijzigingen in uw beveiligingsconfiguratie nodig zijn en implementeert deze.</span><span class="sxs-lookup"><span data-stu-id="513ad-171">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="513ad-172">Als u nog niet bekend bent met beveiligingsanalyse, bekijkt u de inleiding tot het reageren op uw eerste [incident](incidents-overview.md) voor meer informatie en een voorbeeldincident door te nemen.</span><span class="sxs-lookup"><span data-stu-id="513ad-172">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="513ad-173">Voorbeeld van beveiligingsbewerkingen voor Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="513ad-173">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="513ad-174">Hier volgen een voorbeeld van beveiligingsbewerkingen voor Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="513ad-174">Here's an example of security operations for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Een voorbeeld van beveiligingsbewerkingen voor Micosoft 365 Defender":::

<span data-ttu-id="513ad-176">Dagelijkse taken kunnen bestaan uit:</span><span class="sxs-lookup"><span data-stu-id="513ad-176">Daily tasks can include:</span></span>

- <span data-ttu-id="513ad-177">[Incidenten](manage-incidents.md) beheren</span><span class="sxs-lookup"><span data-stu-id="513ad-177">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="513ad-178">Acties voor [automatisch onderzoek en antwoord (AIR)](m365d-action-center.md) controleren</span><span class="sxs-lookup"><span data-stu-id="513ad-178">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions</span></span>
- <span data-ttu-id="513ad-179">De meest recente [Threat Analytics bekijken](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="513ad-179">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="513ad-180">[Reageren op](investigate-incidents.md) incidenten</span><span class="sxs-lookup"><span data-stu-id="513ad-180">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="513ad-181">Maandelijkse taken kunnen bestaan uit:</span><span class="sxs-lookup"><span data-stu-id="513ad-181">Monthly tasks can include:</span></span>

- <span data-ttu-id="513ad-182">[Air-instellingen controleren](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="513ad-182">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="513ad-183">Secure [Score and](microsoft-secure-score-improvement-actions.md) [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="513ad-183">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="513ad-184">Rapporteren aan uw IT-beveiligingsbeheerketen</span><span class="sxs-lookup"><span data-stu-id="513ad-184">Reporting to your IT security management chain</span></span>

<span data-ttu-id="513ad-185">Driemaandelijkse taken kunnen een rapport en een briefing van beveiligingsresultaten bevatten aan de Ciso (Chief Information Security Officer).</span><span class="sxs-lookup"><span data-stu-id="513ad-185">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="513ad-186">Jaarlijkse taken kunnen bestaan uit het uitvoeren van een grote incident- of inbreukoefening om uw personeel, systemen en processen te testen.</span><span class="sxs-lookup"><span data-stu-id="513ad-186">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="513ad-187">Dagelijkse, maandelijkse, kwartaal- en jaarlijkse taken kunnen worden gebruikt om processen, beleidsregels en beveiligingsconfiguraties bij te werken of te verfijnen.</span><span class="sxs-lookup"><span data-stu-id="513ad-187">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="513ad-188">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="513ad-188">Next steps</span></span>

<span data-ttu-id="513ad-189">De incidentenwachtrij van de pagina **Incidenten** bevat de meest recente incidenten.</span><span class="sxs-lookup"><span data-stu-id="513ad-189">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="513ad-190">Hier kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="513ad-190">From here, you can:</span></span>

- <span data-ttu-id="513ad-191">Bekijk welke incidenten prioriteit [moeten krijgen op](incident-queue.md) basis van ernst en andere factoren.</span><span class="sxs-lookup"><span data-stu-id="513ad-191">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="513ad-192">[Beheer incidenten,](manage-incidents.md)waaronder het wijzigen van de naam, de toewijzing, het classificeren en het toevoegen van tags en opmerkingen voor uw werkstroom voor incidentbeheer.</span><span class="sxs-lookup"><span data-stu-id="513ad-192">[Manage incidents](manage-incidents.md), which includes renaming, assignment, classifying, and adding tags and comments for your incident management workflow.</span></span>
- <span data-ttu-id="513ad-193">Een analyse [van](investigate-incidents.md) een incident uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="513ad-193">Perform an [analysis](investigate-incidents.md) of an incident.</span></span>
