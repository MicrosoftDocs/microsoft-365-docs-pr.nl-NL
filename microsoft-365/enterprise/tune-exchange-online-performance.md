---
title: Voorwaardelijke opmaak op basis van een formule die Ja of Nee oplevert
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: Dit artikel bevat algemene tips en koppelingen naar andere bronnen waarin wordt beschreven hoe u de prestaties van Exchange Online.
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909440"
---
# <a name="tune-exchange-online-performance"></a>Voorwaardelijke opmaak op basis van een formule die Ja of Nee oplevert

Dit artikel bevat algemene tips en koppelingen naar andere bronnen waarin wordt beschreven hoe u de prestaties van Exchange Online kunt verbeteren, met name voor een migratie. Dit artikel maakt deel uit van de [netwerkplanning en prestatieafstemming voor Office 365](./network-planning-and-performance.md) project.
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Dingen waar u rekening mee moet houden om de prestaties Exchange Online verbeteren

Als u de migratiesnelheid wilt verbeteren en de bandbreedtebeperkingen voor uw organisatie wilt beperken voor Exchange Online, gaat u als volgt te werk:
  
- **Verklein de grootte van het postvak.** Kleinere postvakken verbeteren de migratiesnelheid. 
    
- **Gebruik de mogelijkheden voor het verplaatsen van postvakken met een Exchange hybride implementatie.** Met een Exchange hybride implementatie, offline e-mail (in de vorm van . OST-bestanden) hoeft u niet opnieuw te downloaden wanneer u migreert naar Exchange Online. Hierdoor worden de vereisten voor downloadbandbreedte aanzienlijk verminderd. 
    
- **Plan dat postvak wordt verplaatst tijdens perioden met weinig internetverkeer en lage on-premises Exchange gebruik.** Wanneer de planning wordt verplaatst, worden migratieaanvragen verzonden naar de postvakreplicatieproxy en vinden ze mogelijk niet onmiddellijk plaats. 
    
- **Gebruik lean pop-outs voor Outlook op het web.** Lean pop-outs bieden kleinere, minder geheugenintensieve versies van bepaalde e-mailberichten in Microsoft Edge of Internet Explorer door bepaalde onderdelen op de server weer te geven. Zie Lean pop-outs gebruiken om het geheugen te verminderen dat wordt gebruikt [bij het lezen van e-mailberichten](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)voor meer informatie.


## <a name="general-advice"></a>Algemeen advies

- Zorg ervoor dat DNS-opzoekactie outlook.office.com het MS-datacenter binnenkomt op een logische invoerlocatie voor uw locatie.

- Zoek postvak caching en kies de juiste opties (opnieuw. caching period, shared mailbox caching, et cetera).

- Zorg ervoor Outlook dat uw gegevens niet via VPN-verbindingen (naar een centraal kantoor) worden overgenomen voordat deze via internet worden overgenomen.

- Zorg ervoor dat uw postvakgegevens voldoen aan de beperkingen voor map- en itembedragen.
    
Zie voor meer informatie Exchange migratieprestaties Office 365 [migratieprestaties en best practices.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)
