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
ms.openlocfilehash: fff09ca41ff0b648d46b5c33f753affc01242264
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695180"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ae498-103">Algemene beheerdersaccounts in uw Microsoft 365 voor Enterprise testomgeving beschermen</span><span class="sxs-lookup"><span data-stu-id="ae498-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ae498-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="ae498-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="ae498-105">U kunt digitale aanvallen van uw organisatie voorkomen door ervoor te zorgen dat uw beheerdersaccounts zo veilig mogelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="ae498-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="ae498-106">In dit artikel wordt uitgelegd hoe u een beleid voor voorwaardelijke toegang van Azure Active Directory (Azure AD) gebruikt om algemene beheerdersaccounts te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="ae498-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="ae498-107">Er zijn twee fasen voor het beschermen van globale beheerdersaccounts in uw Microsoft 365 voor Enterprise testomgeving:</span><span class="sxs-lookup"><span data-stu-id="ae498-107">There are two phases to protecting global administrator accounts in your Microsoft 365 for enterprise test environment:</span></span>

1.  <span data-ttu-id="ae498-108">Maak de testomgeving Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ae498-108">Create the Microsoft 365 for enterprise test environment.</span></span>
2.  <span data-ttu-id="ae498-109">Beveilig uw eigen account voor globale beheerders.</span><span class="sxs-lookup"><span data-stu-id="ae498-109">Protect your dedicated global administrator account.</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="ae498-111">Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="ae498-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ae498-112">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="ae498-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ae498-113">Als u alleen de beveiliging van het account van de globale beheerder op een lichte manier wilt testen met de minimumvereisten, volgt u de instructies in de [basisconfiguratie](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="ae498-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ae498-114">Als u de bescherming van een account van een globale beheerder in een gesimuleerde onderneming wilt testen, volgt u de instructies in de [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="ae498-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae498-115">Voor het testen van de beveiliging van het account van een globale beheerder is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="ae498-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="ae498-116">U kunt dit hier als optie gebruiken, zodat u de beveiliging van het account van een globale beheerder kunt testen en een dergelijk account kunt gebruiken in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="ae498-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="ae498-117">Fase 2: voorwaardelijke toegangsbeleid configureren</span><span class="sxs-lookup"><span data-stu-id="ae498-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="ae498-118">Maak eerst een nieuw gebruikersaccount als een speciale globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="ae498-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="ae498-119">Open het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/)op een apart tabblad.</span><span class="sxs-lookup"><span data-stu-id="ae498-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="ae498-120">Klik op **gebruikers > actieve gebruikers**en klik vervolgens op **een gebruiker toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="ae498-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="ae498-121">Typ in het deelvenster **gebruiker toevoegen** **DedicatedAdmin** in **voornaam**, **weergavenaam**en **gebruikersnaam**.</span><span class="sxs-lookup"><span data-stu-id="ae498-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="ae498-122">Klik op **wachtwoord**, klik op **Ik wil het wachtwoord maken**en typ vervolgens een sterk wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="ae498-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="ae498-123">Neem het wachtwoord van dit nieuwe account op een veilige locatie op.</span><span class="sxs-lookup"><span data-stu-id="ae498-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="ae498-124">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae498-124">Click **Next**.</span></span>
6. <span data-ttu-id="ae498-125">Selecteer in het deelvenster **productlicenties toewijzen** de optie **Microsoft 365 E5**en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae498-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="ae498-126">Klik in het deelvenster **optionele instellingen** op **rollen**en selecteer vervolgens **toegangsbeheer centrum** en **globale beheerder**. Klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae498-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="ae498-127">Klik in het deelvenster **u bent bijna klaar** op **toevoegen voltooien**en klik vervolgens op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="ae498-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="ae498-128">Vervolgens maakt u een nieuwe groep met de naam GlobalAdmins en voegt u het DedicatedAdmin-account toe.</span><span class="sxs-lookup"><span data-stu-id="ae498-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="ae498-129">Ga naar het tabblad **Microsoft 365-Beheercentrum** , klik in het linker navigatiemenu op **groepen** en klik vervolgens op **groepen**.</span><span class="sxs-lookup"><span data-stu-id="ae498-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="ae498-130">Klik op **groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="ae498-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="ae498-131">Selecteer in het deelvenster **een groepstype kiezen** de optie **beveiliging**en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae498-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="ae498-132">Klik in het deelvenster **basisbeginselen instellen** op **groep maken**en klik vervolgens op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="ae498-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="ae498-133">In het deelvenster **groep controleren en voltooien** , typt u **GlobalAdmins**en klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="ae498-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="ae498-134">Klik in de lijst met groepen op de groep **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="ae498-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="ae498-135">Klik in het deelvenster **GlobalAdmins** op **leden**en klik op **AllesWeergeven en leden beheren**.</span><span class="sxs-lookup"><span data-stu-id="ae498-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="ae498-136">Klik in het deelvenster **GlobalAdmins** op **leden toevoegen**, selecteer het **DedicatedAdmin** -account en het account van de globale beheerder en klik vervolgens op **Opslaan > sluiten > sluiten**.</span><span class="sxs-lookup"><span data-stu-id="ae498-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="ae498-137">Vervolgens maakt u een beleid voor voorwaardelijke toegang voor de authenticatie van meervoudige beheerders, en om authenticatie te weigeren als het registratie risico normaal of hoog is.</span><span class="sxs-lookup"><span data-stu-id="ae498-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="ae498-138">Voor dit eerste beleid moet u alle globale-beheerdersaccounts gebruikmaken van MFA.</span><span class="sxs-lookup"><span data-stu-id="ae498-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="ae498-139">Ga op een nieuw tabblad van uw browser naar [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="ae498-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="ae498-140">Klik **> beveiligings > voorwaardelijke toegang op Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="ae498-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="ae498-141">Klik in het deelvenster **voorwaardelijke toegang-beleidsregels** op **basislijn-beleid: MFA vereisen voor beheerders (preview)**.</span><span class="sxs-lookup"><span data-stu-id="ae498-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="ae498-142">Klik in het deelvenster **basislijn beleidsregels** **direct op beleid gebruiken > opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ae498-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="ae498-143">Met dit tweede beleid wordt de toegang tot de accountverificatie van het globale beheerder blokkeren wanneer het aanmeldings risico normaal of hoog is.</span><span class="sxs-lookup"><span data-stu-id="ae498-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="ae498-144">Klik in het deelvenster **voorwaardelijke toegang – beleidsregels** op **Nieuw beleid**.</span><span class="sxs-lookup"><span data-stu-id="ae498-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="ae498-145">Typ in het **nieuwe** deelvenster de naam van een **globale beheerder** in de **naam**.</span><span class="sxs-lookup"><span data-stu-id="ae498-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="ae498-146">Klik in de sectie **opdrachten** op **gebruikers en groepen**.</span><span class="sxs-lookup"><span data-stu-id="ae498-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="ae498-147">Klik op het tabblad **opnemen** van het deelvenster **gebruikers en groepen** op **gebruikers en groepen > gebruikers en groepen selecteren > selecteren**.</span><span class="sxs-lookup"><span data-stu-id="ae498-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="ae498-148">Klik in het **selectie** deelvenster op de groep **GlobalAdmins** en klik vervolgens op **selecteren > gereed**.</span><span class="sxs-lookup"><span data-stu-id="ae498-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="ae498-149">Klik in de sectie **opdrachten** op **voorwaarden**.</span><span class="sxs-lookup"><span data-stu-id="ae498-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="ae498-150">Klik in het deelvenster **voorwaarden** op **aanmeld risico**, klik op **Ja** voor **configureren**, klik op **hoog** en **normaal**en klik vervolgens op **selecteren** en **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="ae498-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="ae498-151">Klik in de sectie **Access-besturingselementen** van het **nieuwe** deelvenster op **toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="ae498-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="ae498-152">Klik in het deelvenster **subsidie** op **toegang blokkeren**en klik vervolgens op **selecteren**.</span><span class="sxs-lookup"><span data-stu-id="ae498-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="ae498-153">Klik in het **nieuwe** deelvenster op **aan** voor inschakelen van het **beleid**en klik vervolgens op **maken**.</span><span class="sxs-lookup"><span data-stu-id="ae498-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="ae498-154">Sluit de tabbladen **Azure Portal** en **Microsoft 365-Beheercentrum** .</span><span class="sxs-lookup"><span data-stu-id="ae498-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="ae498-155">Als u het eerste beleid wilt testen, meldt u zich af en meldt u zich aan met het DedicatedAdmin-account.</span><span class="sxs-lookup"><span data-stu-id="ae498-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="ae498-156">U wordt gevraagd MFA te configureren.</span><span class="sxs-lookup"><span data-stu-id="ae498-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="ae498-157">Dit toont het toepassen van het eerste beleid.</span><span class="sxs-lookup"><span data-stu-id="ae498-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="ae498-158">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="ae498-158">Next step</span></span>

<span data-ttu-id="ae498-159">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="ae498-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae498-160">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ae498-160">See also</span></span>

[<span data-ttu-id="ae498-161">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="ae498-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="ae498-162">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="ae498-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ae498-163">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="ae498-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ae498-164">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="ae498-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
