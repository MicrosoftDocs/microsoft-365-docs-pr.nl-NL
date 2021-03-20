---
title: AutoPilot-apparaten maken en bewerken
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
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
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Meer informatie over het uploaden van apparaten met AutoPilot in Microsoft 365 Business Premium. U kunt een profiel toewijzen aan een apparaat of een groep apparaten.
ms.openlocfilehash: 910abb98b94b749177b04cd12c766f82d348e379
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913393"
---
# <a name="create-and-edit-autopilot-devices"></a>AutoPilot-apparaten maken en bewerken

## <a name="upload-a-list-of-devices"></a>Een lijst met apparaten uploaden

U kunt de [stapsgewijse handleiding gebruiken](add-autopilot-devices-and-profile.md) om apparaten te uploaden, maar u kunt ook apparaten uploaden op het **tabblad** Apparaten. 
  
Apparaten moeten aan deze vereisten voldoen:
  
- Windows 10, versie 1703 of hoger
    
- Nieuwe apparaten die niet out-of-box-ervaring met Windows hebben gehad

1. Kies in het Microsoft 365-beheercentrum de optie **Apparaten** \> **AutoPilot**.
  
2. Kies op **de pagina AutoPilot** het tabblad **Apparaten apparaten** \> **toevoegen.**
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. Blader in **het deelvenster Apparaten** toevoegen naar een [CSV-bestand](../admin/misc/device-list.md) in de lijst Apparaat dat u hebt voorbereid \> **op Sluiten** \> **opslaan.**
    
    U kunt deze informatie krijgen van uw hardwareleverancier of u kunt het [PowerShell-script Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om een CSV-bestand te genereren. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Een profiel toewijzen aan een apparaat of een groep apparaten

1. Kies op **de pagina Windows** voorbereiden het tabblad **Apparaten** en schakel het selectievakje naast een of meer apparaten in. 
    
2. Selecteer in het deelvenster **Apparaat** een profiel in de vervolgkeuzelijst **Toegewezen profiel**. 
    
    Zie [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) (AutoPilot-profielen maken en bewerken) voor instructies als u nog geen profielen hebt. 
