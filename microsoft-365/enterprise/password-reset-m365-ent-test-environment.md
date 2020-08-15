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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Samenvatting: configureer en test het opnieuw instellen van het wachtwoord voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: 98e6b8d8432c86e9d1c432128ed6d223da83610e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686534"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a8b80-103">Opnieuw instellen van het wachtwoord voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="a8b80-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a8b80-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="a8b80-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="a8b80-105">Met de Azure Active Directory (Azure AD) selfservice voor het opnieuw instellen van wachtwoorden (SSPR) kunnen gebruikers hun wachtwoorden of accounts opnieuw instellen of ontgrendelen.</span><span class="sxs-lookup"><span data-stu-id="a8b80-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="a8b80-106">In dit artikel wordt beschreven hoe u wachtwoordinstellingen in uw Microsoft 365-testomgeving in drie fasen kunt configureren en testen:</span><span class="sxs-lookup"><span data-stu-id="a8b80-106">This article describes how you can configure and test password resets in your Microsoft 365 test environment in three phases:</span></span>

1.    <span data-ttu-id="a8b80-107">Maak de testomgeving Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a8b80-107">Create the Microsoft 365 for enterprise test environment.</span></span>
2.  <span data-ttu-id="a8b80-108">Wachtwoord terugschrijven inschakelen.</span><span class="sxs-lookup"><span data-stu-id="a8b80-108">Enable password writeback.</span></span>
3.    <span data-ttu-id="a8b80-109">Configureer en test het opnieuw instellen van het wachtwoord voor het gebruikersaccount 3.</span><span class="sxs-lookup"><span data-stu-id="a8b80-109">Configure and test password reset for the User 3 account.</span></span>
    
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a8b80-111">Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="a8b80-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="a8b80-112">Fase 1: configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="a8b80-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="a8b80-113">Volg eerst de instructies in [wachtwoord-hash-synchronisatie](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a8b80-113">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="a8b80-114">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="a8b80-114">Here is your resulting configuration.</span></span>
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="a8b80-116">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="a8b80-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="a8b80-117">Een proef- of betaald abonnement op Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a8b80-117">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="a8b80-118">Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="a8b80-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="a8b80-119">Azure AD Connect draait op APP1 om het TESTLAD AD DS-domein (Active Directory Domain Services) te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="a8b80-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="a8b80-120">Fase 2: wachtwoord terugschrijven inschakelen.</span><span class="sxs-lookup"><span data-stu-id="a8b80-120">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="a8b80-121">Volg de instructies in [Fase 2 van testlabrichtlijn Wachtwoord terugschrijven](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="a8b80-121">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="a8b80-122">Voor het gebruik van wachtwoordherstel moet u een wachtwoord voor terugschrijven inschakelen.</span><span class="sxs-lookup"><span data-stu-id="a8b80-122">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="a8b80-123">Fase 3: opnieuw instellen van wachtwoorden configureren en testen</span><span class="sxs-lookup"><span data-stu-id="a8b80-123">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="a8b80-124">In deze fase configureert u het opnieuw instellen van wachtwoorden in de Azure AD-Tenant via groepslidmaatschap. Controleer vervolgens of dit werkt.</span><span class="sxs-lookup"><span data-stu-id="a8b80-124">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="a8b80-125">Schakel eerst het opnieuw instellen van het wachtwoord in voor de accounts in een specifieke groep van Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a8b80-125">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="a8b80-126">Open [https://portal.azure.com](https://portal.azure.com)in een privévenster van uw browser en meld u aan met de referenties van uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="a8b80-126">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="a8b80-127">Klik in de Azure-portal op **Azure Active Directory > Nieuwe groep**.</span><span class="sxs-lookup"><span data-stu-id="a8b80-127">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="a8b80-128">Stel het **groepstype** in op **beveiliging**, **groepsnaam** op **PWReset** en het **lidmaatschapstype** op **toegewezen**.</span><span class="sxs-lookup"><span data-stu-id="a8b80-128">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span> 
4. <span data-ttu-id="a8b80-129">Klik op **leden**, zoek en selecteer **gebruiker 3**, klik op **selecteren**en klik vervolgens op **maken**.</span><span class="sxs-lookup"><span data-stu-id="a8b80-129">Click **Members**, find and select **User 3**, and then click **Select**, and then click **Create**.</span></span>
5. <span data-ttu-id="a8b80-130">Sluit het **deelvenster** groepen.</span><span class="sxs-lookup"><span data-stu-id="a8b80-130">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="a8b80-131">Klik in het deelvenster Azure Active Directory op **opnieuw instellen van wachtwoorden** in de linkernavigatiebalk.</span><span class="sxs-lookup"><span data-stu-id="a8b80-131">In the Azure Active Directory pane, click **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="a8b80-132">Kies in het deelvenster **wachtwoordherstel-eigenschappen** onder de optie **selfservice wachtwoord opnieuw instellen ingeschakeld\*\*\*\*geselecteerd**.</span><span class="sxs-lookup"><span data-stu-id="a8b80-132">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="a8b80-133">Klik op **groep selecteren**, selecteer de groep **PWReset** en klik vervolgens op **selecteren > opslaan**.</span><span class="sxs-lookup"><span data-stu-id="a8b80-133">Click **Select group**, select the **PWReset** group, and then click **Select > Save**.</span></span>
9. <span data-ttu-id="a8b80-134">Sluit het privévenster in uw browser.</span><span class="sxs-lookup"><span data-stu-id="a8b80-134">Close the private browser instance.</span></span>

<span data-ttu-id="a8b80-135">Configureer en test vervolgens het opnieuw instellen van het wachtwoord voor het gebruikersaccount 3.</span><span class="sxs-lookup"><span data-stu-id="a8b80-135">Next, you test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="a8b80-136">Open een nieuwe privévenster in uw browser en blader naar [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="a8b80-136">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="a8b80-137">Meld u aan met de referenties van het account gebruikers 3.</span><span class="sxs-lookup"><span data-stu-id="a8b80-137">Sign in with the User 3 account credentials.</span></span>
3. <span data-ttu-id="a8b80-138">Klik in **meer informatie vereist**op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="a8b80-138">In **More information required**, click **Next**.</span></span> 
5. <span data-ttu-id="a8b80-139">Stel bij **Verlies geen toegang tot uw account**, uw mobiele telefoonnummer in als verificatienummer en uw werk- of persoonlijke e-mailaccount als verificatie-e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="a8b80-139">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
7. <span data-ttu-id="a8b80-140">Nadat beide zijn geverifieerd, klikt u op **Ziet er goed uit** en sluit u de privévenster van de browser.</span><span class="sxs-lookup"><span data-stu-id="a8b80-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
8. <span data-ttu-id="a8b80-141">Open een nieuw privévenster en blader naar [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="a8b80-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
9. <span data-ttu-id="a8b80-142">Typ de accountnaam van gebruiker 3, typ de tekens uit de CAPTCHA en klik vervolgens op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="a8b80-142">Type the User 3 account name, type the characters from the CAPTCHA, and then click **Next**.</span></span>
10. <span data-ttu-id="a8b80-143">Klik voor **verificatiestap 1** op **Naar mijn alternatieve e-mail e-mailen** en klik vervolgens **op E-mail**.</span><span class="sxs-lookup"><span data-stu-id="a8b80-143">For **verification step 1**, click **Email my alternate email**, and then click **Email**.</span></span> <span data-ttu-id="a8b80-144">Wanneer u het e-mailbericht ontvangt, typt u de verificatiecode en klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="a8b80-144">When you receive the email, type the verification code, and then click **Next**.</span></span>
11. <span data-ttu-id="a8b80-145">Typ in **Ga terug naar uw account** een nieuw wachtwoord voor het account van Gebruiker 3 en klik vervolgens op **voltooien**.</span><span class="sxs-lookup"><span data-stu-id="a8b80-145">In **Get back into your account**, type a new password for the User 3 account, and then click **Finish**.</span></span> <span data-ttu-id="a8b80-146">Noteer het gewijzigde wachtwoord van het account van gebruiker 3 en bewaar het op een veilige locatie.</span><span class="sxs-lookup"><span data-stu-id="a8b80-146">Note the changed password of the User 3 account and store it in a safe location.</span></span>
12. <span data-ttu-id="a8b80-147">Ga op een afzonderlijk tabblad van dezelfde browser naar [https://portal.office.com](https://portal.office.com), en meld u vervolgens aan met de naam van het account voor gebruikers 3 en het nieuwe wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="a8b80-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="a8b80-148">U zou de pagina van **Microsoft Office voor Thuisgebruik** moeten zien.</span><span class="sxs-lookup"><span data-stu-id="a8b80-148">You should see the **Microsoft Office Home** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="a8b80-149">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="a8b80-149">Next step</span></span>

<span data-ttu-id="a8b80-150">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="a8b80-150">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8b80-151">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a8b80-151">See also</span></span>

[<span data-ttu-id="a8b80-152">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="a8b80-152">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a8b80-153">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="a8b80-153">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a8b80-154">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="a8b80-154">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
