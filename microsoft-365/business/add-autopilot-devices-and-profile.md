---
title: De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Meer informatie over het gebruik van Windows AutoPilot om nieuwe Windows 10-apparaten voor uw bedrijf in te stellen, zodat ze klaar zijn voor gebruik door werknemers.
ms.openlocfilehash: de14012ebf9e7cdd22e41505f316ab665773c670
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165876"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen

U Windows AutoPilot gebruiken om nieuwe Windows **10-apparaten** voor uw bedrijf in te stellen, zodat ze klaar zijn voor gebruik wanneer u ze aan uw werknemers geeft.
  
## <a name="device-requirements"></a>Apparaatvereisten

Apparaten moeten aan deze eisen voldoen:
  
- Windows 10, versie 1703 of hoger
    
- Nieuwe apparaten die niet zijn door Windows out-of-box ervaring
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>De installatiehandleiding gebruiken om apparaten en profielen te maken

[![Etiket om u te laten weten dat het beheercentrum wordt gewijzigd en meer informatie vindt u op aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Als u apparaatgroepen of profielen nog niet hebt gemaakt, u het beste aan de slag met de stapsgewijze handleiding. U er ook [apparaten aan toevoegen](create-and-edit-autopilot-devices.md) en er profielen aan [toewijzen](create-and-edit-autopilot-profiles.md) zonder de handleiding te gebruiken. 
  
1. Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. Kies **Apparaten** \> **Automatisch piloot**in het linkernavigatiedeelvenster .

    ![Kies in het beheercentrum apparaten en vervolgens AutoPilot.](../media/AutoPilot.png)
  
2. Klik of tik op de pagina **AutoPilot** op **De hulplijn Start**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Blader op het **CSV-bestand uploaden met lijst met apparaten** naar een locatie waar u de indeling hebt voorbereid. CSV-bestand en vervolgens **Volgende** \> **openen**. Het bestand moet drie kopteksten hebben:
    
    - Kolom A: Serienummer van apparaat
    
    - Kolom B: Product-id van Windows
    
    - Kolom C: Hardware-hash
    
    U deze informatie ophalen bij uw hardwareleverancier of u het [PowerShell-script Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om een CSV-bestand te genereren. 
    
    Zie [Device list CSV-file](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) (CSV-bestand met lijst met apparaten) voor meer informatie. U kunt ook een voorbeeldbestand downloaden op de pagina **CSV-bestand met lijst met apparaten uploaden**. 
    
4. Op de **profielpagina Toewijzen** u een bestaand profiel kiezen of een nieuw profiel maken. Als je er nog geen hebt, wordt je gevraagd er een te maken. 
    
    Een profiel bestaat uit een reeks instellingen die op één apparaat of op een groep apparaten kunnen worden toegepast.
    
    De standaardfuncties zijn vereist en worden automatisch ingesteld. De standaardfuncties zijn:
    
    - Cortana-, OneDrive- en OEM-registratie overslaan.
    
    - Maak een aanmeldervaring met de huisstijl van uw bedrijf.
    
    - Verbind uw apparaten met Azure Active Directory-accounts en schrijf ze automatisch in om te worden beheerd door Microsoft 365 Business Premium.
    
    Zie [Instellingen voor AutoPilot-profiel voor](autopilot-profile-settings.md)meer informatie . 
    
5. De andere instellingen zijn **Privacy-instellingen overslaan** en **Niet toestaan dat gebruiker de lokale beheerder wordt**. Deze zijn beide standaard **uitgeschakeld**. 
    
    Kies **Volgende**.
    
6. **U bent klaar,** geeft aan dat het profiel dat u hebt gemaakt (of hebt gekozen) wordt toegepast op de apparaatgroep die u hebt gemaakt door de lijst met apparaten te uploaden. De instellingen zijn van kracht wanneer de gebruikers van het apparaat zich als volgende aanmelden. Kies **Sluiten**.
    
