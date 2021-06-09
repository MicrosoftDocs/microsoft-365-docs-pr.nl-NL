---
title: 'SharePoint Syntex toegankelijkheidsmodus '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Meer informatie over het gebruik van de toegankelijkheidsmodus tijdens het trainen van een model in SharePoint Syntex.
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515146"
---
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="0cba5-103">SharePoint Syntex toegankelijkheidsmodus</span><span class="sxs-lookup"><span data-stu-id="0cba5-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="0cba5-104">In [SharePoint Syntex](index.md)kunnen gebruikers de toegankelijkheidsmodus inschakelen in alle fasen van modeltraining (label, trein, test) wanneer ze met voorbeelddocumenten werken.</span><span class="sxs-lookup"><span data-stu-id="0cba5-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="0cba5-105">Als u de toegankelijkheidsmodus gebruikt, kunnen slechtziende gebruikers gemakkelijker toegankelijkheid van het toetsenbord hebben terwijl ze navigeren en items labelen in de documentviewer.</span><span class="sxs-lookup"><span data-stu-id="0cba5-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="0cba5-106">Hiermee kunnen gebruikers hun toetsenbord gebruiken om door tekst in de documentviewer te navigeren en een gesproken tekst te horen van niet alleen de geselecteerde waarden, maar ook van acties (zoals labeling of het verwijderen van labeling uit geselecteerde tekst) of voorspelde labelwaarden terwijl u het model traint met extra voorbeelddocumenten.</span><span class="sxs-lookup"><span data-stu-id="0cba5-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![Toegankelijkheidsmodus](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="0cba5-108">Vereisten</span><span class="sxs-lookup"><span data-stu-id="0cba5-108">Requirements</span></span>

<span data-ttu-id="0cba5-109">Als u het geluid van de gesproken tekst wilt horen, moet u de [Verteller-app](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in uw Verteller op uw Windows 10 in.</span><span class="sxs-lookup"><span data-stu-id="0cba5-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![De Verteller](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="0cba5-111">Labeling voor toetsenbordgebruikers</span><span class="sxs-lookup"><span data-stu-id="0cba5-111">Labeling for keyboard users</span></span>

<span data-ttu-id="0cba5-112">Voor toetsenbordgebruikers die de toegankelijkheidsmodus gebruiken, kunt u de volgende toetsen gebruiken als u tekst in een voorbeelddocument in de viewer labelt:</span><span class="sxs-lookup"><span data-stu-id="0cba5-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="0cba5-113">Tab: Hiermee verplaatst u naar voren en selecteert u het volgende woord.</span><span class="sxs-lookup"><span data-stu-id="0cba5-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="0cba5-114">Tab + Shift: Hiermee verplaatst u u naar achteren en selecteert u het vorige woord.</span><span class="sxs-lookup"><span data-stu-id="0cba5-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="0cba5-115">Enter: Een label labelen of verwijderen uit het geselecteerde woord.</span><span class="sxs-lookup"><span data-stu-id="0cba5-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="0cba5-116">Pijl-rechts: hiermee wordt u door afzonderlijke tekens in een geselecteerd woord verplaatst.</span><span class="sxs-lookup"><span data-stu-id="0cba5-116">Right arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="0cba5-117">Pijl-links: hiermee verplaatst u u naar achteren door afzonderlijke tekens in een geselecteerd woord.</span><span class="sxs-lookup"><span data-stu-id="0cba5-117">Left arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="0cba5-118">Als u meerdere woorden labelt voor één label, moet u elk woord labelen.</span><span class="sxs-lookup"><span data-stu-id="0cba5-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="0cba5-119">Gesproken tekst</span><span class="sxs-lookup"><span data-stu-id="0cba5-119">Narration</span></span>

<span data-ttu-id="0cba5-120">Voor Verteller gebruikers die de toegankelijkheidsmodus gebruiken, gebruikt u dezelfde toetsenbordnavigatie die is beschreven voor toetsenbordgebruikers om door het voorbeelddocument in de viewer te gaan.</span><span class="sxs-lookup"><span data-stu-id="0cba5-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="0cba5-121">Terwijl u door de voorbeelddocumenten en labelreekswaarden navigeert, Verteller de gebruiker de volgende audioprompts:</span><span class="sxs-lookup"><span data-stu-id="0cba5-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="0cba5-122">Wanneer u het toetsenbord gebruikt om door de documentviewer te navigeren, Verteller de geselecteerde tekenreeks.</span><span class="sxs-lookup"><span data-stu-id="0cba5-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="0cba5-123">In een geselecteerde tekenreeks Verteller elk teken in de tekenreeks als u ze selecteert met behulp van de pijl-links of pijl-rechts.</span><span class="sxs-lookup"><span data-stu-id="0cba5-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the left or right arrow keys.</span></span>
- <span data-ttu-id="0cba5-124">Als u een tekenreeks selecteert die is gelabeld, Verteller de waarde en vervolgens 'labeled'.</span><span class="sxs-lookup"><span data-stu-id="0cba5-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="0cba5-125">Als de labelwaarde bijvoorbeeld 'Contoso' is, wordt 'Costoso labeled' vermeld.</span><span class="sxs-lookup"><span data-stu-id="0cba5-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="0cba5-126">Als u op het tabblad training een tekenreeks selecteert in de documentviewer die alleen is voorspeld, wordt Verteller de waarde weergegeven en vervolgens 'voorspeld'.</span><span class="sxs-lookup"><span data-stu-id="0cba5-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="0cba5-127">Dit gebeurt wanneer de training een waarde in het bestand voorspelt die niet overeenkomen met wat door de gebruiker is gelabeld.</span><span class="sxs-lookup"><span data-stu-id="0cba5-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="0cba5-128">Als u op het tabblad training een tekenreeks selecteert in de documentviewer die is gelabeld en voorspeld, wordt Verteller audio de waarde weergegeven en vervolgens 'gelabeld en voorspeld'.</span><span class="sxs-lookup"><span data-stu-id="0cba5-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="0cba5-129">Dit gebeurt wanneer de training is geslaagd en er een overeenkomst is tussen een voorspelde waarde en het gebruikerslabel.</span><span class="sxs-lookup"><span data-stu-id="0cba5-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="0cba5-130">Nadat een tekenreeks is gelabeld of een label is verwijderd in de viewer, wordt Verteller u gewaarschuwd om uw wijzigingen op te slaan voordat u de video sluit.</span><span class="sxs-lookup"><span data-stu-id="0cba5-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="0cba5-131">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0cba5-131">See Also</span></span>

[<span data-ttu-id="0cba5-132">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="0cba5-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="0cba5-133">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="0cba5-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



