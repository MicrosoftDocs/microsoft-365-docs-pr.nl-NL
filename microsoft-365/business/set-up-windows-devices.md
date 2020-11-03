---
title: Windows-apparaten instellen voor gebruikers van Microsoft 365 Business Premium
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
description: Meer informatie over het instellen van Windows-apparaten met Windows 10 Pro voor gebruikers van Microsoft 365 Business Premium, zodat u centrale beheerfuncties en beveiligingsfuncties kunt inschakelen.
ms.openlocfilehash: c95b9e51c7ec3c440509fe34084d2a030c7f2eec
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841254"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="ae371-103">Windows-apparaten instellen voor gebruikers van Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="ae371-103">Set up Windows devices for Microsoft 365 Business Premium users</span></span>

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a><span data-ttu-id="ae371-104">Vereisten voor het instellen van Windows-apparaten voor gebruikers van Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="ae371-104">Prerequisites for setting up Windows devices for Microsoft 365 Business Premium users</span></span>

<span data-ttu-id="ae371-105">Voordat u Windows-apparaten kunt instellen voor gebruikers van Microsoft 365 Business Premium, controleert u of alle Windows-apparaten gebruikmaken van Windows 10 Pro, versie 1703 (Creators update).</span><span class="sxs-lookup"><span data-stu-id="ae371-105">Before you can set up Windows devices for Microsoft 365 Business Premium users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update).</span></span> <span data-ttu-id="ae371-106">Windows 10 Pro is een vereiste voor de implementatie van Windows 10 Business, een set cloudservices en Apparaatbeheer die een aanvulling vormen op Windows 10 Pro en de gecentraliseerde beheer-en beveiligings regeling van Microsoft 365 Business Premium inschakelen.</span><span class="sxs-lookup"><span data-stu-id="ae371-106">Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business Premium.</span></span>
  
<span data-ttu-id="ae371-107">Als u Windows-apparaten met Windows 7 Pro, Windows 8 Pro of Windows 8,1 Pro hebt, geeft uw abonnement op Microsoft 365 Business Premium u recht op een upgrade naar Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ae371-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business Premium subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="ae371-108">Volg de stappen in dit onderwerp voor meer informatie over het voor Windows-apparaten uitvoeren van een upgrade naar de Windows 10 Pro makersupdate. [Voor Windows-apparaten upgrade uitvoeren naar Windows Pro makersupdate](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="ae371-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="ae371-109">Zie [controleren of het apparaat is verbonden met Azure AD](#verify-the-device-is-connected-to-azure-ad) om te controleren of u de upgrade hebt, of om te na te gaan of de upgrade werkt.</span><span class="sxs-lookup"><span data-stu-id="ae371-109">See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.</span></span>

<span data-ttu-id="ae371-110">Bekijk een korte video over het verbinden van Windows met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae371-110">Watch a short video about connecting Windows to Microsoft 365.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

<span data-ttu-id="ae371-111">Als je deze video nuttig vond, raadpleeg dan de [complete reeks trainingen voor kleine bedrijven en nieuwe gebruikers van Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="ae371-111">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="ae371-112">Windows 10-apparaten koppelen aan Azure AD van uw organisatie</span><span class="sxs-lookup"><span data-stu-id="ae371-112">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="ae371-113">Wanneer u alle Windows-apparaten in uw organisatie hebt bijgewerkt naar Windows 10 Pro Creator update of Windows 10 Pro Creator-update al uitvoert, kunt u lid worden van deze apparaten aan Azure Active Directory van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ae371-113">When all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory.</span></span> <span data-ttu-id="ae371-114">Zodra de apparaten zijn toegetreden, worden deze automatisch bijgewerkt naar Windows 10 Business, dat deel uitmaakt van uw abonnement op Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="ae371-114">Once the devices are joined, they'll be automatically upgraded to Windows 10 Business, which is part of your Microsoft 365 Business Premium subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="ae371-115">Voor een Windows 10 Pro-apparaat dat nieuw is of waarvoor pas een upgrade is uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="ae371-115">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="ae371-116">Voor een nieuw apparaat met Windows 10 Pro makersupdate of voor een apparaat waarvoor wel een upgrade is uitgevoerd naar Windows 10 Pro makersupdate maar waarvoor nog geen apparaatinstellingen voor Windows 10 zijn uitgevoerd, doorloopt u de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="ae371-116">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="ae371-117">Doorloop de apparaatinstellingen voor Windows 10 totdat u de pagina **Hoe wilt u instellen?** op uw scherm ziet.</span><span class="sxs-lookup"><span data-stu-id="ae371-117">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="ae371-119">Kies hier **voor instellen voor een organisatie** en voer vervolgens uw gebruikersnaam en wachtwoord in voor microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="ae371-119">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business Premium.</span></span> 
    
3. <span data-ttu-id="ae371-120">Voltooi de apparaatinstellingen voor Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ae371-120">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="ae371-p103">Als u klaar bent, wordt de gebruiker verbonden met Azure AD van uw organisatie. In [Controleren of het apparaat is verbonden met Azure AD](#verify-the-device-is-connected-to-azure-ad) kunt u zien hoe u dit kunt controleren.</span><span class="sxs-lookup"><span data-stu-id="ae371-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="ae371-123">Voor een apparaat dat al is ingesteld en waarop Windows 10 Pro wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="ae371-123">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="ae371-124">**Gebruikers verbinden met Azure AD** :</span><span class="sxs-lookup"><span data-stu-id="ae371-124">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="ae371-125">Klik op de Windows-pc van de gebruiker, waarop Windows 10 Pro, versie 1703 (makersupdate) wordt uitgevoerd (zie [vereisten](pre-requisites-for-data-protection.md)), op het Windows-logo en klik op het pictogram Instellingen.</span><span class="sxs-lookup"><span data-stu-id="ae371-125">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="ae371-127">Ga in **Instellingen** naar **Accounts**</span><span class="sxs-lookup"><span data-stu-id="ae371-127">In **Settings** , go to **Accounts** .</span></span>
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="ae371-129">Klik op de pagina **Uw info** op **Toegang tot werk of school** \> **Verbinden** .</span><span class="sxs-lookup"><span data-stu-id="ae371-129">On **Your info** page, click **Access work or school** \> **Connect** .</span></span>
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="ae371-131">Kies in het dialoogvenster **Een werk- of schoolaccount instellen** onder **Andere acties** de optie **Dit apparaat toevoegen aan Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="ae371-131">On the **Set up a work or school account** dialog, under **Alternate actions** , choose **Join this device to Azure Active Directory** .</span></span>
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="ae371-133">Voer uw werk- of school-e-mailadres in op de pagina **Aanmelden** \> **Volgende** .</span><span class="sxs-lookup"><span data-stu-id="ae371-133">On the **Let's get you signed in** page, enter your work or school account \> **Next** .</span></span>
  
   <span data-ttu-id="ae371-134">Voer op de pagina **Wachtwoord opgeven** uw wachtwoord in \> **Aanmelden** .</span><span class="sxs-lookup"><span data-stu-id="ae371-134">On the **Enter password** page, enter your password \> **Sign in** .</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="ae371-136">Controleer op de pagina **Controleer of dit uw organisatie is** , of de gegevens juist zijn en kies **deelnemen** .</span><span class="sxs-lookup"><span data-stu-id="ae371-136">On the **Make sure this is your organization** page, verify that the information is correct, and choose **Join** .</span></span>
  
   <span data-ttu-id="ae371-137">**U bent klaar!**</span><span class="sxs-lookup"><span data-stu-id="ae371-137">On the **You're all set!**</span></span> <span data-ttu-id="ae371-138">chosse **gereed** .</span><span class="sxs-lookup"><span data-stu-id="ae371-138">page, chosse **Done** .</span></span>
  
   ![Kies lid worden van het scherm zorg dat dit uw organisatie is.](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="ae371-140">Als u bestanden hebt geüpload naar OneDrive voor Bedrijven, kunt u deze weer terug synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="ae371-140">If you uploaded files to OneDrive for Business, sync them back down.</span></span> <span data-ttu-id="ae371-141">Als u een hulpprogramma van derden gebruikte voor het migreren van profielen en bestanden, moet u deze ook naar het nieuwe profiel synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="ae371-141">If you used a third-party tool to migrate profile and files, also sync those to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="ae371-142">Controleren of het apparaat is verbonden met Azure AD</span><span class="sxs-lookup"><span data-stu-id="ae371-142">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="ae371-143">Om de synchronisatiestatus te controleren, selecteert u op de pagina **toegang tot werk of school** in **instellingen** de optie **verbonden met** _ \<organization name\> _ om de knoppen **info** weer te geven en de **verbinding te verbreken** .</span><span class="sxs-lookup"><span data-stu-id="ae371-143">To verify your sync status, on the **Access work or school** page in **Settings** , select the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect** .</span></span> <span data-ttu-id="ae371-144">Kies **info** om de synchronisatiestatus te achterhalen.</span><span class="sxs-lookup"><span data-stu-id="ae371-144">Choose **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="ae371-145">Kies op de pagina **synchronisatiestatus** de optie **synchroniseren** om het recentste beleid voor het beheren van mobiele apparaten naar de PC te halen.</span><span class="sxs-lookup"><span data-stu-id="ae371-145">On the **Sync status** page, choose **Sync** to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="ae371-146">Als u het Microsoft 365 Business Premium-account wilt gaan gebruiken, gaat u naar de knop **Start** van Windows, klikt u met de rechtermuisknop op uw huidige accountafbeelding en schakelt u over naar een **ander account** .</span><span class="sxs-lookup"><span data-stu-id="ae371-146">To start using the Microsoft 365 Business Premium account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account** .</span></span> <span data-ttu-id="ae371-147">Meld u aan met het e-mailadres en wachtwoord van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ae371-147">Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a><span data-ttu-id="ae371-149">Controleren of de PC is bijgewerkt naar Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="ae371-149">Verify the PC is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="ae371-150">Controleer of de Windows 10-apparaten die aan Azure AD zijn gekoppeld, worden bijgewerkt naar Windows 10 Business als onderdeel van uw abonnement op Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="ae371-150">Verify that your Azure AD joined Windows 10 devices are upgraded to Windows 10 Business as part of your Microsoft 365 Business Premium subscription.</span></span>
  
1. <span data-ttu-id="ae371-151">Ga naar **Instellingen** \> **Systeem** \> **Info** .</span><span class="sxs-lookup"><span data-stu-id="ae371-151">Go to **Settings** \> **System** \> **About** .</span></span>
    
2. <span data-ttu-id="ae371-152">Controleer of bij **Editie** **Windows 10 Business** wordt vermeld.</span><span class="sxs-lookup"><span data-stu-id="ae371-152">Confirm that the **Edition** shows **Windows 10 Business** .</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="ae371-154">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="ae371-154">Next steps</span></span>

<span data-ttu-id="ae371-155">Als u uw mobiele apparaten wilt instellen, raadpleegt u [mobiele apparaten instellen voor gebruikers van Microsoft 365 Business Premium](set-up-mobile-devices.md)voor informatie over het instellen van de beveiliging van apparaten of voor het instellen van beveiligingsbeleid [van Microsoft 365 voor bedrijven](manage.md).</span><span class="sxs-lookup"><span data-stu-id="ae371-155">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 for business](manage.md).</span></span>
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a><span data-ttu-id="ae371-156">Voor meer informatie over het instellen en gebruiken van Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="ae371-156">For more on setting up and using Microsoft 365 Business Premium</span></span>

[<span data-ttu-id="ae371-157">Trainingsvideo's voor Microsoft 365 voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="ae371-157">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
