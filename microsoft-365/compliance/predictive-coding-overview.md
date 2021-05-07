---
title: Module voor voorspellende codering voor Advanced eDiscovery (voorbeeld)
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
description: De nieuwe module voor voorspellende codering in Advanced eDiscovery gebruikt machine learning om documenten te analyseren in een revisieset om te voorspellen welke documenten relevant zijn voor uw zaak of onderzoek.
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162476"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a><span data-ttu-id="b5698-103">Module voor voorspellende codering voor Advanced eDiscovery (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="b5698-103">Predictive coding module for Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="b5698-104">Met de nieuwe module voor voorspellende codering in Advanced eDiscovery kunt u een model maken en maken om prioriteit te geven aan het controleren van documenten, te beginnen met de meest relevante documenten.</span><span class="sxs-lookup"><span data-stu-id="b5698-104">Using the new predictive coding module in Advanced eDiscovery, you can create and build a model to prioritize review of documents starting with the most relevant documents.</span></span> <span data-ttu-id="b5698-105">Om aan de slag te gaan, kunt u een model maken, maar liefst 50 documenten labelen en vervolgens documenten filteren op modelvoorspellingsscores om relevante niet-relevante documenten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="b5698-105">To get started, you can create a model, label as few as 50 documents, and then filter documents by model prediction scores to review relevant non-relevant documents.</span></span>

<span data-ttu-id="b5698-106">Hier is een kort overzicht van de werkstroom:</span><span class="sxs-lookup"><span data-stu-id="b5698-106">Here’s a quick overview of the workflow:</span></span>

1. <span data-ttu-id="b5698-107">Open de module voorspellende codering in een revisieset.</span><span class="sxs-lookup"><span data-stu-id="b5698-107">Open the predictive coding module in a review set.</span></span>

   ![Klik in een revisie op de vervolgkeuzelijst Analyseren om naar de module Voorspellende codering te gaan](..\media\PredictiveCoding1.png)

2. <span data-ttu-id="b5698-109">Klik op **de pagina Voorspellende coderingsmodellen** op **Nieuw model** om een nieuw voorspellend coderingsmodel te maken.</span><span class="sxs-lookup"><span data-stu-id="b5698-109">On the **Predictive coding models** page, click **New model** to create a new predictive coding model.</span></span>

   ![Een nieuw model maken](..\media\PredictiveCoding2.png)

3. <span data-ttu-id="b5698-111">Label ten minste 50 documenten als **Relevant** of **Niet relevant.**</span><span class="sxs-lookup"><span data-stu-id="b5698-111">Label at least 50 documents as **Relevant** or **Not relevant**.</span></span> <span data-ttu-id="b5698-112">Deze labeling wordt gebruikt om het systeem te trainen.</span><span class="sxs-lookup"><span data-stu-id="b5698-112">This labeling is used to train the system.</span></span>

   ![Documenten labelen als relevant of niet relevant voor het trainen van het systeem](..\media\PredictiveCoding3.png)

4. <span data-ttu-id="b5698-114">Pas het **filter Voorspellingsscore** voor uw model toe op de revisieset.</span><span class="sxs-lookup"><span data-stu-id="b5698-114">Apply the **Prediction score** filter for your model to the review set.</span></span> <span data-ttu-id="b5698-115">Ga als volgende te werk:</span><span class="sxs-lookup"><span data-stu-id="b5698-115">To do this:</span></span>

   1. <span data-ttu-id="b5698-116">Klik in de revisieset op **Filters.**</span><span class="sxs-lookup"><span data-stu-id="b5698-116">In the review set, click **Filters**.</span></span>
   2. <span data-ttu-id="b5698-117">Vouw op **de** flyoutpagina Filters de sectie **Analyse/ML** uit en schakel vervolgens Het selectievakje Voorspellingsscore in voor het model dat u wilt toepassen. </span><span class="sxs-lookup"><span data-stu-id="b5698-117">In the **Filters** flyout page, expand the **Analytics/ML** section and then select **Prediction score** checkbox for the model you want to apply.</span></span>
   3. <span data-ttu-id="b5698-118">Geef in **het filter Voorspellingsscore** een voorspellingsscore op.</span><span class="sxs-lookup"><span data-stu-id="b5698-118">In the **Prediction score** filter, specify a prediction score.</span></span> <span data-ttu-id="b5698-119">In het filter worden de documenten weergegeven in de revisieset die overeenkomen met de voorspellingsscore.</span><span class="sxs-lookup"><span data-stu-id="b5698-119">The filter will display the documents in the review set that match the prediction score.</span></span>

      ![Een voorspellingsscore opgeven om documenten te filteren](..\media\PredictiveCoding4.png)

5. <span data-ttu-id="b5698-121">Controleer de prestaties, status en stabiliteit van uw model.</span><span class="sxs-lookup"><span data-stu-id="b5698-121">Monitor the performance, status, and stability of your model.</span></span>

   ![De prestaties, status en stabiliteit van uw model controleren](..\media\PredictiveCoding5.png)
