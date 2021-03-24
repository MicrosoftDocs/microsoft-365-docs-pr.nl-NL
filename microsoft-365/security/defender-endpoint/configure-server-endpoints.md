---
title: Windows-servers aan boord van de Microsoft Defender voor Eindpunt-service
description: Onboard Windows-servers, zodat ze sensorgegevens kunnen verzenden naar de Microsoft Defender for Endpoint-sensor.
keywords: onboard server, server, 2012r2, 2016, 2019, server onboarding, device management, configure Windows ATP servers, onboard Microsoft Defender for Endpoint servers, onboard Microsoft Defender for Endpoint servers
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: bd92b44892b49a007316acb97296a44514db0578
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057113"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="f654c-104">Windows-servers aan boord van de Microsoft Defender voor Eindpunt-service</span><span class="sxs-lookup"><span data-stu-id="f654c-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f654c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f654c-105">**Applies to:**</span></span>

- <span data-ttu-id="f654c-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="f654c-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="f654c-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f654c-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="f654c-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f654c-108">Windows Server 2016</span></span>
- <span data-ttu-id="f654c-109">Windows Server (SAC) versie 1803 en hoger</span><span class="sxs-lookup"><span data-stu-id="f654c-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="f654c-110">Windows Server 2019 en hoger</span><span class="sxs-lookup"><span data-stu-id="f654c-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="f654c-111">Windows Server 2019 core edition</span><span class="sxs-lookup"><span data-stu-id="f654c-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="f654c-112">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f654c-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f654c-113">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f654c-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)


<span data-ttu-id="f654c-114">Defender voor Eindpunt breidt de ondersteuning uit met het Windows Server-besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="f654c-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="f654c-115">Deze ondersteuning biedt geavanceerde mogelijkheden voor detectie en onderzoek van aanvallen naadloos via de Microsoft Defender-beveiligingscentrumconsole.</span><span class="sxs-lookup"><span data-stu-id="f654c-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="f654c-116">Zie [Windows-servers](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)beveiligen met Defender voor eindpunt voor praktische richtlijnen over wat er moet worden gebruikt voor licenties en infrastructuur.</span><span class="sxs-lookup"><span data-stu-id="f654c-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="f654c-117">Zie [Windows-beveiligingslijnlijnen](https://docs.microsoft.com/windows/device-security/windows-security-baselines)voor informatie over het downloaden en gebruiken van Windows-beveiligingslijnlijnen voor Windows-servers.</span><span class="sxs-lookup"><span data-stu-id="f654c-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span></span>

<br>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="f654c-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2 en Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f654c-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="f654c-119">U kunt Windows Server 2008 R2 SP1, Windows Server 2012 R2 en Windows Server 2016 met behulp van een van de volgende opties aan boord nemen van Defender voor Eindpunt:</span><span class="sxs-lookup"><span data-stu-id="f654c-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="f654c-120">**Optie 1**: [Onboard door Microsoft Monitoring Agent (MMA) te](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) installeren en te configureren</span><span class="sxs-lookup"><span data-stu-id="f654c-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="f654c-121">**Optie 2**: [Onboard via Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="f654c-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="f654c-122">**Optie 3:** [Onboard via Microsoft Endpoint Manager versie 2002 en hoger](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="f654c-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>


<span data-ttu-id="f654c-123">Nadat u de onboarding-stappen hebt doorlopen met een van de opgegeven opties, moet u [System Center Endpoint Protection-clients configureren en bijwerken.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="f654c-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>


> [!NOTE]
> <span data-ttu-id="f654c-124">Defender for Endpoint standalone server license is vereist, per knooppunt, om een Windows-server aan te sluiten via Microsoft Monitoring Agent (Optie 1) of via Microsoft Endpoint Manager (optie 3).</span><span class="sxs-lookup"><span data-stu-id="f654c-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="f654c-125">U kunt ook per knooppunt een Azure Defender for Servers-licentie gebruiken om een Windows-server aan te sluiten via Azure Security Center (optie 2), zie Ondersteunde functies die beschikbaar zijn [in Azure Security Center.](https://docs.microsoft.com/azure/security-center/security-center-services)</span><span class="sxs-lookup"><span data-stu-id="f654c-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-services).</span></span>


### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="f654c-126">Optie 1: Onboard door Microsoft Monitoring Agent (MMA) te installeren en te configureren</span><span class="sxs-lookup"><span data-stu-id="f654c-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>
<span data-ttu-id="f654c-127">U moet MMA voor Windows-servers installeren en configureren om sensorgegevens te rapporteren aan Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="f654c-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="f654c-128">Zie Logboekgegevens verzamelen [met Azure Log Analytics-agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f654c-128">For more information, see [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="f654c-129">Als u System Center Operations Manager (SCOM) of Azure Monitor (voorheen Bekend als Operations Management Suite (OMS) al gebruikt, koppelt u de Microsoft Monitoring Agent (MMA) om via multihoming-ondersteuning te rapporteren aan uw Werkruimte van Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="f654c-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="f654c-130">Over het algemeen moet u de volgende stappen ondernemen:</span><span class="sxs-lookup"><span data-stu-id="f654c-130">In general, you'll need to take the following steps:</span></span>
1. <span data-ttu-id="f654c-131">Voldoe aan de onboarding-vereisten die worden beschreven in **De sectie Voordat u begint.**</span><span class="sxs-lookup"><span data-stu-id="f654c-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="f654c-132">Schakel servercontrole in vanuit het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="f654c-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="f654c-133">Installeer en configureer MMA voor de server om sensorgegevens te rapporteren aan Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="f654c-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="f654c-134">System Center Endpoint Protection-clients configureren en bijwerken.</span><span class="sxs-lookup"><span data-stu-id="f654c-134">Configure and update System Center Endpoint Protection clients.</span></span>


> [!TIP]
> <span data-ttu-id="f654c-135">Nadat u het apparaat hebt onboarding, kunt u ervoor kiezen om een detectietest uit te voeren om te controleren of het apparaat correct is aan boord van de service.</span><span class="sxs-lookup"><span data-stu-id="f654c-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="f654c-136">Zie Een detectietest uitvoeren op een nieuw ingebouwde [Defender voor eindpunten voor meer informatie.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="f654c-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>


#### <a name="before-you-begin"></a><span data-ttu-id="f654c-137">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="f654c-137">Before you begin</span></span> 
<span data-ttu-id="f654c-138">Voer de volgende stappen uit om te voldoen aan de vereisten voor onboarding:</span><span class="sxs-lookup"><span data-stu-id="f654c-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

 - <span data-ttu-id="f654c-139">Voor Windows Server 2008 R2 SP1 of Windows Server 2012 R2 moet u het volgende hotfix installeren:</span><span class="sxs-lookup"><span data-stu-id="f654c-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>
    - [<span data-ttu-id="f654c-140">Bijwerken voor klantervaring en diagnostische telemetrie</span><span class="sxs-lookup"><span data-stu-id="f654c-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

 - <span data-ttu-id="f654c-141">Zorg er bovendien voor Windows Server 2008 R2 SP1 voor dat u aan de volgende vereisten voldoet:</span><span class="sxs-lookup"><span data-stu-id="f654c-141">In addition, for Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>
    - <span data-ttu-id="f654c-142">De maandelijkse [update-rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598) van februari installeren</span><span class="sxs-lookup"><span data-stu-id="f654c-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
    - <span data-ttu-id="f654c-143">Installeer [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (of hoger) of [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="f654c-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

 - <span data-ttu-id="f654c-144">Voor Windows Server 2008 R2 SP1 en Windows Server 2012 R2: [System Center Endpoint Protection-clients configureren en bijwerken.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="f654c-144">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

    > [!NOTE]
    > <span data-ttu-id="f654c-145">Deze stap is alleen vereist als uw organisatie System Center Endpoint Protection (SCEP) gebruikt en u Windows Server 2008 R2 SP1 en Windows Server 2012 R2 onboardt.</span><span class="sxs-lookup"><span data-stu-id="f654c-145">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>


<span id="server-mma"/>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="f654c-146">Microsoft Monitoring Agent (MMA) installeren en configureren om sensorgegevens te rapporteren aan Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f654c-146">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="f654c-147">Download het installatiebestand van de agent: [Windows 64-bits agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span><span class="sxs-lookup"><span data-stu-id="f654c-147">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="f654c-148">Kies een van de volgende installatiemethoden om de agent op de Windows-server te installeren met behulp van de werkruimte-id en de werkruimtesleutel die in de vorige procedure is verkregen:</span><span class="sxs-lookup"><span data-stu-id="f654c-148">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="f654c-149">[Installeer de agent handmatig met installatie](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="f654c-149">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
    <span data-ttu-id="f654c-150">Kies op **de pagina Opties voor** agentconfiguratie de optie Verbinding maken met Azure Log Analytics **(OMS)**.</span><span class="sxs-lookup"><span data-stu-id="f654c-150">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="f654c-151">[Installeer de agent met de opdrachtregel](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="f654c-151">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="f654c-152">[Configureer de agent met behulp van een script.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)</span><span class="sxs-lookup"><span data-stu-id="f654c-152">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="f654c-153">Als u een klant van de Amerikaanse overheid bent [,](gov.md)moet u onder 'Azure Cloud' de parameter 'Azure US Government' kiezen als u de installatiewizard gebruikt of als u een opdrachtregel of een script gebruikt. Stel de parameter 'OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE' in op 1.</span><span class="sxs-lookup"><span data-stu-id="f654c-153">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>


<span id="server-proxy"/>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="f654c-154">Instellingen voor Windows-serverproxy en internetverbinding configureren indien nodig</span><span class="sxs-lookup"><span data-stu-id="f654c-154">Configure Windows server proxy and Internet connectivity settings if needed</span></span>
<span data-ttu-id="f654c-155">Als uw servers een proxy moeten gebruiken om te communiceren met Defender voor Eindpunt, gebruikt u een van de volgende methoden om de MMA te configureren voor het gebruik van de proxyserver:</span><span class="sxs-lookup"><span data-stu-id="f654c-155">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>


- [<span data-ttu-id="f654c-156">De MMA configureren voor het gebruik van een proxyserver</span><span class="sxs-lookup"><span data-stu-id="f654c-156">Configure the MMA to use a proxy server</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="f654c-157">Windows configureren voor het gebruik van een proxyserver voor alle verbindingen</span><span class="sxs-lookup"><span data-stu-id="f654c-157">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="f654c-158">Als er een proxy of firewall wordt gebruikt, moet u ervoor zorgen dat servers rechtstreeks en zonder SSL-interceptie toegang hebben tot alle URL's van de Microsoft Defender-service voor eindpunten.</span><span class="sxs-lookup"><span data-stu-id="f654c-158">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="f654c-159">Zie Access to [Defender for Endpoint service URL's inschakelen](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f654c-159">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="f654c-160">Het gebruik van SSL-onderschepping voorkomt dat het systeem communiceert met de Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="f654c-160">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span> 

<span data-ttu-id="f654c-161">Wanneer u klaar bent, ziet u binnen een uur onboarded Windows-servers in de portal.</span><span class="sxs-lookup"><span data-stu-id="f654c-161">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="f654c-162">Optie 2: Onboard Windows-servers via Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="f654c-162">Option 2: Onboard Windows servers through Azure Security Center</span></span>
1. <span data-ttu-id="f654c-163">Selecteer in het navigatiedeelvenster van het Microsoft Defender-beveiligingscentrum de optie **Instellingen**  >  **Apparaatbeheer**  >  **Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="f654c-163">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="f654c-164">Selecteer **Windows Server 2008 R2 SP1, 2012 R2 en 2016** als het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="f654c-164">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="f654c-165">Klik **op Onboard Servers in Azure Security Center**.</span><span class="sxs-lookup"><span data-stu-id="f654c-165">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="f654c-166">Volg de onboarding-instructies in [Microsoft Defender voor Eindpunt met Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp).</span><span class="sxs-lookup"><span data-stu-id="f654c-166">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp).</span></span>

<span data-ttu-id="f654c-167">Nadat u de onboarding-stappen hebt doorlopen, moet u [System Center Endpoint Protection-clients configureren en bijwerken.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="f654c-167">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> - <span data-ttu-id="f654c-168">Als onboarding via Azure Defender voor Servers (voorheen Azure Security Center Standard Edition) naar verwachting werkt, moet de server een geschikte werkruimte en sleutel hebben die is geconfigureerd binnen de MMA-instellingen (Microsoft Monitoring Agent).</span><span class="sxs-lookup"><span data-stu-id="f654c-168">For onboarding via Azure Defender for Servers (previously Azure Security Center Standard Edition) to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="f654c-169">Nadat de configuratie is geconfigureerd, wordt het juiste cloudbeheerpakket op de computer geïmplementeerd en wordt het sensorproces (MsSenseS.exe) geïmplementeerd en gestart.</span><span class="sxs-lookup"><span data-stu-id="f654c-169">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span> 
> - <span data-ttu-id="f654c-170">Dit is ook vereist als de server is geconfigureerd voor het gebruik van een OMS Gateway-server als proxy.</span><span class="sxs-lookup"><span data-stu-id="f654c-170">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="f654c-171">Optie 3: Windows-servers inschakelen via Microsoft Endpoint Manager versie 2002 en hoger</span><span class="sxs-lookup"><span data-stu-id="f654c-171">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>
<span data-ttu-id="f654c-172">U kunt Windows Server 2012 R2 en Windows Server 2016 inschakelen met Microsoft Endpoint Manager versie 2002 en hoger.</span><span class="sxs-lookup"><span data-stu-id="f654c-172">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="f654c-173">Zie Microsoft [Defender for Endpoint in Microsoft Endpoint Manager current branch (Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch) voor meer informatie.](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="f654c-173">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="f654c-174">Nadat u de onboarding-stappen hebt doorlopen, moet u [System Center Endpoint Protection-clients configureren en bijwerken.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="f654c-174">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

<br>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="f654c-175">Windows Server (SAC) versie 1803, Windows Server 2019 en Windows Server 2019 Core edition</span><span class="sxs-lookup"><span data-stu-id="f654c-175">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>
<span data-ttu-id="f654c-176">U kunt windows Server-versie 1803, Windows Server 2019 of Windows Server 2019 Core edition inschakelen met behulp van de volgende implementatiemethoden:</span><span class="sxs-lookup"><span data-stu-id="f654c-176">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="f654c-177">Lokaal script</span><span class="sxs-lookup"><span data-stu-id="f654c-177">Local script</span></span>](configure-endpoints-script.md) 
- [<span data-ttu-id="f654c-178">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="f654c-178">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="f654c-179">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f654c-179">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="f654c-180">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="f654c-180">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="f654c-181">VDI-onboarding-scripts voor niet-permanente apparaten</span><span class="sxs-lookup"><span data-stu-id="f654c-181">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
> - <span data-ttu-id="f654c-182">Het Onboarding-pakket voor Windows Server 2019 tot en met Microsoft Endpoint Manager verzendt momenteel een script.</span><span class="sxs-lookup"><span data-stu-id="f654c-182">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="f654c-183">Zie Pakketten en programma's in Configuration Manager voor meer informatie over het implementeren van scripts [in Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="f654c-183">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="f654c-184">Een lokaal script is geschikt voor een proof of concept, maar mag niet worden gebruikt voor productie-implementatie.</span><span class="sxs-lookup"><span data-stu-id="f654c-184">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="f654c-185">Voor een productie-implementatie wordt aangeraden groepsbeleid of Microsoft Endpoint Configuration Manager te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f654c-185">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="f654c-186">Ondersteuning voor Windows Server biedt meer inzicht in serveractiviteiten, dekking voor detectie van kernel- en geheugenaanval en maakt reactieacties mogelijk.</span><span class="sxs-lookup"><span data-stu-id="f654c-186">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="f654c-187">Configureer instellingen voor onboarding van Defender voor eindpunten op de Windows-server met dezelfde hulpmiddelen en methoden voor Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="f654c-187">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="f654c-188">Zie Onboard [Windows 10-apparaten](configure-endpoints.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f654c-188">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="f654c-189">Als u een antimalwareoplossing van derden gebruikt, moet u de volgende instellingen voor de passieve av-modus van Microsoft Defender toepassen.</span><span class="sxs-lookup"><span data-stu-id="f654c-189">If you're running a third-party antimalware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="f654c-190">Controleer of deze correct is geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="f654c-190">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="f654c-191">Stel de volgende registerinvoer in:</span><span class="sxs-lookup"><span data-stu-id="f654c-191">Set the following registry entry:</span></span>
       - <span data-ttu-id="f654c-192">Pad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="f654c-192">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="f654c-193">Naam: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="f654c-193">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="f654c-194">Type: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="f654c-194">Type: REG_DWORD</span></span>
       - <span data-ttu-id="f654c-195">Waarde: 1</span><span class="sxs-lookup"><span data-stu-id="f654c-195">Value: 1</span></span>

    1. <span data-ttu-id="f654c-196">Voer de volgende PowerShell-opdracht uit om te controleren of de passieve modus is geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="f654c-196">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="f654c-197">Controleer of er een recente gebeurtenis met de gebeurtenis in de passieve modus is gevonden:</span><span class="sxs-lookup"><span data-stu-id="f654c-197">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![Afbeelding van het resultaat van verificatie in de passieve modus](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="f654c-199">Voer de volgende opdracht uit om te controleren of Microsoft Defender AV is geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="f654c-199">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="f654c-200">Als het resultaat 'De opgegeven service bestaat niet als een geïnstalleerde service' is, moet u Microsoft Defender AV installeren.</span><span class="sxs-lookup"><span data-stu-id="f654c-200">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="f654c-201">Zie Microsoft [Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f654c-201">For more information, see [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>
    
    <span data-ttu-id="f654c-202">Zie Groepsbeleidsinstellingen gebruiken om Microsoft Defender Antivirus te configureren en te beheren voor informatie over het gebruik van groepsbeleid voor het configureren en beheren van Microsoft Defender Antivirus op uw [Windows-servers.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="f654c-202">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

<br>

## <a name="integration-with-azure-security-center"></a><span data-ttu-id="f654c-203">Integratie met Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="f654c-203">Integration with Azure Security Center</span></span>
<span data-ttu-id="f654c-204">Defender voor Eindpunt kan worden geïntegreerd met Azure Security Center om een uitgebreide windows-serverbeveiligingsoplossing te bieden.</span><span class="sxs-lookup"><span data-stu-id="f654c-204">Defender for Endpoint can integrate with Azure Security Center to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="f654c-205">Met deze integratie kan Azure Security Center de kracht van Defender voor Eindpunt gebruiken om een verbeterde detectie van bedreigingen voor Windows-servers te bieden.</span><span class="sxs-lookup"><span data-stu-id="f654c-205">With this integration, Azure Security Center can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="f654c-206">De volgende mogelijkheden zijn opgenomen in deze integratie:</span><span class="sxs-lookup"><span data-stu-id="f654c-206">The following capabilities are included in this integration:</span></span>
- <span data-ttu-id="f654c-207">Geautomatiseerde onboarding- Defender voor eindpunten-sensor wordt automatisch ingeschakeld op Windows-servers die zijn onboarded bij Azure Security Center.</span><span class="sxs-lookup"><span data-stu-id="f654c-207">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Security Center.</span></span> <span data-ttu-id="f654c-208">Zie [Onboarding to Azure Security Center Standard for enhanced security (Onboarding to Azure Security Center Standard for enhanced security)](https://docs.microsoft.com/azure/security-center/security-center-onboarding)voor meer informatie over onboarding van Azure Security Center.</span><span class="sxs-lookup"><span data-stu-id="f654c-208">For more information on Azure Security Center onboarding, see [Onboarding to Azure Security Center Standard for enhanced security](https://docs.microsoft.com/azure/security-center/security-center-onboarding).</span></span>

    > [!NOTE]
    > <span data-ttu-id="f654c-209">Geautomatiseerde onboarding is alleen van toepassing Windows Server 2008 R2 SP1, Windows Server 2012 R2 en Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="f654c-209">Automated onboarding is only applicable for Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016.</span></span>

- <span data-ttu-id="f654c-210">Windows-servers die worden gecontroleerd door Azure Security Center, zijn ook beschikbaar in Defender voor Eindpunt- Azure Security Center maakt naadloos verbinding met de Defender for Endpoint-tenant, met één weergave voor clients en servers.</span><span class="sxs-lookup"><span data-stu-id="f654c-210">Windows servers monitored by Azure Security Center will also be available in Defender for Endpoint - Azure Security Center seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="f654c-211">Daarnaast zijn defender voor eindpuntwaarschuwingen beschikbaar in de Azure Security Center-console.</span><span class="sxs-lookup"><span data-stu-id="f654c-211">In addition, Defender for Endpoint alerts will be available in the Azure Security Center console.</span></span>
- <span data-ttu-id="f654c-212">Serveronderzoek: klanten van het Azure Security Center hebben toegang tot het Microsoft Defender-beveiligingscentrum om gedetailleerd onderzoek uit te voeren om het bereik van een mogelijke inbreuk te achterhalen.</span><span class="sxs-lookup"><span data-stu-id="f654c-212">Server investigation -  Azure Security Center customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="f654c-213">Wanneer u Azure Security Center gebruikt om servers te controleren, wordt automatisch een Defender for Endpoint-tenant gemaakt (in de VS voor Amerikaanse gebruikers, in de EU voor Europese en Britse gebruikers).</span><span class="sxs-lookup"><span data-stu-id="f654c-213">When you use Azure Security Center to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="f654c-214">Gegevens die door Defender voor Eindpunt worden verzameld, worden opgeslagen op de geografische locatie van de tenant die tijdens de inrichting is geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="f654c-214">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="f654c-215">Als u Defender voor Eindpunt gebruikt voordat u Azure Security Center gebruikt, worden uw gegevens opgeslagen op de locatie die u hebt opgegeven toen u uw tenant maakte, zelfs als u op een later tijdstip integreert met Azure Security Center.</span><span class="sxs-lookup"><span data-stu-id="f654c-215">If you use Defender for Endpoint before using Azure Security Center, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Security Center at a later time.</span></span>
> - <span data-ttu-id="f654c-216">Nadat de gegevens zijn geconfigureerd, kunt u de locatie waarop uw gegevens zijn opgeslagen niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="f654c-216">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="f654c-217">Als u uw gegevens naar een andere locatie wilt verplaatsen, moet u contact opnemen met Microsoft Support om de tenant opnieuw in te stellen.</span><span class="sxs-lookup"><span data-stu-id="f654c-217">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="f654c-218">Server-eindpuntcontrole met behulp van deze integratie is uitgeschakeld voor Office 365 GCC-klanten.</span><span class="sxs-lookup"><span data-stu-id="f654c-218">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

<br>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="f654c-219">System Center Endpoint Protection-clients configureren en bijwerken</span><span class="sxs-lookup"><span data-stu-id="f654c-219">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="f654c-220">Defender for Endpoint is geïntegreerd met System Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="f654c-220">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="f654c-221">De integratie biedt zichtbaarheid voor malwaredetecties en om de verspreiding van een aanval in uw organisatie te stoppen door potentieel schadelijke bestanden of verdachte malware te verbieden.</span><span class="sxs-lookup"><span data-stu-id="f654c-221">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="f654c-222">De volgende stappen zijn vereist om deze integratie mogelijk te maken:</span><span class="sxs-lookup"><span data-stu-id="f654c-222">The following steps are required to enable this integration:</span></span>
- <span data-ttu-id="f654c-223">Installeer de update van het anti-malwareplatform van januari [2017 voor endpoint protection-clients.](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="f654c-223">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="f654c-224">[Configureer het lidmaatschap van de SCEP-client Cloud Protection Service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) op **de instelling Geavanceerd.**</span><span class="sxs-lookup"><span data-stu-id="f654c-224">[Configure the SCEP client Cloud Protection Service membership](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

<br>

## <a name="offboard-windows-servers"></a><span data-ttu-id="f654c-225">Offboard Windows-servers</span><span class="sxs-lookup"><span data-stu-id="f654c-225">Offboard Windows servers</span></span>
<span data-ttu-id="f654c-226">U kunt Windows Server (SAC), Windows Server 2019 en Windows Server 2019 Core edition offboarden volgens dezelfde methode die beschikbaar is voor Windows 10-clientapparaten.</span><span class="sxs-lookup"><span data-stu-id="f654c-226">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="f654c-227">Voor andere Windows-serverversies hebt u twee opties voor offboard Windows-servers van de service:</span><span class="sxs-lookup"><span data-stu-id="f654c-227">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>
- <span data-ttu-id="f654c-228">De MMA-agent verwijderen</span><span class="sxs-lookup"><span data-stu-id="f654c-228">Uninstall the MMA agent</span></span>
- <span data-ttu-id="f654c-229">De configuratie van de Defender voor Eindpunt-werkruimte verwijderen</span><span class="sxs-lookup"><span data-stu-id="f654c-229">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="f654c-230">Offboarding zorgt ervoor dat de Windows-server stopt met het verzenden van sensorgegevens naar de portal, maar gegevens van de Windows-server, inclusief verwijzingen naar eventuele waarschuwingen die de server heeft ontvangen, blijven maximaal 6 maanden bewaard.</span><span class="sxs-lookup"><span data-stu-id="f654c-230">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="f654c-231">Windows-servers verwijderen door de MMA-agent te verwijderen</span><span class="sxs-lookup"><span data-stu-id="f654c-231">Uninstall Windows servers by uninstalling the MMA agent</span></span>
<span data-ttu-id="f654c-232">Als u de Windows-server wilt offboarden, kunt u de MMA-agent van de Windows-server verwijderen of loskoppelen van rapportage naar uw Defender voor Eindpunt-werkruimte.</span><span class="sxs-lookup"><span data-stu-id="f654c-232">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="f654c-233">Na het offboarden van de agent verzendt de Windows-server geen sensorgegevens meer naar Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="f654c-233">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="f654c-234">Zie Een agent uitschakelen voor [meer informatie.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)</span><span class="sxs-lookup"><span data-stu-id="f654c-234">For more information, see [To disable an agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="f654c-235">De configuratie van de Defender voor Eindpunt-werkruimte verwijderen</span><span class="sxs-lookup"><span data-stu-id="f654c-235">Remove the Defender for Endpoint workspace configuration</span></span>
<span data-ttu-id="f654c-236">Als u de Windows-server wilt uitschakelen, kunt u een van de volgende methoden gebruiken:</span><span class="sxs-lookup"><span data-stu-id="f654c-236">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="f654c-237">De configuratie van de Defender voor eindpuntwerkruimte verwijderen uit de MMA-agent</span><span class="sxs-lookup"><span data-stu-id="f654c-237">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="f654c-238">Een PowerShell-opdracht uitvoeren om de configuratie te verwijderen</span><span class="sxs-lookup"><span data-stu-id="f654c-238">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="f654c-239">De configuratie van de Defender voor eindpuntwerkruimte verwijderen uit de MMA-agent</span><span class="sxs-lookup"><span data-stu-id="f654c-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="f654c-240">Selecteer op **het tabblad Microsoft Monitoring Agent Properties** het tabblad Azure Log Analytics **(OMS).**</span><span class="sxs-lookup"><span data-stu-id="f654c-240">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="f654c-241">Selecteer de werkruimte Defender voor eindpunt en klik op **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="f654c-241">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Afbeelding van Eigenschappen van Microsoft Monitoring Agent](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="f654c-243">Een PowerShell-opdracht uitvoeren om de configuratie te verwijderen</span><span class="sxs-lookup"><span data-stu-id="f654c-243">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="f654c-244">Uw werkruimte-id krijgen:</span><span class="sxs-lookup"><span data-stu-id="f654c-244">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="f654c-245">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="f654c-245">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="f654c-246">Selecteer **Windows Server 2008 R2 SP1, 2012 R2 en 2016** als het besturingssysteem en ontvang uw werkruimte-id:</span><span class="sxs-lookup"><span data-stu-id="f654c-246">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Afbeelding van windows-server onboarding](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="f654c-248">Open een verhoogde PowerShell en voer de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="f654c-248">Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id="f654c-249">Gebruik de werkruimte-id die u hebt verkregen en `WorkspaceID` vervangt:</span><span class="sxs-lookup"><span data-stu-id="f654c-249">Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = "SilentlyContinue"
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace("WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

<br>

## <a name="related-topics"></a><span data-ttu-id="f654c-250">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f654c-250">Related topics</span></span>
- [<span data-ttu-id="f654c-251">Onboard Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="f654c-251">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="f654c-252">Onboard niet-Windows-apparaten</span><span class="sxs-lookup"><span data-stu-id="f654c-252">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="f654c-253">Instellingen voor proxy- en internetverbinding configureren</span><span class="sxs-lookup"><span data-stu-id="f654c-253">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="f654c-254">Een detectietest uitvoeren op een nieuw ingebouwde Defender voor eindpuntapparaat</span><span class="sxs-lookup"><span data-stu-id="f654c-254">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="f654c-255">Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen</span><span class="sxs-lookup"><span data-stu-id="f654c-255">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
