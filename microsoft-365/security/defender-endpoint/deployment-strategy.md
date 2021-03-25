---
title: Uw Microsoft Defender voor endpoint-implementatie plannen
description: Selecteer de beste implementatiestrategie van Microsoft Defender voor eindpunten voor uw omgeving
keywords: deploy, plan, deployment strategy, cloud native, management, on prem, evaluation, onboarding, local, group policy, gp, endpoint manager, mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163573"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="70974-104">Uw Microsoft Defender voor endpoint-implementatie plannen</span><span class="sxs-lookup"><span data-stu-id="70974-104">Plan your Microsoft Defender for Endpoint deployment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="70974-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="70974-105">**Applies to:**</span></span>
- [<span data-ttu-id="70974-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="70974-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="70974-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="70974-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="70974-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="70974-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="70974-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="70974-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


<span data-ttu-id="70974-110">Plan uw Microsoft Defender voor endpoint-implementatie, zodat u de beveiligingsmogelijkheden binnen de suite kunt maximaliseren en uw bedrijf beter kunt beschermen tegen cyberdreigingen.</span><span class="sxs-lookup"><span data-stu-id="70974-110">Plan your Microsoft Defender for Endpoint deployment so that you can maximize the security capabilities within the suite and better protect your enterprise from cyber threats.</span></span>


<span data-ttu-id="70974-111">Deze oplossing biedt richtlijnen voor het identificeren van uw omgevingsarchitectuur, het type implementatieprogramma dat het beste aansluit bij uw behoeften en richtlijnen voor het configureren van mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="70974-111">This solution provides guidance on how to identify your environment architecture, select the type of deployment tool that best fits your needs, and guidance on how to configure capabilities.</span></span>


![Afbeelding van implementatiestroom](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a><span data-ttu-id="70974-113">Stap 1: Architectuur identificeren</span><span class="sxs-lookup"><span data-stu-id="70974-113">Step 1: Identify architecture</span></span>
<span data-ttu-id="70974-114">We begrijpen dat elke ondernemingsomgeving uniek is, dus hebben we verschillende opties geboden om u de flexibiliteit te bieden bij het kiezen van de implementatie van de service.</span><span class="sxs-lookup"><span data-stu-id="70974-114">We understand that every enterprise environment is unique, so we've provided several options to give you the flexibility in choosing how to deploy the service.</span></span>

<span data-ttu-id="70974-115">Sommige hulpprogramma's zijn beter geschikt voor bepaalde architecturen, afhankelijk van uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="70974-115">Depending on your environment, some tools are better suited for certain architectures.</span></span> 

<span data-ttu-id="70974-116">Gebruik het volgende materiaal om de juiste Defender voor eindpuntarchitectuur te selecteren die het beste past bij uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="70974-116">Use the following material to select the appropriate Defender for Endpoint architecture that best suites your organization.</span></span>

| <span data-ttu-id="70974-117">Item</span><span class="sxs-lookup"><span data-stu-id="70974-117">Item</span></span> | <span data-ttu-id="70974-118">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="70974-118">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="70974-119">[![Thumb image for Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="70974-119">[![Thumb image for Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="70974-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="70974-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="70974-121">Met het materiaal voor architecten kunt u uw implementatie plannen voor de volgende architecturen:</span><span class="sxs-lookup"><span data-stu-id="70974-121">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="70974-122">Cloud-native</span><span class="sxs-lookup"><span data-stu-id="70974-122">Cloud-native</span></span> </li><li> <span data-ttu-id="70974-123">Co-management</span><span class="sxs-lookup"><span data-stu-id="70974-123">Co-management</span></span> </li><li> <span data-ttu-id="70974-124">On-premises</span><span class="sxs-lookup"><span data-stu-id="70974-124">On-premise</span></span></li><li><span data-ttu-id="70974-125">Evaluatie en lokale onboarding</span><span class="sxs-lookup"><span data-stu-id="70974-125">Evaluation and local onboarding</span></span></li>



## <a name="step-2-select-deployment-method"></a><span data-ttu-id="70974-126">Stap 2: Implementatiemethode selecteren</span><span class="sxs-lookup"><span data-stu-id="70974-126">Step 2: Select deployment method</span></span>
<span data-ttu-id="70974-127">Defender voor Eindpunt ondersteunt diverse eindpunten die u aan boord van de service kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="70974-127">Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> 

<span data-ttu-id="70974-128">De volgende tabel bevat de ondersteunde eindpunten en het bijbehorende implementatieprogramma dat u kunt gebruiken, zodat u de implementatie op de juiste manier kunt plannen.</span><span class="sxs-lookup"><span data-stu-id="70974-128">The following table lists the supported endpoints and the corresponding deployment tool that you can use so that you can plan the deployment appropriately.</span></span>

| <span data-ttu-id="70974-129">Eindpunt</span><span class="sxs-lookup"><span data-stu-id="70974-129">Endpoint</span></span>     | <span data-ttu-id="70974-130">Implementatiehulpmiddel</span><span class="sxs-lookup"><span data-stu-id="70974-130">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="70974-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="70974-131">**Windows**</span></span>  |  [<span data-ttu-id="70974-132">Lokaal script (maximaal 10 apparaten)</span><span class="sxs-lookup"><span data-stu-id="70974-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="70974-133">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="70974-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="70974-134">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="70974-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="70974-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="70974-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="70974-136">VDI-scripts</span><span class="sxs-lookup"><span data-stu-id="70974-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="70974-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="70974-137">**macOS**</span></span>    | [<span data-ttu-id="70974-138">Lokaal script</span><span class="sxs-lookup"><span data-stu-id="70974-138">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="70974-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="70974-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="70974-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="70974-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="70974-141">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="70974-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="70974-142">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="70974-142">**Linux Server**</span></span> | [<span data-ttu-id="70974-143">Lokaal script</span><span class="sxs-lookup"><span data-stu-id="70974-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="70974-144">Poppop</span><span class="sxs-lookup"><span data-stu-id="70974-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="70974-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="70974-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="70974-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="70974-146">**iOS**</span></span>      | [<span data-ttu-id="70974-147">App-gebaseerde</span><span class="sxs-lookup"><span data-stu-id="70974-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="70974-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="70974-148">**Android**</span></span>  | [<span data-ttu-id="70974-149">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="70974-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a><span data-ttu-id="70974-150">Stap 3: Mogelijkheden configureren</span><span class="sxs-lookup"><span data-stu-id="70974-150">Step 3: Configure capabilities</span></span>
<span data-ttu-id="70974-151">Nadat u eindpunten hebt onboarding, configureert u de beveiligingsmogelijkheden in Defender voor Eindpunt, zodat u de krachtige beveiliging kunt maximaliseren die beschikbaar is in de suite.</span><span class="sxs-lookup"><span data-stu-id="70974-151">After onboarding endpoints, configure the security capabilities in Defender for Endpoint so that you can maximize the robust security protection available in the suite.</span></span> <span data-ttu-id="70974-152">De volgende mogelijkheden zijn:</span><span class="sxs-lookup"><span data-stu-id="70974-152">Capabilities include:</span></span>

- <span data-ttu-id="70974-153">Eindpuntdetectie en -antwoord</span><span class="sxs-lookup"><span data-stu-id="70974-153">Endpoint detection and response</span></span>
- <span data-ttu-id="70974-154">Beveiliging van de volgende generatie</span><span class="sxs-lookup"><span data-stu-id="70974-154">Next-generation protection</span></span>
- <span data-ttu-id="70974-155">Surface-beperking voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="70974-155">Attack surface reduction</span></span>


  
## <a name="related-topics"></a><span data-ttu-id="70974-156">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="70974-156">Related topics</span></span>
- [<span data-ttu-id="70974-157">Implementatiefasen</span><span class="sxs-lookup"><span data-stu-id="70974-157">Deployment phases</span></span>](deployment-phases.md)
