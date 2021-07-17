---
title: Pilot Defender voor endpoint-evaluatie
description: Schakel uw Microsoft 365 Defender proeflaboratorium of testomgeving in.
keywords: Microsoft 365 Defender proefversie, probeer Microsoft 365 Defender, evalueer Microsoft 365 Defender, Microsoft 365 Defender evaluatielaboratorium, Microsoft 365 Defender-pilot, cyberbeveiliging, geavanceerde permanente bedreiging, bedrijfsbeveiliging, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerd zoeken
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457842"
---
# <a name="pilot-mde-evaluation"></a><span data-ttu-id="c7a78-104">Pilot MDE-evaluatie</span><span class="sxs-lookup"><span data-stu-id="c7a78-104">Pilot MDE Evaluation</span></span>

>[!NOTE]
><span data-ttu-id="c7a78-105">Om u te begeleiden bij een normale implementatie, wordt in dit scenario alleen het gebruik van Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="c7a78-105">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="c7a78-106">Defender voor Eindpunt ondersteunt het gebruik van andere onboarding-hulpprogramma's, maar deze scenario's worden niet in de implementatiehandleiding bestrijken.</span><span class="sxs-lookup"><span data-stu-id="c7a78-106">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="c7a78-107">Zie Onboard devices to Microsoft Defender for Endpoint (Onboard [devices to Microsoft Defender for Endpoint) voor meer informatie.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="c7a78-107">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="step-1-check-license-state"></a><span data-ttu-id="c7a78-108">Stap 1.</span><span class="sxs-lookup"><span data-stu-id="c7a78-108">Step 1.</span></span> <span data-ttu-id="c7a78-109">Licentiestaat controleren</span><span class="sxs-lookup"><span data-stu-id="c7a78-109">Check license state</span></span>

<span data-ttu-id="c7a78-110">Controleren op de licentiestaat en of deze goed is ingericht, kan via het beheercentrum of via de **Microsoft Azure portal.**</span><span class="sxs-lookup"><span data-stu-id="c7a78-110">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="c7a78-111">Als u uw licenties wilt bekijken, gaat u naar de **Microsoft Azure portal** en gaat u naar de [Microsoft Azure portallicentiesectie.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)</span><span class="sxs-lookup"><span data-stu-id="c7a78-111">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Afbeelding van de pagina Azure Licensing](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="c7a78-113">U kunt ook in het beheercentrum naar  >  **Factureringsabonnementen gaan.**</span><span class="sxs-lookup"><span data-stu-id="c7a78-113">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="c7a78-114">Op het scherm ziet u alle inrichtende licenties en de huidige **status.**</span><span class="sxs-lookup"><span data-stu-id="c7a78-114">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![Afbeelding van factureringslicenties](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="c7a78-116">Stap 2.</span><span class="sxs-lookup"><span data-stu-id="c7a78-116">Step 2.</span></span> <span data-ttu-id="c7a78-117">Onboard-eindpunten met behulp van een van de ondersteunde beheerhulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="c7a78-117">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="c7a78-118">Het [implementatieonderwerp](deployment-strategy.md) Plannen bevat een overzicht van de algemene stappen die u moet ondernemen om Defender voor Eindpunt te implementeren.</span><span class="sxs-lookup"><span data-stu-id="c7a78-118">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="c7a78-119">Bekijk deze video voor een kort overzicht van het onboardingproces en lees meer over de beschikbare hulpprogramma's en methoden.</span><span class="sxs-lookup"><span data-stu-id="c7a78-119">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

<span data-ttu-id="c7a78-120">Nadat u de architectuur hebt identificeren, moet u bepalen welke implementatiemethode u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c7a78-120">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="c7a78-121">Het implementatieprogramma dat u kiest, is van invloed op de manier waarop u eindpunten aan boord van de service inwerkt.</span><span class="sxs-lookup"><span data-stu-id="c7a78-121">The deployment tool you choose influences how you onboard endpoints to the service.</span></span>

### <a name="onboarding-tool-options"></a><span data-ttu-id="c7a78-122">Opties voor onboarding-hulpprogramma's</span><span class="sxs-lookup"><span data-stu-id="c7a78-122">Onboarding tool options</span></span>

<span data-ttu-id="c7a78-123">In de volgende tabel ziet u de beschikbare hulpprogramma's op basis van het eindpunt dat u nodig hebt om aan boord te gaan.</span><span class="sxs-lookup"><span data-stu-id="c7a78-123">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="c7a78-124">Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c7a78-124">Endpoint</span></span>     | <span data-ttu-id="c7a78-125">Opties voor hulpprogramma's</span><span class="sxs-lookup"><span data-stu-id="c7a78-125">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="c7a78-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="c7a78-126">**Windows**</span></span>  |  [<span data-ttu-id="c7a78-127">Lokaal script (maximaal 10 apparaten)</span><span class="sxs-lookup"><span data-stu-id="c7a78-127">Local script (up to 10 devices)</span></span>](../defender-endpoint/configure-endpoints-script.md) <br> [<span data-ttu-id="c7a78-128">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="c7a78-128">Group Policy</span></span>](../defender-endpoint/configure-endpoints-gp.md) <br> [<span data-ttu-id="c7a78-129">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="c7a78-129">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](../defender-endpoint/configure-endpoints-mdm.md) <br> [<span data-ttu-id="c7a78-130">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c7a78-130">Microsoft Endpoint Configuration Manager</span></span>](../defender-endpoint/configure-endpoints-sccm.md) <br> [<span data-ttu-id="c7a78-131">VDI-scripts</span><span class="sxs-lookup"><span data-stu-id="c7a78-131">VDI scripts</span></span>](../defender-endpoint/configure-endpoints-vdi.md) <br> [<span data-ttu-id="c7a78-132">Integratie met Azure Defender</span><span class="sxs-lookup"><span data-stu-id="c7a78-132">Integration with Azure Defender</span></span>](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="c7a78-133">**macOS**</span><span class="sxs-lookup"><span data-stu-id="c7a78-133">**macOS**</span></span>    | [<span data-ttu-id="c7a78-134">Lokale scripts</span><span class="sxs-lookup"><span data-stu-id="c7a78-134">Local scripts</span></span>](../defender-endpoint/mac-install-manually.md) <br> [<span data-ttu-id="c7a78-135">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="c7a78-135">Microsoft Endpoint Manager</span></span>](../defender-endpoint/mac-install-with-intune.md) <br> [<span data-ttu-id="c7a78-136">JAMF-Pro</span><span class="sxs-lookup"><span data-stu-id="c7a78-136">JAMF Pro</span></span>](../defender-endpoint/mac-install-with-jamf.md) <br> [<span data-ttu-id="c7a78-137">Mobile Device Management</span><span class="sxs-lookup"><span data-stu-id="c7a78-137">Mobile Device Management</span></span>](../defender-endpoint/mac-install-with-other-mdm.md) |
| <span data-ttu-id="c7a78-138">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="c7a78-138">**Linux Server**</span></span> | [<span data-ttu-id="c7a78-139">Lokaal script</span><span class="sxs-lookup"><span data-stu-id="c7a78-139">Local script</span></span>](../defender-endpoint/linux-install-manually.md) <br> [<span data-ttu-id="c7a78-140">Poppop</span><span class="sxs-lookup"><span data-stu-id="c7a78-140">Puppet</span></span>](../defender-endpoint/linux-install-with-puppet.md) <br> [<span data-ttu-id="c7a78-141">Ansible</span><span class="sxs-lookup"><span data-stu-id="c7a78-141">Ansible</span></span>](../defender-endpoint/linux-install-with-ansible.md)|
| <span data-ttu-id="c7a78-142">**iOS**</span><span class="sxs-lookup"><span data-stu-id="c7a78-142">**iOS**</span></span>      | [<span data-ttu-id="c7a78-143">App-gebaseerde</span><span class="sxs-lookup"><span data-stu-id="c7a78-143">App-based</span></span>](../defender-endpoint/ios-install.md)                                |
| <span data-ttu-id="c7a78-144">**Android**</span><span class="sxs-lookup"><span data-stu-id="c7a78-144">**Android**</span></span>  | [<span data-ttu-id="c7a78-145">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="c7a78-145">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)               |
