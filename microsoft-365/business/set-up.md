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
description: Ontdek de instellingsstappen voor Microsoft 365 Business Premium, waaronder het toevoegen van een domein en gebruikers, het instellen van beveiligingsbeleid en meer.
ms.openlocfilehash: cc20637d7a78bd34ecb61a4ed46eb06d564d63df
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324491"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="2948a-103">Microsoft 365 Business Premium instellen in de wizard Setup</span><span class="sxs-lookup"><span data-stu-id="2948a-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="2948a-104">Bekijk deze video voor een overzicht van de configuratie van Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="2948a-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="2948a-105">Uw domein, gebruikers en ingestelde beleidsregels toevoegen</span><span class="sxs-lookup"><span data-stu-id="2948a-105">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="2948a-106">Wanneer u Microsoft 365 Business Premium koopt, hebt u de mogelijkheid een domein te gebruiken dat u bezit, of u kunt een domein kopen tijdens de [registratie](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="2948a-106">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="2948a-107">Als u tijdens de registratie een nieuw domein hebt gekocht, is uw domein helemaal ingesteld en kunt u doorgaan met [Gebruikers toevoegen en licenties toewijzen](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="2948a-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="2948a-108">Uw domein toevoegen om uw aanmelding te personaliseren</span><span class="sxs-lookup"><span data-stu-id="2948a-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="2948a-109">Meld u aan bij [Microsoft 365-beheercentrum](https://admin.microsoft.com) met uw globale-beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="2948a-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="2948a-110">Kies **Naar setup** om de wizard te starten.</span><span class="sxs-lookup"><span data-stu-id="2948a-110">Choose **Go to setup** to start the wizard.</span></span>

    ![Selecteer Ga naar Setup.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="2948a-112">Op de pagina **Uw Office-apps installeren** kunt u desgewenst de apps op uw eigen computer installeren.</span><span class="sxs-lookup"><span data-stu-id="2948a-112">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="2948a-113">Voer in de stap **Domein toevoegen** de domeinnaam in die u wilt gebruiken (zoals contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2948a-113">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2948a-114">Als u tijdens de registratie een domein hebt gekocht, ziet u de stap **Een domein toevoegen** hier niet.</span><span class="sxs-lookup"><span data-stu-id="2948a-114">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="2948a-115">Ga in plaats daarvan naar [Gebruikers toevoegen](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="2948a-115">Go to [Add users](#add-users-and-assign-licenses) instead.</span></span>

    ![Schermafbeelding van de aanmeldingspagina personaliseren.](../media/adddomain.png)

    
4. <span data-ttu-id="2948a-117">Volg de stappen in de wizard voor het [maken van DNS-records bij een DNS-hosting provider voor Microsoft 365 waarmee wordt](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) geverifieerd dat u de eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="2948a-117">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="2948a-118">Als u weet wat uw domeinhost is, raadpleegt u ook de [hostspecifieke instructies](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="2948a-118">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="2948a-119">Als uw hostingprovider GoDaddy of een andere host is die is ingeschakeld met [domeinverbinding](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), is het proces eenvoudig en wordt u automatisch gevraagd om u aan te melden en u namens Microsoft te laten verifiëren.</span><span class="sxs-lookup"><span data-stu-id="2948a-119">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Selecteer Autoriseren op de pagina GoDaddy Toegang bevestigen.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="2948a-121">Gebruikers toevoegen en licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="2948a-121">Add users and assign licenses</span></span>

<span data-ttu-id="2948a-122">U kunt gebruikers toevoegen in de wizard, maar u kunt ook [gebruikers later toevoegen](add-users-m365b.md) in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="2948a-122">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="2948a-123">Als u een lokale domeincontroller hebt, kunt u ook gebruikers toevoegen met [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="2948a-123">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="2948a-124">Gebruikers toevoegen in de wizard</span><span class="sxs-lookup"><span data-stu-id="2948a-124">Add users in the wizard</span></span>

<span data-ttu-id="2948a-125">Gebruikers die u in de wizard toevoegt, krijgen automatisch een licentie voor Microsoft 365 Business Premium toegewezen.</span><span class="sxs-lookup"><span data-stu-id="2948a-125">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Schermafbeelding van de pagina nieuwe gebruikers toevoegen in de wizard](../media/addnewuserspage.png)

1. <span data-ttu-id="2948a-127">Als uw Microsoft 365 Business Premium-abonnement bestaande gebruikers heeft (bijvoorbeeld als u Azure AD Connect gebruikt), krijgt u de mogelijkheid om nu licenties toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="2948a-127">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="2948a-128">Wijs nu licenties aan hen toe.</span><span class="sxs-lookup"><span data-stu-id="2948a-128">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="2948a-129">Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie voor het delen van referenties met de nieuwe gebruikers die u hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="2948a-129">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="2948a-130">U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.</span><span class="sxs-lookup"><span data-stu-id="2948a-130">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="2948a-131">Uw domein verbinden</span><span class="sxs-lookup"><span data-stu-id="2948a-131">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="2948a-132">Als u ervoor hebt gekozen om het domein. onmicrosoft te gebruiken of Azure AD Connect hebt gebruikt voor het instellen van gebruikers, wordt deze stap niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2948a-132">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="2948a-133">Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.</span><span class="sxs-lookup"><span data-stu-id="2948a-133">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="2948a-134">Meestal wordt uw registrar automatisch gedetecteerd met de wizard Setup, en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar.</span><span class="sxs-lookup"><span data-stu-id="2948a-134">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="2948a-135">Als dit niet het geval is, [kunt u het naamservers wijzigen voor het instellen van Microsoft 365 met een domeinregistratie](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span><span class="sxs-lookup"><span data-stu-id="2948a-135">If it doesn't, [Change nameservers to set up Microsoft 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar).</span></span> 

    - <span data-ttu-id="2948a-136">Als u bestaande DNS-records hebt, bijvoorbeeld een bestaande website, maar uw DNS-host is ingeschakeld voor [domeinverbinding](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), kiest u **Records toevoegen voor mij**.</span><span class="sxs-lookup"><span data-stu-id="2948a-136">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="2948a-137">Accepteer alle standaardinstellingen op de pagina **Uw online services kiezen**, kies **Volgende** en kies **Autoriseren** op de pagina van uw DNS-host.</span><span class="sxs-lookup"><span data-stu-id="2948a-137">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="2948a-138">Als u bestaande DNS-records hebt met andere DNS-hosts (niet ingeschakeld voor domeinverbinding), kunt u uw eigen DNS-records beheren om ervoor te zorgen dat de bestaande services verbonden blijven.</span><span class="sxs-lookup"><span data-stu-id="2948a-138">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="2948a-139">Zie [basisprincipes van domeinen](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2948a-139">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![De pagina records activeren.](../media/activaterecords.png)

2. <span data-ttu-id="2948a-141">Volg de stappen in de wizard en e-mail en andere services worden voor u ingesteld.</span><span class="sxs-lookup"><span data-stu-id="2948a-141">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="2948a-142">Uw organisatie beschermen</span><span class="sxs-lookup"><span data-stu-id="2948a-142">Protect your organization</span></span> 

<span data-ttu-id="2948a-143">Het beleid dat u instelt in de wizard wordt automatisch toegepast op een [beveiligingsgroep](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) met de naam *alle gebruikers*.</span><span class="sxs-lookup"><span data-stu-id="2948a-143">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="2948a-144">U kunt ook extra groepen maken waarmee u beleidsregels kunt toewijzen in het Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="2948a-144">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="2948a-145">Wanneer u de **bescherming van geavanceerde Cyber bedreigingen**vergemakkelijkt, wordt u aangeraden de standaardinstellingen te accepteren om [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) te laten scannen op bestanden en koppelingen in Office-apps.</span><span class="sxs-lookup"><span data-stu-id="2948a-145">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![Schermafbeelding van de pagina voor het verbeteren van de bescherming.](../media/increasetreatprotection.png)


2. <span data-ttu-id="2948a-147">Accepteer op de pagina **lekkage van gevoelige gegevens voorkomen** de standaardinstellingen voor het inschakelen van Office 365 preventie van gegevensverlies (DLP) om gevoelige gegevens in Office-apps bij te houden en te voorkomen dat deze buiten uw organisatie worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="2948a-147">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="2948a-148">Op de pagina **gegevens in Office beschermen voor mobiel apparaat** wilt u de mobiele app beheren, vouwt u de instellingen uit en bekijkt u ze en selecteert u vervolgens **beleid voor Mobile App Management maken**.</span><span class="sxs-lookup"><span data-stu-id="2948a-148">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Schermafbeelding van de pagina gegevens beschermen in Office voor mobiel.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="2948a-150">Windows 10-Pc's beveiligen</span><span class="sxs-lookup"><span data-stu-id="2948a-150">Secure Windows 10 PCs</span></span>

<span data-ttu-id="2948a-151">Selecteer in het navigatievenster aan de linkerkant de optie **installeren** en kies vervolgens onder **Aanmelden en beveiliging** **de optie Beveilig uw Windows 10-computers**.</span><span class="sxs-lookup"><span data-stu-id="2948a-151">On the left nav, select **Setup** and then, under **Sign-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="2948a-152">Kies **weergave** om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="2948a-152">Choose **View** to get started.</span></span> <span data-ttu-id="2948a-153">Zie [Beveilig uw Windows 10-computers](secure-win-10-pcs.md) voor uitgebreide instructies.</span><span class="sxs-lookup"><span data-stu-id="2948a-153">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="2948a-154">Office 365-clienttoepassingen implementeren</span><span class="sxs-lookup"><span data-stu-id="2948a-154">Deploy Office 365 client apps</span></span>

<span data-ttu-id="2948a-155">Als u ervoor kiest om Office-apps automatisch te installeren tijdens de installatie, worden de apps op Windows 10-apparaten geïnstalleerd nadat de gebruikers zich hebben aangemeld bij Azure AD vanaf hun Windows-apparaten, met hun werk referenties.</span><span class="sxs-lookup"><span data-stu-id="2948a-155">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="2948a-156">Als u Office wilt installeren op mobiele iOS-en Android-apparaten, raadpleegt u [mobiele apparaten instellen voor gebruikers van Microsoft 365 Business Premium](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="2948a-156">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="2948a-157">U kunt Office ook afzonderlijk installeren.</span><span class="sxs-lookup"><span data-stu-id="2948a-157">You can also install Office individually.</span></span> <span data-ttu-id="2948a-158">Zie [Office installeren op een PC of Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="2948a-158">See [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="2948a-159">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2948a-159">See also</span></span>

[<span data-ttu-id="2948a-160">Trainingsvideo's voor Microsoft 365 voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="2948a-160">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
