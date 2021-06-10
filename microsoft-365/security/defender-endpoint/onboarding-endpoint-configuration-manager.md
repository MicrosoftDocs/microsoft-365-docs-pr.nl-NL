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
ms.openlocfilehash: eab23ddeb9011e80cf2835b8d38b2d3fad4b7089
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843504"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="dbfaa-104">Onboarden met behulp van Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="dbfaa-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dbfaa-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-105">**Applies to:**</span></span>
- [<span data-ttu-id="dbfaa-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="dbfaa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dbfaa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dbfaa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dbfaa-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="dbfaa-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dbfaa-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="dbfaa-110">Dit artikel maakt deel uit van de implementatiehandleiding en fungeert als voorbeeld voor onboarding.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="dbfaa-111">In het [onderwerp Planning](deployment-strategy.md) zijn verschillende methoden beschikbaar gesteld voor onboard-apparaten voor de service.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="dbfaa-112">In dit onderwerp wordt de architectuur voor comanagement besproken.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="dbfaa-113">![Afbeelding van cloud-native architectuur ](images/co-management-architecture.png)
 *Diagram van omgevingsarchitectuur*</span><span class="sxs-lookup"><span data-stu-id="dbfaa-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="dbfaa-114">Hoewel Defender voor Eindpunt ondersteuning biedt voor onboarding van verschillende eindpunten en hulpprogramma's, worden deze niet in dit artikel beschreven.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="dbfaa-115">Zie Onboarding overview (Overzicht van onboarding) voor informatie over algemene onboarding met behulp van andere ondersteunde implementatiehulpmiddelen en [-methoden.](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="dbfaa-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="dbfaa-116">In dit onderwerp worden gebruikers begeleid in:</span><span class="sxs-lookup"><span data-stu-id="dbfaa-116">This topic guides users in:</span></span>
- <span data-ttu-id="dbfaa-117">Stap 1: Onboarding Windows apparaten aan de service</span><span class="sxs-lookup"><span data-stu-id="dbfaa-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="dbfaa-118">Stap 2: Defender configureren voor endpoint-mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="dbfaa-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="dbfaa-119">In deze onboarding-richtlijnen wordt u begeleid door de volgende basisstappen die u moet nemen bij het gebruik van Microsoft Endpoint Configuration Manager:</span><span class="sxs-lookup"><span data-stu-id="dbfaa-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="dbfaa-120">**Een verzameling maken in Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="dbfaa-121">**Microsoft Defender configureren voor endpoint-mogelijkheden met Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="dbfaa-122">Alleen Windows apparaten worden in dit voorbeeld geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="dbfaa-123">Stap 1: Onboard Windows apparaten met Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="dbfaa-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="dbfaa-124">Verzameling maken</span><span class="sxs-lookup"><span data-stu-id="dbfaa-124">Collection creation</span></span>
<span data-ttu-id="dbfaa-125">Als u Windows 10 apparaten met Microsoft Endpoint Configuration Manager wilt gebruiken, kan de implementatie gericht zijn op een bestaande verzameling of kan er een nieuwe verzameling worden gemaakt om te testen.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="dbfaa-126">Onboarding met behulp van hulpmiddelen, zoals groepsbeleid of handmatige methode, installeert geen agent op het systeem.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="dbfaa-127">Binnen de Microsoft Endpoint Configuration Manager console wordt het onboardingproces geconfigureerd als onderdeel van de nalevingsinstellingen binnen de console.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="dbfaa-128">Elk systeem dat deze vereiste configuratie ontvangt, blijft die configuratie behouden zolang de Configuration Manager-client dit beleid blijft ontvangen vanaf het beheerpunt.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="dbfaa-129">Volg de onderstaande stappen om eindpunten aan te Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="dbfaa-130">Navigeer Microsoft Endpoint Configuration Manager console naar **Apparaatverzamelingen activa en \> \> complianceoverzicht.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard1](images/configmgr-device-collections.png)

2. <span data-ttu-id="dbfaa-132">Klik met de **rechtermuisknop op Apparaatverzameling** en **selecteer Apparaatverzameling maken.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard2](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="dbfaa-134">Geef een **naam en** verzameling **beperken op** en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard3](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="dbfaa-136">Selecteer **Regel toevoegen** en kies **Queryregel.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard4](images/configmgr-query-rule.png)

5.  <span data-ttu-id="dbfaa-138">Klik **op Volgende** in de wizard Direct **lidmaatschap** en klik op **Queryverklaring bewerken.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![Afbeelding van Microsoft Endpoint Configuration Manager wizard5](images/configmgr-direct-membership.png)

6. <span data-ttu-id="dbfaa-140">Selecteer **Criteria** en kies vervolgens het sterpictogram.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-140">Select **Criteria** and then choose the star icon.</span></span>

     ![Afbeelding van Microsoft Endpoint Configuration Manager wizard6](images/configmgr-criteria.png)

7. <span data-ttu-id="dbfaa-142">Houd criteriumtype als eenvoudige **waarde,** kies waar als besturingssysteem **- buildnummer**, operator **groter dan** of gelijk aan en waarde **14393** en klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard7](images/configmgr-simple-value.png)

8. <span data-ttu-id="dbfaa-144">Selecteer **Volgende** en **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-144">Select **Next** and **Close**.</span></span>

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard8](images/configmgr-membership-rules.png)

9. <span data-ttu-id="dbfaa-146">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-146">Select **Next**.</span></span>

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard9](images/configmgr-confirm.png)


<span data-ttu-id="dbfaa-148">Na het voltooien van deze taak hebt u nu een apparaatverzameling met alle Windows 10 eindpunten in de omgeving.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="dbfaa-149">Stap 2: Microsoft Defender configureren voor endpoint-mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="dbfaa-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="dbfaa-150">In deze sectie wordt u begeleid bij het configureren van de volgende mogelijkheden met Microsoft Endpoint Configuration Manager op Windows apparaten:</span><span class="sxs-lookup"><span data-stu-id="dbfaa-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="dbfaa-151">**Detectie van en reactie op eindpunt**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="dbfaa-152">**Beveiliging van de volgende generatie**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="dbfaa-153">**Kwetsbaarheid voor aanvallen verminderen**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="dbfaa-154">Detectie van en reactie op eindpunt</span><span class="sxs-lookup"><span data-stu-id="dbfaa-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="dbfaa-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="dbfaa-155">Windows 10</span></span>
<span data-ttu-id="dbfaa-156">Vanuit de Microsoft Defender-beveiligingscentrum is het mogelijk om het '.onboarding'-beleid te downloaden dat kan worden gebruikt om het beleid in System Center Configuration Manager te maken en dat beleid te implementeren op Windows 10 apparaten.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="dbfaa-157">Selecteer in Microsoft Defender-beveiligingscentrum portal Instellingen [en vervolgens Onboarding.](https://securitycenter.windows.com/preferences2/onboarding)</span><span class="sxs-lookup"><span data-stu-id="dbfaa-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="dbfaa-158">Selecteer onder Implementatiemethode de ondersteunde versie van **Microsoft Endpoint Configuration Manager.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![Afbeelding van de wizard Onboarding van Microsoft Defender voor eindpunt10](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="dbfaa-160">Selecteer **Downloadpakket.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-160">Select **Download package**.</span></span>

    ![Afbeelding van de wizard Onboarding van Microsoft Defender voor Eindpunt11](images/mdatp-download-package.png)

4. <span data-ttu-id="dbfaa-162">Sla het pakket op een toegankelijke locatie op.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="dbfaa-163">Ga Microsoft Endpoint Configuration Manager naar: Assets **and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="dbfaa-164">Klik met de **rechtermuisknop Microsoft Defender ATP beleidsregels** en selecteer **Microsoft Defender ATP maken.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard12](images/configmgr-create-policy.png)

7. <span data-ttu-id="dbfaa-166">Voer de naam en beschrijving in, controleer **of Onboarding** is geselecteerd en selecteer **volgende.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![Afbeelding van Microsoft Endpoint Configuration Manager wizard13](images/configmgr-policy-name.png)


8. <span data-ttu-id="dbfaa-168">Klik **op Bladeren**.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-168">Click **Browse**.</span></span>

9. <span data-ttu-id="dbfaa-169">Ga vanaf stap 4 hierboven naar de locatie van het gedownloade bestand.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="dbfaa-170">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-170">Click **Next**.</span></span>
11. <span data-ttu-id="dbfaa-171">Configureer de Agent met de juiste steekproeven **(Geen** of **Alle bestandstypen).**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![Afbeelding van configuratie-instellingen1](images/configmgr-config-settings.png)

12. <span data-ttu-id="dbfaa-173">Selecteer de juiste telemetrie **(Normaal** of **Versneld)** en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![Afbeelding van configuratie-instellingen2](images/configmgr-telemetry.png)

14. <span data-ttu-id="dbfaa-175">Controleer de configuratie en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-175">Verify the configuration, then click **Next**.</span></span>

     ![Afbeelding van configuratie-instellingen3](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="dbfaa-177">Klik **op Sluiten** wanneer de wizard is voltooid.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="dbfaa-178">Klik in Microsoft Endpoint Configuration Manager console met de rechtermuisknop op het Beleid van Defender voor eindpunt dat u zojuist hebt gemaakt en selecteer **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![Afbeelding van configuratie-instellingen4](images/configmgr-deploy.png)

17. <span data-ttu-id="dbfaa-180">Selecteer in het rechtervenster de eerder gemaakte verzameling en klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![Afbeelding van configuratie-instellingen5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="dbfaa-182">Vorige versies van Windows Client (Windows 7 en Windows 8.1)</span><span class="sxs-lookup"><span data-stu-id="dbfaa-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="dbfaa-183">Volg de onderstaande stappen om de Defender for Endpoint Workspace ID en Workspace Key te identificeren, die vereist zijn voor het onboarden van eerdere versies van Windows.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="dbfaa-184">Selecteer in Microsoft Defender-beveiligingscentrum portal Instellingen > **Onboarding.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="dbfaa-185">Kies onder besturingssysteem **Windows 7 SP1 en 8.1**.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="dbfaa-186">Kopieer de **werkruimte-id** en **werkruimtesleutel en** sla ze op.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="dbfaa-187">Ze worden later in het proces gebruikt.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-187">They will be used later in the process.</span></span>

    ![Afbeelding van onboarding](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="dbfaa-189">Installeer de Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="dbfaa-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="dbfaa-190">MMA wordt momenteel (vanaf januari 2019) ondersteund op de volgende Windows besturingssystemen:</span><span class="sxs-lookup"><span data-stu-id="dbfaa-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="dbfaa-191">Server-SKU's: Windows Server 2008 SP1 of Nieuwer</span><span class="sxs-lookup"><span data-stu-id="dbfaa-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="dbfaa-192">Client-SKU's: Windows 7 SP1 en hoger</span><span class="sxs-lookup"><span data-stu-id="dbfaa-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="dbfaa-193">De MMA-agent moet worden geïnstalleerd op Windows apparaten.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="dbfaa-194">Als u de agent wilt installeren, moeten sommige systemen de update voor klantervaring en diagnostische [telemetrie](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) downloaden om de gegevens met MMA te verzamelen.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="dbfaa-195">Deze systeemversies omvatten, maar zijn mogelijk niet beperkt tot:</span><span class="sxs-lookup"><span data-stu-id="dbfaa-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="dbfaa-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="dbfaa-196">Windows 8.1</span></span>

    -   <span data-ttu-id="dbfaa-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="dbfaa-197">Windows 7</span></span>

    -   <span data-ttu-id="dbfaa-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="dbfaa-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="dbfaa-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="dbfaa-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="dbfaa-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="dbfaa-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="dbfaa-201">Met name voor Windows 7 SP1 moeten de volgende patches zijn geïnstalleerd:</span><span class="sxs-lookup"><span data-stu-id="dbfaa-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="dbfaa-202">[KB4074598 installeren](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="dbfaa-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="dbfaa-203">Installeer een [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (of hoger) **of** 
         [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span><span class="sxs-lookup"><span data-stu-id="dbfaa-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="dbfaa-204">Installeer beide niet op hetzelfde systeem.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="dbfaa-205">Zie de sectie Proxyinstellingen configureren als u een proxy gebruikt om verbinding te maken met internet.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="dbfaa-206">Wanneer u klaar bent, ziet u binnen een uur onboarded eindpunten in de portal.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="dbfaa-207">Beveiliging van de volgende generatie</span><span class="sxs-lookup"><span data-stu-id="dbfaa-207">Next generation protection</span></span> 
<span data-ttu-id="dbfaa-208">Microsoft Defender Antivirus is een ingebouwde antimalwareoplossing die de volgende generatie bescherming biedt voor desktops, draagbare computers en servers.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="dbfaa-209">Ga in Microsoft Endpoint Configuration Manager console naar **Assets and Compliance Overview Endpoint Protection \> \> \> Antimalware Polices** en kies **Antimalwarebeleid maken.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![Afbeelding van antimalwarebeleid](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="dbfaa-211">Selecteer **Geplande scans**, **Scaninstellingen**, **Standaardacties**, **Realtime** beveiliging **,** **Uitsluitingsinstellingen**, **Geavanceerd**, Bedreiging overschrijven , **Cloud Protection Service** en **Beveiligingsintelligentie-updates** en kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![Afbeelding van het volgende beschermingsvenster1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="dbfaa-213">In bepaalde bedrijfstakken of sommige geselecteerde zakelijke klanten hebben mogelijk specifieke behoeften voor de configuratie van Antivirus.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="dbfaa-214">Snelle scan versus volledige scan en aangepaste scan</span><span class="sxs-lookup"><span data-stu-id="dbfaa-214">Quick scan versus full scan and custom scan</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="dbfaa-215">Zie Windows-beveiliging [configuratiekader voor meer informatie.](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="dbfaa-215">For more details, see [Windows Security configuration framework](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![Afbeelding van het volgende beschermingsvenster2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Afbeelding van het volgende beschermingsvenster3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Afbeelding van het volgende beschermingsvenster4](images/a28afc02c1940d5220b233640364970c.png)

    ![Afbeelding van het volgende beschermingsvenster5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Afbeelding van het volgende beschermingsvenster6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Afbeelding van het volgende beschermingsvenster7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Afbeelding van het volgende beschermingsvenster8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Afbeelding van het volgende beschermingsvenster9](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="dbfaa-224">Klik met de rechtermuisknop op het nieuw gemaakte antimalwarebeleid en selecteer **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![Afbeelding van het volgende beveiligingsvenster10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="dbfaa-226">Richt het nieuwe antimalwarebeleid op uw Windows 10 en klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![Afbeelding van het volgende beschermingsvenster11](images/configmgr-select-collection.png)

<span data-ttu-id="dbfaa-228">Nadat u deze taak hebt voltooid, hebt u de Windows Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="dbfaa-229">Kwetsbaarheid voor aanvallen verminderen</span><span class="sxs-lookup"><span data-stu-id="dbfaa-229">Attack surface reduction</span></span>
<span data-ttu-id="dbfaa-230">De attack surface reduction-pijler van Defender for Endpoint bevat de functieset die beschikbaar is onder Exploit Guard.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="dbfaa-231">Asr-regels (Attack Surface Reduction), Controlled Folder Access, Network Protection en Exploit Protection.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="dbfaa-232">Al deze functies bieden een auditmodus en een blokmodus.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="dbfaa-233">In de auditmodus is er geen effect op de eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="dbfaa-234">Het enige wat u doet, is extra telemetrie verzamelen en beschikbaar maken in de Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="dbfaa-235">Het doel van een implementatie is om beveiligingsbesturingselementen stapsgewijs naar de blokmodus te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="dbfaa-236">Asr-regels instellen in de auditmodus:</span><span class="sxs-lookup"><span data-stu-id="dbfaa-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="dbfaa-237">Ga in Microsoft Endpoint Configuration Manager console naar **Assets and Compliance \> Overview Endpoint Protection Windows Defender Exploit \> \> Guard** en kies **Exploit Guard Policy maken.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![Afbeelding van Microsoft Endpoint Configuration Manager console0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="dbfaa-239">Selecteer **Attack Surface Reduction**.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="dbfaa-240">Stel regels in op **Controleren** en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-240">Set rules to **Audit** and click **Next**.</span></span>


    ![Afbeelding van Microsoft Endpoint Configuration Manager console1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="dbfaa-242">Bevestig het nieuwe beleid van Exploit Guard door op Volgende te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![Afbeelding van Microsoft Endpoint Configuration Manager console2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="dbfaa-244">Wanneer het beleid is gemaakt, klikt u op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-244">Once the policy is created click **Close**.</span></span>

    ![Afbeelding van Microsoft Endpoint Configuration Manager console3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Afbeelding van Microsoft Endpoint Manager console1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="dbfaa-247">Klik met de rechtermuisknop op het nieuw gemaakte beleid en kies **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![Afbeelding van Microsoft Endpoint Configuration Manager console4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="dbfaa-249">Richt het beleid op de nieuwe Windows 10 en klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Afbeelding van Microsoft Endpoint Configuration Manager console5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="dbfaa-251">Nadat u deze taak hebt voltooid, hebt u nu ASR-regels geconfigureerd in de auditmodus.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="dbfaa-252">Hieronder vindt u aanvullende stappen om te controleren of ASR-regels correct worden toegepast op eindpunten.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="dbfaa-253">(Dit kan enkele minuten duren)</span><span class="sxs-lookup"><span data-stu-id="dbfaa-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="dbfaa-254">Navigeer vanuit een webbrowser naar <https://securitycenter.windows.com> .</span><span class="sxs-lookup"><span data-stu-id="dbfaa-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="dbfaa-255">Selecteer **Configuratiebeheer** in het linkermenu.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="dbfaa-256">Klik **op Ga naar aanvallen op surface management** in het Surface Management panel van Attack.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![Afbeelding van aanvalsoppervlakbeheer](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="dbfaa-258">Klik **op het** tabblad Configuratie in rapporten met de surface reduction rules attack.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="dbfaa-259">Hier ziet u het overzicht van asr-regelsconfiguratie en de status van ASR-regels op elke apparaten.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![Een schermafbeelding van rapporten over de beperkingsregels voor de surface van de aanval1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="dbfaa-261">Klik op elk apparaat met configuratiedetails van ASR-regels.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-261">Click each device shows configuration details of ASR rules.</span></span>

    ![Een schermafbeelding van rapporten met regels voor het verlagen van het aanvalsoppervlak2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="dbfaa-263">Zie [Asr-regelimplementatie en -detecties optimaliseren](/microsoft-365/security/defender-endpoint/configure-machines-asr)   voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-263">See [Optimize ASR rule deployment and detections](/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="dbfaa-264">Regels voor netwerkbeveiliging instellen in de auditmodus:</span><span class="sxs-lookup"><span data-stu-id="dbfaa-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="dbfaa-265">Ga in Microsoft Endpoint Configuration Manager console naar **Assets and Compliance \> Overview Endpoint Protection Windows Defender Exploit \> \> Guard** en kies **Exploit Guard Policy maken.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Een schermafbeelding System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="dbfaa-267">Selecteer **Netwerkbeveiliging.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="dbfaa-268">Stel de instelling in op **Controleren** en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![Een schermafbeelding System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="dbfaa-270">Bevestig het nieuwe beleid voor beveiligingsbeleid door op Volgende te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![Een schermafbeelding Van GUard-beleid misbruiken1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="dbfaa-272">Wanneer het beleid is gemaakt, klikt u op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-272">Once the policy is created click on **Close**.</span></span>

    ![Schermafbeelding GUard-beleid misbruiken2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="dbfaa-274">Klik met de rechtermuisknop op het nieuw gemaakte beleid en kies **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Een schermafbeelding van Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="dbfaa-276">Selecteer het beleid voor de nieuwe Windows 10 en kies **OK.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![Een schermafbeelding van Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="dbfaa-278">Nadat u deze taak hebt voltooid, hebt u netwerkbeveiliging nu geconfigureerd in de auditmodus.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="dbfaa-279">Regels voor gecontroleerde maptoegang instellen in de auditmodus:</span><span class="sxs-lookup"><span data-stu-id="dbfaa-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="dbfaa-280">Ga in Microsoft Endpoint Configuration Manager console naar **Assets and Compliance \> Overview Endpoint Protection Windows Defender Exploit \> \> Guard** en kies **Exploit Guard Policy maken.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Schermafbeelding van Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="dbfaa-282">Selecteer **Gecontroleerde maptoegang.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="dbfaa-283">Stel de configuratie in op **Controleren** en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![Schermafbeelding van Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="dbfaa-285">Bevestig het nieuwe beleid voor beveiligingsbeleid door op Volgende te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![Schermafbeelding van Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="dbfaa-287">Wanneer het beleid is gemaakt, klikt u op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-287">Once the policy is created click on **Close**.</span></span>

    ![Een schermafbeelding van Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="dbfaa-289">Klik met de rechtermuisknop op het nieuw gemaakte beleid en kies **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Schermafbeelding van Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="dbfaa-291">Richt het beleid op de nieuwe Windows 10 en klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="dbfaa-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Een schermafbeelding van Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="dbfaa-293">U hebt nu beheerde maptoegang geconfigureerd in de auditmodus.</span><span class="sxs-lookup"><span data-stu-id="dbfaa-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="dbfaa-294">Verwant onderwerp</span><span class="sxs-lookup"><span data-stu-id="dbfaa-294">Related topic</span></span>
- [<span data-ttu-id="dbfaa-295">Onboarden met behulp van Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="dbfaa-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
