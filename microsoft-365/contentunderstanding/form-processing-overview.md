---
title: Overzicht van formulierverwerking (Voorbeeld)
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
description: Meer informatie over formulierverwerking in Project Cortex.
ms.openlocfilehash: 9709c8170f5dc6ce0edbeb2d90cb4e1f6d759c64
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540056"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="879fc-103">Overzicht van formulierverwerking (Voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="879fc-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="879fc-104">De inhoud in dit artikel is voor Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="879fc-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="879fc-105">[Lees meer over Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="879fc-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="879fc-106">Project Cortex gebruikt de formulierverwerking van Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) om modellen te maken in SharePoint-documentbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="879fc-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="879fc-107">U AI Builder-formulierverwerking gebruiken om AI-modellen te maken die machine learning-technologie gebruiken om paren met een sleutelwaarde en tabelgegevens te identificeren en te extraheren uit gestructureerde of semi-gestructureerde documenten, zoals formulier en facturen.</span><span class="sxs-lookup"><span data-stu-id="879fc-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like form and invoices.</span></span>

<span data-ttu-id="879fc-108">Bedrijven ontvangen facturen vaak in grote hoeveelheden en uit verschillende bronnen, zoals e-mail, fax, e-mail of persoonlijk.</span><span class="sxs-lookup"><span data-stu-id="879fc-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="879fc-109">Het verwerken van deze documenten en het handmatig invoeren van deze documenten in uw database kan een aanzienlijke hoeveelheid tijd in beslag nemen.</span><span class="sxs-lookup"><span data-stu-id="879fc-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="879fc-110">Door AI te gebruiken om de tekst, sleutel/waardeparen en tabellen uit uw documenten te extraheren, automatiseert formulierverwerking dit proces.</span><span class="sxs-lookup"><span data-stu-id="879fc-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="879fc-111">U bijvoorbeeld een formulierverwerkingsmodel maken waarmee alle aankooporderdocumenten worden geïdentificeerd die naar de documentbibliotheek zijn geüpload.</span><span class="sxs-lookup"><span data-stu-id="879fc-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="879fc-112">En uit elke inkooporder u specifieke gegevens extraheren en weergeven die voor u belangrijk zijn, zoals *PO-nummer,* *datum*of *totale kosten*.</span><span class="sxs-lookup"><span data-stu-id="879fc-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="879fc-113">U gebruikt voorbeeldbestanden om uw model te trainen en de informatie te definiëren die uit uw formulier moet worden gehaald.</span><span class="sxs-lookup"><span data-stu-id="879fc-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="879fc-114">De lay-out van uw document wordt geleerd door uw model te trainen.</span><span class="sxs-lookup"><span data-stu-id="879fc-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="879fc-115">Je hebt slechts vijf formulierdocumenten nodig om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="879fc-115">You only need five form documents to get started.</span></span> <span data-ttu-id="879fc-116">AI-gebouw analyseert uw voorbeeldbestanden voor paren met een sleutelwaarde en u ook handmatig bestanden identificeren die mogelijk niet zijn gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="879fc-116">AI building will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="879fc-117">Met AI-bouwer u de nauwkeurigheid van uw model testen op uw voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="879fc-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="879fc-118">Nadat u uw model hebt getraind en gepubliceerd, maakt u een [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) die wordt uitgevoerd wanneer een bestand wordt geüpload naar de SharePoint-documentbibliotheek en gegevens extrahert die in het model zijn geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="879fc-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that will run when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="879fc-119">De uitgepakte gegevens worden weergegeven in kolommen in de documentbibliotheekweergave van uw model.</span><span class="sxs-lookup"><span data-stu-id="879fc-119">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="879fc-120">Een Office 365-beheerder moet [formulierverwerking](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) voor de SharePoint-documentbibliotheek inschakelen zodat gebruikers [er een formulierverwerkingsmodel](create-a-form-processing-model.md) in kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="879fc-120">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="879fc-121">Zie ook</span><span class="sxs-lookup"><span data-stu-id="879fc-121">See Also</span></span>
  
[<span data-ttu-id="879fc-122">Documentatie voor energie automatiseren</span><span class="sxs-lookup"><span data-stu-id="879fc-122">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="879fc-123">Een formulierverwerkingsmodel maken</span><span class="sxs-lookup"><span data-stu-id="879fc-123">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="879fc-124">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="879fc-124">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="879fc-125">Training: Verbeter de bedrijfsprestaties met AI Builder</span><span class="sxs-lookup"><span data-stu-id="879fc-125">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




