---
title: De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Informatie over automatische piloot Windows gebruiken voor het instellen van nieuwe Windows 10-apparaten voor uw bedrijf.
ms.openlocfilehash: 56225424125e9eed9f46867837c564aa5d1c4adc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982162"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen

U kunt de WIndows Autopilot gebruiken om nieuwe Windows 10-apparaten voor uw bedrijf in te stellen, zodat deze klaar zijn voor gebruik zodra u ze aan uw werknemers geeft.
  
## <a name="device-requirements"></a>Apparaatvereisten

Apparaten moeten aan deze vereisten voldoen:
  
- Windows 10 versie 1703 of hoger.
    
- Nieuwe apparaten die niet de Out-of-Box Experience van Windows hebben doorlopen.
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>De installatiehandleiding gebruiken om apparaten en profielen te maken

Als u nog geen apparaatgroepen of profielen hebt gemaakt, kunt u het beste aan de slag gaan met de stapsgewijze handleiding, maar u kunt ook [apparaten toevoegen](create-and-edit-autopilot-devices.md) en hieraan [profielen toewijzen](create-and-edit-autopilot-profiles.md) zonder de handleiding te gebruiken. 
  
1. Zoek in het beheercentrum van Microsoft 365 Business naar de kaart **Apparaatacties** en kies **Windows implementeren met AutoPilot**.
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. Klik of tik op de pagina **Windows voorbereiden** op **Handleiding starten**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Blader op de pagina **CSV-bestand met lijst met apparaten uploaden** naar de locatie van het voorbereide CSV-bestand en klik op **Openen** \> **Volgende**. Het bestand moet drie kopteksten bevatten:
    
  - Kolom A: Serienummer van apparaat
    
  - Kolom B: Product-id van Windows
    
  - Kolom C: Hardware-hash
    
    U kunt deze informatie van uw hardwareleverancier krijgen of u kunt het [Get-WindowsAutoPilotInfo-PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken, waarmee een CSV-bestand wordt gegenereerd. 
    
    Zie [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) (CSV-bestand met lijst met apparaten) voor meer informatie. U kunt ook een voorbeeldbestand downloaden op de pagina **CSV-bestand met lijst met apparaten uploaden**. 
    
4. Op de pagina **Profiel toewijzen** kunt u een bestaand profiel kiezen of een nieuw profiel maken. Als u nog geen profiel hebt, wordt u gevraagd om een nieuw profiel te maken. 
    
    Een profiel bestaat uit een reeks instellingen die op één apparaat of op een groep apparaten kunnen worden toegepast.
    
    De standaardfuncties zijn vereist en worden automatisch ingesteld. De standaardfuncties zijn:
    
  - Cortana-, OneDrive- en OEM-registratie wordt overgeslagen.
    
  - Maak een aanmeldervaring met de huisstijl van uw bedrijf.
    
  - De apparaten worden verbonden met Azure Active Directory-accounts en worden automatisch geregistreerd om te worden beheerd door Microsoft 365 Business.
    
    Zie voor meer informatie:
    
    [Info over AutoPilot-profielinstellingen](autopilot-profile-settings.md) voor meer informatie. 
    
5. De andere instellingen zijn **Privacy-instellingen overslaan** en **Niet toestaan dat gebruiker de lokale beheerder wordt**. Deze zijn beide standaard **uitgeschakeld**. 
    
    Kies **Volgende**.
    
6. Op de pagina **U bent klaar** wordt aangegeven dat het profiel dat u hebt gemaakt (of gekozen), wordt toegepast op de apparaatgroep die u hebt gemaakt door de lijst met apparaten te uploaden. Deze instellingen worden van kracht wanneer de gebruiker van het apparaat zich de volgende keer aanmeldt. Kies **Sluiten**.
    