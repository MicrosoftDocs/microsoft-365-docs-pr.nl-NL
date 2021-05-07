---
title: Taken beheren in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Advanced eDiscovery taken kunt u de status bijhouden van langlopende processen die betrekking hebben op het uitvoeren van verschillende Advanced eDiscovery taken.
ms.openlocfilehash: 27ac98d1f98e85800c8ca3dfc91cc5e0803ae2e8
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "52162506"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>Taken beheren in Advanced eDiscovery

Hier is een lijst met de taken (die meestal langlopende processen  zijn) die worden bijgespoord op het tabblad Taken van een zaak in Advanced eDiscovery. Deze taken worden geactiveerd door gebruikersacties bij het gebruik en het beheren van cases.

| Taaktype           | Beschrijving     |
| :----------------- | :----------     |
|Gegevens toevoegen aan een revisieset | Een gebruiker voegt een verzameling toe aan een revisieset. Deze taak bestaat uit twee subtaken: </br>• **Exporteren:** er wordt een lijst met items in de verzameling gegenereerd. </br>• **Opname & Indexering:** de items in de verzameling die overeenkomen met de zoekquery, worden gekopieerd naar een Azure Storage-locatie (in een proces dat opname wordt *genoemd)* en vervolgens worden de items op de Azure Storage-locatie opnieuw geïndexeerd. Deze nieuwe index wordt gebruikt bij het opvragen en analyseren van items in de gegevensset. </br></br>Zie Zoekresultaten toevoegen aan een [revisieset voor meer informatie.](add-data-to-review-set.md) |
|Gegevens toevoegen aan een andere revisieset | Een gebruiker voegt documenten uit één revisieset toe aan een andere revisieset in hetzelfde geval. Zie Gegevens toevoegen aan een revisieset uit een andere revisieset voor [meer informatie.](add-data-to-review-set-from-another-review-set.md)|
|Niet-Microsoft 365 toevoegen aan een revisieset | Een gebruiker uploadt niet-Microsoft 365 gegevens naar een revisieset. De gegevens worden ook geïndexeerd tijdens dit proces. Bestanden van een on-premises bestandsserver of een clientcomputer worden bijvoorbeeld geüpload naar een revisieset. Zie [Niet-Microsoft 365 gegevens laden in een revisieset voor meer informatie.](load-non-office-365-data-into-a-review-set.md)| 
|Herstelgegevens toevoegen aan een revisieset | Gegevens met verwerkingsfouten worden gesaneerd en weer in een revisieset geladen. Zie voor meer informatie:</br>• [Herstelfout bij het verwerken van gegevens](error-remediation-when-processing-data-in-advanced-ediscovery.md)</br>• [Herstel van fout met één item](single-item-error-remediation.md)| 
|Laadsets vergelijken | Een gebruiker bekijkt de verschillen tussen verschillende laadsets in een revisieset. Een laadset is een exemplaar van het toevoegen van gegevens aan een revisieset. Als u bijvoorbeeld de resultaten van twee verschillende zoekopdrachten toevoegt aan dezelfde revisieset, zou elke zoekopdracht een belastingset vertegenwoordigen. |
|Gespreksreconstructie|Wanneer een gebruiker de resultaten van een zoekopdracht toevoegt aan een gespreksbeoordelingsset, worden chatgesprekken (ook wel discussielijngesprekken *genoemd)* in services zoals Microsoft Teams gereconstrueerd in een PDF-bestand. Deze taak wordt ook geactiveerd wanneer een gebruiker op Actie klikt **> Gespreks-PDF's** maken in een revisieset. Zie Gesprekken bekijken [in Advanced eDiscovery.](conversation-review-sets.md)
|Geacacteerde documenten converteren naar PDF|Nadat een gebruiker een document in een revisieset heeft geannoteerd en een deel ervan redacteert, kunnen ze ervoor kiezen om het opnieuw geschreven document te converteren naar een PDF-bestand. Dit zorgt ervoor dat het opnieuw uitgevoerde gedeelte niet zichtbaar is als het document wordt geëxporteerd voor presentatie. Zie Documenten weergeven [in een revisieset](annotating-and-redacting-documents.md)voor meer informatie. |
|Zoekresultaten schatten | Nadat een gebruiker een conceptverzameling heeft gemaakt en uitgevoerd of opnieuw heeft uitgevoerd, zoekt het zoekprogramma in de index naar items die overeenkomen met de zoekquery en wordt een schatting gemaakt met het aantal en de totale grootte van alle items door de zoekopdracht en het aantal gezochte gegevensbronnen.  Zie Gegevens verzamelen [voor een zaak voor meer informatie.](collecting-data-for-ediscovery.md) | 
|Gegevens voorbereiden voor export | Een gebruiker exporteert documenten uit een revisieset. Wanneer het exportproces is voltooid, kunnen ze de geëxporteerde gegevens downloaden naar een lokale computer. Zie Case data exporteren voor [meer informatie.](exporting-data-ediscover20.md) | 
|Voorbereidingen treffen voor foutoplossing |Wanneer een gebruiker een bestand selecteert en een nieuwe fout  herstelt in de weergave Fout op het tabblad Verwerking van een zaak, is de eerste stap in het proces het uploaden van het bestand met de verwerkingsfout naar een Azure Storage-locatie in de Microsoft-cloud. Deze taak houdt de voortgang van het uploadproces bij. Zie Foutremediatie bij het verwerken van gegevens voor meer informatie over de [foutremediatiewerkstroom.](error-remediation-when-processing-data-in-advanced-ediscovery.md) | 
|Zoekvoorbeeld voorbereiden | Nadat een gebruiker een nieuwe conceptverzameling heeft gemaakt en uitgevoerd (of een bestaande conceptverzameling opnieuw uitvoert), wordt met het zoekhulpmiddel een voorbeeld van items voorbereid (die overeenkomen met de zoekquery) die kunnen worden bekeken. Als u een voorbeeld van zoekresultaten bekijkt, kunt u de effectiviteit van de zoekopdracht bepalen.  Zie Gegevens verzamelen [voor een zaak voor meer informatie.](collecting-data-for-ediscovery.md#view-search-results-and-statistics) | 
|Gegevens van beheerders opnieuw indexeren | Wanneer u een bewaarder toevoegt aan een zaak, worden alle gedeeltelijk geïndexeerde items in de geselecteerde gegevensbronnen van de bewaarder opnieuw geïndexeerd door een proces genaamd *Geavanceerd indexeren.* Deze taak wordt ook geactiveerd wanneer  u op **Index bijwerken** klikt op het tabblad Verwerking van een zaak en wanneer u de index voor een specifieke bewaarder bijwerkt op de flyoutpagina met beheerderseigenschappen. Zie Geavanceerde [indexering van bewaargegevens](indexing-custodian-data.md)voor meer informatie.
|Analyses uitvoeren | Een gebruiker analyseert gegevens in een revisieset door Advanced eDiscovery analysehulpmiddelen uit te voeren, zoals near duplicate detection, e-mailthreading analysis en themaanalyse. Zie Gegevens analyseren [in een revisieset](analyzing-data-in-review-set.md)voor meer informatie. | 
|Documenten labelen | Deze taak wordt geactiveerd wanneer een gebruiker klikt op **Taak labelen starten** in **het deelvenster Labelen** bij het controleren van documenten in een revisieset. Een gebruiker kan deze taak starten nadat hij documenten in een revisieset heeft gelabeld en deze vervolgens bulksgewijs selecteert in het weergavedocumentvenster. Zie Documenten [taggen in een revisieset](tagging-documents.md)voor meer informatie. | 
|||

## <a name="job-status"></a>Taakstatus

In de volgende tabel worden de verschillende statusstatussen voor taken beschreven.

| Status           | Beschrijving     |
| :----------------- | :----------     |
| Verzonden | Er is een nieuwe taak gemaakt.  De datum en tijd die de taak heeft ingediend, wordt weergegeven in de kolom **Gemaakt** op **het tabblad** Taken. |
| Inzending is mislukt | De taakinzending is mislukt.  U moet proberen de actie die de taak heeft veroorzaakt, opnieuw uit te voeren. |
| In uitvoering | De taak wordt uitgevoerd, u kunt de voortgang van de taak op het tabblad **Taken** controleren. |
| Geslaagd | De taak is voltooid. De datum en tijd waarop de taak is voltooid, wordt weergegeven in de kolom **Voltooid** op **het tabblad** Taken. |
| Gedeeltelijk geslaagd | De taak is geslaagd. Deze status wordt meestal geretourneerd wanneer de taak geen gedeeltelijk geïndexeerde gegevens (ook wel *niet-geïndexeerde* gegevens genoemd) heeft gevonden in sommige bewaardergegevensbronnen.  |
| Mislukt | De taak is mislukt.  U moet proberen de actie die de taak heeft veroorzaakt, opnieuw uit te voeren. Als de taak een tweede keer mislukt, raden we u aan contact op te nemen met Microsoft Support en de ondersteuningsgegevens van de taak op te geven. |
|||
