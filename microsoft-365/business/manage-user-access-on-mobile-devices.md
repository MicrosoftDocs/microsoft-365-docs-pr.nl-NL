---
title: Beheren hoe gebruikers Office-documenten op mobiele apparaten openen
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- 'O365E_BCSSetup4OfficeMobile '
ms.service: o365-administration
localization_priority: Normal
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
ms.openlocfilehash: 75dbe79acccabd851c43259a165e79bfe3c509c0
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "26983182"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="08fe8-103">Beheren hoe gebruikers Office-documenten op mobiele apparaten openen</span><span class="sxs-lookup"><span data-stu-id="08fe8-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="08fe8-p101">Beleidsinstellingen die bepalen hoe gebruikers toegang hebben tot Office-bestanden op hun mobiele apparaten zijn standaard **uitgeschakeld**. Het is raadzaam dat u de standaardwaarden tijdens de installatie accepteert om beleid voor toepassingen voor Android, iOS en Windows 10 te maken die voor alle gebruikers gelden. Nadat de installatie is voltooid, kunt u meer beleidsregels maken.</span><span class="sxs-lookup"><span data-stu-id="08fe8-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="08fe8-107">Instellingen die bepalen hoe gebruikers Office-bestanden op mobiele apparaten kunnen openen</span><span class="sxs-lookup"><span data-stu-id="08fe8-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="08fe8-108">De volgende instellingen zijn beschikbaar om te bepalen hoe gebruikers toegang tot Office-werkbestanden hebben:</span><span class="sxs-lookup"><span data-stu-id="08fe8-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="08fe8-109">Instelling</span><span class="sxs-lookup"><span data-stu-id="08fe8-109">Setting</span></span>  <br/> |<span data-ttu-id="08fe8-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="08fe8-110">Description</span></span>  <br/> |
|<span data-ttu-id="08fe8-111">Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps</span><span class="sxs-lookup"><span data-stu-id="08fe8-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="08fe8-112">Als deze instelling is **ingeschakeld**, moeten gebruikers nog een tweede vorm van verificatie gebruiken, naast het verstrekken van gebruikersnaam en wachtwoord, voordat ze de Office-apps op hun mobiele apparaat kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="08fe8-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="08fe8-113">Pincode opnieuw instellen wanneer het aanmelden ... keer mislukt</span><span class="sxs-lookup"><span data-stu-id="08fe8-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="08fe8-114">Als u wilt voorkomen dat een niet-geautoriseerde gebruiker een pincode kan raden, wordt de pincode opnieuw ingesteld na het aantal door u opgegeven verkeerde aanmeldpogingen.</span><span class="sxs-lookup"><span data-stu-id="08fe8-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="08fe8-115">Gebruikers verplichten om zich opnieuw aan te melden nadat Office-apps niet actief zijn geweest gedurende</span><span class="sxs-lookup"><span data-stu-id="08fe8-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="08fe8-116">Deze instelling bepaalt hoe lang gebruikers inactief kunnen zijn voordat ze worden gevraagd zich opnieuw aan te melden.</span><span class="sxs-lookup"><span data-stu-id="08fe8-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="08fe8-117">Toegang weigeren tot werkbestanden op jailbroken of geroote apparaten</span><span class="sxs-lookup"><span data-stu-id="08fe8-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="08fe8-p102">Slimme gebruikers hebben mogelijk een jailbroken of geroot apparaat. Dit betekent dat de gebruiker het besturingssysteem kan aanpassen, waardoor het apparaat gevoeliger zou kunnen worden voor malware. Deze apparaten worden geblokkeerd wanneer deze instelling is **ingeschakeld**.  </span><span class="sxs-lookup"><span data-stu-id="08fe8-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="08fe8-121">Gebruikers toestaan om inhoud uit Office-apps te kopiëren naar persoonlijke apps</span><span class="sxs-lookup"><span data-stu-id="08fe8-121">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="08fe8-p103">Dit is standaard toegestaan, maar wanneer de instelling is **ingeschakeld**, kan de gebruiker gegevens in een werkbestand kopiëren naar een persoonlijk bestand. Als de instelling is **uitgeschakeld**, kan de gebruiker geen gegevens uit een werkbestand kopiëren naar een persoonlijke app of persoonlijk account.  </span><span class="sxs-lookup"><span data-stu-id="08fe8-p103">We allow this by default, but when the setting is **On**, the user can copy information in a work file to a personal file. If the setting is **Off**, the user can't copy information from a work file to a personal app or personal account.  </span></span><br/> |
   

