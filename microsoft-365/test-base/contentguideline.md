---
title: Richtlijnen voor testpakketten
description: De richtlijnen rond testpakket bekijken
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322757"
---
# <a name="test-package-guidelines"></a><span data-ttu-id="aec39-103">Richtlijnen voor testpakketten</span><span class="sxs-lookup"><span data-stu-id="aec39-103">Test package guidelines</span></span>

## <a name="1---script-referencing"></a><span data-ttu-id="aec39-104">1. Referencing van scripts</span><span class="sxs-lookup"><span data-stu-id="aec39-104">1.   Script referencing</span></span>

<span data-ttu-id="aec39-105">Wanneer u een .zip naar de portal uploadt, wordt alle inhoud van dat bestand in een hoofdmap opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="aec39-105">When you upload a .zip file to the portal, we unzip all the content of that file into a root folder.</span></span> <span data-ttu-id="aec39-106">U hoeft geen code te schrijven om deze eerste bewerking uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="aec39-106">You do not need to write any code to do this initial unzip operation.</span></span> <span data-ttu-id="aec39-107">U kunt ook verwijzen naar een bestand in de .zip met behulp van het pad ten opzichte van het zip-bestand dat is geüpload.</span><span class="sxs-lookup"><span data-stu-id="aec39-107">You also can reference any file within the .zip by using the path relative to the zip file uploaded.</span></span>

<span data-ttu-id="aec39-108">In het onderstaande voorbeeld laten we zien hoe u vanuit het invoerveld op het tabblad Taken naar uw binaries/scripts kunt verwijzen. De tekst in blauw moet zonder aanhalingstekens worden ingevoerd in het **veld** **Scriptpad.**</span><span class="sxs-lookup"><span data-stu-id="aec39-108">In the example below, we show how you can reference your binaries/scripts from the input field in the Tasks tab. The text in blue should be entered into the **Script path** field **without the quotation marks.**</span></span>

<span data-ttu-id="aec39-109">Het is belangrijk dat u op de hoogte bent van de inhoud in het zip-bestand voordat u deze uploadt.</span><span class="sxs-lookup"><span data-stu-id="aec39-109">It is important you are aware of the content within your zip file before uploading it.</span></span> <span data-ttu-id="aec39-110">Vaak maakt uw lokale computer een hoofdmap onder het zip-bestand wanneer u een map omsingelt.</span><span class="sxs-lookup"><span data-stu-id="aec39-110">Often when zipping a folder, your local machine will create a main folder underneath the zip file.</span></span> <span data-ttu-id="aec39-111">In dit geval wordt de verwijzing weergegeven in vet **hieronder:**</span><span class="sxs-lookup"><span data-stu-id="aec39-111">In this case, the referencing will be as shown in **bold** below:</span></span>

 <span data-ttu-id="aec39-112">**Contoso_App_Folder.zip**</span><span class="sxs-lookup"><span data-stu-id="aec39-112">**Contoso_App_Folder.zip**</span></span>
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - <span data-ttu-id="aec39-113">ScriptX.ps1 – **"Contoso_App_Folder/ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="aec39-113">ScriptX.ps1 – **“Contoso_App_Folder/ScriptX.ps1”**</span></span>
  - <span data-ttu-id="aec39-114">Script.ps1 – **"Contoso_App_Folder/map1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="aec39-114">Script.ps1 – **“Contoso_App_Folder/folder1/script.ps1”**</span></span>

<span data-ttu-id="aec39-115">In andere tijden staan uw bestanden of inhoud mogelijk onder het zip-bestand, dat wil zeggen geen map op het tweede niveau:</span><span class="sxs-lookup"><span data-stu-id="aec39-115">Other times, your zip file may have your files or content right underneath it i.e. no 2nd-level folder:</span></span>

 <span data-ttu-id="aec39-116">**Zip_file_uploaded.zip**</span><span class="sxs-lookup"><span data-stu-id="aec39-116">**Zip_file_uploaded.zip**</span></span>
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="aec39-117">ScriptX.ps1 – **'ScriptX.ps1'**</span><span class="sxs-lookup"><span data-stu-id="aec39-117">ScriptX.ps1 – **“ScriptX.ps1”**</span></span>
  - <span data-ttu-id="aec39-118">Script.ps1 - **'map1/script.ps1'**</span><span class="sxs-lookup"><span data-stu-id="aec39-118">Script.ps1 – **“folder1/script.ps1”**</span></span>
  
## <a name="2---script-execution"></a><span data-ttu-id="aec39-119">2. Scriptuitvoering</span><span class="sxs-lookup"><span data-stu-id="aec39-119">2.   Script execution</span></span>

<span data-ttu-id="aec39-120">**Out-of-Box-tests:** Het toepassingspakket moet ten minste drie PowerShell-scripts bevatten die onbeheerd het installeren, starten en sluiten van de toepassing en de afhankelijkheden ervan uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="aec39-120">**Out-of-Box tests:** The application package needs to contain at least three PowerShell scripts that will execute unattended installing, launching, and closing of the application and its dependencies.</span></span> <span data-ttu-id="aec39-121">Elk script moet het controleren van zijn eigen vereisten afhandelen, het valideren van het is gelukt, evenals het opruimen na zichzelf (indien nodig).</span><span class="sxs-lookup"><span data-stu-id="aec39-121">Each script should handle checking its own prerequisites, validating it succeeded, as well as cleaning up after itself (if necessary).</span></span>

<span data-ttu-id="aec39-122">**Functionele tests:** Het toepassingspakket moet ten minste één PowerShell-script bevatten.</span><span class="sxs-lookup"><span data-stu-id="aec39-122">**Functional tests:** The application package needs to contain at least one PowerShell script.</span></span> <span data-ttu-id="aec39-123">Wanneer meer dan één script wordt geleverd, worden de scripts uitgevoerd in de uploadreeks en wordt het uitvoeren van de volgende scripts door een fout in een bepaald script gestopt.</span><span class="sxs-lookup"><span data-stu-id="aec39-123">Where more than one script is provided, the scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>

### <a name="script-requirements"></a><span data-ttu-id="aec39-124">Scriptvereisten</span><span class="sxs-lookup"><span data-stu-id="aec39-124">Script requirements</span></span>

<span data-ttu-id="aec39-125">• PowerShell versie 5.1+</span><span class="sxs-lookup"><span data-stu-id="aec39-125">•   PowerShell Version 5.1+</span></span>     

<span data-ttu-id="aec39-126">• Onbeheerde uitvoering</span><span class="sxs-lookup"><span data-stu-id="aec39-126">•   Unattended execution</span></span>    

<span data-ttu-id="aec39-127">• Foutmeldingscode</span><span class="sxs-lookup"><span data-stu-id="aec39-127">•   Error return code</span></span>               

<span data-ttu-id="aec39-128">• Succes valideren</span><span class="sxs-lookup"><span data-stu-id="aec39-128">•   Validate success</span></span>            

<span data-ttu-id="aec39-129">• Logboekregistratie voor een specifieke logboekmap</span><span class="sxs-lookup"><span data-stu-id="aec39-129">•   Logging to script specific log folder</span></span>

<span data-ttu-id="aec39-130">Elk script moet volledig onbeheerd worden uitgevoerd om de testpijplijn uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="aec39-130">Each script needs to run completely unattended to successfully execute in the test pipeline.</span></span>

> [!Note]
> <span data-ttu-id="aec39-131">Scripts moeten '0' retourneren bij geslaagde voltooiing en een foutcode zonder nul als er een fout optreedt tijdens de uitvoering.</span><span class="sxs-lookup"><span data-stu-id="aec39-131">Scripts should return “0” on successful completion and a non-zero error code if any error occurs during execution.</span></span>

<span data-ttu-id="aec39-132">Elk script moet valideren dat het is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="aec39-132">Each script should validate that it ran successfully.</span></span> <span data-ttu-id="aec39-133">Bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="aec39-133">E.g.</span></span> <span data-ttu-id="aec39-134">het installatiescript moet controleren op het bestaan van bepaalde binaries en/of registersleutels op het systeem, nadat de binaire installatie is uitgevoerd om er met een redelijke mate van vertrouwen voor te zorgen dat de installatie is geslaagd.</span><span class="sxs-lookup"><span data-stu-id="aec39-134">the install script should check for the existence of certain binaries and/or registry keys on the system, after the installer binary finishes executing to ensure with a reasonable degree of confidence that the installation was successful.</span></span> 

<span data-ttu-id="aec39-135">Dit is nodig om goed te kunnen vaststellen waar fouten optreden tijdens een test, bijvoorbeeld niet in staat om de toepassing te installeren of om de toepassing niet te kunnen starten.</span><span class="sxs-lookup"><span data-stu-id="aec39-135">This is necessary to properly diagnose where errors occur during a test run, e.g. unable to install the application successfully versus being unable to launch it.</span></span>

> [!Important]
> <span data-ttu-id="aec39-136">**Vermijd het volgende:** Scripts moeten de computer niet opnieuw opstarten, als een herstart noodzakelijk is, moet u dit opgeven tijdens het uploaden van uw scripts.</span><span class="sxs-lookup"><span data-stu-id="aec39-136">**Avoid the following:** Scripts should not reboot the machine, if a reboot is necessary please specify this during the upload of your scripts.</span></span>

## <a name="3---log-collection"></a><span data-ttu-id="aec39-137">3. Logboekverzameling</span><span class="sxs-lookup"><span data-stu-id="aec39-137">3.   Log collection</span></span>

<span data-ttu-id="aec39-138">Elk script moet alle logboeken die het genereert, uitvoeren in een map met de naam ```logs``` .</span><span class="sxs-lookup"><span data-stu-id="aec39-138">Each script should output any logs it generates into a folder named ```logs```.</span></span> <span data-ttu-id="aec39-139">Alle mappen in de map met de naam worden gekopieerd en ```logs``` gepresenteerd om te worden gedownload op de ```Test Results``` pagina.</span><span class="sxs-lookup"><span data-stu-id="aec39-139">All folders in the directory named ```logs``` will be copied and presented for download on the ```Test Results``` page.</span></span>

<span data-ttu-id="aec39-140">Met het installatiescript (dat zich mogelijk in de **map App/scripts/install** bevindt) kunnen de logboeken bijvoorbeeld worden uitgevoerd naar: **logs/install.log,** zodat het uiteindelijke logboek zich bevindt op: **Apps/scripts/install/logs/install.log.**</span><span class="sxs-lookup"><span data-stu-id="aec39-140">For example, the installation script (which may be located in the **App/scripts/install** directory) can output its logs to: **logs/install.log**, such that the final log will be at: **Apps/scripts/install/logs/install.log**</span></span>

<span data-ttu-id="aec39-141">Het systeem haalt het bestand samen met andere bestanden in andere mappen op en colleert het om ```install.log``` ```logs``` het te downloaden.</span><span class="sxs-lookup"><span data-stu-id="aec39-141">The system will pick up the ```install.log``` file along with other files within other ```logs``` folders and collate it for download.</span></span>


## <a name="4---application-binaries"></a><span data-ttu-id="aec39-142">4. Toepassings binaries</span><span class="sxs-lookup"><span data-stu-id="aec39-142">4.   Application binaries</span></span>

<span data-ttu-id="aec39-143">Binaries en afhankelijkheden moeten worden opgenomen in het enkele zip-bestand.</span><span class="sxs-lookup"><span data-stu-id="aec39-143">Any binaries and dependencies should be included in the single zip file.</span></span> 

<span data-ttu-id="aec39-144">Deze moeten alle benodigde gegevens bevatten voor de installatie van de toepassing (bijvoorbeeld het installatieprogramma van de toepassing); als de toepassing afhankelijk is van frameworks, zoals .NET Core/Standard of .NET Framework, moeten deze in het bestand worden opgenomen en correct worden verwezen in de meegeleverde scripts.</span><span class="sxs-lookup"><span data-stu-id="aec39-144">These should include everything necessary for installation of the application (e.g. the application installer); if the application has a dependency on any frameworks, such as .NET Core/Standard or .NET Framework, these should be included in the file and referenced correctly in the provided scripts.</span></span>


> [!Note]
> <span data-ttu-id="aec39-145">Het geüploade zip-bestand mag geen spaties of speciale tekens in de naam hebben</span><span class="sxs-lookup"><span data-stu-id="aec39-145">The uploaded zip file cannot have any spaces or special characters in its name</span></span>

## <a name="next-steps"></a><span data-ttu-id="aec39-146">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="aec39-146">Next steps</span></span>

<span data-ttu-id="aec39-147">Naar het volgende artikel gaan om enkele veelgestelde vragen **(veelgestelde vragen) weer te geven**</span><span class="sxs-lookup"><span data-stu-id="aec39-147">Advance to the next article to view some **Frequently Asked Questions (FAQ)**</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="aec39-148">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="aec39-148">Next step</span></span>](faq.md)
