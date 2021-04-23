---
title: Windows-servers aan boord van de Microsoft Defender voor Eindpunt-service
description: Onboard Windows-servers, zodat ze sensorgegevens kunnen verzenden naar de Microsoft Defender for Endpoint-sensor.
keywords: onboard server, server, 2012r2, 2016, 2019, server onboarding, device management, configure Microsoft Defender for Endpoint servers, onboard Microsoft Defender for Endpoint servers, onboard Microsoft Defender for Endpoint servers
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
ms.openlocfilehash: 17aca5fb388aef26504902ee63b22410420c8827
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952486"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="51946-104">Windows-servers aan boord van de Microsoft Defender voor Eindpunt-service</span><span class="sxs-lookup"><span data-stu-id="51946-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="51946-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="51946-105">**Applies to:**</span></span>

- <span data-ttu-id="51946-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="51946-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="51946-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="51946-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="51946-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="51946-108">Windows Server 2016</span></span>
- <span data-ttu-id="51946-109">Windows Server (SAC) versie 1803 en hoger</span><span class="sxs-lookup"><span data-stu-id="51946-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="51946-110">Windows Server 2019 en hoger</span><span class="sxs-lookup"><span data-stu-id="51946-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="51946-111">Windows Server 2019 core edition</span><span class="sxs-lookup"><span data-stu-id="51946-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="51946-112">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="51946-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="51946-113">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="51946-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)

<span data-ttu-id="51946-114">Defender voor Eindpunt breidt de ondersteuning uit met het Windows Server-besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="51946-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="51946-115">Deze ondersteuning biedt geavanceerde mogelijkheden voor detectie en onderzoek van aanvallen naadloos via de Microsoft Defender-beveiligingscentrumconsole.</span><span class="sxs-lookup"><span data-stu-id="51946-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="51946-116">Zie [Windows-servers](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)beveiligen met Defender voor eindpunt voor praktische richtlijnen over wat er moet worden gebruikt voor licenties en infrastructuur.</span><span class="sxs-lookup"><span data-stu-id="51946-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="51946-117">Zie [Windows-beveiligingslijnlijnen](https://docs.microsoft.com/windows/device-security/windows-security-baselines)voor informatie over het downloaden en gebruiken van Windows-beveiligingslijnlijnen voor Windows-servers.</span><span class="sxs-lookup"><span data-stu-id="51946-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span></span>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="51946-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2 en Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="51946-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="51946-119">U kunt Windows Server 2008 R2 SP1, Windows Server 2012 R2 en Windows Server 2016 met behulp van een van de volgende opties aan boord nemen van Defender voor Eindpunt:</span><span class="sxs-lookup"><span data-stu-id="51946-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="51946-120">**Optie 1**: [Onboard door Microsoft Monitoring Agent (MMA) te](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma) installeren en te configureren</span><span class="sxs-lookup"><span data-stu-id="51946-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="51946-121">**Optie 2**: [Onboard via Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="51946-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="51946-122">**Optie 3:** [Onboard via Microsoft Endpoint Manager versie 2002 en hoger](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="51946-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>

<span data-ttu-id="51946-123">Nadat u de onboarding-stappen hebt doorlopen met een van de opgegeven opties, moet u [System Center Endpoint Protection-clients configureren en bijwerken.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="51946-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="51946-124">Defender for Endpoint standalone server license is vereist, per knooppunt, om een Windows-server aan te sluiten via Microsoft Monitoring Agent (Optie 1) of via Microsoft Endpoint Manager (optie 3).</span><span class="sxs-lookup"><span data-stu-id="51946-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="51946-125">U kunt ook per knooppunt een Azure Defender for Servers-licentie gebruiken om een Windows-server aan te sluiten via Azure Security Center (optie 2), zie Ondersteunde functies die beschikbaar zijn [in Azure Defender.](https://docs.microsoft.com/azure/security-center/security-center-services)</span><span class="sxs-lookup"><span data-stu-id="51946-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-services).</span></span>

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="51946-126">Optie 1: Onboard door Microsoft Monitoring Agent (MMA) te installeren en te configureren</span><span class="sxs-lookup"><span data-stu-id="51946-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>

<span data-ttu-id="51946-127">U moet MMA voor Windows-servers installeren en configureren om sensorgegevens te rapporteren aan Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="51946-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="51946-128">Zie Logboekgegevens verzamelen [met Azure Log Analytics-agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="51946-128">For more information, see [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="51946-129">Als u System Center Operations Manager (SCOM) of Azure Monitor (voorheen Bekend als Operations Management Suite (OMS) al gebruikt, koppelt u de Microsoft Monitoring Agent (MMA) om via multihoming-ondersteuning te rapporteren aan uw Werkruimte van Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="51946-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="51946-130">Over het algemeen moet u de volgende stappen ondernemen:</span><span class="sxs-lookup"><span data-stu-id="51946-130">In general, you'll need to take the following steps:</span></span>

1. <span data-ttu-id="51946-131">Voldoe aan de onboarding-vereisten die worden beschreven in **De sectie Voordat u begint.**</span><span class="sxs-lookup"><span data-stu-id="51946-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="51946-132">Schakel servercontrole in vanuit het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="51946-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="51946-133">Installeer en configureer MMA voor de server om sensorgegevens te rapporteren aan Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="51946-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="51946-134">System Center Endpoint Protection-clients configureren en bijwerken.</span><span class="sxs-lookup"><span data-stu-id="51946-134">Configure and update System Center Endpoint Protection clients.</span></span>

> [!TIP]
> <span data-ttu-id="51946-135">Nadat u het apparaat hebt onboarding, kunt u ervoor kiezen om een detectietest uit te voeren om te controleren of het apparaat correct is aan boord van de service.</span><span class="sxs-lookup"><span data-stu-id="51946-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="51946-136">Zie Een detectietest uitvoeren op een nieuw ingebouwde [Defender voor eindpunten voor meer informatie.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="51946-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="51946-137">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="51946-137">Before you begin</span></span>

<span data-ttu-id="51946-138">Voer de volgende stappen uit om te voldoen aan de vereisten voor onboarding:</span><span class="sxs-lookup"><span data-stu-id="51946-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

<span data-ttu-id="51946-139">Voor Windows Server 2008 R2 SP1 of Windows Server 2012 R2 moet u het volgende hotfix installeren:</span><span class="sxs-lookup"><span data-stu-id="51946-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>

- [<span data-ttu-id="51946-140">Bijwerken voor klantervaring en diagnostische telemetrie</span><span class="sxs-lookup"><span data-stu-id="51946-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

<span data-ttu-id="51946-141">Controleer Windows Server 2008 R2 SP1 of u aan de volgende vereisten voldoet:</span><span class="sxs-lookup"><span data-stu-id="51946-141">For Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="51946-142">De maandelijkse [update-rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598) van februari installeren</span><span class="sxs-lookup"><span data-stu-id="51946-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
- <span data-ttu-id="51946-143">Installeer [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (of hoger) of [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="51946-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="51946-144">Als u uw Windows Server 2008 R2 SP1 met SCCM beheert, installeert de SCCM-clientagent .Net Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="51946-144">If you are managing your Windows Server 2008 R2 SP1 with SCCM, the SCCM client agent installs .Net Framework 4.5.2.</span></span> <span data-ttu-id="51946-145">U hoeft dus het .NET framework 4.5 (of hoger) niet te installeren.</span><span class="sxs-lookup"><span data-stu-id="51946-145">So you don't need to install the .NET framework 4.5 (or later).</span></span>

<span data-ttu-id="51946-146">Voor Windows Server 2008 R2 SP1 en Windows Server 2012 R2: [System Center Endpoint Protection-clients configureren en bijwerken.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="51946-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="51946-147">Deze stap is alleen vereist als uw organisatie System Center Endpoint Protection (SCEP) gebruikt en u Windows Server 2008 R2 SP1 en Windows Server 2012 R2 onboardt.</span><span class="sxs-lookup"><span data-stu-id="51946-147">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="51946-148">Microsoft Monitoring Agent (MMA) installeren en configureren om sensorgegevens te rapporteren aan Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="51946-148">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="51946-149">Download het installatiebestand van de agent: [Windows 64-bits agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span><span class="sxs-lookup"><span data-stu-id="51946-149">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="51946-150">Kies een van de volgende installatiemethoden om de agent op de Windows-server te installeren met behulp van de werkruimte-id en de werkruimtesleutel die in de vorige procedure is verkregen:</span><span class="sxs-lookup"><span data-stu-id="51946-150">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="51946-151">[Installeer de agent handmatig met installatie](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="51946-151">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> 
    <span data-ttu-id="51946-152">Kies op **de pagina Opties voor** agentconfiguratie de optie Verbinding maken met Azure Log Analytics **(OMS)**.</span><span class="sxs-lookup"><span data-stu-id="51946-152">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="51946-153">[Installeer de agent met de opdrachtregel](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="51946-153">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="51946-154">[Configureer de agent met behulp van een script.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation)</span><span class="sxs-lookup"><span data-stu-id="51946-154">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="51946-155">Als u een klant van de Amerikaanse overheid bent [,](gov.md)moet u onder 'Azure Cloud' de parameter 'Azure US Government' kiezen als u de installatiewizard gebruikt of als u een opdrachtregel of een script gebruikt. Stel de parameter 'OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE' in op 1.</span><span class="sxs-lookup"><span data-stu-id="51946-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="51946-156">Instellingen voor Windows-serverproxy en internetverbinding configureren indien nodig</span><span class="sxs-lookup"><span data-stu-id="51946-156">Configure Windows server proxy and Internet connectivity settings if needed</span></span>

<span data-ttu-id="51946-157">Als uw servers een proxy moeten gebruiken om te communiceren met Defender voor Eindpunt, gebruikt u een van de volgende methoden om de MMA te configureren voor het gebruik van de proxyserver:</span><span class="sxs-lookup"><span data-stu-id="51946-157">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>

- [<span data-ttu-id="51946-158">De MMA configureren voor het gebruik van een proxyserver</span><span class="sxs-lookup"><span data-stu-id="51946-158">Configure the MMA to use a proxy server</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="51946-159">Windows configureren voor het gebruik van een proxyserver voor alle verbindingen</span><span class="sxs-lookup"><span data-stu-id="51946-159">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="51946-160">Als er een proxy of firewall wordt gebruikt, moet u ervoor zorgen dat servers rechtstreeks en zonder SSL-interceptie toegang hebben tot alle URL's van de Microsoft Defender-service voor eindpunten.</span><span class="sxs-lookup"><span data-stu-id="51946-160">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="51946-161">Zie Access to [Defender for Endpoint service URL's inschakelen](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="51946-161">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="51946-162">Het gebruik van SSL-onderschepping voorkomt dat het systeem communiceert met de Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="51946-162">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span>

<span data-ttu-id="51946-163">Wanneer u klaar bent, ziet u binnen een uur onboarded Windows-servers in de portal.</span><span class="sxs-lookup"><span data-stu-id="51946-163">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="51946-164">Optie 2: Onboard Windows-servers via Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="51946-164">Option 2: Onboard Windows servers through Azure Security Center</span></span>

1. <span data-ttu-id="51946-165">Selecteer in het navigatiedeelvenster van het Microsoft Defender-beveiligingscentrum de optie **Instellingen**  >  **Apparaatbeheer**  >  **Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="51946-165">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="51946-166">Selecteer **Windows Server 2008 R2 SP1, 2012 R2 en 2016** als het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="51946-166">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="51946-167">Klik **op Onboard Servers in Azure Security Center**.</span><span class="sxs-lookup"><span data-stu-id="51946-167">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="51946-168">Volg de onboarding-instructies in [Microsoft Defender voor](https://docs.microsoft.com/azure/security-center/security-center-wdatp) Eindpunt met Azure Defender en Als u Azure ARC gebruikt, volgt u de onboarding-instructies in Microsoft Defender voor [endpoint-integratie inschakelen.](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)</span><span class="sxs-lookup"><span data-stu-id="51946-168">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and If you are using Azure ARC, Follow the onboarding instructions in [Enabling the Microsoft Defender for Endpoint integration](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).</span></span>

<span data-ttu-id="51946-169">Nadat u de onboarding-stappen hebt doorlopen, moet u [System Center Endpoint Protection-clients configureren en bijwerken.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="51946-169">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="51946-170">Als onboarding via Azure Defender voor servers naar verwachting werkt, moet de server een geschikte werkruimte en sleutel hebben die is geconfigureerd binnen de MMA-instellingen (Microsoft Monitoring Agent).</span><span class="sxs-lookup"><span data-stu-id="51946-170">For onboarding via Azure Defender for Servers to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="51946-171">Nadat de configuratie is geconfigureerd, wordt het juiste cloudbeheerpakket op de computer geïmplementeerd en wordt het sensorproces (MsSenseS.exe) geïmplementeerd en gestart.</span><span class="sxs-lookup"><span data-stu-id="51946-171">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span>
> - <span data-ttu-id="51946-172">Dit is ook vereist als de server is geconfigureerd voor het gebruik van een OMS Gateway-server als proxy.</span><span class="sxs-lookup"><span data-stu-id="51946-172">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="51946-173">Optie 3: Windows-servers inschakelen via Microsoft Endpoint Manager versie 2002 en hoger</span><span class="sxs-lookup"><span data-stu-id="51946-173">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>

<span data-ttu-id="51946-174">U kunt Windows Server 2012 R2 en Windows Server 2016 inschakelen met Microsoft Endpoint Manager versie 2002 en hoger.</span><span class="sxs-lookup"><span data-stu-id="51946-174">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="51946-175">Zie Microsoft [Defender for Endpoint in Microsoft Endpoint Manager current branch (Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch) voor meer informatie.](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="51946-175">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="51946-176">Nadat u de onboarding-stappen hebt doorlopen, moet u [System Center Endpoint Protection-clients configureren en bijwerken.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="51946-176">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="51946-177">Windows Server (SAC) versie 1803, Windows Server 2019 en Windows Server 2019 Core edition</span><span class="sxs-lookup"><span data-stu-id="51946-177">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>

<span data-ttu-id="51946-178">U kunt windows Server-versie 1803, Windows Server 2019 of Windows Server 2019 Core edition inschakelen met behulp van de volgende implementatiemethoden:</span><span class="sxs-lookup"><span data-stu-id="51946-178">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="51946-179">Lokaal script</span><span class="sxs-lookup"><span data-stu-id="51946-179">Local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="51946-180">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="51946-180">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="51946-181">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="51946-181">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="51946-182">System Center Configuration Manager 2012 / 2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="51946-182">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="51946-183">VDI-onboarding-scripts voor niet-permanente apparaten</span><span class="sxs-lookup"><span data-stu-id="51946-183">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
>
> - <span data-ttu-id="51946-184">Het Onboarding-pakket voor Windows Server 2019 tot en met Microsoft Endpoint Manager verzendt momenteel een script.</span><span class="sxs-lookup"><span data-stu-id="51946-184">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="51946-185">Zie Pakketten en programma's in Configuration Manager voor meer informatie over het implementeren van scripts [in Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="51946-185">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="51946-186">Een lokaal script is geschikt voor een proof of concept, maar mag niet worden gebruikt voor productie-implementatie.</span><span class="sxs-lookup"><span data-stu-id="51946-186">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="51946-187">Voor een productie-implementatie wordt aangeraden groepsbeleid of Microsoft Endpoint Configuration Manager te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="51946-187">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="51946-188">Ondersteuning voor Windows Server biedt meer inzicht in serveractiviteiten, dekking voor detectie van kernel- en geheugenaanval en maakt reactieacties mogelijk.</span><span class="sxs-lookup"><span data-stu-id="51946-188">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="51946-189">Configureer instellingen voor onboarding van Defender voor eindpunten op de Windows-server met dezelfde hulpmiddelen en methoden voor Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="51946-189">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="51946-190">Zie Onboard [Windows 10-apparaten](configure-endpoints.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="51946-190">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="51946-191">Als u een anti-malwareoplossing van derden gebruikt, moet u de volgende instellingen voor de passieve av-modus van Microsoft Defender toepassen.</span><span class="sxs-lookup"><span data-stu-id="51946-191">If you're running a third-party anti-malware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="51946-192">Controleer of deze correct is geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="51946-192">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="51946-193">Stel de volgende registerinvoer in:</span><span class="sxs-lookup"><span data-stu-id="51946-193">Set the following registry entry:</span></span>
       - <span data-ttu-id="51946-194">Pad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="51946-194">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="51946-195">Naam: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="51946-195">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="51946-196">Type: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="51946-196">Type: REG_DWORD</span></span>
       - <span data-ttu-id="51946-197">Waarde: 1</span><span class="sxs-lookup"><span data-stu-id="51946-197">Value: 1</span></span>

    1. <span data-ttu-id="51946-198">Voer de volgende PowerShell-opdracht uit om te controleren of de passieve modus is geconfigureerd:</span><span class="sxs-lookup"><span data-stu-id="51946-198">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="51946-199">Controleer of er een recente gebeurtenis met de gebeurtenis in de passieve modus is gevonden:</span><span class="sxs-lookup"><span data-stu-id="51946-199">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![Afbeelding van het resultaat van verificatie in de passieve modus](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="51946-201">Voer de volgende opdracht uit om te controleren of Microsoft Defender AV is geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="51946-201">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="51946-202">Als het resultaat 'De opgegeven service bestaat niet als een geïnstalleerde service' is, moet u Microsoft Defender AV installeren.</span><span class="sxs-lookup"><span data-stu-id="51946-202">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="51946-203">Zie Microsoft [Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="51946-203">For more information, see [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>

    <span data-ttu-id="51946-204">Zie Groepsbeleidsinstellingen gebruiken om Microsoft Defender Antivirus te configureren en te beheren voor informatie over het gebruik van groepsbeleid voor het configureren en beheren van Microsoft Defender Antivirus op uw [Windows-servers.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="51946-204">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

## <a name="integration-with-azure-defender"></a><span data-ttu-id="51946-205">Integratie met Azure Defender</span><span class="sxs-lookup"><span data-stu-id="51946-205">Integration with Azure Defender</span></span>

<span data-ttu-id="51946-206">Defender voor Eindpunt kan worden geïntegreerd met Azure Defender om een uitgebreide windows-serverbeveiligingsoplossing te bieden.</span><span class="sxs-lookup"><span data-stu-id="51946-206">Defender for Endpoint can integrate with Azure Defender to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="51946-207">Met deze integratie kan Azure Defender de kracht van Defender voor Eindpunt gebruiken om de detectie van bedreigingen voor Windows-servers te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="51946-207">With this integration, Azure Defender can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="51946-208">De volgende mogelijkheden zijn opgenomen in deze integratie:</span><span class="sxs-lookup"><span data-stu-id="51946-208">The following capabilities are included in this integration:</span></span>

- <span data-ttu-id="51946-209">Geautomatiseerde onboarding: De Defender voor Eindpunt-sensor is automatisch ingeschakeld op Windows-servers die zijn onboarded bij Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="51946-209">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Defender.</span></span> <span data-ttu-id="51946-210">Zie De geïntegreerde Licentie voor [Microsoft Defender voor eindpunt](https://docs.microsoft.com/azure/security-center/security-center-wdatp)gebruiken voor meer informatie over onboarding van Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="51946-210">For more information on Azure Defender onboarding, see [Use the integrated Microsoft Defender for Endpoint license](https://docs.microsoft.com/azure/security-center/security-center-wdatp).</span></span>

    > [!NOTE]
    > <span data-ttu-id="51946-211">De integratie tussen Azure Defender voor servers en Microsoft Defender voor Eindpunt is uitgebreid met ondersteuning voor [Windows Server 2019 en Windows Virtual Desktop (WVD).](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)</span><span class="sxs-lookup"><span data-stu-id="51946-211">The integration between Azure Defender for Servers and Microsoft Defender for Endpoint has been expanded to support [Windows Server 2019 and Windows Virtual Desktop (WVD)](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).</span></span>

- <span data-ttu-id="51946-212">Windows-servers die worden gecontroleerd door Azure Defender, zijn ook beschikbaar in Defender voor Eindpunt: Azure Defender maakt naadloos verbinding met de Defender voor Eindpunttender, waardoor er één weergave beschikbaar is voor clients en servers.</span><span class="sxs-lookup"><span data-stu-id="51946-212">Windows servers monitored by Azure Defender will also be available in Defender for Endpoint - Azure Defender seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="51946-213">Daarnaast zijn defender voor eindpuntwaarschuwingen beschikbaar in de Azure Defender-console.</span><span class="sxs-lookup"><span data-stu-id="51946-213">In addition, Defender for Endpoint alerts will be available in the Azure Defender console.</span></span>
- <span data-ttu-id="51946-214">Serveronderzoek: Azure Defender-klanten hebben toegang tot het Microsoft Defender-beveiligingscentrum om gedetailleerd onderzoek uit te voeren om het bereik van een mogelijke inbreuk aan het licht te brengen.</span><span class="sxs-lookup"><span data-stu-id="51946-214">Server investigation -  Azure Defender customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="51946-215">Wanneer u Azure Defender gebruikt om servers te controleren, wordt automatisch een Defender voor Eindpunt-tenant gemaakt (in de VS voor Amerikaanse gebruikers, in de EU voor Europese en Britse gebruikers).</span><span class="sxs-lookup"><span data-stu-id="51946-215">When you use Azure Defender to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="51946-216">Gegevens die door Defender voor Eindpunt worden verzameld, worden opgeslagen op de geografische locatie van de tenant die tijdens de inrichting is geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="51946-216">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="51946-217">Als u Defender voor Eindpunt gebruikt voordat u Azure Defender gebruikt, worden uw gegevens opgeslagen op de locatie die u hebt opgegeven toen u uw tenant maakte, zelfs als u op een later tijdstip integreert met Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="51946-217">If you use Defender for Endpoint before using Azure Defender, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Defender at a later time.</span></span>
> - <span data-ttu-id="51946-218">Nadat de gegevens zijn geconfigureerd, kunt u de locatie waarop uw gegevens zijn opgeslagen niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="51946-218">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="51946-219">Als u uw gegevens naar een andere locatie wilt verplaatsen, moet u contact opnemen met Microsoft Support om de tenant opnieuw in te stellen.</span><span class="sxs-lookup"><span data-stu-id="51946-219">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="51946-220">Server-eindpuntcontrole met behulp van deze integratie is uitgeschakeld voor Office 365 GCC-klanten.</span><span class="sxs-lookup"><span data-stu-id="51946-220">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="51946-221">System Center Endpoint Protection-clients configureren en bijwerken</span><span class="sxs-lookup"><span data-stu-id="51946-221">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="51946-222">Defender for Endpoint is geïntegreerd met System Center Endpoint Protection.</span><span class="sxs-lookup"><span data-stu-id="51946-222">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="51946-223">De integratie biedt zichtbaarheid voor malwaredetecties en om de verspreiding van een aanval in uw organisatie te stoppen door potentieel schadelijke bestanden of verdachte malware te verbieden.</span><span class="sxs-lookup"><span data-stu-id="51946-223">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="51946-224">De volgende stappen zijn vereist om deze integratie mogelijk te maken:</span><span class="sxs-lookup"><span data-stu-id="51946-224">The following steps are required to enable this integration:</span></span>

- <span data-ttu-id="51946-225">Installeer de update van het anti-malwareplatform van januari [2017 voor endpoint protection-clients.](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="51946-225">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="51946-226">[Configureer het lidmaatschap van de SCEP-client Cloud Protection Service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) op **de instelling Geavanceerd.**</span><span class="sxs-lookup"><span data-stu-id="51946-226">[Configure the SCEP client Cloud Protection Service membership](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

## <a name="offboard-windows-servers"></a><span data-ttu-id="51946-227">Offboard Windows-servers</span><span class="sxs-lookup"><span data-stu-id="51946-227">Offboard Windows servers</span></span>

<span data-ttu-id="51946-228">U kunt Windows Server (SAC), Windows Server 2019 en Windows Server 2019 Core edition offboarden volgens dezelfde methode die beschikbaar is voor Windows 10-clientapparaten.</span><span class="sxs-lookup"><span data-stu-id="51946-228">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="51946-229">Voor andere Windows-serverversies hebt u twee opties voor offboard Windows-servers van de service:</span><span class="sxs-lookup"><span data-stu-id="51946-229">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>

- <span data-ttu-id="51946-230">De MMA-agent verwijderen</span><span class="sxs-lookup"><span data-stu-id="51946-230">Uninstall the MMA agent</span></span>
- <span data-ttu-id="51946-231">De configuratie van de Defender voor Eindpunt-werkruimte verwijderen</span><span class="sxs-lookup"><span data-stu-id="51946-231">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="51946-232">Offboarding zorgt ervoor dat de Windows-server stopt met het verzenden van sensorgegevens naar de portal, maar gegevens van de Windows-server, inclusief verwijzingen naar eventuele waarschuwingen die de server heeft ontvangen, blijven maximaal 6 maanden bewaard.</span><span class="sxs-lookup"><span data-stu-id="51946-232">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="51946-233">Windows-servers verwijderen door de MMA-agent te verwijderen</span><span class="sxs-lookup"><span data-stu-id="51946-233">Uninstall Windows servers by uninstalling the MMA agent</span></span>

<span data-ttu-id="51946-234">Als u de Windows-server wilt offboarden, kunt u de MMA-agent van de Windows-server verwijderen of loskoppelen van rapportage naar uw Defender voor Eindpunt-werkruimte.</span><span class="sxs-lookup"><span data-stu-id="51946-234">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="51946-235">Na het offboarden van de agent verzendt de Windows-server geen sensorgegevens meer naar Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="51946-235">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="51946-236">Zie Een agent uitschakelen voor [meer informatie.](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent)</span><span class="sxs-lookup"><span data-stu-id="51946-236">For more information, see [To disable an agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="51946-237">De configuratie van de Defender voor Eindpunt-werkruimte verwijderen</span><span class="sxs-lookup"><span data-stu-id="51946-237">Remove the Defender for Endpoint workspace configuration</span></span>

<span data-ttu-id="51946-238">Als u de Windows-server wilt uitschakelen, kunt u een van de volgende methoden gebruiken:</span><span class="sxs-lookup"><span data-stu-id="51946-238">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="51946-239">De configuratie van de Defender voor eindpuntwerkruimte verwijderen uit de MMA-agent</span><span class="sxs-lookup"><span data-stu-id="51946-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="51946-240">Een PowerShell-opdracht uitvoeren om de configuratie te verwijderen</span><span class="sxs-lookup"><span data-stu-id="51946-240">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="51946-241">De configuratie van de Defender voor eindpuntwerkruimte verwijderen uit de MMA-agent</span><span class="sxs-lookup"><span data-stu-id="51946-241">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="51946-242">Selecteer op **het tabblad Microsoft Monitoring Agent Properties** het tabblad Azure Log Analytics **(OMS).**</span><span class="sxs-lookup"><span data-stu-id="51946-242">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="51946-243">Selecteer de werkruimte Defender voor eindpunt en klik op **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="51946-243">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Afbeelding van Eigenschappen van Microsoft Monitoring Agent](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="51946-245">Een PowerShell-opdracht uitvoeren om de configuratie te verwijderen</span><span class="sxs-lookup"><span data-stu-id="51946-245">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="51946-246">Uw werkruimte-id krijgen:</span><span class="sxs-lookup"><span data-stu-id="51946-246">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="51946-247">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="51946-247">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="51946-248">Selecteer **Windows Server 2008 R2 SP1, 2012 R2 en 2016** als het besturingssysteem en ontvang uw werkruimte-id:</span><span class="sxs-lookup"><span data-stu-id="51946-248">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Afbeelding van windows-server onboarding](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="51946-250&quot;>Open een verhoogde PowerShell en voer de volgende opdracht uit.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;51946-250&quot;>Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id=&quot;51946-251&quot;>Gebruik de werkruimte-id die u hebt verkregen en `WorkspaceID` vervangt:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;51946-251&quot;>Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = &quot;SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

## <a name="onboarding-servers-with-no-management-solution"></a><span data-ttu-id="51946-252">Onboarding Servers zonder beheeroplossing</span><span class="sxs-lookup"><span data-stu-id="51946-252">Onboarding Servers with no management solution</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="51946-253">Groepsbeleid gebruiken</span><span class="sxs-lookup"><span data-stu-id="51946-253">Using Group Policy</span></span>

<span data-ttu-id="51946-254">**Stap-1: Maak de benodigde bestanden om naar de servers te kopiëren.**</span><span class="sxs-lookup"><span data-stu-id="51946-254">**Step-1: Create the necessary files to copy down to the servers.**</span></span>

1. <span data-ttu-id="51946-255">Ga naar c:\windows\sysvol\domain\scripts (Besturingselement wijzigen kan nodig zijn op een van de domeincontrollers.)</span><span class="sxs-lookup"><span data-stu-id="51946-255">Navigate to c:\windows\sysvol\domain\scripts (Change control could be needed on one of the domain controllers.)</span></span>
1. <span data-ttu-id="51946-256">Maak een map met de naam MMA.</span><span class="sxs-lookup"><span data-stu-id="51946-256">Create a folder named MMA.</span></span>
1. <span data-ttu-id="51946-257">Download het volgende en plaats in de map MMA:</span><span class="sxs-lookup"><span data-stu-id="51946-257">Download the following and place in the MMA folder:</span></span>

    <span data-ttu-id="51946-258">**Bijwerken voor klantervaring en diagnostische telemetrie (Windows Server 2008 R2 en Windows Server 2012 R2)**</span><span class="sxs-lookup"><span data-stu-id="51946-258">**Update for customer experience and diagnostic telemetry (Windows Server 2008 R2 and Windows Server 2012 R2)**</span></span>

    [<span data-ttu-id="51946-259">Voor Windows 2008 R2 x64</span><span class="sxs-lookup"><span data-stu-id="51946-259">For Windows 2008 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [<span data-ttu-id="51946-260">Voor Windows 2012 R2 x64</span><span class="sxs-lookup"><span data-stu-id="51946-260">For Windows 2012 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > <span data-ttu-id="51946-261">In dit artikel wordt ervan uitgenomen dat u x64-servers gebruikt (MMA Agent .exe x64 [New SHA-2 compliant version)](https://go.microsoft.com/fwlink/?LinkId=828603)</span><span class="sxs-lookup"><span data-stu-id="51946-261">This article assumes you are using x64-based servers (MMA Agent .exe x64 [New SHA-2 compliant version](https://go.microsoft.com/fwlink/?LinkId=828603))</span></span>

<span data-ttu-id="51946-262">**Stap-2: Een bestandsnaam maken DeployMMA.cmd (met kladblok)** Voeg de volgende regels toe aan het cmd-bestand.</span><span class="sxs-lookup"><span data-stu-id="51946-262">**Step-2: Create a file name DeployMMA.cmd (using notepad)** Add the following lines to the cmd file.</span></span> <span data-ttu-id="51946-263">Houd er rekening mee dat u uw werkruimte-id en -sleutel nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="51946-263">Note that you'll need your WORKSPACE ID and KEY.</span></span>

```dos
@echo off 
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" ( 
exit
) ELSE (
wusa.exe c:\Windows\MMA\Windows6.1-KB123456-x86.msu /quiet /norestart
wusa.exe c:\Windows\MMA\Windows8.1-KB123456-x86.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /C:"setup.exe /qn ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID=<your workspace ID>
OPINSIGHTS_WORKSPACE_KEY=<your workspace key>== AcceptEndUserLicenseAgreement=1"
)
```

## <a name="group-policy-configuration"></a><span data-ttu-id="51946-264">Groepsbeleidsconfiguratie</span><span class="sxs-lookup"><span data-stu-id="51946-264">Group Policy Configuration</span></span>

<span data-ttu-id="51946-265">Maak een nieuw groepsbeleid speciaal voor onboarding-apparaten, zoals 'Microsoft Defender for Endpoint Onboarding'.</span><span class="sxs-lookup"><span data-stu-id="51946-265">Create a new group policy specifically for onboarding devices such as “Microsoft Defender for Endpoint Onboarding”.</span></span>

- <span data-ttu-id="51946-266">Een groepsbeleidsmap maken met de naam 'c:\windows\MMA'</span><span class="sxs-lookup"><span data-stu-id="51946-266">Create a Group Policy Folder named “c:\windows\MMA”</span></span>

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="mappen":::

    <span data-ttu-id="51946-268">**Hiermee wordt op elke server een nieuwe map toegevoegd waarin het GPO wordt toegepast, genaamd MMA, en wordt deze opgeslagen in c:\windows. Dit bevat de installatiebestanden voor het MMA, de vereisten en het installatiescript.**</span><span class="sxs-lookup"><span data-stu-id="51946-268">**This will add a new folder on every server that gets the GPO applied, called MMA, and will be stored in c:\windows. This will contain the installation files for the MMA, prerequisites, and install script.**</span></span>

- <span data-ttu-id="51946-269">Maak een groepsbeleidsbestandenvoorkeur voor elk van de bestanden die zijn opgeslagen in Net-aanmelding.</span><span class="sxs-lookup"><span data-stu-id="51946-269">Create a Group Policy Files preference for each of the files stored in Net logon.</span></span>

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="afbeelding groepsbeleid1":::

<span data-ttu-id="51946-271">De bestanden worden gekopieerd van DOMAIN\NETLOGON\MMA\filename naar C:\windows\MMA\filename. De installatiebestanden zijn dus lokaal op **de server:**</span><span class="sxs-lookup"><span data-stu-id="51946-271">It copies the files from DOMAIN\NETLOGON\MMA\filename to C:\windows\MMA\filename – **so the installation files are local to the server**:</span></span>

:::image type="content" source="images/deploymma.png" alt-text="mma-cmd implementeren":::

<span data-ttu-id="51946-273">Voor de twee KBs (een voor Windows Server 2008R2/Windows 7 en de andere voor Windows Server 2012 R2) herhaalt u het proces, maar maakt u op het tabblad COMMON het itemniveau, zodat het bestand alleen wordt gekopieerd naar de juiste versie van het platform/besturingssysteem in het bereik:</span><span class="sxs-lookup"><span data-stu-id="51946-273">For the two KBs (one for Windows Server 2008R2/Windows 7 and the other for Windows Server 2012 R2) repeat the process but create item level targeting on the COMMON tab, so the file only gets copied to the appropriate platform/Operating system version in scope:</span></span>

:::image type="content" source="images/targeteditor.png" alt-text="doeleditor":::

- <span data-ttu-id="51946-275">Voor Windows Server 2008 R2 hebt u Windows6.1-BJ3080149-x64.msu nodig (en deze wordt alleen naar beneden kopiëren).</span><span class="sxs-lookup"><span data-stu-id="51946-275">For Windows Server 2008 R2 you need (and it will only copy down) Windows6.1-BJ3080149-x64.msu</span></span>
- <span data-ttu-id="51946-276">Voor Windows Server 2012 R2 hebt u Windows8.1-BJ3080149-x64.msu nodig (en deze wordt alleen naar beneden kopiëren).</span><span class="sxs-lookup"><span data-stu-id="51946-276">For Windows Server 2012 R2 you need (and it will only copy down) Windows8.1-BJ3080149-x64.msu</span></span>

<span data-ttu-id="51946-277">Wanneer dit is gedaan, moet u een opstartscriptbeleid maken:</span><span class="sxs-lookup"><span data-stu-id="51946-277">Once this is done, you'll need to create a start-up script policy:</span></span>

:::image type="content" source="images/startupprops.png" alt-text="Opstarteigenschappen":::

<span data-ttu-id="51946-279">De naam van het bestand dat hier moet worden uitgevoerd, is c:\windows\MMA\DeployMMA.cmd.</span><span class="sxs-lookup"><span data-stu-id="51946-279">The name of the file to run here is c:\windows\MMA\DeployMMA.cmd.</span></span>
<span data-ttu-id="51946-280">Zodra de server opnieuw is gestart als onderdeel van het opstartproces, wordt de UPDATE voor klantervaring en diagnostische telemetrie KB geïnstalleerd en vervolgens de MMA-agent geïnstalleerd, terwijl de werkruimte-id en -sleutel worden ingesteld en wordt de server aan boord gemaakt.</span><span class="sxs-lookup"><span data-stu-id="51946-280">Once the server is restarted as part of the start-up process it will install the Update for customer experience and diagnostic telemetry KB, and then install the MMA Agent, while setting the Workspace ID and Key, and the server will be onboarded.</span></span>

<span data-ttu-id="51946-281">U kunt ook een **directe taak gebruiken om** de deployMMA.cmd uit te voeren als u niet alle servers opnieuw wilt opstarten.</span><span class="sxs-lookup"><span data-stu-id="51946-281">You could also use an **immediate task** to run the deployMMA.cmd if you don't want to reboot all the servers.</span></span>
<span data-ttu-id="51946-282">Dit kan in twee fasen.</span><span class="sxs-lookup"><span data-stu-id="51946-282">This could be done in two phases.</span></span> <span data-ttu-id="51946-283">Maak eerst **de bestanden en de** map in GPO: Geef het systeem de tijd om ervoor te zorgen dat het GPO is toegepast en alle servers hebben de installatiebestanden.</span><span class="sxs-lookup"><span data-stu-id="51946-283">First create **the files and the folder in** GPO – Give the system time to ensure the GPO has been applied, and all the servers have the install files.</span></span> <span data-ttu-id="51946-284">Voeg vervolgens de directe taak toe.</span><span class="sxs-lookup"><span data-stu-id="51946-284">Then, add the immediate task.</span></span> <span data-ttu-id="51946-285">Dit resulteert in hetzelfde resultaat zonder dat u opnieuw moet opstarten.</span><span class="sxs-lookup"><span data-stu-id="51946-285">This will achieve the same result without requiring a reboot.</span></span>

<span data-ttu-id="51946-286">Aangezien het script een exitmethode heeft en gewoon opnieuw wordt uitgevoerd als de MMA is geïnstalleerd, kunt u ook een dagelijkse geplande taak gebruiken om hetzelfde resultaat te bereiken.</span><span class="sxs-lookup"><span data-stu-id="51946-286">As the Script has an exit method and wont re-run if the MMA is installed, you could also use a daily scheduled task to achieve the same result.</span></span> <span data-ttu-id="51946-287">Net als bij een compliancebeleid van Configuration Manager wordt dagelijks gechecked om te controleren of de MMA aanwezig is.</span><span class="sxs-lookup"><span data-stu-id="51946-287">Similar to a Configuration Manager compliance policy it will check daily to ensure the MMA is present.</span></span>

:::image type="content" source="images/schtask.png" alt-text="planningstaak":::

:::image type="content" source="images/newtaskprops.png" alt-text="nieuwe taakeigenschappen":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="mma download props implementeren":::

:::image type="content" source="images/tasksch.png" alt-text="taakplanning":::

<span data-ttu-id="51946-292">Zoals vermeld in de onboarding-documentatie voor Server specifiek rond Server 2008 R2, raadpleegt u hieronder:</span><span class="sxs-lookup"><span data-stu-id="51946-292">As mentioned in the onboarding documentation for Server specifically around Server 2008 R2 please see below:</span></span>

<span data-ttu-id="51946-293">Controleer Windows Server 2008 R2 PS1 of u voldoet aan de volgende vereisten:</span><span class="sxs-lookup"><span data-stu-id="51946-293">For Windows Server 2008 R2 PS1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="51946-294">De maandelijkse update van [februari 2018 installeren](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="51946-294">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
- <span data-ttu-id="51946-295">Installeer [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (of hoger) of [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="51946-295">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

<span data-ttu-id="51946-296">Controleer of de KBs aanwezig zijn voordat u Windows Server 2008 R2 Met dit proces kunt u alle servers aan boord nemen als u geen Configuration Manager-beheerservers hebt.</span><span class="sxs-lookup"><span data-stu-id="51946-296">Please check the KBs are present before onboarding Windows Server 2008 R2 This process allows you to onboard all the servers if you don’t have Configuration Manager managing Servers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="51946-297">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="51946-297">Related topics</span></span>

- [<span data-ttu-id="51946-298">Onboarden Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="51946-298">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="51946-299">Onboarden niet-Windows-apparaten</span><span class="sxs-lookup"><span data-stu-id="51946-299">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="51946-300">Proxy- en internetconnectiviteitsinstellingen configureren</span><span class="sxs-lookup"><span data-stu-id="51946-300">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="51946-301">Een detectietest uitvoeren op een nieuw ingebouwde Defender voor eindpuntapparaat</span><span class="sxs-lookup"><span data-stu-id="51946-301">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="51946-302">Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen</span><span class="sxs-lookup"><span data-stu-id="51946-302">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
