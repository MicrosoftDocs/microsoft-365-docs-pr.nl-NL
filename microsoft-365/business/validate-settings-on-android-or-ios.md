---
title: Beveiligingsinstellingen app op Android of iOS apparaten valideren
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
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: 'Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.  '
ms.openlocfilehash: d4ed70290b21b40ca9ecd5601954c429a27dc528
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072365"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="20262-103">Beveiligingsinstellingen app op Android of iOS apparaten valideren</span><span class="sxs-lookup"><span data-stu-id="20262-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="20262-104">Volg de instructies op de tabbladen voor het valideren van beveiligingsinstellingen app op Android of iOS apparaten.</span><span class="sxs-lookup"><span data-stu-id="20262-104">Follow the instructions in the tabs to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="androidtab"></a>[<span data-ttu-id="20262-105">Android</span><span class="sxs-lookup"><span data-stu-id="20262-105">Android</span></span>](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="20262-106">Controleer of de instellingen voor app-beveiliging werken op gebruikersapparaten</span><span class="sxs-lookup"><span data-stu-id="20262-106">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="20262-107">Nadat u [app-configuraties voor Android-apparaten hebt ingesteld](app-protection-settings-for-android-and-ios.md) om de apps te beschermen, kunt u deze stappen uitvoeren om te controleren of de gekozen instellingen goed werken.</span><span class="sxs-lookup"><span data-stu-id="20262-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="20262-108">Controleer eerst of het beleid van toepassing is op de app waarin u deze wilt valideren.</span><span class="sxs-lookup"><span data-stu-id="20262-108">First, make sure that the policy applies to the app in which you are going to validate it.</span></span>
  
1. <span data-ttu-id="20262-109">Ga in het Microsoft 365 Business-[beheercentrum](https://portal.office.com) naar **Beleid** \> **Beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="20262-109">In the Microsoft 365 Business [admin center](https://portal.office.com) go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="20262-110">Kies **Toepassingenbeleid voor Android** voor de instellingen die u tijdens de installatie hebt gemaakt of een ander beleid dat u hebt gemaakt en controleer of dit bijvoorbeeld wordt afgedwongen voor Outlook.</span><span class="sxs-lookup"><span data-stu-id="20262-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it is enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="20262-112">Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps valideren</span><span class="sxs-lookup"><span data-stu-id="20262-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="20262-113">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Toegangsbeheer Office-documenten**, vouw **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen** uit en zorg ervoor dat **Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps** is ingesteld op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="20262-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="20262-115">Open Outlook op het Android-apparaat van de gebruiker en meld u aan met de Microsoft 365 Business-referenties van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="20262-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="20262-116">U wordt ook gevraagd om een pincode in te voeren of een vingerafdruk te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="20262-116">You will also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="20262-118">Pincode opnieuw instellen na aantal mislukte pogingen valideren</span><span class="sxs-lookup"><span data-stu-id="20262-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="20262-119">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Toegangsbeheer Office-documenten**, vouw **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen** uit en zorg ervoor dat **Pincode opnieuw instellen na aantal mislukte pogingen** is ingesteld op een getal. Standaard is dit 5.</span><span class="sxs-lookup"><span data-stu-id="20262-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number - this is 5 by default.</span></span> 
  
1. <span data-ttu-id="20262-120">Open Outlook op het Android-apparaat van de gebruiker en meld u aan met de Microsoft 365 Business-referenties van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="20262-120">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="20262-p101">Voer net zo vaak een onjuiste pincode in als is aangegeven in het beleid. U ziet de melding **Limiet aantal pogingen voor pincode invoeren bereikt** voor het opnieuw instellen van de pincode.</span><span class="sxs-lookup"><span data-stu-id="20262-p101">Enter an incorrect PIN as many times as specified by the policy. You will see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="20262-p102">Druk op **Pincode opnieuw instellen**. U wordt gevraagd u aan te melden met de Microsoft 365 Business-referenties van de gebruiker en vervolgens een nieuwe pincode in te stellen.</span><span class="sxs-lookup"><span data-stu-id="20262-p102">Press **Reset PIN**. You will be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="20262-126">Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven valideren</span><span class="sxs-lookup"><span data-stu-id="20262-126">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="20262-127">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Beveiliging bij verlies of diefstal van apparaten**, vouw **Werkbestanden beveiligen bij verlies of diefstal van apparaten** uit en zorg ervoor dat **Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven** is ingesteld op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="20262-127">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="20262-129">Open Outlook op het Android-apparaat van de gebruiker, meld u aan met de Microsoft 365 Business-referenties van de gebruiker en voer een pincode in als u hierom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="20262-129">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="20262-130">Open een e-mailbericht met een bijlage en tik op het pictogram Pijl-omlaag naast de gegevens van de bijlage.</span><span class="sxs-lookup"><span data-stu-id="20262-130">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="20262-132">U ziet **Kan niet op apparaat worden opgeslagen** aan de onderkant van het scherm.</span><span class="sxs-lookup"><span data-stu-id="20262-132">You will see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="20262-134">Opslaan in OneDrive voor Bedrijven is op dit moment niet ingeschakeld voor Android, zodat u alleen ziet dat lokaal opslaan is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="20262-134">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="20262-135">Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende een opgegeven tijd valideren</span><span class="sxs-lookup"><span data-stu-id="20262-135">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="20262-136">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Toegangsbeheer Office-documenten**, vouw **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen** uit en zorg ervoor dat **Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende** is ingesteld op een bepaald aantal minuten. Standaard is dit 30 minuten.</span><span class="sxs-lookup"><span data-stu-id="20262-136">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes - this is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="20262-137">Open Outlook op het Android-apparaat van de gebruiker, meld u aan met de Microsoft 365 Business-referenties van de gebruiker en voer een pincode in als u hierom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="20262-137">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="20262-p103">U ziet nu het Postvak IN van Outlook. Gebruik het Android-apparaat minimaal 30 minuten niet (of een andere tijdsduur, langer dan wat u hebt opgegeven in het beleid). Het apparaat wordt waarschijnlijk gedimd.</span><span class="sxs-lookup"><span data-stu-id="20262-p103">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="20262-141">Open Outlook opnieuw op het Android-apparaat.</span><span class="sxs-lookup"><span data-stu-id="20262-141">Re-access Outlook on the Android device.</span></span>
    
4. <span data-ttu-id="20262-142">U wordt gevraagd om uw pincode in te voeren voordat u Outlook opnieuw kunt openen.</span><span class="sxs-lookup"><span data-stu-id="20262-142">You will be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="20262-143">Werkbestanden beveiligen met versleuteling valideren</span><span class="sxs-lookup"><span data-stu-id="20262-143">Validate Protect work files with encryption</span></span>

<span data-ttu-id="20262-144">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Beveiliging bij verlies of diefstal van apparaten**, vouw **Werkbestanden beveiligen bij verlies of diefstal van apparaten** uit en zorg ervoor dat **Werkbestanden beveiligen met versleuteling** is ingesteld op **Aan** en **Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven** is ingesteld op **Uit**.</span><span class="sxs-lookup"><span data-stu-id="20262-144">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="20262-145">Open Outlook op het Android-apparaat van de gebruiker, meld u aan met de Microsoft 365 Business-referenties van de gebruiker en voer een pincode in als u hierom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="20262-145">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="20262-146">Open een e-mailbericht met een paar afbeeldingsbestanden als bijlagen.</span><span class="sxs-lookup"><span data-stu-id="20262-146">Open an email which contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="20262-147">Tik op het pictogram Pijl-omlaag naast de informatie van de bijlage om die op te slaan.</span><span class="sxs-lookup"><span data-stu-id="20262-147">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="20262-p104">U wordt mogelijk gevraagd om toegang toe te staan voor Outlook tot de foto's, media en bestanden op uw apparaat. Tik op **Toestaan**.</span><span class="sxs-lookup"><span data-stu-id="20262-p104">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="20262-151">Kies onderaan het scherm **Opslaan op apparaat** en open vervolgens de **Galerie** -app.</span><span class="sxs-lookup"><span data-stu-id="20262-151">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="20262-p105">U ziet een versleutelde foto (of meer als u meerdere bijlagen met afbeeldingsbestanden hebt opgeslagen) in de lijst. Dit wordt mogelijk weergegeven in de lijst met afbeeldingen als een grijs vierkant met een wit uitroepteken binnen een witte cirkel in het midden van het grijze vak.</span><span class="sxs-lookup"><span data-stu-id="20262-p105">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="iostab"></a>[<span data-ttu-id="20262-155">iOS</span><span class="sxs-lookup"><span data-stu-id="20262-155">iOS</span></span>](#tab/)
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="20262-156">Controleer of de instellingen voor app-beveiliging werken op gebruikersapparaten</span><span class="sxs-lookup"><span data-stu-id="20262-156">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="20262-157">Nadat u [app-configuraties voor iOS-apparaten hebt ingesteld](app-protection-settings-for-android-and-ios.md) om apps te beschermen, kunt u deze stappen uitvoeren om te controleren of de gekozen instellingen goed werken.</span><span class="sxs-lookup"><span data-stu-id="20262-157">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="20262-158">Controleer eerst of het beleid van toepassing is op de app waarin u deze wilt valideren.</span><span class="sxs-lookup"><span data-stu-id="20262-158">First, make sure that the policy applies to the app in which you are going to validate it.</span></span>
  
1. <span data-ttu-id="20262-159">Ga in het Microsoft 365 Business-[beheercentrum](https://portal.office.com) naar **Beleid** \> **Beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="20262-159">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="20262-160">Kies **Toepassingenbeleid voor iOS** voor de instellingen die u tijdens de installatie hebt gemaakt of een ander beleid dat u hebt gemaakt en controleer of dit bijvoorbeeld wordt afgedwongen voor Outlook.</span><span class="sxs-lookup"><span data-stu-id="20262-160">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it is enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="20262-162">Een pincode vereisen om toegang te krijgen tot Office-apps valideren</span><span class="sxs-lookup"><span data-stu-id="20262-162">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="20262-163">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Toegangsbeheer Office-documenten**, vouw **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen** uit en zorg ervoor dat **Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps** is ingesteld op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="20262-163">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="20262-165">Open Outlook op het iOS-apparaat van de gebruiker en meld u aan met de Microsoft 365 Business-referenties van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="20262-165">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="20262-166">U wordt ook gevraagd om een pincode in te voeren of een vingerafdruk te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="20262-166">You will also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="20262-168">Pincode opnieuw instellen na aantal mislukte pogingen valideren</span><span class="sxs-lookup"><span data-stu-id="20262-168">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="20262-169">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Toegangsbeheer Office-documenten**, vouw **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen** uit en zorg ervoor dat **Pincode opnieuw instellen na aantal mislukte pogingen** is ingesteld op een getal. Standaard is dit 5.</span><span class="sxs-lookup"><span data-stu-id="20262-169">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number - this is 5 by default.</span></span> 
  
1. <span data-ttu-id="20262-170">Open Outlook op het iOS-apparaat van de gebruiker en meld u aan met de Microsoft 365 Business-referenties van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="20262-170">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="20262-p106">Voer net zo vaak een onjuiste pincode in als is aangegeven in het beleid. U ziet de melding **Limiet aantal pogingen voor pincode invoeren bereikt** voor het opnieuw instellen van de pincode.</span><span class="sxs-lookup"><span data-stu-id="20262-p106">Enter an incorrect PIN as many times as specified by the policy. You will see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="20262-p107">Druk op **OK**. U wordt gevraagd u aan te melden met de Microsoft 365 Business-referenties van de gebruiker en vervolgens een nieuwe pincode in te stellen.</span><span class="sxs-lookup"><span data-stu-id="20262-p107">Press **OK**. You will be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="20262-176">Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven valideren</span><span class="sxs-lookup"><span data-stu-id="20262-176">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="20262-177">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Beveiliging bij verlies of diefstal van apparaten**, vouw **Werkbestanden beveiligen bij verlies of diefstal van apparaten** uit en zorg ervoor dat **Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven** is ingesteld op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="20262-177">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="20262-179">Open Outlook op het iOS-apparaat van de gebruiker, meld u aan met de Microsoft 365 Business-referenties van de gebruiker en voer een pincode in als u hierom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="20262-179">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="20262-180">Open een e-mailbericht met een bijlage, open de bijlage en kies **Opslaan** onderaan het scherm.</span><span class="sxs-lookup"><span data-stu-id="20262-180">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="20262-p108">U ziet alleen een optie voor OneDrive voor Bedrijven. Als dit niet het geval is, tikt u op **Account toevoegen** en selecteert u **OneDrive voor Bedrijven** in het scherm **Opslagaccount toevoegen**. Geef het Microsoft 365 Business van de eindgebruiker op om u aan te melden wanneer dit wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="20262-p108">You should only see an option for OneDrive for Business. If not If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen. Provide the end user's Microsoft 365 Business to sign in when prompted.</span></span> 
    
    <span data-ttu-id="20262-185">Tik op **Opslaan** en selecteer **OneDrive voor Bedrijven**.</span><span class="sxs-lookup"><span data-stu-id="20262-185">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="20262-186">Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende een opgegeven tijd valideren</span><span class="sxs-lookup"><span data-stu-id="20262-186">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="20262-187">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Toegangsbeheer Office-documenten**, vouw **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen** uit en zorg ervoor dat **Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende** is ingesteld op een bepaald aantal minuten. Standaard is dit 30 minuten.</span><span class="sxs-lookup"><span data-stu-id="20262-187">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes - this is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="20262-188">Open Outlook op het iOS-apparaat van de gebruiker, meld u aan met de Microsoft 365 Business-referenties van de gebruiker en voer een pincode in als u hierom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="20262-188">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="20262-p109">U ziet nu het Postvak IN van Outlook. Gebruik het iOS-apparaat minimaal 30 minuten niet (of een andere tijdsduur, langer dan wat u hebt opgegeven in het beleid). Het apparaat wordt waarschijnlijk gedimd.</span><span class="sxs-lookup"><span data-stu-id="20262-p109">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="20262-192">Open Outlook opnieuw op het iOS-apparaat.</span><span class="sxs-lookup"><span data-stu-id="20262-192">Re-access Outlook on the iOS device.</span></span>
    
4. <span data-ttu-id="20262-193">U wordt gevraagd om uw pincode in te voeren voordat u Outlook opnieuw kunt openen.</span><span class="sxs-lookup"><span data-stu-id="20262-193">You will be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="20262-194">Werkbestanden beveiligen met versleuteling valideren</span><span class="sxs-lookup"><span data-stu-id="20262-194">Validate Protect work files with encryption</span></span>

<span data-ttu-id="20262-195">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Beveiliging bij verlies of diefstal van apparaten**, vouw **Werkbestanden beveiligen bij verlies of diefstal van apparaten** uit en zorg ervoor dat **Werkbestanden beveiligen met versleuteling** is ingesteld op **Aan** en **Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven** is ingesteld op **Uit**.</span><span class="sxs-lookup"><span data-stu-id="20262-195">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="20262-196">Open Outlook op het iOS-apparaat van de gebruiker, meld u aan met de Microsoft 365 Business-referenties van de gebruiker en voer een pincode in als u hierom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="20262-196">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="20262-197">Open een e-mailbericht met een paar afbeeldingsbestanden als bijlagen.</span><span class="sxs-lookup"><span data-stu-id="20262-197">Open an email which contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="20262-198">Tik op de bijlage en tik vervolgens op de optie **Opslaan** eronder.</span><span class="sxs-lookup"><span data-stu-id="20262-198">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="20262-p110">Open de app **Foto's** vanuit het beginscherm. U ziet een versleutelde foto (of meer als u meerdere bijlagen met afbeeldingsbestanden hebt opgeslagen) die is opgeslagen, maar die wel is versleuteld.</span><span class="sxs-lookup"><span data-stu-id="20262-p110">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

