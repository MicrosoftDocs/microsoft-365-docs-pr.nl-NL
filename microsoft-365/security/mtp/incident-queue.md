---
title: Prioriteit geven aan incidenten in Microsoft 365 Defender
description: Informatie over het filteren van incidenten uit de wachtrij voor incidenten in Microsoft 365 Defender
keywords: incident, wachtrij, overzicht, apparaten, identiteiten, gebruikers, postvak, e-mail, incidenten
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e01fce970b806bc425db2cd4886e82f79434656f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929292"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="f8a17-104">Prioriteit geven aan incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8a17-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f8a17-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f8a17-105">**Applies to:**</span></span>
- <span data-ttu-id="f8a17-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8a17-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="f8a17-107">Microsoft 365 Defender past correlatieanalyses toe en verzamelt alle gerelateerde waarschuwingen en onderzoeken van verschillende producten tot één incident.</span><span class="sxs-lookup"><span data-stu-id="f8a17-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="f8a17-108">Microsoft 365 Defender activeert ook unieke waarschuwingen voor activiteiten die alleen kunnen worden geïdentificeerd als schadelijk, gegeven de end-to-end zichtbaarheid die Microsoft 365 Defender heeft voor het hele domein en de suite met producten.</span><span class="sxs-lookup"><span data-stu-id="f8a17-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="f8a17-109">Deze weergave geeft uw beveiligingsanalist de bredere verhaal over aanvallen, waardoor ze complexe bedreigingen in de hele organisatie beter kunnen begrijpen en kunnen omgaan.</span><span class="sxs-lookup"><span data-stu-id="f8a17-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="f8a17-110">De **wachtrij incidenten** toont een verzameling incidenten die werden gemarkeerd voor apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="f8a17-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="f8a17-111">Het helpt u bij het sorteren van incidenten om prioriteiten te stellen en een weloverwogen antwoordbeslissing te maken.</span><span class="sxs-lookup"><span data-stu-id="f8a17-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Afbeelding van de wachtrij met incidenten](../../media/incidents-queue.png) 

<span data-ttu-id="f8a17-113">In de wachtrij in het Microsoft 365-beveiligingscentrum worden standaard incidenten weergegeven van de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="f8a17-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="f8a17-114">Het meest recente incident staat bovenaan de lijst, zodat u het als eerste kunt zien.</span><span class="sxs-lookup"><span data-stu-id="f8a17-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="f8a17-115">De incidentwachtrij bevat aanpasbare kolommen die u inzicht geven in verschillende kenmerken van het incident of de entiteiten in de gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="f8a17-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="f8a17-116">Dit helpt u een weloverwogen beslissing te nemen met betrekking tot prioriteit van incidenten die moeten worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="f8a17-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="f8a17-117">Voor extra zichtbaarheid in een oogopslag worden met automatische naamgeving van incidenten incidentnamen gegenereerd op basis van waarschuwingskenmerken, zoals het aantal beïnvloede eindpunten, betrokken gebruikers, detectiebronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="f8a17-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="f8a17-118">Op deze manier kunt u snel de omvang van het incident begrijpen.</span><span class="sxs-lookup"><span data-stu-id="f8a17-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="f8a17-119">Bijvoorbeeld: *Incident met meerdere stadiums voor meerdere eindpunten gerapporteerd door meerdere bronnen.*</span><span class="sxs-lookup"><span data-stu-id="f8a17-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="f8a17-120">Incidenten die zich vóór de implementatie van automatische naamgeving van incidenten hebben voorgedaan, worden niet gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="f8a17-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="f8a17-121">In de incidentwachtrij worden ook meerdere filteropties beschikbaar, waarmee u wanneer deze wordt toegepast, alle bestaande incidenten in uw omgeving breed kunt opruimen of kunt besluiten om te focussen op een bepaald scenario of risico.</span><span class="sxs-lookup"><span data-stu-id="f8a17-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="f8a17-122">Door filters op de incidentwachtrij toe te passen, kunt u bepalen welk incident onmiddellijke aandacht vereist.</span><span class="sxs-lookup"><span data-stu-id="f8a17-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="f8a17-123">Beschikbare filters</span><span class="sxs-lookup"><span data-stu-id="f8a17-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="f8a17-124">Toegewezen aan</span><span class="sxs-lookup"><span data-stu-id="f8a17-124">Assigned to</span></span>
<span data-ttu-id="f8a17-125">U kunt ervoor kiezen om waarschuwingen weer te geven die zijn toegewezen aan u of de waarschuwingen die worden verwerkt door automatisering.</span><span class="sxs-lookup"><span data-stu-id="f8a17-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="f8a17-126">Categorieën</span><span class="sxs-lookup"><span data-stu-id="f8a17-126">Categories</span></span>
<span data-ttu-id="f8a17-127">Kies categorieën om u te richten op specifieke technieken, technieken of elementen voor aanvallen.</span><span class="sxs-lookup"><span data-stu-id="f8a17-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="f8a17-128">Classificatie</span><span class="sxs-lookup"><span data-stu-id="f8a17-128">Classification</span></span>
<span data-ttu-id="f8a17-129">Filter incidenten op basis van de classificaties van de gerelateerde waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="f8a17-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="f8a17-130">De waarden zijn onder andere waar-waarschuwingen, onwaar-waarschuwingen of niet-ingesteld.</span><span class="sxs-lookup"><span data-stu-id="f8a17-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="f8a17-131">Gegevensgevoeligheid</span><span class="sxs-lookup"><span data-stu-id="f8a17-131">Data sensitivity</span></span>
<span data-ttu-id="f8a17-132">Sommige aanvallen richten zich op het verzamelen van gevoelige of waardevolle gegevens.</span><span class="sxs-lookup"><span data-stu-id="f8a17-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="f8a17-133">Door een filter toe te passen om te zien of er gevoelige gegevens bij het incident zijn betrokken, kunt u snel vaststellen of gevoelige informatie mogelijk is gehackt en prioriteit geven aan de adressering van die incidenten.</span><span class="sxs-lookup"><span data-stu-id="f8a17-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="f8a17-134">Alleen van toepassing als Microsoft Information Protection is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f8a17-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="f8a17-135">Apparaatgroep</span><span class="sxs-lookup"><span data-stu-id="f8a17-135">Device group</span></span>
<span data-ttu-id="f8a17-136">Filteren op gedefinieerde apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="f8a17-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="f8a17-137">Staat van onderzoek</span><span class="sxs-lookup"><span data-stu-id="f8a17-137">Investigation state</span></span>
<span data-ttu-id="f8a17-138">Incidenten filteren op de status van geautomatiseerd onderzoek.</span><span class="sxs-lookup"><span data-stu-id="f8a17-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="f8a17-139">Meerdere categorieën</span><span class="sxs-lookup"><span data-stu-id="f8a17-139">Multiple categories</span></span> 
<span data-ttu-id="f8a17-140">U kunt ervoor kiezen om alleen incidenten te zien die zijn toegesneden aan meerdere categorieën en die daardoor meer schade kunnen veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="f8a17-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="f8a17-141">Meerdere servicebronnen</span><span class="sxs-lookup"><span data-stu-id="f8a17-141">Multiple service sources</span></span> 
<span data-ttu-id="f8a17-142">Filter om alleen incidenten te zien die waarschuwingen van verschillende bronnen bevatten (Microsoft Defender voor eindpunt, Microsoft Cloud App-beveiliging, Microsoft Defender voor identiteit, Microsoft Defender voor Office 365).</span><span class="sxs-lookup"><span data-stu-id="f8a17-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="f8a17-143">Besturingssysteemplatform</span><span class="sxs-lookup"><span data-stu-id="f8a17-143">OS platform</span></span>
<span data-ttu-id="f8a17-144">Beperk de weergave van de incidentenwachtrij per besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="f8a17-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="f8a17-145">Servicebronnen</span><span class="sxs-lookup"><span data-stu-id="f8a17-145">Service sources</span></span>
<span data-ttu-id="f8a17-146">Door een specifieke bron te kiezen, kunt u zich richten op incidenten die ten minste één waarschuwing van die gekozen bron bevatten.</span><span class="sxs-lookup"><span data-stu-id="f8a17-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="f8a17-147">Ernst</span><span class="sxs-lookup"><span data-stu-id="f8a17-147">Severity</span></span>
<span data-ttu-id="f8a17-148">De ernst van een incident is afhankelijk van de invloed die het op uw assets kan hebben.</span><span class="sxs-lookup"><span data-stu-id="f8a17-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="f8a17-149">Hoe hoger de ernst, hoe groter de impact en meestal de meest directe aandacht vereist.</span><span class="sxs-lookup"><span data-stu-id="f8a17-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="f8a17-150">Status</span><span class="sxs-lookup"><span data-stu-id="f8a17-150">Status</span></span>
<span data-ttu-id="f8a17-151">U kunt ervoor kiezen om de lijst met weergegeven incidenten te beperken op basis van hun status om te zien welke actief of opgelost zijn.</span><span class="sxs-lookup"><span data-stu-id="f8a17-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="f8a17-152">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="f8a17-152">Next steps</span></span>
<span data-ttu-id="f8a17-153">Nadat u hebt bepaald welk incident de hoogste prioriteit vereist, kunt u verder werken aan een incident.</span><span class="sxs-lookup"><span data-stu-id="f8a17-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="f8a17-154">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="f8a17-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="f8a17-155">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f8a17-155">See also</span></span>
- [<span data-ttu-id="f8a17-156">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="f8a17-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f8a17-157">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="f8a17-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="f8a17-158">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="f8a17-158">Manage incidents</span></span>](manage-incidents.md)
