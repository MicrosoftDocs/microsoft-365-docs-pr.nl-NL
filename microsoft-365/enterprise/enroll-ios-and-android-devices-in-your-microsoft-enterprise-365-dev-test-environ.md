---
title: IOS-iPadOS en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Gebruik deze test lab-handleiding om apparaten in uw Microsoft 365-test omgeving te registreren en deze extern te beheren.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367081"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="0e1ae-103">IOS-en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="0e1ae-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="0e1ae-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="0e1ae-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="0e1ae-105">In dit artikel wordt uitgelegd hoe u eenvoudige functies voor het beheren van mobiele apparaten voor iOS-en iPadOS-en Android-apparaten registreert en test in uw Microsoft 365 voor Enterprise testomgeving.</span><span class="sxs-lookup"><span data-stu-id="0e1ae-105">This article describes how to enroll and test basic mobile device management capabilities for iOS/iPadOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="0e1ae-106">Voor het registreren van iOS-en iPadOS en Android-apparaten in de testomgeving, moet u drie stappen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="0e1ae-106">Enrolling iOS/iPadOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="0e1ae-107">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="0e1ae-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="0e1ae-108">Fase 2: uw iOS-en iPadOS-en Android-apparaten registreren</span><span class="sxs-lookup"><span data-stu-id="0e1ae-108">Phase 2: Enroll your iOS/iPadOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="0e1ae-109">Fase 3: uw iOS-en iPadOS en Android-apparaten extern beheren</span><span class="sxs-lookup"><span data-stu-id="0e1ae-109">Phase 3: Manage your iOS/iPadOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="0e1ae-111">Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.</span><span class="sxs-lookup"><span data-stu-id="0e1ae-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="0e1ae-112">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="0e1ae-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="0e1ae-113">Als u een iOS-iPadOS en Android-apparaat op een lichte manier wilt registreren met de minimale vereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="0e1ae-113">If you want to enroll iOS/iPadOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="0e1ae-114">Als u iOS-iPadOS en Android-apparaten wilt registreren in een gesimuleerde Enterprise-versie, volgt u de instructies in [Pass-Through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="0e1ae-114">If you want to enroll iOS/iPadOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0e1ae-115">Voor het testen van geautomatiseerde licentie-en groepslidmaatschappen is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest.</span><span class="sxs-lookup"><span data-stu-id="0e1ae-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="0e1ae-116">Dit is een optie, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en u kunt experimenteren in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="0e1ae-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="0e1ae-117">Fase 2: uw iOS-en Android-apparaten registreren</span><span class="sxs-lookup"><span data-stu-id="0e1ae-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="0e1ae-118">Als u een MDM-oplossing (Mobile Device Management) overweegt om uw apparaten te beheren, kunt u Microsoft intune gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0e1ae-118">If you're considering a mobile device management (MDM) solution to manage your devices, you can use Microsoft Intune.</span></span> <span data-ttu-id="0e1ae-119">Wanneer u met een MDM-provider werkt, waaronder intune, zijn de optie ' ingeschreven '.</span><span class="sxs-lookup"><span data-stu-id="0e1ae-119">When working with any MDM provider, including Intune, devices are "enrolled".</span></span> <span data-ttu-id="0e1ae-120">Wanneer u zich registreert, ontvangen ze de functies en instellingen die u configureert.</span><span class="sxs-lookup"><span data-stu-id="0e1ae-120">When enrolled, they receive the features and settings you configure.</span></span> 

<span data-ttu-id="0e1ae-121">In intune zijn er een aantal manieren om uw iOS-iPadOS en Android-apparaten te registreren.</span><span class="sxs-lookup"><span data-stu-id="0e1ae-121">In Intune, there are a few ways to enroll your iOS/iPadOS and Android devices.</span></span> <span data-ttu-id="0e1ae-122">U kunt de optie voor inschrijving kiezen die het meest geschikt is voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0e1ae-122">You can choose the enrollment option that works best for your organization.</span></span> <span data-ttu-id="0e1ae-123">Zie de volgende artikelen voor meer informatie en richtlijnen:</span><span class="sxs-lookup"><span data-stu-id="0e1ae-123">For more information and guidance, see the following articles:</span></span>

- [<span data-ttu-id="0e1ae-124">Implementatiehandleiding: iOS-en iPadOS-apparaten registreren in Microsoft intune</span><span class="sxs-lookup"><span data-stu-id="0e1ae-124">Deployment guide: Enroll iOS and iPadOS devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [<span data-ttu-id="0e1ae-125">Implementatiehandleiding: Android-apparaten registreren in Microsoft intune</span><span class="sxs-lookup"><span data-stu-id="0e1ae-125">Deployment guide: Enroll Android devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-android)

<span data-ttu-id="0e1ae-126">Als u klaar bent om intune te gebruiken voor Apparaatbeheer en bepaalde richtlijnen wilt, kunt u de volgende informatie raadplegen:</span><span class="sxs-lookup"><span data-stu-id="0e1ae-126">If you're ready to use Intune for device management, and want some guidance, then the following information may help:</span></span>

- [<span data-ttu-id="0e1ae-127">Overzicht van apparaats beheer</span><span class="sxs-lookup"><span data-stu-id="0e1ae-127">Device management overview</span></span>](/mem/intune/fundamentals/what-is-device-management)
- [<span data-ttu-id="0e1ae-128">Zelfstudie: procedure intune in Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="0e1ae-128">Tutorial: Walkthrough Intune in Microsoft Endpoint Manager</span></span>](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [<span data-ttu-id="0e1ae-129">Implementatiehandleiding: installatie of verplaatsing naar Microsoft intune</span><span class="sxs-lookup"><span data-stu-id="0e1ae-129">Deployment guide: Setup or move to Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="0e1ae-130">Fase 3: uw iOS-en Android-apparaten extern beheren</span><span class="sxs-lookup"><span data-stu-id="0e1ae-130">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="0e1ae-131">Microsoft intune biedt de functie voor het opnieuw instellen van wachtwoorden voor extern vergrendelen.</span><span class="sxs-lookup"><span data-stu-id="0e1ae-131">Microsoft Intune provides remote lock and passcode reset feature.</span></span> <span data-ttu-id="0e1ae-132">Als iemand zijn of haar apparaat kwijtraakt, kunt u het toestel extern vergrendelen.</span><span class="sxs-lookup"><span data-stu-id="0e1ae-132">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="0e1ae-133">Als iemand zijn of haar wachtwoord vergeet, kunt u dit extern opnieuw instellen.</span><span class="sxs-lookup"><span data-stu-id="0e1ae-133">If someone forgets their passcode, you can remotely reset it.</span></span>

- <span data-ttu-id="0e1ae-134">Als u een iOS-iPadOS of Android-apparaat extern wilt vergrendelen, raadpleegt u [apparaten extern vergrendelen met intune](/mem/intune/remote-actions/device-remote-lock).</span><span class="sxs-lookup"><span data-stu-id="0e1ae-134">To remotely lock an iOS/iPadOS or Android device, see [Remotely lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span></span>
- <span data-ttu-id="0e1ae-135">Als u de wachtwoordcode extern opnieuw wilt instellen, raadpleegt u de [wachtwoordcode van een apparaat in intune opnieuw instellen of verwijderen](/mem/intune/remote-actions/device-passcode-reset).</span><span class="sxs-lookup"><span data-stu-id="0e1ae-135">To remotely reset the passcode, see [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span></span>

<span data-ttu-id="0e1ae-136">Zie [beschikbare Apparaatinstellingen](/mem/intune/remote-actions/device-management#available-device-actions)voor andere taken die u extern kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="0e1ae-136">For additional tasks you can run remotely, see [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="0e1ae-137">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="0e1ae-137">Next step</span></span>

<span data-ttu-id="0e1ae-138">Verken de extra functies en mogelijkheden van het [beheer van mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="0e1ae-138">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e1ae-139">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0e1ae-139">See Also</span></span>

[<span data-ttu-id="0e1ae-140">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="0e1ae-140">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="0e1ae-141">Beleid voor apparaatcompatibiliteit voor uw Microsoft 365 voor Enterprise testomgeving</span><span class="sxs-lookup"><span data-stu-id="0e1ae-141">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="0e1ae-142">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="0e1ae-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
