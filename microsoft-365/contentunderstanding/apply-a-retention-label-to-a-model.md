---
title: Een Bewaar label toepassen op een document wat model
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: In dit artikel wordt uitgelegd hoe u een Bewaar label toepast op een document dat het model van een document begrijpt.
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294916"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="bf629-103">Een Bewaar label toepassen op een document wat model</span><span class="sxs-lookup"><span data-stu-id="bf629-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="bf629-104">U kunt eenvoudig een [Bewaar label](https://docs.microsoft.com/microsoft-365/compliance/retention) toepassen op een document met beinformatie over model in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="bf629-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="bf629-105">Met labels voor bewaarbeleid kunt u bewaarinstellingen toepassen op de documenten die uw document begrijpt.</span><span class="sxs-lookup"><span data-stu-id="bf629-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="bf629-106">U wilt bijvoorbeeld dat uw model alleen de documenten van de *verzekerings kennisgeving* die wordt geüpload naar de documentbibliotheek identificeert, maar u kunt ook een Bewaar code voor een *bedrijf* toepassen, zodat deze documenten niet kunnen worden verwijderd uit de documentbibliotheek voor de opgegeven tijdsperiode (bijvoorbeeld de volgende vijf maanden).</span><span class="sxs-lookup"><span data-stu-id="bf629-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="bf629-107">U kunt een al bestaand Bewaar label toepassen op uw document met behulp van de modelinstellingen op de startpagina van uw model.</span><span class="sxs-lookup"><span data-stu-id="bf629-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="bf629-108">Voor Bewaar etiketten die u kunt gebruiken om uw inhoud toe te passen, moeten ze worden [gemaakt en gepubliceerd in het nalevings centrum van Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="bf629-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="bf629-109">Een Bewaar label toevoegen aan een document wat is het model</span><span class="sxs-lookup"><span data-stu-id="bf629-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="bf629-110">Selecteer op de startpagina van model de optie **modelinstellingen**.</span><span class="sxs-lookup"><span data-stu-id="bf629-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="bf629-111">Selecteer in de sectie **model instellingen**in de sectie **beveiliging en compliance** het menu **Bewaar label** om een lijst weer te geven van de Bewaar etiketten die beschikbaar zijn om te worden toegepast op het model.</span><span class="sxs-lookup"><span data-stu-id="bf629-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="bf629-112">![Menu Bewaar label](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="bf629-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="bf629-113">Selecteer het Bewaar label dat u wilt toepassen op het model en selecteer vervolgens **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="bf629-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="bf629-114">Na het toepassen van het Bewaar etiket op uw model, kunt u dit toepassen op een van de volgende dingen:</span><span class="sxs-lookup"><span data-stu-id="bf629-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="bf629-115">Nieuwe documentbibliotheek</span><span class="sxs-lookup"><span data-stu-id="bf629-115">New document library</span></span>
- <span data-ttu-id="bf629-116">Document bibliotheek waarmee het model al wordt toegepast</span><span class="sxs-lookup"><span data-stu-id="bf629-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="bf629-117">Het label voor bewaarbeleid toepassen op een documentbibliotheek waarmee het model al wordt toegepast</span><span class="sxs-lookup"><span data-stu-id="bf629-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="bf629-118">Als het document al is toegepast op een documentbibliotheek, kunt u het volgende doen om uw Bewaar etiket-update te synchroniseren zodat u deze op de documentbibliotheek kunt toepassen:</span><span class="sxs-lookup"><span data-stu-id="bf629-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="bf629-119">Selecteer op de startpagina van uw model in de sectie **bibliotheken met dit model** de documentbibliotheek waarop u de update voor het Bewaar label wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="bf629-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="bf629-120">Selecteer **synchroniseren**.</span><span class="sxs-lookup"><span data-stu-id="bf629-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="bf629-121">![Model synchroniseren](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="bf629-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="bf629-122">Nadat u de update hebt geïnstalleerd en de update hebt gesynchroniseerd met uw model, kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="bf629-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="bf629-123">Klik in het inhouds centrum, in de sectie **bibliotheken met dit model** , op de bibliotheek waarop uw bijgewerkte model is toegepast.</span><span class="sxs-lookup"><span data-stu-id="bf629-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="bf629-124">Selecteer in de weergave Documentbibliotheek het informatiepictogram om de modeleigenschappen te controleren.</span><span class="sxs-lookup"><span data-stu-id="bf629-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="bf629-125">Selecteer het bijgewerkte model in de lijst **actieve modellen** .</span><span class="sxs-lookup"><span data-stu-id="bf629-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="bf629-126">In het gedeelte **Bewaar label** ziet u de naam van het toegepaste Bewaar etiket.</span><span class="sxs-lookup"><span data-stu-id="bf629-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="bf629-127">Op de paginaweergave van uw model in de documentbibliotheek wordt een nieuwe **Bewaar label** kolom weergegeven.</span><span class="sxs-lookup"><span data-stu-id="bf629-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="bf629-128">Aangezien bestanden worden geclassificeerd op basis van het inhoudstype van de modelsite en deze weergeven in de bibliotheek weergave, wordt in de kolom Bewaar etiket ook de naam van het Bewaar label weergegeven dat op het model is toegepast.</span><span class="sxs-lookup"><span data-stu-id="bf629-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="bf629-129">Alle *verzekerings kennisgevingen* die uw model identificeert, zien er *ook het* bedrijfsbewaar label voor, zodat ze gedurende vijf maanden niet uit de documentbibliotheek kunnen worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="bf629-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="bf629-130">Als er wordt gevraagd of u het bestand uit de documentbibliotheek wilt verwijderen, wordt er een foutbericht weergegeven met de melding dat dit niet is toegestaan vanwege het toegepaste Bewaar etiket.</span><span class="sxs-lookup"><span data-stu-id="bf629-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf629-131">Zie ook</span><span class="sxs-lookup"><span data-stu-id="bf629-131">See Also</span></span>
[<span data-ttu-id="bf629-132">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="bf629-132">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="bf629-133">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="bf629-133">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="bf629-134">Overzicht van document</span><span class="sxs-lookup"><span data-stu-id="bf629-134">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="bf629-135">Een formulier verwerkings model maken</span><span class="sxs-lookup"><span data-stu-id="bf629-135">Create a form processing model</span></span>](create-a-form-processing-model.md)  
