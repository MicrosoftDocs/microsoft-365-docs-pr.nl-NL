---
title: Naadloze eenmalige aanmelding via Azure AD voor uw Microsoft 365-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
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
description: 'Samenvatting: configureer en test naadloze eenmalige aanmelding via Azure AD voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: ba3f943a53f05c452a8e01e40bb6924dc42a866e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636866"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="82aad-103">Naadloze eenmalige aanmelding via Azure AD voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="82aad-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="82aad-104">*Deze testlabrichtlijnen kunnen worden gebruikt voor zowel Microsoft 365 Enterprise- als Office 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="82aad-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="82aad-105">Met de naadloze eenmalige aanmelding via Azure AD worden gebruikers automatisch aangemeld wanneer ze gebruikmaken van pc's of apparaten die zijn verbonden met het bedrijfsnetwerk.</span><span class="sxs-lookup"><span data-stu-id="82aad-105">Azure AD Seamless Single Sign-On (SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network.</span></span> <span data-ttu-id="82aad-106">Naadloze eenmalige aanmelding via Azure AD biedt gebruikers eenvoudige toegang tot toepassingen in de Cloud, zonder dat ze hier extra onderdelen op locatie voor nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="82aad-106">Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="82aad-107">In dit artikel wordt beschreven hoe u uw Microsoft 365-testomgeving kunt configureren voor naadloze eenmalige aanmelding via Azure AD.</span><span class="sxs-lookup"><span data-stu-id="82aad-107">This article describes how you can configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="82aad-108">Er zijn twee fasen om dit in te stellen:</span><span class="sxs-lookup"><span data-stu-id="82aad-108">There are two phases to setting this up:</span></span>

1.    <span data-ttu-id="82aad-109">Maak de Microsoft 365-testomgeving voor uw gesimuleerde onderneming aan met wachtwoord-hash-synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="82aad-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="82aad-110">Configureer Azure Active Connect op APP1 voor naadloze eenmalige aanmelding via Azure AD.</span><span class="sxs-lookup"><span data-stu-id="82aad-110">Configure Azure AD Connect on APP1 for Azure AD Seamless SSO.</span></span>
    
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="82aad-112">Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen over de Microsoft 365 Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="82aad-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="82aad-113">Fase 1: Configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="82aad-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="82aad-114">Volg de instructies in [wachtwoord-hash-synchronisatie voor Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="82aad-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="82aad-115">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="82aad-115">Here is your resulting configuration.</span></span>
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="82aad-117">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="82aad-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="82aad-118">Een betaald of proefabonnement op Microsoft 365 E5 of Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="82aad-118">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="82aad-119">Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="82aad-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="82aad-120">Azure AD Connect draait op APP1 om het TESTLAD AD DS-domein (Active Directory Domain Services) periodiek te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="82aad-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="82aad-121">Fase 2: Configureer Azure AD Connect op APP1 voor naadloze eenmalige aanmelding via Azure AD.</span><span class="sxs-lookup"><span data-stu-id="82aad-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="82aad-122">In deze fase configureert u Azure AD Connect op APP1 voor het gebruik van naadloze eenmalige aanmelding via Azure AD, waarna u controleert of dit werkt.</span><span class="sxs-lookup"><span data-stu-id="82aad-122">In this phase, you configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="82aad-123">Azure AD Connect op APP1 configureren</span><span class="sxs-lookup"><span data-stu-id="82aad-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="82aad-124">Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\Gebruiker1-account.</span><span class="sxs-lookup"><span data-stu-id="82aad-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="82aad-125">Voer Azure AD Connect uit vanaf het bureaublad van APP1.</span><span class="sxs-lookup"><span data-stu-id="82aad-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3. <span data-ttu-id="82aad-126">Klik op de **welkomstpagina** op **Configureren**.</span><span class="sxs-lookup"><span data-stu-id="82aad-126">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="82aad-127">Klik op de pagina **Aanvullende taken** op **Gebruikersaanmelding wijzigen**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="82aad-127">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="82aad-128">Voer op de pagina **Verbinding maken met Azure AD** de referenties van uw globale beheerdersaccount in en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="82aad-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="82aad-129">Selecteer op de pagina **Gebruikersaanmelding** de optie **Eenmalige aanmelding inschakelen** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="82aad-129">On the **User sign-in** page, select **Enable single sign-on**, and then click **Next**.</span></span>

7. <span data-ttu-id="82aad-130">Klik op de pagina **Eenmalige aanmelding inschakelen** op **Referenties invoeren**.</span><span class="sxs-lookup"><span data-stu-id="82aad-130">On the **Enable single sign-on** page, click **Enter credentials**.</span></span>

8. <span data-ttu-id="82aad-131">Typ in het dialoogvenster **Windows Security** in **gebruiker1** en het wachtwoord van het Gebruiker1-account en klik vervolgens op **OK**.</span><span class="sxs-lookup"><span data-stu-id="82aad-131">In the **Windows Security** dialog box, type **user1** and the password of the user1 account, and then click **OK**.</span></span> <span data-ttu-id="82aad-132">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="82aad-132">Click **Next**.</span></span>

9. <span data-ttu-id="82aad-133">Klik op de pagina **Gereed voor configureren** op **Configureren**.</span><span class="sxs-lookup"><span data-stu-id="82aad-133">On the **Ready to Configure** page, click **Configure**.</span></span>

10. <span data-ttu-id="82aad-134">Klik op de pagina **Configuratie voltooid** op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="82aad-134">On the **Configuration complete** page, click **Exit**.</span></span>

11. <span data-ttu-id="82aad-135">Klik in het Azure-portal in het linkerdeelvenster op **Azure Active Directory > Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="82aad-135">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**.</span></span> <span data-ttu-id="82aad-136">Controleer of de **Naadloze eenmalige aanmelding**-functie wordt weergegeven als **Ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="82aad-136">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="82aad-137">Test vervolgens of u zich kunt aanmelden bij uw abonnement met <strong>gebruiker1@testlab.</strong>\<uw openbare domein> gebruikersnaam van het Gebruiker1-account.</span><span class="sxs-lookup"><span data-stu-id="82aad-137">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="82aad-138">Klik in Internet Explorer via APP1 op het instellingenpictogram en vervolgens op **Internet-opties**.</span><span class="sxs-lookup"><span data-stu-id="82aad-138">From Internet Explorer on APP1, click the settings icon, and then click **Internet Options**.</span></span>
 
2. <span data-ttu-id="82aad-139">Klik bij **Internet-opties** op het tabblad **Beveiliging**.</span><span class="sxs-lookup"><span data-stu-id="82aad-139">In **Internet Options**, click the **Security** tab.</span></span>

3. <span data-ttu-id="82aad-140">Klik op **Lokaal intranet** en vervolgens op **Sites**.</span><span class="sxs-lookup"><span data-stu-id="82aad-140">Click **Local intranet**, and then click **Sites**.</span></span>

4. <span data-ttu-id="82aad-141">Klik in **Lokaal intranet** op **Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="82aad-141">In **Local intranet**, click **Advanced**.</span></span>

5. <span data-ttu-id="82aad-142">Bij **Deze website aan de zone toevoegen** typt u **https<span>://</span>autologon.microsoftazuread-sso.com** en klik op **Toevoegen > Afsluiten > OK > OK**.</span><span class="sxs-lookup"><span data-stu-id="82aad-142">In **Add this website to the zone**, type **https<span>://</span>autologon.microsoftazuread-sso.com**, click **Add > Close > OK > OK**.</span></span>

6. <span data-ttu-id="82aad-143">Meld u af en meld u vervolgens weer aan met een ander account.</span><span class="sxs-lookup"><span data-stu-id="82aad-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="82aad-144">Wanneer u wordt gevraagd om u aan te melden, vult u in <strong>user1@testlab.</strong>\<uw openbare domein> naam en klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="82aad-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<your public domain> name, and then click **Next**.</span></span> <span data-ttu-id="82aad-145">U zou zich moeten kunnen aanmelden als Gebruiker1 zonder dat u om een wachtwoord wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="82aad-145">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="82aad-146">Dit bewijst dat de naadloze eenmalige aanmelding via Azure AD werkt.</span><span class="sxs-lookup"><span data-stu-id="82aad-146">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="82aad-147">Zoals u ziet, heeft Gebruiker1 de machtigingen van een domeinbeheerder voor het TESTLAB AD DS-domein, maar is Gebruiker1 geen globale beheerder voor Azure AD.</span><span class="sxs-lookup"><span data-stu-id="82aad-147">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="82aad-148">Daarom wordt het pictogram van de **Beheerder** niet weergegeven als optie.</span><span class="sxs-lookup"><span data-stu-id="82aad-148">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="82aad-149">Dit is de resulterende configuratie:</span><span class="sxs-lookup"><span data-stu-id="82aad-149">Here is your resulting configuration:</span></span>

![De gesimuleerde onderneming met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
<span data-ttu-id="82aad-151">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="82aad-151">This configuration consists of:</span></span>

- <span data-ttu-id="82aad-152">Een betaald of proefabonnement op Microsoft 365 E5 of Office 365 E5 met het DNS-domein testlab.\<uw domeinnaam> geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="82aad-152">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="82aad-153">Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="82aad-153">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="82aad-154">Azure AD Connect draait op APP1 om de lijst van accounts en groepen van de Azure AD-tenant van uw Microsoft 365-abonnement te synchroniseren met het TESTLAB AD DS-domein.</span><span class="sxs-lookup"><span data-stu-id="82aad-154">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="82aad-155">De naadloze eenmalige aanmelding van Azure is ingeschakeld, zodat computers op het gesimuleerde intranet zich kunnen aanmelden bij Microsoft 365 Cloud-bronnen, zonder het wachtwoord voor een gebruikersaccount in te hoeven vullen.</span><span class="sxs-lookup"><span data-stu-id="82aad-155">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifing a user account password.</span></span>

<span data-ttu-id="82aad-156">Zie de stap [Vereenvoudig gebruikersaanmelding](identity-secure-your-passwords.md#identity-sso) in de identiteitsfase voor informatie over en links voor het configureren van de naadloze eenmalige aanmelding via Azure AD.</span><span class="sxs-lookup"><span data-stu-id="82aad-156">See the [Simplify user sign-in](identity-secure-your-passwords.md#identity-sso) step in the Identity phase for information and links to configure Azure AD Seamless SSO in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="82aad-157">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="82aad-157">Next step</span></span>

<span data-ttu-id="82aad-158">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="82aad-158">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="82aad-159">Zie ook</span><span class="sxs-lookup"><span data-stu-id="82aad-159">See also</span></span>

[<span data-ttu-id="82aad-160">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="82aad-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="82aad-161">Microsoft 365 Enterprise implementeren</span><span class="sxs-lookup"><span data-stu-id="82aad-161">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="82aad-162">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="82aad-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


