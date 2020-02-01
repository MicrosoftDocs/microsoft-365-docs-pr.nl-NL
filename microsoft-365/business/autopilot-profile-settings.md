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
description: Met AutoPilot-profielen u bepalen hoe Windows wordt geïnstalleerd op gebruikersapparaten. De profielen bevatten standaard instellingen en optionele instellingen zoals cortana-installatie overslaan.
ms.openlocfilehash: 1cc8a3171bbc4a1e5cb531b9364c7791586fc339
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593328"
---
# <a name="about-autopilot-profile-settings"></a>Info over AutoPilot-profielinstellingen

## <a name="autopilot-profile-settings"></a>AutoPilot-profielinstellingen

U AutoPilot-profielen gebruiken om te bepalen hoe Windows is geïnstalleerd op gebruikersapparaten. De profielen bevatten de volgende instellingen.
  
 **Standaardfuncties van AutoPilot (vereist) die automatisch worden ingesteld:**
  
|**Instelling**|**Beschrijving**|
|:-----|:-----|
|Cortana-, OneDrive- en OEM-registratie overslaan  <br/> |Het installeren van consumentenapplicaties zoals Cortana en persoonlijke OneDrive wordt overgeslagen. De apparaatgebruiker kan deze later installeren zolang de gebruiker een lokale beheerder op het apparaat is. De OEM-registratie wordt overgeslagen omdat het apparaat wordt beheerd door Microsoft 365 Business.  <br/> |
|Aanmeldervaring met de huisstijl van uw bedrijf  <br/> |Als uw bedrijf een [aanmeldingspagina van uw bedrijf heeft toegevoegd aan de aanmeldingspagina van Office 365,](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)krijgt de apparaatgebruiker die ervaring bij het aanmelden.  <br/> |
|Automatische inschrijving van MDM met geconfigureerde AAD-accounts.  <br/> |De gebruikersidentiteit wordt beheerd door Azure Active Directory en gebruikers melden zich aan bij Windows en Office 365 met hun Microsoft 365 Business-referenties.  <br/> |
   
 **Optionele instellingen:**
  
|**Instelling**|**Omschrijving**|
|:-----|:-----|
|Privacy-instellingen overslaan (standaard uitgeschakeld)  <br/> |Als deze optie is ingesteld op **Aan**, krijgt de gebruiker van het apparaat de licentieovereenkomst voor het apparaat en Windows niet te zien wanneer hij of zij zich voor het eerst aanmeldt.  <br/> |
|Niet toestaan dat de gebruiker de lokale administrator wordt  <br/> |Als deze optie is ingesteld op **Aan**, kan de gebruiker van het apparaat geen persoonlijke apps installeren, zoals Cortana.<br/> |
   
