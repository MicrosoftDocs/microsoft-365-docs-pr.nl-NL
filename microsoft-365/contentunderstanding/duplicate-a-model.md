---
title: Een model dupliceren in Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Lees hoe en waarom je een model kunt dupliceren in Microsoft SharePoint Syntex.
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445977"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="8b3f0-103">Een model dupliceren in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="8b3f0-103">Duplicate a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="8b3f0-104">Als je een model met documentbegrip dupliceert, kun je tijd en moeite besparen bij het maken van een nieuw model als je weet dat een bestaand model sterk lijkt op wat je nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-104">Duplicating a document understanding model can save you time and effort if you need to create a new model, and know that an existing model is very similar to what you need.</span></span>

<span data-ttu-id="8b3f0-105">Een bestaand model met de naam 'Contracten' classificeert bijvoorbeeld dezelfde bestanden waarmee je moet werken.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-105">For example, an existing model named “Contracts” classifies the same files you need to work with.</span></span> <span data-ttu-id="8b3f0-106">Het nieuwe model haalt een deel van de bestaande gegevens op, maar moet worden bijgewerkt om extra gegevens op te halen.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-106">Your new model will extract some of the existing data, but will need to be updated to extract some additional data.</span></span> <span data-ttu-id="8b3f0-107">In plaats van een nieuw model helemaal opnieuw zelf te maken en te trainen, kun je met de functie Model dupliceren een kopie van het model Contracten maken, waarbij ook alle bijbehorende trainingsitems worden gekopieerd, zoals voorbeeldbestanden en entiteitsextractoren.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-107">Instead of creating and training a new model from scratch, you can use the duplicate model feature to make a copy of the Contracts model, which will also copy all associated training items, such as example files and entity extractors.</span></span>

<span data-ttu-id="8b3f0-108">Wanneer je het model dupliceert en de naam van het model hebt gewijzigd (bijvoorbeeld in 'Contractverlengingen'), kun je het model vervolgens bijwerken.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-108">When you duplicate the model, after you rename it (for example, to “Contract Renewals”), you can then make updates to it.</span></span> <span data-ttu-id="8b3f0-109">Je kunt bijvoorbeeld sommige bestaande opgehaalde velden verwijderen die je niet nodig hebt en het model vervolgens trainen om een nieuw veld op te halen (bijvoorbeeld 'Verlengingsdatum').</span><span class="sxs-lookup"><span data-stu-id="8b3f0-109">For example, you can choose to remove some of the existing extracted fields that you don’t need, and then train the model to extract a new one (for example, “Renewal date”).</span></span>

## <a name="duplicate-a-model"></a><span data-ttu-id="8b3f0-110">Een model dupliceren</span><span class="sxs-lookup"><span data-stu-id="8b3f0-110">Duplicate a model</span></span>

<span data-ttu-id="8b3f0-111">Volg deze stappen om een model met documentbegrip te dupliceren.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-111">Follow these steps to duplicate a document understanding model.</span></span>

1. <span data-ttu-id="8b3f0-112">Selecteer in het inhoudscentrum **Modellen** om de lijst met modellen te zien.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="8b3f0-113">Selecteer op de pagina **Modellen** het model dat je wilt dupliceren.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-113">On the **Models** page, select the model you want to duplicate.</span></span>

3. <span data-ttu-id="8b3f0-114">Gebruik het lint of de knop **Acties weergeven** (naast de modelnaam) om **Dupliceren** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-114">By using either the ribbon or the **Show actions** button (next to the model name), select **Duplicate**.</span></span></br>

    ![Schermafbeelding van de pagina Modellen met een geselecteerd model waarbij de opties voor dupliceren zijn gemarkeerd.](../media/content-understanding/select-model-duplicate-both.png) </br>

4. <span data-ttu-id="8b3f0-116">In het deelvenster **Model dupliceren**:</span><span class="sxs-lookup"><span data-stu-id="8b3f0-116">On the **Duplicate model** panel:</span></span>

   <span data-ttu-id="8b3f0-117">a.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-117">a.</span></span> <span data-ttu-id="8b3f0-118">Voer bij **Naam** de nieuwe naam in van het model dat je wilt dupliceren.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-118">Under **Name**, enter the new name of the model that you want to duplicate.</span></span></br>

    ![Schermafbeelding van het deelvenster Model dupliceren.](../media/content-understanding/duplicate-model-panel.png) </br>

   <span data-ttu-id="8b3f0-120">b.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-120">b.</span></span> <span data-ttu-id="8b3f0-121">Voeg bij **Beschrijving** een beschrijving van het nieuwe model toe.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-121">Under **Description**, add a description of your new model.</span></span>

   <span data-ttu-id="8b3f0-122">c.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-122">c.</span></span> <span data-ttu-id="8b3f0-123">(Optioneel) Selecteer bij **Geavanceerde instellingen** of je een bestaand [inhoudstype](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) wilt koppelen.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span>

5. <span data-ttu-id="8b3f0-124">Selecteer **Dupliceren**.</span><span class="sxs-lookup"><span data-stu-id="8b3f0-124">Select **Duplicate**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b3f0-125">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8b3f0-125">See Also</span></span>
[<span data-ttu-id="8b3f0-126">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="8b3f0-126">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="8b3f0-127">De naam van een model wijzigen</span><span class="sxs-lookup"><span data-stu-id="8b3f0-127">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="8b3f0-128">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="8b3f0-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="8b3f0-129">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="8b3f0-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="8b3f0-130">Uitlegtypen</span><span class="sxs-lookup"><span data-stu-id="8b3f0-130">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="8b3f0-131">Een model toepassen</span><span class="sxs-lookup"><span data-stu-id="8b3f0-131">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="8b3f0-132">SharePoint Syntex toegankelijkheidsmodus</span><span class="sxs-lookup"><span data-stu-id="8b3f0-132">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)