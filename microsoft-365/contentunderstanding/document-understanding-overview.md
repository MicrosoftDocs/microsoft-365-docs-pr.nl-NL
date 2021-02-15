---
title: Overzicht van documentbegrip
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Bekijk een overzicht van documentbegrip in Microsoft SharePoint Syntex.
ms.openlocfilehash: d2bf581468eeee008d09a242876bed5ad07ae01f
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242408"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="fe206-103">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="fe206-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="fe206-104">Bij documentbegrip wordt gebruikgemaakt van modellen voor kunstmatige intelligentie (AI) om de classificatie van bestanden en extractie van informatie te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="fe206-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="fe206-105">Dit werkt het beste met ongestructureerde documenten zoals brieven of contracten.</span><span class="sxs-lookup"><span data-stu-id="fe206-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="fe206-106">Deze documenten moeten tekst bevatten die kan worden geïdentificeerd op basis van frasen of patronen.</span><span class="sxs-lookup"><span data-stu-id="fe206-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="fe206-107">De geïdentificeerde tekst duidt aan wat het bestandstype is (de classificatie) en wat u eruit wilt halen (de extractoren).</span><span class="sxs-lookup"><span data-stu-id="fe206-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="fe206-108">Zie [Ingebruikname van SharePoint Syntex: introductiehandleiding](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) voor meer informatie over scenariovoorbeelden voor documentbegrip.</span><span class="sxs-lookup"><span data-stu-id="fe206-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="fe206-109">Documentbegripmodellen worden gemaakt en beheerd in een type SharePoint-site, genaamd een *inhoudscentrum*.</span><span class="sxs-lookup"><span data-stu-id="fe206-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="fe206-110">Wanneer het model wordt toegepast op een SharePoint-documentbibliotheek, wordt het gekoppeld aan een inhoudstype dat kolommen bevat waarin de geëxtraheerde informatie wordt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="fe206-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="fe206-111">De inhoud die u maakt, wordt opgeslagen in de SharePoint-inhoudstypegalerie.</span><span class="sxs-lookup"><span data-stu-id="fe206-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="fe206-112">U kunt er ook voor kiezen om het schema van bestaande inhoudstypen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="fe206-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="fe206-113">Alleen-lezen of verzegelde inhoudstypen kunnen niet bijgewerkt worden, dus kunnen ze niet worden gebruikt in een model.</span><span class="sxs-lookup"><span data-stu-id="fe206-113">Read-only or sealed content types cannot be updated, so they cannot be used in a model.</span></span>

<span data-ttu-id="fe206-114">U kunt *classificaties* en *extractoren* toevoegen aan uw documentbegripmodellen om het volgende te doen:</span><span class="sxs-lookup"><span data-stu-id="fe206-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="fe206-115">Classificaties worden gebruikt om documenten die worden geüpload naar de documentbibliotheek te identificeren en classificeren.</span><span class="sxs-lookup"><span data-stu-id="fe206-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="fe206-116">Een classificatie kan bijvoorbeeld worden ‘getraind’ om alle documenten met *contractverlengingen* te identificeren die naar de bibliotheek worden geüpload.</span><span class="sxs-lookup"><span data-stu-id="fe206-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="fe206-117">Het inhoudstype contractverlenging wordt door u gedefinieerd wanneer u de classificatie maakt.</span><span class="sxs-lookup"><span data-stu-id="fe206-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="fe206-118">Extractoren halen informatie uit deze documenten.</span><span class="sxs-lookup"><span data-stu-id="fe206-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="fe206-119">Bijvoorbeeld: voor alle contractverlengingsdocumenten die in uw documentbibliotheek zijn geïdentificeerd, worden in uw weergave kolommen getoond met de *Servicestartdatum* en *Klant* voor elk contractverlengingsdocument.</span><span class="sxs-lookup"><span data-stu-id="fe206-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="fe206-120">U kunt voorbeeldbestanden gebruiken om de classificaties en extractoren in uw model te trainen en te testen.</span><span class="sxs-lookup"><span data-stu-id="fe206-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="fe206-121">Voorbeeldbestanden voorzien uw model van voorbeelden van waar ze naar moeten zoeken bij het identificeren en extraheren van gegevens uit bestanden.</span><span class="sxs-lookup"><span data-stu-id="fe206-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="fe206-122">U kunt bijvoorbeeld uw contractverlengingsclassificaties en -extractoren trainen met voorbeelden van contractverlengingsdocumenten waar uw bedrijf mee werkt.</span><span class="sxs-lookup"><span data-stu-id="fe206-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="fe206-123">U kunt voorbeeldbestanden ook gebruiken om de effectiviteit van uw model te testen.</span><span class="sxs-lookup"><span data-stu-id="fe206-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="fe206-124">Nadat u uw model hebt gepubliceerd, gebruikt u het inhoudscentrum om het toe te passen op een SharePoint-documentbibliotheek waartoe u toegang hebt.</span><span class="sxs-lookup"><span data-stu-id="fe206-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

### <a name="file-limitations"></a><span data-ttu-id="fe206-125">Bestandbeperkingen</span><span class="sxs-lookup"><span data-stu-id="fe206-125">File limitations</span></span>

<span data-ttu-id="fe206-126">Documentbegripmodellen gebruiken Optical Character Recognition- (OCR) technologie om pdf-bestanden, afbeeldingen en tiff-bestanden te scannen wanneer je een model traint met voorbeeldbestanden en wanneer je het model uitvoert op bestanden in een documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="fe206-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="fe206-127">Let op de volgende verschillen in Microsoft Office tekstgebaseerde bestanden en OCR-gescande bestanden (pdf, afbeelding of tiff):</span><span class="sxs-lookup"><span data-stu-id="fe206-127">Note the following differences in regards to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="fe206-128">Office-bestanden: We kappen af op 64k karakters (in training en wanneer uitgevoerd op bestanden in een documentbibliotheek).</span><span class="sxs-lookup"><span data-stu-id="fe206-128">Office files: We truncate at 64K characters (in training and when run against files in a document library).</span></span>
- <span data-ttu-id="fe206-129">OCR-gescande bestanden: Er is een limiet van 20 pagina's.</span><span class="sxs-lookup"><span data-stu-id="fe206-129">OCR-scanned files: There is a 20 page limit.</span></span>  

#### <a name="supported-file-types"></a><span data-ttu-id="fe206-130">Ondersteunde bestandstypen</span><span class="sxs-lookup"><span data-stu-id="fe206-130">Supported file types</span></span>

<span data-ttu-id="fe206-131">Documentbegripmodellen ondersteunen de volgende typen:</span><span class="sxs-lookup"><span data-stu-id="fe206-131">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="fe206-132">doc</span><span class="sxs-lookup"><span data-stu-id="fe206-132">doc</span></span>
- <span data-ttu-id="fe206-133">docx</span><span class="sxs-lookup"><span data-stu-id="fe206-133">docx</span></span>
- <span data-ttu-id="fe206-134">eml</span><span class="sxs-lookup"><span data-stu-id="fe206-134">eml</span></span>
- <span data-ttu-id="fe206-135">heic</span><span class="sxs-lookup"><span data-stu-id="fe206-135">heic</span></span>
- <span data-ttu-id="fe206-136">heif</span><span class="sxs-lookup"><span data-stu-id="fe206-136">heif</span></span>
- <span data-ttu-id="fe206-137">htm</span><span class="sxs-lookup"><span data-stu-id="fe206-137">htm</span></span>
- <span data-ttu-id="fe206-138">html</span><span class="sxs-lookup"><span data-stu-id="fe206-138">html</span></span>
- <span data-ttu-id="fe206-139">jpeg</span><span class="sxs-lookup"><span data-stu-id="fe206-139">jpeg</span></span>
- <span data-ttu-id="fe206-140">jpg</span><span class="sxs-lookup"><span data-stu-id="fe206-140">jpg</span></span>
- <span data-ttu-id="fe206-141">markdown</span><span class="sxs-lookup"><span data-stu-id="fe206-141">markdown</span></span>
- <span data-ttu-id="fe206-142">md</span><span class="sxs-lookup"><span data-stu-id="fe206-142">md</span></span>
- <span data-ttu-id="fe206-143">msg</span><span class="sxs-lookup"><span data-stu-id="fe206-143">msg</span></span>
- <span data-ttu-id="fe206-144">pdf</span><span class="sxs-lookup"><span data-stu-id="fe206-144">pdf</span></span>
- <span data-ttu-id="fe206-145">png</span><span class="sxs-lookup"><span data-stu-id="fe206-145">png</span></span>
- <span data-ttu-id="fe206-146">ppt</span><span class="sxs-lookup"><span data-stu-id="fe206-146">ppt</span></span>
- <span data-ttu-id="fe206-147">pptx</span><span class="sxs-lookup"><span data-stu-id="fe206-147">pptx</span></span>
- <span data-ttu-id="fe206-148">rtf</span><span class="sxs-lookup"><span data-stu-id="fe206-148">rtf</span></span>
- <span data-ttu-id="fe206-149">tif</span><span class="sxs-lookup"><span data-stu-id="fe206-149">tif</span></span>
- <span data-ttu-id="fe206-150">tiff</span><span class="sxs-lookup"><span data-stu-id="fe206-150">tiff</span></span>
- <span data-ttu-id="fe206-151">txt</span><span class="sxs-lookup"><span data-stu-id="fe206-151">txt</span></span>
- <span data-ttu-id="fe206-152">xls</span><span class="sxs-lookup"><span data-stu-id="fe206-152">xls</span></span>
- <span data-ttu-id="fe206-153">xlsx</span><span class="sxs-lookup"><span data-stu-id="fe206-153">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="fe206-154">Zie ook</span><span class="sxs-lookup"><span data-stu-id="fe206-154">See Also</span></span>
[<span data-ttu-id="fe206-155">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="fe206-155">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="fe206-156">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="fe206-156">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="fe206-157">Een inhoudscentrum maken</span><span class="sxs-lookup"><span data-stu-id="fe206-157">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="fe206-158">Een formulierverwerkingsmodel maken</span><span class="sxs-lookup"><span data-stu-id="fe206-158">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="fe206-159">Een model toepassen</span><span class="sxs-lookup"><span data-stu-id="fe206-159">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="fe206-160">Het verschil tussen een documentbegripmodel en een formulierverwerkingsmodel</span><span class="sxs-lookup"><span data-stu-id="fe206-160">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="fe206-161">Overzicht formulierverwerking</span><span class="sxs-lookup"><span data-stu-id="fe206-161">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="fe206-162">SharePoint Syntex toegankheidsmodus</span><span class="sxs-lookup"><span data-stu-id="fe206-162">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)
