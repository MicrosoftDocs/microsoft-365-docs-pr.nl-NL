---
title: Inzicht krijgen in beoordeling in relevantie in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: Krijg een overzicht van de evaluatiefase en de rol ervan bij het bepalen van de rijkheid van problemen tijdens de relevantietraining in Microsoft 365 Advanced eDiscovery.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8930f362d217ed87fc0e16b88b7588ab781164e8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161676"
---
# <a name="assessment-in-the-relevance-module-in-advanced-ediscovery"></a>Beoordeling in de module Relevantie in Advanced eDiscovery
  
Advanced eDiscovery maakt vroegtijdige beoordeling mogelijk, bijvoorbeeld voor de gedefinieerde problemen en de gegevens die voor een zaak zijn geïmporteerd. Advanced eDiscovery kan de expert beslissingen nemen over een goedgekeurde benadering en deze beslissingen toepassen op het documentbeoordelingsproject.
  
## <a name="understanding-assessment"></a>Beoordeling begrijpen

In Beoordeling bekijkt de expert een willekeurige set van ten minste 500 bestanden, die worden gebruikt om de rijkheid van de problemen te bepalen en om statistieken te maken die de trainingsresultaten weerspiegelen. De beoordeling is succesvol wanneer er voldoende relevante bestanden worden gevonden om een statistisch niveau te bereiken dat Advanced eDiscovery Relevantie helpt om nauwkeurige statistieken te verstrekken en om het stabilisatiepunt in het trainingsproces effectief te bepalen. 
  
Hoe hoger het aantal relevante bestanden in de beoordelingsset, hoe nauwkeuriger de statistieken en de effectiviteit van het stabiliteitsalgoritme. Het aantal relevante bestanden in de beoordelingsbestanden is afhankelijk van de rijkheid van het probleem. Rijkheid is het geschatte percentage relevante bestanden in de set dat relevant is voor een probleem. Problemen met een hogere rijkheid bereiken sneller een hoger aantal relevante bestanden dan problemen met een lagere rijkheid. Problemen met een zeer lage rijkheid (bijvoorbeeld 2% of minder) vereisen een zeer grote evaluatieset om een aanzienlijk aantal relevante bestanden te bereiken.
  
De statistieken, die worden weergegeven op de tabbladen Bijhouden en beslissen tijdens de training en na batchberekening, bevatten schattingen van inroepen voor verschillende revisiesets. In statistieken omvatten schattingen die zijn gebaseerd op een steekproefset (in dit geval de beoordelingsbestanden) de foutmarge en het betrouwbaarheidsniveau van die foutmarge. Geschatte terugroeping van 80% kan bijvoorbeeld een foutmarge van plus of min 5% hebben met een betrouwbaarheidsniveau van 95%. Dit betekent dat de geschatte terugroepactie in feite 75%-85% is en dat deze schatting 95% vertrouwen heeft. Hoe groter de beoordelingsset, hoe kleiner de foutmarge en hoe nauwkeuriger de statistieken. 
  
Nadat de expert een eerste evaluatieset van 500 bestanden heeft beoordeeld, kan relevantie de huidige foutmarge van de inroepwaarden bepalen. Relevantie raadt ook een standaardmarge aan om de beoordelingsset te optimaliseren. Dit zijn enkele voorbeelden:
  
- Als de beoordelingsset al een foutmarge van plus of min 10% oplevert, wordt u aangeraden door te gaan met de training (er is geen extra beoordeling nodig). 

- Als de beoordelingsset een foutmarge van plus of min 13% oplevert, kan relevantie het aanbevelen om een andere set beoordelingsbestanden te bekijken om een kleinere marge te bereiken. 

- Als de rijkheid zeer laag is, kan relevantie het stoppen van de beoordeling aanbevelen, ook al is de foutmarge groot (waardoor statistieken onpraktisch zijn), omdat de beoordelingsset die nodig is om een bruikbare foutmarge te bereiken te groot is.

Elk probleem heeft een eigen rijkheid, huidige foutmarge en heeft als gevolg daarvan een geschat aantal extra beoordelingsbestanden. De volgende evaluatieset wordt gemaakt op basis van het maximum aantal bestanden (tot 1.000 in één set).
  
U kunt de aanbevelingen voor relevantie accepteren of de huidige foutmarge aanpassen aan uw behoeften. De standaard huidige foutmarge wordt bepaald voor inroepen bij gelijk aan of boven 75%.
  
> [!NOTE]
> De evaluatiefase kan worden overgeslagen, op het tabblad Relevantie bijhouden in  de uitgebreide weergave voor een probleem, door het selectievakje Beoordeling per probleem uit te wissen en vervolgens op 'alle problemen'. **\>** Hierdoor zijn er geen statistieken voor dit probleem. U kunt **het selectievakje** Beoordeling alleen wissen voordat de beoordeling wordt uitgevoerd. Als er meerdere problemen zijn in een zaak, wordt de beoordeling alleen overgeslagen als het selectievakje voor elk probleem is gewist.
