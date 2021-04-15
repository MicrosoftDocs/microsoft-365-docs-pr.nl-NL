---
title: Prioriteit geven aan incidenten in Microsoft 365 Defender
description: Informatie over het filteren van incidenten in de incidentwachtrij in Microsoft 365 Defender
keywords: incident, wachtrij, overzicht, apparaten, identiteiten, gebruikers, postvak, e-mail, incidenten
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
ms.openlocfilehash: 12207d69b0a1565caf762a265c1a0d32158ca291
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759835"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="26d71-104">Prioriteit geven aan incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26d71-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="26d71-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="26d71-105">**Applies to:**</span></span>
- <span data-ttu-id="26d71-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26d71-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="26d71-107">Microsoft 365 Defender past correlatieanalyse toe en verzamelt gerelateerde waarschuwingen en geautomatiseerde onderzoeken van verschillende producten tot een incident.</span><span class="sxs-lookup"><span data-stu-id="26d71-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="26d71-108">Microsoft 365 Defender activeert ook unieke waarschuwingen voor activiteiten die alleen kunnen worden geïdentificeerd als schadelijk, gezien de end-to-end zichtbaarheid die Microsoft 365 Defender heeft voor de hele suite met producten.</span><span class="sxs-lookup"><span data-stu-id="26d71-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="26d71-109">In deze weergave krijgen uw beveiligingsanalisten het bredere verhaal over aanvallen, waarmee ze complexe bedreigingen in uw organisatie beter kunnen begrijpen en kunnen omgaan.</span><span class="sxs-lookup"><span data-stu-id="26d71-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="26d71-110">In **de wachtrij Incident** ziet u een verzameling incidenten die zijn gemaakt op verschillende apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="26d71-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="26d71-111">Het helpt u incidenten te sorteren om prioriteit te geven en een weloverwogen antwoordbesluit voor cyberbeveiliging te maken.</span><span class="sxs-lookup"><span data-stu-id="26d71-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="26d71-112">U komt bij de incidentwachtrij van **Incidenten & waarschuwingen > Incidenten** op de snelle start van het Microsoft 365-beveiligingscentrum [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="26d71-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Voorbeeld van de incidentwachtrij":::

<span data-ttu-id="26d71-114">Standaard worden in de wachtrij in het Microsoft 365-beveiligingscentrum incidenten weergegeven die de afgelopen zes maanden zijn gezien.</span><span class="sxs-lookup"><span data-stu-id="26d71-114">By default, the queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="26d71-115">Het meest recente incident staat bovenaan de lijst, zodat u het eerst kunt zien.</span><span class="sxs-lookup"><span data-stu-id="26d71-115">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="26d71-116">De incidentwachtrij heeft aanpasbare kolommen (selecteer Kolommen **kiezen)** die u inzicht geven in de verschillende kenmerken van het incident of de beïnvloede entiteiten.</span><span class="sxs-lookup"><span data-stu-id="26d71-116">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="26d71-117">Op deze manier kunt u een weloverwogen beslissing nemen over de prioriteit van incidenten voor anaylsis.</span><span class="sxs-lookup"><span data-stu-id="26d71-117">This helps you make an informed decision regarding the prioritization of incidents for anaylsis.</span></span>

<span data-ttu-id="26d71-118">Voor extra zichtbaarheid in één oogopslag worden met automatische naamgeving voor incidenten incidentnamen gegenereerd op basis van waarschuwingskenmerken, zoals het aantal eindpunten dat is beïnvloed, de betreffende gebruikers, detectiebronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="26d71-118">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="26d71-119">Hierdoor kunt u snel inzicht krijgen in het bereik van het incident.</span><span class="sxs-lookup"><span data-stu-id="26d71-119">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="26d71-120">Bijvoorbeeld: *incident met meerdere fases op meerdere eindpunten die door meerdere bronnen zijn gerapporteerd.*</span><span class="sxs-lookup"><span data-stu-id="26d71-120">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="26d71-121">Incidenten die vóór de implementatie van automatische naamgeving voor incidenten hebben bestaan, worden niet gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="26d71-121">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="26d71-122">In de wachtrij voor incidenten worden ook meerdere filteropties beschikbaar, waarmee u, wanneer deze wordt toegepast, alle bestaande incidenten in uw omgeving breed kunt opsnuiven of kunt besluiten zich te concentreren op een specifiek scenario of bedreiging.</span><span class="sxs-lookup"><span data-stu-id="26d71-122">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="26d71-123">Door filters toe te passen op de incidentwachtrij, kan worden bepaald welk incident direct aandacht nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="26d71-123">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="26d71-124">Beschikbare filters</span><span class="sxs-lookup"><span data-stu-id="26d71-124">Available filters</span></span>

<span data-ttu-id="26d71-125">In de standaardwachtrij voor incidenten kunt u **Filters** selecteren om een deelvenster Filters weer te geven, waaruit u een gefilterde reeks incidenten kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="26d71-125">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="26d71-126">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="26d71-126">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Voorbeeld van het filtervenster voor de incidentwachtrij":::

<span data-ttu-id="26d71-128">In deze tabel worden de filternamen vermeld die beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="26d71-128">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="26d71-129">Filternaam</span><span class="sxs-lookup"><span data-stu-id="26d71-129">Filter name</span></span> | <span data-ttu-id="26d71-130">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="26d71-130">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="26d71-131">Toegewezen aan</span><span class="sxs-lookup"><span data-stu-id="26d71-131">Assigned to</span></span> | <span data-ttu-id="26d71-132">U kunt ervoor kiezen om waarschuwingen weer te geven die aan u zijn toegewezen of waarschuwingen die door automatisering worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="26d71-132">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="26d71-133">Categorieën</span><span class="sxs-lookup"><span data-stu-id="26d71-133">Categories</span></span> | <span data-ttu-id="26d71-134">Kies categorieën om zich te richten op specifieke tactieken, technieken of aanvalsonderdelen.</span><span class="sxs-lookup"><span data-stu-id="26d71-134">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="26d71-135">Classificatie</span><span class="sxs-lookup"><span data-stu-id="26d71-135">Classification</span></span> | <span data-ttu-id="26d71-136">Filter incidenten op basis van de setclassificaties van de gerelateerde waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="26d71-136">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="26d71-137">De waarden omvatten waar waarschuwingen, onwaar waarschuwingen of niet ingesteld.</span><span class="sxs-lookup"><span data-stu-id="26d71-137">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="26d71-138">Gegevensgevoeligheid</span><span class="sxs-lookup"><span data-stu-id="26d71-138">Data sensitivity</span></span> | <span data-ttu-id="26d71-139">Sommige aanvallen richten zich op targeting om gevoelige of waardevolle gegevens te exfiltreren.</span><span class="sxs-lookup"><span data-stu-id="26d71-139">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="26d71-140">Door een filter toe te passen om te zien of er gevoelige gegevens bij het incident betrokken zijn, kunt u snel bepalen of gevoelige informatie mogelijk is gehackt en kunt u prioriteit geven aan het oplossen van deze incidenten.</span><span class="sxs-lookup"><span data-stu-id="26d71-140">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="26d71-141">Alleen van toepassing als Microsoft Information Protection is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="26d71-141">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="26d71-142">Apparaatgroep</span><span class="sxs-lookup"><span data-stu-id="26d71-142">Device group</span></span> | <span data-ttu-id="26d71-143">Filteren op gedefinieerde apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="26d71-143">Filter by defined device groups.</span></span> |
| <span data-ttu-id="26d71-144">Onderzoekstoestand</span><span class="sxs-lookup"><span data-stu-id="26d71-144">Investigation state</span></span> | <span data-ttu-id="26d71-145">Filter incidenten op basis van de status van automatisch onderzoek.</span><span class="sxs-lookup"><span data-stu-id="26d71-145">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="26d71-146">Meerdere categorieën</span><span class="sxs-lookup"><span data-stu-id="26d71-146">Multiple categories</span></span> | <span data-ttu-id="26d71-147">U kunt ervoor kiezen om alleen incidenten te zien die zijn toegesneden op meerdere categorieën en zo mogelijk meer schade kunnen veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="26d71-147">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="26d71-148">Meerdere servicebronnen</span><span class="sxs-lookup"><span data-stu-id="26d71-148">Multiple service sources</span></span>  | <span data-ttu-id="26d71-149">Filter om alleen incidenten te zien die waarschuwingen uit verschillende bronnen bevatten (Microsoft Defender voor Eindpunt, Microsoft Cloud App-beveiliging, Microsoft Defender voor identiteit, Microsoft Defender voor Office 365).</span><span class="sxs-lookup"><span data-stu-id="26d71-149">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="26d71-150">BESTURINGSSYSTEEM-platform</span><span class="sxs-lookup"><span data-stu-id="26d71-150">OS platform</span></span> | <span data-ttu-id="26d71-151">Beperk de weergave van de incidentwachtrij per besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="26d71-151">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="26d71-152">Servicebronnen</span><span class="sxs-lookup"><span data-stu-id="26d71-152">Service sources</span></span> | <span data-ttu-id="26d71-153">Door een specifieke bron te kiezen, kunt u zich richten op incidenten die ten minste één waarschuwing uit die gekozen bron bevatten.</span><span class="sxs-lookup"><span data-stu-id="26d71-153">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="26d71-154">Ernst</span><span class="sxs-lookup"><span data-stu-id="26d71-154">Severity</span></span> | <span data-ttu-id="26d71-155">De ernst van een incident is een indicatie van de invloed die het kan hebben op uw activa.</span><span class="sxs-lookup"><span data-stu-id="26d71-155">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="26d71-156">Hoe hoger de ernst, hoe groter de impact en meestal de meest directe aandacht.</span><span class="sxs-lookup"><span data-stu-id="26d71-156">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="26d71-157">Status</span><span class="sxs-lookup"><span data-stu-id="26d71-157">Status</span></span> | <span data-ttu-id="26d71-158">U kunt ervoor kiezen om de lijst met weergegeven incidenten te beperken op basis van hun status om te zien welke actief of opgelost zijn.</span><span class="sxs-lookup"><span data-stu-id="26d71-158">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="incident-response-workflow"></a><span data-ttu-id="26d71-159">Werkstroom voor incidentrespons</span><span class="sxs-lookup"><span data-stu-id="26d71-159">Incident response workflow</span></span>

<span data-ttu-id="26d71-160">Hier is de gebruikelijke werkstroom voor het reageren op incidenten:</span><span class="sxs-lookup"><span data-stu-id="26d71-160">Here is the typical workflow for responding to incidents:</span></span>

1. <span data-ttu-id="26d71-161">Identificeer en triage de incidenten met de hoogste prioriteit voor onderzoek en oplossing.</span><span class="sxs-lookup"><span data-stu-id="26d71-161">Identify and triage the highest priority incidents for investigation and resolution.</span></span>
2. <span data-ttu-id="26d71-162">Voor elk incident met hoge prioriteit start u een [onderzoek:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="26d71-162">For each high-priority incident, begin an [investigation](investigate-incidents.md):</span></span>

   <span data-ttu-id="26d71-163">a.</span><span class="sxs-lookup"><span data-stu-id="26d71-163">a.</span></span> <span data-ttu-id="26d71-164">Bekijk de samenvatting van het incident om te begrijpen wat het bereik is, welke entiteiten worden beïnvloed en de ernst (het **tabblad** Overzicht).</span><span class="sxs-lookup"><span data-stu-id="26d71-164">View the summary of the incident to understand it's scope, what entities are affected, and severity (the **Summary** tab).</span></span>

   <span data-ttu-id="26d71-165">b.</span><span class="sxs-lookup"><span data-stu-id="26d71-165">b.</span></span> <span data-ttu-id="26d71-166">Kijk eerst naar de waarschuwingen om de herkomst, het bereik en de ernst ervan te begrijpen (het **tabblad** Waarschuwingen).</span><span class="sxs-lookup"><span data-stu-id="26d71-166">Begin looking at the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="26d71-167">c.</span><span class="sxs-lookup"><span data-stu-id="26d71-167">c.</span></span> <span data-ttu-id="26d71-168">Verzamel zo nodig informatie over beïnvloede apparaten, gebruikers en postvakken **(de** tabbladen **Apparaten,** Gebruikers en **Postvakken).**</span><span class="sxs-lookup"><span data-stu-id="26d71-168">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="26d71-169">d.</span><span class="sxs-lookup"><span data-stu-id="26d71-169">d.</span></span> <span data-ttu-id="26d71-170">Bekijk hoe Microsoft 365 Defender bepaalde waarschuwingen automatisch heeft opgelost (het **tabblad** Onderzoeken).</span><span class="sxs-lookup"><span data-stu-id="26d71-170">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="26d71-171">e.</span><span class="sxs-lookup"><span data-stu-id="26d71-171">e.</span></span> <span data-ttu-id="26d71-172">Gebruik zo nodig informatie in de gegevensset voor het incident voor meer informatie (het **tabblad Bewijs en** antwoord).</span><span class="sxs-lookup"><span data-stu-id="26d71-172">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

<span data-ttu-id="26d71-173">Terwijl u onderzoek doet, moet u zich zorgen maken over:</span><span class="sxs-lookup"><span data-stu-id="26d71-173">As you investigate, you should be concerned with:</span></span>

- <span data-ttu-id="26d71-174">Containment: Het verminderen van eventuele extra gevolgen voor uw tenant.</span><span class="sxs-lookup"><span data-stu-id="26d71-174">Containment: Reducing any additional impact on your tenant.</span></span>
- <span data-ttu-id="26d71-175">Verwijdering: het verwijderen van de beveiligingsrisico's.</span><span class="sxs-lookup"><span data-stu-id="26d71-175">Eradication: Removing the security threat.</span></span>
- <span data-ttu-id="26d71-176">Herstel: Herstel de tenantbronnen naar de status waarin ze zich vóór de aanval hadden.</span><span class="sxs-lookup"><span data-stu-id="26d71-176">Recovery: Restoring your tenant resources to the state they were in before the attack.</span></span>

<span data-ttu-id="26d71-177">Nadat u het incident hebt opgelost, neemt u even de tijd om er van te leren:</span><span class="sxs-lookup"><span data-stu-id="26d71-177">After you resolve the incident, take a moment to learn from it to:</span></span>

- <span data-ttu-id="26d71-178">Inzicht in het type van de aanval en de impact ervan.</span><span class="sxs-lookup"><span data-stu-id="26d71-178">Understand the type of the attack and its impact.</span></span>
- <span data-ttu-id="26d71-179">Onderzoek de aanval in de beveiligingsgemeenschap op een beveiligingsaanvaltrend.</span><span class="sxs-lookup"><span data-stu-id="26d71-179">Research the attack in the security community for a security attack trend.</span></span>
- <span data-ttu-id="26d71-180">De werkstroom inroepen die u hebt gebruikt om het incident op te lossen en uw standaardwerkstromen en plalbooks zo nodig bij te werken.</span><span class="sxs-lookup"><span data-stu-id="26d71-180">Recall the workflow you used to resolve the incident and update your standard workflows and plalbooks as needed.</span></span>

<span data-ttu-id="26d71-181">Hier volgt een overzicht van het basisproces.</span><span class="sxs-lookup"><span data-stu-id="26d71-181">Here's a summary of the basic process.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="Het basisproces voor het onderzoeken van incidenten":::

## <a name="next-step"></a><span data-ttu-id="26d71-183">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="26d71-183">Next step</span></span>

<span data-ttu-id="26d71-184">Nadat u hebt bepaald welk incident de hoogste prioriteit vereist, selecteert u het en begint u uw [onderzoek.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="26d71-184">After you've determined which incident requires the highest priority, select it and begin your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="26d71-185">Zie ook</span><span class="sxs-lookup"><span data-stu-id="26d71-185">See also</span></span>
- [<span data-ttu-id="26d71-186">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="26d71-186">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="26d71-187">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="26d71-187">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="26d71-188">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="26d71-188">Manage incidents</span></span>](manage-incidents.md)
