---
title: Migreren naar Microsoft 365 Business van Office 365 E3
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
description: Meer informatie over het verplaatsen van uw bedrijf Microsoft 365 Business Premium van Office 365 E3.
ms.openlocfilehash: f08b054473fdd63ec2372e81c776a1b64f89fe9d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244831"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="92bd1-103">Migreren van Office 365 E3 naar Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="92bd1-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="92bd1-104">Microsoft 365 Business Premium heeft alles wat u nodig hebt voor uw kleine bedrijf, waarbij u de beste productiviteits-apps in de cloud combineert met eenvoudig apparaatbeheer en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="92bd1-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="92bd1-105">Als u momenteel een Office 365 E3-abonnement hebt, maar niet meer dan 300 werknemers hebt, kunt u overwegen over te schakelen naar Microsoft 365 Business Premium voor extra beveiligingsfuncties.</span><span class="sxs-lookup"><span data-stu-id="92bd1-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="92bd1-106">Migreren is eenvoudig: eerst schakelt u over van licentie en blijven al uw gegevens en gebruikersgegevens in uw huidige abonnement behouden.</span><span class="sxs-lookup"><span data-stu-id="92bd1-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="92bd1-107">Na de migratie moet u de functies instellen die in de Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="92bd1-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="92bd1-108">Verschillen tussen Office 365 E3 en Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="92bd1-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="92bd1-109">In deze tabel ziet u de verschillen tussen Microsoft 365 Business Premium en Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="92bd1-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="92bd1-110">Functie</span><span class="sxs-lookup"><span data-stu-id="92bd1-110">Feature</span></span>    | <span data-ttu-id="92bd1-111">Ondersteuning in Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="92bd1-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="92bd1-112">Ondersteuning in Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="92bd1-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="92bd1-113">**On-premises**</span><span class="sxs-lookup"><span data-stu-id="92bd1-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="92bd1-114">Office apps<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="92bd1-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="92bd1-115">Microsoft 365-apps voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="92bd1-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="92bd1-116">Microsoft 365 Apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="92bd1-116">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="92bd1-117">**Cloudproductiviteits-apps**</span><span class="sxs-lookup"><span data-stu-id="92bd1-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="92bd1-118">Exchange Online en Outlook</span><span class="sxs-lookup"><span data-stu-id="92bd1-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="92bd1-119">50 GB opslaglimiet per postvak en onbeperkte Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="92bd1-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="92bd1-120">100 GB opslaglimiet per postvak en onbeperkte Exchange Online Archiving</span><span class="sxs-lookup"><span data-stu-id="92bd1-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="92bd1-121">Teams</span><span class="sxs-lookup"><span data-stu-id="92bd1-121">Teams</span></span>    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="92bd1-124">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="92bd1-124">OneDrive for Business</span></span>    | <span data-ttu-id="92bd1-125">1 TB opslaglimiet per gebruiker</span><span class="sxs-lookup"><span data-stu-id="92bd1-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="92bd1-126">Onbeperkt</span><span class="sxs-lookup"><span data-stu-id="92bd1-126">Unlimited</span></span> | 
| <span data-ttu-id="92bd1-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="92bd1-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="92bd1-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="92bd1-130">StaffHub</span></span>    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="92bd1-133">MileIQ</span><span class="sxs-lookup"><span data-stu-id="92bd1-133">MileIQ</span></span>    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| <span data-ttu-id="92bd1-135">**Bedreigingsbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="92bd1-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="92bd1-136">Defender voor Office 365 Abonnement 1</span><span class="sxs-lookup"><span data-stu-id="92bd1-136">Defender for Office 365 Plan 1</span></span> | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="92bd1-138">Niet inbegrepen, maar kan worden toegevoegd aan</span><span class="sxs-lookup"><span data-stu-id="92bd1-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="92bd1-139">**Identiteitsbeheer**</span><span class="sxs-lookup"><span data-stu-id="92bd1-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="92bd1-140">Selfservice password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span><span class="sxs-lookup"><span data-stu-id="92bd1-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| <span data-ttu-id="92bd1-142">**Apparaat- en app-beheer**</span><span class="sxs-lookup"><span data-stu-id="92bd1-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="92bd1-143">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="92bd1-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="92bd1-145">Activering van gedeelde computer</span><span class="sxs-lookup"><span data-stu-id="92bd1-145">Shared computer activation</span></span>|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="92bd1-148">Upgraderechten voor Windows 10 Pro van Win 7/8.1 Pro licenties</span><span class="sxs-lookup"><span data-stu-id="92bd1-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    || 
| <span data-ttu-id="92bd1-150">**Gegevensbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="92bd1-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="92bd1-151">Office 365 Preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="92bd1-151">Office 365 Data Loss Prevention</span></span>|    ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)|![Inbegrepen bij Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="92bd1-154">Azure Information Protection Plan 1, BitLocker afdwingen</span><span class="sxs-lookup"><span data-stu-id="92bd1-154">Azure Information Protection Plan 1, BitLocker enforcement</span></span>|![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="92bd1-156">Azure Information Protection Plan 1, Gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="92bd1-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="92bd1-158">**Client Access License (CAL-rechten)**</span><span class="sxs-lookup"><span data-stu-id="92bd1-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="92bd1-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="92bd1-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Inbegrepen bij Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="92bd1-161"><sup>1</sup> De Microsoft 365 Business Premium van de Office-apps bevat geen volumeactivering via groepsbeleid, app-telemetrie, bijwerkbesturingselementen, spreadsheets vergelijken en informeren, of bedrijfsinformatie.</span><span class="sxs-lookup"><span data-stu-id="92bd1-161"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="92bd1-162">Migratie</span><span class="sxs-lookup"><span data-stu-id="92bd1-162">Migration</span></span>

<span data-ttu-id="92bd1-163">Zie Abonnementen handmatig [](../commerce/subscriptions/change-plans-manually.md) wijzigen voor instructies als u slechts een paar personen wilt verplaatsen naar Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="92bd1-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="92bd1-164">U kunt ook [iedereen automatisch upgraden](../commerce/subscriptions/upgrade-to-different-plan.md)of samenwerken met een partner om uw E3-abonnement en licenties te verplaatsen naar een Microsoft 365 Business Premium abonnement.</span><span class="sxs-lookup"><span data-stu-id="92bd1-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="92bd1-165">In de volgende secties worden de wijzigingen beschreven die u moet aanbrengen en wat u na de migratie kunt doen.</span><span class="sxs-lookup"><span data-stu-id="92bd1-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="92bd1-166">Office 365 Configuratie en gegevens van E3-abonnement</span><span class="sxs-lookup"><span data-stu-id="92bd1-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="92bd1-167">U hoeft uw huidige abonnement of gegevens niet te wijzigen voordat u migreert, waaronder:</span><span class="sxs-lookup"><span data-stu-id="92bd1-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="92bd1-168">Abonnementsconfiguratie, zoals DNS-records en domeinnamen.</span><span class="sxs-lookup"><span data-stu-id="92bd1-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="92bd1-169">Gebruikers- en groepsaccounts en verificatie-instellingen, zoals meervoudige verificatie of beleid voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="92bd1-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="92bd1-170">Productiviteitsserviceconfiguraties en hun gegevens, zoals Teams, Exchange Online postvakken, SharePoint Online-sites, OneDrive voor Bedrijven mappen en OneNote notitieblokken.</span><span class="sxs-lookup"><span data-stu-id="92bd1-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="92bd1-171">Office toepassingen worden automatisch geschaald.</span><span class="sxs-lookup"><span data-stu-id="92bd1-171">Office applications will scale automatically.</span></span> <span data-ttu-id="92bd1-172">Office 365 moderne licenties controleert de licentietoewijzing van de gebruiker om de 72 uur en converteert Office toepassingen naar de versie die overeenkomt met het gebruikersabonnement.</span><span class="sxs-lookup"><span data-stu-id="92bd1-172">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="92bd1-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="92bd1-173">Windows 10</span></span>

<span data-ttu-id="92bd1-174">Als uw Windows nog niet aan de creator-update Windows Pro, kunt u deze upgraden [naar Windows Pro Creators Update.](upgrade-to-windows-pro-creators-update.md)</span><span class="sxs-lookup"><span data-stu-id="92bd1-174">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="92bd1-175">Beleidsregels instellen om gebruikersapparaten en bestanden te beveiligen</span><span class="sxs-lookup"><span data-stu-id="92bd1-175">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="92bd1-176">Als u Office 365 MDM-beleid en -apparaten in stelt, worden  deze apparaten weergegeven op de pagina Apparaten in het Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="92bd1-176">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="92bd1-177">Alle beleidsregels die u hebt ingesteld, worden weergegeven in de lijst met klassieke beleidsregels in de [Intune-portal.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)</span><span class="sxs-lookup"><span data-stu-id="92bd1-177">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="92bd1-178">Nadat u licenties hebt toegewezen aan Microsoft 365 Business Premium, kunt u de apparaten en bestanden van de gebruikers gaan beveiligen.</span><span class="sxs-lookup"><span data-stu-id="92bd1-178">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="92bd1-179">Als u iedereen in uw organisatie hebt geüpgraded naar Microsoft 365 Business Premium, ziet u de installatiewizard op de startpagina en kunt u de Microsoft 365 Business Premium instellen volgen [in](set-up.md) de stappen voor de installatiewizard om bestanden en mobiele apparaten te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="92bd1-179">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="92bd1-180">U kunt deze stappen ook voltooien op de pagina Apparaten:</span><span class="sxs-lookup"><span data-stu-id="92bd1-180">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="92bd1-181">Ga in het beheercentrum in het  linkernavigatienavigatiepunt naar \> **Apparatenbeleid.**</span><span class="sxs-lookup"><span data-stu-id="92bd1-181">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="92bd1-182">Kies op **de pagina** Apparaatbeleid de optie **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="92bd1-182">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="92bd1-183">Geef in **het deelvenster** Beleid toevoegen het beleid een naam op en kies vervolgens een **type beleid** in de vervolgkeuzekeuze.</span><span class="sxs-lookup"><span data-stu-id="92bd1-183">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="92bd1-184">U kunt toepassingsbeleid instellen voor het beveiligen van bestanden op Android- en iPhone-apparaten, evenals Windows 10, en u kunt apparaatconfiguratiebeleid instellen voor bedrijfsapparaten Windows 10 apparaten.</span><span class="sxs-lookup"><span data-stu-id="92bd1-184">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="92bd1-185">Zie de volgende koppelingen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="92bd1-185">See the following links for details:</span></span>
    
  - [<span data-ttu-id="92bd1-186">Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten</span><span class="sxs-lookup"><span data-stu-id="92bd1-186">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="92bd1-187">Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="92bd1-187">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="92bd1-188">Apparaatbeveiligingsinstellingen instellen voor Windows 10 pc's</span><span class="sxs-lookup"><span data-stu-id="92bd1-188">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="92bd1-189">Nadat u beleidsregels hebt ingesteld, kunnen u en uw werknemers apparaten instellen:</span><span class="sxs-lookup"><span data-stu-id="92bd1-189">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="92bd1-190">Zie [Het instellen van Windows apparaten voor Microsoft 365 Business Premium gebruikers](set-up-windows-devices.md) voor stappen voor Windows apparaten.</span><span class="sxs-lookup"><span data-stu-id="92bd1-190">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="92bd1-191">Zie [Mobiele apparaten instellen voor Microsoft 365 Business Premium gebruikers voor](set-up-mobile-devices.md) stappen voor Android-telefoons en iPhones.</span><span class="sxs-lookup"><span data-stu-id="92bd1-191">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="92bd1-192">Postvakgrootte</span><span class="sxs-lookup"><span data-stu-id="92bd1-192">Mailbox Size</span></span>

<span data-ttu-id="92bd1-193">Microsoft 365 Business Premium heeft een opslaglimiet van 50 GB voor het gebruik van Exchange Online abonnement 1.</span><span class="sxs-lookup"><span data-stu-id="92bd1-193">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="92bd1-194">Als een van uw gebruikers meer dan 50 GB postvakopslag heeft tijdens het migreren naar Microsoft 365 Business Premium, wordt u aangeraden deze gebruiker een Exchange Online-abonnement 2 toe te wijzen en het Exchange Online-abonnement 1 te verwijderen omdat het niet haalbaar is om beide toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="92bd1-194">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>


### <a name="threat-protection"></a><span data-ttu-id="92bd1-195">Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="92bd1-195">Threat protection</span></span>

<span data-ttu-id="92bd1-196">Na de migratie naar Microsoft 365 Business Premium, hebt u Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="92bd1-196">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="92bd1-197">Zie [Microsoft Defender voor Office 365](../security/office-365-security/defender-for-office-365.md) voor een overzicht.</span><span class="sxs-lookup"><span data-stu-id="92bd1-197">See [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="92bd1-198">Zie Het instellen van [Safe Koppelingen](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)instellen, Safe [Bijlagen](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)instellen en [Anti-phishing instellen in Defender](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="92bd1-198">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="92bd1-199">Vertrouwelijkheidslabels</span><span class="sxs-lookup"><span data-stu-id="92bd1-199">Sensitivity labels</span></span>

<span data-ttu-id="92bd1-200">Zie Overzicht van gevoeligheidslabels en het maken en beheren van [gevoeligheidslabels](../business-video/create-sensitivity-labels.md) video als u gevoeligheidslabels wilt gebruiken. [](../compliance/sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="92bd1-200">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](../business-video/create-sensitivity-labels.md) video.</span></span>
