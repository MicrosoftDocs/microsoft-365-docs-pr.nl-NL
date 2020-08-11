---
title: Overzicht van document (preview)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: U krijgt een overzicht van het document wat u in Project cortex.
ms.openlocfilehash: bdebc8a8726a7b9a77eb9a1095f83e937cf36cb1
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612712"
---
# <a name="document-understanding-overview-preview"></a><span data-ttu-id="9ef9e-103">Overzicht van document (preview)</span><span class="sxs-lookup"><span data-stu-id="9ef9e-103">Document understanding overview (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="9ef9e-104">Project cortex is momenteel beschikbaar in de preview-versie.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-104">Project Cortex is currently in Preview.</span></span> <span data-ttu-id="9ef9e-105">[Lees meer over project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="9ef9e-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="9ef9e-106">Document Understanding maakt gebruik van AI-modellen om de indeling van bestanden en het extraheren van gegevens te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-106">Document understanding uses AI models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="9ef9e-107">Het werkt het beste met niet-gestructureerde documenten, zoals brieven of contracten.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-107">It works best with unstructured documents, like letters or contracts.</span></span> <span data-ttu-id="9ef9e-108">De documenten moeten tekst bevatten die kunnen worden geïdentificeerd op basis van woordgroepen of patronen.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-108">The documents should have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="9ef9e-109">Met de geïdentificeerde tekst kunt u zowel het type bestand als het bestand (de classificatie) opgeven en wat u wilt extraheren (de uitgepakte bestanden).</span><span class="sxs-lookup"><span data-stu-id="9ef9e-109">The identified text can designate both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="9ef9e-110">Document leren hoe modellen worden gemaakt en beheerd in een type SharePoint-site met de naam een inhouds centrum.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-110">Document understanding models are created and managed in a type of SharePoint site called a content center.</span></span> <span data-ttu-id="9ef9e-111">Wanneer dit wordt toegepast op een SharePoint-documentbibliotheek, is het model gekoppeld aan een inhoudstype waarvan de kolom kolommen bevat om de verzamelde gegevens op te slaan.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-111">When applied to a SharePoint document library, the model is associated with a content type which has columns to store the information extracted.</span></span> <span data-ttu-id="9ef9e-112">Het inhoudstype dat u maakt, wordt opgeslagen in de SharePoint-galerie met inhoudstypen.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-112">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="9ef9e-113">U kunt er ook voor kiezen om bestaande inhoudstypen te gebruiken om hun schema te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-113">You can also choose to use existing content types in order to use their schema.</span></span>

<span data-ttu-id="9ef9e-114">U kunt *classificaties* en *extracten* aan uw document toevoegen om te begrijpen hoe modellen u het volgende kunt doen:</span><span class="sxs-lookup"><span data-stu-id="9ef9e-114">You can add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="9ef9e-115">Classificaties worden gebruikt voor het identificeren en classificeren van documenten die worden geüpload naar de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="9ef9e-116">Een classificatie kan bijvoorbeeld ' opgeleid ' worden *om alle documenten* te identificeren die worden geüpload naar de bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="9ef9e-117">Het inhoudstype voor het verlengen van het contract wordt door u gedefinieerd wanneer u de classificatie maakt.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="9ef9e-118">Extracten trekken informatie uit deze documenten.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="9ef9e-119">Als u bijvoorbeeld alle documenten in de documentbibliotheek wilt verlengen, worden kolommen weergegeven in uw weergave, waarin de *begindatum* en- *client* van de service ook voor elk document met het verlengen van de service wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-119">For example, for all contract renewal documents that are identified in your document library, columns will display in your view that will also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="9ef9e-120">U gebruikt voorbeeldbestanden om classificaties en extracten in uw model te trainen en testen.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-120">You use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="9ef9e-121">Voorbeeldbestanden hier vindt u voorbeelden van de modellen waarnaar u moet kijken wanneer u gegevens uit bestanden probeert te identificeren en uit te pakken.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="9ef9e-122">U kunt bijvoorbeeld het verlengen van de classificaties en extracties van een contract trainen met voorbeelden van documenten voor het verlengen van de contracten waarmee uw bedrijf werkt.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="9ef9e-123">U kunt ook voorbeeldbestanden gebruiken om de effectiviteit van uw model te testen.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="9ef9e-124">Nadat u uw model hebt gepubliceerd, kunt u het inhouds centrum gebruiken om het toe te passen op een SharePoint-documentbibliotheek waartoe u toegang hebt.</span><span class="sxs-lookup"><span data-stu-id="9ef9e-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="9ef9e-125">Zie ook</span><span class="sxs-lookup"><span data-stu-id="9ef9e-125">See Also</span></span>
[<span data-ttu-id="9ef9e-126">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="9ef9e-126">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="9ef9e-127">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="9ef9e-127">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="9ef9e-128">[Een inhouds centrum maken](create-a-content-center.md) 
 [Een formulier verwerkings model maken](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="9ef9e-128">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="9ef9e-129">[Een model toepassen](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="9ef9e-129">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="9ef9e-130">Het verschil tussen een document en een formulier verwerkings model</span><span class="sxs-lookup"><span data-stu-id="9ef9e-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="9ef9e-131">Overzicht van formulierverwerking</span><span class="sxs-lookup"><span data-stu-id="9ef9e-131">Form processing overview</span></span>](form-processing-overview.md)




