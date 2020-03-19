---
title: IOS- en Android-apparaten inschrijven in uw Microsoft 365 Enterprise-testomgeving
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
description: Gebruik deze Test Lab Guide om apparaten in te schrijven in uw Microsoft 365-testomgeving en deze op afstand te beheren.
ms.openlocfilehash: ae6ff9e704fc239638b5951a95ae23c45e85b7be
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805668"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8c079-103">IOS- en Android-apparaten inschrijven in uw Microsoft 365 Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="8c079-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8c079-104">*Deze Test Lab Guide kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="8c079-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="8c079-105">Door de instructies in dit artikel op te volgen, u de basismogelijkheden voor het beheer van mobiele apparaten voor iOS- en Android-apparaten inschrijven en testen in uw Microsoft 365 Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="8c079-105">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Test Lab-hulplijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="8c079-107">Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.</span><span class="sxs-lookup"><span data-stu-id="8c079-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8c079-108">Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen</span><span class="sxs-lookup"><span data-stu-id="8c079-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8c079-109">Als je iOS- en Android-apparaten alleen op een lichtgewicht manier wilt inschrijven met de minimumvereisten, volg dan de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="8c079-109">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="8c079-110">Als u iOS- en Android-apparaten wilt inschrijven in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8c079-110">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8c079-111">Het testen van geautomatiseerde licenties en groepslidmaatschap vereist niet de gesimuleerde bedrijfstestomgeving, die een gesimuleerd intranet bevat dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="8c079-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="8c079-112">Het wordt hier als optie geleverd, zodat u geautomatiseerde licenties en groepslidmaatschap testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="8c079-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="8c079-113">Fase 2: Schrijf je iOS- en Android-apparaten in</span><span class="sxs-lookup"><span data-stu-id="8c079-113">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="8c079-114">Gebruik eerst de instructies in [Installeren en meld u aan bij de Bedrijfsportal-app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) om de Microsoft Intune Company Portal-app aan te passen aan uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="8c079-114">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="8c079-115">Gebruik vervolgens de instructies in [Het instellen van toegang tot uw bedrijfsbronnen](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) om een iOS-apparaat in te schrijven.</span><span class="sxs-lookup"><span data-stu-id="8c079-115">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="8c079-116">Gebruik vervolgens de instructies in [Schrijf je Android-apparaat in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) om een Android-apparaat in te schrijven.</span><span class="sxs-lookup"><span data-stu-id="8c079-116">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="8c079-117">Fase 3: Beheer je iOS- en Android-apparaten op afstand</span><span class="sxs-lookup"><span data-stu-id="8c079-117">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="8c079-118">Microsoft Intune biedt zowel mogelijkheden voor het vergrendelen als het resetten van toegangscodes.</span><span class="sxs-lookup"><span data-stu-id="8c079-118">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="8c079-119">Als iemand zijn apparaat verliest, u het apparaat op afstand vergrendelen.</span><span class="sxs-lookup"><span data-stu-id="8c079-119">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="8c079-120">Als iemand zijn toegangscode vergeet, u deze op afstand opnieuw instellen.</span><span class="sxs-lookup"><span data-stu-id="8c079-120">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="8c079-121">Een iOS- of Android-apparaat op afstand vergrendelen:</span><span class="sxs-lookup"><span data-stu-id="8c079-121">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="8c079-122">Meld u aan bij [https://portal.azure.com](https://portal.azure.com) de Azure-portal met de referenties van uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="8c079-122">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="8c079-123">Typ Op het tabblad Azure-portal in uw browser **Intune** in het zoekvak en klik vervolgens op **Intune**.</span><span class="sxs-lookup"><span data-stu-id="8c079-123">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="8c079-124">Klik op **Apparaten > alle apparaten**.</span><span class="sxs-lookup"><span data-stu-id="8c079-124">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="8c079-125">Klik in de lijst met apparaten op een iOS- of Android-apparaat en klik vervolgens op de actie **Extern vergrendelen.**</span><span class="sxs-lookup"><span data-stu-id="8c079-125">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="8c079-126">Ga als reactie op het instellen van de toegangscode op afstand:</span><span class="sxs-lookup"><span data-stu-id="8c079-126">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="8c079-127">Meld u indien nodig aan [https://portal.azure.com](https://portal.azure.com) bij de Azure-portal met de referenties van uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="8c079-127">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="8c079-128">Typ Op het tabblad Azure-portal in uw browser **Intune** in het zoekvak en klik vervolgens op **Intune**.</span><span class="sxs-lookup"><span data-stu-id="8c079-128">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="8c079-129">Klik op **Apparaten > alle apparaten**.</span><span class="sxs-lookup"><span data-stu-id="8c079-129">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="8c079-130">Klik in de lijst met apparaten die u beheert op een iOS- of Android-apparaat en kies **... Meer**.</span><span class="sxs-lookup"><span data-stu-id="8c079-130">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="8c079-131">Kies vervolgens de externe actie **voor toegangscodes verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="8c079-131">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="8c079-132">Zie [Beschikbare apparaatacties](https://docs.microsoft.com/intune/device-management#available-device-actions)voor extra experimenten.</span><span class="sxs-lookup"><span data-stu-id="8c079-132">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="8c079-133">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="8c079-133">Next step</span></span>

<span data-ttu-id="8c079-134">Ontdek extra functies en mogelijkheden [voor het beheer](m365-enterprise-test-lab-guides.md#mobile-device-management) van mobiele apparaten in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="8c079-134">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c079-135">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8c079-135">See Also</span></span>

[<span data-ttu-id="8c079-136">Microsoft 365 Enterprise Test Lab-handleidingen</span><span class="sxs-lookup"><span data-stu-id="8c079-136">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="8c079-137">Apparaatnalevingsbeleid voor uw Microsoft 365 Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="8c079-137">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="8c079-138">Microsoft 365 Enterprise implementeren</span><span class="sxs-lookup"><span data-stu-id="8c079-138">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

