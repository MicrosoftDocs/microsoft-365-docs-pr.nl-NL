---
title: De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Lees hoe u Windows AutoPilot gebruikt om nieuwe Windows 10-apparaten voor uw bedrijf in te stellen, zodat ze klaar zijn voor gebruik door werknemers.
ms.openlocfilehash: cd8777e6ae2e395506d2bf308c99309de1e24805
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578522"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen

U kunt Windows AutoPilot gebruiken om nieuwe **Windows** 10-apparaten voor uw bedrijf in te stellen, zodat ze klaar zijn voor gebruik wanneer u ze aan uw werknemers geeft.
  
## <a name="device-requirements"></a>Apparaatvereisten

Apparaten moeten aan deze vereisten voldoen:
  
- Windows 10, versie 1703 of hoger
    
- Nieuwe apparaten die niet out-of-box-ervaring met Windows hebben gehad
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>De installatiehandleiding gebruiken om apparaten en profielen te maken

[![Etiket om u te laten weten dat het beheercentrum wordt gewijzigd en meer informatie vindt u op aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](/office365/admin/microsoft-365-admin-center-preview)

Als u nog geen apparaatgroepen of -profielen hebt gemaakt, kunt u het beste aan de slag met de stapsgewijse handleiding. U kunt ook [apparaten toevoegen en](create-and-edit-autopilot-devices.md) er [profielen](create-and-edit-autopilot-profiles.md) aan toewijzen zonder de handleiding te gebruiken. 
  
1. Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. Kies in het linkernavigatiedeelvenster de optie **Apparaten** \> **AutoPilot**.

    ![Kies in het beheercentrum apparaten en vervolgens AutoPilot.](../media/AutoPilot.png)
  
2. Klik of tik **op de pagina AutoPilot** op **Starthandleiding**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Blader op **de pagina Csv-bestand uploaden met lijst met apparaten** naar een locatie waar u de voorbereidingen hebt getroffen. CSV-bestand en vervolgens **Volgende** \> **openen.** Het bestand moet drie kopteksten hebben:
    
    - Kolom A: Serienummer van apparaat
    
    - Kolom B: Product-id van Windows
    
    - Kolom C: Hardware-hash
    
    U kunt deze informatie krijgen van uw hardwareleverancier of u kunt het [PowerShell-script Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om een CSV-bestand te genereren. 
    
    Zie [Device list CSV-file](../admin/misc/device-list.md) (CSV-bestand met lijst met apparaten) voor meer informatie. U kunt ook een voorbeeldbestand downloaden op de pagina **CSV-bestand met lijst met apparaten uploaden**. 
    
> [!NOTE]
> In dit script wordt WMI gebruikt om eigenschappen op te halen die een klant nodig heeft om een apparaat te registreren bij Windows Autopilot. Houd er rekening mee dat het normaal is dat het resulterende CSV-bestand geen PKID-waarde (Windows Product ID) verzamelt, omdat dit niet nodig is om een apparaat te registreren en PKID null is in de uitvoer-CSV is helemaal prima. Alleen het serienummer en de hardwarehash worden ingevuld.
    
4. Op de **pagina Een profiel** toewijzen kunt u een bestaand profiel kiezen of een nieuw profiel maken. Als u er nog geen hebt, wordt u gevraagd er een te maken. 
    
    Een profiel bestaat uit een reeks instellingen die op één apparaat of op een groep apparaten kunnen worden toegepast.
    
    De standaardfuncties zijn vereist en worden automatisch ingesteld. De standaardfuncties zijn:
    
    - Sla Cortana, OneDrive en OEM-registratie over.
    
    - Maak een aanmeldervaring met de huisstijl van uw bedrijf.
    
    - Verbind uw apparaten met Azure Active Directory-accounts en schrijf ze automatisch in om te worden beheerd door Microsoft 365 Business Premium.
    
    Zie Over [AutoPilot-profielinstellingen voor meer informatie.](autopilot-profile-settings.md) 
    
5. De andere instellingen zijn **Privacy-instellingen overslaan** en **Niet toestaan dat gebruiker de lokale beheerder wordt**. Deze zijn beide standaard **uitgeschakeld**. 
    
    Kies **Volgende**.
    
6. **U bent klaar, geeft** aan dat het profiel dat u hebt gemaakt (of gekozen) wordt toegepast op de apparaatgroep die u hebt gemaakt door de lijst met apparaten te uploaden. De instellingen zijn van kracht wanneer de gebruikers van het apparaat zich volgende aanmelden. Kies **Sluiten**.
