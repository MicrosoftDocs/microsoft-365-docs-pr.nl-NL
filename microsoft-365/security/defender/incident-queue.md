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
ms.openlocfilehash: 5aba1ab4bed0eeb5f6127ab865ceea674e8d5902
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500993"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="e4c72-104">Prioriteit geven aan incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4c72-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e4c72-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e4c72-105">**Applies to:**</span></span>
- <span data-ttu-id="e4c72-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4c72-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="e4c72-107">Microsoft 365 Defender past correlatieanalyse toe en verzamelt alle gerelateerde waarschuwingen en onderzoeken van verschillende producten tot één incident.</span><span class="sxs-lookup"><span data-stu-id="e4c72-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="e4c72-108">Microsoft 365 Defender activeert ook unieke waarschuwingen voor activiteiten die alleen kunnen worden geïdentificeerd als schadelijk, gezien de end-to-end zichtbaarheid die Microsoft 365 Defender heeft in het hele domein en de hele suite met producten.</span><span class="sxs-lookup"><span data-stu-id="e4c72-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="e4c72-109">In deze weergave krijgt uw beveiligingsanalist het bredere aanvalsverhaal, waarmee ze complexe bedreigingen in de hele organisatie beter kunnen begrijpen en kunnen omgaan.</span><span class="sxs-lookup"><span data-stu-id="e4c72-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="e4c72-110">De **wachtrij Incidenten** toont een verzameling incidenten die zijn gemarkeerd op verschillende apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="e4c72-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="e4c72-111">Het helpt u incidenten te sorteren om prioriteit te geven en een weloverwogen antwoordbesluit voor cyberbeveiliging te maken.</span><span class="sxs-lookup"><span data-stu-id="e4c72-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Afbeelding van incidentenwachtrij](../../media/incidents-queue.png) 

<span data-ttu-id="e4c72-113">Standaard worden in de wachtrij in het Microsoft 365-beveiligingscentrum incidenten weergegeven die de afgelopen 30 dagen zijn gezien.</span><span class="sxs-lookup"><span data-stu-id="e4c72-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="e4c72-114">Het meest recente incident staat bovenaan de lijst, zodat u het eerst kunt zien.</span><span class="sxs-lookup"><span data-stu-id="e4c72-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="e4c72-115">De incidentwachtrij bevat aanpasbare kolommen die u inzicht geven in verschillende kenmerken van het incident of de opgenomen entiteiten.</span><span class="sxs-lookup"><span data-stu-id="e4c72-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="e4c72-116">Op deze manier kunt u een weloverwogen beslissing nemen over de prioriteit van incidenten die moeten worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="e4c72-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="e4c72-117">Voor extra zichtbaarheid in één oogopslag worden met automatische naamgeving voor incidenten incidentnamen gegenereerd op basis van waarschuwingskenmerken, zoals het aantal eindpunten dat is beïnvloed, de betreffende gebruikers, detectiebronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="e4c72-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="e4c72-118">Hierdoor kunt u snel inzicht krijgen in het bereik van het incident.</span><span class="sxs-lookup"><span data-stu-id="e4c72-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="e4c72-119">Bijvoorbeeld: *incident met meerdere fases op meerdere eindpunten die door meerdere bronnen zijn gerapporteerd.*</span><span class="sxs-lookup"><span data-stu-id="e4c72-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="e4c72-120">Incidenten die vóór de implementatie van automatische naamgeving voor incidenten hebben bestaan, worden niet gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="e4c72-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="e4c72-121">In de wachtrij voor incidenten worden ook meerdere filteropties beschikbaar, waarmee u, wanneer deze wordt toegepast, alle bestaande incidenten in uw omgeving breed kunt opsnuiven of kunt besluiten zich te concentreren op een specifiek scenario of bedreiging.</span><span class="sxs-lookup"><span data-stu-id="e4c72-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="e4c72-122">Door filters toe te passen op de incidentwachtrij, kan worden bepaald welk incident direct aandacht nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="e4c72-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="e4c72-123">Beschikbare filters</span><span class="sxs-lookup"><span data-stu-id="e4c72-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="e4c72-124">Toegewezen aan</span><span class="sxs-lookup"><span data-stu-id="e4c72-124">Assigned to</span></span>
<span data-ttu-id="e4c72-125">U kunt ervoor kiezen om waarschuwingen weer te geven die aan u zijn toegewezen of waarschuwingen die door automatisering worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="e4c72-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="e4c72-126">Categorieën</span><span class="sxs-lookup"><span data-stu-id="e4c72-126">Categories</span></span>
<span data-ttu-id="e4c72-127">Kies categorieën om zich te richten op specifieke tactieken, technieken of aanvalsonderdelen.</span><span class="sxs-lookup"><span data-stu-id="e4c72-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="e4c72-128">Classificatie</span><span class="sxs-lookup"><span data-stu-id="e4c72-128">Classification</span></span>
<span data-ttu-id="e4c72-129">Filter incidenten op basis van de setclassificaties van de gerelateerde waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="e4c72-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="e4c72-130">De waarden omvatten waar waarschuwingen, onwaar waarschuwingen of niet ingesteld.</span><span class="sxs-lookup"><span data-stu-id="e4c72-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="e4c72-131">Gegevensgevoeligheid</span><span class="sxs-lookup"><span data-stu-id="e4c72-131">Data sensitivity</span></span>
<span data-ttu-id="e4c72-132">Sommige aanvallen richten zich op targeting om gevoelige of waardevolle gegevens te exfiltreren.</span><span class="sxs-lookup"><span data-stu-id="e4c72-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="e4c72-133">Door een filter toe te passen om te zien of er gevoelige gegevens bij het incident betrokken zijn, kunt u snel bepalen of gevoelige informatie mogelijk is gehackt en kunt u prioriteit geven aan het oplossen van deze incidenten.</span><span class="sxs-lookup"><span data-stu-id="e4c72-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="e4c72-134">Alleen van toepassing als Microsoft Information Protection is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e4c72-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="e4c72-135">Apparaatgroep</span><span class="sxs-lookup"><span data-stu-id="e4c72-135">Device group</span></span>
<span data-ttu-id="e4c72-136">Filteren op gedefinieerde apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="e4c72-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="e4c72-137">Onderzoekstoestand</span><span class="sxs-lookup"><span data-stu-id="e4c72-137">Investigation state</span></span>
<span data-ttu-id="e4c72-138">Filter incidenten op basis van de status van automatisch onderzoek.</span><span class="sxs-lookup"><span data-stu-id="e4c72-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="e4c72-139">Meerdere categorieën</span><span class="sxs-lookup"><span data-stu-id="e4c72-139">Multiple categories</span></span> 
<span data-ttu-id="e4c72-140">U kunt ervoor kiezen om alleen incidenten te zien die zijn toegesneden op meerdere categorieën en zo mogelijk meer schade kunnen veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="e4c72-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="e4c72-141">Meerdere servicebronnen</span><span class="sxs-lookup"><span data-stu-id="e4c72-141">Multiple service sources</span></span> 
<span data-ttu-id="e4c72-142">Filter om alleen incidenten te zien die waarschuwingen uit verschillende bronnen bevatten (Microsoft Defender voor Eindpunt, Microsoft Cloud App-beveiliging, Microsoft Defender voor identiteit, Microsoft Defender voor Office 365).</span><span class="sxs-lookup"><span data-stu-id="e4c72-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="e4c72-143">BESTURINGSSYSTEEM-platform</span><span class="sxs-lookup"><span data-stu-id="e4c72-143">OS platform</span></span>
<span data-ttu-id="e4c72-144">Beperk de weergave van de incidentwachtrij per besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="e4c72-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="e4c72-145">Servicebronnen</span><span class="sxs-lookup"><span data-stu-id="e4c72-145">Service sources</span></span>
<span data-ttu-id="e4c72-146">Door een specifieke bron te kiezen, kunt u zich richten op incidenten die ten minste één waarschuwing uit die gekozen bron bevatten.</span><span class="sxs-lookup"><span data-stu-id="e4c72-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="e4c72-147">Ernst</span><span class="sxs-lookup"><span data-stu-id="e4c72-147">Severity</span></span>
<span data-ttu-id="e4c72-148">De ernst van een incident is een indicatie van de invloed die het kan hebben op uw activa.</span><span class="sxs-lookup"><span data-stu-id="e4c72-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="e4c72-149">Hoe hoger de ernst, hoe groter de impact en meestal de meest directe aandacht.</span><span class="sxs-lookup"><span data-stu-id="e4c72-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="e4c72-150">Status</span><span class="sxs-lookup"><span data-stu-id="e4c72-150">Status</span></span>
<span data-ttu-id="e4c72-151">U kunt ervoor kiezen om de lijst met weergegeven incidenten te beperken op basis van hun status om te zien welke actief of opgelost zijn.</span><span class="sxs-lookup"><span data-stu-id="e4c72-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="e4c72-152">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="e4c72-152">Next steps</span></span>
<span data-ttu-id="e4c72-153">Nadat u hebt vastgesteld welk incident de hoogste prioriteit heeft, kunt u verder onderzoek doen naar een incident.</span><span class="sxs-lookup"><span data-stu-id="e4c72-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="e4c72-154">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="e4c72-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="e4c72-155">Zie ook</span><span class="sxs-lookup"><span data-stu-id="e4c72-155">See also</span></span>
- [<span data-ttu-id="e4c72-156">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="e4c72-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e4c72-157">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="e4c72-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="e4c72-158">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="e4c72-158">Manage incidents</span></span>](manage-incidents.md)
