---
title: Overzicht van documentbegrip
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Bekijk een overzicht van documentbegrip in Microsoft SharePoint Syntex.
ms.openlocfilehash: 7e5818a929fa0f4554a7ee4ece460b4fe0d691aa
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683821"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="5bac2-103">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="5bac2-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="5bac2-104">Bij documentbegrip wordt gebruikgemaakt van modellen voor kunstmatige intelligentie (AI) om de classificatie van bestanden en extractie van informatie te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="5bac2-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="5bac2-105">Dit werkt het beste met ongestructureerde documenten zoals brieven of contracten.</span><span class="sxs-lookup"><span data-stu-id="5bac2-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="5bac2-106">Deze documenten moeten tekst bevatten die kan worden geïdentificeerd op basis van frasen of patronen.</span><span class="sxs-lookup"><span data-stu-id="5bac2-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="5bac2-107">De geïdentificeerde tekst duidt aan wat het bestandstype is (de classificatie) en wat u eruit wilt halen (de extractoren).</span><span class="sxs-lookup"><span data-stu-id="5bac2-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="5bac2-108">Zie [Ingebruikname van SharePoint Syntex: introductiehandleiding](./adoption-getstarted.md) voor meer informatie over scenariovoorbeelden voor documentbegrip.</span><span class="sxs-lookup"><span data-stu-id="5bac2-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="5bac2-109">Documentbegripmodellen worden gemaakt en beheerd in een type SharePoint-site, genaamd een *inhoudscentrum*.</span><span class="sxs-lookup"><span data-stu-id="5bac2-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="5bac2-110">Wanneer het model wordt toegepast op een SharePoint-documentbibliotheek, wordt het gekoppeld aan een inhoudstype dat kolommen bevat waarin de geëxtraheerde informatie wordt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="5bac2-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="5bac2-111">De inhoud die u maakt, wordt opgeslagen in de SharePoint-inhoudstypegalerie.</span><span class="sxs-lookup"><span data-stu-id="5bac2-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="5bac2-112">U kunt er ook voor kiezen om het schema van bestaande inhoudstypen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5bac2-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="5bac2-113">Alleen-lezen of verzegelde inhoudstypen kunnen niet bijgewerkt worden, dus kunnen ze niet worden gebruikt in een model.</span><span class="sxs-lookup"><span data-stu-id="5bac2-113">Read-only or sealed content types cannot be updated, so they can't be used in a model.</span></span>

<span data-ttu-id="5bac2-114">U kunt *classificaties* en *extractoren* toevoegen aan uw documentbegripmodellen om het volgende te doen:</span><span class="sxs-lookup"><span data-stu-id="5bac2-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="5bac2-115">Classificaties worden gebruikt om documenten die worden geüpload naar de documentbibliotheek te identificeren en classificeren.</span><span class="sxs-lookup"><span data-stu-id="5bac2-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="5bac2-116">Een classificatie kan bijvoorbeeld worden ‘getraind’ om alle documenten met *contractverlengingen* te identificeren die naar de bibliotheek worden geüpload.</span><span class="sxs-lookup"><span data-stu-id="5bac2-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="5bac2-117">Het inhoudstype contractverlenging wordt door u gedefinieerd wanneer u de classificatie maakt.</span><span class="sxs-lookup"><span data-stu-id="5bac2-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="5bac2-118">Extractoren halen informatie uit deze documenten.</span><span class="sxs-lookup"><span data-stu-id="5bac2-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="5bac2-119">Bijvoorbeeld: voor alle contractverlengingsdocumenten die in uw documentbibliotheek zijn geïdentificeerd, worden in uw weergave kolommen getoond met de *Servicestartdatum* en *Klant* voor elk contractverlengingsdocument.</span><span class="sxs-lookup"><span data-stu-id="5bac2-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="5bac2-120">U kunt voorbeeldbestanden gebruiken om de classificaties en extractoren in uw model te trainen en te testen.</span><span class="sxs-lookup"><span data-stu-id="5bac2-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="5bac2-121">Voorbeeldbestanden voorzien uw model van voorbeelden van waar ze naar moeten zoeken bij het identificeren en extraheren van gegevens uit bestanden.</span><span class="sxs-lookup"><span data-stu-id="5bac2-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="5bac2-122">U kunt bijvoorbeeld uw contractverlengingsclassificaties en -extractoren trainen met voorbeelden van contractverlengingsdocumenten waar uw bedrijf mee werkt.</span><span class="sxs-lookup"><span data-stu-id="5bac2-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="5bac2-123">U kunt voorbeeldbestanden ook gebruiken om de effectiviteit van uw model te testen.</span><span class="sxs-lookup"><span data-stu-id="5bac2-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="5bac2-124">Nadat u uw model hebt gepubliceerd, gebruikt u het inhoudscentrum om het toe te passen op een SharePoint-documentbibliotheek waartoe u toegang hebt.</span><span class="sxs-lookup"><span data-stu-id="5bac2-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="file-limitations"></a><span data-ttu-id="5bac2-125">Bestandbeperkingen</span><span class="sxs-lookup"><span data-stu-id="5bac2-125">File limitations</span></span>

<span data-ttu-id="5bac2-126">Documentbegripmodellen gebruiken Optical Character Recognition- (OCR) technologie om pdf-bestanden, afbeeldingen en tiff-bestanden te scannen wanneer je een model traint met voorbeeldbestanden en wanneer je het model uitvoert op bestanden in een documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="5bac2-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="5bac2-127">Let op de volgende verschillen in Microsoft Office tekstgebaseerde bestanden en OCR-gescande bestanden (pdf, afbeelding of tiff):</span><span class="sxs-lookup"><span data-stu-id="5bac2-127">Note the following differences with regard to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="5bac2-128">Office-bestanden: Afgekapt op 64000 karakters (in training en wanneer uitgevoerd op bestanden in een documentbibliotheek).</span><span class="sxs-lookup"><span data-stu-id="5bac2-128">Office files: Truncated at 64,000 characters (in training and when run against files in a document library).</span></span>

- <span data-ttu-id="5bac2-129">OCR-gescande bestanden: Er is een limiet van 20 pagina's.</span><span class="sxs-lookup"><span data-stu-id="5bac2-129">OCR-scanned files: There's a 20-page limit.</span></span>  

### <a name="requirements"></a><span data-ttu-id="5bac2-130">Vereisten</span><span class="sxs-lookup"><span data-stu-id="5bac2-130">Requirements</span></span>

<span data-ttu-id="5bac2-131">OCR verwerking werkt het beste met documenten die aan de volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="5bac2-131">OCR processing works best on documents that meet the following requirements:</span></span>

- <span data-ttu-id="5bac2-132">JPG, PNG of PDF-formaat (tekst of scan)</span><span class="sxs-lookup"><span data-stu-id="5bac2-132">JPG, PNG, or PDF format (text or scanned).</span></span> <span data-ttu-id="5bac2-133">PDF's met tekst zijn beter, omdat er geen fouten zijn met leestekenextractie en locatie.</span><span class="sxs-lookup"><span data-stu-id="5bac2-133">Text-embedded PDFs are better, because there won't be any errors in character extraction and location.</span></span>

- <span data-ttu-id="5bac2-134">Als u PDF's met een wachtwoord vergrendeld zijn moet u de vergrendeling verwijderen voordat u ze inlevert.</span><span class="sxs-lookup"><span data-stu-id="5bac2-134">If your PDFs are password-locked, you must remove the lock before submitting them.</span></span>

- <span data-ttu-id="5bac2-135">De gecombineerde bestandsgrootte van de documenten die gebruikt worden voor training per collectie mogen niet groter zijn dan 50 MB en PDF-documenten mogen niet meer dan 500 pagina's hebben.</span><span class="sxs-lookup"><span data-stu-id="5bac2-135">The combined file size of the documents used for training per collection must not exceed 50 MB, and PDF documents shouldn't have more than 500 pages.</span></span>

- <span data-ttu-id="5bac2-136">Voor afbeeldingen moeten de afmetingen tussen 50 x 50 en 10000 x 10000 pixels zijn.</span><span class="sxs-lookup"><span data-stu-id="5bac2-136">For images, dimensions must be between 50 × 50 and 10,000 × 10,000 pixels.</span></span>
   > [!NOTE]
   > <span data-ttu-id="5bac2-137">Afbeeldingen die erg breed zijn of aparte afmetingen hebben (bijvoorbeeld bouwtekeningen) kunnen afgekapt worden in het OCR-proces en minder nauwkeurig worden.</span><span class="sxs-lookup"><span data-stu-id="5bac2-137">Images that are very wide or have odd dimensions (for example, floor plans) might get truncated in the OCR process and lose accuracy.</span></span>
 
- <span data-ttu-id="5bac2-138">Afmetingen voor PDF-bestanden moeten maximaal 17 x 17 inches zijn, en overeen komen met juridische of A3 papierformaten of kleiner.</span><span class="sxs-lookup"><span data-stu-id="5bac2-138">For PDF files, dimensions must be at most 17 x 17 inches, corresponding to Legal or A3 paper sizes and smaller.</span></span>

- <span data-ttu-id="5bac2-139">Scans moeten afbeeldingen van hoge kwaliteit zijn wanneer gescand vanaf papieren documenten.</span><span class="sxs-lookup"><span data-stu-id="5bac2-139">If scanned from paper documents, scans should be high-quality images.</span></span>

- <span data-ttu-id="5bac2-140">Moeten gebruik maken van het Latijnse alfabet (Engelse karakters).</span><span class="sxs-lookup"><span data-stu-id="5bac2-140">Must use the Latin alphabet (English characters).</span></span>

> [!NOTE]
> <span data-ttu-id="5bac2-141">AI Builder ondersteunt momenteel de volgende types formuliergevens niet:</span><span class="sxs-lookup"><span data-stu-id="5bac2-141">AI Builder doesn't currently support the following types of form processing input data:</span></span><br><span data-ttu-id="5bac2-142">- Selectievakken of radioknoppen</span><span class="sxs-lookup"><span data-stu-id="5bac2-142">- Check boxes or radio buttons</span></span><br><span data-ttu-id="5bac2-143">- Handtekeningen </span><span class="sxs-lookup"><span data-stu-id="5bac2-143">- Signatures</span></span><br><span data-ttu-id="5bac2-144">- Herstelbare PDF's</span><span class="sxs-lookup"><span data-stu-id="5bac2-144">- Fillable PDFs</span></span>

### <a name="supported-file-types"></a><span data-ttu-id="5bac2-145">Ondersteunde bestandstypen</span><span class="sxs-lookup"><span data-stu-id="5bac2-145">Supported file types</span></span>

<span data-ttu-id="5bac2-146">Documentbegripmodellen ondersteunen de volgende typen:</span><span class="sxs-lookup"><span data-stu-id="5bac2-146">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="5bac2-147">doc</span><span class="sxs-lookup"><span data-stu-id="5bac2-147">doc</span></span>
- <span data-ttu-id="5bac2-148">docx</span><span class="sxs-lookup"><span data-stu-id="5bac2-148">docx</span></span>
- <span data-ttu-id="5bac2-149">eml</span><span class="sxs-lookup"><span data-stu-id="5bac2-149">eml</span></span>
- <span data-ttu-id="5bac2-150">heic</span><span class="sxs-lookup"><span data-stu-id="5bac2-150">heic</span></span>
- <span data-ttu-id="5bac2-151">heif</span><span class="sxs-lookup"><span data-stu-id="5bac2-151">heif</span></span>
- <span data-ttu-id="5bac2-152">htm</span><span class="sxs-lookup"><span data-stu-id="5bac2-152">htm</span></span>
- <span data-ttu-id="5bac2-153">html</span><span class="sxs-lookup"><span data-stu-id="5bac2-153">html</span></span>
- <span data-ttu-id="5bac2-154">jpeg</span><span class="sxs-lookup"><span data-stu-id="5bac2-154">jpeg</span></span>
- <span data-ttu-id="5bac2-155">jpg</span><span class="sxs-lookup"><span data-stu-id="5bac2-155">jpg</span></span>
- <span data-ttu-id="5bac2-156">markdown</span><span class="sxs-lookup"><span data-stu-id="5bac2-156">markdown</span></span>
- <span data-ttu-id="5bac2-157">md</span><span class="sxs-lookup"><span data-stu-id="5bac2-157">md</span></span>
- <span data-ttu-id="5bac2-158">msg</span><span class="sxs-lookup"><span data-stu-id="5bac2-158">msg</span></span>
- <span data-ttu-id="5bac2-159">pdf</span><span class="sxs-lookup"><span data-stu-id="5bac2-159">pdf</span></span>
- <span data-ttu-id="5bac2-160">png</span><span class="sxs-lookup"><span data-stu-id="5bac2-160">png</span></span>
- <span data-ttu-id="5bac2-161">ppt</span><span class="sxs-lookup"><span data-stu-id="5bac2-161">ppt</span></span>
- <span data-ttu-id="5bac2-162">pptx</span><span class="sxs-lookup"><span data-stu-id="5bac2-162">pptx</span></span>
- <span data-ttu-id="5bac2-163">rtf</span><span class="sxs-lookup"><span data-stu-id="5bac2-163">rtf</span></span>
- <span data-ttu-id="5bac2-164">tif</span><span class="sxs-lookup"><span data-stu-id="5bac2-164">tif</span></span>
- <span data-ttu-id="5bac2-165">tiff</span><span class="sxs-lookup"><span data-stu-id="5bac2-165">tiff</span></span>
- <span data-ttu-id="5bac2-166">txt</span><span class="sxs-lookup"><span data-stu-id="5bac2-166">txt</span></span>
- <span data-ttu-id="5bac2-167">xls</span><span class="sxs-lookup"><span data-stu-id="5bac2-167">xls</span></span>
- <span data-ttu-id="5bac2-168">xlsx</span><span class="sxs-lookup"><span data-stu-id="5bac2-168">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="5bac2-169">Zie ook</span><span class="sxs-lookup"><span data-stu-id="5bac2-169">See Also</span></span>
[<span data-ttu-id="5bac2-170">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="5bac2-170">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="5bac2-171">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="5bac2-171">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="5bac2-172">Een inhoudscentrum maken</span><span class="sxs-lookup"><span data-stu-id="5bac2-172">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="5bac2-173">Een formulierverwerkingsmodel maken</span><span class="sxs-lookup"><span data-stu-id="5bac2-173">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="5bac2-174">Een model toepassen</span><span class="sxs-lookup"><span data-stu-id="5bac2-174">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="5bac2-175">Het verschil tussen een documentbegripmodel en een formulierverwerkingsmodel</span><span class="sxs-lookup"><span data-stu-id="5bac2-175">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="5bac2-176">Overzicht formulierverwerking</span><span class="sxs-lookup"><span data-stu-id="5bac2-176">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="5bac2-177">SharePoint Syntex toegankheidsmodus</span><span class="sxs-lookup"><span data-stu-id="5bac2-177">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)