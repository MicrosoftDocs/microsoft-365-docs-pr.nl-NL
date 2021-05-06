---
title: Rapporten uitschakelen wanneer u inhoudszoekresultaten exporteert
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: Bewerk het Windows register op uw lokale computer om rapporten uit te schakelen wanneer u de resultaten van een inhoudszoekactie exporteert vanuit het Beveiligings- & Compliancecentrum.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "52161473"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="8db26-103">Rapporten uitschakelen wanneer u inhoudszoekresultaten exporteert</span><span class="sxs-lookup"><span data-stu-id="8db26-103">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="8db26-104">Wanneer u het hulpprogramma eDiscovery Export gebruikt om de resultaten van een inhoudszoekactie te exporteren in het Beveiligings- & Compliancecentrum, worden met het hulpprogramma automatisch twee rapporten gemaakt en geëxporteerd die aanvullende informatie over de geëxporteerde inhoud bevatten.</span><span class="sxs-lookup"><span data-stu-id="8db26-104">When you use the eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="8db26-105">Deze rapporten zijn het Results.csv en het Manifest.xml-bestand (zie de sectie Veelgestelde vragen over het uitschakelen van [exportrapporten](#frequently-asked-questions-about-disabling-export-reports) in dit onderwerp voor gedetailleerde beschrijvingen van deze rapporten).</span><span class="sxs-lookup"><span data-stu-id="8db26-105">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="8db26-106">Omdat deze bestanden erg groot kunnen zijn, kunt u de downloadtijd versnellen en schijfruimte besparen door te voorkomen dat deze bestanden worden geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="8db26-106">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="8db26-107">U kunt dit doen door de Windows register op de computer te wijzigen die u gebruikt om de zoekresultaten te exporteren.</span><span class="sxs-lookup"><span data-stu-id="8db26-107">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="8db26-108">Als u de rapporten op een later tijdstip wilt opnemen, kunt u de registerinstelling bewerken.</span><span class="sxs-lookup"><span data-stu-id="8db26-108">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="8db26-109">Registerinstellingen maken om de exportrapporten uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="8db26-109">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="8db26-110">Voer de volgende procedure uit op de computer die u gebruikt om de resultaten te exporteren naar een inhoudszoekactie.</span><span class="sxs-lookup"><span data-stu-id="8db26-110">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="8db26-111">Sluit het hulpprogramma eDiscovery-export als deze is geopend.</span><span class="sxs-lookup"><span data-stu-id="8db26-111">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="8db26-112">Voer een of beide van de volgende stappen uit, afhankelijk van het exportrapport dat u wilt uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="8db26-112">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="8db26-113">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="8db26-113">**Results.csv**</span></span>
    
      <span data-ttu-id="8db26-114">Sla de volgende tekst op in een Windows registerbestand met behulp van een bestandsnaamachtervoegsel van .reg; bijvoorbeeld DisableResultsCsv.reg.</span><span class="sxs-lookup"><span data-stu-id="8db26-114">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="8db26-115">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="8db26-115">**Manifest.xml**</span></span>
    
      <span data-ttu-id="8db26-116">Sla de volgende tekst op in een Windows registerbestand met behulp van een bestandsnaamachtervoegsel van .reg; bijvoorbeeld DisableManifestXml.reg.</span><span class="sxs-lookup"><span data-stu-id="8db26-116">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="8db26-117">Klik Windows Explorer op het REG-bestand dat u in de vorige stappen hebt gemaakt of dubbelklik erop.</span><span class="sxs-lookup"><span data-stu-id="8db26-117">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="8db26-118">Klik in het venster Gebruikerstoegangsbeheer op **Ja om** de registereditor de wijziging te laten maken.</span><span class="sxs-lookup"><span data-stu-id="8db26-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="8db26-119">Klik op Ja wanneer u wordt gevraagd om door te **gaan.**</span><span class="sxs-lookup"><span data-stu-id="8db26-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="8db26-120">In de registereditor wordt een bericht weergegeven dat de instelling is toegevoegd aan het register.</span><span class="sxs-lookup"><span data-stu-id="8db26-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="8db26-121">Registerinstellingen bewerken om de exportrapporten opnieuw in te stellen</span><span class="sxs-lookup"><span data-stu-id="8db26-121">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="8db26-122">Als u de Results.csv- en Manifest.xml-rapporten hebt uitgeschakeld door de REG-bestanden in de vorige procedure te maken, kunt u deze bestanden bewerken om een rapport opnieuw in te stellen, zodat het wordt geëxporteerd met de zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="8db26-122">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="8db26-123">Voer nogmaals de volgende procedure uit op de computer die u gebruikt om de resultaten te exporteren naar een inhoudszoekactie.</span><span class="sxs-lookup"><span data-stu-id="8db26-123">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="8db26-124">Sluit het hulpprogramma eDiscovery-export als deze is geopend.</span><span class="sxs-lookup"><span data-stu-id="8db26-124">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="8db26-125">Bewerk een of beide .reg-bestanden die u in de vorige procedure hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8db26-125">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="8db26-126">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="8db26-126">**Results.csv**</span></span>
    
        <span data-ttu-id="8db26-127">Open het bestand DisableResultsCsv.reg in Kladblok, wijzig de waarde in `False` en sla het bestand `True` op.</span><span class="sxs-lookup"><span data-stu-id="8db26-127">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="8db26-128">Nadat u het bestand hebt bewerkt, ziet het er bijvoorbeeld als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="8db26-128">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="8db26-129">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="8db26-129">**Manifest.xml**</span></span>
    
        <span data-ttu-id="8db26-130">Open het bestand DisableManifestXml.reg in Kladblok, wijzig de waarde in `False` en sla het bestand `True` op.</span><span class="sxs-lookup"><span data-stu-id="8db26-130">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="8db26-131">Nadat u het bestand hebt bewerkt, ziet het er bijvoorbeeld als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="8db26-131">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="8db26-132">Klik Windows Explorer op een REG-bestand dat u in de vorige stap hebt bewerkt of dubbelklikt.</span><span class="sxs-lookup"><span data-stu-id="8db26-132">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="8db26-133">Klik in het venster Gebruikerstoegangsbeheer op **Ja om** de registereditor de wijziging te laten maken.</span><span class="sxs-lookup"><span data-stu-id="8db26-133">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="8db26-134">Klik op Ja wanneer u wordt gevraagd om door te **gaan.**</span><span class="sxs-lookup"><span data-stu-id="8db26-134">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="8db26-135">In de registereditor wordt een bericht weergegeven dat de instelling is toegevoegd aan het register.</span><span class="sxs-lookup"><span data-stu-id="8db26-135">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="8db26-136">Veelgestelde vragen over het uitschakelen van exportrapporten</span><span class="sxs-lookup"><span data-stu-id="8db26-136">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="8db26-137">**Wat zijn de Results.csv en Manifest.xml rapporten?**</span><span class="sxs-lookup"><span data-stu-id="8db26-137">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="8db26-138">De Results.csv en Manifest.xml bevatten aanvullende informatie over de inhoud die is geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="8db26-138">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="8db26-139">**Results.csv** Een Excel document met informatie over elk item dat als zoekresultaat wordt gedownload.</span><span class="sxs-lookup"><span data-stu-id="8db26-139">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="8db26-140">Voor e-mail bevat het resultatenlogboek informatie over elk bericht, waaronder:</span><span class="sxs-lookup"><span data-stu-id="8db26-140">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="8db26-141">De locatie van het bericht in het bronpostvak (inclusief of het bericht zich in het primaire of archiefpostvak bevindt).</span><span class="sxs-lookup"><span data-stu-id="8db26-141">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="8db26-142">De datum waarop het bericht is verzonden of ontvangen.</span><span class="sxs-lookup"><span data-stu-id="8db26-142">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="8db26-143">De onderwerpregel van het bericht.</span><span class="sxs-lookup"><span data-stu-id="8db26-143">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="8db26-144">De afzender en geadresseerden van het bericht.</span><span class="sxs-lookup"><span data-stu-id="8db26-144">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="8db26-145">Of het bericht een duplicaatbericht is als u de-duplicatie hebt ingeschakeld bij het exporteren van de zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="8db26-145">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="8db26-146">Dubbele berichten hebben een waarde in de kolom **Bovenliggend itemid** die het bericht als een duplicaat identificeert.</span><span class="sxs-lookup"><span data-stu-id="8db26-146">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="8db26-147">De waarde in de **kolom Bovenliggende item-id** is hetzelfde als de waarde in de **kolom ItemDocumentId** van het bericht dat is geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="8db26-147">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="8db26-148">Voor documenten van SharePoint en OneDrive voor Bedrijven sites bevat het resultatenlogboek informatie over elk document, waaronder:</span><span class="sxs-lookup"><span data-stu-id="8db26-148">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="8db26-149">De URL voor het document.</span><span class="sxs-lookup"><span data-stu-id="8db26-149">The URL for the document.</span></span>
    
  - <span data-ttu-id="8db26-150">De URL voor de siteverzameling waar het document zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="8db26-150">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="8db26-151">De datum waarop het document voor het laatst is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="8db26-151">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="8db26-152">De naam van het document (dat zich in de kolom Onderwerp in het resultatenlogboek bevindt).</span><span class="sxs-lookup"><span data-stu-id="8db26-152">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="8db26-153">**Manifest.xml** Een manifestbestand (in XML-indeling) dat informatie bevat over elk item dat in de zoekresultaten wordt opgenomen.</span><span class="sxs-lookup"><span data-stu-id="8db26-153">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="8db26-154">De informatie in dit rapport is hetzelfde als het Results.csv rapport, maar is in de indeling die is opgegeven door het EDRM (Electronic Discovery Reference Model).</span><span class="sxs-lookup"><span data-stu-id="8db26-154">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="8db26-155">Voor meer informatie over EDRM gaat u naar [https://www.edrm.net](https://www.edrm.net) .</span><span class="sxs-lookup"><span data-stu-id="8db26-155">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="8db26-156">**Wanneer moet ik het exporteren van deze rapporten uitschakelen?**</span><span class="sxs-lookup"><span data-stu-id="8db26-156">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="8db26-157">Dit hangt af van uw specifieke behoeften.</span><span class="sxs-lookup"><span data-stu-id="8db26-157">It depends on your specific needs.</span></span> <span data-ttu-id="8db26-158">Veel organisaties hebben geen aanvullende informatie over zoekresultaten nodig en hebben deze rapporten niet nodig.</span><span class="sxs-lookup"><span data-stu-id="8db26-158">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="8db26-159">**Op welke computer moet ik dit doen?**</span><span class="sxs-lookup"><span data-stu-id="8db26-159">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="8db26-160">U moet de registerinstelling wijzigen op een lokale computer waar u het hulpprogramma eDiscovery-export op uitvoert.</span><span class="sxs-lookup"><span data-stu-id="8db26-160">You have to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="8db26-161">**Moet ik de computer opnieuw starten nadat ik deze instelling heb gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="8db26-161">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="8db26-162">Nee, u hoeft de computer niet opnieuw op te starten.</span><span class="sxs-lookup"><span data-stu-id="8db26-162">No, you don't have to restart the computer.</span></span> <span data-ttu-id="8db26-163">Maar als het hulpprogramma eDiscovery-export wordt uitgevoerd, moet u het programma sluiten en opnieuw starten nadat u de registerinstelling hebt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="8db26-163">But if the eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="8db26-164">**Wordt een bestaande registersleutel bewerkt of wordt er een nieuwe sleutel gemaakt?**</span><span class="sxs-lookup"><span data-stu-id="8db26-164">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="8db26-165">De eerste keer dat u het REG-bestand dat u in de procedure in dit onderwerp hebt gemaakt, wordt een nieuwe registersleutel gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8db26-165">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="8db26-166">Vervolgens wordt de instelling telkens bewerkt wanneer u het .reg-bewerkingsbestand wijzigt en opnieuw uitwerkt.</span><span class="sxs-lookup"><span data-stu-id="8db26-166">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
