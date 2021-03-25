---
title: Apparaten onderzoeken in de lijst Defender voor Endpoint Defender ATP-apparaten
description: Onderzoek getroffen apparaten door waarschuwingen, netwerkverbindingsgegevens, apparaatlabels en groepen toe te voegen en de servicetoestand te controleren.
keywords: apparaten, tags, groepen, eindpunt, waarschuwingenwachtrij, waarschuwingen, apparaatnaam, domein, laatst gezien, intern IP, actieve waarschuwingen, bedreigingscategorie, filter, sorteren, waarschuwingen controleren, netwerk, verbinding, type, wachtwoord stealer, ransomware, exploit, bedreiging, lage ernst, service health
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8f5415b6337d21b780a75a192a565078a6cacc06
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185729"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="67dd2-104">Apparaten onderzoeken in de lijst Microsoft Defender voor eindpuntapparaten</span><span class="sxs-lookup"><span data-stu-id="67dd2-104">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="67dd2-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="67dd2-105">**Applies to:**</span></span>
- [<span data-ttu-id="67dd2-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="67dd2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="67dd2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67dd2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="67dd2-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="67dd2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="67dd2-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="67dd2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="67dd2-110">Onderzoek de details van een waarschuwing die op een specifiek apparaat wordt opgehaald om andere gedragingen of gebeurtenissen te identificeren die mogelijk verband houden met de waarschuwing of het mogelijke bereik van de inbreuk.</span><span class="sxs-lookup"><span data-stu-id="67dd2-110">Investigate the details of an alert raised on a specific device to identify other behaviors or events that might be related to the alert or the potential scope of the breach.</span></span>

> [!NOTE]
> <span data-ttu-id="67dd2-111">Als onderdeel van het onderzoek- of antwoordproces kunt u een onderzoekspakket verzamelen vanaf een apparaat.</span><span class="sxs-lookup"><span data-stu-id="67dd2-111">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="67dd2-112">Dit doet u als: [Onderzoekspakket van apparaten verzamelen.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices)</span><span class="sxs-lookup"><span data-stu-id="67dd2-112">Here's how: [Collect investigation package from devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="67dd2-113">U kunt op getroffen apparaten klikken wanneer u ze in de portal ziet om een gedetailleerd rapport over dat apparaat te openen.</span><span class="sxs-lookup"><span data-stu-id="67dd2-113">You can click on affected devices whenever you see them in the portal to open a detailed report about that device.</span></span> <span data-ttu-id="67dd2-114">Getroffen apparaten worden in de volgende gebieden geïdentificeerd:</span><span class="sxs-lookup"><span data-stu-id="67dd2-114">Affected devices are identified in the following areas:</span></span>

- [<span data-ttu-id="67dd2-115">Lijst apparaten</span><span class="sxs-lookup"><span data-stu-id="67dd2-115">Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="67dd2-116">Waarschuwingenwachtrij</span><span class="sxs-lookup"><span data-stu-id="67dd2-116">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="67dd2-117">Dashboard Beveiligingsbewerkingen</span><span class="sxs-lookup"><span data-stu-id="67dd2-117">Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="67dd2-118">Elke afzonderlijke waarschuwing</span><span class="sxs-lookup"><span data-stu-id="67dd2-118">Any individual alert</span></span>
- <span data-ttu-id="67dd2-119">Weergave van afzonderlijke bestandsdetails</span><span class="sxs-lookup"><span data-stu-id="67dd2-119">Any individual file details view</span></span>
- <span data-ttu-id="67dd2-120">Een ip-adres- of domeindetailweergave</span><span class="sxs-lookup"><span data-stu-id="67dd2-120">Any IP address or domain details view</span></span>

<span data-ttu-id="67dd2-121">Wanneer u een specifiek apparaat onderzoekt, ziet u:</span><span class="sxs-lookup"><span data-stu-id="67dd2-121">When you investigate a specific device, you'll see:</span></span>

- <span data-ttu-id="67dd2-122">Apparaatdetails</span><span class="sxs-lookup"><span data-stu-id="67dd2-122">Device details</span></span>
- <span data-ttu-id="67dd2-123">Reactieacties</span><span class="sxs-lookup"><span data-stu-id="67dd2-123">Response actions</span></span>
- <span data-ttu-id="67dd2-124">Tabbladen (overzicht, waarschuwingen, tijdlijn, beveiligingsaanbevelingen, softwarevoorraad, gevonden beveiligingslekken, ontbrekende KBs)</span><span class="sxs-lookup"><span data-stu-id="67dd2-124">Tabs (overview, alerts, timeline, security recommendations, software inventory, discovered vulnerabilities, missing KBs)</span></span>
- <span data-ttu-id="67dd2-125">Kaarten (actieve waarschuwingen, aangemelde gebruikers, beveiligingsbeoordeling)</span><span class="sxs-lookup"><span data-stu-id="67dd2-125">Cards (active alerts, logged on users, security assessment)</span></span>

![Afbeelding van de apparaatweergave](images/specific-device.png)

## <a name="device-details"></a><span data-ttu-id="67dd2-127">Apparaatdetails</span><span class="sxs-lookup"><span data-stu-id="67dd2-127">Device details</span></span>

<span data-ttu-id="67dd2-128">De sectie apparaatdetails bevat informatie, zoals het domein, het besturingssysteem en de status van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="67dd2-128">The device details section provides information such as the domain, OS, and health state of the device.</span></span> <span data-ttu-id="67dd2-129">Als er een onderzoekspakket beschikbaar is op het apparaat, ziet u een koppeling waarmee u het pakket kunt downloaden.</span><span class="sxs-lookup"><span data-stu-id="67dd2-129">If there's an investigation package available on the device, you'll see a link that allows you to download the package.</span></span>

## <a name="response-actions"></a><span data-ttu-id="67dd2-130">Reactieacties</span><span class="sxs-lookup"><span data-stu-id="67dd2-130">Response actions</span></span>

<span data-ttu-id="67dd2-131">Antwoordacties worden uitgevoerd boven aan een specifieke apparaatpagina en bevatten:</span><span class="sxs-lookup"><span data-stu-id="67dd2-131">Response actions run along the top of a specific device page and include:</span></span>

- <span data-ttu-id="67dd2-132">Tags beheren</span><span class="sxs-lookup"><span data-stu-id="67dd2-132">Manage tags</span></span>
- <span data-ttu-id="67dd2-133">Apparaat isoleren</span><span class="sxs-lookup"><span data-stu-id="67dd2-133">Isolate device</span></span>
- <span data-ttu-id="67dd2-134">De uitvoering van apps beperken</span><span class="sxs-lookup"><span data-stu-id="67dd2-134">Restrict app execution</span></span>
- <span data-ttu-id="67dd2-135">Antivirusscan uitvoeren</span><span class="sxs-lookup"><span data-stu-id="67dd2-135">Run antivirus scan</span></span>
- <span data-ttu-id="67dd2-136">Onderzoekspakket verzamelen</span><span class="sxs-lookup"><span data-stu-id="67dd2-136">Collect investigation package</span></span>
- <span data-ttu-id="67dd2-137">Live-antwoordsessie starten</span><span class="sxs-lookup"><span data-stu-id="67dd2-137">Initiate Live Response Session</span></span>
- <span data-ttu-id="67dd2-138">Geautomatiseerd onderzoek starten</span><span class="sxs-lookup"><span data-stu-id="67dd2-138">Initiate automated investigation</span></span>
- <span data-ttu-id="67dd2-139">Een bedreigingsexpert raadplegen</span><span class="sxs-lookup"><span data-stu-id="67dd2-139">Consult a threat expert</span></span>
- <span data-ttu-id="67dd2-140">Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="67dd2-140">Action center</span></span>

<span data-ttu-id="67dd2-141">U kunt antwoordacties uitvoeren in het actiecentrum, op een specifieke apparaatpagina of op een specifieke bestandspagina.</span><span class="sxs-lookup"><span data-stu-id="67dd2-141">You can take response actions in the Action center, in a specific device page, or in a specific file page.</span></span>

<span data-ttu-id="67dd2-142">Zie Actie ondernemen op een apparaat voor meer informatie over het ondernemen van actie [op een apparaat.](respond-machine-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="67dd2-142">For more information on how to take action on a device, see [Take response action on a device](respond-machine-alerts.md).</span></span>

<span data-ttu-id="67dd2-143">Zie [Gebruikersentiteiten onderzoeken voor meer informatie.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="67dd2-143">For more information, see [Investigate user entities](investigate-user.md).</span></span>

## <a name="tabs"></a><span data-ttu-id="67dd2-144">Tabbladen</span><span class="sxs-lookup"><span data-stu-id="67dd2-144">Tabs</span></span>

<span data-ttu-id="67dd2-145">De tabbladen bevatten relevante beveiligings- en preventiegegevens met betrekking tot het apparaat.</span><span class="sxs-lookup"><span data-stu-id="67dd2-145">The tabs provide relevant security and threat prevention information related to the device.</span></span> <span data-ttu-id="67dd2-146">Op elk tabblad kunt u de kolommen aanpassen die worden weergegeven door Kolommen **aanpassen te selecteren** op de balk boven de kolomkoppen.</span><span class="sxs-lookup"><span data-stu-id="67dd2-146">In each tab, you can customize the columns that are shown by selecting **Customize columns** from the bar above the column headers.</span></span>

### <a name="overview"></a><span data-ttu-id="67dd2-147">Overzicht</span><span class="sxs-lookup"><span data-stu-id="67dd2-147">Overview</span></span>
<span data-ttu-id="67dd2-148">Op **het tabblad** Overzicht worden de kaarten [weergegeven](#cards) voor actieve waarschuwingen, aangemeld bij gebruikers en beveiligingsbeoordeling.</span><span class="sxs-lookup"><span data-stu-id="67dd2-148">The **Overview** tab displays the [cards](#cards) for active alerts, logged on users, and security assessment.</span></span>

![Afbeelding van het tabblad Overzicht op de apparaatpagina](images/overview-device.png)

### <a name="alerts"></a><span data-ttu-id="67dd2-150">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="67dd2-150">Alerts</span></span>

<span data-ttu-id="67dd2-151">Het **tabblad** Waarschuwingen bevat een lijst met waarschuwingen die zijn gekoppeld aan het apparaat.</span><span class="sxs-lookup"><span data-stu-id="67dd2-151">The **Alerts** tab provides a list of alerts that are associated with the device.</span></span> <span data-ttu-id="67dd2-152">Deze lijst is een gefilterde versie van de wachtrij Waarschuwingen en toont een korte beschrijving van de waarschuwing, ernst (hoog, gemiddeld, laag, informatief), status in de wachtrij (nieuw, in uitvoering, opgelost), classificatie (niet ingesteld, onwaar waarschuwing, waar waarschuwing), onderzoeksstatus, categorie van waarschuwing, wie de waarschuwing adresseert en laatste activiteit. [](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="67dd2-152">This list is a filtered version of the [Alerts queue](alerts-queue.md), and shows a short description of the alert, severity (high, medium, low, informational), status in the queue (new, in progress, resolved), classification (not set, false alert, true alert), investigation state, category of alert, who is addressing the alert, and last activity.</span></span> <span data-ttu-id="67dd2-153">U kunt de waarschuwingen ook filteren.</span><span class="sxs-lookup"><span data-stu-id="67dd2-153">You can also filter the alerts.</span></span>

![Afbeelding van waarschuwingen met betrekking tot het apparaat](images/alerts-device.png)

<span data-ttu-id="67dd2-155">Wanneer het cirkelpictogram links van een waarschuwing is geselecteerd, wordt er een fly-out weergegeven.</span><span class="sxs-lookup"><span data-stu-id="67dd2-155">When the circle icon to the left of an alert is selected, a fly-out appears.</span></span> <span data-ttu-id="67dd2-156">In dit deelvenster kunt u de waarschuwing beheren en meer details weergeven, zoals incidentnummer en gerelateerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="67dd2-156">From this panel you can manage the alert and view more details such as incident number and related devices.</span></span> <span data-ttu-id="67dd2-157">Er kunnen meerdere waarschuwingen tegelijk worden geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="67dd2-157">Multiple alerts can be selected at a time.</span></span>

<span data-ttu-id="67dd2-158">Als u een volledige paginaweergave van een waarschuwing wilt zien, inclusief incidentgrafiek en processtructuur, selecteert u de titel van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="67dd2-158">To see a full page view of an alert including incident graph and process tree, select the title of the alert.</span></span>

### <a name="timeline"></a><span data-ttu-id="67dd2-159">Tijdlijn</span><span class="sxs-lookup"><span data-stu-id="67dd2-159">Timeline</span></span>

<span data-ttu-id="67dd2-160">Het **tabblad** Tijdlijn bevat een chronologische weergave van de gebeurtenissen en bijbehorende waarschuwingen die zijn waargenomen op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="67dd2-160">The **Timeline** tab provides a chronological view of the events and associated alerts that have been observed on the device.</span></span> <span data-ttu-id="67dd2-161">Dit kan u helpen bij het correleren van gebeurtenissen, bestanden en IP-adressen ten opzichte van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="67dd2-161">This can help you correlate any events, files, and IP addresses in relation to the device.</span></span>

<span data-ttu-id="67dd2-162">Met de tijdlijn kunt u ook selectief inzoomen op gebeurtenissen die binnen een bepaalde periode hebben plaatsgevonden.</span><span class="sxs-lookup"><span data-stu-id="67dd2-162">The timeline also enables you to selectively drill down into events that occurred within a given time period.</span></span> <span data-ttu-id="67dd2-163">U kunt de temporele volgorde bekijken van gebeurtenissen die zich hebben voorgedaan op een apparaat gedurende een geselecteerde periode.</span><span class="sxs-lookup"><span data-stu-id="67dd2-163">You can view the temporal sequence of events that occurred on a device over a selected time period.</span></span> <span data-ttu-id="67dd2-164">Als u de weergave verder wilt bepalen, kunt u filteren op gebeurtenisgroepen of de kolommen aanpassen.</span><span class="sxs-lookup"><span data-stu-id="67dd2-164">To further control your view, you can filter by event groups or customize the columns.</span></span>

>[!NOTE]
> <span data-ttu-id="67dd2-165">Als u firewallgebeurtenissen wilt weergeven, moet u het controlebeleid inschakelen, zie [Verbinding auditfilterplatform](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span><span class="sxs-lookup"><span data-stu-id="67dd2-165">For firewall events to be displayed, you'll need to enable the audit policy, see [Audit Filtering Platform connection](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span></span>
><span data-ttu-id="67dd2-166">Firewall bestrijkt de volgende gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="67dd2-166">Firewall covers the following events</span></span>
>
>- <span data-ttu-id="67dd2-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - firewallservice gestopt</span><span class="sxs-lookup"><span data-stu-id="67dd2-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - firewall service stopped</span></span>
>- <span data-ttu-id="67dd2-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - toepassing die is geblokkeerd voor het accepteren van inkomende verbindingen in het netwerk</span><span class="sxs-lookup"><span data-stu-id="67dd2-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - application blocked from accepting incoming connections on the network</span></span>
>- <span data-ttu-id="67dd2-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - geblokkeerde verbinding</span><span class="sxs-lookup"><span data-stu-id="67dd2-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - blocked connection</span></span>

![Afbeelding van apparaattijdlijn met gebeurtenissen](images/timeline-device.png)

<span data-ttu-id="67dd2-171">Enkele functies omvatten:</span><span class="sxs-lookup"><span data-stu-id="67dd2-171">Some of the functionality includes:</span></span>

- <span data-ttu-id="67dd2-172">Zoeken naar specifieke gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="67dd2-172">Search for specific events</span></span>
  - <span data-ttu-id="67dd2-173">Gebruik de zoekbalk om te zoeken naar specifieke tijdlijngebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="67dd2-173">Use the search bar to look for specific timeline events.</span></span>
- <span data-ttu-id="67dd2-174">Gebeurtenissen filteren vanaf een bepaalde datum</span><span class="sxs-lookup"><span data-stu-id="67dd2-174">Filter events from a specific date</span></span>
  - <span data-ttu-id="67dd2-175">Selecteer het agendapictogram in de linkerbovenhoek van de tabel om gebeurtenissen weer te geven in de afgelopen dag, week, 30 dagen of aangepast bereik.</span><span class="sxs-lookup"><span data-stu-id="67dd2-175">Select the calendar icon in the upper left of the table to display events in the past day, week, 30 days, or custom range.</span></span> <span data-ttu-id="67dd2-176">De apparaattijdlijn is standaard ingesteld op het weergeven van de gebeurtenissen uit de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="67dd2-176">By default, the device timeline is set to display the events from the past 30 days.</span></span>
  - <span data-ttu-id="67dd2-177">Gebruik de tijdlijn om naar een bepaald moment in de tijd te gaan door de sectie te markeren.</span><span class="sxs-lookup"><span data-stu-id="67dd2-177">Use the timeline to jump to a specific moment in time by highlighting the section.</span></span> <span data-ttu-id="67dd2-178">De pijlen op de tijdlijn wijzen geautomatiseerde onderzoeken aan</span><span class="sxs-lookup"><span data-stu-id="67dd2-178">The arrows on the timeline pinpoint automated investigations</span></span>
- <span data-ttu-id="67dd2-179">Gedetailleerde apparaattijdlijngebeurtenissen exporteren</span><span class="sxs-lookup"><span data-stu-id="67dd2-179">Export detailed device timeline events</span></span>
  - <span data-ttu-id="67dd2-180">Exporteert de apparaattijdlijn voor de huidige datum of een opgegeven datumbereik tot zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="67dd2-180">Export the device timeline for the current date or a specified date range up to seven days.</span></span>

<span data-ttu-id="67dd2-181">Meer informatie over bepaalde gebeurtenissen vindt u in de **sectie Aanvullende** informatie.</span><span class="sxs-lookup"><span data-stu-id="67dd2-181">More details about certain events are provided in the **Additional information** section.</span></span> <span data-ttu-id="67dd2-182">Deze details variëren afhankelijk van het type gebeurtenis, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="67dd2-182">These details vary depending on the type of event, for example:</span></span> 

- <span data-ttu-id="67dd2-183">Ingesloten door Application Guard : de webbrowsergebeurtenis is beperkt door een geïsoleerde container</span><span class="sxs-lookup"><span data-stu-id="67dd2-183">Contained by Application Guard - the web browser event was restricted by an isolated container</span></span>
- <span data-ttu-id="67dd2-184">Actieve bedreiging gedetecteerd: de detectie van bedreigingen vond plaats terwijl de bedreiging werd uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="67dd2-184">Active threat detected - the threat detection occurred while the threat was running</span></span>
- <span data-ttu-id="67dd2-185">Herstel mislukt: een poging om de gedetecteerde bedreiging te herstellen is aangeroepen, maar is mislukt</span><span class="sxs-lookup"><span data-stu-id="67dd2-185">Remediation unsuccessful - an attempt to remediate the detected threat was invoked but failed</span></span>
- <span data-ttu-id="67dd2-186">Herstel is gelukt: de gedetecteerde bedreiging is gestopt en opgeruimd</span><span class="sxs-lookup"><span data-stu-id="67dd2-186">Remediation successful - the detected threat was stopped and cleaned</span></span>
- <span data-ttu-id="67dd2-187">Waarschuwing overgeslagen door gebruiker: de Waarschuwing voor SmartScreen van Windows Defender is door een gebruiker afgewezen en overgenomen</span><span class="sxs-lookup"><span data-stu-id="67dd2-187">Warning bypassed by user - the Windows Defender SmartScreen warning was dismissed and overridden by a user</span></span>
- <span data-ttu-id="67dd2-188">Verdacht script gedetecteerd : er is een mogelijk schadelijk script gevonden dat werd uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="67dd2-188">Suspicious script detected - a potentially malicious script was found running</span></span>
- <span data-ttu-id="67dd2-189">De waarschuwingscategorie: als de gebeurtenis heeft geleid tot het genereren van een waarschuwing, wordt de waarschuwingscategorie ("Zijbeweging", bijvoorbeeld) verstrekt</span><span class="sxs-lookup"><span data-stu-id="67dd2-189">The alert category - if the event led to the generation of an alert, the alert category  ("Lateral Movement", for example) is provided</span></span>

#### <a name="event-details"></a><span data-ttu-id="67dd2-190">Gebeurtenisdetails</span><span class="sxs-lookup"><span data-stu-id="67dd2-190">Event details</span></span>
<span data-ttu-id="67dd2-191">Selecteer een gebeurtenis om relevante details over die gebeurtenis weer te geven.</span><span class="sxs-lookup"><span data-stu-id="67dd2-191">Select an event to view relevant details about that event.</span></span> <span data-ttu-id="67dd2-192">Er wordt een deelvenster weergegeven om algemene gebeurtenisgegevens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="67dd2-192">A panel displays to show general event information.</span></span> <span data-ttu-id="67dd2-193">Wanneer dit van toepassing is en gegevens beschikbaar zijn, wordt ook een grafiek weergegeven met gerelateerde entiteiten en hun relaties.</span><span class="sxs-lookup"><span data-stu-id="67dd2-193">When applicable and data is available, a graph showing related entities and their relationships are also shown.</span></span>

<span data-ttu-id="67dd2-194">Als u de gebeurtenis en gerelateerde gebeurtenissen verder wilt controleren, kunt u snel een geavanceerde [query](advanced-hunting-overview.md) uitvoeren door Hunt te selecteren **voor gerelateerde gebeurtenissen.**</span><span class="sxs-lookup"><span data-stu-id="67dd2-194">To further inspect the event and related events, you can quickly run an [advanced hunting](advanced-hunting-overview.md) query by selecting **Hunt for related events**.</span></span> <span data-ttu-id="67dd2-195">De query retournoemt de geselecteerde gebeurtenis en de lijst met andere gebeurtenissen die rond dezelfde tijd op hetzelfde eindpunt hebben plaatsgevonden.</span><span class="sxs-lookup"><span data-stu-id="67dd2-195">The query will return the selected event and the list of other events that occurred around the same time on the same endpoint.</span></span>

![Afbeelding van het deelvenster details van de gebeurtenis](images/event-details.png)

### <a name="security-recommendations"></a><span data-ttu-id="67dd2-197">Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="67dd2-197">Security recommendations</span></span>

<span data-ttu-id="67dd2-198">**Beveiligingsaanbevelingen** worden gegenereerd vanuit Microsoft Defender voor de mogelijkheid & [beveiligingsprobleembeheer](tvm-dashboard-insights.md) van Endpoint.</span><span class="sxs-lookup"><span data-stu-id="67dd2-198">**Security recommendations** are generated from Microsoft Defender for Endpoint's [Threat & Vulnerability Management](tvm-dashboard-insights.md) capability.</span></span> <span data-ttu-id="67dd2-199">Als u een aanbeveling selecteert, wordt een deelvenster weergegeven waarin u relevante details kunt bekijken, zoals een beschrijving van de aanbeveling en de mogelijke risico's die samenhangen met het niet-bepalen van de aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="67dd2-199">Selecting a recommendation will show a panel where you can view relevant details such as description of the recommendation and the potential risks associated with not enacting it.</span></span> <span data-ttu-id="67dd2-200">Zie [Beveiligingsaanbeveling](tvm-security-recommendation.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="67dd2-200">See [Security recommendation](tvm-security-recommendation.md) for details.</span></span>

![Afbeelding van het tabblad Beveiligingsaanbevelingen](images/security-recommendations-device.png)

### <a name="software-inventory"></a><span data-ttu-id="67dd2-202">Softwarevoorraad</span><span class="sxs-lookup"><span data-stu-id="67dd2-202">Software inventory</span></span>

<span data-ttu-id="67dd2-203">Op **het tabblad Softwarevoorraad** kunt u software op het apparaat bekijken, samen met eventuele zwakke punten of bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="67dd2-203">The **Software inventory** tab lets you view software on the device, along with any weaknesses or threats.</span></span> <span data-ttu-id="67dd2-204">Als u de naam van de software selecteert, gaat u naar de pagina met softwaredetails waar u beveiligingsaanbevelingen, gevonden beveiligingsproblemen, geïnstalleerde apparaten en versiedistributie kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="67dd2-204">Selecting the name of the software will take you to the software details page where you can view security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span> <span data-ttu-id="67dd2-205">Zie [Softwarevoorraad voor](tvm-software-inventory.md) meer informatie</span><span class="sxs-lookup"><span data-stu-id="67dd2-205">See [Software inventory](tvm-software-inventory.md) for details</span></span>

![Afbeelding van het tabblad Softwarevoorraad](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a><span data-ttu-id="67dd2-207">Gevonden beveiligingslekken</span><span class="sxs-lookup"><span data-stu-id="67dd2-207">Discovered vulnerabilities</span></span>

<span data-ttu-id="67dd2-208">Het **tabblad Gevonden beveiligingslekken** toont de naam, ernst en bedreigingsinzichten van gevonden beveiligingslekken op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="67dd2-208">The **Discovered vulnerabilities** tab shows the name, severity, and threat insights of discovered vulnerabilities on the device.</span></span> <span data-ttu-id="67dd2-209">Als u specifieke beveiligingslekken selecteert, worden een beschrijving en details weergegeven.</span><span class="sxs-lookup"><span data-stu-id="67dd2-209">Selecting specific vulnerabilities will show a description and details.</span></span>

![Afbeelding van het tabblad Gevonden beveiligingslekken](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a><span data-ttu-id="67dd2-211">Ontbrekende KBs</span><span class="sxs-lookup"><span data-stu-id="67dd2-211">Missing KBs</span></span>
<span data-ttu-id="67dd2-212">Het **tabblad Ontbrekende KBs** bevat de ontbrekende beveiligingsupdates voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="67dd2-212">The **Missing KBs** tab lists the missing security updates for the device.</span></span>

![Afbeelding van ontbrekende kbs-tabblad](images/missing-kbs-device.png)

## <a name="cards"></a><span data-ttu-id="67dd2-214">Kaarten</span><span class="sxs-lookup"><span data-stu-id="67dd2-214">Cards</span></span>

### <a name="active-alerts"></a><span data-ttu-id="67dd2-215">Actieve waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="67dd2-215">Active alerts</span></span>

<span data-ttu-id="67dd2-216">De **Azure Advanced Threat Protection-kaart** geeft een overzicht op hoog niveau weer van waarschuwingen met betrekking tot het apparaat en het bijbehorende risiconiveau, als u de Azure ATP-functie hebt ingeschakeld en er actieve waarschuwingen zijn.</span><span class="sxs-lookup"><span data-stu-id="67dd2-216">The **Azure Advanced Threat Protection** card will display a high-level overview of alerts related to the device and their risk level, if you have enabled the Azure ATP feature, and there are any active alerts.</span></span> <span data-ttu-id="67dd2-217">Meer informatie vindt u in de inzooming 'Waarschuwingen'.</span><span class="sxs-lookup"><span data-stu-id="67dd2-217">More information is available in the "Alerts" drill down.</span></span>

![Afbeelding van actieve waarschuwingskaart](images/risk-level-small.png)

>[!NOTE]
><span data-ttu-id="67dd2-219">U moet de integratie op zowel Azure ATP als Defender for Endpoint inschakelen om deze functie te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="67dd2-219">You'll need to enable the integration on both Azure ATP and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="67dd2-220">In Defender voor Eindpunt kunt u deze functie inschakelen in geavanceerde functies.</span><span class="sxs-lookup"><span data-stu-id="67dd2-220">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="67dd2-221">Zie Geavanceerde functies inschakelen voor meer informatie over het inschakelen van [geavanceerde functies.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="67dd2-221">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

### <a name="logged-on-users"></a><span data-ttu-id="67dd2-222">Aangemelde gebruikers</span><span class="sxs-lookup"><span data-stu-id="67dd2-222">Logged on users</span></span>

<span data-ttu-id="67dd2-223">Op **de kaart Aangemelde gebruikers** ziet u hoeveel gebruikers zich de afgelopen 30 dagen hebben aangemeld, samen met de meest en minst frequente gebruikers.</span><span class="sxs-lookup"><span data-stu-id="67dd2-223">The **Logged on users** card shows how many users have logged on in the past 30 days, along with the most and least frequent users.</span></span> <span data-ttu-id="67dd2-224">Als u de koppeling 'Alle gebruikers weergeven' selecteert, wordt het detailvenster geopend, waarin informatie wordt weergegeven, zoals het type gebruiker, het type aanmelden en wanneer de gebruiker voor het eerst en voor het laatst is gezien.</span><span class="sxs-lookup"><span data-stu-id="67dd2-224">Selecting the "See all users" link opens the details pane, which displays information such as user type, log on type, and when the user was first and last seen.</span></span> <span data-ttu-id="67dd2-225">Zie [Gebruikersentiteiten onderzoeken voor meer informatie.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="67dd2-225">For more information, see [Investigate user entities](investigate-user.md).</span></span>

![Afbeelding van het deelvenster Gebruikersgegevens](images/logged-on-users.png)

### <a name="security-assessments"></a><span data-ttu-id="67dd2-227">Beveiligingsbeoordelingen</span><span class="sxs-lookup"><span data-stu-id="67dd2-227">Security assessments</span></span>

<span data-ttu-id="67dd2-228">De **kaart Beveiligingsbeoordelingen** toont het algehele blootstellingsniveau, beveiligingsaanbevelingen, geïnstalleerde software en ontdekte beveiligingsproblemen.</span><span class="sxs-lookup"><span data-stu-id="67dd2-228">The **Security assessments** card shows the overall exposure level, security recommendations, installed software, and discovered vulnerabilities.</span></span> <span data-ttu-id="67dd2-229">Het blootstellingsniveau van een apparaat wordt bepaald door de cumulatieve impact van de beveiligingsaanbevelingen in behandeling.</span><span class="sxs-lookup"><span data-stu-id="67dd2-229">A device's exposure level is determined by the cumulative impact of its pending security recommendations.</span></span>

![Afbeelding van beveiligingsbeoordelingenkaart](images/security-assessments.png)

## <a name="related-topics"></a><span data-ttu-id="67dd2-231">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="67dd2-231">Related topics</span></span>

- [<span data-ttu-id="67dd2-232">De wachtrij waarschuwingen voor Microsoft Defender voor eindpunten weergeven en ordenen</span><span class="sxs-lookup"><span data-stu-id="67dd2-232">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="67dd2-233">Waarschuwingen voor Microsoft Defender voor eindpunten beheren</span><span class="sxs-lookup"><span data-stu-id="67dd2-233">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="67dd2-234">Microsoft Defender onderzoeken voor eindpuntwaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="67dd2-234">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="67dd2-235">Een bestand onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="67dd2-235">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="67dd2-236">Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="67dd2-236">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="67dd2-237">Een domein onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="67dd2-237">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="67dd2-238">Een gebruikersaccount onderzoeken in Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="67dd2-238">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="67dd2-239">Beveiligingsaanbeveling</span><span class="sxs-lookup"><span data-stu-id="67dd2-239">Security recommendation</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="67dd2-240">Softwarevoorraad</span><span class="sxs-lookup"><span data-stu-id="67dd2-240">Software inventory</span></span>](tvm-software-inventory.md)
