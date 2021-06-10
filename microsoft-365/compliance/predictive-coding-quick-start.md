---
title: Voorspellende codering in Advanced eDiscovery - Snel aan de slag
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Lees hoe u aan de slag kunt met de module voor voorspellende codering in Advanced eDiscovery. In dit artikel vindt u een overzicht van het end-to-endproces van het gebruik van voorspellende codering om inhoud te identificeren in een revisieset die het meest relevant is voor uw onderzoek.
ms.openlocfilehash: 16fb92af5048ae6cd953e522b2e5e5d8f5a7256f
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822509"
---
# <a name="quick-start-predictive-coding-in-advanced-ediscovery-preview"></a><span data-ttu-id="45ad1-104">Aan de slag: Voorspellende codering in Advanced eDiscovery (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="45ad1-104">Quick start: Predictive coding in Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="45ad1-105">In dit artikel wordt een beknopt begin beschreven voor het gebruik van voorspellende codering in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="45ad1-105">This article presents a quick start for using predictive coding in Advanced eDiscovery.</span></span> <span data-ttu-id="45ad1-106">De module voor voorspellende codering in Advanced eDiscovery maakt gebruik van de intelligente, machine learning-mogelijkheden in Advanced eDiscovery om de hoeveelheid te controleren inhoud te verminderen.</span><span class="sxs-lookup"><span data-stu-id="45ad1-106">The predictive coding module in Advanced eDiscovery uses the intelligent, machine learning capabilities in Advanced eDiscovery to help you reduce the amount of content to review.</span></span> <span data-ttu-id="45ad1-107">Met voorspellende codering kunt u grote hoeveelheden case-inhoud beperken en verwijderen tot een relevante set items die u voor controle kunt prioriteren.</span><span class="sxs-lookup"><span data-stu-id="45ad1-107">Predictive coding helps you reduce and cull large volumes of case content to a relevant set of items that you can prioritize for review.</span></span> <span data-ttu-id="45ad1-108">Dit wordt gedaan door uw eigen voorspellende coderingsmodellen te maken en te trainen, zodat u prioriteit kunt geven aan de beoordeling van de meest relevante items in een revisieset.</span><span class="sxs-lookup"><span data-stu-id="45ad1-108">This is accomplished by creating and training your own predictive coding models that help you prioritize the review of the most relevant items in a review set.</span></span>

<span data-ttu-id="45ad1-109">Hier volgen een kort overzicht van het voorspellende coderingsproces:</span><span class="sxs-lookup"><span data-stu-id="45ad1-109">Here's an a quick overview of the predictive coding process:</span></span>

![Snelstartproces voor voorspellingscodering](..\media\PredictiveCodingQuickStartProcess.png)

<span data-ttu-id="45ad1-111">Om aan de slag te gaan, maakt u een model, labelt u maar liefst 50 items als relevant of niet relevant.</span><span class="sxs-lookup"><span data-stu-id="45ad1-111">To get started, you create a model, label as few as 50 items as relevant or not relevant.</span></span> <span data-ttu-id="45ad1-112">Het systeem gebruikt deze training vervolgens om voorspellingsscores toe te passen op elk item in de revisieset.</span><span class="sxs-lookup"><span data-stu-id="45ad1-112">The system then uses this training to apply prediction scores to every item in the review set.</span></span> <span data-ttu-id="45ad1-113">Hiermee kunt u items filteren op basis van de voorspellingsscore, zodat u eerst de meest relevante (of niet-relevante) items kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="45ad1-113">This lets you filter items based on the prediction score, which  allows you to review the most relevant (or non-relevant) items first.</span></span> <span data-ttu-id="45ad1-114">Als u modellen met hogere nauwkeurigheid en terugroeptarieven wilt trainen, kunt u items in de volgende trainingsronden blijven labelen totdat het model zich stabiliseert.</span><span class="sxs-lookup"><span data-stu-id="45ad1-114">If you want to train models with higher accuracies and recall rates, you can continue labeling items in subsequent training rounds until the model stabilizes.</span></span> <span data-ttu-id="45ad1-115">Wanneer het model is gestabiliseerd, kunt u het uiteindelijke voorspellingsfilter toepassen om prioriteit te geven aan items die moeten worden beoordeeld.</span><span class="sxs-lookup"><span data-stu-id="45ad1-115">Once the model is stabilized, you can apply the final prediction filter to prioritize items to review.</span></span>

<span data-ttu-id="45ad1-116">Zie Meer informatie over voorspellende codering [in](predictive-coding-overview.md)Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="45ad1-116">For a detailed overview of predictive coding, see [Learn about predictive coding in Advanced eDiscovery](predictive-coding-overview.md).</span></span>

## <a name="step-1-create-a-new-predictive-coding-model"></a><span data-ttu-id="45ad1-117">Stap 1: Een nieuw voorspellend coderingsmodel maken</span><span class="sxs-lookup"><span data-stu-id="45ad1-117">Step 1: Create a new predictive coding model</span></span>

<span data-ttu-id="45ad1-118">De eerste stap is het maken van een nieuw voorspellend coderingsmodel in de revisieset</span><span class="sxs-lookup"><span data-stu-id="45ad1-118">The first step is to create a new predictive coding model in the review set</span></span>

1. <span data-ttu-id="45ad1-119">Open in Microsoft 365 compliancecentrum een Advanced eDiscovery en selecteer vervolgens **het tabblad Revisiesets.**</span><span class="sxs-lookup"><span data-stu-id="45ad1-119">In the Microsoft 365 compliance center, open an Advanced eDiscovery case and then select the **Review sets** tab.</span></span>

2. <span data-ttu-id="45ad1-120">Open een revisieset en klik vervolgens op **Voorspellende** codering beheren  >  **(voorbeeld)**.</span><span class="sxs-lookup"><span data-stu-id="45ad1-120">Open a review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

   ![Klik in de vervolgkeuzelijst Analyseren in de revisieset om naar de pagina Voorspellende codering te gaan](..\media\ManagePredictiveCoding.png)

3. <span data-ttu-id="45ad1-122">Klik op **de pagina Voorspellende coderingsmodellen (voorbeeld)** op **Nieuw model.**</span><span class="sxs-lookup"><span data-stu-id="45ad1-122">On the **Predictive coding models (preview)** page, click **New model**.</span></span>

4. <span data-ttu-id="45ad1-123">Typ op de flyoutpagina een naam voor het model en een optionele beschrijving.</span><span class="sxs-lookup"><span data-stu-id="45ad1-123">On the flyout page, type a name for the model and an optional description.</span></span>

5. <span data-ttu-id="45ad1-124">Klik **op Opslaan** om het model te maken.</span><span class="sxs-lookup"><span data-stu-id="45ad1-124">Click **Save** to create the model.</span></span>

   <span data-ttu-id="45ad1-125">Het duurt een paar minuten voordat het systeem uw model heeft voorbereid.</span><span class="sxs-lookup"><span data-stu-id="45ad1-125">It will take a couple minutes for the system to prepare your model.</span></span> <span data-ttu-id="45ad1-126">Nadat het klaar is, kunt u de eerste trainingsronde uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="45ad1-126">After it's ready, you can perform the first round of training.</span></span>

<span data-ttu-id="45ad1-127">Zie Een voorspellend coderingsmodel maken voor meer [gedetailleerde instructies.](predictive-coding-create-model.md)</span><span class="sxs-lookup"><span data-stu-id="45ad1-127">For more detailed instructions, see [Create a predictive coding model](predictive-coding-create-model.md).</span></span>

## <a name="step-2-perform-the-first-training-round"></a><span data-ttu-id="45ad1-128">Stap 2: De eerste trainingsronde uitvoeren</span><span class="sxs-lookup"><span data-stu-id="45ad1-128">Step 2: Perform the first training round</span></span>

<span data-ttu-id="45ad1-129">Nadat u het model hebt gemaakt, is de volgende stap het voltooien van de eerste trainingsronde door items te labelen als relevant of niet relevant.</span><span class="sxs-lookup"><span data-stu-id="45ad1-129">After you create the model, the next step is to complete the first training round by labeling items as relevant or not relevant.</span></span>

1. <span data-ttu-id="45ad1-130">Open de revisieset en klik vervolgens op **Voorspellende** codering beheren  >  **(voorbeeld)**.</span><span class="sxs-lookup"><span data-stu-id="45ad1-130">Open the review set and then click **Analytics** > **Manage predictive coding (preview)**.</span></span>

2. <span data-ttu-id="45ad1-131">Selecteer op **de pagina Voorspellende coderingsmodellen (voorbeeld)** het model dat u wilt trainen.</span><span class="sxs-lookup"><span data-stu-id="45ad1-131">On the **Predictive coding models (preview)** page, select the model that you want to train.</span></span>

3. <span data-ttu-id="45ad1-132">Klik op **het** tabblad Overzicht onder **Ronde 1** op **Volgende trainingsronde starten.**</span><span class="sxs-lookup"><span data-stu-id="45ad1-132">On the **Overview** tab, under **Round 1**, click **Start next training round**.</span></span>

   <span data-ttu-id="45ad1-133">Het **tabblad** Training wordt weergegeven en bevat 50 items die u kunt labelen.</span><span class="sxs-lookup"><span data-stu-id="45ad1-133">The **Training** tab is displayed and contains 50 items for you to label.</span></span>

4. <span data-ttu-id="45ad1-134">Controleer elk document en selecteer vervolgens de **knop Relevant** of **Niet relevant** onder aan het leesvenster om het te labelen.</span><span class="sxs-lookup"><span data-stu-id="45ad1-134">Review each document and then select the **Relevant** or **Not relevant** button at the bottom of the reading pane to label it.</span></span>

   ![Elk document als relevant of niet relevant labelen](..\media\TrainModel1.png)

5. <span data-ttu-id="45ad1-136">Nadat u alle 50 items hebt gelabeld, klikt u op **Voltooien.**</span><span class="sxs-lookup"><span data-stu-id="45ad1-136">After you've labeled all 50 items, click **Finish**.</span></span>

    <span data-ttu-id="45ad1-137">Het duurt een paar minuten voordat het systeem 'leert' van uw labeling en het model bij werkt.</span><span class="sxs-lookup"><span data-stu-id="45ad1-137">It will take a couple minutes for the system to "learn" from your labeling and update the model.</span></span> <span data-ttu-id="45ad1-138">Wanneer dit proces is voltooid, wordt de status **Ready** weergegeven voor het model op de pagina **Voorspellende coderingsmodellen (preview).**</span><span class="sxs-lookup"><span data-stu-id="45ad1-138">When this process is complete, a status of **Ready** is displayed for the model on the **Predictive coding models (preview)** page.</span></span>

<span data-ttu-id="45ad1-139">Zie Een voorspellend coderingsmodel trainen voor meer [gedetailleerde instructies.](predictive-coding-train-model.md)</span><span class="sxs-lookup"><span data-stu-id="45ad1-139">For more detailed instructions, see [Train a predictive coding model](predictive-coding-train-model.md).</span></span>

## <a name="step-3-apply-the-prediction-score-filter-to-items-in-review-set"></a><span data-ttu-id="45ad1-140">Stap 3: Het voorspellingsscorefilter toepassen op items in de revisieset</span><span class="sxs-lookup"><span data-stu-id="45ad1-140">Step 3: Apply the prediction score filter to items in review set</span></span>

<span data-ttu-id="45ad1-141">Nadat u één trainingsronde hebt gedaan bij lease, kunt u het filter voor de voorspellingsscore toepassen op items in de revisieset.</span><span class="sxs-lookup"><span data-stu-id="45ad1-141">After you perform at lease one training round, you can apply the prediction score filter to items in review set.</span></span> <span data-ttu-id="45ad1-142">Op deze manier kunt u de items bekijken die het model heeft voorspeld als relevant of niet relevant.</span><span class="sxs-lookup"><span data-stu-id="45ad1-142">This lets you review the items the model has predicted as relevant or not relevant.</span></span>   

1. <span data-ttu-id="45ad1-143">Open de revisieset.</span><span class="sxs-lookup"><span data-stu-id="45ad1-143">Open the review set.</span></span>

   ![Klik op Filters om de flyoutpagina Filters weer te geven](..\media\PredictionScoreFilter0.png)

   <span data-ttu-id="45ad1-145">De vooraf geladen standaardfilters worden boven aan de pagina met revisiesets weergegeven.</span><span class="sxs-lookup"><span data-stu-id="45ad1-145">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="45ad1-146">U kunt deze instellen op **Any**.</span><span class="sxs-lookup"><span data-stu-id="45ad1-146">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="45ad1-147">Klik **op Filters** om de flyoutpagina **Filters** weer te geven.</span><span class="sxs-lookup"><span data-stu-id="45ad1-147">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="45ad1-148">Vouw de **sectie Analyse & voorspellende codering** uit om een set filters weer te geven.</span><span class="sxs-lookup"><span data-stu-id="45ad1-148">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![Voorspellingsscorefilter in de sectie & voorspellende codering](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="45ad1-150">De naamgevingsconventie voor voorspellingsscorefilters is **Voorspellingsscore (modelnaam)**.</span><span class="sxs-lookup"><span data-stu-id="45ad1-150">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="45ad1-151">De naam van het voorspellingsscorefilter voor een model met de naam **Model A** is **bijvoorbeeld Voorspellingsscore (model A).**</span><span class="sxs-lookup"><span data-stu-id="45ad1-151">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="45ad1-152">Selecteer het voorspellingsscorefilter dat u wilt gebruiken en klik vervolgens op **Klaar.**</span><span class="sxs-lookup"><span data-stu-id="45ad1-152">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="45ad1-153">Klik op de pagina revisieset op de vervolgkeuzekeuze voor het voorspellingsscorefilter en typ minimum- en maximumwaarden voor het voorspellingsscorebereik.</span><span class="sxs-lookup"><span data-stu-id="45ad1-153">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="45ad1-154">In de volgende schermafbeelding ziet u bijvoorbeeld een voorspellingsscorebereik tussen **0,5** en **1,0**.</span><span class="sxs-lookup"><span data-stu-id="45ad1-154">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![Minimum- en maximumwaarden voor het voorspellingsscorefilter](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="45ad1-156">Klik buiten het filter om het filter automatisch toe te passen op de revisieset.</span><span class="sxs-lookup"><span data-stu-id="45ad1-156">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="45ad1-157">Een lijst met documenten met een voorspellingsscore binnen het opgegeven bereik wordt weergegeven op de pagina met revisiesets.</span><span class="sxs-lookup"><span data-stu-id="45ad1-157">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span>

<span data-ttu-id="45ad1-158">Zie Een voorspellingsfilter toepassen op een revisieset voor meer [gedetailleerde instructies.](predictive-coding-apply-prediction-filter.md)</span><span class="sxs-lookup"><span data-stu-id="45ad1-158">For more detailed instructions, see [Apply a prediction filter to a review set](predictive-coding-apply-prediction-filter.md).</span></span>

## <a name="step-4-perform-more-training-rounds"></a><span data-ttu-id="45ad1-159">Stap 4: Meer trainingsronden uitvoeren</span><span class="sxs-lookup"><span data-stu-id="45ad1-159">Step 4: Perform more training rounds</span></span>

<span data-ttu-id="45ad1-160">Waarschijnlijk moet u meer trainingsronden uitvoeren om de module te trainen om relevante en niet-relevante items in de revisieset beter te voorspellen.</span><span class="sxs-lookup"><span data-stu-id="45ad1-160">More than likely, you'll have to perform more training rounds to train the module to better predict relevant and non-relevant items in the review set.</span></span> <span data-ttu-id="45ad1-161">Over het algemeen traint u het model vaak genoeg totdat het voldoende stabiel is om aan uw vereisten te voldoen.</span><span class="sxs-lookup"><span data-stu-id="45ad1-161">In general, you'll train the model enough times until it stabilizes enough to meet your requirements.</span></span>

<span data-ttu-id="45ad1-162">Zie Aanvullende trainingsronden [uitvoeren voor meer informatie.](predictive-coding-train-model.md#perform-additional-training-rounds)</span><span class="sxs-lookup"><span data-stu-id="45ad1-162">For more information, see [Perform additional training rounds](predictive-coding-train-model.md#perform-additional-training-rounds)</span></span>

## <a name="step-5-apply-the-final-prediction-score-filter-to-prioritize-review"></a><span data-ttu-id="45ad1-163">Stap 5: Het filter voor de uiteindelijke voorspellingsscore toepassen om prioriteit te geven aan de beoordeling</span><span class="sxs-lookup"><span data-stu-id="45ad1-163">Step 5: Apply the final prediction score filter to prioritize review</span></span>

<span data-ttu-id="45ad1-164">Herhaal de instructies in stap 3 om de uiteindelijke voorspellingsscore toe te passen op de revisieset om prioriteit te geven aan de beoordeling van relevante en niet-relevante items nadat u alle trainingsronden hebt voltooid en het model hebt gestabiliseerd.</span><span class="sxs-lookup"><span data-stu-id="45ad1-164">Repeat the instructions in Step 3 to apply the final prediction score to the review set to prioritize the review of relevant and non-relevant items after you complete all the training rounds and stabilize the model.</span></span>
