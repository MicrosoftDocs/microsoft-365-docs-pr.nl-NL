---
title: Inhoud exporteren en downloaden uit een Hoofd-eDiscovery-zaak
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Hier wordt beschreven hoe u inhoud exporteert en downloadt vanuit een hoofd-eDiscovery-zaak in Microsoft 365.
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310840"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="a6823-103">Inhoud exporteren uit een hoofd-eDiscovery-zaak</span><span class="sxs-lookup"><span data-stu-id="a6823-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="a6823-104">Nadat een zoekopdracht is uitgevoerd die is gekoppeld aan een Core eDiscovery-zaak, kunt u de zoekresultaten exporteren.</span><span class="sxs-lookup"><span data-stu-id="a6823-104">After a search associated with a Core eDiscovery case is successfully run, you can export the search results.</span></span> <span data-ttu-id="a6823-105">Wanneer u zoekresultaten exporteert, worden postvakitems gedownload in PST-bestanden of als afzonderlijke berichten.</span><span class="sxs-lookup"><span data-stu-id="a6823-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="a6823-106">Wanneer u inhoud exporteert van SharePoint en OneDrive voor Bedrijven sites, worden kopieën van Office documenten en andere documenten geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="a6823-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="a6823-107">Een Results.csv bestand met informatie over elk item dat wordt geëxporteerd en een manifestbestand (in XML-indeling) dat informatie bevat over elk zoekresultaat, wordt ook geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="a6823-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
## <a name="export-search-results"></a><span data-ttu-id="a6823-108">Zoekresultaten exporteren</span><span class="sxs-lookup"><span data-stu-id="a6823-108">Export search results</span></span>

1. <span data-ttu-id="a6823-109">Ga naar en meld u aan met de referenties voor gebruikersaccount die zijn toegewezen aan de juiste [https://compliance.microsoft.com](https://compliance.microsoft.com) eDiscovery-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="a6823-109">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="a6823-110">Klik in het linkernavigatiedeelvenster van Microsoft 365 compliancecentrum op Alles weergeven **en** klik vervolgens op **eDiscovery > Core.**</span><span class="sxs-lookup"><span data-stu-id="a6823-110">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="a6823-111">Klik op **de pagina Core eDiscovery** op de naam van de zaak waarin u de wacht wilt houden.</span><span class="sxs-lookup"><span data-stu-id="a6823-111">On the **Core eDiscovery** page, click the name of the case that you want to create the hold in.</span></span>

4. <span data-ttu-id="a6823-112">Klik op **de startpagina** voor de zaak op **het tabblad** Zoekopdrachten.</span><span class="sxs-lookup"><span data-stu-id="a6823-112">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="a6823-113">Klik in **het** menu Acties onder aan de flyoutpagina op **Resultaten exporteren.**</span><span class="sxs-lookup"><span data-stu-id="a6823-113">On the **Actions** menu at the bottom of the flyout page, click **Export results**.</span></span>

   ![Optie Resultaten exporteren in het menu Acties](../media/ActionMenuExportResults.png)

   <span data-ttu-id="a6823-115">De werkstroom voor het exporteren van de resultaten van een zoekopdracht die is gekoppeld aan een Hoofd eDiscovery-zaak, is hetzelfde als het exporteren van de zoekresultaten voor een zoekopdracht op de pagina **Inhoud zoeken.**</span><span class="sxs-lookup"><span data-stu-id="a6823-115">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="a6823-116">Zie Zoekresultaten voor inhoud exporteren voor [stapsgewijse instructies.](export-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="a6823-116">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="a6823-117">Wanneer u zoekresultaten exporteert, kunt u de-duplicatie inschakelen, zodat slechts één kopie van een e-mailbericht wordt geëxporteerd, ook al zijn er mogelijk meerdere exemplaren van hetzelfde bericht gevonden in de postvakken die zijn doorzocht.</span><span class="sxs-lookup"><span data-stu-id="a6823-117">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="a6823-118">Zie [De-duplicatie in eDiscovery-zoekresultaten](de-duplication-in-ediscovery-search-results.md)voor meer informatie over de-duplicatie en hoe dubbele items worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="a6823-118">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

   <span data-ttu-id="a6823-119">Nadat u de export hebt gestart, worden de zoekresultaten voorbereid voor het downloaden, wat betekent dat ze worden overgebracht naar een door Microsoft verstrekte Azure Storage locatie in de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="a6823-119">After you start the export, the search results are prepared for downloading, which means they are transferred to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="a6823-120">Klik op **het tabblad** Export in de zaak om de lijst met exporttaken weer te geven.</span><span class="sxs-lookup"><span data-stu-id="a6823-120">Click the **Exports** tab in the case to display the list of export jobs.</span></span>
  
   ![Taken exporteren op het tabblad Exporteren in hoofd-eDiscovery-zaak](../media/CoreeDiscoveryExport.png)

   <span data-ttu-id="a6823-122">Mogelijk moet u op Vernieuwen klikken **om** de lijst met exporttaken bij te werken, zodat de exporttaken worden weergegeven die u hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a6823-122">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="a6823-123">Exporttaken hebben dezelfde naam als de bijbehorende zoekopdracht **met _Export** toegevoegd aan de zoeknaam.</span><span class="sxs-lookup"><span data-stu-id="a6823-123">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="a6823-124">Klik op de exportklus die u hebt gemaakt om statusgegevens weer te geven op de flyoutpagina.</span><span class="sxs-lookup"><span data-stu-id="a6823-124">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="a6823-125">Deze informatie bevat het percentage items dat is overgebracht naar de Azure Storage locatie.</span><span class="sxs-lookup"><span data-stu-id="a6823-125">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="a6823-126">Nadat alle items zijn overgedragen, klikt u op **Resultaten downloaden** om de zoekresultaten naar uw lokale computer te downloaden.</span><span class="sxs-lookup"><span data-stu-id="a6823-126">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="a6823-127">Zie Stap 2 in Zoekresultaten exporteren voor meer informatie over het downloaden [van zoekresultaten.](export-search-results.md#step-2-download-the-search-results)</span><span class="sxs-lookup"><span data-stu-id="a6823-127">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

### <a name="more-information-about-exporting-searches-from-a-case"></a><span data-ttu-id="a6823-128">Meer informatie over het exporteren van zoekopdrachten vanuit een zaak</span><span class="sxs-lookup"><span data-stu-id="a6823-128">More information about exporting searches from a case</span></span>

- <span data-ttu-id="a6823-129">Zie Een inhoudszoekrapport exporteren voor meer informatie over de exportbestanden die zijn opgenomen wanneer u zoekresultaten [exporteert.](export-a-content-search-report.md#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="a6823-129">For more information about the export files that are included when you export search results, see [Export a Content search report](export-a-content-search-report.md#whats-included-in-the-report).</span></span>

- <span data-ttu-id="a6823-130">Als u de export opnieuw start, hebben wijzigingen in de query's van de zoekopdrachten die deel uit maken van de exportklus, geen invloed op de zoekresultaten die worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="a6823-130">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="a6823-131">Wanneer u een export opnieuw start, wordt dezelfde gecombineerde zoekquery-taak uitgevoerd die werd uitgevoerd toen de exportklus werd gemaakt, opnieuw uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a6823-131">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="a6823-132">Als u een export opnieuw start, worden de vorige resultaten overschreven door de zoekresultaten die naar de Azure Storage locatie worden gekopieerd.</span><span class="sxs-lookup"><span data-stu-id="a6823-132">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="a6823-133">De vorige resultaten die zijn gekopieerd, zijn niet beschikbaar om te worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="a6823-133">The previous results that were copied won't be available to be downloaded.</span></span>
