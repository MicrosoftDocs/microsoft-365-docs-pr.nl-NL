---
title: Geheugen regressieanalyse
description: Geheugen regressie afleiden
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: cd95c4e0eb04b05860ded256066913cf87d67e86
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322787"
---
# <a name="memory-regression-analysis"></a><span data-ttu-id="07f7f-103">Geheugen regressieanalyse</span><span class="sxs-lookup"><span data-stu-id="07f7f-103">Memory Regression Analysis</span></span>

<span data-ttu-id="07f7f-104">Test Base helpt u duidelijker te zien dat het geheugengebruik aanzienlijk toeneemt in de test-VM's met uw apps.</span><span class="sxs-lookup"><span data-stu-id="07f7f-104">Test Base helps you more clearly notice significant memory usage increases in the test VMs running your apps.</span></span> <span data-ttu-id="07f7f-105">Prestatiegegevens, zoals geheugengebruik, kunnen een indicatie zijn van de algehele toepassingstoestand en we zijn van mening dat deze toevoeging uw apps optimaal kan laten presteren.</span><span class="sxs-lookup"><span data-stu-id="07f7f-105">Performance metrics, such as memory usage, can be indicative of overall application health and we believe this addition will greatly help keep your apps performing optimally.</span></span>

<span data-ttu-id="07f7f-106">Lees verder voor meer informatie of bekijk deze video voor een beknopt overzicht van de meest recente verbeteringen.</span><span class="sxs-lookup"><span data-stu-id="07f7f-106">Read on for more details or watch this video for a quick walk through of the latest improvements.</span></span> 

<span data-ttu-id="07f7f-107">Zie Regressieresultaten op basis van procesbetrouwbaarheid voor meer informatie over de mogelijkheid van M365 om te helpen bij regressieanalyse.</span><span class="sxs-lookup"><span data-stu-id="07f7f-107">For more information on Test Base for M365's ability to help with regression analysis, see Regression results based on process reliability.</span></span>

<span data-ttu-id="07f7f-108"><b>Geheugen regressies nader bekijken</b></span><span class="sxs-lookup"><span data-stu-id="07f7f-108"><b>Looking closer at memory regressions</b></span></span>

<span data-ttu-id="07f7f-109">Het testbasisdashboard voor M365 toont het geheugen dat door uw toepassing wordt verbruikt bij een nieuwe, vooraf uitgebrachte Windows-update en vergelijkt het met het geheugen dat is gebruikt door de laatst uitgebrachte Windows update.</span><span class="sxs-lookup"><span data-stu-id="07f7f-109">The Test Base for M365 dashboard shows the memory consumed by your application on a new pre-released Windows update and compares it with the memory used by the last released Windows update.</span></span> 

<span data-ttu-id="07f7f-110">Met de verbeteringen van deze maand wordt geheugen-regressieanalyse nu opgenomen in uw favoriete processen.</span><span class="sxs-lookup"><span data-stu-id="07f7f-110">With this month’s enhancements, memory regression analysis is now featured in your favorited processes.</span></span> <span data-ttu-id="07f7f-111">Toepassingen kunnen meerdere processen bevatten en u kunt uw favoriete processen handmatig selecteren via het tabblad Betrouwbaarheid. Onze service identificeert vervolgens geheugenregressies in deze favoriete processen en vergelijkt test uitgevoerd in verschillende versies Windows updatereleases.</span><span class="sxs-lookup"><span data-stu-id="07f7f-111">Applications can contain multiple processes and you can manually select your favorite processes through the Reliability tab. Our service will then identify memory regressions in these favorited processes while comparing test runs across different Windows update releases.</span></span> <span data-ttu-id="07f7f-112">Als een regressie wordt gedetecteerd, zijn details over de regressie eenvoudig beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="07f7f-112">If a regression is detected, details about the regression are easily available.</span></span>

<span data-ttu-id="07f7f-113">Laten we deze functie nu in detail bekijken en bespreken hoe u geheugenregressies kunt oplossen met Windows Performance Analyzer.</span><span class="sxs-lookup"><span data-stu-id="07f7f-113">Now let's look at this feature in detail and discuss how you can troubleshoot memory regressions using Windows Performance Analyzer.</span></span>

<span data-ttu-id="07f7f-114">Het foutsignaal dat wordt veroorzaakt door een geheugen regressie, wordt weergegeven in het dashboard Testbasis voor M365 op de pagina Testresultaten onder Geheugengebruik:</span><span class="sxs-lookup"><span data-stu-id="07f7f-114">The failure signal caused by a memory regression is shown in the Test Base for M365 dashboard on the Test results page under Memory Utilization:</span></span>

![Geheugengebruiksresultaten](Media/01_memory-utilization-results.png)


<span data-ttu-id="07f7f-116">Fout voor de toepassing als gevolg van een hoger geheugenverbruik, wordt ook weergegeven zoals ```Fail``` op de pagina Testoverzicht:</span><span class="sxs-lookup"><span data-stu-id="07f7f-116">Failure for the application due to higher memory consumption, will also be displayed as ```Fail``` on the Test Summary page:</span></span>

![Samenvattingsresultaten testen](Media/02_test-summary.png)

<span data-ttu-id="07f7f-118">Door deze foutsignalen vooraf op te geven, is het ons doel om duidelijke markeringen te geven voor mogelijke problemen die de ervaring van de eindgebruiker voor uw toepassing kunnen verstoren en beïnvloeden.</span><span class="sxs-lookup"><span data-stu-id="07f7f-118">By providing these failure signals upfront, our goal is to clearly flag potential issues that can disrupt and impact the end user experience for your application.</span></span> 

<span data-ttu-id="07f7f-119">Vervolgens kunt u de logboekbestanden downloaden en de Windows Performance Analyzer of de gewenste toolkit gebruiken om verder te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="07f7f-119">You can then download the log files and use the Windows Performance Analyzer, or your preferred toolkit, to investigate further.</span></span> <span data-ttu-id="07f7f-120">U kunt ook samenwerken met het Test Base voor M365-team om het probleem te verhelpen en problemen met eindgebruikers te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="07f7f-120">You can also work jointly with the Test Base for M365 team on remediating the issue and help prevent issues impacting end users.</span></span>

<span data-ttu-id="07f7f-121">Geheugensignalen worden vastgelegd op het tabblad Geheugengebruik in de Testbasis voor M365-service voor alle testuitjes.</span><span class="sxs-lookup"><span data-stu-id="07f7f-121">Memory signals are captured in the Memory Utilization tab in the Test Base for M365 service for all test runs.</span></span> <span data-ttu-id="07f7f-122">In het onderstaande voorbeeld ziet u een recente test met de onboarded-toepassing 'Smoke Test Memory Stress' tegen de beveiligingsupdate van augustus 2020 van vóór de release.</span><span class="sxs-lookup"><span data-stu-id="07f7f-122">The example below shows a recent test run with the onboarded application “Smoke Test Memory Stress” against the pre-release August 2020 security update.</span></span> <span data-ttu-id="07f7f-123">(Deze toepassing is geschreven door ons team om geheugen regressies te illustreren.)</span><span class="sxs-lookup"><span data-stu-id="07f7f-123">(This application was written by our team to illustrate memory regressions.)</span></span>

![Resultaten van geheugen regressie](Media/03_memory-regression%20comparison.png)

<span data-ttu-id="07f7f-125">In dit voorbeeld heeft het favoriete proces 'USLTestMemoryStress.exe' een gemiddelde van ongeveer 100 MB verbruikt in de update van augustus vóór de release van augustus in vergelijking met de uitgebrachte update van juli, vandaar dat in de testbasis voor M365 een regressie is vastgesteld.</span><span class="sxs-lookup"><span data-stu-id="07f7f-125">In this example, the favorite process “USLTestMemoryStress.exe” process consumed an average of approximately 100 MB on the pre-release August update compared to the released July update, hence the Test Base for M365 identified a regression.</span></span> 

<span data-ttu-id="07f7f-126">De andere processen, hier weergegeven als 'USLTestMemoryStress_Aux1.exe' en 'USLTestMemoryStress_Aux2.exe', behoren ook tot dezelfde toepassing, maar verbruikten ongeveer dezelfde hoeveelheid geheugen voor de twee versies, zodat ze 'zijn doorgegeven' en als gezond werden beschouwd.</span><span class="sxs-lookup"><span data-stu-id="07f7f-126">The other processes—shown here as “USLTestMemoryStress_Aux1.exe” and “USLTestMemoryStress_Aux2.exe”—also belong to the same application, but consumed approximately the same amount of memory for the two releases so they "passed" and were considered healthy.</span></span>

<span data-ttu-id="07f7f-127">De regressie in het hoofdproces werd bepaald als 'statistisch significant', dus de service communiceerde en gemarkeerde dit verschil voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="07f7f-127">The regression on the main process was determined to be “statistically significant” so the service communicated and highlighted this difference to the user.</span></span> <span data-ttu-id="07f7f-128">Als de vergelijking statistisch niet significant was, werd deze niet gemarkeerd.</span><span class="sxs-lookup"><span data-stu-id="07f7f-128">If the comparison was not statistically significant, it would not be highlighted.</span></span> <span data-ttu-id="07f7f-129">Geheugengebruik kan luidruchtig zijn, dus gebruiken we statistische modellen om tussen builds en releases duidelijke verschillen te onderscheiden van inconsequentiële verschillen.</span><span class="sxs-lookup"><span data-stu-id="07f7f-129">Memory utilization can be noisy, so we use statistical models to distinguish, across builds and releases, meaningful differences from inconsequential differences.</span></span> 

<span data-ttu-id="07f7f-130">Een vergelijking kan zelden worden gemarkeerd als er geen waar verschil is (een onwaar positief), maar dit is een noodzakelijke afweging om de kans op het correct identificeren van regressies (of echte positieven) te verbeteren.)</span><span class="sxs-lookup"><span data-stu-id="07f7f-130">A comparison may rarely be flagged when there is no true difference (a false positive), but this is a necessary tradeoff to improve the likelihood of correctly identifying regressions (or true positives.)</span></span>

<span data-ttu-id="07f7f-131">De volgende stap is om te begrijpen wat de oorzaak is van de regressie van het geheugen.</span><span class="sxs-lookup"><span data-stu-id="07f7f-131">The next step is to understand what caused the memory regression.</span></span> <span data-ttu-id="07f7f-132">U kunt de zip-bestanden voor beide uitvoeringen downloaden via de optie Logboekbestanden downloaden, zoals hieronder wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="07f7f-132">You can download the zip files for both executions from the Download log files option, as shown below.</span></span> 

<span data-ttu-id="07f7f-133">Deze zip-bestanden bevatten de resultaten van de test, inclusief scriptresultaten en geheugen- en CPU-prestatiegegevens die zijn opgenomen in het ETL-bestand.</span><span class="sxs-lookup"><span data-stu-id="07f7f-133">These zip files contain the results of your test run, including script results and memory and CPU performance data which is included in the ETL file.</span></span>

![Geheugen regressie testbestanden](Media/04_memory-regression-test-files.png)

<span data-ttu-id="07f7f-135">U kunt de logboeken voor de twee testversies downloaden en uitlijnen, vervolgens het ETL-bestand in elke map zoeken en de naam ervan wijzigen als target.etl (voor de test uitgevoerd op de pre-releaseupdate) en baseline.etl (voor de test uitgevoerd op de laatst uitgebrachte update) om de verkenning en navigatie te vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="07f7f-135">You can download and unzip the logs for the two test runs, then locate the ETL file within each folder and rename them as target.etl (for the test run on the pre-release update) and baseline.etl (for the test run on last released update) to simplify exploration and navigation.</span></span>
 
## <a name="next-steps"></a><span data-ttu-id="07f7f-136">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="07f7f-136">Next steps</span></span>

<span data-ttu-id="07f7f-137">Ga naar het volgende artikel om aan de slag te gaan met het begrijpen van intelligente CPU-regressieanalyse.</span><span class="sxs-lookup"><span data-stu-id="07f7f-137">Advance to the next article to get started with understanding intelligent CPU regression analysis.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="07f7f-138">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="07f7f-138">Next step</span></span>](cpu.md)

<!---
Add button for next page
-->
