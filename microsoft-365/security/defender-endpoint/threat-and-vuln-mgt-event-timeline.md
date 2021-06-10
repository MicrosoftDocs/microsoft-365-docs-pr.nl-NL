---
title: Tijdlijn van gebeurtenis in Threat and Vulnerability Management
description: Gebeurtenistijdlijn is een nieuwsfeed voor risico's waarmee u kunt interpreteren hoe risico's in de organisatie worden ingevoerd en welke risico's zijn beperkt.
keywords: gebeurtenistijdlijn, Microsoft Defender voor eindpuntgebeurtenistijdlijn, Microsoft Defender voor endpoint tvm-gebeurtenistijdlijn, Threat and Vulnerability Management, Microsoft Defender voor Eindpunt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 64362598ff4b0512eb110917071e6d32abb8ede9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933479"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a><span data-ttu-id="75756-104">Tijdlijn van gebeurtenis - Threat and Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="75756-104">Event timeline - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="75756-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="75756-105">**Applies to:**</span></span>
- [<span data-ttu-id="75756-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="75756-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="75756-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75756-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="75756-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="75756-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="75756-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="75756-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="75756-110">Gebeurtenistijdlijn is een nieuwsfeed voor risico's waarmee u kunt interpreteren hoe risico's in de organisatie worden geïntroduceerd via nieuwe beveiligingslekken of exploits.</span><span class="sxs-lookup"><span data-stu-id="75756-110">Event timeline is a risk news feed that helps you interpret how risk is introduced into the organization through new vulnerabilities or exploits.</span></span> <span data-ttu-id="75756-111">U kunt gebeurtenissen bekijken die van invloed kunnen zijn op het risico van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="75756-111">You can view events that may impact your organization's risk.</span></span> <span data-ttu-id="75756-112">U kunt bijvoorbeeld nieuwe beveiligingslekken vinden die zijn geïntroduceerd, beveiligingslekken die kunnen worden benut, misbruik maken dat is toegevoegd aan een exploitkit en meer.</span><span class="sxs-lookup"><span data-stu-id="75756-112">For example, you can find new vulnerabilities that were introduced, vulnerabilities that became exploitable, exploit that was added to an exploit kit, and more.</span></span>

<span data-ttu-id="75756-113">Gebeurtenistijdlijn vertelt ook het verhaal van uw [blootstellingsscore](tvm-exposure-score.md) en [Microsoft Secure Score voor](tvm-microsoft-secure-score-devices.md) apparaten, zodat u de oorzaak van grote wijzigingen kunt bepalen.</span><span class="sxs-lookup"><span data-stu-id="75756-113">Event timeline also tells the story of your [exposure score](tvm-exposure-score.md) and [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md) so you can determine the cause of large changes.</span></span> <span data-ttu-id="75756-114">Gebeurtenissen kunnen van invloed zijn op uw apparaten of op uw score voor apparaten.</span><span class="sxs-lookup"><span data-stu-id="75756-114">Events can impact your devices or your score for devices.</span></span> <span data-ttu-id="75756-115">Verminder de blootstelling door aan te pakken wat er moet worden gesaneerd op basis van de aanbevolen [beveiligingsaanbevelingen.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="75756-115">Reduce you exposure by addressing what needs to be remediated based on the prioritized [security recommendations](tvm-security-recommendation.md).</span></span>

>[!TIP]
><span data-ttu-id="75756-116">Zie E-mailmeldingen voor kwetsbaarheid configureren in Microsoft Defender voor Eindpunt voor e-mailberichten over [nieuwe beveiligingsprobleemgebeurtenissen](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="75756-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-event-timeline-page"></a><span data-ttu-id="75756-117">Naar de tijdlijnpagina van gebeurtenis navigeren</span><span class="sxs-lookup"><span data-stu-id="75756-117">Navigate to the Event timeline page</span></span>

<span data-ttu-id="75756-118">Er zijn ook drie invoerpunten uit het [Threat and Vulnerability Management dashboard:](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="75756-118">There are also three entry points from the [threat and vulnerability management dashboard](tvm-dashboard-insights.md):</span></span>

- <span data-ttu-id="75756-119">**Score voor organisatieblootstelling:** Plaats de muisaanwijzer op de gebeurtenispunten in de grafiek 'Blootstellingsscore in de tijd' en selecteer 'Alle gebeurtenissen van deze dag bekijken'.</span><span class="sxs-lookup"><span data-stu-id="75756-119">**Organization exposure score card**: Hover over the event dots in the "Exposure Score over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="75756-120">De gebeurtenissen vertegenwoordigen softwareproblemen.</span><span class="sxs-lookup"><span data-stu-id="75756-120">The events represent software vulnerabilities.</span></span>
- <span data-ttu-id="75756-121">**Microsoft Secure Score for Devices:** Plaats de muisaanwijzer op de gebeurtenispunten in de grafiek 'Uw score voor apparaten in de tijd' en selecteer 'Alle gebeurtenissen vanaf deze dag bekijken'.</span><span class="sxs-lookup"><span data-stu-id="75756-121">**Microsoft Secure Score for Devices**: Hover over the event dots in the "Your score for devices over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="75756-122">De gebeurtenissen vertegenwoordigen nieuwe configuratiebeoordelingen.</span><span class="sxs-lookup"><span data-stu-id="75756-122">The events represent new configuration assessments.</span></span>
- <span data-ttu-id="75756-123">**Topgebeurtenissenkaart:** Selecteer 'Meer laten zien' onder aan de bovenste gebeurtenissentabel.</span><span class="sxs-lookup"><span data-stu-id="75756-123">**Top events card**: Select "Show more" at the bottom of the top events table.</span></span> <span data-ttu-id="75756-124">Op de kaart worden de drie meest impactvolle gebeurtenissen in de afgelopen 7 dagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="75756-124">The card displays the three most impactful events in the last 7 days.</span></span> <span data-ttu-id="75756-125">Impactvolle gebeurtenissen kunnen zijn als de gebeurtenis van invloed is op een groot aantal apparaten of als het een kritieke kwetsbaarheid is.</span><span class="sxs-lookup"><span data-stu-id="75756-125">Impactful events can include if the event affects a large number of devices, or if it is a critical vulnerability.</span></span>

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a><span data-ttu-id="75756-126">Blootstellingsscore en Microsoft Secure Score voor apparatengrafieken</span><span class="sxs-lookup"><span data-stu-id="75756-126">Exposure score and Microsoft Secure Score for Devices graphs</span></span>

<span data-ttu-id="75756-127">Plaats in Threat and Vulnerability Management het dashboard de muisaanwijzer op de grafiek Blootstellingsscore om de belangrijkste beveiligingsleedgebeurtenissen van die dag te bekijken die van invloed waren op uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="75756-127">In the threat and vulnerability management dashboard, hover over the Exposure score graph to view top software vulnerability events from that day that impacted your devices.</span></span> <span data-ttu-id="75756-128">Plaats de muisaanwijzer op de grafiek Microsoft Secure Score voor apparaten om nieuwe beveiligingsconfiguratiebeoordelingen weer te geven die van invloed zijn op uw score.</span><span class="sxs-lookup"><span data-stu-id="75756-128">Hover over the Microsoft Secure Score for Devices graph to view new security configuration assessments that affect your score.</span></span>

<span data-ttu-id="75756-129">Als er geen gebeurtenissen zijn die van invloed zijn op uw apparaten of uw score voor apparaten, worden er geen gebeurtenissen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="75756-129">If there are no events that affect your devices or your score for devices, then none will be shown.</span></span>

<span data-ttu-id="75756-130">![Blootstellingsscore hover ](images/tvm-event-timeline-exposure-score350.png) 
 ![ Microsoft Secure Score for Devices hover](images/tvm-event-timeline-device-hover360.png)</span><span class="sxs-lookup"><span data-stu-id="75756-130">![Exposure score hover](images/tvm-event-timeline-exposure-score350.png) 
![Microsoft Secure Score for Devices hover](images/tvm-event-timeline-device-hover360.png)</span></span>

### <a name="drill-down-to-events-from-that-day"></a><span data-ttu-id="75756-131">Inzoomen op gebeurtenissen van die dag</span><span class="sxs-lookup"><span data-stu-id="75756-131">Drill down to events from that day</span></span>

<span data-ttu-id="75756-132">Als **u Alle gebeurtenissen vanaf deze dag tonen selecteert,** gaat u naar de pagina Gebeurtenistijdlijn met een aangepast datumbereik voor die dag.</span><span class="sxs-lookup"><span data-stu-id="75756-132">Selecting **Show all events from this day** takes you to the Event timeline page with a custom date range for that day.</span></span>

![Tijdlijn van gebeurtenis geselecteerd aangepast datumbereik](images/tvm-event-timeline-drilldown.png)

<span data-ttu-id="75756-134">Selecteer **Aangepast bereik** om het datumbereik te wijzigen in een ander aangepast bereik of een vooraf ingesteld tijdsbereik.</span><span class="sxs-lookup"><span data-stu-id="75756-134">Select **Custom range** to change the date range to another custom one, or a pre-set time range.</span></span>

![Opties voor datumbereik van gebeurtenistijdlijn](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a><span data-ttu-id="75756-136">Overzicht van gebeurtenistijdlijn</span><span class="sxs-lookup"><span data-stu-id="75756-136">Event timeline overview</span></span>

<span data-ttu-id="75756-137">Op de pagina Gebeurtenistijdlijn kunt u alle benodigde informatie over een gebeurtenis bekijken.</span><span class="sxs-lookup"><span data-stu-id="75756-137">On the Event timeline page, you can view the all the necessary info related to an event.</span></span> 

<span data-ttu-id="75756-138">Functies:</span><span class="sxs-lookup"><span data-stu-id="75756-138">Features:</span></span>

- <span data-ttu-id="75756-139">Kolommen aanpassen</span><span class="sxs-lookup"><span data-stu-id="75756-139">Customize columns</span></span>
- <span data-ttu-id="75756-140">Filteren op gebeurtenistype of percentage van beïnvloede apparaten</span><span class="sxs-lookup"><span data-stu-id="75756-140">Filter by event type or percent of impacted devices</span></span>
- <span data-ttu-id="75756-141">30, 50 of 100 items per pagina weergeven</span><span class="sxs-lookup"><span data-stu-id="75756-141">View 30, 50, or 100 items per page</span></span>

<span data-ttu-id="75756-142">De twee grote getallen boven aan de pagina geven het aantal nieuwe beveiligingslekken en exploiteerbare beveiligingslekken weer, niet gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="75756-142">The two large numbers at the top of the page show the number of new vulnerabilities and exploitable vulnerabilities, not events.</span></span> <span data-ttu-id="75756-143">Sommige gebeurtenissen kunnen meerdere beveiligingslekken hebben en sommige beveiligingslekken kunnen meerdere gebeurtenissen hebben.</span><span class="sxs-lookup"><span data-stu-id="75756-143">Some events can have multiple vulnerabilities, and some vulnerabilities can have multiple events.</span></span>

![Pagina Gebeurtenistijdlijn](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a><span data-ttu-id="75756-145">Kolommen</span><span class="sxs-lookup"><span data-stu-id="75756-145">Columns</span></span>

- <span data-ttu-id="75756-146">**Datum:** maand, dag, jaar</span><span class="sxs-lookup"><span data-stu-id="75756-146">**Date**: month, day, year</span></span>
- <span data-ttu-id="75756-147">**Gebeurtenis**: impactvolle gebeurtenis, inclusief onderdeel, type en aantal beïnvloede apparaten</span><span class="sxs-lookup"><span data-stu-id="75756-147">**Event**: impactful event, including component, type, and number of impacted devices</span></span>
- <span data-ttu-id="75756-148">**Gerelateerd onderdeel**: software</span><span class="sxs-lookup"><span data-stu-id="75756-148">**Related component**: software</span></span>
- <span data-ttu-id="75756-149">**Oorspronkelijk beïnvloedde apparaten:** het aantal en het percentage van de apparaten waarop deze gebeurtenis oorspronkelijk plaatsvond.</span><span class="sxs-lookup"><span data-stu-id="75756-149">**Originally impacted devices**: the number, and percentage, of impacted devices when this event originally occurred.</span></span> <span data-ttu-id="75756-150">U kunt ook filteren op het percentage van de oorspronkelijk beïnvloede apparaten, op het totale aantal apparaten.</span><span class="sxs-lookup"><span data-stu-id="75756-150">You can also filter by the percent of originally impacted devices, out of your total number of devices.</span></span>
- <span data-ttu-id="75756-151">**Momenteel beïnvloedt apparaten:** het huidige aantal en het huidige percentage, van apparaten die deze gebeurtenis momenteel van invloed is.</span><span class="sxs-lookup"><span data-stu-id="75756-151">**Currently impacted devices**: the current number, and percentage, of devices that this event currently impacts.</span></span> <span data-ttu-id="75756-152">U kunt dit veld vinden door Kolommen **aanpassen te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="75756-152">You can find this field by selecting **Customize columns**.</span></span>
- <span data-ttu-id="75756-153">**Typen:** weerspiegelen gebeurtenissen met een tijdstempel die van invloed zijn op de score.</span><span class="sxs-lookup"><span data-stu-id="75756-153">**Types**: reflect time-stamped events that impact the score.</span></span> <span data-ttu-id="75756-154">Ze kunnen worden gefilterd.</span><span class="sxs-lookup"><span data-stu-id="75756-154">They can be filtered.</span></span>
    - <span data-ttu-id="75756-155">Exploit toegevoegd aan een exploitkit</span><span class="sxs-lookup"><span data-stu-id="75756-155">Exploit added to an exploit kit</span></span>
    - <span data-ttu-id="75756-156">Exploit is geverifieerd</span><span class="sxs-lookup"><span data-stu-id="75756-156">Exploit was verified</span></span>
    - <span data-ttu-id="75756-157">Nieuwe openbare exploit</span><span class="sxs-lookup"><span data-stu-id="75756-157">New public exploit</span></span>
    - <span data-ttu-id="75756-158">Nieuw beveiligingsprobleem</span><span class="sxs-lookup"><span data-stu-id="75756-158">New vulnerability</span></span>
    - <span data-ttu-id="75756-159">Nieuwe configuratiebeoordeling</span><span class="sxs-lookup"><span data-stu-id="75756-159">New configuration assessment</span></span>
- <span data-ttu-id="75756-160">**Scoretrend**: trend blootstellingsscore</span><span class="sxs-lookup"><span data-stu-id="75756-160">**Score trend**: exposure score trend</span></span>

### <a name="icons"></a><span data-ttu-id="75756-161">Pictogrammen</span><span class="sxs-lookup"><span data-stu-id="75756-161">Icons</span></span>

<span data-ttu-id="75756-162">De volgende pictogrammen worden weergegeven naast gebeurtenissen:</span><span class="sxs-lookup"><span data-stu-id="75756-162">The following icons show up next to events:</span></span>

- ![pictogram bug](images/tvm-black-bug-icon.png) <span data-ttu-id="75756-164">Nieuwe openbare exploit</span><span class="sxs-lookup"><span data-stu-id="75756-164">New public exploit</span></span>
- ![rapportwaarschuwingspictogram](images/report-warning-icon.png) <span data-ttu-id="75756-166">Nieuw beveiligingsprobleem is gepubliceerd</span><span class="sxs-lookup"><span data-stu-id="75756-166">New vulnerability was published</span></span>
- ![exploit kit](images/bug-lightning-icon2.png) <span data-ttu-id="75756-168">Exploit gevonden in exploit kit</span><span class="sxs-lookup"><span data-stu-id="75756-168">Exploit found in exploit kit</span></span>
- ![pictogram met waarschuwingspictogram](images/bug-caution-icon2.png) <span data-ttu-id="75756-170">Geverifieerde exploit</span><span class="sxs-lookup"><span data-stu-id="75756-170">Exploit verified</span></span>

### <a name="drill-down-to-a-specific-event"></a><span data-ttu-id="75756-171">Inzoomen op een specifieke gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="75756-171">Drill down to a specific event</span></span>

<span data-ttu-id="75756-172">Wanneer u een gebeurtenis selecteert, wordt er een flyout weergegeven met een lijst met de details en huidige CVE's die van invloed zijn op uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="75756-172">Once you select an event, a flyout will appear with a list of the details and current CVEs that affect your devices.</span></span> <span data-ttu-id="75756-173">U kunt meer CVE's weergeven of de gerelateerde aanbeveling bekijken.</span><span class="sxs-lookup"><span data-stu-id="75756-173">You can show more CVEs or view the related recommendation.</span></span>

<span data-ttu-id="75756-174">Met de pijl onder 'scoretrend' kunt u bepalen of deze gebeurtenis de blootstellingsscore van uw organisatie mogelijk heeft verhoogd of verlaagd.</span><span class="sxs-lookup"><span data-stu-id="75756-174">The arrow below "score trend" helps you determine whether this event potentially raised or lowered your organizational exposure score.</span></span> <span data-ttu-id="75756-175">Een hogere blootstellingsscore betekent dat apparaten kwetsbaarder zijn voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="75756-175">Higher exposure score means devices are more vulnerable to exploitation.</span></span>

![Flyout gebeurtenistijdlijn](images/tvm-event-timeline-flyout500.png)

<span data-ttu-id="75756-177">Selecteer van hier naar **gerelateerde beveiligingsaanbeveling** de aanbeveling weergeven die het nieuwe beveiligingsprobleem op de pagina met [beveiligingsaanbevelingen adresseert.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="75756-177">From there, select **Go to related security recommendation** view the recommendation that addresses the new software vulnerability in the [security recommendations page](tvm-security-recommendation.md).</span></span> <span data-ttu-id="75756-178">Nadat u de beschrijvings- en kwetsbaarheidsdetails in de beveiligingsaanbeveling hebt gelezen, kunt u een herstelaanvraag indienen en de aanvraag bijhouden op de [herstelpagina.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="75756-178">After reading the description and vulnerability details in the security recommendation, you can submit a remediation request, and track the request in the [remediation page](tvm-remediation.md).</span></span>  

## <a name="view-event-timelines-in-software-pages"></a><span data-ttu-id="75756-179">Tijdlijnen voor gebeurtenissen weergeven op softwarepagina's</span><span class="sxs-lookup"><span data-stu-id="75756-179">View Event timelines in software pages</span></span>

<span data-ttu-id="75756-180">Als u een softwarepagina wilt openen, selecteert u een gebeurtenis > selecteert u de naam van de hyperlinksoftware (zoals Visual Studio 2017) in de sectie 'Gerelateerd onderdeel' in de flyout.</span><span class="sxs-lookup"><span data-stu-id="75756-180">To open a software page, select an event > select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout.</span></span> [<span data-ttu-id="75756-181">Meer informatie over softwarepagina's</span><span class="sxs-lookup"><span data-stu-id="75756-181">Learn more about software pages</span></span>](tvm-software-inventory.md#software-pages)

<span data-ttu-id="75756-182">Er wordt een volledige pagina weergegeven met alle details van een specifieke software.</span><span class="sxs-lookup"><span data-stu-id="75756-182">A full page will appear with all the details of a specific software.</span></span> <span data-ttu-id="75756-183">Muis over de grafiek om de tijdlijn van gebeurtenissen voor die specifieke software te zien.</span><span class="sxs-lookup"><span data-stu-id="75756-183">Mouse over the graph to see the timeline of events for that specific software.</span></span>

![Softwarepagina met een tijdlijngrafiek voor gebeurtenissen](images/tvm-event-timeline-software2.png)

<span data-ttu-id="75756-185">Navigeer naar het tabblad tijdlijn van de gebeurtenis om alle gebeurtenissen weer te geven die met die software te maken hebben.</span><span class="sxs-lookup"><span data-stu-id="75756-185">Navigate to the event timeline tab to view all the events related to that software.</span></span> <span data-ttu-id="75756-186">U kunt ook beveiligingsaanbevelingen, gevonden beveiligingsproblemen, geïnstalleerde apparaten en versiedistributie zien.</span><span class="sxs-lookup"><span data-stu-id="75756-186">You can also see security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span>

![Softwarepagina met een tabblad Tijdlijn van gebeurtenis](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a><span data-ttu-id="75756-188">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="75756-188">Related topics</span></span>

- [<span data-ttu-id="75756-189">Overzicht van bedreigingen en vulnerability management</span><span class="sxs-lookup"><span data-stu-id="75756-189">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="75756-190">Dashboard</span><span class="sxs-lookup"><span data-stu-id="75756-190">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="75756-191">Blootstellingsscore</span><span class="sxs-lookup"><span data-stu-id="75756-191">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="75756-192">Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="75756-192">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="75756-193">Beveiligingsproblemen verhelpen</span><span class="sxs-lookup"><span data-stu-id="75756-193">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="75756-194">Software-inventaris</span><span class="sxs-lookup"><span data-stu-id="75756-194">Software inventory</span></span>](tvm-software-inventory.md)

