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
description: Met AutoPilot-profielen kunt u bepalen hoe Windows wordt geïnstalleerd op gebruikersapparaten. De profielen bevatten standaardinstellingen en optionele instellingen, zoals Cortana-installatie overslaan.
ms.openlocfilehash: be10e0e1c8c96ce05aab8526d2010313662ed5f2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913373"
---
# <a name="about-autopilot-profile-settings"></a>Info over AutoPilot-profielinstellingen

## <a name="autopilot-profile-settings"></a>AutoPilot-profielinstellingen

U kunt AutoPilot-profielen gebruiken om te bepalen hoe Windows is geïnstalleerd op gebruikersapparaten. De profielen bevatten de volgende instellingen.
  
 **Standaardfuncties van AutoPilot (vereist) die automatisch worden ingesteld:**
  
|**Instelling**|**Beschrijving**|
|:-----|:-----|
|Cortana-, OneDrive- en OEM-registratie overslaan  <br/> |Het installeren van consumentenapplicaties zoals Cortana en persoonlijke OneDrive wordt overgeslagen. De apparaatgebruiker kan deze later installeren zolang de gebruiker een lokale beheerder op het apparaat is. De oorspronkelijke fabrikantregistratie wordt overgeslagen omdat het apparaat wordt beheerd door Microsoft 365 Business Premium.  <br/> |
|Aanmeldervaring met de huisstijl van uw bedrijf  <br/> |Als uw bedrijf de naam [Add your company branding to Microsoft 365 Sign In page](../admin/setup/customize-sign-in-page.md)heeft, krijgt de apparaatgebruiker die ervaring bij het aanmelden.  <br/> |
|Automatische inschrijving van MDM met geconfigureerde AAD-accounts.  <br/> |De gebruikersidentiteit wordt beheerd door Azure Active Directory en gebruikers melden zich aan bij Windows en Microsoft 365 met hun Microsoft 365 Business Premium-referenties.  <br/> |
   
 **Optionele instellingen:**
  
|**Instelling**|**Omschrijving**|
|:-----|:-----|
|Privacy-instellingen overslaan (standaard uitgeschakeld)  <br/> |Als deze optie is ingesteld op **Aan**, krijgt de gebruiker van het apparaat de licentieovereenkomst voor het apparaat en Windows niet te zien wanneer hij of zij zich voor het eerst aanmeldt.  <br/> |
|Niet toestaan dat de gebruiker de lokale administrator wordt  <br/> |Als deze optie is ingesteld op **Aan**, kan de gebruiker van het apparaat geen persoonlijke apps installeren, zoals Cortana.<br/> |
