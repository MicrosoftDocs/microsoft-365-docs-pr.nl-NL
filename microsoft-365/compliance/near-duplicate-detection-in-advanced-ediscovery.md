---
title: Near duplicate detection - eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Gebruik near duplicate detection to group textually similar documents when analyzeing case data in Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161539"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a><span data-ttu-id="71b5e-103">Bijna dubbele detectie in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="71b5e-103">Near duplicate detection in Advanced eDiscovery</span></span>

<span data-ttu-id="71b5e-104">Overweeg een reeks documenten te herzien waarin een subset is gebaseerd op dezelfde sjabloon en meestal dezelfde standaardtaal heeft, met hier en daar enkele verschillen.</span><span class="sxs-lookup"><span data-stu-id="71b5e-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="71b5e-105">Als een revisor deze subset kon identificeren, een van deze subsets grondig kon bekijken en de verschillen voor de rest kon bekijken, zouden ze geen unieke informatie hebben gemist terwijl ze slechts een fractie van de tijd hadden genomen om alle documenten te lezen.</span><span class="sxs-lookup"><span data-stu-id="71b5e-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="71b5e-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span><span class="sxs-lookup"><span data-stu-id="71b5e-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="71b5e-107">Hoe werkt dit?</span><span class="sxs-lookup"><span data-stu-id="71b5e-107">How does it work?</span></span>

<span data-ttu-id="71b5e-108">Wanneer er bijna dubbele detectie wordt uitgevoerd, parseert het systeem elk document met tekst.</span><span class="sxs-lookup"><span data-stu-id="71b5e-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="71b5e-109">Vervolgens wordt elk document met elkaar vergeleken om te bepalen of de overeenkomst groter is dan de ingesteld drempelwaarde.</span><span class="sxs-lookup"><span data-stu-id="71b5e-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="71b5e-110">Als dat zo is, worden de documenten gegroepeerd.</span><span class="sxs-lookup"><span data-stu-id="71b5e-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="71b5e-111">Wanneer alle documenten zijn vergeleken en gegroepeerd, wordt een document uit elke groep gemarkeerd als het 'draaipunt'. bij het controleren van uw documenten kunt u eerst een draaipunt bekijken en de andere documenten in dezelfde bijna dubbele set bekijken, waarbij u zich richt op het verschil tussen het draaitabel en het document dat wordt beoordeeld.</span><span class="sxs-lookup"><span data-stu-id="71b5e-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
