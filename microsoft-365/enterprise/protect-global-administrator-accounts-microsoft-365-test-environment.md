---
title: Wereldwijde beheerdersaccounts beveiligen in uw Microsoft 365 Enterprise-testomgeving
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
description: Gebruik deze stappen om globale beheerdersaccounts in uw Microsoft 365 Enterprise-testomgeving te beschermen.
ms.openlocfilehash: 9452ac7bafec416833ece9cbcb645bd7eeee21cc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810402"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d803a-103">Wereldwijde beheerdersaccounts beveiligen in uw Microsoft 365 Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="d803a-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d803a-104">*Deze Test Lab Guide kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="d803a-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="d803a-105">U digitale aanvallen op uw organisatie voorkomen door ervoor te zorgen dat uw beheerdersaccounts zo veilig mogelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="d803a-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="d803a-106">In dit artikel wordt beschreven hoe u azure Active Directory (Azure AD) voorwaardelijke toegangsbeleid (Azure AD) gebruikt om globale beheerdersaccounts te beschermen.</span><span class="sxs-lookup"><span data-stu-id="d803a-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="d803a-107">Er zijn twee fasen om globale beheerdersaccounts in uw Microsoft 365 Enterprise-testomgeving te beschermen:</span><span class="sxs-lookup"><span data-stu-id="d803a-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="d803a-108">Maak de Microsoft 365 Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="d803a-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="d803a-109">Bescherm uw speciale wereldwijde beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="d803a-109">Protect your dedicated global administrator account.</span></span>

![Test Lab-hulplijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="d803a-111">Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.</span><span class="sxs-lookup"><span data-stu-id="d803a-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d803a-112">Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen</span><span class="sxs-lookup"><span data-stu-id="d803a-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d803a-113">Als u alleen de beveiliging van het wereldwijde beheerdersaccount op een lichtgewicht manier wilt testen met de minimumvereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="d803a-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d803a-114">Als u de beveiliging van een globale beheerdersaccount wilt testen in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d803a-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d803a-115">Voor het testen van globale beheerdersaccountbeveiliging is niet de gesimuleerde bedrijfstestomgeving vereist, die een gesimuleerd intranet bevat dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="d803a-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="d803a-116">Het wordt hier als optie geleverd, zodat u de beveiliging van het wereldwijde beheerdersaccount testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="d803a-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="d803a-117">Fase 2: Beleid voor voorwaardelijke toegang configureren</span><span class="sxs-lookup"><span data-stu-id="d803a-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="d803a-118">Maak eerst een nieuw gebruikersaccount als een speciale globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="d803a-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="d803a-119">Open op een apart tabblad het [Microsoft 365-beheercentrum](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="d803a-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="d803a-120">Klik op **Gebruikers > Actieve gebruikers**en klik vervolgens op Een gebruiker **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d803a-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="d803a-121">Typ In het **gebruikersvenster Toevoegen** **DedicatedAdmin** in **voornaam,** **weergavenaam**en **gebruikersnaam**.</span><span class="sxs-lookup"><span data-stu-id="d803a-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="d803a-122">Klik op **Wachtwoord,** klik op **Laat me het wachtwoord maken**en typ een sterk wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="d803a-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="d803a-123">Neem het wachtwoord voor dit nieuwe account op een veilige locatie op.</span><span class="sxs-lookup"><span data-stu-id="d803a-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="d803a-124">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d803a-124">Click **Next**.</span></span>
6. <span data-ttu-id="d803a-125">Selecteer in het deelvenster **Productlicenties toewijzen** de optie **Microsoft 365 E5** of **Office 365 E5**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d803a-125">In the **Assign product licenses** pane, select **Microsoft 365 E5** or **Office 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="d803a-126">Klik in het deelvenster **Optionele instellingen** op **Rollen**en selecteer vervolgens toegang **tot beheercentrum** en **globale beheerder**. Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d803a-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="d803a-127">Klik in het deelvenster **U bijna klaar** op Toevoegen **voltooien**en klik vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="d803a-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="d803a-128">Maak vervolgens een nieuwe groep met de naam GlobalAdmins en voeg er het DedicatedAdmin-account aan toe.</span><span class="sxs-lookup"><span data-stu-id="d803a-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="d803a-129">Klik op het tabblad **Microsoft 365-beheercentrum** op **Groepen** in de linkernavigatie en klik vervolgens op **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="d803a-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="d803a-130">Klik op **Een groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d803a-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="d803a-131">Selecteer **Beveiliging**in het deelvenster **Een groepstype kiezen** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d803a-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="d803a-132">Klik in het deelvenster **Basisinstellingen** op **Groep maken**en klik vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="d803a-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="d803a-133">Typ **GlobalAdmins**in het **deelvenster Controleren en voltooien** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="d803a-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="d803a-134">Klik in de lijst met groepen op de groep **GlobalAdmins.**</span><span class="sxs-lookup"><span data-stu-id="d803a-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="d803a-135">Klik in het deelvenster **Globalebeheerders** op **Leden**en klik vervolgens op **Alle weergeven en leden beheren**.</span><span class="sxs-lookup"><span data-stu-id="d803a-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="d803a-136">Klik in het deelvenster **Globalebeheerders** op **Leden toevoegen,** selecteer het **DedicatedAdmin-account** en uw globale beheerdersaccount en klik vervolgens op **Opslaan > sluiten > sluiten**.</span><span class="sxs-lookup"><span data-stu-id="d803a-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="d803a-137">Maak vervolgens een beleid voor voorwaardelijke toegang om meervoudige verificatie voor globale beheerdersaccounts te vereisen en om verificatie te weigeren als het aanmeldingsrisico gemiddeld of hoog is.</span><span class="sxs-lookup"><span data-stu-id="d803a-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="d803a-138">Dit eerste beleid vereist dat alle globale beheerdersaccounts MFA gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d803a-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="d803a-139">Ga in een nieuw tabblad [https://portal.azure.com](https://portal.azure.com)van uw browser naar .</span><span class="sxs-lookup"><span data-stu-id="d803a-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="d803a-140">Klik **op Azure Active Directory > Beveiliging > voorwaardelijke toegang**.</span><span class="sxs-lookup"><span data-stu-id="d803a-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="d803a-141">Klik in het deelvenster **Voorwaardelijke toegang – Beleid** op Beleid **basislijn: MFA vereisen voor beheerders (voorbeeld).**</span><span class="sxs-lookup"><span data-stu-id="d803a-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="d803a-142">Klik in het deelvenster **Beleid basislijn** op Beleid gebruiken **> Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d803a-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="d803a-143">Dit tweede beleid blokkeert de toegang tot globale verificatie van beheerdersaccount wanneer het aanmeldingsrisico gemiddeld of hoog is.</span><span class="sxs-lookup"><span data-stu-id="d803a-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="d803a-144">Klik in het deelvenster **Voorwaardelijke toegang – Beleid** op Nieuw **beleid**.</span><span class="sxs-lookup"><span data-stu-id="d803a-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="d803a-145">Typ in het deelvenster **Nieuw** **Globale beheerders** in **Naam**.</span><span class="sxs-lookup"><span data-stu-id="d803a-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="d803a-146">Klik in de sectie **Toewijzingen** op **Gebruikers en groepen**.</span><span class="sxs-lookup"><span data-stu-id="d803a-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="d803a-147">Klik op het tabblad **Opnemen** van het deelvenster **Gebruikers en groepen** op Gebruikers selecteren en groepen > gebruikers en groepen > **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="d803a-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="d803a-148">Klik in het deelvenster **Selecteren** op de groep **Globalebeheerders** en klik vervolgens op **Selecteren > gedaan**.</span><span class="sxs-lookup"><span data-stu-id="d803a-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="d803a-149">Klik in de sectie **Toewijzingen** op **Voorwaarden**.</span><span class="sxs-lookup"><span data-stu-id="d803a-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="d803a-150">Klik in het deelvenster **Voorwaarden** op **Aanmeldingsrisico,** klik op **Ja** voor **Configureren**, klik op **Hoog** en **Gemiddeld**en klik vervolgens op **Selecteren** en **klaar**.</span><span class="sxs-lookup"><span data-stu-id="d803a-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="d803a-151">Klik in het gedeelte **Besturingselementen voor toegang** in het deelvenster **Nieuw** op **Grant**.</span><span class="sxs-lookup"><span data-stu-id="d803a-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="d803a-152">Klik in het **deelvenster Subsidie** op **Toegang blokkeren**en klik vervolgens op **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="d803a-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="d803a-153">Klik in het deelvenster **Nieuw** op **Aan** voor **Beleid inschakelen**en klik vervolgens op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="d803a-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="d803a-154">Sluit de tabbladen **Azure-portal** en **Microsoft 365-beheercentrum.**</span><span class="sxs-lookup"><span data-stu-id="d803a-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="d803a-155">Als u het eerste beleid wilt testen, meldt u zich af en meldt u zich af met het DedicatedAdmin-account.</span><span class="sxs-lookup"><span data-stu-id="d803a-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="d803a-156">U moet worden gevraagd mfa te configureren.</span><span class="sxs-lookup"><span data-stu-id="d803a-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="d803a-157">Hieruit blijkt dat het eerste beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="d803a-157">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="d803a-158">Bekijk de stap [Voor wereldwijde beheerdersaccounts beveiligen](identity-create-protect-global-admins.md#identity-global-admin) in de identiteitsfase voor informatie en koppelingen om uw wereldwijde beheerdersaccounts in productie te beschermen.</span><span class="sxs-lookup"><span data-stu-id="d803a-158">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="d803a-159">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="d803a-159">Next step</span></span>

<span data-ttu-id="d803a-160">Ontdek extra [identiteitsfuncties](m365-enterprise-test-lab-guides.md#identity) en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="d803a-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d803a-161">Zie ook</span><span class="sxs-lookup"><span data-stu-id="d803a-161">See also</span></span>

[<span data-ttu-id="d803a-162">Fase 2: Identiteit</span><span class="sxs-lookup"><span data-stu-id="d803a-162">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="d803a-163">Microsoft 365 Enterprise Test Lab-handleidingen</span><span class="sxs-lookup"><span data-stu-id="d803a-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d803a-164">Microsoft 365 Enterprise-implementatie</span><span class="sxs-lookup"><span data-stu-id="d803a-164">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d803a-165">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="d803a-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
