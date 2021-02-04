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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Lees hoe u Windows AutoPilot gebruikt om nieuwe Windows 10-apparaten in te stellen voor uw bedrijf, zodat ze klaar zijn voor gebruik door werknemers.
ms.openlocfilehash: f263cc90656ae5e7be1a89e3c7f56bfb2d0e3651
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099745"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen

U kunt Windows AutoPilot gebruiken om nieuwe **Windows** 10-apparaten in te stellen voor uw bedrijf, zodat ze klaar zijn voor gebruik wanneer u ze aan uw werknemers geeft.
  
## <a name="device-requirements"></a>Apparaatvereisten

Apparaten moeten aan deze vereisten voldoen:
  
- Windows 10, versie 1703 of hoger
    
- Nieuwe apparaten die windows niet out-of-box-ervaring hebben gehad
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>De installatiehandleiding gebruiken om apparaten en profielen te maken

[![Etiket om u te laten weten dat het beheercentrum wordt gewijzigd en meer informatie vindt u op aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Als u nog geen apparaatgroepen of profielen hebt gemaakt, kunt u het beste aan de slag gaan met behulp van de stapsgewijse handleiding. U kunt ook [apparaten toevoegen en](create-and-edit-autopilot-devices.md) hieraan [profielen](create-and-edit-autopilot-profiles.md) toewijzen zonder de handleiding te gebruiken. 
  
1. Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. Kies Apparaten AutoPilot  in het \> **linkernavigatiedeelvenster.**

    ![Kies apparaten in het beheercentrum en vervolgens AutoPilot.](../media/AutoPilot.png)
  
2. Klik of **tik op de AutoPilot-pagina** op **Handleiding Starten.**
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Blader op **de pagina .csv-bestand** uploaden met lijst met apparaten naar een locatie waarop u zich hebt voorbereid. CSV-bestand en vervolgens **Volgende** \> **openen.** Het bestand moet drie kopteksten hebben:
    
    - Kolom A: Serienummer van apparaat
    
    - Kolom B: Product-id van Windows
    
    - Kolom C: Hardware-hash
    
    U kunt deze informatie krijgen van uw hardwareleverancier of u kunt het [PowerShell-script Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om een CSV-bestand te genereren. 
    
    Zie [Device list CSV-file](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) (CSV-bestand met lijst met apparaten) voor meer informatie. U kunt ook een voorbeeldbestand downloaden op de pagina **CSV-bestand met lijst met apparaten uploaden**. 
    
> [!NOTE]
> Dit script gebruikt WMI om eigenschappen op te halen die een klant nodig heeft om een apparaat te registreren bij Windows Autopilot. Het is normaal dat in het resulterende CSV-bestand geen PKID-waarde (Windows Product ID) wordt verzameld, omdat dit niet is vereist om een apparaat te registreren en PKID die NULL is in de uitvoer-CSV, geen zorgen. Alleen het serienummer en hardware-hash worden ingevuld.
    
4. Op de **pagina Een profiel** toewijzen kunt u een bestaand profiel kiezen of een nieuw profiel maken. Als u nog geen account hebt, wordt u gevraagd er een te maken. 
    
    Een profiel bestaat uit een reeks instellingen die op één apparaat of op een groep apparaten kunnen worden toegepast.
    
    De standaardfuncties zijn vereist en worden automatisch ingesteld. De standaardfuncties zijn:
    
    - Cortana-, OneDrive- en OEM-registratie overslaan.
    
    - Maak een aanmeldervaring met de huisstijl van uw bedrijf.
    
    - Verbind uw apparaten met Azure Active Directory-accounts en schrijf ze automatisch in om te worden beheerd door Microsoft 365 Business Premium.
    
    Zie Over [AutoPilot-profielinstellingen voor meer informatie.](autopilot-profile-settings.md) 
    
5. De andere instellingen zijn **Privacy-instellingen overslaan** en **Niet toestaan dat gebruiker de lokale beheerder wordt**. Deze zijn beide standaard **uitgeschakeld**. 
    
    Kies **Volgende**.
    
6. **U bent klaar,** geeft aan dat het profiel dat u hebt gemaakt (of gekozen), wordt toegepast op de apparaatgroep die u hebt gemaakt door de lijst met apparaten te uploaden. De instellingen zijn van kracht wanneer de gebruikers van het apparaat zich de volgende keer aanmelden. Kies **Sluiten**.
    
