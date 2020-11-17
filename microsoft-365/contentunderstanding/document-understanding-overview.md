---
title: Overzicht van documentbegrip
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Bekijk een overzicht van documentbegrip in Microsoft SharePoint Syntex.
ms.openlocfilehash: b26ed9a9ed9b8d1f332ccf14377660e634349b3d
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087365"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="d65f7-103">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="d65f7-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="d65f7-104">Bij documentbegrip wordt gebruikgemaakt van modellen voor kunstmatige intelligentie (AI) om de classificatie van bestanden en extractie van informatie te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="d65f7-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="d65f7-105">Dit werkt het beste met ongestructureerde documenten zoals brieven of contracten.</span><span class="sxs-lookup"><span data-stu-id="d65f7-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="d65f7-106">Deze documenten moeten tekst bevatten die kan worden geïdentificeerd op basis van frasen of patronen.</span><span class="sxs-lookup"><span data-stu-id="d65f7-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="d65f7-107">De geïdentificeerde tekst duidt aan wat het bestandstype is (de classificatie) en wat u eruit wilt halen (de extractoren).</span><span class="sxs-lookup"><span data-stu-id="d65f7-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="d65f7-108">Zie [Ingebruikname van SharePoint Syntex: introductiehandleiding](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) voor meer informatie over scenariovoorbeelden voor documentbegrip.</span><span class="sxs-lookup"><span data-stu-id="d65f7-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="d65f7-109">Documentbegripmodellen worden gemaakt en beheerd in een type SharePoint-site, genaamd een *inhoudscentrum*.</span><span class="sxs-lookup"><span data-stu-id="d65f7-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="d65f7-110">Wanneer het model wordt toegepast op een SharePoint-documentbibliotheek, wordt het gekoppeld aan een inhoudstype dat kolommen bevat waarin de geëxtraheerde informatie wordt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="d65f7-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="d65f7-111">De inhoud die u maakt, wordt opgeslagen in de SharePoint-inhoudstypegalerie.</span><span class="sxs-lookup"><span data-stu-id="d65f7-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="d65f7-112">U kunt er ook voor kiezen om het schema van bestaande inhoudstypen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d65f7-112">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="d65f7-113">U kunt *classificaties* en *extractoren* toevoegen aan uw documentbegripmodellen om het volgende te doen:</span><span class="sxs-lookup"><span data-stu-id="d65f7-113">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="d65f7-114">Classificaties worden gebruikt om documenten die worden geüpload naar de documentbibliotheek te identificeren en classificeren.</span><span class="sxs-lookup"><span data-stu-id="d65f7-114">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="d65f7-115">Een classificatie kan bijvoorbeeld worden ‘getraind’ om alle documenten met *contractverlengingen* te identificeren die naar de bibliotheek worden geüpload.</span><span class="sxs-lookup"><span data-stu-id="d65f7-115">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="d65f7-116">Het inhoudstype contractverlenging wordt door u gedefinieerd wanneer u de classificatie maakt.</span><span class="sxs-lookup"><span data-stu-id="d65f7-116">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="d65f7-117">Extractoren halen informatie uit deze documenten.</span><span class="sxs-lookup"><span data-stu-id="d65f7-117">Extractors pull information from these documents.</span></span> <span data-ttu-id="d65f7-118">Bijvoorbeeld: voor alle contractverlengingsdocumenten die in uw documentbibliotheek zijn geïdentificeerd, worden in uw weergave kolommen getoond met de *Servicestartdatum* en *Klant* voor elk contractverlengingsdocument.</span><span class="sxs-lookup"><span data-stu-id="d65f7-118">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="d65f7-119">U kunt voorbeeldbestanden gebruiken om de classificaties en extractoren in uw model te trainen en te testen.</span><span class="sxs-lookup"><span data-stu-id="d65f7-119">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="d65f7-120">Voorbeeldbestanden voorzien uw model van voorbeelden van waar ze naar moeten zoeken bij het identificeren en extraheren van gegevens uit bestanden.</span><span class="sxs-lookup"><span data-stu-id="d65f7-120">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="d65f7-121">U kunt bijvoorbeeld uw contractverlengingsclassificaties en -extractoren trainen met voorbeelden van contractverlengingsdocumenten waar uw bedrijf mee werkt.</span><span class="sxs-lookup"><span data-stu-id="d65f7-121">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="d65f7-122">U kunt voorbeeldbestanden ook gebruiken om de effectiviteit van uw model te testen.</span><span class="sxs-lookup"><span data-stu-id="d65f7-122">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="d65f7-123">Nadat u uw model hebt gepubliceerd, gebruikt u het inhoudscentrum om het toe te passen op een SharePoint-documentbibliotheek waartoe u toegang hebt.</span><span class="sxs-lookup"><span data-stu-id="d65f7-123">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  



## <a name="see-also"></a><span data-ttu-id="d65f7-124">Zie ook</span><span class="sxs-lookup"><span data-stu-id="d65f7-124">See Also</span></span>
[<span data-ttu-id="d65f7-125">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="d65f7-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="d65f7-126">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="d65f7-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="d65f7-127">Een inhoudscentrum maken</span><span class="sxs-lookup"><span data-stu-id="d65f7-127">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="d65f7-128">Een formulierverwerkingsmodel maken</span><span class="sxs-lookup"><span data-stu-id="d65f7-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="d65f7-129">Een model toepassen</span><span class="sxs-lookup"><span data-stu-id="d65f7-129">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="d65f7-130">Het verschil tussen een documentbegripmodel en een formulierverwerkingsmodel</span><span class="sxs-lookup"><span data-stu-id="d65f7-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="d65f7-131">Overzicht formulierverwerking</span><span class="sxs-lookup"><span data-stu-id="d65f7-131">Form processing overview</span></span>](form-processing-overview.md)
