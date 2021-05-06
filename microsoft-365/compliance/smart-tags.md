---
title: Slimme tags instellen in Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: Met slimme tags kunt u de mogelijkheden voor machine learning toepassen wanneer u inhoud in een Advanced eDiscovery bekijkt. Gebruik slimme taggroepen om de resultaten weer te geven van machine-learningdetectiemodellen, zoals het privilegemodel voor advocatenclient.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "52161441"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="87b50-104">Slimme tags instellen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="87b50-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="87b50-105">Met machine learning (ML) in Advanced eDiscovery kunt u het beslissingsproces efficiënter maken bij het controleren van casedocumenten in een revisieset.</span><span class="sxs-lookup"><span data-stu-id="87b50-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="87b50-106">Slimme tags zijn een manier om de ML te brengen waar de beslissingen worden opgenomen: bij het taggen van documenten tijdens de controle.</span><span class="sxs-lookup"><span data-stu-id="87b50-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="87b50-107">Wanneer u een groep met slimme tags maakt, worden de beslissingen die het resultaat zijn van het ML-model dat u hebt gekoppeld aan de groep slimme tags, weergegeven in lijn met de tags in de taggroep.</span><span class="sxs-lookup"><span data-stu-id="87b50-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="87b50-108">Zo kunt u de ML resultaten in de regel bekijken wanneer u specifieke documenten bekijkt.</span><span class="sxs-lookup"><span data-stu-id="87b50-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="87b50-109">Een groep met slimme tags instellen</span><span class="sxs-lookup"><span data-stu-id="87b50-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="87b50-110">Klik in een revisieset op **Controleset beheren** en klik vervolgens **op Tags beheren.**</span><span class="sxs-lookup"><span data-stu-id="87b50-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="87b50-111">Klik **op Taggroep toevoegen** en selecteer vervolgens Groep Slimme tag **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="87b50-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="87b50-112">Selecteer het ML model dat u wilt koppelen aan de taggroep.</span><span class="sxs-lookup"><span data-stu-id="87b50-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="87b50-113">Hiermee worden een taggroep en *N-onderliggende* tags gemaakt, waarbij *N* het aantal mogelijke uitvoers van het model is.</span><span class="sxs-lookup"><span data-stu-id="87b50-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="87b50-114">Het detectiemodel voor [advocaten-clientrechten](attorney-privilege-detection.md) heeft bijvoorbeeld twee mogelijke uitvoer:</span><span class="sxs-lookup"><span data-stu-id="87b50-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="87b50-115">**Positief:** gebruik deze code om documenten te taggen die inhoud bevatten die is geprivilegieerd door een klant.</span><span class="sxs-lookup"><span data-stu-id="87b50-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="87b50-116">**Negatief:** gebruik deze code om documenten te taggen die geen bevoorrechte inhoud van de advocatenclient bevatten.</span><span class="sxs-lookup"><span data-stu-id="87b50-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="87b50-117">Als u dit model selecteert, wordt er een taggroep met twee onderliggende tags gemaakt (een onderliggende tag met de naam **Positief** en de andere met de naam **Negatief)** voor de revisieset.</span><span class="sxs-lookup"><span data-stu-id="87b50-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="87b50-118">In dit voorbeeld komt elke onderliggende tag overeen met een van de mogelijke uitvoer van het detectiemodel voor advocaten-clientvoorrechten.</span><span class="sxs-lookup"><span data-stu-id="87b50-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="87b50-119">Desgewenst kunt u de naam van de taggroep en de onderliggende tags wijzigen.</span><span class="sxs-lookup"><span data-stu-id="87b50-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="87b50-120">U kunt bijvoorbeeld de naam van de tag **Positief** wijzigen in **Bevoorrecht** en negatieve **tag** in Niet **geprivilegieerd.**</span><span class="sxs-lookup"><span data-stu-id="87b50-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="87b50-121">Slimme tags gebruiken</span><span class="sxs-lookup"><span data-stu-id="87b50-121">How to use smart tags</span></span>

<span data-ttu-id="87b50-122">Wanneer u een document controleert, worden de resultaten van het model weergegeven naast de juiste onderliggende tag.</span><span class="sxs-lookup"><span data-stu-id="87b50-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="87b50-123">Als u bijvoorbeeld een smart tag-groep hebt voor detectie van advocaten-clientprivilege's en u een document bekijkt dat mogelijk is geprivilegieerd, wordt de reden voor die conclusie weergegeven naast de juiste tag.</span><span class="sxs-lookup"><span data-stu-id="87b50-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="87b50-124">Het is belangrijk om te weten dat de tag niet automatisch wordt toegepast op het document.</span><span class="sxs-lookup"><span data-stu-id="87b50-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="87b50-125">De revisor neemt de beslissing over het taggen van het document.</span><span class="sxs-lookup"><span data-stu-id="87b50-125">The reviewer makes the decision about how to tag the document.</span></span>
