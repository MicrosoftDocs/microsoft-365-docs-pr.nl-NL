---
title: 'Toegankelijkheidsmodus in SharePoint Syntex '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Informatie over het gebruik van de toegankelijkheidsmodus bij het trainen van een model in SharePoint Syntex.
ms.openlocfilehash: 32e5bd132a7a0145f03e4620545d65d1d92ff223
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080999"
---
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="e5ac6-103">Toegankelijkheidsmodus in SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="e5ac6-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="e5ac6-104">In [SharePoint Syntex](index.md)kunnen gebruikers tijdens het werken met voorbeelddocumenten de toegankelijkheidsmodus inschakelen in alle fases van modeltraining (label, training, test).</span><span class="sxs-lookup"><span data-stu-id="e5ac6-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="e5ac6-105">Als u de toegankelijkheidsmodus gebruikt, kunnen gebruikers die slechtziend zijn gemakkelijker toetsenbordtoegankelijkheid bieden tijdens het navigeren door items en items labelen in de documentviewer.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="e5ac6-106">Hierdoor kunnen gebruikers hun toetsenbord gebruiken om door tekst in de documentviewer te navigeren en ook gesproken tekst te horen van niet alleen de geselecteerde waarden, maar ook van acties (zoals labelen of verwijderen van labeling uit geselecteerde tekst) of voorspelde labelwaarden terwijl u het model met extra voorbeelddocumenten trainen.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![Toegankelijkheidsmodus](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="e5ac6-108">Vereisten</span><span class="sxs-lookup"><span data-stu-id="e5ac6-108">Requirements</span></span>

<span data-ttu-id="e5ac6-109">Als u de audio van de gesproken tekst wilt horen, moet u de [Verteller-app](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in de verteller-instellingen op uw Windows 10-systeem in uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![Verteller in te zetten](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="e5ac6-111">Labelen voor toetsenbordgebruikers</span><span class="sxs-lookup"><span data-stu-id="e5ac6-111">Labeling for keyboard users</span></span>

<span data-ttu-id="e5ac6-112">Voor toetsenbordgebruikers die de toegankelijkheidsmodus gebruiken, kunt u de volgende toetsen gebruiken als u een label aan tekst in een voorbeelddocument in de viewer wilt toevoegen:</span><span class="sxs-lookup"><span data-stu-id="e5ac6-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="e5ac6-113">Tab: Hiermee gaat u naar voren en selecteert u het volgende woord.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="e5ac6-114">Tab+Shift: hiermee verplaatst u het vorige woord naar achteren en selecteert u het vorige woord.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="e5ac6-115">Enter: een label toevoegen aan of verwijderen van het geselecteerde woord.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="e5ac6-116">Pijl naar voren: Hiermee gaat u naar voren door afzonderlijke tekens in een geselecteerd woord.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-116">Forward arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="e5ac6-117">Pijl-terug: Hiermee gaat u achteruit door afzonderlijke tekens in een geselecteerd woord.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-117">Backward arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="e5ac6-118">Als u meerdere woorden labelt voor één etiket, moet u elk woord van een label voorzien.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="e5ac6-119">Gesproken tekst</span><span class="sxs-lookup"><span data-stu-id="e5ac6-119">Narration</span></span>

<span data-ttu-id="e5ac6-120">Voor verteller-gebruikers die de toegankelijkheidsmodus gebruiken, gebruikt u dezelfde toetsenbordnavigatie die voor toetsenbordgebruikers is beschreven om het voorbeelddocument in de viewer te bekijken.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="e5ac6-121">Terwijl u door de voorbeelddocumenten en labelreekswaarden navigeert, geeft Verteller de gebruiker de volgende audioprompts:</span><span class="sxs-lookup"><span data-stu-id="e5ac6-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="e5ac6-122">Wanneer u het toetsenbord gebruikt om door de documentviewer te navigeren, wordt de geselecteerde tekenreeks voor het geluid van Verteller opgezocht.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="e5ac6-123">Binnen een geselecteerde tekenreeks geeft Verteller-audio elk teken in de tekenreeks op terwijl u deze selecteert met behulp van de pijl vooruit of achteruit.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the forward or backward arrow.</span></span>
- <span data-ttu-id="e5ac6-124">Als u een gelabelde tekenreeks selecteert, wordt de waarde door Verteller vermeld en vervolgens 'gelabeld'.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="e5ac6-125">Als de labelwaarde bijvoorbeeld 'Contoso' is, wordt 'Costoso gelabeld' als resultaat geven.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="e5ac6-126">Als u op het tabblad Training een tekenreeks selecteert in de documentviewer die alleen is voorspeld, wordt de waarde voor het geluid van Verteller weergegeven en vervolgens 'voorspeld'.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="e5ac6-127">Deze fout treedt op wanneer met de training een waarde in het bestand wordt voorspeld die niet overeen komt met wat door de gebruiker is gelabeld.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="e5ac6-128">Als u op het tabblad Training een tekenreeks selecteert in de documentviewer die is gelabeld en voorspeld, wordt de waarde voor het geluid van Verteller weergegeven en vervolgens 'gelabeld en voorspeld'.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="e5ac6-129">Dit gebeurt wanneer de training is geslaagd en er een overeenkomst is tussen een voorspelde waarde en het gebruikerslabel.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="e5ac6-130">Nadat een tekenreeks is gelabeld of er een label is verwijderd in de viewer, wordt u gewaarschuwd door Verteller-audio om uw wijzigingen op te slaan voordat u deze sluit.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5ac6-131">Zie ook</span><span class="sxs-lookup"><span data-stu-id="e5ac6-131">See Also</span></span>

[<span data-ttu-id="e5ac6-132">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="e5ac6-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="e5ac6-133">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="e5ac6-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



