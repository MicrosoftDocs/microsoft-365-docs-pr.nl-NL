---
title: Testfase van Microsoft 365 uitvoeren vanaf mijn aangepaste domein
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over het testen van e-mailfunctionaliteit vanaf mijn aangepast domein in een Microsoft 365-postvak met slechts twee testaccounts.
ms.openlocfilehash: 019f1786756a036132f95fd5e8ef8a1d42cd515b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914712"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="566a2-103">Testfase van Microsoft 365 uitvoeren vanaf mijn aangepaste domein</span><span class="sxs-lookup"><span data-stu-id="566a2-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="566a2-104">U kunt Microsoft 365 testen met de volgende vereisten en beperkingen:</span><span class="sxs-lookup"><span data-stu-id="566a2-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="566a2-105">Uw huidige e-mailprovider moet ondersteuning bieden voor het doorsturen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="566a2-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="566a2-106">U moet uw DNS-records voor Microsoft 365 beheren bij uw DNS-hostingprovider in plaats van dat Microsoft 365 dat voor u doet.</span><span class="sxs-lookup"><span data-stu-id="566a2-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="566a2-107">Zie [DNS-records toevoegen om het domein te verbinden](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="566a2-107">To learn more, see [Add DNS records to connect your domain](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

- <span data-ttu-id="566a2-108">Beschikbaarheidsinfo voor gebruikers op de andere e-mailserver is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="566a2-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="566a2-109">Beheerders kunnen niet alle gebruikersaccounts vanaf één locatie beheren.</span><span class="sxs-lookup"><span data-stu-id="566a2-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="566a2-110">Gebruikers kunnen mogelijk geen gebruik maken van Microsoft 365-spamfilters.</span><span class="sxs-lookup"><span data-stu-id="566a2-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

- <span data-ttu-id="566a2-111">Dit wordt aangeraden voor een heel klein aantal gebruikers en is enkel van toepassing op het gebruik van e-mail voor een testfase.</span><span class="sxs-lookup"><span data-stu-id="566a2-111">This is recommended for a very small number of users and only applies to the use of email for a pilot.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="566a2-112">Testfase van Microsoft 365 instellen</span><span class="sxs-lookup"><span data-stu-id="566a2-112">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="566a2-113">Volg deze stappen om een Microsoft 365-testfase in te stellen:</span><span class="sxs-lookup"><span data-stu-id="566a2-113">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="566a2-114">Stap 1: aanmelden bij het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="566a2-114">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="566a2-115">Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met uw werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="566a2-115">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="566a2-116">Selecteer **Instellingen** > **Domeinen** in het linker navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="566a2-116">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="566a2-117">Stap 2: controleren of u de eigenaar bent van het domein dat u wilt gebruiken</span><span class="sxs-lookup"><span data-stu-id="566a2-117">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="566a2-118">Op de pagina **Domeinen** selecteert u **Domein toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="566a2-118">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="566a2-119">Typ de domeinnaam in het vak, selecteer **Dit domein gebruiken** en selecteer vervolgens **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="566a2-119">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="566a2-120">Selecteer de services die u met uw domein wilt testen, zoals e-mail en chatberichten.</span><span class="sxs-lookup"><span data-stu-id="566a2-120">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="566a2-121">Volg de stapsgewijze instructies op de pagina **Domein verifiëren** en selecteer **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="566a2-121">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="566a2-122">Het doorvoeren van DNS-wijzigingen kan enkele minuten tot 72 uur duren.</span><span class="sxs-lookup"><span data-stu-id="566a2-122">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="566a2-123">Als de verificatie is gelukt, wordt u gevraagd uw DNS-records te wijzigen. </span><span class="sxs-lookup"><span data-stu-id="566a2-123">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="566a2-124">Stap 3: het domein in Exchange Online markeren als 'gedeeld'</span><span class="sxs-lookup"><span data-stu-id="566a2-124">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="566a2-125">In het Exchange-beheercentrum selecteert u in de sectie **E-mailstroom** de optie **Geaccepteerde domeinen** en selecteert u vervolgens het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="566a2-125">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="566a2-126">Dubbelklik op het venster om het te openen en selecteer **Interne relay**.</span><span class="sxs-lookup"><span data-stu-id="566a2-126">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="566a2-127">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="566a2-127">Select **Save**.</span></span>

    <span data-ttu-id="566a2-128">Het kan enkele minuten duren voordat deze instelling is doorgevoerd. </span><span class="sxs-lookup"><span data-stu-id="566a2-128">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="566a2-129">Stap 4: blokkering van de bestaande e-mailserver opheffen (optioneel)</span><span class="sxs-lookup"><span data-stu-id="566a2-129">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="566a2-130">Microsoft 365 maakt gebruik van Exchange Online Protection (EOP) voor bescherming tegen spam.</span><span class="sxs-lookup"><span data-stu-id="566a2-130">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="566a2-131">Met EOP kunt u uw bestaande e-mailserver blokkeren als een grote hoeveelheid spam door de huidige e-mailserver wordt doorgestuurd.</span><span class="sxs-lookup"><span data-stu-id="566a2-131">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="566a2-132">Als u de spambeveiliging voor uw andere e-mailprovider vertrouwt, kunt u de blokkering van de server in Microsoft 365 opheffen.</span><span class="sxs-lookup"><span data-stu-id="566a2-132">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="566a2-133">Als u de blokkering van uw bestaande e-mailserver opheft, kan spam die via de oorspronkelijke server binnenkomt, naar de Microsoft 365-postvakken worden gestuurd. U kunt dan niet evalueren hoe goed spam wordt tegengehouden in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="566a2-133">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="566a2-134">In het navigatiedeelvenster van het Exchange-beheercentrum selecteert u **Beveiliging** en vervolgens **Verbindingsfilter**.</span><span class="sxs-lookup"><span data-stu-id="566a2-134">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="566a2-135">In de **IP-acceptatielijst** selecteert u **+** en voegt u het IP-adres van de e-mailserver van uw huidige e-mailprovider toe.</span><span class="sxs-lookup"><span data-stu-id="566a2-135">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="566a2-136">Stap 5: gebruikersaccounts maken en het primaire antwoordadres instellen</span><span class="sxs-lookup"><span data-stu-id="566a2-136">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="566a2-137">Selecteer in het linker navigatiedeelvenster van het Microsoft 365-beheercentrum de opties **Gebruikers** > **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="566a2-137">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="566a2-138">Maak twee testaccounts door twee bestaande gebruikers toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="566a2-138">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="566a2-139">Voor elk account selecteert u **+ Een gebruiker toevoegen** en vult u de vereiste gegevens in, inclusief de wachtwoordmethode die u wilt testen.</span><span class="sxs-lookup"><span data-stu-id="566a2-139">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="566a2-140">Als u wilt dat het e-mailadres van een gebruiker ongewijzigd blijft, moet het veld **Gebruikersnaam** overeenkomen met het huidige e-mailadres van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="566a2-140">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="566a2-141">Kies de juiste licentie, klik op **Volgende** en klik vervolgens op **Toevoegen voltooien**.</span><span class="sxs-lookup"><span data-stu-id="566a2-141">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="566a2-142">Selecteer naast **Gebruikersnaam** de naam van het aangepaste domein in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="566a2-142">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="566a2-143">Selecteer **Maken** > **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="566a2-143">Select **Create** > **Close**.</span></span>

### <a name="step-6-configure-mail-to-flow-from-microsoft-365-or-office-365-to-email-server"></a><span data-ttu-id="566a2-144">Stap 6: \*\*e-mailberichten van Microsoft 365 of Office 365 naar een e-mailserver configureren</span><span class="sxs-lookup"><span data-stu-id="566a2-144">Step 6: \*\*Configure mail to flow from Microsoft 365 or Office 365 to Email server</span></span>

<span data-ttu-id="566a2-145">Hier moet u twee stappen voor volgen:</span><span class="sxs-lookup"><span data-stu-id="566a2-145">There are two steps for this:</span></span>

1. <span data-ttu-id="566a2-146">Configureer uw Microsoft 365-of Office 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="566a2-146">Configure your Microsoft 365 or Office 365 environment.</span></span>

2. <span data-ttu-id="566a2-147">Een connector van Microsoft 365 of Office 365 instellen op uw e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="566a2-147">Set up a connector from Microsoft 365 or Office 365 to your email server.</span></span>

### <a name="1-configure-your-microsoft-365-or-office-365-environment"></a><span data-ttu-id="566a2-148">1. Configureer uw Microsoft 365- of Office 365-omgeving</span><span class="sxs-lookup"><span data-stu-id="566a2-148">1. Configure your Microsoft 365 or Office 365 environment</span></span>

<span data-ttu-id="566a2-149">Controleer of u de volgende taken hebt uitgevoerd in Microsoft 365 of Office 365:</span><span class="sxs-lookup"><span data-stu-id="566a2-149">Make sure you have completed the following in Microsoft 365 or Office 365:</span></span>

1. <span data-ttu-id="566a2-150">Voor het instellen van connectors moet u machtigingen toewijzen voordat u aan de slag kunt.</span><span class="sxs-lookup"><span data-stu-id="566a2-150">To set up connectors, you need permissions assigned before you can begin.</span></span> <span data-ttu-id="566a2-151">Als u wilt controleren welke machtigingen u nodig hebt, raadpleegt u het item Microsoft 365 en Office 365-connectors in bij [Functiemachtigingen in EOP](../../security/office-365-security/feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="566a2-151">To check what permissions you need, see the Microsoft 365 and Office 365 connectors entry in the [Feature permissions in EOP](../../security/office-365-security/feature-permissions-in-eop.md) topic.</span></span>

2. <span data-ttu-id="566a2-152">Als u wilt dat EOP of Exchange Online e-mailberichten van uw e-mailservers naar Internet doorstuurt, doet u het volgende:</span><span class="sxs-lookup"><span data-stu-id="566a2-152">If you want EOP or Exchange Online to relay email from your email servers to the Internet, either:</span></span>

   - <span data-ttu-id="566a2-153">Gebruik een certificaat dat is geconfigureerd met een onderwerpnaam die overeenkomt met een geaccepteerd domein in Microsoft 365 of Office 365.</span><span class="sxs-lookup"><span data-stu-id="566a2-153">Use a certificate configured with a subject name that matches an accepted domain in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="566a2-154">Het is raadzaam om de naam van de algemene naam of alternatieve naam van uw certificaat te laten overeenkomen met het primaire SMTP-domein voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="566a2-154">We recommend that your certificate's common name or subject alternative name matches the primary SMTP domain for your organization.</span></span> <span data-ttu-id="566a2-155">Zie [vereisten voor uw on-premises e-mail omgeving](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="566a2-155">For details, see [Prerequisites for your on-premises email environment](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).</span></span>

   <span data-ttu-id="566a2-156">-OF-</span><span class="sxs-lookup"><span data-stu-id="566a2-156">-OR-</span></span>

   - <span data-ttu-id="566a2-157">Zorg ervoor dat alle domeinnamen van de organisatie en subdomeinen zijn geconfigureerd als geaccepteerde domeinen in Microsoft 365 of Office 365.</span><span class="sxs-lookup"><span data-stu-id="566a2-157">Make sure that all your organization sender domains and subdomains are configured as accepted domains in Microsoft 365 or Office 365.</span></span>

   <span data-ttu-id="566a2-158">Zie voor meer informatie over het definiëren van geaccepteerde domeinen [Geaccepteerde domeinen beheren in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) en [E-mailstroom inschakelen voor subdomeinen in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="566a2-158">For more information about defining accepted domains, see [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) and [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

3. <span data-ttu-id="566a2-159">Beslis of u de regels voor de e-mailstroom (ook wel transportregels genoemd) of domeinnamen wilt gebruiken voor het verzenden van e-mail van Microsoft 365 of Office 365 naar uw e-mailservers.</span><span class="sxs-lookup"><span data-stu-id="566a2-159">Decide whether you want to use mail flow rules (also known as transport rules) or domain names to deliver mail from Microsoft 365 or Office 365 to your email servers.</span></span> <span data-ttu-id="566a2-160">De meeste bedrijven kiezen voor het bezorgen van e-mail voor alle geaccepteerde domeinen.</span><span class="sxs-lookup"><span data-stu-id="566a2-160">Most businesses choose to deliver mail for all accepted domains.</span></span> <span data-ttu-id="566a2-161">Zie voor meer informatie [scenario: voorwaardelijke routering voor e-mail in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span><span class="sxs-lookup"><span data-stu-id="566a2-161">For more information, see [Scenario: Conditional mail routing in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span></span>

> [!NOTE]
> <span data-ttu-id="566a2-162">U kunt regels voor de e-mailstroom instellen zoals wordt beschreven in [de acties voor de e-mailstroom regel in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="566a2-162">You can set up mail flow rules as described in [Mail flow rule actions in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span> <span data-ttu-id="566a2-163">Het is bijvoorbeeld mogelijk dat u regels voor e-mailstroom met connectors wilt gebruiken als uw e-mailberichten momenteel via distributielijsten naar meerdere sites worden gestuurd.</span><span class="sxs-lookup"><span data-stu-id="566a2-163">For example, you might want to use mail flow rules with connectors if your mail is currently directed via distribution lists to multiple sites.</span></span>

### <a name="2-set-up-a-connector-from-microsoft-365-or-office-365-to-your-email-server"></a><span data-ttu-id="566a2-164">2. Een connector van Microsoft 365 of Office 365 instellen op uw e-mailserver.</span><span class="sxs-lookup"><span data-stu-id="566a2-164">2. Set up a connector from Microsoft 365 or Office 365 to your email server</span></span>

<span data-ttu-id="566a2-165">Als u een connector wilt maken in Microsoft 365 of Office 365, klikt u op **Beheer** en klikt u vervolgens op **Exchange** om naar het Exchange-Beheercentrum te gaan.</span><span class="sxs-lookup"><span data-stu-id="566a2-165">To create a connector in Microsoft 365 or Office 365, click **Admin**, and then click **Exchange** to go to the Exchange admin center.</span></span> <span data-ttu-id="566a2-166">Klik vervolgens in het bij **e-mailstroom** op **connectors**.</span><span class="sxs-lookup"><span data-stu-id="566a2-166">Next, click **mail flow**, and click **connectors**.</span></span>

<span data-ttu-id="566a2-167">Connectors instellen met de wizard.</span><span class="sxs-lookup"><span data-stu-id="566a2-167">Set up connectors using the wizard.</span></span>

<span data-ttu-id="566a2-168">Klik op het plusteken **+** om de wizard te starten.</span><span class="sxs-lookup"><span data-stu-id="566a2-168">To start the wizard, click the plus symbol **+**.</span></span> <span data-ttu-id="566a2-169">Kies in het eerste scherm **Van** Office 365 en **Naar** de e-mailserver van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="566a2-169">On the first screen, choose **From** Office 365 and **To** Your Organization Mail server.</span></span>

<span data-ttu-id="566a2-170">Klik op **Volgende** en volg de instructies van de wizard.</span><span class="sxs-lookup"><span data-stu-id="566a2-170">Click **Next**, and follow the instructions in the wizard.</span></span> <span data-ttu-id="566a2-171">Klik op de koppelingen **Help** of **Meer informatie** als u meer informatie nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="566a2-171">Click the **Help** or **Learn More** links if you need more information.</span></span> <span data-ttu-id="566a2-172">De wizard begeleidt u bij het instellen.</span><span class="sxs-lookup"><span data-stu-id="566a2-172">The wizard will guide you through setup.</span></span> <span data-ttu-id="566a2-173">Controleer aan het uiteinde of de connector zich valideert.</span><span class="sxs-lookup"><span data-stu-id="566a2-173">At the end, make sure your connector validates.</span></span> <span data-ttu-id="566a2-174">Als het niet lukt om de connector te valideren, dubbelklikt u op het bericht dat wordt weergegeven om meer informatie weer te geven. Zie [Connectors valideren](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) voor hulp bij het oplossen van problemen.</span><span class="sxs-lookup"><span data-stu-id="566a2-174">If the connector does not validate, double-click the message displayed to get more information, and see [Validate connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) for help resolving issues.</span></span>



### <a name="step-7-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="566a2-175">Stap 7: DNS-records bijwerken bij uw DNS-hostingprovider</span><span class="sxs-lookup"><span data-stu-id="566a2-175">Step 7: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="566a2-176">Meld u aan bij de website van uw DNS-hostingprovider en volg de instructies op [DNS-records toevoegen om het domein te verbinden](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="566a2-176">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="566a2-177">**Maak de volgende twee uitzonderingen:**</span><span class="sxs-lookup"><span data-stu-id="566a2-177">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="566a2-178">Maak geen nieuwe MX-record of wijzig uw bestaande MX-record niet.</span><span class="sxs-lookup"><span data-stu-id="566a2-178">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="566a2-179">Als u al een SPF-record (Sender Policy Framework) hebt voor uw vorige e-mailprovider, voegt u 'include:spf.protection.outlook.com' toe aan de huidige TXT-record in plaats van een nieuwe SPF (TXT)-record te maken voor Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="566a2-179">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="566a2-180">Bijvoorbeeld 'v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all'.</span><span class="sxs-lookup"><span data-stu-id="566a2-180">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="566a2-181">Als u geen SPF-record hebt, wijzigt u de door Microsoft 365 aanbevolen record om het domein voor uw huidige e-mailprovider op te nemen en voegt u spf.protection.outlook.com toe.</span><span class="sxs-lookup"><span data-stu-id="566a2-181">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="566a2-182">Hiermee autoriseert u uitgaande berichten van beide e-mailsystemen.</span><span class="sxs-lookup"><span data-stu-id="566a2-182">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-8-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="566a2-183">Stap 8: doorsturen van e-mail instellen bij uw huidige provider</span><span class="sxs-lookup"><span data-stu-id="566a2-183">Step 8: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="566a2-184">Stel bij uw huidige e-mailprovider het doorsturen van e-mail in voor de e-mailaccounts van uw gebruikers voor het onmicrosoft.com-domein:</span><span class="sxs-lookup"><span data-stu-id="566a2-184">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="566a2-185">Postvak van gebruiker A doorsturen naar gebruikera@uwbedrijf.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="566a2-185">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="566a2-186">Postvak van gebruiker B doorsturen naar gebruikerb@uwbedrijf.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="566a2-186">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="566a2-187">Wanneer u deze stap hebt voltooid, zijn alle e-mailberichten die naar gebruikera@uwbedrijf.onmicrosoft.com en gebruikerb@uwbedrijf.onmicrosoft.com zijn verzonden, beschikbaar in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="566a2-187">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="566a2-188">Neem contact op met uw huidige e-mailprovider voor de juiste stappen voor het instellen van het doorsturen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="566a2-188">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="566a2-189">U hoeft geen kopie van berichten te bewaren bij de huidige e-mailprovider. </span><span class="sxs-lookup"><span data-stu-id="566a2-189">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="566a2-190">Bij de meeste providers blijft het antwoordadres van de afzender behouden bij het doorsturen van e-mail. Antwoorden worden dus verzonden naar de oorspronkelijke afzender. </span><span class="sxs-lookup"><span data-stu-id="566a2-190">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-9-test-mail-flow"></a><span data-ttu-id="566a2-191">Stap 9: e-mailstroom testen</span><span class="sxs-lookup"><span data-stu-id="566a2-191">Step 9: Test mail flow</span></span>

1. <span data-ttu-id="566a2-192">Meld u aan bij Outlook Web App met de referenties van gebruiker A.</span><span class="sxs-lookup"><span data-stu-id="566a2-192">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="566a2-193">Voer de volgende tests uit:</span><span class="sxs-lookup"><span data-stu-id="566a2-193">Perform these tests:</span></span>

    - <span data-ttu-id="566a2-194">Test lokale Microsoft-e-mail door een e-mailbericht te verzenden naar bijvoorbeeld gebruiker B. Het e-mailbericht wordt onmiddellijk bezorgd.</span><span class="sxs-lookup"><span data-stu-id="566a2-194">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="566a2-195">In dit scenario wordt het bericht niet gerouteerd naar het postvak van gebruiker B op de oorspronkelijke server, omdat het Microsoft 365-postvak lokaal is.</span><span class="sxs-lookup"><span data-stu-id="566a2-195">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="566a2-196">Test het verzenden van e-mail naar een gebruiker in het bestaande e-mailsysteem door een e-mailbericht te verzenden naar bijvoorbeeld gebruiker C. Het e-mailbericht wordt in het postvak van gebruiker C op de oorspronkelijke e-mailserver bezorgd.</span><span class="sxs-lookup"><span data-stu-id="566a2-196">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="566a2-197">Controleer of het doorsturen correct is ingesteld vanaf een extern account of vanaf een e-mailaccount van een werknemer in het bestaande e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="566a2-197">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="566a2-198">Bijvoorbeeld: verzend vanaf het oorspronkelijke serveraccount voor gebruiker C of vanaf een Hotmail-account een e-mailbericht naar gebruiker A en controleer of het wordt bezorgd in het Microsoft 365-postvak voor gebruiker A.</span><span class="sxs-lookup"><span data-stu-id="566a2-198">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-10-move-mailbox-contents"></a><span data-ttu-id="566a2-199">Stap 10: inhoud van postvak verplaatsen</span><span class="sxs-lookup"><span data-stu-id="566a2-199">Step 10: Move mailbox contents</span></span>

<span data-ttu-id="566a2-200">Aangezien er slechts twee testgebruikers worden verplaatst en gebruiker A en gebruiker B beide Outlook gebruiken, kunt u de e-mail verplaatsen door het oude PST-bestand te openen in het nieuwe Outlook-profiel en de berichten, agenda-items, contactpersonen, enzovoort te kopiëren.</span><span class="sxs-lookup"><span data-stu-id="566a2-200">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="566a2-201">Zie [E-mail, contactpersonen en agenda importeren vanuit een PST-bestand in Outlook](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="566a2-201">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="566a2-202">Nadat de items naar de juiste locaties in het Microsoft 365-postvak zijn geïmporteerd, kunnen ze overal op elk apparaat worden geopend.</span><span class="sxs-lookup"><span data-stu-id="566a2-202">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>