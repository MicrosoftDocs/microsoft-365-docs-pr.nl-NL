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
ms.openlocfilehash: b999d50b0e98b11638199327bd7ffe7269b261ce
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487126"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="4aaa5-103">Wachtwoord terugschrijven voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="4aaa5-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="4aaa5-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="4aaa5-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="4aaa5-105">Gebruikers kunnen terugschrijven van wachtwoorden gebruiken om hun wachtwoord bij te werken via Azure Active Directory (Azure AD), dat vervolgens wordt gerepliceerd naar uw lokale Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="4aaa5-105">Users can use password writeback to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="4aaa5-106">Met het terugschrijven van wachtwoorden hoeven gebruikers hun wachtwoorden niet bij te werken via de on-premises AD DS, waar hun oorspronkelijke gebruikersaccounts zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-106">With password writeback, users don't have to update their passwords through the on-premises AD DS where their original user accounts are stored.</span></span> <span data-ttu-id="4aaa5-107">Dit helpt u bij zwervende of externe gebruikers die geen verbinding hebben met het on-premises netwerk van een externe verbinding.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-107">This helps roaming or remote users who don't have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="4aaa5-108">In dit artikel wordt uitgelegd hoe u uw Microsoft 365-testomgeving configureert voor het terugschrijven van wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-108">This article describes how to configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="4aaa5-109">Het configureren van uw testomgeving voor het terugschrijven van wachtwoorden omvat twee fasen:</span><span class="sxs-lookup"><span data-stu-id="4aaa5-109">Configuring your test environment for password writeback involves two phases:</span></span>
- [<span data-ttu-id="4aaa5-110">Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="4aaa5-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="4aaa5-111">Fase 2: schakel Wachtwoord terugschrijven in voor het domein TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-111">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="4aaa5-113">Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="4aaa5-114">Fase 1: configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="4aaa5-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="4aaa5-115">Volg eerst de instructies in [wachtwoord-hash-synchronisatie](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4aaa5-115">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="4aaa5-116">De uiteindelijke configuratie ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="4aaa5-116">Your resulting configuration looks like this:</span></span>
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="4aaa5-118">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="4aaa5-118">This configuration consists of:</span></span>
  
- <span data-ttu-id="4aaa5-119">Een proef- of betaald abonnement op Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="4aaa5-120">Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines op een subnet van een Azure virtueel netwerk.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-120">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="4aaa5-121">Azure AD Connect wordt uitgevoerd op APP1 om het AD DS-domein TESTLAB te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="4aaa5-122">Fase 2: schakel Wachtwoord terugschrijven in voor het domein TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="4aaa5-123">Configureer eerst het account gebruiker 1 met de rol globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="4aaa5-124">Meld u aan in het [Microsoft 365-beheercentrum](https://portal.microsoft.com) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="4aaa5-125">Selecteer **actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-125">Select **Active users**.</span></span>
 
3. <span data-ttu-id="4aaa5-126">Selecteer op de pagina **actieve gebruikers** het account **gebruiker1** ,</span><span class="sxs-lookup"><span data-stu-id="4aaa5-126">On the **Active users** page, select the **user1** account,</span></span>

4. <span data-ttu-id="4aaa5-127">Selecteer in het deelvenster **gebruiker1** de optie **bewerken** naast **rollen**.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-127">On the **user1** pane, select **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="4aaa5-128">Selecteer in het deelvenster **gebruikersrollen bewerken** voor gebruiker1 de optie **globale beheerder**, selecteer **Opslaan**en selecteer vervolgens **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-128">On the **Edit user roles** pane for user1, select **Global administrator**, select **Save**, and then select **Close**.</span></span>

<span data-ttu-id="4aaa5-129">Configureer vervolgens het account gebruiker 1 met de beveiligingsinstellingen waarmee wachtwoorden kunnen worden gewijzigd namens andere gebruikers in het domein TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="4aaa5-130">Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\Gebruiker1-account.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="4aaa5-131">Selecteer op de desktopversie van APP1 de optie **Start**, Enter **Active**en selecteer vervolgens **Active Directory: gebruikers en computers**.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-131">From the desktop of APP1, select **Start**, enter **active**, and then select **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="4aaa5-132">Selecteer op de menubalk de optie **weergeven**.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-132">On the menu bar, select **View**.</span></span> <span data-ttu-id="4aaa5-133">Als **geavanceerde functies** niet is ingeschakeld, schakelt u deze optie in.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-133">If **Advanced features** is not enabled, select it to enable it.</span></span>

4. <span data-ttu-id="4aaa5-134">Selecteer in het deelvenster Structuur de optie uw domein (of klik er met de rechtermuisknop op), selecteer **Eigenschappen**en selecteer vervolgens het tabblad **beveiliging** .</span><span class="sxs-lookup"><span data-stu-id="4aaa5-134">In the tree pane, select and hold (or right-click) your domain, select **Properties**, and then select the **Security** tab.</span></span>

5. <span data-ttu-id="4aaa5-135">Selecteer **Geavanceerd**.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-135">Select **Advanced**.</span></span>

6. <span data-ttu-id="4aaa5-136">Selecteer **toevoegen**op het tabblad **machtigingen** .</span><span class="sxs-lookup"><span data-stu-id="4aaa5-136">On the **Permissions** tab, select **Add**.</span></span>

7. <span data-ttu-id="4aaa5-137">Selecteer **een principal selecteren**, typ **gebruiker1**en selecteer **OK**.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-137">Select **Select a principal**, enter **User1**, and then select **OK**.</span></span>

8. <span data-ttu-id="4aaa5-138">Selecteer in **Van toepassing op**, **Onderliggende gebruikersobjecten**.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="4aaa5-139">Selecteer onder **Machtigingen** het volgende:</span><span class="sxs-lookup"><span data-stu-id="4aaa5-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="4aaa5-140">**Wachtwoord wijzigen**</span><span class="sxs-lookup"><span data-stu-id="4aaa5-140">**Change password**</span></span>
    - <span data-ttu-id="4aaa5-141">**Wachtwoord opnieuw instellen**</span><span class="sxs-lookup"><span data-stu-id="4aaa5-141">**Reset password**</span></span>

10. <span data-ttu-id="4aaa5-142">Selecteer onder **Eigenschappen** het volgende:</span><span class="sxs-lookup"><span data-stu-id="4aaa5-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="4aaa5-143">**LockoutTime schrijven**</span><span class="sxs-lookup"><span data-stu-id="4aaa5-143">**Write lockoutTime**</span></span>
    - <span data-ttu-id="4aaa5-144">**pwdLastSet schrijven**</span><span class="sxs-lookup"><span data-stu-id="4aaa5-144">**Write pwdLastSet**</span></span>

11. <span data-ttu-id="4aaa5-145">Klik driemaal op **OK** om de wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-145">Select **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="4aaa5-146">Sluit **Active Directory-gebruikers en -computers**.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="4aaa5-147">Configureer vervolgens Azure AD Connect op APP1 voor Wachtwoord terugschrijven.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="4aaa5-148">Verbind indien nodig APP1 met het account TESTLAB\Gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="4aaa5-149">Dubbelklik op het bureaublad van APP1 op **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="4aaa5-150">Selecteer **configureren**op de **welkomstpagina**.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-150">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="4aaa5-151">Selecteer op de pagina **extra taken** de optie **synchronisatieopties aanpassen**en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-151">On the **Additional tasks** page, select **Customize synchronization options**, and then select **Next**.</span></span>

5. <span data-ttu-id="4aaa5-152">Voer op de pagina **verbinding maken met Azure AD** de referenties van uw globale beheerdersaccount in en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-152">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="4aaa5-153">Selecteer **volgende**op de pagina's **Connect directory's** en **Domain/ou filtering** .</span><span class="sxs-lookup"><span data-stu-id="4aaa5-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span></span>

7. <span data-ttu-id="4aaa5-154">Selecteer op de pagina **optionele functies** de optie **wachtwoord terugschrijven**en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-154">On the **Optional features** page, select **Password writeback**, and then select **Next**.</span></span>

8. <span data-ttu-id="4aaa5-155">Selecteer op de pagina **gereed voor configureren** de optie **configureren** en wacht tot het proces is voltooid.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-155">On the **Ready to configure** page, select **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="4aaa5-156">Wanneer de configuratie voltooien wordt weergegeven, selecteert u **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-156">When you see the configuration finish, select **Exit**.</span></span>

<span data-ttu-id="4aaa5-157">U kunt nu het terugschrijven van wachtwoorden voor gebruikers op computers die geen verbinding hebben met het virtuele netwerk van uw gesimuleerde intranet testen.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-157">You are now ready to test password writeback for users on computers that aren't connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="4aaa5-158">De uiteindelijke configuratie ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="4aaa5-158">Your resulting configuration looks like this:</span></span>

![De gesimuleerde onderneming met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="4aaa5-160">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="4aaa5-160">This configuration consists of:</span></span>

- <span data-ttu-id="4aaa5-161">Een Microsoft 365 E5-proefabonnement of betaalde abonnementen met de DNS-domein TESTLAB.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="4aaa5-161">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<*your domain name*></span></span> <span data-ttu-id="4aaa5-162">geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-162">registered.</span></span>
- <span data-ttu-id="4aaa5-163">Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines op een subnet van een Azure virtueel netwerk.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-163">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="4aaa5-164">Azure AD Connect draait op APP1 om de lijst van accounts en groepen van de Azure AD-tenant van uw Microsoft 365-abonnement te synchroniseren met het TESTLAB AD DS-domein.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="4aaa5-165">Wachtwoord terugschrijven is ingeschakeld, zodat gebruikers hun wachtwoorden kunnen wijzigen via Azure AD, zonder te zijn verbonden met het vereenvoudigde intranet.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="4aaa5-166">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="4aaa5-166">Next step</span></span>

<span data-ttu-id="4aaa5-167">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="4aaa5-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4aaa5-168">Zie ook</span><span class="sxs-lookup"><span data-stu-id="4aaa5-168">See also</span></span>

[<span data-ttu-id="4aaa5-169">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="4aaa5-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4aaa5-170">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="4aaa5-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4aaa5-171">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="4aaa5-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


