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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Met AutoPilot-profielen u bepalen hoe Windows wordt geïnstalleerd op gebruikersapparaten. De profielen bevatten standaard- en optionele instellingen, zoals cortana-installatie overslaan.
ms.openlocfilehash: 100de5e9548f901008d3ae154ac5a237ef265ffb
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401029"
---
# <a name="about-autopilot-profile-settings"></a>Info over AutoPilot-profielinstellingen

## <a name="autopilot-profile-settings"></a>AutoPilot-profielinstellingen

U AutoPilot-profielen gebruiken om te bepalen hoe Windows is geïnstalleerd op gebruikersapparaten. De profielen bevatten de volgende instellingen.
  
 **Standaardfuncties van AutoPilot (vereist) die automatisch worden ingesteld:**
  
|**Instelling**|**Beschrijving**|
|:-----|:-----|
|Cortana-, OneDrive- en OEM-registratie overslaan  <br/> |Het installeren van consumentenapplicaties zoals Cortana en persoonlijke OneDrive wordt overgeslagen. De gebruiker van het apparaat kan deze later installeren zolang de gebruiker een lokale beheerder op het apparaat is. De oorspronkelijke registratie van de fabrikant wordt overgeslagen omdat het apparaat wordt beheerd door Microsoft 365 Business Premium.  <br/> |
|Aanmeldervaring met de huisstijl van uw bedrijf  <br/> |Als uw bedrijf een [aanmeldingspagina toevoegen aan Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page)heeft, krijgt de apparaatgebruiker die ervaring bij het aanmelden.  <br/> |
|Automatische inschrijving van MDM met geconfigureerde AAD-accounts.  <br/> |De gebruikersidentiteit wordt beheerd door Azure Active Directory en gebruikers melden zich aan bij Windows en Microsoft 365 met hun Microsoft 365 Business Premium-referenties.  <br/> |
   
 **Optionele instellingen:**
  
|**Instelling**|**Omschrijving**|
|:-----|:-----|
|Privacy-instellingen overslaan (standaard uitgeschakeld)  <br/> |Als deze optie is ingesteld op **Aan**, krijgt de gebruiker van het apparaat de licentieovereenkomst voor het apparaat en Windows niet te zien wanneer hij of zij zich voor het eerst aanmeldt.  <br/> |
|Niet toestaan dat de gebruiker de lokale administrator wordt  <br/> |Als deze optie is ingesteld op **Aan**, kan de gebruiker van het apparaat geen persoonlijke apps installeren, zoals Cortana.<br/> |
   
