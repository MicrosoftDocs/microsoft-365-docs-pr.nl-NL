---
title: Een document in overeenstemming brengen met een documentbibliotheek (preview)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het toepassen van een model op een SharePoint-documentbibliotheek.
ms.openlocfilehash: 8a4931f4b7a936caeb99d7f8c07deefdac62919b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950246"
---
# <a name="apply-a-document-understanding-model-preview"></a><span data-ttu-id="db67a-103">Een document met informatie over model toepassen (preview)</span><span class="sxs-lookup"><span data-stu-id="db67a-103">Apply a document understanding model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="db67a-104">De inhoud in dit artikel is bedoeld voor project cortex private preview.</span><span class="sxs-lookup"><span data-stu-id="db67a-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="db67a-105">[Lees meer over project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="db67a-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="db67a-106">Nadat u het document hebt gepubliceerd, kunt u dit toepassen op een SharePoint-documentbibliotheek in uw Microsoft 365-Tenant.</span><span class="sxs-lookup"><span data-stu-id="db67a-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!Note]
> <span data-ttu-id="db67a-107">U kunt alleen het model toepassen op documentbibliotheken waartoe u toegang hebt.</span><span class="sxs-lookup"><span data-stu-id="db67a-107">You will only be able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="db67a-108">Uw model toepassen op een documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="db67a-108">Apply your model to a document library.</span></span>

<span data-ttu-id="db67a-109">Uw model toepassen op een SharePoint-documentbibliotheek:</span><span class="sxs-lookup"><span data-stu-id="db67a-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="db67a-110">Selecteer op de startpagina van het model op de tegel **model toepassen op bibliotheken** de optie **model publiceren**.</span><span class="sxs-lookup"><span data-stu-id="db67a-110">On the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="db67a-111">U kunt ook in de sectie **bibliotheken met behulp van deze model** sectie **+ bibliotheek toevoegen** selecteren.</span><span class="sxs-lookup"><span data-stu-id="db67a-111">Or you can  select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Model toevoegen aan bibliotheek](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="db67a-113">Vervolgens kunt u de SharePoint-site met de documentbibliotheek selecteren waarop u het model wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="db67a-113">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="db67a-114">Als de site niet in de lijst wordt weergegeven, gebruikt u het zoekvak om het te vinden.</span><span class="sxs-lookup"><span data-stu-id="db67a-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Selecteer een site](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > <span data-ttu-id="db67a-116">U moet beschikken over machtigingen voor *lijst beheren* of rechten *bewerken* voor de documentbibliotheek waarop u het model wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="db67a-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="db67a-117">Wanneer u de site hebt geselecteerd, moet u de documentbibliotheek selecteren waarop u het model wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="db67a-117">After selecting the site, you then need to select the document library to which you want to apply the model.</span></span> <span data-ttu-id="db67a-118">In dit voorbeeld selecteren we de documentbibliotheek *documenten* op de site van *Contoso zaken bijhouden* .</span><span class="sxs-lookup"><span data-stu-id="db67a-118">In the example, we are selecting the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Een documentbibliotheek selecteren](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="db67a-120">Aangezien het model is gekoppeld aan een inhoudstype, wordt er een weergave gemaakt voor het inhoudstype waarvan de etiketten zijn uitgepakt als kolommen wanneer u deze toepast op de bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="db67a-120">Since the model is associated to a content type, when you apply it to the library it will create a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="db67a-121">Deze weergave is standaard de standaardweergave van een bibliotheek, maar u kunt er ook voor kiezen om de standaardweergave niet te gebruiken door **Geavanceerde instellingen** te selecteren en **deze nieuwe weergave als standaard wilt instellen**.</span><span class="sxs-lookup"><span data-stu-id="db67a-121">This view will be the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Bibliotheek weergave](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="db67a-123">Selecteer **toevoegen** om het model op de bibliotheek toe te passen.</span><span class="sxs-lookup"><span data-stu-id="db67a-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="db67a-124">Op de startpagina van het model, in de sectie **bibliotheken met dit model** , wordt de URL naar de SharePoint-site weergegeven.</span><span class="sxs-lookup"><span data-stu-id="db67a-124">On the model home page, in the **Libraries with this model** section, you will see the URL to the SharePoint site listed.</span></span></br>

    ![Bibliotheek weergave](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="db67a-126">Ga naar de documentbibliotheek en zorg ervoor dat de documentbibliotheek van het model wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="db67a-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="db67a-127">Als u de knop informatie naast de naam van de documentbibliotheek selecteert, ziet u dat u in een bericht ziet dat uw model is toegepast op de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="db67a-127">You'll notice that if you select the information button next to the document library name, a message will note that your model has been applied to the document library.</span></span>

    ![Bibliotheek weergave](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="db67a-129">Nadat u het model hebt toegepast op de documentbibliotheek, kunt u beginnen met het uploaden van documenten naar de site en de resultaten bekijken.</span><span class="sxs-lookup"><span data-stu-id="db67a-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="db67a-130">Het model identificeert alle bestanden met het bijbehorende inhoudstype van het model en geeft ze weer in uw weergave.</span><span class="sxs-lookup"><span data-stu-id="db67a-130">The model will identify any files with model’s associated content type and will list them in your view.</span></span> <span data-ttu-id="db67a-131">Als uw model uitpaknen bevat, worden in de weergave kolommen weergegeven voor de gegevens die u uit elk bestand uitpakt.</span><span class="sxs-lookup"><span data-stu-id="db67a-131">If your model has any extractors, the view will display columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="db67a-132">Het model toepassen op al uw bestanden in de documentbibliotheek</span><span class="sxs-lookup"><span data-stu-id="db67a-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="db67a-133">Wanneer een toegepast model alle bestanden die zijn geüpload naar de documentbibliotheek, uitvoert, kunt u ook het volgende doen om het model uit te voeren op bestanden die al waren opgenomen in de documentbibliotheek voordat het model wordt toegepast:</span><span class="sxs-lookup"><span data-stu-id="db67a-133">While an applied model will process all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already existed in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="db67a-134">Selecteer in de documentbibliotheek de bestanden die u wilt laten verwerken door uw model.</span><span class="sxs-lookup"><span data-stu-id="db67a-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="db67a-135">Nadat u de bestanden hebt geselecteerd, worden **classificeerder en extract** weergegeven op het lint van de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="db67a-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="db67a-136">Selecteer **classificeren en uitpakken**.</span><span class="sxs-lookup"><span data-stu-id="db67a-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="db67a-137">De bestanden die u hebt geselecteerd, worden toegevoegd aan de wachtrij, zodat u deze kunt verwerken.</span><span class="sxs-lookup"><span data-stu-id="db67a-137">The files you selected will be added to the queue to be processed.</span></span>

      ![Classificeren en uitpakken](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a><span data-ttu-id="db67a-139">Zie ook</span><span class="sxs-lookup"><span data-stu-id="db67a-139">See Also</span></span>
[<span data-ttu-id="db67a-140">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="db67a-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="db67a-141">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="db67a-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="db67a-142">Overzicht van document</span><span class="sxs-lookup"><span data-stu-id="db67a-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="db67a-143">Een formulier verwerkings model maken</span><span class="sxs-lookup"><span data-stu-id="db67a-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  




