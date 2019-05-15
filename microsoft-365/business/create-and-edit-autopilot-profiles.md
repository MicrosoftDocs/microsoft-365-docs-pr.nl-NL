---
title: AutoPilot-profielen maken en bewerken
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 'Informatie over te maken, bewerken, verwijderen of automatische piloot profielen verwijderen. '
ms.openlocfilehash: 7987cafb3ea234d81be72c79aee8e584a3770875
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073485"
---
# <a name="create-and-edit-autopilot-profiles"></a>AutoPilot-profielen maken en bewerken

## <a name="create-a-profile"></a>Een profiel maken

Een profiel geldt voor een apparaat of een groep apparaten.
  
1. Kies in het beheercentrum van Microsoft 365 Business **apparaten** \> **automatische piloot**.
  
2. Kies het tabblad **profielen** op de pagina **automatische piloot** \> **profiel maken**.
    
3. Voer op de pagina **Profiel maken** een naam in voor het profiel waaraan u deze kunt herkennen, bijvoorbeeld Marketing, schakel de gewenste instelling in (zie [Info over AutoPilot-profielinstellingen](autopilot-profile-settings.md) voor meer informatie) en kies **Opslaan**.
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Een profiel toepassen op een apparaat

Wanneer u een profiel hebt gemaakt, kunt u deze toepassen op een apparaat of een groep apparaten. U kunt een bestaand profiel kiezen in de [stapsgewijze handleiding](add-autopilot-devices-and-profile.md), u kunt dit toepassen op nieuwe apparaten of u kunt een bestaand profiel voor een apparaat of groep apparaten vervangen. 
  
1. Kies op de pagina **Windows voorbereiden** het tabblad **Apparaten**. 
    
2. Klik op het selectievakje naast een apparaatnaam en kies in het deelvenster **Apparaat** een profiel in de vervolgkeuzelijst **Toegewezen profiel** \> **Opslaan**.
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Een profiel bewerken of verwijderen

Wanneer u een profiel aan een apparaat hebt toegewezen, kunt u dit bijwerken, zelfs als u het apparaat al aan een gebruiker hebt gegeven. Wanneer het apparaat verbinding maakt met internet, wordt de nieuwste versie van uw profiel gedownload tijdens het installatieproces. Als de gebruiker het apparaat herstelt naar de fabrieksinstellingen, worden de nieuwste updates opnieuw naar uw profiel gedownload. 
  
### <a name="edit-a-profile"></a>Een profiel bewerken

1. Kies op de pagina **Windows voorbereiden** het tabblad **Profielen**. 
    
2. Klik op het selectievakje naast een apparaatnaam en werk in het deelvenster **Profiel** de gewenste beschikbare instellingen bij \> **Opslaan**.
    
    Als u dit doet voordat een gebruiker het apparaat verbindt met internet, wordt het profiel toegepast tijdens het installatieproces.
    
### <a name="delete-a-profile"></a>Een profiel verwijderen

1. Kies op de pagina **Windows voorbereiden** het tabblad **Profielen**. 
    
2. Klik op het selectievakje naast een apparaatnaam en klik in het deelvenster **Profiel** op **Profiel verwijderen** \> **Opslaan**.
    
    Wanneer u een profiel verwijdert, wordt dit verwijderd van het apparaat of de groep apparaten waaraan dit was toegewezen.
    
### <a name="remove-a-profile"></a>Een profiel verwijderen

1. Kies op de pagina **Windows voorbereiden** het tabblad **Apparaten**. 
    
2. Klik op het selectievakje naast een apparaatnaam en kies in het deelvenster **Apparaat** de optie **Geen** in de vervolgkeuzelijst **Toegewezen profiel** \> **Opslaan**.
    
