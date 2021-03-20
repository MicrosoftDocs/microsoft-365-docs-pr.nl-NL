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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Meer informatie over het maken van een CSV-bestand voor AutoPilot in Microsoft 365 voor Bedrijven.
ms.openlocfilehash: 78a9012bac054329bdb87b02757f49f30dd44f65
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914736"
---
# <a name="device-list-csv-file"></a>CSV-bestand met apparatenlijst

## <a name="device-list-csv-file-format"></a>Bestandsindeling van .csv-bestand met apparatenlijst

Voor het beheren en implementeren van apparaten via Windows Autopilot hebt u een .csv-bestand nodig dat specifieke informatie over de apparaten bevat.
  
De kolommen in het apparatenlijstbestand moeten de volgende kopteksten hebben, in de opgegeven volgorde:
  
- Kolom A: Serienummer van apparaat

- Kolom B: leeg laten

- Kolom C: Hardware-hash

U kunt deze informatie van uw hardwareleverancier krijgen of u kunt het [Get-WindowsAutoPilotInfo-PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken, waarmee een CSV-bestand wordt gegenereerd. 

Wanneer u apparaten toevoegt, moet u ze ook toevoegen aan een profiel. Een profiel wordt gebruikt om AutoPilot-implementatieprofielen toe te passen op een apparaat of een groep apparaten.
  
## <a name="related-articles"></a>Verwante artikelen

[Microsoft 365 voor bedrijven-documentatie en -bronnen](../../business/index.yml)
  
[Aan de slag met Microsoft 365 voor Bedrijven](../../business/microsoft-365-business-overview.md)
  
[Microsoft 365 voor Bedrijven beheren](../../business/manage.md)
