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
ms.openlocfilehash: bfcb2bda4d560ab629ddebed88ac1d55e6224c05
ms.sourcegitcommit: 5f980a9eb5aca61cf3662ef0bc65dec215e21656
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/20/2020
ms.locfileid: "45186041"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="a37e9-103">Testfase van Microsoft 365 uitvoeren vanaf mijn aangepaste domein</span><span class="sxs-lookup"><span data-stu-id="a37e9-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="a37e9-104">U kunt Microsoft 365 testen met de volgende vereisten en beperkingen:</span><span class="sxs-lookup"><span data-stu-id="a37e9-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="a37e9-105">Uw huidige e-mailprovider moet ondersteuning bieden voor het doorsturen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="a37e9-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="a37e9-106">U moet uw DNS-records voor Microsoft 365 beheren bij uw DNS-hostingprovider in plaats van dat Microsoft 365 dat voor u doet.</span><span class="sxs-lookup"><span data-stu-id="a37e9-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="a37e9-107">Zie [DNS-records toevoegen om het domein te verbinden](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a37e9-107">To learn more, see [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

- <span data-ttu-id="a37e9-108">Beschikbaarheidsinfo voor gebruikers op de andere e-mailserver is niet beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a37e9-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="a37e9-109">Beheerders kunnen niet alle gebruikersaccounts vanaf één locatie beheren.</span><span class="sxs-lookup"><span data-stu-id="a37e9-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="a37e9-110">Gebruikers kunnen mogelijk geen gebruik maken van Microsoft 365-spamfilters.</span><span class="sxs-lookup"><span data-stu-id="a37e9-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="a37e9-111">Testfase van Microsoft 365 instellen</span><span class="sxs-lookup"><span data-stu-id="a37e9-111">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="a37e9-112">Volg deze stappen om een Microsoft 365-testfase in te stellen:</span><span class="sxs-lookup"><span data-stu-id="a37e9-112">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="a37e9-113">Stap 1: aanmelden bij het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="a37e9-113">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="a37e9-114">Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met uw werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="a37e9-114">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="a37e9-115">Selecteer **Instellingen** > **Domeinen** in het linker navigatiedeelvenster.</span><span class="sxs-lookup"><span data-stu-id="a37e9-115">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="a37e9-116">Stap 2: controleren of u de eigenaar bent van het domein dat u wilt gebruiken</span><span class="sxs-lookup"><span data-stu-id="a37e9-116">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="a37e9-117">Op de pagina **Domeinen** selecteert u **Domein toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a37e9-117">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="a37e9-118">Typ de domeinnaam in het vak, selecteer **Dit domein gebruiken** en selecteer vervolgens **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="a37e9-118">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="a37e9-119">Selecteer de services die u met uw domein wilt testen, zoals e-mail en chatberichten.</span><span class="sxs-lookup"><span data-stu-id="a37e9-119">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="a37e9-120">Volg de stapsgewijze instructies op de pagina **Domein verifiëren** en selecteer **Verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="a37e9-120">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="a37e9-121">Het doorvoeren van DNS-wijzigingen kan enkele minuten tot 72 uur duren.</span><span class="sxs-lookup"><span data-stu-id="a37e9-121">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="a37e9-122">Als de verificatie is gelukt, wordt u gevraagd uw DNS-records te wijzigen. </span><span class="sxs-lookup"><span data-stu-id="a37e9-122">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="a37e9-123">Stap 3: het domein in Exchange Online markeren als 'gedeeld'</span><span class="sxs-lookup"><span data-stu-id="a37e9-123">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="a37e9-124">In het Exchange-beheercentrum selecteert u in de sectie **E-mailstroom** de optie **Geaccepteerde domeinen** en selecteert u vervolgens het domein dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="a37e9-124">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="a37e9-125">Dubbelklik op het venster om het te openen en selecteer **Interne relay**.</span><span class="sxs-lookup"><span data-stu-id="a37e9-125">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="a37e9-126">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="a37e9-126">Select **Save**.</span></span>

    <span data-ttu-id="a37e9-127">Het kan enkele minuten duren voordat deze instelling is doorgevoerd. </span><span class="sxs-lookup"><span data-stu-id="a37e9-127">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="a37e9-128">Stap 4: blokkering van de bestaande e-mailserver opheffen (optioneel)</span><span class="sxs-lookup"><span data-stu-id="a37e9-128">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="a37e9-129">Microsoft 365 maakt gebruik van Exchange Online Protection (EOP) voor bescherming tegen spam.</span><span class="sxs-lookup"><span data-stu-id="a37e9-129">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="a37e9-130">Met EOP kunt u uw bestaande e-mailserver blokkeren als een grote hoeveelheid spam door de huidige e-mailserver wordt doorgestuurd.</span><span class="sxs-lookup"><span data-stu-id="a37e9-130">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="a37e9-131">Als u de spambeveiliging voor uw andere e-mailprovider vertrouwt, kunt u de blokkering van de server in Microsoft 365 opheffen.</span><span class="sxs-lookup"><span data-stu-id="a37e9-131">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="a37e9-132">Als u de blokkering van uw bestaande e-mailserver opheft, kan spam die via de oorspronkelijke server binnenkomt, naar de Microsoft 365-postvakken worden gestuurd. U kunt dan niet evalueren hoe goed spam wordt tegengehouden in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a37e9-132">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="a37e9-133">In het navigatiedeelvenster van het Exchange-beheercentrum selecteert u **Beveiliging** en vervolgens **Verbindingsfilter**.</span><span class="sxs-lookup"><span data-stu-id="a37e9-133">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="a37e9-134">In de **IP-acceptatielijst** selecteert u **+** en voegt u het IP-adres van de e-mailserver van uw huidige e-mailprovider toe.</span><span class="sxs-lookup"><span data-stu-id="a37e9-134">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="a37e9-135">Stap 5: gebruikersaccounts maken en het primaire antwoordadres instellen</span><span class="sxs-lookup"><span data-stu-id="a37e9-135">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="a37e9-136">Selecteer in het linker navigatiedeelvenster van het Microsoft 365-beheercentrum de opties **Gebruikers** > **Actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="a37e9-136">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="a37e9-137">Maak twee testaccounts door twee bestaande gebruikers toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="a37e9-137">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="a37e9-138">Voor elk account selecteert u **+ Een gebruiker toevoegen** en vult u de vereiste gegevens in, inclusief de wachtwoordmethode die u wilt testen.</span><span class="sxs-lookup"><span data-stu-id="a37e9-138">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="a37e9-139">Als u wilt dat het e-mailadres van een gebruiker ongewijzigd blijft, moet het veld **Gebruikersnaam** overeenkomen met het huidige e-mailadres van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="a37e9-139">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="a37e9-140">Kies de juiste licentie, klik op **Volgende** en klik vervolgens op **Toevoegen voltooien**.</span><span class="sxs-lookup"><span data-stu-id="a37e9-140">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="a37e9-141">Selecteer naast **Gebruikersnaam** de naam van het aangepaste domein in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="a37e9-141">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="a37e9-142">Selecteer **Maken** > **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="a37e9-142">Select **Create** > **Close**.</span></span>

### <a name="step-6-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="a37e9-143">Stap 6: DNS-records bijwerken bij uw DNS-hostingprovider</span><span class="sxs-lookup"><span data-stu-id="a37e9-143">Step 6: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="a37e9-144">Meld u aan bij de website van uw DNS-hostingprovider en volg de instructies op [DNS-records toevoegen om het domein te verbinden](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="a37e9-144">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

<span data-ttu-id="a37e9-145">**Maak de volgende twee uitzonderingen:**</span><span class="sxs-lookup"><span data-stu-id="a37e9-145">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="a37e9-146">Maak geen nieuwe MX-record of wijzig uw bestaande MX-record niet.</span><span class="sxs-lookup"><span data-stu-id="a37e9-146">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="a37e9-147">Als u al een SPF-record (Sender Policy Framework) hebt voor uw vorige e-mailprovider, voegt u 'include:spf.protection.outlook.com' toe aan de huidige TXT-record in plaats van een nieuwe SPF (TXT)-record te maken voor Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a37e9-147">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="a37e9-148">Bijvoorbeeld 'v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all'.</span><span class="sxs-lookup"><span data-stu-id="a37e9-148">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="a37e9-149">Als u geen SPF-record hebt, wijzigt u de door Microsoft 365 aanbevolen record om het domein voor uw huidige e-mailprovider op te nemen en voegt u spf.protection.outlook.com toe.</span><span class="sxs-lookup"><span data-stu-id="a37e9-149">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="a37e9-150">Hiermee autoriseert u uitgaande berichten van beide e-mailsystemen.</span><span class="sxs-lookup"><span data-stu-id="a37e9-150">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-7-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="a37e9-151">Stap 7: doorsturen van e-mail instellen bij uw huidige provider</span><span class="sxs-lookup"><span data-stu-id="a37e9-151">Step 7: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="a37e9-152">Stel bij uw huidige e-mailprovider het doorsturen van e-mail in voor de e-mailaccounts van uw gebruikers voor het onmicrosoft.com-domein:</span><span class="sxs-lookup"><span data-stu-id="a37e9-152">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="a37e9-153">Postvak van gebruiker A doorsturen naar gebruikera@uwbedrijf.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a37e9-153">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="a37e9-154">Postvak van gebruiker B doorsturen naar gebruikerb@uwbedrijf.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a37e9-154">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="a37e9-155">Wanneer u deze stap hebt voltooid, zijn alle e-mailberichten die naar gebruikera@uwbedrijf.onmicrosoft.com en gebruikerb@uwbedrijf.onmicrosoft.com zijn verzonden, beschikbaar in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a37e9-155">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="a37e9-156">Neem contact op met uw huidige e-mailprovider voor de juiste stappen voor het instellen van het doorsturen van e-mail.</span><span class="sxs-lookup"><span data-stu-id="a37e9-156">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="a37e9-157">U hoeft geen kopie van berichten te bewaren bij de huidige e-mailprovider. </span><span class="sxs-lookup"><span data-stu-id="a37e9-157">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="a37e9-158">Bij de meeste providers blijft het antwoordadres van de afzender behouden bij het doorsturen van e-mail. Antwoorden worden dus verzonden naar de oorspronkelijke afzender. </span><span class="sxs-lookup"><span data-stu-id="a37e9-158">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-8-test-mail-flow"></a><span data-ttu-id="a37e9-159">Stap 8: e-mailstroom testen</span><span class="sxs-lookup"><span data-stu-id="a37e9-159">Step 8: Test mail flow</span></span>

1. <span data-ttu-id="a37e9-160">Meld u aan bij Outlook Web App met de referenties van gebruiker A.</span><span class="sxs-lookup"><span data-stu-id="a37e9-160">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="a37e9-161">Voer de volgende tests uit:</span><span class="sxs-lookup"><span data-stu-id="a37e9-161">Perform these tests:</span></span>

    - <span data-ttu-id="a37e9-162">Test lokale Microsoft-e-mail door een e-mailbericht te verzenden naar bijvoorbeeld gebruiker B. Het e-mailbericht wordt onmiddellijk bezorgd.</span><span class="sxs-lookup"><span data-stu-id="a37e9-162">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="a37e9-163">In dit scenario wordt het bericht niet gerouteerd naar het postvak van gebruiker B op de oorspronkelijke server, omdat het Microsoft 365-postvak lokaal is.</span><span class="sxs-lookup"><span data-stu-id="a37e9-163">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="a37e9-164">Test het verzenden van e-mail naar een gebruiker in het bestaande e-mailsysteem door een e-mailbericht te verzenden naar bijvoorbeeld gebruiker C. Het e-mailbericht wordt in het postvak van gebruiker C op de oorspronkelijke e-mailserver bezorgd.</span><span class="sxs-lookup"><span data-stu-id="a37e9-164">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="a37e9-165">Controleer of het doorsturen correct is ingesteld vanaf een extern account of vanaf een e-mailaccount van een werknemer in het bestaande e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="a37e9-165">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="a37e9-166">Bijvoorbeeld: verzend vanaf het oorspronkelijke serveraccount voor gebruiker C of vanaf een Hotmail-account een e-mailbericht naar gebruiker A en controleer of het wordt bezorgd in het Microsoft 365-postvak voor gebruiker A.</span><span class="sxs-lookup"><span data-stu-id="a37e9-166">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-9-move-mailbox-contents"></a><span data-ttu-id="a37e9-167">Stap 9: inhoud van postvak verplaatsen</span><span class="sxs-lookup"><span data-stu-id="a37e9-167">Step 9: Move mailbox contents</span></span>

<span data-ttu-id="a37e9-168">Aangezien er slechts twee testgebruikers worden verplaatst en gebruiker A en gebruiker B beide Outlook gebruiken, kunt u de e-mail verplaatsen door het oude PST-bestand te openen in het nieuwe Outlook-profiel en de berichten, agenda-items, contactpersonen, enzovoort te kopiëren.</span><span class="sxs-lookup"><span data-stu-id="a37e9-168">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="a37e9-169">Zie [E-mail, contactpersonen en agenda importeren vanuit een PST-bestand in Outlook](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a37e9-169">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="a37e9-170">Nadat de items naar de juiste locaties in het Microsoft 365-postvak zijn geïmporteerd, kunnen ze overal op elk apparaat worden geopend.</span><span class="sxs-lookup"><span data-stu-id="a37e9-170">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>

<span data-ttu-id="a37e9-171">Als er meer postvakken betrokken zijn of als Outlook niet wordt gebruikt, kunt u de migratiehulpprogramma's in het Exchange-beheercentrum gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a37e9-171">When more mailboxes are involved, or if employees are not using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="a37e9-172">Ga aan de slag door naar het Exchange-beheercentrum te gaan en de aanwijzingen te volgen in [E-mail migreren vanaf een IMAP-server naar Exchange Online-postvakken].</span><span class="sxs-lookup"><span data-stu-id="a37e9-172">To get started, go to Exchange admin center, and follow the directions in [Migrate Email from an IMAP Server to Exchange Online Mailboxes – we need a new article resource].</span></span>