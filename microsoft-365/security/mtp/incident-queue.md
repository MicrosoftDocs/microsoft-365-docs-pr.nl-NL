---
title: Incidenten prioriteren in Microsoft 365 Defender
description: Meer informatie over het instellen van een prioriteit in de wachtrij voor incidenten in Microsoft 365 Defender
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4369d51ed740af652be632ba0b8752c708d6c719
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877217"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="29c3a-104">Incidenten prioriteren in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29c3a-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="29c3a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="29c3a-105">**Applies to:**</span></span>
- <span data-ttu-id="29c3a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29c3a-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="29c3a-107">Met Microsoft 365 Defender past u correlatie analyses toe en voegt u alle gerelateerde waarschuwingen en onderzoek van verschillende producten samen tot één voorval.</span><span class="sxs-lookup"><span data-stu-id="29c3a-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="29c3a-108">Microsoft 365 Defender zorgt ook voor unieke meldingen van activiteiten die alleen als schadelijk kunnen worden geïdentificeerd op basis van de end-to-end detectie van de end-to-end-versie van Microsoft 365 voor het hele erfgoed en de productsuite.</span><span class="sxs-lookup"><span data-stu-id="29c3a-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="29c3a-109">Op deze manier wordt in Microsoft 365 Defender het bericht over een bredere aanval met de analist ingesproken, waardoor een beveiligings analist de analist begrijpt en verlegt met ingewikkelde bedreigingen binnen de organisatie.</span><span class="sxs-lookup"><span data-stu-id="29c3a-109">By doing so, Microsoft 365 Defender narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="29c3a-110">In de **wachtrij incidenten** wordt een verzameling incidenten weergegeven die zijn gemarkeerd voor alle apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="29c3a-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="29c3a-111">Met deze functie kunt u een weloverwogen Cyber Security-antwoord beslissing stellen en een weloverwogen antwoord beslissing stellen.</span><span class="sxs-lookup"><span data-stu-id="29c3a-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Afbeelding van een wachtrij voor incidenten](../../media/incidents-queue.png) 

<span data-ttu-id="29c3a-113">Standaard worden in de wachtrij in het Microsoft 365-Beveiligingscentrum de incidenten weergegeven die in de afgelopen 30 dagen zijn weergegeven.</span><span class="sxs-lookup"><span data-stu-id="29c3a-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="29c3a-114">Het nieuwste incident staat boven aan de lijst, zodat u het eerst kunt zien.</span><span class="sxs-lookup"><span data-stu-id="29c3a-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="29c3a-115">In de wachtrij voor incidenten worden aanpasbare kolommen getoond die u inzicht geven in verschillende kenmerken van het incident of de opgenomen entiteiten.</span><span class="sxs-lookup"><span data-stu-id="29c3a-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="29c3a-116">Dit helpt u bij het maken van een weloverwogen beslissing met betrekking tot de prioriteit van incidenten.</span><span class="sxs-lookup"><span data-stu-id="29c3a-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="29c3a-117">Voor een extra detectie in één oogopslag worden de namen van de incidenten gegenereerd op basis van waarschuwings kenmerken, zoals het aantal desbetreffende eindpunten, gebruikers die worden getroffen, detectie bronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="29c3a-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="29c3a-118">Zo kunt u snel inzicht krijgen in de reikwijdte van het incident.</span><span class="sxs-lookup"><span data-stu-id="29c3a-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="29c3a-119">Voorbeeld: een *incident van meerdere stappen op meerdere eindpunten, gerapporteerd door meerdere bronnen.*</span><span class="sxs-lookup"><span data-stu-id="29c3a-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="29c3a-120">Voor incidenten die bestonden vóór de implementatie van de naam van het automatische incident, is de naam niet gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="29c3a-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="29c3a-121">In de wachtrij voor incidenten worden ook meerdere filteropties getoond die u kunt toepassen, zodat u een breed opruimen kunt maken van alle bestaande incidenten in uw omgeving, of als u de focus wilt verplaatsen naar een specifiek scenario of bedreiging.</span><span class="sxs-lookup"><span data-stu-id="29c3a-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="29c3a-122">Door filters toe te passen op de incident wachtrij, kunt u bepalen welk incident directe aandacht vereist.</span><span class="sxs-lookup"><span data-stu-id="29c3a-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="29c3a-123">Beschikbare filters</span><span class="sxs-lookup"><span data-stu-id="29c3a-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="29c3a-124">Toegewezen aan</span><span class="sxs-lookup"><span data-stu-id="29c3a-124">Assigned to</span></span>
<span data-ttu-id="29c3a-125">U kunt ervoor kiezen om waarschuwingen weer te geven die aan u zijn toegewezen of die zijn afgehandeld door automatisering.</span><span class="sxs-lookup"><span data-stu-id="29c3a-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="29c3a-126">Categorieën</span><span class="sxs-lookup"><span data-stu-id="29c3a-126">Categories</span></span>
<span data-ttu-id="29c3a-127">Kies categorieën om te focussen op specifieke tactiek, technieken of onderdelen van een aanval.</span><span class="sxs-lookup"><span data-stu-id="29c3a-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="29c3a-128">Contactpersoonclassificatie</span><span class="sxs-lookup"><span data-stu-id="29c3a-128">Classification</span></span>
<span data-ttu-id="29c3a-129">Filter incidenten op basis van de ingestelde classificaties van de gerelateerde waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="29c3a-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="29c3a-130">De waarden bestaan uit echte waarschuwingen, onjuiste waarschuwingen of niet ingesteld.</span><span class="sxs-lookup"><span data-stu-id="29c3a-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="29c3a-131">Gegevens gevoeligheid</span><span class="sxs-lookup"><span data-stu-id="29c3a-131">Data sensitivity</span></span>
<span data-ttu-id="29c3a-132">Sommige aanvallen richten op het bereiken van exfiltrate gevoelige of waardevolle gegevens.</span><span class="sxs-lookup"><span data-stu-id="29c3a-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="29c3a-133">Door een filter toe te passen om te zien of de gevoelige gegevens bij het incident passen, kunt u snel vaststellen of gevoelige informatie al mogelijk is aangetast en de prioriteit van die incidenten bepalen.</span><span class="sxs-lookup"><span data-stu-id="29c3a-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="29c3a-134">Alleen van toepassing als Microsoft-informatiebeveiliging is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="29c3a-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="29c3a-135">Apparaten groep</span><span class="sxs-lookup"><span data-stu-id="29c3a-135">Device group</span></span>
<span data-ttu-id="29c3a-136">Filteren op gedefinieerde apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="29c3a-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="29c3a-137">Onderzoek status</span><span class="sxs-lookup"><span data-stu-id="29c3a-137">Investigation state</span></span>
<span data-ttu-id="29c3a-138">Filteren op incidenten met de status van een geautomatiseerd onderzoek.</span><span class="sxs-lookup"><span data-stu-id="29c3a-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="29c3a-139">Meerdere categorieën</span><span class="sxs-lookup"><span data-stu-id="29c3a-139">Multiple categories</span></span> 
<span data-ttu-id="29c3a-140">U kunt ervoor kiezen om alleen aanvragen weer te geven die zijn toegewezen aan meerdere categorieën en daarom mogelijk meer schade kunnen veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="29c3a-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="29c3a-141">Meerdere servicebronnen</span><span class="sxs-lookup"><span data-stu-id="29c3a-141">Multiple service sources</span></span> 
<span data-ttu-id="29c3a-142">Filteren om alleen incidenten weer te geven die waarschuwingen van verschillende bronnen bevatten (Microsoft Defender for Endpoint, Microsoft Cloud app Security, Microsoft Defender for Identity, Microsoft Defender voor Office 365).</span><span class="sxs-lookup"><span data-stu-id="29c3a-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="29c3a-143">Platform van OS</span><span class="sxs-lookup"><span data-stu-id="29c3a-143">OS platform</span></span>
<span data-ttu-id="29c3a-144">De weergave van de incidenten wachtrij beperken met besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="29c3a-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="29c3a-145">Service bronnen</span><span class="sxs-lookup"><span data-stu-id="29c3a-145">Service sources</span></span>
<span data-ttu-id="29c3a-146">Als u een specifieke bron kiest, kunt u zich richten op incidenten met minstens één waarschuwing van de gekozen bron.</span><span class="sxs-lookup"><span data-stu-id="29c3a-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="29c3a-147">Ernst</span><span class="sxs-lookup"><span data-stu-id="29c3a-147">Severity</span></span>
<span data-ttu-id="29c3a-148">De ernst van een incident is een indicatie van de invloed die op uw tegoed kan worden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="29c3a-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="29c3a-149">Hoe hoger de ernst, wat groter de gevolgen en is meestal de enige directe aandacht.</span><span class="sxs-lookup"><span data-stu-id="29c3a-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="29c3a-150">Status</span><span class="sxs-lookup"><span data-stu-id="29c3a-150">Status</span></span>
<span data-ttu-id="29c3a-151">U kunt ervoor kiezen de lijst te beperken van de namen die worden weergegeven op basis van hun status, zodat u kunt zien welke gebeurtenissen actief zijn of worden opgelost.</span><span class="sxs-lookup"><span data-stu-id="29c3a-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

>[!IMPORTANT]
><span data-ttu-id="29c3a-152">De filters categorie, apparaat, onderzoek en OS platform zijn momenteel alleen beschikbaar in de openbare preview-versie.</span><span class="sxs-lookup"><span data-stu-id="29c3a-152">The Classification, Device group, Investigation state, and OS platform filters are currently only available in public preview.</span></span>


## <a name="next-steps"></a><span data-ttu-id="29c3a-153">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="29c3a-153">Next steps</span></span>
<span data-ttu-id="29c3a-154">Nadat u hebt vastgesteld voor welk incident de hoogste prioriteit is vereist, kunt u doorgaan met het verdere onderzoek verder werken aan een incident.</span><span class="sxs-lookup"><span data-stu-id="29c3a-154">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="29c3a-155">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="29c3a-155">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="29c3a-156">Zie ook</span><span class="sxs-lookup"><span data-stu-id="29c3a-156">See also</span></span>
- [<span data-ttu-id="29c3a-157">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="29c3a-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="29c3a-158">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="29c3a-158">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="29c3a-159">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="29c3a-159">Manage incidents</span></span>](manage-incidents.md)
