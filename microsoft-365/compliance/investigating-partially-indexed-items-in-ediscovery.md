---
title: Gedeeltelijk geïndexeerde items in eDiscovery onderzoeken
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: Lees hoe u gedeeltelijk geïndexeerde items (ook wel niet-geïndexeerde items genoemd) kunt beheren vanuit Exchange, SharePoint en OneDrive voor Bedrijven binnen uw organisatie.
ms.openlocfilehash: 539fd2687735a5ee14be543750becca8c6c3154c
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311452"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="970d9-103">Gedeeltelijk geïndexeerde items in eDiscovery onderzoeken</span><span class="sxs-lookup"><span data-stu-id="970d9-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="970d9-104">Een eDiscovery-zoekopdracht die u vanuit het Microsoft 365 compliancecentrum hebt uitgevoerd, bevat automatisch gedeeltelijk geïndexeerde items in de geschatte zoekresultaten wanneer u een zoekopdracht uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="970d9-104">An eDiscovery search that you run from the Microsoft 365 compliance center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="970d9-105">Gedeeltelijk geïndexeerde items Exchange postvakitems en documenten op SharePoint en OneDrive voor Bedrijven sites die om een of andere reden niet volledig zijn geïndexeerd voor zoeken.</span><span class="sxs-lookup"><span data-stu-id="970d9-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="970d9-106">De meeste e-mailberichten en sitedocumenten worden geïndexeerd omdat ze binnen de [indexeringslimieten voor e-mailberichten vallen.](limits-for-content-search.md#indexing-limits-for-email-messages)</span><span class="sxs-lookup"><span data-stu-id="970d9-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="970d9-107">Sommige items kunnen deze indexeringslimieten echter overschrijden en worden gedeeltelijk geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="970d9-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="970d9-108">Hier volgen andere redenen waarom items niet kunnen worden geïndexeerd voor zoeken en worden geretourneerd als gedeeltelijk geïndexeerde items wanneer u een eDiscovery-zoekopdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="970d9-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run an eDiscovery search:</span></span>
  
- <span data-ttu-id="970d9-109">E-mailberichten hebben een bijgevoegd bestand zonder een geldige handler, zoals afbeeldingsbestanden; Dit is de meest voorkomende oorzaak van gedeeltelijk geïndexeerde e-mailitems.</span><span class="sxs-lookup"><span data-stu-id="970d9-109">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items.</span></span>

- <span data-ttu-id="970d9-110">Te veel bestanden die zijn gekoppeld aan een e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="970d9-110">Too many files attached to an email message.</span></span>

- <span data-ttu-id="970d9-111">Een bestand dat aan een e-mailbericht is gekoppeld, is te groot.</span><span class="sxs-lookup"><span data-stu-id="970d9-111">A file attached to an email message is too large.</span></span>

- <span data-ttu-id="970d9-112">Het bestandstype wordt ondersteund voor indexering, maar er is een indexeringsfout opgetreden voor een specifiek bestand.</span><span class="sxs-lookup"><span data-stu-id="970d9-112">The file type is supported for indexing but an indexing error occurred for a specific file.</span></span>

<span data-ttu-id="970d9-113">Hoewel de inhoud verschilt, hebben de meeste organisaties minder dan 1% van de inhoud per volume en minder dan 12% van de inhoud per grootte die gedeeltelijk is geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="970d9-113">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="970d9-114">De reden voor het verschil tussen het volume en de grootte is dat grotere bestanden een hogere kans hebben om inhoud te bevatten die niet volledig kan worden geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="970d9-114">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="970d9-115">Waarom verandert het gedeeltelijk geïndexeerde aantal items voor een zoekopdracht?</span><span class="sxs-lookup"><span data-stu-id="970d9-115">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="970d9-116">Nadat u een eDiscovery-zoekopdracht hebt uitgevoerd, worden het totale aantal en de grootte van gedeeltelijk geïndexeerde items op de gezochte locaties weergegeven in de zoekresultaatstatistieken die worden weergegeven in de gedetailleerde statistieken voor de zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="970d9-116">After you run an eDiscovery search, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="970d9-117">Let op: dit worden  *niet-geïndexeerde items*  genoemd in de zoekstatistieken.</span><span class="sxs-lookup"><span data-stu-id="970d9-117">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="970d9-118">Hier volgen enkele zaken die van invloed zijn op het aantal gedeeltelijk geïndexeerde items dat wordt geretourneerd in de zoekresultaten:</span><span class="sxs-lookup"><span data-stu-id="970d9-118">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span>
  
- <span data-ttu-id="970d9-119">Als een item gedeeltelijk is geïndexeerd en overeenkomt met de zoekquery, wordt dit opgenomen in zowel het aantal (en de grootte) van zoekresultaatitems als gedeeltelijk geïndexeerde items.</span><span class="sxs-lookup"><span data-stu-id="970d9-119">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="970d9-120">Wanneer de resultaten van dezelfde zoekopdracht echter worden geëxporteerd, wordt het item alleen opgenomen met een set zoekresultaten. het is niet opgenomen als een gedeeltelijk geïndexeerd item.</span><span class="sxs-lookup"><span data-stu-id="970d9-120">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>

- <span data-ttu-id="970d9-121">Gedeeltelijk geïndexeerde items op SharePoint- en *OneDrive-sites* worden niet opgenomen in de schatting van gedeeltelijk geïndexeerde items die worden weergegeven in de gedetailleerde statistieken voor de zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="970d9-121">Partially indexed items located in SharePoint and OneDrive sites *are not* included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="970d9-122">Gedeeltelijk geïndexeerde items kunnen echter worden geëxporteerd wanneer u de resultaten van een eDiscovery-zoekopdracht exporteert.</span><span class="sxs-lookup"><span data-stu-id="970d9-122">However, partially indexed items can be exported when you export the results of an eDiscovery search.</span></span> <span data-ttu-id="970d9-123">Als u bijvoorbeeld alleen op sites zoekt, is het geschatte aantal gedeeltelijk geïndexeerde items nul.</span><span class="sxs-lookup"><span data-stu-id="970d9-123">For example, if you only search sites, the estimated number partially indexed items will be zero.</span></span>
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="970d9-124">De verhouding van gedeeltelijk geïndexeerde items in uw organisatie berekenen</span><span class="sxs-lookup"><span data-stu-id="970d9-124">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="970d9-125">Als u de blootstelling van uw organisatie aan gedeeltelijk geïndexeerde items wilt begrijpen, kunt u zoeken naar alle inhoud in alle postvakken (met behulp van een lege trefwoordquery).</span><span class="sxs-lookup"><span data-stu-id="970d9-125">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="970d9-126">In het volgende voorbeeld zijn er 1.629.904 (146,46 GB) volledig geïndexeerde items en 10.025 (10,27 GB) gedeeltelijk geïndexeerde items.</span><span class="sxs-lookup"><span data-stu-id="970d9-126">In the following example, there are 1,629,904 (146.46 GB) fully indexed items and 10,025 (10.27 GB) partially indexed items.</span></span>
  
![Voorbeeld van zoekstatistieken met gedeeltelijk geïndexeerde items](../media/PartiallyIndexedItemsTest.png)
  
<span data-ttu-id="970d9-128">U kunt het percentage gedeeltelijk geïndexeerde items bepalen met behulp van de volgende berekeningen.</span><span class="sxs-lookup"><span data-stu-id="970d9-128">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="970d9-129">**De verhouding van gedeeltelijk geïndexeerde items in uw organisatie berekenen:**</span><span class="sxs-lookup"><span data-stu-id="970d9-129">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`

`(10025/1629904) x 100 = 0.62%`

<span data-ttu-id="970d9-130">Door de zoekresultaten uit het vorige voorbeeld te gebruiken, wordt 0,62% van alle postvakken gedeeltelijk geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="970d9-130">By using the search results from the previous example, 0.62% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="970d9-131">**Het percentage van de grootte van gedeeltelijk geïndexeerde items in uw organisatie berekenen:**</span><span class="sxs-lookup"><span data-stu-id="970d9-131">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(10.27 GB/146.46 MB) x 100 = 7.0%`

<span data-ttu-id="970d9-132">In het vorige voorbeeld is 7% van de totale grootte van postvakitems afkomstig van gedeeltelijk geïndexeerde items.</span><span class="sxs-lookup"><span data-stu-id="970d9-132">So in the previous example, 7% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="970d9-133">Zoals eerder vermeld hebben de meeste organisaties minder dan 1% van de inhoud per volume en minder dan 12% van de inhoud per grootte die gedeeltelijk is geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="970d9-133">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="970d9-134">Werken met gedeeltelijk geïndexeerde items</span><span class="sxs-lookup"><span data-stu-id="970d9-134">Working with partially indexed items</span></span>

<span data-ttu-id="970d9-135">In gevallen waarin u items gedeeltelijk moet onderzoeken om te controleren of [](export-a-content-search-report.md) deze geen relevante informatie bevatten, kunt u een inhoudszoekrapport exporteren dat informatie bevat over gedeeltelijk geïndexeerde items.</span><span class="sxs-lookup"><span data-stu-id="970d9-135">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="970d9-136">Wanneer u een inhoudszoekrapport exporteert, moet u een van de exportopties kiezen die gedeeltelijk geïndexeerde items bevat.</span><span class="sxs-lookup"><span data-stu-id="970d9-136">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span>
  
![De tweede of derde optie kiezen om gedeeltelijk geïndexeerde items te exporteren](../media/PartiallyIndexedItemsExportOptions.png)
  
<span data-ttu-id="970d9-138">Wanneer u eDiscovery-zoekresultaten of een zoekrapport exporteert met een van deze opties, bevat de export een rapport met de naam Niet-geïndexeerde Items.csv.</span><span class="sxs-lookup"><span data-stu-id="970d9-138">When you export eDiscovery search results or a search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="970d9-139">Dit rapport bevat de meeste van dezelfde informatie als het ResultsLog.csv bestand. Het niet-geïndexeerde Items.csv bevat echter ook twee velden die betrekking hebben op gedeeltelijk geïndexeerde items: **Foutlabels** en **fouteigenschappen.**</span><span class="sxs-lookup"><span data-stu-id="970d9-139">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="970d9-140">Deze velden bevatten informatie over de indexeringsfout voor elk gedeeltelijk geïndexeerd item.</span><span class="sxs-lookup"><span data-stu-id="970d9-140">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="970d9-141">Als u de gegevens in deze twee velden gebruikt, kunt u bepalen of de indexeringsfout voor een bepaald effect heeft op uw onderzoek.</span><span class="sxs-lookup"><span data-stu-id="970d9-141">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="970d9-142">Als dat zo is, kunt u een gerichte zoekopdracht uitvoeren en specifieke e-mailberichten en SharePoint- of OneDrive-documenten ophalen en exporteren, zodat u ze kunt onderzoeken om te bepalen of ze relevant zijn voor uw onderzoek.</span><span class="sxs-lookup"><span data-stu-id="970d9-142">If it does, you can perform a targeted search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="970d9-143">Zie Een [CSV-bestand](csv-file-for-an-id-list-content-search.md)voorbereiden voor een gerichte zoekopdracht in Office 365.</span><span class="sxs-lookup"><span data-stu-id="970d9-143">For step-by-step instructions, see [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>

> [!NOTE]
> <span data-ttu-id="970d9-144">Het niet-geïndexeerde Items.csv bevat ook velden met de naam **Fouttype** en **Foutbericht.**</span><span class="sxs-lookup"><span data-stu-id="970d9-144">The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="970d9-145">Dit zijn oudere velden die informatie bevatten die  lijkt  op de informatie in de velden Foutlabels en Fouteigenschappen, maar met minder gedetailleerde informatie.</span><span class="sxs-lookup"><span data-stu-id="970d9-145">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="970d9-146">U kunt deze oudere velden veilig negeren.</span><span class="sxs-lookup"><span data-stu-id="970d9-146">You can safely ignore these legacy fields.</span></span>
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="970d9-147">Fouten met betrekking tot gedeeltelijk geïndexeerde items</span><span class="sxs-lookup"><span data-stu-id="970d9-147">Errors related to partially indexed items</span></span>

<span data-ttu-id="970d9-148">Foutlabels zijn gemaakt uit twee gegevens, de fout en het bestandstype.</span><span class="sxs-lookup"><span data-stu-id="970d9-148">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="970d9-149">In dit fout-/bestandstypepaar bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="970d9-149">For example, in this error/file-type pair:</span></span>

```text
 parseroutputsize_xls
```

 <span data-ttu-id="970d9-150">`parseroutputsize` is de fout en `xls` is het bestandstype van het bestand waar de fout is opgetreden.</span><span class="sxs-lookup"><span data-stu-id="970d9-150">`parseroutputsize` is the error and `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="970d9-151">In gevallen waarin het bestandstype niet is herkend of het bestandstype niet van toepassing is op de fout, ziet u de waarde in plaats van `noformat` het bestandstype.</span><span class="sxs-lookup"><span data-stu-id="970d9-151">In cases where the file type wasn't recognized or the file type didn't apply to the error, you will see the value `noformat` in place of the file type.</span></span>
  
<span data-ttu-id="970d9-152">Hieronder volgt een lijst met indexeringsfouten en een beschrijving van de mogelijke oorzaak van de fout.</span><span class="sxs-lookup"><span data-stu-id="970d9-152">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
| <span data-ttu-id="970d9-153">Foutlabel</span><span class="sxs-lookup"><span data-stu-id="970d9-153">Error tag</span></span> | <span data-ttu-id="970d9-154">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="970d9-154">Description</span></span> |
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="970d9-155">Een e-mailbericht had te veel bijlagen en sommige van deze bijlagen zijn niet verwerkt.</span><span class="sxs-lookup"><span data-stu-id="970d9-155">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="970d9-156">In de inhoudsherhaal- en documentparser zijn te veel niveaus met bijlagen gevonden die zijn genest in andere bijlagen.</span><span class="sxs-lookup"><span data-stu-id="970d9-156">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="970d9-157">Sommige van deze bijlagen zijn niet verwerkt.</span><span class="sxs-lookup"><span data-stu-id="970d9-157">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="970d9-158">De decoderen van een bijlage is mislukt omdat deze RMS-beveiligd was.</span><span class="sxs-lookup"><span data-stu-id="970d9-158">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="970d9-159">Een bestand dat aan een e-mailbericht is gekoppeld, was te groot en kon niet worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="970d9-159">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="970d9-160">Bij het schrijven van het verwerkte e-mailbericht naar de index was een van de indexeerbare eigenschappen te groot en werd afgekapt.</span><span class="sxs-lookup"><span data-stu-id="970d9-160">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="970d9-161">De afgekapte eigenschappen worden weergegeven in het veld Fouteigenschappen.</span><span class="sxs-lookup"><span data-stu-id="970d9-161">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="970d9-162">Een e-mailbericht bevatte tekst die niet kon worden verwerkt als geldige Unicode.</span><span class="sxs-lookup"><span data-stu-id="970d9-162">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="970d9-163">Indexering voor dit item kan onvolledig zijn.</span><span class="sxs-lookup"><span data-stu-id="970d9-163">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="970d9-164">De inhoud van bijlage of e-mailbericht is versleuteld en Microsoft 365 de inhoud niet kan decoderen.</span><span class="sxs-lookup"><span data-stu-id="970d9-164">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="970d9-165">Er is een onbekende fout opgetreden tijdens het parseren.</span><span class="sxs-lookup"><span data-stu-id="970d9-165">An unknown error occurred during parsing.</span></span> <span data-ttu-id="970d9-166">Dit is meestal het gevolg van een software bug of een servicestoring.</span><span class="sxs-lookup"><span data-stu-id="970d9-166">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="970d9-167">Een bijlage was te groot om de parser te verwerken en de parsing van die bijlage is niet of niet voltooid.</span><span class="sxs-lookup"><span data-stu-id="970d9-167">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="970d9-168">Een bijlage is verkeerd vervormd en kan niet worden verwerkt door de parser.</span><span class="sxs-lookup"><span data-stu-id="970d9-168">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="970d9-169">Dit resultaat kan worden veroorzaakt door oude bestandsindelingen, bestanden die zijn gemaakt door incompatibele software of virussen die zich voordoen als iets anders dan geclaimd.</span><span class="sxs-lookup"><span data-stu-id="970d9-169">This result can be due to old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="970d9-170">De uitvoer van de parsing van een bijlage was te groot en moest worden afgekapt.</span><span class="sxs-lookup"><span data-stu-id="970d9-170">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="970d9-171">Een bijlage had een bestandstype dat Microsoft 365 niet kon detecteren.</span><span class="sxs-lookup"><span data-stu-id="970d9-171">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="970d9-172">Een bijlage had een bestandstype dat Office 365 kon detecteren, maar het parseren van dat bestandstype wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="970d9-172">An attachment had a file type that Office 365 could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="970d9-173">De waarde van een e-mail eigenschap in Exchange Store was te groot om te worden opgehaald en het bericht kon niet worden verwerkt.</span><span class="sxs-lookup"><span data-stu-id="970d9-173">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="970d9-174">Dit gebeurt meestal alleen met de body-eigenschap van een e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="970d9-174">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="970d9-175">De inhoudsherhaaler kan een met RMS beveiligd bericht niet decoderen.</span><span class="sxs-lookup"><span data-stu-id="970d9-175">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="970d9-176">Er zijn te veel woorden in het document geïdentificeerd tijdens indexering.</span><span class="sxs-lookup"><span data-stu-id="970d9-176">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="970d9-177">De verwerking van de eigenschap is gestopt wanneer de limiet wordt bereikt en de eigenschap wordt afgekapt.</span><span class="sxs-lookup"><span data-stu-id="970d9-177">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |

<span data-ttu-id="970d9-178">Foutvelden beschrijven welke velden worden beïnvloed door de verwerkingsfout die wordt weergegeven in het veld Foutlabels.</span><span class="sxs-lookup"><span data-stu-id="970d9-178">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="970d9-179">Als u een eigenschap zoekt, zoals of , hebben fouten in de hoofdbeslag van het bericht geen invloed op de  `subject`  `participants` resultaten van uw zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="970d9-179">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="970d9-180">Dit kan handig zijn bij het bepalen van precies welke gedeeltelijk geïndexeerde items u mogelijk verder moet onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="970d9-180">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="970d9-181">Een PowerShell-script gebruiken om de blootstelling van uw organisatie aan gedeeltelijk geïndexeerde e-mailitems te bepalen</span><span class="sxs-lookup"><span data-stu-id="970d9-181">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="970d9-182">In de volgende stappen ziet u hoe u een PowerShell-script kunt uitvoeren dat zoekt naar alle items in alle Exchange-postvakken en vervolgens een rapport genereert over de verhouding van uw organisatie van gedeeltelijk geïndexeerde e-mailitems (op aantal en grootte) en het aantal items (en het bestandstype) voor elke indexeringsfout die optreedt.</span><span class="sxs-lookup"><span data-stu-id="970d9-182">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="970d9-183">Gebruik de foutcodebeschrijvingen in de vorige sectie om de indexeringsfout te identificeren.</span><span class="sxs-lookup"><span data-stu-id="970d9-183">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="970d9-184">Sla de volgende tekst op in een Windows PowerShell scriptbestand met behulp van een achtervoegsel voor bestandsnaam van .ps1; `PartiallyIndexedItems.ps1`bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="970d9-184">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

   ```powershell
     write-host "**************************************************"
     write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "**************************************************"
     " " 
     # Create a search with Error Tags Refinders enabled
     Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
     New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
     Start-ComplianceSearch "RefinerTest"
     # Loop while search is in progress
     do{
         Write-host "Waiting for search to complete..."
         Start-Sleep -s 5
         $complianceSearch = Get-ComplianceSearch "RefinerTest"
     }while ($complianceSearch.Status -ne 'Completed')
     $refiners = $complianceSearch.Refiners | ConvertFrom-Json
     $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
     $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
     $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
     " "
     "===== Partially indexed items ====="
     "         Total          Ratio"
     "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
     "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
     " "
     Write-Host ===== Reasons for partially indexed items =====
     foreach($errorTagProperty in $errorTagProperties)
     {
         $name = $refiners.Entries.($errorTagProperty.Name).Name
         $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
         $frag = $name.Split("{_}")
         $errorTag = $frag[0]
         $fileType = $frag[1]
         if ($errorTag -ne $lastErrorTag)
         {
             $errorTag
         }
         "    " + $fileType + " => " + $count
         $lastErrorTag = $errorTag
     }
   ```

2. <span data-ttu-id="970d9-185">[Verbinding maken met Beveiligings- en compliancecentrum van Powershell](/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="970d9-185">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

3. <span data-ttu-id="970d9-186">Ga in & PowerShell naar de map waar u het script hebt opgeslagen in stap 1 en voer het script uit. bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="970d9-186">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

<span data-ttu-id="970d9-187">Hier is een voorbeeld van de uitvoer die door het script wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="970d9-187">Here's an example fo the output returned by the script.</span></span>
  
![Voorbeeld van uitvoer van script dat een rapport genereert over de blootstelling van uw organisatie aan gedeeltelijk geïndexeerde e-mailitems](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> <span data-ttu-id="970d9-189">Noteer het volgende:</span><span class="sxs-lookup"><span data-stu-id="970d9-189">Note the following:</span></span>
>  
> - <span data-ttu-id="970d9-190">Het totale aantal en de grootte van e-mailitems en de verhouding van uw organisatie van gedeeltelijk geïndexeerde e-mailitems (per aantal en per grootte).</span><span class="sxs-lookup"><span data-stu-id="970d9-190">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size).</span></span>
> 
> - <span data-ttu-id="970d9-191">Een lijstfoutlabels en de bijbehorende bestandstypen waarvoor de fout is opgetreden.</span><span class="sxs-lookup"><span data-stu-id="970d9-191">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="970d9-192">Zie ook</span><span class="sxs-lookup"><span data-stu-id="970d9-192">See also</span></span>

[<span data-ttu-id="970d9-193">Gedeeltelijk geïndexeerde items in eDiscovery</span><span class="sxs-lookup"><span data-stu-id="970d9-193">Partially indexed items in eDiscovery</span></span>](partially-indexed-items-in-content-search.md)