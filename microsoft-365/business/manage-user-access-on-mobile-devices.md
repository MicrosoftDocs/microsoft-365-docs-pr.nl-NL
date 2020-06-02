---
title: Beheren hoe gebruikers Office-documenten op mobiele apparaten openen
f1.keywords:
- NOCSH
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Meer informatie over beveiligingsbeleid waarmee u beheren hoe gebruikers toegang krijgen tot Office-apps en werkbestanden vanaf mobiele apparaten.
ms.openlocfilehash: b2b828cf2e201360f12b8fadcb395e72958230f6
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471062"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="eff6f-103">Beheren hoe gebruikers Office-documenten op mobiele apparaten openen</span><span class="sxs-lookup"><span data-stu-id="eff6f-103">Manage how users access Office documents on mobile devices</span></span>

<span data-ttu-id="eff6f-104">Dit artikel is van toepassing op Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="eff6f-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="eff6f-105">Beleidsinstellingen die bepalen hoe gebruikers toegang hebben tot Office-bestanden op hun mobiele apparaten zijn standaard **uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="eff6f-105">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="eff6f-106">We raden u aan tijdens de installatie de standaardwaarden te accepteren om toepassingsbeleid voor Android, iOS en Windows 10 te maken die van toepassing zijn op alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="eff6f-106">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="eff6f-107">Nadat de installatie is voltooid, kunt u meer beleidsregels maken.</span><span class="sxs-lookup"><span data-stu-id="eff6f-107">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="eff6f-108">Instellingen die bepalen hoe gebruikers Office-bestanden op mobiele apparaten kunnen openen</span><span class="sxs-lookup"><span data-stu-id="eff6f-108">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="eff6f-109">De volgende instellingen zijn beschikbaar om te bepalen hoe gebruikers toegang tot Office-werkbestanden hebben:</span><span class="sxs-lookup"><span data-stu-id="eff6f-109">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="eff6f-110">Instelling</span><span class="sxs-lookup"><span data-stu-id="eff6f-110">Setting</span></span>  <br/> |<span data-ttu-id="eff6f-111">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="eff6f-111">Description</span></span>  <br/> |
|<span data-ttu-id="eff6f-112">Een pincode of vingerafdruk vereisen om toegang te krijgen tot Office-apps</span><span class="sxs-lookup"><span data-stu-id="eff6f-112">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="eff6f-113">Als deze instelling **ingeschakeld**is, moeten gebruikers naast hun gebruikersnaam en wachtwoord een andere vorm van verificatie opgeven voordat ze Office-apps op hun mobiele apparaat kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="eff6f-113">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="eff6f-114">Pincode opnieuw instellen wanneer het aanmelden ... keer mislukt</span><span class="sxs-lookup"><span data-stu-id="eff6f-114">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="eff6f-115">Om te voorkomen dat een niet-geautoriseerde gebruiker een pincode kan raden, wordt de pincode opnieuw ingesteld na het aantal door u opgegeven verkeerde aanmeldpogingen.</span><span class="sxs-lookup"><span data-stu-id="eff6f-115">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="eff6f-116">Vereisen dat gebruikers zich opnieuw aanmelden als Office-apps inactief zijn geweest gedurende</span><span class="sxs-lookup"><span data-stu-id="eff6f-116">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="eff6f-117">Met deze instelling bepaalt u hoe lang een gebruiker niet actief kan zijn voordat hij of zij wordt gevraagd zich opnieuw aan te melden.</span><span class="sxs-lookup"><span data-stu-id="eff6f-117">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="eff6f-118">Toegang weigeren tot werkbestanden op jailbroken of geroote apparaten</span><span class="sxs-lookup"><span data-stu-id="eff6f-118">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="eff6f-119">Slimme gebruikers hebben mogelijk een jailbroken of geroot apparaat.</span><span class="sxs-lookup"><span data-stu-id="eff6f-119">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="eff6f-120">Dit betekent dat de gebruiker het besturingssysteem kan wijzigen, waardoor het apparaat gevoeliger kan worden voor malware.</span><span class="sxs-lookup"><span data-stu-id="eff6f-120">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="eff6f-121">Deze apparaten worden geblokkeerd wanneer deze instelling is **ingeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="eff6f-121">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="eff6f-122">Gebruikers niet toestaan inhoud van Office-apps naar persoonlijke apps te kopiëren</span><span class="sxs-lookup"><span data-stu-id="eff6f-122">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="eff6f-123">Wanneer de instelling **ingeschakeld**is, kan de gebruiker geen informatie in een werkbestand kopiëren naar een persoonlijk bestand.</span><span class="sxs-lookup"><span data-stu-id="eff6f-123">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="eff6f-124">Als de instelling is **uitgeschakeld,** kan de gebruiker informatie uit een werkbestand kopiëren naar een persoonlijke app of persoonlijk account.</span><span class="sxs-lookup"><span data-stu-id="eff6f-124">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

