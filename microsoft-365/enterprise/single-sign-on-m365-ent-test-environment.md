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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Samenvatting: configureer en test naadloze eenmalige aanmelding via Azure AD voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: 7fcbc82cfb35c598358c8160dd06427c2a9c59a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904862"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="6a761-103">Naadloze eenmalige aanmelding via Azure AD voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="6a761-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="6a761-104">*Deze testlaborator kan worden gebruikt voor zowel Microsoft 365 voor bedrijven als Office 365 Enterprise testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="6a761-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="6a761-105">Azure AD Seamless Single Sign-On (Seamless SSO) meldt zich automatisch aan bij gebruikers wanneer ze zich op hun pc's of apparaten die zijn verbonden met hun organisatienetwerk.</span><span class="sxs-lookup"><span data-stu-id="6a761-105">Azure AD Seamless Single Sign-On (Seamless SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network.</span></span> <span data-ttu-id="6a761-106">Naadloze eenmalige aanmelding via Azure AD biedt gebruikers eenvoudige toegang tot toepassingen in de Cloud, zonder dat ze hier extra onderdelen op locatie voor nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="6a761-106">Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="6a761-107">In dit artikel wordt beschreven hoe u uw Microsoft 365 voor Azure AD Seamless SSO configureert.</span><span class="sxs-lookup"><span data-stu-id="6a761-107">This article describes how to configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="6a761-108">Het instellen van Azure AD Seamless SSO omvat twee fasen:</span><span class="sxs-lookup"><span data-stu-id="6a761-108">Setting up Azure AD Seamless SSO involves two phases:</span></span>
- [<span data-ttu-id="6a761-109">Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="6a761-109">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="6a761-110">Fase 2: Configureer Azure AD Connect op APP1 voor naadloze eenmalige aanmelding via Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6a761-110">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="6a761-112">Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, gaat u naar Microsoft 365 voor [enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="6a761-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="6a761-113">Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="6a761-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="6a761-114">Volg de instructies in [wachtwoord-hash-synchronisatie voor Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6a761-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="6a761-115">De resulterende configuratie ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="6a761-115">Your resulting configuration looks like this:</span></span>
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="6a761-117">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="6a761-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="6a761-118">Een proef- of betaald abonnement op Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="6a761-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="6a761-119">Een vereenvoudigd intranet van de organisatie dat is verbonden met internet, bestaande uit de virtuele DC1-, APP1- en CLIENT1-machines op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="6a761-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="6a761-120">Azure AD Verbinding maken wordt uitgevoerd op APP1 om het AD DS-domein (TESTLAB Active Directory Domain Services) regelmatig te synchroniseren met de Azure AD-tenant van uw Microsoft 365 abonnement.</span><span class="sxs-lookup"><span data-stu-id="6a761-120">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="6a761-121">Fase 2: Configureer Azure AD Connect op APP1 voor naadloze eenmalige aanmelding via Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6a761-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="6a761-122">In deze fase configureert u Azure AD Verbinding maken op APP1 voor Azure AD Seamless SSO en controleert u of het werkt.</span><span class="sxs-lookup"><span data-stu-id="6a761-122">In this phase, configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="6a761-123">Azure AD Connect op APP1 configureren</span><span class="sxs-lookup"><span data-stu-id="6a761-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="6a761-124">Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\Gebruiker1-account.</span><span class="sxs-lookup"><span data-stu-id="6a761-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="6a761-125">Voer Azure AD-Verbinding maken.</span><span class="sxs-lookup"><span data-stu-id="6a761-125">From the APP1 desktop, run Azure AD Connect.</span></span>

3. <span data-ttu-id="6a761-126">Selecteer **configureren op de** **welkomstpagina.**</span><span class="sxs-lookup"><span data-stu-id="6a761-126">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="6a761-127">Selecteer op **de pagina** Extra taken de optie Gebruikers **aanmelden wijzigen** en selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6a761-127">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>

5. <span data-ttu-id="6a761-128">Voer op **Verbinding maken pagina Naar Azure AD** de referenties van uw globale beheerdersaccount in en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="6a761-128">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="6a761-129">Selecteer op **de pagina Gebruiker** aanmelden de optie Eén aanmelding **inschakelen** en selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6a761-129">On the **User sign-in** page, select **Enable single sign-on**, and then select **Next**.</span></span>

7. <span data-ttu-id="6a761-130">Selecteer op **de pagina Eén aanmelding inschakelen** de optie Referenties **invoeren.**</span><span class="sxs-lookup"><span data-stu-id="6a761-130">On the **Enable single sign-on** page, select **Enter credentials**.</span></span>

8. <span data-ttu-id="6a761-131">Voer in **Windows-beveiliging** dialoogvenster **gebruiker1** en het wachtwoord van het gebruikersaccount in, selecteer **OK** en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="6a761-131">In the **Windows Security** dialog box, enter **user1** and the password of the user1 account, select **OK**, and then select **Next**.</span></span>

9. <span data-ttu-id="6a761-132">Selecteer **configureren** op de pagina Gereed voor **configureren.**</span><span class="sxs-lookup"><span data-stu-id="6a761-132">On the **Ready to Configure** page, select **Configure**.</span></span>

10. <span data-ttu-id="6a761-133">Selecteer op **de pagina Configuratie** voltooid de optie **Afsluiten.**</span><span class="sxs-lookup"><span data-stu-id="6a761-133">On the **Configuration complete** page, select **Exit**.</span></span>

11. <span data-ttu-id="6a761-134">Selecteer in de Azure-portal in het linkerdeelvenster **Azure Active Directory**  >  **Azure AD-Verbinding maken.**</span><span class="sxs-lookup"><span data-stu-id="6a761-134">From the Azure portal, in the left pane, select **Azure Active Directory** > **Azure AD Connect**.</span></span> <span data-ttu-id="6a761-135">Controleer of de **Naadloze eenmalige aanmelding**-functie wordt weergegeven als **Ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="6a761-135">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="6a761-136">Test vervolgens de mogelijkheid om u aan te melden bij uw abonnement met de <strong>user1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="6a761-136">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="6a761-137">van het gebruiker1-account.</span><span class="sxs-lookup"><span data-stu-id="6a761-137">user name of the User1 account.</span></span>

1. <span data-ttu-id="6a761-138">Selecteer in Internet Explorer op APP1 het pictogram Instellingen en selecteer **vervolgens Internetopties.**</span><span class="sxs-lookup"><span data-stu-id="6a761-138">From Internet Explorer on APP1, select the settings icon, and then select **Internet Options**.</span></span>
 
2. <span data-ttu-id="6a761-139">Selecteer **in Internetopties** het **tabblad** Beveiliging.</span><span class="sxs-lookup"><span data-stu-id="6a761-139">In **Internet Options**, select the **Security** tab.</span></span>

3. <span data-ttu-id="6a761-140">Selecteer **Lokaal intranet** en selecteer vervolgens **Sites.**</span><span class="sxs-lookup"><span data-stu-id="6a761-140">Select **Local intranet**, and then select **Sites**.</span></span>

4. <span data-ttu-id="6a761-141">Selecteer Geavanceerd in  **lokaal intranet.**</span><span class="sxs-lookup"><span data-stu-id="6a761-141">In **Local intranet**, select **Advanced**.</span></span>

5. <span data-ttu-id="6a761-142">In **Deze website toevoegen aan de zone**, voert u https **<span>://</span>autologon.microsoftazuread-sso.com**, selecteer **Sluiten**  >    >  **OK**  >  **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="6a761-142">In **Add this website to the zone**, enter **https <span>://</span>autologon.microsoftazuread-sso.com**, select **Add** > **Close** > **OK** > **OK**.</span></span>

6. <span data-ttu-id="6a761-143">Meld u af en meld u vervolgens weer aan met een ander account.</span><span class="sxs-lookup"><span data-stu-id="6a761-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="6a761-144">Wanneer u wordt gevraagd u aan te melden, geeft <strong>u user1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="6a761-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="6a761-145">en selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="6a761-145">name, and then select **Next**.</span></span> <span data-ttu-id="6a761-146">U zou zich moeten kunnen aanmelden als Gebruiker1 zonder dat u om een wachtwoord wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="6a761-146">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="6a761-147">Dit bewijst dat de naadloze eenmalige aanmelding via Azure AD werkt.</span><span class="sxs-lookup"><span data-stu-id="6a761-147">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="6a761-148">Zoals u ziet, heeft Gebruiker1 de machtigingen van een domeinbeheerder voor het TESTLAB AD DS-domein, maar is Gebruiker1 geen globale beheerder voor Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6a761-148">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="6a761-149">Daarom wordt het pictogram van de **Beheerder** niet weergegeven als optie.</span><span class="sxs-lookup"><span data-stu-id="6a761-149">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="6a761-150">Dit is de resulterende configuratie:</span><span class="sxs-lookup"><span data-stu-id="6a761-150">Here is your resulting configuration:</span></span>

![De gesimuleerde onderneming met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="6a761-152">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="6a761-152">This configuration consists of:</span></span>

- <span data-ttu-id="6a761-153">Een Microsoft 365 E5 of betaalde abonnementen met het DNS-domeintestlab.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="6a761-153">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<*your domain name*></span></span> <span data-ttu-id="6a761-154">geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="6a761-154">registered.</span></span>
- <span data-ttu-id="6a761-155">Een vereenvoudigd intranet van de organisatie dat is verbonden met internet, bestaande uit de virtuele DC1-, APP1- en CLIENT1-machines op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="6a761-155">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="6a761-156">Azure AD Connect draait op APP1 om de lijst van accounts en groepen van de Azure AD-tenant van uw Microsoft 365-abonnement te synchroniseren met het TESTLAB AD DS-domein.</span><span class="sxs-lookup"><span data-stu-id="6a761-156">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="6a761-157">Azure AD Seamless SSO is ingeschakeld, zodat computers op het gesimuleerde intranet zich kunnen aanmelden bij Microsoft 365 cloudbronnen zonder een gebruikersaccountwachtwoord op te geven.</span><span class="sxs-lookup"><span data-stu-id="6a761-157">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifying a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="6a761-158">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="6a761-158">Next step</span></span>

<span data-ttu-id="6a761-159">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="6a761-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a761-160">Zie ook</span><span class="sxs-lookup"><span data-stu-id="6a761-160">See also</span></span>

[<span data-ttu-id="6a761-161">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="6a761-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6a761-162">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="6a761-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6a761-163">Microsoft 365 enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="6a761-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)