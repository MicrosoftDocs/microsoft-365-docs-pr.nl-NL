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
search.appverid:
- BCS160
- MET150
description: Meer informatie over het verplaatsen van uw bedrijf naar Microsoft 365 Business vanuit Office 365 E3.
ms.openlocfilehash: b86a163792aa71f0bca115ab918e0800acc0427d
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2020
ms.locfileid: "42811673"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a><span data-ttu-id="b6952-103">Migreren van Office 365 E3 naar Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="b6952-103">Migrating from Office 365 E3 to Microsoft 365 Business</span></span> 

<span data-ttu-id="b6952-104">Microsoft 365 Business heeft alles wat u nodig hebt voor uw kleine bedrijf en combineert de beste cloudgebaseerde productiviteitsapps met eenvoudig apparaatbeheer en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="b6952-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="b6952-105">Als u momenteel een Office 365 E3-abonnement hebt, maar niet meer dan 300 werknemers hebt, u overwegen over te schakelen naar Microsoft 365 Business voor extra beveiligingsfuncties.</span><span class="sxs-lookup"><span data-stu-id="b6952-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business for added security features.</span></span>

<span data-ttu-id="b6952-106">Migreren is eenvoudig: eerst wisselt u van licentie en worden al uw gegevens en gebruikersgegevens in uw huidige abonnement onderhouden.</span><span class="sxs-lookup"><span data-stu-id="b6952-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="b6952-107">Na de migratie moet u de functies instellen die zijn toegevoegd in Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="b6952-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a><span data-ttu-id="b6952-108">Verschillen tussen Office 365 E3 en Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="b6952-108">Differences between Office 365 E3 and Microsoft 365 Business</span></span>

<span data-ttu-id="b6952-109">In deze tabel ziet u de verschillen tussen Microsoft 365 Business en Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="b6952-109">This table shows the differences between Microsoft 365 Business and Office 365 E3.</span></span>

| <span data-ttu-id="b6952-110">Functie</span><span class="sxs-lookup"><span data-stu-id="b6952-110">Feature</span></span>    | <span data-ttu-id="b6952-111">Ondersteuning in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="b6952-111">Support in Microsoft 365 Business</span></span>    | <span data-ttu-id="b6952-112">Ondersteuning in Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="b6952-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="b6952-113">**On-premises**</span><span class="sxs-lookup"><span data-stu-id="b6952-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="b6952-114">Office-apps<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b6952-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="b6952-115">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="b6952-115">Office 365 Business</span></span>    | <span data-ttu-id="b6952-116">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="b6952-116">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="b6952-117">**Cloud productiviteits-apps**</span><span class="sxs-lookup"><span data-stu-id="b6952-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="b6952-118">Exchange Online en Outlook</span><span class="sxs-lookup"><span data-stu-id="b6952-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="b6952-119">50 GB opslaglimiet per postvak en onbeperkt Exchange Online Archiveren</span><span class="sxs-lookup"><span data-stu-id="b6952-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="b6952-120">100 GB opslaglimiet per postvak en onbeperkt Exchange Online Archiveren</span><span class="sxs-lookup"><span data-stu-id="b6952-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="b6952-121">Teams</span><span class="sxs-lookup"><span data-stu-id="b6952-121">Teams</span></span>    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="b6952-124">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="b6952-124">OneDrive for Business</span></span>    | <span data-ttu-id="b6952-125">1 TB opslaglimiet per gebruiker</span><span class="sxs-lookup"><span data-stu-id="b6952-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="b6952-126">Onbeperkt</span><span class="sxs-lookup"><span data-stu-id="b6952-126">Unlimited</span></span> | 
| <span data-ttu-id="b6952-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="b6952-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="b6952-130">StaffHub (StaffHub)</span><span class="sxs-lookup"><span data-stu-id="b6952-130">StaffHub</span></span>    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="b6952-133">Outlook Customer Manager, MileIQ</span><span class="sxs-lookup"><span data-stu-id="b6952-133">Outlook Customer Manager, MileIQ</span></span>    | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | | 
| <span data-ttu-id="b6952-135">**Bescherming tegen bedreigingen**</span><span class="sxs-lookup"><span data-stu-id="b6952-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="b6952-136">ATP-abonnement (Advanced Threat Protection) van Office 365 (Advanced Threat Protection)</span><span class="sxs-lookup"><span data-stu-id="b6952-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | <span data-ttu-id="b6952-138">Niet inbegrepen, maar kan worden toegevoegd op</span><span class="sxs-lookup"><span data-stu-id="b6952-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="b6952-139">**Identiteitsbeheer**</span><span class="sxs-lookup"><span data-stu-id="b6952-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="b6952-140">Selfservice wachtwoord opnieuw instellen voor hybride Azure Active Directory (Azure AD)-accounts, Azure multi-factor authenticatie (MFA), Voorwaardelijke toegang, wachtwoord terugschrijven voor on-premises identiteiten</span><span class="sxs-lookup"><span data-stu-id="b6952-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    |  | 
| <span data-ttu-id="b6952-142">**Apparaat- en appbeheer**</span><span class="sxs-lookup"><span data-stu-id="b6952-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="b6952-143">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="b6952-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    |  |
| <span data-ttu-id="b6952-145">Activering van gedeelde computers</span><span class="sxs-lookup"><span data-stu-id="b6952-145">Shared computer activation</span></span>|     ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="b6952-148">Upgraderechten naar Windows 10 Pro vanaf Win 7/8.1 Pro-licenties</span><span class="sxs-lookup"><span data-stu-id="b6952-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)    || 
| <span data-ttu-id="b6952-150">**Informatiebescherming**</span><span class="sxs-lookup"><span data-stu-id="b6952-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="b6952-151">Preventie van gegevensverlies van Office 365</span><span class="sxs-lookup"><span data-stu-id="b6952-151">Office 365 Data Loss Prevention</span></span>|    ![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)|![Inbegrepen bij Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="b6952-154">Azure Information Protection Plan 1, Bitlocker handhaving</span><span class="sxs-lookup"><span data-stu-id="b6952-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)||
|<span data-ttu-id="b6952-156">Azure Information Protection Plan 1, Gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="b6952-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Inbegrepen bij Microsoft 365 Business](../media/check-mark.png)||
|<span data-ttu-id="b6952-158">**Clienttoegangslicentie (CAL-rechten)**</span><span class="sxs-lookup"><span data-stu-id="b6952-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="b6952-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="b6952-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Inbegrepen bij Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="b6952-161"><sup>1</sup> De Microsoft 365 Business-versie van de Office-apps bevat geen volumeactivering via groepsbeleid, telemetrie van apps, updatebesturingselementen, spreadsheetvergelijken en informeren, of business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="b6952-161"><sup>1</sup> The Microsoft 365 Business version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="b6952-162">Migratie</span><span class="sxs-lookup"><span data-stu-id="b6952-162">Migration</span></span>

<span data-ttu-id="b6952-163">Zie Plannen handmatig [wijzigen](../commerce/subscriptions/change-plans-manually.md) voor instructies als u slechts een paar mensen naar Microsoft 365 Business wilt verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="b6952-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business.</span></span> <span data-ttu-id="b6952-164">U iedereen ook [automatisch upgraden](../commerce/subscriptions/upgrade-to-different-plan.md)of met een partner samenwerken om uw E3-abonnement en licenties te verplaatsen naar een Microsoft 365 Business-abonnement.</span><span class="sxs-lookup"><span data-stu-id="b6952-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business subscription.</span></span>
<span data-ttu-id="b6952-165">In de volgende secties worden de eventuele wijzigingen beschreven die u moet aanbrengen en wat u na de migratie doen.</span><span class="sxs-lookup"><span data-stu-id="b6952-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="b6952-166">Configuratie en gegevens van Office 365 E3-abonnementen</span><span class="sxs-lookup"><span data-stu-id="b6952-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="b6952-167">U hoeft geen wijzigingen aan te brengen in uw huidige abonnement of gegevens voordat u migreert, waaronder:</span><span class="sxs-lookup"><span data-stu-id="b6952-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="b6952-168">Abonnementsconfiguratie, zoals DNS-records en domeinnamen.</span><span class="sxs-lookup"><span data-stu-id="b6952-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="b6952-169">Gebruikers- en groepsaccounts en verificatie-instellingen, zoals multifactorauthenticatie of beleid voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="b6952-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="b6952-170">Productiviteitsserviceconfiguraties en hun gegevens, zoals Teams, Exchange Online-postvakken, SharePoint Online-sites, OneDrive voor Bedrijven-mappen en OneNote-notitieblokken.</span><span class="sxs-lookup"><span data-stu-id="b6952-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

### <a name="windows-10"></a><span data-ttu-id="b6952-171">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b6952-171">Windows 10</span></span>

<span data-ttu-id="b6952-172">Als uw Windows nog niet op windows Pro Creator-update staat, [kunt u deze upgraden naar Windows Pro Creators Update.](upgrade-to-windows-pro-creators-update.md)</span><span class="sxs-lookup"><span data-stu-id="b6952-172">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="b6952-173">Beleidsregels instellen om gebruikersapparaten en bestanden te beschermen</span><span class="sxs-lookup"><span data-stu-id="b6952-173">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="b6952-174">Als u Office 365 MDM-beleid en -apparaten instelt, worden deze apparaten weergegeven op de pagina **Apparaten** in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="b6952-174">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b6952-175">Alle beleidsregels die u instelt, worden weergegeven in de lijst met klassieke beleidsregels in de [Intune-portal.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)</span><span class="sxs-lookup"><span data-stu-id="b6952-175">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="b6952-176">Nadat u licenties hebt toegewezen aan Microsoft 365 Business, u beginnen met het beveiligen van de apparaten en bestanden van de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b6952-176">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="b6952-177">Als u iedereen in uw organisatie hebt geüpgraded naar Microsoft 365 Business, ziet u de wizard Setup op de startpagina en u de stappen [Microsoft 365 Business instellen in de](set-up.md) wizard Setup om bestanden en mobiele apparaten te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="b6952-177">If you upgraded everyone in your organization to Microsoft 365 Business, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="b6952-178">U de volgende stappen ook uitvoeren op de pagina Apparaten:</span><span class="sxs-lookup"><span data-stu-id="b6952-178">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="b6952-179">Ga in het beheercentrum in de linkernavigatienaar \> **Apparatenbeleid**. **Devices**</span><span class="sxs-lookup"><span data-stu-id="b6952-179">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="b6952-180">Kies op de pagina **Apparaatbeleid** de optie **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="b6952-180">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="b6952-181">Geef het beleid in het deelvenster **Beleid toevoegen** een naam en kies vervolgens een **beleidstype** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="b6952-181">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="b6952-182">U toepassingsbeleid instellen voor het beveiligen van bestanden op Android- en iPhone-apparaten, evenals Windows 10, en u apparaatconfiguratiebeleid instellen voor Windows 10-apparaten die eigendom zijn van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="b6952-182">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="b6952-183">Zie de volgende links voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="b6952-183">See the following links for details:</span></span>
    
  - [<span data-ttu-id="b6952-184">Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten</span><span class="sxs-lookup"><span data-stu-id="b6952-184">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="b6952-185">Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="b6952-185">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="b6952-186">Instellingen voor apparaatbeveiliging instellen voor Windows 10-pc's</span><span class="sxs-lookup"><span data-stu-id="b6952-186">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="b6952-187">Zodra u beleid hebt ingesteld, kunnen u en uw medewerkers apparaten instellen:</span><span class="sxs-lookup"><span data-stu-id="b6952-187">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="b6952-188">Zie [Windows-apparaten instellen voor Microsoft 365 Business-gebruikers](set-up-windows-devices.md) voor stappen voor Windows-apparaten.</span><span class="sxs-lookup"><span data-stu-id="b6952-188">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="b6952-189">Zie [Mobiele apparaten instellen voor Microsoft 365 Business-gebruikers](set-up-mobile-devices.md) voor stappen voor Android-telefoons en iPhones.</span><span class="sxs-lookup"><span data-stu-id="b6952-189">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 

### <a name="threat-protection"></a><span data-ttu-id="b6952-190">Bescherming tegen bedreigingen</span><span class="sxs-lookup"><span data-stu-id="b6952-190">Threat protection</span></span>

<span data-ttu-id="b6952-191">Nadat u naar Microsoft 365 Business bent gemigreerd, beschikt u over Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="b6952-191">After migrating to Microsoft 365 Business, you have Office 365 ATP.</span></span> <span data-ttu-id="b6952-192">Zie [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) voor een overzicht.</span><span class="sxs-lookup"><span data-stu-id="b6952-192">See [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview.</span></span> <span data-ttu-id="b6952-193">Zie [atp-veilige koppelingen instellen,](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa) [ATP-veilige bijlagen instellen](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)en [ATP-antiphishing instellen](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="b6952-193">To set up, see [set up ATP safe links](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [set up ATP safe attachments](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up ATP anti-phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="b6952-194">Gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="b6952-194">Sensitivity labels</span></span>

<span data-ttu-id="b6952-195">Zie [Overzicht van gevoeligheidslabels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) maken en beheren als u gevoeligheidslabels wilt gebruiken om gevoeligheidslabels te [gebruiken.](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)</span><span class="sxs-lookup"><span data-stu-id="b6952-195">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
