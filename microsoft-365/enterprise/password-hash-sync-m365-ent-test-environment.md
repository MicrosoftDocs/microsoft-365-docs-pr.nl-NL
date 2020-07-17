---
title: Wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
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
- seo-marvel-apr2020
ms.assetid: ''
description: 'Overzicht: Wachtwoord-hash-synchronisatie en -aanmelding configureren en demonstreren voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: 2d5fbd3ed2a2afb994fc36f5ba3a15a8c55a274e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819386"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="0a213-103">Wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="0a213-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="0a213-104">*Deze testlabrichtlijnen kunnen worden gebruikt voor zowel Microsoft 365 Enterprise- als Office 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="0a213-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="0a213-105">Veel organisaties maken gebruik van Azure AD Connect en wachtwoord-hash-synchronisatie om de accounts in hun AD DS-forest (Active Directory Domain Services) op locatie te synchroniseren met de accounts in de Azure AD-tenant van hun Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="0a213-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> <span data-ttu-id="0a213-106">In dit artikel wordt beschreven hoe u uw Microsoft 365-testomgeving kunt configureren voor wachtwoord-hash-synchronisatie, met de volgende configuratie als resultaat:</span><span class="sxs-lookup"><span data-stu-id="0a213-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="0a213-108">Er zijn twee fasen om deze testomgeving in te stellen:</span><span class="sxs-lookup"><span data-stu-id="0a213-108">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="0a213-109">De Microsoft 365 Enterprise-testomgeving voor een gesimuleerde onderneming maken.</span><span class="sxs-lookup"><span data-stu-id="0a213-109">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="0a213-110">Azure AD Connect op APP1 installeren en configureren.</span><span class="sxs-lookup"><span data-stu-id="0a213-110">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="0a213-111">Ga naar de [Testlabrichtlijnen-stack van Microsoft 365](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="0a213-111">Go to [Microsoft 365 Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="0a213-112">Fase 1: De Microsoft 365-testomgeving voor een gesimuleerde onderneming maken</span><span class="sxs-lookup"><span data-stu-id="0a213-112">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="0a213-113">Volg de instructies in [Basisconfiguratie voor gesimuleerde onderneming in Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="0a213-113">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="0a213-114">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="0a213-114">Here is your resulting configuration.</span></span>
  
![De basisconfiguratie voor een gesimuleerde onderneming](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="0a213-116">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="0a213-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="0a213-117">Een betaald of proefabonnement op Microsoft 365 E5 of Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="0a213-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="0a213-118">Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 in een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="0a213-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="0a213-119">DC1 is een domeincontroller voor het testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="0a213-119">DC1 is a domain controller for the testlab.\<your public domain name></span></span> <span data-ttu-id="0a213-120">AD DS-domein.</span><span class="sxs-lookup"><span data-stu-id="0a213-120">AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="0a213-121">Fase 2: Het testlab-domein maken en registreren</span><span class="sxs-lookup"><span data-stu-id="0a213-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="0a213-122">In deze fase voegt u een openbaar DNS-domein toe en voegt u dit toe aan uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="0a213-122">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="0a213-123">Werk eerst met uw openbare DNS-registratieprovider om een nieuwe openbare DNS-domeinnaam te maken op basis van uw huidige domeinnaam en deze toe te voegen aan uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="0a213-123">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your subscription.</span></span> <span data-ttu-id="0a213-124">U wordt aangeraden de naam **testlab.**\<your public domain> te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0a213-124">We recommend using the name **testlab.**\<your public domain>.</span></span> <span data-ttu-id="0a213-125">Als de naam van uw openbare domein bijvoorbeeld **<span>contoso</span>. com** is, voegt u de openbare domeinnaam **<span>testlab</span>.contoso.com** toe.</span><span class="sxs-lookup"><span data-stu-id="0a213-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="0a213-126">Vervolgens voegt u het **testlab.**\<your public domain>-</span><span class="sxs-lookup"><span data-stu-id="0a213-126">Next, you add the **testlab.**\<your public domain></span></span> <span data-ttu-id="0a213-127">domein toe aan uw betaalde of proefabonnement op Microsoft 365 of Office 365 door het domeinregistratieproces te doorlopen.</span><span class="sxs-lookup"><span data-stu-id="0a213-127">domain to your Microsoft 365 or Office 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="0a213-128">Dit bestaat uit het toevoegen van extra DNS-records aan het **testlab.**\<your public domain>-</span><span class="sxs-lookup"><span data-stu-id="0a213-128">This consists of adding additional DNS records to the **testlab.**\<your public domain></span></span> <span data-ttu-id="0a213-129">domein.</span><span class="sxs-lookup"><span data-stu-id="0a213-129">domain.</span></span> <span data-ttu-id="0a213-130">Zie voor meer informatie [Een domein aan Office 365 toevoegen](https://docs.microsoft.com/office365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="0a213-130">For more information, see [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain).</span></span> 

<span data-ttu-id="0a213-131">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="0a213-131">Here is your resulting configuration.</span></span>
  
![De registratie van de naam van uw testlab-domein](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="0a213-133">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="0a213-133">This configuration consists of:</span></span>

- <span data-ttu-id="0a213-134">Een betaald of proefabonnement op Microsoft 365 E5 of Office 365 E5 met het DNS-domein testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="0a213-134">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your public domain name></span></span> <span data-ttu-id="0a213-135">geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="0a213-135">registered.</span></span>
- <span data-ttu-id="0a213-136">Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="0a213-136">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="0a213-137">U ziet hoe de testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="0a213-137">Notice how the testlab.\<your public domain name></span></span> <span data-ttu-id="0a213-138">nu is:</span><span class="sxs-lookup"><span data-stu-id="0a213-138">is now:</span></span>

- <span data-ttu-id="0a213-139">Ondersteund wordt door openbare DNS-records.</span><span class="sxs-lookup"><span data-stu-id="0a213-139">Supported by public DNS records.</span></span>
- <span data-ttu-id="0a213-140">Geregistreerd is in de Microsoft 365-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="0a213-140">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="0a213-141">Het AD DS-domein op uw gesimuleerde intranet is.</span><span class="sxs-lookup"><span data-stu-id="0a213-141">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="0a213-142">Fase 3: Azure AD Connect op APP1 installeren</span><span class="sxs-lookup"><span data-stu-id="0a213-142">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="0a213-143">In deze fase installeert en configureert u het Azure AD Connect-hulpprogramma op APP1, waarna u controleert of dit werkt.</span><span class="sxs-lookup"><span data-stu-id="0a213-143">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="0a213-144">Eerst installeert en configureert u Azure AD Connect op APP1.</span><span class="sxs-lookup"><span data-stu-id="0a213-144">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="0a213-145">Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\\Gebruiker1-account.</span><span class="sxs-lookup"><span data-stu-id="0a213-145">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="0a213-146">Open, vanaf het bureaublad van APP1, een Windows PowerShell-opdrachtprompt op beheerdersniveau en voer deze opdrachten uit om verbeterde beveiliging van Internet Explorer uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="0a213-146">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="0a213-147">Klik in de taakbalk op **Internet Explorer** en ga naar [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span><span class="sxs-lookup"><span data-stu-id="0a213-147">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="0a213-148">Klik op de pagina Microsoft Azure Active Directory Connect op **Download** en klik vervolgens op **Uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="0a213-148">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="0a213-149">Klik op de pagina **Welkom bij Azure AD Connect** op **Ik ga akkoord** en vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0a213-149">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="0a213-150">Klik op de pagina **Express-instellingen** op **Express-instellingen gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="0a213-150">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="0a213-151">Typ op de pagina **Verbinding maken met Azure AD** de naam van het globale beheerdersaccount in bij **Gebruikersnaam** en het wachtwoord bij **Wachtwoord** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0a213-151">On the **Connect to Azure AD** page, type your global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="0a213-152">Typ op de pagina **Verbinding maken met AD DS** **TESTLAB\\Gebruiker1** in bij **Gebruikersnaam,** het wachtwoord bij **Wachtwoord** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0a213-152">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="0a213-153">Klik op de pagina **Gereed voor configureren** op **Installeren**.</span><span class="sxs-lookup"><span data-stu-id="0a213-153">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="0a213-154">Klik op de pagina **Configuratie voltooid** op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="0a213-154">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="0a213-155">Ga in Internet Explorer naar het Microsoft 365-beheercentrum ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="0a213-155">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="0a213-156">Selecteer **Gebruikers > Actieve gebruikers** op de linkernavigatiebalk.</span><span class="sxs-lookup"><span data-stu-id="0a213-156">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="0a213-157">Bekijk het account met de naam **Gebruiker1**.</span><span class="sxs-lookup"><span data-stu-id="0a213-157">Note the account named **User1**.</span></span> <span data-ttu-id="0a213-158">Dit account is afkomstig uit het TESTLAB AD DS-domein en is het bewijs dat de adreslijstsynchronisatie heeft gewerkt.</span><span class="sxs-lookup"><span data-stu-id="0a213-158">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="0a213-159">Klik op het **Gebruiker1**-account en klik vervolgens op **Licenties en apps**.</span><span class="sxs-lookup"><span data-stu-id="0a213-159">Click the **User1** account, and then click **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="0a213-160">Selecteer bij **Productlicenties** uw locatie (indien nodig), schakel de **Office 365 E5**-licentie uit en schakel de **Microsoft 365 E5**-licentie in.</span><span class="sxs-lookup"><span data-stu-id="0a213-160">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license and enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="0a213-161">Klik onderaan de pagina op **Opslaan** en vervolgens op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="0a213-161">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="0a213-162">Test vervolgens of u zich kunt aanmelden bij uw abonnement met de gebruikersnaam <strong>gebruiker1@testlab.</strong>\<your domain name></span><span class="sxs-lookup"><span data-stu-id="0a213-162">Next, you test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your domain name></span></span> <span data-ttu-id="0a213-163">van het gebruiker1-account.</span><span class="sxs-lookup"><span data-stu-id="0a213-163">user name of the User1 account.</span></span>

1. <span data-ttu-id="0a213-164">Meld u af bij APP1 en meld u weer aan met een ander account.</span><span class="sxs-lookup"><span data-stu-id="0a213-164">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="0a213-165">Wanneer u om een gebruikersnaam en wachtwoord wordt gevraagd, typt u <strong>gebruiker1@testlab.</strong>\<your domain name></span><span class="sxs-lookup"><span data-stu-id="0a213-165">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name></span></span> <span data-ttu-id="0a213-166">en het wachtwoord voor gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="0a213-166">and the User1 password.</span></span> <span data-ttu-id="0a213-167">U moet u nu kunnen aanmelden als Gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="0a213-167">You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="0a213-168">Zoals u ziet, heeft Gebruiker1 de machtigingen van een domeinbeheerder voor het TESTLAB AD DS-domein, maar Gebruiker1 is geen globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="0a213-168">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="0a213-169">Daarom wordt het pictogram van de **Beheerder** niet weergegeven als optie.</span><span class="sxs-lookup"><span data-stu-id="0a213-169">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="0a213-170">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="0a213-170">Here is your resulting configuration.</span></span>

![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="0a213-172">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="0a213-172">This configuration consists of:</span></span> 
  
- <span data-ttu-id="0a213-173">Een betaald of proefabonnement op Microsoft 365 E5 of Office 365 E5 met het DNS-domein TESTLAB.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="0a213-173">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name></span></span> <span data-ttu-id="0a213-174">geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="0a213-174">registered.</span></span>
- <span data-ttu-id="0a213-175">Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="0a213-175">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="0a213-176">Azure AD Connect wordt uitgevoerd op APP1 om het AD DS-domein TESTLAB te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="0a213-176">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>
- <span data-ttu-id="0a213-177">Het Gebruiker1-account in het TESTLAB AD DS-domein is gesynchroniseerd met de Azure AD-tenant.</span><span class="sxs-lookup"><span data-stu-id="0a213-177">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="0a213-178">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="0a213-178">Next step</span></span>

<span data-ttu-id="0a213-179">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="0a213-179">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a213-180">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0a213-180">See also</span></span>

[<span data-ttu-id="0a213-181">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="0a213-181">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="0a213-182">Microsoft 365 Enterprise implementeren</span><span class="sxs-lookup"><span data-stu-id="0a213-182">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="0a213-183">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="0a213-183">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


