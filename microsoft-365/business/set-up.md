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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Informatie over het instellen van Microsoft 365 Business.
ms.openlocfilehash: ac9c8b828ff131a15bf057fa8bdc0bf56dd00987
ms.sourcegitcommit: 75b97d1ff617bc4b1b0ef9135dfe6a8842ea1b52
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/18/2019
ms.locfileid: "35772562"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a><span data-ttu-id="94349-103">Microsoft 365 Business instellen in de wizard setup</span><span class="sxs-lookup"><span data-stu-id="94349-103">Set up Microsoft 365 Business in the setup wizard</span></span>

## <a name="add-your-domain-users-and-set-up-policies"></a><span data-ttu-id="94349-104">Uw domein, gebruikers, toevoegen en instellen van het beleid</span><span class="sxs-lookup"><span data-stu-id="94349-104">Add your domain, users, and set up policies</span></span>

![Banner die verwijzen naar https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

<span data-ttu-id="94349-106">Wanneer u Microsoft 365 Business aanschaft, hebt u de mogelijkheid van een domein dat u de eigenaar of kopen tijdens de [aanmelding](sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="94349-106">When you purchase Microsoft 365 Business, you have the option of using a domain you own, or buying one during the [sign-up](sign-up.md).</span></span>

- <span data-ttu-id="94349-107">Als u een nieuw domein gekocht toen u zich aanmeldde, uw domein is ingesteld op alle en u kunt [gebruikers toevoegen en toewijzen van licenties](#add-users-and-assign-licenses)kunt verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="94349-107">If you purchased a new domain when you signed up, your domain is all set up and you can move to [Add users and assign licenses](#add-users-and-assign-licenses).</span></span>

### <a name="add-your-domain-to-personalize-sign-in"></a><span data-ttu-id="94349-108">Toevoegen van uw domein om aan te passen-in</span><span class="sxs-lookup"><span data-stu-id="94349-108">Add your domain to personalize sign-in</span></span>

1. <span data-ttu-id="94349-109">Aanmelden bij [Microsoft 365 admin center](https://admin.microsoft.com) via uw globale Administrator-referenties.</span><span class="sxs-lookup"><span data-stu-id="94349-109">Sign in to [Microsoft 365 admin center](https://admin.microsoft.com) by using your global admin credentials.</span></span> 

2. <span data-ttu-id="94349-110">Kies **een domein gebruikers** **toevoegen** of toevoegen om de wizard te starten.</span><span class="sxs-lookup"><span data-stu-id="94349-110">Choose **Add a domain** or **Add users** to start the wizard.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="94349-111">Als u tijdens de aanmelding bij een domein hebt aangeschaft, kun je het niet Zie **een domein toevoegen** stap hier.</span><span class="sxs-lookup"><span data-stu-id="94349-111">If you purchased a domain during the sign-up, you will not see **Add a domain** step here.</span></span> <span data-ttu-id="94349-112">Ga in plaats daarvan naar [gebruikers toevoegen](#add-users-and-assign-licenses) .</span><span class="sxs-lookup"><span data-stu-id="94349-112">Go to [Add users ](#add-users-and-assign-licenses) instead.</span></span>

    ![Selecteer een domein toevoegen.](media/addadomainadmincenter.png)
    
3. <span data-ttu-id="94349-114">Voer in de wizard de naam van het domein dat u wilt gebruiken (zoals contoso.com).</span><span class="sxs-lookup"><span data-stu-id="94349-114">In the wizard, enter the domain name you want to use (like contoso.com).</span></span>


    ![Screenshot van het aanpassen van uw pagina.](media/personalizesignin.png)

    
4. <span data-ttu-id="94349-116">Volg de stappen in de wizard [maken DNS-records bij een DNS-hosting provider voor Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) waarmee wordt gecontroleerd of dat u de eigenaar van het domein.</span><span class="sxs-lookup"><span data-stu-id="94349-116">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain.</span></span> <span data-ttu-id="94349-117">Als u uw domeinhost, Zie ook de [host-specifieke instructies](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span><span class="sxs-lookup"><span data-stu-id="94349-117">If you know your domain host, see also the [host specific instructions](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).</span></span>

    <span data-ttu-id="94349-118">Als uw hostingprovider GoDaddy, het proces is eenvoudig en wordt u automatisch gevraagd aangemeld en laten verifiëren namens Microsoft:</span><span class="sxs-lookup"><span data-stu-id="94349-118">If your hosting provider is GoDaddy, the process is easy and you will be automatically asked to sign in and let Microsoft authenticate on your behalf:</span></span>

    ![Selecteer machtigen op GoDaddy bevestigen Access-pagina.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a><span data-ttu-id="94349-120">Gebruikers toevoegen en licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="94349-120">Add users and assign licenses</span></span>

<span data-ttu-id="94349-121">In de wizard kunt u gebruikers toevoegen, maar u kunt ook [gebruikers later toevoegen](add-users-m365b.md) in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="94349-121">You can add users in the wizard, but you can also [add users later](add-users-m365b.md) in the admin center.</span></span> <span data-ttu-id="94349-122">Als er een lokale domeincontroller, kunt u ook gebruikers met [Azure AD verbinden](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)toevoegen.</span><span class="sxs-lookup"><span data-stu-id="94349-122">Additionally, if you have a local domain controller, you can add users with [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

#### <a name="add-users-in-the-wizard"></a><span data-ttu-id="94349-123">Gebruikers toevoegen in de wizard</span><span class="sxs-lookup"><span data-stu-id="94349-123">Add users in the wizard</span></span>

<span data-ttu-id="94349-124">Gebruikers die u in de wizard toevoegt krijgen automatisch een licentie van Microsoft 365 Business toegewezen.</span><span class="sxs-lookup"><span data-stu-id="94349-124">Any users you add in the wizard get automatically assigned a Microsoft 365 Business license.</span></span>

![Schermafbeelding van de pagina nieuwe gebruikers toevoegen in de wizard](media/addnewuserspage.png)

1. <span data-ttu-id="94349-126">Als uw abonnement op Microsoft 365 Business bestaande gebruikers (bijvoorbeeld, als u verbinden met Azure AD) heeft, krijgt u een optie voor het toewijzen van licenties voor hen nu.</span><span class="sxs-lookup"><span data-stu-id="94349-126">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you get an option to assign licenses to them now.</span></span> <span data-ttu-id="94349-127">Wijs nu licenties aan hen toe.</span><span class="sxs-lookup"><span data-stu-id="94349-127">Go ahead and add licenses to them as well.</span></span>

3. <span data-ttu-id="94349-128">Nadat u de gebruikers hebt toegevoegd, krijgt u ook een optie voor het delen van referenties met de nieuwe gebruikers die u hebt toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="94349-128">After you have added the users, you will also get an option to share credentials with the new users you added.</span></span> <span data-ttu-id="94349-129">U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.</span><span class="sxs-lookup"><span data-stu-id="94349-129">You can choose to print them out, email them, or download them.</span></span>

4. <span data-ttu-id="94349-130">Sla het migreren van e-mailberichten over en kies **Volgende** op de pagina **E-mailberichten migreren**.</span><span class="sxs-lookup"><span data-stu-id="94349-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 

    <span data-ttu-id="94349-131">Als u van een andere e-mailprovider verplaatst en kopieer de gegevens later wilt, kunt u [e-mail migreren en contactpersonen voor Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="94349-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>


### <a name="connect-your-domain"></a><span data-ttu-id="94349-132">Uw domein verbinden</span><span class="sxs-lookup"><span data-stu-id="94349-132">Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="94349-133">Als u wilt gebruiken het .onmicrosoft domein of verbinden met Azure AD gebruikt om gebruikers in te stellen, worden er niet in deze stap.</span><span class="sxs-lookup"><span data-stu-id="94349-133">If you chose to use the .onmicrosoft domain, or used Azure AD Connect to set up users, you will not see this step.</span></span>
  
<span data-ttu-id="94349-134">Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.</span><span class="sxs-lookup"><span data-stu-id="94349-134">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="94349-135">Meestal wordt uw registrar automatisch gedetecteerd met de installatiewizard en wordt een koppeling weergegeven naar stapsgewijze instructies voor het bijwerken van uw NS-records op de website van de registrar.</span><span class="sxs-lookup"><span data-stu-id="94349-135">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website.</span></span> <span data-ttu-id="94349-136">Als dat niet het geval, [nameservers voor het instellen van Office 365 met een domeinregistratieservice wijzigen](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="94349-136">If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span> 

    - <span data-ttu-id="94349-137">Als u bestaande DNS-records, bijvoorbeeld met een bestaande website, wilt u uw eigen DNS-records om ervoor te zorgen dat de bestaande services blijven beheren.</span><span class="sxs-lookup"><span data-stu-id="94349-137">If you have existing DNS records, for example an existing web site, you will want to manage your own DNS records to make sure the existing services stay connected.</span></span> <span data-ttu-id="94349-138">Zie [de grondbeginselen van het domein](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="94349-138">See [domain basics](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) for more info.</span></span>

        ![Verbinding maken met uw domein pagina met ik mijn eigen DNS-records kunt beheren.](media/connectyourdomainpage.png)

2. <span data-ttu-id="94349-140">Volg de stappen in de wizard en e-mailadres en andere diensten zal worden voor u ingesteld.</span><span class="sxs-lookup"><span data-stu-id="94349-140">Follow the steps in the wizard and email and other services will be set up for you.</span></span>

### <a name="set-up-security-policies-and-device-configurations"></a><span data-ttu-id="94349-141">Instellen van beveiligingsbeleid en -configuraties</span><span class="sxs-lookup"><span data-stu-id="94349-141">Set up security policies and device configurations</span></span> 

<span data-ttu-id="94349-142">Het beleid dat u hebt ingesteld in de wizard worden automatisch toegepast op de [groep](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) *Alle gebruikers*.</span><span class="sxs-lookup"><span data-stu-id="94349-142">The policies you set up in the wizard are applied automatically to a [Security group](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) called *All Users*.</span></span> <span data-ttu-id="94349-143">Ook kunt u extra groepen wilt toewijzen, beleid voor het in het admin center.</span><span class="sxs-lookup"><span data-stu-id="94349-143">You can also create additional groups to assign policies to in the admin center.</span></span>

1. <span data-ttu-id="94349-144">Op het **werkbestanden op mobiele apparaten beveiligen** de optie is **Protect werkbestanden bij verlies of diefstal van de apparaten** standaard geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="94349-144">On the **Protect your work files on mobile devices** the option **Protect work files when devices are lost or stolen** is selected by default.</span></span> <span data-ttu-id="94349-145">U hebt een optie om te **beheren hoe gebruikers toegang kunnen krijgen tot Office-bestanden op mobiele apparaten**inschakelen en deze optie wordt aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="94349-145">You have an option to turn on **Manage how users access Office files on mobile devices**, and this is recommended.</span></span>

    ![Screenshot van bescherming van werk-bestanden op mobiele apparaten pagina.](media/protectworkfilesondevices.png)

     - <span data-ttu-id="94349-147">Vouw de **werkbestanden beveiligen bij verlies of diefstal van de apparaten** voor het weergeven van de [standaardwaarden](protect-work-files-on-lost-or-stolen-device.md):</span><span class="sxs-lookup"><span data-stu-id="94349-147">Expand **Protect work files when devices are lost or stolen** to display the [default values](protect-work-files-on-lost-or-stolen-device.md):</span></span>

        ![Screenshot van standaardwaarden voor het beveiligen van bestanden op apparaten verloren.](media/protectworkfilesondevicesdefault.png)

    - <span data-ttu-id="94349-149">Selecteren **hoe gebruikers toegang kunnen krijgen tot Office-bestanden op mobiele apparaten beheren** en uitbreiden om de [waarden](manage-user-access-on-mobile-devices.md)weer te geven.</span><span class="sxs-lookup"><span data-stu-id="94349-149">Select **Manage how users access Office files on mobile devices** and expand it to display the [default values](manage-user-access-on-mobile-devices.md).</span></span> <span data-ttu-id="94349-150">Het is raadzaam tijdens setup toepassingenbeleid maken voor Android, iOS en Windows 10 de standaardwaarden die voor alle gebruikers gelden te accepteren.</span><span class="sxs-lookup"><span data-stu-id="94349-150">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="94349-151">Nadat de installatie is voltooid, kunt u meer beleidsregels maken.</span><span class="sxs-lookup"><span data-stu-id="94349-151">You can create more policies after setup completes.</span></span>

        ![Screenshot van beveiligingsinstellingen voor Office-bestanden op een mobiel.](media/useraccessonmobile.png)

2. <span data-ttu-id="94349-153">De laatste stap op bescherming van gegevens en apparaten kunt u een beleid instellen voor het beveiligen van Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="94349-153">The last step on protect data and devices allows you to set up policies to secure Windows 10 devices.</span></span> <span data-ttu-id="94349-154">Deze instellingen worden automatisch toegepast wanneer een gebruiker Windows 10 verbinding met uw organisatie maakt.</span><span class="sxs-lookup"><span data-stu-id="94349-154">These settings are applied automatically when a user's Windows 10 connects to your organization.</span></span> <span data-ttu-id="94349-155">U kunt **beveiligde Windows 10-apparaten** als u wilt zien en wijzigen van de [standaardwaarden](secure-windows-10-devices.md)kunt uitbreiden.</span><span class="sxs-lookup"><span data-stu-id="94349-155">You can expand **Secure Windows 10 devices** to see and modify the [default values](secure-windows-10-devices.md).</span></span>
3. <span data-ttu-id="94349-156">U kunt ook op Windows 10-apparaten [automatisch installeren van Office](install-office-on-windows-10-during-setup.md) .</span><span class="sxs-lookup"><span data-stu-id="94349-156">You can also choose to [automatically install Office](install-office-on-windows-10-during-setup.md) on Windows 10 devices.</span></span>

    ![Screenshot van Windows 10 apparaat configuratiepagina instellen.](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a><span data-ttu-id="94349-158">Office 365-clienttoepassingen installeren</span><span class="sxs-lookup"><span data-stu-id="94349-158">Deploy Office 365 client apps</span></span>

<span data-ttu-id="94349-159">Als u Office apps in automatisch geïnstalleerd tijdens de installatie van, installeert de apps op de Windows 10-apparaten nadat de gebruikers zijn aangemeld bij Azure AD van hun Windows-apparaten met de referenties van hun werk.</span><span class="sxs-lookup"><span data-stu-id="94349-159">If you chose to automatically install Office apps in during the set up, the apps will install on the Windows 10 devices once the users have signed in to Azure AD from their Windows devices with their work credentials.</span></span>
<span data-ttu-id="94349-160">Zie [mobiele apparaten voor Microsoft 365 zakelijke gebruikers](set-up-mobile-devices.md)Office installeren op mobiele iOS- of Android apparaten.</span><span class="sxs-lookup"><span data-stu-id="94349-160">To install Office on mobile iOS or Android devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span>

<span data-ttu-id="94349-161">U kunt Office ook afzonderlijk installeren.</span><span class="sxs-lookup"><span data-stu-id="94349-161">You can also install Office individually.</span></span> <span data-ttu-id="94349-162">Zie [Office op een PC of Mac installeren](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="94349-162">See [install Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) for instructions.</span></span>
