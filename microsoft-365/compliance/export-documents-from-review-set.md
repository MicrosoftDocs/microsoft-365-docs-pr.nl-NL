---
title: Documenten exporteren vanuit een controleset
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
ms.assetid: ''
description: Informatie over het selecteren en exporteren van inhoud uit een Advanced eDiscovery voor presentaties of externe beoordelingen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "52162570"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="901dc-103">Documenten exporteren uit een revisieset in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="901dc-103">Export documents from a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="901dc-104">Met Exporteren kunnen gebruikers de inhoud aanpassen die is opgenomen in het downloadpakket wanneer u een document exporteert vanuit een revisieset in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="901dc-104">Export allows users to customize the content that is included in the download package when you export document from a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="901dc-105">Documenten exporteren uit een revisieset:</span><span class="sxs-lookup"><span data-stu-id="901dc-105">To export documents from a review set:</span></span>

1. <span data-ttu-id="901dc-106">Open in Microsoft 365 compliancecentrum het hoofd- Advanced eDiscovery, selecteer  het tabblad Revisiesets en selecteer vervolgens de revisieset die u wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="901dc-106">In the Microsoft 365 compliance center, open the Advanced eDiscovery case, select the **Review sets** tab, and then select the review set that you want to export.</span></span>

2. <span data-ttu-id="901dc-107">Klik in de revisieset op **Actie**  >  **exporteren.**</span><span class="sxs-lookup"><span data-stu-id="901dc-107">In the review set, click **Action** > **Export**.</span></span>

   <span data-ttu-id="901dc-108">Met het hulpmiddel Exporteren wordt de flyoutpagina weergegeven met de instellingen voor het configureren van de export.</span><span class="sxs-lookup"><span data-stu-id="901dc-108">The Export tool displays the flyout page with the settings to configure the export.</span></span> <span data-ttu-id="901dc-109">Sommige opties zijn standaard geselecteerd, maar u kunt deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="901dc-109">Some options are selected by default, but you can change these.</span></span> <span data-ttu-id="901dc-110">Zie de volgende sectie voor beschrijvingen van de exportopties die u kunt configureren.</span><span class="sxs-lookup"><span data-stu-id="901dc-110">See the following section for descriptions of the export options that you can configure.</span></span>

   ![Configuratieopties voor het exporteren van items uit een revisieset](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. <span data-ttu-id="901dc-112">Nadat u de export hebt geconfigureerd, klikt u **op Exporteren om** het exportproces te starten.</span><span class="sxs-lookup"><span data-stu-id="901dc-112">After you configure the export, click **Export** to start the export process.</span></span> <span data-ttu-id="901dc-113">Afhankelijk van de optie die u **hebt** geselecteerd in de sectie Uitvoeropties, kunt u de exportbestanden openen via direct downloaden of in het account van Azure Storage organisatie.</span><span class="sxs-lookup"><span data-stu-id="901dc-113">Depending on the option that you selected in **Output options** section, you can access the export files by direct download or in your organization's Azure Storage account.</span></span>

> [!NOTE]
> <span data-ttu-id="901dc-114">Exporttaken blijven behouden voor de levensduur van de zaak.</span><span class="sxs-lookup"><span data-stu-id="901dc-114">Export jobs are retained for the life of the case.</span></span> <span data-ttu-id="901dc-115">U moet de inhoud van een exportklus echter binnen 30 dagen nadat de exportklus is voltooid, downloaden.</span><span class="sxs-lookup"><span data-stu-id="901dc-115">However, you must download the content from an export job within 30 days after the export job is complete.</span></span>

## <a name="export-options"></a><span data-ttu-id="901dc-116">Exportopties</span><span class="sxs-lookup"><span data-stu-id="901dc-116">Export options</span></span>

<span data-ttu-id="901dc-117">Gebruik de volgende opties om de export te configureren.</span><span class="sxs-lookup"><span data-stu-id="901dc-117">Use the following options to configure the export.</span></span>

- <span data-ttu-id="901dc-118">**Exportnaam:** naam van de exportklus.</span><span class="sxs-lookup"><span data-stu-id="901dc-118">**Export name**: Name of the export job.</span></span>

- <span data-ttu-id="901dc-119">**Beschrijving**: Veld Vrije tekst om een beschrijving toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="901dc-119">**Description**: Free-text field for you to add a description.</span></span>

- <span data-ttu-id="901dc-120">**Deze documenten exporteren**</span><span class="sxs-lookup"><span data-stu-id="901dc-120">**Export these documents**</span></span>

  - <span data-ttu-id="901dc-121">**Alleen geselecteerde documenten:** deze optie exporteert alleen de documenten die momenteel zijn geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="901dc-121">**Selected documents only**: This option exports only the documents that are currently selected.</span></span>
  
  - <span data-ttu-id="901dc-122">**Alle documenten in de revisieset:** met deze optie worden alle documenten in de revisieset geexporteert.</span><span class="sxs-lookup"><span data-stu-id="901dc-122">**All documents in the review set**: This option exports all documents in the review set.</span></span>

- <span data-ttu-id="901dc-123">**Metagegevens**</span><span class="sxs-lookup"><span data-stu-id="901dc-123">**Metadata**</span></span>
  
  - <span data-ttu-id="901dc-124">**Bestand laden:** dit bestand bevat metagegevens voor elk bestand.</span><span class="sxs-lookup"><span data-stu-id="901dc-124">**Load file**: This file contains metadata for each file.</span></span> <span data-ttu-id="901dc-125">Dit bestand kan meestal worden ingenomen door eDiscovery-hulpprogramma's van derden.</span><span class="sxs-lookup"><span data-stu-id="901dc-125">This file can typically be ingested by third-party eDiscovery tools.</span></span> <span data-ttu-id="901dc-126">Zie Metagegevensvelden in documenten [in](document-metadata-fields-in-Advanced-eDiscovery.md)Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="901dc-126">For more information about what fields are included, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>
  
  - <span data-ttu-id="901dc-127">**Tags:** Wanneer u deze optie hebt geselecteerd, wordt labelingsgegevens opgenomen in het laadbestand.</span><span class="sxs-lookup"><span data-stu-id="901dc-127">**Tags**: When selected, tagging information is included in the load file.</span></span>

- <span data-ttu-id="901dc-128">**Content**</span><span class="sxs-lookup"><span data-stu-id="901dc-128">**Content**</span></span>
  
  - <span data-ttu-id="901dc-129">**Oorspronkelijke bestanden:** Schakel dit selectievakje in om de oorspronkelijke bestanden van de documenten in de revisieset op te nemen.</span><span class="sxs-lookup"><span data-stu-id="901dc-129">**Native files**: Select this checkbox to include the native files of the documents in the review set.</span></span> <span data-ttu-id="901dc-130">Als u ervoor kiest om native bestanden te exporteren, hebt u de volgende opties voor het exporteren van chatgesprekken.</span><span class="sxs-lookup"><span data-stu-id="901dc-130">If you choose to export native files, you have the following options for how export chat conversations.</span></span>
  
  - <span data-ttu-id="901dc-131">**Gespreksopties**</span><span class="sxs-lookup"><span data-stu-id="901dc-131">**Conversation options**</span></span>

    - <span data-ttu-id="901dc-132">**Gespreksbestanden:** Deze optie exporteert gereconstrueerde chatgesprekken.</span><span class="sxs-lookup"><span data-stu-id="901dc-132">**Conversation files**: This option exports reconstructed chat conversations.</span></span> <span data-ttu-id="901dc-133">Deze indeling bevat gesprekken in een formulier dat lijkt op wat gebruikers zien in de oorspronkelijke toepassing.</span><span class="sxs-lookup"><span data-stu-id="901dc-133">This format presents conversations in a form that resembles what users see in the native application.</span></span>

    - <span data-ttu-id="901dc-134">**Afzonderlijke chatberichten:** met deze optie worden de oorspronkelijke gespreksbestanden opgeslagen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="901dc-134">**Individual chat messages**: This option exports the original conversation files as they are stored in Microsoft 365.</span></span>

- <span data-ttu-id="901dc-135">**Opties**</span><span class="sxs-lookup"><span data-stu-id="901dc-135">**Options**</span></span>

  - <span data-ttu-id="901dc-136">**Tekstbestanden:**- Deze optie bevat de uitgepakte tekstversies van oorspronkelijke bestanden in de export.</span><span class="sxs-lookup"><span data-stu-id="901dc-136">**Text files**: - This option includes the extracted text versions of native files in the export.</span></span>
  
  - <span data-ttu-id="901dc-137">**Redacted natives vervangen** door geconverteerde PDF-bestanden: als er tijdens de revisie opnieuw uitgevoerde PDF-bestanden worden gegenereerd, zijn deze bestanden beschikbaar voor export.</span><span class="sxs-lookup"><span data-stu-id="901dc-137">**Replace redacted natives with converted PDFs**: If redacted PDF files are generated during review, these files are available for export.</span></span> <span data-ttu-id="901dc-138">U kunt ervoor kiezen om alleen de oorspronkelijke bestanden te exporteren die opnieuw zijn uitgevoerd (door deze optie niet te selecteren) of u kunt deze optie selecteren om de PDF-bestanden te exporteren die de werkelijke redactions bevatten.</span><span class="sxs-lookup"><span data-stu-id="901dc-138">You can choose to export only the native files that were redacted (by not selecting this option) or you can select this option to export the PDF files that contain the actual redactions.</span></span>

- <span data-ttu-id="901dc-139">**Uitvoeropties:** Geëxporteerde inhoud kan rechtstreeks via een webbrowser worden gedownload of kan worden verzonden naar een Azure Storage account.</span><span class="sxs-lookup"><span data-stu-id="901dc-139">**Output options**: Exported content is either available for download directly through a web browser or can be sent to an Azure Storage account.</span></span> <span data-ttu-id="901dc-140">Met de eerste twee opties kunt u direct downloaden.</span><span class="sxs-lookup"><span data-stu-id="901dc-140">The first two options enable direct download.</span></span>
  
  - <span data-ttu-id="901dc-141">**Losse bestanden en PST's**(e-mail wordt indien mogelijk toegevoegd aan PST's) : Bestanden worden geëxporteerd in een indeling die lijkt op de oorspronkelijke adreslijststructuur die gebruikers in hun eigen toepassingen zien.</span><span class="sxs-lookup"><span data-stu-id="901dc-141">**Loose files and PSTs (email is added to PSTs when possible)**: Files are exported in a format that resembles the original directory structure seen by users in their native applications.</span></span>  <span data-ttu-id="901dc-142">Zie de sectie Losse bestanden en [PST-exportstructuur voor meer](#loose-files-and-pst-export-structure) informatie.</span><span class="sxs-lookup"><span data-stu-id="901dc-142">For more information, see the [Loose files and PST export structure](#loose-files-and-pst-export-structure) section.</span></span>
  
  - <span data-ttu-id="901dc-143">**Gecondenseerde** adreslijststructuur: Bestanden worden geëxporteerd en opgenomen in de download.</span><span class="sxs-lookup"><span data-stu-id="901dc-143">**Condensed directory structure**: Files are exported and included in the download.</span></span>
  
  - <span data-ttu-id="901dc-144">**Gecondenseerde** adreslijststructuur geëxporteerd naar uw Azure Storage account: Bestanden worden geëxporteerd naar het account Azure Storage uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="901dc-144">**Condensed directory structure exported to your Azure Storage account**: Files are exported to your organization's Azure Storage account.</span></span> <span data-ttu-id="901dc-145">Voor deze optie moet u de URL opgeven voor de container in Azure Storage account om de bestanden naar te exporteren.</span><span class="sxs-lookup"><span data-stu-id="901dc-145">For this option, you have to provide the URL for the container in your Azure Storage account to export the files to.</span></span> <span data-ttu-id="901dc-146">U moet ook het SAS-token (Shared Access Signature) voor uw Azure Storage geven.</span><span class="sxs-lookup"><span data-stu-id="901dc-146">You also have to provide the shared access signature (SAS) token for your Azure Storage account.</span></span> <span data-ttu-id="901dc-147">Zie Documenten exporteren in een revisieset naar een Azure Storage [account voor meer informatie.](download-export-jobs.md)</span><span class="sxs-lookup"><span data-stu-id="901dc-147">For more information, see [Export documents in a review set to an Azure Storage account](download-export-jobs.md).</span></span>

<span data-ttu-id="901dc-148">In de volgende secties wordt de mapstructuur voor losse bestanden en de opties voor een verkorte adreslijststructuur beschreven.</span><span class="sxs-lookup"><span data-stu-id="901dc-148">The following sections describe the folder structure for loose files and condensed directory structure options.</span></span>

### <a name="loose-files-and-pst-export-structure"></a><span data-ttu-id="901dc-149">Losse bestanden en PST-exportstructuur</span><span class="sxs-lookup"><span data-stu-id="901dc-149">Loose files and PST export structure</span></span>

<span data-ttu-id="901dc-150">Als u deze exportoptie selecteert, is de geëxporteerde inhoud ingedeeld in de volgende structuur:</span><span class="sxs-lookup"><span data-stu-id="901dc-150">If you select this export option, the exported content is organized in the following structure:</span></span>

- <span data-ttu-id="901dc-151">Hoofdmap: Deze map in benoemde ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="901dc-151">Root folder: This folder in named ExportName.zip</span></span>
  
  - <span data-ttu-id="901dc-152">Export_load_file.csv: Het metagegevensbestand.</span><span class="sxs-lookup"><span data-stu-id="901dc-152">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="901dc-153">Summary.csv: Een overzichtsbestand dat ook exportstatistieken bevat.</span><span class="sxs-lookup"><span data-stu-id="901dc-153">Summary.csv: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="901dc-154">Exchange: Deze map bevat alle inhoud van Exchange in de oorspronkelijke bestandsindeling.</span><span class="sxs-lookup"><span data-stu-id="901dc-154">Exchange: This folder contains all content from Exchange in native file format.</span></span> <span data-ttu-id="901dc-155">Natives-bestanden worden vervangen door ge redacted PDF's als u de optie **Redacted Natives** vervangen door geconverteerde PDF's hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="901dc-155">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>
  
  - <span data-ttu-id="901dc-156">SharePoint: Deze map bevat alle oorspronkelijke inhoud van SharePoint in een oorspronkelijke bestandsindeling.</span><span class="sxs-lookup"><span data-stu-id="901dc-156">SharePoint: This folder contains all native content from SharePoint in a native file format.</span></span> <span data-ttu-id="901dc-157">Natives-bestanden worden vervangen door ge redacted PDF's als u de optie **Redacted Natives** vervangen door geconverteerde PDF's hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="901dc-157">Natives files are replaced with redacted PDFs if you selected the **Replace redacted natives with converted PDFs** option.</span></span>

### <a name="condensed-directory-structure"></a><span data-ttu-id="901dc-158">Gecondenseerde adreslijststructuur</span><span class="sxs-lookup"><span data-stu-id="901dc-158">Condensed directory structure</span></span>

- <span data-ttu-id="901dc-159">Hoofdmap: Deze map heeft de naam ExportName.zip</span><span class="sxs-lookup"><span data-stu-id="901dc-159">Root folder: This folder is named ExportName.zip</span></span>
  
  - <span data-ttu-id="901dc-160">Export_load_file.csv: Het metagegevensbestand.</span><span class="sxs-lookup"><span data-stu-id="901dc-160">Export_load_file.csv: The metadata file.</span></span>
  
  - <span data-ttu-id="901dc-161">Summary.txt: Een overzichtsbestand dat ook exportstatistieken bevat.</span><span class="sxs-lookup"><span data-stu-id="901dc-161">Summary.txt: A summary file that also contains export statistics.</span></span>
  
  - <span data-ttu-id="901dc-162">NativeFiles: Deze map bevat alle oorspronkelijke bestanden die zijn geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="901dc-162">NativeFiles: This folder contains all the native files that were exported.</span></span> <span data-ttu-id="901dc-163">Als u opnieuw uitgevoerde PDF-bestanden exporteert, worden deze niet in PST-bestanden gezet.</span><span class="sxs-lookup"><span data-stu-id="901dc-163">If you export redacted PDF files, they are not put in PST files.</span></span> <span data-ttu-id="901dc-164">In plaats daarvan worden ze toegevoegd aan een gescheiden map.</span><span class="sxs-lookup"><span data-stu-id="901dc-164">Instead, they're added to a separated folder.</span></span>
  
  - <span data-ttu-id="901dc-165">Error_files: Deze map bevat de volgende foutbestanden, als deze zijn opgenomen in de export:</span><span class="sxs-lookup"><span data-stu-id="901dc-165">Error_files: This folder contains the following error files, if they are included in the export:</span></span>

    - <span data-ttu-id="901dc-166">ExtractieFout: een CSV-bestand dat alle beschikbare metagegevens bevat van bestanden die niet correct zijn geëxtraheerd uit bovenliggende bestanden.</span><span class="sxs-lookup"><span data-stu-id="901dc-166">ExtractionError: A CSV file that contains any available metadata of files that weren't properly extracted from parent files.</span></span>

    - <span data-ttu-id="901dc-167">ProcessingError: Dit bestand bevat een lijst met documenten met verwerkingsfouten.</span><span class="sxs-lookup"><span data-stu-id="901dc-167">ProcessingError: This file contains a list of documents with processing errors.</span></span> <span data-ttu-id="901dc-168">Deze inhoud is itemniveau, wat betekent dat als een bijlage een verwerkingsfout heeft veroorzaakt, het e-mailbericht met de bijlage in deze map wordt opgenomen.</span><span class="sxs-lookup"><span data-stu-id="901dc-168">This content is item-level, meaning if an attachment resulted in a processing error, the email message that contains the attachment is included in this folder.</span></span>
  
  - <span data-ttu-id="901dc-169">Extracted_text_files: Deze map bevat alle uitgepakte tekstbestanden die tijdens de verwerking zijn gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="901dc-169">Extracted_text_files: This folder contains all of the extracted text files that were generated at processing.</span></span>
