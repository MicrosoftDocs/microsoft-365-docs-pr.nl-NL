---
title: Test Relevantieanalyse in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het gebruik van het tabblad Testen na batchberekening in Advanced eDiscovery om de algehele kwaliteit van de verwerking te testen, te vergelijken en te valideren.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161667"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a>Test Relevantieanalyse in Advanced eDiscovery
  
Op het tabblad Testen in Advanced eDiscovery kunt u de algehele kwaliteit van de verwerking testen, vergelijken en valideren. Deze tests worden uitgevoerd na batchberekening. Door de bestanden in de verzameling te labelen, maakt een expert het uiteindelijke oordeel over of elk gelabeld bestand relevant is voor de zaak.
  
In scenario's met één of meerdere problemen worden tests meestal per probleem uitgevoerd. De resultaten kunnen na elke test worden bekeken en testresultaten kunnen worden herwerkt met opgegeven voorbeeldtestbestanden.
  
## <a name="testing-the-rest"></a>De rest testen

De test 'Test the Rest' wordt gebruikt om selectiebeslissingen te valideren, bijvoorbeeld om alleen bestanden boven een specifieke relevantiescore te controleren op basis van de uiteindelijke Advanced eDiscovery resultaten. De expert bekijkt een steekproef van bestanden onder een geselecteerde cutoffscore om het aantal relevante bestanden in die set te evalueren.
  
Deze test bevat statistieken en een vergelijking tussen de revisieset en de populatie Rest testen. De resultaten van de revisieset zijn de resultaten die worden berekend door Relevantie tijdens de training. De resultaten zijn berekeningen op basis van instellingen en invoerparameters, zoals:
  
- Test voorbeeldstatistieken van het aantal bestanden in een steekproef en identificeer relevante bestanden.

- Tabellaire vergelijking van de parameters Populatie van de revisieset en de Rest, bijvoorbeeld het aantal bestanden, het geschatte aantal relevante bestanden, de geschatte rijkheid en de gemiddelde kosten van het zoeken naar een ander relevant bestand. Instellingen voor kostenparameters kunnen worden ingesteld door de beheerder.

De test 'Test de rest' uitvoeren:

1. Open het **tabblad \> Relevantietoets.**

2. Klik op **het** tabblad Test op **Nieuwe test.** Het **dialoogvenster Test maken** wordt weergegeven, zoals wordt weergegeven in het volgende voorbeeld.

    ![Relevantie test de resultaten van de rest](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. Typ **in Testnaam** en **Beschrijving** de naam en beschrijving.

4. Selecteer in **de lijst Testtype** **de optie Rest testen**

5. Selecteer in **de lijst Probleem/categorie** de naam van het probleem.

6. Selecteer de belasting in **de** lijst Laden. 

7. Accepteer **in Lees %** de standaardwaarde of selecteer een waarde voor de cutoff Relevantiescore. 

8. In **Grootte instellen** of de standaardwaarde accepteren. Met de pictogrammen voor herstellen worden de standaardwaarden hersteld.

9. Klik **op Labelen starten.** Er wordt een testvoorbeeld gegenereerd.

10. Controleer en tag elk van de bestanden op het tabblad **\> Relevantielabel** en klik wanneer u klaar bent op **Berekenen.**

11. Klik op het tabblad Test op **Resultaten weergeven om** de testresultaten te bekijken. Een voorbeeld wordt weergegeven in de volgende schermafbeelding.

    ![Test de overige resultaten](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
In de vorige schermafbeelding bevat de sectie **Voorbeeldparameters** van de tabel details over het aantal bestanden in het voorbeeld dat door de expert is gelabeld en het aantal relevante bestanden dat in dat voorbeeld is gevonden.
  
De sectie **Populatieparameters** van de tabel bevat de testresultaten, inclusief de populatie van bestanden controleren met een score onder de geselecteerde cutoff en 'De rest'-populatie van bestanden met een score boven de geselecteerde cutoff. Voor elke populatie worden de volgende resultaten weergegeven:
  
- Bevat bestanden met lees % - Aangegeven cutoff

- Het totale aantal bestanden

- Het geschatte aantal relevante bestanden

- De geschatte rijkheid

- De gemiddelde revisiekosten voor het zoeken naar een ander relevant bestand

## <a name="testing-the-slice"></a>Het segment testen

Met de test 'Test the Slice' worden tests uitgevoerd die vergelijkbaar zijn met de test 'Test the Rest', maar met een segment van het bestand dat is ingesteld op relevantie-lees %.

De test 'Het segment testen' uitvoeren:
  
1. Open het **tabblad \> Relevantietoets.**

2. Klik op **het** tabblad Test op **Nieuwe test.** Het **dialoogvenster Test maken** wordt weergegeven.

3. Typ de gegevens **in Testnaam** en Beschrijving.

4. Selecteer in **de lijst Type** testen de optie Het segment **testen.**

5. Selecteer in **de** lijst Probleem de naam van het probleem.

6. Selecteer de belasting in **de** lijst Laden.

7. Accepteer **in Lees % tussen,** de standaardwaarden voor laag en hoog bereik of selecteer waarden voor de cutoff Relevantiescores.

8. Selecteer **in Grootte instellen** een waarde of accepteer de standaardwaarde.

    Met de pictogrammen voor herstellen wordt de standaardwaarde hersteld.

9. Klik **op Labelen starten.** Er wordt een testvoorbeeld gegenereerd.

10. Controleer en tag elk van de bestanden op het tabblad **\> Relevantielabel** en klik wanneer u klaar bent op **Berekenen.**

11. Klik op het tabblad Test op **Resultaten weergeven om** de testresultaten te bekijken.
