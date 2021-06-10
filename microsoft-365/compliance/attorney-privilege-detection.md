---
title: Detectie van advocaten-clientrechten instellen in Advanced eDiscovery
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
ms.assetid: ''
description: Gebruik het detectiemodel voor advocaten-clientprivilege om op machine learning gebaseerde detectie van bevoorrechte inhoud te gebruiken bij het bekijken van inhoud in een Advanced eDiscovery geval.
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/03/2020
ms.locfileid: "52161491"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="52211-103">Detectie van advocaten-clientrechten instellen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="52211-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="52211-104">Een belangrijk en duur aspect van de revisiefase van een eDiscovery-proces is het controleren van documenten op bevoorrechte inhoud.</span><span class="sxs-lookup"><span data-stu-id="52211-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="52211-105">Advanced eDiscovery biedt machine learning-gebaseerde detectie van bevoorrechte inhoud om dit proces efficiënter te maken.</span><span class="sxs-lookup"><span data-stu-id="52211-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="52211-106">Deze functie wordt de *detectie van advocaten-clientvoorrechten genoemd.*</span><span class="sxs-lookup"><span data-stu-id="52211-106">This feature is called *attorney-client privilege detection*.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="52211-107">Hoe werkt dit?</span><span class="sxs-lookup"><span data-stu-id="52211-107">How does it work?</span></span>

<span data-ttu-id="52211-108">Wanneer de detectie van advocaten-clientrechten is ingeschakeld, worden alle documenten in een revisieset verwerkt door het detectiemodel voor advocaten-clientrechten wanneer u de gegevens [in](analyzing-data-in-review-set.md) de revisieset analyseert.</span><span class="sxs-lookup"><span data-stu-id="52211-108">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="52211-109">Het model zoekt naar twee dingen:</span><span class="sxs-lookup"><span data-stu-id="52211-109">The model looks for two things:</span></span>

- <span data-ttu-id="52211-110">Bevoorrechte inhoud: het model maakt gebruik van machine learning om de kans te bepalen dat het document inhoud bevat die juridisch van aard is.</span><span class="sxs-lookup"><span data-stu-id="52211-110">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="52211-111">Deelnemers: als onderdeel van het instellen van de detectie van advocaten-clientrechten, moet u een lijst met advocaten voor uw organisatie indienen.</span><span class="sxs-lookup"><span data-stu-id="52211-111">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="52211-112">Het model vergelijkt vervolgens de deelnemers aan het document met de lijst met advocaten om te bepalen of een document ten minste één deelnemer aan de advocatenlijst heeft.</span><span class="sxs-lookup"><span data-stu-id="52211-112">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="52211-113">Het model produceert de volgende drie eigenschappen voor elk document:</span><span class="sxs-lookup"><span data-stu-id="52211-113">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="52211-114">**AttorneyClientPrivilegeScore:** De kans dat het document juridisch van aard is; de waarden voor de score liggen tussen **0** en **1**.</span><span class="sxs-lookup"><span data-stu-id="52211-114">**AttorneyClientPrivilegeScore:** The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="52211-115">**HasAttorney:** Deze eigenschap is ingesteld op **waar** als een van de deelnemers aan het document wordt vermeld in de lijst met advocaten. anders is de waarde **onwaar.**</span><span class="sxs-lookup"><span data-stu-id="52211-115">**HasAttorney:** This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="52211-116">De waarde is ook ingesteld op **onwaar** als uw organisatie geen advocatenlijst heeft geüpload.</span><span class="sxs-lookup"><span data-stu-id="52211-116">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="52211-117">**IsPrivilege:** Deze eigenschap is ingesteld op **waar** als de waarde voor **AttorneyClientPrivilegeScore** boven de drempel ligt of als het document een deelnemer aan de advocatenlijst heeft.  anders is de waarde ingesteld op **onwaar**.</span><span class="sxs-lookup"><span data-stu-id="52211-117">**IsPrivilege:** This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="52211-118">Deze eigenschappen (en de bijbehorende waarden) worden toegevoegd aan de bestandsmetagegevens van de documenten in een revisieset, zoals wordt weergegeven in de volgende schermafbeelding:</span><span class="sxs-lookup"><span data-stu-id="52211-118">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![Eigenschappen van advocaten-clientrechten die worden weergegeven in bestandsmetagegevens](../media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="52211-120">Deze drie eigenschappen kunnen ook worden doorzocht in een revisieset.</span><span class="sxs-lookup"><span data-stu-id="52211-120">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="52211-121">Zie Query's [uitvoeren op de gegevens in een revisieset voor meer informatie.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="52211-121">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="52211-122">Het detectiemodel voor advocaten-clientrechten instellen</span><span class="sxs-lookup"><span data-stu-id="52211-122">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="52211-123">Als u het detectiemodel voor advocaten-clientrechten wilt inschakelen, moet uw organisatie het inschakelen en vervolgens een lijst met advocaten uploaden.</span><span class="sxs-lookup"><span data-stu-id="52211-123">To enable the attorney-client privilege detection model, your organization has to turn it on and then upload an attorney list.</span></span>

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a><span data-ttu-id="52211-124">Stap 1: Detectie van advocaten-clientrechten in- en uit-</span><span class="sxs-lookup"><span data-stu-id="52211-124">Step 1: Turn on attorney-client privilege detection</span></span>

<span data-ttu-id="52211-125">Een persoon die een eDiscovery-beheerder in uw organisatie is (lid van de subgroep eDiscovery-beheerder in de rollengroep eDiscovery Manager) moet het model beschikbaar stellen in uw Advanced eDiscovery gevallen.</span><span class="sxs-lookup"><span data-stu-id="52211-125">A person who is an eDiscovery Administrator in your organization (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="52211-126">Ga in het & Compliancecentrum naar **eDiscovery > Advanced eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="52211-126">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="52211-127">Klik op **Advanced eDiscovery** startpagina in  de Instellingen op Globale analyse-instellingen **configureren.**</span><span class="sxs-lookup"><span data-stu-id="52211-127">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure global analytics settings**.</span></span>

   ![Selecteer 'Experimentele functies configureren'](../media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="52211-129">Selecteer op **het tabblad Analyse-instellingen** **de instelling Advocaten-clientvoorrecht beheren.**</span><span class="sxs-lookup"><span data-stu-id="52211-129">On the **Analytics settings** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="52211-130">Gebruik op **de flyout pagina Attorney-client privilege** de schakelknop om de functie in te schakelen en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="52211-130">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="52211-131">Stap 2: Upload een lijst met advocaten (optioneel)</span><span class="sxs-lookup"><span data-stu-id="52211-131">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="52211-132">Als u optimaal wilt profiteren van het detectiemodel voor advocaten-clientprivilege en gebruik wilt maken van de resultaten van de eerder beschreven detectie has **attorney** of **Potentially Privileged,** raden we u aan een lijst met e-mailadressen te uploaden voor de advocaten en juridisch personeel die voor uw organisatie werken.</span><span class="sxs-lookup"><span data-stu-id="52211-132">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="52211-133">Een lijst met advocaten uploaden voor gebruik door het detectiemodel voor advocaten-clientrechten:</span><span class="sxs-lookup"><span data-stu-id="52211-133">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="52211-134">Maak een .csv bestand (zonder veldnamenrij) en voeg het e-mailadres voor elke juiste persoon toe aan een aparte regel.</span><span class="sxs-lookup"><span data-stu-id="52211-134">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="52211-135">Sla dit bestand op uw lokale computer op.</span><span class="sxs-lookup"><span data-stu-id="52211-135">Save this file to your local computer.</span></span>

2. <span data-ttu-id="52211-136">Selecteer op **Advanced eDiscovery** startpagina in  de tegel Instellingen experimentele functies configureren **en** selecteer vervolgens De instelling **Advocaten-client privilege beheren.**</span><span class="sxs-lookup"><span data-stu-id="52211-136">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="52211-137">De **pagina Advocaten-clientvoorrecht** wordt weergegeven en de schakelaar Detectie van **advocaten-clientrechten** is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="52211-137">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![Flyoutpagina advocaten-client privilege](../media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="52211-139">Selecteer **Bladeren** en selecteer vervolgens het .csv bestand dat u in stap 1 hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="52211-139">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="52211-140">Selecteer **Opslaan om** de lijst met advocaten te uploaden.</span><span class="sxs-lookup"><span data-stu-id="52211-140">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="52211-141">Het detectiemodel voor advocaten-clientrechten gebruiken</span><span class="sxs-lookup"><span data-stu-id="52211-141">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="52211-142">Volg de stappen in deze sectie om de detectie van advocaten-clientrechten te gebruiken voor documenten in een revisieset.</span><span class="sxs-lookup"><span data-stu-id="52211-142">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="52211-143">Stap 1: Een smart tag-groep maken met het detectiemodel voor advocaten-clientrechten</span><span class="sxs-lookup"><span data-stu-id="52211-143">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="52211-144">Een van de belangrijkste manieren om de resultaten van de detectie van advocaten-clientrechten in uw beoordelingsproces te zien, is door een smart tag-groep te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="52211-144">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="52211-145">Een groep met slimme tags geeft de resultaten aan van de detectie van het privilege van de advocatenclient en toont de resultaten in de regel naast de tags in een groep met slimme labels.</span><span class="sxs-lookup"><span data-stu-id="52211-145">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="52211-146">Op deze manier kunt u snel potentieel bevoorrechte documenten identificeren tijdens de documentbeoordeling.</span><span class="sxs-lookup"><span data-stu-id="52211-146">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="52211-147">Daarnaast kunt u de tags in de groep slimme labels ook gebruiken om documenten te taggen als bevoorrecht of niet-bevoorrecht.</span><span class="sxs-lookup"><span data-stu-id="52211-147">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="52211-148">Zie Slimme tags instellen in Advanced eDiscovery voor meer informatie over slimme [tags.](smart-tags.md)</span><span class="sxs-lookup"><span data-stu-id="52211-148">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="52211-149">Selecteer in de revisieset met de documenten die u  hebt geanalyseerd in stap 1 de optie Controleset beheren en selecteer **vervolgens Tags beheren.**</span><span class="sxs-lookup"><span data-stu-id="52211-149">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="52211-150">Selecteer **onder Tags** de pull-down naast De groep **Toevoegen** en selecteer vervolgens Groep Slimme **tags toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="52211-150">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   ![Selecteer 'Groep slimme tags toevoegen'](../media/AeDCreateSmartTag.png)

3. <span data-ttu-id="52211-152">Kies op **de pagina Kies een model voor uw slimme tag** de optie **Selecteren** naast **Attorney-client privilege.**</span><span class="sxs-lookup"><span data-stu-id="52211-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="52211-153">Er wordt een taggroep met de naam **Attorney-client privilege** weergegeven.</span><span class="sxs-lookup"><span data-stu-id="52211-153">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="52211-154">Het bevat twee onderliggende tags **met** de naam Positief **en** Negatief, die overeenkomen met de mogelijke resultaten die door het model worden geproduceerd.</span><span class="sxs-lookup"><span data-stu-id="52211-154">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![Smart taggroep Advocaten-client privilege](../media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="52211-156">Wijzig de naam van de taggroep en de tags die geschikt zijn voor uw beoordeling.</span><span class="sxs-lookup"><span data-stu-id="52211-156">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="52211-157">U kunt bijvoorbeeld de naam Positief **wijzigen in** **Bevoorrecht** en **Negatief in** **Niet geprivilegieerd.**</span><span class="sxs-lookup"><span data-stu-id="52211-157">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="52211-158">Stap 2: Een revisieset analyseren</span><span class="sxs-lookup"><span data-stu-id="52211-158">Step 2: Analyze a review set</span></span>

<span data-ttu-id="52211-159">Wanneer u de documenten in een revisieset analyseert, wordt het detectiemodel voor advocaten-clientrechten ook uitgevoerd en worden de bijbehorende eigenschappen (beschreven in Hoe werkt [het?](#how-does-it-work) toegevoegd aan elk document in de revisieset).</span><span class="sxs-lookup"><span data-stu-id="52211-159">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="52211-160">Zie Gegevens analyseren in een revisieset in Advanced eDiscovery voor meer informatie over het analyseren van gegevens [in de revisieset.](analyzing-data-in-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="52211-160">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="52211-161">Stap 3: De groep slimme tags gebruiken voor het bekijken van bevoorrechte inhoud</span><span class="sxs-lookup"><span data-stu-id="52211-161">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="52211-162">Na het analyseren van de revisieset en het instellen van slimme tags, is de volgende stap het controleren van de documenten.</span><span class="sxs-lookup"><span data-stu-id="52211-162">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="52211-163">Als het model heeft vastgesteld dat het document potentieel  geprivilegieerd is, geeft de bijbehorende slimme tag in het deelvenster Labelen de volgende resultaten aan die zijn geproduceerd door de detectie van het advocaten-clientprivilege:</span><span class="sxs-lookup"><span data-stu-id="52211-163">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="52211-164">Als het document inhoud bevat die juridisch van aard kan zijn, wordt het label **Juridische** inhoud weergegeven naast de bijbehorende slimme tag (in dit geval de **standaard-positieve** tag).</span><span class="sxs-lookup"><span data-stu-id="52211-164">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="52211-165">Als het document een deelnemer bevat die is gevonden in de advocatenlijst van uw organisatie, wordt het label **Attorney** weergegeven naast de bijbehorende slimme tag (in dit geval ook de **standaard-positieve** tag).</span><span class="sxs-lookup"><span data-stu-id="52211-165">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="52211-166">Als het document inhoud bevat die juridisch van aard kan zijn en  een  deelnemer heeft gevonden in de advocatenlijst, worden zowel de labels Juridische inhoud als Advocaten weergegeven. </span><span class="sxs-lookup"><span data-stu-id="52211-166">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="52211-167">Als in het model wordt bepaald dat een document geen inhoud bevat die juridisch van aard is of die geen deelnemer uit de lijst met advocaten bevat, wordt geen van beide etiketten weergegeven in het labelvenster.</span><span class="sxs-lookup"><span data-stu-id="52211-167">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="52211-168">De volgende schermafbeeldingen bevatten bijvoorbeeld twee documenten.</span><span class="sxs-lookup"><span data-stu-id="52211-168">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="52211-169">De eerste bevat inhoud die juridisch van aard is en die een deelnemer heeft gevonden in de lijst met advocaten.</span><span class="sxs-lookup"><span data-stu-id="52211-169">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="52211-170">De tweede bevat geen van beide en geeft daarom geen etiketten weer.</span><span class="sxs-lookup"><span data-stu-id="52211-170">The second contains neither and therefore doesn't display any labels.</span></span>

![Document met inhoudslabels voor advocaten en juridische inhoud](../media/AeDTaggingPanelLegalContentAttorney.png)

![Document zonder etiketten](../media/AeDTaggingPanelNegative.png)

<span data-ttu-id="52211-173">Nadat u een document hebt beoordeeld om te zien of het bevoorrechte inhoud bevat, kunt u het document taggen met de juiste tag.</span><span class="sxs-lookup"><span data-stu-id="52211-173">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
