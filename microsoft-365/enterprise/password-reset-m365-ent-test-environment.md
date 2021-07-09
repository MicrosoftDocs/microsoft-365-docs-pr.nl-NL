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
ms.openlocfilehash: 13169824866e91c1a09d412a875d2f4ce4391fa8
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339380"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="66875-103">Opnieuw instellen van het wachtwoord voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="66875-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="66875-104">*Deze testlaborator kan alleen worden gebruikt Microsoft 365 voor bedrijfstestomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="66875-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="66875-105">Met de Azure Active Directory (Azure AD) selfservice voor het opnieuw instellen van wachtwoorden (SSPR) kunnen gebruikers hun wachtwoorden of accounts opnieuw instellen of ontgrendelen.</span><span class="sxs-lookup"><span data-stu-id="66875-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span>

<span data-ttu-id="66875-106">In dit artikel wordt beschreven hoe u wachtwoordinstellingen configureert en test in uw Microsoft 365 testomgeving.</span><span class="sxs-lookup"><span data-stu-id="66875-106">This article describes how to configure and test password resets in your Microsoft 365 test environment.</span></span>

<span data-ttu-id="66875-107">Het instellen van SSPR bestaat uit drie fasen:</span><span class="sxs-lookup"><span data-stu-id="66875-107">Setting up SSPR involves three phases:</span></span>
- [<span data-ttu-id="66875-108">Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="66875-108">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="66875-109">Fase 2: wachtwoord terugschrijven inschakelen.</span><span class="sxs-lookup"><span data-stu-id="66875-109">Phase 2: Enable password writeback</span></span>](#phase-2-enable-password-writeback)
- [<span data-ttu-id="66875-110">Fase 3: opnieuw instellen van wachtwoorden configureren en testen</span><span class="sxs-lookup"><span data-stu-id="66875-110">Phase 3: Configure and test password reset</span></span>](#phase-3-configure-and-test-password-reset)
    
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="66875-112">Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, gaat u naar Microsoft 365 voor [enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="66875-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="66875-113">Fase 1: configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="66875-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="66875-114">Volg eerst de instructies in [wachtwoord-hash-synchronisatie](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="66875-114">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="66875-115">De resulterende configuratie ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="66875-115">Your resulting configuration looks like this:</span></span>
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="66875-117">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="66875-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="66875-118">Een proef- of betaald abonnement op Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="66875-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="66875-119">Een vereenvoudigd intranet van de organisatie dat is verbonden met internet, bestaande uit de virtuele DC1-, APP1- en CLIENT1-machines op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="66875-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="66875-120">Azure AD Connect draait op APP1 om het TESTLAD AD DS-domein (Active Directory Domain Services) te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="66875-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="66875-121">Fase 2: wachtwoord terugschrijven inschakelen.</span><span class="sxs-lookup"><span data-stu-id="66875-121">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="66875-122">Volg de instructies in [Fase 2 van testlabrichtlijn Wachtwoord terugschrijven](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="66875-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="66875-123">Voor het gebruik van wachtwoordherstel moet u een wachtwoord voor terugschrijven inschakelen.</span><span class="sxs-lookup"><span data-stu-id="66875-123">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="66875-124">Fase 3: opnieuw instellen van wachtwoorden configureren en testen</span><span class="sxs-lookup"><span data-stu-id="66875-124">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="66875-125">Configureer in deze fase het opnieuw instellen van wachtwoorden in de Azure AD-tenant via groepslidmaatschap en controleer vervolgens of het werkt.</span><span class="sxs-lookup"><span data-stu-id="66875-125">In this phase, configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="66875-126">Schakel eerst het opnieuw instellen van het wachtwoord in voor de accounts in een specifieke groep van Azure AD.</span><span class="sxs-lookup"><span data-stu-id="66875-126">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="66875-127">Open [https://portal.azure.com](https://portal.azure.com)in een privévenster van uw browser en meld u aan met de referenties van uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="66875-127">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="66875-128">Selecteer in de Azure-portal **Azure Active Directory**  >  **nieuwe groep**  >  **Groepen.**</span><span class="sxs-lookup"><span data-stu-id="66875-128">In the Azure portal, select **Azure Active Directory** > **Groups** > **New group**.</span></span>
3. <span data-ttu-id="66875-129">Stel het **groepstype** in op **beveiliging**, **groepsnaam** op **PWReset** en het **lidmaatschapstype** op **toegewezen**.</span><span class="sxs-lookup"><span data-stu-id="66875-129">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span>
4. <span data-ttu-id="66875-130">Selecteer **Leden,** zoek en selecteer **Gebruiker 3,** **selecteer Selecteren** en selecteer vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="66875-130">Select **Members**, find and select **User 3**, select **Select**, and then select **Create**.</span></span>
5. <span data-ttu-id="66875-131">Sluit het **deelvenster** groepen.</span><span class="sxs-lookup"><span data-stu-id="66875-131">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="66875-132">Selecteer in Azure Active Directory deelvenster Wachtwoord **opnieuw instellen** in de linkernavigatie.</span><span class="sxs-lookup"><span data-stu-id="66875-132">In the Azure Active Directory pane, select **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="66875-133">Kies in het deelvenster **wachtwoordherstel-eigenschappen** onder de optie **selfservice wachtwoord opnieuw instellen ingeschakeld\*\*\*\*geselecteerd**.</span><span class="sxs-lookup"><span data-stu-id="66875-133">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="66875-134">Selecteer **Groep selecteren,** selecteer de **groep PWReset** en selecteer **vervolgens Opslaan**  >  **selecteren.**</span><span class="sxs-lookup"><span data-stu-id="66875-134">Select **Select group**, select the **PWReset** group, and then select **Select** > **Save**.</span></span>
9. <span data-ttu-id="66875-135">Sluit het privévenster in uw browser.</span><span class="sxs-lookup"><span data-stu-id="66875-135">Close the private browser instance.</span></span>

<span data-ttu-id="66875-136">Test vervolgens het opnieuw instellen van het wachtwoord voor het account Gebruiker 3.</span><span class="sxs-lookup"><span data-stu-id="66875-136">Next, test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="66875-137">Open een nieuwe privévenster in uw browser en blader naar [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="66875-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
1. <span data-ttu-id="66875-138">Meld u aan met de referenties van het account gebruikers 3.</span><span class="sxs-lookup"><span data-stu-id="66875-138">Sign in with the User 3 account credentials.</span></span>
1. <span data-ttu-id="66875-139">Selecteer **Volgende in Meer informatie** **vereist.**</span><span class="sxs-lookup"><span data-stu-id="66875-139">In **More information required**, select **Next**.</span></span> 
1. <span data-ttu-id="66875-140">Stel bij **Verlies geen toegang tot uw account**, uw mobiele telefoonnummer in als verificatienummer en uw werk- of persoonlijke e-mailaccount als verificatie-e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="66875-140">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
1. <span data-ttu-id="66875-141">Nadat beide zijn geverifieerd, **selecteert** u Ziet er goed uit en sluit u het privé-exemplaar van de browser.</span><span class="sxs-lookup"><span data-stu-id="66875-141">After both are verified, select **Looks good**, and then close the private instance of the browser.</span></span>
1. <span data-ttu-id="66875-142">Ga in een nieuw privébrowser-exemplaar naar [https://aka.ms/sspr](https://aka.ms/sspr) .</span><span class="sxs-lookup"><span data-stu-id="66875-142">In a new private browser instance, go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
1. <span data-ttu-id="66875-143">Voer de accountnaam gebruiker 3 in, voer de tekens in de CAPTCHA in en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="66875-143">Enter the User 3 account name, enter the characters from the CAPTCHA, and then select **Next**.</span></span>
1. <span data-ttu-id="66875-144">Voor **verificatie stap 1** selecteert u **Mijn alternatieve e-mail** en selecteert u vervolgens **E-mail**.</span><span class="sxs-lookup"><span data-stu-id="66875-144">For **verification step 1**, select **Email my alternate email**, and then select **Email**.</span></span> <span data-ttu-id="66875-145">Wanneer u de e-mail ontvangt, voert u de verificatiecode in en selecteert u **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="66875-145">When you receive the email, enter the verification code, and then select **Next**.</span></span>
1. <span data-ttu-id="66875-146">Voer **in Terug naar uw account** een nieuw wachtwoord in voor het Gebruikers 3-account en selecteer **Voltooien.**</span><span class="sxs-lookup"><span data-stu-id="66875-146">In **Get back into your account**, enter a new password for the User 3 account, and then select **Finish**.</span></span> <span data-ttu-id="66875-147">Noteer het gewijzigde wachtwoord van het account van gebruiker 3 en bewaar het op een veilige locatie.</span><span class="sxs-lookup"><span data-stu-id="66875-147">Note the changed password of the User 3 account and store it in a safe location.</span></span>
1. <span data-ttu-id="66875-148">Ga op een afzonderlijk tabblad van dezelfde browser naar [https://admin.microsoft.com](https://admin.microsoft.com), en meld u vervolgens aan met de naam van het account voor gebruikers 3 en het nieuwe wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="66875-148">In a separate tab of the same browser, go to [https://admin.microsoft.com](https://admin.microsoft.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="66875-149">U zou de pagina van **Microsoft Office voor Thuisgebruik** moeten zien.</span><span class="sxs-lookup"><span data-stu-id="66875-149">You should see the **Microsoft Office Home** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="66875-150">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="66875-150">Next step</span></span>

<span data-ttu-id="66875-151">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="66875-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="66875-152">Zie ook</span><span class="sxs-lookup"><span data-stu-id="66875-152">See also</span></span>

[<span data-ttu-id="66875-153">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="66875-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="66875-154">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="66875-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="66875-155">Microsoft 365 enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="66875-155">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)