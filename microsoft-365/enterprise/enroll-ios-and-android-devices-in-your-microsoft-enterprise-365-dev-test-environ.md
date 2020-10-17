---
title: IOS-en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Gebruik deze test lab-handleiding om apparaten in uw Microsoft 365-test omgeving te registreren en deze extern te beheren.
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487694"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7ef6b-103">IOS-en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="7ef6b-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7ef6b-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="7ef6b-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="7ef6b-105">In dit artikel wordt beschreven hoe u eenvoudige functies voor het beheren van mobiele apparaten voor iOS-en Android-apparaten registreert en test in uw Microsoft 365 voor Enterprise testomgeving.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-105">This article describes how to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="7ef6b-106">Voor het registreren van iOS-en Android-apparaten in de testomgeving, moet u drie stappen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="7ef6b-106">Enrolling iOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="7ef6b-107">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="7ef6b-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="7ef6b-108">Fase 2: uw iOS-en Android-apparaten registreren</span><span class="sxs-lookup"><span data-stu-id="7ef6b-108">Phase 2: Enroll your iOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="7ef6b-109">Fase 3: uw iOS-en Android-apparaten extern beheren</span><span class="sxs-lookup"><span data-stu-id="7ef6b-109">Phase 3: Manage your iOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="7ef6b-111">Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7ef6b-112">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="7ef6b-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7ef6b-113">Als u iOS-en Android-apparaten op een lichte manier wilt registreren met de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="7ef6b-113">If you want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7ef6b-114">Als u iOS-en Android-apparaten wilt registreren in een gesimuleerde onderneming, volgt u de instructies in [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7ef6b-114">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7ef6b-115">Voor het testen van geautomatiseerde licentie-en groepslidmaatschappen is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="7ef6b-116">Dit is een optie, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en u kunt experimenteren in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="7ef6b-117">Fase 2: uw iOS-en Android-apparaten registreren</span><span class="sxs-lookup"><span data-stu-id="7ef6b-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="7ef6b-118">Gebruik eerst de instructies in [installeren en meld u aan bij de bedrijfsportal-app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) om de app Microsoft intune Company portal aan te passen aan uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-118">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="7ef6b-119">Volg vervolgens de instructies in [toegang tot uw bedrijfsbronnen instellen](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) om een IOS-apparaat in te schrijven.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-119">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="7ef6b-120">Volg vervolgens de instructies in [uw Android-apparaat in intune registreren](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) om een Android-apparaat in te schrijven.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-120">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="7ef6b-121">Fase 3: uw iOS-en Android-apparaten extern beheren</span><span class="sxs-lookup"><span data-stu-id="7ef6b-121">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="7ef6b-122">Microsoft intune biedt de functies voor het opnieuw instellen van wachtwoorden voor extern vergrendelen.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-122">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="7ef6b-123">Als iemand zijn of haar apparaat kwijtraakt, kunt u het toestel extern vergrendelen.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-123">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="7ef6b-124">Als iemand zijn of haar wachtwoord vergeet, kunt u dit extern opnieuw instellen.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-124">If someone forgets their passcode, you can remotely reset it.</span></span>
  
<span data-ttu-id="7ef6b-125">Een iOS-of Android-apparaat op afstand vergrendelen:</span><span class="sxs-lookup"><span data-stu-id="7ef6b-125">To remotely lock an iOS or Android device:</span></span>

1. <span data-ttu-id="7ef6b-126">Meld u aan bij de Azure-Portal [https://portal.azure.com](https://portal.azure.com) met de referenties van uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-126">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="7ef6b-127">Voer in het zoekvak van de Azure-Portal **intune** in en selecteer vervolgens **intune**.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-127">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="7ef6b-128">Klik op **apparaten > alle apparaten**.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="7ef6b-129">Selecteer in de lijst met apparaten een iOS-of Android-apparaat en selecteer vervolgens de actie op **afstand vergrendelen** .</span><span class="sxs-lookup"><span data-stu-id="7ef6b-129">In the list of devices, select an iOS or Android device, and then select the **Remote lock** action.</span></span>
    
<span data-ttu-id="7ef6b-130">De wachtwoordcode extern opnieuw instellen:</span><span class="sxs-lookup"><span data-stu-id="7ef6b-130">To remotely reset the passcode:</span></span>

1. <span data-ttu-id="7ef6b-131">Meld u indien nodig aan bij de Azure-Portal [https://portal.azure.com](https://portal.azure.com) met de referenties van uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-131">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="7ef6b-132">Voer in het zoekvak van de Azure-Portal **intune** in en selecteer vervolgens **intune**.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-132">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="7ef6b-133">Selecteer **Devices**  >  **alle apparaten**.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-133">Select **Devices** > **All devices**.</span></span>
4. <span data-ttu-id="7ef6b-134">Selecteer in de lijst met apparaten die u beheert een iOS-of Android-apparaat, selecteer \*\*... \*\*En selecteer vervolgens de actie op de computer met de actie **wachtwoordcode verwijderen** .</span><span class="sxs-lookup"><span data-stu-id="7ef6b-134">From the list of devices you manage, select an iOS or Android device, select **...More**, and then select the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="7ef6b-135">Zie [beschikbare acties voor apparaten](https://docs.microsoft.com/intune/device-management#available-device-actions)voor een extra proef.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-135">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="7ef6b-136">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="7ef6b-136">Next step</span></span>

<span data-ttu-id="7ef6b-137">Verken de extra functies en mogelijkheden van het [beheer van mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="7ef6b-137">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ef6b-138">Zie ook</span><span class="sxs-lookup"><span data-stu-id="7ef6b-138">See Also</span></span>

[<span data-ttu-id="7ef6b-139">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="7ef6b-139">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="7ef6b-140">Beleid voor apparaatcompatibiliteit voor uw Microsoft 365 voor Enterprise testomgeving</span><span class="sxs-lookup"><span data-stu-id="7ef6b-140">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="7ef6b-141">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="7ef6b-141">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
