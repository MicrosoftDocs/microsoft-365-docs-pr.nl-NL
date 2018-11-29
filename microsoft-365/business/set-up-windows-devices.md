---
title: Windows-pc's instellen voor gebruikers van Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 'Informatie over het instellen van Windows-apparaten met Windows 10 Pro voor Microsoft 365 zakelijke gebruikers. '
ms.openlocfilehash: 482199b175c568bfae420619aa02024303894789
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/28/2018
ms.locfileid: "26982852"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a><span data-ttu-id="1fd28-103">Windows-pc's instellen voor gebruikers van Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="1fd28-103">Set up Windows devices for Microsoft 365 Business users</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1fd28-104">Vereisten</span><span class="sxs-lookup"><span data-stu-id="1fd28-104">Prerequisites</span></span>

<span data-ttu-id="1fd28-p101">Voordat u Windows-apparaten voor gebruikers van Microsoft 365 Business kunt instellen, moet u ervoor zorgen dat op alle Windows-apparaten Windows 10 Pro, versie 1703 (makersupdate) wordt uitgevoerd. Windows 10 Pro is een vereiste voor de implementatie van Windows 10 Business. Dat is een set cloudservices en apparaatbeheerfuncties die een aanvulling vormt op Windows 10 Pro en die het centrale beheer en de besturingselementen voor beveiliging van Microsoft 365 Business inschakelt.</span><span class="sxs-lookup"><span data-stu-id="1fd28-p101">Before you can set up Windows devices for Microsoft 365 Business users, make sure all the Windows devices are running Windows 10 Pro, version 1703 (Creators Update). Windows 10 Pro is a prerequisite for deploying Windows 10 Business, which is a set of cloud services and device management capabilities that complement Windows 10 Pro and enable the centralized management and security controls of Microsoft 365 Business.</span></span>
  
<span data-ttu-id="1fd28-107">Als u Windows-apparaten met Windows 7 Pro, Windows 8 Pro of Windows 8.1 Pro hebt, geeft uw abonnement op Microsoft 365 Business u recht op een upgrade naar Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1fd28-107">If you have Windows devices running Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your Microsoft 365 Business subscription entitles you to a Windows 10 upgrade.</span></span>
  
<span data-ttu-id="1fd28-108">Volg de stappen in dit onderwerp voor meer informatie over het voor Windows-apparaten uitvoeren van een upgrade naar de Windows 10 Pro makersupdate. [Voor Windows-apparaten upgrade uitvoeren naar Windows Pro makersupdate](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="1fd28-108">For more information on how to upgrade Windows devices to Windows 10 Pro Creators Update, follow the steps in this topic: [Upgrade Windows devices to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
  
<span data-ttu-id="1fd28-109">Zie [Controleren of het apparaat is bijgewerkt naar Windows 10 Business](set-up-windows-devices.md#bkmk_verifywin10) om te controleren of u de upgrade al hebt, of om te na te gaan of de upgrade is geslaagd.</span><span class="sxs-lookup"><span data-stu-id="1fd28-109">See [Verify the device is upgraded to Windows 10 Business](set-up-windows-devices.md#bkmk_verifywin10) to verify you have the upgrade, or to make sure the upgrade worked.</span></span> 
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a><span data-ttu-id="1fd28-110">Windows 10-apparaten koppelen aan Azure AD van uw organisatie</span><span class="sxs-lookup"><span data-stu-id="1fd28-110">Join Windows 10 devices to your organization's Azure AD</span></span>

<span data-ttu-id="1fd28-p102">Wanneer voor alle Windows-apparaten in uw organisatie een upgrade is uitgevoerd naar Windows 10 Pro makersupdate of als daarop Windows 10 Pro makersupdate al wordt uitgevoerd, kunt deze apparaten koppelen aan Azure Active Directory van uw organisatie. Als de apparaten eenmaal zijn gekoppeld, worden deze automatisch bijgewerkt naar Windows 10 Business, dat deel uitmaakt van het abonnement op Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="1fd28-p102">Once all Windows devices in your organization have either been upgraded to Windows 10 Pro Creators Update or are already running Windows 10 Pro Creators Update, you can join these devices to your organization's Azure Active Directory. Once the devices are joined, they will automatically be upgraded to Windows 10 Business, which is part of your Microsoft 365 Business subscription.</span></span>
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a><span data-ttu-id="1fd28-113">Voor een Windows 10 Pro-apparaat dat nieuw is of waarvoor pas een upgrade is uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="1fd28-113">For a brand new, or newly upgraded, Windows 10 Pro device</span></span>

<span data-ttu-id="1fd28-114">Voor een nieuw apparaat met Windows 10 Pro makersupdate of voor een apparaat waarvoor wel een upgrade is uitgevoerd naar Windows 10 Pro makersupdate maar waarvoor nog geen apparaatinstellingen voor Windows 10 zijn uitgevoerd, doorloopt u de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="1fd28-114">For a brand new device running Windows 10 Pro Creators Update, or for a device that was upgraded to Windows 10 Pro Creators Update but has not gone through Windows 10 device setup, follow these steps.</span></span>
  
1. <span data-ttu-id="1fd28-115">Doorloop de apparaatinstellingen voor Windows 10 totdat u de pagina **Hoe wilt u instellen?** op uw scherm ziet.</span><span class="sxs-lookup"><span data-stu-id="1fd28-115">Go through Windows 10 device setup until you get to the **How would you like to set up?** page.</span></span> 
    
    ![On the How would you like to set up page, choose Set up for an organization](media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. <span data-ttu-id="1fd28-117">Kies hier voor **Instellen voor een organisatie** en typ vervolgens uw gebruikersnaam en wachtwoord voor Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="1fd28-117">Here, choose **Set up for an organization** and then enter your username and password for Microsoft 365 Business.</span></span> 
    
3. <span data-ttu-id="1fd28-118">Voltooi de apparaatinstellingen voor Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1fd28-118">Finish Windows 10 device setup.</span></span>
    
   <span data-ttu-id="1fd28-p103">Als u klaar bent, wordt de gebruiker verbonden met Azure AD van uw organisatie. In [Controleren of het apparaat is verbonden met Azure AD](set-up-windows-devices.md#bkmk_verifyaad) kunt u zien hoe u dit kunt controleren.</span><span class="sxs-lookup"><span data-stu-id="1fd28-p103">Once you're done, the user will be connected to your organization's Azure AD. See [Verify the device is connected to Azure AD](set-up-windows-devices.md#bkmk_verifyaad) to make sure.</span></span> 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a><span data-ttu-id="1fd28-121">Voor een apparaat dat al is ingesteld en waarop Windows 10 Pro wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="1fd28-121">For a device already set up and running Windows 10 Pro</span></span>

 <span data-ttu-id="1fd28-122">**Gebruikers verbinden met Azure AD**:</span><span class="sxs-lookup"><span data-stu-id="1fd28-122">**Connect users to Azure AD:**</span></span>
  
1. <span data-ttu-id="1fd28-123">Klik op de Windows-pc van de gebruiker, waarop Windows 10 Pro, versie 1703 (makersupdate) wordt uitgevoerd (zie [vereisten](pre-requisites-for-data-protection.md)), op het Windows-logo en klik op het pictogram Instellingen.</span><span class="sxs-lookup"><span data-stu-id="1fd28-123">In your user's Windows PC, that is running Windows 10 Pro, version 1703 (Creators Update) (see [pre-requisites](pre-requisites-for-data-protection.md)), click the Windows logo, and then the Settings icon.</span></span>
  
   ![In the Start menu, click Windows Settings icon](media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. <span data-ttu-id="1fd28-125">Ga in **Instellingen** naar **Accounts**</span><span class="sxs-lookup"><span data-stu-id="1fd28-125">In **Settings**, go to **Accounts**.</span></span>
  
   ![In Windows Settings, go to Accounts](media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. <span data-ttu-id="1fd28-127">Klik op de pagina **Uw info** op **Toegang tot werk of school** \> **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="1fd28-127">On **Your info** page, click **Access work or school** \> **Connect**.</span></span>
  
   ![Choose Connect under Access work or school](media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. <span data-ttu-id="1fd28-129">Kies in het dialoogvenster **Een werk- of schoolaccount instellen** onder **Andere acties** de optie **Dit apparaat toevoegen aan Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="1fd28-129">On the **Set up a work or school account** dialog, under **Alternate actions**, choose **Join this device to Azure Active Directory**.</span></span>
  
   ![Click Join this device to Azure Active Directory](media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. <span data-ttu-id="1fd28-131">Voer uw werk- of school-e-mailadres in op de pagina **Aanmelden** \> **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="1fd28-131">On the **Let's get you signed in** page, enter your work or school account \> **Next**.</span></span>
  
   <span data-ttu-id="1fd28-132">Voer op de pagina **Wachtwoord opgeven** uw wachtwoord in \> **Aanmelden**.</span><span class="sxs-lookup"><span data-stu-id="1fd28-132">On the **Enter password** page, enter your password \> **Sign in**.</span></span>
  
   ![Enter your work or school email on the Let's get you signed in page](media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. <span data-ttu-id="1fd28-134">Op de \*\* zorg ervoor dat dit is uw organisatie \*\* pagina, controleert u of de informatie klopt en klik op **deelnemen aan**.</span><span class="sxs-lookup"><span data-stu-id="1fd28-134">On the \*\* Make sure this is your organization \*\* page, verify that the information is correct, and click **Join**.</span></span>
  
   <span data-ttu-id="1fd28-p104">Klik op de pagina **U bent nu helemaal klaar** op **Gereed**.</span><span class="sxs-lookup"><span data-stu-id="1fd28-p104">On the **You're all set!** page, click **Done**.</span></span>
  
   ![On the Make sure this is your organization screen, click Join](media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
<span data-ttu-id="1fd28-p105">Als u bestanden hebt geüpload naar OneDrive voor Bedrijven, kunt u deze weer terug synchroniseren. Als u een hulpprogramma van derden hebt gebruikt om het profiel en de bestanden te migreren, moeten deze ook naar het nieuwe profiel worden gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="1fd28-p105">If you uploaded files to OneDrive for Business, sync them back down. If you used a third party tool to migrate profile and files, sync those also to the new profile.</span></span>
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="1fd28-140">Controleren of het apparaat is verbonden met Azure AD</span><span class="sxs-lookup"><span data-stu-id="1fd28-140">Verify the device is connected to Azure AD</span></span>

<span data-ttu-id="1fd28-p106">Als u de synchronisatiestatus wilt controleren, klikt u op de pagina **Toegang tot werk of school** in **Instellingen** in het gebied **Verbonden met** _ \<organization name\> _ om de knoppen **Info** en **Verbinding verbreken** weer te geven. Klik op **Info** om de synchronisatiestatus te bekijken.</span><span class="sxs-lookup"><span data-stu-id="1fd28-p106">To verify your sync status, on the **Access work or school** page in **Settings**, click in the **Connected to** _ \<organization name\> _ area to expose the buttons **Info** and **Disconnect**. Click on **Info** to get your synchronization status.</span></span> 
  
<span data-ttu-id="1fd28-143">Klik op de pagina Synchronisatiestatus op Synchroniseren om het recentste beleid voor het beheren van mobiele apparaten naar de pc te downloaden.</span><span class="sxs-lookup"><span data-stu-id="1fd28-143">On the Sync status page, click Sync to get the latest mobile device management policies onto the PC.</span></span>
  
<span data-ttu-id="1fd28-p107">Als u het Microsoft 365 Business-account wilt gaan gebruiken, gaat u naar de knop **Start** van Windows, klikt u met de rechtermuisknop op uw huidige accountafbeelding en klikt u op **Ander account**. Meld u aan met het e-mailadres en wachtwoord van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="1fd28-p107">To start using the Microsoft 365 Business account, go to the Windows **Start** button, right-click your current account picture and then **Switch account**. Sign in by using your organization email and password.</span></span>
  
![Click Info button to view synchronization status](media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a><span data-ttu-id="1fd28-147">Controleren of het apparaat is bijgewerkt naar Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="1fd28-147">Verify the device is upgraded to Windows 10 Business</span></span>

<span data-ttu-id="1fd28-148">Controleer of voor de Windows 10-apparaten die aan Azure AD zijn gekoppeld, een upgrade naar Windows 10 Business is uitgevoerd, als onderdeel van uw abonnement op Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="1fd28-148">Verify that your Azure AD joined Windows 10 devices were upgraded to Windows 10 Business as part of your Microsoft 365 Business subscription.</span></span>
  
1. <span data-ttu-id="1fd28-149">Ga naar **Instellingen** \> **Systeem** \> **Info**.</span><span class="sxs-lookup"><span data-stu-id="1fd28-149">Go to **Settings** \> **System** \> **About**.</span></span>
    
2. <span data-ttu-id="1fd28-150">Controleer of bij **Editie** **Windows 10 Business** wordt vermeld.</span><span class="sxs-lookup"><span data-stu-id="1fd28-150">Confirm that the **Edition** shows **Windows 10 Business**.</span></span>
    
    ![Verify that Windows edition is Windows 10 Business.](media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a><span data-ttu-id="1fd28-152">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="1fd28-152">Next steps</span></span>

<span data-ttu-id="1fd28-153">Voor het instellen van mobiele apparaten raadpleegt u [Mobiele apparaten instellen voor gebruikers van Microsoft 365 Business](set-up-mobile-devices.md). Voor het instellen van het beveiligingsbeleid voor apparaten of apps raadpleegt u [Microsoft 365 Business beheren](manage.md).</span><span class="sxs-lookup"><span data-stu-id="1fd28-153">To set up your mobile devices, see [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md), To set device protection or app protection policies, see [Manage Microsoft 365 Business](manage.md).</span></span>
  
