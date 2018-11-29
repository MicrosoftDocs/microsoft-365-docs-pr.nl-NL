---
title: Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Informatie over het maken, bewerken, of verwijderen van een beleid voor het beheer van app en werkbestanden op Android of iOS apparaten te beschermen.
ms.openlocfilehash: ed03227496120369b94bf2396974eebfd7798678
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/28/2018
ms.locfileid: "26983662"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="e1c99-103">Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten</span><span class="sxs-lookup"><span data-stu-id="e1c99-103">Set app protection settings for Android or iOS devices</span></span>

## <a name="create-an-app-management-policy"></a><span data-ttu-id="e1c99-104">Beleid voor app-beheer maken</span><span class="sxs-lookup"><span data-stu-id="e1c99-104">Create an app management policy</span></span>

1. <span data-ttu-id="e1c99-105">Meld u aan bij [Microsoft 365 Business](https://portal.office.com) met globale-beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="e1c99-105">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="e1c99-106">Kies in het beheercentrum op de kaart **Apparaatbeleid** de optie **Beleid toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e1c99-106">In the admin center, on the **Device policies** card, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="e1c99-108">Voer in het deelvenster **Beleid toevoegen** een unieke naam in voor dit beleid.</span><span class="sxs-lookup"><span data-stu-id="e1c99-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="e1c99-109">Kies onder **Type beleid** de optie **Toepassingsbeheer voor Android** of **Toepassingsbeheer voor iOS**, afhankelijk van de set beleidsregels die u wilt maken.</span><span class="sxs-lookup"><span data-stu-id="e1c99-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="e1c99-p101">Vouw **Werkbestanden beveiligen bij verlies of diefstal van apparaten** en **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen** uit \> configureer de instellingen op de gewenste manier. De optie **Beheren hoe gebruikers Office-bestanden op mobiele apparaten openen** is standaard **Uit**. U wordt echter aangeraden de optie in te stellen op **Aan** en de standaardwaarden te accepteren. Zie [Beschikbare instellingen](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e1c99-p101">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like. The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. See [Available settings](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) for more information.</span></span> 
    
    <span data-ttu-id="e1c99-113">U kunt altijd de koppeling **Standaardwaarden herstellen** gebruiken om terug te keren naar de standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="e1c99-113">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="e1c99-p102">Bepaal nu **Voor wie zijn deze instellingen?** Als u niet de standaardbeveiligingsgroep **Alle gebruikers** wilt gebruiken, kiest u **Wijzigen**, zoekt u de beveiligingsgroep die deze instellingen krijgt \> **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="e1c99-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="e1c99-117">Kies ten slotte **Gereed** om het beleid op te slaan en dit toe te wijzen aan apparaten.</span><span class="sxs-lookup"><span data-stu-id="e1c99-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="e1c99-118">Beleid voor app-beheer bewerken</span><span class="sxs-lookup"><span data-stu-id="e1c99-118">Edit an app management policy</span></span>

1. <span data-ttu-id="e1c99-119">Kies op de kaart **beleid** **beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="e1c99-119">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="e1c99-120">Kies in het deelvenster **Beleid bewerken** het beleid dat u wilt wijzigen</span><span class="sxs-lookup"><span data-stu-id="e1c99-120">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="e1c99-p103">Kies **Bewerken** naast elke instelling om de waarden in het beleid te wijzigen. Wanneer u een waarde wijzigt, wordt dit automatisch opgeslagen in het beleid</span><span class="sxs-lookup"><span data-stu-id="e1c99-p103">Choose **Edit** next to each setting to change the values in the policy. When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="e1c99-123">Wanneer u klaar bent, sluit u het deelvenster **Beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="e1c99-123">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="e1c99-124">Beleid voor app-beheer verwijderen</span><span class="sxs-lookup"><span data-stu-id="e1c99-124">Delete an app management policy</span></span>

1. <span data-ttu-id="e1c99-125">Kies op de kaart **Beleid** de optie **Beleid verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="e1c99-125">On the **Policies** card, choose **Delete policy**.</span></span>
    
2. <span data-ttu-id="e1c99-126">Kies het beleid dat u wilt verwijderen in het deelvenster **beleid verwijderen** \> **selecteren**en vervolgens **bevestigen** verwijderen van het beleid of het beleid dat u hebt gekozen.</span><span class="sxs-lookup"><span data-stu-id="e1c99-126">On the **Delete policy** pane, choose the policies you want to delete \> **Select**, then **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="e1c99-127">Beschikbare instellingen</span><span class="sxs-lookup"><span data-stu-id="e1c99-127">Available settings</span></span>

<span data-ttu-id="e1c99-128">De volgende tabellen bevatten gedetailleerde informatie over de beschikbare instellingen voor het beveiligen van werkbestanden op apparaten en de instellingen waarmee wordt bepaald hoe gebruikers toegang hebben tot Office-bestanden op hun mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="e1c99-128">The following tables give detailed information about the available settings to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="e1c99-129">Zie [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) (Hoe beveiligingsfuncties in Microsoft 365 Business zijn toegewezen aan Intune-instellingen) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e1c99-129">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="e1c99-130">Instellingen voor het beveiligen van werkbestanden</span><span class="sxs-lookup"><span data-stu-id="e1c99-130">Settings that protect work files</span></span>

<span data-ttu-id="e1c99-131">De volgende instellingen zijn beschikbaar voor het beveiligen van werkbestanden bij verlies of diefstal van het apparaat van een gebruiker:</span><span class="sxs-lookup"><span data-stu-id="e1c99-131">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e1c99-132">Instelling</span><span class="sxs-lookup"><span data-stu-id="e1c99-132">Setting</span></span>  <br/> |<span data-ttu-id="e1c99-133">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e1c99-133">Description</span></span>  <br/> |
|<span data-ttu-id="e1c99-134">Werkbestanden van een inactief apparaat verwijderen na zoveel dagen</span><span class="sxs-lookup"><span data-stu-id="e1c99-134">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="e1c99-135">Als een apparaat het aantal dagen dat u hier opgeeft, niet wordt gebruikt, worden werkbestanden die op het apparaat zijn opgeslagen, automatisch verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e1c99-135">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="e1c99-136">Afdwingen dat gebruikers alle werkbestanden opslaan in OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="e1c99-136">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="e1c99-137">Als deze instelling is **ingeschakeld**, is OneDrive voor Bedrijven de enige beschikbare opslaglocatie voor werkbestanden.</span><span class="sxs-lookup"><span data-stu-id="e1c99-137">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="e1c99-138">Werkbestanden versleutelen</span><span class="sxs-lookup"><span data-stu-id="e1c99-138">Encrypt work files</span></span>  <br/> |<span data-ttu-id="e1c99-p104">Laat deze instelling **ingeschakeld**, zodat werkbestanden worden beveiligd met versleuteling. Zelfs bij verlies of diefstal van het apparaat kan niemand de bedrijfsgegevens lezen.  </span><span class="sxs-lookup"><span data-stu-id="e1c99-p104">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="e1c99-141">Instellingen waarmee wordt bepaald hoe gebruikers toegang hebben tot Office-bestanden op mobiele apparaten</span><span class="sxs-lookup"><span data-stu-id="e1c99-141">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="e1c99-142">De volgende instellingen zijn beschikbaar om te beheren hoe gebruikers toegang hebben tot Office-werkbestanden:</span><span class="sxs-lookup"><span data-stu-id="e1c99-142">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e1c99-143">Instelling</span><span class="sxs-lookup"><span data-stu-id="e1c99-143">Setting</span></span>  <br/> |<span data-ttu-id="e1c99-144">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e1c99-144">Description</span></span>  <br/> |
|<span data-ttu-id="e1c99-145">Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps</span><span class="sxs-lookup"><span data-stu-id="e1c99-145">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="e1c99-146">Als deze instelling is **ingeschakeld**, moeten gebruikers een extra vorm van verificatie gebruiken, naast het verstrekken van gebruikersnaam en wachtwoord, voordat ze de Office-apps op hun mobiele apparaat kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e1c99-146">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="e1c99-147">Pincode opnieuw instellen wanneer het aanmelden ... keer mislukt</span><span class="sxs-lookup"><span data-stu-id="e1c99-147">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="e1c99-148">Om te voorkomen dat een niet-geautoriseerde gebruiker een pincode kan raden, wordt de pincode opnieuw ingesteld na het aantal door u opgegeven verkeerde aanmeldpogingen.</span><span class="sxs-lookup"><span data-stu-id="e1c99-148">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="e1c99-149">Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende</span><span class="sxs-lookup"><span data-stu-id="e1c99-149">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="e1c99-150">Met deze instelling wordt bepaald hoelang gebruikers inactief kunnen zijn voordat hun wordt gevraagd zich opnieuw aan te melden.</span><span class="sxs-lookup"><span data-stu-id="e1c99-150">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="e1c99-151">Toegang weigeren tot werkbestanden op jailbroken of geroote apparaten</span><span class="sxs-lookup"><span data-stu-id="e1c99-151">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="e1c99-p105">Slimme gebruikers hebben mogelijk een jailbroken of geroot apparaat. Dit betekent dat de gebruiker het besturingssysteem kan aanpassen, waardoor het apparaat gevoeliger kan worden voor malware. Deze apparaten worden geblokkeerd wanneer deze instelling **Aan** is.  </span><span class="sxs-lookup"><span data-stu-id="e1c99-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="e1c99-155">Gebruikers toestaan om inhoud uit Office-apps te kopiëren naar persoonlijke apps</span><span class="sxs-lookup"><span data-stu-id="e1c99-155">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="e1c99-p106">Wij staan toe dat dit standaard, maar als de instelling **ingeschakeld is**, de gebruiker informatie in een werkbestand kan kopiëren naar een bestand met persoonlijke. Als de instelling **uitgeschakeld is**, wordt de gebruiker om gegevens te kopiëren van een werk-rekening in een persoonlijke account of een persoonlijke app kan zijn.</span><span class="sxs-lookup"><span data-stu-id="e1c99-p106">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file. If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.  </span></span><br/> |
   

  

