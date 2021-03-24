---
title: Apparaten aan boord van de MICROSOFT Defender ATP-service
description: Onboard Windows 10-apparaten, servers, niet-Windows-apparaten en leer hoe u een detectietest kunt uitvoeren.
keywords: onboarding, microsoft defender for endpoint onboarding, windows atp onboarding, sccm, group policy, mdm, local script, detection test
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1deb8a0e00785705937d4cf6de71a030d3d9c971
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056837"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="b6d13-104">Onboard devices to the Microsoft Defender for Endpoint service</span><span class="sxs-lookup"><span data-stu-id="b6d13-104">Onboard devices to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b6d13-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b6d13-105">**Applies to:**</span></span>
- [<span data-ttu-id="b6d13-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="b6d13-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="b6d13-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b6d13-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="b6d13-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="b6d13-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b6d13-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="b6d13-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="b6d13-110">U moet naar de onboarding-sectie van de Defender for Endpoint-portal gaan om een van de ondersteunde apparaten aan te sluiten.</span><span class="sxs-lookup"><span data-stu-id="b6d13-110">You'll need to go the onboarding section of the Defender for Endpoint portal to onboard any of the supported devices.</span></span> <span data-ttu-id="b6d13-111">Afhankelijk van het apparaat wordt u begeleid met de juiste stappen en de opties voor beheer- en implementatieprogramma's die geschikt zijn voor het apparaat.</span><span class="sxs-lookup"><span data-stu-id="b6d13-111">Depending on the device, you'll be guided with appropriate steps and provided management and deployment tool options suitable for the device.</span></span> 

<span data-ttu-id="b6d13-112">In het algemeen gaat het om apparaten aan boord van de service:</span><span class="sxs-lookup"><span data-stu-id="b6d13-112">In general, to onboard devices to the service:</span></span>

- <span data-ttu-id="b6d13-113">Controleren of het apparaat aan de [minimumvereisten voldoet](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="b6d13-113">Verify that the device fulfills the [minimum requirements](minimum-requirements.md)</span></span>
- <span data-ttu-id="b6d13-114">Volg, afhankelijk van het apparaat, de configuratiestappen in de onboarding-sectie van de Defender for Endpoint-portal</span><span class="sxs-lookup"><span data-stu-id="b6d13-114">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal</span></span>
- <span data-ttu-id="b6d13-115">Het juiste beheerprogramma en de juiste implementatiemethode voor uw apparaten gebruiken</span><span class="sxs-lookup"><span data-stu-id="b6d13-115">Use the appropriate management tool and deployment method for your devices</span></span>
- <span data-ttu-id="b6d13-116">Een detectietest uitvoeren om te controleren of de apparaten correct zijn onboarded en rapporteren aan de service</span><span class="sxs-lookup"><span data-stu-id="b6d13-116">Run a detection test to verify that the devices are properly onboarded and reporting to the service</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a><span data-ttu-id="b6d13-117">Opties voor onboarding-hulpprogramma's</span><span class="sxs-lookup"><span data-stu-id="b6d13-117">Onboarding tool options</span></span>
<span data-ttu-id="b6d13-118">In de volgende tabel ziet u de beschikbare hulpprogramma's op basis van het eindpunt dat u nodig hebt om aan boord te gaan.</span><span class="sxs-lookup"><span data-stu-id="b6d13-118">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="b6d13-119">Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b6d13-119">Endpoint</span></span>     | <span data-ttu-id="b6d13-120">Opties voor hulpprogramma's</span><span class="sxs-lookup"><span data-stu-id="b6d13-120">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="b6d13-121">**Windows**</span><span class="sxs-lookup"><span data-stu-id="b6d13-121">**Windows**</span></span>  |  [<span data-ttu-id="b6d13-122">Lokaal script (maximaal 10 apparaten)</span><span class="sxs-lookup"><span data-stu-id="b6d13-122">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="b6d13-123">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="b6d13-123">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="b6d13-124">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="b6d13-124">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="b6d13-125">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b6d13-125">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="b6d13-126">VDI-scripts</span><span class="sxs-lookup"><span data-stu-id="b6d13-126">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="b6d13-127">**macOS**</span><span class="sxs-lookup"><span data-stu-id="b6d13-127">**macOS**</span></span>    | [<span data-ttu-id="b6d13-128">Lokale scripts</span><span class="sxs-lookup"><span data-stu-id="b6d13-128">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="b6d13-129">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="b6d13-129">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="b6d13-130">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="b6d13-130">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="b6d13-131">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="b6d13-131">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="b6d13-132">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="b6d13-132">**Linux Server**</span></span> | [<span data-ttu-id="b6d13-133">Lokaal script</span><span class="sxs-lookup"><span data-stu-id="b6d13-133">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="b6d13-134">Poppop</span><span class="sxs-lookup"><span data-stu-id="b6d13-134">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="b6d13-135">Ansible</span><span class="sxs-lookup"><span data-stu-id="b6d13-135">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="b6d13-136">**iOS**</span><span class="sxs-lookup"><span data-stu-id="b6d13-136">**iOS**</span></span>      | [<span data-ttu-id="b6d13-137">App-gebaseerde</span><span class="sxs-lookup"><span data-stu-id="b6d13-137">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="b6d13-138">**Android**</span><span class="sxs-lookup"><span data-stu-id="b6d13-138">**Android**</span></span>  | [<span data-ttu-id="b6d13-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="b6d13-139">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




## <a name="in-this-section"></a><span data-ttu-id="b6d13-140">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="b6d13-140">In this section</span></span>
<span data-ttu-id="b6d13-141">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="b6d13-141">Topic</span></span> | <span data-ttu-id="b6d13-142">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="b6d13-142">Description</span></span>
:---|:---
[<span data-ttu-id="b6d13-143">Eerdere versies van Windows aan boord</span><span class="sxs-lookup"><span data-stu-id="b6d13-143">Onboard previous versions of Windows</span></span>](onboard-downlevel.md)| <span data-ttu-id="b6d13-144">Onboard Windows 7 en Windows 8.1-apparaten naar Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="b6d13-144">Onboard Windows 7 and Windows 8.1 devices to Defender for Endpoint.</span></span> 
[<span data-ttu-id="b6d13-145">Onboard Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="b6d13-145">Onboard Windows 10 devices</span></span>](configure-endpoints.md) | <span data-ttu-id="b6d13-146">U moet apparaten aan boord hebben om deze te kunnen rapporteren bij de Service Defender voor eindpunt.</span><span class="sxs-lookup"><span data-stu-id="b6d13-146">You'll need to onboard devices for it to report to the Defender for Endpoint service.</span></span> <span data-ttu-id="b6d13-147">Meer informatie over de hulpprogramma's en methoden die u kunt gebruiken om apparaten in uw bedrijf te configureren.</span><span class="sxs-lookup"><span data-stu-id="b6d13-147">Learn about the tools and methods you can use to configure devices in your enterprise.</span></span>
[<span data-ttu-id="b6d13-148">Onboard-servers</span><span class="sxs-lookup"><span data-stu-id="b6d13-148">Onboard servers</span></span>](configure-server-endpoints.md) |  <span data-ttu-id="b6d13-149">Onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) versie 1803 en hoger, Windows Server 2019 en hoger en Windows Server 2019 core edition naar Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="b6d13-149">Onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) version 1803 and later, Windows Server 2019 and later, and Windows Server 2019 core edition to Defender for Endpoint.</span></span>
[<span data-ttu-id="b6d13-150">Onboard niet-Windows-apparaten</span><span class="sxs-lookup"><span data-stu-id="b6d13-150">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md) | <span data-ttu-id="b6d13-151">Defender voor Eindpunt biedt een gecentraliseerde beveiligingsbewerkingservaring voor Windows en niet-Windows-platforms.</span><span class="sxs-lookup"><span data-stu-id="b6d13-151">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="b6d13-152">U kunt waarschuwingen van verschillende ondersteunde besturingssystemen (OS) zien in het Microsoft Defender-beveiligingscentrum en het netwerk van uw organisatie beter beveiligen.</span><span class="sxs-lookup"><span data-stu-id="b6d13-152">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> <span data-ttu-id="b6d13-153">Deze ervaring maakt gebruik van de sensorgegevens van een beveiligingsproducten van derden.</span><span class="sxs-lookup"><span data-stu-id="b6d13-153">This experience leverages on a third-party security products' sensor data.</span></span> 
[<span data-ttu-id="b6d13-154">Een detectietest uitvoeren op een nieuw onboarded-apparaat</span><span class="sxs-lookup"><span data-stu-id="b6d13-154">Run a detection test on a newly onboarded device</span></span>](run-detection-test.md) | <span data-ttu-id="b6d13-155">Voer een script uit op een nieuw onboarded apparaat om te controleren of het correct rapporteert aan de Defender for Endpoint-service.</span><span class="sxs-lookup"><span data-stu-id="b6d13-155">Run a script on a newly onboarded device to verify that it is properly reporting to the Defender for Endpoint service.</span></span>
[<span data-ttu-id="b6d13-156">Proxy- en internetinstellingen configureren</span><span class="sxs-lookup"><span data-stu-id="b6d13-156">Configure proxy and Internet settings</span></span>](configure-proxy-internet.md)| <span data-ttu-id="b6d13-157">Schakel communicatie met de Defender voor Endpoint-cloudservice in door de proxy- en internetverbindingsinstellingen te configureren.</span><span class="sxs-lookup"><span data-stu-id="b6d13-157">Enable communication with the Defender for Endpoint cloud service by configuring the proxy and Internet connectivity settings.</span></span>
[<span data-ttu-id="b6d13-158">Problemen met onboarding oplossen</span><span class="sxs-lookup"><span data-stu-id="b6d13-158">Troubleshoot onboarding issues</span></span>](troubleshoot-onboarding.md) | <span data-ttu-id="b6d13-159">Meer informatie over het oplossen van problemen die zich kunnen voordoen tijdens onboarding.</span><span class="sxs-lookup"><span data-stu-id="b6d13-159">Learn about resolving issues that might arise during onboarding.</span></span>

><span data-ttu-id="b6d13-160">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="b6d13-160">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b6d13-161">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="b6d13-161">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
