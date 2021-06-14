---
title: REST API voor model voor documentbegrip in SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Overzicht van de REST API voor model voor documentbegrip in SharePoint Syntex.
ms.openlocfilehash: e661df76828db0d05f7c3492880259117b9f8bf1
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908087"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a><span data-ttu-id="151fb-103">REST API voor model voor documentbegrip in SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="151fb-103">SharePoint Syntex document understanding model REST API</span></span>

<span data-ttu-id="151fb-104">U kunt de SharePoint REST-interface gebruiken om een model voor documentbegrip te maken, om het model toe te passen op of te verwijderen uit een of meer bibliotheken, en om informatie over het model op te halen of bij te werken.</span><span class="sxs-lookup"><span data-stu-id="151fb-104">You can use the SharePoint REST interface to create a document understanding model, apply or remove the model to one or more libraries, and obtain or update information about the model.</span></span> 

<span data-ttu-id="151fb-105">De SharePoint Online (en SharePoint 2016 en hoger on-premises) REST-service ondersteunt het combineren van meerdere aanvragen tot één oproep aan de service met behulp van de optie OData $batch query.</span><span class="sxs-lookup"><span data-stu-id="151fb-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests into a single call to the service by using the OData $batch query option.</span></span> 

<span data-ttu-id="151fb-106">Zie voor meer informatie en koppelingen naar codevoorbeelden [Batchaanvragen maken met de REST API's](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span><span class="sxs-lookup"><span data-stu-id="151fb-106">For details and links to code samples, see [Make batch requests with the REST APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="151fb-107">Vereisten</span><span class="sxs-lookup"><span data-stu-id="151fb-107">Prerequisites</span></span>

<span data-ttu-id="151fb-108">Zorg ervoor dat u bekend bent met het volgende voordat u aan de slag gaat:</span><span class="sxs-lookup"><span data-stu-id="151fb-108">Before you get started, make sure that you're familiar with the following:</span></span>

- [<span data-ttu-id="151fb-109">De SharePoint REST-service leren kennen</span><span class="sxs-lookup"><span data-stu-id="151fb-109">Get to know the SharePoint REST service</span></span>](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service) 
- [<span data-ttu-id="151fb-110">Basisbewerkingen uitvoeren met SharePoint REST-eindpunten</span><span class="sxs-lookup"><span data-stu-id="151fb-110">Complete basic operations using SharePoint REST endpoints</span></span>](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints)

## <a name="rest-commands"></a><span data-ttu-id="151fb-111">REST-opdrachten</span><span class="sxs-lookup"><span data-stu-id="151fb-111">REST commands</span></span>

<span data-ttu-id="151fb-112">De volgende REST-opdrachten zijn beschikbaar voor het werken met Syntex-modellen voor documentbegrip:</span><span class="sxs-lookup"><span data-stu-id="151fb-112">The following REST commands are available for working with Syntex document understanding models:</span></span>

- <span data-ttu-id="151fb-113">[Model maken](rest-createmodel-method.md): maakt een model en het gekoppelde inhoudstype.</span><span class="sxs-lookup"><span data-stu-id="151fb-113">[Create model](rest-createmodel-method.md) – Creates a model and its associated content type.</span></span>
- <span data-ttu-id="151fb-114">[GetByUniqueId](rest-getbyuniqueid-method.md): ontvangt of werkt informatie bij over een SharePoint Syntex-model voor documentbegrip.</span><span class="sxs-lookup"><span data-stu-id="151fb-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – Gets or updates information about a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="151fb-115">[GetByUniqueId](rest-getbytitle-method.md): ontvangt of werkt informatie bij over een SharePoint Syntex-model voor documentbegrip met behulp van de modeltitel.</span><span class="sxs-lookup"><span data-stu-id="151fb-115">[GetByTitle](rest-getbytitle-method.md) – Gets or updates information about a SharePoint Syntex document understanding model using the model title.</span></span>
- <span data-ttu-id="151fb-116">[Model toepassen](rest-applymodel-method.md): past (of synchroniseert) een getraind model voor documentbegrip toe op een of meer bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="151fb-116">[Apply model](rest-applymodel-method.md) – Applies (or syncs) a trained document understanding model to one or more libraries.</span></span>
- <span data-ttu-id="151fb-117">[Informatie over model- en bibliotheekgegevens](rest-getmodelandlibraryinfo.md) : informatie over een model en de bibliotheek waar het is toegepast.</span><span class="sxs-lookup"><span data-stu-id="151fb-117">[Get model and library information](rest-getmodelandlibraryinfo.md) – Gets information about a model and the library where it has been applied.</span></span>
- <span data-ttu-id="151fb-118">[UpdateModelSettings](rest-updatemodelsettings-method.md): hiermee worden de beschikbare modelinstellingen (gekoppeld bewaarlabel en modelbeschrijving) bijgewerkt voor een SharePoint Syntex-model voor documentbegrip.</span><span class="sxs-lookup"><span data-stu-id="151fb-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="151fb-119">[BatchDelete](rest-batchdelete-method.md): hiermee verwijdert u een toegepast model met documentbegrip uit een of meer bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="151fb-119">[BatchDelete](rest-batchdelete-method.md) – Removes an applied document understanding model from one or more libraries.</span></span>
- <span data-ttu-id="151fb-120">[Classificatieaanvraag maken](rest-createclassificationrequest.md): hiermee maakt u een aanvraag voor het classificeren van een opgegeven bestand of bestanden met behulp van het toegepaste model.</span><span class="sxs-lookup"><span data-stu-id="151fb-120">[Create classification request](rest-createclassificationrequest.md) – Creates a request to classify a specified file or files using the applied model.</span></span>

## <a name="scenarios"></a><span data-ttu-id="151fb-121">Scenario's</span><span class="sxs-lookup"><span data-stu-id="151fb-121">Scenarios</span></span>

<span data-ttu-id="151fb-122">Let op de volgende scenariovoorbeelden die geen intuïtieve methodenaam hebben.</span><span class="sxs-lookup"><span data-stu-id="151fb-122">Note the following scenario examples that aren't intuitive from the method name.</span></span> <span data-ttu-id="151fb-123">Raadpleeg dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="151fb-123">For more information, see each article.</span></span>

<span data-ttu-id="151fb-124">Met de methode Model maken worden alleen het modelobject en het bijbehorende inhoudstype gemaakt.</span><span class="sxs-lookup"><span data-stu-id="151fb-124">The create model method only creates the model object and its associated content type.</span></span> <span data-ttu-id="151fb-125">U moet het model eerst trainen in het inhoudscentrum voordat het op een bibliotheek kan worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="151fb-125">You'll need to first train the model in the content center before it can be applied to a library.</span></span>

<span data-ttu-id="151fb-126">De methode Model toepassen wordt gebruikt om het model in de doelbibliotheek zo te configureren dat documenten worden geclassificeerd en eventueel aanvullende informatie kan worden geëxtraheerd.</span><span class="sxs-lookup"><span data-stu-id="151fb-126">The apply model method is used to configure the model on the target library to classify documents and optionally extract additional information.</span></span> <span data-ttu-id="151fb-127">Deze API ondersteunt ook het batchgewijs toepassen van het model op meerdere bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="151fb-127">This API also supports batch applying the model to multiple libraries.</span></span>

<span data-ttu-id="151fb-128">Met de methode Model verwijderen wordt het model alleen verwijderd uit een of meer bibliotheken waar het eerder is toegepast.</span><span class="sxs-lookup"><span data-stu-id="151fb-128">The remove model method just removes the model from one or more libraries where it was previously applied.</span></span> <span data-ttu-id="151fb-129">Als u het model wilt verwijderen, moet het eerst worden verwijderd uit alle bibliotheken waar het is toegepast.</span><span class="sxs-lookup"><span data-stu-id="151fb-129">If you want to delete the model, it must first be removed from all the libraries where it was applied.</span></span>


## <a name="see-also"></a><span data-ttu-id="151fb-130">Zie ook</span><span class="sxs-lookup"><span data-stu-id="151fb-130">See also</span></span>

[<span data-ttu-id="151fb-131">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="151fb-131">Document understanding overview</span></span>](../document-understanding-overview.md)

