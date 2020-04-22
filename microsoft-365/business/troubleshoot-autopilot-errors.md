---
title: Fouten in AutoPilot-apparaten oplossen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Meer informatie over het oplossen van fouten die u zien tijdens het werken met AutoPilot-apparaatbestanden in Microsoft 365 Business Premium.
ms.openlocfilehash: 0c0742e5bf17c85cedfb421cabfd87c0e2184ba5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635039"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Fouten in AutoPilot-apparaten oplossen

## <a name="device-file-error-messages"></a>Foutberichten voor apparaatbestanden

Hier vindt u informatie over enkele fouten die u mogelijk ziet tijdens het werken met AutoPilot-apparaatbestanden in Microsoft 365 Business Premium. 
  
|**Foutcode**|**Oplossing om te proberen**|
|:-----|:-----|
|Ongeldige aanvraaginstantie  <br/> |Deze fout moet zelden gebeuren, als u deze fout ziet, probeer de bewerking opnieuw.  <br/> |
|De waarde van hardwarehash voor een apparaat is niet correct.  <br/> |Als u deze fout ziet, betekent dit dat de waarde die u in uw CSV-bestand hebt opgegeven voor de hardwarehash van één apparaat niet correct is. Controleer eerst of de waarde correct is getypt. Als u denkt dat de waarde juist is, maar deze fout nog steeds gebeurt, vraag uw hardwareleverancier om hulp.  <br/> |
|Apparaat toegewezen aan een andere tenant  <br/> |Als u deze fout ziet, betekent dit dat de waarde die u in uw CSV-bestand hebt opgegeven voor het serienummer of de productcode van een of meer apparaten niet correct is. Controleer eerst of de waarde correct is getypt. Als u denkt dat de waarde juist is, maar deze fout nog steeds gebeurt, vraag uw hardwareleverancier om hulp.  <br/> |
|Het CSV-bestand bevat een ongeldig serienummer of productcode  <br/> |Als u deze fout ziet, betekent dit dat het apparaat dat u probeert te registreren al is geregistreerd door een andere organisatie. Als u deze fout wilt oplossen, vraagt u uw hardwareleverancier om hulp.  <br/> |
|Dit apparaat wordt niet ondersteund voor het instellen met Behulp van AutoPilot  <br/> | Deze fout betekent dat het apparaat niet voldoet aan de implementatievereisten van AutoPilot. Apparaten moeten aan deze vereisten voldoen:  <br/>  Windows 10 versie 1703 of hoger.  <br/>  Nieuwe apparaten die niet zijn door Windows out-of-box ervaring.  <br/> |
|Apparaat niet gevonden  <br/> |Deze fout betekent dat een of meer apparaten in uw CSV-bestand niet zijn geregistreerd bij uw organisatie. Om dit op te lossen, vraag uw hardwareleverancier om hulp.  <br/> |
