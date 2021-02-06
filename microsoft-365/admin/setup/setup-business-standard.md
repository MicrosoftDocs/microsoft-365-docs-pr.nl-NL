---
title: Microsoft 365 Business Standard instellen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Meer informatie over het instellen van uw abonnement op Microsoft 365 Business Standard.
ms.openlocfilehash: 7dce8fd4572e8434dd1396f98d94e3eaf0ddf7dc
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126115"
---
# <a name="set-up-microsoft-business-standard"></a><span data-ttu-id="2e9c8-103">Microsoft Business Standard installeren</span><span class="sxs-lookup"><span data-stu-id="2e9c8-103">Set up Microsoft Business Standard</span></span>



## <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="2e9c8-104">Uw domein toevoegen om uw aanmelding te personaliseren</span><span class="sxs-lookup"><span data-stu-id="2e9c8-104">Add your domain to personalize sign-in</span></span>

<span data-ttu-id="2e9c8-105">Wanneer u Microsoft 365 Business Standard aanschaft, hebt u de mogelijkheid om een domein te gebruiken dat u bezit of een domein te kopen tijdens de registratie.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-105">When you purchase Microsoft 365 Business Standard, you have the option of using a domain you own, or buying one during the sign-up.</span></span>

- <span data-ttu-id="2e9c8-106">Als u tijdens de registratie een nieuw domein hebt gekocht, is uw domein helemaal ingesteld en kunt u doorgaan met [Gebruikers toevoegen en licenties toewijzen](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="2e9c8-106">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

1. <span data-ttu-id="2e9c8-107">Meld u aan bij [Microsoft 365-beheercentrum](https://admin.microsoft.com) met uw globale-beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-107">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="2e9c8-108">Kies **Naar setup** om de wizard te starten.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-108">Choose **Go to setup** to start the wizard.</span></span>

3. <span data-ttu-id="2e9c8-109">Op de pagina **Uw Office-apps installeren** kunt u desgewenst de apps op uw eigen computer installeren.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-109">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="2e9c8-110">Voer in de stap **Domein toevoegen** de domeinnaam in die u wilt gebruiken (zoals contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2e9c8-110">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2e9c8-111">Als u tijdens de registratie een domein hebt gekocht, ziet u de stap **Een domein toevoegen** hier niet.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-111">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="2e9c8-112">Ga in plaats daarvan naar [Gebruikers toevoegen](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="2e9c8-112">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    
4. <span data-ttu-id="2e9c8-113">Volg de stappen in de wizard om [DNS-records te maken bij een DNS-hostingprovider voor Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) waarmee wordt geverifieerd of u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-113">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="2e9c8-114">Als u weet wat uw domeinhost is, raadpleegt u ook de [hostspecifieke instructies](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="2e9c8-114">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="2e9c8-115">Als uw hostingprovider GoDaddy of een andere host is die is ingeschakeld met [domeinverbinding](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), is het proces eenvoudig en wordt u automatisch gevraagd om u aan te melden en u namens Microsoft te laten verifiëren.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-115">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Selecteer Autoriseren op de pagina GoDaddy Toegang bevestigen.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a><span data-ttu-id="2e9c8-117">Gebruikers toevoegen en licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="2e9c8-117">Add users and assign licenses</span></span>

<span data-ttu-id="2e9c8-118">U kunt gebruikers toevoegen in de wizard, maar u kunt ook [gebruikers later toevoegen](../add-users/add-users.md) in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-118">You can add users in the wizard, but you can also [add users later](../add-users/add-users.md) in the admin center.</span></span> <span data-ttu-id="2e9c8-119">Als u een lokale domeincontroller hebt, kunt u ook gebruikers toevoegen met [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="2e9c8-119">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

## <a name="add-users-in-the-wizard"></a><span data-ttu-id="2e9c8-120">Gebruikers toevoegen in de wizard</span><span class="sxs-lookup"><span data-stu-id="2e9c8-120">Add users in the wizard</span></span>

<span data-ttu-id="2e9c8-121">Alle gebruikers die u toevoegt in de wizard krijgen automatisch een Microsoft 365 Business Standard-licentie toegewezen.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-121">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Standard license.</span></span>

1. <span data-ttu-id="2e9c8-122">Als uw Microsoft 365 Business Standard-abonnement bestaande gebruikers heeft (bijvoorbeeld als u Azure AD Connect hebt gebruikt), hebt u een optie om nu licenties aan hen toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-122">If your Microsoft 365 Business Standard subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="2e9c8-123">Wijs nu licenties aan hen toe.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-123">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="2e9c8-124">Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie voor het delen van referenties met de nieuwe gebruikers die u hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-124">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="2e9c8-125">U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-125">You can choose to print them out, email them, or download them.</span></span>

## <a name="connect-your-domain"></a><span data-ttu-id="2e9c8-126">Uw domein verbinden</span><span class="sxs-lookup"><span data-stu-id="2e9c8-126">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="2e9c8-127">Als u ervoor hebt gekozen om het domein. onmicrosoft te gebruiken of Azure AD Connect hebt gebruikt voor het instellen van gebruikers, wordt deze stap niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-127">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="2e9c8-128">Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-128">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="2e9c8-129">Meestal wordt uw registrar automatisch gedetecteerd met de wizard Setup, en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-129">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="2e9c8-130">Zo niet, gaat u naar[Naamservers wijzigen voor het instellen van Office 365 bij een domeinregistrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span><span class="sxs-lookup"><span data-stu-id="2e9c8-130">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="2e9c8-131">Als u bestaande DNS-records hebt, bijvoorbeeld een bestaande website, maar uw DNS-host is ingeschakeld voor [domeinverbinding](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), kiest u **Records toevoegen voor mij**.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-131">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="2e9c8-132">Accepteer alle standaardinstellingen op de pagina **Uw online services kiezen**, kies **Volgende** en kies **Autoriseren** op de pagina van uw DNS-host.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-132">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="2e9c8-133">Als u bestaande DNS-records hebt met andere DNS-hosts (niet ingeschakeld voor domeinverbinding), kunt u uw eigen DNS-records beheren om ervoor te zorgen dat de bestaande services verbonden blijven.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-133">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="2e9c8-134">Zie [basisprincipes van domeinen](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-134">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

2. <span data-ttu-id="2e9c8-135">Volg de stappen in de wizard en e-mail en andere services worden voor u ingesteld.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-135">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

    <span data-ttu-id="2e9c8-136">Wanneer het aanmeldingsproces is voltooid, wordt u doorgestuurd naar het beheercentrum, waar u een wizard volgt om Office-apps te installeren, uw domein toe te voegen, gebruikers toe te voegen en licenties toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-136">When the signup process is complete, you'll be directed to the admin center, where you'll follow a wizard to install Office apps, add your domain, add users, and assign licenses.</span></span> <span data-ttu-id="2e9c8-137">Nadat u de eerste installatie hebt voltooid, kunt u de pagina **Instellingen** in het beheercentrum gebruiken om door te gaan met het instellen en configureren van de services die bij uw abonnementen worden geleverd.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-137">After you complete the initial setup, you can use the **Setup** page in the admin center to continue setting up and configuring the services that come with your subscriptions.</span></span>

    <span data-ttu-id="2e9c8-138">Voor meer informatie over de installatiewizard en de **Installatie** pagina in het beheercentrum, raadpleegt u [Verschil tussen de installatiewizard en de installatiepagina](o365-setup-wizard-and-setup-page.md).</span><span class="sxs-lookup"><span data-stu-id="2e9c8-138">For more information about the setup wizard and the admin center **Setup** page, see [Difference between the setup wizard and the Setup page](o365-setup-wizard-and-setup-page.md).</span></span>

## <a name="finish-setting-up"></a><span data-ttu-id="2e9c8-139">Installatie voltooien</span><span class="sxs-lookup"><span data-stu-id="2e9c8-139">Finish setting up</span></span>

### <a name="set-up-outlook-for-email"></a><span data-ttu-id="2e9c8-140">Outlook voor e-mail instellen</span><span class="sxs-lookup"><span data-stu-id="2e9c8-140">Set up Outlook for email</span></span>

1. <span data-ttu-id="2e9c8-141">Zoek in het Startmenu van Windows naar Outlook en selecteer deze.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-141">On the Windows Start menu, search for Outlook, and select it.</span></span>

    <span data-ttu-id="2e9c8-142">(Als u een Mac gebruikt, kunt u Outlook openen in de werkbalk of opzoeken via Finder.)</span><span class="sxs-lookup"><span data-stu-id="2e9c8-142">(If you're using a Mac, open Outlook from the toolbar or locate it using the Finder.)</span></span>

    <span data-ttu-id="2e9c8-143">Kies **Volgende** in het welkomstscherm als u Outlook net hebt geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-143">If you've just installed Outlook, on the Welcome page, select **Next**.</span></span>

2. <span data-ttu-id="2e9c8-144">Kies **Bestand** \> **Info** \> **Account toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-144">Choose **File** \> **Info** \> **Add Account**.</span></span>

3. <span data-ttu-id="2e9c8-145">Voer uw Microsoft-e-mailadres in en selecteer **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-145">Enter your Microsoft email address and select **Connect**.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
<span data-ttu-id="2e9c8-146">Meer informatie vindt u op [Outlook instellen voor e-mail](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span><span class="sxs-lookup"><span data-stu-id="2e9c8-146">More at [Set up Outlook for email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).</span></span>
  
### <a name="import-email"></a><span data-ttu-id="2e9c8-147">E-mail importeren</span><span class="sxs-lookup"><span data-stu-id="2e9c8-147">Import email</span></span>

<span data-ttu-id="2e9c8-148">Als u Outlook met een ander e-mailaccount hebt gebruikt, kunt u de e-mail, agenda en contactpersonen van dat account importeren in uw nieuwe Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-148">If you were using Outlook with another email account, you can import your previous email, calendar, and contacts into your new Microsoft account.</span></span>
  
1. <span data-ttu-id="2e9c8-149">**Uw oude e-mailberichten exporteren**</span><span class="sxs-lookup"><span data-stu-id="2e9c8-149">**Export your old email**</span></span>

    <span data-ttu-id="2e9c8-150">Kies in Outlook **Bestand** \> **Openen &amp;Exporteren**\> **Importeren/Exporteren**.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-150">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>

    <span data-ttu-id="2e9c8-151">Selecteer **Naar een bestand exporteren** en volg de stappen voor het exporteren van uw Outlook-gegevensbestand (.pst) en eventuele submappen.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-151">Select **Export to a File** and then follow the steps to export your Outlook Data File (.pst) and any subfolders.</span></span>

2. <span data-ttu-id="2e9c8-152">**Uw oude e-mails importeren**</span><span class="sxs-lookup"><span data-stu-id="2e9c8-152">**Import your old email**</span></span>

    <span data-ttu-id="2e9c8-153">Kies in Outlook opnieuw **Bestand** \> **Openen &amp;Exporteren** \> **Importeren/Exporteren**.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-153">In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.</span></span>

    <span data-ttu-id="2e9c8-154">Selecteer deze keer **Importeren uit een ander programma of bestand** en volg de stappen om het back-upbestand dat u hebt gemaakt tijdens het exporteren van uw oude e-mails te importeren.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-154">This time, select **Import from another program or file** and follow the steps to import the backup file you created when you exported your old email.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
<span data-ttu-id="2e9c8-155">Meer informatie vindt u op [E-mails in Outlook importeren](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span><span class="sxs-lookup"><span data-stu-id="2e9c8-155">More at [Import email with Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).</span></span>

<span data-ttu-id="2e9c8-156">U kunt ook het Exchange-beheercentrum gebruiken om ieders e-mails te importeren.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-156">You can also use Exchange admin center to import everyone's email.</span></span> <span data-ttu-id="2e9c8-157">Voor meer informatie raadpleegt u [meerdere e-mailaccounts migreren](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="2e9c8-157">For more information, see [migrate multiple email accounts](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
### <a name="use-a-public-website"></a><span data-ttu-id="2e9c8-158">Een openbare website gebruiken</span><span class="sxs-lookup"><span data-stu-id="2e9c8-158">Use a public website</span></span>

<span data-ttu-id="2e9c8-159">Microsoft 365 bevat geen openbare website voor uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-159">Microsoft 365 doesn't include a public website for your business.</span></span> <span data-ttu-id="2e9c8-160">Als u er toch een wilt maken, kunt u een Microsoft-partner overwegen, zoals GoDaddy of WIX.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-160">If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.</span></span>
  
1. <span data-ttu-id="2e9c8-161">Ga in het beheercentrum naar **Resources** en kies vervolgens **Openbare website**.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-161">From the admin center, go to **Resources**, and then select **Public website**.</span></span>

2. <span data-ttu-id="2e9c8-162">Kies **Meer informatie** onder een van de opties en registreer u vervolgens bij een websitepartner. Gebruik daarna de hulpmiddelen van deze partner om uw website te configureren en ontwerpen.</span><span class="sxs-lookup"><span data-stu-id="2e9c8-162">Select **Learn more** under one of the options, and then sign up with a website partner and use their tools to set up and design your site.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

<span data-ttu-id="2e9c8-163">Meer informatie vindt u op [Een openbare website gebruiken](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="2e9c8-163">More at [Use a public website](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>