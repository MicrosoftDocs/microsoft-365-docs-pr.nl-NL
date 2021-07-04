---
title: Nieuwe bedreigingen bijhouden en beantwoorden met bedreigingsanalyse
ms.reviewer: ''
description: Meer informatie over nieuwe bedreigingen en aanvalstechnieken en hoe u deze kunt stoppen. Beoordeel de impact ervan op uw organisatie en evalueer uw organisatiebestendigheid.
keywords: bedreigingsanalyse, risicoanalyse, Microsoft 365 Defender, M365D, mitigatiestatus, veilige configuratie, Microsoft Defender voor Office 365, Microsoft Defender voor Office 365 bedreigingsanalyse, MDO-bedreigingsanalyse, geïntegreerde MDE- en MDO-bedreigingsanalysegegevens, integratie van bedreigingsanalysegegevens, geïntegreerde Microsoft 365 Defender bedreigingsanalyse
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c03dfef28744e2ee565c25d921902b8d11ecb7a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290241"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="1eddc-105">Nieuwe bedreigingen bijhouden en beantwoorden met bedreigingsanalyse</span><span class="sxs-lookup"><span data-stu-id="1eddc-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1eddc-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1eddc-106">**Applies to:**</span></span>
- <span data-ttu-id="1eddc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1eddc-107">Microsoft 365 Defender</span></span>

> <span data-ttu-id="1eddc-108">Wilt u Microsoft 365 Defender ervaren?</span><span class="sxs-lookup"><span data-stu-id="1eddc-108">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="1eddc-109">U kunt het [evalueren in een testomgeving](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) of [uw pilotproject uitvoeren in een productieomgeving](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="1eddc-109">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="1eddc-110">Bedreigingsanalyse is onze in-product threat intelligence-oplossing van deskundige Microsoft-beveiligingsonderzoekers, ontworpen om beveiligingsteams te helpen zo efficiënt mogelijk te werken terwijl ze geconfronteerd worden met nieuwe bedreigingen, zoals:</span><span class="sxs-lookup"><span data-stu-id="1eddc-110">Threat analytics is our in-product threat intelligence solution from expert Microsoft security researchers, designed to assist security teams to be as efficient as possible while facing emerging threats, including:</span></span>

- <span data-ttu-id="1eddc-111">Actieve bedreigingsacteurs en hun campagnes</span><span class="sxs-lookup"><span data-stu-id="1eddc-111">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="1eddc-112">Populaire en nieuwe aanvalstechnieken</span><span class="sxs-lookup"><span data-stu-id="1eddc-112">Popular and new attack techniques</span></span>
- <span data-ttu-id="1eddc-113">Kritieke beveiligingslekken</span><span class="sxs-lookup"><span data-stu-id="1eddc-113">Critical vulnerabilities</span></span>
- <span data-ttu-id="1eddc-114">Veelvoorkomende aanvalsoppervlakken</span><span class="sxs-lookup"><span data-stu-id="1eddc-114">Common attack surfaces</span></span>
- <span data-ttu-id="1eddc-115">Voorkomende malware</span><span class="sxs-lookup"><span data-stu-id="1eddc-115">Prevalent malware</span></span>

<span data-ttu-id="1eddc-116">Bekijk deze korte video voor meer informatie over hoe u met bedreigingsanalyse de meest recente bedreigingen kunt bijhouden en stoppen.</span><span class="sxs-lookup"><span data-stu-id="1eddc-116">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWwJfU]

<span data-ttu-id="1eddc-117">U kunt bedreigingsanalyse openen vanaf de linkerbovenhoek van de navigatiebalk van Microsoft 365 beveiligingsportal of via een speciale dashboardkaart met de belangrijkste bedreigingen in uw organisatie. Als u inzicht krijgt in actieve of lopende campagnes en weet wat u moet doen via bedreigingsanalyses, kunt u uw beveiligingsteam voorzien van weloverwogen beslissingen.</span><span class="sxs-lookup"><span data-stu-id="1eddc-117">You can access threat analytics either from the upper left-hand side of Microsoft 365 security portal’s navigation bar, or from a dedicated dashboard card which shows the top threats in your org. Getting visibility on active or ongoing campaigns and knowing what to do through threat analytics can help equip your security operations team with informed decisions.</span></span> 

![Afbeelding van het dashboard bedreigingsanalyse](../../media/threat-analytics/ta_inlandingpage_mtp.png)

<span data-ttu-id="1eddc-119">_Waar toegang tot bedreigingsanalyse_</span><span class="sxs-lookup"><span data-stu-id="1eddc-119">_Where to access threat analytics_</span></span>

<span data-ttu-id="1eddc-120">Met geavanceerdere tegenstanders en nieuwe bedreigingen die regelmatig en regelmatig verschijnen, is het essentieel om snel te kunnen:</span><span class="sxs-lookup"><span data-stu-id="1eddc-120">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="1eddc-121">Nieuwe bedreigingen identificeren en erop reageren</span><span class="sxs-lookup"><span data-stu-id="1eddc-121">Identify and react to emerging threats</span></span>
- <span data-ttu-id="1eddc-122">Informatie over of u momenteel wordt aangevallen</span><span class="sxs-lookup"><span data-stu-id="1eddc-122">Learn if you are currently under attack</span></span>
- <span data-ttu-id="1eddc-123">Het effect van de bedreiging voor uw activa beoordelen</span><span class="sxs-lookup"><span data-stu-id="1eddc-123">Assess the impact of the threat to your assets</span></span>
- <span data-ttu-id="1eddc-124">Uw tolerantie voor of blootstelling aan de bedreigingen controleren</span><span class="sxs-lookup"><span data-stu-id="1eddc-124">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="1eddc-125">Identificeer de risicobeperkings-, herstel- of preventieacties die u kunt ondernemen om de bedreigingen te stoppen of te bevatten</span><span class="sxs-lookup"><span data-stu-id="1eddc-125">Identify the mitigation, recovery, or prevention actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="1eddc-126">Elk rapport bevat een analyse van een bijgespoorde bedreiging en uitgebreide richtlijnen voor het beschermen tegen die bedreiging.</span><span class="sxs-lookup"><span data-stu-id="1eddc-126">Each report provides an analysis of a tracked threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="1eddc-127">Het bevat ook gegevens uit uw netwerk, waarmee wordt aangegeven of de bedreiging actief is en of u over toepasselijke beveiliging beschikt.</span><span class="sxs-lookup"><span data-stu-id="1eddc-127">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="1eddc-128">Het dashboard bedreigingsanalyse bekijken</span><span class="sxs-lookup"><span data-stu-id="1eddc-128">View the threat analytics dashboard</span></span>

<span data-ttu-id="1eddc-129">In het dashboard bedreigingsanalyse[(security.microsoft.com/threatanalytics3)](https://security.microsoft.com/threatanalytics3)worden de rapporten belicht die het meest relevant zijn voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="1eddc-129">The threat analytics dashboard ([security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3)) highlights the reports that are most relevant to your organization.</span></span> <span data-ttu-id="1eddc-130">De bedreigingen worden in de volgende secties samengevat:</span><span class="sxs-lookup"><span data-stu-id="1eddc-130">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="1eddc-131">**Meest recente bedreigingen:** bevat de meest recent gepubliceerde of bijgewerkte bedreigingsrapporten, samen met het aantal actieve en opgeloste waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="1eddc-131">**Latest threats**—lists the most recently published or updated threat reports, along with the number of active and resolved alerts.</span></span>
- <span data-ttu-id="1eddc-132">**Bedreigingen met een hoge** impact : hier worden de bedreigingen vermeld die de grootste impact hebben op uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="1eddc-132">**High-impact threats**—lists the threats that have the highest impact to your organization.</span></span> <span data-ttu-id="1eddc-133">In deze sectie worden eerst bedreigingen met het hoogste aantal actieve en opgeloste waarschuwingen vermeld.</span><span class="sxs-lookup"><span data-stu-id="1eddc-133">This section lists threats with the highest number of active and resolved alerts first.</span></span>
- <span data-ttu-id="1eddc-134">**Overzicht van** bedreigingen: geeft de algehele impact van alle bijgespoorde bedreigingen door het aantal bedreigingen met actieve en opgeloste waarschuwingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="1eddc-134">**Threat summary**—provides the overall impact of all tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="1eddc-135">Selecteer een bedreiging in het dashboard om het rapport voor die bedreiging weer te geven.</span><span class="sxs-lookup"><span data-stu-id="1eddc-135">Select a threat from the dashboard to view the report for that threat.</span></span>

![Schermafbeelding van het dashboard bedreigingsanalyse](../../media/threat-analytics/ta_dashboard_mtp.png)

<span data-ttu-id="1eddc-137">_Dashboard Bedreigingsanalyse. U kunt ook op het pictogram Zoeken klikken om een sleutel te geven in een trefwoord dat betrekking heeft op het rapport bedreigingsanalyse dat u wilt lezen._</span><span class="sxs-lookup"><span data-stu-id="1eddc-137">_Threat analytics dashboard. You can also click the Search icon to key in a keyword related to the threat analytics report that you'd like to read._</span></span> 

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="1eddc-138">Een bedreigingsanalyserapport weergeven</span><span class="sxs-lookup"><span data-stu-id="1eddc-138">View a threat analytics report</span></span>

<span data-ttu-id="1eddc-139">Elk bedreigingsanalyserapport bevat informatie in verschillende secties:</span><span class="sxs-lookup"><span data-stu-id="1eddc-139">Each threat analytics report provides information in several sections:</span></span>

- [<span data-ttu-id="1eddc-140">**Overzicht**</span><span class="sxs-lookup"><span data-stu-id="1eddc-140">**Overview**</span></span>](#overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses)
- [<span data-ttu-id="1eddc-141">**Analistrapport**</span><span class="sxs-lookup"><span data-stu-id="1eddc-141">**Analyst report**</span></span>](#analyst-report-get-expert-insight-from-microsoft-security-researchers)
- [<span data-ttu-id="1eddc-142">**Gerelateerde incidenten**</span><span class="sxs-lookup"><span data-stu-id="1eddc-142">**Related incidents**</span></span>](#related-incidents-view-and-manage-related-incidents)
- [<span data-ttu-id="1eddc-143">**Beïnvloede activa**</span><span class="sxs-lookup"><span data-stu-id="1eddc-143">**Impacted assets**</span></span>](#impacted-assets-get-list-of-impacted-devices-and-mailboxes)
- [<span data-ttu-id="1eddc-144">**E-mailpogingen voorkomen**</span><span class="sxs-lookup"><span data-stu-id="1eddc-144">**Prevented email attempts**</span></span>](#prevented-email-attempts-view-blocked-or-junked-threat-emails)
- [<span data-ttu-id="1eddc-145">**Risico's**</span><span class="sxs-lookup"><span data-stu-id="1eddc-145">**Mitigations**</span></span>](#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="1eddc-146">Overzicht: Snel inzicht krijgen in de bedreiging, de impact ervan beoordelen en verdedigingslinie bekijken</span><span class="sxs-lookup"><span data-stu-id="1eddc-146">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="1eddc-147">De **sectie** Overzicht bevat een voorbeeld van het gedetailleerde analistenrapport.</span><span class="sxs-lookup"><span data-stu-id="1eddc-147">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="1eddc-148">Het bevat ook grafieken die de impact van de bedreiging voor uw organisatie en uw blootstelling markeren via verkeerd geconfigureerde en ongepatchte apparaten.</span><span class="sxs-lookup"><span data-stu-id="1eddc-148">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

![Afbeelding van de overzichtssectie van een rapport voor bedreigingsanalyse](../../media/threat-analytics/ta_overview_mtp.png)

<span data-ttu-id="1eddc-150">_Overzichtssectie van een rapport voor bedreigingsanalyse_</span><span class="sxs-lookup"><span data-stu-id="1eddc-150">_Overview section of a threat analytics report_</span></span>

#### <a name="assess-impact-on-your-organization"></a><span data-ttu-id="1eddc-151">De impact op uw organisatie beoordelen</span><span class="sxs-lookup"><span data-stu-id="1eddc-151">Assess impact on your organization</span></span>

<span data-ttu-id="1eddc-152">Elk rapport bevat grafieken die zijn ontworpen om informatie te verstrekken over de invloed van een bedreiging op de organisatie:</span><span class="sxs-lookup"><span data-stu-id="1eddc-152">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>

- <span data-ttu-id="1eddc-153">**Gerelateerde incidenten**: geeft een overzicht van de impact van de bijgespoorde bedreiging voor uw organisatie met de volgende gegevens:</span><span class="sxs-lookup"><span data-stu-id="1eddc-153">**Related incidents**—provides an overview of the impact of the tracked threat to your organization with the following data:</span></span>
  - <span data-ttu-id="1eddc-154">Aantal actieve waarschuwingen en het aantal actieve incidenten dat aan deze meldingen is gekoppeld</span><span class="sxs-lookup"><span data-stu-id="1eddc-154">Number of active alerts and the number of active incidents they are associated with</span></span>
  - <span data-ttu-id="1eddc-155">Ernst van actieve incidenten</span><span class="sxs-lookup"><span data-stu-id="1eddc-155">Severity of active incidents</span></span>
- <span data-ttu-id="1eddc-156">**Waarschuwingen in de tijd**: toont het aantal gerelateerde **actieve** en **opgeloste** waarschuwingen in de tijd.</span><span class="sxs-lookup"><span data-stu-id="1eddc-156">**Alerts over time**—shows the number of related **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="1eddc-157">Het aantal opgeloste waarschuwingen geeft aan hoe snel uw organisatie reageert op waarschuwingen die zijn gekoppeld aan een bedreiging.</span><span class="sxs-lookup"><span data-stu-id="1eddc-157">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="1eddc-158">In het ideale kader moet de grafiek binnen enkele dagen waarschuwingen weergeven die zijn opgelost.</span><span class="sxs-lookup"><span data-stu-id="1eddc-158">Ideally, the chart should be showing alerts resolved within a few days.</span></span>
- <span data-ttu-id="1eddc-159">**Beïnvloede activa:** toont het aantal verschillende apparaten en e-mailaccounts (postvakken) dat momenteel ten minste één actieve waarschuwing aan de bijgespoorde bedreiging heeft gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="1eddc-159">**Impacted assets**—shows the number of distinct devices and email accounts (mailboxes) that currently have at least one active alert associated with the tracked threat.</span></span> <span data-ttu-id="1eddc-160">Waarschuwingen worden geactiveerd voor postvakken die e-mailberichten met bedreigingen hebben ontvangen.</span><span class="sxs-lookup"><span data-stu-id="1eddc-160">Alerts are triggered for mailboxes that received threat emails.</span></span> <span data-ttu-id="1eddc-161">Controleer zowel het beleid op organisatie- als gebruikersniveau voor overschrijven die de bezorging van e-mailberichten met bedreigingen veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="1eddc-161">Review both org- and user-level policies for overrides that cause the delivery of threat emails.</span></span>
- <span data-ttu-id="1eddc-162">**E-mailpogingen voorkomen:** toont het aantal e-mailberichten van de afgelopen zeven dagen dat vóór de bezorging is geblokkeerd of die zijn bezorgd in de map ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="1eddc-162">**Prevented email attempts**—shows the number of emails from the past seven days that were either blocked before delivery or delivered to the junk mail folder.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="1eddc-163">Beveiligingsweerbaarheid en -houding controleren</span><span class="sxs-lookup"><span data-stu-id="1eddc-163">Review security resilience and posture</span></span>

<span data-ttu-id="1eddc-164">Elk rapport bevat grafieken die een overzicht geven van hoe veerkrachtig uw organisatie is tegen een bepaalde bedreiging:</span><span class="sxs-lookup"><span data-stu-id="1eddc-164">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>

- <span data-ttu-id="1eddc-165">**Veilige configuratiestatus:** toont het aantal apparaten met verkeerd geconfigureerde beveiligingsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="1eddc-165">**Secure configuration status**—shows the number of devices with misconfigured security settings.</span></span> <span data-ttu-id="1eddc-166">Pas de aanbevolen beveiligingsinstellingen toe om de bedreiging te beperken.</span><span class="sxs-lookup"><span data-stu-id="1eddc-166">Apply the recommended security settings to help mitigate the threat.</span></span> <span data-ttu-id="1eddc-167">Apparaten worden beschouwd **als Veilig** als ze alle _bijgespoorde_ instellingen hebben toegepast.</span><span class="sxs-lookup"><span data-stu-id="1eddc-167">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="1eddc-168">**Beveiligingspatchingstatus**: geeft het aantal kwetsbare apparaten weer.</span><span class="sxs-lookup"><span data-stu-id="1eddc-168">**Vulnerability patching status**—shows the number of vulnerable devices.</span></span> <span data-ttu-id="1eddc-169">Pas beveiligingsupdates of patches toe om beveiligingsproblemen aan te pakken die door de bedreiging worden misbruikt.</span><span class="sxs-lookup"><span data-stu-id="1eddc-169">Apply security updates or patches to address vulnerabilities exploited by the threat.</span></span>

#### <a name="view-reports-per-threat-tags"></a><span data-ttu-id="1eddc-170">Rapporten per bedreigingslabels weergeven</span><span class="sxs-lookup"><span data-stu-id="1eddc-170">View reports per threat tags</span></span>

<span data-ttu-id="1eddc-171">U kunt de lijst met bedreigingsrapporten filteren en de meest relevante rapporten weergeven op basis van een specifieke bedreigingslabel (categorie) of een rapporttype.</span><span class="sxs-lookup"><span data-stu-id="1eddc-171">You can filter the threat report list and view the most relevant reports according to a specific threat tag (category) or a report type.</span></span>

- <span data-ttu-id="1eddc-172">**Bedreigingslabels:** help u bij het weergeven van de meest relevante rapporten op basis van een specifieke bedreigingscategorie.</span><span class="sxs-lookup"><span data-stu-id="1eddc-172">**Threat tags**—assist you in viewing the most relevant reports according to a specific threat category.</span></span> <span data-ttu-id="1eddc-173">Bijvoorbeeld alle rapporten met betrekking tot ransomware.</span><span class="sxs-lookup"><span data-stu-id="1eddc-173">For example, all reports related to ransomware.</span></span>
- <span data-ttu-id="1eddc-174">**Rapporttypen:** help u bij het weergeven van de meest relevante rapporten op basis van een specifiek rapporttype.</span><span class="sxs-lookup"><span data-stu-id="1eddc-174">**Report types**—assist you in viewing the most relevant reports according to a specific report type.</span></span> <span data-ttu-id="1eddc-175">Bijvoorbeeld alle rapporten die betrekking hebben op hulpmiddelen en technieken.</span><span class="sxs-lookup"><span data-stu-id="1eddc-175">For example, all reports that cover tools and techniques.</span></span> 
- <span data-ttu-id="1eddc-176">**Filters:** help u bij het efficiënt controleren van de lijst met bedreigingsrapports en het filteren van de weergave op basis van een specifiek bedreigingslabel of rapporttype.</span><span class="sxs-lookup"><span data-stu-id="1eddc-176">**Filters**—assist you in efficiently reviewing the threat report list and filtering the view based on a specific threat tag or report type.</span></span> <span data-ttu-id="1eddc-177">Bekijk bijvoorbeeld alle bedreigingsrapporten met betrekking tot ransomwarecategorie of bedreigingsrapporten die betrekking hebben op beveiligingslekken.</span><span class="sxs-lookup"><span data-stu-id="1eddc-177">For example, review all threat reports related to ransomware category, or threat reports that cover vulnerabilities.</span></span>

##### <a name="how-does-it-work"></a><span data-ttu-id="1eddc-178">Hoe werkt dit?</span><span class="sxs-lookup"><span data-stu-id="1eddc-178">How does it work?</span></span>

<span data-ttu-id="1eddc-179">Het Microsoft Threat Intelligence-team heeft bedreigingslabels toegevoegd aan elk bedreigingsrapport:</span><span class="sxs-lookup"><span data-stu-id="1eddc-179">The Microsoft Threat Intelligence team has added threat tags to each threat report:</span></span>

- <span data-ttu-id="1eddc-180">Er zijn nu vier bedreigingslabels beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="1eddc-180">Four threat tags are now available:</span></span>
  - <span data-ttu-id="1eddc-181">Ransomware</span><span class="sxs-lookup"><span data-stu-id="1eddc-181">Ransomware</span></span>
  - <span data-ttu-id="1eddc-182">Phishing</span><span class="sxs-lookup"><span data-stu-id="1eddc-182">Phishing</span></span>
  - <span data-ttu-id="1eddc-183">beveiligingsprobleem</span><span class="sxs-lookup"><span data-stu-id="1eddc-183">Vulnerability</span></span>
  - <span data-ttu-id="1eddc-184">Activiteitsgroep</span><span class="sxs-lookup"><span data-stu-id="1eddc-184">Activity group</span></span>
- <span data-ttu-id="1eddc-185">Bedreigingslabels worden boven aan de pagina bedreigingsanalyse weergegeven, met tellers voor het aantal beschikbare rapporten onder elke tag.</span><span class="sxs-lookup"><span data-stu-id="1eddc-185">Threat tags are presented at the top of the threat analytics page, with counters for the number of available reports under each tag.</span></span>

  ![bedreigingslabels](../../media/threat-analytics/ta-threattags-mtp.png)

- <span data-ttu-id="1eddc-187">De lijst kan ook worden gesorteerd op bedreigingslabels:</span><span class="sxs-lookup"><span data-stu-id="1eddc-187">The list can also be sorted by threat tags:</span></span>

  ![lijsten](../../media/threat-analytics//ta-taglist-mtp.png)

- <span data-ttu-id="1eddc-189">Filters zijn beschikbaar per bedreigingslabel en rapporttype:</span><span class="sxs-lookup"><span data-stu-id="1eddc-189">Filters are available per threat tag and report type:</span></span>

  ![filters](../../media/threat-analytics/ta-threattag-filters-mtp.png)

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="1eddc-191">Analistrapport: Krijg inzicht van microsoft-beveiligingsonderzoekers</span><span class="sxs-lookup"><span data-stu-id="1eddc-191">Analyst report: Get expert insight from Microsoft security researchers</span></span>

<span data-ttu-id="1eddc-192">Lees in **de sectie Rapportanalist** de gedetailleerde expert-write-up door.</span><span class="sxs-lookup"><span data-stu-id="1eddc-192">In the **Analyst report** section, read through the detailed expert write-up.</span></span> <span data-ttu-id="1eddc-193">De meeste rapporten bevatten gedetailleerde beschrijvingen van aanvalsketens, waaronder tactieken en technieken die zijn toegesneden op het MITRE ATT&CK-framework, uitgebreide lijsten met aanbevelingen en krachtige richtlijnen voor het zoeken naar [bedreigingen.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1eddc-193">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="1eddc-194">Meer informatie over het analistenrapport</span><span class="sxs-lookup"><span data-stu-id="1eddc-194">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="related-incidents-view-and-manage-related-incidents"></a><span data-ttu-id="1eddc-195">Verwante incidenten: Gerelateerde incidenten weergeven en beheren</span><span class="sxs-lookup"><span data-stu-id="1eddc-195">Related incidents: View and manage related incidents</span></span>

<span data-ttu-id="1eddc-196">Het **tabblad Gerelateerde incidenten** bevat de lijst met alle incidenten met betrekking tot de bijgespoorde bedreiging.</span><span class="sxs-lookup"><span data-stu-id="1eddc-196">The **Related incidents** tab provides the list of all incidents related to the tracked threat.</span></span> <span data-ttu-id="1eddc-197">U kunt incidenten toewijzen of waarschuwingen beheren die aan elk incident zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="1eddc-197">You can assign incidents or manage alerts linked to each incident.</span></span> 


![Afbeelding van de sectie verwante incidenten van een rapport over bedreigingsanalyse](../../media/threat-analytics/ta_related_incidents_mtp.png)

<span data-ttu-id="1eddc-199">_Sectie Verwante incidenten van een rapport over bedreigingsanalyse_</span><span class="sxs-lookup"><span data-stu-id="1eddc-199">_Related incidents section of a threat analytics report_</span></span>

### <a name="impacted-assets-get-list-of-impacted-devices-and-mailboxes"></a><span data-ttu-id="1eddc-200">Beïnvloede activa: Lijst met beïnvloede apparaten en postvakken</span><span class="sxs-lookup"><span data-stu-id="1eddc-200">Impacted assets: Get list of impacted devices and mailboxes</span></span>

<span data-ttu-id="1eddc-201">Een activum wordt als beïnvloed beschouwd als het wordt beïnvloed door een actieve, niet-opgeloste waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="1eddc-201">An asset is considered impacted if it is affected by an active, unresolved alert.</span></span> <span data-ttu-id="1eddc-202">Het **tabblad Beïnvloede activa** bevat de volgende typen beïnvloede activa:</span><span class="sxs-lookup"><span data-stu-id="1eddc-202">The **Impacted assets** tab lists the following types of impacted assets:</span></span>

- <span data-ttu-id="1eddc-203">**Beïnvloede apparaten:** eindpunten met niet-opgeloste waarschuwingen van Microsoft Defender voor eindpunten.</span><span class="sxs-lookup"><span data-stu-id="1eddc-203">**Impacted devices**—endpoints that have unresolved Microsoft Defender for Endpoint alerts.</span></span> <span data-ttu-id="1eddc-204">Deze waarschuwingen worden meestal gebruikt voor waarnemingen van bekende bedreigingsindicatoren en -activiteiten.</span><span class="sxs-lookup"><span data-stu-id="1eddc-204">These alerts typically fire on sightings of known threat indicators and activities.</span></span>
- <span data-ttu-id="1eddc-205">**Beïnvloede postvakken:** postvakken die e-mailberichten hebben ontvangen die Microsoft Defender hebben geactiveerd voor Office 365 waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="1eddc-205">**Impacted mailboxes**—mailboxes that have received email messages that have triggered Microsoft Defender for Office 365 alerts.</span></span> <span data-ttu-id="1eddc-206">Hoewel de meeste berichten die waarschuwingen activeren meestal worden geblokkeerd, kunnen beleidsregels op gebruikers- of organisatieniveau filters overschrijven.</span><span class="sxs-lookup"><span data-stu-id="1eddc-206">While most messages that trigger alerts are typically blocked, user- or org-level policies can override filters.</span></span>

![Afbeelding van de sectie beïnvloede activa van een bedreigingsanalyserapport](../../media/threat-analytics/ta_impacted_assets_mtp.png)

<span data-ttu-id="1eddc-208">_Sectie Beïnvloede activa van een rapport voor bedreigingsanalyse_</span><span class="sxs-lookup"><span data-stu-id="1eddc-208">_Impacted assets section of a threat analytics report_</span></span>

### <a name="prevented-email-attempts-view-blocked-or-junked-threat-emails"></a><span data-ttu-id="1eddc-209">E-mailpogingen voorkomen: geblokkeerde of ongewenste e-mailberichten weergeven</span><span class="sxs-lookup"><span data-stu-id="1eddc-209">Prevented email attempts: View blocked or junked threat emails</span></span>

<span data-ttu-id="1eddc-210">Microsoft Defender voor Office 365 blokkeert meestal e-mailberichten met bekende bedreigingsindicatoren, waaronder schadelijke koppelingen of bijlagen.</span><span class="sxs-lookup"><span data-stu-id="1eddc-210">Microsoft Defender for Office 365 typically blocks emails with known threat indicators, including malicious links or attachments.</span></span> <span data-ttu-id="1eddc-211">In sommige gevallen worden met proactieve filtermechanismen die controleren op verdachte inhoud, in plaats daarvan e-mailberichten met bedreigingen naar de map ongewenste e-mail verzonden.</span><span class="sxs-lookup"><span data-stu-id="1eddc-211">In some cases, proactive filtering mechanisms that check for suspicious content will instead send threat emails to the junk mail folder.</span></span> <span data-ttu-id="1eddc-212">In beide gevallen is de kans op het starten van malwarecode voor bedreigingen op het apparaat kleiner.</span><span class="sxs-lookup"><span data-stu-id="1eddc-212">In either case, the chances of the threat launching malware code on the device is reduced.</span></span>

<span data-ttu-id="1eddc-213">Op **het tabblad E-mailpogingen** voorkomen worden alle e-mailberichten weergegeven die vóór de bezorging zijn geblokkeerd of die door Microsoft Defender zijn verzonden naar de map ongewenste e-mail voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="1eddc-213">The **Prevented email attempts** tab lists all the emails that have either been blocked before delivery or sent to the junk mail folder by Microsoft Defender for Office 365.</span></span> 

![Afbeelding van de sectie verhinderde e-mailpogingen van een rapport voor bedreigingsanalyse](../../media/threat-analytics/ta_prevented_email_attempts_mtp.png)

<span data-ttu-id="1eddc-215">_Sectie E-mailpogingen voorkomen in een rapport voor bedreigingsanalyse_</span><span class="sxs-lookup"><span data-stu-id="1eddc-215">_Prevented email attempts section of a threat analytics report_</span></span>

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="1eddc-216">Risicobeperking: Lijst met risico's en de status van uw apparaten controleren</span><span class="sxs-lookup"><span data-stu-id="1eddc-216">Mitigations: Review list of mitigations and the status of your devices</span></span>

<span data-ttu-id="1eddc-217">Bekijk in **de sectie Mitigaties** de lijst met specifieke actie-aanbevelingen die u kunnen helpen uw organisatieweerbaarheid tegen de bedreiging te vergroten.</span><span class="sxs-lookup"><span data-stu-id="1eddc-217">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="1eddc-218">De lijst met bijgespoorde risico's bevat:</span><span class="sxs-lookup"><span data-stu-id="1eddc-218">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="1eddc-219">**Beveiligingsupdates**: implementatie van ondersteunde softwarebeveiligingsupdates voor beveiligingsproblemen die zijn gevonden op onboarded-apparaten</span><span class="sxs-lookup"><span data-stu-id="1eddc-219">**Security updates**—deployment of supported software security updates for vulnerabilities found on onboarded devices</span></span>
- <span data-ttu-id="1eddc-220">**Ondersteunde beveiligingsconfiguraties**</span><span class="sxs-lookup"><span data-stu-id="1eddc-220">**Supported security configurations**</span></span>
  - <span data-ttu-id="1eddc-221">Cloudbeveiliging</span><span class="sxs-lookup"><span data-stu-id="1eddc-221">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="1eddc-222">Potentieel ongewenste toepassingsbeveiliging (PUA)</span><span class="sxs-lookup"><span data-stu-id="1eddc-222">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="1eddc-223">Realtime beveiliging</span><span class="sxs-lookup"><span data-stu-id="1eddc-223">Real-time protection</span></span>

<span data-ttu-id="1eddc-224">Mitigatiegegevens in deze sectie bevatten gegevens uit [Threat and Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt), die ook gedetailleerde inzoomgegevens bevatten van verschillende koppelingen in het rapport.</span><span class="sxs-lookup"><span data-stu-id="1eddc-224">Mitigation information in this section incorporates data from [threat and vulnerability management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt), which also provides detailed drill-down information from various links in the report.</span></span>

![Afbeelding van de sectie risicobeperking van een bedreigingsanalyserapport met veilige configuratiedetails](../../media/threat-analytics/ta_mitigations_mtp.png)

![Afbeelding van de sectie risicobeperking van een rapport over bedreigingsanalyse met details over kwetsbaarheid](../../media/threat-analytics/ta_mitigations_mtp2.png)

<span data-ttu-id="1eddc-227">_Sectie Risicobeperking van een rapport voor bedreigingsanalyse_</span><span class="sxs-lookup"><span data-stu-id="1eddc-227">_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="1eddc-228">Aanvullende rapportdetails en -beperkingen</span><span class="sxs-lookup"><span data-stu-id="1eddc-228">Additional report details and limitations</span></span>

> [!NOTE]
> <span data-ttu-id="1eddc-229">Als onderdeel van de geïntegreerde beveiligingservaring is bedreigingsanalyse nu niet alleen beschikbaar voor Microsoft Defender voor Eindpunt, maar ook voor Microsoft Defender voor Office E5-licentiehouders.</span><span class="sxs-lookup"><span data-stu-id="1eddc-229">As part of the unified security experience, threat analytics is now available not just for Microsoft Defender for Endpoint, but also for Microsoft Defender for Office E5 license holders.</span></span>
>
> <span data-ttu-id="1eddc-230">Als u de Microsoft 365-beveiligingsportal (Microsoft 365 Defender) niet gebruikt, kunt u ook de rapportdetails (zonder de Microsoft Defender voor Office-gegevens) zien in de Microsoft Defender-beveiligingscentrum-portal (Microsoft Defender voor Eindpunt).</span><span class="sxs-lookup"><span data-stu-id="1eddc-230">If you are not using the Microsoft 365 security portal (Microsoft 365 Defender), you can also see the report details (without the Microsoft Defender for Office data) in the Microsoft Defender Security Center portal (Microsoft Defender for Endpoint).</span></span>

<span data-ttu-id="1eddc-231">Voor toegang tot het rapport Bedreigingsanalyse hebt u bepaalde rollen en machtigingen nodig.</span><span class="sxs-lookup"><span data-stu-id="1eddc-231">To access threat analytics report you need certain roles and permissions.</span></span> <span data-ttu-id="1eddc-232">Zie [Aangepaste rollen in op rollen gebaseerd toegangsbeheer voor Microsoft 365 Defender](custom-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1eddc-232">See [Custom roles in role-based access control for Microsoft 365 Defender](custom-roles.md) for details.</span></span>

- <span data-ttu-id="1eddc-233">Als u waarschuwingen, incidenten of beïnvloede activagegevens wilt weergeven, moet u machtigingen hebben voor Microsoft Defender voor Office of Microsoft Defender voor eindpuntwaarschuwingen, of beide.</span><span class="sxs-lookup"><span data-stu-id="1eddc-233">To view alerts, incidents, or impacted assets data, you need to have permissions to Microsoft Defender for Office or Microsoft Defender for Endpoint alerts data, or both.</span></span>
- <span data-ttu-id="1eddc-234">Als u verhinderde e-mailpogingen wilt weergeven, moet u over machtigingen voor Microsoft Defender Office gegevens.</span><span class="sxs-lookup"><span data-stu-id="1eddc-234">To view prevented email attempts, you need to have permissions to Microsoft Defender for Office hunting data.</span></span> 
- <span data-ttu-id="1eddc-235">Als u beperking wilt weergeven, moet u over machtigingen voor het Threat and Vulnerability Management gegevens in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="1eddc-235">To view mitigations, you need to have permissions to threat and vulnerability management data in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="1eddc-236">Houd rekening met de volgende factoren bij het bekijken van de bedreigingsanalysegegevens:</span><span class="sxs-lookup"><span data-stu-id="1eddc-236">When looking at the threat analytics data, remember the following factors:</span></span>

- <span data-ttu-id="1eddc-237">Grafieken geven alleen risico's weer die worden bijgespoord.</span><span class="sxs-lookup"><span data-stu-id="1eddc-237">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="1eddc-238">Controleer het rapportoverzicht op aanvullende risico's die niet in de grafieken worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="1eddc-238">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="1eddc-239">Risicobeperking garandeert geen volledige tolerantie.</span><span class="sxs-lookup"><span data-stu-id="1eddc-239">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="1eddc-240">De geleverde risico's weerspiegelen de best mogelijke acties die nodig zijn om de tolerantie te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="1eddc-240">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="1eddc-241">Apparaten worden geteld als 'niet beschikbaar' als ze geen gegevens naar de service hebben verzonden.</span><span class="sxs-lookup"><span data-stu-id="1eddc-241">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="1eddc-242">Antivirusgerelateerde statistieken zijn gebaseerd op Microsoft Defender Antivirus instellingen.</span><span class="sxs-lookup"><span data-stu-id="1eddc-242">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="1eddc-243">Apparaten met antivirusoplossingen van derden kunnen worden weergegeven als 'blootgesteld'.</span><span class="sxs-lookup"><span data-stu-id="1eddc-243">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="1eddc-244">Gerelateerde onderwerpen</span><span class="sxs-lookup"><span data-stu-id="1eddc-244">Related topics</span></span>

- [<span data-ttu-id="1eddc-245">Proactief bedreigingen zoeken met geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="1eddc-245">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="1eddc-246">De sectie Analistrapport begrijpen</span><span class="sxs-lookup"><span data-stu-id="1eddc-246">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="1eddc-247">Beveiligingszwakheden en blootstellingen beoordelen en oplossen</span><span class="sxs-lookup"><span data-stu-id="1eddc-247">Assess and resolve security weaknesses and exposures</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
