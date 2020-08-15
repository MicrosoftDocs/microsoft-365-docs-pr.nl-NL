---
title: Gegevens tolerantie in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In dit artikel vindt u meer informatie over het ontwerp en de beginselen van gegevens tolerantie en herstel in Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e6ca643fe9842a71102fbabd3c05324ba52b70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689139"
---
# <a name="data-resiliency-in-microsoft-365"></a>Gegevens tolerantie in Microsoft 365

Aangezien de complexe aard van Cloud Computing verloopt, is Microsoft mindful dat het niet zo is als het niet is gelukt wat er mis is, maar wanneer alles. We ontwerpen onze cloudservices om de betrouwbaarheid te vergroten en de negatieve gevolgen voor klanten te minimaliseren wanneer alles mis gaat. We zijn verhuisd buiten de traditionele strategie voor het vertrouwen op complexe fysieke infrastructuur, en we hebben de redundantie rechtstreeks in onze cloudservices ontwikkeld. We gebruiken een combinatie van minder complexe fysieke infrastructuur en intelligente software waarmee gegevens tolerantie in onze services wordt samengesteld en de beschikbaarheid van onze klanten wordt verzorgd. 

## <a name="resiliency-and-recoverability-are-built-in"></a>De tolerantie en herstelmogelijkheden zijn ingebouwd 

Het maken van een tolerantie en herstel begint met de hypothese dat de onderliggende infrastructuur en processen niet op een bepaald moment worden uitgevoerd: de hardware (infrastructuur) mislukt, dat mensen fouten ondervinden en de softwarefouten bevat. Hoewel het niet zou zijn dat softwareontwikkelaars van deze zaken vóór de Cloud konden nadenken, is het aan te raden dit probleem in een typische IT-implementatie te bedenken.

- Voor de eerste, hardware-en infrastructuur beveiliging zijn belangrijk. Dit was datacenters met een Data betrouwbaarheid van 99,99% nodig, en servers zijn geïmplementeerd met op de client gebaseerde clustering, Dual-voedings apparatuur, twee netwerkinterfaces en de like. 
- Tweede, proces is het allergrootste. IT-teams ondervinden strikte procedures, wijziging van Vensters, en er waren vaak grote kosten voor project management. 
- Derde, de implementatie plaatsvond op een ijsazijn. U kunt code implementeren zonder dat dit van invloed is op de bron die is gewacht op een patch versie, en de belangrijkste versie van de hardware vervangen door de vervangende outlay. Daarnaast is het niet mogelijk om een probleem op te lossen. Daarom zouden de meeste IT-organisaties alleen primaire releases implementeren om te voorkomen dat het werk actueel blijft. 
- Tot slot is de schaal van geïmplementeerde systemen, alsook het niveau van de onderling verbonden hoeveelheid, historisch veel kleiner dan de schaal. 

Vandaag verwachten klanten continue innovatie van Microsoft zonder de kwaliteit te leveren, en dit is een van de redenen waarom de services en software van Microsoft zijn gebouwd met tolerantie en herstel. 

## <a name="microsoft-365-data-resiliency-principles"></a>Microsoft 365 gegevens tolerantie beginselen

Met tolerantie wordt de mogelijkheid van een cloudservice op basis van bepaalde soorten storingen, en nog steeds volledig functioneel van de perspectief van de klant. Gegevens tolerantie houdt in dat de kritieke klantgegevens ongewijzigd blijven en ongewijzigd blijven, ongeacht wat er gebeurt in Microsoft 365. Om die kant zijn de Microsoft 365-Services ontworpen rond vijf specifieke tolerantie beginselen:

- Er bestaan belangrijke en niet-kritieke gegevens. Niet-kritieke gegevens (u kunt bijvoorbeeld opgeven of een bericht is gelezen) kan in scenario's met een zeldzame storing worden verwijderd. Belangrijke gegevens (bijvoorbeeld klantgegevens, zoals e-mailberichten) moeten tegen extreme kosten beschermd zijn. Als ontwerp doelstelling zijn verzonden e-mailberichten altijd essentieel, en zaken alsof een bericht is gelezen is niet essentieel. 
- Kopieën van klantgegevens moeten worden gescheiden in verschillende fout zones of zo veel mogelijk foutdomeinen (bijvoorbeeld datacenters, toegankelijk via enkele referenties (proces, server of operator)) om de fout te isoleren. 
- Cruciale klantgegevens moeten worden gecontroleerd op fouten in het gebied van atoom, consistentie, isolatie, duurzaamheid (zuur). 
- Klantgegevens moeten tegen beschadiging zijn beschermd. Het moet actief worden gecontroleerd of gecontroleerd, hersteld en hersteld. 
- De meeste gegevensverlies resultaten van klant acties, zodat klanten hun eigen gebruikers kunnen terugzetten met behulp van een GUI, zodat ze per ongeluk verwijderde items kunnen terugzetten. 
 
Door het maken van onze cloudservices aan deze principes, met krachtige testen en validering, kan Microsoft 365 de vereisten van klanten vergaderen en groter maken terwijl er een platform voor voortdurende innovatie en verbetering wordt gegarandeerd. 

## <a name="related-links"></a>Verwante koppelingen

- [Omgaan met gegevensbeschadiging](microsoft-365-dealing-with-data-corruption.md)
- [Malware en Ransomware-beveiliging](microsoft-365-malware-and-ransomware-protection.md)
- [Volgen en zelfherstel](microsoft-365-monitoring-and-self-healing.md)
- [Gegevens tolerantie Exchange](microsoft-365-exchange-data-resiliency.md)
