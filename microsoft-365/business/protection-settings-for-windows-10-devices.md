---
title: Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Informatie over het maken van een beleid voor het beheer van app en werkbestanden op Windows 10-apparaten te beschermen.
ms.openlocfilehash: 289c6a74f6ccb53f6a833612a7b4a5bcddd3ea56
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278161"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="e6e3a-103">Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="e6e3a-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="e6e3a-104">Beleid voor app-beheer maken voor Windows 10</span><span class="sxs-lookup"><span data-stu-id="e6e3a-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="e6e3a-105">Als uw gebruikers persoonlijke Windows 10-apparaten gebruiken voor hun werk, kunt u de gegevens op die apparaten ook beschermen.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="e6e3a-106">Het aanmelden bij [admin center](https://go.microsoft.com/fwlink/p/?linkid=837890) met de globale Administrator-referenties.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-106">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=837890) with global admin credentials.</span></span> <span data-ttu-id="e6e3a-107">Kies de tegel **Beheerder** om naar het beheercentrum te gaan.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-107">Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="e6e3a-108">Kies op de Linkernavigatie **apparaten** \> **beleid** \> **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-108">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="e6e3a-109">Voer in het deelvenster **Beleid toevoegen** een unieke naam in voor dit beleid.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-109">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="e6e3a-110">Kies onder **Type beleid** de optie **Toepassingsbeheer voor Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-110">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="e6e3a-111">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-111">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="e6e3a-112">De optie **Werkbestanden versleutelen** is automatisch ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-112">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="e6e3a-113">Stel **Voorkomen dat gebruikers bedrijfsgegevens kopiëren naar persoonlijke bestanden en afdwingen dat werkbestanden worden opgeslagen in OneDrive voor Bedrijven** in op **Aan** als u niet wilt dat de gebruikers werkbestanden opslaan op hun pc.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-113">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
8. <span data-ttu-id="e6e3a-114">Vouw de **beheren hoe gebruikers toegang kunnen krijgen tot Office-bestanden op apparaten** \> de gewenste instellingen te configureren.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-114">Expand **Manage how users access Office files on devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="e6e3a-115">De **manier waarop gebruikers toegang kunnen krijgen tot Office-apparaten op mobiele apparaten beheren** is standaard **uitgeschakeld** , maar het is aanbevolen dat u **deze functie inschakelen** en accepteer de standaardwaarden.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-115">The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="e6e3a-116">Zie de [beschikbare instellingen](#available-settings)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-116">See [Available settings](#available-settings)for more information.</span></span> 
    
    <span data-ttu-id="e6e3a-117">U kunt altijd de koppeling **Standaardwaarden herstellen** gebruiken om terug te keren naar de standaardinstelling.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-117">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
9. <span data-ttu-id="e6e3a-118">Vouw **Gegevens herstellen op Windows-apparaten** uit. U wordt aangeraden de optie **in te schakelen**.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-118">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="e6e3a-p103">Voordat u naar de locatie van het certificaat voor de gegevensherstelagent kunt bladeren, moet u deze eerst maken. Zie [Een certificaat voor een gegevensherstelagent voor het Encrypting File System (EFS) maken en verifiëren](https://go.microsoft.com/fwlink/p/?linkid=853700) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-p103">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="e6e3a-p104">Werkbestanden worden standaard versleuteld met een geheime code die wordt opgeslagen op het apparaat en die gekoppeld is aan het profiel van de gebruiker. Alleen de gebruiker kan het bestand openen en ontsleutelen. Als een apparaat zoekraakt of als een gebruiker wordt verwijderd, kan een bestand echter blijven steken in versleutelde toestand. Het certificaat van de Gegevensherstelagent (DRA - Data Recovery Agent) kan door een beheerder worden gebruikt om het bestand te ontsleutelen.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-p104">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="e6e3a-p105">Vouw **Meer netwerk- en cloudlocaties beveiligen** uit als u extra domeinen of SharePoint Online-locaties wilt toevoegen om ervoor te zorgen dat bestanden in alle weergegeven apps worden beveiligd. Als u meerdere items moet opgeven voor een veld, gebruikt u een puntkomma (;) tussen de items.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-p105">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span> 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="e6e3a-p106">Bepaal nu **Voor wie zijn deze instellingen?** Als u niet de standaardbeveiligingsgroep **Alle gebruikers** wilt gebruiken, kiest u **Wijzigen**, zoekt u de beveiligingsgroep die deze instellingen krijgt \> **Selecteren**.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="e6e3a-131">Kies ten slotte **Toevoegen** om het beleid op te slaan en dit toe te wijzen aan apparaten.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-131">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="e6e3a-132">Beschikbare instellingen</span><span class="sxs-lookup"><span data-stu-id="e6e3a-132">Available settings</span></span>

<span data-ttu-id="e6e3a-133">De volgende instellingen zijn beschikbaar om te beheren hoe gebruikers toegang hebben tot Office-werkbestanden.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-133">The following settings are available to manage how users access Office work files.</span></span>
  
<span data-ttu-id="e6e3a-134">Zie [Hoe beveiligingsfuncties in Microsoft 365 Business zijn toegewezen aan Intune-instellingen](map-protection-features-to-intune-settings.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-134">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span>
  
|<span data-ttu-id="e6e3a-135">**Instelling**</span><span class="sxs-lookup"><span data-stu-id="e6e3a-135">**Setting**</span></span>|<span data-ttu-id="e6e3a-136">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="e6e3a-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e6e3a-137">Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps</span><span class="sxs-lookup"><span data-stu-id="e6e3a-137">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="e6e3a-138">Als deze instelling is **ingeschakeld**, moeten gebruikers een extra vorm van verificatie gebruiken, naast het verstrekken van gebruikersnaam en wachtwoord, voordat ze de Office-apps op hun mobiele apparaat kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-138">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="e6e3a-139">Pincode opnieuw instellen wanneer het aanmelden ... keer mislukt</span><span class="sxs-lookup"><span data-stu-id="e6e3a-139">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="e6e3a-140">Om te voorkomen dat een niet-geautoriseerde gebruiker een pincode kan raden, wordt de pincode opnieuw ingesteld na het aantal door u opgegeven verkeerde aanmeldpogingen.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-140">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="e6e3a-141">Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende</span><span class="sxs-lookup"><span data-stu-id="e6e3a-141">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="e6e3a-142">Met deze instelling wordt bepaald hoelang gebruikers inactief kunnen zijn voordat hun wordt gevraagd zich opnieuw aan te melden.</span><span class="sxs-lookup"><span data-stu-id="e6e3a-142">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
   

