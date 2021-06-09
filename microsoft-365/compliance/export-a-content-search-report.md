---
title: Een inhoudszoekrapport exporteren
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: In plaats van de werkelijke resultaten van een inhoudszoekactie te exporteren in & Compliancecentrum voor beveiliging in Office 365, kunt u een rapport met zoekresultaten exporteren. Het rapport bevat een overzicht van de zoekresultaten en een document met gedetailleerde informatie over elk item dat zou worden geëxporteerd.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311569"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="54d00-104">Een inhoudszoekrapport exporteren</span><span class="sxs-lookup"><span data-stu-id="54d00-104">Export a Content search report</span></span>

<span data-ttu-id="54d00-105">In plaats van de volledige reeks zoekresultaten te exporteren uit een inhoudszoekactie in het Microsoft 365 compliancecentrum (of uit een zoekopdracht die is gekoppeld aan een Core eDiscovery-zaak), kunt u dezelfde rapporten exporteren die worden gegenereerd wanneer u de werkelijke zoekresultaten exporteert.</span><span class="sxs-lookup"><span data-stu-id="54d00-105">Instead of exporting the full set of search results from a Content search in the Microsoft 365 compliance Center (or from a search that's associated with a Core eDiscovery case), you can export the same reports that are generated when you export the actual search results.</span></span>
  
<span data-ttu-id="54d00-106">Wanneer u een rapport exporteert, worden de rapportbestanden gedownload naar een map op uw lokale computer die dezelfde naam heeft als het zoeken naar inhoud, maar die wordt toegevoegd met *_ReportsOnly.*</span><span class="sxs-lookup"><span data-stu-id="54d00-106">When you export a report, the report files are downloaded to a folder on your local computer that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="54d00-107">Als het zoeken naar inhoud bijvoorbeeld de naam *ContosoCase0815* heeft, wordt het rapport gedownload naar een map *met de naam ContosoCase0815_ReportsOnly.*</span><span class="sxs-lookup"><span data-stu-id="54d00-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="54d00-108">Zie Wat is opgenomen in het rapport voor een lijst met documenten die in het rapport [zijn opgenomen.](#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="54d00-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-export-a-search-report"></a><span data-ttu-id="54d00-109">Voordat u een zoekrapport exporteert</span><span class="sxs-lookup"><span data-stu-id="54d00-109">Before you export a search report</span></span>

- <span data-ttu-id="54d00-110">Als u een zoekrapport wilt exporteren, moet u de rol compliancezoekbeheer toegewezen krijgen in & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="54d00-110">To export a search report, you have to be assigned the Compliance Search management role in Security & Compliance Center.</span></span> <span data-ttu-id="54d00-111">Deze rol wordt standaard toegewezen aan de ingebouwde rollengroepen eDiscovery Manager en Organisatiebeheer.</span><span class="sxs-lookup"><span data-stu-id="54d00-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="54d00-112">Zie [eDiscovery-machtigingen toewijzen](assign-ediscovery-permissions.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="54d00-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="54d00-113">Wanneer u een rapport exporteert, worden de gegevens tijdelijk opgeslagen op Azure Storage locatie in de Microsoft-cloud voordat deze worden gedownload naar uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="54d00-113">When you export a report, the data is temporarily stored in an Azure Storage location in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="54d00-114">Zorg ervoor dat uw organisatie verbinding kan maken met het eindpunt in Azure, dat **\* .blob.core.windows.net** is (het jokerteken vertegenwoordigt een unieke id voor uw export).</span><span class="sxs-lookup"><span data-stu-id="54d00-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="54d00-115">De zoekresultaten worden twee weken na het maken Azure Storage van de locatie verwijderd.</span><span class="sxs-lookup"><span data-stu-id="54d00-115">The search results data is deleted from the Azure Storage location two weeks after it's created.</span></span>

- <span data-ttu-id="54d00-116">De computer die u gebruikt om de zoekresultaten te exporteren, moet voldoen aan de volgende systeemvereisten:</span><span class="sxs-lookup"><span data-stu-id="54d00-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="54d00-117">Nieuwste versie van Windows (32-bits of 64-bits)</span><span class="sxs-lookup"><span data-stu-id="54d00-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="54d00-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="54d00-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="54d00-119">U moet een van de volgende ondersteunde browsers gebruiken om het eDiscovery Export Tool 1 uit te<sup>voeren:</sup></span><span class="sxs-lookup"><span data-stu-id="54d00-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="54d00-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="54d00-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="54d00-121">OF</span><span class="sxs-lookup"><span data-stu-id="54d00-121">OR</span></span>

  - <span data-ttu-id="54d00-122">Microsoft Internet Explorer 10 en nieuwere versies</span><span class="sxs-lookup"><span data-stu-id="54d00-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="54d00-123"><sup>1</sup> Microsoft produceert geen extensies of invoegtoepassingen van derden voor ClickOnce toepassingen.</span><span class="sxs-lookup"><span data-stu-id="54d00-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="54d00-124">Het exporteren van zoekresultaten met een niet-ondersteunde browser met extensies of invoegtoepassingen van derden wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="54d00-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="54d00-125"><sup>2</sup> Als gevolg van recente wijzigingen in Microsoft Edge is ClickOnce standaard niet meer ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="54d00-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="54d00-126">Zie Het [eDiscovery-exporthulpmiddel](configure-edge-to-export-search-results.md)gebruiken in Microsoft Edge voor instructies over het inschakelen van ClickOnce ondersteuning in Edge.</span><span class="sxs-lookup"><span data-stu-id="54d00-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="54d00-127">Als de geschatte totale grootte van de resultaten die door zoeken worden geretourneerd groter is dan 2 TB, mislukt het exporteren van de rapporten.</span><span class="sxs-lookup"><span data-stu-id="54d00-127">If the estimated total size of the results returned by search exceeds 2 TB, exporting the reports fails.</span></span> <span data-ttu-id="54d00-128">Als u de rapporten wilt exporteren, probeert u het bereik te beperken en de zoekopdracht opnieuw uit te voeren, zodat de geschatte grootte van de resultaten kleiner is dan 2 TB.</span><span class="sxs-lookup"><span data-stu-id="54d00-128">To successfully export the reports, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="54d00-129">Als de resultaten van een zoekopdracht ouder zijn dan 7 dagen en u een exportrapportfunctie indient, wordt er een foutbericht weergegeven waarin u wordt gevraagd de zoekopdracht opnieuw uit te voeren om de zoekresultaten bij te werken.</span><span class="sxs-lookup"><span data-stu-id="54d00-129">If the results of a search are older than 7 days and you submit an export report job, an error message is displayed prompting you to rerun the search to update the search results.</span></span> <span data-ttu-id="54d00-130">Als dit gebeurt, annuleert u de export, heruitvoert u de zoekopdracht en start u de export opnieuw.</span><span class="sxs-lookup"><span data-stu-id="54d00-130">If this happens, cancel the export, rerun the search, and then start the export again.</span></span>

- <span data-ttu-id="54d00-131">Het exporteren van zoekrapporten telt mee voor het maximum aantal exporten dat tegelijkertijd wordt uitgevoerd en het maximum aantal exporten dat één gebruiker kan uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="54d00-131">Exporting search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="54d00-132">Zie Zoekresultaten voor inhoud exporteren voor meer informatie over [exportlimieten.](export-search-results.md#export-limits)</span><span class="sxs-lookup"><span data-stu-id="54d00-132">For more information about export limits, see [Export Content search results](export-search-results.md#export-limits).</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="54d00-133">Stap 1: Het rapport genereren voor export</span><span class="sxs-lookup"><span data-stu-id="54d00-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="54d00-134">De eerste stap is het voorbereiden van het rapport voor het downloaden naar uw computer exporteren.</span><span class="sxs-lookup"><span data-stu-id="54d00-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="54d00-135">Wanneer u het rapport exporteert, worden de rapportdocumenten geüpload naar een Azure Storage in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="54d00-135">When you export the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="54d00-136">Selecteer in Microsoft 365 compliancecentrum de inhoudszoekactie waaruit u het rapport wilt exporteren.</span><span class="sxs-lookup"><span data-stu-id="54d00-136">In the Microsoft 365 compliance center, select the Content search that you want to export the report from.</span></span>
  
2. <span data-ttu-id="54d00-137">Klik in **het** menu Acties onder aan de flyoutpagina van de zoekactie op **Rapport exporteren.**</span><span class="sxs-lookup"><span data-stu-id="54d00-137">On the **Actions** menu at the bottom of the search flyout page, click **Export report**.</span></span>

   ![Rapportoptie exporteren in het menu Acties](../media/ActionMenuExportReport.png)

   <span data-ttu-id="54d00-139">De **flyoutpagina** Rapport exporteren wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="54d00-139">The **Export report** flyout page is displayed.</span></span> <span data-ttu-id="54d00-140">De exportrapportopties die beschikbaar zijn om informatie over de zoekopdracht te exporteren, zijn afhankelijk van of zoekresultaten zich in postvakken of sites bevinden of een combinatie van beide.</span><span class="sxs-lookup"><span data-stu-id="54d00-140">The export report options available to export information about the search depend on whether search results are located in mailboxes or sites or a combination of both.</span></span>
  
3. <span data-ttu-id="54d00-141">Kies **onder Uitvoeropties** een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="54d00-141">Under **Output options**, choose one of the following options:</span></span>
  
   ![Uitvoeropties exporteren](../media/ExportOutputOptions.png)

    - <span data-ttu-id="54d00-143">Alle items, met uitzondering van items met een niet-herkende notatie, worden versleuteld of zijn om andere redenen **niet geïndexeerd.**</span><span class="sxs-lookup"><span data-stu-id="54d00-143">**All items, excluding ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="54d00-144">Deze optie exporteert alleen informatie over geïndexeerde items.</span><span class="sxs-lookup"><span data-stu-id="54d00-144">This option only exports information about indexed items.</span></span>
  
    - <span data-ttu-id="54d00-145">Alle items, inclusief items met een niet-herkende notatie, worden versleuteld of zijn om andere redenen **niet geïndexeerd.**</span><span class="sxs-lookup"><span data-stu-id="54d00-145">**All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="54d00-146">Met deze optie exporteert u informatie over geïndexeerde en niet-geïndexeerde items.</span><span class="sxs-lookup"><span data-stu-id="54d00-146">This option exports information about indexed and unindexed items.</span></span>
  
    - <span data-ttu-id="54d00-147">**Alleen items met een niet-herkende notatie,** worden versleuteld of om andere redenen niet geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="54d00-147">**Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="54d00-148">Met deze optie wordt alleen informatie over niet-geïndexeerde items geexporteerd.</span><span class="sxs-lookup"><span data-stu-id="54d00-148">This option only exports information about unindexed items.</span></span>

4. <span data-ttu-id="54d00-149">Configureer **de optie Deplicatie inschakelen voor Exchange inhoud.**</span><span class="sxs-lookup"><span data-stu-id="54d00-149">Configure the **Enable de-duplication for Exchange content** option.</span></span>
  
   - <span data-ttu-id="54d00-150">Als u deze optie selecteert, wordt het aantal dubbele berichten (vóór de duplicatie en na de duplicatie) opgenomen in het overzichtsrapport exporteren.</span><span class="sxs-lookup"><span data-stu-id="54d00-150">If you select this option, the count of duplicate messages (before de-duplication and after de-duplication) is included in the export summary report.</span></span> <span data-ttu-id="54d00-151">Er wordt ook slechts één kopie van een bericht opgenomen in het manifest.xml bestand.</span><span class="sxs-lookup"><span data-stu-id="54d00-151">Also, only one copy of a message will be included in the manifest.xml file.</span></span> <span data-ttu-id="54d00-152">Het rapport Exportresultaten bevat echter een rij voor elke kopie van een duplicaatbericht, zodat u de postvakken kunt identificeren die een kopie van het dubbele bericht bevatten.</span><span class="sxs-lookup"><span data-stu-id="54d00-152">But the export results report will contain a row for every copy of a duplicate message so that you can identify the mailboxes that contain a copy of the duplicate message.</span></span> <span data-ttu-id="54d00-153">Zie Wat is opgenomen in het rapport voor meer informatie over [de geëxporteerde rapporten.](#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="54d00-153">For more information about the exported reports, see [What's included in the report](#whats-included-in-the-report).</span></span>

   - <span data-ttu-id="54d00-154">Als u deze optie niet selecteert, bevatten de exportrapporten informatie over alle berichten die door de zoekopdracht worden geretourneerd, inclusief duplicaten.</span><span class="sxs-lookup"><span data-stu-id="54d00-154">If you don't select this option, the export reports will contain information about all messages returned by the search, including duplicates.</span></span>

     <span data-ttu-id="54d00-155">Zie [De-duplicatie in eDiscovery-zoekresultaten](de-duplication-in-ediscovery-search-results.md)voor meer informatie over de-duplicatie en hoe dubbele items worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="54d00-155">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

5. <span data-ttu-id="54d00-156">Klik **op Rapport genereren.**</span><span class="sxs-lookup"><span data-stu-id="54d00-156">Click **Generate report**.</span></span>

   <span data-ttu-id="54d00-157">De zoekrapporten zijn voorbereid voor het downloaden, wat betekent dat de rapportdocumenten worden geüpload naar een Azure Storage locatie in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="54d00-157">The search reports are prepared for downloading, which means the report documents are uploaded to an Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="54d00-158">Dit kan enkele minuten duren.</span><span class="sxs-lookup"><span data-stu-id="54d00-158">This may take several minutes.</span></span>

<span data-ttu-id="54d00-159">Zie de volgende sectie voor instructies voor het downloaden van de geëxporteerde zoekrapporten.</span><span class="sxs-lookup"><span data-stu-id="54d00-159">See the next section for instructions to download the exported search reports.</span></span>
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="54d00-160">Stap 2: Het rapport downloaden</span><span class="sxs-lookup"><span data-stu-id="54d00-160">Step 2: Download the report</span></span>

<span data-ttu-id="54d00-161">De volgende stap is het downloaden van het rapport van het Azure Storage naar uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="54d00-161">The next step is to download the report from the Azure Storage area to your local computer.</span></span>

1. <span data-ttu-id="54d00-162">Selecteer op **de pagina Inhoud** zoeken in het Microsoft 365 compliancecentrum het tabblad **Exporten**</span><span class="sxs-lookup"><span data-stu-id="54d00-162">On the **Content search** page in the Microsoft 365 compliance center, select the **Exports** tab</span></span>
  
   <span data-ttu-id="54d00-163">Mogelijk moet u op Vernieuwen klikken **om** de lijst met exporttaken bij te werken, zodat de exporttaken worden weergegeven die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="54d00-163">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="54d00-164">Rapporttaken exporteren hebben dezelfde naam als de bijbehorende zoekopdracht **_ReportsOnly** toegevoegd aan de zoeknaam.</span><span class="sxs-lookup"><span data-stu-id="54d00-164">Export report jobs have the same name as the corresponding search with **_ReportsOnly** appended to the search name.</span></span>
  
2. <span data-ttu-id="54d00-165">Selecteer de exportklus die u hebt gemaakt in stap 1.</span><span class="sxs-lookup"><span data-stu-id="54d00-165">Select the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="54d00-166">Klik op **de flyoutpagina** Rapport exporteren onder **Exportcode** op **Kopiëren naar klembord.**</span><span class="sxs-lookup"><span data-stu-id="54d00-166">On the **Export report** flyout page under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="54d00-167">U gebruikt deze sleutel in stap 6 om de zoekresultaten te downloaden.</span><span class="sxs-lookup"><span data-stu-id="54d00-167">You use this key in step 6 to download the search results.</span></span>
  
   > [!IMPORTANT]
   > <span data-ttu-id="54d00-168">Omdat iedereen het hulpprogramma eDiscovery Export kan installeren en starten en vervolgens deze sleutel kan gebruiken om het zoekrapport te downloaden, moet u voorzorgsmaatregelen nemen om deze sleutel te beveiligen, net zoals u wachtwoorden of andere beveiligingsgerelateerde informatie zou beveiligen.</span><span class="sxs-lookup"><span data-stu-id="54d00-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span>

4. <span data-ttu-id="54d00-169">Klik boven aan de flyoutpagina op **Resultaten downloaden.**</span><span class="sxs-lookup"><span data-stu-id="54d00-169">At the top of the flyout page, click **Download results**.</span></span>

5. <span data-ttu-id="54d00-170">Als u wordt gevraagd het **eDiscovery-exportprogramma te installeren,** klikt u op **Installeren.**</span><span class="sxs-lookup"><span data-stu-id="54d00-170">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>

6. <span data-ttu-id="54d00-171">Ga als volgt te werk in het **eDiscovery-exporthulpmiddel:**</span><span class="sxs-lookup"><span data-stu-id="54d00-171">In the **eDiscovery Export Tool**, do the following:</span></span>

   ![eDiscovery Export Tool](../media/eDiscoveryExportTool.png)

   1. <span data-ttu-id="54d00-173">Plak de exportcode die u hebt gekopieerd in stap 3 in het juiste vak.</span><span class="sxs-lookup"><span data-stu-id="54d00-173">Paste the export key that you copied in step 3 in the appropriate box.</span></span>
  
   2. <span data-ttu-id="54d00-174">Klik **op Bladeren** om de locatie op te geven waar u de zoekrapportbestanden wilt downloaden.</span><span class="sxs-lookup"><span data-stu-id="54d00-174">Click **Browse** to specify the location where you want to download the search report files.</span></span>

7. <span data-ttu-id="54d00-175">Klik **op Start** om de zoekresultaten naar uw computer te downloaden.</span><span class="sxs-lookup"><span data-stu-id="54d00-175">Click **Start** to download the search results to your computer.</span></span>
  
    <span data-ttu-id="54d00-176">Het **eDiscovery-exporthulpmiddel** geeft statusgegevens weer over het exportproces, inclusief een schatting van het aantal (en de grootte) van de resterende items die moeten worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="54d00-176">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="54d00-177">Wanneer het exportproces is voltooid, hebt u toegang tot de bestanden op de locatie waar ze zijn gedownload.</span><span class="sxs-lookup"><span data-stu-id="54d00-177">When the export process is complete, you can access the files in the location where they were downloaded.</span></span>
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="54d00-178">Wat is opgenomen in het rapport</span><span class="sxs-lookup"><span data-stu-id="54d00-178">What's included in the report</span></span>

<span data-ttu-id="54d00-179">Wanneer u een rapport genereert en exporteert over de resultaten van een zoekopdracht naar inhoud, worden de volgende documenten gedownload:</span><span class="sxs-lookup"><span data-stu-id="54d00-179">When you generate and export a report about the results of a Content search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="54d00-180">**Exportoverzicht:** Een Excel document met een overzicht van de export.</span><span class="sxs-lookup"><span data-stu-id="54d00-180">**Export summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="54d00-181">Dit omvat informatie, zoals het aantal inhoudsbronnen dat is doorzocht, het aantal zoekresultaten van elke inhoudslocatie, het geschatte aantal items, het werkelijke aantal items dat zou worden geëxporteerd en de geschatte en werkelijke grootte van items die zouden worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="54d00-181">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span>

   <span data-ttu-id="54d00-182">Als u niet-geïndexeerde items opgeeft bij het exporteren van het rapport, wordt het aantal niet-geïndexeerde items opgenomen in het totale aantal geschatte zoekresultaten en in het totale aantal gedownloade zoekresultaten (als u de zoekresultaten wilt exporteren) die worden weergegeven in het overzichtsrapport exporteren.</span><span class="sxs-lookup"><span data-stu-id="54d00-182">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the export summary report.</span></span> <span data-ttu-id="54d00-183">Met andere woorden, het totale aantal items dat wordt gedownload, is gelijk aan het totale aantal geschatte resultaten en het totale aantal niet-geïndexeerde items.</span><span class="sxs-lookup"><span data-stu-id="54d00-183">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span>
  
- <span data-ttu-id="54d00-184">**Manifest:** Een manifestbestand (in XML-indeling) dat informatie bevat over elk item dat in de zoekresultaten wordt opgenomen.</span><span class="sxs-lookup"><span data-stu-id="54d00-184">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="54d00-185">Als u de optie de-duplicatie hebt ingeschakeld, worden dubbele berichten niet opgenomen in het manifestbestand.</span><span class="sxs-lookup"><span data-stu-id="54d00-185">If you enabled the de-duplication option, duplicate message are not included in the manifest file.</span></span>

- <span data-ttu-id="54d00-186">**Resultaten:** Een Excel document met een rij met informatie over elk geïndexeerd item dat met de zoekresultaten zou worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="54d00-186">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="54d00-187">Voor e-mail bevat het resultatenlogboek informatie over elk bericht, waaronder:</span><span class="sxs-lookup"><span data-stu-id="54d00-187">For email, the result log contains information about each message, including:</span></span> 

  - <span data-ttu-id="54d00-188">De locatie van het bericht in het bronpostvak (inclusief of het bericht zich in het primaire of archiefpostvak bevindt).</span><span class="sxs-lookup"><span data-stu-id="54d00-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>

  - <span data-ttu-id="54d00-189">De datum waarop het bericht is verzonden of ontvangen.</span><span class="sxs-lookup"><span data-stu-id="54d00-189">The date the message was sent or received.</span></span>

  - <span data-ttu-id="54d00-190">De onderwerpregel van het bericht.</span><span class="sxs-lookup"><span data-stu-id="54d00-190">The Subject line from the message.</span></span>

  - <span data-ttu-id="54d00-191">De afzender en geadresseerden van het bericht.</span><span class="sxs-lookup"><span data-stu-id="54d00-191">The sender and recipients of the message.</span></span>

  <span data-ttu-id="54d00-192">Voor documenten van SharePoint en OneDrive voor Bedrijven sites bevat het resultatenlogboek informatie over elk document, waaronder:</span><span class="sxs-lookup"><span data-stu-id="54d00-192">For documents from SharePoint and OneDrive for Business sites, the results log contains information about each document, including:</span></span>

  - <span data-ttu-id="54d00-193">De URL voor het document.</span><span class="sxs-lookup"><span data-stu-id="54d00-193">The URL for the document.</span></span>

  - <span data-ttu-id="54d00-194">De URL voor de siteverzameling waar het document zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="54d00-194">The URL for the site collection where the document is located.</span></span>

  - <span data-ttu-id="54d00-195">De datum waarop het document voor het laatst is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="54d00-195">The date that the document was last modified.</span></span>

  - <span data-ttu-id="54d00-196">De naam van het document (dat zich in de kolom Onderwerp in het resultatenlogboek bevindt).</span><span class="sxs-lookup"><span data-stu-id="54d00-196">The name of the document (which is located in the Subject column in the result log).</span></span>

  > [!NOTE]
  > <span data-ttu-id="54d00-197">Het aantal rijen  in het rapport Resultaten moet gelijk zijn aan het totale aantal zoekresultaten minus het totale aantal items dat wordt weergegeven in het rapport **Niet-geïndexeerde** items.</span><span class="sxs-lookup"><span data-stu-id="54d00-197">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span>
  
- <span data-ttu-id="54d00-198">**Trace.log:** een tracelogboek dat gedetailleerde logboekgegevens over het exportproces bevat en u kunt helpen bij het opsporen van problemen tijdens het exporteren.</span><span class="sxs-lookup"><span data-stu-id="54d00-198">**Trace.log**: A trace log that contains detailed logging information about the export process and can help uncover issues during export.</span></span> <span data-ttu-id="54d00-199">Als u een ticket opent met Microsoft Support over een probleem met betrekking tot het exporteren van zoekrapporten, wordt u mogelijk gevraagd dit tracelogboek op te geven.</span><span class="sxs-lookup"><span data-stu-id="54d00-199">If you open a ticket with Microsoft Support about an issue related to exporting search reports, you may be asked to provide this trace log.</span></span>

- <span data-ttu-id="54d00-200">**Niet-geïndexeerde items:** Een Excel document met informatie over niet-geïndexeerde items in de zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="54d00-200">**Unindexed items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="54d00-201">Als u geen niet-geïndexeerde items opgeeft wanneer u het rapport met zoekresultaten genereert, wordt dit rapport nog steeds gedownload, maar is het leeg.</span><span class="sxs-lookup"><span data-stu-id="54d00-201">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
