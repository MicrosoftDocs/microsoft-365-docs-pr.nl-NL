---
title: Meervoudige verificatie voor uw Microsoft 365 Enterprise-testomgeving
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
description: Configureer multi-factor authenticatie met behulp van tekstberichten die naar een smartphone worden verzonden in uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: ea2041a463b224781df101251dab0f4d9f0e8753
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806280"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1a371-103">Meervoudige verificatie voor uw Microsoft 365 Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="1a371-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1a371-104">*Deze Test Lab Guide kan worden gebruikt voor zowel Microsoft 365 Enterprise- als Office 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="1a371-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="1a371-105">Voor een extra beveiligingsniveau voor het aanmelden bij Microsoft 365 of een service of toepassing die de Azure AD-tenant voor uw abonnement gebruikt, u Azure-meervoudige verificatie inschakelen, waarvoor meer nodig is dan alleen een gebruikersnaam en wachtwoord om een Account.</span><span class="sxs-lookup"><span data-stu-id="1a371-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> 

<span data-ttu-id="1a371-106">Met multi-factor authenticatie moeten gebruikers een telefoongesprek erkennen, een verificatiecode typen die in een sms-bericht wordt verzonden of een app-wachtwoord opgeven op hun smartphones nadat ze hun wachtwoorden correct hebben ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="1a371-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="1a371-107">Ze kunnen zich pas aanmelden nadat deze tweede verificatiefactor is voldaan.</span><span class="sxs-lookup"><span data-stu-id="1a371-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="1a371-108">In dit artikel wordt beschreven hoe u verificatie op basis van sms'en inschakelt en test voor een specifiek gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="1a371-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="1a371-109">Er zijn twee fasen voor het instellen van meervoudige verificatie voor een account in uw Microsoft 365 Enterprise-testomgeving:</span><span class="sxs-lookup"><span data-stu-id="1a371-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="1a371-110">Maak de Microsoft 365 Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="1a371-110">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="1a371-111">Multi-factor authenticatie inschakelen en testen voor het Gebruikers 2-account.</span><span class="sxs-lookup"><span data-stu-id="1a371-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

3. <span data-ttu-id="1a371-112">Multifactorauthenticatie inschakelen en testen met een beleid voor voorwaardelijke toegang (optioneel).</span><span class="sxs-lookup"><span data-stu-id="1a371-112">Enable and test multi-factor authentication with a conditional access policy (optional).</span></span>

![Test Lab-hulplijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="1a371-114">Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.</span><span class="sxs-lookup"><span data-stu-id="1a371-114">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1a371-115">Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen</span><span class="sxs-lookup"><span data-stu-id="1a371-115">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1a371-116">Als u alleen multi-factor authenticatie op een lichtgewicht manier wilt testen met de minimumvereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="1a371-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1a371-117">Als u meervoudige verificatie wilt testen in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1a371-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1a371-118">Het testen van multi-factor authenticatie vereist niet de gesimuleerde bedrijfstestomgeving, die een gesimuleerd intranet bevat dat is verbonden met het internet en directorysynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="1a371-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="1a371-119">Het wordt hier als optie geleverd, zodat u multi-factor authenticatie testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="1a371-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="1a371-120">Fase 2: Meervoudige verificatie inschakelen en testen voor het Gebruikers 2-account</span><span class="sxs-lookup"><span data-stu-id="1a371-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="1a371-121">Schakel multi-factor authenticatie in voor het Gebruikers 2-account met de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="1a371-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="1a371-122">Open een afzonderlijke, privé-instantie van uw browser, ga[https://portal.microsoft.com](https://portal.microsoft.com)naar het Microsoft 365-beheercentrum en meld u vervolgens aan met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="1a371-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="1a371-123">Klik in de linkernavigatie op **Gebruikers > Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="1a371-123">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="1a371-124">Klik in het deelvenster Actieve gebruikers op **Meervoudige verificatie**.</span><span class="sxs-lookup"><span data-stu-id="1a371-124">In the Active users pane, click **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="1a371-125">Selecteer in de lijst het **account Gebruiker 2.**</span><span class="sxs-lookup"><span data-stu-id="1a371-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="1a371-126">Klik in de sectie **Gebruiker 2** onder **Snelle stappen**op **Inschakelen**.</span><span class="sxs-lookup"><span data-stu-id="1a371-126">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="1a371-127">Klik in het dialoogvenster Over het inschakelen van **multi-factor auth** op **Multifactor auth inschakelen.**</span><span class="sxs-lookup"><span data-stu-id="1a371-127">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="1a371-128">Klik in het dialoogvenster **Updates succesvol** op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="1a371-128">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="1a371-129">Klik op het tabblad **Microsoft 365-beheercentrum** op het pictogram van het gebruikersaccount rechtsboven en klik vervolgens op **Afmelden**.</span><span class="sxs-lookup"><span data-stu-id="1a371-129">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="1a371-130">Sluit uw browserinstantie.</span><span class="sxs-lookup"><span data-stu-id="1a371-130">Close your browser instance.</span></span>
   
<span data-ttu-id="1a371-131">Voltooi de configuratie voor het Gebruikers 2-account om een sms-bericht te gebruiken voor validatie en test het met de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="1a371-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="1a371-132">Open een nieuw, privé-exemplaar van uw browser.</span><span class="sxs-lookup"><span data-stu-id="1a371-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="1a371-133">Ga naar de Office 365-portal[https://portal.office.com](https://portal.office.com)en meld u aan met de naam en het wachtwoord van het Gebruikers2-account.</span><span class="sxs-lookup"><span data-stu-id="1a371-133">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="1a371-134">Nadat u zich hebt aangemeld, wordt u gevraagd het account in te stellen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1a371-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="1a371-135">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="1a371-135">Click **Next**.</span></span>
    
4. <span data-ttu-id="1a371-136">Ga als op de pagina **Aanvullende beveiligingsverificatie:**</span><span class="sxs-lookup"><span data-stu-id="1a371-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="1a371-137">Selecteer uw land of regio.</span><span class="sxs-lookup"><span data-stu-id="1a371-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="1a371-138">Typ het telefoonnummer van de smartphone die sms-berichten ontvangt.</span><span class="sxs-lookup"><span data-stu-id="1a371-138">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="1a371-139">Klik in **Methode**op **Mij een code**per sms sturen .</span><span class="sxs-lookup"><span data-stu-id="1a371-139">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="1a371-140">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="1a371-140">Click **Next**.</span></span>
    
6. <span data-ttu-id="1a371-141">Voer de verificatiecode in van het sms-bericht dat op uw smartphone is ontvangen en klik op **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="1a371-141">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="1a371-142">Houd op de **pagina Stap 3: Houd de** pagina van uw bestaande toepassingen op en noteer het weergegeven app-wachtwoord voor het gebruikers2-account op een veilige locatie en klik vervolgens op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="1a371-142">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="1a371-143">Als dit de eerste keer is dat u zich aanmeldde bij het Gebruikers 2-account, wordt u gevraagd het wachtwoord te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="1a371-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="1a371-144">Typ het oorspronkelijke wachtwoord en een nieuw wachtwoord twee keer en klik op **Wachtwoord bijwerken en meld u aan.**</span><span class="sxs-lookup"><span data-stu-id="1a371-144">Type the original password and a new password twice, and then click **Update password and sign in**.</span></span> <span data-ttu-id="1a371-145">Neem het nieuwe wachtwoord op een veilige locatie op.</span><span class="sxs-lookup"><span data-stu-id="1a371-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="1a371-146">U ziet de Office-portal voor gebruiker 2 op het tabblad **Microsoft Office Start** van uw browser.</span><span class="sxs-lookup"><span data-stu-id="1a371-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="1a371-147">Fase 3: Meervoudige verificatie inschakelen en testen met een beleid voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="1a371-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="1a371-148">*Deze fase kan alleen worden gebruikt voor een Microsoft 365 Enterprise-testomgeving.*</span><span class="sxs-lookup"><span data-stu-id="1a371-148">*This phase can only be used for a Microsoft 365 Enterprise test environment.*</span></span>

<span data-ttu-id="1a371-149">In deze fase schakelt u multi-factor authenticatie in voor het Gebruikers 3-account met behulp van een groep en een beleid voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="1a371-149">In this phase you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="1a371-150">Maak vervolgens een nieuwe groep met de naam MFAUsers en voeg er het Gebruikers 3-account aan toe.</span><span class="sxs-lookup"><span data-stu-id="1a371-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="1a371-151">Klik op het tabblad **Microsoft 365-beheercentrum** op **Groepen** in de linkernavigatie en klik vervolgens op **Groepen**.</span><span class="sxs-lookup"><span data-stu-id="1a371-151">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="1a371-152">Klik op **Een groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="1a371-152">Click **Add a group**.</span></span>
3. <span data-ttu-id="1a371-153">Selecteer **Beveiliging**in het deelvenster **Een groepstype kiezen** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="1a371-153">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="1a371-154">Klik in het deelvenster **Basisinstellingen** op **Groep maken**en klik vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="1a371-154">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="1a371-155">Typ **MFAUsers**in het **deelvenster Controleren en voltooien** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="1a371-155">In the **Review and finish adding group** pane, type **MFAUsers**, and then click **Next**.</span></span>
6. <span data-ttu-id="1a371-156">Klik in de lijst met groepen op de groep **MFAUsers.**</span><span class="sxs-lookup"><span data-stu-id="1a371-156">In the list of groups, click the **MFAUsers** group.</span></span>
7. <span data-ttu-id="1a371-157">Klik in het deelvenster **MFAUsers** op **Leden**en klik vervolgens op **Alle weergeven en leden beheren**.</span><span class="sxs-lookup"><span data-stu-id="1a371-157">In the **MFAUsers** pane, click **Members**, and then click **View all and manage members**.</span></span>
8. <span data-ttu-id="1a371-158">Klik in het deelvenster **MFAUsers** op **Leden toevoegen,** selecteer het **gebruikers3-account** en klik vervolgens op **Opslaan > sluiten > sluiten**.</span><span class="sxs-lookup"><span data-stu-id="1a371-158">In the **MFAUsers** pane, click **Add members**, select the **User 3** account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="1a371-159">Maak vervolgens een beleid voor voorwaardelijke toegang om multifactorauthenticatie te vereisen voor leden van de MFAUsers-groep.</span><span class="sxs-lookup"><span data-stu-id="1a371-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="1a371-160">Ga in een nieuw tabblad [https://portal.azure.com](https://portal.azure.com)van uw browser naar .</span><span class="sxs-lookup"><span data-stu-id="1a371-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="1a371-161">Klik **op Azure Active Directory > Beveiliging > voorwaardelijke toegang**.</span><span class="sxs-lookup"><span data-stu-id="1a371-161">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="1a371-162">Klik in het deelvenster **Voorwaardelijke toegang – Beleid** op Nieuw **beleid**.</span><span class="sxs-lookup"><span data-stu-id="1a371-162">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
4. <span data-ttu-id="1a371-163">Typ MFA in het deelvenster **Nieuw** **voor gebruikersaccounts** in **Naam**.</span><span class="sxs-lookup"><span data-stu-id="1a371-163">In the **New** pane, type **MFA for user accounts** in **Name**.</span></span>
5. <span data-ttu-id="1a371-164">Klik in de sectie **Toewijzingen** op **Gebruikers en groepen**.</span><span class="sxs-lookup"><span data-stu-id="1a371-164">In the **Assignments** section, click **Users and groups**.</span></span>
6. <span data-ttu-id="1a371-165">Klik op het tabblad **Opnemen** van het deelvenster **Gebruikers en groepen** op Gebruikers selecteren en groepen > gebruikers en groepen > **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="1a371-165">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
7. <span data-ttu-id="1a371-166">Klik in het deelvenster **Selecteren** op de groep **MFAUsers** en klik vervolgens op **Selecteren > gedaan**.</span><span class="sxs-lookup"><span data-stu-id="1a371-166">In the **Select** pane, click the **MFAUsers** group, and then click **Select > Done**.</span></span>
8. <span data-ttu-id="1a371-167">Klik in het gedeelte **Besturingselementen voor toegang** in het deelvenster **Nieuw** op **Grant**.</span><span class="sxs-lookup"><span data-stu-id="1a371-167">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="1a371-168">Klik in het deelvenster **Subsidie** op **Meervoudige verificatie vereisen**en klik vervolgens op **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="1a371-168">In the **Grant** pane, click **Require multi-factor authentication**, and then click **Select**.</span></span>
10. <span data-ttu-id="1a371-169">Klik in het deelvenster **Nieuw** op **Aan** voor **Beleid inschakelen**en klik vervolgens op **Maken**.</span><span class="sxs-lookup"><span data-stu-id="1a371-169">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="1a371-170">Sluit de tabbladen **Azure-portal** en **Microsoft 365-beheercentrum.**</span><span class="sxs-lookup"><span data-stu-id="1a371-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="1a371-171">Als u dit beleid wilt testen, meldt u zich af en meldt u zich af met het Account 3 van gebruiker.</span><span class="sxs-lookup"><span data-stu-id="1a371-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="1a371-172">U moet worden gevraagd mfa te configureren.</span><span class="sxs-lookup"><span data-stu-id="1a371-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="1a371-173">Dit toont aan dat het MFAUsers-beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="1a371-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

<span data-ttu-id="1a371-174">Zie de stap [Multi-factor authenticatie instellen](identity-secure-user-sign-ins.md#identity-mfa) in de identiteitsfase voor informatie en koppelingen om multi-factor authenticatie in productie te implementeren.</span><span class="sxs-lookup"><span data-stu-id="1a371-174">See the [Set up multi-factor authentication](identity-secure-user-sign-ins.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="1a371-175">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="1a371-175">Next step</span></span>

<span data-ttu-id="1a371-176">Ontdek extra [identiteitsfuncties](m365-enterprise-test-lab-guides.md#identity) en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="1a371-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a371-177">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1a371-177">See also</span></span>

[<span data-ttu-id="1a371-178">Fase 2: Identiteit</span><span class="sxs-lookup"><span data-stu-id="1a371-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="1a371-179">Microsoft 365 Enterprise Test Lab-handleidingen</span><span class="sxs-lookup"><span data-stu-id="1a371-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1a371-180">Microsoft 365 Enterprise-implementatie</span><span class="sxs-lookup"><span data-stu-id="1a371-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1a371-181">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="1a371-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
