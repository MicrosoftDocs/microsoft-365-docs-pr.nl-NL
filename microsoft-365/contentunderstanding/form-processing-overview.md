---
title: Overzicht formulierverwerking
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
description: Informatie over formulierverwerking in Microsoft SharePoint Syntex
ms.openlocfilehash: 4a6ecc9e6eaca6f0b61f8c04b67eabb29674f6bd
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242444"
---
# <a name="form-processing-overview"></a><span data-ttu-id="0c236-103">Overzicht formulierverwerking</span><span class="sxs-lookup"><span data-stu-id="0c236-103">Form processing overview</span></span>

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="0c236-105">Microsoft SharePoint Syntex maakt gebruik van de formulierverwerking van Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) om modellen te maken in SharePoint-documentbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="0c236-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="0c236-106">U kunt de formulierverwerking van AI Builder gebruiken om AI-modellen te maken die gebruikmaken van machine-learningtechnologie om sleutel-waardeparen en tabelgegevens te identificeren en te extraheren uit gestructureerde of semi-gestructureerde documenten, zoals formulieren en facturen.</span><span class="sxs-lookup"><span data-stu-id="0c236-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="0c236-107">Organisaties ontvangen vaak grote hoeveelheden facturen afkomstig uit verschillende bronnen, zoals post, fax, e-mail, enzovoort. Het verwerken van deze documenten en het handmatig invoeren ervan in een database kan veel tijd in beslag nemen.</span><span class="sxs-lookup"><span data-stu-id="0c236-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="0c236-108">Door kunstmatige intelligentie te gebruiken om de tekst, sleutel-waardeparen en tabellen uit uw documenten te halen, automatiseert de formulierverwerking dit proces.</span><span class="sxs-lookup"><span data-stu-id="0c236-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="0c236-109">Zie [Ingebruikname van SharePoint Syntex: introductiehandleiding](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) voor meer informatie over scenariovoorbeelden voor formulierverwerking.</span><span class="sxs-lookup"><span data-stu-id="0c236-109">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="0c236-110">U kunt bijvoorbeeld een formulierverwerkingsmodel maken dat alle inkooporderdocumenten identificeert die naar de documentbibliotheek worden geüpload.</span><span class="sxs-lookup"><span data-stu-id="0c236-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="0c236-111">Vanuit elke inkooporder kunt u vervolgens specifieke belangrijke gegevens halen en weergeven, zoals *PO-nummer*, *Datum* en *Totale kosten*.</span><span class="sxs-lookup"><span data-stu-id="0c236-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![Documentbibliotheekweergave](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="0c236-113">U gebruikt voorbeeldbestanden om uw model te trainen en de informatie te definiëren die u uit het formulier wilt halen.</span><span class="sxs-lookup"><span data-stu-id="0c236-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="0c236-114">De indeling van het document wordt geleerd door het model te trainen.</span><span class="sxs-lookup"><span data-stu-id="0c236-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="0c236-115">U hebt slechts vijf documenten nodig om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="0c236-115">You only need five form documents to get started.</span></span> <span data-ttu-id="0c236-116">AI Builder analyseert uw voorbeeldbestanden voor sleutel-waardeparen en u kunt ook handmatig de items identificeren die niet zijn gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="0c236-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="0c236-117">Met AI Builder kunt u de nauwkeurigheid van uw model testen op uw voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="0c236-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="0c236-118">Nadat u het model hebt getraind en gepubliceerd, maakt het model een [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span><span class="sxs-lookup"><span data-stu-id="0c236-118">After you train and publish your model, your model creates a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="0c236-119">Deze flow wordt uitgevoerd wanneer een bestand wordt geüpload naar de SharePoint -documentbibliotheek, waarbij de gegevens die zijn geïdentificeerd in het model worden geëxtraheerd.</span><span class="sxs-lookup"><span data-stu-id="0c236-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="0c236-120">De geëxtraheerde gegevens worden weergegeven in kolommen in de documentbibliotheekweergave van uw model.</span><span class="sxs-lookup"><span data-stu-id="0c236-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="0c236-121">Een Office 365-beheerder moet [formulierverwerking inschakelen](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) voor de SharePoint-documentbibliotheek, zodat gebruikers in staat zijn daarin een [formulierverwerkingsmodel te maken](create-a-form-processing-model.md).</span><span class="sxs-lookup"><span data-stu-id="0c236-121">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="0c236-122">Je kunt de sites selecteren tijdens de installatie of na de configuratie van de beheerinstellingen.</span><span class="sxs-lookup"><span data-stu-id="0c236-122">You can select the sites during setup, or after setup in your management settings.</span></span>

### <a name="file-limitations"></a><span data-ttu-id="0c236-123">Bestandbeperkingen</span><span class="sxs-lookup"><span data-stu-id="0c236-123">File limitations</span></span>

<span data-ttu-id="0c236-124">Als je formulierverwerkingsmodellen gebruikt, let dan op de [vereisten en beperkingen voor bestandgebruik](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="0c236-124">When using form processing models, make sure to note the [requirements and limitations for file usage](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span>



## <a name="see-also"></a><span data-ttu-id="0c236-125">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0c236-125">See Also</span></span>
  
[<span data-ttu-id="0c236-126">Power Automate-documentatie</span><span class="sxs-lookup"><span data-stu-id="0c236-126">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="0c236-127">Een formulierverwerkingsmodel maken</span><span class="sxs-lookup"><span data-stu-id="0c236-127">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="0c236-128">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="0c236-128">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="0c236-129">Training: zakelijke prestaties verbeteren met AI-Builder</span><span class="sxs-lookup"><span data-stu-id="0c236-129">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
