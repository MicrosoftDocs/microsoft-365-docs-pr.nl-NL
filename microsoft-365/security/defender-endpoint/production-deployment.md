---
title: Microsoft Defender instellen voor endpoint-implementatie
description: Meer informatie over het instellen van de implementatie voor Microsoft Defender voor Eindpunt
keywords: implementeren, instellen, validatie van licenties, tenantconfiguratie, netwerkconfiguratie
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
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b49565c45c1f38d0d2ce71b097af079782ba4de
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636192"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="435aa-104">Microsoft Defender instellen voor endpoint-implementatie</span><span class="sxs-lookup"><span data-stu-id="435aa-104">Set up Microsoft Defender for Endpoint deployment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="435aa-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="435aa-105">**Applies to:**</span></span>
- [<span data-ttu-id="435aa-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="435aa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="435aa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="435aa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="435aa-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="435aa-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="435aa-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="435aa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="435aa-110">Het implementeren van Defender voor Eindpunt is een proces in drie fasen:</span><span class="sxs-lookup"><span data-stu-id="435aa-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="435aa-111">[![implementatiefase - voorbereiden](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="435aa-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="435aa-112">Fase 1: Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="435aa-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | ![implementatiefase - installatie](images/phase-diagrams/setup.png)<br><span data-ttu-id="435aa-114">Fase 2: Instellen</span><span class="sxs-lookup"><span data-stu-id="435aa-114">Phase 2: Setup</span></span> | <span data-ttu-id="435aa-115">[![implementatiefase - onboard](images/phase-diagrams/onboard.png)](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="435aa-115">[![deployment phase - onboard](images/phase-diagrams/onboard.png)](onboarding.md)</span></span><br>[<span data-ttu-id="435aa-116">Fase 3: Onboarden</span><span class="sxs-lookup"><span data-stu-id="435aa-116">Phase 3: Onboard</span></span>](onboarding.md) |
| ----- | ----- | ----- |
| | <span data-ttu-id="435aa-117">*U bent er!*</span><span class="sxs-lookup"><span data-stu-id="435aa-117">*You are here!*</span></span>||

<span data-ttu-id="435aa-118">U bent momenteel bezig met de in te stellen fase.</span><span class="sxs-lookup"><span data-stu-id="435aa-118">You are currently in the set-up phase.</span></span>

<span data-ttu-id="435aa-119">In dit implementatiescenario wordt u begeleid door de stappen op:</span><span class="sxs-lookup"><span data-stu-id="435aa-119">In this deployment scenario, you'll be guided through the steps on:</span></span>
- <span data-ttu-id="435aa-120">Validatie van licenties</span><span class="sxs-lookup"><span data-stu-id="435aa-120">Licensing validation</span></span>
- <span data-ttu-id="435aa-121">Tenantconfiguratie</span><span class="sxs-lookup"><span data-stu-id="435aa-121">Tenant configuration</span></span>
- <span data-ttu-id="435aa-122">Netwerkconfiguratie</span><span class="sxs-lookup"><span data-stu-id="435aa-122">Network configuration</span></span>


>[!NOTE]
><span data-ttu-id="435aa-123">Om u te begeleiden bij een normale implementatie, wordt in dit scenario alleen het gebruik van Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="435aa-123">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="435aa-124">Defender voor Eindpunt ondersteunt het gebruik van andere onboarding-hulpprogramma's, maar deze scenario's worden niet in de implementatiehandleiding bestrijken.</span><span class="sxs-lookup"><span data-stu-id="435aa-124">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="435aa-125">Zie Onboard devices to Microsoft Defender for Endpoint (Onboard [devices to Microsoft Defender for Endpoint) voor meer informatie.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="435aa-125">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="check-license-state"></a><span data-ttu-id="435aa-126">Licentiestaat controleren</span><span class="sxs-lookup"><span data-stu-id="435aa-126">Check license state</span></span>

<span data-ttu-id="435aa-127">Controleren op de licentiestaat en of deze goed is ingericht, kan via het beheercentrum of via de **Microsoft Azure portal.**</span><span class="sxs-lookup"><span data-stu-id="435aa-127">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="435aa-128">Als u uw licenties wilt bekijken, gaat u naar de **Microsoft Azure portal** en gaat u naar de [Microsoft Azure portallicentiesectie.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)</span><span class="sxs-lookup"><span data-stu-id="435aa-128">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Afbeelding van de pagina Azure Licensing](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="435aa-130">U kunt ook in het beheercentrum naar  >  **Factureringsabonnementen gaan.**</span><span class="sxs-lookup"><span data-stu-id="435aa-130">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="435aa-131">Op het scherm ziet u alle inrichtende licenties en de huidige **status.**</span><span class="sxs-lookup"><span data-stu-id="435aa-131">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![Afbeelding van factureringslicenties](images/atp-billing-subscriptions.png)


## <a name="cloud-service-provider-validation"></a><span data-ttu-id="435aa-133">Validatie van cloudserviceprovider</span><span class="sxs-lookup"><span data-stu-id="435aa-133">Cloud Service Provider validation</span></span>

<span data-ttu-id="435aa-134">Als u toegang wilt krijgen tot welke licenties aan uw bedrijf zijn ingericht en om de status van de licenties te controleren, gaat u naar het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="435aa-134">To gain access into which licenses are provisioned to your company, and to check the state of the licenses, go to the admin center.</span></span>

1. <span data-ttu-id="435aa-135">Selecteer services beheren in de **partnerportal** **> Office 365.**</span><span class="sxs-lookup"><span data-stu-id="435aa-135">From the **Partner portal**, select **Administer services > Office 365**.</span></span>

2. <span data-ttu-id="435aa-136">Als u op de **koppeling Partnerportal** klikt, wordt de optie Beheerder **namens** geopend en hebt u toegang tot het klantbeheerdercentrum.</span><span class="sxs-lookup"><span data-stu-id="435aa-136">Clicking on the **Partner portal** link will open the **Admin on behalf** option and will give you access to the customer admin center.</span></span>

   ![Afbeelding van O365-beheerportal](images/atp-O365-admin-portal-customer.png)



## <a name="tenant-configuration"></a><span data-ttu-id="435aa-138">Tenantconfiguratie</span><span class="sxs-lookup"><span data-stu-id="435aa-138">Tenant Configuration</span></span>
<span data-ttu-id="435aa-139">Onboarding naar Microsoft Defender voor Endpoint is eenvoudig.</span><span class="sxs-lookup"><span data-stu-id="435aa-139">Onboarding to Microsoft Defender for Endpoint is easy.</span></span> <span data-ttu-id="435aa-140">Selecteer in het navigatiemenu een item onder de sectie Eindpunten of een Microsoft 365 Defender-functie zoals Incidenten, Jagen, Actiecentrum of Bedreigingsanalyse om het onboardingproces te starten.</span><span class="sxs-lookup"><span data-stu-id="435aa-140">From the navigation menu, select any item under the Endpoints section, or any Microsoft 365 Defender feature such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span>

<span data-ttu-id="435aa-141">Navigeer vanuit een webbrowser naar het [Microsoft 365 Beveiligingscentrum.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="435aa-141">From a web browser, navigate to the [Microsoft 365 Security Center](https://security.microsoft.com).</span></span>

## <a name="network-configuration"></a><span data-ttu-id="435aa-142">Netwerkconfiguratie</span><span class="sxs-lookup"><span data-stu-id="435aa-142">Network configuration</span></span>
<span data-ttu-id="435aa-143">Als de organisatie de eindpunten niet nodig heeft om een proxy te gebruiken voor toegang tot internet, slaat u deze sectie over.</span><span class="sxs-lookup"><span data-stu-id="435aa-143">If the organization doesn't require the endpoints to use a Proxy to access the Internet, skip this section.</span></span>

<span data-ttu-id="435aa-144">Voor de Microsoft Defender for Endpoint-sensor moet Microsoft Windows HTTP (WinHTTP) sensorgegevens rapporteren en communiceren met de Microsoft Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="435aa-144">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="435aa-145">De ingesloten Microsoft Defender voor Eindpunt-sensor wordt uitgevoerd in de systeemcontext met behulp van het LocalSystem-account.</span><span class="sxs-lookup"><span data-stu-id="435aa-145">The embedded Microsoft Defender for Endpoint sensor runs in the system context using the LocalSystem account.</span></span> <span data-ttu-id="435aa-146">De sensor gebruikt Microsoft Windows HTTP Services (WinHTTP) om communicatie met de Microsoft Defender for Endpoint-cloudservice in te stellen.</span><span class="sxs-lookup"><span data-stu-id="435aa-146">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Microsoft Defender for Endpoint cloud service.</span></span> <span data-ttu-id="435aa-147">De configuratie-instelling WinHTTP is onafhankelijk van de instellingen Windows Internet (WinINet) voor internetbrowsingsproxy en kan alleen een proxyserver vinden met behulp van de volgende detectiemethoden:</span><span class="sxs-lookup"><span data-stu-id="435aa-147">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

<span data-ttu-id="435aa-148">**Autodiscovery-methoden:**</span><span class="sxs-lookup"><span data-stu-id="435aa-148">**Autodiscovery methods:**</span></span>

-   <span data-ttu-id="435aa-149">Transparante proxy</span><span class="sxs-lookup"><span data-stu-id="435aa-149">Transparent proxy</span></span>

-   <span data-ttu-id="435aa-150">Web proxy Autodiscovery Protocol (WPAD)</span><span class="sxs-lookup"><span data-stu-id="435aa-150">Web Proxy Autodiscovery Protocol (WPAD)</span></span>

<span data-ttu-id="435aa-151">Als een transparante proxy of WPAD is geïmplementeerd in de netwerktopologie, is er geen speciale configuratie-instellingen nodig.</span><span class="sxs-lookup"><span data-stu-id="435aa-151">If a Transparent proxy or WPAD has been implemented in the network topology, there is no need for special configuration settings.</span></span> <span data-ttu-id="435aa-152">Zie de sectie [URL's](production-deployment.md#proxy-service-urls) proxyservice in dit document voor de lijst URL's voor URL's toestaan of op Apparaatproxy- en internetverbindingsinstellingen [configureren](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)voor meer informatie over url-uitsluitingen van Microsoft Defender voor eindpunten in de proxy.</span><span class="sxs-lookup"><span data-stu-id="435aa-152">For more information on Microsoft Defender for Endpoint URL exclusions in the proxy, see the [Proxy Service URLs](production-deployment.md#proxy-service-urls) section in this document for the URLs allow list or on [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="435aa-153">**Hnadmatige statische proxyconfiguratie**</span><span class="sxs-lookup"><span data-stu-id="435aa-153">**Manual static proxy configuration:**</span></span>

-   <span data-ttu-id="435aa-154">Configuratie op basis van register</span><span class="sxs-lookup"><span data-stu-id="435aa-154">Registry-based configuration</span></span>

-   <span data-ttu-id="435aa-155">WinHTTP geconfigureerd met de opdracht Netsh</span><span class="sxs-lookup"><span data-stu-id="435aa-155">WinHTTP configured using netsh command</span></span> <br> <span data-ttu-id="435aa-156">Alleen geschikt voor desktops in een stabiele topologie (bijvoorbeeld: een bureaublad in een bedrijfsnetwerk achter dezelfde proxy)</span><span class="sxs-lookup"><span data-stu-id="435aa-156">Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="435aa-157">De proxyserver handmatig configureren met een statische proxy op basis van het register</span><span class="sxs-lookup"><span data-stu-id="435aa-157">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="435aa-158">Configureer een statische proxy op basis van het register zodat alleen de Sensor voor Eindpunten van Microsoft Defender diagnostische gegevens kan rapporteren en kan communiceren met Microsoft Defender voor endpoint-services als een computer geen verbinding mag maken met internet.</span><span class="sxs-lookup"><span data-stu-id="435aa-158">Configure a registry-based static proxy to allow only Microsoft Defender for Endpoint sensor to report diagnostic data and communicate with Microsoft Defender for Endpoint services if a computer isn't permitted to connect to the Internet.</span></span> <span data-ttu-id="435aa-159">De statische proxy kan worden geconfigureerd via Group Policy (GP).</span><span class="sxs-lookup"><span data-stu-id="435aa-159">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="435aa-160">U vindt het groepsbeleid onder:</span><span class="sxs-lookup"><span data-stu-id="435aa-160">The group policy can be found under:</span></span>

 - <span data-ttu-id="435aa-161">Beheersjablonen \> Windows \> Onderdelengegevensverzameling en Preview-builds \> Configureren geverifieerd proxygebruik voor de verbonden gebruikerservaring en telemetrieservice</span><span class="sxs-lookup"><span data-stu-id="435aa-161">Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
     - <span data-ttu-id="435aa-162">Stel deze in **op Ingeschakeld en** selecteer Geverifieerd **proxygebruik uitschakelen**</span><span class="sxs-lookup"><span data-stu-id="435aa-162">Set it to **Enabled** and select **Disable Authenticated Proxy usage**</span></span>

1. <span data-ttu-id="435aa-163">Open de Console Groepsbeleidsbeheer.</span><span class="sxs-lookup"><span data-stu-id="435aa-163">Open the Group Policy Management Console.</span></span>
2. <span data-ttu-id="435aa-164">Maak een beleid of bewerk een bestaand beleid op basis van de organisatiepraktijken.</span><span class="sxs-lookup"><span data-stu-id="435aa-164">Create a policy or edit an existing policy based off the organizational practices.</span></span>
3. <span data-ttu-id="435aa-165">Bewerk het groepsbeleid en navigeer naar beheersjablonen Windows Onderdelengegevensverzameling en **\> \> Preview-versies Configure Authenticated Proxy usage for \> the Connected User Experience and Telemetry Service**.</span><span class="sxs-lookup"><span data-stu-id="435aa-165">Edit the Group Policy and navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**.</span></span> 
    <span data-ttu-id="435aa-166">![Afbeelding van groepsbeleidsconfiguratie](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="435aa-166">![Image of Group Policy configuration](images/atp-gpo-proxy1.png)</span></span>

4. <span data-ttu-id="435aa-167">Selecteer **Ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="435aa-167">Select **Enabled**.</span></span>
5. <span data-ttu-id="435aa-168">Selecteer **Geverifieerd proxygebruik uitschakelen.**</span><span class="sxs-lookup"><span data-stu-id="435aa-168">Select **Disable Authenticated Proxy usage**.</span></span>
   
6. <span data-ttu-id="435aa-169">Ga naar **beheersjablonen Windows \> Onderdelengegevensverzameling en \> Preview-builds Configureren verbonden \> gebruikerservaringen en telemetrie.**</span><span class="sxs-lookup"><span data-stu-id="435aa-169">Navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure connected user experiences and telemetry**.</span></span>
    <span data-ttu-id="435aa-170">![Afbeelding van configuratie-instelling groepsbeleid](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="435aa-170">![Image of Group Policy configuration setting](images/atp-gpo-proxy2.png)</span></span>
7. <span data-ttu-id="435aa-171">Selecteer **Ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="435aa-171">Select **Enabled**.</span></span>
8. <span data-ttu-id="435aa-172">Voer de **naam van de proxyserver in.**</span><span class="sxs-lookup"><span data-stu-id="435aa-172">Enter the **Proxy Server Name**.</span></span>

<span data-ttu-id="435aa-173">Met het beleid worden twee registerwaarden `TelemetryProxyServer` als REG_SZ ingesteld en wordt `DisableEnterpriseAuthProxy` als REG_DWORD ingesteld onder de registersleutel `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span><span class="sxs-lookup"><span data-stu-id="435aa-173">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="435aa-174">De registerwaarde `TelemetryProxyServer` heeft de volgende tekenreeksindeling:</span><span class="sxs-lookup"><span data-stu-id="435aa-174">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

```text
<server name or ip>:<port>
```

<span data-ttu-id="435aa-175">Bijvoorbeeld: 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="435aa-175">For example: 10.0.0.6:8080</span></span>

<span data-ttu-id="435aa-176">De registerwaarde `DisableEnterpriseAuthProxy` moet worden ingesteld op 1.</span><span class="sxs-lookup"><span data-stu-id="435aa-176">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

###  <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="435aa-177">De proxyserver handmatig configureren met de opdracht Netsh</span><span class="sxs-lookup"><span data-stu-id="435aa-177">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="435aa-178">Gebruik netsh om een statische proxy voor het hele systeem te configureren.</span><span class="sxs-lookup"><span data-stu-id="435aa-178">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="435aa-179">Dit is van invloed op alle toepassingen, inclusief Windows-services die WinHTTP met standaardproxy gebruiken.</span><span class="sxs-lookup"><span data-stu-id="435aa-179">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="435aa-180">Laptops die de topologie wijzigen (bijvoorbeeld van kantoor naar thuis) werken niet goed met netsh.</span><span class="sxs-lookup"><span data-stu-id="435aa-180">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="435aa-181">Gebruik de statische proxyconfiguratie op basis van het register.</span><span class="sxs-lookup"><span data-stu-id="435aa-181">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="435aa-182">Open een opdrachtpromptregel met verhoogde bevoegdheid:</span><span class="sxs-lookup"><span data-stu-id="435aa-182">Open an elevated command line:</span></span>

    1. <span data-ttu-id="435aa-183">Go to **Start** and type **cmd**.</span><span class="sxs-lookup"><span data-stu-id="435aa-183">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="435aa-184">Klik met de rechtermuisknop op **Opdrachtprompt** en selecteer **Als beheerder uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="435aa-184">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="435aa-185">Voer de volgende opdracht in en druk op **Enter**:</span><span class="sxs-lookup"><span data-stu-id="435aa-185">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="435aa-186">Bijvoorbeeld: netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="435aa-186">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>


###  <a name="proxy-configuration-for-down-level-devices"></a><span data-ttu-id="435aa-187">Proxyconfiguratie voor apparaten met een laag niveau</span><span class="sxs-lookup"><span data-stu-id="435aa-187">Proxy Configuration for down-level devices</span></span>

<span data-ttu-id="435aa-188">Down-Level apparaten zijn Windows 7 SP1- en Windows 8.1-werkstations en Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 en versies van Windows Server 2016 vóór Windows Server CB 1803.</span><span class="sxs-lookup"><span data-stu-id="435aa-188">Down-Level devices include Windows 7 SP1 and Windows 8.1 workstations as well as Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2, and versions of Windows Server 2016 prior to Windows Server CB 1803.</span></span> <span data-ttu-id="435aa-189">Deze besturingssystemen hebben de proxy geconfigureerd als onderdeel van de Microsoft Management Agent voor het verwerken van communicatie van het eindpunt naar Azure.</span><span class="sxs-lookup"><span data-stu-id="435aa-189">These operating systems will have the proxy configured as part of the Microsoft Management Agent to handle communication from the endpoint to Azure.</span></span> <span data-ttu-id="435aa-190">Raadpleeg de Microsoft Management Agent Fast Deployment Guide voor informatie over de configuratie van een proxy op deze apparaten.</span><span class="sxs-lookup"><span data-stu-id="435aa-190">Refer to the Microsoft Management Agent Fast Deployment Guide for information on how a proxy is configured on these devices.</span></span>

### <a name="proxy-service-urls"></a><span data-ttu-id="435aa-191">URL's voor proxyservice</span><span class="sxs-lookup"><span data-stu-id="435aa-191">Proxy Service URLs</span></span>
<span data-ttu-id="435aa-192">URL's die v20 bevatten, zijn alleen nodig als u Windows 10, versie 1803 of hoger hebt.</span><span class="sxs-lookup"><span data-stu-id="435aa-192">URLs that include v20 in them are only needed if you have Windows 10, version 1803 or later devices.</span></span> <span data-ttu-id="435aa-193">Is bijvoorbeeld alleen ```us-v20.events.data.microsoft.com``` nodig als het apparaat zich op Windows 10, versie 1803 of hoger.</span><span class="sxs-lookup"><span data-stu-id="435aa-193">For example, ```us-v20.events.data.microsoft.com``` is only needed if the device is on Windows 10, version 1803 or later.</span></span>
 

<span data-ttu-id="435aa-194">Als een proxy of firewall anoniem verkeer blokkeert, aangezien microsoft Defender voor eindpunten-sensor verbinding maakt vanuit de systeemcontext, moet u ervoor zorgen dat anoniem verkeer is toegestaan in de vermelde URL's.</span><span class="sxs-lookup"><span data-stu-id="435aa-194">If a proxy or firewall is blocking anonymous traffic, as Microsoft Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the listed URLs.</span></span>

<span data-ttu-id="435aa-195">In de volgende downloadbare spreadsheet vindt u de services en bijbehorende URL's waar uw netwerk verbinding mee moet kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="435aa-195">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="435aa-196">Zorg ervoor dat er geen firewall- of netwerkfilterregels zijn die de toegang tot deze URL's weigeren, of u moet mogelijk een regel voor toestaan *speciaal* voor deze url's maken.</span><span class="sxs-lookup"><span data-stu-id="435aa-196">Ensure there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="435aa-197">**Spreadsheet met domeinenlijst**</span><span class="sxs-lookup"><span data-stu-id="435aa-197">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="435aa-198">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="435aa-198">**Description**</span></span>|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="435aa-200">Spreadsheet met specifieke DNS-records voor servicelocaties, geografische locaties en besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="435aa-200">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="435aa-201">Download de spreadsheet hier.</span><span class="sxs-lookup"><span data-stu-id="435aa-201">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


###  <a name="microsoft-defender-for-endpoint-service-backend-ip-ranges"></a><span data-ttu-id="435aa-202">Back-end IP-bereik van Microsoft Defender for Endpoint-service</span><span class="sxs-lookup"><span data-stu-id="435aa-202">Microsoft Defender for Endpoint service backend IP ranges</span></span>

<span data-ttu-id="435aa-203">Als uw netwerkapparaten geen DNS-regels ondersteunen, gebruikt u in plaats daarvan IP-bereik.</span><span class="sxs-lookup"><span data-stu-id="435aa-203">If your network devices don't support DNS-based rules, use IP ranges instead.</span></span>

<span data-ttu-id="435aa-204">Defender for Endpoint is gebouwd in azure cloud, geïmplementeerd in de volgende regio's:</span><span class="sxs-lookup"><span data-stu-id="435aa-204">Defender for Endpoint is built in Azure cloud, deployed in the following regions:</span></span>

- <span data-ttu-id="435aa-205">AzureCloud.eastus</span><span class="sxs-lookup"><span data-stu-id="435aa-205">AzureCloud.eastus</span></span>
- <span data-ttu-id="435aa-206">AzureCloud.eastus2</span><span class="sxs-lookup"><span data-stu-id="435aa-206">AzureCloud.eastus2</span></span>
- <span data-ttu-id="435aa-207">AzureCloud.westcentralus</span><span class="sxs-lookup"><span data-stu-id="435aa-207">AzureCloud.westcentralus</span></span>
- <span data-ttu-id="435aa-208">AzureCloud.northeurope</span><span class="sxs-lookup"><span data-stu-id="435aa-208">AzureCloud.northeurope</span></span>
- <span data-ttu-id="435aa-209">AzureCloud.westeurope</span><span class="sxs-lookup"><span data-stu-id="435aa-209">AzureCloud.westeurope</span></span>
- <span data-ttu-id="435aa-210">AzureCloud.uksouth</span><span class="sxs-lookup"><span data-stu-id="435aa-210">AzureCloud.uksouth</span></span>
- <span data-ttu-id="435aa-211">AzureCloud.ukwest</span><span class="sxs-lookup"><span data-stu-id="435aa-211">AzureCloud.ukwest</span></span>

<span data-ttu-id="435aa-212">U kunt de Azure IP-bereik vinden in [Azure IP-bereik en Servicetags – Public Cloud.](https://www.microsoft.com/download/details.aspx?id=56519)</span><span class="sxs-lookup"><span data-stu-id="435aa-212">You can find the Azure IP ranges in [Azure IP Ranges and Service Tags – Public Cloud](https://www.microsoft.com/download/details.aspx?id=56519).</span></span>

> [!NOTE]
> <span data-ttu-id="435aa-213">Als cloudoplossing kunnen de IP-adresbereiken worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="435aa-213">As a cloud-based solution, the IP address ranges can change.</span></span> <span data-ttu-id="435aa-214">U wordt aangeraden over te gaan op regels op basis van DNS.</span><span class="sxs-lookup"><span data-stu-id="435aa-214">It's recommended you move to DNS-based rules.</span></span>

> [!NOTE]
> <span data-ttu-id="435aa-215">Als u een klant van de Amerikaanse overheid bent, raadpleegt u de bijbehorende sectie op de [pagina Defender for Endpoint for US Government.](gov.md#service-backend-ip-ranges)</span><span class="sxs-lookup"><span data-stu-id="435aa-215">If you are a US Government customer, please see the corresponding section in the [Defender for Endpoint for US Government](gov.md#service-backend-ip-ranges) page.</span></span>

## <a name="next-step"></a><span data-ttu-id="435aa-216">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="435aa-216">Next step</span></span>

<span data-ttu-id="435aa-217">![**Fase 3: Onboard**](images/onboard.png)</span><span class="sxs-lookup"><span data-stu-id="435aa-217">![**Phase 3: Onboard**](images/onboard.png)</span></span> <br><span data-ttu-id="435aa-218">[Fase 3: Onboard:](onboarding.md)Apparaten aan boord van de service, zodat de Microsoft Defender voor Eindpunt-service sensorgegevens van deze apparaten kan krijgen.</span><span class="sxs-lookup"><span data-stu-id="435aa-218">[Phase 3: Onboard](onboarding.md): Onboard devices to the service so that the Microsoft Defender for Endpoint service can get sensor data from them.</span></span> 
