---
title: Uittreding van relevantiemodule in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: De module Relevantie in Advanced eDiscovery wordt op 10 maart 2021 ingetrokken. In dit artikel wordt uitgelegd wat u moet doen voordat Relevantie wordt ingetrokken. Met name het afronden van onvoltooide modellen door batchberekening uit te voeren, zodat u de metagegevens van het model kunt behouden.
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "52161682"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="666d6-105">De uittreding van de module Relevantie in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="666d6-105">Retirement of the Relevance module in Advanced eDiscovery</span></span>

<span data-ttu-id="666d6-106">Op 10 maart 2021 trekken we de module Relevantie in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="666d6-106">On March 10, 2021, we are retiring the Relevance module in Advanced eDiscovery.</span></span> <span data-ttu-id="666d6-107">Deze uittreding betekent dat organisaties geen toegang meer hebben tot de module Relevantie (door te gaan naar Revisieset Relevantie beheren in een Advanced eDiscovery geval) of toegang hebben tot bestaande  >   relevantiemodellen.</span><span class="sxs-lookup"><span data-stu-id="666d6-107">This retirement means that organizations will no longer have access to the Relevance module (by going to **Manage review set** > **Relevance** in an Advanced eDiscovery case) or be able to access any existing Relevance models.</span></span> <span data-ttu-id="666d6-108">De huidige relevantiemodule die wordt uitgetrokken, wordt vervangen door een nieuwe oplossing voor voorspellende codering in Q2 CY 2021.</span><span class="sxs-lookup"><span data-stu-id="666d6-108">The current Relevance module that is being retired will be replaced with a new predictive coding solution in Q2 CY 2021.</span></span> <span data-ttu-id="666d6-109">Met deze nieuwe functionaliteit kunnen organisaties hun eigen voorspellende coderingsmodellen bouwen in een eenvoudigere en intuïtievere werkstroom.</span><span class="sxs-lookup"><span data-stu-id="666d6-109">This new functionality will let organizations build their own predictive coding models in an easier and more intuitive workflow.</span></span>

<span data-ttu-id="666d6-110">Ter voorbereiding op deze aanstaande uittreding raden we organisaties aan die de uitvoer van hun model vóór de pensioendatum gebruiken, te exporteren door een batchberekening uit te voeren voor alle bestaande modellen.</span><span class="sxs-lookup"><span data-stu-id="666d6-110">To prepare for this upcoming retirement, we recommend that organizations who use the Relevance module export their model’s output before the retirement date by running a Batch calculation for all existing models.</span></span> <span data-ttu-id="666d6-111">Alle relevantiescores van uw model worden permanent opgeslagen in de bijbehorende revisieset en toegankelijk wanneer documenten worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="666d6-111">All Relevance scores from your model will be permanently stored in the corresponding review set and accessible when documents are exported.</span></span> <span data-ttu-id="666d6-112">Relevantiescores blijven ook behouden als metagegevens in het laadbestand.</span><span class="sxs-lookup"><span data-stu-id="666d6-112">Relevance scores are also retained as metadata in the load file.</span></span> <span data-ttu-id="666d6-113">U kunt ook nog steeds inhoud filteren in de revisieset op basis van relevantiescore en toegang hebben tot alle metagegevens die worden geproduceerd door uw relevantiemodellen.</span><span class="sxs-lookup"><span data-stu-id="666d6-113">Also, you will still be able to filter content in the review set based on relevance score and have access to all metadata produced by your Relevance models.</span></span>

## <a name="complete-unfinished-models"></a><span data-ttu-id="666d6-114">Voltooide onvoltooide modellen</span><span class="sxs-lookup"><span data-stu-id="666d6-114">Complete unfinished models</span></span>

<span data-ttu-id="666d6-115">Voor onvoltooide relevantiemodellen kunt u de beoordeling, training en batchberekening voltooien, zodat u het model kunt toepassen op de documenten in een revisieset.</span><span class="sxs-lookup"><span data-stu-id="666d6-115">For any unfinished Relevance models, please complete assessment, training, and Batch calculation so that you can apply the model to the documents in a review set.</span></span> <span data-ttu-id="666d6-116">Als u de batchberekening voltooit, blijven de gegevens behouden na de pensioendatum van de module Relevantie.</span><span class="sxs-lookup"><span data-stu-id="666d6-116">Completing the Batch calculation will preserve the information after the retirement date of the Relevance module.</span></span>

<span data-ttu-id="666d6-117">Hier volgen de stappen voor het voltooien van onvoltooide modellen:</span><span class="sxs-lookup"><span data-stu-id="666d6-117">Here are the steps to complete any unfinished models:</span></span>

1. <span data-ttu-id="666d6-118">Train uw model totdat het is gestabiliseerd en klaar is voor batchberekening.</span><span class="sxs-lookup"><span data-stu-id="666d6-118">Train your model until it is stabilized and ready for Batch calculation.</span></span> <span data-ttu-id="666d6-119">Zie [Training voor labelen en relevantie.](tagging-and-relevance-training-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="666d6-119">See [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span></span>

   <span data-ttu-id="666d6-120">In de volgende schermafbeelding ziet u een module die klaar is voor een batchberekening.</span><span class="sxs-lookup"><span data-stu-id="666d6-120">The following screenshot shows a module that is ready for a Batch calculation.</span></span> <span data-ttu-id="666d6-121">De evaluatie en training zijn voltooid en de volgende stap is het uitvoeren van batchberekening.</span><span class="sxs-lookup"><span data-stu-id="666d6-121">Notice that the Assessment and Training is complete, and the next step is to run Batch calculation.</span></span>

   ![Schermafbeelding van model dat klaar is voor batchberekening](../media/ReadyForBatchCalculation.png)

2. <span data-ttu-id="666d6-123">Voer de batchberekening uit.</span><span class="sxs-lookup"><span data-stu-id="666d6-123">Run the Batch calculation.</span></span> <span data-ttu-id="666d6-124">Zie [Batchberekening uitvoeren.](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)</span><span class="sxs-lookup"><span data-stu-id="666d6-124">See [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span></span>

3. <span data-ttu-id="666d6-125">Controleer of batchberekening is gelukt.</span><span class="sxs-lookup"><span data-stu-id="666d6-125">Verify that Batch calculation was successful.</span></span> <span data-ttu-id="666d6-126">Zie [Batchberekeningsresultaten](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span><span class="sxs-lookup"><span data-stu-id="666d6-126">See [Batch calculation results](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span></span>

<span data-ttu-id="666d6-127">Neem contact op met Microsoft Support voor hulp bij het voltooien van onvoltooide relevantiemodellen.</span><span class="sxs-lookup"><span data-stu-id="666d6-127">For help with completing unfinished Relevance models, contact Microsoft Support.</span></span>
