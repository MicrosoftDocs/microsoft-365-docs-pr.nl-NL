---
title: De naam van een extractor wijzigen in Microsoft SharePoint Syntex.
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
description: Lees hoe en waarom je de naam van een extractor kunt wijzigen in Microsoft SharePoint Syntex.
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445958"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="0403a-103">De naam van een extractor wijzigen in Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="0403a-103">Rename an extractor in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="0403a-104">Op een bepaald moment moet je misschien de naam van een extractor wijzigen als je naar een opgehaald gegevensveld wilt verwijzen met een andere naam.</span><span class="sxs-lookup"><span data-stu-id="0403a-104">At some point, you might need to rename an extractor if you want to refer to an extracted data field by a different name.</span></span> <span data-ttu-id="0403a-105">Je organisatie besluit bijvoorbeeld wijzigingen aan te brengen in hun contractdocumenten en in hun documenten naar 'klanten' te verwijzen als 'cliënten'.</span><span class="sxs-lookup"><span data-stu-id="0403a-105">For example, your organization decides to make changes to their contract documents, and refers to “customers” as “clients” in their documents.</span></span> <span data-ttu-id="0403a-106">Als je een veld 'Klant' uit je model ophaalde, kunt je de naam wijzigen in 'Cliënt'.</span><span class="sxs-lookup"><span data-stu-id="0403a-106">If you were extracting a “Customer” field in your model, you can choose to rename it to “Client.”</span></span>

<span data-ttu-id="0403a-107">Wanneer je het bijgewerkte model synchroniseert met je SharePoint-documentbibliotheek zie je een nieuwe kolom 'Cliënt' in de documentbibliotheekweergave.</span><span class="sxs-lookup"><span data-stu-id="0403a-107">When you sync your updated model to your SharePoint document library, you will see a new “Client” column in your document library view.</span></span> <span data-ttu-id="0403a-108">De weergave behoudt de kolom 'Klant' voor eerdere activiteiten, maar de nieuwe kolom 'Cliënt' wordt bijgewerkt voor alle nieuwe documenten die door je model worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="0403a-108">Your view will retain the “Customer” column for past activity, but will update the new “Client” column for all new documents that are processed by your model.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="0403a-109">Zorg ervoor dat je het bijgewerkte model synchroniseert naar de documentbibliotheken waarin je het eerder hebt toegepast om de nieuwe kolomnaam ook daar weer te geven.</span><span class="sxs-lookup"><span data-stu-id="0403a-109">Make sure to sync your updated model to the document libraries where you had previously applied it for the new column name to display.</span></span> 

## <a name="rename-an-extractor"></a><span data-ttu-id="0403a-110">De naam van een extractor wijzigen</span><span class="sxs-lookup"><span data-stu-id="0403a-110">Rename an extractor</span></span>

<span data-ttu-id="0403a-111">Volg deze stappen om de naam van een entiteitsextractor te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0403a-111">Follow these steps to rename an entity extractor.</span></span>

1. <span data-ttu-id="0403a-112">Selecteer in het inhoudscentrum **Modellen** om de lijst met modellen te zien.</span><span class="sxs-lookup"><span data-stu-id="0403a-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="0403a-113">Selecteer op pagina **Modellen** in de kolom **Naam** het model waarvoor je de naam van een extractor wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0403a-113">On the **Models** page, in the **Name** column, select the model for which you want to rename an extractor.</span></span>

3. <span data-ttu-id="0403a-114">Selecteer bij **Entiteitsextractors** de naam van de extractor waarvan je de naam wilt wijzigen en selecteer vervolgens **Naam wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="0403a-114">Under **Entity extractors**, select the name of the extractor you want to rename, and then select **Rename**.</span></span></br>

    ![Schermafbeelding van de sectie Entiteitsextractors met een geselecteerde extractor waarbij de optie Naam wijzigen is gemarkeerd.](../media/content-understanding/entity-extractor-rename.png) </br>

4. <span data-ttu-id="0403a-116">In het deelvenster **Naam van entiteitsextractor wijzigen**:</span><span class="sxs-lookup"><span data-stu-id="0403a-116">On the **Rename entity extractor** panel:</span></span>

   <span data-ttu-id="0403a-117">a.</span><span class="sxs-lookup"><span data-stu-id="0403a-117">a.</span></span> <span data-ttu-id="0403a-118">Voer bij **Nieuwe naam** de nieuwe naam van de extractor in.</span><span class="sxs-lookup"><span data-stu-id="0403a-118">Under **New name**, enter the new name of the extractor.</span></span></br>

    ![Schermafbeelding van het deelvenster Entiteitsextractors.](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   <span data-ttu-id="0403a-120">b.</span><span class="sxs-lookup"><span data-stu-id="0403a-120">b.</span></span> <span data-ttu-id="0403a-121">(Optioneel) Selecteer bij **Geavanceerde instellingen** of je een bestaande Sitekolom wilt koppelen.</span><span class="sxs-lookup"><span data-stu-id="0403a-121">(Optional) Under **Advanced settings**, select whether you want to associate an existing site column.</span></span>

5. <span data-ttu-id="0403a-122">Selecteer **Naam wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="0403a-122">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0403a-123">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0403a-123">See Also</span></span>
[<span data-ttu-id="0403a-124">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="0403a-124">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="0403a-125">Een classificatie maken</span><span class="sxs-lookup"><span data-stu-id="0403a-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="0403a-126">De naam van een model wijzigen</span><span class="sxs-lookup"><span data-stu-id="0403a-126">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="0403a-127">Uitlegtypen</span><span class="sxs-lookup"><span data-stu-id="0403a-127">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="0403a-128">De taxonomie van een termenarchief benutten bij het maken van een extractor</span><span class="sxs-lookup"><span data-stu-id="0403a-128">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="0403a-129">Overzicht van documentbegrip</span><span class="sxs-lookup"><span data-stu-id="0403a-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="0403a-130">Een model toepassen</span><span class="sxs-lookup"><span data-stu-id="0403a-130">Apply a model</span></span>](apply-a-model.md) 
