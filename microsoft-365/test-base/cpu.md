---
title: CPU-regressieanalyse
description: Regressieresultaten en metrische gegevens voor CPU-verbruik
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: bc28c128902ae353fb35c3b6010856ade934a436
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322719"
---
# <a name="intelligent-cpu-regression-analysis"></a>Intelligente CPU-regressieanalyse

Cpu-gebruik kan aangeven of een toepassing wordt beïnvloed door een update van het besturingssysteem. 

Test Base voor Microsoft 365 biedt softwareontwikkelaars inzicht in regressies van cpu-prestaties die optreden wanneer hun toepassing wordt uitgevoerd op verschillende versies van een komende update van het besturingssysteem Windows besturingssysteem. 

Met deze CPU-regressies kunnen ontwikkelaars toepassingsproblemen (en mogelijke fouten) detecteren en oplossen voordat de os-update breed wordt geïmplementeerd, waardoor een slechte ervaring voor de eindgebruiker wordt voorkomen.


### <a name="how-cpu-regression-analysis-works"></a>Hoe cpu-regressieanalyse werkt ###

Als testbasisgebruiker kunt u de binaries van uw toepassing uploaden (in één .zip-bestand), samen met bijbehorende testscripts en de versie van het Windows-besturingssysteem selecteren waarmee u de toepassing wilt testen in de Test Base-portal in Azure. 

De Test Base-service voert vervolgens de testscripts uit en voert de **CPU-regressieanalyse uit.** 

De service controleert of het CPU-gebruik voor de toepassing in de pre-releaseversie van de update voor het doelbesturingssysteem in overeenstemming is met het CPU-gebruik voor de uitgebrachte versie van het besturingssysteem. 

CPU-gebruik is geen vergelijking van 100% like-for-like, omdat de processen die op de twee versies van het besturingssysteem worden uitgevoerd, al dan niet exact overeenkomen vanwege verschillende besturingssysteemversies. De analyse die door Test Base wordt uitgevoerd, kan echter laten zien of het CPU-gebruik voor uw toepassing wordt beïnvloed door een aanstaande OS-update en specifiek welke processen zijn teruggegaan van eerdere testuitloops.

In de onderstaande momentopname zijn er twee besturingssysteemreleases waarmee de CPU-gebruik wordt vergeleken voor dezelfde toepassing. 
-   Op het tabblad CPU-gebruik worden de boven- en ondergrens van het gebruik weergegeven voor beide versies van respectievelijk 90e en 10e percentiel. 
-   De grafieken geven de tijdreeks cpu-gebruik weer, samen met het gemiddelde gebruik. 

Klanten kunnen nu de functionaliteit gebruiken om te bepalen of het CPU-gebruik van hun toepassing wordt beïnvloed door os-updates en specifiek welke processen zijn teruggegaan van de vorige uitvoering.


![CPU-regressieanalyse](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a>Relevante procesidentificatie ###

Hier bespreken we hoe u regressieve processen in de toepassing kunt identificeren. 

Als u prestatie-regressie analyseert, moet u verschillende soorten prestatietellers bijhouden voor elk proces dat tijdens de test op een virtuele computer wordt uitgevoerd. 

Een dergelijke analyse legt een groot aantal variabelen vast voor een groot aantal processen voor een bepaalde toepassing. Niet alle processen zijn gekoppeld aan een uitvoering of toepassing. Om deze uitdaging te voltooien, wordt een algoritme voor het rangschikken van gegevens met behulp van kans- en informatietheorie toegepast om erachter te komen welke processen het meest relevant zijn voor een bepaalde toepassing. 

Een toepassing kan worden beschouwd als één type afzonderlijke willekeurige variabele, terwijl een proces wordt beschouwd als een ander soort discrete willekeurige variabele. De associatie van de twee willekeurige variabelen wordt gemeten met behulp van voorwaardelijke waarschijnlijkheid voor relevantie. 

Processen worden vervolgens weergegeven in de volgorde van hun relevantie voor elke toepassing. U kunt ook een subset met processen favoriet maken die standaard kunnen worden gecontroleerd, samen met relevante processen voor regressieanalyse van cpu's. Wanneer een regressie is gedetecteerd, kunt u de Windows Performance Analyzer downloaden en redenen voor regressies van de CPU-prestaties analyseren. 

Met Windows Performance Analyzer wordt etl (Event Trace Log) als invoer gebruikt en deze ETL-bestanden zijn beschikbaar in de logboekbestanden die kunnen worden gedownload voor testritten op de portal. Als u meer wilt weten over het debuggen van cpu-prestaties, bekijkt u de documentatie Windows Performance Analyzer.

