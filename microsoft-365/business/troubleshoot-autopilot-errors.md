---
title: Fouten in AutoPilot-apparaten oplossen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Informatie over het oplossen van problemen met automatische piloot fouten in het bestand.
ms.openlocfilehash: 9b8d8ab424dd3189ff5c228dab8f5c513ff5dafc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/28/2018
ms.locfileid: "26982742"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Fouten in AutoPilot-apparaten oplossen

## <a name="device-file-error-messages"></a>Foutberichten van apparaat-bestand

Hier volgt informatie over enkele van de fouten ziet u tijdens het werken met automatische piloot apparaatbestanden in Microsoft 365 Business. 
  
|**Foutcode**|**Oplossing om te proberen**|
|:-----|:-----|
|Ongeldige aanvraag body  <br/> |Deze fout zelden, er moet gebeuren als u deze fout ziet, probeer het opnieuw.  <br/> |
|Hardware-hash-waarde voor een apparaat is niet juist.  <br/> |Als u deze fout ziet, betekent dit dat de waarde die u hebt opgegeven in het CSV-bestand voor de hardware-hash van een apparaat niet correct is. Controleer eerst of de waarde juist is getypt. Als u denkt dat de waarde juist is, maar deze fout nog steeds gebeurt, uw hardwareleverancier om hulp vragen.  <br/> |
|Apparaat is toegewezen aan een andere huurder  <br/> |Als u deze fout ziet, betekent dit dat de waarde die u hebt opgegeven in het CSV-bestand voor het serienummer of de productcode van een of meer apparaten niet correct is. Controleer eerst of de waarde juist is getypt. Als u denkt dat de waarde juist is, maar deze fout nog steeds gebeurt, uw hardwareleverancier om hulp vragen.  <br/> |
|Het CSV-bestand bevat een ongeldig serieel getal of een productcode  <br/> |Als u deze fout betekent dat het apparaat dat u opgetreden bij een poging om te registreren al door een andere organisatie is geregistreerd. U kunt dit oplossen door de hardwareleverancier om hulp te vragen.  <br/> |
|Dit apparaat wordt niet ondersteund voor installatie via automatische piloot  <br/> | Deze fout geeft aan dat het apparaat voldoet niet aan de vereisten voor het implementeren van automatische piloot. Apparaten dient te voldoen aan deze vereisten:  <br/>  Windows 10 versie 1703 of hoger.  <br/>  Nieuwe apparaten die niet de Out-of-Box Experience van Windows hebben doorlopen.  <br/> |
|Apparaat is niet gevonden  <br/> |Deze fout geeft aan dat een of meer apparaten in uw CSV-bestand is niet geregistreerd voor uw organisatie. U kunt dit oplossen door de hardwareleverancier om hulp te vragen.  <br/> |
   
