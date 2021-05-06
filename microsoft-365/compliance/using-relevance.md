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
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a><span data-ttu-id="4b4e7-103">Gebruik de module Relevantie om gegevens te analyseren in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4b4e7-103">Use the Relevance module to analyze data in Advanced eDiscovery</span></span>

<span data-ttu-id="4b4e7-104">In Advanced eDiscovery bevat de module Relevantie de training Relevantie en het controleren van bestanden met betrekking tot een zaak.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-104">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="4b4e7-105">Als u de werkstroom Relevantie wilt gebruiken, gaat u naar Controleset beheren in een revisieset en klikt u op Relevantie tonen.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-105">In order to use the Relevance workflow, go to Manage review set within a review set and click on Show Relevance.</span></span> <span data-ttu-id="4b4e7-106">Er zijn een paar stappen die u moet voltooien voordat u de werkstroom kunt starten:</span><span class="sxs-lookup"><span data-stu-id="4b4e7-106">There are a couple of steps you need to complete before you can start the workflow:</span></span>

- <span data-ttu-id="4b4e7-107">Proces: elke belastingset die aan de revisieset is toegevoegd, wordt hier als een 'container' op de pagina geplaatst.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-107">Process: each load set added to the review set will show up as a "container" here.</span></span> <span data-ttu-id="4b4e7-108">U moet deze documenten verwerken voordat u ze kunt toevoegen aan de module Relevantie. Dit is ook de plaats waar u ze kunt markeren als zaad of vooraf gemarkeerd voor een specifiek probleem.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-108">You need to process these documents before you can add them to Relevance module; this is also where you can mark them as seed or pre-tagged for a specific issue.</span></span>

- <span data-ttu-id="4b4e7-109">Toevoegen aan relevantie: onder Relevantiebelastingen kunt u documenten toevoegen die zijn verwerkt naar Relevantie om ze beschikbaar te maken \> voor training.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-109">Add to Relevance: Under Relevance \> Loads, you can add documents that have been processed to Relevance to make them available for training.</span></span>

<span data-ttu-id="4b4e7-110">De werkstroom Relevantie wordt als volgt weergegeven en beschreven:</span><span class="sxs-lookup"><span data-stu-id="4b4e7-110">The Relevance workflow is shown and described as follows:</span></span>
  
![Relevantiewerkstroom](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="4b4e7-112">**Cyclussen van beoordeling en bijhouden:**</span><span class="sxs-lookup"><span data-stu-id="4b4e7-112">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="4b4e7-113">**Beoordeling:** Maakt vroegtijdige beoordeling mogelijk op basis van een steekproef van bestanden en gebruikt deze beoordeling om beslissingen toe te passen om de prestaties van het voorspellende coderingsproces te bepalen.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-113">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="4b4e7-114">**Bijhouden:** Tussentijdse resultaten van de beoordeling berekenen en weergeven terwijl de statistische geldigheid van het proces wordt gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-114">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="4b4e7-115">**Cyclussen van training en bijhouden**</span><span class="sxs-lookup"><span data-stu-id="4b4e7-115">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="4b4e7-116">**Tag:** Advanced eDiscovery leert relevantiecriteria die specifiek zijn voor elk probleem op basis van de iteratieve controle en labeling van afzonderlijke bestanden door de expert.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-116">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="4b4e7-117">**Bijhouden:** Tussentijdse resultaten van de relevantietraining berekenen en weergeven terwijl de statistische geldigheid van het proces wordt gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-117">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="4b4e7-118">**Batchberekening:** De geaccumuleerde en geleerde relevantiecriteria worden toegepast op de hele bestandsverzameling en er wordt een relevantiescore gegenereerd voor elk bestand.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-118">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="4b4e7-119">**Beslissen:** De resultaten van de analyse die op het hele geval wordt toegepast, worden weergegeven na de batchberekening en gegevens die worden gebruikt om beslissingen over documentbeoordelingen te nemen, worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-119">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="4b4e7-120">**Test:** Resultaten kunnen worden getest om de geldigheid en effectiviteit van de verwerking Advanced eDiscovery controleren.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-120">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>

- <span data-ttu-id="4b4e7-121">**Zoeken:** Wanneer de werkstroom Relevantie is voltooid, kunt u de uitvoer, zoals lees percentiel van een document, gebruiken voor uw probleem wanneer u een query uitvoert in de revisieset.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-121">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your review set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="4b4e7-122">Richtlijnen voor relevantietraining en -revisie</span><span class="sxs-lookup"><span data-stu-id="4b4e7-122">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="4b4e7-123">Hieronder volgt een overzicht van richtlijnen voor relevantietraining en -revisie:</span><span class="sxs-lookup"><span data-stu-id="4b4e7-123">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="4b4e7-124">**Fouten en inconsistenties:** als er tijdens de training fouten worden gemaakt bij het labelen, gaat u terug naar eerdere bestandsvoorbeelden om deze te corrigeren.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-124">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="4b4e7-125">Als er te veel fouten zijn om te corrigeren of als er een nieuw perspectief van het geval of probleem is, moeten de relevantiecriteria opnieuw worden gedefinieerd door de beheerder en wordt de relevantietraining opnieuw gestart.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-125">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="4b4e7-126">**Labelen en training**:</span><span class="sxs-lookup"><span data-stu-id="4b4e7-126">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="4b4e7-127">Bestanden moeten worden gelabeld op basis van alleen inhoud.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-127">Files should be tagged based on content only.</span></span> <span data-ttu-id="4b4e7-128">Houd geen rekening met metagegevens, zoals bewaarder, datum of bestandspad.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-128">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="4b4e7-129">Houd geen rekening met datumbereikindicaties in de tekst bij het labelen van bestanden.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-129">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="4b4e7-130">Overweeg geen ingesloten grafische afbeeldingen bij het taggen van bestanden.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-130">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="4b4e7-131">Tekst negeren die is toegepast op Relevantie, wordt verwijderd in de weergegeven bestandsinhoud in de tekstweergave in Relevantie.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-131">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="4b4e7-132">Als de waarden voor Tekst negeren zijn gedefinieerd nadat de relevantietraining al is gestart, wordt de nieuwe genegeerde tekst toegepast op voorbeeldbestanden die zijn gemaakt vanaf het punt waarop deze is gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-132">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="4b4e7-133">De functie Tekst negeren moet voorzichtig worden gebruikt, omdat het gebruik ervan de prestaties van bestandsanalyse kan verminderen</span><span class="sxs-lookup"><span data-stu-id="4b4e7-133">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="4b4e7-134">Gebruik de **optie Labelen overslaan** alleen wanneer dat nodig is.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-134">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="4b4e7-135">Advanced eDiscovery traint niet op basis van overgeslagen bestanden.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-135">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="4b4e7-136">Als het lastig is om te beoordelen of een bestand relevant is, is het beter om waar mogelijk te taggen als Relevant (R) of Niet relevant (NR) in plaats van **Overslaan te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="4b4e7-136">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="4b4e7-137">Wanneer Advanced eDiscovery training evalueert, kan worden gezien hoe goed deze typen bestanden zijn verwerkt.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-137">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="4b4e7-138">Zelfs bestanden met een zeer kleine hoeveelheid geëxtraheerde tekst moeten in de training worden gelabeld als R/NR, in plaats van als 'Overslaan', indien mogelijk.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-138">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="4b4e7-139">Labelen kan van invloed zijn op de classificatie zolang het bestand leesbaar is en kan worden gelabeld als R/NR.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-139">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="4b4e7-140">Met het bestandsvolgordenummer in de weergegeven lijst Voorbeeldbestanden op het tabblad **Tag** kan de gebruiker terugkeren naar de oorspronkelijke weergegeven volgorde van de bestanden.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-140">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="4b4e7-141">U kunt teruggaan naar een voorbeeld en de labeling van de evaluatie- en trainingssetbestanden wijzigen.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-141">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="4b4e7-142">De wijzigingen worden toegepast bij het maken van het volgende voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-142">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="4b4e7-143">Gescande Excel in PDF-indeling moeten hetzelfde worden behandeld als Excel bestanden bij het taggen van bestanden.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-143">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="4b4e7-144">Als u twijfelt over het labelen van relevantie van een bestand, raadpleegt u een expert.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-144">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="4b4e7-145">Onjuiste labeling tijdens de relevantietraining kan later in het proces leiden tot verloren tijd en kan ook een negatieve invloed hebben op de kwaliteit van de algehele resultaten.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-145">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="4b4e7-146">Trefwoorden die zijn gedefinieerd in trefwoordenlijsten, worden weergegeven in kleuren om de gebruiker te helpen relevante bestanden te identificeren tijdens het labelen.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-146">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="4b4e7-147">**Batchberekening:** Bestanden die door de expert als R/NR zijn gelabeld, krijgen een score van 0 of 100.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-147">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="4b4e7-148">Dit geldt voor labels die vóór batchberekening zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-148">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="4b4e7-149">Als de expert het probleem heeft overgezet naar Idle na batchberekening en dit probleem blijft taggen, zijn de nieuwe scores niet 100/0, maar de oorspronkelijke score.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-149">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="4b4e7-150">**Problemen en** bemonsteringsmodus: Problemen worden meestal uitgeschakeld wanneer het werk aan de problemen is voltooid (Relevantietraining is gestabiliseerd en batchberekening is uitgevoerd), wanneer de problemen worden geannuleerd of wanneer een andere gebruiker aan de problemen werkt.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-150">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="4b4e7-151">Stappen in relevantietraining</span><span class="sxs-lookup"><span data-stu-id="4b4e7-151">Steps in Relevance training</span></span>

<span data-ttu-id="4b4e7-152">Op het **tabblad \> Relevantie** bijhouden Advanced eDiscovery aanbevelingen over hoe u verder kunt gaan met de verwerking, met de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-152">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="4b4e7-153">De implicaties worden hieronder beschreven wanneer elk van de volgende stappen wordt aanbevolen in het trainingsproces Relevantie.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-153">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="4b4e7-154">Labelen/doorgaan met labelen: Bestandsbeoordeling en Relevantielabels die door een expert zijn uitgevoerd voor elk bestand en elk probleem in een steekproef.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-154">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="4b4e7-155">Implicatie: een bestaand voorbeeld moet worden gelabeld.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-155">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="4b4e7-156">Beoordeling /doorgaan met beoordelen: Hiermee kunt u de relevantie van het probleem in een vroeg stadium valideren en een voorlopige weergave van de relevantie van de bestandspopulatie die voor het huidige geval is geïmporteerd.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-156">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="4b4e7-157">Implicatie: Meer beoordeling is vereist of aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-157">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="4b4e7-158">Training / Continue training: Proces waarin Advanced eDiscovery leert van de expert die de bestandsvoorbeelden tagt en de mogelijkheid krijgt relevantiecriteria te identificeren die relevant zijn voor elk probleem in de context van elk geval.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-158">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="4b4e7-159">Implicatie: Het probleem heeft meer training nodig; het volgende voorbeeld moet worden gemaakt en gelabeld.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-159">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="4b4e7-160">Batchberekening: Relevantieproces waarbij Advanced eDiscovery kennis die is verkregen tijdens de trainingsfase, wordt toegepast op de hele bestandspopulatie.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-160">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="4b4e7-161">Alle bestanden in de relevante bestandsgroep worden beoordeeld op relevantie en krijgen een relevantiescore toegewezen.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-161">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="4b4e7-162">Implicatie: het probleem is gestabiliseerd en batchberekening kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-162">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="4b4e7-163">Inhaalactie: Relevantie geeft aan wanneer een expert een voorbeeld van bestanden controleert en tagt die zijn geselecteerd uit een extra bestandsbelasting tijdens een scenario voor rollend laden.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-163">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="4b4e7-164">Implicatie: er is een nieuwe belasting toegevoegd en inhalen is vereist om te kunnen blijven werken.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-164">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="4b4e7-165">Tagconsequenties: Proces identificeert, via Advanced eDiscovery algoritme, inconsistenties in het proces voor het taggen van bestanden die een negatieve invloed kunnen hebben op de analyse.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-165">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="4b4e7-166">Implicatie: Het volgende voorbeeld bevat bestanden die in eerdere voorbeelden zijn gelabeld en de labels moeten opnieuw worden gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-166">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="4b4e7-167">Classificatie bijwerken: Hiermee kan de gebruiker wijzigingen aanbrengen in labels of seeding.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-167">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="4b4e7-168">Implicatie: Wijzigingen in labelen en inzaaien kunnen worden toegepast zonder dat u handmatig een ander relevantievoorbeeld hoeft uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-168">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="4b4e7-169">In de wacht: Het trainingsproces Relevantie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-169">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="4b4e7-170">Implicatie: Er is op dit moment geen relevantietraining vereist.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-170">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="4b4e7-171">Hoewel Advanced eDiscovery u door het proces begeleidt, kunt u met de aanbevolen volgende stappen in verschillende stadia ook navigeren tussen tabbladen en pagina's en keuzes maken om situaties aan te pakken die relevant kunnen zijn voor uw individuele proces voor het controleren van een zaak, probleem of document.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-171">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="4b4e7-172">Het is mogelijk om opties voor het verwerken van Advanced eDiscovery volgende stap te accepteren of te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-172">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="4b4e7-173">Als u een andere stap wilt uitvoeren dan  de aanbevolen volgende stap, klikt u op de  volgende stap die wordt weergegeven in de uit uitgebreide weergave van het probleem in het dialoogvenster, klikt u op de knop Wijzigen naast de volgende stap en selecteert u een andere optie volgende stap.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-173">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4b4e7-174">Sommige opties blijven mogelijk uitgeschakeld na het ontgrendelen, omdat ze op dat moment in het proces niet worden ondersteund voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="4b4e7-174">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="4b4e7-175">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="4b4e7-175">More information</span></span>

[<span data-ttu-id="4b4e7-176">Inzicht in beoordeling in relevantie</span><span class="sxs-lookup"><span data-stu-id="4b4e7-176">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4b4e7-177">Labelen en beoordelen</span><span class="sxs-lookup"><span data-stu-id="4b4e7-177">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4b4e7-178">Training voor labelen en relevantie</span><span class="sxs-lookup"><span data-stu-id="4b4e7-178">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4b4e7-179">Relevantieanalyse bijhouden</span><span class="sxs-lookup"><span data-stu-id="4b4e7-179">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4b4e7-180">Beslissen op basis van de resultaten</span><span class="sxs-lookup"><span data-stu-id="4b4e7-180">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4b4e7-181">Relevantieanalyse testen</span><span class="sxs-lookup"><span data-stu-id="4b4e7-181">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="4b4e7-182">Een query uitvoeren op de gegevens in een controleset</span><span class="sxs-lookup"><span data-stu-id="4b4e7-182">Query the data in a review set</span></span>](review-set-search.md)
