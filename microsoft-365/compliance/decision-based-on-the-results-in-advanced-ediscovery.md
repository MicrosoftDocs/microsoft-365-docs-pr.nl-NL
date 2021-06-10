---
title: Beslissing op basis van de resultaten in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Lees hoe het tabblad Beslissen in Advanced eDiscovery gegevens bevat die u kunnen helpen bij het bepalen van de juiste grootte van de revisieset met hoofddossiers.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161664"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a><span data-ttu-id="51d76-103">Beslissingen op basis van relevantieresultaten in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="51d76-103">Decisions based on Relevance results in Advanced eDiscovery</span></span>
  
<span data-ttu-id="51d76-104">In de module Relevantie in Advanced eDiscovery bevat het tabblad Beslissen aanvullende informatie voor het weergeven en gebruiken van statistieken voor beslissingsondersteuning voor het bepalen van de grootte van de revisieset met hoofddossiers.</span><span class="sxs-lookup"><span data-stu-id="51d76-104">In the Relevance module in Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span>
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="51d76-105">Het tabblad Beslissen gebruiken</span><span class="sxs-lookup"><span data-stu-id="51d76-105">Using the Decide tab</span></span>

![Relevantie bepalen](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="51d76-107">Dit tabblad bevat de volgende onderdelen:</span><span class="sxs-lookup"><span data-stu-id="51d76-107">This tab includes the following components:</span></span>
  
- <span data-ttu-id="51d76-108">**Probleem:** Hier kunt u het probleem van belang selecteren in de lijst.</span><span class="sxs-lookup"><span data-stu-id="51d76-108">**Issue**: From here, you can select the issue of interest from the list.</span></span>

- <span data-ttu-id="51d76-109">**Review-recall ratio:** Vergelijkingen van Advanced eDiscovery beoordeling op basis van relevantiescores.</span><span class="sxs-lookup"><span data-stu-id="51d76-109">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="51d76-110">Het cutoff-punt in de grafiek vertegenwoordigt het percentage bestanden dat moet worden beoordeeld, dat is toegesneden op een relevantiescore.</span><span class="sxs-lookup"><span data-stu-id="51d76-110">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="51d76-111">Dit wordt gebruikt in de fase Relevantietest en als exportdrempel voor ruiming.</span><span class="sxs-lookup"><span data-stu-id="51d76-111">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="51d76-112">Het standaardbezuiningspunt voor het aantal bestanden dat moet worden beoordeeld, ligt op het punt waarop de balans tussen Inroepen en Precisie optimaal is.</span><span class="sxs-lookup"><span data-stu-id="51d76-112">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="51d76-113">Het werkelijke snijpunt moet door de gebruiker worden bepaald, afhankelijk van de doelstellingen en de kostenruil (%beoordeling) en het risico (%recall).</span><span class="sxs-lookup"><span data-stu-id="51d76-113">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="51d76-114">Met de schuifregelaar kunt u het snijpunt aanpassen en het effect op de grafiek en parameters zien, bij het aanpassen van het percentage relevante bestanden dat moet worden opgehaald en voordat u een beslissing valideert.</span><span class="sxs-lookup"><span data-stu-id="51d76-114">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>

- <span data-ttu-id="51d76-115">**Parameters**: Controleren, Inroepen, Volgende relevante en totale kostenparameters zijn cumulatieve berekende statistieken met betrekking tot de revisieset ten opzichte van de verzameling voor het hele geval.</span><span class="sxs-lookup"><span data-stu-id="51d76-115">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="51d76-116">Definities voor deze parameters zijn als volgt:</span><span class="sxs-lookup"><span data-stu-id="51d76-116">Definitions for these parameters are as follows:</span></span>

  - <span data-ttu-id="51d76-117">**Controleren:** Percentage bestanden dat u wilt controleren op basis van deze cutoff.</span><span class="sxs-lookup"><span data-stu-id="51d76-117">**Review**: Percentage of files to review based on this cutoff.</span></span>

  - <span data-ttu-id="51d76-118">**Inroepen:** Percentage relevante bestanden in de revisieset.</span><span class="sxs-lookup"><span data-stu-id="51d76-118">**Recall**: Percentage of relevant files in the review set.</span></span>

  - <span data-ttu-id="51d76-119">**Volgende relevant:** Kosten voor het controleren en identificeren van een ander relevant bestand dat momenteel niet in de revisieset staat.</span><span class="sxs-lookup"><span data-stu-id="51d76-119">**Next relevant**: Cost to review and identify another relevant file that is not currently in the review set.</span></span>

  - <span data-ttu-id="51d76-120">**Totale kosten:** Kosten voor het controleren van dit percentage van de casebestanden.</span><span class="sxs-lookup"><span data-stu-id="51d76-120">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="51d76-121">Instellingen voor kostenparameters kunnen worden ingesteld door Case manager.</span><span class="sxs-lookup"><span data-stu-id="51d76-121">Cost parameter settings can be set by the Case manager.</span></span>

  - <span data-ttu-id="51d76-122">**Verdeling op relevantiescore:** Bestanden in de donkergrijse weergave aan de linkerkant staan onder de cutoffscore.</span><span class="sxs-lookup"><span data-stu-id="51d76-122">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="51d76-123">Met een knoptip worden de relevantiescore en het gerelateerde percentage bestanden weergegeven in het revisiebestand dat is ingesteld ten opzichte van het totale aantal bestanden.</span><span class="sxs-lookup"><span data-stu-id="51d76-123">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>

<span data-ttu-id="51d76-124">In het deelvenster **Uitgebreide details** worden meer details weergegeven.</span><span class="sxs-lookup"><span data-stu-id="51d76-124">The expanded **Details** pane displays more details.</span></span> <span data-ttu-id="51d76-125">Bestanden in verzamelingscijfers bevatten geen lege of nevelige bestanden.</span><span class="sxs-lookup"><span data-stu-id="51d76-125">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="51d76-126">Gezinsbestanden zijn bestanden die niet zijn geladen in Relevantie, maar nog steeds worden meegetelde als onderdeel van het gezin.</span><span class="sxs-lookup"><span data-stu-id="51d76-126">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
