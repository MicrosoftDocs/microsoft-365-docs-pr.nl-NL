---
title: Instellingen voor app-beveiliging valideren op Android- of iOS-apparaten
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Meer informatie over het valideren Microsoft 365 Business Premium instellingen voor app-beveiliging op uw Android- of iOS-apparaten.
ms.openlocfilehash: a0a4a6e6cff59f66a506929e97c99d361472a68b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578062"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="1c63b-103">Instellingen voor app-beveiliging valideren op Android- of iOS-apparaten</span><span class="sxs-lookup"><span data-stu-id="1c63b-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="1c63b-104">Volg de instructies in de volgende secties om instellingen voor app-beveiliging te valideren op Android- of iOS-apparaten.</span><span class="sxs-lookup"><span data-stu-id="1c63b-104">Follow the instructions in the following sections to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="android"></a><span data-ttu-id="1c63b-105">Android</span><span class="sxs-lookup"><span data-stu-id="1c63b-105">Android</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="1c63b-106">Controleer of de instellingen voor app-beveiliging werken op gebruikersapparaten</span><span class="sxs-lookup"><span data-stu-id="1c63b-106">Check that the app protection settings are working on user devices</span></span>

<span data-ttu-id="1c63b-107">Nadat u [app-configuraties voor Android-apparaten hebt ingesteld](app-protection-settings-for-android-and-ios.md) om de apps te beschermen, kunt u deze stappen uitvoeren om te controleren of de gekozen instellingen goed werken.</span><span class="sxs-lookup"><span data-stu-id="1c63b-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="1c63b-108">Controleer eerst of het beleid van toepassing is op de app waarin u het gaat valideren.</span><span class="sxs-lookup"><span data-stu-id="1c63b-108">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="1c63b-109">Ga in Microsoft 365 Business Premium [beheercentrum](https://portal.office.com)naar **Beleidsregels** \> **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="1c63b-109">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="1c63b-110">Kies **Toepassingsbeleid voor Android** voor de instellingen die u hebt gemaakt bij de installatie of een ander beleid dat u hebt gemaakt, en controleer of het beleid is afgedwongen voor Outlook, bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="1c63b-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook, for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="1c63b-112">Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps valideren</span><span class="sxs-lookup"><span data-stu-id="1c63b-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="1c63b-113">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Toegangsbeheer Office-documenten**, vouw **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen** uit en zorg ervoor dat **Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps** is ingesteld op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="1c63b-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Zorg ervoor dat de pincode of vingerafdruk vereisen voor toegang tot Office apps is ingesteld op Aan.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="1c63b-115">Open in het Android-apparaat van de gebruiker Outlook en meld u aan met de Microsoft 365 Business Premium referenties van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="1c63b-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="1c63b-116">U wordt ook gevraagd een pincode in te voeren of een vingerafdruk te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1c63b-116">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="1c63b-118">Pincode opnieuw instellen na aantal mislukte pogingen valideren</span><span class="sxs-lookup"><span data-stu-id="1c63b-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="1c63b-119">Kies  in het deelvenster  Beleid bewerken de optie Bewerken naast toegangsbesturingselement voor Office-documenten, vouw Beheren hoe gebruikers toegang hebben tot **Office-bestanden** op mobiele apparaten uit en zorg ervoor dat Pincode opnieuw instellen nadat het aantal mislukte pogingen **is** ingesteld op een nummer. </span><span class="sxs-lookup"><span data-stu-id="1c63b-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="1c63b-120">Dit is standaard 5.</span><span class="sxs-lookup"><span data-stu-id="1c63b-120">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="1c63b-121">Open in het Android-apparaat van de gebruiker Outlook en meld u aan met de Microsoft 365 Business Premium referenties van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="1c63b-121">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="1c63b-122">Voer net zo vaak een onjuiste pincode in als is aangegeven in het beleid.</span><span class="sxs-lookup"><span data-stu-id="1c63b-122">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="1c63b-123">U ziet een prompt met de melding **Pincode pogingslimiet bereikt om** de pincode opnieuw in te stellen.</span><span class="sxs-lookup"><span data-stu-id="1c63b-123">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="1c63b-125">Druk op **Pincode opnieuw instellen**.</span><span class="sxs-lookup"><span data-stu-id="1c63b-125">Press **Reset PIN**.</span></span> <span data-ttu-id="1c63b-126">U wordt gevraagd u aan te melden met de Microsoft 365 Business Premium gebruikersreferenties en vervolgens een nieuwe pincode in te stellen.</span><span class="sxs-lookup"><span data-stu-id="1c63b-126">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="1c63b-127">Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven valideren</span><span class="sxs-lookup"><span data-stu-id="1c63b-127">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="1c63b-128">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Beveiliging bij verlies of diefstal van apparaten**, vouw **Werkbestanden beveiligen bij verlies of diefstal van apparaten** uit en zorg ervoor dat **Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven** is ingesteld op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="1c63b-128">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="1c63b-130">Open in het Android-apparaat van de gebruiker Outlook en meld u aan met de Microsoft 365 Business Premium referenties van de gebruiker en voer een pincode in indien daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="1c63b-130">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="1c63b-131">Open een e-mailbericht met een bijlage en tik op het pictogram Pijl-omlaag naast de gegevens van de bijlage.</span><span class="sxs-lookup"><span data-stu-id="1c63b-131">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="1c63b-133">U ziet Niet **opslaan op apparaat** onder aan het scherm.</span><span class="sxs-lookup"><span data-stu-id="1c63b-133">You'll see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="1c63b-135">Opslaan in OneDrive voor Bedrijven is op dit moment niet ingeschakeld voor Android, zodat u alleen ziet dat lokaal opslaan is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="1c63b-135">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="1c63b-136">Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende een opgegeven tijd valideren</span><span class="sxs-lookup"><span data-stu-id="1c63b-136">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="1c63b-137">Kies  in het deelvenster  Beleid bewerken de optie Bewerken naast toegangsbesturingselement **voor Office-documenten,** vouw Beheren hoe gebruikers toegang hebben tot **Office-bestanden** op mobiele apparaten uit en zorg ervoor dat Gebruikers opnieuw moeten aanmelden nadat **Office-apps** niet actief zijn geweest, is ingesteld op een aantal minuten.</span><span class="sxs-lookup"><span data-stu-id="1c63b-137">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="1c63b-138">Dit is standaard 30 minuten.</span><span class="sxs-lookup"><span data-stu-id="1c63b-138">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="1c63b-139">Open in het Android-apparaat van de gebruiker Outlook en meld u aan met de Microsoft 365 Business Premium referenties van de gebruiker en voer een pincode in indien daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="1c63b-139">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="1c63b-p105">U ziet nu het Postvak IN van Outlook. Gebruik het Android-apparaat minimaal 30 minuten niet (of een andere tijdsduur, langer dan wat u hebt opgegeven in het beleid). Het apparaat wordt waarschijnlijk gedimd.</span><span class="sxs-lookup"><span data-stu-id="1c63b-p105">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="1c63b-143">Access Outlook weer op het Android-apparaat.</span><span class="sxs-lookup"><span data-stu-id="1c63b-143">Access Outlook on the Android device again.</span></span>
    
4. <span data-ttu-id="1c63b-144">U wordt gevraagd uw pincode in te voeren voordat u weer toegang hebt tot Outlook toegang.</span><span class="sxs-lookup"><span data-stu-id="1c63b-144">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="1c63b-145">Werkbestanden beveiligen met versleuteling valideren</span><span class="sxs-lookup"><span data-stu-id="1c63b-145">Validate Protect work files with encryption</span></span>

<span data-ttu-id="1c63b-146">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Beveiliging bij verlies of diefstal van apparaten**, vouw **Werkbestanden beveiligen bij verlies of diefstal van apparaten** uit en zorg ervoor dat **Werkbestanden beveiligen met versleuteling** is ingesteld op **Aan** en **Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven** is ingesteld op **Uit**.</span><span class="sxs-lookup"><span data-stu-id="1c63b-146">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="1c63b-147">Open in het Android-apparaat van de gebruiker Outlook en meld u aan met de Microsoft 365 Business Premium referenties van de gebruiker en voer een pincode in indien daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="1c63b-147">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="1c63b-148">Open een e-mailbericht met een paar bijlagen in het afbeeldingsbestand.</span><span class="sxs-lookup"><span data-stu-id="1c63b-148">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="1c63b-149">Tik op het pictogram Pijl-omlaag naast de informatie van de bijlage om die op te slaan.</span><span class="sxs-lookup"><span data-stu-id="1c63b-149">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="1c63b-p106">U wordt mogelijk gevraagd om toegang toe te staan voor Outlook tot de foto's, media en bestanden op uw apparaat. Tik op **Toestaan**.</span><span class="sxs-lookup"><span data-stu-id="1c63b-p106">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="1c63b-153">Kies onderaan het scherm **Opslaan op apparaat** en open vervolgens de **Galerie** -app.</span><span class="sxs-lookup"><span data-stu-id="1c63b-153">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="1c63b-p107">U ziet een versleutelde foto (of meer als u meerdere bijlagen met afbeeldingsbestanden hebt opgeslagen) in de lijst. Dit wordt mogelijk weergegeven in de lijst met afbeeldingen als een grijs vierkant met een wit uitroepteken binnen een witte cirkel in het midden van het grijze vak.</span><span class="sxs-lookup"><span data-stu-id="1c63b-p107">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a><span data-ttu-id="1c63b-157">iOS</span><span class="sxs-lookup"><span data-stu-id="1c63b-157">iOS</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="1c63b-158">Controleer of de instellingen voor app-beveiliging werken op gebruikersapparaten</span><span class="sxs-lookup"><span data-stu-id="1c63b-158">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="1c63b-159">Nadat u [app-configuraties voor iOS-apparaten hebt ingesteld](app-protection-settings-for-android-and-ios.md) om apps te beschermen, kunt u deze stappen uitvoeren om te controleren of de gekozen instellingen goed werken.</span><span class="sxs-lookup"><span data-stu-id="1c63b-159">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="1c63b-160">Controleer eerst of het beleid van toepassing is op de app waarin u het gaat valideren.</span><span class="sxs-lookup"><span data-stu-id="1c63b-160">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="1c63b-161">Ga in Microsoft 365 Business Premium [beheercentrum](https://portal.office.com)naar **Beleidsregels** \> **bewerken.**</span><span class="sxs-lookup"><span data-stu-id="1c63b-161">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="1c63b-162">Kies **Toepassingsbeleid voor iOS** voor de instellingen die u hebt gemaakt bij de installatie of een ander beleid dat u hebt gemaakt, en controleer of dit is afgedwongen voor Outlook bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="1c63b-162">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="1c63b-164">Een pincode vereisen om toegang te krijgen tot Office-apps valideren</span><span class="sxs-lookup"><span data-stu-id="1c63b-164">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="1c63b-165">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Toegangsbeheer Office-documenten**, vouw **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen** uit en zorg ervoor dat **Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps** is ingesteld op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="1c63b-165">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Zorg ervoor dat de pincode of vingerafdruk vereisen voor toegang tot Office apps is ingesteld op Aan.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="1c63b-167">Open in het iOS-apparaat van de gebruiker Outlook en meld u aan met de Microsoft 365 Business Premium referenties van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="1c63b-167">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="1c63b-168">U wordt ook gevraagd een pincode in te voeren of een vingerafdruk te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1c63b-168">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="1c63b-170">Pincode opnieuw instellen na aantal mislukte pogingen valideren</span><span class="sxs-lookup"><span data-stu-id="1c63b-170">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="1c63b-171">Kies  in het deelvenster  Beleid bewerken de optie Bewerken naast toegangsbesturingselement voor Office-documenten, vouw Beheren hoe gebruikers toegang hebben tot **Office-bestanden** op mobiele apparaten uit en zorg ervoor dat Pincode opnieuw instellen nadat het aantal mislukte pogingen **is** ingesteld op een nummer. </span><span class="sxs-lookup"><span data-stu-id="1c63b-171">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="1c63b-172">Dit is standaard 5.</span><span class="sxs-lookup"><span data-stu-id="1c63b-172">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="1c63b-173">Open in het iOS-apparaat van de gebruiker Outlook en meld u aan met de Microsoft 365 Business Premium referenties van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="1c63b-173">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="1c63b-174">Voer net zo vaak een onjuiste pincode in als is aangegeven in het beleid.</span><span class="sxs-lookup"><span data-stu-id="1c63b-174">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="1c63b-175">U ziet een prompt met de melding **Pincode pogingslimiet bereikt om** de pincode opnieuw in te stellen.</span><span class="sxs-lookup"><span data-stu-id="1c63b-175">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="1c63b-177">Druk op **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c63b-177">Press **OK**.</span></span> <span data-ttu-id="1c63b-178">U wordt gevraagd u aan te melden met de Microsoft 365 Business Premium gebruikersreferenties en vervolgens een nieuwe pincode in te stellen.</span><span class="sxs-lookup"><span data-stu-id="1c63b-178">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="1c63b-179">Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven valideren</span><span class="sxs-lookup"><span data-stu-id="1c63b-179">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="1c63b-180">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Beveiliging bij verlies of diefstal van apparaten**, vouw **Werkbestanden beveiligen bij verlies of diefstal van apparaten** uit en zorg ervoor dat **Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven** is ingesteld op **Aan**.</span><span class="sxs-lookup"><span data-stu-id="1c63b-180">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="1c63b-182">Open in het iOS-apparaat van de gebruiker Outlook en meld u aan met de referenties van de gebruiker Microsoft 365 Business Premium en voer een pincode in indien daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="1c63b-182">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="1c63b-183">Open een e-mailbericht met een bijlage, open de bijlage en kies **Opslaan** onderaan het scherm.</span><span class="sxs-lookup"><span data-stu-id="1c63b-183">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="1c63b-185">U ziet alleen een optie voor OneDrive voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="1c63b-185">You should only see an option for OneDrive for Business.</span></span> <span data-ttu-id="1c63b-186">Zo niet, tikt **u op Account** toevoegen en **selecteert u OneDrive voor Bedrijven** in het scherm Storage **account** toevoegen.</span><span class="sxs-lookup"><span data-stu-id="1c63b-186">If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen.</span></span> <span data-ttu-id="1c63b-187">Geef de eindgebruiker de Microsoft 365 Business Premium om u aan te melden wanneer u daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="1c63b-187">Provide the end user's Microsoft 365 Business Premium to sign in when prompted.</span></span> 
    
    <span data-ttu-id="1c63b-188">Tik op **Opslaan** en selecteer **OneDrive voor Bedrijven**.</span><span class="sxs-lookup"><span data-stu-id="1c63b-188">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="1c63b-189">Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende een opgegeven tijd valideren</span><span class="sxs-lookup"><span data-stu-id="1c63b-189">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="1c63b-190">Kies  in het deelvenster  Beleid bewerken de optie Bewerken naast toegangsbesturingselement **voor Office-documenten,** vouw Beheren hoe gebruikers toegang hebben tot **Office-bestanden** op mobiele apparaten uit en zorg ervoor dat Gebruikers opnieuw moeten aanmelden nadat **Office-apps** niet actief zijn geweest, is ingesteld op een aantal minuten.</span><span class="sxs-lookup"><span data-stu-id="1c63b-190">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="1c63b-191">Dit is standaard 30 minuten.</span><span class="sxs-lookup"><span data-stu-id="1c63b-191">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="1c63b-192">Open in het iOS-apparaat van de gebruiker Outlook en meld u aan met de referenties van de gebruiker Microsoft 365 Business Premium en voer een pincode in indien daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="1c63b-192">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="1c63b-p113">U ziet nu het Postvak IN van Outlook. Gebruik het iOS-apparaat minimaal 30 minuten niet (of een andere tijdsduur, langer dan wat u hebt opgegeven in het beleid). Het apparaat wordt waarschijnlijk gedimd.</span><span class="sxs-lookup"><span data-stu-id="1c63b-p113">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="1c63b-196">Access Outlook weer op het iOS-apparaat.</span><span class="sxs-lookup"><span data-stu-id="1c63b-196">Access Outlook on the iOS device again.</span></span>
    
4. <span data-ttu-id="1c63b-197">U wordt gevraagd uw pincode in te voeren voordat u weer toegang hebt tot Outlook toegang.</span><span class="sxs-lookup"><span data-stu-id="1c63b-197">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="1c63b-198">Werkbestanden beveiligen met versleuteling valideren</span><span class="sxs-lookup"><span data-stu-id="1c63b-198">Validate Protect work files with encryption</span></span>

<span data-ttu-id="1c63b-199">Kies in het deelvenster **Beleid bewerken** de optie **Bewerken** naast **Beveiliging bij verlies of diefstal van apparaten**, vouw **Werkbestanden beveiligen bij verlies of diefstal van apparaten** uit en zorg ervoor dat **Werkbestanden beveiligen met versleuteling** is ingesteld op **Aan** en **Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven** is ingesteld op **Uit**.</span><span class="sxs-lookup"><span data-stu-id="1c63b-199">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="1c63b-200">Open in het iOS-apparaat van de gebruiker Outlook en meld u aan met de referenties van de gebruiker Microsoft 365 Business Premium en voer een pincode in indien daarom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="1c63b-200">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="1c63b-201">Open een e-mailbericht met een paar bijlagen in het afbeeldingsbestand.</span><span class="sxs-lookup"><span data-stu-id="1c63b-201">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="1c63b-202">Tik op de bijlage en tik vervolgens op de optie **Opslaan** eronder.</span><span class="sxs-lookup"><span data-stu-id="1c63b-202">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="1c63b-p114">Open de app **Foto's** vanuit het beginscherm. U ziet een versleutelde foto (of meer als u meerdere bijlagen met afbeeldingsbestanden hebt opgeslagen) die is opgeslagen, maar die wel is versleuteld.</span><span class="sxs-lookup"><span data-stu-id="1c63b-p114">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

