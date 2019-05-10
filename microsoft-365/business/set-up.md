---
title: Microsoft 365 Business instellen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Informatie over het instellen van Microsoft 365 Business.
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660754"
---
# <a name="set-up-microsoft-365-business"></a><span data-ttu-id="4a006-103">Microsoft 365 Business instellen</span><span class="sxs-lookup"><span data-stu-id="4a006-103">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="4a006-104">Voordat u begint, Zie [Microsoft 365 Business ophalen](get-microsoft-365-business.md) voor aanmelding details.</span><span class="sxs-lookup"><span data-stu-id="4a006-104">Before you get started, see [Get Microsoft 365 Business](get-microsoft-365-business.md) for sign-up details.</span></span>

<span data-ttu-id="4a006-105">Bekijk een [korte video over het instellen van Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) met behulp van de wizard, en wanneer er een Active Directory op de gebouwen</span><span class="sxs-lookup"><span data-stu-id="4a006-105">Watch a [short video on how to set up Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) by using the set up wizard, and when you don't have an on-premises Active Directory</span></span>
  

## <a name="overview"></a><span data-ttu-id="4a006-106">Overzicht</span><span class="sxs-lookup"><span data-stu-id="4a006-106">Overview</span></span>

<span data-ttu-id="4a006-107">De meeste van de instellen van de stappen in de wizard setup kan worden uitgevoerd, maar de andere opties worden ook weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4a006-107">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>

1. <span data-ttu-id="4a006-108">[Uw domein toevoegen](#add-your-domain-to-personalize-sign-in) (als u uw domein tijdens het [aanmelden](sign-up.md)hebt gekocht, wordt deze stap hebt gedaan.)</span><span class="sxs-lookup"><span data-stu-id="4a006-108">[Add your domain](#add-your-domain-to-personalize-sign-in) (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>
2. <span data-ttu-id="4a006-109">Gebruikers toevoegen.</span><span class="sxs-lookup"><span data-stu-id="4a006-109">Add users.</span></span> <span data-ttu-id="4a006-110">U kunt dit op een van de drie manieren doen:</span><span class="sxs-lookup"><span data-stu-id="4a006-110">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="4a006-111">In de [wizard setup](#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="4a006-111">In the [setup wizard](#add-users-in-the-wizard).</span></span>
    - <span data-ttu-id="4a006-112">Adreslijstsynchronisatie toevoegen van [gebruikers met Azure AD verbinding](#add-users-by-using-azure-ad-connect) gebruiken als u een Active directory op gebouwen.</span><span class="sxs-lookup"><span data-stu-id="4a006-112">Use directory synchronization to [add users by using Azure AD Connect](#add-users-by-using-azure-ad-connect) if you have an on-premises Active directory.</span></span>
    - <span data-ttu-id="4a006-113">U kunt ook [gebruikers later toevoegen](add-users-m365b.md) in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="4a006-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
3. <span data-ttu-id="4a006-114">Beveiligingsbeleid instellen en configureren van apparaten.</span><span class="sxs-lookup"><span data-stu-id="4a006-114">Set up security policies and configure devices.</span></span> <span data-ttu-id="4a006-115">U kunt dit op een van de drie manieren doen:</span><span class="sxs-lookup"><span data-stu-id="4a006-115">You can do this in any of the three ways:</span></span>
    - <span data-ttu-id="4a006-116">In de [wizard setup](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="4a006-116">In the [setup wizard](#set-up-policies-in-the-wizard).</span></span>  
    - <span data-ttu-id="4a006-117">In de [admin center](#modify-or-add-policies-in-the-admin-center).</span><span class="sxs-lookup"><span data-stu-id="4a006-117">In the [admin center](#modify-or-add-policies-in-the-admin-center).</span></span>
    - <span data-ttu-id="4a006-118">Klik in het [beheercentrum Intune](https://docs.microsoft.com/intune/what-is-device-management).</span><span class="sxs-lookup"><span data-stu-id="4a006-118">In the [Intune admin center](https://docs.microsoft.com/intune/what-is-device-management).</span></span>
4. <span data-ttu-id="4a006-119">Instellen en beheren van apparaten in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="4a006-119">Set up and manage Windows 10 devices.</span></span>

    <span data-ttu-id="4a006-120">Wanneer u een apparaat met WIndows 10 naar Azure AD, krijgen alle beleidsregels toegepast op.</span><span class="sxs-lookup"><span data-stu-id="4a006-120">When you join a WIndows 10 device to Azure AD, all the policies get applied to it.</span></span>
    - <span data-ttu-id="4a006-121">Configuraties in de [wizard setup van](#set-up-policies-in-the-wizard)Windows 10 instellen.</span><span class="sxs-lookup"><span data-stu-id="4a006-121">Set up Windows 10 device configurations in the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="4a006-122">Lid worden van een [nieuw apparaat met Windows 10](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) naar Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4a006-122">Join a [new Windows 10 device](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) to Azure AD.</span></span>
    - <span data-ttu-id="4a006-123">Lid worden van een [bestaande Windows 10-apparaat](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) naar Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4a006-123">Join an [existing Windows 10 device](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) to Azure AD.</span></span>
1. <span data-ttu-id="4a006-124">Installeer Office 365 Business.</span><span class="sxs-lookup"><span data-stu-id="4a006-124">Install Office 365 Business.</span></span>
    - <span data-ttu-id="4a006-125">Automatisch kunt in de Windows-apparaten u Office installeren met de [wizard setup](#set-up-policies-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="4a006-125">You can automatically install Office in the Windows devices by using the [setup wizard](#set-up-policies-in-the-wizard).</span></span>
    - <span data-ttu-id="4a006-126">Automatisch [Office installeren](auto-install-or-uninstall-office.md) vanaf het admin center.</span><span class="sxs-lookup"><span data-stu-id="4a006-126">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
    - <span data-ttu-id="4a006-127">Laat de gebruikers [installeren Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) voor Windows en apparaten.</span><span class="sxs-lookup"><span data-stu-id="4a006-127">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
1. <span data-ttu-id="4a006-128">Extra beveiliging instellen.</span><span class="sxs-lookup"><span data-stu-id="4a006-128">Set up additional security.</span></span>
    - <span data-ttu-id="4a006-129">De wizard setup voegt beleid om uw apparaten te beveiligen, maar kunt u ook profiteren van de mogelijkheden voor [Extra beveiliging](#additional-security-settings) kunt veilig uw gegevens, accounts en e-mailberichten.</span><span class="sxs-lookup"><span data-stu-id="4a006-129">The setup wizard adds policies to secure your devices, but you can also take advantage of [additional security](#additional-security-settings) capabilities to helps secure your data, accounts, and emails.</span></span> 

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="4a006-130">Uw domein, gebruikers toevoegen en instellen van het beleid</span><span class="sxs-lookup"><span data-stu-id="4a006-130">Add your domain, users and set up policies</span></span>

![Banner die verwijzen naar https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

<span data-ttu-id="4a006-132">Wanneer u Microsoft 365 Business aanschaft, hebt u de mogelijkheid van een domein dat u de eigenaar of kopen tijdens de [aanmelding](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="4a006-132">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="4a006-133">Als u een nieuw domein gekocht toen u zich aanmeldde, uw domein is ingesteld op alle en u kunt [gebruikers toevoegen en toewijzen van licenties](#add-users-and-assign-licenses)kunt verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="4a006-133">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="4a006-134">Toevoegen van uw domein om aan te passen-in</span><span class="sxs-lookup"><span data-stu-id="4a006-134">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="4a006-135">Aanmelden bij [Microsoft 365 admin center](https://admin.microsoft.com) via uw globale Administrator-referenties.</span><span class="sxs-lookup"><span data-stu-id="4a006-135">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="4a006-136">Kies **een domein toevoegen** om de wizard te starten.</span><span class="sxs-lookup"><span data-stu-id="4a006-136">Choose **Add a domain** to start the wizard.</span></span>

    ![Selecteer een domein toevoegen.](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="4a006-138">Voer in de wizard de naam van het domein dat u wilt gebruiken (zoals contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4a006-138">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Screenshot van het aanpassen van uw pagina.](media/personalizesignin.png)

    
4. <span data-ttu-id="4a006-140">Volg de stappen in de wizard [maken DNS-records bij een DNS-hosting provider voor Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) waarmee wordt gecontroleerd of dat u de eigenaar van het domein.</span><span class="sxs-lookup"><span data-stu-id="4a006-140">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="4a006-141">Als u uw domeinhost, Zie ook de [host-specifieke instructies](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="4a006-141">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="4a006-142">Als uw hostingprovider GoDaddy, het proces is eenvoudig en wordt u automatisch gevraagd aangemeld en laten verifiëren namens Microsoft:</span><span class="sxs-lookup"><span data-stu-id="4a006-142">If your hosting provider is GoDaddy, the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![Selecteer machtigen op GoDaddy bevestigen Access-pagina.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="4a006-144">Gebruikers toevoegen en licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="4a006-144">Add users and assign licenses</span></span>

<span data-ttu-id="4a006-145">In de wizard kunt u gebruikers toevoegen, maar u kunt ook [gebruikers later toevoegen](add-users-m365b.md) in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="4a006-145">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="4a006-146">Als er een lokale domeincontroller, kunt u ook gebruikers met [Azure AD verbinden](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)toevoegen.</span><span class="sxs-lookup"><span data-stu-id="4a006-146">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="4a006-147">Gebruikers toevoegen in de wizard</span><span class="sxs-lookup"><span data-stu-id="4a006-147">Add users in the wizard</span></span>

<span data-ttu-id="4a006-148">Gebruikers die u in de wizard toevoegt krijgen automatisch een licentie van Microsoft 365 Business toegewezen.</span><span class="sxs-lookup"><span data-stu-id="4a006-148">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>
<span data-ttu-id="4a006-149">Als u een lokale domeincontroller en Active Directory gebruikt, Zie [ddd gebruikers met Azure AD verbinding](#add-users-by-using-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="4a006-149">If you have a local domain controller, and are using Active Directory, see [how to ddd users by using Azure AD Connect](#add-users-by-using-azure-ad-connect).</span></span>

![Schermafbeelding van de pagina nieuwe gebruikers toevoegen in de wizard](media/addnewuserspage.png)

1. <span data-ttu-id="4a006-p106">Als uw Microsoft 365 Business-abonnement bestaande gebruikers heeft (bijvoorbeeld als u Azure AD Connect hebt gebruikt), hebt u een optie om nu licenties aan hen toe te wijzen. Wijs nu licenties aan hen toe.</span><span class="sxs-lookup"><span data-stu-id="4a006-p106">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="4a006-153">Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie voor het delen van referenties met de nieuwe gebruikers die u hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="4a006-153">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="4a006-154">U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.</span><span class="sxs-lookup"><span data-stu-id="4a006-154">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="4a006-155">Sla het migreren van e-mailberichten over en kies **Volgende** op de pagina **E-mailberichten migreren**.</span><span class="sxs-lookup"><span data-stu-id="4a006-155">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="4a006-156">Als u van een andere e-mailprovider verplaatst en kopieer de gegevens later wilt, kunt u [e-mail migreren en contactpersonen voor Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="4a006-156">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>

#### <a name="add-users-by-using-azure-ad-connect"></a><span data-ttu-id="4a006-157">Gebruikers toevoegen met behulp van Azure AD verbinden</span><span class="sxs-lookup"><span data-stu-id="4a006-157">Add users by using Azure AD Connect</span></span>

 <span data-ttu-id="4a006-158">Als er een lokale domeincontroller met Active Directory, gesynchroniseerd u uw gebruikers met Microsoft 365 Business met [Azure AD verbinding](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="4a006-158">If you have a local domain controller with Active Directory, you synchronize your users with Microsoft 365 Business by using [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span> <span data-ttu-id="4a006-159">Voltooien voordat u de wizard setup.</span><span class="sxs-lookup"><span data-stu-id="4a006-159">Complete this before you start the setup wizard.</span></span> <span data-ttu-id="4a006-160">U kunt deze in het admin center downloaden:</span><span class="sxs-lookup"><span data-stu-id="4a006-160">You can download it in the admin center:</span></span>

- <span data-ttu-id="4a006-161">Ga naar **gebruikers** \> **actieve gebruikers**, selecteer de ovalen boven aan de pagina en selecteer vervolgens **adreslijstsynchronisatie** Azure AD verbinden downloaden.</span><span class="sxs-lookup"><span data-stu-id="4a006-161">Go to **Users** \> **Active users**, select the ellipses on the top of the page and then select **Directory synchronization** to download Azure AD Connect.</span></span>

    ![Selecteer op de pagina actieve gebruikers ellipsen > Directory snchronization.](media/setupdirsync.png)

    > [!IMPORTANT]
    > <span data-ttu-id="4a006-163">Als u gebruikers op deze manier maakt, moet u nog steeds licenties hieraan toewijzen in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="4a006-163">If you create users this way, you will still have to assign licenses to them in the admin center.</span></span>

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a><span data-ttu-id="4a006-164">Doorgaan naar deel uitmaakt van een domein apps en apparaten</span><span class="sxs-lookup"><span data-stu-id="4a006-164">Continue to access domain-joined apps and devices</span></span>

<span data-ttu-id="4a006-165">Als u doorgaan wilt naar deel uitmaakt van een domein apps en apparaten, lees de volgende artikelen voor twee verschillende richtingen die in te schakelen:</span><span class="sxs-lookup"><span data-stu-id="4a006-165">If you want to continue to access domain-joined apps and devices, read the following articles for two different way of enabling that:</span></span>
  
- [<span data-ttu-id="4a006-166">Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd</span><span class="sxs-lookup"><span data-stu-id="4a006-166">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    - <span data-ttu-id="4a006-167">Dit is de aanbevolen manier.</span><span class="sxs-lookup"><span data-stu-id="4a006-167">This is the recommended way.</span></span>

- [<span data-ttu-id="4a006-168">Toegang op-premises resources uit een Azure AD verbonden apparaat in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="4a006-168">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)

### <a name="connect-your-domain"></a><span data-ttu-id="4a006-169">Uw domein verbinden</span><span class="sxs-lookup"><span data-stu-id="4a006-169">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="4a006-170">Als u wilt gebruiken het .onmicrosoft domein of verbinden met Azure AD gebruikt om gebruikers in te stellen, worden er niet in deze stap.</span><span class="sxs-lookup"><span data-stu-id="4a006-170">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="4a006-171">Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.</span><span class="sxs-lookup"><span data-stu-id="4a006-171">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="4a006-172">Meestal wordt uw registrar automatisch gedetecteerd met de installatiewizard en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar.</span><span class="sxs-lookup"><span data-stu-id="4a006-172">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="4a006-173">Als dat niet het geval, [nameservers voor het instellen van Office 365 met een domeinregistratieservice wijzigen](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="4a006-173">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="4a006-174">Als u bestaande DNS-records, bijvoorbeeld met een bestaande website, wilt u uw eigen DNS-records om ervoor te zorgen dat de bestaande services blijven beheren.</span><span class="sxs-lookup"><span data-stu-id="4a006-174">If you have existing DNS records, for example an existing web site, you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="4a006-175">Zie [de grondbeginselen van het domein](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4a006-175">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Verbinding maken met uw domein pagina met ik mijn eigen DNS-records kunt beheren.](media/connectyourdomainpage.png)

2. <span data-ttu-id="4a006-177">Volg de stappen in de wizard en e-mailadres en andere diensten zal worden voor u ingesteld.</span><span class="sxs-lookup"><span data-stu-id="4a006-177">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="4a006-178">Instellen van beveiligingsbeleid en -configuraties</span><span class="sxs-lookup"><span data-stu-id="4a006-178">Set up security policies and device configurations</span></span> 

<span data-ttu-id="4a006-179">Dit beleid van toepassing op alle gebruikers u een licentie verlenen tot, of een groep gebruikers als u verschillende soorten beleid toewijzen aan een groep gebruikers.</span><span class="sxs-lookup"><span data-stu-id="4a006-179">These policies apply to every user you give a license to, or to a group of users if you decide to assign different policies to a set of users.</span></span>

#### <a name="set-up-policies-in-the-wizard"></a><span data-ttu-id="4a006-180">Instellen van het beleid van de wizard</span><span class="sxs-lookup"><span data-stu-id="4a006-180">Set up policies in the wizard</span></span>

<span data-ttu-id="4a006-181">Het beleid dat u hebt ingesteld in de wizard worden automatisch toegepast op de [groep](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) *Alle gebruikers*.</span><span class="sxs-lookup"><span data-stu-id="4a006-181">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span>

1. <span data-ttu-id="4a006-182">Op het **werkbestanden op mobiele apparaten beveiligen** de optie is **Protect werkbestanden bij verlies of diefstal van de apparaten** standaard geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="4a006-182">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="4a006-183">U hebt een optie om te **beheren hoe gebruikers toegang kunnen krijgen tot Office-bestanden op mobiele apparaten**inschakelen en deze optie wordt aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="4a006-183">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Screenshot van bescherming van werk-bestanden op mobiele apparaten pagina.](media/protectworkfilesondevices.png)

     - <span data-ttu-id="4a006-185">Als u **de werkbestanden beveiligen wanneer apparaten zijn verloren of gestolen**uitvouwt, worden de [standaardwaarden](protect-work-files-on-lost-or-stolen-device.md) vooraf geselecteerde:</span><span class="sxs-lookup"><span data-stu-id="4a006-185">If you expand **Protect work files when devices are lost or stolen**, the [default values](protect-work-files-on-lost-or-stolen-device.md) are pre-selected:</span></span>

        ![Screenshot van standaardwaarden voor het beveiligen van bestanden op apparaten verloren.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="4a006-187">Als u selecteren **hoe gebruikers toegang kunnen krijgen tot Office-bestanden op mobiele apparaten beheren** en vouwen, worden de [standaardwaarden](manage-user-access-on-mobile-devices.md) weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4a006-187">If you select **Manage how users access Office files on mobile devices** and expand it, the [default values](manage-user-access-on-mobile-devices.md) are shown.</span></span> <span data-ttu-id="4a006-188">Het is raadzaam dat u de standaardwaarden tijdens de installatie accepteert om beleid voor toepassingen voor Android, iOS en Windows 10 te maken die voor alle gebruikers gelden.</span><span class="sxs-lookup"><span data-stu-id="4a006-188">We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="4a006-189">Nadat de installatie is voltooid, kunt u meer beleidsregels maken.</span><span class="sxs-lookup"><span data-stu-id="4a006-189">You can create more policies after setup completes.</span></span>

        ![Screenshot van beveiligingsinstellingen voor Office-bestanden op een mobiel.](media/useraccessonmobile.png)

2. <span data-ttu-id="4a006-191">De laatste stap op bescherming van gegevens en apparaten kunt u een beleid instellen voor het beveiligen van Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="4a006-191">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="4a006-192">Deze instellingen worden automatisch toegepast wanneer een gebruiker Windows 10 verbinding met uw organisatie maakt.</span><span class="sxs-lookup"><span data-stu-id="4a006-192">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="4a006-193">U kunt **beveiligde Windows 10-apparaten** als u wilt zien en wijzigen van de [standaardwaarden](secure-windows-10-devices.md)kunt uitbreiden.</span><span class="sxs-lookup"><span data-stu-id="4a006-193">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="4a006-194">U kunt ook op Windows 10-apparaten [automatisch installeren van Office](install-office-on-windows-10-during-setup.md) .</span><span class="sxs-lookup"><span data-stu-id="4a006-194">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Screenshot van Windows 10 apparaat configuratiepagina instellen.](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a><span data-ttu-id="4a006-196">Wijzigen of toevoegen van beleid in het admin center</span><span class="sxs-lookup"><span data-stu-id="4a006-196">Modify or add policies in the admin center</span></span>

<span data-ttu-id="4a006-197">Zie [Microsoft 365 Business beheren](manage.md) voor koppelingen naar onderwerpen over het weergeven en wijzigen van apparaat- en app-bescherming beleid, en hoe u kunt gegevens verwijderen uit of opnieuw ingesteld Gebruikersapparaten.</span><span class="sxs-lookup"><span data-stu-id="4a006-197">See [manage Microsoft 365 Business](manage.md) for links to topics on how to view and modify device and app protection polices, and how to remove data from, or reset user devices.</span></span>

## <a name="deploy-and-manage-windows-10"></a><span data-ttu-id="4a006-198">Implementeren en beheren van Windows 10</span><span class="sxs-lookup"><span data-stu-id="4a006-198">Deploy and manage Windows 10</span></span>
<span data-ttu-id="4a006-199">Zie [Windows apparaten voor gebruikers van Microsoft 365 Business instellen](set-up-windows-devices.md) handmatig verbinding maken met Azure AD, hetzij tijdens de installatie voor nieuwe computers, of door het profiel aanmelden voor bestaande computers wijzigen.</span><span class="sxs-lookup"><span data-stu-id="4a006-199">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) to manually connect to Azure AD, either during setup for new computers, or by changing sign-in profile for existing computers.</span></span> 

### <a name="use-autopilot-to-set-up-new-devices"></a><span data-ttu-id="4a006-200">Automatische piloot gebruiken voor het instellen van nieuwe apparaten</span><span class="sxs-lookup"><span data-stu-id="4a006-200">Use Autopilot to set up new devices</span></span>

<span data-ttu-id="4a006-201">U kunt [Windows Automatische piloot](add-autopilot-devices-and-profile.md) automatisch vooraf configureren voor een gebruiker **nieuwe** Windows 10-apparaten, maar is het misschien gemakkelijker om een [partner](https://www.microsoft.com/solution-providers/search) die dit voor u kan doen.</span><span class="sxs-lookup"><span data-stu-id="4a006-201">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="4a006-202">U kunt ook gaat u naar de [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) en vragen een deskundige cloud-technologie nieuwe apparaten die u voor u aanschaft ingesteld.</span><span class="sxs-lookup"><span data-stu-id="4a006-202">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

### <a name="access-on-premises-resources"></a><span data-ttu-id="4a006-203">Toegang op ruimten resources</span><span class="sxs-lookup"><span data-stu-id="4a006-203">Access on-premises resources</span></span>

<span data-ttu-id="4a006-204">Als uw organisatie gebruikmaakt van Windows Server Active Directory op lokalen, kunt u Microsoft 365 Business instellen ter bescherming van uw Windows 10-apparaten, terwijl zij toch toegang tot bronnen voor ruimten die lokale verificatie vereisen.</span><span class="sxs-lookup"><span data-stu-id="4a006-204">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="4a006-205">Volg de stappen in [Windows 10-apparaten worden beheerd door Microsoft 365 Business domein behoren](manage-windows-devices.md) tot dit instellen.</span><span class="sxs-lookup"><span data-stu-id="4a006-205">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="4a006-206">Dit is de aanbevolen methode en apparaten in deze toestand worden genoemd hybride Azure AD verbonden apparaten.</span><span class="sxs-lookup"><span data-stu-id="4a006-206">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

<span data-ttu-id="4a006-207">Als uw bedrijf een lokale Active Directory met sommige op-ruimten (zoals bestandsshares en printers), u kunt uw Azure AD verbonden apparaten toegang geven tot deze bronnen door de stappen hier: [toegang op-premises resources uit een Azure AD verbonden apparaat in Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="4a006-207">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="4a006-208">Office 365-clienttoepassingen installeren</span><span class="sxs-lookup"><span data-stu-id="4a006-208">Deploy Office 365 client apps</span></span>

<span data-ttu-id="4a006-209">Als u Office apps in automatisch geïnstalleerd tijdens de installatie van, installeert de apps op de Windows 10-apparaten nadat de gebruikers zijn aangemeld bij Azure AD van hun Windows-apparaten met de referenties van hun werk.</span><span class="sxs-lookup"><span data-stu-id="4a006-209">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="4a006-210">Zie [mobiele apparaten voor Microsoft 365 zakelijke gebruikers](set-up-mobile-devices.md)Office installeren op mobiele iOS- of Android apparaten.</span><span class="sxs-lookup"><span data-stu-id="4a006-210">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="4a006-211">U kunt Office ook afzonderlijk installeren.</span><span class="sxs-lookup"><span data-stu-id="4a006-211">You can also install Office individually.</span></span> <span data-ttu-id="4a006-212">Zie [Office op een PC of Mac installeren](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="4a006-212">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) for instructions.</span></span>

## <a name="additional-security-settings"></a><span data-ttu-id="4a006-213">Extra beveiligingsinstellingen</span><span class="sxs-lookup"><span data-stu-id="4a006-213">Additional security settings</span></span>

<span data-ttu-id="4a006-214">Naast de beveiliging en naleving instellen in de wizard setup kunt u ook de volgende aanvullende instellingen instellen:</span><span class="sxs-lookup"><span data-stu-id="4a006-214">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="4a006-215">**E-mail beveiliging tegen ongewenste software**</span><span class="sxs-lookup"><span data-stu-id="4a006-215">**Email malware protection**</span></span>
- <span data-ttu-id="4a006-216">**Geavanceerde Threat Protection (ATP) veilige bijlagen**</span><span class="sxs-lookup"><span data-stu-id="4a006-216">**Advanced Threat Protection (ATP) Safe Attachments**</span></span>
- <span data-ttu-id="4a006-217">**ATP veilig koppelingen**</span><span class="sxs-lookup"><span data-stu-id="4a006-217">**ATP Safe Links**</span></span>
- <span data-ttu-id="4a006-218">**APT anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="4a006-218">**APT anti-phishing**</span></span>
- <span data-ttu-id="4a006-219">**Exchange Online Archiving**</span><span class="sxs-lookup"><span data-stu-id="4a006-219">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="4a006-220">**Gegevensverlies voorkomen (DLP)**</span><span class="sxs-lookup"><span data-stu-id="4a006-220">**Data loss prevention (DLP)**</span></span>
- <span data-ttu-id="4a006-221">**Azure informatiebescherming** (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="4a006-221">**Azure Information Protection** (Plan 1)</span></span>
- <span data-ttu-id="4a006-222">**Intune portal beschikbaarheid**</span><span class="sxs-lookup"><span data-stu-id="4a006-222">**Intune portal availability**</span></span>

<span data-ttu-id="4a006-223">Zie [Geavanceerde beveiligingsbeleid instellen](set-up-advanced-security.md)om op te halen is gestart.</span><span class="sxs-lookup"><span data-stu-id="4a006-223">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

<span data-ttu-id="4a006-224">Zie ook de [top 10 manieren voor het beveiligen van uw bedrijf Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) voor een overzicht van aanbevolen beveiligingsprocedures.</span><span class="sxs-lookup"><span data-stu-id="4a006-224">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>