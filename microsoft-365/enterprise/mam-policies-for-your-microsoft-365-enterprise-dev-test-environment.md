---
title: Beleid voor apparaatnaleving voor uw Microsoft 365 Enterprise-testomgeving
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
description: Gebruik deze Test Lab-handleiding om intune-apparaatnalevingsbeleid toe te voegen aan uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: 5ef39310ff74e5d5a38e8a5dd8c7ca24a126af58
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679024"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9f252-103">Beleid voor apparaatnaleving voor uw Microsoft 365 Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="9f252-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9f252-104">*Deze testlabrichtlijn kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="9f252-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="9f252-105">Met de instructies in dit artikel voegt u een intune-apparaatcompliancebeleid voor Windows 10-apparaten en Microsoft 365-apps voor bedrijven toe aan uw Microsoft 365 Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="9f252-105">With the instructions in this article, you add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 Enterprise test environment.</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="9f252-107">Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen over de Microsoft 365 Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="9f252-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="9f252-108">Fase 1: uw Microsoft 365 Enterprise-testomgeving uitbouwen</span><span class="sxs-lookup"><span data-stu-id="9f252-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="9f252-109">Als u gewoon mam-beleid op een lichtgewicht manier wilt configureren met de minimumvereisten, volgt u de instructies in [lichtgewicht basisconfiguratie](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="9f252-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9f252-110">Als u MAM-beleid wilt configureren in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9f252-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9f252-111">Voor het testen van geautomatiseerde licenties en groepslidmaatschap is niet de gesimuleerde bedrijfstestomgeving vereist, die een gesimuleerd intranet bevat dat is verbonden met internet en directorysynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="9f252-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="9f252-112">Het wordt hier als optie aangeboden, zodat u geautomatiseerde licenties en groepslidmaatschap testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="9f252-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="9f252-113">Fase 2: Een beleid voor naleving van apparaten maken voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="9f252-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="9f252-114">In deze fase maakt u een beleid voor apparaatnaleving voor Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="9f252-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="9f252-115">Ga naar de Office 365-portal op ( [https://portal.office.com](https://portal.office.com) ) en meld u aan bij uw Office 365-testlab-abonnement met uw algemene beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="9f252-115">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="9f252-116">Open op een nieuw tabblad van uw browser de Azure-portal op [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="9f252-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="9f252-117">Typ **Intune** op het tabblad Azure-portal in uw browser in het zoekvak en klik op **Intune**.</span><span class="sxs-lookup"><span data-stu-id="9f252-117">From the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="9f252-118">Als u een **bericht Voor apparaatbeheer u nog niet hebt ingeschakeld,** klikt u erop in het deelvenster **Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="9f252-118">If you see a **You haven't enabled device management yet** message In the **Microsoft Intune** pane, click it.</span></span> <span data-ttu-id="9f252-119">Klik in het deelvenster **Autoriteit voor mobiel apparaatbeheer** op **Intune MDM-autoriteit**en klik vervolgens op **Kiezen**.</span><span class="sxs-lookup"><span data-stu-id="9f252-119">In the **Mobile Device Management authority** pane, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="9f252-120">Vernieuw het tabblad browser.</span><span class="sxs-lookup"><span data-stu-id="9f252-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="9f252-121">Klik in het linkernavigatiedeelvenster op **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="9f252-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="9f252-122">In the **Groups-All groups** pane, click **+ New Group**.</span><span class="sxs-lookup"><span data-stu-id="9f252-122">In the **Groups-All groups** pane, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="9f252-123">Selecteer in het deelvenster **Groep** De optie **Office 365** of **Beveiliging** voor **groepstype?** typ **Gebruikers van beheerde Windows 10-apparaten** in **Naam,** selecteer **Toegewezen** in het **type Lidmaatschap**en klik op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="9f252-123">In the **Group** pane, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="9f252-124">Klik op **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="9f252-124">Click **Microsoft Intune**.</span></span> <span data-ttu-id="9f252-125">Klik in het deelvenster **Microsoft Intune** in de lijst **Snelle taken** op **Een nalevingsbeleid maken**.</span><span class="sxs-lookup"><span data-stu-id="9f252-125">In the **Microsoft Intune** pane, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
9. <span data-ttu-id="9f252-126">Klik in het deelvenster **Nalevingsbeleidsprofielen** op **Beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="9f252-126">In the **Compliance Policy Profiles** pane, click **Create Policy**.</span></span>
    
10. <span data-ttu-id="9f252-127">Typ **Windows 10**in het deelvenster **Beleid maken** in **Naam**.</span><span class="sxs-lookup"><span data-stu-id="9f252-127">In the **Create Policy** pane, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="9f252-128">Selecteer in **Platform** **Windows 10 en hoger**op **OK** In het **deelvenster Nalevingsbeleid van Windows 10** en klik vervolgens op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="9f252-128">In **Platform**, select **Windows 10 and later**, click **OK** In the **Windows 10 compliance policy** pane, and then click **Create**.</span></span> 
    
11. <span data-ttu-id="9f252-129">Klik op **Nalevingsbeleidsprofielen**en klik vervolgens op de naam **van het Windows 10-beleid.**</span><span class="sxs-lookup"><span data-stu-id="9f252-129">Click **Compliance Policy Profiles**, and then click the **Windows 10** policy name.</span></span>
    
12. <span data-ttu-id="9f252-130">Klik in het deelvenster **Windows 10** op **Toewijzingen**en klik vervolgens op **Groepen selecteren om op te nemen**.</span><span class="sxs-lookup"><span data-stu-id="9f252-130">In the **Windows 10** pane, click **Assignments**, and then click **Select groups to include**.</span></span>
    
13. <span data-ttu-id="9f252-131">Klik in het deelvenster **Groepen selecteren dat u wilt opnemen** op de groep Gebruikers van beheerd Windows **10-apparaat** en klik vervolgens op **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="9f252-131">In the **Select groups to include** pane, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
14. <span data-ttu-id="9f252-132">Klik **op Opslaan,** klik op **Microsoft Intune-Overzicht**en klik vervolgens op **Client-apps** in de linkernavigatie.</span><span class="sxs-lookup"><span data-stu-id="9f252-132">Click **Save**, click **Microsoft Intune-Overview**, and then click **Client apps** in the left navigation.</span></span>
    
15. <span data-ttu-id="9f252-133">Klik in het deelvenster **Client-apps** op **Apps**en klik vervolgens op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9f252-133">In the **Client Apps** pane, click **Apps**, and then click **Add**.</span></span> 

16. <span data-ttu-id="9f252-134">Selecteer **app-type toevoegen in** het deelvenster App toevoegen en selecteer **vervolgens Windows 10** onder **Office 365 Suite**. **App type**</span><span class="sxs-lookup"><span data-stu-id="9f252-134">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

17. <span data-ttu-id="9f252-135">Selecteer **app-suitegegevens**in het deelvenster **App** toevoegen .</span><span class="sxs-lookup"><span data-stu-id="9f252-135">In the **Add App** pane, select **App Suite Information**.</span></span>
 
18. <span data-ttu-id="9f252-136">Typ **Microsoft 365-apps voor bedrijven** in het deelvenster App **Suite** in zowel **Suite-naam** als **suitebeschrijving.**</span><span class="sxs-lookup"><span data-stu-id="9f252-136">In the **App Suite Information** pane, type **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**.</span></span>
<span data-ttu-id="9f252-137">Klik op OK.</span><span class="sxs-lookup"><span data-stu-id="9f252-137">Click OK.</span></span>

19. <span data-ttu-id="9f252-138">Selecteer **app-suite configureren**in het deelvenster **App toevoegen** en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f252-138">In the **Add App** pane, select **Configure App Suite**, and then click **OK**.</span></span>

20. <span data-ttu-id="9f252-139">Selecteer **app-suite-instellingen**in het deelvenster **App** toevoegen .</span><span class="sxs-lookup"><span data-stu-id="9f252-139">In the **Add App** pane, select **App Suite Settings**.</span></span>

21. <span data-ttu-id="9f252-140">Selecteer **voor Update-kanaal**de optie **Semijaarlijkse onderneming**en klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f252-140">For **Update Channel**, select **Semi-Annual Enterprise**, and then click **OK**.</span></span>

22. <span data-ttu-id="9f252-141">Klik **in** het deelvenster App toevoegen op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9f252-141">In the **Add app** pane, click **Add**.</span></span>

<span data-ttu-id="9f252-142">U hebt nu een beleid voor de naleving van het apparaat voor het testen van de geselecteerde apps in het nalevingsbeleid voor **Windows 10-apparaten** en voor leden van de groep Gebruikers van **beheerde Windows 10-apparaten.**</span><span class="sxs-lookup"><span data-stu-id="9f252-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="9f252-143">Houd er rekening mee dat het selecteren van Office 365 als groepstype extra bronnen maakt.</span><span class="sxs-lookup"><span data-stu-id="9f252-143">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="9f252-144">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="9f252-144">Next step</span></span>

<span data-ttu-id="9f252-145">Ontdek aanvullende functies en mogelijkheden voor het beheer van [mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="9f252-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f252-146">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9f252-146">See also</span></span>

<span data-ttu-id="9f252-147">[Microsoft 365 Enterprise Test Lab-gidsen](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="9f252-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="9f252-148">IOS- en Android-apparaten inschrijven in uw Microsoft 365 Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="9f252-148">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="9f252-149">Microsoft 365 Enterprise implementeren</span><span class="sxs-lookup"><span data-stu-id="9f252-149">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9f252-150">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="9f252-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
