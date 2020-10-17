---
title: Beleid voor apparaatcompatibiliteit voor uw Microsoft 365 voor Enterprise testomgeving
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: U kunt deze test lab-handleiding gebruiken om beleid voor het naleving van intune-apparaten toe te voegen aan de testomgeving van Microsoft 365.
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487410"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="21032-103">Beleid voor apparaatcompatibiliteit voor uw Microsoft 365 voor Enterprise testomgeving</span><span class="sxs-lookup"><span data-stu-id="21032-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="21032-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="21032-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="21032-105">In dit artikel wordt uitgelegd hoe u een intune-apparaatcompatibiliteit voor Windows 10-apparaten en Microsoft 365-apps voor Enterprise toevoegt aan uw Microsoft 365 voor Enterprise testomgeving.</span><span class="sxs-lookup"><span data-stu-id="21032-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="21032-106">Het nalevingsbeleid van een intune-apparaat bestaat uit twee fasen:</span><span class="sxs-lookup"><span data-stu-id="21032-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="21032-107">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="21032-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="21032-108">Fase 2: een beleid voor naleving van apparaten maken voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="21032-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="21032-110">Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.</span><span class="sxs-lookup"><span data-stu-id="21032-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="21032-111">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="21032-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="21032-112">Als u het MAM-beleid op slechts een lichte manier met de minimumvereisten wilt configureren, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="21032-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="21032-113">Als u het MAM-beleid in een gesimuleerde Enterprise wilt configureren, volgt u de instructies in [Pass-to-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="21032-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="21032-114">Voor het testen van geautomatiseerde licentie-en groepslidmaatschappen is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest.</span><span class="sxs-lookup"><span data-stu-id="21032-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="21032-115">Dit wordt hier als optie geboden, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="21032-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="21032-116">Fase 2: een beleid voor naleving van apparaten maken voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="21032-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="21032-117">In deze fase maakt u een apparaatcompatibiliteit voor Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="21032-117">In this phase, create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="21032-118">Ga naar het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) , Meld u aan bij uw microsoft 365-test abonnement met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="21032-118">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
1. <span data-ttu-id="21032-119">Open de Azure-Portal op een nieuw tabblad van uw browser [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="21032-119">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
1. <span data-ttu-id="21032-120">Voer in het zoekvak van de Azure-Portal **intune**in en selecteer vervolgens **intune**.</span><span class="sxs-lookup"><span data-stu-id="21032-120">In the search box of the Azure portal, enter **Intune**, and then select **Intune**.</span></span>
1. <span data-ttu-id="21032-121">Als u in het **Microsoft intune** -venster geen optie voor **Apparaatbeheer hebt ingeschakeld** , kunt u deze selecteren.</span><span class="sxs-lookup"><span data-stu-id="21032-121">If you see a **You haven't enabled device management yet** message in the **Microsoft Intune** pane, select it.</span></span> <span data-ttu-id="21032-122">Selecteer in het deelvenster **Mobile Device Management Authority** de optie **intune MDM Authority**en selecteer vervolgens **Choose**.</span><span class="sxs-lookup"><span data-stu-id="21032-122">In the **Mobile Device Management authority** pane, select **Intune MDM Authority**, and then select **Choose**.</span></span>
1. <span data-ttu-id="21032-123">Vernieuw het tabblad browser.</span><span class="sxs-lookup"><span data-stu-id="21032-123">Refresh your browser tab.</span></span>
1. <span data-ttu-id="21032-124">Selecteer **groepen**in het linker navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="21032-124">In the left navigation pane, select **Groups**.</span></span>
1. <span data-ttu-id="21032-125">Selecteer in het deelvenster **groepen-alle groepen de** optie **+ nieuwe groep**.</span><span class="sxs-lookup"><span data-stu-id="21032-125">In the **Groups-All groups** pane, select **+ New Group**.</span></span>
1. <span data-ttu-id="21032-126">Selecteer in het deelvenster **groep** de optie **Microsoft 365** of **beveiliging** voor **groepstype?**, Voer **beheerde gebruikers van Windows 10-apparaten** in **naam**in, selecteer **toegewezen aan** **lidmaatschaps type**en selecteer **maken**.</span><span class="sxs-lookup"><span data-stu-id="21032-126">In the **Group** pane, select **Microsoft 365** or **Security** for **Group type?**, enter **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then select **Create**.</span></span>
1. <span data-ttu-id="21032-127">Selecteer **Microsoft intune**.</span><span class="sxs-lookup"><span data-stu-id="21032-127">Select **Microsoft Intune**.</span></span>
1. <span data-ttu-id="21032-128">Selecteer in het deelvenster **Microsoft intune** in de lijst **snelle taken** de optie **een nalevingsbeleid maken**.</span><span class="sxs-lookup"><span data-stu-id="21032-128">In the **Microsoft Intune** pane, in the **Quick tasks** list, select **Create a compliance policy**.</span></span>
1. <span data-ttu-id="21032-129">Selecteer in het deelvenster beleids **profielen voor compliance beleids** **regels maken**.</span><span class="sxs-lookup"><span data-stu-id="21032-129">In the **Compliance Policy Profiles** pane, select **Create Policy**.</span></span>
1. <span data-ttu-id="21032-130">Voer in het deelvenster **beleid maken** in **naam** **Windows 10**in.</span><span class="sxs-lookup"><span data-stu-id="21032-130">In the **Create Policy** pane, in **Name**, enter **Windows 10**.</span></span> <span data-ttu-id="21032-131">In **platform**selecteert u **Windows 10 en later**, selecteert u **OK** in het deelvenster **nalevingsbeleid van Windows 10** en selecteert u **maken**.</span><span class="sxs-lookup"><span data-stu-id="21032-131">In **Platform**, select **Windows 10 and later**, select **OK** in the **Windows 10 compliance policy** pane, and then select **Create**.</span></span>
1. <span data-ttu-id="21032-132">Selecteer **profielen voor nalevingsbeleid**en selecteer vervolgens de naam van het **Windows 10** -beleid.</span><span class="sxs-lookup"><span data-stu-id="21032-132">Select **Compliance Policy Profiles**, and then select the **Windows 10** policy name.</span></span>
1. <span data-ttu-id="21032-133">Selecteer in het deelvenster **Windows 10** **opdrachten**en selecteer **groepen selecteren om op te nemen**.</span><span class="sxs-lookup"><span data-stu-id="21032-133">In the **Windows 10** pane, select **Assignments**, and then select **Select groups to include**.</span></span>
1. <span data-ttu-id="21032-134">Selecteer in het deelvenster **groepen selecteren die moeten worden opgenomen** de groep gebruikers van de **beheerde Windows 10-apparaten** en selecteer vervolgens **selecteren**.</span><span class="sxs-lookup"><span data-stu-id="21032-134">In the **Select groups to include** pane, select the **Managed Windows 10 device users** group, and then select **Select**.</span></span>
1. <span data-ttu-id="21032-135">Selecteer **Opslaan**, selecteer **Microsoft intune-overzicht**en selecteer **client toepassingen** in de linkernavigatiebalk.</span><span class="sxs-lookup"><span data-stu-id="21032-135">Select **Save**, select **Microsoft Intune-Overview**, and then select **Client apps** in the left navigation.</span></span>
1. <span data-ttu-id="21032-136">Selecteer **apps**in het deelvenster **client-apps** en selecteer vervolgens **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="21032-136">In the **Client Apps** pane, select **Apps**, and then select **Add**.</span></span>
1. <span data-ttu-id="21032-137">Selecteer in het deelvenster **app toevoegen** de optie **app-type**en selecteer vervolgens **Windows 10** onder **Microsoft 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="21032-137">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Microsoft 365 Suite**.</span></span>
1. <span data-ttu-id="21032-138">Selecteer in het deelvenster **app toevoegen** de gegevens van de **app-Suite**.</span><span class="sxs-lookup"><span data-stu-id="21032-138">In the **Add App** pane, select **App Suite Information**.</span></span>
1. <span data-ttu-id="21032-139">Voer in het deelvenster met **app-Suite gegevens** de **Microsoft 365-apps voor Enterprise** in zowel **naam** als **Suite-beschrijving**in en selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="21032-139">In the **App Suite Information** pane, enter **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**, and then select **OK**.</span></span>
1. <span data-ttu-id="21032-140">Selecteer in het deelvenster **app toevoegen** de optie **app-Suite configureren**en selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="21032-140">In the **Add App** pane, select **Configure App Suite**, and then select **OK**.</span></span>
1. <span data-ttu-id="21032-141">Selecteer **app Suite-instellingen**in het deelvenster **app toevoegen** .</span><span class="sxs-lookup"><span data-stu-id="21032-141">In the **Add App** pane, select **App Suite Settings**.</span></span>
1. <span data-ttu-id="21032-142">Selecteer voor **Update kanaal**de optie **Semi-Annual Enterprise**en selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="21032-142">For **Update Channel**, select **Semi-Annual Enterprise**, and then select **OK**.</span></span>
1. <span data-ttu-id="21032-143">Selecteer **toevoegen**in het deelvenster **app toevoegen** .</span><span class="sxs-lookup"><span data-stu-id="21032-143">In the **Add app** pane, select **Add**.</span></span>

<span data-ttu-id="21032-144">U beschikt nu over een apparaatcompatibiliteit voor het testen van de geselecteerde apps in het nalevingsbeleid voor **Windows 10** -apparaten en de leden van de groep gebruikers van de **beheerde Windows 10-apparaat** .</span><span class="sxs-lookup"><span data-stu-id="21032-144">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="21032-145">Houd er rekening mee dat **Microsoft 365** wordt geselecteerd als groepstype, om aanvullende bronnen te maken.</span><span class="sxs-lookup"><span data-stu-id="21032-145">Please note that selecting **Microsoft 365** as the group type creates additional resources.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="21032-146">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="21032-146">Next step</span></span>

<span data-ttu-id="21032-147">Verken de extra functies en mogelijkheden van het [beheer van mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="21032-147">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="21032-148">Zie ook</span><span class="sxs-lookup"><span data-stu-id="21032-148">See also</span></span>

<span data-ttu-id="21032-149">[Proefversie van Microsoft 365 voor Enterprise test lab](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="21032-149">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="21032-150">IOS-en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="21032-150">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="21032-151">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="21032-151">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="21032-152">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="21032-152">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
