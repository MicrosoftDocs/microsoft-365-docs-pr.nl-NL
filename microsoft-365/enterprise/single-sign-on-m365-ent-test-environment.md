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
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487598"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="80de2-103">Naadloze eenmalige aanmelding via Azure AD voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="80de2-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="80de2-104">*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="80de2-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="80de2-105">Met behulp van Sign-On naadloze eenmalige aanmelding van Azure ACTIVEert u automatisch gebruikers op hun Pc's of apparaten die zijn verbonden met het netwerk van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="80de2-105">Azure AD Seamless Single Sign-On (Seamless SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network.</span></span> <span data-ttu-id="80de2-106">Naadloze eenmalige aanmelding via Azure AD biedt gebruikers eenvoudige toegang tot toepassingen in de Cloud, zonder dat ze hier extra onderdelen op locatie voor nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="80de2-106">Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="80de2-107">In dit artikel wordt uitgelegd hoe u uw Microsoft 365-testomgeving voor Azure AD perfect SSO kunt configureren.</span><span class="sxs-lookup"><span data-stu-id="80de2-107">This article describes how to configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="80de2-108">Het instellen van Azure AD perfect SSO omvat twee fasen:</span><span class="sxs-lookup"><span data-stu-id="80de2-108">Setting up Azure AD Seamless SSO involves two phases:</span></span>
- [<span data-ttu-id="80de2-109">Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="80de2-109">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="80de2-110">Fase 2: Configureer Azure AD Connect op APP1 voor naadloze eenmalige aanmelding via Azure AD.</span><span class="sxs-lookup"><span data-stu-id="80de2-110">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="80de2-112">Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.</span><span class="sxs-lookup"><span data-stu-id="80de2-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="80de2-113">Fase 1: Configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="80de2-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="80de2-114">Volg de instructies in [wachtwoord-hash-synchronisatie voor Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="80de2-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="80de2-115">De uiteindelijke configuratie ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="80de2-115">Your resulting configuration looks like this:</span></span>
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="80de2-117">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="80de2-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="80de2-118">Een proef- of betaald abonnement op Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="80de2-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="80de2-119">Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines op een subnet van een Azure virtueel netwerk.</span><span class="sxs-lookup"><span data-stu-id="80de2-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="80de2-120">Azure AD Connect wordt uitgevoerd op APP1 om periodiek het TESTLAB Active Directory Domain Services (AD DS) te synchroniseren met de Azure AD-Tenant van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="80de2-120">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="80de2-121">Fase 2: Configureer Azure AD Connect op APP1 voor naadloze eenmalige aanmelding via Azure AD.</span><span class="sxs-lookup"><span data-stu-id="80de2-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="80de2-122">In deze fase configureert u Azure AD Connect op APP1 voor Azure AD perfect SSO en controleert u vervolgens of het werkt.</span><span class="sxs-lookup"><span data-stu-id="80de2-122">In this phase, configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="80de2-123">Azure AD Connect op APP1 configureren</span><span class="sxs-lookup"><span data-stu-id="80de2-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="80de2-124">Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\Gebruiker1-account.</span><span class="sxs-lookup"><span data-stu-id="80de2-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="80de2-125">Voer in het APP1-bureaublad Azure AD Connect uit.</span><span class="sxs-lookup"><span data-stu-id="80de2-125">From the APP1 desktop, run Azure AD Connect.</span></span>

3. <span data-ttu-id="80de2-126">Selecteer **configureren**op de **welkomstpagina**.</span><span class="sxs-lookup"><span data-stu-id="80de2-126">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="80de2-127">Selecteer op de pagina **extra taken** de optie **gebruikersaanmelding wijzigen**en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="80de2-127">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>

5. <span data-ttu-id="80de2-128">Voer op de pagina **verbinding maken met Azure AD** de referenties van uw globale beheerdersaccount in en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="80de2-128">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="80de2-129">Selecteer op de aanmeldingspagina van de **gebruiker** de optie **eenmalige aanmelding inschakelen**en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="80de2-129">On the **User sign-in** page, select **Enable single sign-on**, and then select **Next**.</span></span>

7. <span data-ttu-id="80de2-130">Selecteer op de pagina **eenmalige aanmelding inschakelen** de optie **referenties invoeren**.</span><span class="sxs-lookup"><span data-stu-id="80de2-130">On the **Enable single sign-on** page, select **Enter credentials**.</span></span>

8. <span data-ttu-id="80de2-131">Voer in het dialoogvenster **Windows** -beveiliging **gebruiker1** in en het wachtwoord van het account gebruiker1, selecteer **OK**en selecteer vervolgens **volgende**.</span><span class="sxs-lookup"><span data-stu-id="80de2-131">In the **Windows Security** dialog box, enter **user1** and the password of the user1 account, select **OK**, and then select **Next**.</span></span>

9. <span data-ttu-id="80de2-132">Selecteer **configureren**op de pagina **klaar voor de configuratie** .</span><span class="sxs-lookup"><span data-stu-id="80de2-132">On the **Ready to Configure** page, select **Configure**.</span></span>

10. <span data-ttu-id="80de2-133">Selecteer op de pagina **configuratie voltooid** de optie **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="80de2-133">On the **Configuration complete** page, select **Exit**.</span></span>

11. <span data-ttu-id="80de2-134">Selecteer in het linkerdeelvenster van de Azure-Portal **Azure Active Directory**  >  **Azure AD CONNECT**.</span><span class="sxs-lookup"><span data-stu-id="80de2-134">From the Azure portal, in the left pane, select **Azure Active Directory** > **Azure AD Connect**.</span></span> <span data-ttu-id="80de2-135">Controleer of de **Naadloze eenmalige aanmelding**-functie wordt weergegeven als **Ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="80de2-135">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="80de2-136">Test vervolgens de mogelijkheid om u aan te melden bij uw abonnement met het <strong>user1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="80de2-136">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="80de2-137">van het gebruiker1-account.</span><span class="sxs-lookup"><span data-stu-id="80de2-137">user name of the User1 account.</span></span>

1. <span data-ttu-id="80de2-138">Selecteer in Internet Explorer op APP1 het pictogram instellingen en selecteer vervolgens **Internet opties**.</span><span class="sxs-lookup"><span data-stu-id="80de2-138">From Internet Explorer on APP1, select the settings icon, and then select **Internet Options**.</span></span>
 
2. <span data-ttu-id="80de2-139">Klik in **Internet opties**op het tabblad **beveiliging** .</span><span class="sxs-lookup"><span data-stu-id="80de2-139">In **Internet Options**, select the **Security** tab.</span></span>

3. <span data-ttu-id="80de2-140">Selecteer **Lokaal intranet**en selecteer vervolgens **sites**.</span><span class="sxs-lookup"><span data-stu-id="80de2-140">Select **Local intranet**, and then select **Sites**.</span></span>

4. <span data-ttu-id="80de2-141">Selecteer in het **lokale intranet**de optie **Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="80de2-141">In **Local intranet**, select **Advanced**.</span></span>

5. <span data-ttu-id="80de2-142">Voer in het dialoogvenster **deze website aan de zone toevoegen** **https<span>://</span>AutoLogon.microsoftazuread-SSO.com**in en selecteer **toevoegen**  >  **sluiten**  >  **OK**  >  **OK**.</span><span class="sxs-lookup"><span data-stu-id="80de2-142">In **Add this website to the zone**, enter **https<span>://</span>autologon.microsoftazuread-sso.com**, select **Add** > **Close** > **OK** > **OK**.</span></span>

6. <span data-ttu-id="80de2-143">Meld u af en meld u vervolgens weer aan met een ander account.</span><span class="sxs-lookup"><span data-stu-id="80de2-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="80de2-144">Wanneer u wordt gevraagd u aan te melden, geeft u <strong>user1@testlab op.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="80de2-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="80de2-145">naam en selecteer vervolgens **volgende**.</span><span class="sxs-lookup"><span data-stu-id="80de2-145">name, and then select **Next**.</span></span> <span data-ttu-id="80de2-146">U zou zich moeten kunnen aanmelden als Gebruiker1 zonder dat u om een wachtwoord wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="80de2-146">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="80de2-147">Dit bewijst dat de naadloze eenmalige aanmelding via Azure AD werkt.</span><span class="sxs-lookup"><span data-stu-id="80de2-147">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="80de2-148">Zoals u ziet, heeft Gebruiker1 de machtigingen van een domeinbeheerder voor het TESTLAB AD DS-domein, maar is Gebruiker1 geen globale beheerder voor Azure AD.</span><span class="sxs-lookup"><span data-stu-id="80de2-148">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="80de2-149">Daarom wordt het pictogram van de **Beheerder** niet weergegeven als optie.</span><span class="sxs-lookup"><span data-stu-id="80de2-149">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="80de2-150">Dit is de resulterende configuratie:</span><span class="sxs-lookup"><span data-stu-id="80de2-150">Here is your resulting configuration:</span></span>

![De gesimuleerde onderneming met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="80de2-152">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="80de2-152">This configuration consists of:</span></span>

- <span data-ttu-id="80de2-153">Een Microsoft 365 E5-proefabonnement of betaalde abonnementen met de DNS-domein testlab.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="80de2-153">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<*your domain name*></span></span> <span data-ttu-id="80de2-154">geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="80de2-154">registered.</span></span>
- <span data-ttu-id="80de2-155">Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines op een subnet van een Azure virtueel netwerk.</span><span class="sxs-lookup"><span data-stu-id="80de2-155">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="80de2-156">Azure AD Connect draait op APP1 om de lijst van accounts en groepen van de Azure AD-tenant van uw Microsoft 365-abonnement te synchroniseren met het TESTLAB AD DS-domein.</span><span class="sxs-lookup"><span data-stu-id="80de2-156">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="80de2-157">Naadloze SSO van Azure AD is ingeschakeld, zodat computers in het gesimuleerde intranet zich kunnen aanmelden bij Microsoft 365 Cloud-bronnen zonder dat het wachtwoord van een gebruiker wordt opgegeven.</span><span class="sxs-lookup"><span data-stu-id="80de2-157">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifying a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="80de2-158">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="80de2-158">Next step</span></span>

<span data-ttu-id="80de2-159">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="80de2-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="80de2-160">Zie ook</span><span class="sxs-lookup"><span data-stu-id="80de2-160">See also</span></span>

[<span data-ttu-id="80de2-161">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="80de2-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="80de2-162">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="80de2-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="80de2-163">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="80de2-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
