---
title: Overzicht documentbegrip (voorbeeld)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Krijg een overzicht van het documentbegrip in Project Cortex.
ms.openlocfilehash: 13b0aa3742c6cf1c0c1123996c683d13c6577876
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537133"
---
# <a name="document-understanding-overview-preview"></a><span data-ttu-id="cfc2c-103">Overzicht documentbegrip (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="cfc2c-103">Document understanding overview (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="cfc2c-104">Project Cortex is momenteel in Preview.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-104">Project Cortex is currently in Preview.</span></span> <span data-ttu-id="cfc2c-105">[Lees meer over Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="cfc2c-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="cfc2c-106">Document understanding maakt gebruik van AI-modellen om de classificatie van bestanden en het verwijderen van informatie te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-106">Document understanding uses AI models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="cfc2c-107">Het werkt het beste met ongestructureerde documenten, zoals brieven of contracten.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-107">It works best with unstructured documents, like letters or contracts.</span></span> <span data-ttu-id="cfc2c-108">De documenten moeten tekst hebben die kan worden geïdentificeerd op basis van zinnen of patronen.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-108">The documents should have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="cfc2c-109">De geïdentificeerde tekst kan zowel het type bestand aanwijzen (de classificatie ervan) als wat u wilt extraheren (de uittreksels).</span><span class="sxs-lookup"><span data-stu-id="cfc2c-109">The identified text can designate both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="cfc2c-110">Document understanding modellen worden gemaakt en beheerd in een type SharePoint-site genaamd een inhoudscentrum.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-110">Document understanding models are created and managed in a type of SharePoint site called a content center.</span></span> <span data-ttu-id="cfc2c-111">Wanneer het model wordt toegepast op een SharePoint-documentbibliotheek, is het gekoppeld aan een inhoudstype met kolommen om de uitgepakte informatie op te slaan.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-111">When applied to a SharePoint document library, the model is associated with a content type which has columns to store the information extracted.</span></span> <span data-ttu-id="cfc2c-112">Het inhoudstype dat u maakt, wordt opgeslagen in de galerie met SharePoint-inhoudstype.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-112">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="cfc2c-113">U er ook voor kiezen om bestaande inhoudstypen te gebruiken om hun schema te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-113">You can also choose to use existing content types in order to use their schema.</span></span>

<span data-ttu-id="cfc2c-114">U *classificaties* en *uittreksels* toevoegen aan de modellen voor het begrijpen van documenten om het volgende te doen:</span><span class="sxs-lookup"><span data-stu-id="cfc2c-114">You can add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="cfc2c-115">Classificaties worden gebruikt om documenten te identificeren en te classificeren die naar de documentbibliotheek zijn geüpload.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="cfc2c-116">Een classificatie kan bijvoorbeeld worden 'getraind' om alle *contractverlengingsdocumenten* te identificeren die naar de bibliotheek zijn geüpload.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="cfc2c-117">Het inhoudstype contractverlenging wordt door u gedefinieerd wanneer u uw classificatie maakt.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="cfc2c-118">Extractors halen informatie uit deze documenten.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="cfc2c-119">Voor alle contractverlengingsdocumenten die in uw documentbibliotheek zijn geïdentificeerd, worden kolommen bijvoorbeeld weergegeven in uw weergave met de *begindatum* van de service en *de client* voor elk document voor contractverlenging.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-119">For example, for all contract renewal documents that are identified in your document library, columns will display in your view that will also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="cfc2c-120">U gebruikt voorbeeldbestanden om uw classificaties en extractors in uw model te trainen en te testen.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-120">You use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="cfc2c-121">Voorbeeldbestanden geven uw modelvoorbeelden van waar u op moet letten wanneer u gegevens uit bestanden probeert te identificeren en te extraheren.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="cfc2c-122">U traint bijvoorbeeld uw classificeerders en uitsinoordgers voor contractverlenging met voorbeelden van contractverlengingsdocumenten waarmee uw bedrijf werkt.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="cfc2c-123">U ook voorbeeldbestanden gebruiken om de effectiviteit van uw model te testen.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="cfc2c-124">Nadat u uw model hebt gepubliceerd, gebruikt u het inhoudscentrum om het toe te passen op elke SharePoint-documentbibliotheek waar u toegang toe hebt.</span><span class="sxs-lookup"><span data-stu-id="cfc2c-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="cfc2c-125">Zie ook</span><span class="sxs-lookup"><span data-stu-id="cfc2c-125">See Also</span></span>
[<span data-ttu-id="cfc2c-126">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="cfc2c-126">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="cfc2c-127">Een afzuiger maken</span><span class="sxs-lookup"><span data-stu-id="cfc2c-127">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="cfc2c-128">[Een inhoudscentrum maken](create-a-content-center.md) 
 [Een formulierverwerkingsmodel maken](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="cfc2c-128">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="cfc2c-129">[Een model toepassen](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="cfc2c-129">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="cfc2c-130">Verschil tussen een documentbegrip en een formulierverwerkingsmodel</span><span class="sxs-lookup"><span data-stu-id="cfc2c-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="cfc2c-131">Overzicht van formulierverwerking</span><span class="sxs-lookup"><span data-stu-id="cfc2c-131">Form processing overview</span></span>](form-processing-overview.md)




