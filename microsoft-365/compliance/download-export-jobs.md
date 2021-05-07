---
title: Documenten exporteren naar het account van uw Azure Storage organisatie
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
ms.custom: seo-marvel-mar2020
description: Exporteert documenten in een revisieset naar een Azure Storage account en gebruik Azure Storage Explorer om ze te downloaden naar een lokale computer.
ms.openlocfilehash: dfb3892f31e857d4744f6da337c924efaa87ab11
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "52162567"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a><span data-ttu-id="06594-103">Documenten in een revisieset exporteren naar een Azure Storage account</span><span class="sxs-lookup"><span data-stu-id="06594-103">Export documents in a review set to an Azure Storage account</span></span>

<span data-ttu-id="06594-104">Wanneer u documenten exporteert uit een revisieset in een Advanced eDiscovery, hebt u de optie om ze te exporteren naar een Azure Storage account dat door uw organisatie wordt beheerd.</span><span class="sxs-lookup"><span data-stu-id="06594-104">When you export documents from a review set in an Advanced eDiscovery case, you have the option to export them to an Azure Storage account managed by your organization.</span></span> <span data-ttu-id="06594-105">Als u deze optie hebt gebruikt, worden de documenten geüpload naar uw Azure Storage locatie.</span><span class="sxs-lookup"><span data-stu-id="06594-105">If you used this option, the documents are uploaded to your Azure Storage location.</span></span> <span data-ttu-id="06594-106">Nadat ze zijn geëxporteerd, kunt u de documenten openen (en downloaden naar een lokale computer of andere locatie) met behulp van de Azure Storage Explorer.</span><span class="sxs-lookup"><span data-stu-id="06594-106">After they are exported, you can access the documents (and download them to a local computer or other location) by using the Azure Storage Explorer.</span></span> <span data-ttu-id="06594-107">In dit artikel vindt u instructies voor het exporteren van documenten naar uw Azure Storage-account en het gebruik van de Azure Storage Explorer om verbinding te maken met een Azure Storage locatie om de geëxporteerde documenten te downloaden.</span><span class="sxs-lookup"><span data-stu-id="06594-107">This article provides instructions for how to export documents to your Azure Storage account and the use the Azure Storage Explorer to connect to an Azure Storage location to download the exported documents.</span></span> <span data-ttu-id="06594-108">Zie Gebruik Azure Storage Explorer voor [meer Azure Storage Explorer.](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)</span><span class="sxs-lookup"><span data-stu-id="06594-108">For more information about Azure Storage Explorer, see [Use Azure Storage Explorer](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="before-you-export-documents-from-a-review-set"></a><span data-ttu-id="06594-109">Voordat u documenten exporteert uit een revisieset</span><span class="sxs-lookup"><span data-stu-id="06594-109">Before you export documents from a review set</span></span>

- <span data-ttu-id="06594-110">U moet een SAS-token (Shared Access Signature) opgeven voor uw Azure Storage-account en de URL voor een specifieke container in het opslagaccount om documenten uit een revisieset te exporteren.</span><span class="sxs-lookup"><span data-stu-id="06594-110">You need to provide a shared access signature (SAS) token for your Azure Storage account and the URL for a specific container in the storage account to export documents from a review set.</span></span> <span data-ttu-id="06594-111">Zorg ervoor dat u deze bij de hand hebt (bijvoorbeeld gekopieerd naar een tekstbestand) wanneer u stap 2 uit te voeren</span><span class="sxs-lookup"><span data-stu-id="06594-111">Be sure to have these at hand (for example, copied to a text file) when you perform Step 2</span></span>

  - <span data-ttu-id="06594-112">**SAS-token:** Zorg ervoor dat u het SAS-token krijgt voor uw Azure Storage account (en niet voor de container).</span><span class="sxs-lookup"><span data-stu-id="06594-112">**SAS token**: Be sure to get the SAS token is for your Azure Storage account (and not for the container).</span></span> <span data-ttu-id="06594-113">U kunt een SAS-token voor uw account genereren in Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="06594-113">You can generate an SAS token for your account in Azure Storage.</span></span> <span data-ttu-id="06594-114">Hiervoor gaat u naar het Azure Storage account en selecteert u  **Toegangshandtekening** delen onder de Instellingen instellingen in het opslagaccountblad.</span><span class="sxs-lookup"><span data-stu-id="06594-114">To do this, go to the Azure Storage account, and select **Share access signature** under the **Settings** settings in the storage account blade.</span></span> <span data-ttu-id="06594-115">Gebruik de standaardinstellingen en sta alle resourcetypen toe wanneer u het SAS-token genereert.</span><span class="sxs-lookup"><span data-stu-id="06594-115">Use the default settings and allow all resource types when you generate the SAS token.</span></span>

  - <span data-ttu-id="06594-116">**Container-URL:** u moet een container maken om de documenten van de revisieset te uploaden naar en vervolgens een kopie van de URL voor de container krijgen. `https://ediscoverydata.blob.core.windows.net/exportdata`bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="06594-116">**Container URL**: You need to create a container to upload the review set documents to, and then get a copy of the URL for the container; for example, `https://ediscoverydata.blob.core.windows.net/exportdata`.</span></span> <span data-ttu-id="06594-117">Als u de URL wilt krijgen, gaat u naar de container in Azure Storage en **selecteert** u Eigenschappen onder de **Instellingen** sectie in het containerblad.</span><span class="sxs-lookup"><span data-stu-id="06594-117">To get the URL, go to the container in Azure Storage, and select **Properties** under the **Settings** section in the container blade.</span></span>

- <span data-ttu-id="06594-118">Download en installeer de Azure Storage Explorer.</span><span class="sxs-lookup"><span data-stu-id="06594-118">Download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="06594-119">Zie het Azure Storage Explorer [voor instructies.](https://go.microsoft.com/fwlink/p/?LinkId=544842)</span><span class="sxs-lookup"><span data-stu-id="06594-119">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="06594-120">U gebruikt dit hulpprogramma om verbinding te maken met de container in Azure Storage account en de documenten te downloaden die u hebt geëxporteerd in stap 1.</span><span class="sxs-lookup"><span data-stu-id="06594-120">You use this tool to connect to the container in your Azure Storage account and download the documents that you exported in Step 1.</span></span>

## <a name="step-1-export-the-documents-from-a-review-set"></a><span data-ttu-id="06594-121">Stap 1: De documenten exporteren uit een revisieset</span><span class="sxs-lookup"><span data-stu-id="06594-121">Step 1: Export the documents from a review set</span></span>

<span data-ttu-id="06594-122">De eerste stap is het maken van een exportklus om documenten uit een revisieset te exporteren.</span><span class="sxs-lookup"><span data-stu-id="06594-122">The first step is to create an export job to export documents out of a review set.</span></span> <span data-ttu-id="06594-123">Zie Documenten exporteren uit een revisieset voor meer gedetailleerde instructies over alle [exportopties.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="06594-123">For more detailed instructions about all the export options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="06594-124">In de volgende procedure worden de instellingen belicht voor het exporteren van documenten naar het account Azure Storage uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="06594-124">The following procedure highlights the settings to export documents to your organization's Azure Storage account.</span></span>

1. <span data-ttu-id="06594-125">Open in Microsoft 365 compliancecentrum het hoofd- Advanced eDiscovery, selecteer  het tabblad Revisiesets en selecteer vervolgens de revisieset die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="06594-125">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="06594-126">Klik in de revisieset op **Actie**  >  **exporteren.**</span><span class="sxs-lookup"><span data-stu-id="06594-126">In the review set, click **Action** > **Export**.</span></span>

3. <span data-ttu-id="06594-127">Typ op **de flyoutpagina** Exportopties een naam (vereist) en beschrijving (optioneel) voor de export.</span><span class="sxs-lookup"><span data-stu-id="06594-127">On the **Export options** flyout page, type a name (required) and description (optional) for the export.</span></span>

4. <span data-ttu-id="06594-128">Configureer de instellingen in de secties documenten, metagegevens, inhoud en opties.</span><span class="sxs-lookup"><span data-stu-id="06594-128">Configure the settings in the documents, metadata, content, and options sections.</span></span> <span data-ttu-id="06594-129">Zie Documenten exporteren uit een revisieset voor meer informatie over [deze instellingen.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="06594-129">For more information about these settings, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

5. <span data-ttu-id="06594-130">Selecteer in **de sectie Uitvoeropties** de **optie Gecondenseerde** adreslijststructuur die naar uw Azure Storage account wordt geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="06594-130">In the **Output options** section, select the **Condensed directory structure exported to your Azure Storage account** option.</span></span>

6. <span data-ttu-id="06594-131">Plak de container-URL en het SAS-token voor uw opslagaccount in de bijbehorende velden.</span><span class="sxs-lookup"><span data-stu-id="06594-131">Paste the container URL and the SAS token for your storage account in the corresponding fields.</span></span>

   ![De verbindings-URL en het SAS-token in de bijbehorende velden plakken](../media/AzureStorageOutputOptions.png)

7. <span data-ttu-id="06594-133">Klik **op Exporteren** om de exportklus te maken.</span><span class="sxs-lookup"><span data-stu-id="06594-133">Click **Export** to create the export job.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="06594-134">Stap 2: De SAS-URL van de exportklus verkrijgen</span><span class="sxs-lookup"><span data-stu-id="06594-134">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="06594-135">De volgende stap is het verkrijgen van de SAS-URL die wordt gegenereerd nadat u de exportklus hebt gemaakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="06594-135">The next step is to obtain the SAS URL that's generated after you create the export job in Step 1.</span></span> <span data-ttu-id="06594-136">U gebruikt de SAS-URL om verbinding te maken met de container in uw Azure Storage account waar u de revisiesetdocumenten naar hebt geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="06594-136">You use the SAS URL to connect to the container in your Azure Storage account that you exported the review set documents to.</span></span>

1. <span data-ttu-id="06594-137">Ga op **Advanced eDiscovery** pagina naar de zaak en klik vervolgens op **het tabblad** Exporteren.</span><span class="sxs-lookup"><span data-stu-id="06594-137">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="06594-138">Klik op **het** tabblad Export op de exportklus die u wilt downloaden.</span><span class="sxs-lookup"><span data-stu-id="06594-138">On the **Exports** tab, click the export job that you want to download.</span></span> <span data-ttu-id="06594-139">Dit is de exportklus die u hebt gemaakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="06594-139">This is the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="06594-140">Kopieer op de flyoutpagina onder **Locaties** de SAS-URL die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="06594-140">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="06594-141">Zo nodig kunt u het bestand opslaan in een tekstbestand, zodat u het in stap 3 kunt openen.</span><span class="sxs-lookup"><span data-stu-id="06594-141">If necessary, you can save it to a text file so you can access it in Step 3.</span></span>

   ![De SAS-URL kopiëren die wordt weergegeven onder Locaties](../media/eDiscoExportJob.png)

   > [!TIP]
   > <span data-ttu-id="06594-143">De SAS-URL die wordt weergegeven in de exportklus is een samenvoeging van de CONTAINER-URL en het SAS-token voor uw Azure Storage account.</span><span class="sxs-lookup"><span data-stu-id="06594-143">The SAS URL that's displayed in the export job is a concatenation of the container URL and the SAS token for your Azure Storage account.</span></span> <span data-ttu-id="06594-144">U kunt deze kopiëren vanuit de exportklus of zelf maken door de URL en het SAS-token te combineren.</span><span class="sxs-lookup"><span data-stu-id="06594-144">You can copy it from the export job or create it yourself by combining the URL and the SAS token.</span></span>

## <a name="step-3-connect-to-the-azure-storage-container"></a><span data-ttu-id="06594-145">Stap 3: Verbinding maken naar de Azure Storage container</span><span class="sxs-lookup"><span data-stu-id="06594-145">Step 3: Connect to the Azure Storage container</span></span>

<span data-ttu-id="06594-146">De laatste stap is om de Azure Storage Explorer en de SAS-URL te gebruiken om verbinding te maken met de container in uw Azure Storage-account en de geëxporteerde documenten naar een lokale computer te downloaden.</span><span class="sxs-lookup"><span data-stu-id="06594-146">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the container in your Azure Storage account and download the exported documents to a local computer.</span></span>

1. <span data-ttu-id="06594-147">Start de Azure Storage Explorer die u hebt gedownload en geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="06594-147">Start the Azure Storage Explorer that you downloaded and installed.</span></span>

2. <span data-ttu-id="06594-148">Klik op **het pictogram Verbinding maken dialoogvenster** openen.</span><span class="sxs-lookup"><span data-stu-id="06594-148">Click the **Open Connect Dialog** icon.</span></span>

   ![Klik op het pictogram Account toevoegen](../media/AzureStorageConnect.png)

3. <span data-ttu-id="06594-150">Klik op **Verbinding maken pagina Azure Storage** op Blob **container.**</span><span class="sxs-lookup"><span data-stu-id="06594-150">On the **Connect to Azure Storage** page, click **Blob container**.</span></span>

4. <span data-ttu-id="06594-151">Selecteer op **de pagina Verificatiemethode** selecteren de optie **Sas (Shared Access signature)** en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="06594-151">On the **Select Authentication Method** page, select the **Shared access signature (SAS)** option and then click **Next**.</span></span>

5. <span data-ttu-id="06594-152">Plak op **de pagina Verbindingsgegevens** invoeren de SAS-URL (die u hebt verkregen in de exportklus in stap 2) in het vak **Blob Container SAS URL.**</span><span class="sxs-lookup"><span data-stu-id="06594-152">On the **Enter Connection Info** page, paste the SAS URL (that you obtained in the export job in Step 2) in the **Blob Container SAS URL** box.</span></span>

    ![De SAS-URL in het vak URI plakken](../media/AzureStorageConnect3.png)

    <span data-ttu-id="06594-154">U ziet dat de containernaam wordt weergegeven in het **vak Weergavenaam.**</span><span class="sxs-lookup"><span data-stu-id="06594-154">Notice that the container name is displayed in the **Display name** box.</span></span> <span data-ttu-id="06594-155">U kunt deze naam bewerken.</span><span class="sxs-lookup"><span data-stu-id="06594-155">You can edit this name.</span></span>

6. <span data-ttu-id="06594-156">Klik **op Volgende** om de **overzichtspagina weer te** geven en klik vervolgens op **Verbinding maken.**</span><span class="sxs-lookup"><span data-stu-id="06594-156">Click **Next** to display the **summary** page and then click **Connect**.</span></span>

    <span data-ttu-id="06594-157">Het **knooppunt blobcontainers** **(onder Storage Accounts**  >  **(Bijgevoegde containers)** wordt \> geopend.</span><span class="sxs-lookup"><span data-stu-id="06594-157">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span>

    ![Taken exporteren in het knooppunt Blobs containers](../media/AzureStorageConnect5.png)

    <span data-ttu-id="06594-159">De container bevat een container met de weergavenaam uit stap 5.</span><span class="sxs-lookup"><span data-stu-id="06594-159">It contains a container named with the display name from step 5.</span></span> <span data-ttu-id="06594-160">Deze container bevat een map voor elke exportklus die u hebt gedownload naar de container in uw Azure Storage account.</span><span class="sxs-lookup"><span data-stu-id="06594-160">This container contains a folder for each export job that you've downloaded to the container in your Azure Storage account.</span></span> <span data-ttu-id="06594-161">Deze mappen worden benoemd met een id die overeenkomt met de id van de exportklus.</span><span class="sxs-lookup"><span data-stu-id="06594-161">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="06594-162">U kunt deze export-ID's (en de  naam van de export) vinden onder Ondersteuningsinformatie op  de flyoutpagina voor elke voorbereiding van gegevens voor **exporttaken** die worden weergegeven op het tabblad Taken in het Advanced eDiscovery geval.</span><span class="sxs-lookup"><span data-stu-id="06594-162">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab in the Advanced eDiscovery case.</span></span>

7. <span data-ttu-id="06594-163">Dubbelklik op de exportmap om deze te openen.</span><span class="sxs-lookup"><span data-stu-id="06594-163">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="06594-164">Er wordt een lijst met mappen en exportrapporten weergegeven.</span><span class="sxs-lookup"><span data-stu-id="06594-164">A list of folders and export reports is displayed.</span></span>

    ![De exportmap bevat geëxporteerde bestanden en exportrapporten](../media/AzureStorageConnect6.png)

8. <span data-ttu-id="06594-166">Als u alle inhoud van de  exportklus wilt exporteren, klikt u op de pijl-omhoog om terug te gaan naar de map Exportklus en klikt u vervolgens op **Downloaden.**</span><span class="sxs-lookup"><span data-stu-id="06594-166">To export all contents from the export job, click the **Up** arrow to go back to the export job folder, and then click **Download**.</span></span>

9. <span data-ttu-id="06594-167">Geef de locatie op waar u de geëxporteerde bestanden wilt downloaden en klik vervolgens op Map selecteren.</span><span class="sxs-lookup"><span data-stu-id="06594-167">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="06594-168">Met Azure Storage Explorer start u het downloadproces.</span><span class="sxs-lookup"><span data-stu-id="06594-168">The Azure Storage Explorer starts the download process.</span></span> <span data-ttu-id="06594-169">De status van het downloaden van de geëxporteerde items wordt weergegeven in het **deelvenster** Activiteiten.</span><span class="sxs-lookup"><span data-stu-id="06594-169">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="06594-170">Er wordt een bericht weergegeven wanneer de download is voltooid.</span><span class="sxs-lookup"><span data-stu-id="06594-170">A message is displayed when the download is complete.</span></span>

> [!NOTE]
> <span data-ttu-id="06594-171">In plaats van de hele exportklus in Azure Storage Explorer downloaden, kunt u specifieke items selecteren die u wilt downloaden en weergeven.</span><span class="sxs-lookup"><span data-stu-id="06594-171">Instead of downloading the entire export job in Azure Storage Explorer, you can select specific items to download and view.</span></span>

## <a name="more-information"></a><span data-ttu-id="06594-172">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="06594-172">More information</span></span>

- <span data-ttu-id="06594-173">De map Taak exporteren bevat de volgende items.</span><span class="sxs-lookup"><span data-stu-id="06594-173">The export job folder contains the following items.</span></span> <span data-ttu-id="06594-174">De werkelijke items in de exportmap worden bepaald door de exportopties die zijn geconfigureerd toen de exportklus werd gemaakt.</span><span class="sxs-lookup"><span data-stu-id="06594-174">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="06594-175">Zie Documenten exporteren uit een revisieset voor meer informatie over [deze opties.](export-documents-from-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="06594-175">For more information about these options, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

  - <span data-ttu-id="06594-176">Export_load_file.csv: Dit CSV-bestand is een detailexportrapport met informatie over elk geëxporteerd document.</span><span class="sxs-lookup"><span data-stu-id="06594-176">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="06594-177">Het bestand bestaat uit een kolom voor elke eigenschap metagegevens voor een document.</span><span class="sxs-lookup"><span data-stu-id="06594-177">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="06594-178">Zie de kolom Geëxporteerde veldnaam in de tabel  in documentmetagegevensvelden in Advanced eDiscovery voor een lijst en beschrijving van de metagegevens die in dit [rapport zijn opgenomen.](document-metadata-fields-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="06594-178">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-advanced-ediscovery.md).</span></span>

  - <span data-ttu-id="06594-179">Summary.txt: Een tekstbestand met een overzicht van de export, inclusief exportstatistieken.</span><span class="sxs-lookup"><span data-stu-id="06594-179">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>

  - <span data-ttu-id="06594-180">Extracted_text_files: Deze map bevat een tekstbestandsversie van elk geëxporteerd document.</span><span class="sxs-lookup"><span data-stu-id="06594-180">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>

  - <span data-ttu-id="06594-181">NativeFiles: Deze map bevat een oorspronkelijke bestandsversie van elk geëxporteerd document.</span><span class="sxs-lookup"><span data-stu-id="06594-181">NativeFiles: This folder contains a native file version of each exported document.</span></span>

  - <span data-ttu-id="06594-182">Error_files: Deze map bevat de volgende items wanneer de exportklus foutbestanden bevat:</span><span class="sxs-lookup"><span data-stu-id="06594-182">Error_files: This folder includes the following items when the export job contains any error files:</span></span>

    - <span data-ttu-id="06594-183">ExtractionError.csv: Dit CSV-bestand bevat de beschikbare metagegevens voor bestanden die niet correct zijn geëxtraheerd uit het bovenliggende item.</span><span class="sxs-lookup"><span data-stu-id="06594-183">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>

    - <span data-ttu-id="06594-184">ProcessingError: Deze map bevat documenten met verwerkingsfouten.</span><span class="sxs-lookup"><span data-stu-id="06594-184">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="06594-185">Deze inhoud is op itemniveau, wat betekent dat als een bijlage een verwerkingsfout heeft, het document met de bijlage ook in deze map wordt opgenomen.</span><span class="sxs-lookup"><span data-stu-id="06594-185">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
