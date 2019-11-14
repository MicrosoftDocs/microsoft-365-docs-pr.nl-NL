---
title: De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Informatie over het gebruik van Windows AutoPilot voor het instellen van nieuwe Windows 10-apparaten voor uw bedrijf.
ms.openlocfilehash: 5f40dac57285b83da57d4506bac58e562475522c
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/14/2019
ms.locfileid: "38323090"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen

U Windows AutoPilot gebruiken om **nieuwe** Windows 10-apparaten voor uw bedrijf in te stellen, zodat ze klaar zijn voor gebruik wanneer u ze aan uw werknemers geeft.
  
## <a name="device-requirements"></a>Apparaatvereisten

Apparaten moeten aan deze vereisten voldoen:
  
- Windows 10, versie 1703 of hoger
    
- Nieuwe apparaten die niet door Windows zijn out-of-Box-ervaring
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>De installatiehandleiding gebruiken om apparaten en profielen te maken

[![Etiket om u te laten weten dat het beheercentrum wordt gewijzigd en meer informatie vindt u op aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Als u nog geen apparaatgroepen of profielen hebt gemaakt, u de beste manier om aan de slag te gaan door de stapsgewijze handleiding te gebruiken. U ook [apparaten toevoegen](create-and-edit-autopilot-devices.md) en hieraan [profielen toewijzen](create-and-edit-autopilot-profiles.md) zonder de Guide te gebruiken. 
  
1. Ga naar het Admin Center op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. Kies in het linkernavigatievenster **apparaten** \> **Autopilot**.

    ![In het Admin Center, kiest u apparaten en vervolgens AutoPilot.](media/AutoPilot.png)
  
2. Klik of tik op de pagina **stuurautomaat** op **start gids**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Op de **Upload. CSV-bestand met lijst met apparaten** pagina, bladert u naar een locatie waar u de voorbereide. CSV-bestand en **Open** \> vervolgens **de volgende**. Het bestand moet drie koppen hebben:
    
    - Kolom A: Serienummer van apparaat
    
    - Kolom B: Product-id van Windows
    
    - Kolom C: Hardware-hash
    
    U deze informatie ophalen van uw hardwareleverancier, of u het [Get-WindowsAutoPilotInfo PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om een CSV-bestand te genereren. 
    
    Zie [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) (CSV-bestand met lijst met apparaten) voor meer informatie. U kunt ook een voorbeeldbestand downloaden op de pagina **CSV-bestand met lijst met apparaten uploaden**. 
    
4. Op de pagina **een profiel toewijzen** u een bestaand profiel kiezen of een nieuwe maken. Als u er nog geen hebt, wordt u gevraagd er een te maken. 
    
    Een profiel bestaat uit een reeks instellingen die op één apparaat of op een groep apparaten kunnen worden toegepast.
    
    De standaardfuncties zijn vereist en worden automatisch ingesteld. De standaardfuncties zijn:
    
    - Sla Cortana, OneDrive en OEM-registratie over.
    
    - Maak een aanmeldervaring met de huisstijl van uw bedrijf.
    
    - Verbind uw apparaten met Azure Active Directory-accounts en registreer ze automatisch om te worden beheerd door Microsoft 365 Business.
    
    Zie over de instellingen van het [Autopilot-profiel](autopilot-profile-settings.md)voor meer informatie. 
    
5. De andere instellingen zijn **Privacy-instellingen overslaan** en **Niet toestaan dat gebruiker de lokale beheerder wordt**. Deze zijn beide standaard **uitgeschakeld**. 
    
    Kies **Volgende**.
    
6. **U bent klaar** geeft aan dat het profiel dat u hebt gemaakt (of gekozen) wordt toegepast op de apparaatgroep die u hebt gemaakt door de lijst met apparaten te uploaden. De instellingen zijn van kracht wanneer de apparaatgebruikers zich vervolgens aanmelden. Kies **Sluiten**.
    