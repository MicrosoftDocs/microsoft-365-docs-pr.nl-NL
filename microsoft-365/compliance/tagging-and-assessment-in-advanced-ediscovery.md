---
title: Labelen en beoordelen in Advanced eDiscovery
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
ROBOTS: NOINDEX, NOFOLLOW
description: Bekijk de stappen voor het uitvoeren van evaluatietraining, inclusief het labelen van bestanden, en het controleren van evaluatieresultaten in Advanced eDiscovery.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161668"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a>Labelen en beoordelen in de module Relevantie in Advanced eDiscovery
  
In deze sectie wordt de procedure voor beoordeling beschreven in de module Relevantie in Advanced eDiscovery.
  
## <a name="performing-assessment-training-and-analysis"></a>Evaluatietraining en -analyse uitvoeren

1. Klik op **het \> tabblad Relevantie** bijhouden op **Beoordeling om** een beoordeling van de zaak te starten.

    In deze procedure wordt bijvoorbeeld een steekproefbeoordelingsset van 500 bestanden gemaakt en wordt het tabblad Tag weergegeven, dat het deelvenster Labelen, weergegeven bestandsinhoud en andere opties voor labelen bevat.  

    ![Tabblad Relevantielabel voor beoordeling](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. Controleer elk bestand in het voorbeeld, bepaal de relevantie van het bestand voor elk probleem en tag het bestand met de knoppen Relevantie (R), Niet relevant (NR) en Overslaan in het deelvenster **Labelen.** 

    > [!NOTE]
    >  Beoordeling vereist 500 gelabelde bestanden. Als bestanden worden overgeslagen, ontvangt u meer bestanden om te taggen. 
  
3. Nadat u alle bestanden in het voorbeeld hebt gelabeld, klikt u op **Berekenen.**

    De huidige foutmarge en -rijkdom beoordelen worden  berekend en weergegeven op het tabblad Relevantie bijhouden, met uitgebreide details per probleem, zoals hieronder wordt weergegeven. Meer informatie over dit dialoogvenster wordt beschreven in [de sectie Beoordelingsresultaten.](#reviewing-assessment-results)

    ![Relevantie bijhouden - Beoordeling](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > Het is standaard raadzaam om door te gaan met de standaardstap Volgende stap wanneer de voortgangsindicator Evaluatie voor het probleem is voltooid, wat aangeeft dat het beoordelingsvoorbeeld is beoordeeld en dat voldoende relevante bestanden zijn gelabeld. > Als u anders de resultaten  van het tabblad Bijhouden wilt bekijken en de  foutmarge en de volgende stap wilt bepalen, klikt u op Wijzigen naast Volgende **stap,** selecteert u Doorgaan met beoordelen en klikt u vervolgens op **OK.**
  
4. Klik **rechts** van het  selectievakje Beoordeling op Wijzigen om de beoordelingsparameters per probleem weer te geven en op te geven. Een **dialoogvenster Beoordelingsniveau** voor elk probleem wordt weergegeven, zoals wordt weergegeven in het volgende voorbeeld: 

    ![Probleem op beoordelingsniveau](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    De volgende parameters voor het probleem worden berekend en weergegeven in het dialoogvenster **Beoordelingsniveau:** 

    **Doelfoutmarge voor rappelschattingen:** Op basis van deze waarde wordt het geschatte aantal extra bestanden berekend dat nodig is om te controleren. De marge die wordt gebruikt voor inroepen is groter dan 75% en met een betrouwbaarheidsniveau van 95%.

    **Extra beoordelingsbestanden vereist:** geeft aan hoeveel bestanden er nog nodig zijn als niet aan de huidige foutmarge is voldaan. 

5. De huidige foutmarge aanpassen en het effect van verschillende foutmarges (per probleem) bekijken:

6. Selecteer een **probleem in de** lijst Probleem selecteren. 

7. Voer **in Doelfoutmarge voor schatting van inroepen** een nieuwe waarde in.

8. Klik **op Waarden bijwerken** om het effect van de aanpassingen te zien. 

9. Klik **op Geavanceerd** in het dialoogvenster **Beoordelingsniveau** om de volgende aanvullende parameters en details te zien: 

    ![Geavanceerde weergave case-probleem op beoordelingsniveau](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - **Geschatte rijkheid:** Geschatte rijkheid op basis van de huidige evaluatieresultaten

    - **Voor veronderstelde inroeping:** De doelfoutmarge is standaard van toepassing op inroepen boven 75%. Klik **op Bewerken** als u deze parameter wilt wijzigen en de foutmarge voor een ander bereik met inroepwaarden wilt bepalen. 

    - **Betrouwbaarheidsniveau:** Standaard is de aanbevolen foutmarge voor betrouwbaarheid 95%. Klik **op Bewerken** als u deze parameter wilt wijzigen.

    - **Verwachte foutenmarge :** Gezien de bijgewerkte waarden is dit de verwachte foutmarge van de rijkheid, nadat alle aanvullende beoordelingsbestanden zijn gecontroleerd.

    - **Aanvullende beoordelingsbestanden vereist:** gezien de bijgewerkte waarden, het aantal extra beoordelingsbestanden dat moet worden gecontroleerd om het doel te bereiken.

    - **Totaal vereiste beoordelingsbestanden:** Gezien de bijgewerkte waarden zijn de totale beoordelingsbestanden vereist voor controle.

    - **Verwacht aantal relevante bestanden in de beoordeling:** gezien de bijgewerkte waarden, wordt het verwachte aantal relevante bestanden in de hele beoordeling gecontroleerd nadat alle aanvullende beoordelingsbestanden zijn beoordeeld.

10. Klik **op Waarden herberekenen** als parameters worden gewijzigd. Wanneer u klaar bent, als er één probleem is, klikt u op **OK** om de wijzigingen op te slaan (of **Volgende** wanneer er meerdere problemen zijn die u moet controleren of wijzigen en vervolgens **voltooien).** 

    Wanneer er meerdere problemen zijn, wordt, nadat alle problemen zijn beoordeeld of aangepast, een dialoogvenster **Beoordelingsniveau:** samenvatting weergegeven, zoals wordt weergegeven in het volgende voorbeeld. 

    ![Overzicht van beoordelingsniveau](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    Als de evaluatie is voltooid, gaat u verder met de volgende fase in de relevantietraining.

## <a name="reviewing-assessment-results"></a>Beoordelingsresultaten bekijken

Nadat een evaluatievoorbeeld is gelabeld, worden de beoordelingsresultaten berekend en weergegeven op het tabblad Relevantie bijhouden.
  
De volgende resultaten worden weergegeven in de uitgebreide weergave Bijhouden:
  
- Huidige foutmarge voor schattingen voor inroepen beoordelen

- Geschatte rijkheid

- Aanvullende beoordelingsbestanden vereist (voor controle)

De huidige foutmarge beoordelen is de foutmarge die wordt aanbevolen door Advanced eDiscovery. Het getal dat wordt weergegeven voor de 'Aanvullende beoordelingsbestanden vereist' komt overeen met die aanbeveling.
  
De voortgangsindicator Beoordeling geeft het niveau van voltooiing van de beoordeling aan, gezien de huidige foutmarge. Wanneer de evaluatie aan de gang is, tagt de gebruiker een ander beoordelingsvoorbeeld.
  
Wanneer de beoordelingsvoortgangsindicator de beoordeling als voltooid weggedreed, betekent dit dat de evaluatie steekproefbeoordeling is voltooid en dat voldoende relevante bestanden zijn gelabeld. 
  
De uitgebreide weergave Bijhouden toont de aanbevolen volgende stap, de beoordelingsstatistieken en toegang tot gedetailleerde resultaten.
  
Wanneer de rijkheid erg laag is, is het aantal extra beoordelingsbestanden dat nodig is om een minimaal aantal relevante bestanden te bereiken, zeer hoog om nuttige statistieken te maken. Advanced eDiscovery raadt u aan over te gaan op de training. De indicator voor de voortgang van de beoordeling wordt gearceerd en er zijn geen statistieken beschikbaar.
  
Als er geen statistische stabilisatie is, zijn er resultaten met een lager nauwkeurigheids- en betrouwbaarheidsniveau. Deze resultaten kunnen echter worden gebruikt om relevante bestanden te vinden wanneer u niet het percentage gevonden relevante bestanden hoeft te weten. Op dezelfde manier kan deze status worden gebruikt om problemen met een lage rijkheid op te leiden, waarbij relevantiescores de toegang tot bestanden die relevant zijn voor een specifiek probleem kunnen versnellen.
  
> [!TIP]
> Op het **tabblad \> Relevantie** bijhouden, uit uitgebreid probleemweergave, zijn de volgende weergaveopties beschikbaar: 
> 
> De aanbevolen volgende stap, zoals **Volgende stap:** Labelen kan worden  overgeslagen (per probleem) door op de knop Wijzigen rechts te klikken en vervolgens een andere stap te selecteren in **de volgende stap.** Wanneer de indicator voor de voortgang van de beoordeling nog niet is voltooid, is evaluatie de volgende aanbevolen optie om meer beoordelingsbestanden te taggen en de nauwkeurigheid van de statistieken te verhogen. 
> 
> U kunt de foutmarge wijzigen en de impact ervan beoordelen door te klikken op Wijzigen **en** in het dialoogvenster Beoordelingsniveau **de** foutmarge Doel voor inroepingsschattingen te wijzigen en op Waarden bijwerken **te klikken.**  In dit dialoogvenster kunt u ook geavanceerde opties weergeven door op Geavanceerd te **klikken.** 
> 
> U kunt aanvullende statistieken op beoordelingsniveau en de impact ervan bekijken door op **Weergave te klikken.** In het dialoogvenster Weergegeven detailresultaten zijn statistieken per probleem beschikbaar, wanneer er ten minste 500 gelabelde beoordelingsbestanden zijn en ten minste 18 bestanden zijn gemarkeerd als Relevant voor het probleem. 
