---
title: Prestaties van Exchange Online afstemmen
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
description: Dit artikel bevat algemene tips en koppelingen naar andere informatiebronnen over het verbeteren van de prestaties van Exchange Online.
ms.openlocfilehash: 495b662aa6ef247a5751febbf2d50e1c1f21a44e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689389"
---
# <a name="tune-exchange-online-performance"></a>Prestaties van Exchange Online afstemmen

Dit artikel bevat algemene tips en koppelingen naar andere informatiebronnen over het verbeteren van de prestaties van Exchange Online, met name vóór een migratie. Dit artikel maakt deel uit van het project [netwerk planning en prestaties optimaliseren voor Office 365](https://aka.ms/tune) .
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Aandachtspunten om de prestaties van Exchange Online te verbeteren

Als u de migratie snelheid wilt verbeteren en de bandbreedte beperkingen van uw organisatie voor Exchange Online wilt beperken, kunt u het volgende overwegen:
  
- **De grootte van het postvak verkleinen.** Kleinere postvakgrootte zorgt voor een betere migratie snelheid. 
    
- **Gebruik de mogelijkheden van Postvak verplaatsen met een hybride implementatie van Exchange.** Met een hybride Exchange-implementatie, offline mail (in de vorm van). De OST-bestanden zijn opnieuw te downloaden wanneer u de migratie naar Exchange Online uitvoert. Dit vermindert de vereisten voor het downloaden van de bandbreedte. 
    
- **Gepland postvak wordt verplaatst tijdens perioden van een laag Internet verkeer en een on-premises Exchange-gebruik.** Bij het plannen van verplaatsingsopdrachten worden de migratie verzoeken verzonden naar de proxy voor de Postvak replicatie en mogelijk niet onmiddellijk. 
    
- **De webversie van popouts gebruiken voor de webversie van Outlook.** Met popouts kunt u kleinere en minder geheugen intensiefere versies van bepaalde e-mailberichten in Microsoft Edge of Internet Explorer weergeven door sommige onderdelen op de server weer te geven. Zie voor meer informatie [het artikel Popouts gebruiken om geheugen te verminderen voor het lezen van e-mailberichten](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).


## <a name="general-advice"></a>Algemeen advies

- Zorg ervoor dat DNS-zoekopdracht voor outlook.office.com het MS-datacenter plaats voert op een logische invoerlocatie voor uw locatie.

- Onderzoek postvak cache voor onderzoek en kies de gewenste opties (opnieuw). cache periode, gedeelde Postvak cache, et enzovoort tot).

- Zorg dat uw Outlook-gegevens worden overgezet via VPN-verbindingen (naar een centrale Office) voordat u ze via internet plaatst.

- Zorg ervoor dat uw postvakgegevens voldoen aan de beperkingen voor de map en het item, de bedragen.
    
Zie voor meer informatie over de prestaties van de Exchange-migratie de [migratie prestaties en aanbevolen procedures voor Office 365](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).
  

