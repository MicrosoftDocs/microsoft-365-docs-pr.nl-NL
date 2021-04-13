---
title: Onboard to the Microsoft Defender for Endpoint service
description: Meer informatie over het onboarden van eindpunten aan Microsoft Defender voor endpoint-service
keywords: ''
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
ms.openlocfilehash: cc538c887397d5bbea78f63c8a8acd318ec7fe9f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689531"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="4bc6f-103">Onboard to the Microsoft Defender for Endpoint service</span><span class="sxs-lookup"><span data-stu-id="4bc6f-103">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4bc6f-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4bc6f-104">**Applies to:**</span></span>
- [<span data-ttu-id="4bc6f-105">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4bc6f-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4bc6f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4bc6f-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="4bc6f-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="4bc6f-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4bc6f-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="4bc6f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="4bc6f-109">Meer informatie over de verschillende fasen van de implementatie van Microsoft Defender voor Eindpunt en hoe u de mogelijkheden binnen de oplossing configureert.</span><span class="sxs-lookup"><span data-stu-id="4bc6f-109">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="4bc6f-110">Het implementeren van Defender voor Eindpunt is een proces in drie fasen:</span><span class="sxs-lookup"><span data-stu-id="4bc6f-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="4bc6f-111">[![implementatiefase - voorbereiden](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="4bc6f-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="4bc6f-112">Fase 1: Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="4bc6f-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="4bc6f-113">[![implementatiefase - installatie](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="4bc6f-113">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="4bc6f-114">Fase 2: Instellen</span><span class="sxs-lookup"><span data-stu-id="4bc6f-114">Phase 2: Setup</span></span>](production-deployment.md) | ![implementatiefase - onboard](images/phase-diagrams/onboard.png)<br><span data-ttu-id="4bc6f-116">Fase 3: Onboarden</span><span class="sxs-lookup"><span data-stu-id="4bc6f-116">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="4bc6f-117">*U bent er!*</span><span class="sxs-lookup"><span data-stu-id="4bc6f-117">*You are here!*</span></span>|

<span data-ttu-id="4bc6f-118">U bent momenteel bezig met de onboardingfase.</span><span class="sxs-lookup"><span data-stu-id="4bc6f-118">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="4bc6f-119">Dit zijn de stappen die u moet ondernemen om Defender voor Eindpunt te implementeren:</span><span class="sxs-lookup"><span data-stu-id="4bc6f-119">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="4bc6f-120">Stap 1: Eindpunten aan boord van de service</span><span class="sxs-lookup"><span data-stu-id="4bc6f-120">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="4bc6f-121">Stap 2: Mogelijkheden configureren</span><span class="sxs-lookup"><span data-stu-id="4bc6f-121">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="4bc6f-122">Stap 1: Onboard-eindpunten met behulp van een van de ondersteunde beheerhulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="4bc6f-122">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="4bc6f-123">Het [implementatieonderwerp](deployment-strategy.md) Plannen bevat een overzicht van de algemene stappen die u moet ondernemen om Defender voor Eindpunt te implementeren.</span><span class="sxs-lookup"><span data-stu-id="4bc6f-123">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="4bc6f-124">Bekijk deze video voor een kort overzicht van het onboardingproces en lees meer over de beschikbare hulpprogramma's en methoden.</span><span class="sxs-lookup"><span data-stu-id="4bc6f-124">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="4bc6f-125">Nadat u de architectuur hebt identificeren, moet u bepalen welke implementatiemethode u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="4bc6f-125">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="4bc6f-126">Het implementatieprogramma dat u kiest, is van invloed op de manier waarop u eindpunten aan boord van de service inwerkt.</span><span class="sxs-lookup"><span data-stu-id="4bc6f-126">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="4bc6f-127">Opties voor onboarding-hulpprogramma's</span><span class="sxs-lookup"><span data-stu-id="4bc6f-127">Onboarding tool options</span></span>

<span data-ttu-id="4bc6f-128">In de volgende tabel ziet u de beschikbare hulpprogramma's op basis van het eindpunt dat u nodig hebt om aan boord te gaan.</span><span class="sxs-lookup"><span data-stu-id="4bc6f-128">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="4bc6f-129">Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4bc6f-129">Endpoint</span></span>     | <span data-ttu-id="4bc6f-130">Opties voor hulpprogramma's</span><span class="sxs-lookup"><span data-stu-id="4bc6f-130">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="4bc6f-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="4bc6f-131">**Windows**</span></span>  |  [<span data-ttu-id="4bc6f-132">Lokaal script (maximaal 10 apparaten)</span><span class="sxs-lookup"><span data-stu-id="4bc6f-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="4bc6f-133">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="4bc6f-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="4bc6f-134">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="4bc6f-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br> [<span data-ttu-id="4bc6f-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4bc6f-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="4bc6f-136">VDI-scripts</span><span class="sxs-lookup"><span data-stu-id="4bc6f-136">VDI scripts</span></span>](configure-endpoints-vdi.md) <br> [<span data-ttu-id="4bc6f-137">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="4bc6f-137">Azure Security Center</span></span>](configure-server-endpoints.md#integration-with-azure-security-center) |
| <span data-ttu-id="4bc6f-138">**macOS**</span><span class="sxs-lookup"><span data-stu-id="4bc6f-138">**macOS**</span></span>    | [<span data-ttu-id="4bc6f-139">Lokale scripts</span><span class="sxs-lookup"><span data-stu-id="4bc6f-139">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="4bc6f-140">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4bc6f-140">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="4bc6f-141">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="4bc6f-141">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="4bc6f-142">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="4bc6f-142">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="4bc6f-143">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="4bc6f-143">**Linux Server**</span></span> | [<span data-ttu-id="4bc6f-144">Lokaal script</span><span class="sxs-lookup"><span data-stu-id="4bc6f-144">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="4bc6f-145">Poppop</span><span class="sxs-lookup"><span data-stu-id="4bc6f-145">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="4bc6f-146">Ansible</span><span class="sxs-lookup"><span data-stu-id="4bc6f-146">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="4bc6f-147">**iOS**</span><span class="sxs-lookup"><span data-stu-id="4bc6f-147">**iOS**</span></span>      | [<span data-ttu-id="4bc6f-148">App-gebaseerde</span><span class="sxs-lookup"><span data-stu-id="4bc6f-148">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="4bc6f-149">**Android**</span><span class="sxs-lookup"><span data-stu-id="4bc6f-149">**Android**</span></span>  | [<span data-ttu-id="4bc6f-150">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4bc6f-150">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="4bc6f-151">Stap 2: Mogelijkheden configureren</span><span class="sxs-lookup"><span data-stu-id="4bc6f-151">Step 2: Configure capabilities</span></span>
<span data-ttu-id="4bc6f-152">Nadat u de eindpunten hebt onboarding, configureert u vervolgens de verschillende mogelijkheden, zoals eindpuntdetectie en -reactie, beveiliging van de volgende generatie en de beperking van het oppervlak van de aanval.</span><span class="sxs-lookup"><span data-stu-id="4bc6f-152">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="4bc6f-153">Voorbeeldimplementaties</span><span class="sxs-lookup"><span data-stu-id="4bc6f-153">Example deployments</span></span>
<span data-ttu-id="4bc6f-154">In deze implementatiehandleiding begeleiden we u bij het gebruik van twee implementatiehulpmiddelen voor het onboarden van eindpunten en het configureren van mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="4bc6f-154">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="4bc6f-155">De hulpprogramma's in de voorbeeldimplementaties zijn:</span><span class="sxs-lookup"><span data-stu-id="4bc6f-155">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="4bc6f-156">Onboarden met behulp van Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4bc6f-156">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="4bc6f-157">Onboarden met behulp van Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4bc6f-157">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="4bc6f-158">Met behulp van de bovenstaande implementatiehulpmiddelen wordt u begeleid bij het configureren van de volgende Mogelijkheden van Defender voor Eindpunt:</span><span class="sxs-lookup"><span data-stu-id="4bc6f-158">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="4bc6f-159">Configuratie van eindpuntdetectie en -antwoord</span><span class="sxs-lookup"><span data-stu-id="4bc6f-159">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="4bc6f-160">Beveiligingsconfiguratie van de volgende generatie</span><span class="sxs-lookup"><span data-stu-id="4bc6f-160">Next-generation protection configuration</span></span>
- <span data-ttu-id="4bc6f-161">Surface Reduction-configuratie voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="4bc6f-161">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="4bc6f-162">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4bc6f-162">Related topics</span></span>
- [<span data-ttu-id="4bc6f-163">Onboarden met behulp van Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4bc6f-163">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="4bc6f-164">Onboarden met behulp van Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4bc6f-164">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
- [<span data-ttu-id="4bc6f-165">Veilige documenten in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4bc6f-165">Safe Documents in Microsoft 365 E5</span></span>](../office-365-security/safe-docs.md)
