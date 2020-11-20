---
title: Beleid voor apparaatcompatibiliteit voor uw Microsoft 365 voor Enterprise testomgeving
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: U kunt deze test lab-handleiding gebruiken om beleid voor het naleving van intune-apparaten toe te voegen aan de testomgeving van Microsoft 365.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367093"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="22c55-103">Beleid voor apparaatcompatibiliteit voor uw Microsoft 365 voor Enterprise testomgeving</span><span class="sxs-lookup"><span data-stu-id="22c55-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="22c55-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="22c55-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="22c55-105">In dit artikel wordt uitgelegd hoe u een intune-apparaatcompatibiliteit voor Windows 10-apparaten en Microsoft 365-apps voor Enterprise toevoegt aan uw Microsoft 365 voor Enterprise testomgeving.</span><span class="sxs-lookup"><span data-stu-id="22c55-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="22c55-106">Het nalevingsbeleid van een intune-apparaat bestaat uit twee fasen:</span><span class="sxs-lookup"><span data-stu-id="22c55-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="22c55-107">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="22c55-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="22c55-108">Fase 2: een beleid voor naleving van apparaten maken voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="22c55-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="22c55-110">Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.</span><span class="sxs-lookup"><span data-stu-id="22c55-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="22c55-111">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="22c55-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="22c55-112">Als u het MAM-beleid op slechts een lichte manier met de minimumvereisten wilt configureren, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="22c55-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="22c55-113">Als u het MAM-beleid in een gesimuleerde Enterprise wilt configureren, volgt u de instructies in [Pass-to-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="22c55-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="22c55-114">Voor het testen van geautomatiseerde licentie-en groepslidmaatschappen is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest.</span><span class="sxs-lookup"><span data-stu-id="22c55-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="22c55-115">Dit wordt hier als optie geboden, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="22c55-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="22c55-116">Fase 2: een beleid voor naleving van apparaten maken voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="22c55-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="22c55-117">In deze fase maakt u een beleid voor naleving van apparaten voor Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="22c55-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="22c55-118">In deze fase wordt Microsoft intune en het [Beheercentrum van Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) gebruikt om een groep toe te voegen en een nalevingsbeleid te maken.</span><span class="sxs-lookup"><span data-stu-id="22c55-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="22c55-119">Ga naar het [Microsoft 365-Beheercentrum](https://admin.microsoft.com)en meld u aan bij uw microsoft 365-test abonnement met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="22c55-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="22c55-120">Selecteer het Beheercentrum voor **eindpunten** van de beheerder.</span><span class="sxs-lookup"><span data-stu-id="22c55-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="22c55-121">Het [Beheercentrum voor eindpunten](https://go.microsoft.com/fwlink/?linkid=2109431) wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="22c55-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="22c55-122">Als u een bericht ziet dat vergelijkbaar is met de optie **Apparaatbeheer** weergeven, selecteert u intune als de MDM-autoriteit.</span><span class="sxs-lookup"><span data-stu-id="22c55-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="22c55-123">Voor de specifieke stappen raadpleegt u [de service voor het beheer van mobiele apparaten instellen](/mem/intune/fundamentals/mdm-authority-set).</span><span class="sxs-lookup"><span data-stu-id="22c55-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="22c55-124">Het Beheercentrum voor eindpunten van het Beheercentrum voor apparaten en de app-beheer.</span><span class="sxs-lookup"><span data-stu-id="22c55-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="22c55-125">Voor een rondleiding van dit Beheercentrum raadpleegt u [Zelfstudie: procedure intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span><span class="sxs-lookup"><span data-stu-id="22c55-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="22c55-126">In **groepen** voegt u een nieuwe **Microsoft 365** of **beveiligings** groep met de naam **beheerde gebruikers van Windows 10-apparaten** met een **toegewezen** lidmaatschaps type toe.</span><span class="sxs-lookup"><span data-stu-id="22c55-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="22c55-127">In de volgende stappen wijst u uw compliance-beleid toe aan deze groep.</span><span class="sxs-lookup"><span data-stu-id="22c55-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="22c55-128">Voor de specifieke stappen en voor informatie over **Microsoft 365** of **beveiligings** groepen, raadpleegt [u groepen toevoegen om gebruikers en apparaten te ordenen](/mem/intune/fundamentals/groups-add).</span><span class="sxs-lookup"><span data-stu-id="22c55-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="22c55-129">Maak in **apparaten** een nalevingsbeleid voor Windows 10.</span><span class="sxs-lookup"><span data-stu-id="22c55-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="22c55-130">Wijs dit beleid toe aan de groep gebruikers van de **beheerde Windows 10-apparaten** die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="22c55-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="22c55-131">In uw beleid kunt u eenvoudige wachtwoorden blokkeren, een firewall vereisen, de Microsoft Defender malware-service uitvoeren en nog veel meer.</span><span class="sxs-lookup"><span data-stu-id="22c55-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="22c55-132">Het nalevingsbeleid bevat meestal de basisinstellingen, of het minimum aantal voor elk apparaat.</span><span class="sxs-lookup"><span data-stu-id="22c55-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="22c55-133">Voor de specifieke stappen en voor informatie over de beschikbare compliance-instellingen die u kunt configureren, raadpleegt u [nalevingsbeleid gebruiken om regels in te stellen voor apparaten die u beheert](/mem/intune/protect/device-compliance-get-started).</span><span class="sxs-lookup"><span data-stu-id="22c55-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="22c55-134">Wanneer u klaar bent, beschikt u over een beleid voor apparaatcompatibiliteit voor het testen van leden in de groep gebruikers van de **beheerde Windows 10-apparaten** .</span><span class="sxs-lookup"><span data-stu-id="22c55-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="22c55-135">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="22c55-135">Next step</span></span>

<span data-ttu-id="22c55-136">Verken de extra functies en mogelijkheden van het [beheer van mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="22c55-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="22c55-137">Zie ook</span><span class="sxs-lookup"><span data-stu-id="22c55-137">See also</span></span>

<span data-ttu-id="22c55-138">[Proefversie van Microsoft 365 voor Enterprise test lab](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="22c55-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="22c55-139">IOS-en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="22c55-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="22c55-140">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="22c55-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="22c55-141">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="22c55-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
