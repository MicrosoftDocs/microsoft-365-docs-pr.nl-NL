---
title: Relevantieanalyse bijhouden in Advanced eDiscovery
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het weergeven en interpreteren van de relevantietrainingsstatus en -resultaten voor caseproblemen in Advanced eDiscovery.
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161666"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="9c027-103">Relevantieanalyse bijhouden in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="9c027-103">Track Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="9c027-104">Op Advanced eDiscovery tabblad Relevantie bijhouden wordt de berekende geldigheid weergegeven van de relevantietraining die wordt uitgevoerd op het tabblad Tag en wordt de volgende stap aangegeven in het iteratieve trainingsproces in Relevantie.</span><span class="sxs-lookup"><span data-stu-id="9c027-104">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="9c027-105">Trainingsstatus relevantie bijhouden</span><span class="sxs-lookup"><span data-stu-id="9c027-105">Tracking Relevance training status</span></span>

1. <span data-ttu-id="9c027-106">Bekijk de volgende details in Relevantie bijhouden voor de problemen met de zaak, zoals wordt weergegeven in het volgende voorbeeld van het dialoogvenster **Naam** van probleem hieronder.</span><span class="sxs-lookup"><span data-stu-id="9c027-106">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span>

   - <span data-ttu-id="9c027-107">**Beoordeling:** Deze voortgangsindicator geeft aan in welke mate de relevantietraining die tot nu toe is uitgevoerd, het beoordelingsdoel heeft bereikt in termen van foutmarge.</span><span class="sxs-lookup"><span data-stu-id="9c027-107">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="9c027-108">De rijkheid van de resultaten van de relevantietraining wordt ook weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9c027-108">The richness of the Relevance training results is also displayed.</span></span>

   - <span data-ttu-id="9c027-109">**Training:** Met deze indicator voor de voortgang met kleurcode en de knoptip worden de stabiliteit van de relevantietrainingsresultaten en een numerieke schaal aangegeven met het aantal relevantietrainingsvoorbeelden dat voor elk probleem is gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="9c027-109">**Training**: This color-coded progress indicator and tool-tip indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="9c027-110">De expert houdt de voortgang van het iteratieve trainingsproces relevantie bij.</span><span class="sxs-lookup"><span data-stu-id="9c027-110">The expert monitors the progress of the iterative Relevance training process.</span></span> 
  
   - <span data-ttu-id="9c027-111">**Batchberekening:** Deze voortgangsindicator bevat informatie over de voltooiing van batchberekening.</span><span class="sxs-lookup"><span data-stu-id="9c027-111">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
  
   - <span data-ttu-id="9c027-112">**Volgende stap:** geeft de aanbeveling weer voor de volgende stap die moet worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="9c027-112">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
  
    <span data-ttu-id="9c027-113">In het voorbeeld wordt een voltooide evaluatie voor een probleem weergegeven, aangegeven met de indicator voltooide kleurvergang en het vinkje.</span><span class="sxs-lookup"><span data-stu-id="9c027-113">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="9c027-114">Tagging is aan de gang, maar de zaak wordt nog steeds als instabiel beschouwd (stabiliteitsstatus wordt ook weergegeven in een tool-tip).</span><span class="sxs-lookup"><span data-stu-id="9c027-114">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="9c027-115">De volgende stapaanbeveling is 'Training'.</span><span class="sxs-lookup"><span data-stu-id="9c027-115">The next step recommendation is "Training".</span></span> 
  
    ![Training voor relevantie bijhouden stap 1](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="9c027-117">In de uit uitgebreide weergave worden extra informatie en opties weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9c027-117">The expanded view displays additional information and options.</span></span> <span data-ttu-id="9c027-118">De weergegeven huidige foutmarge is de foutmarge van het inroepen in de huidige beoordelingstoestand, gezien de bestaande (al gelabelde) beoordelingsbestanden.</span><span class="sxs-lookup"><span data-stu-id="9c027-118">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="9c027-119">De evaluatiefase kan worden overgeslagen door het **selectievakje** Beoordeling per probleem uit te wissen en vervolgens voor 'alle problemen'.</span><span class="sxs-lookup"><span data-stu-id="9c027-119">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="9c027-120">Hierdoor zijn er echter geen statistieken voor dit probleem.</span><span class="sxs-lookup"><span data-stu-id="9c027-120">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="9c027-121">> Het selectievakje **Beoordeling** wissen kan alleen worden uitgevoerd voordat de evaluatie wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="9c027-121">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="9c027-122">Als er meerdere problemen zijn in een zaak, wordt de beoordeling alleen overgeslagen als het selectievakje voor elk probleem is gewist</span><span class="sxs-lookup"><span data-stu-id="9c027-122">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="9c027-123">Wanneer de beoordeling niet is voltooid met de eerste voorbeeldset bestanden, is beoordeling mogelijk de volgende stap voor het labelen van meer bestanden.</span><span class="sxs-lookup"><span data-stu-id="9c027-123">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span>
  
    <span data-ttu-id="9c027-124">In **Relevantie** bijhouden geven de indicator voor de voortgang van de training en de tool-tip het geschatte aantal extra steekproeven aan dat nodig is om de stabiliteit te \> bereiken.</span><span class="sxs-lookup"><span data-stu-id="9c027-124">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="9c027-125">Deze schatting bevat een richtlijn voor de benodigde aanvullende training.</span><span class="sxs-lookup"><span data-stu-id="9c027-125">This estimate provides a guideline for the additional training needed.</span></span>
  
    ![Training voor relevantie bijhouden](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="9c027-127">Wanneer u klaar bent met labelen en als u de training wilt voortzetten, klikt u op **Training.**</span><span class="sxs-lookup"><span data-stu-id="9c027-127">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="9c027-128">Een andere voorbeeldset met bestanden wordt gegenereerd uit de geladen bestandsset voor extra training.</span><span class="sxs-lookup"><span data-stu-id="9c027-128">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="9c027-129">Vervolgens keert u terug naar het tabblad Tag om meer bestanden te taggen en te trainen.</span><span class="sxs-lookup"><span data-stu-id="9c027-129">You are then returned to the Tag tab to tag and train more files.</span></span>

### <a name="reaching-stable-training-levels"></a><span data-ttu-id="9c027-130">Stabiele trainingsniveaus bereiken</span><span class="sxs-lookup"><span data-stu-id="9c027-130">Reaching stable training levels</span></span>

<span data-ttu-id="9c027-131">Nadat de beoordelingsbestanden een stabiel trainingsniveau hebben bereikt, is Advanced eDiscovery klaar voor batchberekening.</span><span class="sxs-lookup"><span data-stu-id="9c027-131">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9c027-132">Meestal is de volgende stap na drie stabiele trainingsvoorbeelden 'Batchberekening'.</span><span class="sxs-lookup"><span data-stu-id="9c027-132">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="9c027-133">Er kunnen uitzonderingen zijn, bijvoorbeeld wanneer er wijzigingen zijn aangebracht in het labelen van bestanden uit eerdere steekproeven of wanneer seedbestanden zijn toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="9c027-133">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="9c027-134">Batchberekening uitvoeren</span><span class="sxs-lookup"><span data-stu-id="9c027-134">Performing Batch calculation</span></span>

<span data-ttu-id="9c027-135">Batchberekening wordt uitgevoerd als de volgende stap nadat de training is voltooid (wanneer een stabiele trainingsstatus wordt weergegeven door de voortgangsbalk, een vinkje en een stabiele status in de tool-tip.) Batchberekening past de kennis die tijdens de relevantietraining is verkregen toe op de hele bestandspopulatie, om de relevantie van de bestanden te beoordelen en relevantiescores toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="9c027-135">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="9c027-136">Wanneer er meer dan één probleem is, wordt batchberekening per probleem uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="9c027-136">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="9c027-137">Tijdens batchberekening wordt de voortgang bij het verwerken van alle bestanden gecontroleerd.</span><span class="sxs-lookup"><span data-stu-id="9c027-137">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="9c027-138">Hier is de aanbevolen volgende stap 'Geen', wat aangeeft dat er op dit moment geen extra iteratieve relevantietraining nodig is.</span><span class="sxs-lookup"><span data-stu-id="9c027-138">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="9c027-139">De volgende fase is het **tabblad \> Relevantie** bepalen.</span><span class="sxs-lookup"><span data-stu-id="9c027-139">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="9c027-140">Als u nieuwe bestanden wilt importeren na batchberekening, kan de beheerder de geïmporteerde bestanden toevoegen aan een nieuwe belasting.</span><span class="sxs-lookup"><span data-stu-id="9c027-140">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9c027-141">Als u op **Annuleren klikt** tijdens de berekening van batch, wordt in het proces op slaat wat al is uitgevoerd op.</span><span class="sxs-lookup"><span data-stu-id="9c027-141">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="9c027-142">Als u batchberekening opnieuw uitwerkt, wordt het proces voortgezet vanaf het laatst uitgevoerde punt.</span><span class="sxs-lookup"><span data-stu-id="9c027-142">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="9c027-143">Labelconsistentie beoordelen</span><span class="sxs-lookup"><span data-stu-id="9c027-143">Assessing tagging consistency</span></span>

<span data-ttu-id="9c027-144">Als er inconsistenties zijn in het labelen van bestanden, kan dit van invloed zijn op de analyse.</span><span class="sxs-lookup"><span data-stu-id="9c027-144">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="9c027-145">De Advanced eDiscovery kan worden gebruikt wanneer de resultaten niet optimaal zijn of als de consistentie in twijfel wordt 2019.</span><span class="sxs-lookup"><span data-stu-id="9c027-145">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="9c027-146">Er wordt een lijst met mogelijk inconsistent gelabelde bestanden geretourneerd en deze kunnen zo nodig worden gecontroleerd en opnieuw getagd.</span><span class="sxs-lookup"><span data-stu-id="9c027-146">A list of possible inconsistently tagged files is returned, and they can be reviewed and retagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9c027-147">Na zeven of meer trainingsronden na de evaluatie kan de consistentie van labels worden bekeken in **Relevant** \> **Track** \> **Issue** \> **Gedetailleerde resultaten** Trainings \> **voortgang.**</span><span class="sxs-lookup"><span data-stu-id="9c027-147">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="9c027-148">Deze beoordeling wordt voor één probleem tegelijk uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="9c027-148">This review is done for one issue at a time.</span></span>
  
1. <span data-ttu-id="9c027-149">Vouw **in \> Relevantie bijhouden** de rij van een probleem uit.</span><span class="sxs-lookup"><span data-stu-id="9c027-149">In **Relevance \> Track**, expand an issue's row.</span></span>
  
2. <span data-ttu-id="9c027-150">Klik rechts van **Volgende stap** op **Wijzigen.**</span><span class="sxs-lookup"><span data-stu-id="9c027-150">To the right of **Next step**, click **Modify**.</span></span>
  
3. <span data-ttu-id="9c027-151">Selecteer **Inconsistenties taggen** als **de optie Volgende stap,** na zeven trainingsvoorbeelden en klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="9c027-151">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
  
4. <span data-ttu-id="9c027-152">Selecteer **Inconsistenties met tags.**</span><span class="sxs-lookup"><span data-stu-id="9c027-152">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="9c027-153">Het **tabblad Tag** wordt geopend met een lijst met inconsistenties die zo nodig opnieuw moeten worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9c027-153">The **Tag** tab opens displaying a list of the inconsistencies to retag as necessary.</span></span>
  
5. <span data-ttu-id="9c027-154">Klik **op Berekenen** om de wijzigingen in te dienen.</span><span class="sxs-lookup"><span data-stu-id="9c027-154">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="9c027-155">De volgende stap na het labelen van inconsistenties is 'Training'.</span><span class="sxs-lookup"><span data-stu-id="9c027-155">The next step after tagging inconsistencies is "Training".</span></span> 
  
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="9c027-156">Relevantieresultaten weergeven en gebruiken</span><span class="sxs-lookup"><span data-stu-id="9c027-156">Viewing and using Relevance results</span></span>

<span data-ttu-id="9c027-157">Vouw op het tabblad **\> Relevantie** bijhouden de rij van een probleem uit en klik naast **Gedetailleerde resultaten** op **Weergave.**</span><span class="sxs-lookup"><span data-stu-id="9c027-157">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="9c027-158">De deelvensters Gedetailleerde resultaten worden weergegeven, zoals hieronder wordt weergegeven en beschreven.</span><span class="sxs-lookup"><span data-stu-id="9c027-158">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![Gedetailleerde resultaten van relevantietraining](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="9c027-160">Overzicht van labelen</span><span class="sxs-lookup"><span data-stu-id="9c027-160">Tagging summary</span></span>

 <span data-ttu-id="9c027-161">In het onderstaande voorbeeld worden in de samenvatting **Labelen** totalen weergegeven voor elk van de processen voor beoordeling, training en bijvangstbestandslabels.</span><span class="sxs-lookup"><span data-stu-id="9c027-161">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span>
  
![Overzicht van relevantielabels bijhouden](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="9c027-163">Trefwoorden</span><span class="sxs-lookup"><span data-stu-id="9c027-163">Keywords</span></span>

<span data-ttu-id="9c027-164">Een trefwoord is een unieke tekenreeks, woord, woordgroep of reeks woorden in een bestand dat is geïdentificeerd door Advanced eDiscovery als een significante indicator voor de vraag of een bestand relevant is.</span><span class="sxs-lookup"><span data-stu-id="9c027-164">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="9c027-165">Het trefwoord 'Kolommen opnemen' en de gewichten in bestanden die zijn gemarkeerd als Relevant, en de kolommen 'Uitsluiten' bevatten trefwoorden en gewichten in bestanden die zijn gemarkeerd als Niet relevant.</span><span class="sxs-lookup"><span data-stu-id="9c027-165">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="9c027-166">Advanced eDiscovery wijst negatieve of positieve trefwoordgewichtswaarden toe.</span><span class="sxs-lookup"><span data-stu-id="9c027-166">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="9c027-167">Hoe hoger het gewicht, hoe groter de kans dat een bestand waarin het trefwoord wordt weergegeven, een hogere relevantiescore krijgt toegewezen tijdens de berekening van batch.</span><span class="sxs-lookup"><span data-stu-id="9c027-167">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span>
  
<span data-ttu-id="9c027-168">De Advanced eDiscovery lijst met trefwoorden kan worden gebruikt om een lijst aan te vullen die is gemaakt door een expert of als een indirecte sanity-controle op elk moment in het proces voor bestandscontrole.</span><span class="sxs-lookup"><span data-stu-id="9c027-168">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="9c027-169">Voortgang van de training</span><span class="sxs-lookup"><span data-stu-id="9c027-169">Training progress</span></span>

<span data-ttu-id="9c027-170">Het **deelvenster Trainings voortgang** bevat een grafiek van de trainings voortgang en een kwaliteitsindicator, zoals wordt weergegeven in het onderstaande voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="9c027-170">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span>
  
![Voortgang van training voor relevantie bijhouden](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
<span data-ttu-id="9c027-172">**Indicator voor trainingskwaliteit:** geeft als volgt de beoordeling van de labelconsistentie weer:</span><span class="sxs-lookup"><span data-stu-id="9c027-172">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="9c027-173">**Goed:** Bestanden worden consistent gelabeld.</span><span class="sxs-lookup"><span data-stu-id="9c027-173">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="9c027-174">(Groen licht weergegeven)</span><span class="sxs-lookup"><span data-stu-id="9c027-174">(Green light displayed)</span></span>
  
- <span data-ttu-id="9c027-175">**Medium:** Sommige bestanden kunnen inconsistent zijn gelabeld.</span><span class="sxs-lookup"><span data-stu-id="9c027-175">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="9c027-176">(Geel licht weergegeven)</span><span class="sxs-lookup"><span data-stu-id="9c027-176">(Yellow light displayed)</span></span>

- <span data-ttu-id="9c027-177">**Waarschuwing:** Veel bestanden kunnen inconsistent zijn gelabeld.</span><span class="sxs-lookup"><span data-stu-id="9c027-177">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="9c027-178">(Rood licht weergegeven)</span><span class="sxs-lookup"><span data-stu-id="9c027-178">(Red light displayed)</span></span>

<span data-ttu-id="9c027-179">**Trainingsverloopgrafiek:** geeft de mate van relevantietrainingsstabiliteit weer na veel relevantietrainingscyclussen in vergelijking met de F-metingswaarde.</span><span class="sxs-lookup"><span data-stu-id="9c027-179">**Training progress graph**: Shows the degree of Relevance training stability after many Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="9c027-180">Als we van links naar rechts over de grafiek gaan, wordt het betrouwbaarheidsinterval smaller en wordt het gebruikt, samen met de F-meting, door Advanced eDiscovery Relevantie om de stabiliteit te bepalen wanneer de relevantietrainingsresultaten zijn geoptimaliseerd.</span><span class="sxs-lookup"><span data-stu-id="9c027-180">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9c027-181">Relevantie maakt gebruik van F2, een F-metingsmetrische waarde waarbij Inroepen tweemaal zoveel gewicht krijgt als Precisie.</span><span class="sxs-lookup"><span data-stu-id="9c027-181">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="9c027-182">Voor gevallen met een hoge rijkheid (meer dan 25%) wordt gebruikgemaakt van F1 (verhouding 1:1).</span><span class="sxs-lookup"><span data-stu-id="9c027-182">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="9c027-183">De verhouding F-meting kan worden geconfigureerd in **De relevantie-instelling** \> **Geavanceerde instellingen.**</span><span class="sxs-lookup"><span data-stu-id="9c027-183">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span>
  
### <a name="batch-calculation-results"></a><span data-ttu-id="9c027-184">Resultaten van batchberekening</span><span class="sxs-lookup"><span data-stu-id="9c027-184">Batch calculation results</span></span>

<span data-ttu-id="9c027-185">Het **deelvenster Resultaten van batchberekening** bevat het aantal bestanden dat is gescored voor Relevantie, als volgt:</span><span class="sxs-lookup"><span data-stu-id="9c027-185">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="9c027-186">**Succes**</span><span class="sxs-lookup"><span data-stu-id="9c027-186">**Success**</span></span>
  
- <span data-ttu-id="9c027-187">**Leeg:** bevat geen tekst, bijvoorbeeld alleen spaties/tabbladen</span><span class="sxs-lookup"><span data-stu-id="9c027-187">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
  
- <span data-ttu-id="9c027-188">**Mislukt:** Vanwege een te grote grootte of omdat deze niet kan worden gelezen</span><span class="sxs-lookup"><span data-stu-id="9c027-188">**Failed**: Due to excessive size or could not be read</span></span>
  
- <span data-ttu-id="9c027-189">**Genegeerd:** Vanwege de te grote grootte</span><span class="sxs-lookup"><span data-stu-id="9c027-189">**Ignored**: Due to excessive size</span></span>
  
- <span data-ttu-id="9c027-190">**Nevelig:** bevat betekenisloze tekst of geen functies die relevant zijn voor het probleem</span><span class="sxs-lookup"><span data-stu-id="9c027-190">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
  
> [!NOTE]
> <span data-ttu-id="9c027-191">Leeg, Mislukt, Genegeerd of Nebulous ontvangt een relevantiescore van -1.</span><span class="sxs-lookup"><span data-stu-id="9c027-191">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span>
  
### <a name="training-statistics"></a><span data-ttu-id="9c027-192">Trainingsstatistieken</span><span class="sxs-lookup"><span data-stu-id="9c027-192">Training statistics</span></span>

<span data-ttu-id="9c027-193">In **het deelvenster Trainingsstatistieken** worden statistieken en grafieken weergegeven op basis van resultaten Advanced eDiscovery Relevantietraining.</span><span class="sxs-lookup"><span data-stu-id="9c027-193">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![Trainingsstatistieken voor relevantie bijhouden](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="9c027-195">In deze weergave ziet u het volgende:</span><span class="sxs-lookup"><span data-stu-id="9c027-195">This view shows the following:</span></span>
  
- <span data-ttu-id="9c027-196">**Beoordelings-terugroepverhouding:** Vergelijking van resultaten op basis van relevantiescores in een hypothetisch lineair overzicht.</span><span class="sxs-lookup"><span data-stu-id="9c027-196">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="9c027-197">Inroepen wordt geschat, gezien de grootteset voor revisiesets.</span><span class="sxs-lookup"><span data-stu-id="9c027-197">Recall is estimated given the review set size set.</span></span>
  
- <span data-ttu-id="9c027-198">**Parameters:** Cumulatieve berekende statistieken met betrekking tot de revisieset ten opzichte van de bestandspopulatie voor het hele geval.</span><span class="sxs-lookup"><span data-stu-id="9c027-198">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
  
- <span data-ttu-id="9c027-199">**Controleren:** Percentage bestanden dat u wilt controleren op basis van deze cutoff.</span><span class="sxs-lookup"><span data-stu-id="9c027-199">**Review**: Percentage of files to review based on this cutoff.</span></span>
  
- <span data-ttu-id="9c027-200">**Inroepen:** Percentage relevante bestanden in de revisieset.</span><span class="sxs-lookup"><span data-stu-id="9c027-200">**Recall**: Percentage of Relevant files in the review set.</span></span> 
  
- <span data-ttu-id="9c027-201">**Verdeling op relevantiescore:** Bestanden in de donkergrijse weergave aan de linkerkant staan onder de cutoffscore.</span><span class="sxs-lookup"><span data-stu-id="9c027-201">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="9c027-202">Met een knoptip worden de relevantiescore en het gerelateerde percentage bestanden weergegeven in het revisiebestand dat is ingesteld ten opzichte van het totale aantal bestanden.</span><span class="sxs-lookup"><span data-stu-id="9c027-202">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
