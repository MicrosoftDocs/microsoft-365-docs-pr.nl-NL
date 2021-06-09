---
title: Een CSV-bestand voorbereiden voor een id-lijst Zoeken naar inhoud
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
description: Gebruik een CSV-bestand van een bestaande inhoudszoekactie om een zoekopdracht in de lijst met id's te maken die specifieke e-mailitems retourneert.
ms.openlocfilehash: 37a398d0896fcfd7b7282bda1f6a549ed9f53601
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311536"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a><span data-ttu-id="de736-103">Een CSV-bestand voorbereiden voor een id-lijst Zoeken naar inhoud</span><span class="sxs-lookup"><span data-stu-id="de736-103">Prepare a CSV file for an ID list Content search</span></span>

<span data-ttu-id="de736-104">U kunt zoeken naar specifieke postvak-e-mailberichten en andere postvakitems met een lijst met Exchange-ed's.</span><span class="sxs-lookup"><span data-stu-id="de736-104">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="de736-105">Als u een zoekopdracht voor een lijst met id's wilt maken, dient u een bestand met door komma's gescheiden waarden (CSV) in dat de specifieke postvakitems identificeert waar u naar wilt zoeken.</span><span class="sxs-lookup"><span data-stu-id="de736-105">To create an ID list search, you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="de736-106">Voor dit CSV-bestand gebruikt u het **Results.csv-bestand of** het niet-geïndexeerde **Items.csv-bestand** dat is opgenomen wanneer u de zoekresultaten inhoud exporteert of een inhoudszoekrapport exporteert vanuit een bestaande inhoudszoekactie.</span><span class="sxs-lookup"><span data-stu-id="de736-106">For this CSV file, you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content search results or export a Content search report from an existing Content search.</span></span> <span data-ttu-id="de736-107">Vervolgens bewerkt u een van deze bestanden om de specifieke items aan te geven die u wilt zoeken, maakt u een nieuwe zoekopdracht naar de lijst met id's en verstuurt u het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="de736-107">Then you edit one of these files to indicate the specific items to search for, create a new ID list search, and submit the CSV file.</span></span>

<span data-ttu-id="de736-108">**Waarom een id-lijst zoeken?**</span><span class="sxs-lookup"><span data-stu-id="de736-108">**Why create an ID list search?**</span></span> <span data-ttu-id="de736-109">Als u niet kunt bepalen of een item reageert op een eDiscovery-aanvraag op basis van de metagegevens in **deResults.csv-** of Niet-geïndexeerde **Items.csv-bestanden,** kunt u een zoekopdracht naar een id-lijst gebruiken om dat item te zoeken, een voorbeeld te bekijken en vervolgens te exporteren om te bepalen of het reageert op de zaak die u onderzoekt.</span><span class="sxs-lookup"><span data-stu-id="de736-109">If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating.</span></span> <span data-ttu-id="de736-110">Zoekopdrachten in id-lijst worden meestal gebruikt om een specifieke set niet-geïndexeerde items te zoeken en te retourneren.</span><span class="sxs-lookup"><span data-stu-id="de736-110">ID list searches are typically used to search for and return a specific set of unindexed items.</span></span>

<span data-ttu-id="de736-111">Hier is een kort overzicht van het proces voor het maken van een zoekopdracht naar een lijst met id's.</span><span class="sxs-lookup"><span data-stu-id="de736-111">Here's a quick overview of the process for creating an ID list search.</span></span>

1. <span data-ttu-id="de736-112">Een nieuwe zoekopdracht maken en uitvoeren in het Microsoft 365 compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="de736-112">Create and run a new search in the Microsoft 365 compliance center.</span></span>

2. <span data-ttu-id="de736-113">Exporteert de inhoudszoekresultaten of het inhoudszoekrapport.</span><span class="sxs-lookup"><span data-stu-id="de736-113">Export the content search results or the content search report.</span></span> <span data-ttu-id="de736-114">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="de736-114">For more information, see:</span></span>

    - [<span data-ttu-id="de736-115">Zoekresultaten voor inhoud exporteren</span><span class="sxs-lookup"><span data-stu-id="de736-115">Export Content search results</span></span>](export-search-results.md)

    - [<span data-ttu-id="de736-116">Een inhoudszoekrapport exporteren</span><span class="sxs-lookup"><span data-stu-id="de736-116">Export a Content search report</span></span>](export-a-content-search-report.md)

3. <span data-ttu-id="de736-117">Bewerk het **Results.csv** **bestand of niet-geïndexeerd** Items.csvbestand en identificeer de specifieke postvakitems die moeten worden opgenomen in de zoekopdracht id-lijst.</span><span class="sxs-lookup"><span data-stu-id="de736-117">Edit the **Results.csv** file or **Unindexed Items.csv** file and identify the specific mailbox items to include in the ID list search.</span></span> <span data-ttu-id="de736-118">Zie de [instructies voor](#prepare-the-csv-file-for-an-id-list-search) het voorbereiden van een CSV-bestand voor het zoeken naar een id-lijst.</span><span class="sxs-lookup"><span data-stu-id="de736-118">See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span>

4. <span data-ttu-id="de736-119">Maak een nieuwe id-lijst zoeken (zie de [instructies)](#create-an-id-list-search)en verzend het CSV-bestand dat u hebt voorbereid.</span><span class="sxs-lookup"><span data-stu-id="de736-119">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared.</span></span> <span data-ttu-id="de736-120">De zoekquery die is gemaakt, zoekt alleen naar de items die zijn geselecteerd in het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="de736-120">The search query that's created will only search for the items selected in the CSV file.</span></span>

> [!NOTE]
> <span data-ttu-id="de736-121">Zoekopdrachten in id-lijst worden alleen ondersteund voor postvakitems.</span><span class="sxs-lookup"><span data-stu-id="de736-121">ID list searches are only supported for mailbox items.</span></span> <span data-ttu-id="de736-122">U kunt niet zoeken naar SharePoint en OneDrive zoeken in een id-lijst.</span><span class="sxs-lookup"><span data-stu-id="de736-122">You can't search for SharePoint and OneDrive documents in an ID list search.</span></span>

## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="de736-123">Het CSV-bestand voorbereiden voor een zoekopdracht in een id-lijst</span><span class="sxs-lookup"><span data-stu-id="de736-123">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="de736-124">Nadat u de zoekresultaten of het rapport voor een zoekopdracht hebt geëxporteerd, voert u de volgende stappen uit om het CSV-bestand voor te bereiden op een zoekopdracht naar een id-lijst.</span><span class="sxs-lookup"><span data-stu-id="de736-124">After you export the search results or report for a search, perform the following steps to prepare the CSV file for an ID list search.</span></span> <span data-ttu-id="de736-125">Dit CSV-bestand identificeert elk item in de zoekopdracht id-lijst.</span><span class="sxs-lookup"><span data-stu-id="de736-125">This CSV file identifies every item in the ID list search.</span></span>

<span data-ttu-id="de736-126">U kunt een CSV-bestand gebruiken uit een zoekopdracht met SharePoint sites en OneDrive-accounts, maar u kunt alleen postvakitems selecteren voor een zoekopdracht in een lijst met id's.</span><span class="sxs-lookup"><span data-stu-id="de736-126">You can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can only select mailbox items for an ID list search.</span></span> <span data-ttu-id="de736-127">Als u een document selecteert in SharePoint of OneDrive, mislukt de validatie van het CSV-bestand wanneer u een zoekopdracht naar een id-lijst maakt.</span><span class="sxs-lookup"><span data-stu-id="de736-127">If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span>

1. <span data-ttu-id="de736-128">Open het **Results.csv** **of niet-geïndexeerd Items.csv** bestand in Excel.</span><span class="sxs-lookup"><span data-stu-id="de736-128">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span>

2. <span data-ttu-id="de736-129">Typ **ja** **in** de kolom Geselecteerd in de cel die overeenkomt met het item dat u wilt zoeken.</span><span class="sxs-lookup"><span data-stu-id="de736-129">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for.</span></span> <span data-ttu-id="de736-130">Herhaal deze stap voor elk item dat u wilt zoeken.</span><span class="sxs-lookup"><span data-stu-id="de736-130">Repeat this step for every item that you want to search for.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="de736-131">Wanneer u het CSV-bestand opent in Excel, is de gegevensindeling voor de **kolom Document-id** mogelijk gewijzigd in **Algemeen.**</span><span class="sxs-lookup"><span data-stu-id="de736-131">When you open the CSV file in Excel, the data format for the **Document ID** column may have been changed to **General**.</span></span> <span data-ttu-id="de736-132">Dit resulteert in het weergeven van de document-id voor een item in wetenschappelijke notatie.</span><span class="sxs-lookup"><span data-stu-id="de736-132">This results in displaying the document ID for an item in scientific notation.</span></span> <span data-ttu-id="de736-133">De document-id van '481037338205' wordt bijvoorbeeld weergegeven als '4,81037E+11'.</span><span class="sxs-lookup"><span data-stu-id="de736-133">For example, the document ID of "481037338205" is displayed as "4.81037E+11".</span></span> <span data-ttu-id="de736-134">Als dit gebeurt, moet u de volgende stappen uitvoeren om de  gegevensindeling van de **kolom Document-id** te wijzigen in Getal om de juiste notatie voor de document-id te herstellen.</span><span class="sxs-lookup"><span data-stu-id="de736-134">If this happens, you have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID.</span></span> <span data-ttu-id="de736-135">Als u dit niet doet, mislukt de zoekopdracht id-lijst met het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="de736-135">If you don't do this, the ID list search that uses the CSV file will fail.</span></span>

3. <span data-ttu-id="de736-136">Klik met de rechtermuisknop op de hele **kolom Document-id** en selecteer **Cellen opmaken.**</span><span class="sxs-lookup"><span data-stu-id="de736-136">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>

4. <span data-ttu-id="de736-137">Klik in **het** vak Categorie op **Getal**.</span><span class="sxs-lookup"><span data-stu-id="de736-137">In the **Category** box, click **Number**.</span></span>

5. <span data-ttu-id="de736-138">Wijzig het aantal decimalen in **0** en klik vervolgens op **OK** om de wijzigingen op te slaan.</span><span class="sxs-lookup"><span data-stu-id="de736-138">Change the number of decimal places to **0**, and then click **OK** to save your changes.</span></span> <span data-ttu-id="de736-139">U ziet dat de waarden in de kolom Document-id worden gewijzigd in getallen.</span><span class="sxs-lookup"><span data-stu-id="de736-139">Notice that the values in the Document ID column are changed to numbers.</span></span>

    <span data-ttu-id="de736-140">Hier is een voorbeeld van een CSV-bestand dat klaar is om te worden verzonden voor een zoekopdracht naar inhoud in de lijst met id's.</span><span class="sxs-lookup"><span data-stu-id="de736-140">Here's an example of a CSV file that's ready to be submitted for an ID list content search.</span></span>

    ![Voorbeeld van een CSV-bestand voor een gerichte inhoudszoekactie](../media/SearchIDListCSVFile.png)

6. <span data-ttu-id="de736-142">Sla het CSV-bestand op of gebruik **Opslaan als** om het bestand met een andere bestandsnaam op te slaan.</span><span class="sxs-lookup"><span data-stu-id="de736-142">Save the CSV file or use **Save As** to the save the file with different file name.</span></span> <span data-ttu-id="de736-143">In beide gevallen moet u het bestand opslaan met de CSV-indeling.</span><span class="sxs-lookup"><span data-stu-id="de736-143">In both cases, be sure to save the file with the CSV format.</span></span>

## <a name="create-an-id-list-search"></a><span data-ttu-id="de736-144">Zoeken naar een id-lijst maken</span><span class="sxs-lookup"><span data-stu-id="de736-144">Create an ID list search</span></span>

<span data-ttu-id="de736-145">De volgende stap is het maken van een nieuwe zoekopdracht in de lijst met id's en het CSV-bestand indienen dat u in de vorige stap hebt voorbereid.</span><span class="sxs-lookup"><span data-stu-id="de736-145">The next step is to create a new ID list search and submit the CSV file that you prepared in the previous step.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de736-146">U moet niet meer dan twee dagen na het exporteren van de zoekresultaten of het rapport een zoekopdracht voor een id-lijst maken.</span><span class="sxs-lookup"><span data-stu-id="de736-146">You should create an ID list search no more than 2 days after exporting the search results or report.</span></span> <span data-ttu-id="de736-147">Als de zoekresultaten of het rapport meer dan 2 dagen geleden zijn geëxporteerd, moet u de zoekresultaten of het rapport opnieuw exporteren om bijgewerkte CSV-bestanden te genereren.</span><span class="sxs-lookup"><span data-stu-id="de736-147">If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files.</span></span> <span data-ttu-id="de736-148">Vervolgens kunt u een van de bijgewerkte CSV-bestanden voorbereiden en deze gebruiken om een zoekopdracht naar een id-lijst te maken.</span><span class="sxs-lookup"><span data-stu-id="de736-148">Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span>

1. <span data-ttu-id="de736-149">Ga naar <https://compliance.microsoft.com> en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="de736-149">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="de736-150">Klik in het linker navigatiedeelvenster van het Microsoft 365-compliancecentrum op **Alles weergeven** en klik vervolgens op **Inhoud zoeken**.</span><span class="sxs-lookup"><span data-stu-id="de736-150">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Content search**.</span></span>

3. <span data-ttu-id="de736-151">Klik op **de pagina Inhoud** zoeken op Zoeken op **id-lijst.**</span><span class="sxs-lookup"><span data-stu-id="de736-151">On the **Content search** page, click **Search by ID List**.</span></span>

4. <span data-ttu-id="de736-152">In het **flyout** Zoeken op id-lijst geeft u de zoekfunctie een naam (en beschrijft u deze desgewenst) en klikt u op Bladeren en selecteert u het CSV-bestand dat u in de vorige stap hebt voorbereid. </span><span class="sxs-lookup"><span data-stu-id="de736-152">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span>

    <span data-ttu-id="de736-153">Microsoft 365 probeert het CSV-bestand te valideren.</span><span class="sxs-lookup"><span data-stu-id="de736-153">Microsoft 365 attempts to validate the CSV file.</span></span> <span data-ttu-id="de736-154">Als de validatie mislukt, wordt een foutbericht weergegeven dat u kan helpen bij het oplossen van de validatiefouten.</span><span class="sxs-lookup"><span data-stu-id="de736-154">If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors.</span></span> <span data-ttu-id="de736-155">Het CSV-bestand moet worden gevalideerd om een zoekopdracht in een id-lijst te maken.</span><span class="sxs-lookup"><span data-stu-id="de736-155">The CSV file has to be successfully validated to create an ID list search.</span></span>

5. <span data-ttu-id="de736-156">Nadat het CSV-bestand is gevalideerd, klikt u **op Zoeken om** de zoekopdracht in de lijst met id's te maken.</span><span class="sxs-lookup"><span data-stu-id="de736-156">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span>

    <span data-ttu-id="de736-157">Hier ziet u een voorbeeld van de flyoutpagina van een zoekopdracht in een id-lijst met de gegenereerde query en het geschatte aantal zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="de736-157">Here's an example of the flyout page from an ID list search that shows the query that's generated and the estimated number of search results.</span></span>

    ![Zoekquery voor zoeken in lijst met id's](../media/SearchIDListFlyout.png)

    <span data-ttu-id="de736-159">Het aantal geschatte items dat wordt weergegeven in statistieken voor het zoeken naar id's, moet overeenkomen met het aantal items dat u hebt geselecteerd in het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="de736-159">The number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>

6. <span data-ttu-id="de736-160">Bekijk of exporteert de items die worden geretourneerd door de zoekactie naar de lijst met id's.</span><span class="sxs-lookup"><span data-stu-id="de736-160">Preview or export the items returned by the ID list search.</span></span>

## <a name="more-information"></a><span data-ttu-id="de736-161">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="de736-161">More information</span></span>

<span data-ttu-id="de736-162">Als u een postvak verplaatst na het maken van een zoekopdracht naar de lijst met id's, worden de opgegeven items niet door de query voor de zoekopdracht retourneerd.</span><span class="sxs-lookup"><span data-stu-id="de736-162">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items.</span></span> <span data-ttu-id="de736-163">De eigenschap **DocumentId** voor postvakitems wordt namelijk gewijzigd wanneer een postvak wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="de736-163">That's because the **DocumentId** property for mailbox items is changed when a mailbox is moved.</span></span> <span data-ttu-id="de736-164">In het zeldzame geval dat een postvak wordt verplaatst nadat u een zoekopdracht naar een id-lijst hebt gemaakt, moet u een nieuwe zoekactie naar inhoud maken (of de zoekresultaten bijwerken voor een bestaande zoekopdracht) en vervolgens de zoekresultaten of het rapport exporteren om bijgewerkte CSV-bestanden te genereren die kunnen worden gebruikt om een nieuwe zoekopdracht in de lijst met id's te maken.</span><span class="sxs-lookup"><span data-stu-id="de736-164">In the rare instance when a mailbox is moved after you create an ID list search, you should create a new Content search (or update the search results for an existing search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span>
