---
title: AutoPilot-apparaten maken en bewerken
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Meer informatie over het uploaden van apparaten met behulp van AutoPilot in Microsoft 365 Business. U een profiel toewijzen aan een apparaat of een groep apparaten.
ms.openlocfilehash: 1dd6b1a574166379e29465bf3699e47e3b155e0b
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/14/2019
ms.locfileid: "38320253"
---
# <a name="create-and-edit-autopilot-devices"></a>AutoPilot-apparaten maken en bewerken

## <a name="upload-a-list-of-devices"></a>Een lijst met apparaten uploaden

U de [Stapsgewijze handleiding](add-autopilot-devices-and-profile.md) gebruiken om apparaten te uploaden, maar u ook apparaten uploaden op het tabblad **apparaten** . 
  
Apparaten moeten aan deze vereisten voldoen:
  
- Windows 10, versie 1703 of hoger
    
- Nieuwe apparaten die niet door Windows zijn out-of-Box-ervaring

1. Kies in het Microsoft 365 Business Admin Center **apparaten** \> **Autopilot**.
  
2. Kies op de pagina **stuurautomaat** het **** tabblad \> apparaten **apparaten toevoegen**.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. Blader in het deelvenster **apparaten toevoegen** naar een [CSV-bestand met apparaatlijsten](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) dat \> u hebt voorbereid om het **Opslaan** \> te **sluiten**.
    
    U deze informatie ophalen van uw hardwareleverancier, of u het [Get-WindowsAutoPilotInfo PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om een CSV-bestand te genereren. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Een profiel toewijzen aan een apparaat of een groep apparaten

1. Kies op de pagina **Windows voorbereiden** het tabblad **apparaten** en schakel het selectievakje naast een of meer apparaten in. 
    
2. Selecteer in het deelvenster **Apparaat** een profiel in de vervolgkeuzelijst **Toegewezen profiel**. 
    
    Zie [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) (AutoPilot-profielen maken en bewerken) voor instructies als u nog geen profielen hebt. 
    
