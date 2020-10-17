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
ms.openlocfilehash: 3c20d1997be2ff47f0b449cbba3afb1e6edcd59a
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487456"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="eeb4b-103">Wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="eeb4b-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="eeb4b-104">*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="eeb4b-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="eeb4b-105">Veel organisaties maken gebruik van Azure AD Connect en wachtwoord-hash-synchronisatie om de accounts in hun AD DS-forest (Active Directory Domain Services) op locatie te synchroniseren met de accounts in de Azure AD-tenant van hun Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="eeb4b-106">In dit artikel wordt beschreven hoe u wachtwoord hash-synchronisatie kunt toevoegen aan uw Microsoft 365-testomgeving, wat resulteert in deze configuratie:</span><span class="sxs-lookup"><span data-stu-id="eeb4b-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="eeb4b-108">Het instellen van deze testomgeving omvat drie fasen:</span><span class="sxs-lookup"><span data-stu-id="eeb4b-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="eeb4b-109">Fase 1: De Microsoft 365-testomgeving voor een gesimuleerde onderneming maken</span><span class="sxs-lookup"><span data-stu-id="eeb4b-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="eeb4b-110">Fase 2: Het testlab-domein maken en registreren</span><span class="sxs-lookup"><span data-stu-id="eeb4b-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="eeb4b-111">Fase 3: Azure AD Connect op APP1 installeren</span><span class="sxs-lookup"><span data-stu-id="eeb4b-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="eeb4b-112">Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="eeb4b-113">Fase 1: De Microsoft 365-testomgeving voor een gesimuleerde onderneming maken</span><span class="sxs-lookup"><span data-stu-id="eeb4b-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="eeb4b-114">Volg de instructies in [Basisconfiguratie voor gesimuleerde onderneming in Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="eeb4b-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="eeb4b-115">De uiteindelijke configuratie ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="eeb4b-115">Your resulting configuration looks like this:</span></span>
  
![De basisconfiguratie voor een gesimuleerde onderneming](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="eeb4b-117">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="eeb4b-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="eeb4b-118">Een proef- of betaald abonnement op Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="eeb4b-119">Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines in een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="eeb4b-120">DC1 is een domeincontroller voor de testlab. <*uw openbare domeinnaam*> Active Directory-domein.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="eeb4b-121">Fase 2: Het testlab-domein maken en registreren</span><span class="sxs-lookup"><span data-stu-id="eeb4b-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="eeb4b-122">In deze fase voegt u een openbaar DNS-domein toe en voegt u dit toe aan uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="eeb4b-123">U moet eerst werken met uw openbare DNS-registratie provider om een nieuwe openbare DNS-domeinnaam te maken die is gebaseerd op uw huidige domeinnaam en deze vervolgens toe te voegen aan uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="eeb4b-124">We raden u aan gebruik te maken van de naam \**testlab. <*uw openbare domein\* > \*\*.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="eeb4b-125">Als uw openbare domeinnaam bijvoorbeeld \*\* <span>Contoso</span>. com**is, voegt u de naam van het openbare domein toe: \*\* <span>testlab</span>. contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="eeb4b-126">Vervolgens voegt u de \**testlab. <*uw openbare domein\* > \*\* domein toe aan uw proefabonnement voor Microsoft 365 of betaald door het domeinregistratie proces te passeren.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="eeb4b-127">Dit omvat het toevoegen van extra DNS-records aan \**testlab. <*uw openbare domein\* > \*\* domein.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="eeb4b-128">Zie voor meer informatie [een domein toevoegen aan Microsoft 365](../admin/setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="eeb4b-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="eeb4b-129">De uiteindelijke configuratie ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="eeb4b-129">Your resulting configuration looks like this:</span></span>
  
![De registratie van de naam van uw testlab-domein](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="eeb4b-131">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="eeb4b-131">This configuration consists of:</span></span>

- <span data-ttu-id="eeb4b-132">Een Microsoft 365 E5-proefabonnement of een betaald abonnement met de DNS Domain testlab. <*de naam van uw openbare domein*> geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="eeb4b-133">Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines op een subnet van een Azure virtueel netwerk.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="eeb4b-134">U ziet hoe de testlab. <*de naam van uw openbare domein*> nu:</span><span class="sxs-lookup"><span data-stu-id="eeb4b-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="eeb4b-135">Ondersteund wordt door openbare DNS-records.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="eeb4b-136">Geregistreerd is in de Microsoft 365-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="eeb4b-137">Het AD DS-domein op uw gesimuleerde intranet is.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="eeb4b-138">Fase 3: Azure AD Connect op APP1 installeren</span><span class="sxs-lookup"><span data-stu-id="eeb4b-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="eeb4b-139">In deze fase installeert en configureert u het hulpprogramma van Azure AD Connect op APP1 en controleert u vervolgens of het werkt.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="eeb4b-140">Installeer en Configureer eerst Azure AD Connect op APP1.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="eeb4b-141">Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\\Gebruiker1-account.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="eeb4b-142">Open, vanaf het bureaublad van APP1, een Windows PowerShell-opdrachtprompt op beheerdersniveau en voer deze opdrachten uit om verbeterde beveiliging van Internet Explorer uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="eeb4b-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="eeb4b-143">Selecteer **Internet Explorer** op de taakbalk en ga naar [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="eeb4b-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="eeb4b-144">Selecteer op de pagina Microsoft Azure Active Directory Connect de optie **downloaden**en klik vervolgens op **uitvoeren**.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="eeb4b-145">Selecteer op de pagina **Welkom bij Azure AD Connect** de optie **Ik ga akkoord**en selecteer vervolgens **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="eeb4b-146">Selecteer op de pagina **expres instellingen** de optie **snelle instellingen gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="eeb4b-147">Voer op de pagina **verbinding maken met Azure AD** de naam van uw globale beheerdersaccount in de gebruikersnaam in **,** Voer het wacht **woord in en**Selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="eeb4b-148">Voer op de pagina **verbinding maken met AD DS** **TESTLAB \\ gebruiker1** in **gebruikersnaam in,** Geef het wachtwoord op in het **wachtwoord**en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="eeb4b-149">Selecteer **installeren**op de pagina **klaar voor de configuratie** .</span><span class="sxs-lookup"><span data-stu-id="eeb4b-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="eeb4b-150">Selecteer op de pagina **configuratie voltooid** de optie **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="eeb4b-151">Ga in Internet Explorer naar het Microsoft 365-beheercentrum ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="eeb4b-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="eeb4b-152">Selecteer **gebruikers > actieve gebruikers**in het linker navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="eeb4b-153">Bekijk het account met de naam **Gebruiker1**.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-153">Note the account named **User1**.</span></span> <span data-ttu-id="eeb4b-154">Dit account is afkomstig uit het TESTLAB AD DS-domein en is het bewijs dat de adreslijstsynchronisatie heeft gewerkt.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="eeb4b-155">Selecteer het account **gebruiker1** en selecteer vervolgens **licenties en apps**.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="eeb4b-156">Selecteer in **product licenties**uw locatie (indien nodig), schakel de licentie voor **Office 365 E5** uit en schakel de **Microsoft 365 E5** -licentie in.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="eeb4b-157">Selecteer **Opslaan** onderaan de pagina en selecteer vervolgens **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="eeb4b-158">Test vervolgens de mogelijkheid om u aan te melden bij uw abonnement met het \**user1@testlab. <*uw domeinnaam\* > \*\* gebruikersnaam van het account gebruiker1:</span><span class="sxs-lookup"><span data-stu-id="eeb4b-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="eeb4b-159">Meld u af bij APP1 en meld u weer aan met een ander account.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="eeb4b-160">Wanneer u wordt gevraagd om een gebruikersnaam en wachtwoord, geeft u \**user1@testlab op. <*uw domeinnaam\* > \*\* en het wachtwoord gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="eeb4b-161">U moet u nu kunnen aanmelden als Gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="eeb4b-162">Zoals u ziet, heeft Gebruiker1 de machtigingen van een domeinbeheerder voor het TESTLAB AD DS-domein, maar Gebruiker1 is geen globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="eeb4b-163">Daarom wordt het pictogram van de **Beheerder** niet weergegeven als optie.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="eeb4b-164">De uiteindelijke configuratie ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="eeb4b-164">Your resulting configuration looks like this:</span></span>

![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="eeb4b-166">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="eeb4b-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="eeb4b-167">Microsoft 365 E5 of Office 365 E5-proefabonnement of betaalde abonnementen met DNS Domain TESTLAB. <*uw domeinnaam*> geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="eeb4b-168">Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines op een subnet van een Azure virtueel netwerk.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="eeb4b-169">Azure AD Connect wordt uitgevoerd op APP1 om periodiek het TESTLAB AD DS-domein te synchroniseren met de Azure AD-Tenant van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="eeb4b-170">Het Gebruiker1-account in het TESTLAB AD DS-domein is gesynchroniseerd met de Azure AD-tenant.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="eeb4b-171">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="eeb4b-171">Next step</span></span>

<span data-ttu-id="eeb4b-172">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="eeb4b-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="eeb4b-173">Zie ook</span><span class="sxs-lookup"><span data-stu-id="eeb4b-173">See also</span></span>

[<span data-ttu-id="eeb4b-174">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="eeb4b-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="eeb4b-175">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="eeb4b-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="eeb4b-176">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="eeb4b-176">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
