---
title: Microsoft Defender voor eindpunt implementeren in ringen
description: Meer informatie over het implementeren van Microsoft Defender voor eindpunten in ringen
keywords: deploy, rings, evaluate, pilot, insider fast, insider slow, setup, onboard, phase, deployment, deploying, adoption, configuring
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
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5aeaa51e5ab8974c8ca26453534396dac14b5853
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297202"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a><span data-ttu-id="142a3-104">Microsoft Defender voor eindpunt implementeren in ringen</span><span class="sxs-lookup"><span data-stu-id="142a3-104">Deploy Microsoft Defender for Endpoint in rings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="142a3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="142a3-105">**Applies to:**</span></span>
- [<span data-ttu-id="142a3-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="142a3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="142a3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="142a3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="142a3-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="142a3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="142a3-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="142a3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="142a3-110">Het implementeren van Microsoft Defender voor Endpoint kan worden uitgevoerd met behulp van een ringgebaseerde implementatiebenadering.</span><span class="sxs-lookup"><span data-stu-id="142a3-110">Deploying Microsoft Defender for Endpoint can be done using a ring-based deployment approach.</span></span> 

<span data-ttu-id="142a3-111">De implementatieringen kunnen in de volgende scenario's worden toegepast:</span><span class="sxs-lookup"><span data-stu-id="142a3-111">The deployment rings can be applied in the following scenarios:</span></span>
- [<span data-ttu-id="142a3-112">Nieuwe implementaties</span><span class="sxs-lookup"><span data-stu-id="142a3-112">New deployments</span></span>](#new-deployments)
- [<span data-ttu-id="142a3-113">Bestaande implementaties</span><span class="sxs-lookup"><span data-stu-id="142a3-113">Existing deployments</span></span>](#existing-deployments)

## <a name="new-deployments"></a><span data-ttu-id="142a3-114">Nieuwe implementaties</span><span class="sxs-lookup"><span data-stu-id="142a3-114">New deployments</span></span>

![Afbeelding van implementatieringen](images/deployment-rings.png)


<span data-ttu-id="142a3-116">Een ringbenadering is een methode om een set eindpunten aan boord te identificeren en te controleren of aan bepaalde criteria wordt voldaan voordat u doorgaat met het implementeren van de service naar een grotere set apparaten.</span><span class="sxs-lookup"><span data-stu-id="142a3-116">A ring-based approach is a method of identifying a set of endpoints to onboard and verifying that certain criteria is met before proceeding to deploy the service to a larger set of devices.</span></span> <span data-ttu-id="142a3-117">U kunt de criteria voor het afsluiten van elke ring definiëren en ervoor zorgen dat ze tevreden zijn voordat u naar de volgende ring gaat.</span><span class="sxs-lookup"><span data-stu-id="142a3-117">You can define the exit criteria for each ring and ensure that they are satisfied before moving on to the next ring.</span></span>

<span data-ttu-id="142a3-118">Het implementeren van een ringgebaseerde implementatie helpt mogelijke problemen te beperken die zich kunnen voordoen tijdens de implementatie van de service.</span><span class="sxs-lookup"><span data-stu-id="142a3-118">Adopting a ring-based deployment helps reduce potential issues that could arise while rolling out the service.</span></span> <span data-ttu-id="142a3-119">Als u eerst een bepaald aantal apparaten test, kunt u potentiële problemen identificeren en mogelijke risico's beperken die zich kunnen voordoen.</span><span class="sxs-lookup"><span data-stu-id="142a3-119">By piloting a certain number of devices first, you can identify potential issues and mitigate potential risks that might arise.</span></span> 


<span data-ttu-id="142a3-120">Tabel 1 geeft een voorbeeld van de implementatieringen die u mogelijk gebruikt.</span><span class="sxs-lookup"><span data-stu-id="142a3-120">Table 1 provides an example of the deployment rings you might use.</span></span> 

<span data-ttu-id="142a3-121">**Tabel 1**</span><span class="sxs-lookup"><span data-stu-id="142a3-121">**Table 1**</span></span>

|<span data-ttu-id="142a3-122">**Implementatiering**</span><span class="sxs-lookup"><span data-stu-id="142a3-122">**Deployment ring**</span></span>|<span data-ttu-id="142a3-123">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="142a3-123">**Description**</span></span>|
|:-----|:-----|
<span data-ttu-id="142a3-124">Evalueren</span><span class="sxs-lookup"><span data-stu-id="142a3-124">Evaluate</span></span> | <span data-ttu-id="142a3-125">Ring 1: 50 systemen identificeren voor testproeven</span><span class="sxs-lookup"><span data-stu-id="142a3-125">Ring 1: Identify 50 systems for pilot testing</span></span> 
<span data-ttu-id="142a3-126">Pilot</span><span class="sxs-lookup"><span data-stu-id="142a3-126">Pilot</span></span> | <span data-ttu-id="142a3-127">Ring 2: de volgende 50-100 eindpunten in de productieomgeving identificeren</span><span class="sxs-lookup"><span data-stu-id="142a3-127">Ring 2: Identify the next 50-100  endpoints in production environment</span></span> <br>  
<span data-ttu-id="142a3-128">Volledige implementatie</span><span class="sxs-lookup"><span data-stu-id="142a3-128">Full deployment</span></span> | <span data-ttu-id="142a3-129">Ring 3: Service in grotere stappen uitrollen naar de rest van de omgeving</span><span class="sxs-lookup"><span data-stu-id="142a3-129">Ring 3: Roll out service to the rest of environment in larger increments</span></span>



### <a name="exit-criteria"></a><span data-ttu-id="142a3-130">Criteria afsluiten</span><span class="sxs-lookup"><span data-stu-id="142a3-130">Exit criteria</span></span>
<span data-ttu-id="142a3-131">Een voorbeeldset met exitcriteria voor deze ringen kan bestaan uit:</span><span class="sxs-lookup"><span data-stu-id="142a3-131">An example set of exit criteria for these rings can include:</span></span>
- <span data-ttu-id="142a3-132">Apparaten worden weergegeven in de lijst met apparaatvoorraad</span><span class="sxs-lookup"><span data-stu-id="142a3-132">Devices show up in the device inventory list</span></span>
- <span data-ttu-id="142a3-133">Waarschuwingen worden weergegeven in dashboard</span><span class="sxs-lookup"><span data-stu-id="142a3-133">Alerts appear in dashboard</span></span>
- [<span data-ttu-id="142a3-134">Een detectietest uitvoeren</span><span class="sxs-lookup"><span data-stu-id="142a3-134">Run a detection test</span></span>](run-detection-test.md)
- [<span data-ttu-id="142a3-135">Een gesimuleerde aanval uitvoeren op een apparaat</span><span class="sxs-lookup"><span data-stu-id="142a3-135">Run a simulated attack on a device</span></span>](attack-simulations.md)

### <a name="evaluate"></a><span data-ttu-id="142a3-136">Evalueren</span><span class="sxs-lookup"><span data-stu-id="142a3-136">Evaluate</span></span>
<span data-ttu-id="142a3-137">Identificeer een klein aantal testapparaten in uw omgeving om aan te boord van de service.</span><span class="sxs-lookup"><span data-stu-id="142a3-137">Identify a small number of test machines in your environment to onboard to the service.</span></span> <span data-ttu-id="142a3-138">In het ideale ideale situatie zijn deze machines minder dan 50 eindpunten.</span><span class="sxs-lookup"><span data-stu-id="142a3-138">Ideally, these machines would be fewer than 50 endpoints.</span></span> 


### <a name="pilot"></a><span data-ttu-id="142a3-139">Pilot</span><span class="sxs-lookup"><span data-stu-id="142a3-139">Pilot</span></span>
<span data-ttu-id="142a3-140">Microsoft Defender voor Eindpunt ondersteunt diverse eindpunten die u aan boord van de service kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="142a3-140">Microsoft Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> <span data-ttu-id="142a3-141">Identificeer in deze ring verschillende apparaten aan boord en op basis van de exitcriteria die u definieert, besluit u door te gaan naar de volgende implementatiering.</span><span class="sxs-lookup"><span data-stu-id="142a3-141">In this ring, identify several devices to onboard and based on the exit criteria you define, decide to proceed to the next deployment ring.</span></span>

<span data-ttu-id="142a3-142">In de volgende tabel ziet u de ondersteunde eindpunten en het bijbehorende hulpprogramma dat u kunt gebruiken om apparaten aan te boord van de service.</span><span class="sxs-lookup"><span data-stu-id="142a3-142">The following table shows the supported endpoints and the corresponding tool you can use to onboard devices to the service.</span></span> 

| <span data-ttu-id="142a3-143">Eindpunt</span><span class="sxs-lookup"><span data-stu-id="142a3-143">Endpoint</span></span>     | <span data-ttu-id="142a3-144">Implementatiehulpmiddel</span><span class="sxs-lookup"><span data-stu-id="142a3-144">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="142a3-145">**Windows**</span><span class="sxs-lookup"><span data-stu-id="142a3-145">**Windows**</span></span>  |  [<span data-ttu-id="142a3-146">Lokaal script (maximaal 10 apparaten)</span><span class="sxs-lookup"><span data-stu-id="142a3-146">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br> <span data-ttu-id="142a3-147">OPMERKING: Als u meer dan tien apparaten wilt implementeren in een productieomgeving, gebruikt u in plaats daarvan de methode Groepsbeleid of de andere ondersteunde hulpmiddelen die hieronder worden vermeld.</span><span class="sxs-lookup"><span data-stu-id="142a3-147">NOTE: If you want to deploy more than 10 devices in a production environment, use the Group Policy method instead or the other supported tools listed below.</span></span><br>  [<span data-ttu-id="142a3-148">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="142a3-148">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="142a3-149">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="142a3-149">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="142a3-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="142a3-150">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="142a3-151">VDI-scripts</span><span class="sxs-lookup"><span data-stu-id="142a3-151">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="142a3-152">**macOS**</span><span class="sxs-lookup"><span data-stu-id="142a3-152">**macOS**</span></span>    | [<span data-ttu-id="142a3-153">Lokaal script</span><span class="sxs-lookup"><span data-stu-id="142a3-153">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="142a3-154">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="142a3-154">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="142a3-155">JAMF-Pro</span><span class="sxs-lookup"><span data-stu-id="142a3-155">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="142a3-156">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="142a3-156">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="142a3-157">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="142a3-157">**Linux Server**</span></span> | [<span data-ttu-id="142a3-158">Lokaal script</span><span class="sxs-lookup"><span data-stu-id="142a3-158">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="142a3-159">Poppop</span><span class="sxs-lookup"><span data-stu-id="142a3-159">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="142a3-160">Ansible</span><span class="sxs-lookup"><span data-stu-id="142a3-160">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="142a3-161">**iOS**</span><span class="sxs-lookup"><span data-stu-id="142a3-161">**iOS**</span></span>      | [<span data-ttu-id="142a3-162">App-gebaseerde</span><span class="sxs-lookup"><span data-stu-id="142a3-162">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="142a3-163">**Android**</span><span class="sxs-lookup"><span data-stu-id="142a3-163">**Android**</span></span>  | [<span data-ttu-id="142a3-164">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="142a3-164">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




### <a name="full-deployment"></a><span data-ttu-id="142a3-165">Volledige implementatie</span><span class="sxs-lookup"><span data-stu-id="142a3-165">Full deployment</span></span>
<span data-ttu-id="142a3-166">In dit stadium kunt u het implementatiemateriaal [plannen](deployment-strategy.md) gebruiken om uw implementatie te plannen.</span><span class="sxs-lookup"><span data-stu-id="142a3-166">At this stage, you can use the [Plan deployment](deployment-strategy.md) material to help you plan your deployment.</span></span> 


<span data-ttu-id="142a3-167">Gebruik het volgende materiaal om de juiste Microsoft Defender voor eindpuntarchitectuur te selecteren die het beste past bij uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="142a3-167">Use the following material to select the appropriate Microsoft Defender for Endpoint architecture that best suites your organization.</span></span>

|<span data-ttu-id="142a3-168">**Item**</span><span class="sxs-lookup"><span data-stu-id="142a3-168">**Item**</span></span>|<span data-ttu-id="142a3-169">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="142a3-169">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="142a3-170">[![Thumb image for Microsoft Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="142a3-170">[![Thumb image for Microsoft Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="142a3-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="142a3-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="142a3-172">Met het materiaal voor architecten kunt u uw implementatie plannen voor de volgende architecturen:</span><span class="sxs-lookup"><span data-stu-id="142a3-172">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="142a3-173">Cloud-native</span><span class="sxs-lookup"><span data-stu-id="142a3-173">Cloud-native</span></span> </li><li> <span data-ttu-id="142a3-174">Co-management</span><span class="sxs-lookup"><span data-stu-id="142a3-174">Co-management</span></span> </li><li> <span data-ttu-id="142a3-175">On-premises</span><span class="sxs-lookup"><span data-stu-id="142a3-175">On-premise</span></span></li><li><span data-ttu-id="142a3-176">Evaluatie en lokale onboarding</span><span class="sxs-lookup"><span data-stu-id="142a3-176">Evaluation and local onboarding</span></span></li>




## <a name="existing-deployments"></a><span data-ttu-id="142a3-177">Bestaande implementaties</span><span class="sxs-lookup"><span data-stu-id="142a3-177">Existing deployments</span></span>

### <a name="windows-endpoints"></a><span data-ttu-id="142a3-178">Windows eindpunten</span><span class="sxs-lookup"><span data-stu-id="142a3-178">Windows endpoints</span></span>
<span data-ttu-id="142a3-179">Voor Windows en/of Windows-servers selecteert u verschillende machines die u van tevoren wilt testen (vóór patchdinsdag) met behulp van het BEVEILIGINGSupdatevalidatieprogramma **(SUVP).**</span><span class="sxs-lookup"><span data-stu-id="142a3-179">For Windows and/or Windows Servers, you select several machines to test ahead of time (before patch Tuesday) by using the **Security Update Validation program (SUVP)**.</span></span>

<span data-ttu-id="142a3-180">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="142a3-180">For more information, see:</span></span>
- [<span data-ttu-id="142a3-181">Wat is het validatieprogramma voor beveiligingsupdates</span><span class="sxs-lookup"><span data-stu-id="142a3-181">What is the Security Update Validation Program</span></span>](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [<span data-ttu-id="142a3-182">Software Update Validation Program and Microsoft Centrum voor beveiliging tegen schadelijke software Establishment - TwC Interactive Timeline Part 4</span><span class="sxs-lookup"><span data-stu-id="142a3-182">Software Update Validation Program and Microsoft Malware Protection Center Establishment - TwC Interactive Timeline Part 4</span></span>](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)


### <a name="non-windows-endpoints"></a><span data-ttu-id="142a3-183">Niet-Windows eindpunten</span><span class="sxs-lookup"><span data-stu-id="142a3-183">Non-Windows endpoints</span></span>
<span data-ttu-id="142a3-184">Met macOS en Linux kunt u een paar systemen gebruiken en uitvoeren in het Beta-kanaal.</span><span class="sxs-lookup"><span data-stu-id="142a3-184">With macOS and Linux, you could take a couple of systems and run in the Beta channel.</span></span>

>[!NOTE]
><span data-ttu-id="142a3-185">Idealiter ten minste één beveiligingsbeheerder en één ontwikkelaar, zodat u compatibiliteits-, prestatie- en betrouwbaarheidsproblemen kunt vinden voordat de build in het huidige kanaal wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="142a3-185">Ideally at least one security admin and one developer so that you are able to find compatibility, performance and reliability issues before the build makes it into the Current channel.</span></span>

<span data-ttu-id="142a3-186">De keuze van het kanaal bepaalt het type en de frequentie van de updates die op uw apparaat worden aangeboden.</span><span class="sxs-lookup"><span data-stu-id="142a3-186">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="142a3-187">Apparaten in bètaversie zijn de eerste apparaten die updates en nieuwe functies ontvangen, later gevolgd door Preview en ten laatste door Current.</span><span class="sxs-lookup"><span data-stu-id="142a3-187">Devices in Beta are the first ones to receive updates and new features, followed later by Preview and lastly by Current.</span></span>

![Afbeelding van insiderringen](images/insider-rings.png)

<span data-ttu-id="142a3-189">Als u een voorbeeld van nieuwe functies wilt bekijken en vroegtijdig feedback wilt geven, wordt u aangeraden sommige apparaten in uw bedrijf te configureren voor het gebruik van bèta of preview.</span><span class="sxs-lookup"><span data-stu-id="142a3-189">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either Beta or Preview.</span></span>

>[!WARNING]
><span data-ttu-id="142a3-190">Als u het kanaal na de eerste installatie overschakelt, moet het product opnieuw worden geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="142a3-190">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="142a3-191">Als u het productkanaal wilt wijzigen: verwijder het bestaande pakket, configureer het apparaat opnieuw om het nieuwe kanaal te gebruiken en volg de stappen in dit document om het pakket vanaf de nieuwe locatie te installeren.</span><span class="sxs-lookup"><span data-stu-id="142a3-191">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>
