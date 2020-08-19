---
title: Incidenten prioriteren in Microsoft Threat Protection
description: Meer informatie over het instellen van een prioriteit aan de incidenten wachtrij in Microsoft Threat Protection
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
ms.openlocfilehash: a08ff27d6d33317df9bd4bf61c0c2ee4cf0ee14e
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797756"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="14de8-104">Incidenten prioriteren in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="14de8-104">Prioritize incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="14de8-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="14de8-105">**Applies to:**</span></span>
- <span data-ttu-id="14de8-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="14de8-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="14de8-107">Microsoft Threat Protection past correlatie analyses toe en voegt alle bijbehorende waarschuwingen en onderzoek van verschillende producten samen tot één voorval.</span><span class="sxs-lookup"><span data-stu-id="14de8-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="14de8-108">Microsoft Threat Protection zorgt ook voor unieke meldingen over activiteiten die alleen als schadelijk kunnen worden geïdentificeerd aan de end-to-end zichtbaarheid van Microsoft Threat Protection voor het hele erfgoed en de suite met producten.</span><span class="sxs-lookup"><span data-stu-id="14de8-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="14de8-109">Op deze manier beschermt Microsoft Threat Protection het bredere verhaal van een verhaal, waardoor een beveiligings analist de analist begrijpt en begrijpt met ingewikkelde bedreigingen binnen de organisatie.</span><span class="sxs-lookup"><span data-stu-id="14de8-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="14de8-110">In de **wachtrij incidenten** wordt een verzameling incidenten weergegeven die zijn gemarkeerd voor alle apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="14de8-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="14de8-111">Met deze functie kunt u een weloverwogen Cyber Security-antwoord beslissing stellen en een weloverwogen antwoord beslissing stellen.</span><span class="sxs-lookup"><span data-stu-id="14de8-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Afbeelding van een wachtrij voor incidenten](../../media/incidents-queue.png) 

<span data-ttu-id="14de8-113">Standaard worden in de wachtrij in het Microsoft 365-Beveiligingscentrum de incidenten weergegeven die in de afgelopen 30 dagen worden weergegeven, met het meest recente incident dat bovenaan de lijst wordt weergegeven, zodat u eerst de meest recente aanvragen kunt zien.</span><span class="sxs-lookup"><span data-stu-id="14de8-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="14de8-114">In de wachtrij voor incidenten worden aanpasbare kolommen gemaakt waarmee u inzicht krijgt in verschillende kenmerken van het incident of de opgenomen entiteiten, zodat u een weloverwogen beslissing moet nemen over de prioriteit van incidenten.</span><span class="sxs-lookup"><span data-stu-id="14de8-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="14de8-115">Voor meer inzicht in één oogopslag worden namen van geadresseerden automatisch de naam van een incident gegenereerd op basis van waarschuwings kenmerken, zoals het aantal desbetreffende eindpunten, gebruikers die worden getroffen, detectie bronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="14de8-115">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="14de8-116">Zo kunt u snel inzicht krijgen in de reikwijdte van het incident.</span><span class="sxs-lookup"><span data-stu-id="14de8-116">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="14de8-117">Voorbeeld: een *incident van meerdere stappen op meerdere eindpunten, gerapporteerd door meerdere bronnen.*</span><span class="sxs-lookup"><span data-stu-id="14de8-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="14de8-118">Voor incidenten die bestonden vóór de implementatie van de naam van het automatische incident, is de naam niet gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="14de8-118">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="14de8-119">In de wachtrij voor incidenten worden ook meerdere filteropties getoond die u kunt gebruiken om ervoor te zorgen dat al uw bestaande incidenten in uw omgeving meerdere keren worden opruimen of dat u zich kunt richten op een specifiek scenario of bedreiging.</span><span class="sxs-lookup"><span data-stu-id="14de8-119">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="14de8-120">Door filters toe te passen op de incident wachtrij, kunt u bepalen welk incident directe aandacht vereist.</span><span class="sxs-lookup"><span data-stu-id="14de8-120">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="14de8-121">Beschikbare filters</span><span class="sxs-lookup"><span data-stu-id="14de8-121">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="14de8-122">Status</span><span class="sxs-lookup"><span data-stu-id="14de8-122">Status</span></span>
<span data-ttu-id="14de8-123">U kunt ervoor kiezen de lijst te beperken van de namen die worden weergegeven op basis van hun status, zodat u kunt zien welke gebeurtenissen actief zijn of worden opgelost.</span><span class="sxs-lookup"><span data-stu-id="14de8-123">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="14de8-124">Ernst</span><span class="sxs-lookup"><span data-stu-id="14de8-124">Severity</span></span>
<span data-ttu-id="14de8-125">De ernst van een incident is van invloed op de invloed die dit kan hebben op uw activa.</span><span class="sxs-lookup"><span data-stu-id="14de8-125">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="14de8-126">Hoe hoger de ernst, hoe groter de impact en is meestal de enige directe aandacht.</span><span class="sxs-lookup"><span data-stu-id="14de8-126">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="14de8-127">Toegewezen aan (eigenaar)</span><span class="sxs-lookup"><span data-stu-id="14de8-127">Assigned to (owner)</span></span>
<span data-ttu-id="14de8-128">Als u de lijst wilt filteren, selecteert u de gewenste optie voor iedereen of degene die aan u is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="14de8-128">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="14de8-129">Meerdere meldingen</span><span class="sxs-lookup"><span data-stu-id="14de8-129">Multiple alerts</span></span> 
<span data-ttu-id="14de8-130">Filteren om alleen aanvragen weer te geven die meer dan één waarschuwing bevatten.</span><span class="sxs-lookup"><span data-stu-id="14de8-130">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="14de8-131">Dit kan een aanwijzing zijn voor een aanval met een complexere of een afgang van de werk keten.</span><span class="sxs-lookup"><span data-stu-id="14de8-131">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="14de8-132">Meerdere servicebronnen</span><span class="sxs-lookup"><span data-stu-id="14de8-132">Multiple service sources</span></span> 
<span data-ttu-id="14de8-133">Filteren om alleen incidenten weer te geven die waarschuwingen van verschillende bronnen bevatten (Microsoft Defender ATP, beveiliging van Microsoft Cloud app, Azure ATP, Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="14de8-133">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="14de8-134">Service bronnen</span><span class="sxs-lookup"><span data-stu-id="14de8-134">Service sources</span></span>
<span data-ttu-id="14de8-135">Als u een specifieke bron kiest, kunt u zich richten op incidenten met minstens één waarschuwing van de gekozen bron.</span><span class="sxs-lookup"><span data-stu-id="14de8-135">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="14de8-136">Meerdere categorieën</span><span class="sxs-lookup"><span data-stu-id="14de8-136">Multiple categories</span></span> 
<span data-ttu-id="14de8-137">U kunt ervoor kiezen om alleen aanvragen weer te geven die zijn toegewezen aan meerdere categorieën van de Kill-chain en hierdoor meer schade kan veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="14de8-137">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="14de8-138">Categorieën</span><span class="sxs-lookup"><span data-stu-id="14de8-138">Categories</span></span>
<span data-ttu-id="14de8-139">Kies specifieke categorieën om te focussen op een specifieke stap in de keten afbreken</span><span class="sxs-lookup"><span data-stu-id="14de8-139">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="14de8-140">Gegevens gevoeligheid</span><span class="sxs-lookup"><span data-stu-id="14de8-140">Data sensitivity</span></span>
<span data-ttu-id="14de8-141">Sommige aanvallen richten op het bereiken van exfiltrate gevoelige of waardevolle gegevens.</span><span class="sxs-lookup"><span data-stu-id="14de8-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="14de8-142">Door een filter toe te passen om te zien of de gevoelige gegevens bij het incident passen, kunt u snel vaststellen of gevoelige informatie al mogelijk is aangetast en de prioriteit van die incidenten bepalen.</span><span class="sxs-lookup"><span data-stu-id="14de8-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="14de8-143">Alleen van toepassing als Microsoft-informatiebeveiliging is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="14de8-143">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="14de8-144">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="14de8-144">Next steps</span></span>
<span data-ttu-id="14de8-145">Nadat u hebt vastgesteld voor welk incident de hoogste prioriteit is vereist, kunt u doorgaan met het verdere onderzoek verder werken aan een incident.</span><span class="sxs-lookup"><span data-stu-id="14de8-145">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="14de8-146">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="14de8-146">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="14de8-147">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="14de8-147">Related topics</span></span>
- [<span data-ttu-id="14de8-148">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="14de8-148">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="14de8-149">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="14de8-149">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="14de8-150">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="14de8-150">Manage incidents</span></span>](manage-incidents.md)
