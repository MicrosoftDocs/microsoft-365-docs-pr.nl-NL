---
title: 'Beveiligingslekken in mijn organisatie : bedreigings- en kwetsbaarheidsbeheer'
description: Hier vindt u de algemene beveiligingslekken en blootstellings-id (CVE) van zwakke punten in de software die in uw organisatie wordt uitgevoerd. Ontdekt door de Microsoft Defender for Endpoint threat and vulnerability management capability.
keywords: mdatp threat & vulnerability management, threat and vulnerability management, mdatp tvm weaknesses page, finding weaknesses through tvm, tvm vulnerability list, vulnerability details in tvm
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
ms.openlocfilehash: 0f573b2425764876e877de44555691979a0e1fcf
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689399"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a><span data-ttu-id="e3c58-105">Beveiligingslekken in mijn organisatie : bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="e3c58-105">Vulnerabilities in my organization - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e3c58-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e3c58-106">**Applies to:**</span></span>
- [<span data-ttu-id="e3c58-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e3c58-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e3c58-108">Bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="e3c58-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e3c58-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3c58-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e3c58-110">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="e3c58-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e3c58-111">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="e3c58-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="e3c58-112">Bedreigings- en kwetsbaarheidsbeheer gebruikt dezelfde signalen in de endpointbeveiliging van Defender voor eindpuntbeveiliging om beveiligingsproblemen te scannen en op te sporen.</span><span class="sxs-lookup"><span data-stu-id="e3c58-112">Threat and vulnerability management uses the same signals in Defender for Endpoint's endpoint protection to scan and detect vulnerabilities.</span></span>

<span data-ttu-id="e3c58-113">Op **de pagina Zwakke** punten worden de beveiligingslekken vermeld waar uw apparaten aan worden blootgesteld door de CVE-id (Common Vulnerabilities and Exposures) te noteren.</span><span class="sxs-lookup"><span data-stu-id="e3c58-113">The **Weaknesses** page lists the software vulnerabilities your devices are exposed to by listing the Common Vulnerabilities and Exposures (CVE) ID.</span></span> <span data-ttu-id="e3c58-114">U kunt ook de ernst, cvss-classificatie (Common Vulnerability Scoring System), de prevalentie in uw organisatie, de bijbehorende inbreuk, bedreigingsinzichten en meer bekijken.</span><span class="sxs-lookup"><span data-stu-id="e3c58-114">You can also view the severity, Common Vulnerability Scoring System (CVSS) rating, prevalence in your organization, corresponding breach, threat insights, and more.</span></span>

>[!NOTE]
><span data-ttu-id="e3c58-115">Als er geen officiële CVE-ID is toegewezen aan een beveiligingsprobleem, wordt de naam van de kwetsbaarheid toegewezen door bedreigings- en kwetsbaarheidsbeheer.</span><span class="sxs-lookup"><span data-stu-id="e3c58-115">If there is no official CVE-ID assigned to a vulnerability, the vulnerability name is assigned by threat and vulnerability management.</span></span>

>[!TIP]
><span data-ttu-id="e3c58-116">Zie E-mailmeldingen voor kwetsbaarheid configureren in Microsoft Defender voor Eindpunt voor e-mailberichten over [nieuwe beveiligingsprobleemgebeurtenissen](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="e3c58-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-weaknesses-page"></a><span data-ttu-id="e3c58-117">Naar de pagina Zwakke punten gaan</span><span class="sxs-lookup"><span data-stu-id="e3c58-117">Navigate to the Weaknesses page</span></span>

<span data-ttu-id="e3c58-118">Toegang tot de pagina Zwakheden op een aantal verschillende manieren:</span><span class="sxs-lookup"><span data-stu-id="e3c58-118">Access the Weaknesses page a few different ways:</span></span>

- <span data-ttu-id="e3c58-119">Zwakke **punten selecteren** in het navigatiemenu bedreigings- en kwetsbaarheidsbeheer in het Microsoft [Defender-beveiligingscentrum](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e3c58-119">Selecting **Weaknesses** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="e3c58-120">Algemene zoekactie</span><span class="sxs-lookup"><span data-stu-id="e3c58-120">Global search</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="e3c58-121">Navigatiemenu</span><span class="sxs-lookup"><span data-stu-id="e3c58-121">Navigation menu</span></span>

<span data-ttu-id="e3c58-122">Ga naar het navigatiemenu bedreigings- en beveiligingsprobleembeheer en selecteer **Zwakke punten om** de lijst met CVE's te openen.</span><span class="sxs-lookup"><span data-stu-id="e3c58-122">Go to the threat and vulnerability management navigation menu and select **Weaknesses** to open the list of CVEs.</span></span>

### <a name="vulnerabilities-in-global-search"></a><span data-ttu-id="e3c58-123">Beveiligingslekken in globale zoekopdrachten</span><span class="sxs-lookup"><span data-stu-id="e3c58-123">Vulnerabilities in global search</span></span>

1. <span data-ttu-id="e3c58-124">Ga naar de vervolgkeuzelijst Voor algemene zoekopdrachten.</span><span class="sxs-lookup"><span data-stu-id="e3c58-124">Go to the global search drop-down menu.</span></span>
2. <span data-ttu-id="e3c58-125">Selecteer **Kwetsbaarheid** en selecteer de CVE-id (Common Vulnerabilities and Exposures) die u zoekt en selecteer vervolgens het zoekpictogram.</span><span class="sxs-lookup"><span data-stu-id="e3c58-125">Select **Vulnerability** and key-in the Common Vulnerabilities and Exposures (CVE) ID that you're looking for, then select the search icon.</span></span> <span data-ttu-id="e3c58-126">De **pagina Zwakheden** wordt geopend met de CVE-informatie die u zoekt.</span><span class="sxs-lookup"><span data-stu-id="e3c58-126">The **Weaknesses** page opens with the CVE information that you're looking for.</span></span>
<span data-ttu-id="e3c58-127">![Algemeen zoekvak met de vervolgkeuzeoptie 'kwetsbaarheid' geselecteerd en een voorbeeld CVE.](images/tvm-vuln-globalsearch.png)</span><span class="sxs-lookup"><span data-stu-id="e3c58-127">![Global search box with the dropdown option "vulnerability" selected and an example CVE.](images/tvm-vuln-globalsearch.png)</span></span>
3. <span data-ttu-id="e3c58-128">Selecteer de CVE om een flyout-paneel te openen met meer informatie, zoals de beschrijving van de kwetsbaarheid, details, bedreigingsinzichten en blootgestelde apparaten.</span><span class="sxs-lookup"><span data-stu-id="e3c58-128">Select the CVE to open a flyout panel with more information, including the vulnerability description, details, threat insights, and exposed devices.</span></span>

<span data-ttu-id="e3c58-129">Als u de rest van de beveiligingslekken op de pagina **Zwakke** punten wilt zien, typt u CVE en selecteert u zoeken.</span><span class="sxs-lookup"><span data-stu-id="e3c58-129">To see the rest of the vulnerabilities in the **Weaknesses** page, type CVE, then select search.</span></span>

## <a name="weaknesses-overview"></a><span data-ttu-id="e3c58-130">Overzicht van zwakke punten</span><span class="sxs-lookup"><span data-stu-id="e3c58-130">Weaknesses overview</span></span>

<span data-ttu-id="e3c58-131">Herstel de beveiligingslekken in blootgestelde apparaten om het risico voor uw activa en organisatie te beperken.</span><span class="sxs-lookup"><span data-stu-id="e3c58-131">Remediate the vulnerabilities in exposed devices to reduce the risk to your assets and organization.</span></span> <span data-ttu-id="e3c58-132">Als in **de kolom Blootgestelde** apparaten 0 wordt getoond, betekent dit dat u geen risico loopt.</span><span class="sxs-lookup"><span data-stu-id="e3c58-132">If the **Exposed Devices** column shows 0, that means you aren't at risk.</span></span>

![Zwakke landingspagina.](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a><span data-ttu-id="e3c58-134">Inzichten in inbreuken en bedreigingen</span><span class="sxs-lookup"><span data-stu-id="e3c58-134">Breach and threat insights</span></span>

<span data-ttu-id="e3c58-135">Bekijk eventuele gerelateerde inbreuk- en bedreigingsinzichten in de kolom **Bedreiging** wanneer de pictogrammen rood zijn gekleurd.</span><span class="sxs-lookup"><span data-stu-id="e3c58-135">View any related breach and threat insights in the **Threat** column when the icons are colored red.</span></span>

 >[!NOTE]
 > <span data-ttu-id="e3c58-136">Geef altijd prioriteit aan aanbevelingen die zijn gekoppeld aan lopende bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="e3c58-136">Always prioritize recommendations that are associated with ongoing threats.</span></span> <span data-ttu-id="e3c58-137">Deze aanbevelingen zijn gemarkeerd met het pictogram Bedreigingsinzicht ![ Eenvoudige tekening van een rode bug.](images/tvm_bug_icon.png)</span><span class="sxs-lookup"><span data-stu-id="e3c58-137">These recommendations are marked with the threat insight icon ![Simple drawing of a red bug.](images/tvm_bug_icon.png)</span></span> <span data-ttu-id="e3c58-138">en inzichtspictogram inbreuk ![ maken Eenvoudige tekening van een pijl die een doel ](images/tvm_alert_icon.png) raakt. .</span><span class="sxs-lookup"><span data-stu-id="e3c58-138">and breach insight icon ![Simple drawing of an arrow hitting a target.](images/tvm_alert_icon.png).</span></span>  

<span data-ttu-id="e3c58-139">Het pictogram Inbreukinzichten wordt gemarkeerd als er een beveiligingsprobleem is gevonden in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e3c58-139">The breach insights icon is highlighted if there's a vulnerability found in your organization.</span></span>
<span data-ttu-id="e3c58-140">![Voorbeeld van een inbreukinzichten in tekst die kan worden weergegeven wanneer u de muisaanwijzer op het pictogram plaats.</span><span class="sxs-lookup"><span data-stu-id="e3c58-140">![Example of a breach insights text that could show up when hovering over icon.</span></span> <span data-ttu-id="e3c58-141">Deze geeft aan dat 'mogelijke actieve waarschuwing is gekoppeld aan deze aanbeveling.](images/tvm-breach-insights.png)</span><span class="sxs-lookup"><span data-stu-id="e3c58-141">This one says "possible active alert is associated with this recommendation.](images/tvm-breach-insights.png)</span></span>

<span data-ttu-id="e3c58-142">Het pictogram Bedreigingsinzichten wordt gemarkeerd als er gekoppelde exploits zijn in de kwetsbaarheid die in uw organisatie wordt gevonden.</span><span class="sxs-lookup"><span data-stu-id="e3c58-142">The threat insights icon is highlighted if there are associated exploits in the vulnerability found in your organization.</span></span> <span data-ttu-id="e3c58-143">Wanneer u de muisaanwijzer boven het pictogram houdt, wordt weergegeven of de bedreiging deel uitmaakt van een exploitkit of verbonden is met specifieke geavanceerde permanente campagnes of activiteitsgroepen.</span><span class="sxs-lookup"><span data-stu-id="e3c58-143">Hovering over the icon shows whether the threat is a part of an exploit kit, or connected to specific advanced persistent campaigns or activity groups.</span></span> <span data-ttu-id="e3c58-144">Wanneer deze beschikbaar zijn, is er een koppeling naar een Threat Analytics-rapport met zero-day misbruiknieuws, openbaarmakingen of gerelateerde beveiligingsadviseurs.</span><span class="sxs-lookup"><span data-stu-id="e3c58-144">When available, there's a link to a Threat Analytics report with zero-day exploitation news, disclosures, or related security advisories.</span></span>  

![Threat insights text that that could show up when hovering over icon.](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a><span data-ttu-id="e3c58-147">Inzicht krijgen in kwetsbaarheid</span><span class="sxs-lookup"><span data-stu-id="e3c58-147">Gain vulnerability insights</span></span>

<span data-ttu-id="e3c58-148">Als u een CVE selecteert, wordt er een flyoutvenster geopend met meer informatie, zoals de beschrijving van de kwetsbaarheid, details, bedreigingsinzichten en blootgestelde apparaten.</span><span class="sxs-lookup"><span data-stu-id="e3c58-148">If you select a CVE, a flyout panel will open with more information such as the vulnerability description, details, threat insights, and exposed devices.</span></span>

- <span data-ttu-id="e3c58-149">De categorie 'OS-functie' wordt weergegeven in relevante scenario's</span><span class="sxs-lookup"><span data-stu-id="e3c58-149">The "OS Feature" category is shown in relevant scenarios</span></span>
- <span data-ttu-id="e3c58-150">U kunt naar de bijbehorende beveiligingsaanbeveling voor elke CVE met een blootgesteld apparaat gaan</span><span class="sxs-lookup"><span data-stu-id="e3c58-150">You can go to the related security recommendation for every CVE with exposed device</span></span>

 ![Voorbeeld van een zwakke flyout.](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a><span data-ttu-id="e3c58-152">Software die niet wordt ondersteund</span><span class="sxs-lookup"><span data-stu-id="e3c58-152">Software that isn't supported</span></span>

<span data-ttu-id="e3c58-153">CVE's voor software die momenteel niet wordt ondersteund door & kwetsbaarheidsbeheer is nog steeds aanwezig op de pagina Zwakke punten.</span><span class="sxs-lookup"><span data-stu-id="e3c58-153">CVEs for software that isn't currently supported by threat & vulnerability management is still present in the Weaknesses page.</span></span> <span data-ttu-id="e3c58-154">Omdat de software niet wordt ondersteund, zijn er slechts beperkte gegevens beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e3c58-154">Because the software is not supported, only limited data will be available.</span></span>

<span data-ttu-id="e3c58-155">Blootgestelde apparaatgegevens zijn niet beschikbaar voor CVE's met niet-ondersteunde software.</span><span class="sxs-lookup"><span data-stu-id="e3c58-155">Exposed device information will not be available for CVEs with unsupported software.</span></span> <span data-ttu-id="e3c58-156">Filter op niet-ondersteunde software door de optie 'Niet beschikbaar' te selecteren in de sectie 'Blootgestelde apparaten'.</span><span class="sxs-lookup"><span data-stu-id="e3c58-156">Filter by unsupported software by selecting the "Not available" option in the "Exposed devices" section.</span></span>

 ![Blootgestelde apparaten filteren.](images/tvm-exposed-devices-filter.png)

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a><span data-ttu-id="e3c58-158">CvE-vermeldingen (Common Vulnerabilities and Exposures) weergeven op andere plaatsen</span><span class="sxs-lookup"><span data-stu-id="e3c58-158">View Common Vulnerabilities and Exposures (CVE) entries in other places</span></span>

### <a name="top-vulnerable-software-in-the-dashboard"></a><span data-ttu-id="e3c58-159">Meest kwetsbare software in het dashboard</span><span class="sxs-lookup"><span data-stu-id="e3c58-159">Top vulnerable software in the dashboard</span></span>

1. <span data-ttu-id="e3c58-160">Ga naar het [dashboard bedreigings- en kwetsbaarheidsbeheer](tvm-dashboard-insights.md) en schuif omlaag naar de widget Top vulnerable **software.**</span><span class="sxs-lookup"><span data-stu-id="e3c58-160">Go to the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) and scroll down to the **Top vulnerable software** widget.</span></span> <span data-ttu-id="e3c58-161">U ziet het aantal beveiligingsproblemen in elke software, samen met bedreigingsgegevens en een weergave op hoog niveau van blootstelling aan apparaten in de tijd.</span><span class="sxs-lookup"><span data-stu-id="e3c58-161">You will see the number of vulnerabilities found in each software, along with threat information and a high-level view of device exposure over time.</span></span>

    ![Top kwetsbaar softwarekaart met vier kolommen: software, zwakke punten, bedreigingen, blootgestelde apparaten.](images/tvm-top-vulnerable-software500.png)

2. <span data-ttu-id="e3c58-163">Selecteer de software die u wilt onderzoeken om naar een inzoompagina te gaan.</span><span class="sxs-lookup"><span data-stu-id="e3c58-163">Select the software you want to investigate to go to a drilldown page.</span></span>
3. <span data-ttu-id="e3c58-164">Selecteer het **tabblad Gevonden beveiligingslekken.**</span><span class="sxs-lookup"><span data-stu-id="e3c58-164">Select the **Discovered vulnerabilities** tab.</span></span>
4. <span data-ttu-id="e3c58-165">Selecteer het beveiligingsprobleem dat u wilt onderzoeken voor meer informatie over beveiligingsdetails</span><span class="sxs-lookup"><span data-stu-id="e3c58-165">Select the vulnerability you want to investigate for more information on vulnerability details</span></span>

    ![Overzicht van Windows Server 2019 inzoomen.](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a><span data-ttu-id="e3c58-167">Beveiligingslekken ontdekken op de apparaatpagina</span><span class="sxs-lookup"><span data-stu-id="e3c58-167">Discover vulnerabilities in the device page</span></span>

<span data-ttu-id="e3c58-168">Informatie over gerelateerde zwakke punten weergeven op de apparaatpagina.</span><span class="sxs-lookup"><span data-stu-id="e3c58-168">View related weaknesses information in the device page.</span></span>

1. <span data-ttu-id="e3c58-169">Ga naar de navigatiemenubalk van het Microsoft Defender-beveiligingscentrum en selecteer vervolgens het apparaatpictogram.</span><span class="sxs-lookup"><span data-stu-id="e3c58-169">Go to the Microsoft Defender Security Center navigation menu bar, then select the device icon.</span></span> <span data-ttu-id="e3c58-170">De **lijstpagina Apparaten** wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="e3c58-170">The **Devices list** page opens.</span></span>
2. <span data-ttu-id="e3c58-171">Selecteer op **de pagina Apparatenlijst** de apparaatnaam die u wilt onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="e3c58-171">In the **Devices list** page, select the device name that you want to investigate.</span></span>

    ![Apparaatlijst met geselecteerd apparaat om te onderzoeken.](images/tvm_machinetoinvestigate.png)

3. <span data-ttu-id="e3c58-173">De apparaatpagina wordt geopend met details en antwoordopties voor het apparaat dat u wilt onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="e3c58-173">The device page will open with details and response options for the device you want to investigate.</span></span>
4. <span data-ttu-id="e3c58-174">Selecteer **Gevonden beveiligingslekken.**</span><span class="sxs-lookup"><span data-stu-id="e3c58-174">Select **Discovered vulnerabilities**.</span></span>

    ![Apparaatpagina met details en antwoordopties.](images/tvm-discovered-vulnerabilities.png)

5. <span data-ttu-id="e3c58-176">Selecteer het beveiligingsprobleem dat u wilt onderzoeken om een flyoutvenster te openen met de CVE-details, zoals: beschrijving van kwetsbaarheid, bedreigingsinzichten en detectielogica.</span><span class="sxs-lookup"><span data-stu-id="e3c58-176">Select the vulnerability that you want to investigate to open up a flyout panel with the CVE details, such as: vulnerability description, threat insights, and detection logic.</span></span>

#### <a name="cve-detection-logic"></a><span data-ttu-id="e3c58-177">CVE-detectielogica</span><span class="sxs-lookup"><span data-stu-id="e3c58-177">CVE Detection logic</span></span>

<span data-ttu-id="e3c58-178">Net als bij de software wordt nu de detectielogica we toegepast op een apparaat om aan te geven dat het kwetsbaar is.</span><span class="sxs-lookup"><span data-stu-id="e3c58-178">Similar to the software evidence, we now show the detection logic we applied on a device in order to state that it's vulnerable.</span></span> <span data-ttu-id="e3c58-179">De nieuwe sectie heet 'Detectielogica' (in een gedetecteerd beveiligingsprobleem op de apparaatpagina) en toont de detectielogica en -bron.</span><span class="sxs-lookup"><span data-stu-id="e3c58-179">The new section is called "Detection Logic" (in any discovered vulnerability in the device page) and shows the detection logic and source.</span></span>

<span data-ttu-id="e3c58-180">De categorie 'OS-functie' wordt ook weergegeven in relevante scenario's.</span><span class="sxs-lookup"><span data-stu-id="e3c58-180">The "OS Feature" category is also shown in relevant scenarios.</span></span> <span data-ttu-id="e3c58-181">Een CVE is alleen van invloed op apparaten met een kwetsbaar besturingssysteem als een specifiek besturingssysteemonderdeel is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e3c58-181">A CVE would affect devices that run a vulnerable OS only if a specific OS component is enabled.</span></span> <span data-ttu-id="e3c58-182">Stel dat Windows Server 2019 een kwetsbaarheid heeft in het DNS-onderdeel.</span><span class="sxs-lookup"><span data-stu-id="e3c58-182">Let's say Windows Server 2019 has vulnerability in its DNS component.</span></span> <span data-ttu-id="e3c58-183">Met deze nieuwe mogelijkheid voegen we deze CVE alleen toe aan de Windows Server 2019-apparaten met de DNS-mogelijkheid die is ingeschakeld in het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="e3c58-183">With this new capability, we’ll only attach this CVE to the Windows Server 2019 devices with the DNS capability enabled in their OS.</span></span>

![Voorbeeld van detectielogica waarin de software wordt vermeld die is gedetecteerd op het apparaat en de KBs.](images/tvm-cve-detection-logic.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="e3c58-185">Onnauwkeurigheid van rapport</span><span class="sxs-lookup"><span data-stu-id="e3c58-185">Report inaccuracy</span></span>

<span data-ttu-id="e3c58-186">Meld een onwaar positief wanneer u vage, onnauwkeurige of onvolledige informatie ziet.</span><span class="sxs-lookup"><span data-stu-id="e3c58-186">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="e3c58-187">U kunt ook rapporteren over beveiligingsaanbevelingen die al zijn gesaneerd.</span><span class="sxs-lookup"><span data-stu-id="e3c58-187">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="e3c58-188">Open de CVE op de pagina Zwakke punten.</span><span class="sxs-lookup"><span data-stu-id="e3c58-188">Open the CVE on the Weaknesses page.</span></span>
2. <span data-ttu-id="e3c58-189">Selecteer **Onnauwkeurigheid melden en** er wordt een flyoutvenster geopend.</span><span class="sxs-lookup"><span data-stu-id="e3c58-189">Select **Report inaccuracy** and a flyout pane will open.</span></span>
3. <span data-ttu-id="e3c58-190">Selecteer de onnauwkeurigheidscategorie in de vervolgkeuzelijst en vul uw e-mailadres en onnauwkeurigheidsdetails in.</span><span class="sxs-lookup"><span data-stu-id="e3c58-190">Select the inaccuracy category from the drop-down menu and fill in your email address and inaccuracy details.</span></span>
4. <span data-ttu-id="e3c58-191">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="e3c58-191">Select **Submit**.</span></span> <span data-ttu-id="e3c58-192">Uw feedback wordt onmiddellijk verzonden naar de experts voor bedreigings- en kwetsbaarheidsbeheer.</span><span class="sxs-lookup"><span data-stu-id="e3c58-192">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e3c58-193">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="e3c58-193">Related articles</span></span>

- [<span data-ttu-id="e3c58-194">Overzicht van bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="e3c58-194">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e3c58-195">Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="e3c58-195">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="e3c58-196">Software-inventaris</span><span class="sxs-lookup"><span data-stu-id="e3c58-196">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="e3c58-197">Dashboardinzichten</span><span class="sxs-lookup"><span data-stu-id="e3c58-197">Dashboard insights</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="e3c58-198">De lijst Met Microsoft Defender voor eindpuntapparaten weergeven en organiseren</span><span class="sxs-lookup"><span data-stu-id="e3c58-198">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
