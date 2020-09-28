---
title: Overzicht van document
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: U krijgt een overzicht van het document wat u in Microsoft SharePoint Syntex.
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294758"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="52909-103">Overzicht van document</span><span class="sxs-lookup"><span data-stu-id="52909-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="52909-104">In dit document wordt gebruikgemaakt van een AI-model (kunstmatige intelligentie) om de indeling van bestanden en het extraheren van gegevens te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="52909-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="52909-105">Het werkt het beste met niet-gestructureerde documenten, zoals brieven of contracten.</span><span class="sxs-lookup"><span data-stu-id="52909-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="52909-106">Deze documenten moeten tekst bevatten die kunnen worden geïdentificeerd op basis van woordgroepen of patronen.</span><span class="sxs-lookup"><span data-stu-id="52909-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="52909-107">De aangewezen tekst geeft zowel het type bestand aan dat de naam is (de classificatie) en wat u wilt extraheren (de uitgepakte bestanden).</span><span class="sxs-lookup"><span data-stu-id="52909-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="52909-108">Document leren hoe modellen worden gemaakt en beheerd in een type SharePoint-site met de naam een *inhouds centrum*.</span><span class="sxs-lookup"><span data-stu-id="52909-108">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="52909-109">Wanneer dit wordt toegepast op een SharePoint-documentbibliotheek, is het model gekoppeld aan een inhoudstype om de gegevens op te slaan die worden geëxtraheerd.</span><span class="sxs-lookup"><span data-stu-id="52909-109">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="52909-110">Het inhoudstype dat u maakt, wordt opgeslagen in de SharePoint-galerie met inhoudstypen.</span><span class="sxs-lookup"><span data-stu-id="52909-110">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="52909-111">U kunt er ook voor kiezen om bestaande inhoudstypen te gebruiken om hun schema te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="52909-111">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="52909-112">Voeg *classificaties* en *extracten* aan uw document toe om te begrijpen hoe modellen u het volgende kunt doen:</span><span class="sxs-lookup"><span data-stu-id="52909-112">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="52909-113">Classificaties worden gebruikt voor het identificeren en classificeren van documenten die worden geüpload naar de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="52909-113">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="52909-114">Een classificatie kan bijvoorbeeld ' opgeleid ' worden *om alle documenten* te identificeren die worden geüpload naar de bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="52909-114">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="52909-115">Het inhoudstype voor het verlengen van het contract wordt door u gedefinieerd wanneer u de classificatie maakt.</span><span class="sxs-lookup"><span data-stu-id="52909-115">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="52909-116">Extracten trekken informatie uit deze documenten.</span><span class="sxs-lookup"><span data-stu-id="52909-116">Extractors pull information from these documents.</span></span> <span data-ttu-id="52909-117">Voor alle documenten die zijn gekoppeld aan de documentbibliotheek, worden de kolommen weergegeven in uw weergave, waarmee ook de *begindatum* en-  *cliënt* van de service worden weergegeven voor elk document voor het verlengen van de contracten.</span><span class="sxs-lookup"><span data-stu-id="52909-117">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="52909-118">U kunt voorbeeldbestanden gebruiken om classificaties en extracten in uw model te trainen en testen.</span><span class="sxs-lookup"><span data-stu-id="52909-118">You can use sample files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="52909-119">Voorbeeldbestanden hier vindt u voorbeelden van de modellen waarnaar u moet kijken wanneer u gegevens uit bestanden probeert te identificeren en uit te pakken.</span><span class="sxs-lookup"><span data-stu-id="52909-119">Sample files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="52909-120">U kunt bijvoorbeeld het verlengen van de classificaties en extracties van een contract trainen met voorbeelden van documenten voor het verlengen van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="52909-120">For example, you would train your contract renewal classifiers and extractors with samples of contract renewal documents your company works with.</span></span> <span data-ttu-id="52909-121">U kunt ook voorbeeldbestanden gebruiken om de effectiviteit van uw model te testen.</span><span class="sxs-lookup"><span data-stu-id="52909-121">You can also use sample files to test the effectiveness of your model.</span></span>

<span data-ttu-id="52909-122">Nadat u uw model hebt gepubliceerd, kunt u het inhouds centrum gebruiken om het toe te passen op een SharePoint-documentbibliotheek waartoe u toegang hebt.</span><span class="sxs-lookup"><span data-stu-id="52909-122">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="52909-123">Zie ook</span><span class="sxs-lookup"><span data-stu-id="52909-123">See Also</span></span>
[<span data-ttu-id="52909-124">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="52909-124">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="52909-125">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="52909-125">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="52909-126">[Een inhouds centrum maken](create-a-content-center.md) 
 [Een formulier verwerkings model maken](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="52909-126">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="52909-127">[Een model toepassen](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="52909-127">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="52909-128">Het verschil tussen een document en een formulier verwerkings model</span><span class="sxs-lookup"><span data-stu-id="52909-128">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="52909-129">Overzicht van formulierverwerking</span><span class="sxs-lookup"><span data-stu-id="52909-129">Form processing overview</span></span>](form-processing-overview.md)
