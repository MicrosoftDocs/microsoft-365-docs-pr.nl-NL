---
title: Apparaten onderzoeken in de lijst Defender voor eindpuntapparaten
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
ms.openlocfilehash: c89de5fbf5d5b4d5d5e53074109bc8884a271eea
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394891"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="a23b2-104">Apparaten onderzoeken in de lijst Microsoft Defender voor eindpuntapparaten</span><span class="sxs-lookup"><span data-stu-id="a23b2-104">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a23b2-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a23b2-105">**Applies to:**</span></span>
- [<span data-ttu-id="a23b2-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a23b2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a23b2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a23b2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a23b2-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="a23b2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a23b2-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="a23b2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="a23b2-110">Onderzoek de details van een waarschuwing die op een specifiek apparaat wordt opgehaald om andere gedragingen of gebeurtenissen te identificeren die mogelijk verband houden met de waarschuwing of het mogelijke bereik van de inbreuk.</span><span class="sxs-lookup"><span data-stu-id="a23b2-110">Investigate the details of an alert raised on a specific device to identify other behaviors or events that might be related to the alert or the potential scope of the breach.</span></span>

> [!NOTE]
> <span data-ttu-id="a23b2-111">Als onderdeel van het onderzoek- of antwoordproces kunt u een onderzoekspakket verzamelen vanaf een apparaat.</span><span class="sxs-lookup"><span data-stu-id="a23b2-111">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="a23b2-112">Dit doet u als: [Onderzoekspakket van apparaten verzamelen.](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices)</span><span class="sxs-lookup"><span data-stu-id="a23b2-112">Here's how: [Collect investigation package from devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="a23b2-113">U kunt op getroffen apparaten klikken wanneer u ze in de portal ziet om een gedetailleerd rapport over dat apparaat te openen.</span><span class="sxs-lookup"><span data-stu-id="a23b2-113">You can click on affected devices whenever you see them in the portal to open a detailed report about that device.</span></span> <span data-ttu-id="a23b2-114">Getroffen apparaten worden in de volgende gebieden geïdentificeerd:</span><span class="sxs-lookup"><span data-stu-id="a23b2-114">Affected devices are identified in the following areas:</span></span>

- [<span data-ttu-id="a23b2-115">Lijst met apparaten</span><span class="sxs-lookup"><span data-stu-id="a23b2-115">Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="a23b2-116">Waarschuwingenwachtrij</span><span class="sxs-lookup"><span data-stu-id="a23b2-116">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="a23b2-117">Dashboard beveiligingsbewerkingen</span><span class="sxs-lookup"><span data-stu-id="a23b2-117">Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="a23b2-118">Elke afzonderlijke waarschuwing</span><span class="sxs-lookup"><span data-stu-id="a23b2-118">Any individual alert</span></span>
- <span data-ttu-id="a23b2-119">Weergave van afzonderlijke bestandsdetails</span><span class="sxs-lookup"><span data-stu-id="a23b2-119">Any individual file details view</span></span>
- <span data-ttu-id="a23b2-120">Een ip-adres- of domeindetailweergave</span><span class="sxs-lookup"><span data-stu-id="a23b2-120">Any IP address or domain details view</span></span>

<span data-ttu-id="a23b2-121">Wanneer u een specifiek apparaat onderzoekt, ziet u:</span><span class="sxs-lookup"><span data-stu-id="a23b2-121">When you investigate a specific device, you'll see:</span></span>

- <span data-ttu-id="a23b2-122">Apparaatdetails</span><span class="sxs-lookup"><span data-stu-id="a23b2-122">Device details</span></span>
- <span data-ttu-id="a23b2-123">Reactieacties</span><span class="sxs-lookup"><span data-stu-id="a23b2-123">Response actions</span></span>
- <span data-ttu-id="a23b2-124">Tabbladen (overzicht, waarschuwingen, tijdlijn, beveiligingsaanbevelingen, softwarevoorraad, gevonden beveiligingslekken, ontbrekende KBs)</span><span class="sxs-lookup"><span data-stu-id="a23b2-124">Tabs (overview, alerts, timeline, security recommendations, software inventory, discovered vulnerabilities, missing KBs)</span></span>
- <span data-ttu-id="a23b2-125">Kaarten (actieve waarschuwingen, aangemelde gebruikers, beveiligingsbeoordeling)</span><span class="sxs-lookup"><span data-stu-id="a23b2-125">Cards (active alerts, logged on users, security assessment)</span></span>

![Afbeelding van de apparaatweergave](images/specific-device.png)

> [!NOTE]
> <span data-ttu-id="a23b2-127">Vanwege productbeperkten wordt in het apparaatprofiel niet rekening met alle cybergegevens bij het bepalen van de periode 'Laatst gezien' (zoals u ook op de apparaatpagina ziet).</span><span class="sxs-lookup"><span data-stu-id="a23b2-127">Due to product constrains, the device profile does not consider all cyber evidence when determining the 'Last Seen' timeframe (as seen on the device page as well).</span></span>
> <span data-ttu-id="a23b2-128">De waarde 'Laatst gezien' op de pagina Apparaat kan bijvoorbeeld een ouder tijdsbestek weergeven, ook al zijn er recentere waarschuwingen of gegevens beschikbaar in de tijdlijn van de computer.</span><span class="sxs-lookup"><span data-stu-id="a23b2-128">For example, the 'Last seen' value in the Device page may show an older time frame even though more recent alerts or data is available in the machine's timeline.</span></span>

## <a name="device-details"></a><span data-ttu-id="a23b2-129">Apparaatdetails</span><span class="sxs-lookup"><span data-stu-id="a23b2-129">Device details</span></span>

<span data-ttu-id="a23b2-130">De sectie apparaatdetails bevat informatie, zoals het domein, het besturingssysteem en de status van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a23b2-130">The device details section provides information such as the domain, OS, and health state of the device.</span></span> <span data-ttu-id="a23b2-131">Als er een onderzoekspakket beschikbaar is op het apparaat, ziet u een koppeling waarmee u het pakket kunt downloaden.</span><span class="sxs-lookup"><span data-stu-id="a23b2-131">If there's an investigation package available on the device, you'll see a link that allows you to download the package.</span></span>

## <a name="response-actions"></a><span data-ttu-id="a23b2-132">Reactieacties</span><span class="sxs-lookup"><span data-stu-id="a23b2-132">Response actions</span></span>

<span data-ttu-id="a23b2-133">Antwoordacties worden uitgevoerd boven aan een specifieke apparaatpagina en bevatten:</span><span class="sxs-lookup"><span data-stu-id="a23b2-133">Response actions run along the top of a specific device page and include:</span></span>

- <span data-ttu-id="a23b2-134">Tags beheren</span><span class="sxs-lookup"><span data-stu-id="a23b2-134">Manage tags</span></span>
- <span data-ttu-id="a23b2-135">Apparaat isoleren</span><span class="sxs-lookup"><span data-stu-id="a23b2-135">Isolate device</span></span>
- <span data-ttu-id="a23b2-136">Het uitvoeren van apps beperken</span><span class="sxs-lookup"><span data-stu-id="a23b2-136">Restrict app execution</span></span>
- <span data-ttu-id="a23b2-137">Antivirusscan uitvoeren</span><span class="sxs-lookup"><span data-stu-id="a23b2-137">Run antivirus scan</span></span>
- <span data-ttu-id="a23b2-138">Onderzoekspakket verzamelen</span><span class="sxs-lookup"><span data-stu-id="a23b2-138">Collect investigation package</span></span>
- <span data-ttu-id="a23b2-139">Live-antwoordsessie starten</span><span class="sxs-lookup"><span data-stu-id="a23b2-139">Initiate Live Response Session</span></span>
- <span data-ttu-id="a23b2-140">Geautomatiseerd onderzoek starten</span><span class="sxs-lookup"><span data-stu-id="a23b2-140">Initiate automated investigation</span></span>
- <span data-ttu-id="a23b2-141">Contact opnemen met een risicodeskundige</span><span class="sxs-lookup"><span data-stu-id="a23b2-141">Consult a threat expert</span></span>
- <span data-ttu-id="a23b2-142">Actiecentrum</span><span class="sxs-lookup"><span data-stu-id="a23b2-142">Action center</span></span>

<span data-ttu-id="a23b2-143">U kunt antwoordacties uitvoeren in het actiecentrum, op een specifieke apparaatpagina of op een specifieke bestandspagina.</span><span class="sxs-lookup"><span data-stu-id="a23b2-143">You can take response actions in the Action center, in a specific device page, or in a specific file page.</span></span>

<span data-ttu-id="a23b2-144">Zie Actie ondernemen op een apparaat voor meer informatie over het ondernemen van actie [op een apparaat.](respond-machine-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="a23b2-144">For more information on how to take action on a device, see [Take response action on a device](respond-machine-alerts.md).</span></span>

<span data-ttu-id="a23b2-145">Zie [Gebruikersentiteiten onderzoeken voor meer informatie.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="a23b2-145">For more information, see [Investigate user entities](investigate-user.md).</span></span>

## <a name="tabs"></a><span data-ttu-id="a23b2-146">Tabbladen</span><span class="sxs-lookup"><span data-stu-id="a23b2-146">Tabs</span></span>

<span data-ttu-id="a23b2-147">De tabbladen bevatten relevante beveiligings- en preventiegegevens met betrekking tot het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a23b2-147">The tabs provide relevant security and threat prevention information related to the device.</span></span> <span data-ttu-id="a23b2-148">Op elk tabblad kunt u de kolommen aanpassen die worden weergegeven door Kolommen **aanpassen te selecteren** op de balk boven de kolomkoppen.</span><span class="sxs-lookup"><span data-stu-id="a23b2-148">In each tab, you can customize the columns that are shown by selecting **Customize columns** from the bar above the column headers.</span></span>

### <a name="overview"></a><span data-ttu-id="a23b2-149">Overzicht</span><span class="sxs-lookup"><span data-stu-id="a23b2-149">Overview</span></span>
<span data-ttu-id="a23b2-150">Op **het tabblad** Overzicht worden de kaarten [weergegeven](#cards) voor actieve waarschuwingen, aangemeld bij gebruikers en beveiligingsbeoordeling.</span><span class="sxs-lookup"><span data-stu-id="a23b2-150">The **Overview** tab displays the [cards](#cards) for active alerts, logged on users, and security assessment.</span></span>

![Afbeelding van het tabblad Overzicht op de apparaatpagina](images/overview-device.png)

### <a name="alerts"></a><span data-ttu-id="a23b2-152">Waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="a23b2-152">Alerts</span></span>

<span data-ttu-id="a23b2-153">Het **tabblad** Waarschuwingen bevat een lijst met waarschuwingen die zijn gekoppeld aan het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a23b2-153">The **Alerts** tab provides a list of alerts that are associated with the device.</span></span> <span data-ttu-id="a23b2-154">Deze lijst is een gefilterde versie van de wachtrij Waarschuwingen en toont een korte beschrijving van de waarschuwing, ernst (hoog, gemiddeld, laag, informatief), status in de wachtrij (nieuw, in uitvoering, opgelost), classificatie (niet ingesteld, onwaar waarschuwing, waar waarschuwing), onderzoeksstatus, categorie van waarschuwing, wie de waarschuwing adresseert en laatste activiteit. [](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="a23b2-154">This list is a filtered version of the [Alerts queue](alerts-queue.md), and shows a short description of the alert, severity (high, medium, low, informational), status in the queue (new, in progress, resolved), classification (not set, false alert, true alert), investigation state, category of alert, who is addressing the alert, and last activity.</span></span> <span data-ttu-id="a23b2-155">U kunt de waarschuwingen ook filteren.</span><span class="sxs-lookup"><span data-stu-id="a23b2-155">You can also filter the alerts.</span></span>

![Afbeelding van waarschuwingen met betrekking tot het apparaat](images/alerts-device.png)

<span data-ttu-id="a23b2-157">Wanneer het cirkelpictogram links van een waarschuwing is geselecteerd, wordt er een fly-out weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a23b2-157">When the circle icon to the left of an alert is selected, a fly-out appears.</span></span> <span data-ttu-id="a23b2-158">In dit deelvenster kunt u de waarschuwing beheren en meer details weergeven, zoals incidentnummer en gerelateerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="a23b2-158">From this panel you can manage the alert and view more details such as incident number and related devices.</span></span> <span data-ttu-id="a23b2-159">Er kunnen meerdere waarschuwingen tegelijk worden geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="a23b2-159">Multiple alerts can be selected at a time.</span></span>

<span data-ttu-id="a23b2-160">Als u een volledige paginaweergave van een waarschuwing wilt zien, inclusief incidentgrafiek en processtructuur, selecteert u de titel van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="a23b2-160">To see a full page view of an alert including incident graph and process tree, select the title of the alert.</span></span>

### <a name="timeline"></a><span data-ttu-id="a23b2-161">Tijdlijn</span><span class="sxs-lookup"><span data-stu-id="a23b2-161">Timeline</span></span>

<span data-ttu-id="a23b2-162">Het **tabblad** Tijdlijn bevat een chronologische weergave van de gebeurtenissen en bijbehorende waarschuwingen die zijn waargenomen op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a23b2-162">The **Timeline** tab provides a chronological view of the events and associated alerts that have been observed on the device.</span></span> <span data-ttu-id="a23b2-163">Dit kan u helpen bij het correleren van gebeurtenissen, bestanden en IP-adressen ten opzichte van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a23b2-163">This can help you correlate any events, files, and IP addresses in relation to the device.</span></span>

<span data-ttu-id="a23b2-164">Met de tijdlijn kunt u ook selectief inzoomen op gebeurtenissen die binnen een bepaalde periode hebben plaatsgevonden.</span><span class="sxs-lookup"><span data-stu-id="a23b2-164">The timeline also enables you to selectively drill down into events that occurred within a given time period.</span></span> <span data-ttu-id="a23b2-165">U kunt de temporele volgorde bekijken van gebeurtenissen die zich hebben voorgedaan op een apparaat gedurende een geselecteerde periode.</span><span class="sxs-lookup"><span data-stu-id="a23b2-165">You can view the temporal sequence of events that occurred on a device over a selected time period.</span></span> <span data-ttu-id="a23b2-166">Als u de weergave verder wilt bepalen, kunt u filteren op gebeurtenisgroepen of de kolommen aanpassen.</span><span class="sxs-lookup"><span data-stu-id="a23b2-166">To further control your view, you can filter by event groups or customize the columns.</span></span>

>[!NOTE]
> <span data-ttu-id="a23b2-167">Als u firewallgebeurtenissen wilt weergeven, moet u het controlebeleid inschakelen, zie [Verbinding auditfilterplatform](/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span><span class="sxs-lookup"><span data-stu-id="a23b2-167">For firewall events to be displayed, you'll need to enable the audit policy, see [Audit Filtering Platform connection](/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span></span>
><span data-ttu-id="a23b2-168">Firewall bestrijkt de volgende gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="a23b2-168">Firewall covers the following events</span></span>
>
>- <span data-ttu-id="a23b2-169">[5025](/windows/security/threat-protection/auditing/event-5025) - firewallservice gestopt</span><span class="sxs-lookup"><span data-stu-id="a23b2-169">[5025](/windows/security/threat-protection/auditing/event-5025) - firewall service stopped</span></span>
>- <span data-ttu-id="a23b2-170">[5031](/windows/security/threat-protection/auditing/event-5031) - toepassing die is geblokkeerd voor het accepteren van inkomende verbindingen in het netwerk</span><span class="sxs-lookup"><span data-stu-id="a23b2-170">[5031](/windows/security/threat-protection/auditing/event-5031) - application blocked from accepting incoming connections on the network</span></span>
>- <span data-ttu-id="a23b2-171">[5157](/windows/security/threat-protection/auditing/event-5157) - geblokkeerde verbinding</span><span class="sxs-lookup"><span data-stu-id="a23b2-171">[5157](/windows/security/threat-protection/auditing/event-5157) - blocked connection</span></span>

![Afbeelding van apparaattijdlijn met gebeurtenissen](images/timeline-device.png)

<span data-ttu-id="a23b2-173">Enkele functies omvatten:</span><span class="sxs-lookup"><span data-stu-id="a23b2-173">Some of the functionality includes:</span></span>

- <span data-ttu-id="a23b2-174">Zoeken naar specifieke gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="a23b2-174">Search for specific events</span></span>
  - <span data-ttu-id="a23b2-175">Gebruik de zoekbalk om te zoeken naar specifieke tijdlijngebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="a23b2-175">Use the search bar to look for specific timeline events.</span></span>
- <span data-ttu-id="a23b2-176">Gebeurtenissen filteren vanaf een bepaalde datum</span><span class="sxs-lookup"><span data-stu-id="a23b2-176">Filter events from a specific date</span></span>
  - <span data-ttu-id="a23b2-177">Selecteer het agendapictogram in de linkerbovenhoek van de tabel om gebeurtenissen weer te geven in de afgelopen dag, week, 30 dagen of aangepast bereik.</span><span class="sxs-lookup"><span data-stu-id="a23b2-177">Select the calendar icon in the upper left of the table to display events in the past day, week, 30 days, or custom range.</span></span> <span data-ttu-id="a23b2-178">De apparaattijdlijn is standaard ingesteld op het weergeven van de gebeurtenissen uit de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="a23b2-178">By default, the device timeline is set to display the events from the past 30 days.</span></span>
  - <span data-ttu-id="a23b2-179">Gebruik de tijdlijn om naar een bepaald moment in de tijd te gaan door de sectie te markeren.</span><span class="sxs-lookup"><span data-stu-id="a23b2-179">Use the timeline to jump to a specific moment in time by highlighting the section.</span></span> <span data-ttu-id="a23b2-180">De pijlen op de tijdlijn wijzen geautomatiseerde onderzoeken aan</span><span class="sxs-lookup"><span data-stu-id="a23b2-180">The arrows on the timeline pinpoint automated investigations</span></span>
- <span data-ttu-id="a23b2-181">Gedetailleerde apparaattijdlijngebeurtenissen exporteren</span><span class="sxs-lookup"><span data-stu-id="a23b2-181">Export detailed device timeline events</span></span>
  - <span data-ttu-id="a23b2-182">Exporteert de apparaattijdlijn voor de huidige datum of een opgegeven datumbereik tot zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="a23b2-182">Export the device timeline for the current date or a specified date range up to seven days.</span></span>

<span data-ttu-id="a23b2-183">Meer informatie over bepaalde gebeurtenissen vindt u in de **sectie Aanvullende** informatie.</span><span class="sxs-lookup"><span data-stu-id="a23b2-183">More details about certain events are provided in the **Additional information** section.</span></span> <span data-ttu-id="a23b2-184">Deze details variëren afhankelijk van het type gebeurtenis, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="a23b2-184">These details vary depending on the type of event, for example:</span></span> 

- <span data-ttu-id="a23b2-185">Ingesloten door Application Guard : de webbrowsergebeurtenis is beperkt door een geïsoleerde container</span><span class="sxs-lookup"><span data-stu-id="a23b2-185">Contained by Application Guard - the web browser event was restricted by an isolated container</span></span>
- <span data-ttu-id="a23b2-186">Actieve bedreiging gedetecteerd: de detectie van bedreigingen vond plaats terwijl de bedreiging werd uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="a23b2-186">Active threat detected - the threat detection occurred while the threat was running</span></span>
- <span data-ttu-id="a23b2-187">Herstel mislukt: een poging om de gedetecteerde bedreiging te herstellen is aangeroepen, maar is mislukt</span><span class="sxs-lookup"><span data-stu-id="a23b2-187">Remediation unsuccessful - an attempt to remediate the detected threat was invoked but failed</span></span>
- <span data-ttu-id="a23b2-188">Herstel is gelukt: de gedetecteerde bedreiging is gestopt en opgeruimd</span><span class="sxs-lookup"><span data-stu-id="a23b2-188">Remediation successful - the detected threat was stopped and cleaned</span></span>
- <span data-ttu-id="a23b2-189">Waarschuwing overgeslagen door gebruiker: de waarschuwing Windows Defender SmartScreen is door een gebruiker afgewezen en overgenomen</span><span class="sxs-lookup"><span data-stu-id="a23b2-189">Warning bypassed by user - the Windows Defender SmartScreen warning was dismissed and overridden by a user</span></span>
- <span data-ttu-id="a23b2-190">Verdacht script gedetecteerd : er is een mogelijk schadelijk script gevonden dat werd uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="a23b2-190">Suspicious script detected - a potentially malicious script was found running</span></span>
- <span data-ttu-id="a23b2-191">De waarschuwingscategorie: als de gebeurtenis heeft geleid tot het genereren van een waarschuwing, wordt de waarschuwingscategorie ("Zijbeweging", bijvoorbeeld) verstrekt</span><span class="sxs-lookup"><span data-stu-id="a23b2-191">The alert category - if the event led to the generation of an alert, the alert category  ("Lateral Movement", for example) is provided</span></span>

#### <a name="event-details"></a><span data-ttu-id="a23b2-192">Details van de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="a23b2-192">Event details</span></span>
<span data-ttu-id="a23b2-193">Selecteer een gebeurtenis om relevante details over die gebeurtenis weer te geven.</span><span class="sxs-lookup"><span data-stu-id="a23b2-193">Select an event to view relevant details about that event.</span></span> <span data-ttu-id="a23b2-194">Er wordt een deelvenster weergegeven om algemene gebeurtenisgegevens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="a23b2-194">A panel displays to show general event information.</span></span> <span data-ttu-id="a23b2-195">Wanneer dit van toepassing is en gegevens beschikbaar zijn, wordt ook een grafiek weergegeven met gerelateerde entiteiten en hun relaties.</span><span class="sxs-lookup"><span data-stu-id="a23b2-195">When applicable and data is available, a graph showing related entities and their relationships are also shown.</span></span>

<span data-ttu-id="a23b2-196">Als u de gebeurtenis en gerelateerde gebeurtenissen verder wilt controleren, kunt u snel een geavanceerde [query](advanced-hunting-overview.md) uitvoeren door Hunt te selecteren **voor gerelateerde gebeurtenissen.**</span><span class="sxs-lookup"><span data-stu-id="a23b2-196">To further inspect the event and related events, you can quickly run an [advanced hunting](advanced-hunting-overview.md) query by selecting **Hunt for related events**.</span></span> <span data-ttu-id="a23b2-197">De query retournoemt de geselecteerde gebeurtenis en de lijst met andere gebeurtenissen die rond dezelfde tijd op hetzelfde eindpunt hebben plaatsgevonden.</span><span class="sxs-lookup"><span data-stu-id="a23b2-197">The query will return the selected event and the list of other events that occurred around the same time on the same endpoint.</span></span>

![Afbeelding van het deelvenster details van de gebeurtenis](images/event-details.png)

### <a name="security-recommendations"></a><span data-ttu-id="a23b2-199">Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="a23b2-199">Security recommendations</span></span>

<span data-ttu-id="a23b2-200">**Beveiligingsaanbevelingen** worden gegenereerd vanuit Microsoft Defender voor de mogelijkheid & [beveiligingsprobleembeheer](tvm-dashboard-insights.md) van Endpoint.</span><span class="sxs-lookup"><span data-stu-id="a23b2-200">**Security recommendations** are generated from Microsoft Defender for Endpoint's [Threat & Vulnerability Management](tvm-dashboard-insights.md) capability.</span></span> <span data-ttu-id="a23b2-201">Als u een aanbeveling selecteert, wordt een deelvenster weergegeven waarin u relevante details kunt bekijken, zoals een beschrijving van de aanbeveling en de mogelijke risico's die samenhangen met het niet-bepalen van de aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="a23b2-201">Selecting a recommendation will show a panel where you can view relevant details such as description of the recommendation and the potential risks associated with not enacting it.</span></span> <span data-ttu-id="a23b2-202">Zie [Beveiligingsaanbeveling](tvm-security-recommendation.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a23b2-202">See [Security recommendation](tvm-security-recommendation.md) for details.</span></span>

![Afbeelding van het tabblad Beveiligingsaanbevelingen](images/security-recommendations-device.png)

### <a name="software-inventory"></a><span data-ttu-id="a23b2-204">Software-inventaris</span><span class="sxs-lookup"><span data-stu-id="a23b2-204">Software inventory</span></span>

<span data-ttu-id="a23b2-205">Op **het tabblad Softwarevoorraad** kunt u software op het apparaat bekijken, samen met eventuele zwakke punten of bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="a23b2-205">The **Software inventory** tab lets you view software on the device, along with any weaknesses or threats.</span></span> <span data-ttu-id="a23b2-206">Als u de naam van de software selecteert, gaat u naar de pagina met softwaredetails waar u beveiligingsaanbevelingen, gevonden beveiligingsproblemen, geïnstalleerde apparaten en versiedistributie kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="a23b2-206">Selecting the name of the software will take you to the software details page where you can view security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span> <span data-ttu-id="a23b2-207">Zie [Softwarevoorraad voor](tvm-software-inventory.md) meer informatie</span><span class="sxs-lookup"><span data-stu-id="a23b2-207">See [Software inventory](tvm-software-inventory.md) for details</span></span>

![Afbeelding van het tabblad Softwarevoorraad](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a><span data-ttu-id="a23b2-209">Gevonden beveiligingslekken</span><span class="sxs-lookup"><span data-stu-id="a23b2-209">Discovered vulnerabilities</span></span>

<span data-ttu-id="a23b2-210">Het **tabblad Gevonden beveiligingslekken** toont de naam, ernst en bedreigingsinzichten van gevonden beveiligingslekken op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a23b2-210">The **Discovered vulnerabilities** tab shows the name, severity, and threat insights of discovered vulnerabilities on the device.</span></span> <span data-ttu-id="a23b2-211">Als u specifieke beveiligingslekken selecteert, worden een beschrijving en details weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a23b2-211">Selecting specific vulnerabilities will show a description and details.</span></span>

![Afbeelding van het tabblad Gevonden beveiligingslekken](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a><span data-ttu-id="a23b2-213">Ontbrekende KBs</span><span class="sxs-lookup"><span data-stu-id="a23b2-213">Missing KBs</span></span>
<span data-ttu-id="a23b2-214">Het **tabblad Ontbrekende KBs** bevat de ontbrekende beveiligingsupdates voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a23b2-214">The **Missing KBs** tab lists the missing security updates for the device.</span></span>

![Afbeelding van ontbrekende kbs-tabblad](images/missing-kbs-device.png)

## <a name="cards"></a><span data-ttu-id="a23b2-216">Kaarten</span><span class="sxs-lookup"><span data-stu-id="a23b2-216">Cards</span></span>

### <a name="active-alerts"></a><span data-ttu-id="a23b2-217">Actieve waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="a23b2-217">Active alerts</span></span>

<span data-ttu-id="a23b2-218">De **Azure Advanced Threat Protection-kaart** geeft een overzicht van waarschuwingen op hoog niveau met betrekking tot het apparaat en het risiconiveau, als u de microsoft Defender voor identiteitsfunctie hebt ingeschakeld en er actieve waarschuwingen zijn.</span><span class="sxs-lookup"><span data-stu-id="a23b2-218">The **Azure Advanced Threat Protection** card will display a high-level overview of alerts related to the device and their risk level, if you have enabled the Microsoft Defender for Identity feature, and there are any active alerts.</span></span> <span data-ttu-id="a23b2-219">Meer informatie vindt u in de inzooming 'Waarschuwingen'.</span><span class="sxs-lookup"><span data-stu-id="a23b2-219">More information is available in the "Alerts" drill down.</span></span>

![Afbeelding van actieve waarschuwingskaart](images/risk-level-small.png)

>[!NOTE]
><span data-ttu-id="a23b2-221">U moet de integratie inschakelen op zowel Microsoft Defender voor identiteit als Defender voor Eindpunt om deze functie te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a23b2-221">You'll need to enable the integration on both Microsoft Defender for Identity and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="a23b2-222">In Defender voor Eindpunt kunt u deze functie inschakelen in geavanceerde functies.</span><span class="sxs-lookup"><span data-stu-id="a23b2-222">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="a23b2-223">Zie Geavanceerde functies inschakelen voor meer informatie over het inschakelen van [geavanceerde functies.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="a23b2-223">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

### <a name="logged-on-users"></a><span data-ttu-id="a23b2-224">Aangemelde gebruikers</span><span class="sxs-lookup"><span data-stu-id="a23b2-224">Logged on users</span></span>

<span data-ttu-id="a23b2-225">Op **de kaart Aangemelde gebruikers** ziet u hoeveel gebruikers zich de afgelopen 30 dagen hebben aangemeld, samen met de meest en minst frequente gebruikers.</span><span class="sxs-lookup"><span data-stu-id="a23b2-225">The **Logged on users** card shows how many users have logged on in the past 30 days, along with the most and least frequent users.</span></span> <span data-ttu-id="a23b2-226">Als u de koppeling 'Alle gebruikers weergeven' selecteert, wordt het detailvenster geopend, waarin informatie wordt weergegeven, zoals het type gebruiker, het type aanmelden en wanneer de gebruiker voor het eerst en voor het laatst is gezien.</span><span class="sxs-lookup"><span data-stu-id="a23b2-226">Selecting the "See all users" link opens the details pane, which displays information such as user type, log on type, and when the user was first and last seen.</span></span> <span data-ttu-id="a23b2-227">Zie [Gebruikersentiteiten onderzoeken voor meer informatie.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="a23b2-227">For more information, see [Investigate user entities](investigate-user.md).</span></span>

![Afbeelding van het deelvenster Gebruikersgegevens](images/logged-on-users.png)
> [!NOTE]
> <span data-ttu-id="a23b2-229">De 'Meest voorkomende' gebruikerswaarde wordt alleen berekend op basis van gegevens van gebruikers die zich interactief hebben aangemeld.</span><span class="sxs-lookup"><span data-stu-id="a23b2-229">The 'Most frequent' user value is calculated only based on evidence of users who successfully logged on interactively.</span></span> <span data-ttu-id="a23b2-230">In het zijdeelvenster 'Alle gebruikers' worden echter allerlei gebruikerslogo's berekend, zodat er naar verwachting vaker gebruikers in het zijdeelvenster worden weergegeven, aangezien deze gebruikers mogelijk niet interactief zijn.</span><span class="sxs-lookup"><span data-stu-id="a23b2-230">However, the "All users" side-pane calculates all sorts of user logons so it is expected to see more frequent users in the side-pane, given that those users may not be interactive.</span></span>

### <a name="security-assessments"></a><span data-ttu-id="a23b2-231">Beveiligingsbeoordelingen</span><span class="sxs-lookup"><span data-stu-id="a23b2-231">Security assessments</span></span>

<span data-ttu-id="a23b2-232">De **kaart Beveiligingsbeoordelingen** toont het algehele blootstellingsniveau, beveiligingsaanbevelingen, geïnstalleerde software en ontdekte beveiligingsproblemen.</span><span class="sxs-lookup"><span data-stu-id="a23b2-232">The **Security assessments** card shows the overall exposure level, security recommendations, installed software, and discovered vulnerabilities.</span></span> <span data-ttu-id="a23b2-233">Het blootstellingsniveau van een apparaat wordt bepaald door de cumulatieve impact van de beveiligingsaanbevelingen in behandeling.</span><span class="sxs-lookup"><span data-stu-id="a23b2-233">A device's exposure level is determined by the cumulative impact of its pending security recommendations.</span></span>

![Afbeelding van beveiligingsbeoordelingenkaart](images/security-assessments.png)

## <a name="related-topics"></a><span data-ttu-id="a23b2-235">Gerelateerde onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a23b2-235">Related topics</span></span>

- [<span data-ttu-id="a23b2-236">De wachtrij waarschuwingen voor Microsoft Defender voor eindpunten weergeven en ordenen</span><span class="sxs-lookup"><span data-stu-id="a23b2-236">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="a23b2-237">Waarschuwingen voor Microsoft Defender voor eindpunten beheren</span><span class="sxs-lookup"><span data-stu-id="a23b2-237">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="a23b2-238">Microsoft Defender onderzoeken voor eindpuntwaarschuwingen</span><span class="sxs-lookup"><span data-stu-id="a23b2-238">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="a23b2-239">Een bestand onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="a23b2-239">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="a23b2-240">Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="a23b2-240">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="a23b2-241">Een domein onderzoeken dat is gekoppeld aan een waarschuwing van Defender voor eindpunt</span><span class="sxs-lookup"><span data-stu-id="a23b2-241">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="a23b2-242">Een gebruikersaccount onderzoeken in Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a23b2-242">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="a23b2-243">Beveiligingsaanbeveling</span><span class="sxs-lookup"><span data-stu-id="a23b2-243">Security recommendation</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="a23b2-244">Software-inventaris</span><span class="sxs-lookup"><span data-stu-id="a23b2-244">Software inventory</span></span>](tvm-software-inventory.md)
