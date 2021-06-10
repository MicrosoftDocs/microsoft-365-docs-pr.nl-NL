---
title: De grootte van PST-bestanden wijzigen bij het exporteren van eDiscovery-zoekresultaten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: U kunt de standaardgrootte wijzigen van PST-bestanden die naar uw computer worden gedownload wanneer u eDiscovery-zoekresultaten exporteert.
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2020
ms.locfileid: "52161451"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="00428-103">De grootte van PST-bestanden wijzigen bij het exporteren van eDiscovery-zoekresultaten</span><span class="sxs-lookup"><span data-stu-id="00428-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="00428-104">Wanneer u het hulpprogramma eDiscovery Export gebruikt om de e-mailresultaten van een eDiscovery-zoekopdracht te exporteren vanuit de verschillende Microsoft eDiscovery-hulpprogramma's, is de standaardgrootte van een PST-bestand dat kan worden geëxporteerd 10 GB.</span><span class="sxs-lookup"><span data-stu-id="00428-104">When you use the eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB.</span></span> <span data-ttu-id="00428-105">Als u deze standaardgrootte wilt wijzigen, kunt u het register Windows bewerken op de computer die u gebruikt om de zoekresultaten te exporteren.</span><span class="sxs-lookup"><span data-stu-id="00428-105">If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="00428-106">Een van de redenen hiervoor is dat een PST-bestand kan passen op verwisselbare media, zoals een dvd, een compacte schijf of een USB-station.</span><span class="sxs-lookup"><span data-stu-id="00428-106">One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="00428-107">Het hulpprogramma eDiscovery-export wordt gebruikt om de zoekresultaten te exporteren wanneer u het hulpprogramma Inhoud zoeken gebruikt in het Beveiligings- & Compliancecentrum, In-Place eDiscovery in Exchange Online en het eDiscovery-centrum in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="00428-107">The eDiscovery Export tool is used to export the search results when using the Content Search tool in the Security & Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="00428-108">Een registerinstelling maken om de grootte van PST-bestanden te wijzigen wanneer u eDiscovery-zoekresultaten exporteert</span><span class="sxs-lookup"><span data-stu-id="00428-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="00428-109">Voer de volgende procedure uit op de computer die u gebruikt om de resultaten van een eDiscovery-zoekopdracht te exporteren.</span><span class="sxs-lookup"><span data-stu-id="00428-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="00428-110">Sluit het hulpprogramma eDiscovery-export als deze is geopend.</span><span class="sxs-lookup"><span data-stu-id="00428-110">Close the eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="00428-111">Sla de volgende tekst op in een registerbestand van venster met een achtervoegsel van .reg; bijvoorbeeld PstExportSize.reg.</span><span class="sxs-lookup"><span data-stu-id="00428-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="00428-112">In het bovenstaande voorbeeld wordt de waarde ingesteld op  `PstSizeLimitInBytes` 1.073.741.824 bytes of ongeveer 1 GB.</span><span class="sxs-lookup"><span data-stu-id="00428-112">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB.</span></span> <span data-ttu-id="00428-113">Hier zijn enkele andere voorbeeldwaarden voor de  `PstSizeLimitInBytes` instelling.</span><span class="sxs-lookup"><span data-stu-id="00428-113">Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="00428-114">**Grootte in GB (ca.**</span><span class="sxs-lookup"><span data-stu-id="00428-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="00428-115">**Grootte in bytes**</span><span class="sxs-lookup"><span data-stu-id="00428-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="00428-116">0,7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="00428-116">0.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="00428-117">751619277</span><span class="sxs-lookup"><span data-stu-id="00428-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="00428-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="00428-118">2 GB</span></span>  <br/> |<span data-ttu-id="00428-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="00428-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="00428-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="00428-120">4 GB</span></span>  <br/> |<span data-ttu-id="00428-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="00428-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="00428-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="00428-122">8 GB</span></span>  <br/> |<span data-ttu-id="00428-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="00428-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="00428-124">Wijzig de `PstSizeLimitInBytes` waarde in de gewenste maximale grootte van een PST-bestand wanneer u zoekresultaten exporteert en sla het bestand vervolgens op.</span><span class="sxs-lookup"><span data-stu-id="00428-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="00428-125">Klik Windows Explorer op het REG-bestand dat u in de vorige stappen hebt gemaakt of dubbelklik erop.</span><span class="sxs-lookup"><span data-stu-id="00428-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="00428-126">Klik in het venster Gebruikerstoegangsbeheer op **Ja om** de registereditor de wijziging te laten maken.</span><span class="sxs-lookup"><span data-stu-id="00428-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="00428-127">Klik op Ja wanneer u wordt gevraagd om door te **gaan.**</span><span class="sxs-lookup"><span data-stu-id="00428-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="00428-128">In de registereditor wordt een bericht weergegeven dat de instelling is toegevoegd aan het register.</span><span class="sxs-lookup"><span data-stu-id="00428-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="00428-129">U kunt stap 3 tot en met 6 herhalen om de waarde voor de registerinstelling  `PstSizeLimitInBytes` te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="00428-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="00428-130">Veelgestelde vragen over het wijzigen van de standaardgrootte van PST-bestanden wanneer u eDiscovery-zoekresultaten exporteert</span><span class="sxs-lookup"><span data-stu-id="00428-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="00428-131">**Waarom is de standaardgrootte 10 GB?**</span><span class="sxs-lookup"><span data-stu-id="00428-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="00428-132">De standaardgrootte van 10 GB is gebaseerd op feedback van klanten. 10 GB is een goede balans tussen de optimale hoeveelheid inhoud in één PST en met een minimale kans op bestandscorruptie.</span><span class="sxs-lookup"><span data-stu-id="00428-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="00428-133">**Moet ik de standaardgrootte van PST-bestanden vergroten of verlagen?**</span><span class="sxs-lookup"><span data-stu-id="00428-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="00428-134">Klanten hebben de neiging om de groottelimiet te verlagen, zodat de zoekresultaten passen op verwisselbare media die ze fysiek naar andere locaties in hun organisatie kunnen verzenden.</span><span class="sxs-lookup"><span data-stu-id="00428-134">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship to other locations in their organization.</span></span> <span data-ttu-id="00428-135">U wordt niet aangeraden de standaardgrootte te vergroten, omdat PST-bestanden groter dan 10 GB mogelijk beschadigingsproblemen hebben.</span><span class="sxs-lookup"><span data-stu-id="00428-135">We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="00428-136">**Op welke computer moet ik dit doen?**</span><span class="sxs-lookup"><span data-stu-id="00428-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="00428-137">U moet de registerinstelling wijzigen op een lokale computer waar u het hulpprogramma eDiscovery-export op hebt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="00428-137">You need to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="00428-138">**Moet ik de computer opnieuw opstarten nadat ik deze instelling heb gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="00428-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="00428-139">Nee, u hoeft de computer niet opnieuw op te starten.</span><span class="sxs-lookup"><span data-stu-id="00428-139">No, you don't have to reboot the computer.</span></span> <span data-ttu-id="00428-140">Maar als het hulpprogramma voor eDiscovery-export wordt uitgevoerd, moet u het programma sluiten en opnieuw starten nadat u deze instelling hebt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="00428-140">But, if the eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="00428-141">**Wordt een bestaande registersleutel bewerkt of wordt er een nieuwe sleutel gemaakt?**</span><span class="sxs-lookup"><span data-stu-id="00428-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="00428-142">De eerste keer dat u het REG-bestand dat u in deze procedure hebt gemaakt, wordt een nieuwe registersleutel gemaakt.</span><span class="sxs-lookup"><span data-stu-id="00428-142">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="00428-143">Vervolgens wordt de instelling telkens bewerkt wanneer u het .reg-bewerkingsbestand wijzigt en opnieuw uitwerkt.</span><span class="sxs-lookup"><span data-stu-id="00428-143">Then the setting is edited each time you change and rerun the .reg edit file.</span></span>
