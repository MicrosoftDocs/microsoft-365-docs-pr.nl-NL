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
description: Meer informatie over het uploaden van apparaten met AutoPilot in Microsoft 365 Business Premium. U een profiel toewijzen aan een apparaat of een groep apparaten.
ms.openlocfilehash: 83c027cfe019e037518c4ca13eb331e5300fc2c1
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165856"
---
# <a name="create-and-edit-autopilot-devices"></a>AutoPilot-apparaten maken en bewerken

## <a name="upload-a-list-of-devices"></a>Een lijst met apparaten uploaden

U de [stapsgewijze handleiding](add-autopilot-devices-and-profile.md) gebruiken om apparaten te uploaden, maar u ook apparaten uploaden op het tabblad **Apparaten.** 
  
Apparaten moeten aan deze eisen voldoen:
  
- Windows 10, versie 1703 of hoger
    
- Nieuwe apparaten die niet zijn door Windows out-of-box ervaring

1. Kies **Apparaten** \> **AutoPilot**in het Microsoft 365-beheercentrum .
  
2. Kies op de pagina **AutoPilot** het tabblad \> **Apparaten** **toevoegen**.
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. Blader in het deelvenster **Apparaten toevoegen** naar een \> [CSV-bestand van](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) de apparaatlijst dat u Hebt voorbereid Op sluit **opslaan** \> **Close**.
    
    U deze informatie ophalen bij uw hardwareleverancier of u het [PowerShell-script Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om een CSV-bestand te genereren. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Een profiel toewijzen aan een apparaat of een groep apparaten

1. Kies **op** de pagina Windows voorbereiden het tabblad **Apparaten** en schakel het selectievakje in naast een of meer apparaten. 
    
2. Selecteer in het deelvenster **Apparaat** een profiel in de vervolgkeuzelijst **Toegewezen profiel**. 
    
    Zie [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) (AutoPilot-profielen maken en bewerken) voor instructies als u nog geen profielen hebt. 
    
