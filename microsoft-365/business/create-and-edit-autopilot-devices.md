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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Meer informatie over het uploaden van apparaten met AutoPilot in Microsoft 365 Business. U een profiel toewijzen aan een apparaat of een groep apparaten.
ms.openlocfilehash: 5a99f691b0325f511f34e3a6c3a20f08ee8d909f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594006"
---
# <a name="create-and-edit-autopilot-devices"></a>AutoPilot-apparaten maken en bewerken

## <a name="upload-a-list-of-devices"></a>Een lijst met apparaten uploaden

U de [stapsgewijze handleiding](add-autopilot-devices-and-profile.md) gebruiken om apparaten te uploaden, maar u ook apparaten uploaden op het tabblad **Apparaten.** 
  
Apparaten moeten aan deze eisen voldoen:
  
- Windows 10, versie 1703 of hoger
    
- Nieuwe apparaten die niet via Windows out-of-box-ervaring zijn geweest

1. Kies In het Microsoft 365 Business Admin Center de optie **Apparaten** \> **AutoPilot**.
  
2. Kies op de pagina **AutoPilot** het tabblad \> **Apparaten** **toevoegen**.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. Blader in het deelvenster **Apparaten toevoegen** naar een \> [CSV-bestand in](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) een apparaatlijst dat u hebt voorbereid **Save** \> **Close**.
    
    U deze informatie van uw hardwareleverancier ophalen of u het [PowerShell-script Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om een CSV-bestand te genereren. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Een profiel toewijzen aan een apparaat of een groep apparaten

1. Kies op de pagina **Windows voorbereiden** het tabblad **Apparaten** en schakel het selectievakje naast een of meer apparaten in. 
    
2. Selecteer in het deelvenster **Apparaat** een profiel in de vervolgkeuzelijst **Toegewezen profiel**. 
    
    Zie [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) (AutoPilot-profielen maken en bewerken) voor instructies als u nog geen profielen hebt. 
    
