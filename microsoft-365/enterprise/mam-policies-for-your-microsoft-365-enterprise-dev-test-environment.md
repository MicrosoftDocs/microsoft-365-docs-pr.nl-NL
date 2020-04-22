---
title: Nalevingsbeleid voor apparaten voor uw Microsoft 365 Enterprise-testomgeving
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
description: Gebruik deze Test Lab Guide om intune-beleid voor apparaatnaleving toe te voegen aan uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: 4324ccca761e504812edc210ee6b6abdc484b670
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631583"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="824f8-103">Nalevingsbeleid voor apparaten voor uw Microsoft 365 Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="824f8-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="824f8-104">*Deze testlabrichtlijn kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="824f8-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="824f8-105">Met de instructies in dit artikel voegt u een Intune-beleid voor apparaatnaleving toe voor Windows 10-apparaten en Microsoft 365 Apps for enterprise aan uw Microsoft 365 Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="824f8-105">With the instructions in this article, you add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 Enterprise test environment.</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="824f8-107">Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen over de Microsoft 365 Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="824f8-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="824f8-108">Fase 1: uw Microsoft 365 Enterprise-testomgeving uitbouwen</span><span class="sxs-lookup"><span data-stu-id="824f8-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="824f8-109">Als u alleen mam-beleid op een lichtgewicht manier wilt configureren met de minimale vereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="824f8-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="824f8-110">Als u MAM-beleid wilt configureren in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="824f8-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="824f8-111">Voor het testen van geautomatiseerde licenties en groepslidmaatschap is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="824f8-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="824f8-112">Het wordt hier als optie verstrekt, zodat u geautomatiseerde licenties en groepslidmaatschap testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="824f8-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="824f8-113">Fase 2: Een beleid voor naleving van apparaten voor apparaten met apparaten voor apparaten met apparaten maken</span><span class="sxs-lookup"><span data-stu-id="824f8-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="824f8-114">In deze fase maakt u een nalevingsbeleid voor apparaten voor apparaten met apparaten voor apparaten met een apparaat.</span><span class="sxs-lookup"><span data-stu-id="824f8-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="824f8-115">Ga naar de Office 365-portal op ([https://portal.office.com](https://portal.office.com)) en meld u aan bij uw Office 365-testlababonnement met uw wereldwijde beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="824f8-115">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="824f8-116">Open de Azure-portal op een nieuw [https://portal.azure.com](https://portal.azure.com)tabblad van uw browser op .</span><span class="sxs-lookup"><span data-stu-id="824f8-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="824f8-117">Typ **Intune** in het zoekvak op het tabblad Azure-portal in uw browser en klik op **Intune**.</span><span class="sxs-lookup"><span data-stu-id="824f8-117">From the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="824f8-118">Als u een **bericht Voor apparaatbeheer u nog niet** hebt ingeschakeld In het deelvenster Microsoft **Intune** klikt u erop.</span><span class="sxs-lookup"><span data-stu-id="824f8-118">If you see a **You haven't enabled device management yet** message In the **Microsoft Intune** pane, click it.</span></span> <span data-ttu-id="824f8-119">Klik in het **deelvenster Autoriteit voor beheer** van mobiele apparaten op **MDM-autoriteit inafstemmen**en klik vervolgens op **Kiezen**.</span><span class="sxs-lookup"><span data-stu-id="824f8-119">In the **Mobile Device Management authority** pane, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="824f8-120">Het tabblad browser vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="824f8-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="824f8-121">Klik in het linkernavigatiedeelvenster op **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="824f8-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="824f8-122">In the **Groups-All groups** pane, click **+ New Group**.</span><span class="sxs-lookup"><span data-stu-id="824f8-122">In the **Groups-All groups** pane, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="824f8-123">Selecteer **in** het deelvenster Groep de optie Office **365** of **Beveiliging** voor **Name** **groepstype?** **Managed Windows 10 device users** **Assigned** **Membership type** **Create**</span><span class="sxs-lookup"><span data-stu-id="824f8-123">In the **Group** pane, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="824f8-124">Klik **op Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="824f8-124">Click **Microsoft Intune**.</span></span> <span data-ttu-id="824f8-125">Klik in het deelvenster **Microsoft Intune** in de lijst **Snelle taken** op **Een nalevingsbeleid maken**.</span><span class="sxs-lookup"><span data-stu-id="824f8-125">In the **Microsoft Intune** pane, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
9. <span data-ttu-id="824f8-126">Klik in het deelvenster **Nalevingsbeleidsprofielen** op **Beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="824f8-126">In the **Compliance Policy Profiles** pane, click **Create Policy**.</span></span>
    
10. <span data-ttu-id="824f8-127">Typ **Windows 10**in het deelvenster **Beleid maken** in **Naam**.</span><span class="sxs-lookup"><span data-stu-id="824f8-127">In the **Create Policy** pane, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="824f8-128">Selecteer **in Platform**Windows **10 en hoger**op **OK** in het deelvenster **Nalevingsbeleid van Windows 10** en klik vervolgens op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="824f8-128">In **Platform**, select **Windows 10 and later**, click **OK** In the **Windows 10 compliance policy** pane, and then click **Create**.</span></span> 
    
11. <span data-ttu-id="824f8-129">Klik op **Nalevingsbeleidsprofielen**en klik vervolgens op de naam van het **Windows 10-beleid.**</span><span class="sxs-lookup"><span data-stu-id="824f8-129">Click **Compliance Policy Profiles**, and then click the **Windows 10** policy name.</span></span>
    
12. <span data-ttu-id="824f8-130">Klik in het deelvenster **Windows 10** op **Toewijzingen**en klik vervolgens op **Groepen selecteren om op te nemen**.</span><span class="sxs-lookup"><span data-stu-id="824f8-130">In the **Windows 10** pane, click **Assignments**, and then click **Select groups to include**.</span></span>
    
13. <span data-ttu-id="824f8-131">Klik in het **deelvenster Selecteren om op te nemen** op de groep **Beheerde gebruikers van Windows 10-apparaten** en klik vervolgens op **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="824f8-131">In the **Select groups to include** pane, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
14. <span data-ttu-id="824f8-132">Klik **op Opslaan,** klik op **Microsoft Intune-Overzicht**en klik vervolgens op **Client-apps** in de linkernavigatie.</span><span class="sxs-lookup"><span data-stu-id="824f8-132">Click **Save**, click **Microsoft Intune-Overview**, and then click **Client apps** in the left navigation.</span></span>
    
15. <span data-ttu-id="824f8-133">Klik in het deelvenster **Client-apps** op **Apps**en klik vervolgens op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="824f8-133">In the **Client Apps** pane, click **Apps**, and then click **Add**.</span></span> 

16. <span data-ttu-id="824f8-134">Selecteer **app-type** toevoegen in het deelvenster **App**toevoegen en selecteer **Vervolgens Windows 10** onder **Office 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="824f8-134">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

17. <span data-ttu-id="824f8-135">Selecteer **App-suitegegevens**in het deelvenster **App toevoegen** .</span><span class="sxs-lookup"><span data-stu-id="824f8-135">In the **Add App** pane, select **App Suite Information**.</span></span>
 
18. <span data-ttu-id="824f8-136">Typ **Microsoft 365 Apps voor bedrijven in** het deelvenster App **Suite-informatie** in zowel **Suite-naam** als **suitebeschrijving**.</span><span class="sxs-lookup"><span data-stu-id="824f8-136">In the **App Suite Information** pane, type **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**.</span></span>
<span data-ttu-id="824f8-137">Klik op OK.</span><span class="sxs-lookup"><span data-stu-id="824f8-137">Click OK.</span></span>

19. <span data-ttu-id="824f8-138">Selecteer **app-suite configureren**in het deelvenster **App toevoegen** en klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="824f8-138">In the **Add App** pane, select **Configure App Suite**, and then click **OK**.</span></span>

20. <span data-ttu-id="824f8-139">Selecteer **App-instellingen**in het deelvenster **App toevoegen** .</span><span class="sxs-lookup"><span data-stu-id="824f8-139">In the **Add App** pane, select **App Suite Settings**.</span></span>

21. <span data-ttu-id="824f8-140">Selecteer **Halfjaarlijks**kanaal voor **Bijwerken**en klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="824f8-140">For **Update Channel**, select **Semi-Annual**, and then click **OK**.</span></span>

22. <span data-ttu-id="824f8-141">Klik **in** het deelvenster App toevoegen op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="824f8-141">In the **Add app** pane, click **Add**.</span></span>

<span data-ttu-id="824f8-142">U hebt nu een beleid voor apparaatnaleving voor het testen van de geselecteerde apps in het nalevingsbeleid voor **Windows 10-apparaten** en voor leden van de groep Beheerde gebruikers van **Windows 10-apparaten.**</span><span class="sxs-lookup"><span data-stu-id="824f8-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="824f8-143">Houd er rekening mee dat het selecteren van Office 365 als groepstype extra bronnen zal opleveren.</span><span class="sxs-lookup"><span data-stu-id="824f8-143">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="824f8-144">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="824f8-144">Next step</span></span>

<span data-ttu-id="824f8-145">Ontdek extra functies en mogelijkheden voor het beheer van [mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="824f8-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="824f8-146">Zie ook</span><span class="sxs-lookup"><span data-stu-id="824f8-146">See also</span></span>

<span data-ttu-id="824f8-147">[Microsoft 365 Enterprise Test Lab-handleidingen](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="824f8-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="824f8-148">IOS- en Android-apparaten inschrijven in uw Microsoft 365 Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="824f8-148">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="824f8-149">Microsoft 365 Enterprise implementeren</span><span class="sxs-lookup"><span data-stu-id="824f8-149">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="824f8-150">Enterprise Mobility + Beveiliging (EMS)</span><span class="sxs-lookup"><span data-stu-id="824f8-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
