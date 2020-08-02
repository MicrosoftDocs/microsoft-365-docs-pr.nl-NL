---
title: Een documentinzichtmodel toepassen op een documentbibliotheek (Voorbeeld)
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
description: Meer informatie over het toepassen van een gepubliceerd model op een SharePoint-documentbibliotheek.
ms.openlocfilehash: 7e5f3f02c2679769515b27026918a15c901c896e
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537252"
---
# <a name="apply-a-document-understanding-model-preview"></a><span data-ttu-id="14809-103">Een documentbegripmodel toepassen (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="14809-103">Apply a document understanding model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="14809-104">De inhoud in dit artikel is voor Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="14809-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="14809-105">[Lees meer over Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="14809-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="14809-106">Nadat u het model voor het begrijpen van documenten hebt gepubliceerd, u dit toepassen op een SharePoint-documentbibliotheek in uw Microsoft 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="14809-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!Note]
> <span data-ttu-id="14809-107">U het model alleen toepassen op documentbibliotheken waar u toegang toe hebt.</span><span class="sxs-lookup"><span data-stu-id="14809-107">You will only be able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="14809-108">Pas uw model toe op een documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="14809-108">Apply your model to a document library.</span></span>

<span data-ttu-id="14809-109">Ga als voorbeeld van uw model naar een SharePoint-documentbibliotheek:</span><span class="sxs-lookup"><span data-stu-id="14809-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="14809-110">Selecteer op de startpagina van het model op de tegel **Model toepassen** op bibliotheken de optie **Model publiceren**.</span><span class="sxs-lookup"><span data-stu-id="14809-110">On the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="14809-111">U **ook +Bibliotheek toevoegen** in de **bibliotheken selecteren met deze modelsectie.**</span><span class="sxs-lookup"><span data-stu-id="14809-111">Or you can  select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Model toevoegen aan bibliotheek](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="14809-113">U vervolgens de SharePoint-site selecteren die de documentbibliotheek bevat waarop u het model wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="14809-113">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="14809-114">Als de site niet wordt weergegeven in de lijst, gebruikt u het zoekvak om deze te zoeken.</span><span class="sxs-lookup"><span data-stu-id="14809-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Een site selecteren](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > <span data-ttu-id="14809-116">U moet *machtigingen voor lijst beheren* of De rechten voor de documentbibliotheek *waarop* u het model toepast, bewerken.</span><span class="sxs-lookup"><span data-stu-id="14809-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="14809-117">Nadat u de site hebt geselecteerd, moet u de documentbibliotheek selecteren waarop u het model wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="14809-117">After selecting the site, you then need to select the document library to which you want to apply the model.</span></span> <span data-ttu-id="14809-118">In het voorbeeld selecteren we de documentbibliotheek *Documenten* op de *contoso-site voor het bijhouden van de aanvraag.*</span><span class="sxs-lookup"><span data-stu-id="14809-118">In the example, we are selecting the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Een documentbibliotheek selecteren](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="14809-120">Aangezien het model is gekoppeld aan een inhoudstype, wordt bij het toepassen van het model een weergave gemaakt voor het inhoudstype met de labels die u als kolommen hebt geëxtraheerd.</span><span class="sxs-lookup"><span data-stu-id="14809-120">Since the model is associated to a content type, when you apply it to the library it will create a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="14809-121">Deze weergave is standaard de standaardweergave van de bibliotheek, maar u er optioneel voor kiezen om deze niet de standaardweergave te laten zijn door **Geavanceerde instellingen** te selecteren en deze nieuwe weergave **als standaard**instellen uit te stellen.</span><span class="sxs-lookup"><span data-stu-id="14809-121">This view will be the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Bibliotheekweergave](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="14809-123">Selecteer **Toevoegen** om het model toe te passen op de bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="14809-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="14809-124">Op de startpagina van het model, in de **sectie Bibliotheken met dit model,** ziet u de URL naar de SharePoint-site vermeld.</span><span class="sxs-lookup"><span data-stu-id="14809-124">On the model home page, in the **Libraries with this model** section, you will see the URL to the SharePoint site listed.</span></span></br>

    ![Bibliotheekweergave](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="14809-126">Ga naar uw documentbibliotheek en zorg ervoor dat u zich in de documentbibliotheekweergave van het model bevindt.</span><span class="sxs-lookup"><span data-stu-id="14809-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="14809-127">U zult merken dat als u de informatieknop naast de naam van de documentbibliotheek selecteert, er een bericht wordt weergegeven dat uw model is toegepast op de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="14809-127">You'll notice that if you select the information button next to the document library name, a message will note that your model has been applied to the document library.</span></span>

    ![Bibliotheekweergave](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="14809-129">Nadat u het model hebt toegepast op de documentbibliotheek, u beginnen met het uploaden van documenten naar de site en de resultaten bekijken.</span><span class="sxs-lookup"><span data-stu-id="14809-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="14809-130">Het model identificeert alle bestanden met het bijbehorende inhoudstype van het model en geeft deze in uw weergave weer.</span><span class="sxs-lookup"><span data-stu-id="14809-130">The model will identify any files with model’s associated content type and will list them in your view.</span></span> <span data-ttu-id="14809-131">Als uw model uitstanden heeft, worden in de weergave kolommen weergegeven voor de gegevens die u uit elk bestand haalt.</span><span class="sxs-lookup"><span data-stu-id="14809-131">If your model has any extractors, the view will display columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="14809-132">Het model toepassen op bestanden die al in de documentbibliotheek staan</span><span class="sxs-lookup"><span data-stu-id="14809-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="14809-133">Hoewel een toegepast model alle bestanden verwerkt die naar de documentbibliotheek zijn geüpload nadat het is toegepast, u ook het volgende uitvoeren om het model uit te voeren op bestanden die al in de documentbibliotheek bestonden voordat het model werd toegepast:</span><span class="sxs-lookup"><span data-stu-id="14809-133">While an applied model will process all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already existed in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="14809-134">Selecteer in uw documentbibliotheek de bestanden die u door uw model wilt verwerken.</span><span class="sxs-lookup"><span data-stu-id="14809-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="14809-135">Nadat u uw bestanden hebt geselecteerd, wordt **Classificeren en extraheren** weergegeven op het lint van de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="14809-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="14809-136">Selecteer **Classificeren en uitpakken**.</span><span class="sxs-lookup"><span data-stu-id="14809-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="14809-137">De geselecteerde bestanden worden toegevoegd aan de wachtrij die moet worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="14809-137">The files you selected will be added to the queue to be processed.</span></span>

      ![Classificeren en extraheren](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a><span data-ttu-id="14809-139">Zie ook</span><span class="sxs-lookup"><span data-stu-id="14809-139">See Also</span></span>
[<span data-ttu-id="14809-140">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="14809-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="14809-141">Een afzuiger maken</span><span class="sxs-lookup"><span data-stu-id="14809-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="14809-142">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="14809-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="14809-143">Een formulierverwerkingsmodel maken</span><span class="sxs-lookup"><span data-stu-id="14809-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  




