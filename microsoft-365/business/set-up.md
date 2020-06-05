---
title: Microsoft 365 Business Premium instellen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Ontdek de installatiestappen voor Microsoft 365 Business Premium, waaronder het toevoegen van een domein en gebruikers, het instellen van beveiligingsbeleid en meer.
ms.openlocfilehash: 58dc5eb71b41f5b9316e8d68cc3fc3c8c91748b3
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564905"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="a2c62-103">Microsoft 365 Business Premium instellen in de wizard Setup</span><span class="sxs-lookup"><span data-stu-id="a2c62-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="a2c62-104">Bekijk deze video voor een overzicht van de microsoft 365 Business Premium-installatie.</span><span class="sxs-lookup"><span data-stu-id="a2c62-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="a2c62-105">Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="a2c62-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="a2c62-106">Uw domein, gebruikers en beleidsregels toevoegen</span><span class="sxs-lookup"><span data-stu-id="a2c62-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="a2c62-107">Wanneer u Microsoft 365 Business Premium koopt, u een domein gebruiken dat u bezit of een domein kopen tijdens de [aanmelding.](sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="a2c62-107">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="a2c62-108">Als u een nieuw domein hebt gekocht toen u zich aanmeldde, is uw domein helemaal ingesteld en u naar [Gebruikers toevoegen en licenties toewijzen.](#add-users-and-assign-licenses)</span><span class="sxs-lookup"><span data-stu-id="a2c62-108">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="a2c62-109">Uw domein toevoegen om aanmelding te personaliseren</span><span class="sxs-lookup"><span data-stu-id="a2c62-109">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="a2c62-110">Meld u aan bij [microsoft 365-beheercentrum](https://admin.microsoft.com) met behulp van uw globale beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="a2c62-110">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="a2c62-111">Kies **Ga naar setup** om de wizard te starten.</span><span class="sxs-lookup"><span data-stu-id="a2c62-111">Choose **Go to setup** to start the wizard.</span></span>

    ![Selecteer Ga naar setup.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="a2c62-113">Op de pagina **Uw Office-apps installeren** u de apps optioneel op uw eigen computer installeren.</span><span class="sxs-lookup"><span data-stu-id="a2c62-113">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="a2c62-114">Voer in de stap **Domein toevoegen** de domeinnaam in die u wilt gebruiken (zoals contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a2c62-114">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a2c62-115">Als u een domein hebt gekocht tijdens de aanmelding, ziet u hier **geen domeinstap toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="a2c62-115">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="a2c62-116">Ga in plaats daarvan naar [Gebruikers toevoegen.](#add-users-and-assign-licenses)</span><span class="sxs-lookup"><span data-stu-id="a2c62-116">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Schermafbeelding van de aanmeldingspagina Personaliseren.](../media/adddomain.png)

    
4. <span data-ttu-id="a2c62-118">Volg de stappen in de wizard OM [DNS-records te maken bij een DNS-hostingprovider voor Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) die controleert of u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="a2c62-118">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="a2c62-119">Als u uw domeinhost kent, raadpleegt u ook de [specifieke instructies voor de host.](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)</span><span class="sxs-lookup"><span data-stu-id="a2c62-119">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="a2c62-120">Als uw hostingprovider GoDaddy is of een andere host ingeschakeld met [domeinverbinden,](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)is het proces eenvoudig en wordt u automatisch gevraagd om u aan te melden en Microsoft namens u te laten verifiëren.</span><span class="sxs-lookup"><span data-stu-id="a2c62-120">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Selecteer Toegang toestaan op de pagina GoDaddy-bevestiging.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="a2c62-122">Gebruikers toevoegen en licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="a2c62-122">Add users and assign licenses</span></span>

<span data-ttu-id="a2c62-123">U gebruikers toevoegen aan de wizard, maar u later ook [gebruikers toevoegen](add-users-m365b.md) in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="a2c62-123">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="a2c62-124">Als u een lokale domeincontroller hebt, u bovendien gebruikers toevoegen met [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="a2c62-124">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="a2c62-125">Gebruikers toevoegen aan de wizard</span><span class="sxs-lookup"><span data-stu-id="a2c62-125">Add users in the wizard</span></span>

<span data-ttu-id="a2c62-126">Alle gebruikers die u in de wizard toevoegt, krijgen automatisch een Microsoft 365 Business Premium-licentie toegewezen.</span><span class="sxs-lookup"><span data-stu-id="a2c62-126">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Schermafbeelding van de pagina Nieuwe gebruikers toevoegen in de wizard](../media/addnewuserspage.png)

1. <span data-ttu-id="a2c62-128">Als uw Microsoft 365 Business Premium-abonnement bestaande gebruikers heeft (bijvoorbeeld als u Azure AD Connect hebt gebruikt), krijgt u een optie om nu licenties aan hen toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="a2c62-128">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="a2c62-129">Wijs nu licenties aan hen toe.</span><span class="sxs-lookup"><span data-stu-id="a2c62-129">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="a2c62-130">Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie om referenties te delen met de nieuwe gebruikers die u hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="a2c62-130">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="a2c62-131">U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.</span><span class="sxs-lookup"><span data-stu-id="a2c62-131">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="a2c62-132">Uw domein verbinden</span><span class="sxs-lookup"><span data-stu-id="a2c62-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="a2c62-133">Als u ervoor kiest om het .onmicrosoft-domein te gebruiken of Azure AD Connect hebt gebruikt om gebruikers in te stellen, ziet u deze stap niet.</span><span class="sxs-lookup"><span data-stu-id="a2c62-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="a2c62-134">Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.</span><span class="sxs-lookup"><span data-stu-id="a2c62-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="a2c62-135">Meestal wordt uw registrar automatisch gedetecteerd met de installatiewizard en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar.</span><span class="sxs-lookup"><span data-stu-id="a2c62-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="a2c62-136">Als dit niet het geval is, [wijzigt u naamservers om Office 365 in te stellen met een domeinregistrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span><span class="sxs-lookup"><span data-stu-id="a2c62-136">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="a2c62-137">Als u bestaande DNS-records hebt, bijvoorbeeld een bestaande website, maar uw DNS-host is ingeschakeld voor [domeinbinding,](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)kiest u **Records voor mij toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="a2c62-137">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="a2c62-138">Accepteer **op** de pagina Kies uw online services alle standaardinstellingen en kies **Volgende**en kies **Autoriseren** op de pagina van uw DNS-host.</span><span class="sxs-lookup"><span data-stu-id="a2c62-138">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="a2c62-139">Als u bestaande DNS-records hebt met andere DNS-hosts (niet ingeschakeld voor domeinverbintending), wilt u uw eigen DNS-records beheren om ervoor te zorgen dat de bestaande services verbonden blijven.</span><span class="sxs-lookup"><span data-stu-id="a2c62-139">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="a2c62-140">Zie [basisprincipes van domeinen](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a2c62-140">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Records pagina activeren.](../media/activaterecords.png)

2. <span data-ttu-id="a2c62-142">Volg de stappen in de wizard en e-mail en andere services worden voor u ingesteld.</span><span class="sxs-lookup"><span data-stu-id="a2c62-142">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="a2c62-143">Uw organisatie beveiligen</span><span class="sxs-lookup"><span data-stu-id="a2c62-143">Protect your organization</span></span> 

<span data-ttu-id="a2c62-144">Het beleid dat u in de wizard hebt ingesteld, wordt automatisch toegepast op een [beveiligingsgroep](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) met de naam *Alle gebruikers*.</span><span class="sxs-lookup"><span data-stu-id="a2c62-144">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="a2c62-145">U ook extra groepen maken om beleid aan toe te wijzen in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="a2c62-145">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="a2c62-146">Op de **verhoogingsbeveiliging tegen geavanceerde cyberbedreigingen**wordt aanbevolen dat u de standaardinstellingen accepteert om [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) bestanden en koppelingen in Office-apps te laten scannen.</span><span class="sxs-lookup"><span data-stu-id="a2c62-146">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![Schermafbeelding van de pagina Beveiliging verhogen.](../media/increasetreatprotection.png)


2. <span data-ttu-id="a2c62-148">Accepteer op de pagina **Lekken van gevoelige gegevens voorkomen** de standaardinstellingen om Office 365 Data Loss Prevention (DLP) in te schakelen om gevoelige gegevens in Office-apps bij te houden en te voorkomen dat deze gegevens per ongeluk buiten uw organisatie worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="a2c62-148">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="a2c62-149">Laat **op** de pagina Gegevens beveiligen in Office voor mobiel het beheer van mobiele apps aan, vouw de instellingen uit en bekijk ze en selecteer **vervolgens Beleid voor beheer van mobiele apps**maken.</span><span class="sxs-lookup"><span data-stu-id="a2c62-149">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Schermafbeelding van Gegevens beveiligen in office voor mobiele pagina.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="a2c62-151">Beveilig Windows 10-pc's</span><span class="sxs-lookup"><span data-stu-id="a2c62-151">Secure Windows 10 PCs</span></span>

<span data-ttu-id="a2c62-152">Selecteer aan de linkerkant **Setup** en kies onder Aanmelden en beveiliging **de optie Uw Windows 10-computers beveiligen.** **Sign-in and security**</span><span class="sxs-lookup"><span data-stu-id="a2c62-152">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="a2c62-153">Kies **Weergave** om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="a2c62-153">Choose **View** to get started.</span></span> <span data-ttu-id="a2c62-154">Zie [Uw Windows 10-computers beveiligen](secure-win-10-pcs.md) voor volledige instructies.</span><span class="sxs-lookup"><span data-stu-id="a2c62-154">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="a2c62-155">Office 365-client-apps implementeren</span><span class="sxs-lookup"><span data-stu-id="a2c62-155">Deploy Office 365 client apps</span></span>

<span data-ttu-id="a2c62-156">Als u ervoor kiest om Office-apps automatisch te installeren tijdens de installatie, worden de apps geïnstalleerd op de Windows 10-apparaten zodra de gebruikers zich vanaf hun Windows-apparaten bij Azure AD hebben aangemeld met hun werkreferenties.</span><span class="sxs-lookup"><span data-stu-id="a2c62-156">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="a2c62-157">Zie Mobiele apparaten instellen voor Microsoft [365 Business Premium-gebruikers als](set-up-mobile-devices.md)u Office wilt installeren op mobiele iOS- of Android-apparaten.</span><span class="sxs-lookup"><span data-stu-id="a2c62-157">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="a2c62-158">U Office ook afzonderlijk installeren.</span><span class="sxs-lookup"><span data-stu-id="a2c62-158">You can also install Office individually.</span></span> <span data-ttu-id="a2c62-159">Zie [Office installeren op een pc of Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="a2c62-159">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2c62-160">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a2c62-160">See also</span></span>

[<span data-ttu-id="a2c62-161">Trainingsvideo's voor Microsoft 365 voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="a2c62-161">Microsoft 365 for business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
