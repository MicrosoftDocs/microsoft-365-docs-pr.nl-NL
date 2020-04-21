---
title: CSV-bestand met apparatenlijst
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Meer informatie over het maken van een CSV-bestand voor AutoPilot in Microsoft 365 voor bedrijven.
ms.openlocfilehash: b1154d639ba23180f637520750d94f00e997cfc4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627858"
---
# <a name="device-list-csv-file"></a>CSV-bestand met apparatenlijst

## <a name="device-list-csv-file-format"></a>Bestandsindeling van .csv-bestand met apparatenlijst

Voor het beheren en implementeren van apparaten via Windows Autopilot hebt u een .csv-bestand nodig dat specifieke informatie over de apparaten bevat.
  
De kolommen in het apparatenlijstbestand moeten de volgende kopteksten hebben, in de opgegeven volgorde:
  
- Kolom A: Serienummer van apparaat

- Kolom B: laat leeg

- Kolom C: Hardware-hash

U kunt deze informatie van uw hardwareleverancier krijgen of u kunt het [Get-WindowsAutoPilotInfo-PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken, waarmee een CSV-bestand wordt gegenereerd. 

Wanneer u apparaten toevoegt, moet u ze ook toevoegen aan een profiel. Een profiel wordt gebruikt om AutoPilot-implementatieprofielen toe te passen op een apparaat of een groep apparaten.
  
## <a name="related-articles"></a>Verwante artikelen

[Microsoft 365 voor bedrijfsdocumentatie en -bronnen](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Aan de slag met Microsoft 365 voor bedrijven](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[Microsoft 365 voor bedrijven beheren](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
