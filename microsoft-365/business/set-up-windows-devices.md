---
title: Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Meer informatie over het instellen van Windows-apparaten met Windows 10 Pro voor Microsoft 365 Business Premium-gebruikers, waarmee gecentraliseerde beheer- en beveiligingsbesturingselementen mogelijk zijn.
ms.openlocfilehash: 85ac3c964792a132d5699703e543289020e38f57
ms.sourcegitcommit: e5bc49f0a25954d008b6cc09c2b98bb7bfe1aa2f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785847"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="4a5ec-103">Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers</span><span class="sxs-lookup"><span data-stu-id="4a5ec-103">Set up Windows devices for Microsoft 365 Business Premium users</span></span>

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="4a5ec-104">Voorwaarden voor het instellen van Windows-apparaten voor Microsoft 365 Business Premium-gebruikers</span><span class="sxs-lookup"><span data-stu-id="4a5ec-104">Prerequisites for setting up Windows devices for Microsoft 365 Business Premium users</span></span>

<span data-ttu-id="4a5ec-105">Voordat u Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers, controleert u of op alle Windows-apparaten Windows 10 Pro, versie 1703 (Creators Update) wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-105">Before you can set up Windows devices for Microsoft 365 Business Premium users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update).</span></span> <span data-ttu-id="4a5ec-106">Windows 10 Pro is een voorwaarde voor de implementatie van Windows 10 Business, een reeks cloudservices en mogelijkheden voor apparaatbeheer die windows 10 Pro aanvullen en de gecentraliseerde beheer- en beveiligingscontroles van Microsoft 365 Business Premium mogelijk maken.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-106">Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business Premium.</span></span>
  
<span data-ttu-id="4a5ec-107">Als u Windows-apparaten hebt met Windows 7 Pro, Windows 8 Pro of Windows 8.1 Pro, geeft uw Microsoft 365 Business Premium-abonnement recht op een Windows 10-upgrade.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business Premium subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="4a5ec-108">Volg de stappen in dit onderwerp voor meer informatie over het voor Windows-apparaten uitvoeren van een upgrade naar de Windows 10 Pro makersupdate. [Voor Windows-apparaten upgrade uitvoeren naar Windows Pro makersupdate](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="4a5ec-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="4a5ec-109">Zie [Controleren of het apparaat is verbonden met Azure AD](#verify-the-device-is-connected-to-azure-ad) om te controleren of u de upgrade hebt uitgevoerd of om te controleren of de upgrade heeft gewerkt.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

<span data-ttu-id="4a5ec-110">Bekijk een korte video over het verbinden van Windows met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-110">Watch a short video about connecting Windows to Microsoft 365.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="4a5ec-111">Als u deze video nuttig vond, raadpleegt u dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="4a5ec-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="4a5ec-112">Windows 10-apparaten koppelen aan Azure AD van uw organisatie</span><span class="sxs-lookup"><span data-stu-id="4a5ec-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="4a5ec-113">Wanneer alle Windows-apparaten in uw organisatie zijn geüpgraded naar Windows 10 Pro Creators Update of al Windows 10 Pro Creators Update draaien, u deze apparaten koppelen aan de Azure Active Directory van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="4a5ec-114">Zodra de apparaten zijn aangesloten, worden ze automatisch geüpgraded naar Windows 10 Business, dat deel uitmaakt van uw Microsoft 365 Business Premium-abonnement.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business Premium subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="4a5ec-115">Voor een Windows 10 Pro-apparaat dat nieuw is of waarvoor pas een upgrade is uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="4a5ec-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="4a5ec-116">Voor een nieuw apparaat met Windows 10 Pro makersupdate of voor een apparaat waarvoor wel een upgrade is uitgevoerd naar Windows 10 Pro makersupdate maar waarvoor nog geen apparaatinstellingen voor Windows 10 zijn uitgevoerd, doorloopt u de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="4a5ec-117">Doorloop de apparaatinstellingen voor Windows 10 totdat u de pagina **Hoe wilt u instellen?** op uw scherm ziet.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="4a5ec-119">Kies hier **Instellen voor een organisatie** en voer vervolgens uw gebruikersnaam en wachtwoord in voor Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business Premium.</span></span> 
    
3. <span data-ttu-id="4a5ec-120">Voltooi de apparaatinstellingen voor Windows 10.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="4a5ec-p103">Als u klaar bent, wordt de gebruiker verbonden met Azure AD van uw organisatie. In [Controleren of het apparaat is verbonden met Azure AD](#verify-the-device-is-connected-to-azure-ad) kunt u zien hoe u dit kunt controleren.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="4a5ec-123">Voor een apparaat dat al is ingesteld en waarop Windows 10 Pro wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="4a5ec-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="4a5ec-124">**Gebruikers verbinden met Azure AD**:</span><span class="sxs-lookup"><span data-stu-id="4a5ec-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="4a5ec-125">Klik op de Windows-pc van de gebruiker, waarop Windows 10 Pro, versie 1703 (makersupdate) wordt uitgevoerd (zie [vereisten](pre-requisites-for-data-protection.md)), op het Windows-logo en klik op het pictogram Instellingen.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="4a5ec-127">Ga in **Instellingen** naar **Accounts**</span><span class="sxs-lookup"><span data-stu-id="4a5ec-127">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="4a5ec-129">Klik op de pagina **Uw info** op **Toegang tot werk of school** \> **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-129">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="4a5ec-131">Kies in het dialoogvenster **Een werk- of schoolaccount instellen** onder **Andere acties** de optie **Dit apparaat toevoegen aan Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-131">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="4a5ec-133">Voer uw werk- of school-e-mailadres in op de pagina **Aanmelden** \> **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-133">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="4a5ec-134">Voer op de pagina **Wachtwoord opgeven** uw wachtwoord in \> **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-134">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="4a5ec-136">Controleer op de pagina **Controleren of dit uw organisatie is,** controleer of de informatie juist is en klik op **Deelnemen**.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-136">On the **Make sure this is your organization** page, verify that the information is correct, and click **Join**.</span></span>
  
   <span data-ttu-id="4a5ec-p104">Klik op de pagina **U bent nu helemaal klaar** op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-p104">On the **You're all set!** page, click **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, click Join](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="4a5ec-140">Als u bestanden hebt geüpload naar OneDrive voor Bedrijven, kunt u deze weer terug synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="4a5ec-141">Als u een hulpprogramma van derden hebt gebruikt om profiel en bestanden te migreren, synchroniseert u deze ook met het nieuwe profiel.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="4a5ec-142">Controleren of het apparaat is verbonden met Azure AD</span><span class="sxs-lookup"><span data-stu-id="4a5ec-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="4a5ec-143">Als u uw synchronisatiestatus wilt verifiëren, klikt u op de pagina **Access-werk of school** in **Instellingen**in het gebied **Verbonden met** _ _ om de \<organization name\> knoppen **Info** en **Loskoppelen**bloot te leggen.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-143">To verify your sync status, on the **Access work or school** page in **Settings**, click in the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**.</span></span> <span data-ttu-id="4a5ec-144">Klik op **Info** om de synchronisatiestatus te bekijken.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-144">Click on **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="4a5ec-145">Klik op de pagina Synchronisatiestatus op Synchroniseren om het recentste beleid voor het beheren van mobiele apparaten naar de pc te downloaden.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-145">On the Sync status page, click Sync to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="4a5ec-146">Als u het Microsoft 365 Business Premium-account wilt gebruiken, gaat u naar de knop **Start** van Windows, klikt u met de rechtermuisknop op de afbeelding van uw huidige account en **schakelt u vervolgens van account .**</span><span class="sxs-lookup"><span data-stu-id="4a5ec-146">To start using the Microsoft 365 Business Premium account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**.</span></span> <span data-ttu-id="4a5ec-147">Meld u aan met het e-mailadres en wachtwoord van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a><span data-ttu-id="4a5ec-149">Controleren of het apparaat is bijgewerkt naar Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="4a5ec-149">Verify the device is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="4a5ec-150">Controleer of uw Azure AD-apparaten die zijn aangesloten bij Windows 10-apparaten zijn geüpgraded naar Windows 10 Business als onderdeel van uw Microsoft 365 Business Premium-abonnement.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-150">Verify that your Azure AD joined Windows 10 devices were upgraded to Windows 10 Business as part of your Microsoft 365 Business Premium subscription.</span></span>
  
1. <span data-ttu-id="4a5ec-151">Ga naar **Instellingen** \> **Systeem** \> **Info**.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-151">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="4a5ec-152">Controleer of bij **Editie** **Windows 10 Business** wordt vermeld.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-152">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="4a5ec-154">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="4a5ec-154">Next steps</span></span>

<span data-ttu-id="4a5ec-155">Zie [Microsoft 365](set-up-mobile-devices.md) [voor bedrijven](manage.md)beheren als u uw mobiele apparaten wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="4a5ec-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 for business](manage.md).</span></span>
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a><span data-ttu-id="4a5ec-156">Voor meer informatie over het instellen en gebruiken van Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="4a5ec-156">For more on setting up and using Microsoft 365 Business Premium</span></span>

[<span data-ttu-id="4a5ec-157">Trainingsvideo's voor Microsoft 365 voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="4a5ec-157">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
