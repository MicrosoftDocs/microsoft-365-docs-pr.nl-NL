---
title: Apparaat-proxy en instellingen voor internetverbinding voor Endpoint DLP configureren.
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Apparaat-proxy en instellingen voor internetverbinding voor Endpoint DLP configureren.
ms.openlocfilehash: f2a62b5c7913b6f41c414310a97ab5f072f59642
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538613"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-endpoint-dlp"></a><span data-ttu-id="a7069-103">Apparaat-proxy en instellingen voor internetverbinding voor Endpoint DLP configureren.</span><span class="sxs-lookup"><span data-stu-id="a7069-103">Configure device proxy and internet connection settings for Endpoint DLP</span></span>

<span data-ttu-id="a7069-104">Microsoft Endpoint DLP gebruikt Microsoft Windows HTTP (WinHTTP) om gegevens te rapporteren en te communiceren met de cloudservice voor Microsoft-eindpunten.</span><span class="sxs-lookup"><span data-stu-id="a7069-104">Microsoft Endpoint DLP uses Microsoft Windows HTTP (WinHTTP) to report data and communicate with the Microsoft endpoint cloud service.</span></span> <span data-ttu-id="a7069-105">De ingesloten Endpoint DLP wordt in de systeemcontext uitgevoerd met het LocalSystem-account.</span><span class="sxs-lookup"><span data-stu-id="a7069-105">The embedded Endpoint DLP runs in system context using the LocalSystem account.</span></span>

> [!TIP]
> <span data-ttu-id="a7069-106">Organisaties die forward proxy's gebruiken als gateway voor internet, kunt netwerkbeveiliging gebruiken om een proxy te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="a7069-106">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="a7069-107">Zie [Verbindingsgebeurtenissen achter forward proxy's onderzoeken](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a7069-107">For more information, see [Investigate connection events that occur behind forward proxies](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span></span>

<span data-ttu-id="a7069-108">De configuratie-instelling WinHTTP is onafhankelijk van de internetbrowserproxy-instellingen voor Windows Internet (WinINet) en kan alleen een proxyserver vinden met behulp van de volgende methoden voor automatische detectie:</span><span class="sxs-lookup"><span data-stu-id="a7069-108">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following auto discovery methods:</span></span>

- <span data-ttu-id="a7069-109">Transparante proxy</span><span class="sxs-lookup"><span data-stu-id="a7069-109">Transparent proxy</span></span>
- <span data-ttu-id="a7069-110">WPAD (Web Proxy Auto Discovery Protocol)</span><span class="sxs-lookup"><span data-stu-id="a7069-110">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

> [!NOTE]
> <span data-ttu-id="a7069-111">Als u transparante proxy of WPAD gebruikt in uw netwerktopologie, hebt u geen speciale configuratie-instellingen nodig.</span><span class="sxs-lookup"><span data-stu-id="a7069-111">If you’re using Transparent proxy or WPAD in your network topology, you don’t need special configuration settings.</span></span> <span data-ttu-id="a7069-112">Zie [Enable access to Endpoint DLP cloud service URLLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server)(Toegang tot URL's van DLP-cloudservice voor eindpunten in de proxyserver inschakelen) voor meer informatie over uitsluitingen van URL's van Defender voor eindpunten in de proxyserver.</span><span class="sxs-lookup"><span data-stu-id="a7069-112">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="a7069-113">Hnadmatige statische proxyconfiguratie</span><span class="sxs-lookup"><span data-stu-id="a7069-113">Manual static proxy configuration:</span></span>
    - <span data-ttu-id="a7069-114">Configuratie op basis van register</span><span class="sxs-lookup"><span data-stu-id="a7069-114">Registry-based configuration</span></span>
    - <span data-ttu-id="a7069-115">WinHTTP geconfigureerd met de Netsh-opdracht– Alleen geschikt voor desktops in een stabiele topologie (bijvoorbeeld: een bureaublad in een bedrijfsnetwerk achter dezelfde proxy)</span><span class="sxs-lookup"><span data-stu-id="a7069-115">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="a7069-116">De proxyserver handmatig configureren met een statische proxy op basis van het register</span><span class="sxs-lookup"><span data-stu-id="a7069-116">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="a7069-117">Voor eindpuntapparaten die geen verbinding mogen maken met internet, moet u een statische proxy op basis van het register configureren.</span><span class="sxs-lookup"><span data-stu-id="a7069-117">For endpoint devices that aren't permitted to connect to the Internet, you need to configure a registry-based static proxy.</span></span> <span data-ttu-id="a7069-118">U moet dit zo configureren dat alleen Microsoft Endpoint DLP diagnostische gegevens kan rapporteren en kan communiceren met de cloudservice van Microsoft-eindpunt.</span><span class="sxs-lookup"><span data-stu-id="a7069-118">You need to configure this to allow only Microsoft Endpoint DLP to report diagnostic data and communicate with Microsoft endpoint cloud service.</span></span>

<span data-ttu-id="a7069-119">De statische proxy kan worden geconfigureerd via Group Policy (GP).</span><span class="sxs-lookup"><span data-stu-id="a7069-119">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="a7069-120">U vindt het groepsbeleid onder:</span><span class="sxs-lookup"><span data-stu-id="a7069-120">The group policy can be found under:</span></span>

1. <span data-ttu-id="a7069-121">Open **Veheersjablonen > Windows Components > Gegevensverzameling en Voorbeeldversies > Geverifieerd proxygebruik configureren voor de verbonden gebruikerservaring en telemetrieservice**</span><span class="sxs-lookup"><span data-stu-id="a7069-121">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

2. <span data-ttu-id="a7069-122">Stel deze in op **ingeschakelde** selecteer **Het gebruik van geverifieerde proxy uitschakelen**:</span><span class="sxs-lookup"><span data-stu-id="a7069-122">Set it to **Enabled** and select **Disable Authenticated Proxy usage**:</span></span> 

![Afbeelding van groepsbeleidsinstellingen 1](../media/atp-gpo-proxy1.png)
 
3. <span data-ttu-id="a7069-124">Open **Veheersjablonen > Windows Components > Gegevensverzameling en Voorbeeldversies > Verbonden gebruikerservaringen en telemetrie configureren**:</span><span class="sxs-lookup"><span data-stu-id="a7069-124">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

 <span data-ttu-id="a7069-125">De peoxy configureren</span><span class="sxs-lookup"><span data-stu-id="a7069-125">Configure the proxy</span></span>

![Afbeelding van groepsbeleidsinstellingen 2](../media/atp-gpo-proxy2.png)

<span data-ttu-id="a7069-127">Met het beleid worden twee registerwaarden `TelemetryProxyServer` als REG_SZ ingesteld en wordt `DisableEnterpriseAuthProxy` als REG_DWORD ingesteld onder de registersleutel `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span><span class="sxs-lookup"><span data-stu-id="a7069-127">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="a7069-128">De registerwaarde TelemetryProxyServer heeft deze indeling \<server name or ip\>:\<port\>.</span><span class="sxs-lookup"><span data-stu-id="a7069-128">The registry value TelemetryProxyServer is in this format \<server name or ip\>:\<port\>.</span></span> <span data-ttu-id="a7069-129">Bijvoorbeeld: **10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="a7069-129">For example: **10.0.0.6:8080**</span></span>

<span data-ttu-id="a7069-130">De registerwaarde `DisableEnterpriseAuthProxy` moet worden ingesteld op 1.</span><span class="sxs-lookup"><span data-stu-id="a7069-130">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="a7069-131">De proxyserver handmatig configureren met de opdracht 'Netsh'</span><span class="sxs-lookup"><span data-stu-id="a7069-131">Configure the proxy server manually using "netsh" command</span></span>

<span data-ttu-id="a7069-132">Gebruik netsh om een statische proxy voor het hele systeem te configureren.</span><span class="sxs-lookup"><span data-stu-id="a7069-132">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> <span data-ttu-id="a7069-133">Dit is van invloed op alle toepassingen, inclusief Windows-services die WinHTTP met standaardproxy gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a7069-133">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span> <span data-ttu-id="a7069-134">- Laptops die van topologie veranderen (bijvoorbeeld van kantoor naar thuis) werken niet goed met netsh.</span><span class="sxs-lookup"><span data-stu-id="a7069-134">- Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="a7069-135">Gebruik de statische proxyconfiguratie op basis van het register.</span><span class="sxs-lookup"><span data-stu-id="a7069-135">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="a7069-136">Open een opdrachtpromptregel met verhoogde bevoegdheid.</span><span class="sxs-lookup"><span data-stu-id="a7069-136">Open an elevated command line:</span></span>
    1. <span data-ttu-id="a7069-137">Go to **Start** and type **cmd**</span><span class="sxs-lookup"><span data-stu-id="a7069-137">Go to **Start** and type **cmd**</span></span>
    1. <span data-ttu-id="a7069-138">Klik met de rechtermuisknop op **Opdrachtprompt** en selecteer **Als beheerder uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="a7069-138">Right-click **Command prompt** and select **Run as administrator**.</span></span>
2.  <span data-ttu-id="a7069-139">Voer de volgende opdracht in en druk op **Enter**:</span><span class="sxs-lookup"><span data-stu-id="a7069-139">Enter the following command and press **Enter**:</span></span>

    `netsh winhttp set proxy <proxy>:<port>`

    <span data-ttu-id="a7069-140">Bijvoorbeeld: **netsh winhttp set proxy 10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="a7069-140">For example: **netsh winhttp set proxy 10.0.0.6:8080**</span></span>

3. <span data-ttu-id="a7069-141">Voer de volgende opdracht in en druk op **Enter** om de winhttp proxy opnieuw in te stellen:</span><span class="sxs-lookup"><span data-stu-id="a7069-141">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

     `netsh winhttp reset proxy`

<span data-ttu-id="a7069-142">Zie [Syntaxis, contexten en opmaak van Netsh](/windows-server/networking/technologies/netsh/netsh-contexts) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a7069-142">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>


## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a><span data-ttu-id="a7069-143">Toegang tot URL's van de DLP-cloudservice voor eindpunten inschakelen op de proxyserver</span><span class="sxs-lookup"><span data-stu-id="a7069-143">Enable access to Endpoint DLP cloud service URLs in the proxy server</span></span>

<span data-ttu-id="a7069-144">Als door een proxy of firewall standaard al het verkeer wordt geblokkeerd en alleen bepaalde domeinen worden toegestaan, voegt u de domeinen die worden vermeld in het downloadbare blad toe aan de lijst met toegestane domeinen.</span><span class="sxs-lookup"><span data-stu-id="a7069-144">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="a7069-145">Dit [downloadbare werkblad](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) bevat services en de bijbehorende URL's waar uw netwerk verbinding mee moet kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="a7069-145">This [downloadable spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="a7069-146">Zorg ervoor dat er geen firewall- of netwerkfilterregels zijn die toegang tot deze URL's weigeren of u moet mogelijk een specifieke toegangsregel maken.</span><span class="sxs-lookup"><span data-stu-id="a7069-146">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an allow rule specifically for them.</span></span>

<span data-ttu-id="a7069-147">Als https-scannen (SSL-controle) is ingeschakeld voor een proxy of firewall, moet u de domeinen in de bovenstaande tabel uitsluiten van HTTPS-scannen.</span><span class="sxs-lookup"><span data-stu-id="a7069-147">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>
<span data-ttu-id="a7069-148">Als een proxy of firewall anoniem verkeer blokkeert, aangezien Eindpunt DLP verbinding maakt vanuit de systeemcontext, zorg er dan voor dat anoniem verkeer is toegestaan in de eerder vermelde URL's.</span><span class="sxs-lookup"><span data-stu-id="a7069-148">If a proxy or firewall is blocking anonymous traffic, as Endpoint DLP is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a><span data-ttu-id="a7069-149">Clientconnectiviteit met URL's voor Microsoft-cloudservices verifiëren</span><span class="sxs-lookup"><span data-stu-id="a7069-149">Verify client connectivity to Microsoft cloud service URLs</span></span>

<span data-ttu-id="a7069-150">Controleer of de proxyconfiguratie is voltooid, of WinHTTP de proxyserver in uw omgeving kan vinden en communiceren, en of via de proxyserver verkeer wordt toegestaan naar de URL's van de Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="a7069-150">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="a7069-151">Download het hulpprogramma [MDATP Client Analyzer](https://aka.ms/mdatpanalyzer) naar de pc waarop Endpoint DLP wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a7069-151">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Endpoint DLP is running on.</span></span>
2. <span data-ttu-id="a7069-152">Pak de inhoud van MDATPClientAnalyzer.zip uit op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a7069-152">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>
3. <span data-ttu-id="a7069-153">Open een opdrachtpromptregel met verhoogde bevoegdheid:</span><span class="sxs-lookup"><span data-stu-id="a7069-153">Open an elevated command line:</span></span>
    1. <span data-ttu-id="a7069-154">Go to **Start** and type **cmd**.</span><span class="sxs-lookup"><span data-stu-id="a7069-154">Go to **Start** and type **cmd**.</span></span>
    1. <span data-ttu-id="a7069-155">Klik met de rechtermuisknop op **Opdrachtprompt** en selecteer **Als beheerder uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="a7069-155">Right-click **Command prompt** and select **Run as administrator**.</span></span>
4.  <span data-ttu-id="a7069-156">Voer de volgende opdracht in en druk op **Enter**:</span><span class="sxs-lookup"><span data-stu-id="a7069-156">Enter the following command and press **Enter**:</span></span>
    
`HardDrivePath\MDATPClientAnalyzer.cmd`

<span data-ttu-id="a7069-157">Vervang *HardDrivePath* door het pad waar bijvoorbeeld het hulpprogramma MDATPClientAnalyzer is gedownload</span><span class="sxs-lookup"><span data-stu-id="a7069-157">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>
    
<span data-ttu-id="a7069-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span><span class="sxs-lookup"><span data-stu-id="a7069-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span></span>


5.  <span data-ttu-id="a7069-159">Pak het bestand **MDATPClientAnalyzerResult.zip** dat is aangemaakt door de tool in de map die gebruikt wordt in de _HardDrivePath\*.</span><span class="sxs-lookup"><span data-stu-id="a7069-159">Extract the **MDATPClientAnalyzerResult.zip** _ file created by tool in the folder used in the _HardDrivePath\*.</span></span>

6.  <span data-ttu-id="a7069-160">Open **MDATPClientAnalyzerResult.txt** en controleer of u de configuratiestappen voor de proxy hebt uitgevoerd om serverdetectie en toegang tot de service-URL's in te stellen.</span><span class="sxs-lookup"><span data-stu-id="a7069-160">Open **MDATPClientAnalyzerResult.txt** and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>  <span data-ttu-id="a7069-161">Het hulpprogramma controleert de verbindingen van URL's van Defender voor Endpoint-service die voor Defender voor Endpoint-client zijn geconfigureerd voor interactie.</span><span class="sxs-lookup"><span data-stu-id="a7069-161">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="a7069-162">Vervolgens worden de resultaten afgedrukt in het bestand **MDATPClientAnalyzerResult.txt** voor elke URL die mogelijk kan worden gebruikt voor communicatie met Defender voor Endpoint-services.</span><span class="sxs-lookup"><span data-stu-id="a7069-162">It then prints the results into the **MDATPClientAnalyzerResult.txt** file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="a7069-163">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="a7069-163">For example:</span></span>

    <span data-ttu-id="a7069-164">**Test-URL: https://xxx.microsoft.com/xxx </br> 1 - standaardproxy: Geslaagd (200) </br> 2 - Proxy Auto Discovery (WPAD): Geslaagd (200)</br> 3 - Proxy uitgeschakeld: Geslaagd (200)</br> 4 - Benoemde proxy: bestaat niet</br> 5 - Opdrachtregelproxy: bestaat niet**</span><span class="sxs-lookup"><span data-stu-id="a7069-164">**Testing URL: https://xxx.microsoft.com/xxx </br> 1 - Default proxy: Succeeded (200) </br> 2 - Proxy auto discovery (WPAD): Succeeded (200)</br> 3 - Proxy disabled: Succeeded (200)</br> 4 - Named proxy: Doesn't exist</br> 5 - Command-line proxy: Doesn't exist**</span></span></br>


<span data-ttu-id="a7069-165">Als minimaal één van de connectiviteitsopties een status (200) retourneert, kan de Defender voor Endpoint-client met deze connectiviteitsmethode correct communiceren met de geteste URL.</span><span class="sxs-lookup"><span data-stu-id="a7069-165">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> 

<span data-ttu-id="a7069-166">Als de resultaten van de connectiviteitscontrole echter aangeven dat er een fout is, wordt een HTTP-fout weergegeven (zie HTTP-statuscodes).</span><span class="sxs-lookup"><span data-stu-id="a7069-166">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="a7069-167">Vervolgens kunt u de URL's gebruiken in de tabel die wordt weergegeven in [Toegang tot URL's van de service voor DLP-cloudservices voor eindpunten inschakelen in de proxyserver](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="a7069-167">You can then use the URLs in the table shown in [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="a7069-168">De URL's die u gebruikt, zijn afhankelijk van de regio die is geselecteerd tijdens de onboardingprocedure.</span><span class="sxs-lookup"><span data-stu-id="a7069-168">The URLs you’ll use will depend on the region selected during the onboarding procedure.</span></span>
[!NOTE]<span data-ttu-id="a7069-169"> Het hulpprogramma Connectivity Analyzer is niet compatibel met ASR-regel [Creaties van proces afkomstig van de PSExec- en WMI-opdrachten blokkeren](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="a7069-169"> The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="a7069-170">U moet deze regel tijdelijk uitschakelen om het hulpprogramma voor connectiviteit uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="a7069-170">You will need to temporarily disable this rule to run the connectivity tool.</span></span>

[!NOTE] <span data-ttu-id="a7069-171">Wanneer de TelemetryProxyServer is ingesteld, in het register of via groepsbeleid, valt Defender for Endpoint terug naar direct als het geen toegang heeft tot de gedefinieerde proxy.</span><span class="sxs-lookup"><span data-stu-id="a7069-171">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can’t access the defined proxy.</span></span>
<span data-ttu-id="a7069-172">Verwante onderwerpen • Windows 10-apparaten in onboarden • Problemen met de onboarding van Microsoft Endpoint DLP oplossen</span><span class="sxs-lookup"><span data-stu-id="a7069-172">Related topics •   Onboard Windows 10 devices •   Troubleshoot Microsoft Endpoint DLP onboarding issues</span></span>





## <a name="see-also"></a><span data-ttu-id="a7069-173">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a7069-173">See also</span></span>

- [<span data-ttu-id="a7069-174">Meer informatie over Preventie van gegevensverlies voor eindpunten</span><span class="sxs-lookup"><span data-stu-id="a7069-174">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="a7069-175">Preventie van gegevensverlies voor eindpunten gebruiken</span><span class="sxs-lookup"><span data-stu-id="a7069-175">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="a7069-176">Meer informatie over preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="a7069-176">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="a7069-177">Een DLP-beleid maken, testen en afstemmen</span><span class="sxs-lookup"><span data-stu-id="a7069-177">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="a7069-178">Aan de slag met de activiteitenverkenner</span><span class="sxs-lookup"><span data-stu-id="a7069-178">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="a7069-179">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="a7069-179">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="a7069-180">Hulpmiddelen en methoden onboarden voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="a7069-180">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="a7069-181">Microsoft 365-abonnement</span><span class="sxs-lookup"><span data-stu-id="a7069-181">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="a7069-182">Azure AD-gekoppelde apparaten</span><span class="sxs-lookup"><span data-stu-id="a7069-182">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="a7069-183">De nieuwe Microsoft Edge op basis van Chromium downloaden</span><span class="sxs-lookup"><span data-stu-id="a7069-183">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)