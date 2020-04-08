---
title: Opnieuw instellen van het wachtwoord voor uw Microsoft 365-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Samenvatting: configureer en test het opnieuw instellen van het wachtwoord voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: c8d5ed0c7feac98afd3230a305f4ab1f850ca7f8
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42805679"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="f2310-103">Opnieuw instellen van het wachtwoord voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="f2310-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="f2310-104">*Deze testlabrichtlijn kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="f2310-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="f2310-105">Met de Azure Active Directory (Azure AD) selfservice voor het opnieuw instellen van wachtwoorden (SSPR) kunnen gebruikers hun wachtwoorden of accounts opnieuw instellen of ontgrendelen.</span><span class="sxs-lookup"><span data-stu-id="f2310-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="f2310-106">In dit artikel wordt beschreven hoe u wachtwoordinstellingen in uw Microsoft 365-testomgeving in drie fasen kunt configureren en testen:</span><span class="sxs-lookup"><span data-stu-id="f2310-106">This article describes how you can configure and test password resets in your Microsoft 365 test environment in three phases:</span></span>

1.  <span data-ttu-id="f2310-107">Maak de Microsoft 365 Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="f2310-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="f2310-108">Wachtwoord terugschrijven inschakelen.</span><span class="sxs-lookup"><span data-stu-id="f2310-108">Enable password writeback.</span></span>
3.  <span data-ttu-id="f2310-109">Configureer en test het opnieuw instellen van het wachtwoord voor het gebruikersaccount 3.</span><span class="sxs-lookup"><span data-stu-id="f2310-109">Configure and test password reset for the User 3 account.</span></span>
    
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="f2310-111">Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen over de Microsoft 365 Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="f2310-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="f2310-112">Fase 1: configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="f2310-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="f2310-113">Volg eerst de instructies in [wachtwoord-hash-synchronisatie](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f2310-113">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="f2310-114">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="f2310-114">Here is your resulting configuration.</span></span>
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="f2310-116">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="f2310-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="f2310-117">Een betaald of proefabonnement op Microsoft 365 E5 of Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="f2310-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="f2310-118">Een vereenvoudigde organisatie die via intranet is verbonden met internet, bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="f2310-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="f2310-119">Azure AD Connect wordt uitgevoerd op APP1 om het AD DS-domein TESTLAB periodiek te synchroniseren met de Azure AD-tenant van uw Microsoft 365- of Office 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="f2310-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="f2310-120">Fase 2: wachtwoord terugschrijven inschakelen.</span><span class="sxs-lookup"><span data-stu-id="f2310-120">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="f2310-121">Volg de instructies in [Fase 2 van testlabrichtlijn Wachtwoord terugschrijven](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="f2310-121">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="f2310-122">Voor het gebruik van wachtwoordherstel moet u een wachtwoord voor terugschrijven inschakelen.</span><span class="sxs-lookup"><span data-stu-id="f2310-122">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="f2310-123">Fase 3: opnieuw instellen van wachtwoorden configureren en testen</span><span class="sxs-lookup"><span data-stu-id="f2310-123">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="f2310-124">In deze fase configureert u het opnieuw instellen van wachtwoorden in de Azure AD-Tenant via groepslidmaatschap. Controleer vervolgens of dit werkt.</span><span class="sxs-lookup"><span data-stu-id="f2310-124">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="f2310-125">Schakel eerst het opnieuw instellen van het wachtwoord in voor de accounts in een specifieke groep van Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f2310-125">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="f2310-126">Open [https://portal.azure.com](https://portal.azure.com)in een privévenster van uw browser en meld u aan met de referenties van uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="f2310-126">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="f2310-127">Klik in de Azure-portal op **Azure Active Directory > Nieuwe groep**.</span><span class="sxs-lookup"><span data-stu-id="f2310-127">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="f2310-128">Stel het **groepstype** in op **beveiliging**, **groepsnaam** op **PWReset** en het **lidmaatschapstype** op **toegewezen**.</span><span class="sxs-lookup"><span data-stu-id="f2310-128">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span> 
4. <span data-ttu-id="f2310-129">Klik op **leden**, zoek en selecteer **gebruiker 3**, klik op **selecteren**en klik vervolgens op **maken**.</span><span class="sxs-lookup"><span data-stu-id="f2310-129">Click **Members**, find and select **User 3**, and then click **Select**, and then click **Create**.</span></span>
5. <span data-ttu-id="f2310-130">Sluit het **deelvenster** groepen.</span><span class="sxs-lookup"><span data-stu-id="f2310-130">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="f2310-131">Klik in het deelvenster Azure Active Directory op **opnieuw instellen van wachtwoorden** in de linkernavigatiebalk.</span><span class="sxs-lookup"><span data-stu-id="f2310-131">In the Azure Active Directory pane, click **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="f2310-132">Kies in het deelvenster **wachtwoordherstel-eigenschappen** onder de optie **selfservice wachtwoord opnieuw instellen ingeschakeld\*\*\*\*geselecteerd**.</span><span class="sxs-lookup"><span data-stu-id="f2310-132">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="f2310-133">Klik op **groep selecteren**, selecteer de groep **PWReset** en klik vervolgens op **selecteren > opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f2310-133">Click **Select group**, select the **PWReset** group, and then click **Select > Save**.</span></span>
9. <span data-ttu-id="f2310-134">Sluit het privévenster in uw browser.</span><span class="sxs-lookup"><span data-stu-id="f2310-134">Close the private browser instance.</span></span>

<span data-ttu-id="f2310-135">Configureer en test vervolgens het opnieuw instellen van het wachtwoord voor het gebruikersaccount 3.</span><span class="sxs-lookup"><span data-stu-id="f2310-135">Next, you test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="f2310-136">Open een nieuwe privévenster in uw browser en blader naar [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="f2310-136">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="f2310-137">Meld u aan met de referenties van het account gebruikers 3.</span><span class="sxs-lookup"><span data-stu-id="f2310-137">Sign in with the User 3 account credentials.</span></span>
3. <span data-ttu-id="f2310-138">Klik in **meer informatie vereist**op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="f2310-138">In **More information required**, click **Next**.</span></span> 
5. <span data-ttu-id="f2310-139">Stel bij **Verlies geen toegang tot uw account**, uw mobiele telefoonnummer in als verificatienummer en uw werk- of persoonlijke e-mailaccount als verificatie-e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="f2310-139">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
7. <span data-ttu-id="f2310-140">Nadat beide zijn geverifieerd, klikt u op **Ziet er goed uit** en sluit u de privévenster van de browser.</span><span class="sxs-lookup"><span data-stu-id="f2310-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
8. <span data-ttu-id="f2310-141">Open een nieuw privévenster en blader naar [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="f2310-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
9. <span data-ttu-id="f2310-142">Typ de accountnaam van gebruiker 3, typ de tekens uit de CAPTCHA en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="f2310-142">Type the User 3 account name, type the characters from the CAPTCHA, and then click **Next**.</span></span>
10. <span data-ttu-id="f2310-143">Klik voor **verificatiestap 1** op **Naar mijn alternatieve e-mail e-mailen** en klik vervolgens **op E-mail**.</span><span class="sxs-lookup"><span data-stu-id="f2310-143">For **verification step 1**, click **Email my alternate email**, and then click **Email**.</span></span> <span data-ttu-id="f2310-144">Wanneer u het e-mailbericht ontvangt, typt u de verificatiecode en klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="f2310-144">When you receive the email, type the verification code, and then click **Next**.</span></span>
11. <span data-ttu-id="f2310-145">Typ in **Ga terug naar uw account** een nieuw wachtwoord voor het account van Gebruiker 3 en klik vervolgens op **voltooien**.</span><span class="sxs-lookup"><span data-stu-id="f2310-145">In **Get back into your account**, type a new password for the User 3 account, and then click **Finish**.</span></span> <span data-ttu-id="f2310-146">Noteer het gewijzigde wachtwoord van het account van gebruiker 3 en bewaar het op een veilige locatie.</span><span class="sxs-lookup"><span data-stu-id="f2310-146">Note the changed password of the User 3 account and store it in a safe location.</span></span>
12. <span data-ttu-id="f2310-147">Ga op een afzonderlijk tabblad van dezelfde browser naar [https://portal.office.com](https://portal.office.com), en meld u vervolgens aan met de naam van het account voor gebruikers 3 en het nieuwe wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="f2310-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="f2310-148">U zou de pagina van **Microsoft Office voor Thuisgebruik** moeten zien.</span><span class="sxs-lookup"><span data-stu-id="f2310-148">You should see the **Microsoft Office Home** page.</span></span>

<span data-ttu-id="f2310-149">Zie de stap [Vereenvoudig het opnieuw instellen van wachtwoorden](identity-secure-your-passwords.md#identity-pw-reset) in de Identiteitsfase voor informatie en koppelingen om het opnieuw instellen van wachtwoorden in productie te configureren.</span><span class="sxs-lookup"><span data-stu-id="f2310-149">See the [Simplify password resets](identity-secure-your-passwords.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="f2310-150">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="f2310-150">Next step</span></span>

<span data-ttu-id="f2310-151">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="f2310-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2310-152">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f2310-152">See also</span></span>

[<span data-ttu-id="f2310-153">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="f2310-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f2310-154">Microsoft 365 Enterprise implementeren</span><span class="sxs-lookup"><span data-stu-id="f2310-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f2310-155">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="f2310-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
