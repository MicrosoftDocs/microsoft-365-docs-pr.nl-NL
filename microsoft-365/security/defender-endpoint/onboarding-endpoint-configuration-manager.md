---
title: Onboarden met behulp van Microsoft Endpoint Configuration Manager
description: Meer informatie over het onboarden van Microsoft Defender voor Eindpunt met Microsoft Endpoint Configuration Manager
keywords: onboarding, configuration, deploy, deployment, endpoint configuration manager, Microsoft Defender for Endpoint, collection creation, endpoint detection response, next generation protection, attack surface reduction, microsoft endpoint configuration manager
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 84273ce3e060eb86ee246a5cc6a8cae3cba743b5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934487"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="ee927-104">Onboarden met behulp van Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ee927-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ee927-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ee927-105">**Applies to:**</span></span>
- [<span data-ttu-id="ee927-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="ee927-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ee927-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ee927-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ee927-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="ee927-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ee927-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="ee927-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="ee927-110">Dit artikel maakt deel uit van de implementatiehandleiding en fungeert als voorbeeld voor onboarding.</span><span class="sxs-lookup"><span data-stu-id="ee927-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="ee927-111">In het [onderwerp Planning](deployment-strategy.md) zijn verschillende methoden beschikbaar gesteld voor onboard-apparaten voor de service.</span><span class="sxs-lookup"><span data-stu-id="ee927-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="ee927-112">In dit onderwerp wordt de architectuur voor comanagement besproken.</span><span class="sxs-lookup"><span data-stu-id="ee927-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="ee927-113">![Afbeelding van cloud-native architectuur ](images/co-management-architecture.png)
 *Diagram van omgevingsarchitectuur*</span><span class="sxs-lookup"><span data-stu-id="ee927-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="ee927-114">Hoewel Defender voor Eindpunt ondersteuning biedt voor onboarding van verschillende eindpunten en hulpprogramma's, worden deze niet in dit artikel beschreven.</span><span class="sxs-lookup"><span data-stu-id="ee927-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="ee927-115">Zie Onboarding overview (Overzicht van onboarding) voor informatie over algemene onboarding met behulp van andere ondersteunde implementatiehulpmiddelen en [-methoden.](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="ee927-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="ee927-116">In dit onderwerp worden gebruikers begeleid in:</span><span class="sxs-lookup"><span data-stu-id="ee927-116">This topic guides users in:</span></span>
- <span data-ttu-id="ee927-117">Stap 1: Windows-apparaten onboarden bij de service</span><span class="sxs-lookup"><span data-stu-id="ee927-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="ee927-118">Stap 2: Defender configureren voor endpoint-mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="ee927-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="ee927-119">Met deze onboarding-richtlijnen wordt u begeleid door de volgende basisstappen die u moet nemen bij het gebruik van Microsoft Endpoint Configuration Manager:</span><span class="sxs-lookup"><span data-stu-id="ee927-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="ee927-120">**Een verzameling maken in Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="ee927-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="ee927-121">**Microsoft Defender configureren voor endpoint-mogelijkheden met Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="ee927-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="ee927-122">Alleen Windows-apparaten worden in dit voorbeeld geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="ee927-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="ee927-123">Stap 1: Windows-apparaten onboarden met Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ee927-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="ee927-124">Verzameling maken</span><span class="sxs-lookup"><span data-stu-id="ee927-124">Collection creation</span></span>
<span data-ttu-id="ee927-125">Als u Windows 10-apparaten wilt onboarden met Microsoft Endpoint Configuration Manager, kan de implementatie gericht zijn op een bestaande verzameling of kan er een nieuwe verzameling worden gemaakt om te testen.</span><span class="sxs-lookup"><span data-stu-id="ee927-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="ee927-126">Onboarding met behulp van hulpmiddelen, zoals groepsbeleid of handmatige methode, installeert geen agent op het systeem.</span><span class="sxs-lookup"><span data-stu-id="ee927-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="ee927-127">In de Microsoft Endpoint Configuration Manager-console wordt het onboardingproces geconfigureerd als onderdeel van de compliance-instellingen binnen de console.</span><span class="sxs-lookup"><span data-stu-id="ee927-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="ee927-128">Elk systeem dat deze vereiste configuratie ontvangt, blijft die configuratie behouden zolang de Configuration Manager-client dit beleid blijft ontvangen vanaf het beheerpunt.</span><span class="sxs-lookup"><span data-stu-id="ee927-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="ee927-129">Volg de onderstaande stappen voor onboard-eindpunten met Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="ee927-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="ee927-130">Navigeer in microsoft Endpoint Configuration Manager-console naar **Apparaatverzamelingen activa en \> \> complianceoverzicht.**</span><span class="sxs-lookup"><span data-stu-id="ee927-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![Afbeelding van de wizard Configuratiebeheer van Microsoft Endpoint1](images/configmgr-device-collections.png)

2. <span data-ttu-id="ee927-132">Klik met de **rechtermuisknop op Apparaatverzameling** en **selecteer Apparaatverzameling maken.**</span><span class="sxs-lookup"><span data-stu-id="ee927-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![Afbeelding van de wizard Configuratiebeheer van Microsoft Endpoint2](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="ee927-134">Geef een **naam en** verzameling **beperken op** en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="ee927-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![Afbeelding van de wizard Configuratiebeheer van Microsoft Endpoint3](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="ee927-136">Selecteer **Regel toevoegen** en kies **Queryregel.**</span><span class="sxs-lookup"><span data-stu-id="ee927-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![Afbeelding van de wizard Configuratiebeheer van Microsoft Endpoint4](images/configmgr-query-rule.png)

5.  <span data-ttu-id="ee927-138">Klik **op Volgende** in de wizard Direct **lidmaatschap** en klik op **Queryverklaring bewerken.**</span><span class="sxs-lookup"><span data-stu-id="ee927-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![Afbeelding van de wizard Configuratiebeheer van Microsoft Endpoint5](images/configmgr-direct-membership.png)

6. <span data-ttu-id="ee927-140">Selecteer **Criteria** en kies vervolgens het sterpictogram.</span><span class="sxs-lookup"><span data-stu-id="ee927-140">Select **Criteria** and then choose the star icon.</span></span>

     ![Afbeelding van de wizard Configuratiebeheer van Microsoft Endpoint6](images/configmgr-criteria.png)

7. <span data-ttu-id="ee927-142">Houd criteriumtype als eenvoudige **waarde,** kies waar als besturingssysteem **- buildnummer**, operator **groter dan** of gelijk aan en waarde **14393** en klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="ee927-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![Afbeelding van de wizard Configuratiebeheer van Microsoft Endpoint7](images/configmgr-simple-value.png)

8. <span data-ttu-id="ee927-144">Selecteer **Volgende** en **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="ee927-144">Select **Next** and **Close**.</span></span>

    ![Afbeelding van de wizard Configuratiebeheer van Microsoft Endpoint8](images/configmgr-membership-rules.png)

9. <span data-ttu-id="ee927-146">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="ee927-146">Select **Next**.</span></span>

    ![Afbeelding van de wizard Configuratiebeheer van Microsoft Endpoint9](images/configmgr-confirm.png)


<span data-ttu-id="ee927-148">Na het voltooien van deze taak hebt u nu een apparaatverzameling met alle Windows 10-eindpunten in de omgeving.</span><span class="sxs-lookup"><span data-stu-id="ee927-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="ee927-149">Stap 2: Microsoft Defender configureren voor endpoint-mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="ee927-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="ee927-150">In deze sectie wordt u begeleid bij het configureren van de volgende mogelijkheden met Microsoft Endpoint Configuration Manager op Windows-apparaten:</span><span class="sxs-lookup"><span data-stu-id="ee927-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="ee927-151">**Detectie van en reactie op eindpunt**</span><span class="sxs-lookup"><span data-stu-id="ee927-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="ee927-152">**Beveiliging van de volgende generatie**</span><span class="sxs-lookup"><span data-stu-id="ee927-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="ee927-153">**Kwetsbaarheid voor aanvallen verminderen**</span><span class="sxs-lookup"><span data-stu-id="ee927-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="ee927-154">Detectie van en reactie op eindpunt</span><span class="sxs-lookup"><span data-stu-id="ee927-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="ee927-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ee927-155">Windows 10</span></span>
<span data-ttu-id="ee927-156">Vanuit het Microsoft Defender-beveiligingscentrum is het mogelijk om het '.onboarding'-beleid te downloaden dat kan worden gebruikt om het beleid te maken in System Center Configuration Manager en dat beleid te implementeren op Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="ee927-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="ee927-157">Selecteer instellingen en [onboarding](https://securitycenter.windows.com/preferences2/onboarding)in een Microsoft Defender-beveiligingscentrumportal.</span><span class="sxs-lookup"><span data-stu-id="ee927-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="ee927-158">Selecteer onder Implementatiemethode de ondersteunde versie van **Microsoft Endpoint Configuration Manager.**</span><span class="sxs-lookup"><span data-stu-id="ee927-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![Afbeelding van de wizard Onboarding van Microsoft Defender voor eindpunt10](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="ee927-160">Selecteer **Downloadpakket.**</span><span class="sxs-lookup"><span data-stu-id="ee927-160">Select **Download package**.</span></span>

    ![Afbeelding van de wizard Onboarding van Microsoft Defender voor Eindpunt11](images/mdatp-download-package.png)

4. <span data-ttu-id="ee927-162">Sla het pakket op een toegankelijke locatie op.</span><span class="sxs-lookup"><span data-stu-id="ee927-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="ee927-163">Ga in Microsoft Endpoint Configuration Manager naar: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span><span class="sxs-lookup"><span data-stu-id="ee927-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="ee927-164">Klik met de rechtermuisknop **op Microsoft Defender ATP-beleid** en selecteer **Microsoft Defender ATP-beleid maken.**</span><span class="sxs-lookup"><span data-stu-id="ee927-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![Afbeelding van de wizard Configuratiebeheer van Microsoft Endpoint12](images/configmgr-create-policy.png)

7. <span data-ttu-id="ee927-166">Voer de naam en beschrijving in, controleer **of Onboarding** is geselecteerd en selecteer **volgende.**</span><span class="sxs-lookup"><span data-stu-id="ee927-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![Afbeelding van de wizard Configuratiebeheer van Microsoft Endpoint13](images/configmgr-policy-name.png)


8. <span data-ttu-id="ee927-168">Klik **op Bladeren**.</span><span class="sxs-lookup"><span data-stu-id="ee927-168">Click **Browse**.</span></span>

9. <span data-ttu-id="ee927-169">Ga vanaf stap 4 hierboven naar de locatie van het gedownloade bestand.</span><span class="sxs-lookup"><span data-stu-id="ee927-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="ee927-170">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="ee927-170">Click **Next**.</span></span>
11. <span data-ttu-id="ee927-171">Configureer de Agent met de juiste steekproeven **(Geen** of **Alle bestandstypen).**</span><span class="sxs-lookup"><span data-stu-id="ee927-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![Afbeelding van configuratie-instellingen1](images/configmgr-config-settings.png)

12. <span data-ttu-id="ee927-173">Selecteer de juiste telemetrie **(Normaal** of **Versneld)** en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="ee927-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![Afbeelding van configuratie-instellingen2](images/configmgr-telemetry.png)

14. <span data-ttu-id="ee927-175">Controleer de configuratie en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="ee927-175">Verify the configuration, then click **Next**.</span></span>

     ![Afbeelding van configuratie-instellingen3](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="ee927-177">Klik **op Sluiten** wanneer de wizard is voltooid.</span><span class="sxs-lookup"><span data-stu-id="ee927-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="ee927-178">Klik in de Microsoft Endpoint Configuration Manager-console met de rechtermuisknop op het Beleid van Defender voor eindpunt dat u zojuist hebt gemaakt en selecteer **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="ee927-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![Afbeelding van configuratie-instellingen4](images/configmgr-deploy.png)

17. <span data-ttu-id="ee927-180">Selecteer in het rechtervenster de eerder gemaakte verzameling en klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="ee927-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![Afbeelding van configuratie-instellingen5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="ee927-182">Vorige versies van Windows Client (Windows 7 en Windows 8.1)</span><span class="sxs-lookup"><span data-stu-id="ee927-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="ee927-183">Volg de onderstaande stappen om de Defender for Endpoint Workspace ID en Workspace Key te identificeren, die nodig zijn voor de onboarding van eerdere versies van Windows.</span><span class="sxs-lookup"><span data-stu-id="ee927-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="ee927-184">Selecteer instellingen voor onboarding in een Microsoft Defender-beveiligingscentrumportal **> Onboarding.**</span><span class="sxs-lookup"><span data-stu-id="ee927-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="ee927-185">Kies onder besturingssysteem **Windows 7 SP1 en 8.1.**</span><span class="sxs-lookup"><span data-stu-id="ee927-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="ee927-186">Kopieer de **werkruimte-id** en **werkruimtesleutel en** sla ze op.</span><span class="sxs-lookup"><span data-stu-id="ee927-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="ee927-187">Ze worden later in het proces gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ee927-187">They will be used later in the process.</span></span>

    ![Afbeelding van onboarding](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="ee927-189">Installeer de Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="ee927-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="ee927-190">MMA wordt momenteel (vanaf januari 2019) ondersteund op de volgende Windows-besturingssystemen:</span><span class="sxs-lookup"><span data-stu-id="ee927-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="ee927-191">Server-SKU's: Windows Server 2008 SP1 of Nieuwer</span><span class="sxs-lookup"><span data-stu-id="ee927-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="ee927-192">Client-SKU's: Windows 7 SP1 en hoger</span><span class="sxs-lookup"><span data-stu-id="ee927-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="ee927-193">De MMA-agent moet worden geïnstalleerd op Windows-apparaten.</span><span class="sxs-lookup"><span data-stu-id="ee927-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="ee927-194">Als u de agent wilt installeren, moeten sommige systemen de update voor klantervaring en diagnostische [telemetrie](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) downloaden om de gegevens met MMA te verzamelen.</span><span class="sxs-lookup"><span data-stu-id="ee927-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="ee927-195">Deze systeemversies omvatten, maar zijn mogelijk niet beperkt tot:</span><span class="sxs-lookup"><span data-stu-id="ee927-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="ee927-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ee927-196">Windows 8.1</span></span>

    -   <span data-ttu-id="ee927-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="ee927-197">Windows 7</span></span>

    -   <span data-ttu-id="ee927-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ee927-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="ee927-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ee927-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="ee927-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ee927-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="ee927-201">Met name voor Windows 7 SP1 moeten de volgende patches zijn geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="ee927-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="ee927-202">[KB4074598 installeren](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="ee927-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="ee927-203">Installeer [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (of hoger) **of** 
         [KB3154518.](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="ee927-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="ee927-204">Installeer beide niet op hetzelfde systeem.</span><span class="sxs-lookup"><span data-stu-id="ee927-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="ee927-205">Zie de sectie Proxyinstellingen configureren als u een proxy gebruikt om verbinding te maken met internet.</span><span class="sxs-lookup"><span data-stu-id="ee927-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="ee927-206">Wanneer u klaar bent, ziet u binnen een uur onboarded eindpunten in de portal.</span><span class="sxs-lookup"><span data-stu-id="ee927-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="ee927-207">Beveiliging van de volgende generatie</span><span class="sxs-lookup"><span data-stu-id="ee927-207">Next generation protection</span></span> 
<span data-ttu-id="ee927-208">Microsoft Defender Antivirus is een ingebouwde antimalwareoplossing die de volgende generatie bescherming biedt voor desktops, draagbare computers en servers.</span><span class="sxs-lookup"><span data-stu-id="ee927-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="ee927-209">Ga in de Microsoft Endpoint Configuration Manager-console naar **Assets and Compliance Overview \> \> Endpoint Protection \> Antimalware Polices** en kies **Antimalwarebeleid maken.**</span><span class="sxs-lookup"><span data-stu-id="ee927-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![Afbeelding van antimalwarebeleid](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="ee927-211">Selecteer **Geplande scans**, **Scaninstellingen**, **Standaardacties**, **Realtime** beveiliging **,** **Uitsluitingsinstellingen**, **Geavanceerd**, Bedreiging overschrijven , **Cloud Protection Service** en **Beveiligingsintelligentie-updates** en kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="ee927-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![Afbeelding van het volgende beschermingsvenster1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="ee927-213">In bepaalde bedrijfstakken of sommige geselecteerde zakelijke klanten hebben mogelijk specifieke behoeften voor de configuratie van Antivirus.</span><span class="sxs-lookup"><span data-stu-id="ee927-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="ee927-214">Snelle scan versus volledige scan en aangepaste scan</span><span class="sxs-lookup"><span data-stu-id="ee927-214">Quick scan versus full scan and custom scan</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="ee927-215">Zie Windows [Security configuration framework (Configuratiekader voor Windows-beveiliging) voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="ee927-215">For more details, see [Windows Security configuration framework](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![Afbeelding van het volgende beschermingsvenster2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Afbeelding van het volgende beschermingsvenster3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Afbeelding van het volgende beschermingsvenster4](images/a28afc02c1940d5220b233640364970c.png)

    ![Afbeelding van het volgende beschermingsvenster5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Afbeelding van het volgende beschermingsvenster6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Afbeelding van het volgende beschermingsvenster7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Afbeelding van het volgende beschermingsvenster8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Afbeelding van het volgende beschermingsvenster9](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="ee927-224">Klik met de rechtermuisknop op het nieuw gemaakte antimalwarebeleid en selecteer **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="ee927-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![Afbeelding van het volgende beveiligingsvenster10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="ee927-226">Richt het nieuwe antimalwarebeleid op uw Windows 10-verzameling en klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="ee927-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![Afbeelding van het volgende beschermingsvenster11](images/configmgr-select-collection.png)

<span data-ttu-id="ee927-228">Nadat u deze taak hebt voltooid, hebt u Windows Defender Antivirus nu geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="ee927-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="ee927-229">Kwetsbaarheid voor aanvallen verminderen</span><span class="sxs-lookup"><span data-stu-id="ee927-229">Attack surface reduction</span></span>
<span data-ttu-id="ee927-230">De attack surface reduction-pijler van Defender for Endpoint bevat de functieset die beschikbaar is onder Exploit Guard.</span><span class="sxs-lookup"><span data-stu-id="ee927-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="ee927-231">Asr-regels (Attack Surface Reduction), Controlled Folder Access, Network Protection en Exploit Protection.</span><span class="sxs-lookup"><span data-stu-id="ee927-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="ee927-232">Al deze functies bieden een auditmodus en een blokmodus.</span><span class="sxs-lookup"><span data-stu-id="ee927-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="ee927-233">In de auditmodus is er geen effect op de eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="ee927-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="ee927-234">Het enige wat u doet, is extra telemetrie verzamelen en beschikbaar maken in het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="ee927-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="ee927-235">Het doel van een implementatie is om beveiligingsbesturingselementen stapsgewijs naar de blokmodus te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="ee927-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="ee927-236">Asr-regels instellen in de auditmodus:</span><span class="sxs-lookup"><span data-stu-id="ee927-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="ee927-237">Ga in de Microsoft Endpoint Configuration Manager-console naar **Assets and Compliance Overview \> \> Endpoint Protection Windows Defender Exploit \> Guard** en kies **Beleid voor exploitbeveiliging maken.**</span><span class="sxs-lookup"><span data-stu-id="ee927-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![Afbeelding van Microsoft Endpoint Configuration Manager-console0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="ee927-239">Selecteer **Attack Surface Reduction**.</span><span class="sxs-lookup"><span data-stu-id="ee927-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="ee927-240">Stel regels in op **Controleren** en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="ee927-240">Set rules to **Audit** and click **Next**.</span></span>


    ![Afbeelding van Microsoft Endpoint Configuration Manager-console1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="ee927-242">Bevestig het nieuwe beleid van Exploit Guard door op Volgende te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="ee927-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![Afbeelding van Microsoft Endpoint Configuration Manager-console2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="ee927-244">Wanneer het beleid is gemaakt, klikt u op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="ee927-244">Once the policy is created click **Close**.</span></span>

    ![Afbeelding van Microsoft Endpoint Configuration Manager-console3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Afbeelding van Microsoft Endpoint Manager-console1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="ee927-247">Klik met de rechtermuisknop op het nieuw gemaakte beleid en kies **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="ee927-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![Afbeelding van Microsoft Endpoint Configuration Manager-console4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="ee927-249">Richt het beleid op de nieuw gemaakte Windows 10-verzameling en klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="ee927-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Afbeelding van Microsoft Endpoint Configuration Manager-console5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="ee927-251">Nadat u deze taak hebt voltooid, hebt u nu ASR-regels geconfigureerd in de auditmodus.</span><span class="sxs-lookup"><span data-stu-id="ee927-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="ee927-252">Hieronder vindt u aanvullende stappen om te controleren of ASR-regels correct worden toegepast op eindpunten.</span><span class="sxs-lookup"><span data-stu-id="ee927-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="ee927-253">(Dit kan enkele minuten duren)</span><span class="sxs-lookup"><span data-stu-id="ee927-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="ee927-254">Navigeer vanuit een webbrowser naar <https://securitycenter.windows.com> .</span><span class="sxs-lookup"><span data-stu-id="ee927-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="ee927-255">Selecteer **Configuratiebeheer** in het linkermenu.</span><span class="sxs-lookup"><span data-stu-id="ee927-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="ee927-256">Klik **op Ga naar aanvallen op surface management** in het Surface Management panel van Attack.</span><span class="sxs-lookup"><span data-stu-id="ee927-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![Afbeelding van aanvalsoppervlakbeheer](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="ee927-258">Klik **op het** tabblad Configuratie in rapporten met de surface reduction rules attack.</span><span class="sxs-lookup"><span data-stu-id="ee927-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="ee927-259">Hier ziet u het overzicht van asr-regelsconfiguratie en de status van ASR-regels op elke apparaten.</span><span class="sxs-lookup"><span data-stu-id="ee927-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![Een schermafbeelding van rapporten over de beperkingsregels voor de surface van de aanval1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="ee927-261">Klik op elk apparaat met configuratiedetails van ASR-regels.</span><span class="sxs-lookup"><span data-stu-id="ee927-261">Click each device shows configuration details of ASR rules.</span></span>

    ![Een schermafbeelding van rapporten met regels voor het verlagen van het aanvalsoppervlak2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="ee927-263">Zie [Asr-regelimplementatie en -detecties optimaliseren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ee927-263">See [Optimize ASR rule deployment and detections](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="ee927-264">Regels voor netwerkbeveiliging instellen in de auditmodus:</span><span class="sxs-lookup"><span data-stu-id="ee927-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="ee927-265">Ga in de Microsoft Endpoint Configuration Manager-console naar **Assets and Compliance Overview \> \> Endpoint Protection Windows Defender Exploit \> Guard** en kies **Beleid voor exploitbeveiliging maken.**</span><span class="sxs-lookup"><span data-stu-id="ee927-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Een schermafbeelding van System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="ee927-267">Selecteer **Netwerkbeveiliging.**</span><span class="sxs-lookup"><span data-stu-id="ee927-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="ee927-268">Stel de instelling in op **Controleren** en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="ee927-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![Een schermafbeelding van Systeemcentrum Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="ee927-270">Bevestig het nieuwe beleid voor beveiligingsbeleid door op Volgende te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="ee927-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![Een schermafbeelding Van GUard-beleid misbruiken1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="ee927-272">Wanneer het beleid is gemaakt, klikt u op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="ee927-272">Once the policy is created click on **Close**.</span></span>

    ![Schermafbeelding GUard-beleid misbruiken2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="ee927-274">Klik met de rechtermuisknop op het nieuw gemaakte beleid en kies **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="ee927-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Een schermafbeelding van Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="ee927-276">Selecteer het beleid voor de nieuw gemaakte Windows 10-verzameling en kies **OK.**</span><span class="sxs-lookup"><span data-stu-id="ee927-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![Een schermafbeelding van Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="ee927-278">Nadat u deze taak hebt voltooid, hebt u netwerkbeveiliging nu geconfigureerd in de auditmodus.</span><span class="sxs-lookup"><span data-stu-id="ee927-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="ee927-279">Regels voor gecontroleerde maptoegang instellen in de auditmodus:</span><span class="sxs-lookup"><span data-stu-id="ee927-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="ee927-280">Ga in de Microsoft Endpoint Configuration Manager-console naar **Assets and Compliance Overview \> \> Endpoint Protection Windows Defender Exploit \> Guard** en kies **Beleid voor exploitbeveiliging maken.**</span><span class="sxs-lookup"><span data-stu-id="ee927-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Schermafbeelding van Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="ee927-282">Selecteer **Gecontroleerde maptoegang.**</span><span class="sxs-lookup"><span data-stu-id="ee927-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="ee927-283">Stel de configuratie in op **Controleren** en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="ee927-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![Schermafbeelding van Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="ee927-285">Bevestig het nieuwe beleid voor beveiligingsbeleid door op Volgende te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="ee927-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![Schermafbeelding van Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="ee927-287">Wanneer het beleid is gemaakt, klikt u op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="ee927-287">Once the policy is created click on **Close**.</span></span>

    ![Een schermafbeelding van Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="ee927-289">Klik met de rechtermuisknop op het nieuw gemaakte beleid en kies **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="ee927-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Schermafbeelding van Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="ee927-291">Richt het beleid op de nieuw gemaakte Windows 10-verzameling en klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="ee927-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Een schermafbeelding van Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="ee927-293">U hebt nu beheerde maptoegang geconfigureerd in de auditmodus.</span><span class="sxs-lookup"><span data-stu-id="ee927-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="ee927-294">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="ee927-294">Related topic</span></span>
- [<span data-ttu-id="ee927-295">Onboarden met behulp van Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="ee927-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
