---
title: Info over AutoPilot-profielinstellingen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Automatische piloot profielen kunnen u bepalen hoe Windows Gebruikersapparaten wordt geïnstalleerd. De profielen bevatten standaard en optionele instellingen zoals Cortana installatie overslaan.
ms.openlocfilehash: d43a15e5f3dc83596b5c23dd0ceb416b24810298
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276936"
---
# <a name="about-autopilot-profile-settings"></a>Info over AutoPilot-profielinstellingen

## <a name="autopilot-profile-settings"></a>AutoPilot-profielinstellingen

U kunt bepalen hoe Windows op gebruikersapparaten wordt geïnstalleerd door de AutoPilot-profielen te gebruiken. De profielen bevatten de volgende instellingen.
  
 **Standaardfuncties van AutoPilot (vereist) die automatisch worden ingesteld:**
  
|**Instelling**|**Beschrijving**|
|:-----|:-----|
|Cortana, OneDrive en OEM-registratie overslaan  <br/> |Het installeren van consumentenapplicaties zoals Cortana en persoonlijke OneDrive wordt overgeslagen. De gebruiker van het apparaat kan ze later installeren als hij of zij een lokale administrator op het apparaat is. De OEM-registratie wordt overgeslagen omdat het apparaat wordt beheerd door Microsoft 365 Business.  <br/> |
|Aanmeldervaring met de huisstijl van uw bedrijf  <br/> |Als uw bedrijf beschikt over een [van uw bedrijf toevoegen aan Office 365 aanmeldingspagina huisstijl](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), krijgt de gebruiker van het apparaat dat de ervaring tijdens het aanmelden.  <br/> |
|Automatische inschrijving van MDM met geconfigureerde AAD-accounts.  <br/> |De gebruikersidentiteit wordt beheerd door Azure Active Directory, en de gebruikers melden zich aan bij Windows en Office 365 met hun Microsoft 365 Business gegevens.  <br/> |
   
 **Optionele instellingen:**
  
|**Instelling**|**Omschrijving**|
|:-----|:-----|
|Privacy-instellingen overslaan (standaard uitgeschakeld)  <br/> |Als deze optie is ingesteld op **Aan**, krijgt de gebruiker van het apparaat de licentieovereenkomst voor het apparaat en Windows niet te zien wanneer hij of zij zich voor het eerst aanmeldt.  <br/> |
|Niet toestaan dat de gebruiker de lokale administrator wordt  <br/> |Als deze optie is ingesteld op **Aan**, kan de gebruiker van het apparaat geen persoonlijke apps installeren, zoals Cortana.  <br/> |
   
