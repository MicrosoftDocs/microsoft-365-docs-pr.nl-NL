---
title: Apparaat compliancebeleid voor uw Microsoft 365 voor bedrijfstestomgeving
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
description: Gebruik deze testlaboratoriumhandleiding om intune-beleid voor apparaat compliance toe te voegen aan uw Microsoft 365 voor bedrijfstestomgeving.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367093"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d5475-103">Apparaat compliancebeleid voor uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="d5475-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d5475-104">*Deze testlaborator kan alleen worden gebruikt Microsoft 365 voor bedrijfstestomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="d5475-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="d5475-105">In dit artikel wordt beschreven hoe u een intune-apparaat compliancebeleid voor Windows 10 apparaten en Microsoft 365-apps voor ondernemingen toevoegt aan uw Microsoft 365 voor bedrijfstestomgeving.</span><span class="sxs-lookup"><span data-stu-id="d5475-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="d5475-106">Het toevoegen van een Intune-beleid voor apparaat compliance omvat twee fasen:</span><span class="sxs-lookup"><span data-stu-id="d5475-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="d5475-107">Fase 1: uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="d5475-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="d5475-108">Fase 2: Een apparaat compliancebeleid maken voor Windows 10 apparaten</span><span class="sxs-lookup"><span data-stu-id="d5475-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="d5475-110">Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, gaat u naar Microsoft 365 voor [enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="d5475-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d5475-111">Fase 1: uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="d5475-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d5475-112">Als u MAM-beleid alleen op een lichtgewicht manier wilt configureren met de minimumvereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="d5475-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d5475-113">Als u MAM-beleid wilt configureren in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="d5475-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5475-114">Voor het testen van geautomatiseerde licenties en groepslidmaatschap is geen gesimuleerde testomgeving voor ondernemingen vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="d5475-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="d5475-115">Het wordt hier als een optie aangeboden, zodat u geautomatiseerde licenties en groepslidmaatschap kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="d5475-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="d5475-116">Fase 2: Een apparaat compliancebeleid maken voor Windows 10 apparaten</span><span class="sxs-lookup"><span data-stu-id="d5475-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="d5475-117">In deze fase maakt u een apparaat compliancebeleid voor Windows 10 apparaten.</span><span class="sxs-lookup"><span data-stu-id="d5475-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="d5475-118">In deze fase Microsoft Intune en het [Microsoft Endpoint Manager beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) gebruikt om een groep toe te voegen en een compliancebeleid te maken.</span><span class="sxs-lookup"><span data-stu-id="d5475-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="d5475-119">Ga naar het [Microsoft 365-beheercentrum](https://admin.microsoft.com)en meld u aan bij uw Microsoft 365 testlaboratorium met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="d5475-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="d5475-120">Selecteer het **Endpoint Manager** beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d5475-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="d5475-121">Het [Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="d5475-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="d5475-122">Als er een bericht wordt weergegeven dat lijkt op **U** hebt apparaatbeheer nog niet ingeschakeld, selecteert u Intune als de MDM-autoriteit.</span><span class="sxs-lookup"><span data-stu-id="d5475-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="d5475-123">Zie De autoriteit voor mobiel apparaatbeheer instellen voor de [specifieke stappen.](/mem/intune/fundamentals/mdm-authority-set)</span><span class="sxs-lookup"><span data-stu-id="d5475-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="d5475-124">Het Endpoint Manager beheercentrum richt zich op apparaatbeheer en app-beheer.</span><span class="sxs-lookup"><span data-stu-id="d5475-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="d5475-125">Zie [Zelfstudie: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span><span class="sxs-lookup"><span data-stu-id="d5475-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="d5475-126">Voeg **in** Groepen een nieuwe **groep** Microsoft 365 **of** beveiligingsgroep met de naam Beheerd **Windows 10 apparaatgebruikers** toe, met een type **Toegewezen** lidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="d5475-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="d5475-127">In de volgende stappen wijst u uw compliancebeleid toe aan deze groep.</span><span class="sxs-lookup"><span data-stu-id="d5475-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="d5475-128">Zie Groepen toevoegen om gebruikers en apparaten te ordenen **voor meer informatie over** Microsoft 365 of [beveiligingsgroepen.](/mem/intune/fundamentals/groups-add) </span><span class="sxs-lookup"><span data-stu-id="d5475-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="d5475-129">Maak **in Apparaten** een Windows 10 compliancebeleid.</span><span class="sxs-lookup"><span data-stu-id="d5475-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="d5475-130">Wijs dit beleid toe aan **de groep Windows 10 apparaten die u** hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d5475-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="d5475-131">In uw beleid kunt u eenvoudige wachtwoorden blokkeren, een firewall vereisen, de Microsoft Defender Antimalware-service uitvoeren en meer.</span><span class="sxs-lookup"><span data-stu-id="d5475-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="d5475-132">Een compliancebeleid bevat meestal de basisinstellingen of het absolute minimum dat elk apparaat moet hebben.</span><span class="sxs-lookup"><span data-stu-id="d5475-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="d5475-133">Zie Compliancebeleid gebruiken om regels in te stellen voor apparaten die u beheert voor de specifieke stappen en voor informatie over de beschikbare nalevingsinstellingen die u kunt [configureren.](/mem/intune/protect/device-compliance-get-started)</span><span class="sxs-lookup"><span data-stu-id="d5475-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="d5475-134">Wanneer u klaar bent, hebt u een apparaat compliancebeleid voor het testen van leden in de groep Windows 10 **apparaatgebruikers.**</span><span class="sxs-lookup"><span data-stu-id="d5475-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="d5475-135">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="d5475-135">Next step</span></span>

<span data-ttu-id="d5475-136">Ontdek extra [functies en mogelijkheden](m365-enterprise-test-lab-guides.md#mobile-device-management) voor mobiel apparaatbeheer in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="d5475-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5475-137">Zie ook</span><span class="sxs-lookup"><span data-stu-id="d5475-137">See also</span></span>

<span data-ttu-id="d5475-138">[Microsoft 365 voor enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="d5475-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="d5475-139">IOS- en Android-apparaten registreren in uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="d5475-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="d5475-140">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="d5475-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d5475-141">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="d5475-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
