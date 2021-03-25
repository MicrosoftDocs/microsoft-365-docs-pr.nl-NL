---
title: Eerdere versies van Windows aan boord van Microsoft Defender ATP
description: Ondersteunde eerdere versies van Windows-apparaten aan boord, zodat ze sensorgegevens kunnen verzenden naar de ATP-sensor van Microsoft Defender
keywords: onboard, windows, 7, 81, oms, sp1, enterprise, pro, down level
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b180e7555bb3339324d3b99956d8f8ad73dc13c3
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186387"
---
# <a name="onboard-previous-versions-of-windows"></a><span data-ttu-id="4625c-104">Eerdere versies van Windows aan boord</span><span class="sxs-lookup"><span data-stu-id="4625c-104">Onboard previous versions of Windows</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4625c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4625c-105">**Applies to:**</span></span>
- [<span data-ttu-id="4625c-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="4625c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4625c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4625c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="4625c-108">**Platforms**</span><span class="sxs-lookup"><span data-stu-id="4625c-108">**Platforms**</span></span>
- <span data-ttu-id="4625c-109">Windows 7 SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4625c-109">Windows 7 SP1 Enterprise</span></span>
- <span data-ttu-id="4625c-110">Windows 7 SP1 Pro</span><span class="sxs-lookup"><span data-stu-id="4625c-110">Windows 7 SP1 Pro</span></span>
- <span data-ttu-id="4625c-111">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="4625c-111">Windows 8.1 Pro</span></span>
- <span data-ttu-id="4625c-112">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4625c-112">Windows 8.1 Enterprise</span></span>


><span data-ttu-id="4625c-113">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="4625c-113">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="4625c-114">[Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="4625c-114">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span></span>

<span data-ttu-id="4625c-115">Defender voor Eindpunt breidt de ondersteuning uit met besturingssystemen op lager niveau, met geavanceerde mogelijkheden voor detectie van aanvallen en onderzoeksmogelijkheden voor ondersteunde Windows-versies.</span><span class="sxs-lookup"><span data-stu-id="4625c-115">Defender for Endpoint extends support to include down-level operating systems, providing advanced attack detection and investigation capabilities on supported Windows versions.</span></span>

<span data-ttu-id="4625c-116">Als u windows-client-eindpunten op een lager niveau wilt in- en onboarden bij Defender voor Eindpunt, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="4625c-116">To onboard down-level Windows client endpoints to Defender for Endpoint, you'll need to:</span></span>
- <span data-ttu-id="4625c-117">System Center Endpoint Protection-clients configureren en bijwerken.</span><span class="sxs-lookup"><span data-stu-id="4625c-117">Configure and update System Center Endpoint Protection clients.</span></span>
- <span data-ttu-id="4625c-118">Installeer en configureer Microsoft Monitoring Agent (MMA) om sensorgegevens te rapporteren aan Defender voor Eindpunt, zoals hieronder wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="4625c-118">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Defender for Endpoint as instructed below.</span></span>

> [!TIP]
> <span data-ttu-id="4625c-119">Nadat u het apparaat hebt onboarding, kunt u ervoor kiezen om een detectietest uit te voeren om te controleren of het apparaat correct is aan boord van de service.</span><span class="sxs-lookup"><span data-stu-id="4625c-119">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="4625c-120">Zie Een detectietest uitvoeren op een nieuw ingebouwde [Defender voor eindpunten voor meer informatie.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="4625c-120">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="4625c-121">System Center Endpoint Protection-clients configureren en bijwerken</span><span class="sxs-lookup"><span data-stu-id="4625c-121">Configure and update System Center Endpoint Protection clients</span></span>
> [!IMPORTANT]
> <span data-ttu-id="4625c-122">Deze stap is alleen vereist als uw organisatie System Center Endpoint Protection (SCEP) gebruikt.</span><span class="sxs-lookup"><span data-stu-id="4625c-122">This step is required only if your organization uses System Center Endpoint Protection (SCEP).</span></span>

<span data-ttu-id="4625c-123">Defender for Endpoint is geïntegreerd met System Center Endpoint Protection om malwaredetecties zichtbaar te maken en de verspreiding van een aanval in uw organisatie te stoppen door potentieel schadelijke bestanden of verdachte malware te verbieden.</span><span class="sxs-lookup"><span data-stu-id="4625c-123">Defender for Endpoint integrates with System Center Endpoint Protection to provide visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 

<span data-ttu-id="4625c-124">De volgende stappen zijn vereist om deze integratie mogelijk te maken:</span><span class="sxs-lookup"><span data-stu-id="4625c-124">The following steps are required to enable this integration:</span></span> 
- <span data-ttu-id="4625c-125">De update [van het anti-malwareplatform van januari 2017 installeren voor endpoint protection-clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="4625c-125">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span></span> 
- <span data-ttu-id="4625c-126">Het lidmaatschap van de SCEP-client Cloud Protection Service configureren op **de instelling Geavanceerd**</span><span class="sxs-lookup"><span data-stu-id="4625c-126">Configure the SCEP client Cloud Protection Service membership to the **Advanced** setting</span></span>
- <span data-ttu-id="4625c-127">Configureer uw netwerk om verbindingen met de Microsoft Defender Antivirus-cloud toe te staan.</span><span class="sxs-lookup"><span data-stu-id="4625c-127">Configure your network to allow connections to the Microsoft Defender Antivirus cloud.</span></span> <span data-ttu-id="4625c-128">Zie Verbindingen toestaan [met de Microsoft Defender Antivirus-cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4625c-128">For more information, see [Allow connections to the Microsoft Defender Antivirus cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span></span>

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="4625c-129">Microsoft Monitoring Agent (MMA) installeren en configureren om sensorgegevens te rapporteren aan Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4625c-129">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="4625c-130">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="4625c-130">Before you begin</span></span>
<span data-ttu-id="4625c-131">Bekijk de volgende details om de minimale systeemvereisten te controleren:</span><span class="sxs-lookup"><span data-stu-id="4625c-131">Review the following details to verify minimum system requirements:</span></span>
- <span data-ttu-id="4625c-132">De maandelijkse update van [februari 2018 installeren](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="4625c-132">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="4625c-133">Alleen van toepassing op Windows 7 SP1 Enterprise en Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="4625c-133">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span> 

- <span data-ttu-id="4625c-134">De [update voor klantervaring en diagnostische telemetrie installeren](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span><span class="sxs-lookup"><span data-stu-id="4625c-134">Install the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span></span>

- <span data-ttu-id="4625c-135">Installeer [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (of hoger) of [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="4625c-135">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="4625c-136">Alleen van toepassing op Windows 7 SP1 Enterprise en Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="4625c-136">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span>
    > <span data-ttu-id="4625c-137">Installeer .NET Framework 4.0.x niet, omdat de bovenstaande installatie wordt ontbonden.</span><span class="sxs-lookup"><span data-stu-id="4625c-137">Don't install .NET Framework 4.0.x, since it will negate the above installation.</span></span>

- <span data-ttu-id="4625c-138">Voldoe aan de minimale systeemvereisten voor Azure Log Analytics-agent.</span><span class="sxs-lookup"><span data-stu-id="4625c-138">Meet the Azure Log Analytics agent minimum system requirements.</span></span> <span data-ttu-id="4625c-139">Zie Gegevens verzamelen van computers in uw omgeving met Log Analytics voor [meer informatie.](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="4625c-139">For more information, see [Collect data from computers in you environment with Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span></span>



1. <span data-ttu-id="4625c-140">Download het installatiebestand van de agent: [Windows 64-bits agent](https://go.microsoft.com/fwlink/?LinkId=828603) of [Windows 32-bits agent.](https://go.microsoft.com/fwlink/?LinkId=828604)</span><span class="sxs-lookup"><span data-stu-id="4625c-140">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603) or [Windows 32-bit agent](https://go.microsoft.com/fwlink/?LinkId=828604).</span></span>

2. <span data-ttu-id="4625c-141">De werkruimte-id verkrijgen:</span><span class="sxs-lookup"><span data-stu-id="4625c-141">Obtain the workspace ID:</span></span>
   - <span data-ttu-id="4625c-142">Selecteer in het navigatiedeelvenster Defender voor eindpunt de optie **Instellingen > Apparaatbeheer > Onboarding**</span><span class="sxs-lookup"><span data-stu-id="4625c-142">In the Defender for Endpoint navigation pane, select **Settings > Device management > Onboarding**</span></span>
   - <span data-ttu-id="4625c-143">Selecteer **Windows 7 SP1 en 8.1** als het besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="4625c-143">Select **Windows 7 SP1 and 8.1** as the operating system</span></span>
   - <span data-ttu-id="4625c-144">De werkruimte-id en -werkruimtecode kopiëren</span><span class="sxs-lookup"><span data-stu-id="4625c-144">Copy the workspace ID and workspace key</span></span>

3. <span data-ttu-id="4625c-145">Kies een van de volgende installatiemethoden om de agent te installeren met behulp van de werkruimte-id en de werkruimtetoets:</span><span class="sxs-lookup"><span data-stu-id="4625c-145">Using the Workspace ID and Workspace key choose any of the following installation methods to install the agent:</span></span>
    - <span data-ttu-id="4625c-146">[Installeer de agent handmatig met installatie](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="4625c-146">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
      <span data-ttu-id="4625c-147">Selecteer op **de pagina Opties voor** agentconfiguratie de optie Verbinding maken met Azure Log Analytics **(OMS)**</span><span class="sxs-lookup"><span data-stu-id="4625c-147">On the **Agent Setup Options** page, select **Connect the agent to Azure Log Analytics (OMS)**</span></span>
    - <span data-ttu-id="4625c-148">[Installeer de agent met de opdrachtregel](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="4625c-148">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="4625c-149">[Configureer de agent met behulp van een script.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)</span><span class="sxs-lookup"><span data-stu-id="4625c-149">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

   > [!NOTE]
   > <span data-ttu-id="4625c-150">Als u een klant van de Amerikaanse overheid bent [,](gov.md)moet u onder 'Azure Cloud' de parameter 'Azure US Government' kiezen als u de installatiewizard gebruikt of als u een opdrachtregel of een script gebruikt. Stel de parameter 'OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE' in op 1.</span><span class="sxs-lookup"><span data-stu-id="4625c-150">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

4. <span data-ttu-id="4625c-151">Zie de sectie Proxyinstellingen configureren als u een proxy gebruikt om verbinding te maken met internet.</span><span class="sxs-lookup"><span data-stu-id="4625c-151">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="4625c-152">Wanneer u klaar bent, ziet u binnen een uur onboarded eindpunten in de portal.</span><span class="sxs-lookup"><span data-stu-id="4625c-152">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="configure-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="4625c-153">Instellingen voor proxy- en internetverbinding configureren</span><span class="sxs-lookup"><span data-stu-id="4625c-153">Configure proxy and Internet connectivity settings</span></span>
 
- <span data-ttu-id="4625c-154">Elk Windows-eindpunt moet verbinding kunnen maken met internet via HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4625c-154">Each Windows endpoint must be able to connect to the Internet using HTTPS.</span></span> <span data-ttu-id="4625c-155">Deze verbinding kan rechtstreeks zijn, met behulp van een proxy of via de [OMS Gateway.](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)</span><span class="sxs-lookup"><span data-stu-id="4625c-155">This connection can be direct, using a proxy, or through the [OMS Gateway](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway).</span></span>
- <span data-ttu-id="4625c-156">Als een proxy of firewall standaard al het verkeer blokkeert en alleen specifieke domeinen via of HTTPS-scannen (SSL-inspectie) is ingeschakeld, moet u ervoor zorgen dat u toegang tot URL's van de Defender voor [Eindpunt-service](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)inschakelen.</span><span class="sxs-lookup"><span data-stu-id="4625c-156">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through or HTTPS scanning (SSL inspection) is enabled, make sure that you [enable access to Defender for Endpoint service URLs](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

## <a name="offboard-client-endpoints"></a><span data-ttu-id="4625c-157">Offboard client-eindpunten</span><span class="sxs-lookup"><span data-stu-id="4625c-157">Offboard client endpoints</span></span>
<span data-ttu-id="4625c-158">Als u offboard wilt, kunt u de MMA-agent van het eindpunt verwijderen of deze loskoppelen van de rapportage naar uw Werkruimte Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="4625c-158">To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="4625c-159">Na het offboarden van de agent verzendt het eindpunt geen sensorgegevens meer naar Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="4625c-159">After offboarding the agent, the endpoint will no longer send sensor data to Defender for Endpoint.</span></span> 

> <span data-ttu-id="4625c-160">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="4625c-160">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="4625c-161">[Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink)</span><span class="sxs-lookup"><span data-stu-id="4625c-161">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span></span>

