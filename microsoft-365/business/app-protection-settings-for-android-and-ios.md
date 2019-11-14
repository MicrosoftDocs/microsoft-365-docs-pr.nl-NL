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
ms.openlocfilehash: 2eebe5b603837d7e4125ab7e88b61792ca3a1e5d
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/14/2019
ms.locfileid: "38321840"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="5ecde-103">Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten</span><span class="sxs-lookup"><span data-stu-id="5ecde-103">Set app protection settings for Android or iOS devices</span></span>

![Banner die naar https://aka.ms/aboutM365previewwijst.](media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="5ecde-105">Beleid voor app-beheer maken</span><span class="sxs-lookup"><span data-stu-id="5ecde-105">Create an app management policy</span></span>

1. <span data-ttu-id="5ecde-106">Ga naar het Admin Center op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="5ecde-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="5ecde-107">Kies in de linker navigatie \> **apparaatbeleidsregels** \> **toevoegen**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5ecde-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="5ecde-108">Voer in het deelvenster **Beleid toevoegen** een unieke naam in voor dit beleid.</span><span class="sxs-lookup"><span data-stu-id="5ecde-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="5ecde-109">Onder **beleidstype**, kiest u **Toepassingsbeheer voor Android** of **Toepassingsbeheer voor IOS**, afhankelijk van welke set beleidsregels die u wilt maken.</span><span class="sxs-lookup"><span data-stu-id="5ecde-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS**, depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="5ecde-110">Vouw **werkbestanden beveiligen wanneer apparaten zijn verloren of gestolen** en **beheren hoe gebruikers toegang hebben tot Office-bestanden op mobiele apparaten**.</span><span class="sxs-lookup"><span data-stu-id="5ecde-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices**.</span></span> <span data-ttu-id="5ecde-111">Configureer de instellingen zoals u dat wilt.</span><span class="sxs-lookup"><span data-stu-id="5ecde-111">Configure the settings how you would like.</span></span> <span data-ttu-id="5ecde-112">**Beheren hoe gebruikers toegang hebben tot Office-bestanden op mobiele apparaten** is standaard **uitgeschakeld** , maar we raden **u aan deze** in te schakelen en de standaardwaarden te accepteren.</span><span class="sxs-lookup"><span data-stu-id="5ecde-112">**Manage how users access Office files on mobile devices** is **Off** by default, but we recommend that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="5ecde-113">Zie voor meer informatie, [beschikbare instellingen](#available-settings).</span><span class="sxs-lookup"><span data-stu-id="5ecde-113">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="5ecde-114">U kunt altijd de koppeling **Standaardwaarden herstellen** gebruiken om terug te keren naar de standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="5ecde-114">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="5ecde-116">Bepaal nu **Voor wie zijn deze instellingen?**</span><span class="sxs-lookup"><span data-stu-id="5ecde-116">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="5ecde-117">Als u de standaard beveiligingsgroep **alle gebruikers** niet wilt gebruiken, kiest u **wijzigen**, kiest u de beveiligingsgroepen die deze instellingen \> krijgen **selecteren**.</span><span class="sxs-lookup"><span data-stu-id="5ecde-117">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups that get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="5ecde-118">Kies ten slotte, **Klaar** om het beleid op te slaan en dit toe te wijzen aan apparaten.</span><span class="sxs-lookup"><span data-stu-id="5ecde-118">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="5ecde-119">Beleid voor app-beheer bewerken</span><span class="sxs-lookup"><span data-stu-id="5ecde-119">Edit an app management policy</span></span>

1. <span data-ttu-id="5ecde-120">Kies **beleid bewerken**op de kaart **beleid** .</span><span class="sxs-lookup"><span data-stu-id="5ecde-120">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="5ecde-121">Kies in het deelvenster **Beleid bewerken** het beleid dat u wilt wijzigen</span><span class="sxs-lookup"><span data-stu-id="5ecde-121">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="5ecde-122">Kies **Bewerken** naast elke instelling om de waarden in het beleid te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5ecde-122">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="5ecde-123">Wanneer u een waarde wijzigt, wordt deze automatisch opgeslagen in het beleid.</span><span class="sxs-lookup"><span data-stu-id="5ecde-123">When you change a value, it's automatically saved in the policy.</span></span>
    
4. <span data-ttu-id="5ecde-124">Wanneer u klaar bent, sluit u het deelvenster **beleid bewerken** .</span><span class="sxs-lookup"><span data-stu-id="5ecde-124">When you're finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="5ecde-125">Beleid voor app-beheer verwijderen</span><span class="sxs-lookup"><span data-stu-id="5ecde-125">Delete an app management policy</span></span>

1. <span data-ttu-id="5ecde-126">Op de **beleid** pagina, kiest u een beleid en vervolgens **verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="5ecde-126">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="5ecde-127">Kies in het deelvenster **beleid verwijderen** de optie **bevestigen** om het beleid of beleid te verwijderen dat u hebt gekozen.</span><span class="sxs-lookup"><span data-stu-id="5ecde-127">On the **Delete policy** pane, choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="5ecde-128">Beschikbare instellingen</span><span class="sxs-lookup"><span data-stu-id="5ecde-128">Available settings</span></span>

<span data-ttu-id="5ecde-129">De volgende tabellen geven gedetailleerde informatie over de beschikbare instellingen voor het beveiligen van werkbestanden op apparaten en de instellingen die bepalen hoe gebruikers toegang hebben tot Office-bestanden vanaf hun mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="5ecde-129">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="5ecde-130">Zie [Hoe beveiligingsfuncties in Microsoft 365 Business zijn toegewezen aan Intune-instellingen](map-protection-features-to-intune-settings.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5ecde-130">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="5ecde-131">Instellingen voor het beveiligen van werkbestanden</span><span class="sxs-lookup"><span data-stu-id="5ecde-131">Settings that protect work files</span></span>

<span data-ttu-id="5ecde-132">De volgende instellingen zijn beschikbaar voor het beveiligen van werkbestanden bij verlies of diefstal van het apparaat van een gebruiker:</span><span class="sxs-lookup"><span data-stu-id="5ecde-132">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5ecde-133">Instelling</span><span class="sxs-lookup"><span data-stu-id="5ecde-133">Setting</span></span>  <br/> |<span data-ttu-id="5ecde-134">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="5ecde-134">Description</span></span>  <br/> |
|<span data-ttu-id="5ecde-135">Werkbestanden van een inactief apparaat verwijderen na zoveel dagen</span><span class="sxs-lookup"><span data-stu-id="5ecde-135">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="5ecde-136">Als een apparaat niet wordt gebruikt voor het aantal dagen dat u hier opgeeft, worden alle werkbestanden die op het apparaat zijn opgeslagen, automatisch verwijderd.</span><span class="sxs-lookup"><span data-stu-id="5ecde-136">If a device isn't used for the number of days that you specify here, any work files stored on the device will be deleted automatically.</span></span>  <br/> |
|<span data-ttu-id="5ecde-137">Gebruikers dwingen om alle werkbestanden op te slaan in OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="5ecde-137">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="5ecde-138">Als deze instelling is **ingeschakeld**, is de enige beschikbare opslaglocatie voor werkbestanden OneDrive voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="5ecde-138">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="5ecde-139">Werkbestanden versleutelen</span><span class="sxs-lookup"><span data-stu-id="5ecde-139">Encrypt work files</span></span>  <br/> |<span data-ttu-id="5ecde-140">Laat deze instelling **ingeschakeld** zodat werkbestanden worden beveiligd door versleuteling.</span><span class="sxs-lookup"><span data-stu-id="5ecde-140">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="5ecde-141">Zelfs als het apparaat is kwijtgeraakt of gestolen, kan niemand uw bedrijfsgegevens lezen.</span><span class="sxs-lookup"><span data-stu-id="5ecde-141">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="5ecde-142">Instellingen die bepalen hoe gebruikers Office-bestanden op mobiele apparaten kunnen openen</span><span class="sxs-lookup"><span data-stu-id="5ecde-142">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="5ecde-143">De volgende instellingen zijn beschikbaar om te bepalen hoe gebruikers toegang tot Office-werkbestanden hebben:</span><span class="sxs-lookup"><span data-stu-id="5ecde-143">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5ecde-144">Instelling</span><span class="sxs-lookup"><span data-stu-id="5ecde-144">Setting</span></span>  <br/> |<span data-ttu-id="5ecde-145">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="5ecde-145">Description</span></span>  <br/> |
|<span data-ttu-id="5ecde-146">Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps</span><span class="sxs-lookup"><span data-stu-id="5ecde-146">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="5ecde-147">Als deze instelling **op** gebruikers moet bieden een andere vorm van verificatie, naast hun gebruikersnaam en wachtwoord, voordat ze Office-apps op hun mobiele apparaten kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5ecde-147">If this setting is **On** users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile devices.</span></span><br/> |
|<span data-ttu-id="5ecde-148">Pincode opnieuw instellen wanneer het aanmelden ... keer mislukt</span><span class="sxs-lookup"><span data-stu-id="5ecde-148">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="5ecde-149">Om te voorkomen dat een niet-geautoriseerde gebruiker een pincode kan raden, wordt de pincode opnieuw ingesteld na het aantal door u opgegeven verkeerde aanmeldpogingen.</span><span class="sxs-lookup"><span data-stu-id="5ecde-149">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="5ecde-150">Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende</span><span class="sxs-lookup"><span data-stu-id="5ecde-150">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="5ecde-151">Deze instelling bepaalt hoe lang een gebruiker inactief kan zijn voordat deze wordt gevraagd om opnieuw aan te melden.</span><span class="sxs-lookup"><span data-stu-id="5ecde-151">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="5ecde-152">Toegang weigeren tot werkbestanden op jailbroken of geroote apparaten</span><span class="sxs-lookup"><span data-stu-id="5ecde-152">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="5ecde-p105">Slimme gebruikers hebben mogelijk een jailbroken of geroot apparaat. Dit betekent dat de gebruiker het besturingssysteem kan aanpassen, waardoor het apparaat gevoeliger zou kunnen worden voor malware. Deze apparaten worden geblokkeerd wanneer deze instelling is **ingeschakeld**.  </span><span class="sxs-lookup"><span data-stu-id="5ecde-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="5ecde-156">Gebruikers toestaan om inhoud uit Office-apps te kopiëren naar persoonlijke apps</span><span class="sxs-lookup"><span data-stu-id="5ecde-156">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="5ecde-157">Dit is standaard toegestaan, maar als de instelling **Aan** is, kan de gebruiker gegevens uit een werkbestand kopiëren naar een persoonlijk bestand.</span><span class="sxs-lookup"><span data-stu-id="5ecde-157">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="5ecde-158">Als de instelling **Uit** is, kan de gebruiker geen gegevens uit een werkbestand kopiëren naar een persoonlijke app of persoonlijk account.</span><span class="sxs-lookup"><span data-stu-id="5ecde-158">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
