---
title: Fouten in AutoPilot-apparaten oplossen
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Meer informatie over het oplossen van fouten die u mogelijk ziet tijdens het werken met AutoPilot-apparaatbestanden in Microsoft 365 Business Premium.
ms.openlocfilehash: 1078ab74b07952e4bb565555a081b98ecce9db5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578082"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Fouten in AutoPilot-apparaten oplossen

## <a name="device-file-error-messages"></a>Foutberichten van apparaatbestand

Hier vindt u informatie over enkele fouten die u mogelijk ziet tijdens het werken met AutoPilot-apparaatbestanden in Microsoft 365 Business Premium. 
  
|**Foutcode**|**Fix om te proberen**|
|:-----|:-----|
|Ongeldige aanvraag  <br/> |Deze fout gebeurt zelden, als u deze fout ziet, probeert u de bewerking opnieuw.  <br/> |
|De hashwaarde voor hardware voor een apparaat is niet correct.  <br/> |Als u deze fout ziet, betekent dit dat de waarde die u hebt opgegeven in uw CSV-bestand voor de hardware-hash van één apparaat, niet juist is. Controleer eerst of de waarde correct is getypt. Als u denkt dat de waarde juist is, maar deze fout nog steeds wordt weergegeven, vraagt u uw hardwareleverancier om hulp.  <br/> |
|Apparaat dat is toegewezen aan een andere tenant  <br/> |Als u deze fout ziet, betekent dit dat de waarde die u hebt opgegeven in uw CSV-bestand voor het serienummer of de productcode van een of meer apparaten niet juist is. Controleer eerst of de waarde correct is getypt. Als u denkt dat de waarde juist is, maar deze fout nog steeds wordt weergegeven, vraagt u uw hardwareleverancier om hulp.  <br/> |
|Het CSV-bestand bevat een ongeldig serienummer of productcode  <br/> |Als u deze fout ziet, betekent dit dat het apparaat dat u wilt registreren al is geregistreerd door een andere organisatie. Als u deze fout wilt oplossen, vraagt u uw hardwareleverancier om hulp.  <br/> |
|Dit apparaat wordt niet ondersteund voor het instellen met Behulp van AutoPilot  <br/> | Deze fout betekent dat het apparaat niet voldoet aan de implementatievereisten voor AutoPilot. Apparaten moeten aan deze vereisten voldoen:  <br/>  Windows 10 versie 1703 of hoger.  <br/>  Nieuwe apparaten die nog niet zijn Windows-out-of-box-ervaring.  <br/> |
|Apparaat niet gevonden  <br/> |Deze fout betekent dat een of meer apparaten in uw CSV-bestand niet zijn geregistreerd bij uw organisatie. Als u dit wilt oplossen, vraagt u uw hardwareleverancier om hulp.  <br/> |
