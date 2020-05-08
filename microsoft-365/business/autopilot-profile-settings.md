---
title: Info over AutoPilot-profielinstellingen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
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
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Met AutoPilot-profielen u bepalen hoe Windows wordt geïnstalleerd op gebruikersapparaten. De profielen bevatten standaard- en optionele instellingen, zoals cortana-installatie overslaan.
ms.openlocfilehash: 0c706d12ba262856ff40ea3bee57c64234fd77f7
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165836"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="3fa82-104">Info over AutoPilot-profielinstellingen</span><span class="sxs-lookup"><span data-stu-id="3fa82-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="3fa82-105">AutoPilot-profielinstellingen</span><span class="sxs-lookup"><span data-stu-id="3fa82-105">AutoPilot profile settings</span></span>

<span data-ttu-id="3fa82-106">U AutoPilot-profielen gebruiken om te bepalen hoe Windows is geïnstalleerd op gebruikersapparaten.</span><span class="sxs-lookup"><span data-stu-id="3fa82-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="3fa82-107">De profielen bevatten de volgende instellingen.</span><span class="sxs-lookup"><span data-stu-id="3fa82-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="3fa82-108">**Standaardfuncties van AutoPilot (vereist) die automatisch worden ingesteld:**</span><span class="sxs-lookup"><span data-stu-id="3fa82-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="3fa82-109">**Instelling**</span><span class="sxs-lookup"><span data-stu-id="3fa82-109">**Setting**</span></span>|<span data-ttu-id="3fa82-110">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="3fa82-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3fa82-111">Cortana-, OneDrive- en OEM-registratie overslaan</span><span class="sxs-lookup"><span data-stu-id="3fa82-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="3fa82-112">Het installeren van consumentenapplicaties zoals Cortana en persoonlijke OneDrive wordt overgeslagen.</span><span class="sxs-lookup"><span data-stu-id="3fa82-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="3fa82-113">De gebruiker van het apparaat kan deze later installeren zolang de gebruiker een lokale beheerder op het apparaat is.</span><span class="sxs-lookup"><span data-stu-id="3fa82-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="3fa82-114">De oorspronkelijke registratie van de fabrikant wordt overgeslagen omdat het apparaat wordt beheerd door Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="3fa82-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="3fa82-115">Aanmeldervaring met de huisstijl van uw bedrijf</span><span class="sxs-lookup"><span data-stu-id="3fa82-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="3fa82-116">Als uw bedrijf een [aanmeldingspagina toevoegen aan Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page)heeft, krijgt de apparaatgebruiker die ervaring bij het aanmelden.</span><span class="sxs-lookup"><span data-stu-id="3fa82-116">If your company has a [Add your company branding to Microsoft 365 Sign In page](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="3fa82-117">Automatische inschrijving van MDM met geconfigureerde AAD-accounts.</span><span class="sxs-lookup"><span data-stu-id="3fa82-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="3fa82-118">De gebruikersidentiteit wordt beheerd door Azure Active Directory en gebruikers melden zich aan bij Windows en Microsoft 365 met hun Microsoft 365 Business Premium-referenties.</span><span class="sxs-lookup"><span data-stu-id="3fa82-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Microsoft 365 with their Microsoft 365 Business Premium credentials.</span></span>  <br/> |
   
 <span data-ttu-id="3fa82-119">**Optionele instellingen:**</span><span class="sxs-lookup"><span data-stu-id="3fa82-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="3fa82-120">**Instelling**</span><span class="sxs-lookup"><span data-stu-id="3fa82-120">**Setting**</span></span>|<span data-ttu-id="3fa82-121">**Omschrijving**</span><span class="sxs-lookup"><span data-stu-id="3fa82-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3fa82-122">Privacy-instellingen overslaan (standaard uitgeschakeld)</span><span class="sxs-lookup"><span data-stu-id="3fa82-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="3fa82-123">Als deze optie is ingesteld op **Aan**, krijgt de gebruiker van het apparaat de licentieovereenkomst voor het apparaat en Windows niet te zien wanneer hij of zij zich voor het eerst aanmeldt.</span><span class="sxs-lookup"><span data-stu-id="3fa82-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="3fa82-124">Niet toestaan dat de gebruiker de lokale administrator wordt</span><span class="sxs-lookup"><span data-stu-id="3fa82-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="3fa82-125">Als deze optie is ingesteld op **Aan**, kan de gebruiker van het apparaat geen persoonlijke apps installeren, zoals Cortana.</span><span class="sxs-lookup"><span data-stu-id="3fa82-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
   
