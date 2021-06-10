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
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="82d58-103">Labelen en beoordelen in de module Relevantie in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="82d58-103">Tagging and Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="82d58-104">In deze sectie wordt de procedure voor beoordeling beschreven in de module Relevantie in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="82d58-104">This section describes the procedure for Assessment in the Relevance module in Advanced eDiscovery.</span></span>
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="82d58-105">Evaluatietraining en -analyse uitvoeren</span><span class="sxs-lookup"><span data-stu-id="82d58-105">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="82d58-106">Klik op **het \> tabblad Relevantie** bijhouden op **Beoordeling om** een beoordeling van de zaak te starten.</span><span class="sxs-lookup"><span data-stu-id="82d58-106">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span>

    <span data-ttu-id="82d58-107">In deze procedure wordt bijvoorbeeld een steekproefbeoordelingsset van 500 bestanden gemaakt en wordt het tabblad Tag weergegeven, dat het deelvenster Labelen, weergegeven bestandsinhoud en andere opties voor labelen bevat. </span><span class="sxs-lookup"><span data-stu-id="82d58-107">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 

    ![Tabblad Relevantielabel voor beoordeling](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="82d58-109">Controleer elk bestand in het voorbeeld, bepaal de relevantie van het bestand voor elk probleem en tag het bestand met de knoppen Relevantie (R), Niet relevant (NR) en Overslaan in het deelvenster **Labelen.**</span><span class="sxs-lookup"><span data-stu-id="82d58-109">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 

    > [!NOTE]
    >  <span data-ttu-id="82d58-110">Beoordeling vereist 500 gelabelde bestanden.</span><span class="sxs-lookup"><span data-stu-id="82d58-110">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="82d58-111">Als bestanden worden overgeslagen, ontvangt u meer bestanden om te taggen.</span><span class="sxs-lookup"><span data-stu-id="82d58-111">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="82d58-112">Nadat u alle bestanden in het voorbeeld hebt gelabeld, klikt u op **Berekenen.**</span><span class="sxs-lookup"><span data-stu-id="82d58-112">After tagging all files in the sample, click **Calculate**.</span></span>

    <span data-ttu-id="82d58-113">De huidige foutmarge en -rijkdom beoordelen worden  berekend en weergegeven op het tabblad Relevantie bijhouden, met uitgebreide details per probleem, zoals hieronder wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="82d58-113">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="82d58-114">Meer informatie over dit dialoogvenster wordt beschreven in [de sectie Beoordelingsresultaten.](#reviewing-assessment-results)</span><span class="sxs-lookup"><span data-stu-id="82d58-114">More details about this dialog are described in the [Reviewing assessment results](#reviewing-assessment-results) section.</span></span>

    ![Relevantie bijhouden - Beoordeling](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="82d58-116">Het is standaard raadzaam om door te gaan met de standaardstap Volgende stap wanneer de voortgangsindicator Evaluatie voor het probleem is voltooid, wat aangeeft dat het beoordelingsvoorbeeld is beoordeeld en dat voldoende relevante bestanden zijn gelabeld.</span><span class="sxs-lookup"><span data-stu-id="82d58-116">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="82d58-117">> Als u anders de resultaten  van het tabblad Bijhouden wilt bekijken en de  foutmarge en de volgende stap wilt bepalen, klikt u op Wijzigen naast Volgende **stap,** selecteert u Doorgaan met beoordelen en klikt u vervolgens op **OK.**</span><span class="sxs-lookup"><span data-stu-id="82d58-117">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span>
  
4. <span data-ttu-id="82d58-118">Klik **rechts** van het  selectievakje Beoordeling op Wijzigen om de beoordelingsparameters per probleem weer te geven en op te geven.</span><span class="sxs-lookup"><span data-stu-id="82d58-118">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="82d58-119">Een **dialoogvenster Beoordelingsniveau** voor elk probleem wordt weergegeven, zoals wordt weergegeven in het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="82d58-119">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 

    ![Probleem op beoordelingsniveau](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="82d58-121">De volgende parameters voor het probleem worden berekend en weergegeven in het dialoogvenster **Beoordelingsniveau:**</span><span class="sxs-lookup"><span data-stu-id="82d58-121">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 

    <span data-ttu-id="82d58-122">**Doelfoutmarge voor rappelschattingen:** Op basis van deze waarde wordt het geschatte aantal extra bestanden berekend dat nodig is om te controleren.</span><span class="sxs-lookup"><span data-stu-id="82d58-122">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="82d58-123">De marge die wordt gebruikt voor inroepen is groter dan 75% en met een betrouwbaarheidsniveau van 95%.</span><span class="sxs-lookup"><span data-stu-id="82d58-123">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span>

    <span data-ttu-id="82d58-124">**Extra beoordelingsbestanden vereist:** geeft aan hoeveel bestanden er nog nodig zijn als niet aan de huidige foutmarge is voldaan.</span><span class="sxs-lookup"><span data-stu-id="82d58-124">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 

5. <span data-ttu-id="82d58-125">De huidige foutmarge aanpassen en het effect van verschillende foutmarges (per probleem) bekijken:</span><span class="sxs-lookup"><span data-stu-id="82d58-125">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>

6. <span data-ttu-id="82d58-126">Selecteer een **probleem in de** lijst Probleem selecteren.</span><span class="sxs-lookup"><span data-stu-id="82d58-126">In the **Select issue** list, select an issue.</span></span> 

7. <span data-ttu-id="82d58-127">Voer **in Doelfoutmarge voor schatting van inroepen** een nieuwe waarde in.</span><span class="sxs-lookup"><span data-stu-id="82d58-127">In **Target error margin for recall estimates**, enter a new value.</span></span>

8. <span data-ttu-id="82d58-128">Klik **op Waarden bijwerken** om het effect van de aanpassingen te zien.</span><span class="sxs-lookup"><span data-stu-id="82d58-128">Click **Update values** to see the impact of the adjustments.</span></span> 

9. <span data-ttu-id="82d58-129">Klik **op Geavanceerd** in het dialoogvenster **Beoordelingsniveau** om de volgende aanvullende parameters en details te zien:</span><span class="sxs-lookup"><span data-stu-id="82d58-129">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 

    ![Geavanceerde weergave case-probleem op beoordelingsniveau](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - <span data-ttu-id="82d58-131">**Geschatte rijkheid:** Geschatte rijkheid op basis van de huidige evaluatieresultaten</span><span class="sxs-lookup"><span data-stu-id="82d58-131">**Estimated richness**: Estimated richness according to the current assessment results</span></span>

    - <span data-ttu-id="82d58-132">**Voor veronderstelde inroeping:** De doelfoutmarge is standaard van toepassing op inroepen boven 75%.</span><span class="sxs-lookup"><span data-stu-id="82d58-132">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="82d58-133">Klik **op Bewerken** als u deze parameter wilt wijzigen en de foutmarge voor een ander bereik met inroepwaarden wilt bepalen.</span><span class="sxs-lookup"><span data-stu-id="82d58-133">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 

    - <span data-ttu-id="82d58-134">**Betrouwbaarheidsniveau:** Standaard is de aanbevolen foutmarge voor betrouwbaarheid 95%.</span><span class="sxs-lookup"><span data-stu-id="82d58-134">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="82d58-135">Klik **op Bewerken** als u deze parameter wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="82d58-135">Click **Edit** if you want to change this parameter.</span></span>

    - <span data-ttu-id="82d58-136">**Verwachte foutenmarge :** Gezien de bijgewerkte waarden is dit de verwachte foutmarge van de rijkheid, nadat alle aanvullende beoordelingsbestanden zijn gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="82d58-136">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>

    - <span data-ttu-id="82d58-137">**Aanvullende beoordelingsbestanden vereist:** gezien de bijgewerkte waarden, het aantal extra beoordelingsbestanden dat moet worden gecontroleerd om het doel te bereiken.</span><span class="sxs-lookup"><span data-stu-id="82d58-137">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>

    - <span data-ttu-id="82d58-138">**Totaal vereiste beoordelingsbestanden:** Gezien de bijgewerkte waarden zijn de totale beoordelingsbestanden vereist voor controle.</span><span class="sxs-lookup"><span data-stu-id="82d58-138">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>

    - <span data-ttu-id="82d58-139">**Verwacht aantal relevante bestanden in de beoordeling:** gezien de bijgewerkte waarden, wordt het verwachte aantal relevante bestanden in de hele beoordeling gecontroleerd nadat alle aanvullende beoordelingsbestanden zijn beoordeeld.</span><span class="sxs-lookup"><span data-stu-id="82d58-139">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>

10. <span data-ttu-id="82d58-140">Klik **op Waarden herberekenen** als parameters worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="82d58-140">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="82d58-141">Wanneer u klaar bent, als er één probleem is, klikt u op **OK** om de wijzigingen op te slaan (of **Volgende** wanneer er meerdere problemen zijn die u moet controleren of wijzigen en vervolgens **voltooien).**</span><span class="sxs-lookup"><span data-stu-id="82d58-141">When you're done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 

    <span data-ttu-id="82d58-142">Wanneer er meerdere problemen zijn, wordt, nadat alle problemen zijn beoordeeld of aangepast, een dialoogvenster **Beoordelingsniveau:** samenvatting weergegeven, zoals wordt weergegeven in het volgende voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="82d58-142">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 

    ![Overzicht van beoordelingsniveau](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="82d58-144">Als de evaluatie is voltooid, gaat u verder met de volgende fase in de relevantietraining.</span><span class="sxs-lookup"><span data-stu-id="82d58-144">On successful completion of assessment, proceed to the next stage in Relevance training.</span></span>

## <a name="reviewing-assessment-results"></a><span data-ttu-id="82d58-145">Beoordelingsresultaten bekijken</span><span class="sxs-lookup"><span data-stu-id="82d58-145">Reviewing assessment results</span></span>

<span data-ttu-id="82d58-146">Nadat een evaluatievoorbeeld is gelabeld, worden de beoordelingsresultaten berekend en weergegeven op het tabblad Relevantie bijhouden.</span><span class="sxs-lookup"><span data-stu-id="82d58-146">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="82d58-147">De volgende resultaten worden weergegeven in de uitgebreide weergave Bijhouden:</span><span class="sxs-lookup"><span data-stu-id="82d58-147">The following results are displayed in the expanded Track display:</span></span>
  
- <span data-ttu-id="82d58-148">Huidige foutmarge voor schattingen voor inroepen beoordelen</span><span class="sxs-lookup"><span data-stu-id="82d58-148">Assessment current error margin for recall estimates</span></span>

- <span data-ttu-id="82d58-149">Geschatte rijkheid</span><span class="sxs-lookup"><span data-stu-id="82d58-149">Estimated richness</span></span>

- <span data-ttu-id="82d58-150">Aanvullende beoordelingsbestanden vereist (voor controle)</span><span class="sxs-lookup"><span data-stu-id="82d58-150">Additional assessment files required (for review)</span></span>

<span data-ttu-id="82d58-151">De huidige foutmarge beoordelen is de foutmarge die wordt aanbevolen door Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="82d58-151">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="82d58-152">Het getal dat wordt weergegeven voor de 'Aanvullende beoordelingsbestanden vereist' komt overeen met die aanbeveling.</span><span class="sxs-lookup"><span data-stu-id="82d58-152">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="82d58-153">De voortgangsindicator Beoordeling geeft het niveau van voltooiing van de beoordeling aan, gezien de huidige foutmarge.</span><span class="sxs-lookup"><span data-stu-id="82d58-153">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="82d58-154">Wanneer de evaluatie aan de gang is, tagt de gebruiker een ander beoordelingsvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="82d58-154">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="82d58-155">Wanneer de beoordelingsvoortgangsindicator de beoordeling als voltooid weggedreed, betekent dit dat de evaluatie steekproefbeoordeling is voltooid en dat voldoende relevante bestanden zijn gelabeld.</span><span class="sxs-lookup"><span data-stu-id="82d58-155">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="82d58-156">De uitgebreide weergave Bijhouden toont de aanbevolen volgende stap, de beoordelingsstatistieken en toegang tot gedetailleerde resultaten.</span><span class="sxs-lookup"><span data-stu-id="82d58-156">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="82d58-157">Wanneer de rijkheid erg laag is, is het aantal extra beoordelingsbestanden dat nodig is om een minimaal aantal relevante bestanden te bereiken, zeer hoog om nuttige statistieken te maken.</span><span class="sxs-lookup"><span data-stu-id="82d58-157">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="82d58-158">Advanced eDiscovery raadt u aan over te gaan op de training.</span><span class="sxs-lookup"><span data-stu-id="82d58-158">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="82d58-159">De indicator voor de voortgang van de beoordeling wordt gearceerd en er zijn geen statistieken beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="82d58-159">The assessment progress indicator will be shaded, and no statistics will be available.</span></span>
  
<span data-ttu-id="82d58-160">Als er geen statistische stabilisatie is, zijn er resultaten met een lager nauwkeurigheids- en betrouwbaarheidsniveau.</span><span class="sxs-lookup"><span data-stu-id="82d58-160">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="82d58-161">Deze resultaten kunnen echter worden gebruikt om relevante bestanden te vinden wanneer u niet het percentage gevonden relevante bestanden hoeft te weten.</span><span class="sxs-lookup"><span data-stu-id="82d58-161">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="82d58-162">Op dezelfde manier kan deze status worden gebruikt om problemen met een lage rijkheid op te leiden, waarbij relevantiescores de toegang tot bestanden die relevant zijn voor een specifiek probleem kunnen versnellen.</span><span class="sxs-lookup"><span data-stu-id="82d58-162">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="82d58-163">Op het **tabblad \> Relevantie** bijhouden, uit uitgebreid probleemweergave, zijn de volgende weergaveopties beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="82d58-163">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available:</span></span> 
> 
> <span data-ttu-id="82d58-164">De aanbevolen volgende stap, zoals **Volgende stap:** Labelen kan worden  overgeslagen (per probleem) door op de knop Wijzigen rechts te klikken en vervolgens een andere stap te selecteren in **de volgende stap.**</span><span class="sxs-lookup"><span data-stu-id="82d58-164">The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="82d58-165">Wanneer de indicator voor de voortgang van de beoordeling nog niet is voltooid, is evaluatie de volgende aanbevolen optie om meer beoordelingsbestanden te taggen en de nauwkeurigheid van de statistieken te verhogen.</span><span class="sxs-lookup"><span data-stu-id="82d58-165">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> 
> 
> <span data-ttu-id="82d58-166">U kunt de foutmarge wijzigen en de impact ervan beoordelen door te klikken op Wijzigen **en** in het dialoogvenster Beoordelingsniveau **de** foutmarge Doel voor inroepingsschattingen te wijzigen en op Waarden bijwerken **te klikken.** </span><span class="sxs-lookup"><span data-stu-id="82d58-166">You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="82d58-167">In dit dialoogvenster kunt u ook geavanceerde opties weergeven door op Geavanceerd te **klikken.**</span><span class="sxs-lookup"><span data-stu-id="82d58-167">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> 
> 
> <span data-ttu-id="82d58-168">U kunt aanvullende statistieken op beoordelingsniveau en de impact ervan bekijken door op **Weergave te klikken.**</span><span class="sxs-lookup"><span data-stu-id="82d58-168">You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="82d58-169">In het dialoogvenster Weergegeven detailresultaten zijn statistieken per probleem beschikbaar, wanneer er ten minste 500 gelabelde beoordelingsbestanden zijn en ten minste 18 bestanden zijn gemarkeerd als Relevant voor het probleem.</span><span class="sxs-lookup"><span data-stu-id="82d58-169">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
