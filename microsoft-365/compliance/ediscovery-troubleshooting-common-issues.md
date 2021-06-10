---
title: Veelvoorkomende problemen met eDiscovery oplossen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Meer informatie over eenvoudige stappen voor het oplossen van problemen die u kunt ondernemen om veelvoorkomende problemen in Office 365 eDiscovery op te lossen.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28c092cefbdd8add46d3f36aa118e230d16a918a
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822236"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a><span data-ttu-id="fe491-103">Veelvoorkomende eDiscovery-problemen onderzoeken, oplossen en oplossen</span><span class="sxs-lookup"><span data-stu-id="fe491-103">Investigate, troubleshoot, and resolve common eDiscovery issues</span></span>

<span data-ttu-id="fe491-104">Dit onderwerp gaat over eenvoudige stappen voor het oplossen van problemen die u kunt ondernemen om problemen te identificeren en op te lossen die u tijdens een eDiscovery-zoekopdracht of elders in het eDiscovery-proces kunt tegenkomen.</span><span class="sxs-lookup"><span data-stu-id="fe491-104">This topic covers basic troubleshooting steps you can take to identify and resolve issues you may encounter during an eDiscovery search or elsewhere in the eDiscovery process.</span></span> <span data-ttu-id="fe491-105">Voor het oplossen van een aantal van deze scenario's is hulp nodig van Microsoft Support.</span><span class="sxs-lookup"><span data-stu-id="fe491-105">Resolving some of these scenarios requires help from Microsoft Support.</span></span> <span data-ttu-id="fe491-106">Informatie over wanneer u contact op wilt nemen met Microsoft Support, wordt opgenomen in de stappen voor de oplossing.</span><span class="sxs-lookup"><span data-stu-id="fe491-106">Information on when to contact Microsoft Support is included in the resolution steps.</span></span>

## <a name="errorissue-ambiguous-location"></a><span data-ttu-id="fe491-107">Fout/probleem: onduidelijke locatie</span><span class="sxs-lookup"><span data-stu-id="fe491-107">Error/issue: Ambiguous location</span></span>

<span data-ttu-id="fe491-108">Als u de postvaklocatie van de gebruiker probeert toe te voegen om te zoeken en er dubbele of conflicterende objecten met dezelfde gebruikers-id in de EOP-adreslijst (Exchange Online Protection) staan, krijgt u deze foutmelding: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .</span><span class="sxs-lookup"><span data-stu-id="fe491-108">If you try to add user's mailbox location to search and there are duplicate or conflicting objects with the same userID in the Exchange Online Protection (EOP) directory, you receive this error: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous`.</span></span>

### <a name="resolution"></a><span data-ttu-id="fe491-109">Oplossing</span><span class="sxs-lookup"><span data-stu-id="fe491-109">Resolution</span></span>

<span data-ttu-id="fe491-110">Controleer op dubbele gebruikers of distributielijst met dezelfde gebruikers-id.</span><span class="sxs-lookup"><span data-stu-id="fe491-110">Check for duplicate users or distribution list with the same user ID.</span></span>

1. <span data-ttu-id="fe491-111">Verbinding maken [naar Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="fe491-111">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="fe491-112">Voer de volgende opdracht uit om alle exemplaren van de gebruikersnaam op te halen:</span><span class="sxs-lookup"><span data-stu-id="fe491-112">Run the following command to retrieve all instances of the username:</span></span>

    ```powershell
    Get-Recipient <username>
    ```

   <span data-ttu-id="fe491-113">De uitvoer voor 'useralias@contoso.com' lijkt op het volgende:</span><span class="sxs-lookup"><span data-stu-id="fe491-113">The output for 'useralias@contoso.com' would be similar to the following:</span></span>

   > 
   > |<span data-ttu-id="fe491-114">Naam</span><span class="sxs-lookup"><span data-stu-id="fe491-114">Name</span></span>|<span data-ttu-id="fe491-115">RecipientType</span><span class="sxs-lookup"><span data-stu-id="fe491-115">RecipientType</span></span>|
   > |---|---|
   > |<span data-ttu-id="fe491-116">Alias, gebruiker</span><span class="sxs-lookup"><span data-stu-id="fe491-116">Alias, User</span></span>|<span data-ttu-id="fe491-117">MailUser</span><span class="sxs-lookup"><span data-stu-id="fe491-117">MailUser</span></span>|
   > |<span data-ttu-id="fe491-118">Alias, gebruiker</span><span class="sxs-lookup"><span data-stu-id="fe491-118">Alias, User</span></span>|<span data-ttu-id="fe491-119">Gebruiker</span><span class="sxs-lookup"><span data-stu-id="fe491-119">User</span></span>|

3. <span data-ttu-id="fe491-120">Als meerdere gebruikers worden geretourneerd, zoekt u het conflicterende object en lost u het op.</span><span class="sxs-lookup"><span data-stu-id="fe491-120">If multiple users are returned, locate and fix the conflicting object.</span></span>

## <a name="errorissue-search-fails-on-specific-locations"></a><span data-ttu-id="fe491-121">Fout/probleem: Zoeken mislukt op specifieke locaties</span><span class="sxs-lookup"><span data-stu-id="fe491-121">Error/issue: Search fails on specific locations</span></span>

<span data-ttu-id="fe491-122">Een eDiscovery- of inhoudszoekactie kan de volgende fout opleveren: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span><span class="sxs-lookup"><span data-stu-id="fe491-122">An eDiscovery or content search may yield the following error: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`</span></span>

![Schermafbeelding van zoekspecifieke locatie mislukt](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a><span data-ttu-id="fe491-124">Oplossing</span><span class="sxs-lookup"><span data-stu-id="fe491-124">Resolution</span></span>

<span data-ttu-id="fe491-125">Als u deze foutmelding krijgt, raden we u aan de locaties te controleren die niet zijn gevonden in de zoekopdracht en de zoekopdracht vervolgens alleen op de mislukte locaties opnieuw uit te proberen.</span><span class="sxs-lookup"><span data-stu-id="fe491-125">If you receive this error, we recommend that you verify the locations that failed in the search  then rerun the search only on the failed locations.</span></span>

1. <span data-ttu-id="fe491-126">Verbinding maken [naar Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) en voer vervolgens de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="fe491-126">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="fe491-127">Bekijk vanuit de PowerShell-uitvoer de mislukte locaties in het foutenveld of van de statusdetails in de fout uit de zoekuitvoer.</span><span class="sxs-lookup"><span data-stu-id="fe491-127">From the PowerShell output, view the failed locations in the errors field or from the status details in the error from the search output.</span></span>

3. <span data-ttu-id="fe491-128">U kunt de eDiscovery-zoekopdracht alleen op de mislukte locaties opnieuw proberen.</span><span class="sxs-lookup"><span data-stu-id="fe491-128">Retry the eDiscovery search on the failed locations only.</span></span>

4. <span data-ttu-id="fe491-129">Zie Mislukte locaties opnieuw proberen [](/Office365/SecurityCompliance/retry-failed-content-search) voor meer stappen voor het oplossen van problemen als u deze fouten blijft ontvangen.</span><span class="sxs-lookup"><span data-stu-id="fe491-129">If you continue to receive these errors, see [Retry failed locations](/Office365/SecurityCompliance/retry-failed-content-search) for more troubleshooting steps.</span></span>

## <a name="errorissue-file-not-found"></a><span data-ttu-id="fe491-130">Fout/probleem: Bestand niet gevonden</span><span class="sxs-lookup"><span data-stu-id="fe491-130">Error/issue: File not found</span></span>

<span data-ttu-id="fe491-131">Bij het uitvoeren van een eDiscovery-zoekopdracht met SharePoint Online- en One Drive For Business-locaties, ontvangt u mogelijk de fout, hoewel het bestand zich `File Not Found` op de site bevindt.</span><span class="sxs-lookup"><span data-stu-id="fe491-131">When running an eDiscovery search that includes SharePoint Online and One Drive For Business locations, you may receive the error `File Not Found` although the file is located on the site.</span></span> <span data-ttu-id="fe491-132">Deze fout wordt weergegeven in de exportwaarschuwingen en errors.csv of overgeslagen items.csv.</span><span class="sxs-lookup"><span data-stu-id="fe491-132">This error will be in the export warnings and errors.csv or skipped items.csv.</span></span> <span data-ttu-id="fe491-133">Dit kan optreden als het bestand niet kan worden gevonden op de site of als de index verouderd is.</span><span class="sxs-lookup"><span data-stu-id="fe491-133">This may occur if the file can't be found on the site or if the index is out of date.</span></span> <span data-ttu-id="fe491-134">Hier is de tekst van een werkelijke fout (met nadruk toegevoegd).</span><span class="sxs-lookup"><span data-stu-id="fe491-134">Here's the text of an actual error (with emphasis added).</span></span>

> <span data-ttu-id="fe491-135">28.06.2019 10:02:19_FailedToExportItem_Failed om inhoud te downloaden.</span><span class="sxs-lookup"><span data-stu-id="fe491-135">28.06.2019 10:02:19_FailedToExportItem_Failed to download content.</span></span> <span data-ttu-id="fe491-136">Aanvullende diagnostische informatie: Microsoft. Office. Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Kan niet worden gedownload van inhoud 6ea52149-91cd-4965-b5bb-82ca6a3ec9be van het type Document.</span><span class="sxs-lookup"><span data-stu-id="fe491-136">Additional diagnostic info : Microsoft.Office.Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Failed to download from content 6ea52149-91cd-4965-b5bb-82ca6a3ec9be of type Document.</span></span> <span data-ttu-id="fe491-137">Correlatie-id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span><span class="sxs-lookup"><span data-stu-id="fe491-137">Correlation Id: 3bd84722-937b-4c23-b61b-08d6fba9ec32.</span></span> <span data-ttu-id="fe491-138">ServerErrorCode: -2147024894 ---> Microsoft. SharePoint. Client.ServerException: ***Bestand niet gevonden.***</span><span class="sxs-lookup"><span data-stu-id="fe491-138">ServerErrorCode: -2147024894 ---> Microsoft.SharePoint.Client.ServerException: ***File Not Found***.</span></span> <span data-ttu-id="fe491-139">bij Microsoft. SharePoint. Client.ClientRequest.ProcessResponseStream(Stream responseStream) bij Microsoft. SharePoint. Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span><span class="sxs-lookup"><span data-stu-id="fe491-139">at Microsoft.SharePoint.Client.ClientRequest.ProcessResponseStream(Stream responseStream) at Microsoft.SharePoint.Client.ClientRequest.ProcessResponse() --- End of inner exception stack trace ---</span></span>

### <a name="resolution"></a><span data-ttu-id="fe491-140">Oplossing</span><span class="sxs-lookup"><span data-stu-id="fe491-140">Resolution</span></span>

1. <span data-ttu-id="fe491-141">Controleer de locatie die is geïdentificeerd in de zoekopdracht om ervoor te zorgen dat de locatie van het bestand juist is en toegevoegd aan de zoeklocaties.</span><span class="sxs-lookup"><span data-stu-id="fe491-141">Check location identified in the search to ensure that the location of the file is correct and added in the search locations.</span></span>

2. <span data-ttu-id="fe491-142">Gebruik de procedures bij [Handmatig aanvragen voor het crawlen](/sharepoint/crawl-site-content) en opnieuw indexeren van een site, bibliotheek of lijst om de site opnieuw te indexeren.</span><span class="sxs-lookup"><span data-stu-id="fe491-142">Use the procedures at [Manually request crawling and re-indexing of a site, a library, or a list](/sharepoint/crawl-site-content) to reindex the site.</span></span>

## <a name="errorissue-this-file-wasnt-exported-because-it-doesnt-exist-anymore-the-file-was-included-in-the-count-of-estimated-search-results-because-its-still-listed-in-the-index-the-file-will-eventually-be-removed-from-the-index-and-wont-cause-an-error-in-the-future"></a><span data-ttu-id="fe491-143">Fout/probleem: Dit bestand is niet geëxporteerd omdat het niet meer bestaat.</span><span class="sxs-lookup"><span data-stu-id="fe491-143">Error/issue: This file wasn't exported because it doesn't exist anymore.</span></span> <span data-ttu-id="fe491-144">Het bestand is opgenomen in het aantal geschatte zoekresultaten omdat het nog steeds in de index wordt vermeld.</span><span class="sxs-lookup"><span data-stu-id="fe491-144">The file was included in the count of estimated search results because it's still listed in the index.</span></span> <span data-ttu-id="fe491-145">Het bestand wordt uiteindelijk uit de index verwijderd en veroorzaakt in de toekomst geen fout.</span><span class="sxs-lookup"><span data-stu-id="fe491-145">The file will eventually be removed from the index, and won't cause an error in the future.</span></span>

<span data-ttu-id="fe491-146">Mogelijk ziet u deze fout bij het uitvoeren van een eDiscovery-zoekopdracht met SharePoint Online en One Drive For Business-locaties.</span><span class="sxs-lookup"><span data-stu-id="fe491-146">You may see that error when running an eDiscovery search that includes SharePoint Online and One Drive For Business locations.</span></span> <span data-ttu-id="fe491-147">eDiscovery is afhankelijk van de SPO-index om de bestandslocaties te identificeren.</span><span class="sxs-lookup"><span data-stu-id="fe491-147">eDiscovery relies on teh SPO index to identify the file locations.</span></span> <span data-ttu-id="fe491-148">Als het bestand is verwijderd, maar de SPO-index nog niet is bijgewerkt, kan deze fout optreden.</span><span class="sxs-lookup"><span data-stu-id="fe491-148">If the file was deleted but the SPO index was not yet updated this error may occur.</span></span>

### <a name="resolution"></a><span data-ttu-id="fe491-149">Oplossing</span><span class="sxs-lookup"><span data-stu-id="fe491-149">Resolution</span></span> 
<span data-ttu-id="fe491-150">Open de SPO-locatie en controleer of dit bestand er inderdaad niet is.</span><span class="sxs-lookup"><span data-stu-id="fe491-150">Open the SPO location and verify that this file indeed is not there.</span></span>
<span data-ttu-id="fe491-151">Voorgestelde oplossing is om de site handmatig opnieuw te indexeren of te wachten totdat de site opnieuw wordt geïndexeerd door het automatische achtergrondproces.</span><span class="sxs-lookup"><span data-stu-id="fe491-151">Suggested solution is to manually reindex the site, or wait till the site reindexes by the automatic background process.</span></span>


## <a name="errorissue-this-search-result-was-not-downloaded-as-it-is-a-folder-or-other-artefact-that-cant-be-downloaded-by-itself-any-items-inside-the-folder-or-library-will-be-downloaded"></a><span data-ttu-id="fe491-152">Fout/probleem: Dit zoekresultaat is niet gedownload omdat het een map of ander artefact is dat niet zelf kan worden gedownload, items in de map of bibliotheek worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="fe491-152">Error/issue: This search result was not downloaded as it is a folder or other artefact that can't be downloaded by itself, any items inside the folder or library will be downloaded.</span></span>

<span data-ttu-id="fe491-153">Mogelijk ziet u deze fout bij het uitvoeren van een eDiscovery-zoekopdracht met SharePoint Online en One Drive For Business-locaties.</span><span class="sxs-lookup"><span data-stu-id="fe491-153">You may see that error when running an eDiscovery search that includes SharePoint Online and One Drive For Business locations.</span></span> <span data-ttu-id="fe491-154">Het betekent dat we het item dat in de index is gerapporteerd, zouden proberen te exporteren, maar het bleek een map te zijn, zodat we het niet hebben geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="fe491-154">It means that we were going to try and export the item reported in the index, but it turned out to be a folder so we did not export it.</span></span> <span data-ttu-id="fe491-155">Zoals in de fout wordt vermeld, exporteren we geen mapitems, maar exporteren we wel de inhoud ervan.</span><span class="sxs-lookup"><span data-stu-id="fe491-155">As mentioned in the error, we don't export folder items but we do export their contents.</span></span>


## <a name="errorissue-search-fails-because-recipient-is-not-found"></a><span data-ttu-id="fe491-156">Fout/probleem: Zoeken mislukt omdat geadresseerde niet wordt gevonden</span><span class="sxs-lookup"><span data-stu-id="fe491-156">Error/issue: Search fails because recipient is not found</span></span>

<span data-ttu-id="fe491-157">Een eDiscovery-zoekopdracht mislukt met de fout de `recipient not found` .</span><span class="sxs-lookup"><span data-stu-id="fe491-157">An eDiscovery search fails with error the `recipient not found`.</span></span> <span data-ttu-id="fe491-158">Deze fout kan optreden als het gebruikersobject niet kan worden gevonden in Exchange Online Protection (EOP) omdat het object niet is gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="fe491-158">This error may occur if the user object cannot be found in Exchange Online Protection (EOP) because the object has not synced.</span></span>

### <a name="resolution"></a><span data-ttu-id="fe491-159">Oplossing</span><span class="sxs-lookup"><span data-stu-id="fe491-159">Resolution</span></span>

1. <span data-ttu-id="fe491-160">Verbinding maken [powershell Exchange Online gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="fe491-160">Connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="fe491-161">Voer de volgende opdracht uit om te controleren of de gebruiker is gesynchroniseerd met Exchange Online Protection:</span><span class="sxs-lookup"><span data-stu-id="fe491-161">Run the following command to check if the user is synced to Exchange Online Protection:</span></span>

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. <span data-ttu-id="fe491-162">Er moet een e-mailgebruikersobject zijn voor de gebruikersvraag.</span><span class="sxs-lookup"><span data-stu-id="fe491-162">There should be a mail user object for the user question.</span></span> <span data-ttu-id="fe491-163">Als er niets wordt geretourneerd, onderzoekt u het gebruikersobject.</span><span class="sxs-lookup"><span data-stu-id="fe491-163">If nothing is returned, investigate the user object.</span></span> <span data-ttu-id="fe491-164">Neem contact op met Microsoft Support als het object niet kan worden gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="fe491-164">Contact Microsoft Support if the object can't be synced.</span></span>

## <a name="errorissue-exporting-search-results-is-slow"></a><span data-ttu-id="fe491-165">Fout/probleem: Het exporteren van zoekresultaten is traag</span><span class="sxs-lookup"><span data-stu-id="fe491-165">Error/issue: Exporting search results is slow</span></span>

<span data-ttu-id="fe491-166">Wanneer u zoekresultaten exporteert vanuit eDiscovery of Inhoud zoeken in het beveiligings- en compliancecentrum, duurt de download langer dan verwacht.</span><span class="sxs-lookup"><span data-stu-id="fe491-166">When exporting search results from eDiscovery or Content Search in the Security and Compliance center, the download takes longer than expected.</span></span>  <span data-ttu-id="fe491-167">U kunt controleren hoeveel gegevens moeten worden gedownload en de exportsnelheid mogelijk verhogen.</span><span class="sxs-lookup"><span data-stu-id="fe491-167">You can check to see the amount of data to be download and possibly increase the export speed.</span></span>

### <a name="resolution"></a><span data-ttu-id="fe491-168">Oplossing</span><span class="sxs-lookup"><span data-stu-id="fe491-168">Resolution</span></span>

1. <span data-ttu-id="fe491-169">Verbinding maken [naar Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) en voer vervolgens de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="fe491-169">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. <span data-ttu-id="fe491-170">Zoek de hoeveelheid gegevens die moet worden gedownload in de parameters SearchResults en SearchStatistics.</span><span class="sxs-lookup"><span data-stu-id="fe491-170">Find the amount of data to be downloaded in the SearchResults and SearchStatistics parameters.</span></span>

3. <span data-ttu-id="fe491-171">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="fe491-171">Run the following command:</span></span>

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. <span data-ttu-id="fe491-172">Zoek in het veld Resultaten de gegevens die zijn geëxporteerd en bekijk eventuele fouten die zijn aangetroffen.</span><span class="sxs-lookup"><span data-stu-id="fe491-172">In the results field, find the data that has been exported and view any errors encountered.</span></span>

5. <span data-ttu-id="fe491-173">Controleer het trace.log-bestand in de adreslijst waar u de inhoud naar hebt geëxporteerd op eventuele fouten.</span><span class="sxs-lookup"><span data-stu-id="fe491-173">Check the trace.log file located in the directory that you exported the content to for any errors.</span></span>

6. <span data-ttu-id="fe491-174">Als u nog steeds problemen hebt, kunt u zoekopdrachten die een grote reeks resultaten retourneren, verdelen in kleinere zoekopdrachten.</span><span class="sxs-lookup"><span data-stu-id="fe491-174">If you still have issues, consider dividing searches that return a large set of results into smaller searches.</span></span> <span data-ttu-id="fe491-175">U kunt bijvoorbeeld datumbereiken in zoekquery's gebruiken om een kleinere reeks resultaten te retourneren die sneller kunnen worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="fe491-175">For example, you can use date ranges in search queries to return a smaller set of results that can be downloaded faster.</span></span>

## <a name="errorissue-internal-server-error-500-occurred"></a><span data-ttu-id="fe491-176">Fout/probleem: 'Interne serverfout (500) is opgetreden'</span><span class="sxs-lookup"><span data-stu-id="fe491-176">Error/issue: "Internal server error (500) occurred"</span></span>

<span data-ttu-id="fe491-177">Bij het uitvoeren van een eDiscovery-zoekopdracht, als de zoekopdracht voortdurend mislukt met een fout die lijkt op 'Interne serverfout (500) is opgetreden', moet u de zoekopdracht mogelijk alleen opnieuw uitvoeren op specifieke postvaklocaties.</span><span class="sxs-lookup"><span data-stu-id="fe491-177">When running an eDiscovery search, if the search continually fails with error similar to "Internal server error (500) occurred", you may need rerun the search only on specific mailbox locations.</span></span>

![Schermafbeelding van interne serverfout 500](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a><span data-ttu-id="fe491-179">Oplossing</span><span class="sxs-lookup"><span data-stu-id="fe491-179">Resolution</span></span>

1. <span data-ttu-id="fe491-180">Deel de zoekopdracht op in kleinere zoekopdrachten en voer de zoekopdracht opnieuw uit.</span><span class="sxs-lookup"><span data-stu-id="fe491-180">Break the search into smaller searches and run the search again.</span></span>  <span data-ttu-id="fe491-181">Probeer een kleiner datumbereik te gebruiken of beperk het aantal locaties dat wordt gezocht.</span><span class="sxs-lookup"><span data-stu-id="fe491-181">Try using a smaller date range or limit the number of locations being searched.</span></span>

2. <span data-ttu-id="fe491-182">Verbinding maken [naar Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) en voer vervolgens de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="fe491-182">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command:</span></span>

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. <span data-ttu-id="fe491-183">Bekijk de uitvoer op resultaten en fouten.</span><span class="sxs-lookup"><span data-stu-id="fe491-183">Examine the output for results and errors.</span></span>

4. <span data-ttu-id="fe491-184">Bekijk het trace.log-bestand.</span><span class="sxs-lookup"><span data-stu-id="fe491-184">Examine the trace.log file.</span></span> <span data-ttu-id="fe491-185">De map bevindt zich in dezelfde map waar u de zoekresultaten naar hebt geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="fe491-185">It's located  in the same folder that you exported the search results to.</span></span>

5. <span data-ttu-id="fe491-186">Contact Microsoft Support.</span><span class="sxs-lookup"><span data-stu-id="fe491-186">Contact Microsoft Support.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="fe491-187">Fout/probleem: de synchronisatie van de in-en-uit-standen wordt niet gesynchroniseerd</span><span class="sxs-lookup"><span data-stu-id="fe491-187">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="fe491-188">eDiscovery Case Hold Policy Sync Distribution error.</span><span class="sxs-lookup"><span data-stu-id="fe491-188">eDiscovery Case Hold Policy Sync Distribution error.</span></span> <span data-ttu-id="fe491-189">De fout leest:</span><span class="sxs-lookup"><span data-stu-id="fe491-189">The error reads:</span></span>

> <span data-ttu-id="fe491-190">'Resources: het implementeren van het beleid duurt langer dan verwacht.</span><span class="sxs-lookup"><span data-stu-id="fe491-190">"Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="fe491-191">Het kan nog twee uur duren voordat de uiteindelijke implementatiestatus is bijgewerkt, dus kijk over een paar uur terug.</span><span class="sxs-lookup"><span data-stu-id="fe491-191">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

### <a name="resolution"></a><span data-ttu-id="fe491-192">Oplossing</span><span class="sxs-lookup"><span data-stu-id="fe491-192">Resolution</span></span>

1. <span data-ttu-id="fe491-193">Verbinding maken naar [Security & Compliance Center PowerShell en](/powershell/exchange/connect-to-scc-powershell) voer vervolgens de volgende opdracht uit voor een eDiscovery-case hold:</span><span class="sxs-lookup"><span data-stu-id="fe491-193">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and then run the following command for an eDiscovery case hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    <span data-ttu-id="fe491-194">Voer voor een bewaarbeleid de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="fe491-194">For a retention policy, run the following command:</span></span>

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. <span data-ttu-id="fe491-195">Bekijk de waarde in de parameter DistributionDetail op fouten als volgt:</span><span class="sxs-lookup"><span data-stu-id="fe491-195">Examine the value in the DistributionDetail parameter for errors like the following:</span></span>

   > <span data-ttu-id="fe491-196">Fout: Resources: het implementeren van het beleid duurt langer dan verwacht.</span><span class="sxs-lookup"><span data-stu-id="fe491-196">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="fe491-197">Het kan nog twee uur duren voordat de uiteindelijke implementatiestatus is bijgewerkt, dus kijk over een paar uur terug.</span><span class="sxs-lookup"><span data-stu-id="fe491-197">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours."</span></span>

3. <span data-ttu-id="fe491-198">Probeer de parameter RetryDistribution uit te voeren op het beleid in kwestie:</span><span class="sxs-lookup"><span data-stu-id="fe491-198">Try running the RetryDistribution parameter on the policy in question:</span></span>

   <span data-ttu-id="fe491-199">Voor eDiscovery geldt het volgende:</span><span class="sxs-lookup"><span data-stu-id="fe491-199">For eDiscovery case holds:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   <span data-ttu-id="fe491-200">Voor bewaarbeleid:</span><span class="sxs-lookup"><span data-stu-id="fe491-200">For retention policies:</span></span>

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. <span data-ttu-id="fe491-201">Contact Microsoft Support.</span><span class="sxs-lookup"><span data-stu-id="fe491-201">Contact Microsoft Support.</span></span>

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a><span data-ttu-id="fe491-202">Fout: 'Aan de voorwaarde die is opgegeven met behulp van HTTP-voorwaardelijke kopteksten wordt niet voldaan'</span><span class="sxs-lookup"><span data-stu-id="fe491-202">Error: "The condition specified using HTTP conditional header(s) is not met"</span></span>

<span data-ttu-id="fe491-203">Wanneer u zoekresultaten downloadt met het eDiscovery-exporthulpmiddel, is het mogelijk dat u de volgende foutmelding ontvangt: Dit is een tijdelijke fout, die meestal optreedt op de Azure Storage `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` locatie.</span><span class="sxs-lookup"><span data-stu-id="fe491-203">When downloading search results using the eDiscovery Export Tool, it's possible you might receive the following error: `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` This is transient error, which typically occurs in the Azure Storage location.</span></span>

### <a name="resolution"></a><span data-ttu-id="fe491-204">Oplossing</span><span class="sxs-lookup"><span data-stu-id="fe491-204">Resolution</span></span>

<span data-ttu-id="fe491-205">Als u dit probleem wilt oplossen, [downloadt](export-search-results.md#step-2-download-the-search-results)u de zoekresultaten opnieuw, waarmee het eDiscovery-exporthulpmiddel opnieuw wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="fe491-205">To resolve this issue, retry [downloading the search results](export-search-results.md#step-2-download-the-search-results), which will restart the eDiscovery Export Tool.</span></span>

## <a name="errorissue-downloaded-export-shows-no-results"></a><span data-ttu-id="fe491-206">Fout/probleem: Gedownloade export toont geen resultaten</span><span class="sxs-lookup"><span data-stu-id="fe491-206">Error/issue: Downloaded export shows no results</span></span>

<span data-ttu-id="fe491-207">Na een geslaagde export toont de voltooide download via het exporthulpmiddel nul bestanden in de resultaten.</span><span class="sxs-lookup"><span data-stu-id="fe491-207">After a successful export, the completed download via the export tool shows zero files in the results.</span></span>

### <a name="resolution"></a><span data-ttu-id="fe491-208">Oplossing</span><span class="sxs-lookup"><span data-stu-id="fe491-208">Resolution</span></span>

<span data-ttu-id="fe491-209">Dit is een probleem aan de clientzijde en probeer de volgende stappen om het probleem te verhelpen:</span><span class="sxs-lookup"><span data-stu-id="fe491-209">This is a client-side issue and in order to remediate it, please attempt the following steps:</span></span>

1. <span data-ttu-id="fe491-210">Probeer een andere client/computer te downloaden.</span><span class="sxs-lookup"><span data-stu-id="fe491-210">Try using another client/machine to download.</span></span>

2. <span data-ttu-id="fe491-211">Verwijder oude zoekopdrachten die niet meer nodig zijn met [de cmdlet Remove-ComplianceSearch.](/powershell/module/exchange/remove-compliancesearch)</span><span class="sxs-lookup"><span data-stu-id="fe491-211">Remove old searches that are no longer needed using [Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) cmdlet.</span></span>

3. <span data-ttu-id="fe491-212">Zorg ervoor dat u downloadt naar een lokaal station.</span><span class="sxs-lookup"><span data-stu-id="fe491-212">Make sure to download to a local drive.</span></span>

4. <span data-ttu-id="fe491-213">Zorg ervoor dat de virusscanner niet wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="fe491-213">Make sure the virus scanner is not running.</span></span>

5. <span data-ttu-id="fe491-214">Zorg ervoor dat er geen andere export wordt gedownload naar dezelfde map of een bovenliggende map.</span><span class="sxs-lookup"><span data-stu-id="fe491-214">Make sure that no other export is downloading to the same folder or any parent folder.</span></span>

6. <span data-ttu-id="fe491-215">Als de vorige stappen niet werken, schakelt u het omkeren en de duplicatie uit.</span><span class="sxs-lookup"><span data-stu-id="fe491-215">If the previous steps did not work, disable zipping and de-duplication.</span></span>

7. <span data-ttu-id="fe491-216">Als dit werkt, is het probleem het gevolg van een lokale virusscanner of een schijfprobleem.</span><span class="sxs-lookup"><span data-stu-id="fe491-216">If this works then the issue is due to a local virus scanner or a disk issue.</span></span>
