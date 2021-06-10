---
title: Thema's - eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Gebruik Thema's in Advanced eDiscovery om revisiesets te organiseren door het dominante thema in elk document te zoeken.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161531"
---
# <a name="themes-in-advanced-ediscovery"></a><span data-ttu-id="d7ca1-103">Thema's in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d7ca1-103">Themes in Advanced eDiscovery</span></span>

<span data-ttu-id="d7ca1-104">Hoe schrijft een persoon een document?</span><span class="sxs-lookup"><span data-stu-id="d7ca1-104">How does a person write a document?</span></span> <span data-ttu-id="d7ca1-105">Ze beginnen meestal met een of meer ideeën die ze in het document willen overbrengen en opstellen met behulp van woorden die zijn uitgelijnd met de ideeën.</span><span class="sxs-lookup"><span data-stu-id="d7ca1-105">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="d7ca1-106">Hoe vaker een idee voorkomt, hoe vaker de woorden die aan dat idee zijn gerelateerd, zijn.</span><span class="sxs-lookup"><span data-stu-id="d7ca1-106">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="d7ca1-107">Op deze manier wordt ook bekent hoe personen documenten gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d7ca1-107">This informs how people consume documents as well.</span></span> <span data-ttu-id="d7ca1-108">Het belangrijkste om te begrijpen van het lezen van een document zijn de ideeën die het document probeert over te brengen, welke ideeën worden weergegeven waar en wat de relaties tussen de ideeën zijn.</span><span class="sxs-lookup"><span data-stu-id="d7ca1-108">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="d7ca1-109">Dit kan worden uitgebreid tot de manier waarop een persoon een set documenten wil gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d7ca1-109">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="d7ca1-110">Ze willen zien welke ideeën er in de sets aanwezig zijn en welke documenten over deze ideeën praten.</span><span class="sxs-lookup"><span data-stu-id="d7ca1-110">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="d7ca1-111">Als ze een bepaald document van belang vinden, willen ze ook documenten kunnen zien waarin soortgelijke ideeën worden besproken.</span><span class="sxs-lookup"><span data-stu-id="d7ca1-111">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="d7ca1-112">De functionaliteit Thema's in Advanced eDiscovery probeert na te bootsen  hoe mensen redeneren over documenten, door de thema's te analyseren die worden besproken in een revisieset en een thema toe te wijzen aan documenten in de revisieset.</span><span class="sxs-lookup"><span data-stu-id="d7ca1-112">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="d7ca1-113">In Advanced eDiscovery thema's gaat u nog een stap verder en identificeert u het *dominante thema* in elk document.</span><span class="sxs-lookup"><span data-stu-id="d7ca1-113">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="d7ca1-114">Het meest voorkomende thema is het thema dat het vaakst in een document wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d7ca1-114">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="d7ca1-115">Hoe werken thema's?</span><span class="sxs-lookup"><span data-stu-id="d7ca1-115">How does Themes work?</span></span>

<span data-ttu-id="d7ca1-116">De functie Thema's analyseert documenten met tekst in een revisieset om algemene thema's te parseren die worden weergegeven in alle documenten in de revisieset.</span><span class="sxs-lookup"><span data-stu-id="d7ca1-116">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="d7ca1-117">Advanced eDiscovery deze thema's toe aan de documenten waarin ze worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d7ca1-117">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="d7ca1-118">Het labelt ook elk thema met de woorden die worden gebruikt in de documenten die representatief zijn voor het thema.</span><span class="sxs-lookup"><span data-stu-id="d7ca1-118">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="d7ca1-119">Omdat een document verschillende typen onderwerp kan bevatten, Advanced eDiscovery vaak meerdere thema's aan documenten toegewezen.</span><span class="sxs-lookup"><span data-stu-id="d7ca1-119">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="d7ca1-120">Het thema dat het meest prominent in een document wordt weergegeven, wordt aangeduid als het hoofdthema.</span><span class="sxs-lookup"><span data-stu-id="d7ca1-120">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
