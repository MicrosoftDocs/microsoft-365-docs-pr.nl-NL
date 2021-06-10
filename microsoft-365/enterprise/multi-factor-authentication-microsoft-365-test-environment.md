---
title: Microsoft 365 voor ondernemingstestomgeving meervoudige verificatie
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
- seo-marvel-apr2020
description: Configureer meervoudige verificatie met tekstberichten die zijn verzonden naar een smartphone in uw Microsoft 365 voor bedrijfstestomgeving.
ms.openlocfilehash: aeb8940a9499909b8c568d1230f9aa45aee07b3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923754"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="05f74-103">Meervoudige verificatie voor uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="05f74-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="05f74-104">*Deze testlaborator kan worden gebruikt voor zowel Microsoft 365 voor bedrijven als Office 365 Enterprise testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="05f74-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="05f74-105">Voor een extra beveiligingsniveau voor het aanmelden bij Microsoft 365 of een service of toepassing die gebruikmaakt van de Azure AD-tenant voor uw abonnement, kunt u Meervoudige verificatie van Azure AD inschakelen, waarvoor meer dan alleen een gebruikersnaam en wachtwoord nodig zijn om een account te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="05f74-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure AD multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="05f74-106">Bij meervoudige verificatie moeten gebruikers een telefoongesprek bevestigen, een verificatiecode typen die in een sms-bericht is verzonden of de verificatie verifiëren met een app op hun smartphone nadat ze hun wachtwoorden correct hebben invoeren.</span><span class="sxs-lookup"><span data-stu-id="05f74-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="05f74-107">Ze kunnen zich alleen aanmelden nadat deze tweede verificatiefactor is voldaan.</span><span class="sxs-lookup"><span data-stu-id="05f74-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="05f74-108">In dit artikel wordt beschreven hoe u verificatie op basis van tekstberichten in- en test voor een specifiek gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="05f74-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="05f74-109">Het instellen van meervoudige verificatie voor een account in uw Microsoft 365 voor ondernemingstestomgeving omvat twee fasen en een derde optionele fase:</span><span class="sxs-lookup"><span data-stu-id="05f74-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="05f74-110">Fase 1: uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="05f74-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="05f74-111">Fase 2: Meervoudige verificatie in- en testen voor het Gebruikers 2-account</span><span class="sxs-lookup"><span data-stu-id="05f74-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="05f74-112">Fase 3: Meervoudige verificatie inschakelen en testen met een beleid voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="05f74-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="05f74-114">Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, gaat u naar Microsoft 365 voor [enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="05f74-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="05f74-115">Fase 1: uw Microsoft 365 voor bedrijfstestomgeving</span><span class="sxs-lookup"><span data-stu-id="05f74-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="05f74-116">Als u alleen meervoudige verificatie op een lichtgewicht manier wilt testen met de minimumvereisten, volgt u de instructies in [de lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="05f74-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="05f74-117">Als u meervoudige verificatie wilt testen in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="05f74-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="05f74-118">Voor het testen van meervoudige verificatie is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="05f74-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="05f74-119">Het is hier beschikbaar als een optie, zodat u meervoudige verificatie kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="05f74-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="05f74-120">Fase 2: Meervoudige verificatie in- en testen voor het Gebruikers 2-account</span><span class="sxs-lookup"><span data-stu-id="05f74-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="05f74-121">Schakel meervoudige verificatie in voor het Gebruikers 2-account met de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="05f74-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="05f74-122">Open een afzonderlijk, privé-exemplaar van uw browser, ga naar het Microsoft 365 beheercentrum ( ) en meld u aan [https://portal.microsoft.com](https://portal.microsoft.com) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="05f74-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="05f74-123">Selecteer in de linkernavigatie de optie **Gebruikers**  >  **Actieve gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="05f74-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="05f74-124">Selecteer in het deelvenster Actieve gebruikers de optie **Meervoudige verificatie**.</span><span class="sxs-lookup"><span data-stu-id="05f74-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="05f74-125">Selecteer in de lijst het **account Gebruiker 2.**</span><span class="sxs-lookup"><span data-stu-id="05f74-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="05f74-126">Selecteer in de sectie Gebruiker **2** onder **Snelle stappen** de optie **Inschakelen.**</span><span class="sxs-lookup"><span data-stu-id="05f74-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="05f74-127">Selecteer in het dialoogvenster Over het inschakelen van **multi-factor auth** de optie **Multi-factor auth inschakelen.**</span><span class="sxs-lookup"><span data-stu-id="05f74-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="05f74-128">Selecteer sluiten **in het** dialoogvenster Updates **succesvol.**</span><span class="sxs-lookup"><span data-stu-id="05f74-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="05f74-129">Selecteer op **Microsoft 365 tabblad Beheercentrum** het pictogram gebruikersaccount in de rechterbovenhoek en selecteer **vervolgens Uitloggen.**</span><span class="sxs-lookup"><span data-stu-id="05f74-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="05f74-130">Sluit het browserexe instance.</span><span class="sxs-lookup"><span data-stu-id="05f74-130">Close your browser instance.</span></span>
   
<span data-ttu-id="05f74-131">Voltooi de configuratie voor het Gebruikers 2-account om een tekstbericht te gebruiken voor validatie en test dit met de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="05f74-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="05f74-132">Open een nieuw, privé-exemplaar van uw browser.</span><span class="sxs-lookup"><span data-stu-id="05f74-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="05f74-133">Ga naar het [Microsoft 365 beheercentrum](https://admin.microsoft.com) en meld u aan met de accountnaam en het wachtwoord van gebruiker 2.</span><span class="sxs-lookup"><span data-stu-id="05f74-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="05f74-134">Nadat u zich hebt aanmelden, wordt u gevraagd het account in te stellen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="05f74-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="05f74-135">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="05f74-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="05f74-136">Op de **pagina Extra beveiligingsverificatie:**</span><span class="sxs-lookup"><span data-stu-id="05f74-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="05f74-137">Selecteer uw land of regio.</span><span class="sxs-lookup"><span data-stu-id="05f74-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="05f74-138">Voer het telefoonnummer in van de smartphone die sms-berichten ontvangt.</span><span class="sxs-lookup"><span data-stu-id="05f74-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="05f74-139">Selecteer **in Methode** de optie Een code per sms **verzenden.**</span><span class="sxs-lookup"><span data-stu-id="05f74-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="05f74-140">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="05f74-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="05f74-141">Voer de verificatiecode in van het sms-bericht dat u op uw smartphone hebt ontvangen en selecteer **controleren.**</span><span class="sxs-lookup"><span data-stu-id="05f74-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="05f74-142">Selecteer op **de pagina Stap 3: Uw bestaande toepassingen** behouden de optie **Klaar.**</span><span class="sxs-lookup"><span data-stu-id="05f74-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="05f74-143">Als dit de eerste keer is dat u zich hebt aangemeld met het account Gebruiker 2, wordt u gevraagd het wachtwoord te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="05f74-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="05f74-144">Voer tweemaal het oorspronkelijke wachtwoord en een nieuw wachtwoord in en selecteer **vervolgens Wachtwoord bijwerken en meld u aan.**</span><span class="sxs-lookup"><span data-stu-id="05f74-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="05f74-145">Neem het nieuwe wachtwoord op een veilige locatie op.</span><span class="sxs-lookup"><span data-stu-id="05f74-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="05f74-146">U ziet de Office portal voor gebruiker 2 op Microsoft Office **tabblad Start** van uw browser.</span><span class="sxs-lookup"><span data-stu-id="05f74-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="05f74-147">Fase 3: Meervoudige verificatie inschakelen en testen met een beleid voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="05f74-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="05f74-148">*Deze fase kan alleen worden gebruikt voor een Microsoft 365 voor ondernemingstestomgeving.*</span><span class="sxs-lookup"><span data-stu-id="05f74-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="05f74-149">In deze fase kunt u meervoudige verificatie voor het Gebruikers 3-account inschakelen met behulp van een groep en een beleid voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="05f74-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="05f74-150">Maak vervolgens een nieuwe groep met de naam MFAUsers en voeg het account Gebruiker 3 hieraan toe.</span><span class="sxs-lookup"><span data-stu-id="05f74-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="05f74-151">Selecteer op **Microsoft 365 tabblad Beheercentrum** de optie **Groepen** in de linkernavigatie en selecteer **vervolgens Groepen**.</span><span class="sxs-lookup"><span data-stu-id="05f74-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="05f74-152">Selecteer **Een groep toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="05f74-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="05f74-153">Selecteer in **het deelvenster Een groeptype** kiezen de optie **Beveiliging** en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="05f74-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="05f74-154">Selecteer in **het deelvenster De basisbeginselen** instellen de optie Groep **maken** en selecteer vervolgens **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="05f74-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="05f74-155">Voer in **het deelvenster Controleren en** voltooien groep toevoegen **MFAUsers** in en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="05f74-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="05f74-156">Selecteer in de lijst met groepen de **groep MFAUsers.**</span><span class="sxs-lookup"><span data-stu-id="05f74-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="05f74-157">Selecteer leden in het deelvenster **MFAUsers** **en** selecteer vervolgens Alle leden weergeven **en beheren.**</span><span class="sxs-lookup"><span data-stu-id="05f74-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="05f74-158">Selecteer leden toevoegen in het deelvenster **MFAUsers,** selecteer het account **Gebruiker 3** en selecteer **sluiten**  >  **sluiten**  >  **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="05f74-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="05f74-159">Maak vervolgens een beleid voor voorwaardelijke toegang om meervoudige verificatie voor leden van de groep MFAUsers te vereisen.</span><span class="sxs-lookup"><span data-stu-id="05f74-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="05f74-160">Ga op een nieuw tabblad van uw browser naar [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="05f74-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="05f74-161">Selecteer **Azure Active Directory**  >    >  **Voorwaardelijke toegang voor beveiliging**.</span><span class="sxs-lookup"><span data-stu-id="05f74-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="05f74-162">Selecteer in **het deelvenster Voorwaardelijke** toegang – Beleid de optie **Nieuw beleid.**</span><span class="sxs-lookup"><span data-stu-id="05f74-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="05f74-163">Typ in **het** deelvenster Nieuw **MFA voor gebruikersaccounts** in **het vak Naam.**</span><span class="sxs-lookup"><span data-stu-id="05f74-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="05f74-164">Selecteer gebruikers en groepen in **de** sectie **Opdrachten.**</span><span class="sxs-lookup"><span data-stu-id="05f74-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="05f74-165">Selecteer op **het** tabblad Opnemen van het deelvenster Gebruikers **en groepen** de optie Gebruikers en **groepen** selecteren Gebruikers  >  **en groepen**  >  **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="05f74-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="05f74-166">Selecteer in **het** deelvenster Selecteren de **groep MFAUsers** en selecteer **vervolgens Done**  >  **selecteren.**</span><span class="sxs-lookup"><span data-stu-id="05f74-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="05f74-167">Selecteer in **de sectie Besturingselementen** van Access **van het** deelvenster Nieuw de optie **Grant**.</span><span class="sxs-lookup"><span data-stu-id="05f74-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="05f74-168">Selecteer in **het** deelvenster Verlenen de optie **Meervoudige verificatie vereisen** en selecteer vervolgens **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="05f74-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="05f74-169">Selecteer in **het** deelvenster Nieuw **de optie Aan** voor Beleid **inschakelen** en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="05f74-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="05f74-170">Sluit de **Azure-portal** en **Microsoft 365 tabbladen van het** beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="05f74-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="05f74-171">Als u dit beleid wilt testen, meld u zich af en meld u aan met het account Gebruiker 3.</span><span class="sxs-lookup"><span data-stu-id="05f74-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="05f74-172">U moet worden gevraagd om MFA te configureren.</span><span class="sxs-lookup"><span data-stu-id="05f74-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="05f74-173">Dit toont aan dat het MFAUsers-beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="05f74-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="05f74-174">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="05f74-174">Next step</span></span>

<span data-ttu-id="05f74-175">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="05f74-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="05f74-176">Zie ook</span><span class="sxs-lookup"><span data-stu-id="05f74-176">See also</span></span>

[<span data-ttu-id="05f74-177">Routekaart voor identiteit</span><span class="sxs-lookup"><span data-stu-id="05f74-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="05f74-178">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="05f74-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="05f74-179">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="05f74-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="05f74-180">Microsoft 365 enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="05f74-180">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)