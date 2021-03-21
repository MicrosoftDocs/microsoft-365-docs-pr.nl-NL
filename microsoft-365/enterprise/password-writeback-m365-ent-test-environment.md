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
ms.openlocfilehash: f1118c22ad1f65ea29bb14afacb7506a60d1fe1a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921478"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="5d357-103">Wachtwoord terugschrijven voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="5d357-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="5d357-104">*Deze testlaborator kan alleen worden gebruikt voor Microsoft 365 voor testomgevingen voor ondernemingen.*</span><span class="sxs-lookup"><span data-stu-id="5d357-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="5d357-105">Gebruikers kunnen wachtwoord writeback gebruiken om hun wachtwoorden bij te werken via Azure Active Directory (Azure AD), dat vervolgens wordt gerepliceerd naar uw lokale Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="5d357-105">Users can use password writeback to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="5d357-106">Met wachtwoordschrijven hoeven gebruikers hun wachtwoorden niet bij te werken via de on-premises AD DS waar hun oorspronkelijke gebruikersaccounts zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="5d357-106">With password writeback, users don't have to update their passwords through the on-premises AD DS where their original user accounts are stored.</span></span> <span data-ttu-id="5d357-107">Dit helpt roaming- of externe gebruikers die geen externe toegang hebben tot hun on-premises netwerk.</span><span class="sxs-lookup"><span data-stu-id="5d357-107">This helps roaming or remote users who don't have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="5d357-108">In dit artikel wordt beschreven hoe u uw Microsoft 365-testomgeving configureert voor het terugschrijven van wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="5d357-108">This article describes how to configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="5d357-109">Het configureren van uw testomgeving voor het terugschrijven van wachtwoorden omvat twee fasen:</span><span class="sxs-lookup"><span data-stu-id="5d357-109">Configuring your test environment for password writeback involves two phases:</span></span>
- [<span data-ttu-id="5d357-110">Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="5d357-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="5d357-111">Fase 2: schakel Wachtwoord terugschrijven in voor het domein TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="5d357-111">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="5d357-113">Ga naar [Microsoft 365 for enterprise Test Lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)Stack voor een visuele kaart voor alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide Stack.</span><span class="sxs-lookup"><span data-stu-id="5d357-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="5d357-114">Fase 1: configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving</span><span class="sxs-lookup"><span data-stu-id="5d357-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="5d357-115">Volg eerst de instructies in [wachtwoord-hash-synchronisatie](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="5d357-115">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="5d357-116">De resulterende configuratie ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="5d357-116">Your resulting configuration looks like this:</span></span>
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="5d357-118">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="5d357-118">This configuration consists of:</span></span>
  
- <span data-ttu-id="5d357-119">Een proef- of betaald abonnement op Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="5d357-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="5d357-120">Een vereenvoudigd intranet van de organisatie dat is verbonden met internet, bestaande uit de virtuele DC1-, APP1- en CLIENT1-machines op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="5d357-120">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="5d357-121">Azure AD Connect wordt uitgevoerd op APP1 om het AD DS-domein TESTLAB te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="5d357-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="5d357-122">Fase 2: schakel Wachtwoord terugschrijven in voor het domein TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="5d357-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="5d357-123">Configureer eerst het account gebruiker 1 met de rol globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="5d357-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="5d357-124">Meld u aan in het [Microsoft 365-beheercentrum](https://portal.microsoft.com) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="5d357-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="5d357-125">Selecteer **Actieve gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="5d357-125">Select **Active users**.</span></span>
 
3. <span data-ttu-id="5d357-126">Selecteer op **de pagina** Actieve gebruikers het **gebruikers1-account,**</span><span class="sxs-lookup"><span data-stu-id="5d357-126">On the **Active users** page, select the **user1** account,</span></span>

4. <span data-ttu-id="5d357-127">Selecteer bewerken naast **Rollen** in **het deelvenster gebruiker1.** </span><span class="sxs-lookup"><span data-stu-id="5d357-127">On the **user1** pane, select **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="5d357-128">Selecteer in **het deelvenster Gebruikersrollen bewerken** voor gebruiker1 de optie Globale **beheerder,** selecteer **Opslaan** en selecteer **vervolgens Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="5d357-128">On the **Edit user roles** pane for user1, select **Global administrator**, select **Save**, and then select **Close**.</span></span>

<span data-ttu-id="5d357-129">Configureer vervolgens het account gebruiker 1 met de beveiligingsinstellingen waarmee wachtwoorden kunnen worden gewijzigd namens andere gebruikers in het domein TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="5d357-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="5d357-130">Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\Gebruiker1-account.</span><span class="sxs-lookup"><span data-stu-id="5d357-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="5d357-131">Selecteer op het bureaublad van APP1 **Start,** voer **actief in** en selecteer **vervolgens Active Directory-gebruikers en -computers.**</span><span class="sxs-lookup"><span data-stu-id="5d357-131">From the desktop of APP1, select **Start**, enter **active**, and then select **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="5d357-132">Selecteer weergeven op de **menubalk.**</span><span class="sxs-lookup"><span data-stu-id="5d357-132">On the menu bar, select **View**.</span></span> <span data-ttu-id="5d357-133">Als **Geavanceerde functies** niet zijn ingeschakeld, selecteert u deze om deze in te stellen.</span><span class="sxs-lookup"><span data-stu-id="5d357-133">If **Advanced features** is not enabled, select it to enable it.</span></span>

4. <span data-ttu-id="5d357-134">Selecteer in het deelvenster Structuur uw domein en houd deze ingedrukt (of klik erop met de rechtermuisknop), selecteer **Eigenschappen** en selecteer vervolgens het **tabblad** Beveiliging.</span><span class="sxs-lookup"><span data-stu-id="5d357-134">In the tree pane, select and hold (or right-click) your domain, select **Properties**, and then select the **Security** tab.</span></span>

5. <span data-ttu-id="5d357-135">Selecteer **Geavanceerd.**</span><span class="sxs-lookup"><span data-stu-id="5d357-135">Select **Advanced**.</span></span>

6. <span data-ttu-id="5d357-136">Selecteer op **het tabblad** Machtigingen de optie **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="5d357-136">On the **Permissions** tab, select **Add**.</span></span>

7. <span data-ttu-id="5d357-137">Selecteer **Selecteer een principal,** voer **Gebruiker1** in en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="5d357-137">Select **Select a principal**, enter **User1**, and then select **OK**.</span></span>

8. <span data-ttu-id="5d357-138">Selecteer in **Van toepassing op**, **Onderliggende gebruikersobjecten**.</span><span class="sxs-lookup"><span data-stu-id="5d357-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="5d357-139">Selecteer onder **Machtigingen** het volgende:</span><span class="sxs-lookup"><span data-stu-id="5d357-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="5d357-140">**Wachtwoord wijzigen**</span><span class="sxs-lookup"><span data-stu-id="5d357-140">**Change password**</span></span>
    - <span data-ttu-id="5d357-141">**Wachtwoord opnieuw instellen**</span><span class="sxs-lookup"><span data-stu-id="5d357-141">**Reset password**</span></span>

10. <span data-ttu-id="5d357-142">Selecteer onder **Eigenschappen** het volgende:</span><span class="sxs-lookup"><span data-stu-id="5d357-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="5d357-143">**LockoutTime schrijven**</span><span class="sxs-lookup"><span data-stu-id="5d357-143">**Write lockoutTime**</span></span>
    - <span data-ttu-id="5d357-144">**pwdLastSet schrijven**</span><span class="sxs-lookup"><span data-stu-id="5d357-144">**Write pwdLastSet**</span></span>

11. <span data-ttu-id="5d357-145">Selecteer **OK** drie keer om de wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="5d357-145">Select **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="5d357-146">Sluit **Active Directory-gebruikers en -computers**.</span><span class="sxs-lookup"><span data-stu-id="5d357-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="5d357-147">Configureer vervolgens Azure AD Connect op APP1 voor Wachtwoord terugschrijven.</span><span class="sxs-lookup"><span data-stu-id="5d357-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="5d357-148">Verbind indien nodig APP1 met het account TESTLAB\Gebruiker1.</span><span class="sxs-lookup"><span data-stu-id="5d357-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="5d357-149">Dubbelklik op het bureaublad van APP1 op **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="5d357-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="5d357-150">Selecteer **configureren op de** **welkomstpagina.**</span><span class="sxs-lookup"><span data-stu-id="5d357-150">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="5d357-151">Selecteer op **de pagina** Extra taken de **optie Synchronisatieopties aanpassen** en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="5d357-151">On the **Additional tasks** page, select **Customize synchronization options**, and then select **Next**.</span></span>

5. <span data-ttu-id="5d357-152">Voer op **de pagina Verbinding maken met Azure AD** uw globale beheerdersaccountreferenties in en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="5d357-152">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="5d357-153">Selecteer volgende **op de pagina's** Verbinding maken met directories en filterpagina's voor domeinen/ou's.  </span><span class="sxs-lookup"><span data-stu-id="5d357-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span></span>

7. <span data-ttu-id="5d357-154">Selecteer op **de pagina** Optionele functies de optie **Wachtwoordterugschrijven** en selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="5d357-154">On the **Optional features** page, select **Password writeback**, and then select **Next**.</span></span>

8. <span data-ttu-id="5d357-155">Selecteer op **de pagina Gereed om te** configureren de optie **Configureren** en wacht totdat het proces is klaar.</span><span class="sxs-lookup"><span data-stu-id="5d357-155">On the **Ready to configure** page, select **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="5d357-156">Wanneer u de configuratie-afwerking ziet, selecteert u **Afsluiten.**</span><span class="sxs-lookup"><span data-stu-id="5d357-156">When you see the configuration finish, select **Exit**.</span></span>

<span data-ttu-id="5d357-157">U bent nu klaar om wachtwoord writeback te testen voor gebruikers op computers die niet zijn verbonden met het virtuele netwerk van uw gesimuleerde intranet.</span><span class="sxs-lookup"><span data-stu-id="5d357-157">You are now ready to test password writeback for users on computers that aren't connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="5d357-158">De resulterende configuratie ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="5d357-158">Your resulting configuration looks like this:</span></span>

![De gesimuleerde onderneming met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="5d357-160">Deze configuratie bestaat uit:</span><span class="sxs-lookup"><span data-stu-id="5d357-160">This configuration consists of:</span></span>

- <span data-ttu-id="5d357-161">Een proefversie van Microsoft 365 E5 of betaalde abonnementen met het DNS-domein TESTLAB.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="5d357-161">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<*your domain name*></span></span> <span data-ttu-id="5d357-162">geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="5d357-162">registered.</span></span>
- <span data-ttu-id="5d357-163">Een vereenvoudigd intranet van de organisatie dat is verbonden met internet, bestaande uit de virtuele DC1-, APP1- en CLIENT1-machines op een subnet van een virtueel Azure-netwerk.</span><span class="sxs-lookup"><span data-stu-id="5d357-163">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="5d357-164">Azure AD Connect draait op APP1 om de lijst van accounts en groepen van de Azure AD-tenant van uw Microsoft 365-abonnement te synchroniseren met het TESTLAB AD DS-domein.</span><span class="sxs-lookup"><span data-stu-id="5d357-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="5d357-165">Wachtwoord terugschrijven is ingeschakeld, zodat gebruikers hun wachtwoorden kunnen wijzigen via Azure AD, zonder te zijn verbonden met het vereenvoudigde intranet.</span><span class="sxs-lookup"><span data-stu-id="5d357-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="5d357-166">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="5d357-166">Next step</span></span>

<span data-ttu-id="5d357-167">Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="5d357-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d357-168">Zie ook</span><span class="sxs-lookup"><span data-stu-id="5d357-168">See also</span></span>

[<span data-ttu-id="5d357-169">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="5d357-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5d357-170">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="5d357-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5d357-171">Microsoft 365 enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="5d357-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)