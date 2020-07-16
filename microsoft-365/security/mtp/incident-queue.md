---
title: Prioriteit geven aan incidenten in Microsoft Threat Protection
description: Meer informatie over het prioriteren van incidenten vanuit de wachtrij voor incidenten in Microsoft Threat Protection
keywords: incident, wachtrij, overzicht, apparaten, identiteiten, gebruikers, postvak, e-mail, incidenten
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
ms.openlocfilehash: d827484a440b291bccd45b58e977fbcb280680f2
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148134"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="7e20f-104">Prioriteit geven aan incidenten in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7e20f-104">Prioritize incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="7e20f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7e20f-105">**Applies to:**</span></span>
- <span data-ttu-id="7e20f-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7e20f-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="7e20f-107">Microsoft Threat Protection past correlatieanalyses toe en verzamelt alle gerelateerde waarschuwingen en onderzoeken van verschillende producten in één incident.</span><span class="sxs-lookup"><span data-stu-id="7e20f-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="7e20f-108">Microsoft Threat Protection activeert ook unieke waarschuwingen over activiteiten die alleen als kwaadaardig kunnen worden geïdentificeerd, gezien de end-to-end zichtbaarheid die Microsoft Threat Protection heeft over het hele landgoed en een reeks producten.</span><span class="sxs-lookup"><span data-stu-id="7e20f-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="7e20f-109">Door dit te doen, Microsoft Threat Protection vertelt de bredere aanval verhaal, waardoor een security operations analist te begrijpen en omgaan met complexe bedreigingen in de hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="7e20f-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="7e20f-110">In **de wachtrij Incidenten** wordt een verzameling incidenten weergegeven die zijn gemarkeerd vanaf verschillende apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="7e20f-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="7e20f-111">Het helpt u bij het sorteren van incidenten om prioriteit te geven en een weloverwogen beslissing over cyberbeveiliging te creëren.</span><span class="sxs-lookup"><span data-stu-id="7e20f-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Afbeelding van incidentenwachtrij](../../media/incidents-queue.png) 

<span data-ttu-id="7e20f-113">Standaard wordt in de wachtrij in het Microsoft 365-beveiligingscentrum incidenten weergegeven die in de afgelopen 30 dagen zijn gezien, waarbij het meest recente incident bovenaan de lijst wordt weergegeven, zodat u eerst de meest recente incidenten zien.</span><span class="sxs-lookup"><span data-stu-id="7e20f-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="7e20f-114">De incidentwachtrij stelt aanpasbare kolommen bloot die u inzicht geven in verschillende kenmerken van het incident of de opgenomen entiteiten, zodat u een weloverwogen beslissing nemen over prioritering van incidenten die moeten worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="7e20f-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="7e20f-115">Voor extra zichtbaarheid in één oogopslag genereert automatische incidentnaamgeving, die momenteel in openbare preview is, incidentnamen op basis van waarschuwingskenmerken, zoals het aantal getroffen eindpunten, de getroffen gebruikers, detectiebronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="7e20f-115">For additional visibility at-a-glance, automatic incident naming, currently in public preview, generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="7e20f-116">Hierdoor u snel inzicht krijgen in de omvang van het incident.</span><span class="sxs-lookup"><span data-stu-id="7e20f-116">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="7e20f-117">Bijvoorbeeld: *Multi-stage incident op meerdere eindpunten gerapporteerd door meerdere bronnen.*</span><span class="sxs-lookup"><span data-stu-id="7e20f-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="7e20f-118">Incidenten die vóór de uitrol van automatische incidentnaamgeving bestonden, worden niet gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="7e20f-118">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="7e20f-119">Meer informatie over [het inschakelen van voorbeeldfuncties](preview.md#turn-on-preview-features).</span><span class="sxs-lookup"><span data-stu-id="7e20f-119">Learn more about [turning on preview features](preview.md#turn-on-preview-features).</span></span>

<span data-ttu-id="7e20f-120">De incidentwachtrij stelt ook meerdere filteropties bloot, waarmee u, wanneer deze wordt toegepast, kiezen om een breed onderzoek uit te voeren van alle bestaande incidenten in uw omgeving, of besluit zich te concentreren op een specifiek scenario of bedreiging.</span><span class="sxs-lookup"><span data-stu-id="7e20f-120">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="7e20f-121">Het toepassen van filters op de incidentwachtrij kan helpen bepalen welk incident onmiddellijke aandacht vereist.</span><span class="sxs-lookup"><span data-stu-id="7e20f-121">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="7e20f-122">Beschikbare filters</span><span class="sxs-lookup"><span data-stu-id="7e20f-122">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="7e20f-123">Status</span><span class="sxs-lookup"><span data-stu-id="7e20f-123">Status</span></span>
<span data-ttu-id="7e20f-124">U ervoor kiezen om de lijst met weergegeven incidenten te beperken op basis van hun status om te zien welke incidenten actief of opgelost zijn.</span><span class="sxs-lookup"><span data-stu-id="7e20f-124">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="7e20f-125">Ernst</span><span class="sxs-lookup"><span data-stu-id="7e20f-125">Severity</span></span>
<span data-ttu-id="7e20f-126">De ernst van een incident is indicatief voor de impact die het kan hebben in uw activa.</span><span class="sxs-lookup"><span data-stu-id="7e20f-126">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="7e20f-127">Hoe hoger de ernst, hoe groter de impact en vereist meestal de meest directe aandacht.</span><span class="sxs-lookup"><span data-stu-id="7e20f-127">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="7e20f-128">Toegewezen aan (eigenaar)</span><span class="sxs-lookup"><span data-stu-id="7e20f-128">Assigned to (owner)</span></span>
<span data-ttu-id="7e20f-129">U ervoor kiezen om de lijst te filteren door toegewezen te selecteren aan iedereen of degenen die aan u zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="7e20f-129">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="7e20f-130">Meerdere waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="7e20f-130">Multiple alerts</span></span> 
<span data-ttu-id="7e20f-131">Filter alleen incidenten met meer dan één waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="7e20f-131">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="7e20f-132">Dit kan een indicatie zijn voor een aanval die complexer is of vorderde in de kill chain.</span><span class="sxs-lookup"><span data-stu-id="7e20f-132">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="7e20f-133">Meerdere servicebronnen</span><span class="sxs-lookup"><span data-stu-id="7e20f-133">Multiple service sources</span></span> 
<span data-ttu-id="7e20f-134">Filter alleen om incidenten te zien die waarschuwingen uit verschillende bronnen bevatten (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="7e20f-134">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="7e20f-135">Servicebronnen</span><span class="sxs-lookup"><span data-stu-id="7e20f-135">Service sources</span></span>
<span data-ttu-id="7e20f-136">Door een specifieke bron te kiezen, u zich richten op incidenten die ten minste één waarschuwing van die gekozen bron bevatten.</span><span class="sxs-lookup"><span data-stu-id="7e20f-136">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="7e20f-137">Meerdere rubrieken</span><span class="sxs-lookup"><span data-stu-id="7e20f-137">Multiple categories</span></span> 
<span data-ttu-id="7e20f-138">U ervoor kiezen om alleen incidenten te zien die zijn toegewezen aan meerdere categorieën van de kill chain en mogelijk meer schade kunnen veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="7e20f-138">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="7e20f-139">Categorieën</span><span class="sxs-lookup"><span data-stu-id="7e20f-139">Categories</span></span>
<span data-ttu-id="7e20f-140">Kies specifieke categorieën om je te concentreren op een specifieke stap in de kill chain</span><span class="sxs-lookup"><span data-stu-id="7e20f-140">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="7e20f-141">Gegevensgevoeligheid</span><span class="sxs-lookup"><span data-stu-id="7e20f-141">Data sensitivity</span></span>
<span data-ttu-id="7e20f-142">Sommige aanvallen richten zich op targeting om gevoelige of waardevolle gegevens te exfiltreren.</span><span class="sxs-lookup"><span data-stu-id="7e20f-142">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="7e20f-143">Door een filter toe te passen om te zien of er gevoelige gegevens bij het incident betrokken zijn, u snel bepalen of gevoelige informatie mogelijk is gecompromitteerd en prioriteit geven aan het aanpakken van deze incidenten.</span><span class="sxs-lookup"><span data-stu-id="7e20f-143">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="7e20f-144">Alleen van toepassing als Microsoft Information Protection is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="7e20f-144">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="7e20f-145">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="7e20f-145">Next steps</span></span>
<span data-ttu-id="7e20f-146">Nadat u hebt vastgesteld welk incident de hoogste prioriteit vereist, u verder onderzoek doen naar een incident.</span><span class="sxs-lookup"><span data-stu-id="7e20f-146">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="7e20f-147">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="7e20f-147">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="7e20f-148">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7e20f-148">Related topics</span></span>
- [<span data-ttu-id="7e20f-149">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="7e20f-149">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="7e20f-150">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="7e20f-150">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="7e20f-151">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="7e20f-151">Manage incidents</span></span>](manage-incidents.md)
