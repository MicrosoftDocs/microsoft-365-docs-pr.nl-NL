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
description: Gebruik deze stappen om wereldwijde beheerdersaccounts in uw Microsoft 365 Enterprise-testomgeving te beschermen.
ms.openlocfilehash: e6b93e3888873b6d78fec1802d179ed9624ffa63
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153866"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6d20f-103">Wereldwijde beheerdersaccounts beveiligen in uw Microsoft 365 Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="6d20f-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6d20f-104">*Deze testlabrichtlijn kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="6d20f-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="6d20f-105">U digitale aanvallen op uw organisatie voorkomen door ervoor te zorgen dat uw beheerdersaccounts zo veilig mogelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="6d20f-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="6d20f-106">In dit artikel wordt beschreven hoe u azure active directory -beleid (Azure AD) voorwaardelijke toegang gebruikt om globale beheerdersaccounts te beschermen.</span><span class="sxs-lookup"><span data-stu-id="6d20f-106">This article describes how to use Azure Active Directory (Azure AD) Conditional Access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="6d20f-107">Er zijn twee fasen voor het beveiligen van algemene beheerdersaccounts in uw Microsoft 365 Enterprise-testomgeving:</span><span class="sxs-lookup"><span data-stu-id="6d20f-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="6d20f-108">Maak de Microsoft 365 Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="6d20f-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="6d20f-109">Bescherm uw toegewijde wereldwijde beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="6d20f-109">Protect your dedicated global administrator account.</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="6d20f-111">Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen over de Microsoft 365 Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="6d20f-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6d20f-112">Fase 1: uw Microsoft 365 Enterprise-testomgeving uitbouwen</span><span class="sxs-lookup"><span data-stu-id="6d20f-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6d20f-113">Als u alleen de bescherming van wereldwijde beheerdersaccount op een lichtgewicht manier wilt testen met de minimale vereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="6d20f-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6d20f-114">Als u de bescherming van globale beheerdersaccount in een gesimuleerde onderneming wilt testen, volgt u de instructies in [pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="6d20f-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6d20f-115">Voor het testen van de globale beheerdersaccountbeveiliging is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="6d20f-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="6d20f-116">Het wordt hier als optie aangeboden, zodat u de bescherming van globale beheerdersaccount testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="6d20f-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="6d20f-117">Fase 2: Beleid voor voorwaardelijke toegang configureren</span><span class="sxs-lookup"><span data-stu-id="6d20f-117">Phase 2: Configure Conditional Access policies</span></span>

<span data-ttu-id="6d20f-118">Maak eerst een nieuw gebruikersaccount aan als een toegewijde globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="6d20f-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="6d20f-119">Open op een apart tabblad het [Microsoft 365-beheercentrum](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="6d20f-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="6d20f-120">Klik **op Gebruikers > Actieve gebruikers**en klik vervolgens op Een gebruiker **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="6d20f-121">Typ **DedicatedAdmin** in **Voornaam,** **Weergavenaam**en **Gebruikersnaam**in het **deelvenster Gebruiker toevoegen** .</span><span class="sxs-lookup"><span data-stu-id="6d20f-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="6d20f-122">Klik op **Wachtwoord**, klik op **Laat me het wachtwoord maken**en typ een sterk wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="6d20f-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="6d20f-123">Neem het wachtwoord voor dit nieuwe account op een veilige locatie op.</span><span class="sxs-lookup"><span data-stu-id="6d20f-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="6d20f-124">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-124">Click **Next**.</span></span>
6. <span data-ttu-id="6d20f-125">Selecteer microsoft **365 E5** of Office **365 E5**in het deelvenster **Productlicenties toewijzen** en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-125">In the **Assign product licenses** pane, select **Microsoft 365 E5** or **Office 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="6d20f-126">Klik in het deelvenster **Optionele instellingen** op **Rollen**en selecteer vervolgens Toegang tot **het beheercentrum** en **globale beheerder**. Klik **op Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="6d20f-127">Klik in het deelvenster **U bent bijna klaar** op Toevoegen **voltooien**en klik vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="6d20f-128">Maak vervolgens een nieuwe groep met de naam GlobalAdmins en voeg het DedicatedAdmin-account eraan toe.</span><span class="sxs-lookup"><span data-stu-id="6d20f-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="6d20f-129">Klik op het tabblad **Microsoft 365-beheercentrum** op **Groepen** in de linkernavigatie en klik vervolgens op **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="6d20f-130">Klik **op Een groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="6d20f-131">Selecteer **beveiliging**in het **groepstypevenster kiezen** en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="6d20f-132">Klik in het deelvenster **Basisbasis instellen** op Groep **maken**en klik vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="6d20f-133">Typ **GlobalAdmins**in het **groepsvenster controleren en voltooien** en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="6d20f-134">Klik in de lijst met groepen op de groep **GlobalAdmins.**</span><span class="sxs-lookup"><span data-stu-id="6d20f-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="6d20f-135">Klik in het deelvenster **GlobalAdmins** op **Leden**en klik vervolgens op **Alle weergeven en leden beheren.**</span><span class="sxs-lookup"><span data-stu-id="6d20f-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="6d20f-136">Klik in het deelvenster **GlobalAdmins** op **Leden toevoegen,** selecteer het **DedicatedAdmin-account** en uw globale beheerdersaccount en klik vervolgens op **Opslaan > sluiten > sluiten**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="6d20f-137">Maak vervolgens beleid voor voorwaardelijke toegang om multifactorauthenticatie voor globale beheerdersaccounts te vereisen en verificatie te weigeren als het aanmeldingsrisico gemiddeld of hoog is.</span><span class="sxs-lookup"><span data-stu-id="6d20f-137">Next, create Conditional Access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="6d20f-138">Dit eerste beleid vereist dat alle accounts van globale beheerders MFA gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6d20f-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="6d20f-139">Ga in een nieuw tabblad [https://portal.azure.com](https://portal.azure.com)van uw browser naar .</span><span class="sxs-lookup"><span data-stu-id="6d20f-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="6d20f-140">Klik op **Azure Active Directory > Beveiliging > voorwaardelijke toegang**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="6d20f-141">Klik in het deelvenster **Voorwaardelijke toegang – Beleid** op **Basislijnbeleid: MFA vereisen voor beheerders (voorbeeld)**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="6d20f-142">Klik in het **beleidsvenster Basislijn** op **Beleid gebruiken onmiddellijk > Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="6d20f-143">Dit tweede beleid blokkeert de toegang tot globale verificatie van beheerdersaccount wanneer het aanmeldingsrisico gemiddeld of hoog is.</span><span class="sxs-lookup"><span data-stu-id="6d20f-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="6d20f-144">Klik in het deelvenster **Voorwaardelijke toegang – Beleid** op Nieuw **beleid**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="6d20f-145">Typ **Globale beheerders** in **Naam**in het deelvenster **Nieuw** .</span><span class="sxs-lookup"><span data-stu-id="6d20f-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="6d20f-146">Klik in de sectie **Toewijzingen** op **Gebruikers en groepen**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="6d20f-147">Klik op het tabblad **Opnemen** van het deelvenster **Gebruikers en groepen** op Gebruikers en groepen selecteren > gebruikers en groepen > **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="6d20f-148">Klik **in** het deelvenster Selecteren op de groep **GlobalAdmins** en klik vervolgens op **> gereed selecteren**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="6d20f-149">Klik in de sectie **Toewijzingen** op **Voorwaarden**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="6d20f-150">Klik **in** het deelvenster Voorwaarden op **Aanmeldingsrisico**, klik op **Ja** voor **Configureren,** klik op **Hoog** en **Gemiddeld**en klik vervolgens op **Selecteren** en **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="6d20f-151">Klik in het gedeelte **Toegangsbesturingselementen** van het deelvenster **Nieuw** op **Verlenen**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="6d20f-152">Klik **in** het deelvenster Subsidie op **Toegang blokkeren**en klik vervolgens op **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="6d20f-153">Klik in het deelvenster **Nieuw** op **Beleid** **inschakelen**en klik vervolgens op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="6d20f-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="6d20f-154">Sluit de tabbladen **Azure-portal** en **Microsoft 365-beheercentrum.**</span><span class="sxs-lookup"><span data-stu-id="6d20f-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="6d20f-155">Als u het eerste beleid wilt testen, meldt u zich af en meldt u zich aan met het DedicatedAdmin-account.</span><span class="sxs-lookup"><span data-stu-id="6d20f-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="6d20f-156">U moet worden gevraagd om MFA te configureren.</span><span class="sxs-lookup"><span data-stu-id="6d20f-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="6d20f-157">Dit toont aan dat het eerste beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="6d20f-157">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="6d20f-158">Zie de stap [Accounts voor globale beheerders beveiligen](identity-create-protect-global-admins.md#identity-global-admin) in de identiteitsfase voor informatie en koppelingen om uw wereldwijde beheerdersaccounts in productie te beschermen.</span><span class="sxs-lookup"><span data-stu-id="6d20f-158">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="6d20f-159">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="6d20f-159">Next step</span></span>

<span data-ttu-id="6d20f-160">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="6d20f-160">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d20f-161">Zie ook</span><span class="sxs-lookup"><span data-stu-id="6d20f-161">See also</span></span>

[<span data-ttu-id="6d20f-162">Fase 2: Identiteit</span><span class="sxs-lookup"><span data-stu-id="6d20f-162">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="6d20f-163">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="6d20f-163">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6d20f-164">Microsoft 365 Enterprise-implementatie</span><span class="sxs-lookup"><span data-stu-id="6d20f-164">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="6d20f-165">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="6d20f-165">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
