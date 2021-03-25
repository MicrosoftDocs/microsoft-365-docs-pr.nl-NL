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
description: Meer informatie over het verplaatsen van uw bedrijf naar Microsoft 365 Business Premium vanuit Office 365 E3.
ms.openlocfilehash: 3f9fd70b2d31b32027981e638de249d92e98ea08
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164528"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="075b6-103">Migreren van Office 365 E3 naar Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="075b6-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="075b6-104">Microsoft 365 Business Premium heeft alles wat u nodig hebt voor uw kleine bedrijf, waarbij de beste productiviteitsapps in de cloud worden gecombineerd met eenvoudig apparaatbeheer en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="075b6-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="075b6-105">Als u momenteel een Office 365 E3-abonnement hebt, maar niet meer dan 300 werknemers hebt, kunt u overwegen over te stappen op Microsoft 365 Business Premium voor extra beveiligingsfuncties.</span><span class="sxs-lookup"><span data-stu-id="075b6-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="075b6-106">Migreren is eenvoudig: eerst schakelt u over van licentie en blijven al uw gegevens en gebruikersgegevens in uw huidige abonnement behouden.</span><span class="sxs-lookup"><span data-stu-id="075b6-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="075b6-107">Na de migratie moet u de functies instellen die worden toegevoegd in Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="075b6-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="075b6-108">Verschillen tussen Office 365 E3 en Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="075b6-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="075b6-109">In deze tabel ziet u de verschillen tussen Microsoft 365 Business Premium en Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="075b6-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="075b6-110">Functie</span><span class="sxs-lookup"><span data-stu-id="075b6-110">Feature</span></span>    | <span data-ttu-id="075b6-111">Ondersteuning in Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="075b6-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="075b6-112">Ondersteuning in Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="075b6-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="075b6-113">**On-premises**</span><span class="sxs-lookup"><span data-stu-id="075b6-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="075b6-114">Office-apps<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="075b6-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="075b6-115">Microsoft 365-apps voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="075b6-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="075b6-116">Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="075b6-116">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="075b6-117">**Cloudproductiviteits-apps**</span><span class="sxs-lookup"><span data-stu-id="075b6-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="075b6-118">Exchange Online en Outlook</span><span class="sxs-lookup"><span data-stu-id="075b6-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="075b6-119">50 GB opslaglimiet per postvak en onbeperkte Archivering van Exchange Online</span><span class="sxs-lookup"><span data-stu-id="075b6-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="075b6-120">100 GB opslaglimiet per postvak en onbeperkte Archivering van Exchange Online</span><span class="sxs-lookup"><span data-stu-id="075b6-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="075b6-121">Teams</span><span class="sxs-lookup"><span data-stu-id="075b6-121">Teams</span></span>    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="075b6-124">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="075b6-124">OneDrive for Business</span></span>    | <span data-ttu-id="075b6-125">1 TB opslaglimiet per gebruiker</span><span class="sxs-lookup"><span data-stu-id="075b6-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="075b6-126">Onbeperkt</span><span class="sxs-lookup"><span data-stu-id="075b6-126">Unlimited</span></span> | 
| <span data-ttu-id="075b6-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="075b6-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="075b6-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="075b6-130">StaffHub</span></span>    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="075b6-133">Outlook Customer Manager</span><span class="sxs-lookup"><span data-stu-id="075b6-133">Outlook Customer Manager</span></span>    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| <span data-ttu-id="075b6-135">**Bedreigingsbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="075b6-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="075b6-136">Defender voor Office 365 Abonnement 1</span><span class="sxs-lookup"><span data-stu-id="075b6-136">Defender for Office 365 Plan 1</span></span> | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="075b6-138">Niet inbegrepen, maar kan worden toegevoegd aan</span><span class="sxs-lookup"><span data-stu-id="075b6-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="075b6-139">**Identiteitsbeheer**</span><span class="sxs-lookup"><span data-stu-id="075b6-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="075b6-140">Selfservice password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span><span class="sxs-lookup"><span data-stu-id="075b6-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| <span data-ttu-id="075b6-142">**Apparaat- en app-beheer**</span><span class="sxs-lookup"><span data-stu-id="075b6-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="075b6-143">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="075b6-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="075b6-145">Activering van gedeelde computer</span><span class="sxs-lookup"><span data-stu-id="075b6-145">Shared computer activation</span></span>|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="075b6-148">Upgraderechten voor Windows 10 Pro van Win 7/8.1 Pro-licenties</span><span class="sxs-lookup"><span data-stu-id="075b6-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    || 
| <span data-ttu-id="075b6-150">**Gegevensbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="075b6-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="075b6-151">Preventie van gegevensverlies in Office 365</span><span class="sxs-lookup"><span data-stu-id="075b6-151">Office 365 Data Loss Prevention</span></span>|    ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)|![Inbegrepen bij Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="075b6-154">Azure Information Protection Plan 1, Bitlocker enforcement</span><span class="sxs-lookup"><span data-stu-id="075b6-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="075b6-156">Azure Information Protection Plan 1, Gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="075b6-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="075b6-158">**Client Access License (CAL-rechten)**</span><span class="sxs-lookup"><span data-stu-id="075b6-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="075b6-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="075b6-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Inbegrepen bij Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="075b6-161"><sup>1</sup> De Microsoft 365 Business Premium-versie van de Office-apps bevat geen volumeactivering via groepsbeleid, app-telemetrie, bijwerkbesturingselementen, spreadsheets vergelijken en informeren of bedrijfsinformatie.</span><span class="sxs-lookup"><span data-stu-id="075b6-161"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="075b6-162">Migratie</span><span class="sxs-lookup"><span data-stu-id="075b6-162">Migration</span></span>

<span data-ttu-id="075b6-163">Zie Abonnementen handmatig [](../commerce/subscriptions/change-plans-manually.md) wijzigen voor instructies als u slechts een paar personen naar Microsoft 365 Business Premium wilt verplaatsen om uw abonnement te migreren.</span><span class="sxs-lookup"><span data-stu-id="075b6-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="075b6-164">U kunt ook [iedereen automatisch](../commerce/subscriptions/upgrade-to-different-plan.md)upgraden of samenwerken met een partner om uw E3-abonnement en licenties te verplaatsen naar een Microsoft 365 Business Premium-abonnement.</span><span class="sxs-lookup"><span data-stu-id="075b6-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="075b6-165">In de volgende secties worden de wijzigingen beschreven die u moet aanbrengen en wat u na de migratie kunt doen.</span><span class="sxs-lookup"><span data-stu-id="075b6-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="075b6-166">Configuratie en gegevens van office 365 E3-abonnement</span><span class="sxs-lookup"><span data-stu-id="075b6-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="075b6-167">U hoeft uw huidige abonnement of gegevens niet te wijzigen voordat u migreert, waaronder:</span><span class="sxs-lookup"><span data-stu-id="075b6-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="075b6-168">Abonnementsconfiguratie, zoals DNS-records en domeinnamen.</span><span class="sxs-lookup"><span data-stu-id="075b6-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="075b6-169">Gebruikers- en groepsaccounts en verificatie-instellingen, zoals meervoudige verificatie of beleid voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="075b6-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="075b6-170">Productiviteitsserviceconfiguraties en hun gegevens, zoals Teams, Exchange Online-postvakken, SharePoint Online-sites, OneDrive voor Bedrijven-mappen en OneNote-notitieblokken.</span><span class="sxs-lookup"><span data-stu-id="075b6-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="075b6-171">Office-toepassingen worden automatisch geschaald.</span><span class="sxs-lookup"><span data-stu-id="075b6-171">Office applications will scale automatically.</span></span> <span data-ttu-id="075b6-172">Moderne licenties voor Office 365 controleren elke 72 uur de licentietoewijzing van de gebruiker en converteren Office-toepassingen naar de versie die overeenkomt met het gebruikersabonnement.</span><span class="sxs-lookup"><span data-stu-id="075b6-172">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="075b6-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="075b6-173">Windows 10</span></span>

<span data-ttu-id="075b6-174">Als windows nog niet is bijgewerkt met Windows Pro Creator, kunt u deze [upgraden naar Windows Pro Creators Update.](upgrade-to-windows-pro-creators-update.md)</span><span class="sxs-lookup"><span data-stu-id="075b6-174">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="075b6-175">Beleidsregels instellen om gebruikersapparaten en bestanden te beveiligen</span><span class="sxs-lookup"><span data-stu-id="075b6-175">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="075b6-176">Als u Office 365 MDM-beleid en -apparaten in  stelt, worden deze apparaten weergegeven op de pagina Apparaten in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="075b6-176">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="075b6-177">Alle beleidsregels die u hebt ingesteld, worden weergegeven in de lijst met klassieke beleidsregels in de [Intune-portal.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)</span><span class="sxs-lookup"><span data-stu-id="075b6-177">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="075b6-178">Nadat u licenties hebt toegewezen aan Microsoft 365 Business Premium, kunt u de apparaten en bestanden van de gebruikers gaan beveiligen.</span><span class="sxs-lookup"><span data-stu-id="075b6-178">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="075b6-179">Als u iedereen in uw organisatie hebt geüpgraded naar Microsoft 365 Business Premium, ziet u de installatiewizard op de startpagina en kunt u de wizard [Microsoft 365 Business Premium](set-up.md) instellen volgen in de stappen voor de installatiewizard om bestanden en mobiele apparaten te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="075b6-179">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="075b6-180">U kunt deze stappen ook voltooien op de pagina Apparaten:</span><span class="sxs-lookup"><span data-stu-id="075b6-180">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="075b6-181">Ga in het beheercentrum in het  linkernavigatienavigatiepunt naar \> **Apparatenbeleid.**</span><span class="sxs-lookup"><span data-stu-id="075b6-181">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="075b6-182">Kies op **de pagina** Apparaatbeleid de optie **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="075b6-182">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="075b6-183">Geef in **het deelvenster** Beleid toevoegen het beleid een naam op en kies vervolgens een **type beleid** in de vervolgkeuzekeuze.</span><span class="sxs-lookup"><span data-stu-id="075b6-183">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="075b6-184">U kunt toepassingsbeleid instellen voor het beveiligen van bestanden op Android- en iPhone-apparaten, evenals Windows 10, en u kunt apparaatconfiguratiebeleid instellen voor windows 10-apparaten van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="075b6-184">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="075b6-185">Zie de volgende koppelingen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="075b6-185">See the following links for details:</span></span>
    
  - [<span data-ttu-id="075b6-186">Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten</span><span class="sxs-lookup"><span data-stu-id="075b6-186">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="075b6-187">Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="075b6-187">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="075b6-188">Apparaatbeveiligingsinstellingen instellen voor Windows 10-pc's</span><span class="sxs-lookup"><span data-stu-id="075b6-188">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="075b6-189">Nadat u beleidsregels hebt ingesteld, kunnen u en uw werknemers apparaten instellen:</span><span class="sxs-lookup"><span data-stu-id="075b6-189">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="075b6-190">Zie [Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-windows-devices.md) voor stappen voor Windows-apparaten.</span><span class="sxs-lookup"><span data-stu-id="075b6-190">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="075b6-191">Zie [Mobiele apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-mobile-devices.md) voor stappen voor Android-telefoons en iPhones.</span><span class="sxs-lookup"><span data-stu-id="075b6-191">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="075b6-192">Postvakgrootte</span><span class="sxs-lookup"><span data-stu-id="075b6-192">Mailbox Size</span></span>

<span data-ttu-id="075b6-193">Microsoft 365 Business Premium heeft een opslaglimiet van 50 GB omdat hiervoor Exchange Online Plan 1 wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="075b6-193">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="075b6-194">Wanneer u migreert naar Microsoft 365 Business Premium, wordt u aangeraden om deze gebruiker een Exchange Online-abonnement 2 toe te wijzen en het Exchange Online-abonnement 1 te verwijderen omdat het niet haalbaar is om beide toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="075b6-194">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>


### <a name="threat-protection"></a><span data-ttu-id="075b6-195">Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="075b6-195">Threat protection</span></span>

<span data-ttu-id="075b6-196">Na de migratie naar Microsoft 365 Business Premium hebt u Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="075b6-196">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="075b6-197">Zie [Microsoft Defender voor Office 365](../security/defender-365-security/defender-for-office-365.md) voor een overzicht.</span><span class="sxs-lookup"><span data-stu-id="075b6-197">See [Microsoft Defender for Office 365](../security/defender-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="075b6-198">Zie Veilige koppelingen [instellen,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)Veilige [](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)bijlagen instellen en [Anti-phishing instellen in Defender voor Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)om dit in te stellen.</span><span class="sxs-lookup"><span data-stu-id="075b6-198">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="075b6-199">Vertrouwelijkheidslabels</span><span class="sxs-lookup"><span data-stu-id="075b6-199">Sensitivity labels</span></span>

<span data-ttu-id="075b6-200">Zie Overzicht van gevoeligheidslabels en het maken en beheren van [gevoeligheidslabels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video als u gevoeligheidslabels wilt gebruiken. [](../compliance/sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="075b6-200">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
