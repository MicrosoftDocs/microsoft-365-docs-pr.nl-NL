---
title: Microsoft 365 Business instellen
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Meer informatie over het instellen van Microsoft 365 Business.
ms.openlocfilehash: 4f31af3fa63416d3b1bd7281f7712313252ad437
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2019
ms.locfileid: "37440587"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a><span data-ttu-id="b1859-103">Microsoft 365 Business instellen in de wizard Setup</span><span class="sxs-lookup"><span data-stu-id="b1859-103">Set up Microsoft 365 Business in the setup wizard</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="b1859-104">Uw domein, gebruikers en beleidsinstellingen toevoegen</span><span class="sxs-lookup"><span data-stu-id="b1859-104">Add your domain, users, and set up policies</span></span>

<span data-ttu-id="b1859-105">[![Label om u te laten weten dat het Admin Center is aan het veranderen en u meer informatie vinden op aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="b1859-105">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="b1859-106">Wanneer u Microsoft 365 Business aanschaft, hebt u de mogelijkheid om een domein te gebruiken waarvan u eigenaar bent, of om er een te kopen tijdens de [aanmelding](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="b1859-106">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="b1859-107">Als u een nieuw domein hebt aangeschaft toen u zich aanmeldde, is uw domein allemaal ingesteld en u verplaatsen naar [gebruikers toevoegen en licenties toewijzen](#add-users-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="b1859-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="b1859-108">Uw domein toevoegen om aanmelding te personaliseren</span><span class="sxs-lookup"><span data-stu-id="b1859-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="b1859-109">Meld u aan bij [Microsoft 365 Admin Center](https://admin.microsoft.com) met behulp van de referenties van uw globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="b1859-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="b1859-110">Kies **een domein toevoegen** of **gebruikers toevoegen** om de wizard te starten.</span><span class="sxs-lookup"><span data-stu-id="b1859-110">Choose **Add a domain** or **Add users** to start the wizard.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="b1859-111">Als u een domein heeft aangeschaft tijdens de aanmelding, ziet u hier geen **domein toevoegen** .</span><span class="sxs-lookup"><span data-stu-id="b1859-111">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="b1859-112">Ga in plaats daarvan naar [gebruikers toevoegen](#add-users-and-assign-licenses) .</span><span class="sxs-lookup"><span data-stu-id="b1859-112">Go to [Add users ](#add-users-and-assign-licenses) instead.</span></span>

    ![Selecteer Ga naar Setup.](media/gotosetupinadmincenter.png)
    
3. <span data-ttu-id="b1859-114">Voer in de wizard de domeinnaam in die u wilt gebruiken (zoals contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b1859-114">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Screenshot van de Personaliseer je inlogpagina.](media/personalizesignin.png)

    
4. <span data-ttu-id="b1859-116">Volg de stappen in de wizard om [DNS-records te maken bij elke DNS-hosting provider voor Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) die controleert of u de eigenaar van het domein bent.</span><span class="sxs-lookup"><span data-stu-id="b1859-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="b1859-117">Als u uw domeinhost kent, raadpleegt u ook de [hostspecifieke instructies](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="b1859-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="b1859-118">Als uw hosting provider GoDaddy is of een andere host die is ingeschakeld met [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), is het proces eenvoudig en wordt u automatisch gevraagd om in te loggen en Microsoft namens u te laten verifiëren:</span><span class="sxs-lookup"><span data-stu-id="b1859-118">If your hosting provider is GoDaddy, or another host enabled with [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![Selecteer op GoDaddy toegangspagina bevestigen de optie autoriseren.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="b1859-120">Gebruikers toevoegen en licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="b1859-120">Add users and assign licenses</span></span>

<span data-ttu-id="b1859-121">U gebruikers toevoegen in de wizard, maar u ook [gebruikers later toevoegen](add-users-m365b.md) in het Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="b1859-121">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="b1859-122">Als u een lokale domeincontroller hebt, u bovendien gebruikers met [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)toevoegen.</span><span class="sxs-lookup"><span data-stu-id="b1859-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="b1859-123">Gebruikers toevoegen in de wizard</span><span class="sxs-lookup"><span data-stu-id="b1859-123">Add users in the wizard</span></span>

<span data-ttu-id="b1859-124">Gebruikers die u toevoegt aan de wizard krijgen automatisch een licentie voor Microsoft 365 Business toegewezen.</span><span class="sxs-lookup"><span data-stu-id="b1859-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>

![Schermafbeelding van de pagina nieuwe gebruikers toevoegen in de wizard](media/addnewuserspage.png)

1. <span data-ttu-id="b1859-126">Als uw Microsoft 365 Business-abonnement bestaande gebruikers heeft (bijvoorbeeld, als u Azure AD Connect hebt gebruikt), krijgt u een optie om licenties toe te wijzen aan hen nu.</span><span class="sxs-lookup"><span data-stu-id="b1859-126">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you get an option to assign licenses to them now.</span></span> <span data-ttu-id="b1859-127">Wijs nu licenties aan hen toe.</span><span class="sxs-lookup"><span data-stu-id="b1859-127">Go ahead and add licenses to them as well.</span></span>

2. <span data-ttu-id="b1859-128">Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie om referenties te delen met de nieuwe gebruikers die u hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="b1859-128">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="b1859-129">U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.</span><span class="sxs-lookup"><span data-stu-id="b1859-129">You can choose to print them out, email them, or download them.</span></span>

3. <span data-ttu-id="b1859-130">Op de teams maken voor uw organisatie, u teams toevoegen en gebruikers toevoegen aan hen.</span><span class="sxs-lookup"><span data-stu-id="b1859-130">On the Create Teams for your organization, you can choose to add Teams and add users to them.</span></span> <span data-ttu-id="b1859-131">U dit ook later doen.</span><span class="sxs-lookup"><span data-stu-id="b1859-131">You can also do this later.</span></span> <span data-ttu-id="b1859-132">Zie [een bedrijfsbreed team maken](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b1859-132">For more information, see [create a company-wide Team](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).</span></span>

4. <span data-ttu-id="b1859-133">Sla het migreren van e-mailberichten over en kies **Volgende** op de pagina **E-mailberichten migreren**.</span><span class="sxs-lookup"><span data-stu-id="b1859-133">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="b1859-134">Als u van een andere e-mailprovider verhuist en uw gegevens later wilt kopiëren, u [e-mail en contactpersonen migreren naar Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="b1859-134">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>


### <a name="connect-your-domain"></a><span data-ttu-id="b1859-135">Uw domein verbinden</span><span class="sxs-lookup"><span data-stu-id="b1859-135">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="b1859-136">Als u ervoor kiest om het domein. onmicrosoft te gebruiken of Azure AD Connect gebruikt om gebruikers in te stellen, wordt deze stap niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b1859-136">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="b1859-137">Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.</span><span class="sxs-lookup"><span data-stu-id="b1859-137">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="b1859-138">Meestal wordt uw registrar automatisch gedetecteerd met de installatiewizard en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar.</span><span class="sxs-lookup"><span data-stu-id="b1859-138">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="b1859-139">Als dit niet het [geval is, wijzigt u nameservers om Office 365 in te stellen met een domeinregistrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="b1859-139">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="b1859-140">Als u bestaande DNS-records hebt, bijvoorbeeld een bestaande website, maar uw DNS-host is ingeschakeld voor [domein verbinding](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), kiest u **records toevoegen voor mij**.</span><span class="sxs-lookup"><span data-stu-id="b1859-140">If you have existing DNS records, for example an existing web site, but your DNS host is enabled for [domain connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), choose **Add records for me**.</span></span> <span data-ttu-id="b1859-141">Accepteer alle standaardinstellingen op de pagina **Kies uw online services** en kies **volgende**en kies **autoriseren** op de pagina van uw DNS-host.</span><span class="sxs-lookup"><span data-stu-id="b1859-141">On the **Choose your online services** page, accept all the defaults, and choose **Next**,and choose **Authorize** on your DNS host's page.</span></span>
    - <span data-ttu-id="b1859-142">Als u bestaande DNS-records hebt met andere DNS-hosts (niet ingeschakeld voor domein verbinding), wilt u uw eigen DNS-records beheren om ervoor te zorgen dat de bestaande services verbonden blijven.</span><span class="sxs-lookup"><span data-stu-id="b1859-142">If you have existing DNS records with other DNS hosts (not enabled for domain connect), you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="b1859-143">Zie [basisbeginselen](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) van het domein voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b1859-143">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Verbind uw domein pagina met ik beheer mijn eigen DNS-records.](media/connectyourdomainpage.png)

2. <span data-ttu-id="b1859-145">Volg de stappen in de wizard en e-mail en andere services worden voor u ingesteld.</span><span class="sxs-lookup"><span data-stu-id="b1859-145">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="protect-data-and-devices"></a><span data-ttu-id="b1859-146">Gegevens en apparaten beveiligen</span><span class="sxs-lookup"><span data-stu-id="b1859-146">Protect data and devices</span></span> 

<span data-ttu-id="b1859-147">Het beleid dat u in de wizard hebt ingesteld, wordt automatisch toegepast op een [beveiligingsgroep](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) met de naam *alle gebruikers*.</span><span class="sxs-lookup"><span data-stu-id="b1859-147">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="b1859-148">U ook extra groepen maken om beleidsregels toe te wijzen in het Admin Center.</span><span class="sxs-lookup"><span data-stu-id="b1859-148">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="b1859-149">Op de **Bescherm uw werkbestanden op mobiele apparaten** de optie **werkbestanden beveiligen wanneer apparaten zijn verloren of gestolen** is standaard geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="b1859-149">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="b1859-150">U hebt een optie om in te schakelen **beheren hoe gebruikers toegang hebben tot Office-bestanden op mobiele apparaten**, en dit wordt aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="b1859-150">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Screenshot van werkbestanden beschermen op de pagina mobiele apparaten.](media/protectworkfilesondevices.png)

     - <span data-ttu-id="b1859-152">Vouw **werkbestanden beveiligen wanneer apparaten zijn verloren of gestolen** om de [Standaardwaarden](protect-work-files-on-lost-or-stolen-device.md)weer te geven:</span><span class="sxs-lookup"><span data-stu-id="b1859-152">Expand **Protect work files when devices are lost or stolen** to display the [default values](protect-work-files-on-lost-or-stolen-device.md):</span></span>

        ![Screenshot van standaardwaarden voor het beschermen van bestanden op verloren apparaten.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="b1859-154">Selecteer **beheren hoe gebruikers toegang hebben tot Office-bestanden op mobiele apparaten** en vouw deze uit om de [Standaardwaarden](manage-user-access-on-mobile-devices.md)weer te geven.</span><span class="sxs-lookup"><span data-stu-id="b1859-154">Select **Manage how users access Office files on mobile devices** and expand it to display the [default values](manage-user-access-on-mobile-devices.md).</span></span> <span data-ttu-id="b1859-155">We raden u aan de standaardwaarden tijdens de installatie te accepteren om toepassings beleidsregels te maken voor Android, iOS en Windows 10 die van toepassing zijn op alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b1859-155">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="b1859-156">Nadat de installatie is voltooid, kunt u meer beleidsregels maken.</span><span class="sxs-lookup"><span data-stu-id="b1859-156">You can create more policies after setup completes.</span></span>

        ![Screenshot van beveiligingsinstellingen voor Office-bestanden op mobiel.](media/useraccessonmobile.png)

2. <span data-ttu-id="b1859-158">De laatste stap op gegevens en apparaten beveiligen, u beleid instellen voor het beveiligen van Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="b1859-158">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="b1859-159">Deze instellingen worden automatisch toegepast wanneer Windows 10 van een gebruiker verbinding met uw organisatie maakt.</span><span class="sxs-lookup"><span data-stu-id="b1859-159">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="b1859-160">U **beveiligde Windows 10-apparaten** uitvouwen om de [Standaardwaarden](secure-windows-10-devices.md)te bekijken en te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="b1859-160">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="b1859-161">U er ook voor kiezen om [Office automatisch te installeren](install-office-on-windows-10-during-setup.md) op Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="b1859-161">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Screenshot van set Windows 10 Device configuration pagina.](media/setwin10config.png)


## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="b1859-163">Office 365-client-Apps implementeren</span><span class="sxs-lookup"><span data-stu-id="b1859-163">Deploy Office 365 client apps</span></span>

<span data-ttu-id="b1859-164">Als u ervoor kiest om automatisch Office-apps te installeren tijdens de installatie, worden de apps geïnstalleerd op de Windows 10-apparaten zodra de gebruikers zich hebben aangemeld bij Azure AD vanaf hun Windows-apparaten met hun werkreferenties.</span><span class="sxs-lookup"><span data-stu-id="b1859-164">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="b1859-165">Als u Office op mobiele iOS-of Android-apparaten wilt installeren, raadpleegt u [mobiele apparaten instellen voor zakelijke gebruikers van Microsoft 365](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="b1859-165">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="b1859-166">U Office ook afzonderlijk installeren.</span><span class="sxs-lookup"><span data-stu-id="b1859-166">You can also install Office individually.</span></span> <span data-ttu-id="b1859-167">Zie [Office installeren op een PC of Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="b1859-167">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>
