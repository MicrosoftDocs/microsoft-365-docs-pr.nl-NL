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
ms.openlocfilehash: b4a95b2c7e58239c0a8d0d3b5045e7337f43de6b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686008"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="1baf6-103">IOS-en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="1baf6-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="1baf6-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="1baf6-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="1baf6-105">Door de instructies in dit artikel te volgen, kunt u de functies voor het beheren van mobiele apparaten voor iOS-en Android-apparaten registreren en testen in uw Microsoft 365 voor Enterprise testomgeving.</span><span class="sxs-lookup"><span data-stu-id="1baf6-105">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="1baf6-107">Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="1baf6-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="1baf6-108">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="1baf6-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="1baf6-109">Als u alleen iOS-en Android-apparaten op een lichte manier wilt registreren met de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="1baf6-109">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1baf6-110">Als u iOS-en Android-apparaten wilt registreren in een gesimuleerde onderneming, volgt u de instructies in [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1baf6-110">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1baf6-111">Voor het testen van de geautomatiseerde licentie-en groepslidmaatschappen is de gesimuleerde Enterprise testomgeving niet vereist, waaronder een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest.</span><span class="sxs-lookup"><span data-stu-id="1baf6-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="1baf6-112">U kunt dit hier opgeven als optie, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="1baf6-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="1baf6-113">Fase 2: uw iOS-en Android-apparaten registreren</span><span class="sxs-lookup"><span data-stu-id="1baf6-113">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="1baf6-114">Gebruik eerst de instructies in [installeren en meld u aan bij de bedrijfsportal-app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) om de app Microsoft intune Company portal aan te passen aan uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="1baf6-114">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="1baf6-115">Volg vervolgens de instructies in [toegang tot uw bedrijfsbronnen instellen](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) om een IOS-apparaat in te schrijven.</span><span class="sxs-lookup"><span data-stu-id="1baf6-115">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="1baf6-116">Volg vervolgens de instructies in [uw Android-apparaat in intune registreren](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) om een Android-apparaat in te schrijven.</span><span class="sxs-lookup"><span data-stu-id="1baf6-116">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="1baf6-117">Fase 3: uw iOS-en Android-apparaten extern beheren</span><span class="sxs-lookup"><span data-stu-id="1baf6-117">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="1baf6-118">Microsoft intune biedt de functies voor het opnieuw instellen van wachtwoorden voor extern vergrendelen.</span><span class="sxs-lookup"><span data-stu-id="1baf6-118">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="1baf6-119">Als iemand zijn of haar apparaat kwijtraakt, kunt u het apparaat extern vergrendelen.</span><span class="sxs-lookup"><span data-stu-id="1baf6-119">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="1baf6-120">Als iemand zijn of haar wachtwoord vergeet, kunt u dit extern herstellen.</span><span class="sxs-lookup"><span data-stu-id="1baf6-120">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="1baf6-121">Een iOS-of Android-apparaat op afstand vergrendelen:</span><span class="sxs-lookup"><span data-stu-id="1baf6-121">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="1baf6-122">Meld u aan bij de Azure-Portal [https://portal.azure.com](https://portal.azure.com) met de referenties van uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="1baf6-122">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="1baf6-123">Typ in het dialoogvenster van uw browser op het tabblad Azure Portal de tekst **intune** in het zoekvak en klik vervolgens op **intune**.</span><span class="sxs-lookup"><span data-stu-id="1baf6-123">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="1baf6-124">Klik op **apparaten > alle apparaten**.</span><span class="sxs-lookup"><span data-stu-id="1baf6-124">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="1baf6-125">Klik op een iOS-of Android-apparaat in de lijst met apparaten en klik vervolgens op de actie op **afstand vergrendelen** .</span><span class="sxs-lookup"><span data-stu-id="1baf6-125">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="1baf6-126">De wachtwoordcode extern opnieuw instellen:</span><span class="sxs-lookup"><span data-stu-id="1baf6-126">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="1baf6-127">Meld u indien nodig aan bij de Azure-Portal [https://portal.azure.com](https://portal.azure.com) met de referenties van uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="1baf6-127">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="1baf6-128">Typ in het dialoogvenster van uw browser op het tabblad Azure Portal de tekst **intune** in het zoekvak en klik vervolgens op **intune**.</span><span class="sxs-lookup"><span data-stu-id="1baf6-128">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="1baf6-129">Klik op **apparaten > alle apparaten**.</span><span class="sxs-lookup"><span data-stu-id="1baf6-129">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="1baf6-130">Klik in de lijst met apparaten die u beheert op een iOS-of Android-apparaat en kies **... Meer informatie**.</span><span class="sxs-lookup"><span data-stu-id="1baf6-130">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="1baf6-131">Kies vervolgens de actie op de computer met de actie **wachtwoordcode verwijderen** .</span><span class="sxs-lookup"><span data-stu-id="1baf6-131">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="1baf6-132">Zie [beschikbare acties voor apparaten](https://docs.microsoft.com/intune/device-management#available-device-actions)voor een extra proef.</span><span class="sxs-lookup"><span data-stu-id="1baf6-132">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="1baf6-133">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="1baf6-133">Next step</span></span>

<span data-ttu-id="1baf6-134">Verken de extra functies en mogelijkheden van het [beheer van mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="1baf6-134">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1baf6-135">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1baf6-135">See Also</span></span>

[<span data-ttu-id="1baf6-136">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="1baf6-136">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="1baf6-137">Beleid voor apparaatcompatibiliteit voor uw Microsoft 365 voor Enterprise testomgeving</span><span class="sxs-lookup"><span data-stu-id="1baf6-137">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="1baf6-138">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="1baf6-138">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

