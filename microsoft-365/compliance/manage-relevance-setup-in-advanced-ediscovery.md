---
title: Configuratie voor relevantie beheren in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
ROBOTS: NOINDEX, NOFOLLOW
description: Lees de aanbevelingen voor het instellen van relevantie-training in Advanced eDiscovery om bestanden te scoren op hun relevantie en analytische resultaten te genereren.
ms.openlocfilehash: 8ba09babc91f233514cd0195c3e1da08b07ccb3c
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161660"
---
# <a name="manage-relevance-setup-in-advanced-ediscovery-classic"></a>Configuratie voor relevantie beheren in Advanced eDiscovery (klassiek).

> [!NOTE]
> Voor Advanced eDiscovery is een Office 365 E3 vereist met de Advanced Compliance-invoegtoepassing of een E5-abonnement voor uw organisatie. Als u niet beschikt over een van deze abonnementen en Advanced eDiscovery wilt uitproberen, kunt u zich [registreren voor een proefabonnement op Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
 Advanced eDiscovery-relevantietechnologie maakt gebruik van door experts begeleide software voor het scoren van bestanden op hun relevantie. Advanced eDiscovery-relevantie kan worden gebruikt voor beoordeling van vroege cases (ECA), selectie en beoordeling van bestandsvoorbeelden. 
  
 Advanced eDiscovery bevat onderdelen voor de Relevantie-training en het taggen van bestanden die relevant zijn voor een case. Advanced eDiscovery leert van de ingeleerde voorbeelden van relevante en niet-relevante bestanden om Relevantie-scores voor elk bestand te leveren en genereert analytische resultaten die tijdens en na de bestandsbeoordeling kunnen worden gebruikt. 
  
## <a name="guidelines-for-setting-up-relevance-training"></a>Richtlijnen voor het instellen van Relevantie-training

 Selecteer in Advanced eDiscovery in het venster **Cases** een case en klik op **Ga naar case**. Klik op **Relevantie** \> **Configuratie van relevantie**. Volg deze aanbevolen richtlijnen om Relevantie in te stellen. 
  
- **Taggen**: De doeltreffendheid van het iteratieve Relevantie-trainingsproces hangt af van het vermogen van de expert om de bestandssamples met precisie en consistentie te taggen.

- **Problemen met case**:
  
  - Gebruik voor elk probleem dezelfde expert in het hele Relevantie-trainingsproces. Gelijktijdig taggen van hetzelfde probleem door meerdere experts is niet toegestaan.
  
  - Bepaal of elke groep bestanden alleen relevant is voor een specifiek probleem.

  - Als een probleem te algemeen is gedefinieerd, kan Advanced eDiscovery te veel bestanden opleveren die niet relevant zijn. Als een probleem te smal is gedefinieerd, kan het Relevantie-trainingsproces meer tijd in beslag nemen. 

  - Tijdens elke Relevantie-trainingscyclus richt Advanced eDiscovery zich op één actief probleem en worden tussentijdse voorbeeldresultaten dienovereenkomstig weergegeven.

  - In een scenario met meerdere problemen kan in de Samplingmodus een selectie worden gemaakt van problemen die in de verwerking moeten worden opgenomen. Problemen die zijn gedefinieerd als 'uit', worden pas verwerkt als de Samplingmodus is gewijzigd. Een probleem kan voor slechts één expert 'inactief' of 'aan' zijn.

  - Advanced eDiscovery kan worden gebruikt om bestanden met kandidatenrechten te genereren. Stel een afzonderlijk probleem voor bevoegdheden in. Train en kom eerst met een relevante waarde en train vervolgens alleen voor bevoegdheden in de geselecteerde set (laad de set opnieuw als afzonderlijke case). 

  - Batchberekening kan alleen worden uitgevoerd wanneer er geen open voorbeelden zijn (wanneer u op Batchberekening klikt, wordt een lijst weergegeven met gebruikers met open voorbeelden). Als u voorbeelden van andere gebruikers wilt 'sluiten' (deze moeten alleen worden uitgevoerd als deze gebruikers deze voorbeelden niet taggen), kan een beheerder het hulpprogramma 'Relevantie wijzigen' gebruiken met de optie 'Voorbeeld alle gebruikers'.

- **Metagegevens**: Advanced eDiscovery richt zich op inhoud. Metagegevens worden niet als onderdeel van de relevantie-criteria gezien.

- **Rijkheid**: Als de rijkheid voor een probleem na beoordeling kleiner is dan 3%, kunt u overwegen de Relevantie-training te seeden met bekende relevante en niet-relevante bestanden.

- **Bestandsgrootte**: grote bestanden (meer dan 5.242.880 tekens aan uitgepakte tekst) worden genegeerd in Relevantie. De bestanden nemen niet deel aan het Relevantie-trainingsproces en ontvangen geen Relevantiescore na Batchberekening. Bestanden van meer dan 5 MB kunnen worden opgenomen in de Beoordelingsset.

## <a name="setting-up-case-issues"></a>Problemen met het instellen van cases

De parameters die in deze sectie worden beschreven, zijn beschikbaar in Advanced eDiscovery **Relevantie** \> **Configuratie van relevantie**.
  
- Problemen moeten worden toegewezen aan een gebruiker die de bestanden zal trainen.

- Geïmporteerde bestanden moeten vervolgens worden toegevoegd aan de belasting die wordt verwerkt.

- Definieer en organiseer problemen zorgvuldig. Dit kan van invloed zijn op de resultaten van de Relevantie-training.

Nadat parameters zijn ingesteld, kan de revisor/expert de bestanden gaan trainen in het tabblad **Relevantie**.
