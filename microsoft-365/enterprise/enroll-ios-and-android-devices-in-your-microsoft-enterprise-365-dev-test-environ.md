---
title: IOS-/iPadOS- en Android-apparaten registreren in uw Microsoft 365 voor bedrijfstestomgeving
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
description: Gebruik deze Test Lab Guide om apparaten in te schrijven in uw Microsoft 365 testomgeving en ze op afstand te beheren.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367081"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="67a5b-103">IOS- en Android-apparaten registreren in uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="67a5b-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="67a5b-104">*Deze testlaborator kan alleen worden gebruikt Microsoft 365 voor bedrijfstestomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="67a5b-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="67a5b-105">In dit artikel wordt beschreven hoe u eenvoudige mogelijkheden voor mobiel apparaatbeheer voor iOS/iPadOS- en Android-apparaten kunt registreren en testen in uw Microsoft 365 voor bedrijfstestomgeving.</span><span class="sxs-lookup"><span data-stu-id="67a5b-105">This article describes how to enroll and test basic mobile device management capabilities for iOS/iPadOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="67a5b-106">Het registreren van iOS-/iPadOS- en Android-apparaten in uw testomgeving omvat drie fasen:</span><span class="sxs-lookup"><span data-stu-id="67a5b-106">Enrolling iOS/iPadOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="67a5b-107">Fase 1: uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="67a5b-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="67a5b-108">Fase 2: Uw iOS-/iPadOS- en Android-apparaten registreren</span><span class="sxs-lookup"><span data-stu-id="67a5b-108">Phase 2: Enroll your iOS/iPadOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="67a5b-109">Fase 3: Uw iOS/iPadOS- en Android-apparaten op afstand beheren</span><span class="sxs-lookup"><span data-stu-id="67a5b-109">Phase 3: Manage your iOS/iPadOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="67a5b-111">Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, gaat u naar Microsoft 365 voor [enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="67a5b-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="67a5b-112">Fase 1: uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="67a5b-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="67a5b-113">Als u iOS-/iPadOS- en Android-apparaten op een lichtgewicht manier wilt registreren met de minimumvereisten, volgt u de instructies in [de lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="67a5b-113">If you want to enroll iOS/iPadOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="67a5b-114">Als u iOS/iPadOS- en Android-apparaten wilt registreren in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="67a5b-114">If you want to enroll iOS/iPadOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="67a5b-115">Voor het testen van geautomatiseerde licenties en groepslidmaatschap is geen gesimuleerde testomgeving voor ondernemingen vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="67a5b-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="67a5b-116">Het wordt hier als een optie aangeboden, zodat u geautomatiseerde licenties en groepslidmaatschap kunt testen en u erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="67a5b-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="67a5b-117">Fase 2: Uw iOS- en Android-apparaten registreren</span><span class="sxs-lookup"><span data-stu-id="67a5b-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="67a5b-118">Als u een MDM-oplossing (Mobile Device Management) overweegt om uw apparaten te beheren, kunt u deze Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="67a5b-118">If you're considering a mobile device management (MDM) solution to manage your devices, you can use Microsoft Intune.</span></span> <span data-ttu-id="67a5b-119">Wanneer u met een MDM-provider werkt, inclusief Intune, worden apparaten 'geregistreerd'.</span><span class="sxs-lookup"><span data-stu-id="67a5b-119">When working with any MDM provider, including Intune, devices are "enrolled".</span></span> <span data-ttu-id="67a5b-120">Wanneer ze zijn geregistreerd, ontvangen ze de functies en instellingen die u configureert.</span><span class="sxs-lookup"><span data-stu-id="67a5b-120">When enrolled, they receive the features and settings you configure.</span></span> 

<span data-ttu-id="67a5b-121">In Intune zijn er een aantal manieren om uw iOS-/iPadOS- en Android-apparaten in te schrijven.</span><span class="sxs-lookup"><span data-stu-id="67a5b-121">In Intune, there are a few ways to enroll your iOS/iPadOS and Android devices.</span></span> <span data-ttu-id="67a5b-122">U kunt de inschrijvingsoptie kiezen die het beste werkt voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="67a5b-122">You can choose the enrollment option that works best for your organization.</span></span> <span data-ttu-id="67a5b-123">Zie de volgende artikelen voor meer informatie en richtlijnen:</span><span class="sxs-lookup"><span data-stu-id="67a5b-123">For more information and guidance, see the following articles:</span></span>

- [<span data-ttu-id="67a5b-124">Implementatiehandleiding: IOS- en iPadOS-apparaten registreren in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="67a5b-124">Deployment guide: Enroll iOS and iPadOS devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [<span data-ttu-id="67a5b-125">Implementatiehandleiding: Android-apparaten registreren in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="67a5b-125">Deployment guide: Enroll Android devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-android)

<span data-ttu-id="67a5b-126">Als u Klaar bent om Intune te gebruiken voor apparaatbeheer en wat richtlijnen wilt, kunnen de volgende informatie u helpen:</span><span class="sxs-lookup"><span data-stu-id="67a5b-126">If you're ready to use Intune for device management, and want some guidance, then the following information may help:</span></span>

- [<span data-ttu-id="67a5b-127">Overzicht van apparaatbeheer</span><span class="sxs-lookup"><span data-stu-id="67a5b-127">Device management overview</span></span>](/mem/intune/fundamentals/what-is-device-management)
- [<span data-ttu-id="67a5b-128">Zelfstudie: Walkthrough Intune in Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="67a5b-128">Tutorial: Walkthrough Intune in Microsoft Endpoint Manager</span></span>](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [<span data-ttu-id="67a5b-129">Implementatiehandleiding: Instellen of verplaatsen naar Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="67a5b-129">Deployment guide: Setup or move to Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="67a5b-130">Fase 3: Uw iOS- en Android-apparaten op afstand beheren</span><span class="sxs-lookup"><span data-stu-id="67a5b-130">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="67a5b-131">Microsoft Intune biedt de functie Voor het opnieuw instellen van toegangscodes op afstand.</span><span class="sxs-lookup"><span data-stu-id="67a5b-131">Microsoft Intune provides remote lock and passcode reset feature.</span></span> <span data-ttu-id="67a5b-132">Als iemand zijn of haar apparaat kwijt is, kunt u het apparaat op afstand vergrendelen.</span><span class="sxs-lookup"><span data-stu-id="67a5b-132">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="67a5b-133">Als iemand zijn wachtwoordcode vergeet, kunt u deze op afstand opnieuw instellen.</span><span class="sxs-lookup"><span data-stu-id="67a5b-133">If someone forgets their passcode, you can remotely reset it.</span></span>

- <span data-ttu-id="67a5b-134">Zie Apparaten op afstand vergrendelen met Intune als u een iOS/iPadOS- of Android-apparaat op afstand [wilt vergrendelen.](/mem/intune/remote-actions/device-remote-lock)</span><span class="sxs-lookup"><span data-stu-id="67a5b-134">To remotely lock an iOS/iPadOS or Android device, see [Remotely lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span></span>
- <span data-ttu-id="67a5b-135">Zie Een apparaatcode opnieuw instellen of verwijderen [in Intune](/mem/intune/remote-actions/device-passcode-reset)om de wachtwoordcode op afstand opnieuw in te stellen.</span><span class="sxs-lookup"><span data-stu-id="67a5b-135">To remotely reset the passcode, see [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span></span>

<span data-ttu-id="67a5b-136">Zie beschikbare apparaatacties voor extra taken die u op afstand [kunt uitvoeren.](/mem/intune/remote-actions/device-management#available-device-actions)</span><span class="sxs-lookup"><span data-stu-id="67a5b-136">For additional tasks you can run remotely, see [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="67a5b-137">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="67a5b-137">Next step</span></span>

<span data-ttu-id="67a5b-138">Ontdek extra [functies en mogelijkheden](m365-enterprise-test-lab-guides.md#mobile-device-management) voor mobiel apparaatbeheer in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="67a5b-138">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="67a5b-139">Zie ook</span><span class="sxs-lookup"><span data-stu-id="67a5b-139">See Also</span></span>

[<span data-ttu-id="67a5b-140">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="67a5b-140">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="67a5b-141">Apparaat compliancebeleid voor uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="67a5b-141">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="67a5b-142">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="67a5b-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
