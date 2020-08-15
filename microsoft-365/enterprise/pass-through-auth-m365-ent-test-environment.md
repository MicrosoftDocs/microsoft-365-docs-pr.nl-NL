---
title: Pass Through-verificatie voor uw Microsoft 365-testomgeving
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
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Samenvatting: Configureer Pass Through-verificatie voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: 1b5540f2e16ac0267bf33faf42defe6bca6d25cd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695192"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="9f270-103">Pass Through-verificatie voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="9f270-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="9f270-104">*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="9f270-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="9f270-105">Organisaties die rechtstreeks gebruik willen maken van hun on-premises infrastructuur met Active Directory Domain Services (AD DS) voor verificatie bij Microsoft-cloudservices en -toepassingen, kunnen Pass Through-verificatie gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9f270-105">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="9f270-106">In dit artikel wordt beschreven hoe u uw Microsoft 365-testomgeving kunt configureren voor Pass Through-verificatie, met de volgende configuratie als resultaat:</span><span class="sxs-lookup"><span data-stu-id="9f270-106">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![De gesimuleerde onderneming in een testomgeving met Pass-Through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="9f270-108">Er zijn twee fasen om deze testomgeving in te stellen:</span><span class="sxs-lookup"><span data-stu-id="9f270-108">There are two phases to setting up this test environment:</span></span>

1.    <span data-ttu-id="9f270-109">Maak de Microsoft 365-testomgeving met gesimuleerde onderneming voor wachtwoord-hash-synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="9f270-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="9f270-110">Configureer Azure AD Connect op APP1 voor Pass Through-verificatie.</span><span class="sxs-lookup"><span data-stu-id="9f270-110">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="9f270-112">Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="9f270-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="9f270-113">Fase 1: Configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="9f270-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="9f270-114">Volg de instructies in [wachtwoord-hash-synchronisatie voor Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="9f270-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="9f270-115">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="9f270-115">Here is your resulting configuration.</span></span>
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="9f270-117">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="9f270-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="9f270-118">Microsoft 365 E5-proefabonnement of betaald abonnement.</span><span class="sxs-lookup"><span data-stu-id="9f270-118">Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="9f270-119">Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="9f270-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="9f270-120">Azure AD Connect wordt uitgevoerd op APP1 om het AD DS-domein TESTLAB te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="9f270-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="9f270-121">Fase 2: Azure AD Connect op APP1 configureren voor Pass Through-verificatie</span><span class="sxs-lookup"><span data-stu-id="9f270-121">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="9f270-122">In deze fase configureert u Azure AD Connect op APP1 voor het gebruik van Pass Through-verificatie. Vervolgens controleert u of dit werkt.</span><span class="sxs-lookup"><span data-stu-id="9f270-122">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="9f270-123">Azure AD Connect configureren op APP1</span><span class="sxs-lookup"><span data-stu-id="9f270-123">Configure Azure AD Connect on APP1</span></span>

1.    <span data-ttu-id="9f270-124">Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\Gebruiker1-account.</span><span class="sxs-lookup"><span data-stu-id="9f270-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.    <span data-ttu-id="9f270-125">Voer Azure AD Connect uit vanaf het bureaublad van APP1.</span><span class="sxs-lookup"><span data-stu-id="9f270-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3.    <span data-ttu-id="9f270-126">Klik op de **welkomstpagina** op **Configureren**.</span><span class="sxs-lookup"><span data-stu-id="9f270-126">On the **Welcome page**, click **Configure**.</span></span>

4.    <span data-ttu-id="9f270-127">Klik op de pagina Extra taken op **Gebruikersaanmelding wijzigen**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9f270-127">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.    <span data-ttu-id="9f270-128">Voer op de pagina **Verbinding maken met Azure AD** de referenties in van uw globale beheerdersaccount en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9f270-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.    <span data-ttu-id="9f270-129">Klik op de pagina **Gebruikersaanmelding** op **Pass Through-verificatie**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9f270-129">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.    <span data-ttu-id="9f270-130">Klik op de pagina **Gereed om te configureren** op **Configureren**.</span><span class="sxs-lookup"><span data-stu-id="9f270-130">On the **Ready to configure** page, click **Configure**.</span></span>

8.    <span data-ttu-id="9f270-131">Klik op de pagina **Configuratie voltooid** op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="9f270-131">On the **Configuration complete** page, click **Exit**.</span></span>

9.    <span data-ttu-id="9f270-132">Klik vanuit Azure Portal in het linkerdeelvenster op **Azure Active Directory > Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="9f270-132">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**.</span></span> <span data-ttu-id="9f270-133">Controleer of de functie **Pass Through-verificatie** wordt weergegeven als **Ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="9f270-133">Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10.    <span data-ttu-id="9f270-134">Klik op **Pass Through-verificatie**.</span><span class="sxs-lookup"><span data-stu-id="9f270-134">Click **Pass-through authentication**.</span></span> <span data-ttu-id="9f270-135">In het deelvenster **Pass Through-verificatie** worden de servers weergegeven waarop uw verificatie-agenten zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="9f270-135">The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed.</span></span> <span data-ttu-id="9f270-136">U ziet nu APP1 in de lijst.</span><span class="sxs-lookup"><span data-stu-id="9f270-136">You should see APP1 in the list.</span></span> <span data-ttu-id="9f270-137">Sluit het deelvenster **Pass Through-verificatie**.</span><span class="sxs-lookup"><span data-stu-id="9f270-137">Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="9f270-138">Test vervolgens de mogelijkheid om u aan te melden bij uw abonnement met het <strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="9f270-138">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="9f270-139">van het gebruiker1-account.</span><span class="sxs-lookup"><span data-stu-id="9f270-139">user name of the User1 account.</span></span>

1. <span data-ttu-id="9f270-140">Meld u af bij APP1 en meld u weer aan met een ander account.</span><span class="sxs-lookup"><span data-stu-id="9f270-140">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="9f270-141">Wanneer u om een gebruikersnaam en wachtwoord wordt gevraagd, typt u <strong>gebruiker1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="9f270-141">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="9f270-142">en het wachtwoord voor gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="9f270-142">and the User1 password.</span></span> <span data-ttu-id="9f270-143">U moet u nu kunnen aanmelden als Gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="9f270-143">You should successfully sign in as User1.</span></span>

<span data-ttu-id="9f270-144">Zoals u ziet, heeft Gebruiker1 de machtigingen van een domeinbeheerder voor het TESTLAB AD DS-domein, maar Gebruiker1 is geen globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="9f270-144">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="9f270-145">Daarom wordt het pictogram van de **Beheerder** niet weergegeven als optie.</span><span class="sxs-lookup"><span data-stu-id="9f270-145">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="9f270-146">Dit is de resulterende configuratie:</span><span class="sxs-lookup"><span data-stu-id="9f270-146">Here is your resulting configuration:</span></span>

![De gesimuleerde onderneming met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="9f270-148">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="9f270-148">This configuration consists of:</span></span>

- <span data-ttu-id="9f270-149">Een Microsoft 365 E5-proefabonnement of betaalde abonnementen met de DNS-domein testlab.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="9f270-149">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name></span></span> <span data-ttu-id="9f270-150">geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="9f270-150">registered.</span></span>
- <span data-ttu-id="9f270-151">Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="9f270-151">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="9f270-152">Er wordt een verificatieagent uitgevoerd op APP1 voor het verwerken van Pass Through-verificatieaanvragen van de Azure AD-tenant van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="9f270-152">An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="next-step"></a><span data-ttu-id="9f270-153">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="9f270-153">Next step</span></span>

<span data-ttu-id="9f270-154">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="9f270-154">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f270-155">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9f270-155">See also</span></span>

[<span data-ttu-id="9f270-156">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="9f270-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="9f270-157">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="9f270-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="9f270-158">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="9f270-158">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
