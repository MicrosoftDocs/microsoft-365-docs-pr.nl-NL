---
title: Een document met modellen op een documentbibliotheek toepassen
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het toepassen van een model op een SharePoint-documentbibliotheek
ms.openlocfilehash: c693fa08bf3103eca01e01774e8f8b1d9e783b07
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295488"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="b7acf-103">Een document met model toepassen in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="b7acf-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="b7acf-104">De inhoud in dit artikel is bedoeld voor de cortex van de private preview van project.</span><span class="sxs-lookup"><span data-stu-id="b7acf-104">The content in this article is for the the Project Cortex Private Preview.</span></span> <span data-ttu-id="b7acf-105">[Lees meer over project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="b7acf-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="b7acf-106">Nadat u het document hebt gepubliceerd, kunt u dit toepassen op een SharePoint-documentbibliotheek in uw Microsoft 365-Tenant.</span><span class="sxs-lookup"><span data-stu-id="b7acf-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="b7acf-107">U kunt alleen het model toepassen op documentbibliotheken waartoe u toegang hebt.</span><span class="sxs-lookup"><span data-stu-id="b7acf-107">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="b7acf-108">Uw model toepassen op een documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="b7acf-108">Apply your model to a document library.</span></span>

<span data-ttu-id="b7acf-109">Uw model toepassen op een SharePoint-documentbibliotheek:</span><span class="sxs-lookup"><span data-stu-id="b7acf-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="b7acf-110">Selecteer op de startpagina van het model in de tegel **model toepassen op bibliotheken** de optie **model publiceren**.</span><span class="sxs-lookup"><span data-stu-id="b7acf-110">From the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="b7acf-111">U kunt ook in de sectie **bibliotheken met behulp van deze model** sectie **+ bibliotheek toevoegen** selecteren.</span><span class="sxs-lookup"><span data-stu-id="b7acf-111">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Model toevoegen aan bibliotheek](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="b7acf-113">Selecteer de SharePoint-site met de documentbibliotheek waarop u het model wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="b7acf-113">Select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="b7acf-114">Als de site niet in de lijst wordt weergegeven, gebruikt u het zoekvak om het te vinden.</span><span class="sxs-lookup"><span data-stu-id="b7acf-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Selecteer een site](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="b7acf-116">U moet beschikken over machtigingen voor *lijst beheren* of rechten *bewerken* voor de documentbibliotheek waarop u het model wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="b7acf-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="b7acf-117">Wanneer u de site hebt geselecteerd, selecteert u de documentbibliotheek waarop u het model wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="b7acf-117">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="b7acf-118">Selecteer de documentbibliotheek van de *documenten* in het voorbeeld op de site voor het *bijhouden van hoofdletters* .</span><span class="sxs-lookup"><span data-stu-id="b7acf-118">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Een documentbibliotheek selecteren](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="b7acf-120">Aangezien het model is gekoppeld aan een inhoudstype, wordt er een weergave gemaakt voor het inhoudstype waarvan de etiketten worden weergegeven als kolommen wanneer u deze toepast op de bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="b7acf-120">Since the model is associated to a content type, when you apply it to the library it creates a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="b7acf-121">Deze weergave is standaard de standaardweergave van een bibliotheek, maar u kunt er ook voor kiezen om de standaardweergave niet te gebruiken door **Geavanceerde instellingen** te selecteren en **deze nieuwe weergave als standaard wilt instellen**.</span><span class="sxs-lookup"><span data-stu-id="b7acf-121">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Bibliotheek weergave](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="b7acf-123">Selecteer **toevoegen** om het model op de bibliotheek toe te passen.</span><span class="sxs-lookup"><span data-stu-id="b7acf-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="b7acf-124">Op de startpagina van het model, in de sectie **bibliotheken met dit model** , ziet u de URL naar de weergegeven SharePoint-site.</span><span class="sxs-lookup"><span data-stu-id="b7acf-124">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Geselecteerde bibliotheek](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="b7acf-126">Ga naar de documentbibliotheek en zorg ervoor dat de documentbibliotheek van het model wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b7acf-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="b7acf-127">Als u de knop informatie naast de naam van de documentbibliotheek selecteert, wordt een bericht weergegeven dat uw model is toegepast op de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="b7acf-127">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![Informatie weergave](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="b7acf-129">Nadat u het model hebt toegepast op de documentbibliotheek, kunt u beginnen met het uploaden van documenten naar de site en de resultaten bekijken.</span><span class="sxs-lookup"><span data-stu-id="b7acf-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="b7acf-130">Het model identificeert alle bestanden met het bijbehorende inhoudstype van het model en toont ze in de weergave.</span><span class="sxs-lookup"><span data-stu-id="b7acf-130">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="b7acf-131">Als het model uitpaknen bevat, worden in de weergave kolommen weergegeven voor de gegevens die u uit elk bestand wilt extraheren.</span><span class="sxs-lookup"><span data-stu-id="b7acf-131">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="b7acf-132">Het model toepassen op al uw bestanden in de documentbibliotheek</span><span class="sxs-lookup"><span data-stu-id="b7acf-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="b7acf-133">Hoewel een toegepast model alle bestanden die zijn geüpload naar de documentbibliotheek, wordt verwerkt nadat dit is toegepast, kunt u ook het volgende doen om het model uit te voeren op bestanden die al bestaan in de documentbibliotheek voordat het model wordt toegepast:</span><span class="sxs-lookup"><span data-stu-id="b7acf-133">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="b7acf-134">Selecteer in de documentbibliotheek de bestanden die u wilt laten verwerken door uw model.</span><span class="sxs-lookup"><span data-stu-id="b7acf-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="b7acf-135">Nadat u de bestanden hebt geselecteerd, worden **classificeerder en extract** weergegeven op het lint van de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="b7acf-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="b7acf-136">Selecteer **classificeren en uitpakken**.</span><span class="sxs-lookup"><span data-stu-id="b7acf-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="b7acf-137">De bestanden die u hebt geselecteerd, worden toegevoegd aan de wachtrij, zodat u deze kunt verwerken.</span><span class="sxs-lookup"><span data-stu-id="b7acf-137">The files you selected will be added to the queue to be processed.</span></span>

      ![Classificeren en uitpakken](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="b7acf-139">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b7acf-139">See Also</span></span>
[<span data-ttu-id="b7acf-140">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="b7acf-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="b7acf-141">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="b7acf-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="b7acf-142">Overzicht van document</span><span class="sxs-lookup"><span data-stu-id="b7acf-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="b7acf-143">Een formulier verwerkings model maken</span><span class="sxs-lookup"><span data-stu-id="b7acf-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  
