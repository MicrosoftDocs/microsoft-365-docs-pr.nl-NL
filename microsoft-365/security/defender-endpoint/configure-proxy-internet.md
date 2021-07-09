---
title: Apparaatproxy- en internetverbindingsinstellingen configureren
description: Configureer de Microsoft Defender voor eindpuntproxy- en internetinstellingen om communicatie met de cloudservice in te stellen.
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
ms.openlocfilehash: 6a3bbc46bb5859743d5170451b0d1c68793f93bf
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338707"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="c6fed-104">Instellingen voor apparaatproxy en internetverbinding configureren</span><span class="sxs-lookup"><span data-stu-id="c6fed-104">Configure device proxy and Internet connectivity settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c6fed-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c6fed-105">**Applies to:**</span></span>
- [<span data-ttu-id="c6fed-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c6fed-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c6fed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6fed-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c6fed-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="c6fed-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c6fed-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="c6fed-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="c6fed-110">Voor de Defender for Endpoint-sensor moet Microsoft Windows HTTP (WinHTTP) sensorgegevens rapporteren en communiceren met de Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="c6fed-110">The Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Defender for Endpoint service.</span></span>

<span data-ttu-id="c6fed-111">De ingesloten Defender voor Eindpunt-sensor wordt uitgevoerd in systeemcontext met behulp van het LocalSystem-account.</span><span class="sxs-lookup"><span data-stu-id="c6fed-111">The embedded Defender for Endpoint sensor runs in system context using the LocalSystem account.</span></span> <span data-ttu-id="c6fed-112">De sensor gebruikt Microsoft Windows HTTP Services (WinHTTP) om communicatie met de Defender for Endpoint-cloudservice in te stellen.</span><span class="sxs-lookup"><span data-stu-id="c6fed-112">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Defender for Endpoint cloud service.</span></span>

> [!TIP]
> <span data-ttu-id="c6fed-113">Organisaties die forward proxy's gebruiken als gateway voor internet, kunt netwerkbeveiliging gebruiken om een proxy te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="c6fed-113">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="c6fed-114">Zie [Verbindingsgebeurtenissen achter forward proxy's onderzoeken](investigate-behind-proxy.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c6fed-114">For more information, see [Investigate connection events that occur behind forward proxies](investigate-behind-proxy.md).</span></span>

<span data-ttu-id="c6fed-115">De configuratie-instelling WinHTTP is onafhankelijk van de instellingen Windows Internet (WinINet) voor internetbrowsingsproxy en kan alleen een proxyserver vinden met behulp van de volgende detectiemethoden:</span><span class="sxs-lookup"><span data-stu-id="c6fed-115">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

- <span data-ttu-id="c6fed-116">Methoden voor automatische detectie:</span><span class="sxs-lookup"><span data-stu-id="c6fed-116">Auto-discovery methods:</span></span>

  - <span data-ttu-id="c6fed-117">Transparante proxy</span><span class="sxs-lookup"><span data-stu-id="c6fed-117">Transparent proxy</span></span>

  - <span data-ttu-id="c6fed-118">WPAD (Web Proxy Auto Discovery Protocol)</span><span class="sxs-lookup"><span data-stu-id="c6fed-118">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

    > [!NOTE]
    > <span data-ttu-id="c6fed-119">Als u Transparante proxy of WPAD gebruikt in de netwerktopologie, hebt u geen speciale configuratie-instellingen nodig.</span><span class="sxs-lookup"><span data-stu-id="c6fed-119">If you're using Transparent proxy or WPAD in your network topology, you don't need special configuration settings.</span></span> <span data-ttu-id="c6fed-120">Zie Access [to Defender for Endpoint service URLLs in](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)de proxy inschakelen voor meer informatie over URL-uitsluitingen van Defender voor eindpunten in de proxy.</span><span class="sxs-lookup"><span data-stu-id="c6fed-120">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="c6fed-121">Hnadmatige statische proxyconfiguratie</span><span class="sxs-lookup"><span data-stu-id="c6fed-121">Manual static proxy configuration:</span></span>

  - <span data-ttu-id="c6fed-122">Configuratie op basis van register</span><span class="sxs-lookup"><span data-stu-id="c6fed-122">Registry based configuration</span></span>

  - <span data-ttu-id="c6fed-123">WinHTTP geconfigureerd met de Netsh-opdracht– Alleen geschikt voor desktops in een stabiele topologie (bijvoorbeeld: een bureaublad in een bedrijfsnetwerk achter dezelfde proxy)</span><span class="sxs-lookup"><span data-stu-id="c6fed-123">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="c6fed-124">De proxyserver handmatig configureren met een statische proxy op basis van het register</span><span class="sxs-lookup"><span data-stu-id="c6fed-124">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="c6fed-125">Configureer een statische proxy op basis van het register zodat alleen defender voor eindpunten-sensor diagnostische gegevens kan rapporteren en kan communiceren met Defender voor eindpuntservices als een computer geen verbinding mag maken met internet.</span><span class="sxs-lookup"><span data-stu-id="c6fed-125">Configure a registry-based static proxy to allow only Defender for Endpoint sensor to report diagnostic data and communicate with Defender for Endpoint services if a computer is not permitted to connect to the Internet.</span></span>

> [!NOTE]
> <span data-ttu-id="c6fed-126">Wanneer u deze optie gebruikt op Windows 10 of Windows Server 2019, wordt het aanbevolen om de volgende (of latere) build- en cumulatieve update-rollup te hebben:</span><span class="sxs-lookup"><span data-stu-id="c6fed-126">When using this option on Windows 10 or Windows Server 2019, it is recommended to have the following (or later) build and cumulative update rollup:</span></span>
>
> - <span data-ttu-id="c6fed-127">Windows 10 versie 1809 of Windows Server 2019 -https://support.microsoft.com/kb/5001384</span><span class="sxs-lookup"><span data-stu-id="c6fed-127">Windows 10, version 1809 or Windows Server 2019 - https://support.microsoft.com/kb/5001384</span></span>
> - <span data-ttu-id="c6fed-128">Windows 10, versie 1909 -https://support.microsoft.com/kb/4601380</span><span class="sxs-lookup"><span data-stu-id="c6fed-128">Windows 10, version 1909 - https://support.microsoft.com/kb/4601380</span></span>
> - <span data-ttu-id="c6fed-129">Windows 10, versie 2004 -https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="c6fed-129">Windows 10, version 2004 - https://support.microsoft.com/kb/4601382</span></span>
> - <span data-ttu-id="c6fed-130">Windows 10, versie 20H2 -https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="c6fed-130">Windows 10, version 20H2 - https://support.microsoft.com/kb/4601382</span></span>
>
> <span data-ttu-id="c6fed-131">Deze updates verbeteren de connectiviteit en betrouwbaarheid van het CnC-kanaal (Command and Control).</span><span class="sxs-lookup"><span data-stu-id="c6fed-131">These updates improve the connectivity and reliability of the CnC (Command and Control) channel.</span></span>

<span data-ttu-id="c6fed-132">De statische proxy kan worden geconfigureerd via Group Policy (GP).</span><span class="sxs-lookup"><span data-stu-id="c6fed-132">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="c6fed-133">U vindt het groepsbeleid onder:</span><span class="sxs-lookup"><span data-stu-id="c6fed-133">The group policy can be found under:</span></span>

- <span data-ttu-id="c6fed-134">**Beheersjablonen > Windows Onderdelen > Gegevensverzameling en Preview-builds > Geverifieerd proxygebruik configureren voor de verbonden gebruikerservaring en telemetrieservice**</span><span class="sxs-lookup"><span data-stu-id="c6fed-134">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

  <span data-ttu-id="c6fed-135">Stel deze in **op Ingeschakeld en** selecteer Geverifieerd **proxygebruik uitschakelen.**</span><span class="sxs-lookup"><span data-stu-id="c6fed-135">Set it to **Enabled** and select **Disable Authenticated Proxy usage**.</span></span>

  ![Afbeelding van groepsbeleidsinstelling1](images/atp-gpo-proxy1.png)

- <span data-ttu-id="c6fed-137">**Beheersjablonen > Windows Onderdelen > Gegevensverzameling en Preview-builds > Verbonden gebruikerservaringen en telemetrie configureren:**</span><span class="sxs-lookup"><span data-stu-id="c6fed-137">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

  <span data-ttu-id="c6fed-138">De peoxy configureren</span><span class="sxs-lookup"><span data-stu-id="c6fed-138">Configure the proxy</span></span>

  ![Afbeelding van groepsbeleidsinstelling2](images/atp-gpo-proxy2.png)

  <span data-ttu-id="c6fed-140">Met het beleid worden twee registerwaarden, `TelemetryProxyServer` als REG_SZ en `DisableEnterpriseAuthProxy` REG_DWORD, onder de registersleutel. `HKLM\Software\Policies\Microsoft\Windows\DataCollection`</span><span class="sxs-lookup"><span data-stu-id="c6fed-140">The policy sets two registry values, `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD, under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

  <span data-ttu-id="c6fed-141">De registerwaarde `TelemetryProxyServer` heeft de volgende tekenreeksindeling:</span><span class="sxs-lookup"><span data-stu-id="c6fed-141">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

  ```text
  <server name or ip>:<port>
  ```

  <span data-ttu-id="c6fed-142">Bijvoorbeeld: 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="c6fed-142">For example: 10.0.0.6:8080</span></span>

  <span data-ttu-id="c6fed-143">De registerwaarde `DisableEnterpriseAuthProxy` moet worden ingesteld op 1.</span><span class="sxs-lookup"><span data-stu-id="c6fed-143">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="c6fed-144">De proxyserver handmatig configureren met de opdracht Netsh</span><span class="sxs-lookup"><span data-stu-id="c6fed-144">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="c6fed-145">Gebruik netsh om een statische proxy voor het hele systeem te configureren.</span><span class="sxs-lookup"><span data-stu-id="c6fed-145">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="c6fed-146">Dit is van invloed op alle toepassingen, inclusief Windows-services die WinHTTP met standaardproxy gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c6fed-146">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="c6fed-147">Laptops die de topologie wijzigen (bijvoorbeeld van kantoor naar thuis) werken niet goed met netsh.</span><span class="sxs-lookup"><span data-stu-id="c6fed-147">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="c6fed-148">Gebruik de statische proxyconfiguratie op basis van het register.</span><span class="sxs-lookup"><span data-stu-id="c6fed-148">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="c6fed-149">Open een verhoogde opdrachtregel:</span><span class="sxs-lookup"><span data-stu-id="c6fed-149">Open an elevated command-line:</span></span>

   1. <span data-ttu-id="c6fed-150">Go to **Start** and type **cmd**.</span><span class="sxs-lookup"><span data-stu-id="c6fed-150">Go to **Start** and type **cmd**.</span></span>

   1. <span data-ttu-id="c6fed-151">Klik met de rechtermuisknop op **Opdrachtprompt** en selecteer **Als beheerder uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="c6fed-151">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="c6fed-152">Voer de volgende opdracht in en druk op **Enter**:</span><span class="sxs-lookup"><span data-stu-id="c6fed-152">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="c6fed-153">Bijvoorbeeld:`netsh winhttp set proxy 10.0.0.6:8080`</span><span class="sxs-lookup"><span data-stu-id="c6fed-153">For example: `netsh winhttp set proxy 10.0.0.6:8080`</span></span>

<span data-ttu-id="c6fed-154">Voer de volgende opdracht in en druk op **Enter** om de winhttp proxy opnieuw in te stellen:</span><span class="sxs-lookup"><span data-stu-id="c6fed-154">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

```PowerShell
netsh winhttp reset proxy
```

<span data-ttu-id="c6fed-155">Zie [Syntaxis, contexten en opmaak van Netsh](/windows-server/networking/technologies/netsh/netsh-contexts) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c6fed-155">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a><span data-ttu-id="c6fed-156">Toegang tot URL's van microsoft Defender voor eindpuntservice inschakelen op de proxyserver</span><span class="sxs-lookup"><span data-stu-id="c6fed-156">Enable access to Microsoft Defender for Endpoint service URLs in the proxy server</span></span>

<span data-ttu-id="c6fed-157">Als door een proxy of firewall standaard al het verkeer wordt geblokkeerd en alleen bepaalde domeinen worden toegestaan, voegt u de domeinen die worden vermeld in het downloadbare blad toe aan de lijst met toegestane domeinen.</span><span class="sxs-lookup"><span data-stu-id="c6fed-157">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="c6fed-158">In de volgende downloadbare spreadsheet vindt u de services en bijbehorende URL's waar uw netwerk verbinding mee moet kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="c6fed-158">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="c6fed-159">U moet ervoor zorgen dat er geen firewall- of netwerkfilterregels zijn die de  toegang tot deze URL's weigeren, of u moet mogelijk een regel voor toestaan speciaal voor deze url's maken.</span><span class="sxs-lookup"><span data-stu-id="c6fed-159">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>

| <span data-ttu-id="c6fed-160">Spreadsheet met domeinenlijst</span><span class="sxs-lookup"><span data-stu-id="c6fed-160">Spreadsheet of domains list</span></span> | <span data-ttu-id="c6fed-161">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="c6fed-161">Description</span></span> |
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="c6fed-163">Spreadsheet met specifieke DNS-records voor servicelocaties, geografische locaties en besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="c6fed-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="c6fed-164">Download de spreadsheet hier.</span><span class="sxs-lookup"><span data-stu-id="c6fed-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

<span data-ttu-id="c6fed-165">Als https-scannen (SSL-controle) is ingeschakeld voor een proxy of firewall, moet u de domeinen in de bovenstaande tabel uitsluiten van HTTPS-scannen.</span><span class="sxs-lookup"><span data-stu-id="c6fed-165">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>

> [!NOTE]
> <span data-ttu-id="c6fed-166">settings-win.data.microsoft.com is alleen nodig als u Windows 10 hebt met versie 1803 of eerder.</span><span class="sxs-lookup"><span data-stu-id="c6fed-166">settings-win.data.microsoft.com is only needed if you have Windows 10 devices running version 1803 or earlier.</span></span><br>
>
> <span data-ttu-id="c6fed-167">URL's die v20 bevatten, zijn alleen nodig als u Windows 10 apparaten met versie 1803 of hoger hebt.</span><span class="sxs-lookup"><span data-stu-id="c6fed-167">URLs that include v20 in them are only needed if you have Windows 10 devices running version 1803 or later.</span></span> <span data-ttu-id="c6fed-168">Dit is bijvoorbeeld nodig voor een Windows 10 met versie 1803 of hoger en is aan boord van us `us-v20.events.data.microsoft.com` Data Storage regio.</span><span class="sxs-lookup"><span data-stu-id="c6fed-168">For example, `us-v20.events.data.microsoft.com` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.</span></span>
>
> <span data-ttu-id="c6fed-169">Zie Netwerkverbindingen configureren Microsoft Defender Antivirus cloudservice als u Microsoft Defender Antivirus [in uw omgeving gebruikt.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="c6fed-169">If you are using Microsoft Defender Antivirus in your environment, see [Configure network connections to the Microsoft Defender Antivirus cloud service](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="c6fed-170">Als een proxy of firewall anoniem verkeer blokkeert, aangezien defender voor eindpunten vanuit de systeemcontext verbinding maakt, moet u ervoor zorgen dat anoniem verkeer is toegestaan in de eerder genoemde URL's.</span><span class="sxs-lookup"><span data-stu-id="c6fed-170">If a proxy or firewall is blocking anonymous traffic, as Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a><span data-ttu-id="c6fed-171">Microsoft Monitoring Agent (MMA) - proxy- en firewallvereisten voor oudere versies van Windows client of Windows Server</span><span class="sxs-lookup"><span data-stu-id="c6fed-171">Microsoft Monitoring Agent (MMA) - proxy and firewall requirements for older versions of Windows client or Windows Server</span></span>

<span data-ttu-id="c6fed-172">In de onderstaande informatie vindt u de configuratiegegevens van de proxy en firewall die nodig zijn om te communiceren met loganalyseagent (ook wel Microsoft Monitoring Agent genoemd) voor de vorige versies van Windows, zoals Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 en Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="c6fed-172">The information below list the proxy and firewall configuration information required to communicate with Log Analytics agent (often referred to as Microsoft Monitoring Agent) for the previous versions of Windows such as Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2, and Windows Server 2016.</span></span>

|<span data-ttu-id="c6fed-173">Agent-resource</span><span class="sxs-lookup"><span data-stu-id="c6fed-173">Agent Resource</span></span>|<span data-ttu-id="c6fed-174">Poorten</span><span class="sxs-lookup"><span data-stu-id="c6fed-174">Ports</span></span> |<span data-ttu-id="c6fed-175">Richting</span><span class="sxs-lookup"><span data-stu-id="c6fed-175">Direction</span></span> |<span data-ttu-id="c6fed-176">HTTPS-inspectie omzeilen</span><span class="sxs-lookup"><span data-stu-id="c6fed-176">Bypass HTTPS inspection</span></span>|
|------|---------|--------|--------|
|<span data-ttu-id="c6fed-177">\*.ods.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="c6fed-177">\*.ods.opinsights.azure.com</span></span> |<span data-ttu-id="c6fed-178">Poort 443</span><span class="sxs-lookup"><span data-stu-id="c6fed-178">Port 443</span></span> |<span data-ttu-id="c6fed-179">Uitgaand</span><span class="sxs-lookup"><span data-stu-id="c6fed-179">Outbound</span></span>|<span data-ttu-id="c6fed-180">Ja</span><span class="sxs-lookup"><span data-stu-id="c6fed-180">Yes</span></span> |  
|<span data-ttu-id="c6fed-181">\*.oms.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="c6fed-181">\*.oms.opinsights.azure.com</span></span> |<span data-ttu-id="c6fed-182">Poort 443</span><span class="sxs-lookup"><span data-stu-id="c6fed-182">Port 443</span></span> |<span data-ttu-id="c6fed-183">Uitgaand</span><span class="sxs-lookup"><span data-stu-id="c6fed-183">Outbound</span></span>|<span data-ttu-id="c6fed-184">Ja</span><span class="sxs-lookup"><span data-stu-id="c6fed-184">Yes</span></span> |  
|<span data-ttu-id="c6fed-185">\*.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="c6fed-185">\*.blob.core.windows.net</span></span> |<span data-ttu-id="c6fed-186">Poort 443</span><span class="sxs-lookup"><span data-stu-id="c6fed-186">Port 443</span></span> |<span data-ttu-id="c6fed-187">Uitgaand</span><span class="sxs-lookup"><span data-stu-id="c6fed-187">Outbound</span></span>|<span data-ttu-id="c6fed-188">Ja</span><span class="sxs-lookup"><span data-stu-id="c6fed-188">Yes</span></span> |
|<span data-ttu-id="c6fed-189">\*.azure-automation.net</span><span class="sxs-lookup"><span data-stu-id="c6fed-189">\*.azure-automation.net</span></span> |<span data-ttu-id="c6fed-190">Poort 443</span><span class="sxs-lookup"><span data-stu-id="c6fed-190">Port 443</span></span> |<span data-ttu-id="c6fed-191">Uitgaand</span><span class="sxs-lookup"><span data-stu-id="c6fed-191">Outbound</span></span>|<span data-ttu-id="c6fed-192">Ja</span><span class="sxs-lookup"><span data-stu-id="c6fed-192">Yes</span></span> |  

> [!NOTE]
> <span data-ttu-id="c6fed-193">Als cloudoplossing kan het IP-bereik veranderen.</span><span class="sxs-lookup"><span data-stu-id="c6fed-193">As a cloud-based solution, the IP range can change.</span></span> <span data-ttu-id="c6fed-194">U wordt aangeraden over te gaan naar de instelling VOOR DNS-oplossing.</span><span class="sxs-lookup"><span data-stu-id="c6fed-194">It's recommended you move to DNS resolving setting.</span></span>

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a><span data-ttu-id="c6fed-195">Microsoft Monitoring Agent (MMA) Service URL-vereisten bevestigen</span><span class="sxs-lookup"><span data-stu-id="c6fed-195">Confirm Microsoft Monitoring Agent (MMA) Service URL Requirements</span></span> 

<span data-ttu-id="c6fed-196">Raadpleeg de volgende richtlijnen om de vereiste jokerteken (\*) voor uw specifieke omgeving te verwijderen wanneer u de Microsoft Monitoring Agent (MMA) gebruikt voor eerdere versies van Windows.</span><span class="sxs-lookup"><span data-stu-id="c6fed-196">Please see the following guidance to eliminate the wildcard (\*) requirement for your specific environment when using the Microsoft Monitoring Agent (MMA) for previous versions of Windows.</span></span>

1. <span data-ttu-id="c6fed-197">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see Onboard previous [versions of Windows](https://go.microsoft.com/fwlink/p/?linkid=2010326) on Defender for Endpoint and Onboard Windows [servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span><span class="sxs-lookup"><span data-stu-id="c6fed-197">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span>

2. <span data-ttu-id="c6fed-198">Controleer of de computer succesvol rapporteert in de Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="c6fed-198">Ensure the machine is successfully reporting into the Microsoft 365 Defender portal.</span></span>

3. <span data-ttu-id="c6fed-199">Voer het TestCloudConnection.exe uit van 'C:\Program Files\Microsoft Monitoring Agent\Agent' om de connectiviteit te valideren en om de vereiste URL's voor uw specifieke werkruimte te bekijken.</span><span class="sxs-lookup"><span data-stu-id="c6fed-199">Run the TestCloudConnection.exe tool from “C:\Program Files\Microsoft Monitoring Agent\Agent” to validate the connectivity and to see the required URLs for your specific workspace.</span></span>

4. <span data-ttu-id="c6fed-200">Controleer de lijst MET URL's van Microsoft Defender voor eindpunten voor de volledige lijst met vereisten voor uw regio (raadpleeg het spreadsheet [Service-URL's](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span><span class="sxs-lookup"><span data-stu-id="c6fed-200">Check the Microsoft Defender for Endpoint URLs list for the complete list of requirements for your region (please refer to the Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span></span>

    ![Afbeelding van beheerder in Windows PowerShell](images/admin-powershell.png)

<span data-ttu-id="c6fed-202">De jokertekens () die worden gebruikt \* in \* .ods.opinsights.azure.com, .oms.opinsights.azure.com en .agentsvc.azure-automation.net URL-eindpunten kunnen worden vervangen door uw specifieke \* werkruimte-id. \*</span><span class="sxs-lookup"><span data-stu-id="c6fed-202">The wildcards (\*) used in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com, and \*.agentsvc.azure-automation.net URL endpoints can be replaced with your specific Workspace ID.</span></span> <span data-ttu-id="c6fed-203">De werkruimte-id is specifiek voor uw omgeving en werkruimte en is te vinden in de sectie Onboarding van uw tenant binnen de Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="c6fed-203">The Workspace ID is specific to your environment and workspace and can be found in the Onboarding section of your tenant within the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="c6fed-204">Het .blob.core.windows.net URL-eindpunt kan worden vervangen door de URL's die worden weergegeven in de sectie \* Firewallregel: \* .blob.core.windows.net' van de testresultaten.</span><span class="sxs-lookup"><span data-stu-id="c6fed-204">The \*.blob.core.windows.net URL endpoint can be replaced with the URLs shown in the "Firewall Rule: \*.blob.core.windows.net" section of the test results.</span></span>

> [!NOTE]
> <span data-ttu-id="c6fed-205">In het geval van onboarding via Azure Defender worden mogelijk meerdere werkruimten gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c6fed-205">In the case of onboarding via Azure Defender, multiple workspaces maybe used.</span></span> <span data-ttu-id="c6fed-206">U moet de bovenstaande TestCloudConnection.exe uitvoeren op een onboarded machine vanuit elke werkruimte (om te bepalen of er wijzigingen zijn in de \*.blob.core.windows.net-URL's tussen de werkruimten).</span><span class="sxs-lookup"><span data-stu-id="c6fed-206">You will need to perform the TestCloudConnection.exe procedure above on an onboarded machine from each workspace (to determine if there are any changes to the \*.blob.core.windows.net URLs between the workspaces).</span></span>

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a><span data-ttu-id="c6fed-207">Clientconnectiviteit verifiëren met URL's van Microsoft Defender voor endpoint-service</span><span class="sxs-lookup"><span data-stu-id="c6fed-207">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>

<span data-ttu-id="c6fed-208">Controleer of de proxyconfiguratie is voltooid, of WinHTTP de proxyserver in uw omgeving kan vinden en communiceren, en of via de proxyserver verkeer wordt toegestaan naar de URL's van de Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="c6fed-208">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="c6fed-209">Download het [hulpprogramma MDATP Client Analyzer](https://aka.ms/mdatpanalyzer) naar de pc waarop de Defender for Endpoint-sensor wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="c6fed-209">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Defender for Endpoint sensor is running on.</span></span>

2. <span data-ttu-id="c6fed-210">Pak de inhoud van MDATPClientAnalyzer.zip uit op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="c6fed-210">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>

3. <span data-ttu-id="c6fed-211">Open een verhoogde opdrachtregel:</span><span class="sxs-lookup"><span data-stu-id="c6fed-211">Open an elevated command-line:</span></span>

   1. <span data-ttu-id="c6fed-212">Go to **Start** and type **cmd**.</span><span class="sxs-lookup"><span data-stu-id="c6fed-212">Go to **Start** and type **cmd**.</span></span>

   1. <span data-ttu-id="c6fed-213">Klik met de rechtermuisknop op **Opdrachtprompt** en selecteer **Als beheerder uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="c6fed-213">Right-click **Command prompt** and select **Run as administrator**.</span></span>

4. <span data-ttu-id="c6fed-214">Voer de volgende opdracht in en druk op **Enter**:</span><span class="sxs-lookup"><span data-stu-id="c6fed-214">Enter the following command and press **Enter**:</span></span>

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    <span data-ttu-id="c6fed-215">Vervang *HardDrivePath* door het pad waar het hulpprogramma MDATPClientAnalyzer naar is gedownload, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="c6fed-215">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example:</span></span>

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. <span data-ttu-id="c6fed-216">Haal het *MDATPClientAnalyzerResult.zip* bestand op dat is gemaakt met het hulpprogramma in de map die wordt gebruikt in *HardDrivePath.*</span><span class="sxs-lookup"><span data-stu-id="c6fed-216">Extract the *MDATPClientAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.</span></span>

6. <span data-ttu-id="c6fed-217">Open *MDATPClientAnalyzerResult.txt* en controleer of u de configuratiestappen voor de proxy hebt uitgevoerd om serverdetectie en toegang tot de service-URL's in te stellen.</span><span class="sxs-lookup"><span data-stu-id="c6fed-217">Open *MDATPClientAnalyzerResult.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>

   <span data-ttu-id="c6fed-218">Het hulpprogramma controleert de verbindingen van URL's van Defender voor Endpoint-service die voor Defender voor Endpoint-client zijn geconfigureerd voor interactie.</span><span class="sxs-lookup"><span data-stu-id="c6fed-218">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="c6fed-219">Vervolgens worden de resultaten afgedrukt in het bestand *MDATPClientAnalyzerResult.txt* voor elke URL die mogelijk kan worden gebruikt voor communicatie met Defender voor Endpoint-services.</span><span class="sxs-lookup"><span data-stu-id="c6fed-219">It then prints the results into the *MDATPClientAnalyzerResult.txt* file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="c6fed-220">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="c6fed-220">For example:</span></span>

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

<span data-ttu-id="c6fed-221">Als minimaal één van de connectiviteitsopties een status (200) retourneert, kan de Defender voor Endpoint-client met deze connectiviteitsmethode correct communiceren met de geteste URL.</span><span class="sxs-lookup"><span data-stu-id="c6fed-221">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span>

<span data-ttu-id="c6fed-222">Als de resultaten van de connectiviteitscontrole echter aangeven dat er een fout is, wordt een HTTP-fout weergegeven (zie HTTP-statuscodes).</span><span class="sxs-lookup"><span data-stu-id="c6fed-222">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="c6fed-223">U kunt vervolgens de URL's in de tabel gebruiken die wordt weergegeven in Toegang tot URL's van de Defender voor [eindpuntservice inschakelen op de proxyserver.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="c6fed-223">You can then use the URLs in the table shown in [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="c6fed-224">De URL's die u gebruikt, zijn afhankelijk van de regio die tijdens de onboardingprocedure is geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="c6fed-224">The URLs you'll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="c6fed-225">Het hulpprogramma Connectivity Analyzer is niet compatibel met de ASR-regel [Maken van processen via PSExec- en WMI-opdrachten blokkeren](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="c6fed-225">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="c6fed-226">Schakel deze regel tijdelijk uit om het hulpprogramma Connectivity Analyzer uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="c6fed-226">You will need to temporarily disable this rule to run the connectivity tool.</span></span>
>
> <span data-ttu-id="c6fed-227">Wanneer de TelemetryProxyServer is ingesteld, in register of via groepsbeleid, valt Defender voor Eindpunt terug naar direct als deze geen toegang heeft tot de gedefinieerde proxy.</span><span class="sxs-lookup"><span data-stu-id="c6fed-227">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can't access the defined proxy.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c6fed-228">Gerelateerde onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c6fed-228">Related topics</span></span>

- [<span data-ttu-id="c6fed-229">Onboarden Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="c6fed-229">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="c6fed-230">Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen</span><span class="sxs-lookup"><span data-stu-id="c6fed-230">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
