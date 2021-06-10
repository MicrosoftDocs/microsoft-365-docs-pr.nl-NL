---
title: Het voorspellingsscorefilter toepassen op items in een revisieset
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
description: Gebruik een voorspellingsscorefilter om items weer te geeft die een voorspellend coderingsmodel zijn, zoals voorspeld als relevant of niet relevant.
ms.openlocfilehash: 0ca2770d5ccbcc3ea5f3dec8394f69d1f5117da5
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822493"
---
# <a name="apply-a-prediction-score-filter-to-a-review-set-preview"></a><span data-ttu-id="78812-103">Een voorspellingsscorefilter toepassen op een revisieset (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="78812-103">Apply a prediction score filter to a review set (preview)</span></span>

<span data-ttu-id="78812-104">Nadat u een voorspellend coderingsmodel hebt gemaakt in Advanced eDiscovery en dit hebt getrained naar het punt waar het stabiel is, kunt u het voorspellingsscorefilter toepassen om de items in de revisieset weer te geven die volgens het model relevant zijn (of niet relevant).</span><span class="sxs-lookup"><span data-stu-id="78812-104">After you create a predictive coding model in Advanced eDiscovery and train it to the point where it's stable, you can apply the prediction score filter to display review set items that the model has determined are relevant (or not relevant).</span></span> <span data-ttu-id="78812-105">Wanneer u een model maakt, wordt er ook een bijbehorend voorspellingsscorefilter gemaakt.</span><span class="sxs-lookup"><span data-stu-id="78812-105">When you create a model, a corresponding prediction score filter is also created.</span></span> <span data-ttu-id="78812-106">U kunt dit filter gebruiken om items weer te geven die een voorspellingsscore binnen een opgegeven bereik hebben gekregen.</span><span class="sxs-lookup"><span data-stu-id="78812-106">You can use this filter to display items assigned a prediction score within a specified range.</span></span> <span data-ttu-id="78812-107">In het algemeen zijn voorspellingsscores **tussen 0** en **0,5** toegewezen aan items die door het model zijn voorspeld, niet relevant.</span><span class="sxs-lookup"><span data-stu-id="78812-107">In general, prediction scores between **0** and **.5** are assigned to items that model has predicted are not relevant.</span></span> <span data-ttu-id="78812-108">Items die zijn toegewezen voorspellingsscores **tussen 0,5** en **1,0** zijn items die het model heeft voorspeld, zijn relevant.</span><span class="sxs-lookup"><span data-stu-id="78812-108">Items assigned prediction scores between **.5** and **1.0** are items the model has predicted are relevant.</span></span>

<span data-ttu-id="78812-109">Hier zijn twee manieren waarop u het voorspellingsscorefilter kunt gebruiken:</span><span class="sxs-lookup"><span data-stu-id="78812-109">Here are two ways you can use the prediction score filter:</span></span>

- <span data-ttu-id="78812-110">Geef prioriteit aan het controleren van items in een revisieset die het model heeft voorspeld, zijn relevant.</span><span class="sxs-lookup"><span data-stu-id="78812-110">Prioritize the review of items in a review set that the model has predicted are relevant.</span></span>

- <span data-ttu-id="78812-111">Items verwijderen uit de revisieset die het model heeft voorspeld, zijn niet relevant.</span><span class="sxs-lookup"><span data-stu-id="78812-111">Cull items from the review set that the model has predicted are not relevant.</span></span> <span data-ttu-id="78812-112">U kunt ook het voorspellingsscorefilter gebruiken om de prioriteit voor het controleren van niet-relevante items te de-prioriteren.</span><span class="sxs-lookup"><span data-stu-id="78812-112">Alternative, you can use the prediction score filter to de-prioritize the review of non-relevant items.</span></span>

## <a name="before-you-apply-a-prediction-score-filter"></a><span data-ttu-id="78812-113">Voordat u een voorspellingsscorefilter toe te passen</span><span class="sxs-lookup"><span data-stu-id="78812-113">Before you apply a prediction score filter</span></span>

- <span data-ttu-id="78812-114">Maak een voorspellend coderingsmodel zodat er een overeenkomend voorspellingsscorefilter wordt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="78812-114">Create a predictive coding model so that a corresponding prediction score filter is created.</span></span>

- <span data-ttu-id="78812-115">U kunt een voorspellingsscorefilter toepassen na een van de trainingsronden.</span><span class="sxs-lookup"><span data-stu-id="78812-115">You can apply a prediction score filter after any of the training rounds.</span></span> <span data-ttu-id="78812-116">Maar misschien wilt u wachten nadat u meerdere rondes hebt gedaan of totdat het model stabiel is voordat u het voorspellingsscorefilter gebruikt.</span><span class="sxs-lookup"><span data-stu-id="78812-116">But you may want to wait after performing several rounds or until the model is stable before using the prediction score filter.</span></span>

## <a name="apply-a-prediction-score-filter"></a><span data-ttu-id="78812-117">Een voorspellingsscorefilter toepassen</span><span class="sxs-lookup"><span data-stu-id="78812-117">Apply a prediction score filter</span></span>

1. <span data-ttu-id="78812-118">Open in Microsoft 365 compliancecentrum het hoofd- Advanced eDiscovery, selecteer  het tabblad Revisiesets en open de revisieset.</span><span class="sxs-lookup"><span data-stu-id="78812-118">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then open the review set.</span></span>

   ![Klik op Filters om de flyoutpagina Filters weer te geven](..\media\PredictionScoreFilter0.png)   

   <span data-ttu-id="78812-120">De vooraf geladen standaardfilters worden boven aan de pagina met revisiesets weergegeven.</span><span class="sxs-lookup"><span data-stu-id="78812-120">The pre-loaded default filters are displayed at the top of the review set page.</span></span> <span data-ttu-id="78812-121">U kunt deze instellen op **Any**.</span><span class="sxs-lookup"><span data-stu-id="78812-121">You can leave these set to **Any**.</span></span>

2. <span data-ttu-id="78812-122">Klik **op Filters** om de flyoutpagina **Filters** weer te geven.</span><span class="sxs-lookup"><span data-stu-id="78812-122">Click **Filters** to display the **Filters** flyout page.</span></span>

3. <span data-ttu-id="78812-123">Vouw de **sectie Analyse & voorspellende codering** uit om een set filters weer te geven.</span><span class="sxs-lookup"><span data-stu-id="78812-123">Expand the **Analytics & predictive coding** section to display a set of filters.</span></span>

      ![Voorspellingsscorefilter in de sectie & voorspellende codering](..\media\PredictionScoreFilter1.png)

   <span data-ttu-id="78812-125">De naamgevingsconventie voor voorspellingsscorefilters is **Voorspellingsscore (modelnaam)**.</span><span class="sxs-lookup"><span data-stu-id="78812-125">The naming convention for prediction score filters is **Prediction score (model name)**.</span></span> <span data-ttu-id="78812-126">De naam van het voorspellingsscorefilter voor een model met de naam **Model A** is **bijvoorbeeld Voorspellingsscore (model A).**</span><span class="sxs-lookup"><span data-stu-id="78812-126">For example, the prediction score filter name for a model named **Model A** is **Prediction score (Model A)**.</span></span>

4. <span data-ttu-id="78812-127">Selecteer het voorspellingsscorefilter dat u wilt gebruiken en klik vervolgens op **Klaar.**</span><span class="sxs-lookup"><span data-stu-id="78812-127">Select the prediction score filter that you want to use and then click **Done**.</span></span>

5. <span data-ttu-id="78812-128">Klik op de pagina revisieset op de vervolgkeuzekeuze voor het voorspellingsscorefilter en typ minimum- en maximumwaarden voor het voorspellingsscorebereik.</span><span class="sxs-lookup"><span data-stu-id="78812-128">On the review set page, click the dropdown for the prediction score filter and type minimum and maximum values for the prediction score range.</span></span> <span data-ttu-id="78812-129">In de volgende schermafbeelding ziet u bijvoorbeeld een voorspellingsscorebereik tussen **0,5** en **1,0**.</span><span class="sxs-lookup"><span data-stu-id="78812-129">For example, the following screenshot shows a prediction score range between **.5** and **1.0**.</span></span>

   ![Minimum- en maximumwaarden voor het voorspellingsscorefilter](..\media\PredictionScoreFilter2.png)

6. <span data-ttu-id="78812-131">Klik buiten het filter om het filter automatisch toe te passen op de revisieset.</span><span class="sxs-lookup"><span data-stu-id="78812-131">Click outside the filter to automatically apply the filter to the review set.</span></span>

  <span data-ttu-id="78812-132">Een lijst met documenten met een voorspellingsscore binnen het opgegeven bereik wordt weergegeven op de pagina met revisiesets.</span><span class="sxs-lookup"><span data-stu-id="78812-132">A list of documents with a prediction score within the range you specified is displayed on the review set page.</span></span> 

  > [!TIP]
  > <span data-ttu-id="78812-133">Als u de werkelijke voorspellingsscore wilt weergeven die aan een document is toegewezen, klikt u op het **tabblad** Metagegevens in het leesvenster.</span><span class="sxs-lookup"><span data-stu-id="78812-133">To view the actual prediction score assign to a document, you can click the **Metadata** tab in the reading pane.</span></span> <span data-ttu-id="78812-134">De voorspellingsscores voor alle modellen in de revisieset worden weergegeven in de **eigenschap Relevantiescores** metagegevens.</span><span class="sxs-lookup"><span data-stu-id="78812-134">The prediction scores for all models in the review set are displayed in the **RelevanceScores** metadata property.</span></span>

## <a name="more-information"></a><span data-ttu-id="78812-135">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="78812-135">More information</span></span>

- <span data-ttu-id="78812-136">Zie Inhoud query's en [filteren in een revisieset](review-set-search.md)voor meer informatie over het gebruik van filters.</span><span class="sxs-lookup"><span data-stu-id="78812-136">For more information about using filters, see [Query and filter content in a review set](review-set-search.md).</span></span>
