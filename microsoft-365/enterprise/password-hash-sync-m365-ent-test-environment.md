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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 'Overzicht: Wachtwoord-hash-synchronisatie en -aanmelding configureren en demonstreren voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: 9c61745fe322dce4cb2b537b18963634a97c697a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921502"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="c57af-103">Wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="c57af-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="c57af-104">*Deze testlaborator kan worden gebruikt voor zowel Microsoft 365 voor bedrijven als Office 365 Enterprise testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="c57af-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="c57af-105">Veel organisaties maken gebruik van Azure AD Connect en wachtwoord-hash-synchronisatie om de accounts in hun AD DS-forest (Active Directory Domain Services) op locatie te synchroniseren met de accounts in de Azure AD-tenant van hun Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="c57af-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="c57af-106">In dit artikel wordt beschreven hoe u wachtwoordhashsynchronisatie kunt toevoegen aan uw Microsoft 365 testomgeving, wat resulteert in deze configuratie:</span><span class="sxs-lookup"><span data-stu-id="c57af-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="c57af-108">Het instellen van deze testomgeving bestaat uit drie fasen:</span><span class="sxs-lookup"><span data-stu-id="c57af-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="c57af-109">Fase 1: De Microsoft 365-testomgeving voor een gesimuleerde onderneming maken</span><span class="sxs-lookup"><span data-stu-id="c57af-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="c57af-110">Fase 2: Het testlab-domein maken en registreren</span><span class="sxs-lookup"><span data-stu-id="c57af-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="c57af-111">Fase 3: Azure AD Connect op APP1 installeren</span><span class="sxs-lookup"><span data-stu-id="c57af-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="c57af-112">Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, gaat u naar Microsoft 365 voor [enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="c57af-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="c57af-113">Fase 1: De Microsoft 365-testomgeving voor een gesimuleerde onderneming maken</span><span class="sxs-lookup"><span data-stu-id="c57af-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="c57af-114">Volg de instructies in [Basisconfiguratie voor gesimuleerde onderneming in Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c57af-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="c57af-115">De resulterende configuratie ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="c57af-115">Your resulting configuration looks like this:</span></span>
  
![De basisconfiguratie voor een gesimuleerde onderneming](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="c57af-117">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="c57af-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="c57af-118">Een proef- of betaald abonnement op Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c57af-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="c57af-119">Een vereenvoudigd intranet van de organisatie dat is verbonden met internet, bestaande uit de virtuele DC1-, APP1- en CLIENT1-machines in een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="c57af-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="c57af-120">DC1 is een domeincontroller voor het testlab.<*uw openbare* domeinnaam> AD DS-domein.</span><span class="sxs-lookup"><span data-stu-id="c57af-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="c57af-121">Fase 2: Het testlab-domein maken en registreren</span><span class="sxs-lookup"><span data-stu-id="c57af-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="c57af-122">Voeg in deze fase een openbaar DNS-domein toe en voeg het vervolgens toe aan uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="c57af-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="c57af-123">Werk eerst samen met uw openbare DNS-registratieprovider om een nieuwe openbare DNS-domeinnaam te maken die is gebaseerd op uw huidige domeinnaam en voeg deze vervolgens toe aan uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="c57af-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="c57af-124">Het is raadzaam om de naam **testlab.<*uw openbare domein te gebruiken.\* >*\*</span><span class="sxs-lookup"><span data-stu-id="c57af-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="c57af-125">Als uw openbare domeinnaam bijvoorbeeld **<span>contoso</span>.com** is, voegt u de openbare domeinnaam toe: **<span>testlab</span>.contoso.com.**</span><span class="sxs-lookup"><span data-stu-id="c57af-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="c57af-126">Voeg vervolgens het **testlab.< >** uw openbare domeindomein toe aan uw Microsoft 365 proefabonnement of betaald abonnement door het domeinregistratieproces te doorlopen.</span><span class="sxs-lookup"><span data-stu-id="c57af-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="c57af-127">Dit bestaat uit het toevoegen van extra DNS-records aan het **testlab.<*uw openbare domeindomein.\* >*\*</span><span class="sxs-lookup"><span data-stu-id="c57af-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="c57af-128">Zie Een domein toevoegen [aan Microsoft 365.](../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="c57af-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="c57af-129">De resulterende configuratie ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="c57af-129">Your resulting configuration looks like this:</span></span>
  
![De registratie van de naam van uw testlab-domein](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="c57af-131">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="c57af-131">This configuration consists of:</span></span>

- <span data-ttu-id="c57af-132">Een Microsoft 365 E5 of betaald abonnement met het DNS-domein testlab.<*uw openbare* domeinnaam> geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="c57af-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="c57af-133">Een vereenvoudigd intranet van de organisatie dat is verbonden met internet, bestaande uit de virtuele DC1-, APP1- en CLIENT1-machines op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="c57af-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="c57af-134">U ziet hoe het testlab.<*uw openbare* domeinnaam> nu is:</span><span class="sxs-lookup"><span data-stu-id="c57af-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="c57af-135">Ondersteund wordt door openbare DNS-records.</span><span class="sxs-lookup"><span data-stu-id="c57af-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="c57af-136">Geregistreerd is in de Microsoft 365-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="c57af-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="c57af-137">Het AD DS-domein op uw gesimuleerde intranet is.</span><span class="sxs-lookup"><span data-stu-id="c57af-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="c57af-138">Fase 3: Azure AD Connect op APP1 installeren</span><span class="sxs-lookup"><span data-stu-id="c57af-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="c57af-139">In deze fase installeert en configureert u de Azure AD Verbinding maken app1 en controleert u of het werkt.</span><span class="sxs-lookup"><span data-stu-id="c57af-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="c57af-140">Installeer eerst Azure AD-Verbinding maken op APP1.</span><span class="sxs-lookup"><span data-stu-id="c57af-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="c57af-141">Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\\Gebruiker1-account.</span><span class="sxs-lookup"><span data-stu-id="c57af-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="c57af-142">Open, vanaf het bureaublad van APP1, een Windows PowerShell-opdrachtprompt op beheerdersniveau en voer deze opdrachten uit om verbeterde beveiliging van Internet Explorer uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="c57af-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="c57af-143">Selecteer Internet **Explorer** op de taakbalk en ga naar [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="c57af-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="c57af-144">Selecteer op Microsoft Azure Active Directory Verbinding maken pagina **Downloaden** en selecteer vervolgens **Uitvoeren.**</span><span class="sxs-lookup"><span data-stu-id="c57af-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="c57af-145">Selecteer op **de pagina Welkom bij Azure AD Verbinding maken** ik ga akkoord en selecteer vervolgens **Doorgaan.** </span><span class="sxs-lookup"><span data-stu-id="c57af-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="c57af-146">Selecteer op **de Instellingen** Express-instellingen **gebruiken.**</span><span class="sxs-lookup"><span data-stu-id="c57af-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="c57af-147">Voer op **Verbinding maken pagina Naar Azure AD** de naam van uw globale beheerdersaccount in Gebruikersnaam **in,** voer het wachtwoord **in** Wachtwoord in en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c57af-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="c57af-148">Voer op **Verbinding maken pagina NAAR AD DS** **TESTLAB \\ User1** in **Gebruikersnaam in,** voer het wachtwoord **in** Wachtwoord in en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c57af-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="c57af-149">Selecteer installeren **op de pagina** Gereed om te **configureren.**</span><span class="sxs-lookup"><span data-stu-id="c57af-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="c57af-150">Selecteer op **de pagina Configuratie** voltooid de optie **Afsluiten.**</span><span class="sxs-lookup"><span data-stu-id="c57af-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="c57af-151">Ga in Internet Explorer naar het Microsoft 365-beheercentrum ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="c57af-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="c57af-152">Selecteer in het linkernavigatiedeelvenster **Gebruikers > Actieve gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="c57af-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="c57af-153">Bekijk het account met de naam **Gebruiker1**.</span><span class="sxs-lookup"><span data-stu-id="c57af-153">Note the account named **User1**.</span></span> <span data-ttu-id="c57af-154">Dit account is afkomstig uit het TESTLAB AD DS-domein en is het bewijs dat de adreslijstsynchronisatie heeft gewerkt.</span><span class="sxs-lookup"><span data-stu-id="c57af-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="c57af-155">Selecteer het **User1-account** en selecteer vervolgens **Licenties en apps.**</span><span class="sxs-lookup"><span data-stu-id="c57af-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="c57af-156">In **Productlicenties**, selecteert u uw locatie (indien nodig), schakelt u de **Office 365 E5-licentie** uit en schakelt u de Microsoft 365 E5 **in.**</span><span class="sxs-lookup"><span data-stu-id="c57af-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="c57af-157">Selecteer **Opslaan** onder aan de pagina en selecteer **sluiten.**</span><span class="sxs-lookup"><span data-stu-id="c57af-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="c57af-158">Test vervolgens de mogelijkheid om u aan te melden bij uw abonnement met **user1@testlab.< >** domeinnaam van het Gebruikers1-account:</span><span class="sxs-lookup"><span data-stu-id="c57af-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="c57af-159">Meld u af bij APP1 en meld u weer aan met een ander account.</span><span class="sxs-lookup"><span data-stu-id="c57af-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="c57af-160">Wanneer u wordt gevraagd om een gebruikersnaam en wachtwoord, geeft **u user1@testlab.<*domeinnaam\* >*\* en het gebruikers1-wachtwoord op.</span><span class="sxs-lookup"><span data-stu-id="c57af-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="c57af-161">U moet u nu kunnen aanmelden als Gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="c57af-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="c57af-162">Zoals u ziet, heeft Gebruiker1 de machtigingen van een domeinbeheerder voor het TESTLAB AD DS-domein, maar Gebruiker1 is geen globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="c57af-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="c57af-163">Daarom wordt het pictogram van de **Beheerder** niet weergegeven als optie.</span><span class="sxs-lookup"><span data-stu-id="c57af-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="c57af-164">De resulterende configuratie ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="c57af-164">Your resulting configuration looks like this:</span></span>

![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="c57af-166">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="c57af-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="c57af-167">Microsoft 365 E5 of Office 365 E5-proefabonnement of betaalde abonnementen met het DNS-domein TESTLAB.<*uw* domeinnaam> geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="c57af-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="c57af-168">Een vereenvoudigd intranet van de organisatie dat is verbonden met internet, bestaande uit de virtuele DC1-, APP1- en CLIENT1-machines op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="c57af-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="c57af-169">Azure AD Verbinding maken wordt uitgevoerd op APP1 om het TESTLAB AD DS-domein regelmatig te synchroniseren met de Azure AD-tenant van uw Microsoft 365 abonnement.</span><span class="sxs-lookup"><span data-stu-id="c57af-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="c57af-170">Het Gebruiker1-account in het TESTLAB AD DS-domein is gesynchroniseerd met de Azure AD-tenant.</span><span class="sxs-lookup"><span data-stu-id="c57af-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="c57af-171">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="c57af-171">Next step</span></span>

<span data-ttu-id="c57af-172">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="c57af-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c57af-173">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c57af-173">See also</span></span>

[<span data-ttu-id="c57af-174">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="c57af-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c57af-175">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="c57af-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c57af-176">Microsoft 365 enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="c57af-176">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)