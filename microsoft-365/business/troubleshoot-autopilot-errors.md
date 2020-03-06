---
title: Fouten in AutoPilot-apparaten oplossen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Meer informatie over het oplossen van fouten die u mogelijk ziet tijdens het werken met AutoPilot-apparaatbestanden in Microsoft 365 Business.
ms.openlocfilehash: 7569f18097a1f5959b3dd491958c78886e1e05d6
ms.sourcegitcommit: 41c0bc5cf50f4ca63b4286d1ea0f58ab82984b7a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2020
ms.locfileid: "42547466"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Fouten in AutoPilot-apparaten oplossen

## <a name="device-file-error-messages"></a>Foutberichten in apparaatbestanden

Hier vindt u informatie over enkele fouten die u mogelijk ziet tijdens het werken met AutoPilot-apparaatbestanden in Microsoft 365 Business. 
  
|**Foutcode**|**Oplossen om te proberen**|
|:-----|:-----|
|Ongeldige aanvraaginstantie  <br/> |Deze fout moet zelden voorkomen, als u deze fout ziet, probeer de bewerking opnieuw.  <br/> |
|Hardwarehashwaarde voor een apparaat is niet correct.  <br/> |Als u deze fout ziet, betekent dit dat de waarde die u in uw CSV-bestand hebt opgegeven voor de hardwarehash van één apparaat niet correct is. Controleer eerst of de waarde correct is getypt. Als u denkt dat de waarde juist is, maar deze fout nog steeds gebeurt, vraag dan uw hardwareleverancier om hulp.  <br/> |
|Apparaat toegewezen aan een andere tenant  <br/> |Als u deze fout ziet, betekent dit dat de waarde die u in uw CSV-bestand hebt opgegeven voor het serienummer of de productcode van een of meer apparaten niet correct is. Controleer eerst of de waarde correct is getypt. Als u denkt dat de waarde juist is, maar deze fout nog steeds gebeurt, vraag dan uw hardwareleverancier om hulp.  <br/> |
|Het CSV-bestand bevat een ongeldig serienummer of productcode  <br/> |Als u deze fout ziet, betekent dit dat het apparaat dat u probeert te registreren, al is geregistreerd door een andere organisatie. Als u deze fout wilt verhelpen, vraagt u uw hardwareleverancier om hulp.  <br/> |
|Dit apparaat wordt niet ondersteund voor installatie met Behulp van AutoPilot  <br/> | Deze fout betekent dat het apparaat niet voldoet aan de implementatievereisten van AutoPilot. Apparaten moeten aan deze vereisten voldoen:  <br/>  Windows 10 versie 1703 of hoger.  <br/>  Nieuwe apparaten die niet zijn door Windows out-of-box ervaring.  <br/> |
|Apparaat niet gevonden  <br/> |Deze fout betekent dat een of meer apparaten in uw CSV-bestand niet zijn geregistreerd bij uw organisatie. Om dit op te lossen, vraagt u uw hardwareleverancier om hulp.  <br/> |
