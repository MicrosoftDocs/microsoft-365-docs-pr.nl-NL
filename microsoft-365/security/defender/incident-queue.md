---
title: Prioriteit geven aan incidenten in Microsoft 365 Defender
description: Informatie over het filteren van incidenten in de wachtrij voor incidenten in Microsoft 365 Defender
keywords: incident, wachtrij, overzicht, apparaten, identiteiten, gebruikers, postvak, e-mail, incidenten, analyseren, antwoord
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
ms.openlocfilehash: df2d2660267c38dccf5ef09fa4955615d3a78141
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636264"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="42c2a-104">Prioriteit geven aan incidenten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42c2a-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="42c2a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="42c2a-105">**Applies to:**</span></span>
- <span data-ttu-id="42c2a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42c2a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="42c2a-107">Microsoft 365 Defender past correlatieanalyse toe en aggregeert gerelateerde waarschuwingen en geautomatiseerde onderzoeken van verschillende producten in een incident.</span><span class="sxs-lookup"><span data-stu-id="42c2a-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="42c2a-108">Microsoft 365 Defender activeert ook unieke waarschuwingen voor activiteiten die alleen kunnen worden geïdentificeerd als schadelijk, gezien de end-to-end zichtbaarheid die Microsoft 365 Defender heeft in de hele suite met producten.</span><span class="sxs-lookup"><span data-stu-id="42c2a-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="42c2a-109">In deze weergave krijgen uw beveiligingsanalisten het bredere verhaal over aanvallen, waarmee ze complexe bedreigingen in uw organisatie beter kunnen begrijpen en kunnen omgaan.</span><span class="sxs-lookup"><span data-stu-id="42c2a-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="42c2a-110">In **de wachtrij Incident** ziet u een verzameling incidenten die zijn gemaakt op verschillende apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="42c2a-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="42c2a-111">Het helpt u incidenten te sorteren om prioriteit te geven en een weloverwogen antwoordbesluit voor cyberbeveiliging te maken.</span><span class="sxs-lookup"><span data-stu-id="42c2a-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="42c2a-112">U komt bij de incidentenwachtrij van **Incidenten & waarschuwingen > Incidenten** op de snelle start van het Microsoft 365 beveiligingscentrum [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="42c2a-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="42c2a-113">Hier is een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="42c2a-113">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Voorbeeld van de incidentwachtrij":::

<span data-ttu-id="42c2a-115">In **de sectie Meest recente incidenten en waarschuwingen** ziet u een grafiek van het aantal ontvangen waarschuwingen en incidenten die in de afgelopen 24 uur zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="42c2a-115">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="42c2a-116">Standaard worden in de wachtrij voor incidenten in het Microsoft 365 beveiligingscentrum incidenten weergegeven die de afgelopen zes maanden zijn gezien.</span><span class="sxs-lookup"><span data-stu-id="42c2a-116">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="42c2a-117">Het meest recente incident staat bovenaan de lijst, zodat u het eerst kunt zien.</span><span class="sxs-lookup"><span data-stu-id="42c2a-117">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="42c2a-118">De incidentwachtrij heeft aanpasbare kolommen (selecteer Kolommen **kiezen)** die u inzicht geven in de verschillende kenmerken van het incident of de beïnvloede entiteiten.</span><span class="sxs-lookup"><span data-stu-id="42c2a-118">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="42c2a-119">Op deze manier kunt u een weloverwogen beslissing nemen over de prioriteit van incidenten voor analyse.</span><span class="sxs-lookup"><span data-stu-id="42c2a-119">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="42c2a-120">Voor extra zichtbaarheid in één oogopslag worden met automatische naamgeving voor incidenten incidentnamen gegenereerd op basis van waarschuwingskenmerken, zoals het aantal eindpunten dat is beïnvloed, de betreffende gebruikers, detectiebronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="42c2a-120">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="42c2a-121">Hierdoor kunt u snel inzicht krijgen in het bereik van het incident.</span><span class="sxs-lookup"><span data-stu-id="42c2a-121">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="42c2a-122">Bijvoorbeeld: *incident met meerdere fases op meerdere eindpunten die door meerdere bronnen zijn gerapporteerd.*</span><span class="sxs-lookup"><span data-stu-id="42c2a-122">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="42c2a-123">Incidenten die vóór de implementatie van automatische naamgeving voor incidenten hebben bestaan, worden niet gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="42c2a-123">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="42c2a-124">In de wachtrij voor incidenten worden ook meerdere filteropties beschikbaar, waarmee u, wanneer deze wordt toegepast, alle bestaande incidenten in uw omgeving breed kunt opsnuiven of kunt besluiten zich te concentreren op een specifiek scenario of bedreiging.</span><span class="sxs-lookup"><span data-stu-id="42c2a-124">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="42c2a-125">Door filters toe te passen op de incidentwachtrij, kan worden bepaald welk incident direct aandacht nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="42c2a-125">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="42c2a-126">Beschikbare filters</span><span class="sxs-lookup"><span data-stu-id="42c2a-126">Available filters</span></span>

<span data-ttu-id="42c2a-127">In de standaardwachtrij voor incidenten kunt u **Filters** selecteren om een deelvenster Filters weer te geven, waaruit u een gefilterde reeks incidenten kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="42c2a-127">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="42c2a-128">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="42c2a-128">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Voorbeeld van het filtervenster voor de incidentwachtrij":::

<span data-ttu-id="42c2a-130">In deze tabel worden de filternamen vermeld die beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="42c2a-130">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="42c2a-131">Filternaam</span><span class="sxs-lookup"><span data-stu-id="42c2a-131">Filter name</span></span> | <span data-ttu-id="42c2a-132">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="42c2a-132">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="42c2a-133">Toegewezen aan</span><span class="sxs-lookup"><span data-stu-id="42c2a-133">Assigned to</span></span> | <span data-ttu-id="42c2a-134">U kunt ervoor kiezen om waarschuwingen weer te geven die aan u zijn toegewezen of waarschuwingen die door automatisering worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="42c2a-134">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="42c2a-135">Categorieën</span><span class="sxs-lookup"><span data-stu-id="42c2a-135">Categories</span></span> | <span data-ttu-id="42c2a-136">Kies categorieën om zich te richten op specifieke tactieken, technieken of aanvalsonderdelen.</span><span class="sxs-lookup"><span data-stu-id="42c2a-136">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="42c2a-137">Classificatie</span><span class="sxs-lookup"><span data-stu-id="42c2a-137">Classification</span></span> | <span data-ttu-id="42c2a-138">Filter incidenten op basis van de setclassificaties van de gerelateerde waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="42c2a-138">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="42c2a-139">De waarden omvatten waar waarschuwingen, onwaar waarschuwingen of niet ingesteld.</span><span class="sxs-lookup"><span data-stu-id="42c2a-139">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="42c2a-140">Gegevensgevoeligheid</span><span class="sxs-lookup"><span data-stu-id="42c2a-140">Data sensitivity</span></span> | <span data-ttu-id="42c2a-141">Sommige aanvallen richten zich op targeting om gevoelige of waardevolle gegevens te exfiltreren.</span><span class="sxs-lookup"><span data-stu-id="42c2a-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="42c2a-142">Door een filter toe te passen om te zien of er gevoelige gegevens bij het incident betrokken zijn, kunt u snel bepalen of gevoelige informatie mogelijk is gehackt en kunt u prioriteit geven aan het oplossen van deze incidenten.</span><span class="sxs-lookup"><span data-stu-id="42c2a-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="42c2a-143">Alleen van toepassing als Microsoft Information Protection is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="42c2a-143">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="42c2a-144">Apparaatgroep</span><span class="sxs-lookup"><span data-stu-id="42c2a-144">Device group</span></span> | <span data-ttu-id="42c2a-145">Filteren op gedefinieerde apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="42c2a-145">Filter by defined device groups.</span></span> |
| <span data-ttu-id="42c2a-146">Onderzoekstoestand</span><span class="sxs-lookup"><span data-stu-id="42c2a-146">Investigation state</span></span> | <span data-ttu-id="42c2a-147">Filter incidenten op basis van de status van automatisch onderzoek.</span><span class="sxs-lookup"><span data-stu-id="42c2a-147">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="42c2a-148">Meerdere categorieën</span><span class="sxs-lookup"><span data-stu-id="42c2a-148">Multiple categories</span></span> | <span data-ttu-id="42c2a-149">U kunt ervoor kiezen om alleen incidenten te zien die zijn toegesneden op meerdere categorieën en zo mogelijk meer schade kunnen veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="42c2a-149">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="42c2a-150">Meerdere servicebronnen</span><span class="sxs-lookup"><span data-stu-id="42c2a-150">Multiple service sources</span></span>  | <span data-ttu-id="42c2a-151">Filter om alleen incidenten te zien die waarschuwingen uit verschillende bronnen bevatten (Microsoft Defender voor Eindpunt, Microsoft Cloud App Security, Microsoft Defender voor identiteit, Microsoft Defender voor Office 365).</span><span class="sxs-lookup"><span data-stu-id="42c2a-151">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="42c2a-152">BESTURINGSSYSTEEM-platform</span><span class="sxs-lookup"><span data-stu-id="42c2a-152">OS platform</span></span> | <span data-ttu-id="42c2a-153">Beperk de weergave van de incidentwachtrij per besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="42c2a-153">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="42c2a-154">Servicebronnen</span><span class="sxs-lookup"><span data-stu-id="42c2a-154">Service sources</span></span> | <span data-ttu-id="42c2a-155">Door een specifieke bron te kiezen, kunt u zich richten op incidenten die ten minste één waarschuwing uit die gekozen bron bevatten.</span><span class="sxs-lookup"><span data-stu-id="42c2a-155">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="42c2a-156">Ernst</span><span class="sxs-lookup"><span data-stu-id="42c2a-156">Severity</span></span> | <span data-ttu-id="42c2a-157">De ernst van een incident is een indicatie van de invloed die het kan hebben op uw activa.</span><span class="sxs-lookup"><span data-stu-id="42c2a-157">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="42c2a-158">Hoe hoger de ernst, hoe groter de impact en meestal de meest directe aandacht.</span><span class="sxs-lookup"><span data-stu-id="42c2a-158">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="42c2a-159">Status</span><span class="sxs-lookup"><span data-stu-id="42c2a-159">Status</span></span> | <span data-ttu-id="42c2a-160">U kunt ervoor kiezen om de lijst met weergegeven incidenten te beperken op basis van hun status om te zien welke actief of opgelost zijn.</span><span class="sxs-lookup"><span data-stu-id="42c2a-160">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="next-steps"></a><span data-ttu-id="42c2a-161">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="42c2a-161">Next steps</span></span>

<span data-ttu-id="42c2a-162">Nadat u hebt bepaald welk incident de hoogste prioriteit vereist, selecteert u het en:</span><span class="sxs-lookup"><span data-stu-id="42c2a-162">After you've determined which incident requires the highest priority, select it and:</span></span>

- <span data-ttu-id="42c2a-163">[Beheer](manage-incidents.md) de eigenschappen van het incident voor tags, toewijzing, onmiddellijke oplossing voor fout-positieve incidenten en opmerkingen.</span><span class="sxs-lookup"><span data-stu-id="42c2a-163">[Manage](manage-incidents.md) the properties of the incident for tags, assignment, immediate resolution for false positive incidents, and comments.</span></span>
- <span data-ttu-id="42c2a-164">Begin uw [onderzoeken.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="42c2a-164">Begin your [investigations](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="42c2a-165">Zie ook</span><span class="sxs-lookup"><span data-stu-id="42c2a-165">See also</span></span>
- [<span data-ttu-id="42c2a-166">Overzicht van incidenten</span><span class="sxs-lookup"><span data-stu-id="42c2a-166">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="42c2a-167">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="42c2a-167">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="42c2a-168">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="42c2a-168">Investigate incidents</span></span>](investigate-incidents.md)
