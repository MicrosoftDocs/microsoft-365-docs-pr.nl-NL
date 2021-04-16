---
title: Onboard to the Microsoft Defender for Endpoint service
description: Meer informatie over het onboarden van eindpunten aan Microsoft Defender voor endpoint-service
keywords: Microsoft Defender voor eindpunt, onboard, deploy
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
ms.openlocfilehash: 2a3325a290dc985bdb99a5a843b4b9e1f642a62b
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861801"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="86da6-104">Onboard to the Microsoft Defender for Endpoint service</span><span class="sxs-lookup"><span data-stu-id="86da6-104">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="86da6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="86da6-105">**Applies to:**</span></span>
- [<span data-ttu-id="86da6-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="86da6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="86da6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="86da6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="86da6-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="86da6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="86da6-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="86da6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="86da6-110">Meer informatie over de verschillende fasen van de implementatie van Microsoft Defender voor Eindpunt en hoe u de mogelijkheden binnen de oplossing configureert.</span><span class="sxs-lookup"><span data-stu-id="86da6-110">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="86da6-111">Het implementeren van Defender voor Eindpunt is een proces in drie fasen:</span><span class="sxs-lookup"><span data-stu-id="86da6-111">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="86da6-112">[![implementatiefase - voorbereiden](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="86da6-112">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="86da6-113">Fase 1: Voorbereiden</span><span class="sxs-lookup"><span data-stu-id="86da6-113">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="86da6-114">[![implementatiefase - installatie](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="86da6-114">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="86da6-115">Fase 2: Instellen</span><span class="sxs-lookup"><span data-stu-id="86da6-115">Phase 2: Setup</span></span>](production-deployment.md) | ![implementatiefase - onboard](images/phase-diagrams/onboard.png)<br><span data-ttu-id="86da6-117">Fase 3: Onboarden</span><span class="sxs-lookup"><span data-stu-id="86da6-117">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="86da6-118">*U bent er!*</span><span class="sxs-lookup"><span data-stu-id="86da6-118">*You are here!*</span></span>|

<span data-ttu-id="86da6-119">U bent momenteel bezig met de onboardingfase.</span><span class="sxs-lookup"><span data-stu-id="86da6-119">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="86da6-120">Dit zijn de stappen die u moet ondernemen om Defender voor Eindpunt te implementeren:</span><span class="sxs-lookup"><span data-stu-id="86da6-120">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="86da6-121">Stap 1: Eindpunten aan boord van de service</span><span class="sxs-lookup"><span data-stu-id="86da6-121">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="86da6-122">Stap 2: Mogelijkheden configureren</span><span class="sxs-lookup"><span data-stu-id="86da6-122">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="86da6-123">Stap 1: Onboard-eindpunten met behulp van een van de ondersteunde beheerhulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="86da6-123">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="86da6-124">Het [implementatieonderwerp](deployment-strategy.md) Plannen bevat een overzicht van de algemene stappen die u moet ondernemen om Defender voor Eindpunt te implementeren.</span><span class="sxs-lookup"><span data-stu-id="86da6-124">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="86da6-125">Bekijk deze video voor een kort overzicht van het onboardingproces en lees meer over de beschikbare hulpprogramma's en methoden.</span><span class="sxs-lookup"><span data-stu-id="86da6-125">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="86da6-126">Nadat u de architectuur hebt identificeren, moet u bepalen welke implementatiemethode u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="86da6-126">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="86da6-127">Het implementatieprogramma dat u kiest, is van invloed op de manier waarop u eindpunten aan boord van de service inwerkt.</span><span class="sxs-lookup"><span data-stu-id="86da6-127">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="86da6-128">Opties voor onboarding-hulpprogramma's</span><span class="sxs-lookup"><span data-stu-id="86da6-128">Onboarding tool options</span></span>

<span data-ttu-id="86da6-129">In de volgende tabel ziet u de beschikbare hulpprogramma's op basis van het eindpunt dat u nodig hebt om aan boord te gaan.</span><span class="sxs-lookup"><span data-stu-id="86da6-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="86da6-130">Eindpunt</span><span class="sxs-lookup"><span data-stu-id="86da6-130">Endpoint</span></span>     | <span data-ttu-id="86da6-131">Opties voor hulpprogramma's</span><span class="sxs-lookup"><span data-stu-id="86da6-131">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="86da6-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="86da6-132">**Windows**</span></span>  |  [<span data-ttu-id="86da6-133">Lokaal script (maximaal 10 apparaten)</span><span class="sxs-lookup"><span data-stu-id="86da6-133">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="86da6-134">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="86da6-134">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="86da6-135">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="86da6-135">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br> [<span data-ttu-id="86da6-136">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="86da6-136">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="86da6-137">VDI-scripts</span><span class="sxs-lookup"><span data-stu-id="86da6-137">VDI scripts</span></span>](configure-endpoints-vdi.md) <br> [<span data-ttu-id="86da6-138">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="86da6-138">Azure Security Center</span></span>](configure-server-endpoints.md#integration-with-azure-security-center) |
| <span data-ttu-id="86da6-139">**macOS**</span><span class="sxs-lookup"><span data-stu-id="86da6-139">**macOS**</span></span>    | [<span data-ttu-id="86da6-140">Lokale scripts</span><span class="sxs-lookup"><span data-stu-id="86da6-140">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="86da6-141">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="86da6-141">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="86da6-142">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="86da6-142">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="86da6-143">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="86da6-143">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="86da6-144">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="86da6-144">**Linux Server**</span></span> | [<span data-ttu-id="86da6-145">Lokaal script</span><span class="sxs-lookup"><span data-stu-id="86da6-145">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="86da6-146">Poppop</span><span class="sxs-lookup"><span data-stu-id="86da6-146">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="86da6-147">Ansible</span><span class="sxs-lookup"><span data-stu-id="86da6-147">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="86da6-148">**iOS**</span><span class="sxs-lookup"><span data-stu-id="86da6-148">**iOS**</span></span>      | [<span data-ttu-id="86da6-149">App-gebaseerde</span><span class="sxs-lookup"><span data-stu-id="86da6-149">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="86da6-150">**Android**</span><span class="sxs-lookup"><span data-stu-id="86da6-150">**Android**</span></span>  | [<span data-ttu-id="86da6-151">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="86da6-151">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="86da6-152">Stap 2: Mogelijkheden configureren</span><span class="sxs-lookup"><span data-stu-id="86da6-152">Step 2: Configure capabilities</span></span>
<span data-ttu-id="86da6-153">Nadat u de eindpunten hebt onboarding, configureert u vervolgens de verschillende mogelijkheden, zoals eindpuntdetectie en -reactie, beveiliging van de volgende generatie en de beperking van het oppervlak van de aanval.</span><span class="sxs-lookup"><span data-stu-id="86da6-153">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="86da6-154">Voorbeeldimplementaties</span><span class="sxs-lookup"><span data-stu-id="86da6-154">Example deployments</span></span>
<span data-ttu-id="86da6-155">In deze implementatiehandleiding begeleiden we u bij het gebruik van twee implementatiehulpmiddelen voor het onboarden van eindpunten en het configureren van mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="86da6-155">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="86da6-156">De hulpprogramma's in de voorbeeldimplementaties zijn:</span><span class="sxs-lookup"><span data-stu-id="86da6-156">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="86da6-157">Onboarden met behulp van Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="86da6-157">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="86da6-158">Onboarden met behulp van Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="86da6-158">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="86da6-159">Met behulp van de bovenstaande implementatiehulpmiddelen wordt u begeleid bij het configureren van de volgende Mogelijkheden van Defender voor Eindpunt:</span><span class="sxs-lookup"><span data-stu-id="86da6-159">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="86da6-160">Configuratie van eindpuntdetectie en -antwoord</span><span class="sxs-lookup"><span data-stu-id="86da6-160">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="86da6-161">Beveiligingsconfiguratie van de volgende generatie</span><span class="sxs-lookup"><span data-stu-id="86da6-161">Next-generation protection configuration</span></span>
- <span data-ttu-id="86da6-162">Surface Reduction-configuratie voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="86da6-162">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="86da6-163">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="86da6-163">Related topics</span></span>
- [<span data-ttu-id="86da6-164">Onboarden met behulp van Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="86da6-164">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="86da6-165">Onboarden met behulp van Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="86da6-165">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
- [<span data-ttu-id="86da6-166">Veilige documenten in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="86da6-166">Safe Documents in Microsoft 365 E5</span></span>](../office-365-security/safe-docs.md)
