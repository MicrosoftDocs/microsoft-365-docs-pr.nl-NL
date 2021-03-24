---
title: Nieuwe bedreigingen bijhouden en beantwoorden met ATP-bedreigingsanalyse van Microsoft Defender
ms.reviewer: ''
description: Meer informatie over nieuwe bedreigingen en aanvalstechnieken en hoe u deze kunt stoppen. Beoordeel de impact ervan op uw organisatie en evalueer uw organisatiebestendigheid.
keywords: bedreigingsanalyse, risicoanalyse, mitigatie van besturingssysteem, microcodebeperking, mitigatiestatus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f532d20e4fb7cfa101eb6b96a89a4dbc4e658956
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060673"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="7e1c6-105">Nieuwe bedreigingen bijhouden en beantwoorden met bedreigingsanalyse</span><span class="sxs-lookup"><span data-stu-id="7e1c6-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7e1c6-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7e1c6-106">**Applies to:**</span></span>
- [<span data-ttu-id="7e1c6-107">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="7e1c6-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7e1c6-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7e1c6-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7e1c6-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="7e1c6-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7e1c6-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="7e1c6-111">Met geavanceerdere tegenstanders en nieuwe bedreigingen die regelmatig en regelmatig verschijnen, is het essentieel om snel te kunnen:</span><span class="sxs-lookup"><span data-stu-id="7e1c6-111">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="7e1c6-112">De impact van nieuwe bedreigingen beoordelen</span><span class="sxs-lookup"><span data-stu-id="7e1c6-112">Assess the impact of new threats</span></span>
- <span data-ttu-id="7e1c6-113">Uw tolerantie voor of blootstelling aan de bedreigingen controleren</span><span class="sxs-lookup"><span data-stu-id="7e1c6-113">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="7e1c6-114">De acties identificeren die u kunt uitvoeren om de bedreigingen te stoppen of te bevatten</span><span class="sxs-lookup"><span data-stu-id="7e1c6-114">Identify the actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="7e1c6-115">Bedreigingsanalyse is een reeks rapporten van deskundige Microsoft-beveiligingsonderzoekers over de meest relevante bedreigingen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="7e1c6-115">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats, including:</span></span>

- <span data-ttu-id="7e1c6-116">Actieve bedreigingsacteurs en hun campagnes</span><span class="sxs-lookup"><span data-stu-id="7e1c6-116">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="7e1c6-117">Populaire en nieuwe aanvalstechnieken</span><span class="sxs-lookup"><span data-stu-id="7e1c6-117">Popular and new attack techniques</span></span>
- <span data-ttu-id="7e1c6-118">Kritieke beveiligingslekken</span><span class="sxs-lookup"><span data-stu-id="7e1c6-118">Critical vulnerabilities</span></span>
- <span data-ttu-id="7e1c6-119">Veelvoorkomende aanvalsoppervlakken</span><span class="sxs-lookup"><span data-stu-id="7e1c6-119">Common attack surfaces</span></span>
- <span data-ttu-id="7e1c6-120">Voorkomende malware</span><span class="sxs-lookup"><span data-stu-id="7e1c6-120">Prevalent malware</span></span>

<span data-ttu-id="7e1c6-121">Elk rapport bevat een gedetailleerde analyse van een bedreiging en uitgebreide richtlijnen voor het beschermen tegen die bedreiging.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-121">Each report provides a detailed analysis of a threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="7e1c6-122">Het bevat ook gegevens uit uw netwerk, waarmee wordt aangegeven of de bedreiging actief is en of u over toepasselijke beveiliging beschikt.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-122">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

<span data-ttu-id="7e1c6-123">Bekijk deze korte video voor meer informatie over hoe u met bedreigingsanalyse de meest recente bedreigingen kunt bijhouden en stoppen.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-123">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="7e1c6-124">Het dashboard bedreigingsanalyse bekijken</span><span class="sxs-lookup"><span data-stu-id="7e1c6-124">View the threat analytics dashboard</span></span>

<span data-ttu-id="7e1c6-125">Het dashboard bedreigingsanalyse is een goed uitgangspunt om naar de rapporten te gaan die het meest relevant zijn voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-125">The threat analytics dashboard is a great jump off point for getting to the reports that are most relevant to your organization.</span></span> <span data-ttu-id="7e1c6-126">De bedreigingen worden in de volgende secties samengevat:</span><span class="sxs-lookup"><span data-stu-id="7e1c6-126">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="7e1c6-127">**Meest recente bedreigingen:** bevat de meest recent gepubliceerde bedreigingsrapporten, samen met het aantal apparaten met actieve en opgeloste waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-127">**Latest threats**—lists the most recently published threat reports, along with the number of devices with active and resolved alerts.</span></span>
- <span data-ttu-id="7e1c6-128">**Bedreigingen met een hoge** impact : hier worden de bedreigingen vermeld die de grootste impact hebben gehad op de organisatie.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-128">**High-impact threats**—lists the threats that have had the highest impact to the organization.</span></span> <span data-ttu-id="7e1c6-129">In deze sectie worden bedreigingen gerangeerd op het aantal apparaten met actieve waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-129">This section ranks threats by the number of devices that have active alerts.</span></span>
- <span data-ttu-id="7e1c6-130">**Overzicht van** bedreigingen: toont de algehele impact van bijgespoorde bedreigingen door het aantal bedreigingen met actieve en opgeloste waarschuwingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-130">**Threat summary**—shows the overall impact of tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="7e1c6-131">Selecteer een bedreiging in het dashboard om het rapport voor die bedreiging weer te geven.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-131">Select a threat from the dashboard to view the report for that threat.</span></span>

![Afbeelding van een dashboard voor bedreigingsanalyse](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="7e1c6-133">Een bedreigingsanalyserapport weergeven</span><span class="sxs-lookup"><span data-stu-id="7e1c6-133">View a threat analytics report</span></span>

<span data-ttu-id="7e1c6-134">Elk rapport voor bedreigingsanalyse bevat informatie in drie secties: **Overzicht,** **Analistrapport** en **Mitigaties.**</span><span class="sxs-lookup"><span data-stu-id="7e1c6-134">Each threat analytics report provides information in three sections: **Overview**, **Analyst report**, and **Mitigations**.</span></span>

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="7e1c6-135">Overzicht: Snel inzicht krijgen in de bedreiging, de impact ervan beoordelen en verdedigingslinie bekijken</span><span class="sxs-lookup"><span data-stu-id="7e1c6-135">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="7e1c6-136">De **sectie** Overzicht bevat een voorbeeld van het gedetailleerde analistenrapport.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-136">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="7e1c6-137">Het bevat ook grafieken die de impact van de bedreiging voor uw organisatie en uw blootstelling markeren via verkeerd geconfigureerde en ongepatchte apparaten.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-137">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

<span data-ttu-id="7e1c6-138">![Afbeelding van de overzichtssectie van een rapport Voor bedreigingsanalyse ](images/ta-overview.png)
 _Overzicht sectie van een bedreigingsanalyserapport_</span><span class="sxs-lookup"><span data-stu-id="7e1c6-138">![Image of the overview section of a threat analytics report](images/ta-overview.png)
_Overview section of a threat analytics report_</span></span>

#### <a name="assess-the-impact-to-your-organization"></a><span data-ttu-id="7e1c6-139">De impact voor uw organisatie beoordelen</span><span class="sxs-lookup"><span data-stu-id="7e1c6-139">Assess the impact to your organization</span></span>
<span data-ttu-id="7e1c6-140">Elk rapport bevat grafieken die zijn ontworpen om informatie te verstrekken over de invloed van een bedreiging op de organisatie:</span><span class="sxs-lookup"><span data-stu-id="7e1c6-140">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>
- <span data-ttu-id="7e1c6-141">**Apparaten met waarschuwingen**: toont het huidige aantal verschillende apparaten dat door de bedreiging is beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-141">**Devices with alerts**—shows the current number of distinct devices that have been impacted by the threat.</span></span> <span data-ttu-id="7e1c6-142">Een apparaat wordt gecategoriseerd als Actief als er  ten  minste één waarschuwing is gekoppeld aan die bedreiging en Opgelost als alle waarschuwingen die zijn gekoppeld aan de bedreiging op het apparaat zijn opgelost. </span><span class="sxs-lookup"><span data-stu-id="7e1c6-142">A device is categorized as **Active** if there is at least one alert associated with that threat and **Resolved** if *all* alerts associated with the threat on the device have been resolved.</span></span>
- <span data-ttu-id="7e1c6-143">**Apparaten met waarschuwingen in de tijd**: toont het aantal verschillende apparaten met **actieve** en **opgeloste** waarschuwingen in de tijd.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-143">**Devices with alerts over time**—shows the number of distinct devices with **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="7e1c6-144">Het aantal opgeloste waarschuwingen geeft aan hoe snel uw organisatie reageert op waarschuwingen die zijn gekoppeld aan een bedreiging.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-144">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="7e1c6-145">In het ideale kader moet de grafiek binnen enkele dagen waarschuwingen weergeven die zijn opgelost.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-145">Ideally, the chart should be showing alerts resolved within a few days.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="7e1c6-146">Beveiligingsweerbaarheid en -houding controleren</span><span class="sxs-lookup"><span data-stu-id="7e1c6-146">Review security resilience and posture</span></span>
<span data-ttu-id="7e1c6-147">Elk rapport bevat grafieken die een overzicht geven van hoe veerkrachtig uw organisatie is tegen een bepaalde bedreiging:</span><span class="sxs-lookup"><span data-stu-id="7e1c6-147">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>
- <span data-ttu-id="7e1c6-148">**Beveiligingsconfiguratiestatus:** toont het aantal apparaten dat de aanbevolen beveiligingsinstellingen heeft toegepast om de bedreiging te beperken.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-148">**Security configuration status**—shows the number of devices that have applied the recommended security settings that can help mitigate the threat.</span></span> <span data-ttu-id="7e1c6-149">Apparaten worden beschouwd **als Veilig** als ze alle _bijgespoorde_ instellingen hebben toegepast.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-149">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="7e1c6-150">**Status van beveiligingspatches:** toont het aantal apparaten dat beveiligingsupdates of patches heeft toegepast waarmee beveiligingsproblemen worden aangepakt die door de bedreiging worden misbruikt.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-150">**Vulnerability patching status**—shows the number of devices that have applied security updates or patches that address vulnerabilities exploited by the threat.</span></span>

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="7e1c6-151">Analistrapport: Krijg inzicht van microsoft-beveiligingsonderzoekers</span><span class="sxs-lookup"><span data-stu-id="7e1c6-151">Analyst report: Get expert insight from Microsoft security researchers</span></span>
<span data-ttu-id="7e1c6-152">Ga naar de **sectie Analistrapport** om de gedetailleerde expert write-up te lezen.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-152">Go to the **Analyst report** section to read through the detailed expert write-up.</span></span> <span data-ttu-id="7e1c6-153">De meeste rapporten bevatten gedetailleerde beschrijvingen van aanvalsketens, waaronder tactieken en technieken die zijn toegesneden op het MITRE ATT&CK-framework, uitgebreide lijsten met aanbevelingen en krachtige richtlijnen voor het zoeken naar [bedreigingen.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7e1c6-153">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="7e1c6-154">Meer informatie over het analistenrapport</span><span class="sxs-lookup"><span data-stu-id="7e1c6-154">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="7e1c6-155">Risicobeperking: Lijst met risico's en de status van uw apparaten controleren</span><span class="sxs-lookup"><span data-stu-id="7e1c6-155">Mitigations: Review list of mitigations and the status of your devices</span></span>
<span data-ttu-id="7e1c6-156">Bekijk in **de sectie Mitigaties** de lijst met specifieke actie-aanbevelingen die u kunnen helpen uw organisatieweerbaarheid tegen de bedreiging te vergroten.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-156">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="7e1c6-157">De lijst met bijgespoorde risico's bevat:</span><span class="sxs-lookup"><span data-stu-id="7e1c6-157">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="7e1c6-158">**Beveiligingsupdates**: implementatie van beveiligingsupdates of patches voor beveiligingsproblemen</span><span class="sxs-lookup"><span data-stu-id="7e1c6-158">**Security updates**—deployment of security updates or patches for vulnerabilities</span></span>
- <span data-ttu-id="7e1c6-159">**Microsoft Defender Antivirus-instellingen**</span><span class="sxs-lookup"><span data-stu-id="7e1c6-159">**Microsoft Defender Antivirus settings**</span></span>
  - <span data-ttu-id="7e1c6-160">Versie van beveiligingsinformatie</span><span class="sxs-lookup"><span data-stu-id="7e1c6-160">Security intelligence version</span></span>
  - <span data-ttu-id="7e1c6-161">Beveiliging in de cloud</span><span class="sxs-lookup"><span data-stu-id="7e1c6-161">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="7e1c6-162">Potentieel ongewenste toepassingsbeveiliging (PUA)</span><span class="sxs-lookup"><span data-stu-id="7e1c6-162">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="7e1c6-163">Realtime beveiliging</span><span class="sxs-lookup"><span data-stu-id="7e1c6-163">Real-time protection</span></span>
 
<span data-ttu-id="7e1c6-164">Mitigatiegegevens in deze [](next-gen-threat-and-vuln-mgt.md)sectie bevatten gegevens van bedreigings- en kwetsbaarheidsbeheer, die ook gedetailleerde inzoomgegevens bevatten van verschillende koppelingen in het rapport.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-164">Mitigation information in this section incorporates data from [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md), which also provides detailed drill-down information from various links in the report.</span></span>

<span data-ttu-id="7e1c6-165">![Afbeelding van de sectie risicobeperking van een sectie ](images/ta-mitigations.png)
 _Risicoanalyse-sectie Mitigatie van een bedreigingsanalyserapport_</span><span class="sxs-lookup"><span data-stu-id="7e1c6-165">![Image of the mitigations section of a threat analytics report](images/ta-mitigations.png)
_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="7e1c6-166">Aanvullende rapportdetails en -beperkingen</span><span class="sxs-lookup"><span data-stu-id="7e1c6-166">Additional report details and limitations</span></span>
<span data-ttu-id="7e1c6-167">Houd bij het gebruik van de rapporten rekening met het volgende:</span><span class="sxs-lookup"><span data-stu-id="7e1c6-167">When using the reports, keep the following in mind:</span></span> 

- <span data-ttu-id="7e1c6-168">Gegevens hebben een bereik op basis van uw RBAC-bereik (Role-Based Access Control).</span><span class="sxs-lookup"><span data-stu-id="7e1c6-168">Data is scoped based on your role-based access control (RBAC) scope.</span></span> <span data-ttu-id="7e1c6-169">U ziet de status van apparaten in [groepen die u kunt openen.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="7e1c6-169">You will see the status of devices in [groups that you can access](machine-groups.md).</span></span>
- <span data-ttu-id="7e1c6-170">Grafieken geven alleen risico's weer die worden bijgespoord.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-170">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="7e1c6-171">Controleer het rapportoverzicht op aanvullende risico's die niet in de grafieken worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-171">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="7e1c6-172">Risicobeperking garandeert geen volledige tolerantie.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-172">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="7e1c6-173">De geleverde risico's weerspiegelen de best mogelijke acties die nodig zijn om de tolerantie te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-173">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="7e1c6-174">Apparaten worden geteld als 'niet beschikbaar' als ze geen gegevens naar de service hebben verzonden.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-174">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="7e1c6-175">Antivirusgerelateerde statistieken zijn gebaseerd op de antivirusinstellingen van Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-175">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="7e1c6-176">Apparaten met antivirusoplossingen van derden kunnen worden weergegeven als 'blootgesteld'.</span><span class="sxs-lookup"><span data-stu-id="7e1c6-176">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="7e1c6-177">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7e1c6-177">Related topics</span></span>
- [<span data-ttu-id="7e1c6-178">Proactief bedreigingen zoeken met geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="7e1c6-178">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="7e1c6-179">De sectie Analistrapport begrijpen</span><span class="sxs-lookup"><span data-stu-id="7e1c6-179">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="7e1c6-180">Beveiligingszwakheden en blootstellingen beoordelen en oplossen</span><span class="sxs-lookup"><span data-stu-id="7e1c6-180">Assess and resolve security weaknesses and exposures</span></span>](next-gen-threat-and-vuln-mgt.md)