---
title: Configuratie voor relevantie beheren in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
ROBOTS: NOINDEX, NOFOLLOW
description: Lees de aanbevelingen voor het instellen van relevantie-training in Advanced eDiscovery om bestanden te scoren op hun relevantie en analytische resultaten te genereren.
ms.openlocfilehash: 8ba09babc91f233514cd0195c3e1da08b07ccb3c
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "52161660"
---
# <a name="manage-relevance-setup-in-advanced-ediscovery-classic"></a><span data-ttu-id="58e08-103">Configuratie voor relevantie beheren in Advanced eDiscovery (klassiek).</span><span class="sxs-lookup"><span data-stu-id="58e08-103">Manage Relevance setup in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="58e08-104">Voor Advanced eDiscovery is een Office 365 E3 vereist met de Advanced Compliance-invoegtoepassing of een E5-abonnement voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="58e08-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="58e08-105">Als u niet beschikt over een van deze abonnementen en Advanced eDiscovery wilt uitproberen, kunt u zich [registreren voor een proefabonnement op Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="58e08-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="58e08-106">Advanced eDiscovery-relevantietechnologie maakt gebruik van door experts begeleide software voor het scoren van bestanden op hun relevantie.</span><span class="sxs-lookup"><span data-stu-id="58e08-106">Advanced eDiscovery Relevance technology employs expert-guided software for scoring files by their relevance.</span></span> <span data-ttu-id="58e08-107">Advanced eDiscovery-relevantie kan worden gebruikt voor beoordeling van vroege cases (ECA), selectie en beoordeling van bestandsvoorbeelden.</span><span class="sxs-lookup"><span data-stu-id="58e08-107">Advanced eDiscovery Relevance can be used for Early Case Assessment (ECA), culling, and file sample review.</span></span> 
  
 <span data-ttu-id="58e08-108">Advanced eDiscovery bevat onderdelen voor de Relevantie-training en het taggen van bestanden die relevant zijn voor een case.</span><span class="sxs-lookup"><span data-stu-id="58e08-108">Advanced eDiscovery includes components for the Relevance training and tagging of files relevant to a case.</span></span> <span data-ttu-id="58e08-109">Advanced eDiscovery leert van de ingeleerde voorbeelden van relevante en niet-relevante bestanden om Relevantie-scores voor elk bestand te leveren en genereert analytische resultaten die tijdens en na de bestandsbeoordeling kunnen worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="58e08-109">Advanced eDiscovery learns from the trained samples of Relevant and Not Relevant files to provide Relevance scores for each file, and generates analytical results that can be used during and after the file review process.</span></span> 
  
## <a name="guidelines-for-setting-up-relevance-training"></a><span data-ttu-id="58e08-110">Richtlijnen voor het instellen van Relevantie-training</span><span class="sxs-lookup"><span data-stu-id="58e08-110">Guidelines for setting up Relevance training</span></span>

 <span data-ttu-id="58e08-111">Selecteer in Advanced eDiscovery in het venster **Cases** een case en klik op **Ga naar case**.</span><span class="sxs-lookup"><span data-stu-id="58e08-111">In Advance eDiscovery, in the **Cases** window, select a case and click **Go to case**.</span></span> <span data-ttu-id="58e08-112">Klik op **Relevantie** \> **Configuratie van relevantie**.</span><span class="sxs-lookup"><span data-stu-id="58e08-112">Click **Relevance** \> **Relevance setup**.</span></span> <span data-ttu-id="58e08-113">Volg deze aanbevolen richtlijnen om Relevantie in te stellen.</span><span class="sxs-lookup"><span data-stu-id="58e08-113">Follow these recommended guidelines to set up Relevance.</span></span> 
  
- <span data-ttu-id="58e08-114">**Taggen**: De doeltreffendheid van het iteratieve Relevantie-trainingsproces hangt af van het vermogen van de expert om de bestandssamples met precisie en consistentie te taggen.</span><span class="sxs-lookup"><span data-stu-id="58e08-114">**Tagging**: The effectiveness of the iterative Relevance training process is dependent on the ability of the expert to tag the file samples with precision and consistency.</span></span>

- <span data-ttu-id="58e08-115">**Problemen met case**:</span><span class="sxs-lookup"><span data-stu-id="58e08-115">**Case issues**:</span></span>
  
  - <span data-ttu-id="58e08-116">Gebruik voor elk probleem dezelfde expert in het hele Relevantie-trainingsproces.</span><span class="sxs-lookup"><span data-stu-id="58e08-116">For each issue, use the same expert throughout the entire Relevance training process.</span></span> <span data-ttu-id="58e08-117">Gelijktijdig taggen van hetzelfde probleem door meerdere experts is niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="58e08-117">Simultaneous tagging of the same issue by multiple experts is not permitted.</span></span>
  
  - <span data-ttu-id="58e08-118">Bepaal of elke groep bestanden alleen relevant is voor een specifiek probleem.</span><span class="sxs-lookup"><span data-stu-id="58e08-118">Determine if each group of files is pertinent only to a specific issue.</span></span>

  - <span data-ttu-id="58e08-119">Als een probleem te algemeen is gedefinieerd, kan Advanced eDiscovery te veel bestanden opleveren die niet relevant zijn.</span><span class="sxs-lookup"><span data-stu-id="58e08-119">If an issue is defined too generally, Advanced eDiscovery may yield too many files that are not relevant.</span></span> <span data-ttu-id="58e08-120">Als een probleem te smal is gedefinieerd, kan het Relevantie-trainingsproces meer tijd in beslag nemen.</span><span class="sxs-lookup"><span data-stu-id="58e08-120">If an issue is defined too narrowly, the Relevance training process may take more time.</span></span> 

  - <span data-ttu-id="58e08-121">Tijdens elke Relevantie-trainingscyclus richt Advanced eDiscovery zich op één actief probleem en worden tussentijdse voorbeeldresultaten dienovereenkomstig weergegeven.</span><span class="sxs-lookup"><span data-stu-id="58e08-121">During each Relevance training cycle, Advanced eDiscovery focuses on a single active issue and interim sample results are displayed accordingly.</span></span>

  - <span data-ttu-id="58e08-122">In een scenario met meerdere problemen kan in de Samplingmodus een selectie worden gemaakt van problemen die in de verwerking moeten worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="58e08-122">In a multiple-issue scenario, the Sampling mode enables the selection of issues to be included in processing.</span></span> <span data-ttu-id="58e08-123">Problemen die zijn gedefinieerd als 'uit', worden pas verwerkt als de Samplingmodus is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="58e08-123">Issues defined as "off" are not handled until their Sampling mode is changed.</span></span> <span data-ttu-id="58e08-124">Een probleem kan voor slechts één expert 'inactief' of 'aan' zijn.</span><span class="sxs-lookup"><span data-stu-id="58e08-124">An issue can be "idle" or "on" for only one expert.</span></span>

  - <span data-ttu-id="58e08-125">Advanced eDiscovery kan worden gebruikt om bestanden met kandidatenrechten te genereren.</span><span class="sxs-lookup"><span data-stu-id="58e08-125">Advanced eDiscovery can be used to generate candidate privilege files.</span></span> <span data-ttu-id="58e08-126">Stel een afzonderlijk probleem voor bevoegdheden in.</span><span class="sxs-lookup"><span data-stu-id="58e08-126">Set up a separate issue for privilege.</span></span> <span data-ttu-id="58e08-127">Train en kom eerst met een relevante waarde en train vervolgens alleen voor bevoegdheden in de geselecteerde set (laad de set opnieuw als afzonderlijke case).</span><span class="sxs-lookup"><span data-stu-id="58e08-127">If possible, train and cull for relevance first, and then train for privilege on the culled set only (reload the culled set as a separate case).</span></span> 

  - <span data-ttu-id="58e08-128">Batchberekening kan alleen worden uitgevoerd wanneer er geen open voorbeelden zijn (wanneer u op Batchberekening klikt, wordt een lijst weergegeven met gebruikers met open voorbeelden).</span><span class="sxs-lookup"><span data-stu-id="58e08-128">Batch calculation can be performed only when there are no open samples (when clicking Batch Calculation, there will be a list displayed of users with open samples).</span></span> <span data-ttu-id="58e08-129">Als u voorbeelden van andere gebruikers wilt 'sluiten' (deze moeten alleen worden uitgevoerd als deze gebruikers deze voorbeelden niet taggen), kan een beheerder het hulpprogramma 'Relevantie wijzigen' gebruiken met de optie 'Voorbeeld alle gebruikers'.</span><span class="sxs-lookup"><span data-stu-id="58e08-129">To "close" samples of other users (this should be performed only if these users are not tagging these samples), an Administrator can use the "Modify relevance" utility with the "All users sample" option.</span></span>

- <span data-ttu-id="58e08-130">**Metagegevens**: Advanced eDiscovery richt zich op inhoud.</span><span class="sxs-lookup"><span data-stu-id="58e08-130">**Metadata**: Advanced eDiscovery focuses on content.</span></span> <span data-ttu-id="58e08-131">Metagegevens worden niet als onderdeel van de relevantie-criteria gezien.</span><span class="sxs-lookup"><span data-stu-id="58e08-131">It does not consider metadata as part of the relevance criteria.</span></span>

- <span data-ttu-id="58e08-132">**Rijkheid**: Als de rijkheid voor een probleem na beoordeling kleiner is dan 3%, kunt u overwegen de Relevantie-training te seeden met bekende relevante en niet-relevante bestanden.</span><span class="sxs-lookup"><span data-stu-id="58e08-132">**Richness**: If the Richness for an issue is less than 3% after Assessment, consider seeding the Relevance training with known Relevant and Not Relevant files.</span></span>

- <span data-ttu-id="58e08-133">**Bestandsgrootte**: grote bestanden (meer dan 5.242.880 tekens aan uitgepakte tekst) worden genegeerd in Relevantie.</span><span class="sxs-lookup"><span data-stu-id="58e08-133">**File size**: Large files (over 5,242,880 characters of extracted text) are ignored in Relevance.</span></span> <span data-ttu-id="58e08-134">De bestanden nemen niet deel aan het Relevantie-trainingsproces en ontvangen geen Relevantiescore na Batchberekening.</span><span class="sxs-lookup"><span data-stu-id="58e08-134">The files do not participate in the Relevance training process and do not receive a Relevance score after Batch Calculation.</span></span> <span data-ttu-id="58e08-135">Bestanden van meer dan 5 MB kunnen worden opgenomen in de Beoordelingsset.</span><span class="sxs-lookup"><span data-stu-id="58e08-135">Files over 5 MB can be included in the Assessment set.</span></span>

## <a name="setting-up-case-issues"></a><span data-ttu-id="58e08-136">Problemen met het instellen van cases</span><span class="sxs-lookup"><span data-stu-id="58e08-136">Setting up case issues</span></span>

<span data-ttu-id="58e08-137">De parameters die in deze sectie worden beschreven, zijn beschikbaar in Advanced eDiscovery **Relevantie** \> **Configuratie van relevantie**.</span><span class="sxs-lookup"><span data-stu-id="58e08-137">The parameters described in this section are available in the Advanced eDiscovery **Relevance** \> **Relevance setup**.</span></span>
  
- <span data-ttu-id="58e08-138">Problemen moeten worden toegewezen aan een gebruiker die de bestanden zal trainen.</span><span class="sxs-lookup"><span data-stu-id="58e08-138">Issues must be assigned to a user who will train the files.</span></span>

- <span data-ttu-id="58e08-139">Geïmporteerde bestanden moeten vervolgens worden toegevoegd aan de belasting die wordt verwerkt.</span><span class="sxs-lookup"><span data-stu-id="58e08-139">Imported files must then be added to the load being processed.</span></span>

- <span data-ttu-id="58e08-140">Definieer en organiseer problemen zorgvuldig. Dit kan van invloed zijn op de resultaten van de Relevantie-training.</span><span class="sxs-lookup"><span data-stu-id="58e08-140">Define and organize issues carefully, as this can impact the Relevance training results.</span></span>

<span data-ttu-id="58e08-141">Nadat parameters zijn ingesteld, kan de revisor/expert de bestanden gaan trainen in het tabblad **Relevantie**.</span><span class="sxs-lookup"><span data-stu-id="58e08-141">After parameters are set, the reviewer / expert can start training the files in the **Relevance** tab.</span></span>
