---
title: Algemene beheerdersaccounts in uw Microsoft 365 voor Enterprise testomgeving beschermen
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Volg deze stappen voor het beveiligen van globale beheerdersaccounts in uw Microsoft 365 voor Enterprise test-omgeving.
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487634"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d1024-103">Algemene beheerdersaccounts in uw Microsoft 365 voor Enterprise testomgeving beschermen</span><span class="sxs-lookup"><span data-stu-id="d1024-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d1024-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="d1024-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="d1024-105">U kunt digitale aanvallen van uw organisatie voorkomen door ervoor te zorgen dat uw beheerdersaccounts zo veilig mogelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="d1024-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="d1024-106">In dit artikel wordt uitgelegd hoe u een beleid voor voorwaardelijke toegang van Azure Active Directory (Azure AD) gebruikt om algemene beheerdersaccounts te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="d1024-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="d1024-107">Het beveiligen van globale beheerdersaccounts in uw Microsoft 365 voor Enterprise-testomgeving bestaat uit twee fasen:</span><span class="sxs-lookup"><span data-stu-id="d1024-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="d1024-108">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="d1024-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="d1024-109">Fase 2: voorwaardelijke toegangsbeleid configureren</span><span class="sxs-lookup"><span data-stu-id="d1024-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="d1024-111">Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.</span><span class="sxs-lookup"><span data-stu-id="d1024-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d1024-112">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="d1024-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d1024-113">Als u de beveiliging van het account van de globale beheerder op een lichte manier wilt testen aan de minimumvereisten, volgt u de instructies in de [basisconfiguratie](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d1024-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d1024-114">Als u de bescherming van een account van een globale beheerder in een gesimuleerde onderneming wilt testen, volgt u de instructies in de [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d1024-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1024-115">Voor het testen van de beveiliging van het account van een globale beheerder is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="d1024-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="d1024-116">U kunt dit hier als optie gebruiken, zodat u de beveiliging van het account van een globale beheerder kunt testen en een dergelijk account kunt gebruiken in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="d1024-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="d1024-117">Fase 2: voorwaardelijke toegangsbeleid configureren</span><span class="sxs-lookup"><span data-stu-id="d1024-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="d1024-118">Maak eerst een nieuw gebruikersaccount als een speciale globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="d1024-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="d1024-119">Open het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/)op een apart tabblad.</span><span class="sxs-lookup"><span data-stu-id="d1024-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="d1024-120">Selecteer **gebruikers**  >  **actieve gebruikers**en selecteer vervolgens **een gebruiker toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d1024-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="d1024-121">Voer in het deelvenster **gebruiker toevoegen** **DedicatedAdmin** in de vakken **voornaam**, **weergavenaam**en **gebruikersnaam** in.</span><span class="sxs-lookup"><span data-stu-id="d1024-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="d1024-122">Selecteer **wachtwoord**, selecteer **Ik wil het wachtwoord maken**en voer vervolgens een sterk wachtwoord in.</span><span class="sxs-lookup"><span data-stu-id="d1024-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="d1024-123">Neem het wachtwoord van dit nieuwe account op een veilige locatie op.</span><span class="sxs-lookup"><span data-stu-id="d1024-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="d1024-124">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d1024-124">Select **Next**.</span></span>
6. <span data-ttu-id="d1024-125">Selecteer in het deelvenster **productlicenties toewijzen** de optie **Microsoft 365 E5**en selecteer vervolgens **volgende**.</span><span class="sxs-lookup"><span data-stu-id="d1024-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="d1024-126">Selecteer in het deelvenster **optionele instellingen** de optie globale beheerder voor **rollen**van  >  **Beheercentrum**  >  **Global admin**  >  **Next**.</span><span class="sxs-lookup"><span data-stu-id="d1024-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="d1024-127">Selecteer in het deelvenster **u bent bijna klaar** de optie **toevoeging voltooien**en selecteer vervolgens **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="d1024-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="d1024-128">Vervolgens maakt u een nieuwe groep met de naam GlobalAdmins en voegt u het DedicatedAdmin-account toe.</span><span class="sxs-lookup"><span data-stu-id="d1024-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="d1024-129">Ga naar het tabblad **Microsoft 365-Beheercentrum** , selecteer **groepen** in het linker navigatieonderdeel en selecteer **groepen**.</span><span class="sxs-lookup"><span data-stu-id="d1024-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="d1024-130">Selecteer **een groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d1024-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="d1024-131">Selecteer in het deelvenster **een groepstype kiezen** de optie **beveiliging**en selecteer vervolgens **volgende**.</span><span class="sxs-lookup"><span data-stu-id="d1024-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="d1024-132">Selecteer **groep maken**in het deelvenster **basisbeginselen instellen** en selecteer vervolgens **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="d1024-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="d1024-133">Voer in het deelvenster **groep toevoegen en voltooien** **GlobalAdmins**in en selecteer vervolgens **volgende**.</span><span class="sxs-lookup"><span data-stu-id="d1024-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="d1024-134">Selecteer in de lijst met groepen de groep **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="d1024-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="d1024-135">Selecteer **leden**in het **GlobalAdmins** -deelvenster en selecteer vervolgens **AllesWeergeven en leden beheren**.</span><span class="sxs-lookup"><span data-stu-id="d1024-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="d1024-136">Selecteer **leden toevoegen**in het deelvenster **GlobalAdmins** , selecteer het **DedicatedAdmin** -account en uw globale beheerdersaccount **en selecteer vervolgens sluiten**  >  **sluiten**  >  **Close**.</span><span class="sxs-lookup"><span data-stu-id="d1024-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="d1024-137">Vervolgens maakt u beleidsregels voor voorwaardelijke toegang zodat u meervoudige verificatie voor algemene beheerdersaccounts en authenticatie weigert als het gebruik van het risico normaal of hoog is.</span><span class="sxs-lookup"><span data-stu-id="d1024-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="d1024-138">Voor dit eerste beleid moet u alle globale-beheerdersaccounts gebruikmaken van MFA.</span><span class="sxs-lookup"><span data-stu-id="d1024-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="d1024-139">Ga op een nieuw tabblad van uw browser naar [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="d1024-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="d1024-140">Klik op de voorwaardelijke toegang van **Azure Active Directory**-  >  **beveiliging**  >  **Conditional Access**.</span><span class="sxs-lookup"><span data-stu-id="d1024-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="d1024-141">Selecteer in het deelvenster **voorwaardelijke toegang – beleidsregels** de optie **basisbeleid: MFA vereisen voor beheerders (preview)**.</span><span class="sxs-lookup"><span data-stu-id="d1024-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="d1024-142">Selecteer in het deelvenster **basislijn beleidsregels** de optie **beleid direct gebruiken > opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d1024-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="d1024-143">Met dit tweede beleid wordt de toegang tot de accountverificatie van het globale beheerder blokkeren wanneer het aanmeldings risico normaal of hoog is.</span><span class="sxs-lookup"><span data-stu-id="d1024-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="d1024-144">Selecteer in het deelvenster **voorwaardelijke toegang – beleidsregels** de optie **nieuwe beleids**optie.</span><span class="sxs-lookup"><span data-stu-id="d1024-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="d1024-145">Voer in het **nieuwe** deelvenster **globale beheerders** **naam**in.</span><span class="sxs-lookup"><span data-stu-id="d1024-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="d1024-146">Selecteer in de sectie **opdrachten** de optie **gebruikers en groepen**.</span><span class="sxs-lookup"><span data-stu-id="d1024-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="d1024-147">Selecteer op het tabblad **opnemen** van het deelvenster **gebruikers en groepen** de optie **gebruikers en groepen**  >  **gebruikers en groepen**  >  **selecteren**.</span><span class="sxs-lookup"><span data-stu-id="d1024-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="d1024-148">In het **selectie** deelvenster selecteert u de groep **GlobalAdmins** **en selecteert u**vervolgens  >  **gereed**.</span><span class="sxs-lookup"><span data-stu-id="d1024-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="d1024-149">Selecteer in de sectie **opdrachten** de optie **voorwaarden**.</span><span class="sxs-lookup"><span data-stu-id="d1024-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="d1024-150">Selecteer in het deelvenster **voorwaarden** de optie **Aanmelden**, selecteer **Ja** voor **configureren**, selecteer **hoog** en **normaal**en selecteer vervolgens **selecteren** en **gereed**.</span><span class="sxs-lookup"><span data-stu-id="d1024-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="d1024-151">Selecteer in de sectie **Access-besturingselementen** van het **nieuwe** deelvenster de optie **verlenen**.</span><span class="sxs-lookup"><span data-stu-id="d1024-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="d1024-152">Selecteer in het deelvenster **verlenen** de optie **toegang blokkeren**en selecteer vervolgens **selecteren**.</span><span class="sxs-lookup"><span data-stu-id="d1024-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="d1024-153">Selecteer **in het** deelvenster **Nieuw** de optie inschakelen voor **beleidsinstelling**en selecteer **maken**.</span><span class="sxs-lookup"><span data-stu-id="d1024-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="d1024-154">Sluit de tabbladen **Azure Portal** en **Microsoft 365-Beheercentrum** .</span><span class="sxs-lookup"><span data-stu-id="d1024-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="d1024-155">Als u het eerste beleid wilt testen, meldt u zich af en meldt u zich aan met het DedicatedAdmin-account.</span><span class="sxs-lookup"><span data-stu-id="d1024-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="d1024-156">U wordt gevraagd MFA te configureren.</span><span class="sxs-lookup"><span data-stu-id="d1024-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="d1024-157">Dit toont het toepassen van het eerste beleid.</span><span class="sxs-lookup"><span data-stu-id="d1024-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="d1024-158">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="d1024-158">Next step</span></span>

<span data-ttu-id="d1024-159">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="d1024-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1024-160">Zie ook</span><span class="sxs-lookup"><span data-stu-id="d1024-160">See also</span></span>

[<span data-ttu-id="d1024-161">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="d1024-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="d1024-162">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="d1024-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d1024-163">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="d1024-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d1024-164">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="d1024-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
