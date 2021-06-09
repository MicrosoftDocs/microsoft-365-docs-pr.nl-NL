---
title: Beheren hoe gebruikers Office-documenten op mobiele apparaten openen
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Meer informatie over beveiligingsbeleid waarmee u kunt beheren hoe gebruikers toegang hebben tot Office apps en bestanden werken vanaf mobiele apparaten.
ms.openlocfilehash: a48aa241c9e70cf087da3f1701e859dae7238024
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578382"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="90760-103">Beheren hoe gebruikers Office-documenten op mobiele apparaten openen</span><span class="sxs-lookup"><span data-stu-id="90760-103">Manage how users access Office documents on mobile devices</span></span>

<span data-ttu-id="90760-104">Dit artikel is van toepassing op Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="90760-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="90760-105">Beleidsinstellingen die bepalen hoe gebruikers toegang hebben tot Office-bestanden op hun mobiele apparaten zijn standaard **uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="90760-105">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="90760-106">Het is raadzaam om de standaardwaarden tijdens de installatie te accepteren om toepassingsbeleid te maken voor Android, iOS en Windows 10 die van toepassing zijn op alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="90760-106">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="90760-107">Nadat de installatie is voltooid, kunt u meer beleidsregels maken.</span><span class="sxs-lookup"><span data-stu-id="90760-107">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="90760-108">Instellingen die bepalen hoe gebruikers Office-bestanden op mobiele apparaten kunnen openen</span><span class="sxs-lookup"><span data-stu-id="90760-108">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="90760-109">De volgende instellingen zijn beschikbaar om te bepalen hoe gebruikers toegang tot Office-werkbestanden hebben:</span><span class="sxs-lookup"><span data-stu-id="90760-109">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="90760-110">Instelling</span><span class="sxs-lookup"><span data-stu-id="90760-110">Setting</span></span>  <br/> |<span data-ttu-id="90760-111">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="90760-111">Description</span></span>  <br/> |
|<span data-ttu-id="90760-112">Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps</span><span class="sxs-lookup"><span data-stu-id="90760-112">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="90760-113">Als deze instelling **Aan** is, moeten gebruikers een andere vorm van verificatie opgeven, naast hun gebruikersnaam en wachtwoord, voordat ze Office apps op hun mobiele apparaat kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="90760-113">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="90760-114">Pincode opnieuw instellen wanneer het aanmelden ... keer mislukt</span><span class="sxs-lookup"><span data-stu-id="90760-114">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="90760-115">Om te voorkomen dat een niet-geautoriseerde gebruiker een pincode kan raden, wordt de pincode opnieuw ingesteld na het aantal door u opgegeven verkeerde aanmeldpogingen.</span><span class="sxs-lookup"><span data-stu-id="90760-115">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="90760-116">Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende</span><span class="sxs-lookup"><span data-stu-id="90760-116">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="90760-117">Met deze instelling wordt bepaald hoelang een gebruiker inactief kan zijn voordat hij of zij wordt gevraagd zich opnieuw aan te melden.</span><span class="sxs-lookup"><span data-stu-id="90760-117">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="90760-118">Toegang weigeren tot werkbestanden op jailbroken of geroote apparaten</span><span class="sxs-lookup"><span data-stu-id="90760-118">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="90760-119">Slimme gebruikers hebben mogelijk een jailbroken of geroot apparaat.</span><span class="sxs-lookup"><span data-stu-id="90760-119">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="90760-120">Dit betekent dat de gebruiker het besturingssysteem kan wijzigen, waardoor het apparaat gevoeliger kan zijn voor malware.</span><span class="sxs-lookup"><span data-stu-id="90760-120">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="90760-121">Deze apparaten worden geblokkeerd wanneer deze instelling is **ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="90760-121">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="90760-122">Gebruikers mogen geen inhoud kopiëren van Office apps naar persoonlijke apps</span><span class="sxs-lookup"><span data-stu-id="90760-122">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="90760-123">Wanneer de instelling **Aan** is, kan de gebruiker geen gegevens in een werkbestand kopiëren naar een persoonlijk bestand.</span><span class="sxs-lookup"><span data-stu-id="90760-123">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="90760-124">Als de instelling **Uit** is, kan de gebruiker gegevens uit een werkbestand kopiëren naar een persoonlijke app of persoonlijk account.</span><span class="sxs-lookup"><span data-stu-id="90760-124">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

