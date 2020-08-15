---
title: Multi-factor Authentication voor Microsoft 365 voor Enterprise testomgeving
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
description: Configureer multi-factor Authentication met behulp van SMS-berichten die zijn verzonden naar een smartphone in uw Microsoft 365 voor Enterprise test environment.
ms.openlocfilehash: 4ed50d37e0f4e73d5d1fc62e295df374c61b9786
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686272"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="9ee11-103">Meervoudige verificatie voor uw Microsoft 365 voor Enterprise testomgeving</span><span class="sxs-lookup"><span data-stu-id="9ee11-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="9ee11-104">*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="9ee11-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="9ee11-105">Voor een extra beveiligingsniveau voor het aanmelden bij Microsoft 365 of een willekeurige service of toepassing die de Azure AD-Tenant voor uw abonnement gebruikt, kunt u gebruikmaken van Azure multi-factor Authentication, waarvoor meer dan alleen een gebruikersnaam en wachtwoord voor de verificatie van een account is vereist.</span><span class="sxs-lookup"><span data-stu-id="9ee11-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> 

<span data-ttu-id="9ee11-106">Met authenticatie via meerdere factoren zijn gebruikers verplicht een telefoongesprek te erkennen, typt u een verificatiecode die u in een SMS-bericht ontvangt, of controleert u de verificatie met een app op de smartphone nadat de juiste wachtwoorden zijn ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="9ee11-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="9ee11-107">Ze kunnen zich alleen aanmelden nadat aan deze tweede verificatie factor is voldaan.</span><span class="sxs-lookup"><span data-stu-id="9ee11-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="9ee11-108">In dit artikel wordt beschreven hoe u op tekst gebaseerde verificatie voor een specifiek gebruikersaccount kunt inschakelen en testen.</span><span class="sxs-lookup"><span data-stu-id="9ee11-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="9ee11-109">Er zijn twee fasen voor het instellen van meervoudige verificatie voor een account in uw Microsoft 365 voor Enterprise testomgeving:</span><span class="sxs-lookup"><span data-stu-id="9ee11-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment:</span></span>
  
1. <span data-ttu-id="9ee11-110">Maak de testomgeving Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="9ee11-110">Create the Microsoft 365 for enterprise test environment.</span></span>
    
2. <span data-ttu-id="9ee11-111">Verificatie in meerdere factoren inschakelen en testen voor het account van de gebruiker 2.</span><span class="sxs-lookup"><span data-stu-id="9ee11-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

3. <span data-ttu-id="9ee11-112">Meervoudige verificatie inschakelen en testen met een voorwaardelijk toegangsbeleid (optioneel).</span><span class="sxs-lookup"><span data-stu-id="9ee11-112">Enable and test multi-factor authentication with a conditional access policy (optional).</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="9ee11-114">Ga naar de proefversie van de [test lab](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de microsoft 365 voor Enterprise test lab Guide.</span><span class="sxs-lookup"><span data-stu-id="9ee11-114">Go to [Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="9ee11-115">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="9ee11-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="9ee11-116">Als u de verificatie met meerdere factoren op een lichte manier wilt testen met de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="9ee11-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="9ee11-117">Als u multi-factor Authentication wilt testen in een gesimuleerde onderneming, volgt u de instructies in [Pass-Through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9ee11-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ee11-118">Bij het testen van meervoudige verificatie is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest.</span><span class="sxs-lookup"><span data-stu-id="9ee11-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="9ee11-119">U kunt dit als optie gebruiken, zodat u meervoudige verificatie kunt testen en een proef kunt uitvoeren in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="9ee11-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="9ee11-120">Fase 2: meervoudige verificatie inschakelen en testen voor de account van de gebruiker 2</span><span class="sxs-lookup"><span data-stu-id="9ee11-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="9ee11-121">Schakel meervoudige verificatie in voor de gebruiker 2-account door deze stappen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="9ee11-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="9ee11-122">Open een afzonderlijke, persoonlijke versie van uw browser, ga naar het Microsoft 365-Beheercentrum ( [https://portal.microsoft.com](https://portal.microsoft.com) ) en meld u aan met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="9ee11-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="9ee11-123">Selecteer **Gebruikers > Actieve gebruikers** op de linkernavigatiebalk.</span><span class="sxs-lookup"><span data-stu-id="9ee11-123">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="9ee11-124">Klik in het deelvenster actieve gebruikers op **multi-factor Authentication**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-124">In the Active users pane, click **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="9ee11-125">Selecteer in de lijst de account **gebruiker 2** .</span><span class="sxs-lookup"><span data-stu-id="9ee11-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="9ee11-126">Klik in de sectie **gebruiker 2** onder **snelle stappen**op **inschakelen**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-126">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="9ee11-127">Klik in het dialoogvenster **multi-factor Authentication** inschakelen op **multi-factor Authentication inschakelen**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-127">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="9ee11-128">Klik in het dialoogvenster **updates voltooid** op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-128">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="9ee11-129">Ga naar het tabblad **Microsoft 365-Beheercentrum** , klik in de rechterbovenhoek op het pictogram van het gebruikersaccount en klik vervolgens op **Afmelden**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-129">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="9ee11-130">Sluit uw browser exemplaar.</span><span class="sxs-lookup"><span data-stu-id="9ee11-130">Close your browser instance.</span></span>
   
<span data-ttu-id="9ee11-131">Voltooi de configuratie van de gebruiker 2-account om een tekstbericht te valideren en te testen met behulp van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="9ee11-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="9ee11-132">Open een nieuwe, persoonlijke instantie van uw browser.</span><span class="sxs-lookup"><span data-stu-id="9ee11-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="9ee11-133">Ga naar het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) en meld u aan met de accountnaam en het wachtwoord van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="9ee11-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="9ee11-134">Nadat u zich hebt aangemeld, wordt u gevraagd of u het account wilt instellen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9ee11-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="9ee11-135">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-135">Click **Next**.</span></span>
    
4. <span data-ttu-id="9ee11-136">Op de pagina **extra beveiligingsverificatie** :</span><span class="sxs-lookup"><span data-stu-id="9ee11-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="9ee11-137">Selecteer uw land of regio.</span><span class="sxs-lookup"><span data-stu-id="9ee11-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="9ee11-138">Typ het telefoonnummer van de smartphone waarop SMS-berichten worden ontvangen.</span><span class="sxs-lookup"><span data-stu-id="9ee11-138">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="9ee11-139">Klik bij **methode**op **code per SMS-bericht verzenden**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-139">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="9ee11-140">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-140">Click **Next**.</span></span>
    
6. <span data-ttu-id="9ee11-141">Voer de verificatiecode in van het SMS-bericht dat op uw smartphone is ontvangen en klik op **verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-141">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="9ee11-142">Klik op de pagina **stap 3: de bestaande toepassingen bewaren** op **gereed**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-142">On the **Step 3: Keep your existing applications** page, click **Done**.</span></span>
    
8. <span data-ttu-id="9ee11-143">Als dit de eerste keer is dat u zich aanmeldt met het account van de gebruiker 2, wordt u gevraagd het wachtwoord te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="9ee11-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="9ee11-144">Typ tweemaal het oorspronkelijke wachtwoord en een nieuw wachtwoord en klik vervolgens op **wachtwoord bijwerken en meld u aan**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-144">Type the original password and a new password twice, and then click **Update password and sign in**.</span></span> <span data-ttu-id="9ee11-145">Neem het nieuwe wachtwoord op een veilige locatie op.</span><span class="sxs-lookup"><span data-stu-id="9ee11-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="9ee11-146">U ziet nu de Office-portal voor gebruiker 2 op het tabblad **Start van Microsoft Office** in uw browser.</span><span class="sxs-lookup"><span data-stu-id="9ee11-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="9ee11-147">Fase 3: multi-factor Authentication inschakelen en testen met een voorwaardelijk toegangsbeleid</span><span class="sxs-lookup"><span data-stu-id="9ee11-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="9ee11-148">*Deze fase kan alleen worden gebruikt voor een testomgeving van Microsoft 365 voor bedrijven.*</span><span class="sxs-lookup"><span data-stu-id="9ee11-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="9ee11-149">In deze fase schakelt u meervoudige verificatie in voor het account van de gebruiker 3 met behulp van een groep en een beleid voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="9ee11-149">In this phase you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="9ee11-150">Vervolgens maakt u een nieuwe groep met de naam MFAUsers en voegt u de gebruikers 3-account toe aan de groep.</span><span class="sxs-lookup"><span data-stu-id="9ee11-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="9ee11-151">Ga naar het tabblad **Microsoft 365-Beheercentrum** , klik in het linker navigatiemenu op **groepen** en klik vervolgens op **groepen**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-151">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="9ee11-152">Klik op **groep toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-152">Click **Add a group**.</span></span>
3. <span data-ttu-id="9ee11-153">Selecteer in het deelvenster **een groepstype kiezen** de optie **beveiliging**en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-153">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="9ee11-154">Klik in het deelvenster **basisbeginselen instellen** op **groep maken**en klik vervolgens op **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-154">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="9ee11-155">In het deelvenster **groep controleren en voltooien** , typt u **MFAUsers**en klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-155">In the **Review and finish adding group** pane, type **MFAUsers**, and then click **Next**.</span></span>
6. <span data-ttu-id="9ee11-156">Klik in de lijst met groepen op de groep **MFAUsers** .</span><span class="sxs-lookup"><span data-stu-id="9ee11-156">In the list of groups, click the **MFAUsers** group.</span></span>
7. <span data-ttu-id="9ee11-157">Klik in het deelvenster **MFAUsers** op **leden**en klik op **AllesWeergeven en leden beheren**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-157">In the **MFAUsers** pane, click **Members**, and then click **View all and manage members**.</span></span>
8. <span data-ttu-id="9ee11-158">Klik in het deelvenster **MFAUsers** op **leden toevoegen**, selecteer het account van de **gebruiker 3** en klik op **Opslaan > sluiten > sluiten**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-158">In the **MFAUsers** pane, click **Add members**, select the **User 3** account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="9ee11-159">Vervolgens maakt u een voorwaardelijk toegangsbeleid voor de verificatie van meervoudige authenticatie voor leden van de groep MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="9ee11-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="9ee11-160">Ga op een nieuw tabblad van uw browser naar [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="9ee11-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="9ee11-161">Klik **> beveiligings > voorwaardelijke toegang op Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-161">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="9ee11-162">Klik in het deelvenster **voorwaardelijke toegang – beleidsregels** op **Nieuw beleid**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-162">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
4. <span data-ttu-id="9ee11-163">Typ MFA in het **nieuwe** deelvenster in **naam** **van gebruikersaccounts** .</span><span class="sxs-lookup"><span data-stu-id="9ee11-163">In the **New** pane, type **MFA for user accounts** in **Name**.</span></span>
5. <span data-ttu-id="9ee11-164">Klik in de sectie **opdrachten** op **gebruikers en groepen**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-164">In the **Assignments** section, click **Users and groups**.</span></span>
6. <span data-ttu-id="9ee11-165">Klik op het tabblad **opnemen** van het deelvenster **gebruikers en groepen** op **gebruikers en groepen > gebruikers en groepen selecteren > selecteren**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-165">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
7. <span data-ttu-id="9ee11-166">Klik in het **selectie** deelvenster op de groep **MFAUsers** en klik vervolgens op **selecteren > gereed**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-166">In the **Select** pane, click the **MFAUsers** group, and then click **Select > Done**.</span></span>
8. <span data-ttu-id="9ee11-167">Klik in de sectie **Access-besturingselementen** van het **nieuwe** deelvenster op **toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-167">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="9ee11-168">Klik in het deelvenster **verlenen** op **Meervoudige verificatie vereisen**en klik vervolgens op **selecteren**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-168">In the **Grant** pane, click **Require multi-factor authentication**, and then click **Select**.</span></span>
10. <span data-ttu-id="9ee11-169">Klik in het **nieuwe** deelvenster op **aan** voor inschakelen van het **beleid**en klik vervolgens op **maken**.</span><span class="sxs-lookup"><span data-stu-id="9ee11-169">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="9ee11-170">Sluit de tabbladen **Azure Portal** en **Microsoft 365-Beheercentrum** .</span><span class="sxs-lookup"><span data-stu-id="9ee11-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="9ee11-171">Als u dit beleid wilt testen, meldt u zich af en meldt u zich aan met het account van de gebruiker 3.</span><span class="sxs-lookup"><span data-stu-id="9ee11-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="9ee11-172">U wordt gevraagd MFA te configureren.</span><span class="sxs-lookup"><span data-stu-id="9ee11-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="9ee11-173">Dit demonstreert het toepassen van het MFAUsers-beleid.</span><span class="sxs-lookup"><span data-stu-id="9ee11-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="9ee11-174">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="9ee11-174">Next step</span></span>

<span data-ttu-id="9ee11-175">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="9ee11-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ee11-176">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9ee11-176">See also</span></span>

[<span data-ttu-id="9ee11-177">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="9ee11-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="9ee11-178">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="9ee11-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="9ee11-179">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="9ee11-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="9ee11-180">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="9ee11-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
