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
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Samenvatting: Configureer Pass Through-verificatie voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: 4f9941b017f00b40a6ae7e893211131cae51c611
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812022"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="30099-103">Pass Through-verificatie voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="30099-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="30099-104">*Deze testlabrichtlijnen kunnen worden gebruikt voor zowel Microsoft 365 Enterprise- als Office 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="30099-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="30099-105">Organisaties die rechtstreeks gebruik willen maken van hun on-premises infrastructuur met Active Directory Domain Services (AD DS) voor verificatie bij Microsoft-cloudservices en -toepassingen, kunnen Pass Through-verificatie gebruiken.</span><span class="sxs-lookup"><span data-stu-id="30099-105">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="30099-106">In dit artikel wordt beschreven hoe u uw Microsoft 365-testomgeving kunt configureren voor Pass Through-verificatie, met de volgende configuratie als resultaat:</span><span class="sxs-lookup"><span data-stu-id="30099-106">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![De gesimuleerde onderneming in een testomgeving met Pass-Through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="30099-108">Er zijn twee fasen om deze testomgeving in te stellen:</span><span class="sxs-lookup"><span data-stu-id="30099-108">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="30099-109">Maak de Microsoft 365-testomgeving met gesimuleerde onderneming voor wachtwoord-hash-synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="30099-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="30099-110">Configureer Azure AD Connect op APP1 voor Pass Through-verificatie.</span><span class="sxs-lookup"><span data-stu-id="30099-110">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="30099-112">Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen in de stack met Microsoft 365 Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="30099-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="30099-113">Fase 1: Wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="30099-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="30099-114">Volg de instructies in [Wachtwoord-hash-synchronisatie voor Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="30099-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="30099-115">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="30099-115">Here is your resulting configuration.</span></span>
  
![De gesimuleerde onderneming in een testomgeving voor wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="30099-117">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="30099-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="30099-118">Een proef- of betaald abonnement op Microsoft 365 E5 of Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="30099-118">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="30099-119">Een vereenvoudigde organisatie die via intranet is verbonden met internet, bestaande uit drie virtuele machines (DC1, APP1 en CLIENT1) op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="30099-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="30099-120">Azure AD Connect wordt uitgevoerd op APP1 om het AD DS-domein TESTLAB periodiek te synchroniseren met de Azure AD-tenant van uw Microsoft 365- of Office 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="30099-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="30099-121">Fase 2: Azure AD Connect op APP1 configureren voor Pass Through-verificatie</span><span class="sxs-lookup"><span data-stu-id="30099-121">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="30099-122">In deze fase configureert u Azure AD Connect op APP1 voor het gebruik van Pass Through-verificatie. Vervolgens controleert u of dit werkt.</span><span class="sxs-lookup"><span data-stu-id="30099-122">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="30099-123">Azure AD Connect configureren op APP1</span><span class="sxs-lookup"><span data-stu-id="30099-123">Configure Azure AD Connect on APP1</span></span>

1.  <span data-ttu-id="30099-124">Ga naar [Azure Portal](https://portal.azure.com), meld u aan met uw globale-beheerdersaccount en maak vervolgens verbinding met APP1 via het account TESTLAB\Gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="30099-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="30099-125">Voer Azure AD Connect uit vanaf het bureaublad van APP1.</span><span class="sxs-lookup"><span data-stu-id="30099-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3.  <span data-ttu-id="30099-126">Klik op de **welkomstpagina** op **Configureren**.</span><span class="sxs-lookup"><span data-stu-id="30099-126">On the **Welcome page**, click **Configure**.</span></span>

4.  <span data-ttu-id="30099-127">Klik op de pagina Extra taken op **Gebruikersaanmelding wijzigen**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="30099-127">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.  <span data-ttu-id="30099-128">Voer op de pagina **Verbinding maken met Azure AD** de referenties in van uw globale beheerdersaccount en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="30099-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.  <span data-ttu-id="30099-129">Klik op de pagina **Gebruikersaanmelding** op **Pass Through-verificatie**en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="30099-129">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.  <span data-ttu-id="30099-130">Klik op de pagina **Gereed om te configureren** op **Configureren**.</span><span class="sxs-lookup"><span data-stu-id="30099-130">On the **Ready to configure** page, click **Configure**.</span></span>

8.  <span data-ttu-id="30099-131">Klik op de pagina **Configuratie voltooid** op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="30099-131">On the **Configuration complete** page, click **Exit**.</span></span>

9.  <span data-ttu-id="30099-132">Klik vanuit Azure Portal in het linkerdeelvenster op **Azure Active Directory > Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="30099-132">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**.</span></span> <span data-ttu-id="30099-133">Controleer of de functie **Pass Through-verificatie** wordt weergegeven als **Ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="30099-133">Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10. <span data-ttu-id="30099-134">Klik op **Pass Through-verificatie**.</span><span class="sxs-lookup"><span data-stu-id="30099-134">Click **Pass-through authentication**.</span></span> <span data-ttu-id="30099-135">In het deelvenster **Pass Through-verificatie** worden de servers weergegeven waarop uw verificatie-agenten zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="30099-135">The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed.</span></span> <span data-ttu-id="30099-136">U ziet nu APP1 in de lijst.</span><span class="sxs-lookup"><span data-stu-id="30099-136">You should see APP1 in the list.</span></span> <span data-ttu-id="30099-137">Sluit het deelvenster **Pass Through-verificatie**.</span><span class="sxs-lookup"><span data-stu-id="30099-137">Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="30099-138">Test vervolgens of u zich kunt aanmelden bij uw abonnement met <strong>gebruiker1@testlab.</strong>\<uw openbare domein> gebruikersnaam van het account Gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="30099-138">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="30099-139">Meld u af bij APP1 en meld u weer aan met een ander account.</span><span class="sxs-lookup"><span data-stu-id="30099-139">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="30099-140">Wanneer u om een gebruikersnaam en wachtwoord wordt gevraagd, typt u <strong>gebruiker1@testlab.</strong>\<uw openbare domein> en het wachtwoord voor Gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="30099-140">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain> and the User1 password.</span></span> <span data-ttu-id="30099-141">U moet u nu kunnen aanmelden als Gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="30099-141">You should successfully sign in as User1.</span></span>

<span data-ttu-id="30099-142">Zoals u ziet, heeft Gebruiker1 machtigingen van een domeinbeheerder voor het AD DS-domein TESTLAB, maar Gebruiker1 is geen globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="30099-142">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="30099-143">Daarom wordt het pictogram van de **-beheerder** niet weergegeven als optie.</span><span class="sxs-lookup"><span data-stu-id="30099-143">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="30099-144">Dit is de resulterende configuratie:</span><span class="sxs-lookup"><span data-stu-id="30099-144">Here is your resulting configuration:</span></span>

![De gesimuleerde onderneming in een testomgeving met Pass-Through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="30099-146">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="30099-146">This configuration consists of:</span></span>

- <span data-ttu-id="30099-147">Een proef- of betaald abonnement op Microsoft 365 E5 of Office 365 E5 met het DNS-domein Testlab.\<uw domeinnaam> geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="30099-147">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="30099-148">Een vereenvoudigde organisatie die via intranet is verbonden met internet, bestaande uit drie virtuele machines (DC1, APP1 en CLIENT1) op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="30099-148">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="30099-149">Er wordt een verificatieagent uitgevoerd op APP1 voor het verwerken van Pass Through-verificatieaanvragen van de Azure AD-tenant van uw Microsoft 365- of Office 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="30099-149">An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Microsoft 365 or Office 365 subscription.</span></span>

## <a name="next-step"></a><span data-ttu-id="30099-150">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="30099-150">Next step</span></span>

<span data-ttu-id="30099-151">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="30099-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="30099-152">Zie ook</span><span class="sxs-lookup"><span data-stu-id="30099-152">See also</span></span>

[<span data-ttu-id="30099-153">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="30099-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="30099-154">Microsoft 365 Enterprise implementeren</span><span class="sxs-lookup"><span data-stu-id="30099-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="30099-155">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="30099-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
