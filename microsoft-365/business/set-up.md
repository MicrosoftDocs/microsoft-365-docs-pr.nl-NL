---
title: Microsoft 365 Business instellen met de wizard Setup
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
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Informatie over het instellen van Microsoft 365 Business door vier stappen uit te voeren.
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982192"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a><span data-ttu-id="f16d5-103">Microsoft 365 Business instellen met de wizard Setup</span><span class="sxs-lookup"><span data-stu-id="f16d5-103">Set up Microsoft 365 Business by using the setup wizard</span></span>

<span data-ttu-id="f16d5-104">De stappen 1-4 hieronder.</span><span class="sxs-lookup"><span data-stu-id="f16d5-104">Complete steps 1-4 below.</span></span>
  
### <a name="set-up-microsoft-365-business"></a><span data-ttu-id="f16d5-105">Microsoft 365 Business instellen</span><span class="sxs-lookup"><span data-stu-id="f16d5-105">Set up Microsoft 365 Business</span></span>

<span data-ttu-id="f16d5-106">Bekijk een video over hoe Microsoft 365 Business instellen wanneer u een Active Directory op de locatie niet hebt:</span><span class="sxs-lookup"><span data-stu-id="f16d5-106">Watch a video on how to set up Microsoft 365 Business when you don't have an on-premises Active Directory:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
<span data-ttu-id="f16d5-p101">De installatie stappen omvatten informatie over instellingen die de lokale Active Directory opnemen. Als u doorgaan wilt naar apparaten die deel uitmaakt van een domein, leest u de volgende artikelen voor twee verschillende manier in te schakelen die en voer de stappen uit voordat u de wizard Setup uitvoert:</span><span class="sxs-lookup"><span data-stu-id="f16d5-p101">The set-up steps include information for setups that include local Active Directory. If you want to continue to access domain-joined devices, read the following articles for two different way of enabling that, and complete the steps before you run the Setup wizard:</span></span>
  
- [<span data-ttu-id="f16d5-109">Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd</span><span class="sxs-lookup"><span data-stu-id="f16d5-109">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>](manage-windows-devices.md)
    
    <span data-ttu-id="f16d5-110">-Dit is de aanbevolen manier.</span><span class="sxs-lookup"><span data-stu-id="f16d5-110">-This is the recommended way.</span></span>
    
- [<span data-ttu-id="f16d5-111">Toegang op-premises resources uit een Azure AD verbonden apparaat in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="f16d5-111">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a><span data-ttu-id="f16d5-112">Stap 1: Aanmelden aanpassen</span><span class="sxs-lookup"><span data-stu-id="f16d5-112">Step 1: Personalize sign-in</span></span>

1. <span data-ttu-id="f16d5-p102">Meld u aan bij [Microsoft 365 Business](https://portal.microsoft.com) met uw globale-beheerdersreferenties. Kies de tegel **Beheerder** om naar het beheercentrum te gaan.</span><span class="sxs-lookup"><span data-stu-id="f16d5-p102">Sign in to [Microsoft 365 Business](https://portal.microsoft.com) by using your global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="f16d5-115">Kies **Setup starten** (afhankelijk van uw status ziet u in plaats hiervan mogelijk **Doorgaan met setup** in het beheercentrum om de wizard te starten.</span><span class="sxs-lookup"><span data-stu-id="f16d5-115">Choose **Start setup** (depending on your state you may see **Continue setup** instead) in the admin center to start the wizard.</span></span> 
    
3. <span data-ttu-id="f16d5-116">Voer de domeinnaam in die u wilt gebruiken (zoals contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f16d5-116">Enter the domain name you want to use (like contoso.com).</span></span>
    
    <span data-ttu-id="f16d5-p103">Ga verder en geef uw domein, zelfs als u dit hebt gecontroleerd tijdens het gebruik van Azure AD Connect, bijvoorbeeld. De volgende twee stappen niet van toepassing op u als u Azure AD verbinden om te controleren of uw domein gebruikt.</span><span class="sxs-lookup"><span data-stu-id="f16d5-p103">Go ahead and enter your domain even if you have verified it while using Azure AD Connect, for example. The following two steps do not apply to you if you used Azure AD Connect to verify your domain.</span></span>
    
4. <span data-ttu-id="f16d5-119">Volg de stappen in de wizard [maken DNS-records bij een DNS-hosting provider voor Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) waarmee wordt gecontroleerd of dat u de eigenaar van het domein.</span><span class="sxs-lookup"><span data-stu-id="f16d5-119">Follow the steps in the wizard to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) that verifies you own the domain.</span></span> 
    
    <span data-ttu-id="f16d5-p104">Ziet u een voorbeeld van de video van [Video: Office 365-instelling in het nieuwe Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Opmerking: deze video bevat niet de stappen van de bescherming van gegevens van Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="f16d5-p104">You can view an example video of [Video: Setup Office 365 in the new Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Note that this video does not include the data protection steps of Microsoft 365 Business.</span></span>
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a><span data-ttu-id="f16d5-123">Stap 2: Toevoegen van gebruikers en toewijzen van licenties</span><span class="sxs-lookup"><span data-stu-id="f16d5-123">Step 2: Add users and assign licenses</span></span>

1. <span data-ttu-id="f16d5-124">U kunt hier gebruikers toevoegen of u kunt [gebruikers later toevoegen](add-users-m365b.md) in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="f16d5-124">You can add users here, or you can [add users later](add-users-m365b.md) in the admin center.</span></span> 
    
    <span data-ttu-id="f16d5-125">Aan gebruikers die u toevoegt, wordt automatisch een Microsoft 365 Business-licentie toegewezen.</span><span class="sxs-lookup"><span data-stu-id="f16d5-125">Any users you add get automatically assigned a Microsoft 365 Business license.</span></span>
    
2. <span data-ttu-id="f16d5-p105">Als uw Microsoft 365 Business-abonnement bestaande gebruikers heeft (bijvoorbeeld als u Azure AD Connect hebt gebruikt), hebt u een optie om nu licenties aan hen toe te wijzen. Wijs nu licenties aan hen toe.</span><span class="sxs-lookup"><span data-stu-id="f16d5-p105">If your Microsoft 365 Business subscription has existing users (for example, if you used Azure AD Connect) , you will get an option to assign licenses to them now. Go ahead and add licenses to them as well.</span></span>
    
3. <span data-ttu-id="f16d5-p106">U krijgt ook een optie voor het delen van referenties met de nieuwe gebruikers die u hebt toegevoegd. U kunt deze afdrukken, hun een e-mail sturen of deze downloaden.</span><span class="sxs-lookup"><span data-stu-id="f16d5-p106">You will also get an option to share credentials with the new users you added. You can choose to print them out, email them, or download them.</span></span>
    
4. <span data-ttu-id="f16d5-130">Sla het migreren van e-mailberichten over en kies **Volgende** op de pagina **E-mailberichten migreren**.</span><span class="sxs-lookup"><span data-stu-id="f16d5-130">Skip migrating email messages and choose **Next** on **Migrate email messages** page.</span></span> 
    
    <span data-ttu-id="f16d5-131">Als u van een andere e-mailprovider verplaatst en kopieer de gegevens later wilt, kunt u [e-mail migreren en contactpersonen voor Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span><span class="sxs-lookup"><span data-stu-id="f16d5-131">If you are moving from another email provider and want to copy your data later, you can [Migrate email and contacts to Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).</span></span>
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a><span data-ttu-id="f16d5-133">Stap 3: Uw domein verbinding</span><span class="sxs-lookup"><span data-stu-id="f16d5-133">Step 3: Connect your domain</span></span>

> [!NOTE]
> <span data-ttu-id="f16d5-134">Als u hebt gekozen voor het gebruik van het domein .onmicrosoft of Azure AD Connect gebruikt, ziet u deze stap niet.</span><span class="sxs-lookup"><span data-stu-id="f16d5-134">If you chose to use the .onmicrosoft domain, or used Azure AD Connect, you will not see this step.</span></span> 
  
<span data-ttu-id="f16d5-135">Als u services wilt instellen, moet u enkele records bij uw DNS-host of domeinregistrar bijwerken.</span><span class="sxs-lookup"><span data-stu-id="f16d5-135">To set up services, you have to update some records at your DNS host or domain registrar.</span></span>
  
1. <span data-ttu-id="f16d5-p107">De wizard setup detecteert uw registratieservice meestal en geeft u een koppeling naar de stapsgewijze instructies voor het bijwerken van de NS-records bij de domeinregistratie. Als dat niet het geval, [nameservers voor het instellen van Office 365 met een domeinregistratieservice wijzigen](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span><span class="sxs-lookup"><span data-stu-id="f16d5-p107">The setup wizard typically detects your registrar and gives you a link to step-by-step instructions for updating your NS records at the registrar website. If it doesn't, [Change nameservers to set up Office 365 with any domain registrar](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).</span></span>
    
2. <span data-ttu-id="f16d5-138">E-mail en andere services worden voor u ingesteld</span><span class="sxs-lookup"><span data-stu-id="f16d5-138">Email and other services will be set up for you</span></span>
    
### <a name="step-4-manage-devices-and-work-files"></a><span data-ttu-id="f16d5-139">Stap 4: Apparaten beheren en bestanden te werken</span><span class="sxs-lookup"><span data-stu-id="f16d5-139">Step 4: Manage devices and work files</span></span>

1. <span data-ttu-id="f16d5-p108">Op de **werkbestanden beveiligen op uw mobiele apparaten** instellen pagina **beveiligen werkbestanden bij verlies of diefstal van de apparaten** en instellingen **beheren hoe gebruikers toegang kunnen krijgen tot Office-bestanden op mobiele apparaten** **aan**. U kunt ook toegang krijgen tot elk sub instellen door te klikken op de pijltjes naast elke instelling.</span><span class="sxs-lookup"><span data-stu-id="f16d5-p108">On the **Protect work files on your mobile devices** page set both **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** settings to **On**. You can also access each sub-setting by clicking the chevrons next to each setting.</span></span>
  
  <span data-ttu-id="f16d5-142">Alle werkbestanden van uw gelicentieerde gebruikers kunnen nu worden beveiligd op iOS en Android-apparaten, zodra ze [Office apps installeren](set-up-mobile-devices.md) (en te verifiëren met hun referenties Microsoft 365 Business).</span><span class="sxs-lookup"><span data-stu-id="f16d5-142">All of your licensed users' work files are now protected on iOS and Android devices, as soon as they [install Office apps](set-up-mobile-devices.md) (and authenticate with their Microsoft 365 Business credentials).</span></span> 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. <span data-ttu-id="f16d5-144">Klik op de pagina **configuratie van Windows 10 instellen** instellen **Secure Windows 10-apparaten** **aan**.</span><span class="sxs-lookup"><span data-stu-id="f16d5-144">On the **Set Windows 10 device configuration** page, set **Secure Windows 10 Devices** setting to **On**.</span></span>
  
   <span data-ttu-id="f16d5-145">U kunt ook toegang krijgen tot elke Sub instellen door te klikken op de dubbele punthaken ernaast.</span><span class="sxs-lookup"><span data-stu-id="f16d5-145">You can also access each sub-setting by clicking the chevron next to it.</span></span>
  
3. <span data-ttu-id="f16d5-p109">De **Installatie van Office op Windows 10-apparaten** instelt op **Ja** als alle gebruikers computers Windows 10 hebt en geen bestaande Office installeert of klik-en-klaar Office wordt geïnstalleerd. Als dit niet het geval is, moet u deze optie instelt op **Nee**. Kunt u [automatisch installeren van Office](auto-install-or-uninstall-office.md) later via het admin center nadat u de computer van gebruikers hebt voorbereid. Zie [Office client-installatie voorbereiden](prepare-for-office-client-deployment.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f16d5-p109">Set the **Install Office on Windows 10 Devices** setting to **Yes** if all of your users have Windows 10 computers, and either no existing Office installs, or click-to-run Office installs. If this is not the case, set this option to **No**. You can [automatically install Office](auto-install-or-uninstall-office.md) later from the admin center after you have prepared the user computers. For instructions, see [prepare for Office client installation](prepare-for-office-client-deployment.md).</span></span>
  
    <span data-ttu-id="f16d5-150">De gelicentieerde gebruikers werkbestanden op apparaten met Windows 10 worden zodra ze worden geprojecteerd [deelnemen aan hun Windows 10-apparaat](set-up-windows-devices.md) naar een Business 365 Microsoft Azure AD-domein of [Windows 10 op een nieuwe computer hebt geïnstalleerd](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) , terwijl het tegelijkertijd lid worden van de Microsoft-365 Business Azure AD-domein.</span><span class="sxs-lookup"><span data-stu-id="f16d5-150">The licensed users' work files on Windows 10 devices will be projected as soon as they [join their Windows 10 device](set-up-windows-devices.md) to a Microsoft 365 Business Azure AD domain or [install Windows 10 on a new computer](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) while simultaneously joining the Microsoft 365 Business Azure AD domain.</span></span> 
  
4. <span data-ttu-id="f16d5-151">Klik op **volgende** en u klaar bent met de installatie.</span><span class="sxs-lookup"><span data-stu-id="f16d5-151">Click **Next** and you are done with setup.</span></span> 
  
    <span data-ttu-id="f16d5-152">Laat ons feedback op deze stap om te helpen bij het verbeteren van de ervaring.</span><span class="sxs-lookup"><span data-stu-id="f16d5-152">Please leave us feedback at this step to help us improve the experience.</span></span>
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a><span data-ttu-id="f16d5-154">Extra beveiligingsinstellingen</span><span class="sxs-lookup"><span data-stu-id="f16d5-154">Additional security settings</span></span>

<span data-ttu-id="f16d5-155">Naast de beveiliging en naleving instellen in de wizard setup kunt u ook de volgende aanvullende instellingen instellen:</span><span class="sxs-lookup"><span data-stu-id="f16d5-155">In addition to the security and compliance setting in the setup wizard, you can also set up the following additional settings:</span></span>
  
- <span data-ttu-id="f16d5-p110">Bescherming tegen onveilige bijlagen instellen. **Advanced Threat Protection** (ATP) identificeert schadelijke inhoud en vervolgens blokkeert levering van onveilige bijlagen te beschermen u tegen phishing-trucs en ransomware infecties. Zie bijlage bescherming activeren [Office 365 ATP veilige bijlagen beleid instellen](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span><span class="sxs-lookup"><span data-stu-id="f16d5-p110">Set up protection against unsafe attachments. **Advanced Threat Protection** (ATP) identifies malicious content and then blocks delivery of unsafe attachments, helping protect you against phishing schemes and ransomware infections. To activate attachment protection, see [Set up Office 365 ATP Safe Attachments policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).</span></span>
    
- <span data-ttu-id="f16d5-p111">Bescherm uw omgeving wanneer de gebruiker op een schadelijke koppelingen. ATP onderzoekt koppelingen in e-mailbericht op het moment dat een gebruiker klikt. Als u een koppeling onveilig is, wordt de gebruiker gewaarschuwd niet te bezoeken of op de hoogte gesteld dat de site is geblokkeerd. Dit biedt bescherming tegen phishing-trucs. [Instellen van het beleid van Office 365 ATP veilige koppelingen](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) of [Office 365 ATP veilige koppelingen beleid instellen](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span><span class="sxs-lookup"><span data-stu-id="f16d5-p111">Protect your environment when users click malicious links. ATP examines links in email at the time a user clicks them. If a link is unsafe, the user is warned not to visit the site or informed that the site has been blocked. This helps protect against phishing schemes. [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) or [Set up Office 365 ATP Safe Links policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).</span></span>
    
- <span data-ttu-id="f16d5-p112">U kunt alle inhoud met inbegrip van verwijderde items door het volledige postvak van een gebruiker plaatsen op **rechtszaak houdt**behouden. Zie voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="f16d5-p112">You can preserve all mailbox content including deleted items by putting a user's entire mailbox on **litigation hold**. For instructions, see</span></span> 
- <span data-ttu-id="f16d5-166">Het [vasthouden van e-mail met Exchange Online archiveren instellen](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span><span class="sxs-lookup"><span data-stu-id="f16d5-166">[Set up email retention with Exchange Online Archiving](security-features.md#set-up-email-retention-with-exchange-online-archiving).</span></span>
    
- <span data-ttu-id="f16d5-p113">Stel aangepaste **bewaarbeleid**, bijvoorbeeld gedurende een bepaalde tijd behouden of definitief verwijderen van inhoud aan het einde van de bewaarperiode. Kunt u aangepaste bewaarbeleid in effecten en Ga naar de **Data governance** conformiteit \> **vasthouden**, en volg de stappen in de wizard. Voor meer informatie, Zie [overzicht van het bewaarbeleid](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="f16d5-p113">Set up customized **retention policies**, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period. You can enable customized retention policies in the Securities and compliance center, go to **Data governance** \> **Retention**, and then follow the steps in the wizard. To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="f16d5-170">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="f16d5-170">Next steps</span></span>

<span data-ttu-id="f16d5-171">Voor gebruikers die de benodigde licenties al hebben, is de volgende stap het instellen van apparaten.</span><span class="sxs-lookup"><span data-stu-id="f16d5-171">For the users that have their licenses, the next step is to set up devices.</span></span><br/> <span data-ttu-id="f16d5-172">Zie [Windows-apparaten instellen voor gebruikers van Microsoft 365 Business](set-up-windows-devices.md) en [Mobiele apparaten instellen voor gebruikers van Microsoft 365 Business](set-up-mobile-devices.md).</span><span class="sxs-lookup"><span data-stu-id="f16d5-172">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) and [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md).</span></span> <br/><span data-ttu-id="f16d5-173">Zie [Microsoft 365 Business beheren](manage.md) voor koppelingen naar onderwerpen over het instellen van beveiligingsbeleid voor apparaten en apps en over het verwijderen van gegevens uit gebruikersapparaten.</span><span class="sxs-lookup"><span data-stu-id="f16d5-173">See [Manage Microsoft 365 Business](manage.md) for links to topics on how to set device and app protection polices, and how to remove data from user devices.</span></span> 
  


