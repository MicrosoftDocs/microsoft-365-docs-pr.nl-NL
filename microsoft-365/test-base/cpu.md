---
title: CPU-regressieanalyse
description: Regressieresultaten en metrische gegevens voor CPU-verbruik
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
ms.openlocfilehash: bc28c128902ae353fb35c3b6010856ade934a436
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322719"
---
# <a name="intelligent-cpu-regression-analysis"></a><span data-ttu-id="f65a4-103">Intelligente CPU-regressieanalyse</span><span class="sxs-lookup"><span data-stu-id="f65a4-103">Intelligent CPU regression analysis</span></span>

<span data-ttu-id="f65a4-104">Cpu-gebruik kan aangeven of een toepassing wordt beïnvloed door een update van het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="f65a4-104">CPU utilization can indicate whether an application is affected by an operating system update.</span></span> 

<span data-ttu-id="f65a4-105">Test Base voor Microsoft 365 biedt softwareontwikkelaars inzicht in regressies van cpu-prestaties die optreden wanneer hun toepassing wordt uitgevoerd op verschillende versies van een komende update van het besturingssysteem Windows besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="f65a4-105">Test Base for Microsoft 365 provides software developers with an insight into CPU performance regressions which occur when their application is running on different versions of an upcoming Windows Operating System (OS) update.</span></span> 

<span data-ttu-id="f65a4-106">Met deze CPU-regressies kunnen ontwikkelaars toepassingsproblemen (en mogelijke fouten) detecteren en oplossen voordat de os-update breed wordt geïmplementeerd, waardoor een slechte ervaring voor de eindgebruiker wordt voorkomen.</span><span class="sxs-lookup"><span data-stu-id="f65a4-106">These CPU regressions enable developers to detect and resolve application issues (and potential failures) before the OS update is deployed broadly, thus preventing a bad experience for the end user.</span></span>


### <a name="how-cpu-regression-analysis-works"></a><span data-ttu-id="f65a4-107">Hoe cpu-regressieanalyse werkt</span><span class="sxs-lookup"><span data-stu-id="f65a4-107">How CPU regression analysis works</span></span> ###

<span data-ttu-id="f65a4-108">Als testbasisgebruiker kunt u de binaries van uw toepassing uploaden (in één .zip-bestand), samen met bijbehorende testscripts en de versie van het Windows-besturingssysteem selecteren waarmee u de toepassing wilt testen in de Test Base-portal in Azure.</span><span class="sxs-lookup"><span data-stu-id="f65a4-108">As a Test Base user, you can upload your application's binaries (in a single .zip file), along with associated test scripts and select the Windows OS version against which you would like to test your application on the Test Base portal on Azure.</span></span> 

<span data-ttu-id="f65a4-109">De Test Base-service voert vervolgens de testscripts uit en voert de **CPU-regressieanalyse uit.**</span><span class="sxs-lookup"><span data-stu-id="f65a4-109">The Test Base service then runs the test scripts and performs the **CPU Regression Analysis**.</span></span> 

<span data-ttu-id="f65a4-110">De service controleert of het CPU-gebruik voor de toepassing in de pre-releaseversie van de update voor het doelbesturingssysteem in overeenstemming is met het CPU-gebruik voor de uitgebrachte versie van het besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="f65a4-110">The service checks if the CPU utilization for the application on the pre-release version of the update for the target OS is in line with the CPU utilization for the released version of the OS.</span></span> 

<span data-ttu-id="f65a4-111">CPU-gebruik is geen vergelijking van 100% like-for-like, omdat de processen die op de twee versies van het besturingssysteem worden uitgevoerd, al dan niet exact overeenkomen vanwege verschillende besturingssysteemversies. De analyse die door Test Base wordt uitgevoerd, kan echter laten zien of het CPU-gebruik voor uw toepassing wordt beïnvloed door een aanstaande OS-update en specifiek welke processen zijn teruggegaan van eerdere testuitloops.</span><span class="sxs-lookup"><span data-stu-id="f65a4-111">CPU utilization is not a 100% like-for-like comparison because the processes running on the two versions of the OS may or may not be an exact match due to differing OS versions; however, the analysis performed by Test Base can show you whether CPU utilization for your application is impacted by an upcoming OS update and specifically which processes have regressed from previous test runs.</span></span>

<span data-ttu-id="f65a4-112">In de onderstaande momentopname zijn er twee besturingssysteemreleases waarmee de CPU-gebruik wordt vergeleken voor dezelfde toepassing.</span><span class="sxs-lookup"><span data-stu-id="f65a4-112">In the snapshot below, there are two OS releases against which the CPU utilizations are compared for the same application.</span></span> 
-   <span data-ttu-id="f65a4-113">Op het tabblad CPU-gebruik worden de boven- en ondergrens van het gebruik weergegeven voor beide versies van respectievelijk 90e en 10e percentiel.</span><span class="sxs-lookup"><span data-stu-id="f65a4-113">The CPU utilization tab shows the upper and lower bounds of utilization for both releases at 90th and 10th percentiles respectively.</span></span> 
-   <span data-ttu-id="f65a4-114">De grafieken geven de tijdreeks cpu-gebruik weer, samen met het gemiddelde gebruik.</span><span class="sxs-lookup"><span data-stu-id="f65a4-114">The graphs show the time series of CPU utilization along with the average utilization.</span></span> 

<span data-ttu-id="f65a4-115">Klanten kunnen nu de functionaliteit gebruiken om te bepalen of het CPU-gebruik van hun toepassing wordt beïnvloed door os-updates en specifiek welke processen zijn teruggegaan van de vorige uitvoering.</span><span class="sxs-lookup"><span data-stu-id="f65a4-115">Customers can now use the functionality to determine if their application's CPU utilization is impacted by OS updates and specifically which processes have regressed from their previous execution.</span></span>


![CPU-regressieanalyse](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a><span data-ttu-id="f65a4-117">Relevante procesidentificatie</span><span class="sxs-lookup"><span data-stu-id="f65a4-117">Relevant Process Identification</span></span> ###

<span data-ttu-id="f65a4-118">Hier bespreken we hoe u regressieve processen in de toepassing kunt identificeren.</span><span class="sxs-lookup"><span data-stu-id="f65a4-118">Here, we discuss how to identify regressed processes in the application.</span></span> 

<span data-ttu-id="f65a4-119">Als u prestatie-regressie analyseert, moet u verschillende soorten prestatietellers bijhouden voor elk proces dat tijdens de test op een virtuele computer wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="f65a4-119">Analyzing performance regression requires tracking different kinds of performance counters for every process running on a virtual machine during the test run.</span></span> 

<span data-ttu-id="f65a4-120">Een dergelijke analyse legt een groot aantal variabelen vast voor een groot aantal processen voor een bepaalde toepassing.</span><span class="sxs-lookup"><span data-stu-id="f65a4-120">Such analysis captures a lot of variables for a lot of processes for a given application.</span></span> <span data-ttu-id="f65a4-121">Niet alle processen zijn gekoppeld aan een uitvoering of toepassing.</span><span class="sxs-lookup"><span data-stu-id="f65a4-121">Not all processes are associated with a run or application.</span></span> <span data-ttu-id="f65a4-122">Om deze uitdaging te voltooien, wordt een algoritme voor het rangschikken van gegevens met behulp van kans- en informatietheorie toegepast om erachter te komen welke processen het meest relevant zijn voor een bepaalde toepassing.</span><span class="sxs-lookup"><span data-stu-id="f65a4-122">To work around this challenge, a mutual information ranking algorithm using probability and information theory is applied to figure out which processes are most relevant for a given application.</span></span> 

<span data-ttu-id="f65a4-123">Een toepassing kan worden beschouwd als één type afzonderlijke willekeurige variabele, terwijl een proces wordt beschouwd als een ander soort discrete willekeurige variabele.</span><span class="sxs-lookup"><span data-stu-id="f65a4-123">An application can be considered one type of discrete random variable while a process is considered another kind of discrete random variable.</span></span> <span data-ttu-id="f65a4-124">De associatie van de twee willekeurige variabelen wordt gemeten met behulp van voorwaardelijke waarschijnlijkheid voor relevantie.</span><span class="sxs-lookup"><span data-stu-id="f65a4-124">The association of the two random variables is measured using conditional probabilities for relevance.</span></span> 

<span data-ttu-id="f65a4-125">Processen worden vervolgens weergegeven in de volgorde van hun relevantie voor elke toepassing.</span><span class="sxs-lookup"><span data-stu-id="f65a4-125">Processes are then displayed in the order of their relevance for each application.</span></span> <span data-ttu-id="f65a4-126">U kunt ook een subset met processen favoriet maken die standaard kunnen worden gecontroleerd, samen met relevante processen voor regressieanalyse van cpu's.</span><span class="sxs-lookup"><span data-stu-id="f65a4-126">You can also favorite a subset of processes that can be monitored, by default, along with relevant processes for CPU regression analysis.</span></span> <span data-ttu-id="f65a4-127">Wanneer een regressie is gedetecteerd, kunt u de Windows Performance Analyzer downloaden en redenen voor regressies van de CPU-prestaties analyseren.</span><span class="sxs-lookup"><span data-stu-id="f65a4-127">Once a regression is detected, you can download the Windows Performance Analyzer toolkit and analyze reasons for CPU performance regressions.</span></span> 

<span data-ttu-id="f65a4-128">Met Windows Performance Analyzer wordt etl (Event Trace Log) als invoer gebruikt en deze ETL-bestanden zijn beschikbaar in de logboekbestanden die kunnen worden gedownload voor testritten op de portal.</span><span class="sxs-lookup"><span data-stu-id="f65a4-128">The Windows Performance Analyzer takes event trace log (ETL) as inputs and these .etl files are available in the log files downloadable for test runs on the portal.</span></span> <span data-ttu-id="f65a4-129">Als u meer wilt weten over het debuggen van cpu-prestaties, bekijkt u de documentatie Windows Performance Analyzer.</span><span class="sxs-lookup"><span data-stu-id="f65a4-129">If you would like to know more about debugging CPU performance, see the Windows Performance Analyzer documentation.</span></span>

