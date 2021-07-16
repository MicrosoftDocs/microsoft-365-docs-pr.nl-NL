---
title: Microsoft Defender inschakelen voor endpoint-evaluatie, de evaluatie voor MDE activeren
description: Uw testlaboratorium Microsoft 365 Defender testomgeving inschakelen, inclusief het controleren van de licentiestaat en onboarding-enpoints
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 48186dbfcde897022ac74dfad604c739a45ab68f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457797"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a><span data-ttu-id="52d01-103">Microsoft Defender voor endpoint-evaluatieomgeving inschakelen</span><span class="sxs-lookup"><span data-stu-id="52d01-103">Enable Microsoft Defender for Endpoint evaluation environment</span></span>


<span data-ttu-id="52d01-104">In dit artikel wordt u begeleid bij de stappen voor het instellen van de evaluatieomgeving voor Microsoft Defender voor Eindpunt met behulp van productieapparaten.</span><span class="sxs-lookup"><span data-stu-id="52d01-104">This article will guide you through the steps on setting up the evaluation environment for Microsoft Defender for Endpoint using production devices.</span></span> 


>[!TIP]
><span data-ttu-id="52d01-105">Microsoft Defender voor Eindpunt wordt ook geleverd met een evaluatielaboratorium voor in-product, waar u vooraf geconfigureerde apparaten kunt toevoegen en simulaties kunt uitvoeren om de mogelijkheden van het platform te evalueren.</span><span class="sxs-lookup"><span data-stu-id="52d01-105">Microsoft Defender for Endpoint also comes with an in-product evaluation lab where you can add pre-configured devices and run simulations to evaluate the capabilities of the platform.</span></span> <span data-ttu-id="52d01-106">Het lab wordt geleverd met een vereenvoudigde set-upervaring die u snel de waarde van Microsoft Defender voor Enpdoint kan laten zien, inclusief richtlijnen voor veel functies, zoals geavanceerde zoek- en bedreigingsanalyses.</span><span class="sxs-lookup"><span data-stu-id="52d01-106">The lab comes with a simplified set-up experience that can help quickly demonstrate the value of Microsoft Defender for Enpdoint including guidance for many features like advanced hunting and threat analytics.</span></span> <span data-ttu-id="52d01-107">Zie Mogelijkheden evalueren voor [meer informatie.](/defender-endpoint/evaluation-lab.md)</span><span class="sxs-lookup"><span data-stu-id="52d01-107">For more information, see [Evaluate capabilities](/defender-endpoint/evaluation-lab.md).</span></span> <br> <span data-ttu-id="52d01-108">Het belangrijkste verschil tussen de richtlijnen in dit artikel en het evaluatielaboratorium is dat in de evaluatieomgeving productieapparaten worden gebruikt, terwijl in het evaluatielaboratorium niet-productieapparaten worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="52d01-108">The main difference between the guidance provided in this article and the evaluation lab is the evaluation environment uses production devices whereas the evaluation lab uses non-production devices.</span></span> 

<span data-ttu-id="52d01-109">Gebruik de volgende stappen om de evaluatie voor Microsoft Defender voor Eindpunt in te stellen.</span><span class="sxs-lookup"><span data-stu-id="52d01-109">Use the following steps to enable the evaluation for Microsoft Defender for Endpoint.</span></span>

![Stappen voor het inschakelen van Microsoft Defender voor Eindpunt in de evaluatieomgeving van Microsoft Defender](../../media/defender/m365-defender-endpoint-eval-enable-steps.png)

- [<span data-ttu-id="52d01-111">Stap 1. Licentiestaat controleren</span><span class="sxs-lookup"><span data-stu-id="52d01-111">Step 1. Check license state</span></span>](#step-1-check-license-state)
- [<span data-ttu-id="52d01-112">Stap 2. Eindpunten aan boord</span><span class="sxs-lookup"><span data-stu-id="52d01-112">Step 2. Onboard endpoints</span></span>](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a><span data-ttu-id="52d01-113">Stap 1.</span><span class="sxs-lookup"><span data-stu-id="52d01-113">Step 1.</span></span> <span data-ttu-id="52d01-114">Licentiestaat controleren</span><span class="sxs-lookup"><span data-stu-id="52d01-114">Check license state</span></span>

<span data-ttu-id="52d01-115">U moet eerst de licentiestaat controleren om te controleren of deze correct is ingericht.</span><span class="sxs-lookup"><span data-stu-id="52d01-115">You'll first need to check the license state to verify that it was properly provisioned.</span></span> <span data-ttu-id="52d01-116">U kunt dit doen via het beheercentrum of via de **Microsoft Azure portal.**</span><span class="sxs-lookup"><span data-stu-id="52d01-116">You can do this through the admin center or through the **Microsoft Azure portal**.</span></span>


1. <span data-ttu-id="52d01-117">Als u uw licenties wilt bekijken, gaat u naar de **Microsoft Azure portal** en gaat u naar de [Microsoft Azure portallicentiesectie.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)</span><span class="sxs-lookup"><span data-stu-id="52d01-117">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Afbeelding van de pagina Azure Licensing](../../media/defender/atp-licensing-azure-portal.png)

1. <span data-ttu-id="52d01-119">U kunt ook in het beheercentrum naar  >  **Factureringsabonnementen gaan.**</span><span class="sxs-lookup"><span data-stu-id="52d01-119">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="52d01-120">Op het scherm ziet u alle inrichtende licenties en de huidige **status.**</span><span class="sxs-lookup"><span data-stu-id="52d01-120">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![Afbeelding van factureringslicenties](../../media/defender/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="52d01-122">Stap 2.</span><span class="sxs-lookup"><span data-stu-id="52d01-122">Step 2.</span></span> <span data-ttu-id="52d01-123">Onboard-eindpunten met behulp van een van de ondersteunde beheerhulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="52d01-123">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="52d01-124">Nadat u hebt gecontroleerd of de licentiestaat correct is ingericht, kunt u beginnen met het onboarden van apparaten voor de service.</span><span class="sxs-lookup"><span data-stu-id="52d01-124">After verifying that the license state has been provisioned properly, you can start onboarding devices to the service.</span></span> 

<span data-ttu-id="52d01-125">Voor het evalueren van Microsoft Defender voor Eindpunt raden we u aan een aantal apparaten Windows 10 om de evaluatie uit te voeren op.</span><span class="sxs-lookup"><span data-stu-id="52d01-125">For the purpose of evaluating Microsoft Defender for Endpoint, we recommend choosing a couple of Windows 10 devices to conduct the evaluation on.</span></span> 

<span data-ttu-id="52d01-126">Het [implementatieonderwerp](../defender-endpoint/deployment-strategy.md) Plannen bevat een overzicht van de algemene stappen die u moet ondernemen om Defender voor Eindpunt te implementeren.</span><span class="sxs-lookup"><span data-stu-id="52d01-126">The [Plan deployment](../defender-endpoint/deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="52d01-127">Bekijk deze video voor een kort overzicht van het onboardingproces en lees meer over de beschikbare hulpprogramma's en methoden.</span><span class="sxs-lookup"><span data-stu-id="52d01-127">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a><span data-ttu-id="52d01-128">Opties voor onboarding-hulpprogramma's</span><span class="sxs-lookup"><span data-stu-id="52d01-128">Onboarding tool options</span></span>

<span data-ttu-id="52d01-129">In de volgende tabel ziet u de beschikbare hulpprogramma's op basis van het eindpunt dat u nodig hebt om aan boord te gaan.</span><span class="sxs-lookup"><span data-stu-id="52d01-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

<span data-ttu-id="52d01-130">Eindpunt</span><span class="sxs-lookup"><span data-stu-id="52d01-130">Endpoint</span></span> | <span data-ttu-id="52d01-131">Opties voor hulpprogramma's</span><span class="sxs-lookup"><span data-stu-id="52d01-131">Tool options</span></span>
:---|:---
<span data-ttu-id="52d01-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="52d01-132">**Windows**</span></span> | <span data-ttu-id="52d01-133">[Lokaal script (maximaal 10 apparaten)](../defender-endpoint/configure-endpoints-script.md) [,](../defender-endpoint/configure-endpoints-gp.md)Groepsbeleid , [Microsoft Endpoint Manager/ Mobile Device Manager](../defender-endpoint/configure-endpoints-mdm.md), Microsoft Endpoint Configuration Manager , [VDI-scripts](../defender-endpoint/configure-endpoints-vdi.md), [Integratie met Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) [](../defender-endpoint/configure-endpoints-sccm.md)</span><span class="sxs-lookup"><span data-stu-id="52d01-133">[Local script (up to 10 devices)](../defender-endpoint/configure-endpoints-script.md),  [Group Policy](../defender-endpoint/configure-endpoints-gp.md),  [Microsoft Endpoint Manager/ Mobile Device Manager](../defender-endpoint/configure-endpoints-mdm.md),  [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md),  [VDI scripts](../defender-endpoint/configure-endpoints-vdi.md),  [Integration with Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)</span></span>
<span data-ttu-id="52d01-134">**macOS**</span><span class="sxs-lookup"><span data-stu-id="52d01-134">**macOS**</span></span> | <span data-ttu-id="52d01-135">[Lokale scripts](../defender-endpoint/mac-install-manually.md), [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md), [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md), Mobile [Device Management](../defender-endpoint/mac-install-with-other-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="52d01-135">[Local scripts](../defender-endpoint/mac-install-manually.md),  [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md),  [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md),  [Mobile Device Management](../defender-endpoint/mac-install-with-other-mdm.md)</span></span>
<span data-ttu-id="52d01-136">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="52d01-136">**Linux Server**</span></span> | <span data-ttu-id="52d01-137">[Lokaal script](../defender-endpoint/linux-install-manually.md),  [Pop ,](../defender-endpoint/linux-install-with-puppet.md)  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span><span class="sxs-lookup"><span data-stu-id="52d01-137">[Local script](../defender-endpoint/linux-install-manually.md),  [Puppet](../defender-endpoint/linux-install-with-puppet.md),  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span></span>
<span data-ttu-id="52d01-138">**iOS**</span><span class="sxs-lookup"><span data-stu-id="52d01-138">**iOS**</span></span> | [<span data-ttu-id="52d01-139">App-gebaseerde</span><span class="sxs-lookup"><span data-stu-id="52d01-139">App-based</span></span>](../defender-endpoint/ios-install.md)
<span data-ttu-id="52d01-140">**Android**</span><span class="sxs-lookup"><span data-stu-id="52d01-140">**Android**</span></span> | [<span data-ttu-id="52d01-141">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="52d01-141">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)



## <a name="next-step"></a><span data-ttu-id="52d01-142">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="52d01-142">Next step</span></span>
[<span data-ttu-id="52d01-143">De pilot voor Microsoft Defender voor Eindpunt instellen</span><span class="sxs-lookup"><span data-stu-id="52d01-143">Setup the pilot for Microsoft Defender for Endpoint</span></span>](eval-defender-endpoint-pilot.md)
 
<span data-ttu-id="52d01-144">Terug naar het overzicht voor [Microsoft Defender evalueren voor eindpunt](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="52d01-144">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="52d01-145">Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="52d01-145">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>