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
ms.openlocfilehash: fec6e441458ad7429067a1314a7aec3824aff11a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "52162589"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="74b0d-104">Een inhoudszoekrapport exporteren</span><span class="sxs-lookup"><span data-stu-id="74b0d-104">Export a Content Search report</span></span>

<span data-ttu-id="74b0d-105">In plaats van de volledige set zoekresultaten te exporteren uit een inhoudszoekactie in het Beveiligings- & Compliancecentrum (en vanuit een inhoudszoekactie die is gekoppeld aan een eDiscovery-zaak), kunt u dezelfde rapporten exporteren die worden gegenereerd wanneer u zoekresultaten exporteert.</span><span class="sxs-lookup"><span data-stu-id="74b0d-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="74b0d-106">Wanneer u een rapport exporteert, wordt het gedownload naar een map met dezelfde naam als het zoeken naar inhoud, maar die is toegevoegd aan *_ReportsOnly.*</span><span class="sxs-lookup"><span data-stu-id="74b0d-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="74b0d-107">Als het zoeken naar inhoud bijvoorbeeld de naam *ContosoCase0815* heeft, wordt het rapport gedownload naar een map *met de naam ContosoCase0815_ReportsOnly.*</span><span class="sxs-lookup"><span data-stu-id="74b0d-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="74b0d-108">Zie Wat is opgenomen in het rapport voor een lijst met documenten die in het rapport [zijn opgenomen.](#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="74b0d-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="assign-roles-and-check-system-requirements"></a><span data-ttu-id="74b0d-109">Rollen toewijzen en systeemvereisten controleren</span><span class="sxs-lookup"><span data-stu-id="74b0d-109">Assign roles and check system requirements</span></span>

- <span data-ttu-id="74b0d-110">Als u een inhoudszoekrapport wilt exporteren, moet u de rol compliancezoekbeheer toegewezen krijgen in het beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="74b0d-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="74b0d-111">Deze rol wordt standaard toegewezen aan de ingebouwde rollengroepen eDiscovery Manager en Organisatiebeheer.</span><span class="sxs-lookup"><span data-stu-id="74b0d-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="74b0d-112">Zie [eDiscovery-machtigingen](assign-ediscovery-permissions.md)toewijzen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="74b0d-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="74b0d-113">Wanneer u een rapport exporteert, worden de gegevens tijdelijk opgeslagen in een uniek Azure Storage in de Microsoft-cloud voordat deze worden gedownload naar uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="74b0d-113">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="74b0d-114">Zorg ervoor dat uw organisatie verbinding kan maken met het eindpunt in Azure, dat **\* .blob.core.windows.net** is (het jokerteken vertegenwoordigt een unieke id voor uw export).</span><span class="sxs-lookup"><span data-stu-id="74b0d-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="74b0d-115">De zoekresultaten worden twee weken na het maken Azure Storage verwijderd uit het Azure Storage gebied.</span><span class="sxs-lookup"><span data-stu-id="74b0d-115">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span>

- <span data-ttu-id="74b0d-116">De computer die u gebruikt om de zoekresultaten te exporteren, moet voldoen aan de volgende systeemvereisten:</span><span class="sxs-lookup"><span data-stu-id="74b0d-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="74b0d-117">Nieuwste versie van Windows (32-bits of 64-bits)</span><span class="sxs-lookup"><span data-stu-id="74b0d-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="74b0d-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="74b0d-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="74b0d-119">U moet een van de volgende ondersteunde browsers gebruiken om het eDiscovery Export Tool 1 uit te<sup>voeren:</sup></span><span class="sxs-lookup"><span data-stu-id="74b0d-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="74b0d-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="74b0d-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="74b0d-121">OF</span><span class="sxs-lookup"><span data-stu-id="74b0d-121">OR</span></span>

  - <span data-ttu-id="74b0d-122">Microsoft Internet Explorer 10 en nieuwere versies</span><span class="sxs-lookup"><span data-stu-id="74b0d-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="74b0d-123"><sup>1</sup> Microsoft produceert geen extensies of invoegtoepassingen van derden voor ClickOnce toepassingen.</span><span class="sxs-lookup"><span data-stu-id="74b0d-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="74b0d-124">Het exporteren van zoekresultaten met een niet-ondersteunde browser met extensies of invoegtoepassingen van derden wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="74b0d-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="74b0d-125"><sup>2</sup> Als gevolg van recente wijzigingen in Microsoft Edge is ClickOnce standaard niet meer ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="74b0d-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="74b0d-126">Zie Het [eDiscovery-exporthulpmiddel](configure-edge-to-export-search-results.md)gebruiken in Microsoft Edge voor instructies over het inschakelen van ClickOnce ondersteuning in Edge.</span><span class="sxs-lookup"><span data-stu-id="74b0d-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="74b0d-127">Als de geschatte totale grootte van de resultaten die worden geretourneerd door een inhoudszoekactie groter is dan 2 TB, mislukt het exporteren van het rapport.</span><span class="sxs-lookup"><span data-stu-id="74b0d-127">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="74b0d-128">Als u het rapport wilt exporteren, probeert u het bereik te beperken en de zoekopdracht opnieuw uit te voeren, zodat de geschatte grootte van de resultaten kleiner is dan 2 TB.</span><span class="sxs-lookup"><span data-stu-id="74b0d-128">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="74b0d-129">Het exporteren van inhoudszoekrapporten telt mee voor het maximum aantal exporten dat tegelijkertijd wordt uitgevoerd en het maximum aantal exporten dat één gebruiker kan uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="74b0d-129">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="74b0d-130">Zie Inhoudszoekresultaten exporteren voor meer informatie over [exportlimieten.](export-search-results.md#export-limits)</span><span class="sxs-lookup"><span data-stu-id="74b0d-130">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="74b0d-131">Een inhoudszoekrapport genereren en downloaden</span><span class="sxs-lookup"><span data-stu-id="74b0d-131">Generate and download a Content Search report</span></span>

<span data-ttu-id="74b0d-132">De stappen voor het genereren en downloaden van een inhoudszoekrapport zijn vergelijkbaar met het daadwerkelijk exporteren van zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="74b0d-132">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="74b0d-133">Stap 1: Het rapport genereren voor export</span><span class="sxs-lookup"><span data-stu-id="74b0d-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="74b0d-134">De eerste stap is het voorbereiden van het rapport voor het downloaden naar uw computer exporteren.</span><span class="sxs-lookup"><span data-stu-id="74b0d-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="74b0d-135">Wanneer u het rapport gebruikt, worden de rapportdocumenten geüpload naar een Azure Storage in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="74b0d-135">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="74b0d-136">Ga naar [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="74b0d-136">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="74b0d-137">Meld u aan met uw werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="74b0d-137">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="74b0d-138">Klik in het linkerdeelvenster van & Compliancecentrum op **Zoeken in** \> **inhoud.**</span><span class="sxs-lookup"><span data-stu-id="74b0d-138">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="74b0d-139">Selecteer op **de pagina Inhoud** zoeken een zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="74b0d-139">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="74b0d-140">Klik in het detailvenster onder **Rapport exporteren naar een computer** op Rapport **genereren.**</span><span class="sxs-lookup"><span data-stu-id="74b0d-140">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="74b0d-141">Als de resultaten voor een zoekopdracht ouder zijn dan 7 dagen, wordt u gevraagd de zoekresultaten bij te werken.</span><span class="sxs-lookup"><span data-stu-id="74b0d-141">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="74b0d-142">Als dit gebeurt, annuleert u de export, klikt u **in** het detailvenster op Zoekresultaten bijwerken voor de geselecteerde zoekopdracht en start u het rapport opnieuw nadat de resultaten zijn bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="74b0d-142">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="74b0d-143">Kies op **de pagina Een rapport** exporteren onder Deze items uit de **zoekopdracht** opnemen een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="74b0d-143">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="74b0d-144">Alleen geïndexeerde items exporteren</span><span class="sxs-lookup"><span data-stu-id="74b0d-144">Export only indexed items</span></span>
    
    - <span data-ttu-id="74b0d-145">Geïndexeerde en niet-geïndexeerde items exporteren</span><span class="sxs-lookup"><span data-stu-id="74b0d-145">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="74b0d-146">Alleen niet-geïndexeerde items exporteren</span><span class="sxs-lookup"><span data-stu-id="74b0d-146">Export only unindexed items</span></span>
    
    <span data-ttu-id="74b0d-147">Zie Gedeeltelijk geïndexeerde items in Inhoud zoeken voor meer informatie over niet-geïndexeerde [items.](partially-indexed-items-in-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="74b0d-147">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="74b0d-148">Kies om zoekstatistieken op te nemen voor alle versies van SharePoint documenten.</span><span class="sxs-lookup"><span data-stu-id="74b0d-148">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="74b0d-149">Deze optie wordt alleen weergegeven als de inhoudsbronnen van de zoekopdracht sites SharePoint of OneDrive voor Bedrijven bevatten.</span><span class="sxs-lookup"><span data-stu-id="74b0d-149">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="74b0d-150">Klik **op Rapport genereren.**</span><span class="sxs-lookup"><span data-stu-id="74b0d-150">Click **Generate report**.</span></span>
    
    <span data-ttu-id="74b0d-151">Het rapport met zoekresultaten is voorbereid voor het downloaden, wat betekent dat de rapportdocumenten worden geüpload naar het Azure Storage in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="74b0d-151">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="74b0d-152">Wanneer het rapport klaar is om te worden gedownload, wordt de **koppeling** Rapport downloaden weergegeven onder Rapport exporteren naar **een computer** in het detailvenster.</span><span class="sxs-lookup"><span data-stu-id="74b0d-152">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="74b0d-153">U kunt ook een rapport exporteren voor een inhoudszoekactie die is gekoppeld aan een eDiscovery-zaak.</span><span class="sxs-lookup"><span data-stu-id="74b0d-153">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="74b0d-154">Hiervoor gaat u naar **eDiscovery** \> **eDiscovery,** selecteert u een zaak en klikt u op **Pictogram** ![ Bewerken ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) bewerken.</span><span class="sxs-lookup"><span data-stu-id="74b0d-154">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="74b0d-155">Selecteer op **de pagina** Zoekopdrachten een zoekopdracht en klik vervolgens op **Pictogram** Zoekresultaten exporteren Exporteren ![ Een rapport ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **exporteren.**</span><span class="sxs-lookup"><span data-stu-id="74b0d-155">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="74b0d-156">Stap 2: Het rapport downloaden</span><span class="sxs-lookup"><span data-stu-id="74b0d-156">Step 2: Download the report</span></span>

<span data-ttu-id="74b0d-157">De volgende stap is het downloaden van het rapport van het Azure Storage naar uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="74b0d-157">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="74b0d-158">Klik in het detailvenster voor de zoekopdracht waar u het rapport voor hebt gegenereerd, onder **Rapport exporteren** naar een computer op Rapport **downloaden.**</span><span class="sxs-lookup"><span data-stu-id="74b0d-158">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="74b0d-159">De **pagina Rapport** downloaden wordt weergegeven en bevat de volgende informatie over het rapport dat naar uw computer is gedownload.</span><span class="sxs-lookup"><span data-stu-id="74b0d-159">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="74b0d-160">Het aantal items dat wordt gedownload.</span><span class="sxs-lookup"><span data-stu-id="74b0d-160">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="74b0d-161">De geschatte totale grootte van de items die worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="74b0d-161">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="74b0d-162">Geïndexeerd of niet-geïndexeerd wordt geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="74b0d-162">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="74b0d-163">Niet-geïndexeerde items zijn items met een herkende notatie, die zijn versleuteld of die om andere redenen niet zijn geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="74b0d-163">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="74b0d-164">Of versies van SharePoint documenten worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="74b0d-164">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="74b0d-165">De status van het rapportexportproces.</span><span class="sxs-lookup"><span data-stu-id="74b0d-165">The status of the report export process.</span></span> <span data-ttu-id="74b0d-166">U kunt het rapport gaan downloaden, zelfs als de voorbereiding van het rapport niet is voltooid.</span><span class="sxs-lookup"><span data-stu-id="74b0d-166">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="74b0d-167">Klik **onder Exportcode** op **Kopiëren naar klembord.**</span><span class="sxs-lookup"><span data-stu-id="74b0d-167">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="74b0d-168">U gebruikt deze sleutel in stap 5 om het rapport te downloaden.</span><span class="sxs-lookup"><span data-stu-id="74b0d-168">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="74b0d-169">Omdat iedereen het hulpprogramma eDiscovery Export kan installeren en starten en vervolgens deze sleutel kan gebruiken om het zoekrapport te downloaden, moet u voorzorgsmaatregelen nemen om deze sleutel te beveiligen, net zoals u wachtwoorden of andere beveiligingsgerelateerde informatie zou beveiligen.</span><span class="sxs-lookup"><span data-stu-id="74b0d-169">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="74b0d-170">Klik **op Rapport downloaden.**</span><span class="sxs-lookup"><span data-stu-id="74b0d-170">Click **Download report**.</span></span>
    
4. <span data-ttu-id="74b0d-171">Als u wordt gevraagd het **eDiscovery-exportprogramma te installeren,** klikt u op **Installeren.**</span><span class="sxs-lookup"><span data-stu-id="74b0d-171">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="74b0d-172">Plak in **het eDiscovery-exporthulpmiddel** de exportcode die u in stap 2 in het juiste vak hebt gekopieerd.</span><span class="sxs-lookup"><span data-stu-id="74b0d-172">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="74b0d-173">Klik **op Bladeren** om de locatie op te geven waar u het rapport wilt downloaden.</span><span class="sxs-lookup"><span data-stu-id="74b0d-173">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="74b0d-174">Klik **op Start** om de zoekresultaten naar uw computer te downloaden.</span><span class="sxs-lookup"><span data-stu-id="74b0d-174">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="74b0d-175">Het **eDiscovery-exporthulpmiddel** geeft statusgegevens weer over het exportproces, inclusief een schatting van het aantal (en de grootte) van de resterende items die moeten worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="74b0d-175">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="74b0d-176">Wanneer het exportproces is voltooid, hebt u toegang tot de bestanden op de locatie waar ze zijn gedownload.</span><span class="sxs-lookup"><span data-stu-id="74b0d-176">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="74b0d-177">U kunt het rapport downloaden voor een inhoudszoekactie die is gekoppeld aan een eDiscovery-zaak.</span><span class="sxs-lookup"><span data-stu-id="74b0d-177">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="74b0d-178">Hiervoor gaat u naar **eDiscovery** \> **eDiscovery,** selecteert u een zaak en klikt u op **Pictogram** ![ Bewerken ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) bewerken.</span><span class="sxs-lookup"><span data-stu-id="74b0d-178">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="74b0d-179">Selecteer op **de** pagina Export een rapport exporteren en klik vervolgens op **Rapport downloaden** in het detailvenster.</span><span class="sxs-lookup"><span data-stu-id="74b0d-179">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="74b0d-180">Wat is opgenomen in het rapport</span><span class="sxs-lookup"><span data-stu-id="74b0d-180">What's included in the report</span></span>

<span data-ttu-id="74b0d-181">Wanneer u een rapport over de resultaten van een inhoudszoekactie genereert en exporteert, worden de volgende documenten gedownload:</span><span class="sxs-lookup"><span data-stu-id="74b0d-181">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="74b0d-182">**Exportoverzicht:** Een Excel document met een overzicht van de export.</span><span class="sxs-lookup"><span data-stu-id="74b0d-182">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="74b0d-183">Dit omvat informatie, zoals het aantal inhoudsbronnen dat is doorzocht, het aantal zoekresultaten van elke inhoudslocatie, het geschatte aantal items, het werkelijke aantal items dat zou worden geëxporteerd en de geschatte en werkelijke grootte van items die zouden worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="74b0d-183">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="74b0d-184">Als u niet-geïndexeerde items opgeeft bij het exporteren van het rapport, wordt het aantal niet-geïndexeerde items opgenomen in het totale aantal geschatte zoekresultaten en in het totale aantal gedownloade zoekresultaten (als u de zoekresultaten wilt exporteren) die worden weergegeven in het rapport Overzicht exporteren.</span><span class="sxs-lookup"><span data-stu-id="74b0d-184">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="74b0d-185">Met andere woorden, het totale aantal items dat wordt gedownload, is gelijk aan het totale aantal geschatte resultaten en het totale aantal niet-geïndexeerde items.</span><span class="sxs-lookup"><span data-stu-id="74b0d-185">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="74b0d-186">**Manifest:** Een manifestbestand (in XML-indeling) dat informatie bevat over elk item dat in de zoekresultaten wordt opgenomen.</span><span class="sxs-lookup"><span data-stu-id="74b0d-186">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="74b0d-187">**Resultaten:** Een Excel document met een rij met informatie over elk geïndexeerd item dat met de zoekresultaten zou worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="74b0d-187">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="74b0d-188">Voor e-mail bevat het resultatenlogboek informatie over elk bericht, waaronder:</span><span class="sxs-lookup"><span data-stu-id="74b0d-188">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="74b0d-189">De locatie van het bericht in het bronpostvak (inclusief of het bericht zich in het primaire of archiefpostvak bevindt).</span><span class="sxs-lookup"><span data-stu-id="74b0d-189">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="74b0d-190">De datum waarop het bericht is verzonden of ontvangen.</span><span class="sxs-lookup"><span data-stu-id="74b0d-190">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="74b0d-191">De onderwerpregel van het bericht.</span><span class="sxs-lookup"><span data-stu-id="74b0d-191">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="74b0d-192">De afzender en geadresseerden van het bericht.</span><span class="sxs-lookup"><span data-stu-id="74b0d-192">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="74b0d-193">Voor documenten van SharePoint en OneDrive voor Bedrijven sites bevat het logboek Resultaten informatie over elk document, waaronder:</span><span class="sxs-lookup"><span data-stu-id="74b0d-193">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="74b0d-194">De URL voor het document.</span><span class="sxs-lookup"><span data-stu-id="74b0d-194">The URL for the document.</span></span>
    
  - <span data-ttu-id="74b0d-195">De URL voor de siteverzameling waar het document zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="74b0d-195">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="74b0d-196">De datum waarop het document voor het laatst is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="74b0d-196">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="74b0d-197">De naam van het document (dat zich in de kolom Onderwerp in het resultatenlogboek bevindt).</span><span class="sxs-lookup"><span data-stu-id="74b0d-197">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="74b0d-198">Het aantal rijen  in het rapport Resultaten moet gelijk zijn aan het totale aantal zoekresultaten minus het totale aantal items dat wordt weergegeven in het rapport **Niet-geïndexeerde** items.</span><span class="sxs-lookup"><span data-stu-id="74b0d-198">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="74b0d-199">**Niet-geïndexeerde items:** Een Excel document met informatie over niet-geïndexeerde items in de zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="74b0d-199">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="74b0d-200">Als u geen niet-geïndexeerde items opgeeft wanneer u het rapport met zoekresultaten genereert, wordt dit rapport nog steeds gedownload, maar is het leeg.</span><span class="sxs-lookup"><span data-stu-id="74b0d-200">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
