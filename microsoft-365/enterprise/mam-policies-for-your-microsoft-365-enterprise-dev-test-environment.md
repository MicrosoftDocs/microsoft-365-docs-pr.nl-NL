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
ms.openlocfilehash: 3c77a7ea8ddc5120a2ce53fa0834dab213502657
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686752"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5dc85-103">Beleid voor apparaatcompatibiliteit voor uw Microsoft 365 voor Enterprise testomgeving</span><span class="sxs-lookup"><span data-stu-id="5dc85-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5dc85-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="5dc85-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="5dc85-105">Met de instructies in dit artikel voegt u het nalevingsbeleid van een intune-apparaat voor Windows 10-apparaten en Microsoft 365-apps voor Enterprise toe aan uw Microsoft 365 voor Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="5dc85-105">With the instructions in this article, you add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="5dc85-107">Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="5dc85-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5dc85-108">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="5dc85-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5dc85-109">Als u het MAM-beleid slechts op een lichte manier met de minimumvereisten wilt configureren, volgt u de instructies in de [basisconfiguratie](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="5dc85-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="5dc85-110">Als u het MAM-beleid in een gesimuleerde Enterprise wilt configureren, volgt u de instructies in [Pass-to-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="5dc85-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5dc85-111">Voor het testen van de geautomatiseerde licentie-en groepslidmaatschappen is de gesimuleerde Enterprise testomgeving niet vereist, waaronder een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest.</span><span class="sxs-lookup"><span data-stu-id="5dc85-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="5dc85-112">U kunt dit hier opgeven als optie, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="5dc85-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="5dc85-113">Fase 2: een beleid voor naleving van apparaten maken voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="5dc85-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="5dc85-114">In deze fase maakt u een beleid voor naleving van apparaten voor Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="5dc85-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="5dc85-115">Ga naar het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) , Meld u aan bij uw microsoft 365-test abonnement met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="5dc85-115">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="5dc85-116">Open de Azure-Portal op een nieuw tabblad van uw browser [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="5dc85-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="5dc85-117">Ga naar het tabblad Azure Portal in uw browser, typ **intune** in het zoekvak en klik vervolgens op **intune**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-117">From the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="5dc85-118">Als u in het **Microsoft intune** -venster geen optie voor **Apparaatbeheer hebt ingeschakeld** , klikt u erop.</span><span class="sxs-lookup"><span data-stu-id="5dc85-118">If you see a **You haven't enabled device management yet** message In the **Microsoft Intune** pane, click it.</span></span> <span data-ttu-id="5dc85-119">Klik in het deelvenster voor het **beheer van mobiele apparaten** op **intune MDM-autoriteit**en klik vervolgens op **kiezen**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-119">In the **Mobile Device Management authority** pane, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="5dc85-120">Vernieuw het tabblad browser.</span><span class="sxs-lookup"><span data-stu-id="5dc85-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="5dc85-121">Klik in het linker navigatiedeelvenster op **groepen**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="5dc85-122">Klik in het deelvenster **groepen-alle groepen** op **+ nieuwe groep**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-122">In the **Groups-All groups** pane, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="5dc85-123">Selecteer in het deelvenster **groep** de tekst **Microsoft 365** of **beveiliging** voor **groepstype?**, typ **beheerd Windows 10-apparaat gebruikers** in **naam**, selecteer **toegewezen aan** **lidmaatschaps type**en klik vervolgens op **maken**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-123">In the **Group** pane, select **Microsoft 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="5dc85-124">Klik op **Microsoft intune**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-124">Click **Microsoft Intune**.</span></span> <span data-ttu-id="5dc85-125">Klik in het deelvenster **Microsoft intune** in de lijst **snelle taken** op **een nalevingsbeleid maken**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-125">In the **Microsoft Intune** pane, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
9. <span data-ttu-id="5dc85-126">Klik in het deelvenster **profielen voor nalevingsbeleid** op **beleid maken**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-126">In the **Compliance Policy Profiles** pane, click **Create Policy**.</span></span>
    
10. <span data-ttu-id="5dc85-127">Typ **Windows 10**in het deelvenster **beleid maken** onder **naam**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-127">In the **Create Policy** pane, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="5dc85-128">In **platform**selecteert u **Windows 10 en hoger**, klikt u op **OK** in het venster **Windows 10-nalevingsbeleid** en vervolgens op **maken**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-128">In **Platform**, select **Windows 10 and later**, click **OK** In the **Windows 10 compliance policy** pane, and then click **Create**.</span></span> 
    
11. <span data-ttu-id="5dc85-129">Klik op **profielen voor nalevingsbeleid**en klik vervolgens op de naam van het **Windows 10** -beleid.</span><span class="sxs-lookup"><span data-stu-id="5dc85-129">Click **Compliance Policy Profiles**, and then click the **Windows 10** policy name.</span></span>
    
12. <span data-ttu-id="5dc85-130">Klik in het deelvenster **Windows 10** op **opdrachten**en vervolgens op **groepen selecteren om op te nemen**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-130">In the **Windows 10** pane, click **Assignments**, and then click **Select groups to include**.</span></span>
    
13. <span data-ttu-id="5dc85-131">Klik in het deelvenster **groepen selecteren om** op te nemen op de groep gebruikers van de **beheerde Windows 10-apparaten** en klik vervolgens op **selecteren**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-131">In the **Select groups to include** pane, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
14. <span data-ttu-id="5dc85-132">Klik achtereenvolgens op **Opslaan**, **Microsoft intune-overzicht**en **client toepassingen** in de linkernavigatiebalk.</span><span class="sxs-lookup"><span data-stu-id="5dc85-132">Click **Save**, click **Microsoft Intune-Overview**, and then click **Client apps** in the left navigation.</span></span>
    
15. <span data-ttu-id="5dc85-133">Klik in het deelvenster **client toepassingen** op **apps**en klik vervolgens op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-133">In the **Client Apps** pane, click **Apps**, and then click **Add**.</span></span> 

16. <span data-ttu-id="5dc85-134">Selecteer in het deelvenster **app toevoegen** de optie **app-type**en selecteer vervolgens **Windows 10** onder **Microsoft 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-134">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Microsoft 365 Suite**.</span></span>

17. <span data-ttu-id="5dc85-135">Selecteer in het deelvenster **app toevoegen** de gegevens van de **app-Suite**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-135">In the **Add App** pane, select **App Suite Information**.</span></span>
 
18. <span data-ttu-id="5dc85-136">Typ in het deelvenster **gegevens van app-Suite** **Microsoft 365-apps for Enterprise** in **naam van Suite** en **Suite-beschrijving**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-136">In the **App Suite Information** pane, type **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**.</span></span>
<span data-ttu-id="5dc85-137">Klik op OK.</span><span class="sxs-lookup"><span data-stu-id="5dc85-137">Click OK.</span></span>

19. <span data-ttu-id="5dc85-138">Selecteer in het deelvenster **app toevoegen** de optie **app-Suite configureren**en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-138">In the **Add App** pane, select **Configure App Suite**, and then click **OK**.</span></span>

20. <span data-ttu-id="5dc85-139">Selecteer **app Suite-instellingen**in het deelvenster **app toevoegen** .</span><span class="sxs-lookup"><span data-stu-id="5dc85-139">In the **Add App** pane, select **App Suite Settings**.</span></span>

21. <span data-ttu-id="5dc85-140">Selecteer voor **Update kanaal**de optie **Semi-Annual Enterprise**en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-140">For **Update Channel**, select **Semi-Annual Enterprise**, and then click **OK**.</span></span>

22. <span data-ttu-id="5dc85-141">Klik in het deelvenster **app toevoegen** op **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="5dc85-141">In the **Add app** pane, click **Add**.</span></span>

<span data-ttu-id="5dc85-142">U beschikt nu over een apparaatcompatibiliteit voor het testen van de geselecteerde apps in het nalevingsbeleid voor **Windows 10** -apparaten en de leden van de groep gebruikers van de **beheerde Windows 10-apparaat** .</span><span class="sxs-lookup"><span data-stu-id="5dc85-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="5dc85-143">Houd er rekening mee dat Microsoft 365 wordt geselecteerd als groepstype, om aanvullende bronnen te maken.</span><span class="sxs-lookup"><span data-stu-id="5dc85-143">Please note that selecting Microsoft 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="5dc85-144">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="5dc85-144">Next step</span></span>

<span data-ttu-id="5dc85-145">Verken de extra functies en mogelijkheden van het [beheer van mobiele apparaten](m365-enterprise-test-lab-guides.md#mobile-device-management) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="5dc85-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5dc85-146">Zie ook</span><span class="sxs-lookup"><span data-stu-id="5dc85-146">See also</span></span>

<span data-ttu-id="5dc85-147">[Proefversie van Microsoft 365 voor Enterprise test lab](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="5dc85-147">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="5dc85-148">IOS-en Android-apparaten registreren in uw Microsoft 365 voor Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="5dc85-148">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="5dc85-149">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="5dc85-149">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5dc85-150">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="5dc85-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
