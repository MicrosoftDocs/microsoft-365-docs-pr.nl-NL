---
title: Apparaatproxy- en internetverbindingsinstellingen configureren
description: Configureer de MICROSOFT Defender ATP-proxy en internetinstellingen om communicatie met de cloudservice in te stellen.
keywords: configureren, proxy, internet, internetverbinding, instellingen, proxy-instellingen, netsh, winhttp, proxyserver
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b529b1c7fa5c4f9f81cb6bfbb5f1a6bd7823a9ad
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587597"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="2a9c7-104">Instellingen voor apparaatproxy en internetverbinding configureren</span><span class="sxs-lookup"><span data-stu-id="2a9c7-104">Configure device proxy and Internet connectivity settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2a9c7-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2a9c7-105">**Applies to:**</span></span>
- [<span data-ttu-id="2a9c7-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="2a9c7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2a9c7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a9c7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2a9c7-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="2a9c7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2a9c7-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="2a9c7-110">Voor de Defender for Endpoint-sensor is Microsoft Windows HTTP (WinHTTP) vereist om sensorgegevens te rapporteren en te communiceren met de Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-110">The Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Defender for Endpoint service.</span></span>

<span data-ttu-id="2a9c7-111">De ingesloten Defender voor Eindpunt-sensor wordt uitgevoerd in systeemcontext met behulp van het LocalSystem-account.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-111">The embedded Defender for Endpoint sensor runs in system context using the LocalSystem account.</span></span> <span data-ttu-id="2a9c7-112">De sensor gebruikt Microsoft Windows HTTP Services (WinHTTP) om communicatie met de Defender for Endpoint-cloudservice mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-112">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Defender for Endpoint cloud service.</span></span>

>[!TIP]
><span data-ttu-id="2a9c7-113">Voor organisaties die doorgestuurde proxy's gebruiken als gateway voor internet, kunt u netwerkbeveiliging gebruiken om onderzoek te doen achter een proxy.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-113">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="2a9c7-114">Zie Verbindingsgebeurtenissen onderzoeken die [plaatsvinden achter forward proxies](investigate-behind-proxy.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-114">For more information, see [Investigate connection events that occur behind forward proxies](investigate-behind-proxy.md).</span></span>

<span data-ttu-id="2a9c7-115">De configuratie-instelling WinHTTP is onafhankelijk van de instellingen van Windows Internet (WinINet) voor internetbrowsingsproxy en kan alleen een proxyserver vinden met behulp van de volgende detectiemethoden:</span><span class="sxs-lookup"><span data-stu-id="2a9c7-115">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

- <span data-ttu-id="2a9c7-116">Methoden voor automatische detectie:</span><span class="sxs-lookup"><span data-stu-id="2a9c7-116">Auto-discovery methods:</span></span>
  - <span data-ttu-id="2a9c7-117">Transparante proxy</span><span class="sxs-lookup"><span data-stu-id="2a9c7-117">Transparent proxy</span></span>
  - <span data-ttu-id="2a9c7-118">Web proxy Auto-discovery Protocol (WPAD)</span><span class="sxs-lookup"><span data-stu-id="2a9c7-118">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

    > [!NOTE]
    > <span data-ttu-id="2a9c7-119">Als u Transparante proxy of WPAD gebruikt in de netwerktopologie, hebt u geen speciale configuratie-instellingen nodig.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-119">If you're using Transparent proxy or WPAD in your network topology, you don't need special configuration settings.</span></span> <span data-ttu-id="2a9c7-120">Zie Access [to Defender for Endpoint service URLLs in](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)de proxy inschakelen voor meer informatie over URL-uitsluitingen van Defender voor eindpunten in de proxy.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-120">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="2a9c7-121">Handmatige statische proxyconfiguratie:</span><span class="sxs-lookup"><span data-stu-id="2a9c7-121">Manual static proxy configuration:</span></span>
  - <span data-ttu-id="2a9c7-122">Configuratie op basis van register</span><span class="sxs-lookup"><span data-stu-id="2a9c7-122">Registry based configuration</span></span>
  - <span data-ttu-id="2a9c7-123">WinHTTP geconfigureerd met de opdracht Netsh: alleen geschikt voor desktops in een stabiele topologie (bijvoorbeeld: een bureaublad in een bedrijfsnetwerk achter dezelfde proxy)</span><span class="sxs-lookup"><span data-stu-id="2a9c7-123">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="2a9c7-124">De proxyserver handmatig configureren met behulp van een statische proxy op basis van het register</span><span class="sxs-lookup"><span data-stu-id="2a9c7-124">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="2a9c7-125">Configureer een statische proxy op basis van het register zodat alleen defender voor eindpunten-sensor diagnostische gegevens kan rapporteren en kan communiceren met Defender voor eindpuntservices als een computer geen verbinding mag maken met internet.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-125">Configure a registry-based static proxy to allow only Defender for Endpoint sensor to report diagnostic data and communicate with Defender for Endpoint services if a computer is not be permitted to connect to the Internet.</span></span>

<span data-ttu-id="2a9c7-126">De statische proxy kan worden geconfigureerd via Groepsbeleid (GP).</span><span class="sxs-lookup"><span data-stu-id="2a9c7-126">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="2a9c7-127">Het groepsbeleid vindt u onder:</span><span class="sxs-lookup"><span data-stu-id="2a9c7-127">The group policy can be found under:</span></span>

- <span data-ttu-id="2a9c7-128">Beheersjablonen > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span><span class="sxs-lookup"><span data-stu-id="2a9c7-128">Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
  - <span data-ttu-id="2a9c7-129">Stel deze optie **in op Ingeschakeld en** selecteer Geverifieerd **proxygebruik uitschakelen**: Afbeelding van ![ groepsbeleidsinstelling1](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="2a9c7-129">Set it to **Enabled** and select **Disable Authenticated Proxy usage**: ![Image of Group Policy setting1](images/atp-gpo-proxy1.png)</span></span>
- <span data-ttu-id="2a9c7-130">**Beheersjablonen > Windows-onderdelen > Gegevensverzameling en Preview-builds > Verbonden gebruikerservaringen en telemetrie configureren:**</span><span class="sxs-lookup"><span data-stu-id="2a9c7-130">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>
  - <span data-ttu-id="2a9c7-131">De proxy configureren:</span><span class="sxs-lookup"><span data-stu-id="2a9c7-131">Configure the proxy:</span></span><br>
    <span data-ttu-id="2a9c7-132">![Afbeelding van groepsbeleidsinstelling2](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="2a9c7-132">![Image of Group Policy setting2](images/atp-gpo-proxy2.png)</span></span>

    <span data-ttu-id="2a9c7-133">Met het beleid worden twee `TelemetryProxyServer` registerwaarden REG_SZ en `DisableEnterpriseAuthProxy` REG_DWORD onder de `HKLM\Software\Policies\Microsoft\Windows\DataCollection` registersleutel.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-133">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

    <span data-ttu-id="2a9c7-134">De registerwaarde `TelemetryProxyServer` heeft de volgende tekenreeksindeling:</span><span class="sxs-lookup"><span data-stu-id="2a9c7-134">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

    ```text
    <server name or ip>:<port>
    ```

    <span data-ttu-id="2a9c7-135">Bijvoorbeeld: 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="2a9c7-135">For example: 10.0.0.6:8080</span></span>

    <span data-ttu-id="2a9c7-136">De registerwaarde `DisableEnterpriseAuthProxy` moet worden ingesteld op 1.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-136">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="2a9c7-137">De proxyserver handmatig configureren met de opdracht Netsh</span><span class="sxs-lookup"><span data-stu-id="2a9c7-137">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="2a9c7-138">Gebruik netsh om een statische proxy voor het hele systeem te configureren.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-138">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="2a9c7-139">Dit is van invloed op alle toepassingen, inclusief Windows-services die WinHTTP met standaardproxy gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-139">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="2a9c7-140">Laptops die de topologie wijzigen (bijvoorbeeld van kantoor naar thuis) werken niet goed met netsh.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-140">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="2a9c7-141">Gebruik de statische proxyconfiguratie op basis van het register.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-141">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="2a9c7-142">Open een verhoogde opdrachtregel:</span><span class="sxs-lookup"><span data-stu-id="2a9c7-142">Open an elevated command-line:</span></span>

    <span data-ttu-id="2a9c7-143">a.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-143">a.</span></span> <span data-ttu-id="2a9c7-144">Ga naar **Start** en typ **cmd.**</span><span class="sxs-lookup"><span data-stu-id="2a9c7-144">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="2a9c7-145">b.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-145">b.</span></span> <span data-ttu-id="2a9c7-146">Klik met de rechtermuisknop **op Opdrachtprompt** en selecteer **Uitvoeren als beheerder.**</span><span class="sxs-lookup"><span data-stu-id="2a9c7-146">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="2a9c7-147">Voer de volgende opdracht in en druk op **Enter:**</span><span class="sxs-lookup"><span data-stu-id="2a9c7-147">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="2a9c7-148">Bijvoorbeeld: netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="2a9c7-148">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>

<span data-ttu-id="2a9c7-149">Als u de winhttp proxy opnieuw wilt instellen, voert u de volgende opdracht in en drukt u op **Enter**</span><span class="sxs-lookup"><span data-stu-id="2a9c7-149">To reset the winhttp proxy, enter the following command and press **Enter**</span></span>

```PowerShell
netsh winhttp reset proxy
```

<span data-ttu-id="2a9c7-150">Zie [Netsh Command Syntaxis, Contexten en Opmaak voor](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-150">See [Netsh Command Syntax, Contexts, and Formatting](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a><span data-ttu-id="2a9c7-151">Toegang tot URL's van microsoft Defender voor eindpuntservice inschakelen op de proxyserver</span><span class="sxs-lookup"><span data-stu-id="2a9c7-151">Enable access to Microsoft Defender for Endpoint service URLs in the proxy server</span></span>

<span data-ttu-id="2a9c7-152">Als een proxy of firewall standaard al het verkeer blokkeert en alleen specifieke domeinen toestaat, voegt u de domeinen in het downloadbare blad toe aan de lijst met toegestane domeinen.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-152">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="2a9c7-153">In de volgende downloadbare spreadsheet vindt u de services en bijbehorende URL's waar uw netwerk verbinding mee moet kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-153">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="2a9c7-154">U moet ervoor zorgen dat er geen firewall- of netwerkfilterregels zijn die de  toegang tot deze URL's weigeren, of u moet mogelijk een regel voor toestaan speciaal voor deze url's maken.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-154">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>


|<span data-ttu-id="2a9c7-155">**Spreadsheet met domeinenlijst**</span><span class="sxs-lookup"><span data-stu-id="2a9c7-155">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="2a9c7-156">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="2a9c7-156">**Description**</span></span>|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="2a9c7-158">Spreadsheet met specifieke DNS-records voor servicelocaties, geografische locaties en besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-158">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="2a9c7-159">Download de spreadsheet hier.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-159">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


<span data-ttu-id="2a9c7-160">Als een proxy of firewall HTTPS-scan (SSL-inspectie) heeft ingeschakeld, sluit u de domeinen in de bovenstaande tabel uit van HTTPS-scannen.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-160">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>

> [!NOTE]
> <span data-ttu-id="2a9c7-161">settings-win.data.microsoft.com is alleen nodig als u Windows 10-apparaten hebt met versie 1803 of eerder.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-161">settings-win.data.microsoft.com is only needed if you have Windows 10 devices running version 1803 or earlier.</span></span><br>


> [!NOTE]
> <span data-ttu-id="2a9c7-162">URL's die v20 bevatten, zijn alleen nodig als u Windows 10-apparaten hebt met versie 1803 of hoger.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-162">URLs that include v20 in them are only needed if you have Windows 10 devices running version 1803 or later.</span></span> <span data-ttu-id="2a9c7-163">Is bijvoorbeeld nodig voor een Windows 10-apparaat met versie 1803 of hoger en is aan boord van de ```us-v20.events.data.microsoft.com``` Vs Data Storage-regio.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-163">For example, ```us-v20.events.data.microsoft.com``` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.</span></span>


> [!NOTE]
> <span data-ttu-id="2a9c7-164">Zie Netwerkverbindingen configureren met de [Microsoft Defender Antivirus-cloudservice](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)als u Microsoft Defender Antivirus gebruikt in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-164">If you are using Microsoft Defender Antivirus in your environment, see [Configure network connections to the Microsoft Defender Antivirus cloud service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="2a9c7-165">Als een proxy of firewall anoniem verkeer blokkeert, aangezien defender voor eindpunten vanuit de systeemcontext verbinding maakt, moet u ervoor zorgen dat anoniem verkeer is toegestaan in de eerder genoemde URL's.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-165">If a proxy or firewall is blocking anonymous traffic, as Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a><span data-ttu-id="2a9c7-166">Microsoft Monitoring Agent (MMA) - proxy- en firewallvereisten voor oudere versies van Windows-client of Windows Server</span><span class="sxs-lookup"><span data-stu-id="2a9c7-166">Microsoft Monitoring Agent (MMA) - proxy and firewall requirements for older versions of Windows client or Windows Server</span></span>

<span data-ttu-id="2a9c7-167">In de onderstaande informatie vindt u de configuratiegegevens voor proxy en firewall die nodig zijn om te communiceren met de Log Analytics-agent (ook wel Microsoft Monitoring Agent genoemd) voor de vorige versies van Windows, zoals Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 en Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-167">The information below list the proxy and firewall configuration information required to communicate with Log Analytics agent (often referred to as Microsoft Monitoring Agent) for the previous versions of Windows such as Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2, and Windows Server 2016.</span></span>

|<span data-ttu-id="2a9c7-168">Agent Resource</span><span class="sxs-lookup"><span data-stu-id="2a9c7-168">Agent Resource</span></span>|<span data-ttu-id="2a9c7-169">Poorten</span><span class="sxs-lookup"><span data-stu-id="2a9c7-169">Ports</span></span> |<span data-ttu-id="2a9c7-170">Richting</span><span class="sxs-lookup"><span data-stu-id="2a9c7-170">Direction</span></span> |<span data-ttu-id="2a9c7-171">HTTPS-inspectie omzeilen</span><span class="sxs-lookup"><span data-stu-id="2a9c7-171">Bypass HTTPS inspection</span></span>|
|------|---------|--------|--------|   
|<span data-ttu-id="2a9c7-172">\*.ods.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="2a9c7-172">\*.ods.opinsights.azure.com</span></span> |<span data-ttu-id="2a9c7-173">Poort 443</span><span class="sxs-lookup"><span data-stu-id="2a9c7-173">Port 443</span></span> |<span data-ttu-id="2a9c7-174">Uitgaande</span><span class="sxs-lookup"><span data-stu-id="2a9c7-174">Outbound</span></span>|<span data-ttu-id="2a9c7-175">Ja</span><span class="sxs-lookup"><span data-stu-id="2a9c7-175">Yes</span></span> |  
|<span data-ttu-id="2a9c7-176">\*.oms.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="2a9c7-176">\*.oms.opinsights.azure.com</span></span> |<span data-ttu-id="2a9c7-177">Poort 443</span><span class="sxs-lookup"><span data-stu-id="2a9c7-177">Port 443</span></span> |<span data-ttu-id="2a9c7-178">Uitgaande</span><span class="sxs-lookup"><span data-stu-id="2a9c7-178">Outbound</span></span>|<span data-ttu-id="2a9c7-179">Ja</span><span class="sxs-lookup"><span data-stu-id="2a9c7-179">Yes</span></span> |  
|<span data-ttu-id="2a9c7-180">\*.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="2a9c7-180">\*.blob.core.windows.net</span></span> |<span data-ttu-id="2a9c7-181">Poort 443</span><span class="sxs-lookup"><span data-stu-id="2a9c7-181">Port 443</span></span> |<span data-ttu-id="2a9c7-182">Uitgaande</span><span class="sxs-lookup"><span data-stu-id="2a9c7-182">Outbound</span></span>|<span data-ttu-id="2a9c7-183">Ja</span><span class="sxs-lookup"><span data-stu-id="2a9c7-183">Yes</span></span> |
|<span data-ttu-id="2a9c7-184">\*.azure-automation.net</span><span class="sxs-lookup"><span data-stu-id="2a9c7-184">\*.azure-automation.net</span></span> |<span data-ttu-id="2a9c7-185">Poort 443</span><span class="sxs-lookup"><span data-stu-id="2a9c7-185">Port 443</span></span> |<span data-ttu-id="2a9c7-186">Uitgaande</span><span class="sxs-lookup"><span data-stu-id="2a9c7-186">Outbound</span></span>|<span data-ttu-id="2a9c7-187">Ja</span><span class="sxs-lookup"><span data-stu-id="2a9c7-187">Yes</span></span> |  


> [!NOTE]
> <span data-ttu-id="2a9c7-188">Als cloudoplossing kan het IP-bereik veranderen.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-188">As a cloud-based solution, the IP range can change.</span></span> <span data-ttu-id="2a9c7-189">U wordt aangeraden over te gaan naar de instelling VOOR DNS-oplossing.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-189">It's recommended you move to DNS resolving setting.</span></span>

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a><span data-ttu-id="2a9c7-190">Microsoft Monitoring Agent (MMA) Service URL-vereisten bevestigen</span><span class="sxs-lookup"><span data-stu-id="2a9c7-190">Confirm Microsoft Monitoring Agent (MMA) Service URL Requirements</span></span> 

<span data-ttu-id="2a9c7-191">Raadpleeg de volgende richtlijnen om de jokertekenvereiste (\*) voor uw specifieke omgeving te verwijderen wanneer u de Microsoft Monitoring Agent (MMA) gebruikt voor eerdere versies van Windows.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-191">Please see the following guidance to eliminate the wildcard (\*) requirement for your specific environment when using the Microsoft Monitoring Agent (MMA) for previous versions of Windows.</span></span>

1.  <span data-ttu-id="2a9c7-192">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see Onboard previous [versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span><span class="sxs-lookup"><span data-stu-id="2a9c7-192">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span>

2.  <span data-ttu-id="2a9c7-193">Controleer of de computer met succes rapporteert in de Microsoft Defender-beveiligingscentrumportal.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-193">Ensure the machine is successfully reporting into the Microsoft Defender Security Center portal.</span></span>

3.  <span data-ttu-id="2a9c7-194">Voer het TestCloudConnection.exe uit van 'C:\Program Files\Microsoft Monitoring Agent\Agent' om de connectiviteit te valideren en om de vereiste URL's voor uw specifieke werkruimte te bekijken.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-194">Run the TestCloudConnection.exe tool from “C:\Program Files\Microsoft Monitoring Agent\Agent” to validate the connectivity and to see the required URLs for your specific workspace.</span></span>

4.  <span data-ttu-id="2a9c7-195">Controleer de lijst MET URL's van Microsoft Defender voor eindpunten voor de volledige lijst met vereisten voor uw regio (raadpleeg het spreadsheet [Service-URL's](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span><span class="sxs-lookup"><span data-stu-id="2a9c7-195">Check the Microsoft Defender for Endpoint URLs list for the complete list of requirements for your region (please refer to the Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span></span>

![Afbeelding van beheerder in Windows PowerShell](images/admin-powershell.png)

<span data-ttu-id="2a9c7-197">De jokertekens (\*) die worden gebruikt in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com en \*.agentsvc.azure-automation.net URL-eindpunten, kunnen worden vervangen door uw specifieke werkruimte-id.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-197">The wildcards (\*) used in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com, and \*.agentsvc.azure-automation.net URL endpoints can be replaced with your specific Workspace ID.</span></span> <span data-ttu-id="2a9c7-198">De werkruimte-id is specifiek voor uw omgeving en werkruimte en is te vinden in de sectie Onboarding van uw tenant in de Microsoft Defender Security Center-portal.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-198">The Workspace ID is specific to your environment and workspace and can be found in the Onboarding section of your tenant within the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="2a9c7-199">Het eindpunt \*.blob.core.windows.net URL kan worden vervangen door de URL's die worden weergegeven in de sectie Firewallregel: \*.blob.core.windows.net' van de testresultaten.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-199">The \*.blob.core.windows.net URL endpoint can be replaced with the URLs shown in the “Firewall Rule: \*.blob.core.windows.net” section of the test results.</span></span> 

> [!NOTE]
> <span data-ttu-id="2a9c7-200">In het geval van onboarding via Azure Security Center (ASC) worden mogelijk meerdere werkruimten gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-200">In the case of onboarding via Azure Security Center (ASC), multiple workspaces maybe used.</span></span> <span data-ttu-id="2a9c7-201">U moet de bovenstaande TestCloudConnection.exe uitvoeren op een onboarded machine vanuit elke werkruimte (om te bepalen of er wijzigingen zijn in de \*.blob.core.windows.net-URL's tussen de werkruimten).</span><span class="sxs-lookup"><span data-stu-id="2a9c7-201">You will need to perform the TestCloudConnection.exe procedure above on an onboarded machine from each workspace (to determine if there are any changes to the \*.blob.core.windows.net URLs between the workspaces).</span></span>

## <a name="verify-client-connectivity-to-microsoft-defender-atp-service-urls"></a><span data-ttu-id="2a9c7-202">Clientconnectiviteit met ATP-service-URL's van Microsoft Defender verifiëren</span><span class="sxs-lookup"><span data-stu-id="2a9c7-202">Verify client connectivity to Microsoft Defender ATP service URLs</span></span>

<span data-ttu-id="2a9c7-203">Controleer of de proxyconfiguratie is voltooid, of WinHTTP kan ontdekken en communiceren via de proxyserver in uw omgeving, en of de proxyserver verkeer toestaat naar de URL's van de Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-203">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="2a9c7-204">Download het [hulpprogramma MDATP Client Analyzer](https://aka.ms/mdatpanalyzer) naar de pc waarop de Defender for Endpoint-sensor wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-204">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Defender for Endpoint sensor is running on.</span></span>

2. <span data-ttu-id="2a9c7-205">Haal de inhoud van MDATPClientAnalyzer.zip op het apparaat op.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-205">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>

3. <span data-ttu-id="2a9c7-206">Open een verhoogde opdrachtregel:</span><span class="sxs-lookup"><span data-stu-id="2a9c7-206">Open an elevated command-line:</span></span>

    <span data-ttu-id="2a9c7-207">a.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-207">a.</span></span> <span data-ttu-id="2a9c7-208">Ga naar **Start** en typ **cmd.**</span><span class="sxs-lookup"><span data-stu-id="2a9c7-208">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="2a9c7-209">b.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-209">b.</span></span>  <span data-ttu-id="2a9c7-210">Klik met de rechtermuisknop **op Opdrachtprompt** en selecteer **Uitvoeren als beheerder.**</span><span class="sxs-lookup"><span data-stu-id="2a9c7-210">Right-click **Command prompt** and select **Run as administrator**.</span></span>

4. <span data-ttu-id="2a9c7-211">Voer de volgende opdracht in en druk op **Enter:**</span><span class="sxs-lookup"><span data-stu-id="2a9c7-211">Enter the following command and press **Enter**:</span></span>

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    <span data-ttu-id="2a9c7-212">*Vervang HardDrivePath* door het pad waar het hulpprogramma MDATPClientAnalyzer naar is gedownload, bijvoorbeeld</span><span class="sxs-lookup"><span data-stu-id="2a9c7-212">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. <span data-ttu-id="2a9c7-213">Haal het *MDATPClientAnalyzerResult.zip* bestand op dat is gemaakt met het hulpprogramma in de map die wordt gebruikt in *HardDrivePath.*</span><span class="sxs-lookup"><span data-stu-id="2a9c7-213">Extract the *MDATPClientAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.</span></span>

6. <span data-ttu-id="2a9c7-214">Open *MDATPClientAnalyzerResult.txt* en controleer of u de proxyconfiguratiestappen hebt uitgevoerd om serverdetectie en toegang tot de service-URL's in te stellen.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-214">Open *MDATPClientAnalyzerResult.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span> <br><br>
   <span data-ttu-id="2a9c7-215">Het hulpprogramma controleert de connectiviteit van URL's van de Defender-service voor eindpunten waarmee defender voor eindpuntclient is geconfigureerd voor interactie.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-215">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="2a9c7-216">Vervolgens worden de resultaten afgedrukt in *hetMDATPClientAnalyzerResult.txt* bestand voor elke URL die mogelijk kan worden gebruikt om te communiceren met de Defender for Endpoint-services.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-216">It then prints the results into the *MDATPClientAnalyzerResult.txt* file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="2a9c7-217">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="2a9c7-217">For example:</span></span>

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

<span data-ttu-id="2a9c7-218">Als ten minste één van de connectiviteitsopties een status (200) retourneert, kan de Defender voor Eindpunt-client correct communiceren met de geteste URL met behulp van deze verbindingsmethode.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-218">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> <br><br>

<span data-ttu-id="2a9c7-219">Als de resultaten van de connectiviteitscontrole echter aangeven dat er een fout is opgetreden, wordt er een HTTP-fout weergegeven (zie HTTP-statuscodes).</span><span class="sxs-lookup"><span data-stu-id="2a9c7-219">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="2a9c7-220">U kunt vervolgens de URL's in de tabel gebruiken die wordt weergegeven in Toegang tot URL's van de Defender voor [eindpuntservice inschakelen op de proxyserver.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="2a9c7-220">You can then use the URLs in the table shown in [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="2a9c7-221">De URL's die u gebruikt, zijn afhankelijk van de regio die tijdens de onboardingprocedure is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-221">The URLs you'll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="2a9c7-222">Het hulpprogramma Connectivity Analyzer is niet compatibel met ASR-regel Procescreaties blokkeren die afkomstig zijn [van PSExec- en WMI-opdrachten.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="2a9c7-222">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="2a9c7-223">U moet deze regel tijdelijk uitschakelen om het verbindingshulpmiddel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-223">You will need to temporarily disable this rule to run the connectivity tool.</span></span>


> [!NOTE]
> <span data-ttu-id="2a9c7-224">Wanneer de TelemetryProxyServer is ingesteld, in register of via groepsbeleid, valt Defender voor Eindpunt terug naar direct als deze geen toegang heeft tot de gedefinieerde proxy.</span><span class="sxs-lookup"><span data-stu-id="2a9c7-224">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can't access the defined proxy.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a9c7-225">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2a9c7-225">Related topics</span></span>

- [<span data-ttu-id="2a9c7-226">Onboarden Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="2a9c7-226">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="2a9c7-227">Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen</span><span class="sxs-lookup"><span data-stu-id="2a9c7-227">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
