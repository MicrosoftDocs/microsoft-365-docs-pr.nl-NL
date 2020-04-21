---
title: Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten
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
description: Meer informatie over het maken, bewerken of verwijderen van een app-beheerbeleid en het beveiligen van werkbestanden op Android- of iOS-apparaten.
ms.openlocfilehash: 0d9e901cac94fe7692ffe705c6b0a51df2bc542f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627429"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="e785c-103">Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten</span><span class="sxs-lookup"><span data-stu-id="e785c-103">Set app protection settings for Android or iOS devices</span></span>

![Banner die https://aka.ms/aboutM365previewwijzen op .](../media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="e785c-105">Beleid voor app-beheer maken</span><span class="sxs-lookup"><span data-stu-id="e785c-105">Create an app management policy</span></span>

1. <span data-ttu-id="e785c-106">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="e785c-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="e785c-107">Kies in het linkernavigatiegebied de optie \> **Apparatenbeleid** \> **Toevoegen**. **Devices**</span><span class="sxs-lookup"><span data-stu-id="e785c-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="e785c-108">Voer in het deelvenster **Beleid toevoegen** een unieke naam in voor dit beleid.</span><span class="sxs-lookup"><span data-stu-id="e785c-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="e785c-109">Kies **onder Beleidstype** **Toepassingsbeheer voor Android** of **Toepassingsbeheer voor iOS,** afhankelijk van welke set beleidsregels u wilt maken.</span><span class="sxs-lookup"><span data-stu-id="e785c-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS**, depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="e785c-110">Vouw **werkbestanden beveiligen uit wanneer apparaten verloren of gestolen zijn** en beheer hoe gebruikers toegang krijgen tot **Office-bestanden op mobiele apparaten.**</span><span class="sxs-lookup"><span data-stu-id="e785c-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices**.</span></span> <span data-ttu-id="e785c-111">Configureer de instellingen zoals u dat wilt.</span><span class="sxs-lookup"><span data-stu-id="e785c-111">Configure the settings how you would like.</span></span> <span data-ttu-id="e785c-112">**Beheren hoe gebruikers toegang krijgen tot Office-bestanden op mobiele apparaten** is standaard **uitgeschakeld,** maar we raden u aan deze **in te** schakelen en de standaardwaarden te accepteren.</span><span class="sxs-lookup"><span data-stu-id="e785c-112">**Manage how users access Office files on mobile devices** is **Off** by default, but we recommend that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="e785c-113">Zie [Beschikbare instellingen voor](#available-settings)meer informatie .</span><span class="sxs-lookup"><span data-stu-id="e785c-113">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="e785c-114">U kunt altijd de koppeling **Standaardwaarden herstellen** gebruiken om terug te keren naar de standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="e785c-114">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="e785c-116">Bepaal nu **Voor wie zijn deze instellingen?**</span><span class="sxs-lookup"><span data-stu-id="e785c-116">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="e785c-117">Als u de standaardbeveiligingsgroep **Alle gebruikers** niet wilt gebruiken, kiest u **Wijzigen**, kiest u de beveiligingsgroepen die deze \> **instellingen**selecteren .</span><span class="sxs-lookup"><span data-stu-id="e785c-117">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups that get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="e785c-118">Kies ten slotte, **Klaar** om het beleid op te slaan en dit toe te wijzen aan apparaten.</span><span class="sxs-lookup"><span data-stu-id="e785c-118">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="e785c-119">Beleid voor app-beheer bewerken</span><span class="sxs-lookup"><span data-stu-id="e785c-119">Edit an app management policy</span></span>

1. <span data-ttu-id="e785c-120">Kies op de **beleidskaart** **Beleid bewerken**.</span><span class="sxs-lookup"><span data-stu-id="e785c-120">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="e785c-121">Kies in het deelvenster **Beleid bewerken** het beleid dat u wilt wijzigen</span><span class="sxs-lookup"><span data-stu-id="e785c-121">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="e785c-122">Kies **Bewerken** naast elke instelling om de waarden in het beleid te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e785c-122">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="e785c-123">Wanneer u een waarde wijzigt, wordt deze automatisch opgeslagen in het beleid.</span><span class="sxs-lookup"><span data-stu-id="e785c-123">When you change a value, it's automatically saved in the policy.</span></span>
    
4. <span data-ttu-id="e785c-124">Wanneer u klaar bent, sluit u het **deelvenster Beleidsvenster bewerken.**</span><span class="sxs-lookup"><span data-stu-id="e785c-124">When you're finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="e785c-125">Beleid voor app-beheer verwijderen</span><span class="sxs-lookup"><span data-stu-id="e785c-125">Delete an app management policy</span></span>

1. <span data-ttu-id="e785c-126">Kies **op** de pagina Beleid een beleid en **verwijder vervolgens .**</span><span class="sxs-lookup"><span data-stu-id="e785c-126">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="e785c-127">Kies **in** het deelvenster Beleid verwijderen de optie **Bevestigen** om het beleid of beleid dat u hebt gekozen te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e785c-127">On the **Delete policy** pane, choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="e785c-128">Beschikbare instellingen</span><span class="sxs-lookup"><span data-stu-id="e785c-128">Available settings</span></span>

<span data-ttu-id="e785c-129">In de volgende tabellen vindt u gedetailleerde informatie over de beschikbare instellingen om werkbestanden op apparaten te beschermen en de instellingen waarmee wordt bepalen hoe gebruikers office-bestanden vanaf hun mobiele apparaten openen.</span><span class="sxs-lookup"><span data-stu-id="e785c-129">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="e785c-130">Zie [Hoe bewaar beveiligingsfuncties in de Microsoft 365 Business Premium-kaart naar Intune-instellingen](map-protection-features-to-intune-settings.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e785c-130">For more information, see [How do protection features in Microsoft 365 Business Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="e785c-131">Instellingen voor het beveiligen van werkbestanden</span><span class="sxs-lookup"><span data-stu-id="e785c-131">Settings that protect work files</span></span>

<span data-ttu-id="e785c-132">De volgende instellingen zijn beschikbaar voor het beveiligen van werkbestanden bij verlies of diefstal van het apparaat van een gebruiker:</span><span class="sxs-lookup"><span data-stu-id="e785c-132">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e785c-133">Instelling</span><span class="sxs-lookup"><span data-stu-id="e785c-133">Setting</span></span>  <br/> |<span data-ttu-id="e785c-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e785c-134">Description</span></span>  <br/> |
|<span data-ttu-id="e785c-135">Werkbestanden van een inactief apparaat verwijderen na zoveel dagen</span><span class="sxs-lookup"><span data-stu-id="e785c-135">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="e785c-136">Als een apparaat niet wordt gebruikt voor het aantal dagen dat u hier opgeeft, worden alle werkbestanden die op het apparaat zijn opgeslagen, automatisch verwijderd.</span><span class="sxs-lookup"><span data-stu-id="e785c-136">If a device isn't used for the number of days that you specify here, any work files stored on the device will be deleted automatically.</span></span>  <br/> |
|<span data-ttu-id="e785c-137">Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="e785c-137">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="e785c-138">Als deze instelling **ingeschakeld**is, is De enige beschikbare opslaglocatie voor werkbestanden OneDrive voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="e785c-138">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="e785c-139">Werkbestanden versleutelen</span><span class="sxs-lookup"><span data-stu-id="e785c-139">Encrypt work files</span></span>  <br/> |<span data-ttu-id="e785c-140">Laat deze instelling **ingeschakeld** zodat werkbestanden worden beveiligd door versleuteling.</span><span class="sxs-lookup"><span data-stu-id="e785c-140">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="e785c-141">Zelfs als het apparaat verloren of gestolen is, kan niemand uw bedrijfsgegevens lezen.</span><span class="sxs-lookup"><span data-stu-id="e785c-141">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="e785c-142">Instellingen die bepalen hoe gebruikers Office-bestanden op mobiele apparaten kunnen openen</span><span class="sxs-lookup"><span data-stu-id="e785c-142">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="e785c-143">De volgende instellingen zijn beschikbaar om te bepalen hoe gebruikers toegang tot Office-werkbestanden hebben:</span><span class="sxs-lookup"><span data-stu-id="e785c-143">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e785c-144">Instelling</span><span class="sxs-lookup"><span data-stu-id="e785c-144">Setting</span></span>  <br/> |<span data-ttu-id="e785c-145">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e785c-145">Description</span></span>  <br/> |
|<span data-ttu-id="e785c-146">Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps</span><span class="sxs-lookup"><span data-stu-id="e785c-146">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="e785c-147">Als deze instelling **Aan** is, moeten gebruikers naast hun gebruikersnaam en wachtwoord ook een andere vorm van verificatie opgeven voordat ze Office-apps op hun mobiele apparaten kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e785c-147">If this setting is **On** users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile devices.</span></span><br/> |
|<span data-ttu-id="e785c-148">Pincode opnieuw instellen wanneer het aanmelden ... keer mislukt</span><span class="sxs-lookup"><span data-stu-id="e785c-148">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="e785c-149">Om te voorkomen dat een niet-geautoriseerde gebruiker een pincode kan raden, wordt de pincode opnieuw ingesteld na het aantal door u opgegeven verkeerde aanmeldpogingen.</span><span class="sxs-lookup"><span data-stu-id="e785c-149">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="e785c-150">Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende</span><span class="sxs-lookup"><span data-stu-id="e785c-150">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="e785c-151">Met deze instelling bepaalt u hoe lang een gebruiker niet kan worden inactief voordat hij zich opnieuw moet aanmelden.</span><span class="sxs-lookup"><span data-stu-id="e785c-151">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="e785c-152">Toegang weigeren tot werkbestanden op jailbroken of geroote apparaten</span><span class="sxs-lookup"><span data-stu-id="e785c-152">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="e785c-p105">Slimme gebruikers hebben mogelijk een jailbroken of geroot apparaat. Dit betekent dat de gebruiker het besturingssysteem kan aanpassen, waardoor het apparaat gevoeliger zou kunnen worden voor malware. Deze apparaten worden geblokkeerd wanneer deze instelling is **ingeschakeld**.  </span><span class="sxs-lookup"><span data-stu-id="e785c-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="e785c-156">Gebruikers mogen geen inhoud uit Office-apps kopiëren naar persoonlijke apps</span><span class="sxs-lookup"><span data-stu-id="e785c-156">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="e785c-157">Dit is standaard toegestaan, maar als de instelling **Aan** is, kan de gebruiker gegevens uit een werkbestand kopiëren naar een persoonlijk bestand.</span><span class="sxs-lookup"><span data-stu-id="e785c-157">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="e785c-158">Als de instelling **Uit** is, kan de gebruiker geen gegevens uit een werkbestand kopiëren naar een persoonlijke app of persoonlijk account.</span><span class="sxs-lookup"><span data-stu-id="e785c-158">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
