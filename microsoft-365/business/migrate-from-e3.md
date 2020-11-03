---
title: Migreren naar Microsoft 365 Business vanuit Office 365 E3
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Meer informatie over hoe u uw bedrijf kunt overzetten naar Microsoft 365 Business Premium van Office 365 E3.
ms.openlocfilehash: b8aa58f1f050ec6247479ed02e142507a2df45fc
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842155"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="1a8fd-103">Migreren van Office 365 E3 naar Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="1a8fd-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span> 

<span data-ttu-id="1a8fd-104">Microsoft 365 Business Premium biedt alles wat u nodig hebt voor uw kleine bedrijf, waarbij de beste productiviteitstoepassingen voor de beste Cloud worden gecombineerd met eenvoudig Apparaatbeheer en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="1a8fd-105">Als u momenteel een Office 365 E3-abonnement hebt, maar niet meer dan 300 medewerkers hebt, kunt u overstappen op Microsoft 365 Business Premium voor extra beveiligingsfuncties.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="1a8fd-106">Migratie is eenvoudig: eerst overstappen op een ander abonnement, worden alle gegevens en gebruikersgegevens in uw huidige abonnement bewaard.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="1a8fd-107">Na de migratie moet u de functies instellen die worden toegevoegd in Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="1a8fd-108">Verschillen tussen Office 365 E3 en Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="1a8fd-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="1a8fd-109">In deze tabel ziet u de verschillen tussen Microsoft 365 Business Premium en Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="1a8fd-110">Functie</span><span class="sxs-lookup"><span data-stu-id="1a8fd-110">Feature</span></span>    | <span data-ttu-id="1a8fd-111">Ondersteuning in Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="1a8fd-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="1a8fd-112">Ondersteuning in Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="1a8fd-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="1a8fd-113">**On-premises**</span><span class="sxs-lookup"><span data-stu-id="1a8fd-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="1a8fd-114">Office-apps<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1a8fd-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="1a8fd-115">Microsoft 365-apps voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="1a8fd-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="1a8fd-116">Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="1a8fd-116">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="1a8fd-117">**Apps voor Cloud productiviteit**</span><span class="sxs-lookup"><span data-stu-id="1a8fd-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="1a8fd-118">Exchange Online en Outlook</span><span class="sxs-lookup"><span data-stu-id="1a8fd-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="1a8fd-119">50 GB opslaglimiet per postvak en onbeperkt Exchange Online archivering</span><span class="sxs-lookup"><span data-stu-id="1a8fd-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="1a8fd-120">100 GB opslaglimiet per postvak en onbeperkt Exchange Online archivering</span><span class="sxs-lookup"><span data-stu-id="1a8fd-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="1a8fd-121">Teams</span><span class="sxs-lookup"><span data-stu-id="1a8fd-121">Teams</span></span>    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="1a8fd-124">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="1a8fd-124">OneDrive for Business</span></span>    | <span data-ttu-id="1a8fd-125">1 TB opslaglimiet per gebruiker</span><span class="sxs-lookup"><span data-stu-id="1a8fd-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="1a8fd-126">Begrensd</span><span class="sxs-lookup"><span data-stu-id="1a8fd-126">Unlimited</span></span> | 
| <span data-ttu-id="1a8fd-127">Yammer, SharePoint Online, planner, stream</span><span class="sxs-lookup"><span data-stu-id="1a8fd-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="1a8fd-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="1a8fd-130">StaffHub</span></span>    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="1a8fd-133">Outlook Customer Manager, MileIQ</span><span class="sxs-lookup"><span data-stu-id="1a8fd-133">Outlook Customer Manager, MileIQ</span></span>    | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| <span data-ttu-id="1a8fd-135">**Bedreigingsbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="1a8fd-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="1a8fd-136">Abonnement 1 voor Office 365</span><span class="sxs-lookup"><span data-stu-id="1a8fd-136">Defender for Office 365 Plan 1</span></span> | ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="1a8fd-138">Niet inbegrepen, maar kan worden toegevoegd aan</span><span class="sxs-lookup"><span data-stu-id="1a8fd-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="1a8fd-139">**Identiteitsbeheer**</span><span class="sxs-lookup"><span data-stu-id="1a8fd-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="1a8fd-140">Selfservice voor wachtwoordherstel voor hybride Azure Active Directory-accounts (Azure AD), Azure multi-factor Authentication (MFA), voorwaardelijke toegang, wachtwoord terugschrijven voor on-premises id's</span><span class="sxs-lookup"><span data-stu-id="1a8fd-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| <span data-ttu-id="1a8fd-142">**Apparaten en apps beheren**</span><span class="sxs-lookup"><span data-stu-id="1a8fd-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="1a8fd-143">Microsoft intune, Windows auto pilot</span><span class="sxs-lookup"><span data-stu-id="1a8fd-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="1a8fd-145">Gedeelde computeractivering</span><span class="sxs-lookup"><span data-stu-id="1a8fd-145">Shared computer activation</span></span>|     ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen in Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="1a8fd-148">Upgrade rechten voor Windows 10 Pro van Win 7/8.1 Pro-licenties</span><span class="sxs-lookup"><span data-stu-id="1a8fd-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)    || 
| <span data-ttu-id="1a8fd-150">**Gegevensbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="1a8fd-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="1a8fd-151">Office 365 preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="1a8fd-151">Office 365 Data Loss Prevention</span></span>|    ![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)|![Inbegrepen in Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="1a8fd-154">Azure-informatie beschermings abonnement 1, BitLocker Enforcement</span><span class="sxs-lookup"><span data-stu-id="1a8fd-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="1a8fd-156">Azure Information Protection abonnement 1, vertrouwelijkheids labels</span><span class="sxs-lookup"><span data-stu-id="1a8fd-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Inbegrepen in Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="1a8fd-158">**Licentie voor client toegang (CAL-rechten)**</span><span class="sxs-lookup"><span data-stu-id="1a8fd-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="1a8fd-159">Enterprise CAL suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="1a8fd-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Inbegrepen in Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="1a8fd-161"><sup>1</sup> de microsoft 365 Business Premium-versie van de Office-apps omvat geen volumeactivering via Groepsbeleid, app-telemetrie, bijwerk besturingselementen, spreadsheets vergelijken en inquire of Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-161"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="1a8fd-162">Migratie</span><span class="sxs-lookup"><span data-stu-id="1a8fd-162">Migration</span></span>

<span data-ttu-id="1a8fd-163">Als u uw abonnement wilt migreren, raadpleegt u [abonnementen handmatig wijzigen](../commerce/subscriptions/change-plans-manually.md) voor instructies als u slechts enkele personen wilt overzetten naar microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="1a8fd-164">U kunt [iedereen ook automatisch upgraden](../commerce/subscriptions/upgrade-to-different-plan.md)of met een partner samenwerken om uw E3-abonnement en licenties te verplaatsen naar een abonnement op microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="1a8fd-165">In de volgende secties wordt beschreven welke wijzigingen u moet aanbrengen, indien van toepassing, en wat u na de migratie kunt doen.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="1a8fd-166">Configuratie en gegevens van Office 365 E3-abonnement</span><span class="sxs-lookup"><span data-stu-id="1a8fd-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="1a8fd-167">U hoeft geen wijzigingen aan te voeren voor uw huidige abonnement of gegevens vóór de overstap, waaronder:</span><span class="sxs-lookup"><span data-stu-id="1a8fd-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="1a8fd-168">Configuratie van het abonnement, zoals DNS-records en domeinnamen.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="1a8fd-169">Accounts en verificatie-instellingen van gebruikers en groepen, zoals multi-factor Authentication of regels voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="1a8fd-170">Productiviteits serviceconfiguraties en hun gegevens, zoals teams, Exchange Online-postvakken, SharePoint Online-sites, OneDrive voor bedrijven-mappen en OneNote-notitieblokken.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="1a8fd-171">Office-toepassingen worden automatisch aangepast.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-171">Office applications will scale automatically.</span></span> <span data-ttu-id="1a8fd-172">Met Office 365 modern Licensing wordt elke 72 uur de licentietoewijzing van de gebruiker gecontroleerd en worden de Office-toepassingen geconverteerd naar de versie die overeenkomt met het gebruikers abonnement.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-172">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="1a8fd-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1a8fd-173">Windows 10</span></span>

<span data-ttu-id="1a8fd-174">Als de Windows Update voor Windows Pro Creator nog niet is geïnstalleerd, kunt [u deze upgraden naar de Windows Pro Creators update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="1a8fd-174">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="1a8fd-175">Beleidsregels instellen voor het beschermen van gebruikers apparaten en-bestanden</span><span class="sxs-lookup"><span data-stu-id="1a8fd-175">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="1a8fd-176">Als u een beleid en apparaten voor Office 365 MDM instelt, worden deze apparaten weergegeven op de pagina **apparaten** in het microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-176">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="1a8fd-177">Beleidsregels die u instelt, worden weergegeven in de lijst met klassieke beleidsregels in de [intune-Portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span><span class="sxs-lookup"><span data-stu-id="1a8fd-177">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="1a8fd-178">Nadat u licenties hebt toegewezen aan Microsoft 365 Business Premium, kunt u beginnen met de bescherming van de apparaten en bestanden van de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-178">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="1a8fd-179">Als u iedereen in uw organisatie hebt bijgewerkt naar Microsoft 365 Business Premium, wordt de wizard Setup op de startpagina weergegeven en kunt u [Microsoft 365 Business Premium volgen via de installatiewizard van de wizard](set-up.md) om bestanden en mobiele apparaten te beschermen.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-179">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="1a8fd-180">U kunt deze stappen ook voltooien op de pagina apparaten:</span><span class="sxs-lookup"><span data-stu-id="1a8fd-180">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="1a8fd-181">Ga in het Beheercentrum in het linkernavigatievenster naar **apparaten** \> **beleid**.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-181">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="1a8fd-182">Kies **toevoegen** op de pagina **apparaatbeleid** .</span><span class="sxs-lookup"><span data-stu-id="1a8fd-182">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="1a8fd-183">Geef in het deelvenster **beleid toevoegen** een naam op voor het beleid en kies vervolgens een **beleidstype** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-183">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="1a8fd-184">U kunt toepassingenbeleid instellen voor het beschermen van bestanden op Android-en iPhone-apparaten, en Windows 10, en u kunt beleidsinstellingen voor apparaatconfiguratie instellen voor bedrijfseigen Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-184">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="1a8fd-185">Voor meer informatie raadpleegt u de volgende koppelingen:</span><span class="sxs-lookup"><span data-stu-id="1a8fd-185">See the following links for details:</span></span>
    
  - [<span data-ttu-id="1a8fd-186">Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten</span><span class="sxs-lookup"><span data-stu-id="1a8fd-186">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="1a8fd-187">Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="1a8fd-187">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="1a8fd-188">Instellingen voor apparaat-beveiliging instellen voor Windows 10-Pc's</span><span class="sxs-lookup"><span data-stu-id="1a8fd-188">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="1a8fd-189">Nadat u beleidsregels hebt ingesteld, kunnen u en uw werknemers apparaten instellen:</span><span class="sxs-lookup"><span data-stu-id="1a8fd-189">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="1a8fd-190">Zie [Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-windows-devices.md) voor stappen voor Windows-apparaten.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-190">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="1a8fd-191">Zie [mobiele apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-mobile-devices.md) voor stappen voor Android-telefoons en iPhones.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-191">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="1a8fd-192">Postvakgrootte</span><span class="sxs-lookup"><span data-stu-id="1a8fd-192">Mailbox Size</span></span>

<span data-ttu-id="1a8fd-193">Microsoft 365 Business Premium heeft een opslaglimiet van 50 GB omdat Exchange Online (abonnement 1) wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-193">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="1a8fd-194">Wanneer een van uw 50 gebruikers migreert naar Microsoft 365 Business Premium, wordt u aangeraden deze gebruiker een Exchange Online-abonnement 2 toe te wijzen en Exchange Online abonnement 1 te verwijderen, aangezien het niet haalbaar is om beide berichten toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-194">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>


### <a name="threat-protection"></a><span data-ttu-id="1a8fd-195">Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="1a8fd-195">Threat protection</span></span>

<span data-ttu-id="1a8fd-196">Na de migratie naar Microsoft 365 Business Premium hebt u Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-196">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="1a8fd-197">Zie [Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) voor een overzicht.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-197">See [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview.</span></span> <span data-ttu-id="1a8fd-198">Als u deze instelling wilt instellen, raadpleegt [u veilige koppelingen instellen](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [veilige bijlagen instellen](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)en [anti phishing instellen in Defender voor Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="1a8fd-198">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="1a8fd-199">Vertrouwelijkheidslabels</span><span class="sxs-lookup"><span data-stu-id="1a8fd-199">Sensitivity labels</span></span>

<span data-ttu-id="1a8fd-200">Als u de palletlabels wilt gebruiken, raadpleegt u [overzicht van de palletlabels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) en de video over het [maken en beheren](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) van laag labels.</span><span class="sxs-lookup"><span data-stu-id="1a8fd-200">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
