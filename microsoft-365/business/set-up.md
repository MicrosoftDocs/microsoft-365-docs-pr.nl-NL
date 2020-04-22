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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Ontdek de installatiestappen voor Microsoft 365 Business Premium, waaronder het toevoegen van een domein en gebruikers, het instellen van beveiligingsbeleid en meer.
ms.openlocfilehash: a34ede0002e7e78c5dc437c663fe527cf94e46c5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635758"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a><span data-ttu-id="0e5d7-103">Microsoft 365 Business Premium instellen in de wizard Setup</span><span class="sxs-lookup"><span data-stu-id="0e5d7-103">Set up Microsoft 365 Business Premium in the setup wizard</span></span>

<span data-ttu-id="0e5d7-104">Bekijk deze video voor een overzicht van microsoft 365 Business Premium setup.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-104">Watch this video for an overview of Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

<span data-ttu-id="0e5d7-105">Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="0e5d7-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="0e5d7-106">Uw domein, gebruikers en beleid instellen toevoegen</span><span class="sxs-lookup"><span data-stu-id="0e5d7-106">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="0e5d7-107">[![Etiket om u te laten weten dat het beheercentrum wordt gewijzigd en meer informatie vindt u op aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="0e5d7-107">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="0e5d7-108">Wanneer u Microsoft 365 Business Premium koopt, hebt u de mogelijkheid om een domein te gebruiken dat u bezit of er een te kopen tijdens de [aanmelding.](sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="0e5d7-108">When you purchase Microsoft 365 Business Premium, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="0e5d7-109">Als u een nieuw domein hebt gekocht toen u zich hebt aangemeld, is uw domein helemaal ingesteld en u overgaan naar [Gebruikers toevoegen en licenties toewijzen.](#add-users-and-assign-licenses)</span><span class="sxs-lookup"><span data-stu-id="0e5d7-109">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="0e5d7-110">Uw domein toevoegen om aanmelding te personaliseren</span><span class="sxs-lookup"><span data-stu-id="0e5d7-110">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="0e5d7-111">Meld u aan bij [het Microsoft 365-beheercentrum](https://admin.microsoft.com) met uw globale beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-111">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="0e5d7-112">Kies **Ga naar setup om** de wizard te starten.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-112">Choose **Go to setup** to start the wizard.</span></span>

    ![Selecteer Ga naar instellen.](../media/gotosetupinadmincenter.png)

3. <span data-ttu-id="0e5d7-114">Op de pagina **Uw Office-apps installeren** u de apps optioneel op uw eigen computer installeren.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-114">On the **Install your Office apps** page, you can optionally install the apps on your own computer.</span></span>
    
4. <span data-ttu-id="0e5d7-115">Voer in de stap **Domein toevoegen** de domeinnaam in die u wilt gebruiken (zoals contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0e5d7-115">In the **Add domain** step, enter the domain name you want to use (like contoso.com).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0e5d7-116">Als u tijdens de aanmelding een domein hebt gekocht, ziet u hier **geen domeinstap toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="0e5d7-116">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="0e5d7-117">Ga in plaats daarvan naar [Gebruikers toevoegen.](#add-users-and-assign-licenses)</span><span class="sxs-lookup"><span data-stu-id="0e5d7-117">Go to [Add users ](#add-users-and-assign-licenses) instead.</span></span>

    ![Schermafbeelding van de pagina Uw aanmelding personaliseren.](../media/adddomain.png)

    
4. <span data-ttu-id="0e5d7-119">Volg de stappen in de wizard om [DNS-records te maken bij elke DNS-hostingprovider voor Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) die controleert of u eigenaar bent van het domein.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="0e5d7-120">Als u uw domeinhost kent, raadpleegt u ook de [hostspecifieke instructies.](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)</span><span class="sxs-lookup"><span data-stu-id="0e5d7-120">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="0e5d7-121">Als uw hostingprovider GoDaddy is of een andere host die is ingeschakeld met [domeinverbinding,](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)is het proces eenvoudig en wordt u automatisch gevraagd om u aan te melden en microsoft namens u te laten verifiëren.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-121">If your hosting provider is GoDaddy or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you'll be automatically asked to sign in and let Microsoft authenticate on your behalf.</span></span>

    ![Selecteer op de pagina Access bevestigen van GoDaddy Bevestigen de optie Autoriseren.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="0e5d7-123">Gebruikers toevoegen en licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="0e5d7-123">Add users and assign licenses</span></span>

<span data-ttu-id="0e5d7-124">U gebruikers toevoegen in de wizard, maar u later ook [gebruikers toevoegen](add-users-m365b.md) in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-124">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="0e5d7-125">Als u een lokale domeincontroller hebt, u bovendien gebruikers toevoegen met [Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)</span><span class="sxs-lookup"><span data-stu-id="0e5d7-125">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="0e5d7-126">Gebruikers toevoegen aan de wizard</span><span class="sxs-lookup"><span data-stu-id="0e5d7-126">Add users in the wizard</span></span>

<span data-ttu-id="0e5d7-127">Gebruikers die u in de wizard toevoegt, krijgen automatisch een Microsoft 365 Business Premium-licentie toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-127">Any users you add in the wizard get automatically assigned a Microsoft 365 Business Premium license.</span></span>

![Schermafbeelding van de pagina Nieuwe gebruikers toevoegen in de wizard](../media/addnewuserspage.png)

1. <span data-ttu-id="0e5d7-129">Als uw Microsoft 365 Business Premium-abonnement bestaande gebruikers heeft (bijvoorbeeld als u Azure AD Connect hebt gebruikt), krijgt u nu de optie om licenties aan hen toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-129">If your Microsoft 365 Business Premium subscription has existing users (for example, if you used Azure AD Connect), you get an option to assign licenses to them now.</span></span> <span data-ttu-id="0e5d7-130">Wijs nu licenties aan hen toe.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-130">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="0e5d7-131">Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie om referenties te delen met de nieuwe gebruikers die u hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-131">After you've added the users, you'll also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="0e5d7-132">U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-132">You can choose to print them out, email them, or download them.</span></span>

### <a name="connect-your-domain"></a><span data-ttu-id="0e5d7-133">Uw domein verbinden</span><span class="sxs-lookup"><span data-stu-id="0e5d7-133">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="0e5d7-134">Als u ervoor kiest om het .onmicrosoft-domein te gebruiken of Azure AD Connect hebt gebruikt om gebruikers in te stellen, ziet u deze stap niet.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="0e5d7-135">Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="0e5d7-136">Meestal wordt uw registrar automatisch gedetecteerd met de installatiewizard en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-136">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="0e5d7-137">Als dit niet het geval is, [wijzigt u naamservers om Office 365 in te stellen bij een domeinregistrar.](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)</span><span class="sxs-lookup"><span data-stu-id="0e5d7-137">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="0e5d7-138">Als u bestaande DNS-records hebt, bijvoorbeeld een bestaande website, maar uw DNS-host is ingeschakeld voor [domeinverbinding,](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)kiest u **Records voor mij toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-138">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="0e5d7-139">Accepteer op de pagina **Uw onlineservices kiezen** alle standaardinstellingen en kies **Volgende**en kies **Autoriseren** op de pagina van uw DNS-host.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-139">On the **Choose your online services** page, accept all the defaults, and choose **Next**, and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="0e5d7-140">Als u bestaande DNS-records hebt met andere DNS-hosts (niet ingeschakeld voor domeinverbinding), wilt u uw eigen DNS-records beheren om ervoor te zorgen dat de bestaande services verbonden blijven.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-140">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you'll want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="0e5d7-141">Zie [de basisprincipes van het domein](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-141">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Records-pagina activeren.](../media/activaterecords.png)

2. <span data-ttu-id="0e5d7-143">Volg de stappen in de wizard en e-mail en andere services worden voor u ingesteld.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-143">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-your-organization"></a><span data-ttu-id="0e5d7-144">Uw organisatie beschermen</span><span class="sxs-lookup"><span data-stu-id="0e5d7-144">Protect your organization</span></span> 

<span data-ttu-id="0e5d7-145">Het beleid dat u in de wizard hebt ingesteld, wordt automatisch toegepast op een [beveiligingsgroep](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) met de naam *Alle gebruikers*.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-145">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="0e5d7-146">U ook extra groepen maken om beleid toe te wijzen in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-146">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="0e5d7-147">In de **optiebeveiliging verhogen tegen geavanceerde cyberbedreigingen**wordt aanbevolen dat u de standaardinstellingen accepteert om [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) bestanden en koppelingen in Office-apps te laten scannen.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-147">On the **Increase protection from advanced cyber threats**, it is recommended that you accept the defaults to let [Office 365 Advance Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) scan files and links in Office apps.</span></span>

    ![Schermafbeelding van de pagina Bescherming vergroten.](../media/increasetreatprotection.png)


2. <span data-ttu-id="0e5d7-149">Accepteer op de pagina **Lekken van gevoelige gegevens** voorkomen de standaardinstellingen om Office 365 Data Loss Prevention (DLP) in te schakelen om gevoelige gegevens in Office-apps te volgen en het per ongeluk delen van deze gegevens buiten uw organisatie te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-149">On the **Prevent leaks of sensitive data** page, accept the defaults to turn on Office 365 Data Loss Prevention (DLP) to track sensitive data in Office apps and prevent the accidental sharing of these outside your organization.</span></span>

3. <span data-ttu-id="0e5d7-150">Laat op de pagina **Gegevens beveiligen in Office voor mobiel** het beheer van mobiele apps aan, vouw de instellingen uit en bekijk deze en selecteer vervolgens Beleid voor beheer van mobiele apps **maken**.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-150">On the **Protect data in Office for mobile** page, leave mobile app management on, expand the settings and review them, and then select **Create mobile app management policy**.</span></span>

    ![Schermafbeelding van Gegevens beveiligen in de pagina Office voor mobiel.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a><span data-ttu-id="0e5d7-152">Beveiligde Windows 10-pc's</span><span class="sxs-lookup"><span data-stu-id="0e5d7-152">Secure Windows 10 PCs</span></span>

<span data-ttu-id="0e5d7-153">Selecteer op de linkernavigatie de optie **Setup** en kies vervolgens onder Inzingen en beveiliging de optie **Uw Windows 10-computers beveiligen**. **Sing-in and security**</span><span class="sxs-lookup"><span data-stu-id="0e5d7-153">On the left nav, select **Setup** and then, under **Sing-in and security**, choose **Secure your Windows 10 computers**.</span></span> <span data-ttu-id="0e5d7-154">Kies **Weergave** om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-154">Choose **View** to get started.</span></span> <span data-ttu-id="0e5d7-155">Bekijk [uw Windows 10-computers beveiligen](secure-win-10-pcs.md) voor volledige instructies.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-155">See [secure your Windows 10 computers](secure-win-10-pcs.md) for complete instructions.</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="0e5d7-156">Office 365-client-apps implementeren</span><span class="sxs-lookup"><span data-stu-id="0e5d7-156">Deploy Office 365 client apps</span></span>

<span data-ttu-id="0e5d7-157">Als u ervoor kiest om Office-apps automatisch te installeren tijdens de installatie, worden de apps geïnstalleerd op de Windows 10-apparaten zodra de gebruikers zich vanaf hun Windows-apparaten hebben aangemeld bij Azure AD met behulp van hun werkreferenties.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-157">If you chose to automatically install Office apps during setup, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices, using their work credentials.</span></span>

<span data-ttu-id="0e5d7-158">Zie Mobiele apparaten instellen voor Microsoft [365 Business Premium-gebruikers](set-up-mobile-devices.md)als u Office wilt installeren op mobiele iOS- of Android-apparaten.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-158">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="0e5d7-159">U Office ook afzonderlijk installeren.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-159">You can also install Office individually.</span></span> <span data-ttu-id="0e5d7-160">Zie [Office installeren op een pc of Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="0e5d7-160">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e5d7-161">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0e5d7-161">See also</span></span>

[<span data-ttu-id="0e5d7-162">Microsoft 365 voor zakelijke trainingsvideo's</span><span class="sxs-lookup"><span data-stu-id="0e5d7-162">Microsoft 365 for business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
