---
title: Info over AutoPilot-profielinstellingen
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
description: Met AutoPilot-profielen u bepalen hoe Windows op gebruikers apparaten wordt geïnstalleerd. De profielen bevatten standaard en optionele instellingen, zoals de installatie van Skip Cortana.
ms.openlocfilehash: 912a24e3d458986a4bcf7dcf903f80211996aca2
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/14/2019
ms.locfileid: "38321780"
---
# <a name="about-autopilot-profile-settings"></a>Info over AutoPilot-profielinstellingen

## <a name="autopilot-profile-settings"></a>AutoPilot-profielinstellingen

U AutoPilot-profielen gebruiken om te bepalen hoe Windows op gebruikers apparaten is geïnstalleerd. De profielen bevatten de volgende instellingen.
  
 **Standaardfuncties van AutoPilot (vereist) die automatisch worden ingesteld:**
  
|**Instelling**|**Beschrijving**|
|:-----|:-----|
|Cortana, OneDrive en OEM-registratie overslaan  <br/> |Het installeren van consumentenapplicaties zoals Cortana en persoonlijke OneDrive wordt overgeslagen. De gebruiker van het apparaat kan deze later installeren, zolang de gebruiker een lokale beheerder op het apparaat is. De OEM-registratie wordt overgeslagen omdat het apparaat wordt beheerd door Microsoft 365 Business.  <br/> |
|Aanmeldervaring met de huisstijl van uw bedrijf  <br/> |Als uw bedrijf heeft een [huisstijl toevoegen aan Office 365 aanmelden pagina](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), de gebruiker van het apparaat krijgt die ervaring bij het aanmelden.  <br/> |
|Automatische inschrijving van MDM met geconfigureerde AAD-accounts.  <br/> |De gebruikersidentiteit wordt beheerd door Azure Active Directory en gebruikers zullen zich aanmelden bij Windows en Office 365 met hun Microsoft 365 zakelijke referenties.  <br/> |
   
 **Optionele instellingen:**
  
|**Instelling**|**Omschrijving**|
|:-----|:-----|
|Privacy-instellingen overslaan (standaard uitgeschakeld)  <br/> |Als deze optie is ingesteld op **Aan**, krijgt de gebruiker van het apparaat de licentieovereenkomst voor het apparaat en Windows niet te zien wanneer hij of zij zich voor het eerst aanmeldt.  <br/> |
|Niet toestaan dat de gebruiker de lokale administrator wordt  <br/> |Als deze optie is ingesteld op **Aan**, kan de gebruiker van het apparaat geen persoonlijke apps installeren, zoals Cortana.<br/> |
   
