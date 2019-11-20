---
title: Fouten in AutoPilot-apparaten oplossen
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Informatie over het oplossen van fouten met AutoPilot-apparaten.
ms.openlocfilehash: 1b5358bd6686c2548e82ec5297ac0ad675835718
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2019
ms.locfileid: "38718694"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Fouten in AutoPilot-apparaten oplossen

## <a name="device-file-error-messages"></a>Foutberichten van apparaatbestand

Hier vindt u informatie over enkele van de fouten die u zien tijdens het werken met AutoPilot-apparaatbestanden in Microsoft 365 Business. 
  
|**Error code**|**Oplossing om te proberen**|
|:-----|:-----|
|Ongeldige aanvraagtekst  <br/> |Deze fout moet zelden gebeuren, als u deze fout ziet, probeer de bewerking opnieuw.  <br/> |
|Hardware-hashwaarde voor een apparaat is niet correct.  <br/> |Als u deze fout ziet, betekent dit dat de waarde die u hebt opgegeven in uw CSV-bestand voor de hardware-hash van een apparaat niet correct is. Controleer eerst of de waarde juist is getypt. Als u denkt dat de waarde juist is, maar deze fout nog steeds optreedt, vraagt u uw hardwareleverancier om hulp.  <br/> |
|Apparaat toegewezen aan een andere Tenant  <br/> |Als u deze fout ziet, betekent dit dat de waarde die u hebt opgegeven in uw CSV-bestand voor het serienummer of de productcode van een of meer apparaten niet correct is. Controleer eerst of de waarde juist is getypt. Als u denkt dat de waarde juist is, maar deze fout nog steeds optreedt, vraagt u uw hardwareleverancier om hulp.  <br/> |
|Het CSV-bestand bevat een ongeldig serienummer of productcode  <br/> |Als u deze fout ziet, betekent dit dat het apparaat dat u probeert te registreren al is geregistreerd door een andere organisatie. U deze fout oplossen door uw hardwareleverancier om hulp te vragen.  <br/> |
|Dit apparaat wordt niet ondersteund voor Setup met behulp van AutoPilot  <br/> | Deze fout betekent dat het apparaat niet voldoet aan de vereisten voor de AutoPilot-implementatie. Apparaten moeten aan deze vereisten voldoen:  <br/>  Windows 10 versie 1703 of hoger.  <br/>  Nieuwe apparaten die niet via Windows out-of-Box-ervaring.  <br/> |
|Apparaat niet gevonden  <br/> |Deze fout betekent dat een of meer apparaten in uw CSV-bestand is niet geregistreerd voor uw organisatie. Om dit op te lossen, vraagt u uw hardwareleverancier om hulp.  <br/> |
