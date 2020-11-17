---
title: Een documentbegripmodel toepassen op een documentbibliotheek
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Informatie over het toepassen van een gepubliceerd model op een SharePoint-documentbibliotheek.
ms.openlocfilehash: 0ca58e863d42d41b634978f53f55201a10a5ed93
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087485"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="03f92-103">Een documentbegripmodel toepassen in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="03f92-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="03f92-104">Na het publiceren van uw documentbegtipmodel kunt u het toepassen op een of meer SharePoint-documentbibliotheken in uw Microsoft 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="03f92-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="03f92-105">U kunt het model alleen toepassen op documentbibliotheken waar u toegang toe heeft.</span><span class="sxs-lookup"><span data-stu-id="03f92-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="03f92-106">Uw model toepassen op een documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="03f92-106">Apply your model to a document library.</span></span>

<span data-ttu-id="03f92-107">U past als volgt een model toe op een SharePoint-documentbibliotheek:</span><span class="sxs-lookup"><span data-stu-id="03f92-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="03f92-108">Op de startpagina van het model selecteert u op tegel **Model toepassen op bibliotheken** de optie **Model publiceren**.</span><span class="sxs-lookup"><span data-stu-id="03f92-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="03f92-109">U kunt ook **+Bibliotheek toevoegen** selecteren in het gedeelte **Bibliotheken met dit model**.</span><span class="sxs-lookup"><span data-stu-id="03f92-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Model toevoegen aan bibliotheek](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="03f92-111">Vervolgens kunt u de SharePoint-site selecteren die de documentbibliotheek bevat waarop u het model wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="03f92-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="03f92-112">Als de site niet in de lijst wordt weergegeven, gebruikt u het zoekvak om de site te vinden.</span><span class="sxs-lookup"><span data-stu-id="03f92-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Een site selecteren](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="03f92-114">U moet beschikken over de machtiging *Lijst beheren* of *Machtiging voor bewerken* voor de documentbibliotheek waarop u het model toepast.</span><span class="sxs-lookup"><span data-stu-id="03f92-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="03f92-115">Na het selecteren van de site selecteert u de documentbibliotheek waarop u het model wilt toepassen.</span><span class="sxs-lookup"><span data-stu-id="03f92-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="03f92-116">Selecteer in het voorbeeld de documentbibliotheek *Documenten* van de site *Contoso Case Tracking*.</span><span class="sxs-lookup"><span data-stu-id="03f92-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Een documentbibliotheek selecteren](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="03f92-118">Aangezien het model aan een inhoudstype is gekoppeld, worden het inhoudstype en de bijbehorende weergave met de labels die worden opgehaald, als kolommen toegevoegd wanneer u het model toepast.</span><span class="sxs-lookup"><span data-stu-id="03f92-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="03f92-119">Deze weergave is de standaardweergave van de bibliotheek, maar u kunt ervoor kiezen om dit niet de standaardweergave te maken door **Geavanceerde instellingen** te selecteren en **Deze nieuwe weergave instellen als standaard** te deselecteren.</span><span class="sxs-lookup"><span data-stu-id="03f92-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Documentbibliotheekweergave](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="03f92-121">Selecteer **Toevoegen** om het model toe te passen op de bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="03f92-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="03f92-122">Op de startpagina van het model wordt in het gedeelte **Bibliotheken met dit model** de URL van de SharePoint-site weergegeven.</span><span class="sxs-lookup"><span data-stu-id="03f92-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Geselecteerde bibliotheek](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="03f92-124">Ga naar de documentbibliotheek en controleer of de documentbibliotheekweergave van het model wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="03f92-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="03f92-125">U ziet dat wanneer u de informatieknop naast de naam van de documentbibliotheek selecteert, het bericht wordt weergegeven dat uw model is toegepast op de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="03f92-125">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![Informatieweergave](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="03f92-127">Nadat u het model hebt toegepast op de documentbibliotheek, kunt u beginnen met het uploaden van documenten naar de site en bekijken van de resultaten.</span><span class="sxs-lookup"><span data-stu-id="03f92-127">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="03f92-128">Het model identificeert bestanden met het relevante inhoudstype en toont ze in de weergave.</span><span class="sxs-lookup"><span data-stu-id="03f92-128">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="03f92-129">Als uw model extractoren bevat, worden in de weergave kolommen weergegeven voor de gegevens die u uit elk bestand haalt.</span><span class="sxs-lookup"><span data-stu-id="03f92-129">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="03f92-130">Het model toepassen op bestanden die zich al in de documentbibliotheek bevinden</span><span class="sxs-lookup"><span data-stu-id="03f92-130">Apply the model to files already in the document library</span></span>

<span data-ttu-id="03f92-131">Terwijl een toegepast model alle bestanden verwerkt die naar de documentbibliotheek worden geüpload nadat het is toegepast, kunt u ook het volgende doen om het model uit te voeren op bestanden die al aanwezig waren in de documentbibliotheek voordat het model werd toegepast:</span><span class="sxs-lookup"><span data-stu-id="03f92-131">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="03f92-132">Selecteer in de documentbibliotheek de bestanden die u wilt laten verwerken door het model.</span><span class="sxs-lookup"><span data-stu-id="03f92-132">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="03f92-133">Nadat u bestanden hebt geselecteerd, wordt **Classificeren en extraheren** weergegeven op het lint van de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="03f92-133">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="03f92-134">Selecteer **Classificeren en extraheren**.</span><span class="sxs-lookup"><span data-stu-id="03f92-134">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="03f92-135">De bestanden die u hebt geselecteerd, worden toegevoegd aan de verwerkingswachtrij.</span><span class="sxs-lookup"><span data-stu-id="03f92-135">The files you selected will be added to the queue to be processed.</span></span>

      ![Classificeren en extraheren](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="03f92-137">Zie ook</span><span class="sxs-lookup"><span data-stu-id="03f92-137">See Also</span></span>
[<span data-ttu-id="03f92-138">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="03f92-138">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="03f92-139">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="03f92-139">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="03f92-140">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="03f92-140">Document Understanding overview</span></span>](document-understanding-overview.md)


