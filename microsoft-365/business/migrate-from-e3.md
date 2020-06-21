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
description: Meer informatie over het verplaatsen van uw bedrijf naar Microsoft 365 Business Premium van Office 365 E3.
ms.openlocfilehash: d72f0c52a745ff973868b6fdaa95efa1a37a3dbd
ms.sourcegitcommit: e5bc49f0a25954d008b6cc09c2b98bb7bfe1aa2f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785926"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="0f679-103">Migreren van Office 365 E3 naar Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="0f679-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span> 

<span data-ttu-id="0f679-104">Microsoft 365 Business Premium heeft alles wat u nodig hebt voor uw kleine bedrijf, waarbij u de beste cloudgebaseerde productiviteitsapps combineert met eenvoudig apparaatbeheer en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="0f679-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="0f679-105">Als u momenteel een Office 365 E3-abonnement hebt, maar niet meer dan 300 werknemers hebt, u overwegen over te stappen naar Microsoft 365 Business Premium voor extra beveiligingsfuncties.</span><span class="sxs-lookup"><span data-stu-id="0f679-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="0f679-106">Migreren is eenvoudig: eerst wisselt u van licentie en wordt al uw gegevens en gebruikersgegevens in uw huidige abonnement gehandhaafd.</span><span class="sxs-lookup"><span data-stu-id="0f679-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="0f679-107">Na de migratie moet u de functies instellen die zijn toegevoegd in Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="0f679-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="0f679-108">Verschillen tussen Office 365 E3 en Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="0f679-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="0f679-109">In deze tabel worden de verschillen tussen Microsoft 365 Business Premium en Office 365 E3 weergegeven.</span><span class="sxs-lookup"><span data-stu-id="0f679-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="0f679-110">Functie</span><span class="sxs-lookup"><span data-stu-id="0f679-110">Feature</span></span>    | <span data-ttu-id="0f679-111">Ondersteuning in Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="0f679-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="0f679-112">Ondersteuning in Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="0f679-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="0f679-113">**On-premises**</span><span class="sxs-lookup"><span data-stu-id="0f679-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="0f679-114">Office-apps<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0f679-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="0f679-115">Microsoft 365-apps voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="0f679-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="0f679-116">Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="0f679-116">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="0f679-117">**Apps voor productiviteit in de cloud**</span><span class="sxs-lookup"><span data-stu-id="0f679-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="0f679-118">Exchange Online en Outlook</span><span class="sxs-lookup"><span data-stu-id="0f679-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="0f679-119">Opslaglimiet van 50 GB per postvak en onbeperkte Exchange Online Archivering</span><span class="sxs-lookup"><span data-stu-id="0f679-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="0f679-120">Opslaglimiet van 100 GB per postvak en onbeperkte Exchange Online Archivering</span><span class="sxs-lookup"><span data-stu-id="0f679-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="0f679-121">Teams</span><span class="sxs-lookup"><span data-stu-id="0f679-121">Teams</span></span>    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0f679-124">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="0f679-124">OneDrive for Business</span></span>    | <span data-ttu-id="0f679-125">1 TB opslaglimiet per gebruiker</span><span class="sxs-lookup"><span data-stu-id="0f679-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="0f679-126">Onbeperkt</span><span class="sxs-lookup"><span data-stu-id="0f679-126">Unlimited</span></span> | 
| <span data-ttu-id="0f679-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="0f679-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0f679-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="0f679-130">StaffHub</span></span>    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="0f679-133">Outlook Customer Manager, MileIQ</span><span class="sxs-lookup"><span data-stu-id="0f679-133">Outlook Customer Manager, MileIQ</span></span>    | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| <span data-ttu-id="0f679-135">**Bescherming tegen bedreigingen**</span><span class="sxs-lookup"><span data-stu-id="0f679-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="0f679-136">Atp-abonnement (Advanced Threat Protection) van Office 365</span><span class="sxs-lookup"><span data-stu-id="0f679-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="0f679-138">Niet inbegrepen, maar kan worden toegevoegd op</span><span class="sxs-lookup"><span data-stu-id="0f679-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="0f679-139">**Identiteitsbeheer**</span><span class="sxs-lookup"><span data-stu-id="0f679-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="0f679-140">Selfservice wachtwoordreset voor hybride Azure Active Directory-accounts (Azure AD), Azure multi-factor authentication (MFA), Voorwaardelijke toegang, terugschrijving van wachtwoorden voor on-premises identiteiten</span><span class="sxs-lookup"><span data-stu-id="0f679-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| <span data-ttu-id="0f679-142">**Apparaat- en appbeheer**</span><span class="sxs-lookup"><span data-stu-id="0f679-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="0f679-143">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="0f679-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="0f679-145">Activering van gedeelde computer</span><span class="sxs-lookup"><span data-stu-id="0f679-145">Shared computer activation</span></span>|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    | ![Inbegrepen bij Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="0f679-148">Upgraderechten naar Windows 10 Pro vanaf Win 7/8.1 Pro-licenties</span><span class="sxs-lookup"><span data-stu-id="0f679-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)    || 
| <span data-ttu-id="0f679-150">**Gegevensbeveiliging**</span><span class="sxs-lookup"><span data-stu-id="0f679-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="0f679-151">Preventie van gegevensverlies in Office 365</span><span class="sxs-lookup"><span data-stu-id="0f679-151">Office 365 Data Loss Prevention</span></span>|    ![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)|![Inbegrepen bij Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="0f679-154">Azure Information Protection Plan 1, handhaving van Bitlocker</span><span class="sxs-lookup"><span data-stu-id="0f679-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="0f679-156">Azure Information Protection Plan 1, gevoeligheidslabels</span><span class="sxs-lookup"><span data-stu-id="0f679-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Inbegrepen bij Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="0f679-158">**Client Access License (CAL-rechten)**</span><span class="sxs-lookup"><span data-stu-id="0f679-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="0f679-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="0f679-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Inbegrepen bij Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="0f679-161"><sup>1</sup> De Microsoft 365 Business Premium-versie van de Office-apps bevat geen volumeactivering via Groepsbeleid, telemetrie voor apps, updatebesturingselementen, spreadsheetvergelijking en -onderzoek of business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="0f679-161"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="0f679-162">Migratie</span><span class="sxs-lookup"><span data-stu-id="0f679-162">Migration</span></span>

<span data-ttu-id="0f679-163">Zie [Abonnementen handmatig wijzigen](../commerce/subscriptions/change-plans-manually.md) voor instructies als u slechts een paar personen wilt verplaatsen naar Microsoft 365 Business Premium als u uw abonnement wilt migreren.</span><span class="sxs-lookup"><span data-stu-id="0f679-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="0f679-164">U ook [iedereen automatisch upgraden](../commerce/subscriptions/upgrade-to-different-plan.md)of samenwerken met een partner om uw E3-abonnement en licenties te verplaatsen naar een Microsoft 365 Business Premium-abonnement.</span><span class="sxs-lookup"><span data-stu-id="0f679-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="0f679-165">In de volgende secties worden de wijzigingen beschreven die u moet aanbrengen en wat u na de migratie doen.</span><span class="sxs-lookup"><span data-stu-id="0f679-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="0f679-166">Configuratie en gegevens van Office 365 E3-abonnementen</span><span class="sxs-lookup"><span data-stu-id="0f679-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="0f679-167">U hoeft geen wijzigingen aan te brengen in uw huidige abonnement of gegevens voordat u migreert, waaronder:</span><span class="sxs-lookup"><span data-stu-id="0f679-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="0f679-168">Abonnementsconfiguratie, zoals DNS-records en domeinnamen.</span><span class="sxs-lookup"><span data-stu-id="0f679-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="0f679-169">Gebruikers- en groepsaccounts en verificatie-instellingen, zoals meerfactorauthenticatie of beleid voor voorwaardelijke toegang.</span><span class="sxs-lookup"><span data-stu-id="0f679-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="0f679-170">Configuraties van productiviteitsservice en hun gegevens, zoals Teams, Exchange Online-postvakken, SharePoint Online-sites, OneDrive voor Bedrijven-mappen en OneNote-notitieblokken.</span><span class="sxs-lookup"><span data-stu-id="0f679-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="0f679-171">Office-toepassingen worden automatisch geschaald.</span><span class="sxs-lookup"><span data-stu-id="0f679-171">Office applications will scale automatically.</span></span> <span data-ttu-id="0f679-172">Office 365-licenties controleren elke 72 uur de licentietoewijzing van de gebruiker en converteren Office-toepassingen naar de versie die overeenkomt met het gebruikersabonnement.</span><span class="sxs-lookup"><span data-stu-id="0f679-172">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="0f679-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="0f679-173">Windows 10</span></span>

<span data-ttu-id="0f679-174">Als uw Windows nog niet in windows Pro Creator-update staat, [kunt u deze bijwerken naar Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="0f679-174">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="0f679-175">Beleid instellen om gebruikersapparaten en bestanden te beschermen</span><span class="sxs-lookup"><span data-stu-id="0f679-175">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="0f679-176">Als u Office 365 MDM-beleid en -apparaten instelt, worden deze apparaten weergegeven op de pagina **Apparaten** in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="0f679-176">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="0f679-177">Alle beleidsregels die u hebt ingesteld, worden weergegeven in de lijst met klassieke beleidsregels in de [Intune-portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span><span class="sxs-lookup"><span data-stu-id="0f679-177">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="0f679-178">Nadat u licenties hebt toegewezen aan Microsoft 365 Business Premium, u beginnen met het beveiligen van de apparaten en bestanden van de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="0f679-178">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="0f679-179">Als u iedereen in uw organisatie hebt geüpgraded naar Microsoft 365 Business Premium, ziet u de wizard Setup op de startpagina en u de stappen [microsoft 365 Business Premium instellen](set-up.md) volgen in de wizard Setup om bestanden en mobiele apparaten te beschermen.</span><span class="sxs-lookup"><span data-stu-id="0f679-179">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="0f679-180">U deze stappen ook uitvoeren op de pagina Apparaten:</span><span class="sxs-lookup"><span data-stu-id="0f679-180">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="0f679-181">Ga in het beheercentrum in het **Devices** linkernavigatiesysteem naar \> **Apparaatbeleid**.</span><span class="sxs-lookup"><span data-stu-id="0f679-181">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="0f679-182">Kies Op de pagina **Apparaatbeleid** de optie **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0f679-182">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="0f679-183">Geef het beleid in **het deelvenster Polis toevoegen** een naam en kies vervolgens een **beleidstype** uit de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="0f679-183">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="0f679-184">U toepassingsbeleid instellen voor het beveiligen van bestanden op Android- en iPhone-apparaten, evenals Windows 10, en u apparaatconfiguratiebeleid instellen voor Windows 10-apparaten die eigendom zijn van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="0f679-184">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="0f679-185">Zie de volgende links voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="0f679-185">See the following links for details:</span></span>
    
  - [<span data-ttu-id="0f679-186">Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten</span><span class="sxs-lookup"><span data-stu-id="0f679-186">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="0f679-187">Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="0f679-187">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="0f679-188">Instellingen voor apparaatbeveiliging instellen voor Windows 10-pc's</span><span class="sxs-lookup"><span data-stu-id="0f679-188">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="0f679-189">Zodra u beleid hebt ingesteld, kunnen u en uw medewerkers apparaten instellen:</span><span class="sxs-lookup"><span data-stu-id="0f679-189">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="0f679-190">Zie [Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-windows-devices.md) voor stappen voor Windows-apparaten.</span><span class="sxs-lookup"><span data-stu-id="0f679-190">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="0f679-191">Zie [Mobiele apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-mobile-devices.md) voor stappen voor Android-telefoons en iPhones.</span><span class="sxs-lookup"><span data-stu-id="0f679-191">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 

### <a name="threat-protection"></a><span data-ttu-id="0f679-192">Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="0f679-192">Threat protection</span></span>

<span data-ttu-id="0f679-193">Nadat u bent gemigreerd naar Microsoft 365 Business Premium, hebt u Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="0f679-193">After migrating to Microsoft 365 Business Premium, you have Office 365 ATP.</span></span> <span data-ttu-id="0f679-194">Zie [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) voor een overzicht.</span><span class="sxs-lookup"><span data-stu-id="0f679-194">See [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview.</span></span> <span data-ttu-id="0f679-195">Zie [VEILIGE ATP-koppelingen instellen,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa) [ATP-veilige bijlagen instellen](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)en [ATP-antiphishing instellen.](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)</span><span class="sxs-lookup"><span data-stu-id="0f679-195">To set up, see [set up ATP safe links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up ATP safe attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up ATP anti-phishing](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="0f679-196">Vertrouwelijkheidslabels</span><span class="sxs-lookup"><span data-stu-id="0f679-196">Sensitivity labels</span></span>

<span data-ttu-id="0f679-197">Zie [Overzicht van gevoeligheidslabels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) en het maken en beheren van gevoeligheidslabels video als u wilt beginnen met het gebruik van [gevoeligheidslabels.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)</span><span class="sxs-lookup"><span data-stu-id="0f679-197">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
