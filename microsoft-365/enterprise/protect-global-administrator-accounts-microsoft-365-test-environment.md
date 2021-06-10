---
title: Globale beheerdersaccounts beveiligen in uw Microsoft 365 voor ondernemingstestomgeving
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
description: Gebruik deze stappen om globale beheerdersaccounts in uw Microsoft 365 voor ondernemingstestomgeving te beveiligen.
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918880"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="70140-103">Globale beheerdersaccounts beveiligen in uw Microsoft 365 voor ondernemingstestomgeving</span><span class="sxs-lookup"><span data-stu-id="70140-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="70140-104">*Deze testlaborator kan alleen worden gebruikt Microsoft 365 voor bedrijfstestomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="70140-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="70140-105">U kunt digitale aanvallen op uw organisatie voorkomen door ervoor te zorgen dat uw beheerdersaccounts zo veilig mogelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="70140-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="70140-106">In dit artikel wordt beschreven hoe u Azure Active Directory (Azure AD) beleid voor voorwaardelijke toegang gebruikt om globale beheerdersaccounts te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="70140-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="70140-107">Voor het beveiligen van globale beheerdersaccounts in Microsoft 365 testomgeving voor ondernemingen zijn twee fasen vereist:</span><span class="sxs-lookup"><span data-stu-id="70140-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="70140-108">Fase 1: uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="70140-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="70140-109">Fase 2: Beleid voor voorwaardelijke toegang configureren</span><span class="sxs-lookup"><span data-stu-id="70140-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="70140-111">Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, gaat u naar Microsoft 365 voor [enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="70140-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="70140-112">Fase 1: uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="70140-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="70140-113">Als u de beveiliging van globale beheerdersaccounts op een lichtgewicht manier wilt testen met de minimumvereisten, volgt u de instructies in [Lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="70140-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="70140-114">Als u de beveiliging van globale beheerdersaccounts in een gesimuleerde onderneming wilt testen, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="70140-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="70140-115">Voor het testen van globale beheerdersaccountbeveiliging is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="70140-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="70140-116">Het wordt hier als een optie aangeboden, zodat u de beveiliging van globale beheerdersaccounts kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="70140-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="70140-117">Fase 2: Beleid voor voorwaardelijke toegang configureren</span><span class="sxs-lookup"><span data-stu-id="70140-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="70140-118">Maak eerst een nieuw gebruikersaccount als een toegewezen globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="70140-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="70140-119">Open op een afzonderlijk tabblad het [Microsoft 365 beheercentrum](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="70140-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="70140-120">Selecteer **Gebruikers**  >  **Actieve gebruikers** en selecteer vervolgens Een gebruiker **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="70140-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="70140-121">Voer in **het deelvenster** Gebruiker toevoegen **DedicatedAdmin** in de vakken **Voornaam,** **Weergavenaam** en **Gebruikersnaam** in.</span><span class="sxs-lookup"><span data-stu-id="70140-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="70140-122">Selecteer **Wachtwoord,** selecteer **Laat me het wachtwoord maken** en voer een sterk wachtwoord in.</span><span class="sxs-lookup"><span data-stu-id="70140-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="70140-123">Neem het wachtwoord voor dit nieuwe account op een veilige locatie op.</span><span class="sxs-lookup"><span data-stu-id="70140-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="70140-124">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="70140-124">Select **Next**.</span></span>
6. <span data-ttu-id="70140-125">Selecteer in **het deelvenster Productlicenties** toewijzen **Microsoft 365 E5** en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="70140-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="70140-126">Selecteer in **het deelvenster Optionele** instellingen de optie   >  **Rollenbeheerder toegang tot** Globale  >  **beheerder**  >  **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="70140-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="70140-127">Selecteer in **het deelvenster U bent bijna klaar** de optie Toevoegen **voltooien** en selecteer **vervolgens Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="70140-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="70140-128">Maak vervolgens een nieuwe groep met de naam GlobalAdmins en voeg het DedicatedAdmin-account hieraan toe.</span><span class="sxs-lookup"><span data-stu-id="70140-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="70140-129">Selecteer op **Microsoft 365 tabblad Beheercentrum** de optie **Groepen** in de linkernavigatie en selecteer **vervolgens Groepen**.</span><span class="sxs-lookup"><span data-stu-id="70140-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="70140-130">Selecteer **Een groep toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="70140-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="70140-131">Selecteer in **het deelvenster Een groeptype** kiezen de optie **Beveiliging** en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="70140-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="70140-132">Selecteer in **het deelvenster De basisbeginselen** instellen de optie Groep **maken** en selecteer vervolgens **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="70140-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="70140-133">Voer in **het deelvenster Controleren en** voltooien groep toevoegen **GlobalAdmins** in en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="70140-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="70140-134">Selecteer in de lijst met groepen de **groep GlobalAdmins.**</span><span class="sxs-lookup"><span data-stu-id="70140-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="70140-135">Selecteer leden **in het deelvenster GlobalAdmins** **en** selecteer **vervolgens Alle leden weergeven en beheren.**</span><span class="sxs-lookup"><span data-stu-id="70140-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="70140-136">Selecteer in **het deelvenster GlobalAdmins** de optie **Leden** toevoegen, selecteer het **DedicatedAdmin-account** en uw globale beheerdersaccount en selecteer **vervolgens Sluiten**  >    >  **sluiten opslaan.**</span><span class="sxs-lookup"><span data-stu-id="70140-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="70140-137">Maak vervolgens beleid voor voorwaardelijke toegang om meervoudige verificatie voor globale beheerdersaccounts te vereisen en verificatie te weigeren als het aanmeldingsrisico gemiddeld of hoog is.</span><span class="sxs-lookup"><span data-stu-id="70140-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="70140-138">Dit eerste beleid vereist dat alle globale beheerdersaccounts MFA gebruiken.</span><span class="sxs-lookup"><span data-stu-id="70140-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="70140-139">Ga op een nieuw tabblad van uw browser naar [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="70140-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="70140-140">Klik **Azure Active Directory**  >    >  **Voorwaardelijke toegang voor beveiliging**.</span><span class="sxs-lookup"><span data-stu-id="70140-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="70140-141">Selecteer in **het deelvenster Voorwaardelijke** toegang - Beleid de optie **Basislijnbeleid: MFA vereisen voor beheerders (voorbeeld)**.</span><span class="sxs-lookup"><span data-stu-id="70140-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="70140-142">Selecteer in **het deelvenster** Basislijnbeleid de optie Beleid direct gebruiken **> Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="70140-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="70140-143">Dit tweede beleid blokkeert de toegang tot globale verificatie van beheerdersaccounts wanneer het aanmeldingsrisico gemiddeld of hoog is.</span><span class="sxs-lookup"><span data-stu-id="70140-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="70140-144">Selecteer in **het deelvenster Voorwaardelijke** toegang – Beleid de optie **Nieuw beleid.**</span><span class="sxs-lookup"><span data-stu-id="70140-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="70140-145">Voer in **het** deelvenster Nieuw **globale beheerders** in **naam in.**</span><span class="sxs-lookup"><span data-stu-id="70140-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="70140-146">Selecteer gebruikers en groepen in **de** sectie **Opdrachten.**</span><span class="sxs-lookup"><span data-stu-id="70140-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="70140-147">Selecteer op **het** tabblad Opnemen van het deelvenster Gebruikers **en groepen** de optie Gebruikers en **groepen** selecteren Gebruikers  >  **en groepen**  >  **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="70140-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="70140-148">Selecteer in **het** deelvenster Selecteren de **groep GlobalAdmins** en selecteer **vervolgens Done**  >  **selecteren.**</span><span class="sxs-lookup"><span data-stu-id="70140-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="70140-149">Selecteer voorwaarden in **de** sectie **Opdrachten.**</span><span class="sxs-lookup"><span data-stu-id="70140-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="70140-150">Selecteer in **het** deelvenster Voorwaarden de optie Aanmeldingsrisico, selecteer **Ja** voor **configureren,** selecteer **Hoog** en **Gemiddeld** en selecteer vervolgens **Selecteren** en **Klaar.**</span><span class="sxs-lookup"><span data-stu-id="70140-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="70140-151">Selecteer in **de sectie Besturingselementen** van Access **van het** deelvenster Nieuw de optie **Grant**.</span><span class="sxs-lookup"><span data-stu-id="70140-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="70140-152">Selecteer in **het** deelvenster Verlenen de optie **Toegang blokkeren** en selecteer **vervolgens Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="70140-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="70140-153">Selecteer in **het** deelvenster Nieuw **de optie Aan** voor Beleid **inschakelen** en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="70140-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="70140-154">Sluit de **Azure-portal** en **Microsoft 365 tabbladen van het** beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="70140-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="70140-155">Als u het eerste beleid wilt testen, meld u zich af en meld u aan met het DedicatedAdmin-account.</span><span class="sxs-lookup"><span data-stu-id="70140-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="70140-156">U moet worden gevraagd om MFA te configureren.</span><span class="sxs-lookup"><span data-stu-id="70140-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="70140-157">Dit laat zien dat het eerste beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="70140-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="70140-158">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="70140-158">Next step</span></span>

<span data-ttu-id="70140-159">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="70140-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="70140-160">Zie ook</span><span class="sxs-lookup"><span data-stu-id="70140-160">See also</span></span>

[<span data-ttu-id="70140-161">Routekaart voor identiteit</span><span class="sxs-lookup"><span data-stu-id="70140-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="70140-162">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="70140-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="70140-163">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="70140-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="70140-164">Microsoft 365 enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="70140-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)