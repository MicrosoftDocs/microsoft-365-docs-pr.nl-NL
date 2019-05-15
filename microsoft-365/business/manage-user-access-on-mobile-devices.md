---
title: Beheren hoe gebruikers Office-documenten op mobiele apparaten openen
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Meer informatie over bescherming beleid waarmee beveiligde toegang tot Office apps vanaf mobiele apparaten.
ms.openlocfilehash: cade979635dd5d4a618537d544a7a76ef64a2963
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071525"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="bc3c9-103">Beheren hoe gebruikers Office-documenten op mobiele apparaten openen</span><span class="sxs-lookup"><span data-stu-id="bc3c9-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="bc3c9-p101">Beleidsinstellingen die bepalen hoe gebruikers toegang hebben tot Office-bestanden op hun mobiele apparaten zijn standaard **uitgeschakeld**. Het is raadzaam dat u de standaardwaarden tijdens de installatie accepteert om beleid voor toepassingen voor Android, iOS en Windows 10 te maken die voor alle gebruikers gelden. Nadat de installatie is voltooid, kunt u meer beleidsregels maken.</span><span class="sxs-lookup"><span data-stu-id="bc3c9-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="bc3c9-107">Instellingen die bepalen hoe gebruikers Office-bestanden op mobiele apparaten kunnen openen</span><span class="sxs-lookup"><span data-stu-id="bc3c9-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="bc3c9-108">De volgende instellingen zijn beschikbaar om te bepalen hoe gebruikers toegang tot Office-werkbestanden hebben:</span><span class="sxs-lookup"><span data-stu-id="bc3c9-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bc3c9-109">Instelling</span><span class="sxs-lookup"><span data-stu-id="bc3c9-109">Setting</span></span>  <br/> |<span data-ttu-id="bc3c9-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="bc3c9-110">Description</span></span>  <br/> |
|<span data-ttu-id="bc3c9-111">Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps</span><span class="sxs-lookup"><span data-stu-id="bc3c9-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="bc3c9-112">Als deze instelling is **ingeschakeld**, moeten gebruikers een extra vorm van verificatie gebruiken, naast het verstrekken van gebruikersnaam en wachtwoord, voordat ze de Office-apps op hun mobiele apparaat kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="bc3c9-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="bc3c9-113">Pincode opnieuw instellen wanneer het aanmelden ... keer mislukt</span><span class="sxs-lookup"><span data-stu-id="bc3c9-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="bc3c9-114">Om te voorkomen dat een niet-geautoriseerde gebruiker een pincode kan raden, wordt de pincode opnieuw ingesteld na het aantal door u opgegeven verkeerde aanmeldpogingen.</span><span class="sxs-lookup"><span data-stu-id="bc3c9-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="bc3c9-115">Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende</span><span class="sxs-lookup"><span data-stu-id="bc3c9-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="bc3c9-116">Met deze instelling wordt bepaald hoelang gebruikers inactief kunnen zijn voordat hun wordt gevraagd zich opnieuw aan te melden.</span><span class="sxs-lookup"><span data-stu-id="bc3c9-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="bc3c9-117">Toegang weigeren tot werkbestanden op jailbroken of geroote apparaten</span><span class="sxs-lookup"><span data-stu-id="bc3c9-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="bc3c9-p102">Slimme gebruikers hebben mogelijk een jailbroken of geroot apparaat. Dit betekent dat de gebruiker het besturingssysteem kan aanpassen, waardoor het apparaat gevoeliger zou kunnen worden voor malware. Deze apparaten worden geblokkeerd wanneer deze instelling is **ingeschakeld**.  </span><span class="sxs-lookup"><span data-stu-id="bc3c9-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="bc3c9-121">Niet toestaan dat gebruikers inhoud kopiëren vanuit Office apps naar persoonlijke apps</span><span class="sxs-lookup"><span data-stu-id="bc3c9-121">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="bc3c9-122">Wanneer de instelling **ingeschakeld is**, kan de gebruiker informatie in een werkbestand naar een bestand met persoonlijke kopiëren.</span><span class="sxs-lookup"><span data-stu-id="bc3c9-122">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="bc3c9-123">Als de instelling **uitgeschakeld is**, kan de gebruiker gegevens kopiëren uit een werkbestand naar een persoonlijke app of een persoonlijke account.</span><span class="sxs-lookup"><span data-stu-id="bc3c9-123">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

