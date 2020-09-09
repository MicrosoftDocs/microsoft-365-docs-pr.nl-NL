---
title: Verschil tussen document begrijpt en formulier verwerkings modellen (preview)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: In dit artikel wordt het verschil beschreven tussen document begrijpt en formulier verwerkings modellen.
ms.openlocfilehash: 972fa9e8446a44f6220baa7cde3f484172c50da6
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405615"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a><span data-ttu-id="40df4-103">Verschil tussen document begrijpt en formulier verwerkings modellen (preview)</span><span class="sxs-lookup"><span data-stu-id="40df4-103">Difference between document understanding and form processing models (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="40df4-104">De inhoud in dit artikel is bedoeld voor project cortex private preview.</span><span class="sxs-lookup"><span data-stu-id="40df4-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="40df4-105">[Lees meer over project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="40df4-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="40df4-106">Met inhoud begrijpen in Project cortex kunt u documenten identificeren en classificeren die worden geüpload naar SharePoint-documentbibliotheken, en relevante informatie uit elk bestand ophalen.</span><span class="sxs-lookup"><span data-stu-id="40df4-106">Content understanding in Project Cortex allows you to identify and classify documents that are uploaded to SharePoint document libraries, as well as extracting relevant information from each file.</span></span>  <span data-ttu-id="40df4-107">Wanneer bestanden worden geüpload naar een SharePoint-documentbibliotheek, worden alle bestanden die zijn geïdentificeerd als *aankoop orders* , geclassificeerd en weergegeven in de aangepaste weergave van een documentbibliotheek waarin ze worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="40df4-107">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such and displayed in a custom document library view in which they are displayed.</span></span> <span data-ttu-id="40df4-108">Daarnaast kunt u specifieke informatie uit elk bestand (bijvoorbeeld *ko-nummer* en *totaal*) optrekken en dit weergeven in een kolom in de weergave van de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="40df4-108">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it in a column in your document library view.</span></span> 


<span data-ttu-id="40df4-109">Met inhoud kunt u *modellen* maken waarmee de benodigde gegevens worden geïdentificeerd en uitgepakt.</span><span class="sxs-lookup"><span data-stu-id="40df4-109">Content understanding lets you create *models* to identify and extract the information you need.</span></span>  <span data-ttu-id="40df4-110">Er zijn twee soorten modellen die kunnen worden gebruikt:</span><span class="sxs-lookup"><span data-stu-id="40df4-110">There are two types of models that can be used:</span></span>

- [<span data-ttu-id="40df4-111">Documenten begrijpen met modellen</span><span class="sxs-lookup"><span data-stu-id="40df4-111">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="40df4-112">Formulier verwerkings modellen</span><span class="sxs-lookup"><span data-stu-id="40df4-112">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="40df4-113">Hoewel beide modellen voor algemeen dezelfde doeleinden worden gebruikt, is er sprake van belangrijke verschillen die van invloed zijn op de manier waarop u kunt kiezen.</span><span class="sxs-lookup"><span data-stu-id="40df4-113">While both models are used for generally the same purpose, there are key differences that will affect which one you might choose to use.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="40df4-114">Gestructureerd versus niet-gestructureerd en gedeeltelijk gestructureerde inhoud</span><span class="sxs-lookup"><span data-stu-id="40df4-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="40df4-115">U kunt documenten gebruiken om gegevens te identificeren en te extraheren uit niet-gestructureerde documenten, zoals brieven of contracten, waarbij de tekst entiteiten die u wilt extraheren, zich bevinden in zinnen of bepaalde gebieden van het document.</span><span class="sxs-lookup"><span data-stu-id="40df4-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document.</span></span> <span data-ttu-id="40df4-116">Een niet-gestructureerd document kan bijvoorbeeld een brief voor het verlengen van een contract zijn dat op verschillende manieren kan worden geschreven.</span><span class="sxs-lookup"><span data-stu-id="40df4-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="40df4-117">Er is echter informatie die consistent is in de hoofdtekst van het document voor het verlengen van contracten, zoals de tekenreeks ' service begindatum ', gevolgd door een werkelijke datum.</span><span class="sxs-lookup"><span data-stu-id="40df4-117">However, there is information that is consistently in the body of each contract renewal document, such as the text string "Service start date of" followed by an actual date.</span></span>   

<span data-ttu-id="40df4-118">Gebruik formulier verwerkings modellen om bestanden te identificeren en gegevens te extraheren uit gestructureerd of gedeeltelijk gestructureerde documenten, zoals formulieren of facturen, waar u paren met sleutelwaarden hebt uitgeschakeld (bijvoorbeeld *datum: 10/1/2020*) \* of tabelgegevens.</span><span class="sxs-lookup"><span data-stu-id="40df4-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices, where you have clear key-value pairs (for example, *Date: 10/1/2020*)\* or table data.</span></span> <span data-ttu-id="40df4-119">Voorbeeld: een goede kandidaat voor het verwerken van een formulier is een aanvraagformulier voor de order van een bedrijf waarin clients hun gegevens moeten verschaffen voor specifieke velden die zich in hetzelfde gebied van de documentindeling bevinden, zoals *naam*, *telefoonnummer*, *totale kosten*, etc.  Een belasting formulier is een goed voorbeeld van een gestructureerd document.</span><span class="sxs-lookup"><span data-stu-id="40df4-119">As an example, a good candidate for form processing would be a company's order request form in which clients need to provide their information for specific fields which are located in the same area of the document layout, such as *Name*, *Phone Number*, *Total Cost*, etc.  A tax form is a good example of a structured document.</span></span> 

## <a name="where-they-are-created"></a><span data-ttu-id="40df4-120">Waar ze worden gemaakt</span><span class="sxs-lookup"><span data-stu-id="40df4-120">Where they are created</span></span>

<span data-ttu-id="40df4-121">Document leren hoe modellen worden gemaakt en beheerd op een SharePoint-inhouds centrum site.</span><span class="sxs-lookup"><span data-stu-id="40df4-121">Document understanding models are created and managed in a SharePoint content center site.</span></span> <span data-ttu-id="40df4-122">U moet toegang hebben tot een inhouds centrum site om een document te leren maken met model of om een document toe te passen op een SharePoint-documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="40df4-122">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 

<span data-ttu-id="40df4-123">Wanneer u een document maakt wat het model is, maakt u een nieuw [SharePoint-inhoudstype](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) dat is opgeslagen in de galerie met SharePoint-inhoudstypen.</span><span class="sxs-lookup"><span data-stu-id="40df4-123">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="40df4-124">U kunt eventueel bestaande inhoudstypen gebruiken om zo nodig uw model te definiëren.</span><span class="sxs-lookup"><span data-stu-id="40df4-124">You can optionally use existing content types to define your model if needed.</span></span>

<span data-ttu-id="40df4-125">Formulier verwerkings modellen worden gemaakt in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), maar het maken van een SharePoint-documentbibliotheek wordt direct geïnitieerd.</span><span class="sxs-lookup"><span data-stu-id="40df4-125">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint document library.</span></span> <span data-ttu-id="40df4-126">Het maken van een model voor formulierverwerking moet zijn ingeschakeld in de documentbibliotheek om een gebruiker hiervoor een formulier verwerkings model te kunnen maken, en een beheerder kan dit doen met de inhoud van de beheerdersinstellingen.</span><span class="sxs-lookup"><span data-stu-id="40df4-126">Form processing model creation needs to be enabled on your document library in order for a user to create a form processing model for it, and an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="40df4-127">Formulier verwerkings modellen gebruiken PowerAutomate-stromen om bestanden te verwerken wanneer ze worden geüpload naar de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="40df4-127">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="40df4-128">Voor formulier verwerkings modellen worden ook nieuwe [SharePoint-inhoudstypen](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)gemaakt, die ook zijn opgeslagen in de galerie met SharePoint-inhoudstypen.</span><span class="sxs-lookup"><span data-stu-id="40df4-128">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), which are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="40df4-129">Waar ze kunnen worden toegepast</span><span class="sxs-lookup"><span data-stu-id="40df4-129">Where they can be applied</span></span>

<span data-ttu-id="40df4-130">Document wat betekent dat modellen kunnen worden toegepast op verschillende SharePoint-documentbibliotheken waartoe u toegang hebt.</span><span class="sxs-lookup"><span data-stu-id="40df4-130">Document understanding models can be applied to different SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="40df4-131">U kunt het inhouds centrum gebruiken om niet alleen een document te leren maken dat niet wordt gebruikt, maar ook om dit toe te passen op verschillende documentbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="40df4-131">You can use the content center to not only create a document understanding model, but also to apply it to different document libraries.</span></span> <span data-ttu-id="40df4-132">Het inhouds centrum biedt een meer centrale controle over hoe documenten worden gebruikt en waar ze worden toegepast, aangezien deze informatie moet worden opgedeeld in een inhouds centrum.</span><span class="sxs-lookup"><span data-stu-id="40df4-132">The content center gives a more central control of how document understanding models are used and where they are applied, since this information must roll up to a content center.</span></span>

<span data-ttu-id="40df4-133">Formulier verwerkings modellen kunnen op dit moment alleen worden toegepast op de SharePoint-documentbibliotheek van waaraf ze zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="40df4-133">Form processing models can currently only be applied to the SharePoint document library from which they were created.</span></span> <span data-ttu-id="40df4-134">Hiermee kan een gelicentieerde gebruiker die toegang heeft tot de site, een formulier verwerkings model maken.</span><span class="sxs-lookup"><span data-stu-id="40df4-134">This allows any licensed user who has access to the site to create a form processing model.</span></span>




 ## <a name="see-also"></a><span data-ttu-id="40df4-135">Zie ook</span><span class="sxs-lookup"><span data-stu-id="40df4-135">See Also</span></span>
[<span data-ttu-id="40df4-136">Training: bedrijfsprestaties verbeteren met AI Builder</span><span class="sxs-lookup"><span data-stu-id="40df4-136">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[<span data-ttu-id="40df4-137">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="40df4-137">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="40df4-138">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="40df4-138">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="40df4-139">Een document met inzicht toepassen</span><span class="sxs-lookup"><span data-stu-id="40df4-139">Apply a document understanding model</span></span>](apply-a-model.md)</br>
[<span data-ttu-id="40df4-140">Een formulier verwerkings model maken</span><span class="sxs-lookup"><span data-stu-id="40df4-140">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>



  
  



