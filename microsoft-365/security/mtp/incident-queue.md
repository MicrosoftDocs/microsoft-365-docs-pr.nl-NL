---
title: Prioriteit geven aan incidenten in Microsoft Threat Protection
description: Meer informatie over het prioriteren van incidenten in de wachtrij voor incidenten in Microsoft Threat Protection
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
ms.openlocfilehash: ef10eede38128bbf9b23537d860113b71f603089
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42805719"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="a8f19-104">Prioriteit geven aan incidenten in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a8f19-104">Prioritize incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="a8f19-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a8f19-105">**Applies to:**</span></span>
- <span data-ttu-id="a8f19-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="a8f19-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="a8f19-107">Microsoft Threat Protection past correlatieanalyses toe en verzamelt alle gerelateerde waarschuwingen en onderzoeken van verschillende producten in één incident.</span><span class="sxs-lookup"><span data-stu-id="a8f19-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="a8f19-108">Microsoft Threat Protection activeert ook unieke waarschuwingen over activiteiten die alleen kunnen worden geïdentificeerd als kwaadaardig gezien de end-to-end zichtbaarheid die Microsoft Threat Protection heeft over het hele landgoed en de suite van producten.</span><span class="sxs-lookup"><span data-stu-id="a8f19-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="a8f19-109">Door dit te doen, Microsoft Threat Protection vertelt de bredere aanval verhaal, waardoor een security operations analist te begrijpen en te gaan met complexe bedreigingen in de hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="a8f19-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="a8f19-110">**In de wachtrij Incidenten** wordt een verzameling incidenten weergegeven die zijn gemarkeerd vanaf verschillende apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="a8f19-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="a8f19-111">Het helpt u bij het sorteren van incidenten om prioriteiten te stellen en een weloverwogen reactiebeslissing over cyberbeveiliging te maken.</span><span class="sxs-lookup"><span data-stu-id="a8f19-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Afbeelding van incidentenwachtrij](../../media/incidents-queue.png) 

<span data-ttu-id="a8f19-113">Standaard worden in de wachtrij in het Microsoft 365-beveiligingscentrum incidenten weergegeven die in de afgelopen 30 dagen zijn gezien, waarbij het meest recente incident bovenaan de lijst wordt weergegeven, zodat u eerst de meest recente incidenten zien.</span><span class="sxs-lookup"><span data-stu-id="a8f19-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="a8f19-114">De wachtrij voor incidenten stelt aanpasbare kolommen bloot die u inzicht geven in de verschillende kenmerken van het incident of de opgenomen entiteiten, zodat u een weloverwogen beslissing nemen over prioritering van te behandelen incidenten.</span><span class="sxs-lookup"><span data-stu-id="a8f19-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span> 

<span data-ttu-id="a8f19-115">De incidentwachtrij stelt ook meerdere filteropties bloot, die u bij het toepassen in staat stellen om een brede sweep van alle bestaande incidenten in uw omgeving uit te voeren of te besluiten zich te concentreren op een specifiek scenario of bedreiging.</span><span class="sxs-lookup"><span data-stu-id="a8f19-115">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="a8f19-116">Het toepassen van filters in de incidentenwachtrij kan helpen bepalen welk incident onmiddellijke aandacht vereist.</span><span class="sxs-lookup"><span data-stu-id="a8f19-116">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="a8f19-117">Beschikbare filters</span><span class="sxs-lookup"><span data-stu-id="a8f19-117">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="a8f19-118">Status</span><span class="sxs-lookup"><span data-stu-id="a8f19-118">Status</span></span>
<span data-ttu-id="a8f19-119">U ervoor kiezen om de lijst met weergegeven incidenten te beperken op basis van hun status om te zien welke incidenten actief of opgelost zijn.</span><span class="sxs-lookup"><span data-stu-id="a8f19-119">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="a8f19-120">Ernst</span><span class="sxs-lookup"><span data-stu-id="a8f19-120">Severity</span></span>
<span data-ttu-id="a8f19-121">De ernst van een incident is indicatief voor de impact die het kan hebben op uw activa.</span><span class="sxs-lookup"><span data-stu-id="a8f19-121">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="a8f19-122">Hoe hoger de ernst, hoe groter de impact en vereist meestal de meest directe aandacht.</span><span class="sxs-lookup"><span data-stu-id="a8f19-122">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="a8f19-123">Toegewezen aan (eigenaar)</span><span class="sxs-lookup"><span data-stu-id="a8f19-123">Assigned to (owner)</span></span>
<span data-ttu-id="a8f19-124">U ervoor kiezen de lijst te filteren door toegewezen te selecteren aan iedereen of degenen die aan u zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="a8f19-124">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="a8f19-125">Meerdere waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="a8f19-125">Multiple alerts</span></span> 
<span data-ttu-id="a8f19-126">Filter om alleen incidenten te zien die meer dan één waarschuwing bevatten.</span><span class="sxs-lookup"><span data-stu-id="a8f19-126">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="a8f19-127">Dit kan een indicatie zijn voor een aanval die complexer is of vorderde in de kill chain.</span><span class="sxs-lookup"><span data-stu-id="a8f19-127">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="a8f19-128">Meerdere servicebronnen</span><span class="sxs-lookup"><span data-stu-id="a8f19-128">Multiple service sources</span></span> 
<span data-ttu-id="a8f19-129">Filteren om alleen incidenten te zien die waarschuwingen uit verschillende bronnen bevatten (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="a8f19-129">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="a8f19-130">Servicebronnen</span><span class="sxs-lookup"><span data-stu-id="a8f19-130">Service sources</span></span>
<span data-ttu-id="a8f19-131">Door een specifieke bron te kiezen, u zich richten op incidenten die ten minste één waarschuwing van die gekozen bron bevatten.</span><span class="sxs-lookup"><span data-stu-id="a8f19-131">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="a8f19-132">Meerdere categorieën</span><span class="sxs-lookup"><span data-stu-id="a8f19-132">Multiple categories</span></span> 
<span data-ttu-id="a8f19-133">U ervoor kiezen om alleen incidenten te zien die in kaart zijn gebracht in meerdere categorieën van de kill chain en mogelijk meer schade kunnen veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="a8f19-133">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="a8f19-134">Categorieën</span><span class="sxs-lookup"><span data-stu-id="a8f19-134">Categories</span></span>
<span data-ttu-id="a8f19-135">Kies specifieke categorieën om u te concentreren op een specifieke stap in de kill chain</span><span class="sxs-lookup"><span data-stu-id="a8f19-135">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="a8f19-136">Gegevensgevoeligheid</span><span class="sxs-lookup"><span data-stu-id="a8f19-136">Data sensitivity</span></span>
<span data-ttu-id="a8f19-137">Sommige aanvallen richten zich op targeting om gevoelige of waardevolle gegevens te exfiltreren.</span><span class="sxs-lookup"><span data-stu-id="a8f19-137">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="a8f19-138">Door een filter toe te passen om te zien of gevoelige gegevens betrokken zijn bij het incident, u snel bepalen of gevoelige informatie mogelijk is gecompromitteerd en prioriteit geven aan het aanpakken van die incidenten.</span><span class="sxs-lookup"><span data-stu-id="a8f19-138">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="a8f19-139">Alleen van toepassing als Microsoft Information Protection is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a8f19-139">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="a8f19-140">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="a8f19-140">Next steps</span></span>
<span data-ttu-id="a8f19-141">Nadat u hebt vastgesteld welk incident de hoogste prioriteit vereist, u verder onderzoek doen naar een incident.</span><span class="sxs-lookup"><span data-stu-id="a8f19-141">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="a8f19-142">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="a8f19-142">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="a8f19-143">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a8f19-143">Related topics</span></span>
- [<span data-ttu-id="a8f19-144">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="a8f19-144">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="a8f19-145">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="a8f19-145">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="a8f19-146">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="a8f19-146">Manage incidents</span></span>](manage-incidents.md)
