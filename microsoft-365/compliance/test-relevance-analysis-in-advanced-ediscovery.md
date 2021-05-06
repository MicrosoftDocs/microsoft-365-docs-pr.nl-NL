---
title: Test Relevantieanalyse in Advanced eDiscovery
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het gebruik van het tabblad Testen na batchberekening in Advanced eDiscovery om de algehele kwaliteit van de verwerking te testen, te vergelijken en te valideren.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161667"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="b4f8c-103">Test Relevantieanalyse in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b4f8c-103">Test Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="b4f8c-104">Op het tabblad Testen in Advanced eDiscovery kunt u de algehele kwaliteit van de verwerking testen, vergelijken en valideren.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-104">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="b4f8c-105">Deze tests worden uitgevoerd na batchberekening.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-105">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="b4f8c-106">Door de bestanden in de verzameling te labelen, maakt een expert het uiteindelijke oordeel over of elk gelabeld bestand relevant is voor de zaak.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-106">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is relevant to the case.</span></span>
  
<span data-ttu-id="b4f8c-107">In scenario's met één of meerdere problemen worden tests meestal per probleem uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-107">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="b4f8c-108">De resultaten kunnen na elke test worden bekeken en testresultaten kunnen worden herwerkt met opgegeven voorbeeldtestbestanden.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-108">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="b4f8c-109">De rest testen</span><span class="sxs-lookup"><span data-stu-id="b4f8c-109">Testing the rest</span></span>

<span data-ttu-id="b4f8c-110">De test 'Test the Rest' wordt gebruikt om selectiebeslissingen te valideren, bijvoorbeeld om alleen bestanden boven een specifieke relevantiescore te controleren op basis van de uiteindelijke Advanced eDiscovery resultaten.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-110">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="b4f8c-111">De expert bekijkt een steekproef van bestanden onder een geselecteerde cutoffscore om het aantal relevante bestanden in die set te evalueren.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-111">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="b4f8c-112">Deze test bevat statistieken en een vergelijking tussen de revisieset en de populatie Rest testen.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-112">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="b4f8c-113">De resultaten van de revisieset zijn de resultaten die worden berekend door Relevantie tijdens de training.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-113">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="b4f8c-114">De resultaten zijn berekeningen op basis van instellingen en invoerparameters, zoals:</span><span class="sxs-lookup"><span data-stu-id="b4f8c-114">The results include calculations based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="b4f8c-115">Test voorbeeldstatistieken van het aantal bestanden in een steekproef en identificeer relevante bestanden.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-115">Test sample statistics of the number of files in a sample and identified relevant files.</span></span>

- <span data-ttu-id="b4f8c-116">Tabellaire vergelijking van de parameters Populatie van de revisieset en de Rest, bijvoorbeeld het aantal bestanden, het geschatte aantal relevante bestanden, de geschatte rijkheid en de gemiddelde kosten van het zoeken naar een ander relevant bestand.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span></span> <span data-ttu-id="b4f8c-117">Instellingen voor kostenparameters kunnen worden ingesteld door de beheerder.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-117">Cost parameter settings can be set by the administrator.</span></span>

<span data-ttu-id="b4f8c-118">De test 'Test de rest' uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="b4f8c-118">To run the "Test the Rest" test:</span></span>

1. <span data-ttu-id="b4f8c-119">Open het **tabblad \> Relevantietoets.**</span><span class="sxs-lookup"><span data-stu-id="b4f8c-119">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="b4f8c-120">Klik op **het** tabblad Test op **Nieuwe test.**</span><span class="sxs-lookup"><span data-stu-id="b4f8c-120">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="b4f8c-121">Het **dialoogvenster Test maken** wordt weergegeven, zoals wordt weergegeven in het volgende voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-121">The **Create test** dialog is displayed, as shown in the following example.</span></span>

    ![Relevantie test de resultaten van de rest](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="b4f8c-123">Typ **in Testnaam** en **Beschrijving** de naam en beschrijving.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-123">In **Test name**, and **Description**, type the name and description.</span></span>

4. <span data-ttu-id="b4f8c-124">Selecteer in **de lijst Testtype** **de optie Rest testen**</span><span class="sxs-lookup"><span data-stu-id="b4f8c-124">In the **Test type** list, select **Test the Rest**</span></span>

5. <span data-ttu-id="b4f8c-125">Selecteer in **de lijst Probleem/categorie** de naam van het probleem.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-125">In the **Issue / Category** list, select the issue name.</span></span>

6. <span data-ttu-id="b4f8c-126">Selecteer de belasting in **de** lijst Laden.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-126">In the **Load** list, select the load.</span></span> 

7. <span data-ttu-id="b4f8c-127">Accepteer **in Lees %** de standaardwaarde of selecteer een waarde voor de cutoff Relevantiescore.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-127">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 

8. <span data-ttu-id="b4f8c-128">In **Grootte instellen** of de standaardwaarde accepteren.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-128">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="b4f8c-129">Met de pictogrammen voor herstellen worden de standaardwaarden hersteld.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-129">The restore icons will restore the default values.</span></span>

9. <span data-ttu-id="b4f8c-130">Klik **op Labelen starten.**</span><span class="sxs-lookup"><span data-stu-id="b4f8c-130">Click **Start tagging**.</span></span> <span data-ttu-id="b4f8c-131">Er wordt een testvoorbeeld gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-131">A test sample is generated.</span></span>

10. <span data-ttu-id="b4f8c-132">Controleer en tag elk van de bestanden op het tabblad **\> Relevantielabel** en klik wanneer u klaar bent op **Berekenen.**</span><span class="sxs-lookup"><span data-stu-id="b4f8c-132">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="b4f8c-133">Klik op het tabblad Test op **Resultaten weergeven om** de testresultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-133">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="b4f8c-134">Een voorbeeld wordt weergegeven in de volgende schermafbeelding.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-134">An example is shown in the following screenshot.</span></span>

    ![Test de overige resultaten](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="b4f8c-136">In de vorige schermafbeelding bevat de sectie **Voorbeeldparameters** van de tabel details over het aantal bestanden in het voorbeeld dat door de expert is gelabeld en het aantal relevante bestanden dat in dat voorbeeld is gevonden.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-136">In the previous screenshot, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span>
  
<span data-ttu-id="b4f8c-137">De sectie **Populatieparameters** van de tabel bevat de testresultaten, inclusief de populatie van bestanden controleren met een score onder de geselecteerde cutoff en 'De rest'-populatie van bestanden met een score boven de geselecteerde cutoff.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-137">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="b4f8c-138">Voor elke populatie worden de volgende resultaten weergegeven:</span><span class="sxs-lookup"><span data-stu-id="b4f8c-138">For each population, the following results are displayed:</span></span>
  
- <span data-ttu-id="b4f8c-139">Bevat bestanden met lees % - Aangegeven cutoff</span><span class="sxs-lookup"><span data-stu-id="b4f8c-139">Includes files with read % - Stated cutoff</span></span>

- <span data-ttu-id="b4f8c-140">Het totale aantal bestanden</span><span class="sxs-lookup"><span data-stu-id="b4f8c-140">The total number of files</span></span>

- <span data-ttu-id="b4f8c-141">Het geschatte aantal relevante bestanden</span><span class="sxs-lookup"><span data-stu-id="b4f8c-141">The estimated number of relevant files</span></span>

- <span data-ttu-id="b4f8c-142">De geschatte rijkheid</span><span class="sxs-lookup"><span data-stu-id="b4f8c-142">The estimated richness</span></span>

- <span data-ttu-id="b4f8c-143">De gemiddelde revisiekosten voor het zoeken naar een ander relevant bestand</span><span class="sxs-lookup"><span data-stu-id="b4f8c-143">The average review cost of finding another relevant file</span></span>

## <a name="testing-the-slice"></a><span data-ttu-id="b4f8c-144">Het segment testen</span><span class="sxs-lookup"><span data-stu-id="b4f8c-144">Testing the slice</span></span>

<span data-ttu-id="b4f8c-145">Met de test 'Test the Slice' worden tests uitgevoerd die vergelijkbaar zijn met de test 'Test the Rest', maar met een segment van het bestand dat is ingesteld op relevantie-lees %.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-145">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>

<span data-ttu-id="b4f8c-146">De test 'Het segment testen' uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="b4f8c-146">To run the "Test the Slice" test:</span></span>
  
1. <span data-ttu-id="b4f8c-147">Open het **tabblad \> Relevantietoets.**</span><span class="sxs-lookup"><span data-stu-id="b4f8c-147">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="b4f8c-148">Klik op **het** tabblad Test op **Nieuwe test.**</span><span class="sxs-lookup"><span data-stu-id="b4f8c-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="b4f8c-149">Het **dialoogvenster Test maken** wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-149">The **Create test** dialog is displayed.</span></span>

3. <span data-ttu-id="b4f8c-150">Typ de gegevens **in Testnaam** en Beschrijving.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-150">In **Test name** and **Description**, type the information.</span></span>

4. <span data-ttu-id="b4f8c-151">Selecteer in **de lijst Type** testen de optie Het segment **testen.**</span><span class="sxs-lookup"><span data-stu-id="b4f8c-151">In the **Test type** list, select **Test the Slice**.</span></span>

5. <span data-ttu-id="b4f8c-152">Selecteer in **de** lijst Probleem de naam van het probleem.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-152">In the **Issue** list, select the issue name.</span></span>

6. <span data-ttu-id="b4f8c-153">Selecteer de belasting in **de** lijst Laden.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-153">In the **Load** list, select the load.</span></span>

7. <span data-ttu-id="b4f8c-154">Accepteer **in Lees % tussen,** de standaardwaarden voor laag en hoog bereik of selecteer waarden voor de cutoff Relevantiescores.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span>

8. <span data-ttu-id="b4f8c-155">Selecteer **in Grootte instellen** een waarde of accepteer de standaardwaarde.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-155">In **Set size**, select a value or accept the default value.</span></span>

    <span data-ttu-id="b4f8c-156">Met de pictogrammen voor herstellen wordt de standaardwaarde hersteld.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-156">The restore icons will restore the default value.</span></span>

9. <span data-ttu-id="b4f8c-157">Klik **op Labelen starten.**</span><span class="sxs-lookup"><span data-stu-id="b4f8c-157">Click **Start tagging**.</span></span> <span data-ttu-id="b4f8c-158">Er wordt een testvoorbeeld gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-158">A test sample is generated.</span></span>

10. <span data-ttu-id="b4f8c-159">Controleer en tag elk van de bestanden op het tabblad **\> Relevantielabel** en klik wanneer u klaar bent op **Berekenen.**</span><span class="sxs-lookup"><span data-stu-id="b4f8c-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="b4f8c-160">Klik op het tabblad Test op **Resultaten weergeven om** de testresultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="b4f8c-160">In the Test tab, you can click **View results** to see the test results.</span></span>
