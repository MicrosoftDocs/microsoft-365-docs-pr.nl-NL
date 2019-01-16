---
title: Info over AutoPilot-profielinstellingen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
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
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Automatische piloot profielen kunnen u bepalen hoe Windows Gebruikersapparaten wordt geïnstalleerd. De profielen bevatten standaard en optionele instellingen zoals Cortana installatie overslaan.
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982242"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="8042b-104">Info over AutoPilot-profielinstellingen</span><span class="sxs-lookup"><span data-stu-id="8042b-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="8042b-105">AutoPilot-profielinstellingen</span><span class="sxs-lookup"><span data-stu-id="8042b-105">AutoPilot profile settings</span></span>

<span data-ttu-id="8042b-p102">U kunt bepalen hoe Windows op gebruikersapparaten wordt geïnstalleerd door de AutoPilot-profielen te gebruiken. De profielen bevatten de volgende instellingen.</span><span class="sxs-lookup"><span data-stu-id="8042b-p102">You can control how Windows gets installed on user devices by using the AutoPilot profiles. The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="8042b-108">**Standaardfuncties van AutoPilot (vereist) die automatisch worden ingesteld:**</span><span class="sxs-lookup"><span data-stu-id="8042b-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="8042b-109">**Instelling**</span><span class="sxs-lookup"><span data-stu-id="8042b-109">**Setting**</span></span>|<span data-ttu-id="8042b-110">**Omschrijving**</span><span class="sxs-lookup"><span data-stu-id="8042b-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8042b-111">Cortana, OneDrive en OEM-registratie overslaan</span><span class="sxs-lookup"><span data-stu-id="8042b-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="8042b-p103">Het installeren van consumentenapplicaties zoals Cortana en persoonlijke OneDrive wordt overgeslagen. De gebruiker van het apparaat kan ze later installeren als hij of zij een lokale administrator op het apparaat is. De OEM-registratie wordt overgeslagen omdat het apparaat wordt beheerd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="8042b-p103">Skips the installation of consumer apps like Cortana and personal OneDrive. The device user can install these later as long as he or she is a local admin on the device. The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="8042b-115">Aanmeldervaring met de huisstijl van uw bedrijf</span><span class="sxs-lookup"><span data-stu-id="8042b-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="8042b-116">Als uw bedrijf beschikt over een [van uw bedrijf toevoegen aan Office 365 aanmeldingspagina huisstijl](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), krijgt de gebruiker van het apparaat dat de ervaring tijdens het aanmelden.</span><span class="sxs-lookup"><span data-stu-id="8042b-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="8042b-117">Automatische inschrijving van MDM met geconfigureerde AAD-accounts.</span><span class="sxs-lookup"><span data-stu-id="8042b-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="8042b-118">De gebruikersidentiteit wordt beheerd door Azure Active Directory, en de gebruikers melden zich aan bij Windows en Office 365 met hun Microsoft 365 Business gegevens.</span><span class="sxs-lookup"><span data-stu-id="8042b-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="8042b-119">**Optionele instellingen:**</span><span class="sxs-lookup"><span data-stu-id="8042b-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="8042b-120">**Instelling**</span><span class="sxs-lookup"><span data-stu-id="8042b-120">**Setting**</span></span>|<span data-ttu-id="8042b-121">**Omschrijving**</span><span class="sxs-lookup"><span data-stu-id="8042b-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8042b-122">Privacy-instellingen overslaan (standaard uitgeschakeld)</span><span class="sxs-lookup"><span data-stu-id="8042b-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="8042b-123">Als deze optie is ingesteld op **Aan**, krijgt de gebruiker van het apparaat de licentieovereenkomst voor het apparaat en Windows niet te zien wanneer hij of zij zich voor het eerst aanmeldt.</span><span class="sxs-lookup"><span data-stu-id="8042b-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="8042b-124">Niet toestaan dat de gebruiker de lokale administrator wordt</span><span class="sxs-lookup"><span data-stu-id="8042b-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="8042b-125">Als deze optie is ingesteld op **Aan**, kan de gebruiker van het apparaat geen persoonlijke apps installeren, zoals Cortana.</span><span class="sxs-lookup"><span data-stu-id="8042b-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   
