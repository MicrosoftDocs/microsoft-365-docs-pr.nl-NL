---
title: Een CSV-bestand voorbereiden voor een inhoudszoekactie in een id-lijst
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: Gebruik CSV-bestanden van een bestaande inhoudszoekfunctie om een zoekopdracht in de lijst met id's te maken die specifieke e-mailberichten retourneert.
ms.openlocfilehash: 7b63a78d34306cf3afcef49276e584bc816c107f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "52161475"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="588ee-103">Een CSV-bestand voorbereiden voor een inhoudszoekactie in een id-lijst</span><span class="sxs-lookup"><span data-stu-id="588ee-103">Prepare a CSV file for an ID list Content Search</span></span>

<span data-ttu-id="588ee-104">U kunt zoeken naar specifieke postvak-e-mailberichten en andere postvakitems met een lijst met Exchange-ed's.</span><span class="sxs-lookup"><span data-stu-id="588ee-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="588ee-105">Als u een zoekopdracht naar een id-lijst wilt maken (formeel een gerichte zoekopdracht genoemd), dient u een CSV-bestand (door komma's gescheiden waarde) in dat de specifieke postvakitems identificeert die moeten worden gezocht.</span><span class="sxs-lookup"><span data-stu-id="588ee-105">To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="588ee-106">Voor dit CSV-bestand gebruikt u het **Results.csv-bestand of** het niet-geïndexeerde **Items.csv-bestand** dat is opgenomen wanneer u de resultaten van Inhoudszoekactie exporteert of een inhoudszoekrapport exporteert van en bestaande inhoudszoekactie.</span><span class="sxs-lookup"><span data-stu-id="588ee-106">For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search.</span></span> <span data-ttu-id="588ee-107">Vervolgens bewerkt u een van deze bestanden om de specifieke items aan te geven die u wilt zoeken. Vervolgens maakt u een nieuwe zoekopdracht in de lijst met id's en verstuurt u het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="588ee-107">Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span>

<span data-ttu-id="588ee-108">Hier is een kort overzicht van het proces voor het maken van een zoekopdracht naar een lijst met id's.</span><span class="sxs-lookup"><span data-stu-id="588ee-108">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="588ee-109">Maak en voer een nieuwe of begeleide inhoudszoekactie uit in het & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="588ee-109">Create and run a new or guided Content Search in the Security & Compliance Center.</span></span>

2. <span data-ttu-id="588ee-110">Exporteert de zoekresultaten voor inhoud of exporteert het inhoudszoekrapport.</span><span class="sxs-lookup"><span data-stu-id="588ee-110">Export the content search results or export the content search report.</span></span> <span data-ttu-id="588ee-111">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="588ee-111">For more information, see:</span></span>

    - [<span data-ttu-id="588ee-112">Inhoudszoekresultaten exporteren</span><span class="sxs-lookup"><span data-stu-id="588ee-112">Export Content Search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="588ee-113">Een inhoudszoekrapport exporteren</span><span class="sxs-lookup"><span data-stu-id="588ee-113">Export a Content Search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="588ee-114">Bewerk **hetResults.csv** bestand of de niet-geïndexeerde **Items.csv** en identificeer de specifieke postvakitems die u wilt opnemen in de zoekopdracht in de lijst met id's.</span><span class="sxs-lookup"><span data-stu-id="588ee-114">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search.</span></span> <span data-ttu-id="588ee-115">Zie de [instructies voor](#prepare-the-csv-file-for-an-id-list-search) het voorbereiden van een CSV-bestand voor het zoeken naar een id-lijst.</span><span class="sxs-lookup"><span data-stu-id="588ee-115">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="588ee-116">Maak een nieuwe id-lijst zoeken (zie de [instructies)](#create-an-id-list-search)en verzend het CSV-bestand dat u hebt voorbereid.</span><span class="sxs-lookup"><span data-stu-id="588ee-116">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="588ee-117">De zoekquery die is gemaakt, zoekt alleen naar de items die zijn geselecteerd in het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="588ee-117">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="588ee-118">Zoekopdrachten in id-lijst worden alleen ondersteund voor postvakitems.</span><span class="sxs-lookup"><span data-stu-id="588ee-118">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="588ee-119">U kunt niet zoeken naar SharePoint en OneDrive zoeken in een id-lijst.</span><span class="sxs-lookup"><span data-stu-id="588ee-119">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

 <span data-ttu-id="588ee-120">**Waarom een id-lijst zoeken?**</span><span class="sxs-lookup"><span data-stu-id="588ee-120">**Why create an ID list search?**</span></span> <span data-ttu-id="588ee-121">Als u niet kunt bepalen of een item reageert op een eDiscovery-aanvraag op basis van de metagegevens in **deResults.csv-** of Niet-geïndexeerde **Items.csv-bestanden,** kunt u een zoekopdracht naar een id-lijst gebruiken om dat item te zoeken, een voorbeeld te bekijken en vervolgens te exporteren om te bepalen of het reageert op de zaak die u onderzoekt.</span><span class="sxs-lookup"><span data-stu-id="588ee-121">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="588ee-122">Zoekopdrachten in id-lijst worden meestal gebruikt om een specifieke set niet-geïndexeerde items te zoeken en te retourneren.</span><span class="sxs-lookup"><span data-stu-id="588ee-122">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="588ee-123">Het CSV-bestand voorbereiden voor een zoekopdracht in een id-lijst</span><span class="sxs-lookup"><span data-stu-id="588ee-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="588ee-124">Nadat u de zoekresultaten of het rapport voor een inhoudszoekactie hebt geëxporteerd, kunt u de volgende stappen uitvoeren om het CSV-bestand voor te bereiden op een zoekopdracht naar een id-lijst.</span><span class="sxs-lookup"><span data-stu-id="588ee-124">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="588ee-125">Dit CSV-bestand identificeert elk item in de zoekopdracht id-lijst.</span><span class="sxs-lookup"><span data-stu-id="588ee-125">This CSV file will identify every item in the ID list search.</span></span>

<span data-ttu-id="588ee-126">Houd er rekening mee dat u een CSV-bestand kunt gebruiken uit een zoekopdracht die  SharePoint sites en OneDrive-accounts bevat, maar u kunt alleen postvakitems selecteren voor een zoekopdracht in een id-lijst.</span><span class="sxs-lookup"><span data-stu-id="588ee-126">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search.</span></span> <span data-ttu-id="588ee-127">Als u een document selecteert in SharePoint of OneDrive, mislukt de validatie van het CSV-bestand wanneer u een zoekopdracht naar een id-lijst maakt.</span><span class="sxs-lookup"><span data-stu-id="588ee-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="588ee-128">Open het **Results.csv** **of niet-geïndexeerd Items.csv** bestand in Excel.</span><span class="sxs-lookup"><span data-stu-id="588ee-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="588ee-129">Typ **ja** **in** de kolom Geselecteerd in de cel die overeenkomt met het item dat u wilt zoeken.</span><span class="sxs-lookup"><span data-stu-id="588ee-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="588ee-130">Herhaal deze stap voor elk item dat u wilt zoeken.</span><span class="sxs-lookup"><span data-stu-id="588ee-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="588ee-131">Wanneer u het CSV-bestand in Excel opent, wordt de gegevensindeling voor de **kolom Document-id** gewijzigd in **Algemeen.**</span><span class="sxs-lookup"><span data-stu-id="588ee-131">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**.</span></span> <span data-ttu-id="588ee-132">Dit resulteert in het weergeven van de document-id voor een item in wetenschappelijke notatie.</span><span class="sxs-lookup"><span data-stu-id="588ee-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="588ee-133">De document-id van '481037338205' wordt bijvoorbeeld weergegeven als '4.81037E+11'. U moet de volgende stappen  uitvoeren om de gegevensindeling van de **kolom Document-id** te wijzigen in Getal om de juiste notatie voor de document-id te herstellen.</span><span class="sxs-lookup"><span data-stu-id="588ee-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="588ee-134">Als u dit niet doet, mislukt de zoekopdracht id-lijst met het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="588ee-134">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="588ee-135">Klik met de rechtermuisknop op de hele **kolom Document-id** en selecteer **Cellen opmaken.**</span><span class="sxs-lookup"><span data-stu-id="588ee-135">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="588ee-136">Klik in **het** vak Categorie op **Getal**.</span><span class="sxs-lookup"><span data-stu-id="588ee-136">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="588ee-137">Wijzig het aantal decimalen in **0** en klik vervolgens op **OK** om de wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="588ee-137">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="588ee-138">U ziet dat de waarden in de kolom Document-id worden gewijzigd in getallen.</span><span class="sxs-lookup"><span data-stu-id="588ee-138">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="588ee-139">Hier is een voorbeeld van het CSV-bestand dat klaar is om te worden verzonden voor een zoekopdracht naar inhoud in de lijst met id's.</span><span class="sxs-lookup"><span data-stu-id="588ee-139">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>

    ![Voorbeeld van een CSV-bestand voor een gerichte inhoudszoekactie](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. <span data-ttu-id="588ee-141">Sla het CSV-bestand op of gebruik **Opslaan als** om het bestand met een andere bestandsnaam op te slaan.</span><span class="sxs-lookup"><span data-stu-id="588ee-141">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="588ee-142">In beide gevallen moet u het bestand opslaan met de CSV-indeling.</span><span class="sxs-lookup"><span data-stu-id="588ee-142">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="588ee-143">Zoeken naar een id-lijst maken</span><span class="sxs-lookup"><span data-stu-id="588ee-143">Create an ID list search</span></span>

<span data-ttu-id="588ee-144">De volgende stap is het maken van een nieuwe id-lijst Inhoud zoeken en het CSV-bestand indienen dat u in de vorige stap hebt voorbereid.</span><span class="sxs-lookup"><span data-stu-id="588ee-144">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="588ee-145">U moet niet meer dan twee dagen na het exporteren van de resultaten of het rapport vanuit een inhoudszoekactie een zoekactie voor een id-lijst maken.</span><span class="sxs-lookup"><span data-stu-id="588ee-145">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search.</span></span> <span data-ttu-id="588ee-146">Als de zoekresultaten of het rapport meer dan 2 dagen geleden zijn geëxporteerd, moet u de zoekresultaten of het rapport opnieuw exporteren om bijgewerkte CSV-bestanden te genereren.</span><span class="sxs-lookup"><span data-stu-id="588ee-146">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="588ee-147">Vervolgens kunt u een van de bijgewerkte CSV-bestanden voorbereiden en deze gebruiken om een zoekopdracht naar een id-lijst te maken.</span><span class="sxs-lookup"><span data-stu-id="588ee-147">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="588ee-148">Ga in het & Compliancecentrum naar **Zoeken naar** inhoud \> **zoeken.**</span><span class="sxs-lookup"><span data-stu-id="588ee-148">In the Security & Compliance Center, go to **Search** \> **Content search**.</span></span>

2. <span data-ttu-id="588ee-149">Klik op **de pagina** Zoeken op de pijl naast Pictogram Nieuw ![ zoeken ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **toevoegen** en klik vervolgens op Zoeken **op id-lijst.**</span><span class="sxs-lookup"><span data-stu-id="588ee-149">On the **Search** page, click the arrow next to ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>

    ![Klik op Zoeken op id-lijst in de vervolgkeuzelijst Nieuwe zoekopdracht](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. <span data-ttu-id="588ee-151">In het **flyout** Zoeken op id-lijst geeft u de zoekfunctie een naam (en beschrijft u deze desgewenst) en klikt u op Bladeren en selecteert u het CSV-bestand dat u in de vorige stap hebt voorbereid. </span><span class="sxs-lookup"><span data-stu-id="588ee-151">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="588ee-152">Microsoft 365 probeert het CSV-bestand te valideren.</span><span class="sxs-lookup"><span data-stu-id="588ee-152">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="588ee-153">Als de validatie mislukt, wordt een foutbericht weergegeven dat u kan helpen bij het oplossen van de validatiefouten.</span><span class="sxs-lookup"><span data-stu-id="588ee-153">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="588ee-154">Het CSV-bestand moet worden gevalideerd om een zoekopdracht in een id-lijst te maken.</span><span class="sxs-lookup"><span data-stu-id="588ee-154">The CSV file has to be successfully validated to create an ID list search.</span></span>

4. <span data-ttu-id="588ee-155">Nadat het CSV-bestand is gevalideerd, klikt u **op Zoeken om** de zoekopdracht in de lijst met id's te maken.</span><span class="sxs-lookup"><span data-stu-id="588ee-155">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="588ee-156">Hier volgen een voorbeeld van de geschatte zoekresultaten en de query die wordt gegenereerd voor een zoekopdracht in een lijst met id's.</span><span class="sxs-lookup"><span data-stu-id="588ee-156">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>

    ![Zoekquery voor een gerichte inhoudszoekactie in het detailvenster](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    <span data-ttu-id="588ee-158">Het aantal geschatte items dat wordt weergegeven in statistieken voor het zoeken naar id's, moet overeenkomen met het aantal items dat u hebt geselecteerd in het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="588ee-158">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

5. <span data-ttu-id="588ee-159">Bekijk of exporteert de items die worden geretourneerd door de zoekactie naar de lijst met id's.</span><span class="sxs-lookup"><span data-stu-id="588ee-159">Preview or export the items returned by the ID list search.</span></span>

> [!NOTE]
> <span data-ttu-id="588ee-160">Als u een postvak verplaatst na het maken van een zoekopdracht naar de lijst met id's, worden de opgegeven items niet door de query voor de zoekopdracht retourneerd.</span><span class="sxs-lookup"><span data-stu-id="588ee-160">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="588ee-161">De eigenschap **DocumentId** voor postvakitems wordt namelijk gewijzigd wanneer een postvak wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="588ee-161">That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved.</span></span> <span data-ttu-id="588ee-162">In het zeldzame geval dat een postvak wordt verplaatst nadat u een zoekopdracht naar een id-lijst hebt gemaakt, moet u een nieuwe inhoudszoekactie maken (of de zoekresultaten bijwerken voor de bestaande inhoudszoekactie) en vervolgens de zoekresultaten of het rapport exporteren om bijgewerkte CSV-bestanden te genereren die kunnen worden gebruikt om een nieuwe zoekopdracht in de lijst met id's te maken.</span><span class="sxs-lookup"><span data-stu-id="588ee-162">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
