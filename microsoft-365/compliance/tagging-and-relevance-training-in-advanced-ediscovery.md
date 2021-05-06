---
title: Training voor labelen en relevantie in Advanced eDiscovery
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
ms.assetid: 8576cc86-d51b-4285-b54b-67184714cc62
ROBOTS: NOINDEX, NOFOLLOW
description: Leer de stappen om te taggen en vervolgens te werken met een trainingsvoorbeeld van 40 bestanden tijdens de trainingsfase Relevantie van Advanced eDiscovery.
ms.openlocfilehash: ae4a9f2e9fd87fdd0679bbfd8f287b6eaa98e41f
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161669"
---
# <a name="tagging-and-relevance-training-in-advanced-ediscovery"></a>Training voor labelen en relevantie in Advanced eDiscovery
  
In dit artikel wordt de procedure beschreven voor het werken met de trainingsmodule Relevantie in Advanced eDiscovery.
  
Nadat de evaluatie is voltooid in Advanced eDiscovery en u de trainingsfase Relevantie in gaat, wordt een trainingsvoorbeeld van 40 bestanden naar het tabblad Tag gebracht voor labelen.
  
## <a name="performing-relevance-training"></a>Relevantietraining uitvoeren

1. Op **het tabblad \> Relevantielabel** wordt het deelvenster Labelen standaard weergegeven in het linkerdeelvenster en worden de voorbeeldbestanden één voor één weergegeven om te worden gelabeld.

    ![Deelvenster Relevantielabel](../media/0cf19ab4-b427-4a7f-8749-0f4ed9afaf58.png)
  
    Op het **tabblad** Tag wordt de weergavenaam van het bestand weergegeven. Dit kan het pad, het e-mailonderwerp, de titel of de door de gebruiker gedefinieerde naam zijn. De id, het bestandspad of het tekstpad kunnen worden gekopieerd door met de rechtermuisknop op het pad van het bestand te klikken.

    In  de statistische tagtatiktalabels ziet u het voorbeeldnummer van het bestand (boven aan het linkerdeelvenster), het nummer van het momenteel weergegeven bestand uit de totale bestanden in het voorbeeld (onder aan het rechterdeelvenster) en het huidige totale aantal gelabelde bestanden in het voorbeeld (onder aan het linkerdeelvenster), die verandert terwijl u bestanden tagt. Dit is van toepassing op alle relevantielabels die zijn uitgevoerd, ongeacht of dit gebeurt in Assessment, Training, Catch-up of Test.

    Pictogrammen die aangeven dat er opmerkingen, tags en gezinsbestanden bestaan, worden weergegeven in de bestandsweergave op een balk boven het bestand.

2. Bepaal de relevantie van het bestand voor het probleem met de zaak en tag het bestand met behulp van de knoppen voor de optie Labelen of sneltoetsen, zoals wordt weergegeven in de volgende tabel:

   |**Optie Voor labelen**|**Beschrijving**|**Sneltoets**|**Sneltoets bulksgewijs labelen (voor meerdere problemen)**|
   |-----|-----|-----|-----|
   |R  <br/> |Relevant  <br/> |Z  <br/> |`Shift + Z`  <br/> |
   |NR  <br/> |Niet relevant  <br/> |X  <br/> |`Shift + X`  <br/> |
   |Overslaan  <br/> |Overslaan  <br/> |C  <br/> |`Shift + A`  <br/> |
   |||||

   - Wanneer er meerdere problemen zijn voor een bestand, gaat de selectie na het labelen van een probleem naar het volgende probleem (indien aanwezig).  

   - Trefwoorden die zijn gedefinieerd door de beheerder of casemanager bij het markeren van trefwoorden (Relevantie-instelling Gemarkeerde trefwoorden), worden weergegeven (in opgegeven kleuren) om relevante bestanden te identificeren tijdens het \> labelen. Als een trefwoord een dubbele onderstreping heeft, kan erop worden geklikt om een knoptip weer te geven met de beschrijving van het trefwoord.

     Klik desgewenst op het tabblad **Tag** op **Tag-instellingen** om de volgende opties in te stellen:

      ![Instellingen voor relevantielabels](../media/533e89fa-7eb4-409e-ab07-f5aab9296dd8.png)
  
   - **Bulktag:** Gebruik deze optie om meerdere problemen  voor een bestand toe te wijzen door Alles te selecteren om de tag voor het geselecteerde bestand in te stellen voor alle problemen (overschrijven al gemarkeerde problemen) of door **De rest** te selecteren om de tag toe te passen op de resterende niet-gemarkeerde problemen. De geselecteerde optie blijft van kracht voor alle gevallen van deze gebruiker totdat deze is gewijzigd door die gebruiker (instelling is per gebruiker voor alle gevallen van de gebruiker).

   - **Automatische tag:** Schakel dit selectievakje in om andere problemen voor een bestand in te stellen als Niet relevant na één relevante labeling.

   - **Automatisch vooraf:** Schakel dit selectievakje in om de weergegeven bestandsselectie naar het volgende bestand te verplaatsen wanneer u het laatste of enige probleem zonder label labelt.

    Overgeslagen bestanden worden niet in aanmerking genomen voor relevantietraining en relevantiescoredoeleinden.

3. Opmerkingen met vrije tekst, gekoppeld aan een bestand, kunnen  worden bekeken en bewerkt via de optie Opmerking in de vervolgkeuzelijst van het linkerdeelvenster. (optioneel)

4. Richtlijnen voor labelen kunnen worden weergegeven door de optie Richtlijnen **labelen** te selecteren in de vervolgkeuzelijst van het linkerdeelvenster.

5. Nadat u alle bestanden in de lijst hebt gelabeld en klaar bent om de resultaten te berekenen, klikt u op **Berekenen.** Het **tabblad** Bijhouden wordt weergegeven.  

## <a name="working-with-the-sample-files-list"></a>Werken met de lijst met voorbeeldbestanden

Met de lijst met voorbeeldbestanden kunt u een lijst met de bestanden weergeven in een trainingsvoorbeeld en verschillende acties uitvoeren op een of meer bestanden. Op het **tabblad** Relevantielabel wordt in het linkerdeelvenster Voorbeeldbestanden een lijst met voorbeeldbestanden weergegeven voor verwerking met \>  evaluatie-, trainings-, inhaal- en inconsistentiesprocessen. 
  
1. Selecteer op het tabblad **\> Relevantielabel** de vervolgkeuzelijst Voorbeeldbestanden in het linkerdeelvenster. De voorbeeldbestanden worden weergegeven in het linkerdeelvenster.

    ![Lijst met voorbeeldbestanden van relevantielabels](../media/fd058bdd-645a-4af1-a1eb-bff08581cb18.png)
  
2. Selecteer een specifiek voorbeeld- of bestandsnummer door het nummer in te vullen of te selecteren in de vakken **Voorbeeld** **of** Bestand.

   - Een bestandsreeksnummer wordt weergegeven in de linkerkolom van de weergegeven lijst met bestanden op het **tabblad** Tag. Door op de koptekst te klikken, keert de oorspronkelijke weergegeven volgorde van de bestanden terug naar de oorspronkelijke volgorde.

   - Als u op een bestandsrij klikt, wordt de inhoud ervan weergegeven in het rechterdeelvenster.

   - Navigeer tussen bestanden in het huidige voorbeeld met behulp van de opties voor de lagere menubalk. Daarnaast zijn navigatietoetsensneltoetsen beschikbaar:
  
     - Ga als eerste naar het eerste bestand in het voorbeeld: `Shift + Ctrl + <`

     - Ga als eerste naar het vorige bestand in het voorbeeld: `Shift + <`

     - Ga als eerste naar het volgende bestand in het voorbeeld: `Shift + >`

     - Ga als eerste naar het laatste bestand in het voorbeeld: `Shift + Ctrl + >`
