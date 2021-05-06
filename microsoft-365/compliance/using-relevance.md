---
title: Gebruik de module Relevantie om gegevens te analyseren in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Lees hoe de module Relevantie gegevens analyseert met een beschrijving van de relevantiewerkstroom en trainingsstappen in Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4a05ec47a4a6b2100c062912e7668c2bf785caf7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161541"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a>Gebruik de module Relevantie om gegevens te analyseren in Advanced eDiscovery

In Advanced eDiscovery bevat de module Relevantie de training Relevantie en het controleren van bestanden met betrekking tot een zaak. Als u de werkstroom Relevantie wilt gebruiken, gaat u naar Controleset beheren in een revisieset en klikt u op Relevantie tonen. Er zijn een paar stappen die u moet voltooien voordat u de werkstroom kunt starten:

- Proces: elke belastingset die aan de revisieset is toegevoegd, wordt hier als een 'container' op de pagina geplaatst. U moet deze documenten verwerken voordat u ze kunt toevoegen aan de module Relevantie. Dit is ook de plaats waar u ze kunt markeren als zaad of vooraf gemarkeerd voor een specifiek probleem.

- Toevoegen aan relevantie: onder Relevantiebelastingen kunt u documenten toevoegen die zijn verwerkt naar Relevantie om ze beschikbaar te maken \> voor training.

De werkstroom Relevantie wordt als volgt weergegeven en beschreven:
  
![Relevantiewerkstroom](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **Cyclussen van beoordeling en bijhouden:**
    
  - **Beoordeling:** Maakt vroegtijdige beoordeling mogelijk op basis van een steekproef van bestanden en gebruikt deze beoordeling om beslissingen toe te passen om de prestaties van het voorspellende coderingsproces te bepalen. 
    
  - **Bijhouden:** Tussentijdse resultaten van de beoordeling berekenen en weergeven terwijl de statistische geldigheid van het proces wordt gecontroleerd. 
    
- **Cyclussen van training en bijhouden**
    
  - **Tag:** Advanced eDiscovery leert relevantiecriteria die specifiek zijn voor elk probleem op basis van de iteratieve controle en labeling van afzonderlijke bestanden door de expert.
    
  - **Bijhouden:** Tussentijdse resultaten van de relevantietraining berekenen en weergeven terwijl de statistische geldigheid van het proces wordt gecontroleerd. 
    
- **Batchberekening:** De geaccumuleerde en geleerde relevantiecriteria worden toegepast op de hele bestandsverzameling en er wordt een relevantiescore gegenereerd voor elk bestand.
    
- **Beslissen:** De resultaten van de analyse die op het hele geval wordt toegepast, worden weergegeven na de batchberekening en gegevens die worden gebruikt om beslissingen over documentbeoordelingen te nemen, worden weergegeven.
    
- **Test:** Resultaten kunnen worden getest om de geldigheid en effectiviteit van de verwerking Advanced eDiscovery controleren.

- **Zoeken:** Wanneer de werkstroom Relevantie is voltooid, kunt u de uitvoer, zoals lees percentiel van een document, gebruiken voor uw probleem wanneer u een query uitvoert in de revisieset.
    
## <a name="guidelines-for-relevance-training-and-review"></a>Richtlijnen voor relevantietraining en -revisie

Hieronder volgt een overzicht van richtlijnen voor relevantietraining en -revisie:
  
- **Fouten en inconsistenties:** als er tijdens de training fouten worden gemaakt bij het labelen, gaat u terug naar eerdere bestandsvoorbeelden om deze te corrigeren. Als er te veel fouten zijn om te corrigeren of als er een nieuw perspectief van het geval of probleem is, moeten de relevantiecriteria opnieuw worden gedefinieerd door de beheerder en wordt de relevantietraining opnieuw gestart.
    
- **Labelen en training**: 
    
  - Bestanden moeten worden gelabeld op basis van alleen inhoud. Houd geen rekening met metagegevens, zoals bewaarder, datum of bestandspad. 
    
  - Houd geen rekening met datumbereikindicaties in de tekst bij het labelen van bestanden.
    
  - Overweeg geen ingesloten grafische afbeeldingen bij het taggen van bestanden.
     
  - Tekst negeren die is toegepast op Relevantie, wordt verwijderd in de weergegeven bestandsinhoud in de tekstweergave in Relevantie. Als de waarden voor Tekst negeren zijn gedefinieerd nadat de relevantietraining al is gestart, wordt de nieuwe genegeerde tekst toegepast op voorbeeldbestanden die zijn gemaakt vanaf het punt waarop deze is gedefinieerd. De functie Tekst negeren moet voorzichtig worden gebruikt, omdat het gebruik ervan de prestaties van bestandsanalyse kan verminderen
    
  - Gebruik de **optie Labelen overslaan** alleen wanneer dat nodig is. Advanced eDiscovery traint niet op basis van overgeslagen bestanden. Als het lastig is om te beoordelen of een bestand relevant is, is het beter om waar mogelijk te taggen als Relevant (R) of Niet relevant (NR) in plaats van **Overslaan te selecteren.** Wanneer Advanced eDiscovery training evalueert, kan worden gezien hoe goed deze typen bestanden zijn verwerkt.
    
  - Zelfs bestanden met een zeer kleine hoeveelheid geëxtraheerde tekst moeten in de training worden gelabeld als R/NR, in plaats van als 'Overslaan', indien mogelijk. 
    
  - Labelen kan van invloed zijn op de classificatie zolang het bestand leesbaar is en kan worden gelabeld als R/NR.
    
  - Met het bestandsvolgordenummer in de weergegeven lijst Voorbeeldbestanden op het tabblad **Tag** kan de gebruiker terugkeren naar de oorspronkelijke weergegeven volgorde van de bestanden. 
    
  - U kunt teruggaan naar een voorbeeld en de labeling van de evaluatie- en trainingssetbestanden wijzigen. De wijzigingen worden toegepast bij het maken van het volgende voorbeeld.
    
  - Gescande Excel in PDF-indeling moeten hetzelfde worden behandeld als Excel bestanden bij het taggen van bestanden.
    
  - Als u twijfelt over het labelen van relevantie van een bestand, raadpleegt u een expert. Onjuiste labeling tijdens de relevantietraining kan later in het proces leiden tot verloren tijd en kan ook een negatieve invloed hebben op de kwaliteit van de algehele resultaten.
    
  - Trefwoorden die zijn gedefinieerd in trefwoordenlijsten, worden weergegeven in kleuren om de gebruiker te helpen relevante bestanden te identificeren tijdens het labelen.
    
- **Batchberekening:** Bestanden die door de expert als R/NR zijn gelabeld, krijgen een score van 0 of 100. Dit geldt voor labels die vóór batchberekening zijn gemaakt. Als de expert het probleem heeft overgezet naar Idle na batchberekening en dit probleem blijft taggen, zijn de nieuwe scores niet 100/0, maar de oorspronkelijke score.
    
- **Problemen en** bemonsteringsmodus: Problemen worden meestal uitgeschakeld wanneer het werk aan de problemen is voltooid (Relevantietraining is gestabiliseerd en batchberekening is uitgevoerd), wanneer de problemen worden geannuleerd of wanneer een andere gebruiker aan de problemen werkt.
    
## <a name="steps-in-relevance-training"></a>Stappen in relevantietraining

Op het **tabblad \> Relevantie** bijhouden Advanced eDiscovery aanbevelingen over hoe u verder kunt gaan met de verwerking, met de volgende stappen. De implicaties worden hieronder beschreven wanneer elk van de volgende stappen wordt aanbevolen in het trainingsproces Relevantie. 
  
- Labelen/doorgaan met labelen: Bestandsbeoordeling en Relevantielabels die door een expert zijn uitgevoerd voor elk bestand en elk probleem in een steekproef.
    
  - Implicatie: een bestaand voorbeeld moet worden gelabeld.
    
- Beoordeling /doorgaan met beoordelen: Hiermee kunt u de relevantie van het probleem in een vroeg stadium valideren en een voorlopige weergave van de relevantie van de bestandspopulatie die voor het huidige geval is geïmporteerd.
    
  - Implicatie: Meer beoordeling is vereist of aanbevolen.
    
- Training / Continue training: Proces waarin Advanced eDiscovery leert van de expert die de bestandsvoorbeelden tagt en de mogelijkheid krijgt relevantiecriteria te identificeren die relevant zijn voor elk probleem in de context van elk geval.
    
  - Implicatie: Het probleem heeft meer training nodig; het volgende voorbeeld moet worden gemaakt en gelabeld. 
    
- Batchberekening: Relevantieproces waarbij Advanced eDiscovery kennis die is verkregen tijdens de trainingsfase, wordt toegepast op de hele bestandspopulatie. Alle bestanden in de relevante bestandsgroep worden beoordeeld op relevantie en krijgen een relevantiescore toegewezen.
    
  - Implicatie: het probleem is gestabiliseerd en batchberekening kan worden uitgevoerd.
    
- Inhaalactie: Relevantie geeft aan wanneer een expert een voorbeeld van bestanden controleert en tagt die zijn geselecteerd uit een extra bestandsbelasting tijdens een scenario voor rollend laden.
    
  - Implicatie: er is een nieuwe belasting toegevoegd en inhalen is vereist om te kunnen blijven werken.
    
- Tagconsequenties: Proces identificeert, via Advanced eDiscovery algoritme, inconsistenties in het proces voor het taggen van bestanden die een negatieve invloed kunnen hebben op de analyse.
    
  - Implicatie: Het volgende voorbeeld bevat bestanden die in eerdere voorbeelden zijn gelabeld en de labels moeten opnieuw worden gemarkeerd.
    
- Classificatie bijwerken: Hiermee kan de gebruiker wijzigingen aanbrengen in labels of seeding.
    
  - Implicatie: Wijzigingen in labelen en inzaaien kunnen worden toegepast zonder dat u handmatig een ander relevantievoorbeeld hoeft uit te voeren.
    
- In de wacht: Het trainingsproces Relevantie is voltooid.
    
  - Implicatie: Er is op dit moment geen relevantietraining vereist.
    
Hoewel Advanced eDiscovery u door het proces begeleidt, kunt u met de aanbevolen volgende stappen in verschillende stadia ook navigeren tussen tabbladen en pagina's en keuzes maken om situaties aan te pakken die relevant kunnen zijn voor uw individuele proces voor het controleren van een zaak, probleem of document. 
  
Het is mogelijk om opties voor het verwerken van Advanced eDiscovery volgende stap te accepteren of te overschrijven. Als u een andere stap wilt uitvoeren dan  de aanbevolen volgende stap, klikt u op de  volgende stap die wordt weergegeven in de uit uitgebreide weergave van het probleem in het dialoogvenster, klikt u op de knop Wijzigen naast de volgende stap en selecteert u een andere optie volgende stap. 
  
> [!NOTE]
> Sommige opties blijven mogelijk uitgeschakeld na het ontgrendelen, omdat ze op dat moment in het proces niet worden ondersteund voor gebruik. 
  
## <a name="more-information"></a>Meer informatie

[Inzicht in beoordeling in relevantie](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Labelen en beoordelen](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Training voor labelen en relevantie](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Relevantieanalyse bijhouden](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Beslissen op basis van de resultaten](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Relevantieanalyse testen](test-relevance-analysis-in-advanced-ediscovery.md)

[Een query uitvoeren op de gegevens in een controleset](review-set-search.md)
