---
title: Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten
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
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Informatie over het maken, bewerken of verwijderen van een app-beheerbeleid en het beveiligen van werkbestanden op Android-of iOS-apparaten.
ms.openlocfilehash: 914e6848ac46eb334516aadff2827da2b83a38c4
ms.sourcegitcommit: 0fa897d06b664c0ed005817752da1426d4ee17cb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/06/2019
ms.locfileid: "38002080"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="30b80-103">Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten</span><span class="sxs-lookup"><span data-stu-id="30b80-103">Set app protection settings for Android or iOS devices</span></span>

![Banner die naar https://aka.ms/aboutM365previewwijst.](media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="30b80-105">Beleid voor app-beheer maken</span><span class="sxs-lookup"><span data-stu-id="30b80-105">Create an app management policy</span></span>

1. <span data-ttu-id="30b80-106">Ga naar het Admin Center op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="30b80-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="30b80-107">Kies in de linker navigatie \> **apparaatbeleidsregels** \> **toevoegen**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="30b80-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="30b80-108">Voer in het deelvenster **Beleid toevoegen** een unieke naam in voor dit beleid.</span><span class="sxs-lookup"><span data-stu-id="30b80-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="30b80-109">Kies onder **Type beleid** de optie **Toepassingsbeheer voor Android** of **Toepassingsbeheer voor iOS**, afhankelijk van de set beleidsregels die u wilt maken.</span><span class="sxs-lookup"><span data-stu-id="30b80-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="30b80-110">Vouw **werkbestanden beveiligen wanneer apparaten zijn verloren of gestolen** en **beheren hoe gebruikers toegang hebben tot Office-bestanden op mobiele apparaten** \> Configureer de instellingen hoe u wilt.</span><span class="sxs-lookup"><span data-stu-id="30b80-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="30b80-111">De **gebruikers toegang tot Office-bestanden op mobiele apparaten beheren** is standaard **uitgeschakeld** , **maar het is** raadzaam deze functie in te schakelen en de standaardwaarden te accepteren.</span><span class="sxs-lookup"><span data-stu-id="30b80-111">The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="30b80-112">Zie de [beschikbare instellingen](#available-settings) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="30b80-112">See [Available settings](#available-settings)  for more information.</span></span> 
    
    <span data-ttu-id="30b80-113">U kunt altijd de koppeling **Standaardwaarden herstellen** gebruiken om terug te keren naar de standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="30b80-113">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="30b80-p102">Bepaal nu **Voor wie zijn deze instellingen?** Als u niet de standaardbeveiligingsgroep **Alle gebruikers** wilt gebruiken, kiest u **Wijzigen**, zoekt u de beveiligingsgroep die deze instellingen krijgt \> **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="30b80-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="30b80-117">Kies ten slotte **Gereed** om het beleid op te slaan en dit toe te wijzen aan apparaten.</span><span class="sxs-lookup"><span data-stu-id="30b80-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="30b80-118">Beleid voor app-beheer bewerken</span><span class="sxs-lookup"><span data-stu-id="30b80-118">Edit an app management policy</span></span>

1. <span data-ttu-id="30b80-119">Kies **beleid bewerken**op de kaart **beleid** .</span><span class="sxs-lookup"><span data-stu-id="30b80-119">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="30b80-120">Kies in het deelvenster **Beleid bewerken** het beleid dat u wilt wijzigen</span><span class="sxs-lookup"><span data-stu-id="30b80-120">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="30b80-p103">Kies **Bewerken** naast elke instelling om de waarden in het beleid te wijzigen. Wanneer u een waarde wijzigt, wordt dit automatisch opgeslagen in het beleid</span><span class="sxs-lookup"><span data-stu-id="30b80-p103">Choose **Edit** next to each setting to change the values in the policy. When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="30b80-123">Wanneer u klaar bent, sluit u het deelvenster **Beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="30b80-123">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="30b80-124">Beleid voor app-beheer verwijderen</span><span class="sxs-lookup"><span data-stu-id="30b80-124">Delete an app management policy</span></span>

1. <span data-ttu-id="30b80-125">Op de **beleid** pagina, kiest u een beleid en vervolgens **verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="30b80-125">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="30b80-126">Kies in het deelvenster **beleid verwijderen** de optie **bevestigen** om het beleid of beleid te verwijderen dat u hebt gekozen.</span><span class="sxs-lookup"><span data-stu-id="30b80-126">On the **Delete policy** pane choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="30b80-127">Beschikbare instellingen</span><span class="sxs-lookup"><span data-stu-id="30b80-127">Available settings</span></span>

<span data-ttu-id="30b80-128">De volgende tabellen geven gedetailleerde informatie over de beschikbare instellingen voor het beveiligen van werkbestanden op apparaten en de instellingen die bepalen hoe gebruikers toegang hebben tot Office-bestanden vanaf hun mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="30b80-128">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="30b80-129">Zie [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) (Hoe beveiligingsfuncties in Microsoft 365 Business zijn toegewezen aan Intune-instellingen) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="30b80-129">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="30b80-130">Instellingen voor het beveiligen van werkbestanden</span><span class="sxs-lookup"><span data-stu-id="30b80-130">Settings that protect work files</span></span>

<span data-ttu-id="30b80-131">De volgende instellingen zijn beschikbaar voor het beveiligen van werkbestanden bij verlies of diefstal van het apparaat van een gebruiker:</span><span class="sxs-lookup"><span data-stu-id="30b80-131">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="30b80-132">Instelling</span><span class="sxs-lookup"><span data-stu-id="30b80-132">Setting</span></span>  <br/> |<span data-ttu-id="30b80-133">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="30b80-133">Description</span></span>  <br/> |
|<span data-ttu-id="30b80-134">Werkbestanden van een inactief apparaat verwijderen na zoveel dagen</span><span class="sxs-lookup"><span data-stu-id="30b80-134">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="30b80-135">Als een apparaat niet het aantal dagen wordt gebruikt dat u hier opgeeft, worden werkbestanden die op het apparaat zijn opgeslagen, automatisch verwijderd.</span><span class="sxs-lookup"><span data-stu-id="30b80-135">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="30b80-136">Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="30b80-136">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="30b80-137">Als deze instelling is **ingeschakeld**, is OneDrive voor Bedrijven de enige beschikbare opslaglocatie voor werkbestanden.</span><span class="sxs-lookup"><span data-stu-id="30b80-137">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="30b80-138">Werkbestanden versleutelen</span><span class="sxs-lookup"><span data-stu-id="30b80-138">Encrypt work files</span></span>  <br/> |<span data-ttu-id="30b80-p104">Laat deze instelling **ingeschakeld** zodat werkbestanden worden beveiligd door versleuteling. Zelfs bij verlies of diefstal van het apparaat kan niemand de bedrijfsgegevens lezen.  </span><span class="sxs-lookup"><span data-stu-id="30b80-p104">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="30b80-141">Instellingen waarmee wordt bepaald hoe gebruikers toegang hebben tot Office-bestanden op mobiele apparaten</span><span class="sxs-lookup"><span data-stu-id="30b80-141">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="30b80-142">De volgende instellingen zijn beschikbaar om te bepalen hoe gebruikers toegang tot Office-werkbestanden hebben:</span><span class="sxs-lookup"><span data-stu-id="30b80-142">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="30b80-143">Instelling</span><span class="sxs-lookup"><span data-stu-id="30b80-143">Setting</span></span>  <br/> |<span data-ttu-id="30b80-144">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="30b80-144">Description</span></span>  <br/> |
|<span data-ttu-id="30b80-145">Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps</span><span class="sxs-lookup"><span data-stu-id="30b80-145">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="30b80-146">Als deze instelling is **ingeschakeld**, moeten gebruikers een extra vorm van verificatie gebruiken, naast het verstrekken van gebruikersnaam en wachtwoord, voordat ze de Office-apps op hun mobiele apparaat kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="30b80-146">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="30b80-147">Pincode opnieuw instellen wanneer het aanmelden ... keer mislukt</span><span class="sxs-lookup"><span data-stu-id="30b80-147">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="30b80-148">Om te voorkomen dat een niet-geautoriseerde gebruiker een pincode kan raden, wordt de pincode opnieuw ingesteld na het aantal door u opgegeven verkeerde aanmeldpogingen.</span><span class="sxs-lookup"><span data-stu-id="30b80-148">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="30b80-149">Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende</span><span class="sxs-lookup"><span data-stu-id="30b80-149">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="30b80-150">Met deze instelling wordt bepaald hoelang gebruikers inactief kunnen zijn voordat hun wordt gevraagd zich opnieuw aan te melden.</span><span class="sxs-lookup"><span data-stu-id="30b80-150">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="30b80-151">Toegang weigeren tot werkbestanden op jailbroken of geroote apparaten</span><span class="sxs-lookup"><span data-stu-id="30b80-151">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="30b80-p105">Slimme gebruikers hebben mogelijk een jailbroken of geroot apparaat. Dit betekent dat de gebruiker het besturingssysteem kan aanpassen, waardoor het apparaat gevoeliger zou kunnen worden voor malware. Deze apparaten worden geblokkeerd wanneer deze instelling is **ingeschakeld**.  </span><span class="sxs-lookup"><span data-stu-id="30b80-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="30b80-155">Gebruikers toestaan om inhoud uit Office-apps te kopiëren naar persoonlijke apps</span><span class="sxs-lookup"><span data-stu-id="30b80-155">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="30b80-156">Dit is standaard toegestaan, maar als de instelling **Aan** is, kan de gebruiker gegevens uit een werkbestand kopiëren naar een persoonlijk bestand.</span><span class="sxs-lookup"><span data-stu-id="30b80-156">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="30b80-157">Als de instelling **Uit** is, kan de gebruiker geen gegevens uit een werkbestand kopiëren naar een persoonlijke app of persoonlijk account.</span><span class="sxs-lookup"><span data-stu-id="30b80-157">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
   

  

