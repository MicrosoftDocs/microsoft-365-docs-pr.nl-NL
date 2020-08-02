---
title: Verschil tussen documentbegrip en formulierverwerkingsmodellen (Voorbeeld)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Beschrijft het belangrijkste verschil tussen documentbegrip en formulierverwerkingsmodellen.
ms.openlocfilehash: bceeb4b2f52ecf95aa0a23bf8970d1427088d877
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537150"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a><span data-ttu-id="15875-103">Verschil tussen documentbegrip en formulierverwerkingsmodellen (Voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="15875-103">Difference between document understanding and form processing models (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="15875-104">De inhoud in dit artikel is voor Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="15875-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="15875-105">[Lees meer over Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="15875-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="15875-106">Met inhoudsbegrip in Project Cortex u documenten identificeren en classificeren die naar SharePoint-documentbibliotheken worden geüpload en relevante informatie uit elk bestand extraheren.</span><span class="sxs-lookup"><span data-stu-id="15875-106">Content understanding in Project Cortex allows you to identify and classify documents that are uploaded to SharePoint document libraries, as well as extracting relevant information from each file.</span></span>  <span data-ttu-id="15875-107">Als bestanden bijvoorbeeld worden geüpload naar een SharePoint-documentbibliotheek, worden alle bestanden die als *inkooporders* zijn geïdentificeerd, als zodanig geclassificeerd en weergegeven in een aangepaste documentbibliotheekweergave waarin ze worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="15875-107">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such and displayed in a custom document library view in which they are displayed.</span></span> <span data-ttu-id="15875-108">Daarnaast u specifieke informatie uit elk bestand ophalen (bijvoorbeeld *PO-nummer* en *Totaal)* en deze weergeven in een kolom in de documentbibliotheekweergave.</span><span class="sxs-lookup"><span data-stu-id="15875-108">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it in a column in your document library view.</span></span> 


<span data-ttu-id="15875-109">Met het begrijpen van inhoud u *modellen* maken om de informatie die u nodig hebt te identificeren en te extraheren.</span><span class="sxs-lookup"><span data-stu-id="15875-109">Content understanding lets you create *models* to identify and extract the information you need.</span></span>  <span data-ttu-id="15875-110">Er zijn twee soorten modellen die kunnen worden gebruikt:</span><span class="sxs-lookup"><span data-stu-id="15875-110">There are two types of models that can be used:</span></span>

- [<span data-ttu-id="15875-111">Modellen voor documentinzicht</span><span class="sxs-lookup"><span data-stu-id="15875-111">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="15875-112">Formulierverwerkingsmodellen</span><span class="sxs-lookup"><span data-stu-id="15875-112">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="15875-113">Hoewel beide modellen worden gebruikt voor over het algemeen hetzelfde doel, zijn er belangrijke verschillen die van invloed zijn op welke modellen u kiezen om te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="15875-113">While both models are used for generally the same purpose, there are key differences that will affect which ones you may choose to use.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="15875-114">Gestructureerd versus ongestructureerde en semi-gestructureerde inhoud</span><span class="sxs-lookup"><span data-stu-id="15875-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="15875-115">Gebruik modellen voor documentbegrip om gegevens uit ongestructureerde documenten, zoals brieven of contracten, te identificeren en te extraheren, waarbij de tekstentiteiten die u wilt extraheren zich in zinnen of specifieke gebieden van het document bevinden.</span><span class="sxs-lookup"><span data-stu-id="15875-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document.</span></span> <span data-ttu-id="15875-116">Een ongestructureerd document kan bijvoorbeeld een brief voor contractverlenging zijn die op verschillende manieren kan worden geschreven.</span><span class="sxs-lookup"><span data-stu-id="15875-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="15875-117">Er is echter informatie die consistent in de hoofdtekst van elk contractverlengingsdocument zit, zoals de tekstreeks 'Begindatum van de service' gevolgd door een werkelijke datum.</span><span class="sxs-lookup"><span data-stu-id="15875-117">However, there is information that is consistently in the body of each contract renewal document, such as the text string "Service start date of" followed by an actual date.</span></span>   

<span data-ttu-id="15875-118">Gebruik formulierverwerkingsmodellen om bestanden te identificeren en gegevens uit gestructureerde of semi-gestructureerde documenten te extraheren, zoals formulieren of facturen, waarbij u duidelijke sleutelwaardeparen hebt (bijvoorbeeld *Datum: 10/1/2020*)\* of tabelgegevens.</span><span class="sxs-lookup"><span data-stu-id="15875-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices, where you have clear key-value pairs (for example, *Date: 10/1/2020*)\* or table data.</span></span> <span data-ttu-id="15875-119">Een goede kandidaat voor formulierverwerking zou bijvoorbeeld het aanvraagformulier van een bedrijf zijn waarin klanten hun informatie moeten verstrekken voor specifieke velden die zich in hetzelfde gebied van de documentindeling bevinden, zoals *Naam,* *Telefoonnummer,* *Totale kosten,* enz.  Een belastingformulier is een goed voorbeeld van een gestructureerd document.</span><span class="sxs-lookup"><span data-stu-id="15875-119">As an example, a good candidate for form processing would be a company's order request form in which clients need to provide their information for specific fields which are located in the same area of the document layout, such as *Name*, *Phone Number*, *Total Cost*, etc.  A tax form is a good example of a structured document.</span></span> 

## <a name="where-they-are-created"></a><span data-ttu-id="15875-120">Waar ze worden gemaakt</span><span class="sxs-lookup"><span data-stu-id="15875-120">Where they are created</span></span>

<span data-ttu-id="15875-121">Document understanding modellen worden gemaakt en beheerd in een SharePoint content center site.</span><span class="sxs-lookup"><span data-stu-id="15875-121">Document understanding models are created and managed in a SharePoint content center site.</span></span> <span data-ttu-id="15875-122">U moet toegang hebben tot een inhoudscentrumsite om een documentbegripmodel te maken of om een model toe te passen op een SharePoint-documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="15875-122">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 

<span data-ttu-id="15875-123">Wanneer u een documentbegripmodel maakt, maakt u een nieuw [SharePoint-inhoudstype](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) dat is opgeslagen in de galerie SharePoint-inhoudstypen.</span><span class="sxs-lookup"><span data-stu-id="15875-123">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="15875-124">U optioneel bestaande inhoudstypen gebruiken om uw model zo nodig te definiëren.</span><span class="sxs-lookup"><span data-stu-id="15875-124">You can optionally use existing content types to define your model if needed.</span></span>

<span data-ttu-id="15875-125">Formulierverwerkingsmodellen worden gemaakt in PowerApps [AI Builder,](https://docs.microsoft.com/ai-builder/overview)maar de creatie wordt rechtstreeks gestart vanuit een SharePoint-documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="15875-125">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint Document library.</span></span> <span data-ttu-id="15875-126">Het maken van formulierverwerkingsmodellen moet worden ingeschakeld in uw documentbibliotheek, zodat een gebruiker er een formulierverwerkingsmodel voor kan maken, en een beheerder kan dit doen in de beheerdersinstellingen voor inhoudsbegrip.</span><span class="sxs-lookup"><span data-stu-id="15875-126">Form processing model creation needs to be enabled on your document library in order for a user to create a form processing model for it, and an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="15875-127">Formulierverwerkingsmodellen gebruiken PowerAutomate-stromen om bestanden te verwerken wanneer ze worden geüpload naar de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="15875-127">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="15875-128">Formulierverwerkingsmodellen maken ook nieuwe [SharePoint-inhoudstypen,](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)die ook worden opgeslagen in de galerie SharePoint-inhoudstypen.</span><span class="sxs-lookup"><span data-stu-id="15875-128">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), which are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="15875-129">Waar ze kunnen worden toegepast</span><span class="sxs-lookup"><span data-stu-id="15875-129">Where they can be applied</span></span>

<span data-ttu-id="15875-130">Modellen voor documentbegrip kunnen worden toegepast op verschillende SharePoint-documentbibliotheken waar toe u toegang hebt.</span><span class="sxs-lookup"><span data-stu-id="15875-130">Document understanding models can be applied to different SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="15875-131">U het inhoudscentrum gebruiken om niet alleen een documentbegripmodel te maken, maar ook om het toe te passen op verschillende documentbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="15875-131">You can use the content center to not only create a document understanding model, but also to apply it to different document libraries.</span></span> <span data-ttu-id="15875-132">Het inhoudscentrum geeft een meer centrale controle over hoe documentbegripmodellen worden gebruikt en waar ze worden toegepast, omdat deze informatie moet worden uitgerold naar een inhoudscentrum.</span><span class="sxs-lookup"><span data-stu-id="15875-132">The content center gives a more central control of how document understanding models are used and where they are applied, since this information must roll up to a content center.</span></span>

<span data-ttu-id="15875-133">Formulierverwerkingsmodellen kunnen momenteel alleen worden toegepast op de SharePoint-documentbibliotheek waaruit ze zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="15875-133">Form processing models can currently only be applied to the SharePoint document library from which they were created.</span></span> <span data-ttu-id="15875-134">Hierdoor kan elke gelicentieerde gebruiker die toegang heeft tot de site een formulierverwerkingsmodel maken.</span><span class="sxs-lookup"><span data-stu-id="15875-134">This allows any licensed user who has access to the site to create a form processing model.</span></span>




 ## <a name="see-also"></a><span data-ttu-id="15875-135">Zie ook</span><span class="sxs-lookup"><span data-stu-id="15875-135">See Also</span></span>
[<span data-ttu-id="15875-136">Training: Verbeter de bedrijfsprestaties met AI Builder</span><span class="sxs-lookup"><span data-stu-id="15875-136">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[<span data-ttu-id="15875-137">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="15875-137">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="15875-138">Een afzuiger maken</span><span class="sxs-lookup"><span data-stu-id="15875-138">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="15875-139">Een documentbegripmodel toepassen</span><span class="sxs-lookup"><span data-stu-id="15875-139">Apply a document understanding model</span></span>](apply-a-model.md)</br>
[<span data-ttu-id="15875-140">Een formulierverwerkingsmodel maken</span><span class="sxs-lookup"><span data-stu-id="15875-140">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>



  
  



