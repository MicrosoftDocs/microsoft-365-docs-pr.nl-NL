---
title: Softwarevoorraad in Threat and Vulnerability Management
description: Op de pagina met softwarevoorraad voor de Threat and Vulnerability Management van Microsoft Defender voor Endpoint wordt weergegeven hoeveel zwakke punten en beveiligingslekken zijn gedetecteerd in software.
keywords: Threat and Vulnerability Management, Microsoft Defender for Endpoint, Microsoft Defender for Endpoint software inventory, Microsoft Defender for Endpoint threat & vulnerability management, Microsoft Defender for Endpoint threat & vulnerability management software inventory, Microsoft Defender for Endpoint tvm software inventory, tvm software inventory
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
ms.openlocfilehash: 0d270760cfed965c8190668afcdb1cc25223d2b1
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933719"
---
# <a name="software-inventory---threat-and-vulnerability-management"></a><span data-ttu-id="b47cd-104">Softwarevoorraad - Threat and Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="b47cd-104">Software inventory - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b47cd-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b47cd-105">**Applies to:**</span></span>
- [<span data-ttu-id="b47cd-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b47cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b47cd-107">Bedreiging en vulnerability management</span><span class="sxs-lookup"><span data-stu-id="b47cd-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="b47cd-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b47cd-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b47cd-109">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="b47cd-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b47cd-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="b47cd-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="b47cd-111">De softwarevoorraad in Threat and Vulnerability Management is een lijst met bekende software in uw organisatie met officiële Algemene Platform-opsommingen [(CPE).](https://nvd.nist.gov/products/cpe)</span><span class="sxs-lookup"><span data-stu-id="b47cd-111">The software inventory in threat and vulnerability management is a list of known software in your organization with official [Common Platform Enumerations (CPE)](https://nvd.nist.gov/products/cpe).</span></span> <span data-ttu-id="b47cd-112">Softwareproducten zonder een officiële CPE hebben geen beveiligingslekken gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="b47cd-112">Software products without an official CPE don’t have vulnerabilities published.</span></span> <span data-ttu-id="b47cd-113">Het bevat ook details, zoals de naam van de leverancier, het aantal zwakke punten, bedreigingen en het aantal blootgestelde apparaten.</span><span class="sxs-lookup"><span data-stu-id="b47cd-113">It also includes details such as the name of the vendor, number of weaknesses, threats, and number of exposed devices.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="b47cd-114">Hoe het werkt</span><span class="sxs-lookup"><span data-stu-id="b47cd-114">How it works</span></span>

<span data-ttu-id="b47cd-115">Op het gebied van detectie maken we gebruik van dezelfde reeks signalen die verantwoordelijk zijn voor detectie en kwetsbaarheidsanalyse in Microsoft Defender voor de detectie- en antwoordmogelijkheden voor [eindpunten.](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="b47cd-115">In the field of discovery, we're leveraging the same set of signals that is responsible for detection and vulnerability assessment in [Microsoft Defender for Endpoint detection and response capabilities](overview-endpoint-detection-response.md).</span></span>

<span data-ttu-id="b47cd-116">Aangezien het in realtime is, ziet u binnen enkele minuten informatie over de kwetsbaarheid wanneer deze worden ontdekt.</span><span class="sxs-lookup"><span data-stu-id="b47cd-116">Since it's real time, in a matter of minutes, you'll see vulnerability information as they get discovered.</span></span> <span data-ttu-id="b47cd-117">De engine neemt automatisch informatie op uit meerdere beveiligingsfeeds.</span><span class="sxs-lookup"><span data-stu-id="b47cd-117">The engine automatically grabs information from multiple security feeds.</span></span> <span data-ttu-id="b47cd-118">In feite ziet u of een bepaalde software is verbonden met een live-bedreigingscampagne.</span><span class="sxs-lookup"><span data-stu-id="b47cd-118">In fact, you'll see if a particular software is connected to a live threat campaign.</span></span> <span data-ttu-id="b47cd-119">Het rapport bevat ook een koppeling naar een Threat Analytics-rapport zodra het beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="b47cd-119">It also provides a link to a Threat Analytics report soon as it's available.</span></span>

## <a name="navigate-to-the-software-inventory-page"></a><span data-ttu-id="b47cd-120">Ga naar de pagina Softwarevoorraad</span><span class="sxs-lookup"><span data-stu-id="b47cd-120">Navigate to the Software inventory page</span></span>

<span data-ttu-id="b47cd-121">Toegang tot de pagina Softwarevoorraad door **Softwarevoorraad** te selecteren in het Threat and Vulnerability Management navigatiemenu in [de Microsoft Defender-beveiligingscentrum.](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b47cd-121">Access the Software inventory page by selecting **Software inventory** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md).</span></span>

<span data-ttu-id="b47cd-122">Bekijk software op specifieke apparaten op de pagina's met afzonderlijke apparaten in [de lijst met apparaten.](machines-view-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b47cd-122">View software on specific devices in the individual devices pages from the [devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="b47cd-123">Als u zoekt naar software met behulp van de globale zoekactie van Microsoft Defender voor Eindpunt, moet u een onderstrepingsteken in plaats van een spatie zetten.</span><span class="sxs-lookup"><span data-stu-id="b47cd-123">If you search for software using the Microsoft Defender for Endpoint global search, make sure to put an underscore instead of a space.</span></span> <span data-ttu-id="b47cd-124">Voor de beste zoekresultaten schrijft u bijvoorbeeld 'windows_10' in plaats van 'Windows 10'.</span><span class="sxs-lookup"><span data-stu-id="b47cd-124">For example, for the best search results you'd write "windows_10" instead of "Windows 10".</span></span>

## <a name="software-inventory-overview"></a><span data-ttu-id="b47cd-125">Overzicht van softwarevoorraad</span><span class="sxs-lookup"><span data-stu-id="b47cd-125">Software inventory overview</span></span>

<span data-ttu-id="b47cd-126">De **pagina Softwarevoorraad** wordt geopend met een lijst met software die in uw netwerk is geïnstalleerd, inclusief de naam van de leverancier, gevonden zwakke punten, bijbehorende bedreigingen, blootgestelde apparaten, invloed op de blootstellingsscore en tags.</span><span class="sxs-lookup"><span data-stu-id="b47cd-126">The **Software inventory** page opens with a list of software installed in your network, including the vendor name, weaknesses found, threats associated with them, exposed devices, impact to exposure score, and tags.</span></span>

<span data-ttu-id="b47cd-127">U kunt de lijstweergave filteren op basis van zwakke punten in de software, bedreigingen die aan de lijst zijn gekoppeld en tags, zoals of de software het einde van de ondersteuning heeft bereikt.</span><span class="sxs-lookup"><span data-stu-id="b47cd-127">You can filter the list view based on weaknesses found in the software, threats associated with them, and tags like whether the software has reached end-of-support.</span></span>

![Voorbeeld van de landingspagina voor softwarevoorraad.](images/tvm-software-inventory.png)

<span data-ttu-id="b47cd-129">Selecteer de software die u wilt onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="b47cd-129">Select the software that you want to investigate.</span></span> <span data-ttu-id="b47cd-130">Er wordt een flyoutvenster geopend met een compactere weergave van de informatie op de pagina.</span><span class="sxs-lookup"><span data-stu-id="b47cd-130">A flyout panel will open with a more compact view of the information on the page.</span></span> <span data-ttu-id="b47cd-131">U kunt dieper in het onderzoek duiken en softwarepagina openen selecteren of eventuele technische inconsistenties markeren door Onnauwkeurigheid van rapport **te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="b47cd-131">You can either dive deeper into the investigation and select **Open software page**, or flag any technical inconsistencies by selecting **Report inaccuracy**.</span></span>

### <a name="software-that-isnt-supported"></a><span data-ttu-id="b47cd-132">Software die niet wordt ondersteund</span><span class="sxs-lookup"><span data-stu-id="b47cd-132">Software that isn't supported</span></span>

<span data-ttu-id="b47cd-133">Software die momenteel niet wordt ondersteund door bedreigingen & vulnerability management kan aanwezig zijn op de inventarispagina software.</span><span class="sxs-lookup"><span data-stu-id="b47cd-133">Software that isn't currently supported by threat & vulnerability management may be present in the Software inventory page.</span></span> <span data-ttu-id="b47cd-134">Omdat deze niet wordt ondersteund, zijn er slechts beperkte gegevens beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="b47cd-134">Because it is not supported, only limited data will be available.</span></span> <span data-ttu-id="b47cd-135">Filter op niet-ondersteunde software met de optie 'Niet beschikbaar' in de sectie 'Zwakheid'.</span><span class="sxs-lookup"><span data-stu-id="b47cd-135">Filter by unsupported software with the "Not available" option in the "Weakness" section.</span></span>

![Niet-ondersteund softwarefilter.](images/tvm-unsupported-software-filter.png)

<span data-ttu-id="b47cd-137">Het volgende geeft aan dat een software niet wordt ondersteund:</span><span class="sxs-lookup"><span data-stu-id="b47cd-137">The following indicates that a software is not supported:</span></span>

- <span data-ttu-id="b47cd-138">Het veld Zwakke punten toont 'Niet beschikbaar'</span><span class="sxs-lookup"><span data-stu-id="b47cd-138">Weaknesses field shows "Not available"</span></span>
- <span data-ttu-id="b47cd-139">Veld Blootgestelde apparaten toont een streepje</span><span class="sxs-lookup"><span data-stu-id="b47cd-139">Exposed devices field shows a dash</span></span>
- <span data-ttu-id="b47cd-140">Informatie over tekst die is toegevoegd in het zijpaneel en op de softwarepagina</span><span class="sxs-lookup"><span data-stu-id="b47cd-140">Informational text added in side panel and in software page</span></span>
- <span data-ttu-id="b47cd-141">De softwarepagina heeft geen beveiligingsaanbevelingen, gevonden beveiligingsproblemen of tijdlijnsecties voor gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="b47cd-141">The software page won't have the security recommendations, discovered vulnerabilities, or event timeline sections</span></span>

<span data-ttu-id="b47cd-142">Momenteel worden producten zonder CPE niet weergegeven op de pagina softwarevoorraad, alleen in de softwarevoorraad op apparaatniveau.</span><span class="sxs-lookup"><span data-stu-id="b47cd-142">Currently, products without a CPE are not shown in the software inventory page, only in the device level software inventory.</span></span>

## <a name="software-inventory-on-devices"></a><span data-ttu-id="b47cd-143">Softwarevoorraad op apparaten</span><span class="sxs-lookup"><span data-stu-id="b47cd-143">Software inventory on devices</span></span>

<span data-ttu-id="b47cd-144">Ga vanuit Microsoft Defender-beveiligingscentrum navigatiescherm naar de lijst **[Apparaten.](machines-view-overview.md)**</span><span class="sxs-lookup"><span data-stu-id="b47cd-144">From the Microsoft Defender Security Center navigation panel, go to the **[Devices list](machines-view-overview.md)**.</span></span> <span data-ttu-id="b47cd-145">Selecteer de naam van een apparaat om de apparaatpagina te openen (zoals Computer1) en selecteer vervolgens het tabblad **Softwarevoorraad** om een lijst weer te geven met alle bekende software die op het apparaat aanwezig is.</span><span class="sxs-lookup"><span data-stu-id="b47cd-145">Select the name of a device to open the device page (like Computer1), then select the **Software inventory** tab to see a list of all the known software present on the device.</span></span> <span data-ttu-id="b47cd-146">Selecteer een specifieke software-vermelding om de flyout te openen met meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b47cd-146">Select a specific software entry to open the flyout with more information.</span></span>

<span data-ttu-id="b47cd-147">Software is mogelijk zichtbaar op apparaatniveau, zelfs als deze momenteel niet wordt ondersteund door Threat and Vulnerability Management.</span><span class="sxs-lookup"><span data-stu-id="b47cd-147">Software may be visible at the device level even if it is currently not supported by threat and vulnerability management.</span></span> <span data-ttu-id="b47cd-148">Er zijn echter slechts beperkte gegevens beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="b47cd-148">However, only limited data will be available.</span></span> <span data-ttu-id="b47cd-149">U weet of software niet wordt ondersteund, omdat er 'Niet beschikbaar' wordt gezegd in de kolom 'Zwakheid'.</span><span class="sxs-lookup"><span data-stu-id="b47cd-149">You'll know if software is unsupported because it will say "Not available" in the "Weakness" column.</span></span>

<span data-ttu-id="b47cd-150">Software zonder CPE kan ook worden gebruikt onder deze apparaatspecifieke softwarevoorraad.</span><span class="sxs-lookup"><span data-stu-id="b47cd-150">Software with no CPE can also show up under this device specific software inventory.</span></span>

### <a name="software-evidence"></a><span data-ttu-id="b47cd-151">Software-bewijs</span><span class="sxs-lookup"><span data-stu-id="b47cd-151">Software evidence</span></span>

<span data-ttu-id="b47cd-152">Bekijk waar we een specifieke software op een apparaat hebben gedetecteerd vanuit het register, de schijf of beide. U vindt het op elk apparaat in de inventaris van de apparaatsoftware.</span><span class="sxs-lookup"><span data-stu-id="b47cd-152">See evidence of where we detected a specific software on a device from the registry, disk, or both.You can find it on any device in the device software inventory.</span></span>

<span data-ttu-id="b47cd-153">Selecteer een softwarenaam om de flyout te openen en zoek naar de sectie 'Software evidence'.</span><span class="sxs-lookup"><span data-stu-id="b47cd-153">Select a software name to open the flyout, and look for the section called "Software Evidence."</span></span>

![Software evidence example of Windows 10 from the devices list, showing software evidence registry path.](images/tvm-software-evidence.png)

## <a name="software-pages"></a><span data-ttu-id="b47cd-155">Softwarepagina's</span><span class="sxs-lookup"><span data-stu-id="b47cd-155">Software pages</span></span>

<span data-ttu-id="b47cd-156">U kunt softwarepagina's op verschillende manieren bekijken:</span><span class="sxs-lookup"><span data-stu-id="b47cd-156">You can view software pages a few different ways:</span></span>

- <span data-ttu-id="b47cd-157">Pagina softwarevoorraad > Selecteer een softwarenaam > Selecteer **Softwarepagina openen** in de flyout</span><span class="sxs-lookup"><span data-stu-id="b47cd-157">Software inventory page > Select a software name > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="b47cd-158">[Pagina Met beveiligingsaanbevelingen](tvm-security-recommendation.md) > Selecteer een aanbeveling > Selecteer **Softwarepagina openen** in de flyout</span><span class="sxs-lookup"><span data-stu-id="b47cd-158">[Security recommendations page](tvm-security-recommendation.md) > Select a recommendation > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="b47cd-159">[Pagina tijdlijn](threat-and-vuln-mgt-event-timeline.md) van gebeurtenis > Selecteer een gebeurtenis > Selecteer de softwarenaam met hyperlinks (zoals Visual Studio 2017) in de sectie 'Gerelateerd onderdeel' in het flyout</span><span class="sxs-lookup"><span data-stu-id="b47cd-159">[Event timeline page](threat-and-vuln-mgt-event-timeline.md) > Select an event > Select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout</span></span>

 <span data-ttu-id="b47cd-160">Er wordt een volledige pagina weergegeven met alle details van een specifieke software en de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="b47cd-160">A full page will appear with all the details of a specific software and the following information:</span></span>

- <span data-ttu-id="b47cd-161">Zijpaneel met leveranciersgegevens, de aanwezigheid van de software in de organisatie (inclusief het aantal apparaten dat is geïnstalleerd op en blootgestelde apparaten die niet zijn gepatcht), of en welke exploit beschikbaar is, en van invloed zijn op uw blootstellingsscore.</span><span class="sxs-lookup"><span data-stu-id="b47cd-161">Side panel with vendor information, prevalence of the software in the organization (including number of devices it's installed on, and exposed devices that aren't patched), whether and exploit is available, and impact to your exposure score.</span></span>
- <span data-ttu-id="b47cd-162">Gegevensvisualisaties met het aantal en de ernst van, beveiligingslekken en onjuiste configuraties.</span><span class="sxs-lookup"><span data-stu-id="b47cd-162">Data visualizations showing the number of, and severity of, vulnerabilities and misconfigurations.</span></span> <span data-ttu-id="b47cd-163">Ook grafieken met het aantal blootgestelde apparaten.</span><span class="sxs-lookup"><span data-stu-id="b47cd-163">Also, graphs with the number of exposed devices.</span></span>
- <span data-ttu-id="b47cd-164">Tabbladen met informatie zoals:</span><span class="sxs-lookup"><span data-stu-id="b47cd-164">Tabs showing information such as:</span></span>
    - <span data-ttu-id="b47cd-165">Bijbehorende beveiligingsaanbevelingen voor de vastgestelde zwakke punten en beveiligingsproblemen.</span><span class="sxs-lookup"><span data-stu-id="b47cd-165">Corresponding security recommendations for the weaknesses and vulnerabilities identified.</span></span>
    - <span data-ttu-id="b47cd-166">Benoemde CVE's van gevonden beveiligingslekken.</span><span class="sxs-lookup"><span data-stu-id="b47cd-166">Named CVEs of discovered vulnerabilities.</span></span>
    - <span data-ttu-id="b47cd-167">Apparaten die de software hebben geïnstalleerd (samen met de naam van het apparaat, domein, besturingssysteem en meer).</span><span class="sxs-lookup"><span data-stu-id="b47cd-167">Devices that have the software installed (along with device name, domain, OS, and more).</span></span>
    - <span data-ttu-id="b47cd-168">Lijst met softwareversies (inclusief het aantal apparaten waar de versie op is geïnstalleerd, het aantal gevonden beveiligingslekken en de namen van de geïnstalleerde apparaten).</span><span class="sxs-lookup"><span data-stu-id="b47cd-168">Software version list (including number of devices the version is installed on, the number of discovered vulnerabilities, and the names of the installed devices).</span></span>

    ![Pagina softwarevoorbeeld voor Visual Studio 2017 met de softwaredetails, zwakke punten, blootgestelde apparaten en meer.](images/tvm-software-page-example.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="b47cd-170">Onnauwkeurigheid van rapport</span><span class="sxs-lookup"><span data-stu-id="b47cd-170">Report inaccuracy</span></span>

<span data-ttu-id="b47cd-171">Meld een onwaar positief wanneer u vage, onnauwkeurige of onvolledige informatie ziet.</span><span class="sxs-lookup"><span data-stu-id="b47cd-171">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="b47cd-172">U kunt ook rapporteren over beveiligingsaanbevelingen die al zijn gesaneerd.</span><span class="sxs-lookup"><span data-stu-id="b47cd-172">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="b47cd-173">Open de software flyout op de pagina Softwarevoorraad.</span><span class="sxs-lookup"><span data-stu-id="b47cd-173">Open the software flyout on the Software inventory page.</span></span>
2. <span data-ttu-id="b47cd-174">Selecteer **Onnauwkeurigheid van rapport**.</span><span class="sxs-lookup"><span data-stu-id="b47cd-174">Select **Report inaccuracy**.</span></span>
3. <span data-ttu-id="b47cd-175">Selecteer in het deelvenster Flyout de onnauwkeurigheidscategorie in de vervolgkeuzelijst, vul uw e-mailadres in en details over de onnauwkeurigheid.</span><span class="sxs-lookup"><span data-stu-id="b47cd-175">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details about the inaccuracy.</span></span>
4. <span data-ttu-id="b47cd-176">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="b47cd-176">Select **Submit**.</span></span> <span data-ttu-id="b47cd-177">Uw feedback wordt onmiddellijk verzonden naar de Threat and Vulnerability Management experts.</span><span class="sxs-lookup"><span data-stu-id="b47cd-177">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b47cd-178">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="b47cd-178">Related articles</span></span>

- [<span data-ttu-id="b47cd-179">Overzicht van bedreigingen en vulnerability management</span><span class="sxs-lookup"><span data-stu-id="b47cd-179">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="b47cd-180">Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="b47cd-180">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="b47cd-181">Tijdlijn van het evenement</span><span class="sxs-lookup"><span data-stu-id="b47cd-181">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
- [<span data-ttu-id="b47cd-182">De lijst Met Microsoft Defender voor eindpuntapparaten weergeven en organiseren</span><span class="sxs-lookup"><span data-stu-id="b47cd-182">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
