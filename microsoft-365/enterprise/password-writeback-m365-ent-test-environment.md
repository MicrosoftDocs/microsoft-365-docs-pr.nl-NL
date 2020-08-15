---
title: Wachtwoord terugschrijven voor uw Microsoft 365-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: 'Overzicht: Wachtwoord terugschrijven configureren voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: b8c89ca7ef967c423b89db4559ef04f715a5f869
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686224"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="3a318-103">Wachtwoord terugschrijven voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="3a318-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="3a318-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="3a318-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="3a318-105">Met Wachtwoord terugschrijven kunnen gebruikers hun wachtwoorden opnieuw instellen via Azure Active Directory (Azure AD), die vervolgens worden gerepliceerd naar uw lokale Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="3a318-105">Password writeback allows users to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="3a318-106">Met het terugschrijven van wachtwoorden hoeven gebruikers hun wachtwoorden niet bij te werken via de on-premises AD DS waar de originele gebruikersaccounts zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="3a318-106">With password writeback, users don't need to update their passwords through the on-premises AD DS where their original user accounts are stored.</span></span> <span data-ttu-id="3a318-107">Dit is handig bij roaming en gebruikers die extern werken die geen RAS-verbinding met het on-premises netwerk hebben.</span><span class="sxs-lookup"><span data-stu-id="3a318-107">This helps roaming or remote users who do not have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="3a318-108">In dit artikel wordt beschreven hoe u uw Microsoft 365-testomgeving kunt configureren voor Wachtwoord terugschrijven.</span><span class="sxs-lookup"><span data-stu-id="3a318-108">This article describes how you can configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="3a318-109">Er zijn twee fasen om dit in te stellen:</span><span class="sxs-lookup"><span data-stu-id="3a318-109">There are two phases to setting this up:</span></span>

1.    <span data-ttu-id="3a318-110">Maak de Microsoft 365-testomgeving voor uw gesimuleerde onderneming aan met wachtwoord-hash-synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="3a318-110">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="3a318-111">Schakel Wachtwoord terugschrijven in voor het domein TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="3a318-111">Enable password writeback for the TESTLAB AD DS domain.</span></span>
    
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="3a318-113">Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="3a318-113">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="3a318-114">Fase 1: configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="3a318-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="3a318-115">Volg eerst de instructies in [wachtwoord-hash-synchronisatie](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="3a318-115">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="3a318-116">Dit is de resulterende configuratie.</span><span class="sxs-lookup"><span data-stu-id="3a318-116">Here is your resulting configuration.</span></span>
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="3a318-118">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="3a318-118">This configuration consists of:</span></span> 
  
- <span data-ttu-id="3a318-119">Een proef- of betaald abonnement op Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="3a318-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="3a318-120">Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="3a318-120">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="3a318-121">Azure AD Connect wordt uitgevoerd op APP1 om het AD DS-domein TESTLAB te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="3a318-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="3a318-122">Fase 2: schakel Wachtwoord terugschrijven in voor het domein TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="3a318-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="3a318-123">Configureer eerst het account gebruiker 1 met de rol globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="3a318-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="3a318-124">Meld u aan in het [Microsoft 365-beheercentrum](https://portal.microsoft.com) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="3a318-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="3a318-125">Klik op **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="3a318-125">Click **Active users**.</span></span>
 
3. <span data-ttu-id="3a318-126">Klik in de pagina **Actieve gebruikers** op het account **gebruiker1**,</span><span class="sxs-lookup"><span data-stu-id="3a318-126">On the **Active users** page, click the **user1** account,</span></span>

4. <span data-ttu-id="3a318-127">klik in het deelvenster **gebruiker1** op **Bewerken** naast **Rollen**.</span><span class="sxs-lookup"><span data-stu-id="3a318-127">On the **user1** pane, click **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="3a318-128">Klik in het deelvenster **Gebruikersrollen bewerken** voor gebruiker1 op **Globale beheerder**.</span><span class="sxs-lookup"><span data-stu-id="3a318-128">On the **Edit user roles** pane for user1, click **Global administrator**.</span></span> <span data-ttu-id="3a318-129">Klik op **Opslaan** en vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="3a318-129">Click **Save**, and then click **Close**.</span></span>

<span data-ttu-id="3a318-130">Configureer vervolgens het account gebruiker 1 met de beveiligingsinstellingen waarmee wachtwoorden kunnen worden gewijzigd namens andere gebruikers in het domein TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="3a318-130">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="3a318-131">Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\Gebruiker1-account.</span><span class="sxs-lookup"><span data-stu-id="3a318-131">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="3a318-132">Klik vanuit het bureaublad van APP1 op **Start**, typ **actief** en klik dan op **Active Directory-gebruikers en -computers**.</span><span class="sxs-lookup"><span data-stu-id="3a318-132">From the desktop of APP1, click **Start**, type **active**, and then click **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="3a318-133">Klik op **Weergave** in de menubalk.</span><span class="sxs-lookup"><span data-stu-id="3a318-133">Click **View** in the menu bar.</span></span> <span data-ttu-id="3a318-134">Als **Geavanceerde functies** niet is ingeschakeld, klik er dan op om ze in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="3a318-134">If **Advanced features** is not enabled, click it to enable it.</span></span>

4. <span data-ttu-id="3a318-135">Klik in het structuurvenster met de rechtermuisknop op uw domein, klik op **Eigenschappen** en vervolgens op het tabblad **Beveiliging**.</span><span class="sxs-lookup"><span data-stu-id="3a318-135">In the tree pane, right-click your domain, click **Properties**, and then click the **Security** tab.</span></span>

5. <span data-ttu-id="3a318-136">Klik op **Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="3a318-136">Click **Advanced**.</span></span>

6. <span data-ttu-id="3a318-137">Klik op het tabblad **Machtigingen** op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="3a318-137">On the **Permissions** tab, click **Add**.</span></span>

7. <span data-ttu-id="3a318-138">Klik op **Een hoofdmachtiging selecteren**, typ **Gebruiker1** en klik dan op **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a318-138">Click **Select a principal**, type **User1**, and then click **OK**.</span></span>

8. <span data-ttu-id="3a318-139">Selecteer in **Van toepassing op**, **Onderliggende gebruikersobjecten**.</span><span class="sxs-lookup"><span data-stu-id="3a318-139">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="3a318-140">Selecteer onder **Machtigingen** het volgende:</span><span class="sxs-lookup"><span data-stu-id="3a318-140">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="3a318-141">Wachtwoord wijzigen</span><span class="sxs-lookup"><span data-stu-id="3a318-141">Change password</span></span>
    - <span data-ttu-id="3a318-142">Wachtwoord opnieuw instellen</span><span class="sxs-lookup"><span data-stu-id="3a318-142">Reset password</span></span>

10. <span data-ttu-id="3a318-143">Selecteer onder **Eigenschappen** het volgende:</span><span class="sxs-lookup"><span data-stu-id="3a318-143">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="3a318-144">LockoutTime schrijven</span><span class="sxs-lookup"><span data-stu-id="3a318-144">Write lockoutTime</span></span>
    - <span data-ttu-id="3a318-145">pwdLastSet schrijven</span><span class="sxs-lookup"><span data-stu-id="3a318-145">Write pwdLastSet</span></span>

11. <span data-ttu-id="3a318-146">Klik drie keer op **OK** om de wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="3a318-146">Click **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="3a318-147">Sluit **Active Directory-gebruikers en -computers**.</span><span class="sxs-lookup"><span data-stu-id="3a318-147">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="3a318-148">Configureer vervolgens Azure AD Connect op APP1 voor Wachtwoord terugschrijven.</span><span class="sxs-lookup"><span data-stu-id="3a318-148">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="3a318-149">Verbind indien nodig APP1 met het account TESTLAB\Gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="3a318-149">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="3a318-150">Dubbelklik op het bureaublad van APP1 op **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="3a318-150">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="3a318-151">Klik in de **welkomstpagina** op **Configureren**.</span><span class="sxs-lookup"><span data-stu-id="3a318-151">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="3a318-152">Klik in de pagina **Aanvullende taken** op **Synchronisatieopties aanpassen** en klik dan op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3a318-152">On the **Additional tasks** page, click **Customize synchronization options**, and then click **Next**.</span></span>

5. <span data-ttu-id="3a318-153">Voer in de pagina **Verbinding maken met Azure AD** de referenties van uw globale beheerdersaccount in en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3a318-153">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="3a318-154">Klik in de pagina’s **Mappen verbinden** en **Domein/OE filteren** op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3a318-154">On the **Connect directories** and **Domain/OU filtering** pages, click **Next**.</span></span>

7. <span data-ttu-id="3a318-155">Selecteer in de pagina **Optionele functies**, **Wachtwoord terugschrijven** en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3a318-155">On the **Optional features** page, select **Password writeback** and click **Next**.</span></span> 

8. <span data-ttu-id="3a318-156">Klik in de pagina **Klaar om te configureren** op **Configureren** en wacht tot het proces is voltooid.</span><span class="sxs-lookup"><span data-stu-id="3a318-156">On the **Ready to configure** page, click **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="3a318-157">Wanneer u ziet dat de configuratie is voltooid, klikt u op **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="3a318-157">When you see the configuration finish, click **Exit**.</span></span>

<span data-ttu-id="3a318-158">U kunt nu Wachtwoord terugschrijven testen voor gebruikers op computers die niet zijn verbonden met het virtuele netwerk van uw gesimuleerde intranet.</span><span class="sxs-lookup"><span data-stu-id="3a318-158">You are now ready to test password writeback for users on computers that are not connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="3a318-159">Dit is de resulterende configuratie:</span><span class="sxs-lookup"><span data-stu-id="3a318-159">Here is your resulting configuration:</span></span>

![De gesimuleerde onderneming met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="3a318-161">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="3a318-161">This configuration consists of:</span></span>

- <span data-ttu-id="3a318-162">Een Microsoft 365 E5-proefabonnement of betaalde abonnementen met de DNS-domein TESTLAB.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="3a318-162">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name></span></span> <span data-ttu-id="3a318-163">geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="3a318-163">registered.</span></span>
- <span data-ttu-id="3a318-164">Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="3a318-164">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="3a318-165">Azure AD Connect draait op APP1 om de lijst van accounts en groepen van de Azure AD-tenant van uw Microsoft 365-abonnement te synchroniseren met het TESTLAB AD DS-domein.</span><span class="sxs-lookup"><span data-stu-id="3a318-165">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="3a318-166">Wachtwoord terugschrijven is ingeschakeld, zodat gebruikers hun wachtwoorden kunnen wijzigen via Azure AD, zonder te zijn verbonden met het vereenvoudigde intranet.</span><span class="sxs-lookup"><span data-stu-id="3a318-166">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="3a318-167">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="3a318-167">Next step</span></span>

<span data-ttu-id="3a318-168">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="3a318-168">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a318-169">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3a318-169">See also</span></span>

[<span data-ttu-id="3a318-170">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="3a318-170">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3a318-171">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="3a318-171">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="3a318-172">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="3a318-172">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


