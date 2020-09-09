---
title: Overzicht van formulierverwerking (preview)
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
description: Meer informatie over het verwerken van formulieren in Project cortex.
ms.openlocfilehash: 44ae5d9cbfbabc5615a751dba5f6c13290fc7b35
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405626"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="4dfcf-103">Overzicht van formulierverwerking (preview)</span><span class="sxs-lookup"><span data-stu-id="4dfcf-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="4dfcf-104">De inhoud in dit artikel is bedoeld voor project cortex private preview.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="4dfcf-105">[Lees meer over project cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="4dfcf-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="4dfcf-106">Project cortex gebruikt Microsoft PowerApps [AI Builder Builder](https://docs.microsoft.com/ai-builder/overview) -formulierverwerking voor het maken van modellen binnen SharePoint-documentbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="4dfcf-107">U kunt de formulierverwerking van de AI-opbouwfunctie gebruiken om AI-modellen te maken die gebruikmaken van machine learning Technology om sleutel-/waardeparen te identificeren en te extraheren uit gestructureerd of gedeeltelijk gestructureerde documenten, zoals formulieren en facturen.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="4dfcf-108">Bedrijven ontvangen vaak grote hoeveelheden en van diverse bronnen, zoals e-mail, Fax, e-mailadres of persoon.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="4dfcf-109">Door deze documenten te verwerken en handmatig in te voeren in de database, kan dit veel tijd in beslag nemen.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="4dfcf-110">Met AI voor het extraheren van de tekst, sleutel-/waardeparen en tabellen uit uw documenten, wordt dit proces door de formulierverwerking geautomatiseerd.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="4dfcf-111">U kunt bijvoorbeeld een formulier voor formulier verwerkings modellen maken waarmee alle documenten voor de aankooporders worden geïdentificeerd die worden geüpload naar de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="4dfcf-112">Met een van de aankooporders kunt u specifieke gegevens die belangrijk voor u zijn, ophalen en weergeven, zoals *ko-nummer*, *datum*of *totale kosten*.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="4dfcf-113">U gebruikt voorbeeldbestanden om uw model uit te leggen en te definiëren welke gegevens uit het formulier worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="4dfcf-114">De lay-out van uw document wordt geleerd door een training voor uw model.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="4dfcf-115">U hebt maar vijf formulier documenten nodig om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-115">You only need five form documents to get started.</span></span> <span data-ttu-id="4dfcf-116">Met de AI-opbouwfunctie worden de voorbeeldbestanden geanalyseerd voor de paren met sleutelwaarden en kunt u deze handmatig identificeren.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="4dfcf-117">Met de AI-opbouwfunctie kunt u de nauwkeurigheid van uw model testen op uw voorbeeldbestanden.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="4dfcf-118">Wanneer u uw model hebt opgetraind en gepubliceerd, kunt u het gebruiken om een stroom [automatisering](https://docs.microsoft.com/power-automate/getting-started)te maken.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="4dfcf-119">De stroom wordt uitgevoerd wanneer een bestand wordt geüpload naar de SharePoint-documentbibliotheek en gegevens worden opgehaald die in het model zijn gevonden.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="4dfcf-120">De opgehaalde gegevens worden weergegeven in kolommen in de documentbibliotheekweergave van uw model.</span><span class="sxs-lookup"><span data-stu-id="4dfcf-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="4dfcf-121">Een beheerder van Office 365 moet de [formulierverwerking inschakelen](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) voor de SharePoint-documentbibliotheek, zodat gebruikers [een formulier verwerkings model kunnen maken](create-a-form-processing-model.md) .</span><span class="sxs-lookup"><span data-stu-id="4dfcf-121">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="4dfcf-122">Zie ook</span><span class="sxs-lookup"><span data-stu-id="4dfcf-122">See Also</span></span>
  
[<span data-ttu-id="4dfcf-123">De documentatie voor Power Automatiseer</span><span class="sxs-lookup"><span data-stu-id="4dfcf-123">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="4dfcf-124">Een formulier verwerkings model maken</span><span class="sxs-lookup"><span data-stu-id="4dfcf-124">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="4dfcf-125">Overzicht van document</span><span class="sxs-lookup"><span data-stu-id="4dfcf-125">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="4dfcf-126">Training: bedrijfsprestaties verbeteren met AI Builder</span><span class="sxs-lookup"><span data-stu-id="4dfcf-126">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




