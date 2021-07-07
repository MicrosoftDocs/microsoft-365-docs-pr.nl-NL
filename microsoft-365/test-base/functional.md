---
title: Functionele tests op testbasis
description: Meer informatie over het testen van uw toepassing met uw bestaande geautomatiseerde functionele tests
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
ms.openlocfilehash: 7b5cb907756ec0fb746d303b3ab629e912bf9c96
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322847"
---
# <a name="functional-testing"></a><span data-ttu-id="969f1-103">Functioneel testen</span><span class="sxs-lookup"><span data-stu-id="969f1-103">Functional testing</span></span>

<span data-ttu-id="969f1-104">Als softwareleverancier kunt u nu aangepaste functionele tests uitvoeren, met behulp van het testkader van uw keuze- via de self-serve Test Base voor M365-portal.</span><span class="sxs-lookup"><span data-stu-id="969f1-104">As a software vendor, you can now perform custom functional tests, using the test framework of your choice - via the self-serve Test Base for M365 portal.</span></span> 

<span data-ttu-id="969f1-105">Toen we de service in eerste instantie startte, hebben we de standaardtests aangeboden. Dit is een vooraf gedefinieerde set tests die wordt uitgevoerd via gestandaardiseerde scripts.</span><span class="sxs-lookup"><span data-stu-id="969f1-105">When we initially launched the service, we offered the Out-of-box tests, which is a pre-defined set of tests driven through standardized scripting.</span></span> <span data-ttu-id="969f1-106">Dit kan echter niet tot volledige testdekking voor veel onafhankelijke softwareleveranciers (ISV's) komen.</span><span class="sxs-lookup"><span data-stu-id="969f1-106">This, however, could not achieve full test coverage for many Independent Software Vendors (ISVs).</span></span> 

<span data-ttu-id="969f1-107">Daarom bieden we onze isv's in antwoord op uw feedback de mogelijkheid om geautomatiseerde functionele tests te uploaden.</span><span class="sxs-lookup"><span data-stu-id="969f1-107">Hence, in response to your feedback, we are providing our ISVs with the ability to upload automated functional tests.</span></span>

<span data-ttu-id="969f1-108">Als u deze functie wilt gebruiken, volgt u de onderstaande stappen:</span><span class="sxs-lookup"><span data-stu-id="969f1-108">To use this feature, follow the steps below:</span></span>

1. <span data-ttu-id="969f1-109">Upload bestanden (binaries, afhankelijkheden en scripts) als één .zip pakket.</span><span class="sxs-lookup"><span data-stu-id="969f1-109">Upload your files (binaries, dependencies and scripts) as a single .zip package.</span></span>
2. <span data-ttu-id="969f1-110">Kies of u de test Virtuele machines (VM's) op verschillende uitvoeringspunten opnieuw wilt starten.</span><span class="sxs-lookup"><span data-stu-id="969f1-110">Choose if you want to reboot the test Virtual Machines (VMs) at various points of execution.</span></span>
3. <span data-ttu-id="969f1-111">Beschikbare opties voor uw scripts beheren.</span><span class="sxs-lookup"><span data-stu-id="969f1-111">Manage available options for your scripts.</span></span>
4. <span data-ttu-id="969f1-112">Kies wanneer u de update Windows VM wilt toepassen tijdens de uitvoering.</span><span class="sxs-lookup"><span data-stu-id="969f1-112">Choose when to apply the Windows update on the VM during execution.</span></span>

<span data-ttu-id="969f1-113">Gedetailleerde beschrijvingen van de bovenstaande stappen worden hieronder gemarkeerd:</span><span class="sxs-lookup"><span data-stu-id="969f1-113">Detailed descriptions of the above steps are highlighted below:</span></span>

<span data-ttu-id="969f1-114">**Upload een functioneel testpakket**</span><span class="sxs-lookup"><span data-stu-id="969f1-114">**Upload a functional test package**</span></span>

<span data-ttu-id="969f1-115">Als u wilt beginnen, gaat u naar de Upload pagina en selecteert u Upload nieuwe toepassing onder Toepassingscatalogus in het navigatiemenu aan de linkerkant van de testbasis voor M365-portal in Azure.</span><span class="sxs-lookup"><span data-stu-id="969f1-115">To get started, navigate to the Upload page, select Upload new application under Application catalog on the left-side navigation menu of the Test Base for M365 portal in Azure.</span></span> <span data-ttu-id="969f1-116">Van hier uit:</span><span class="sxs-lookup"><span data-stu-id="969f1-116">From there:</span></span>

<span data-ttu-id="969f1-117">Tab 1 - Voer basisgegevens in.</span><span class="sxs-lookup"><span data-stu-id="969f1-117">Tab 1 - Enter basic information.</span></span> <span data-ttu-id="969f1-118">Geef de naam en versie van uw toepassing op.</span><span class="sxs-lookup"><span data-stu-id="969f1-118">Provide the name and version of your application.</span></span> <span data-ttu-id="969f1-119">Selecteer in de optie Type test ```Functional tests``` de optie .</span><span class="sxs-lookup"><span data-stu-id="969f1-119">In the Type of test option, select ```Functional tests```.</span></span> 

<span data-ttu-id="969f1-120">*De optie Out-of-Box (OOB) is standaard vereist.*</span><span class="sxs-lookup"><span data-stu-id="969f1-120">*Note that the Out-of-Box (OOB) option is required by default.*</span></span>


![Het tabblad Functioneel testen selecteren](Media/functional_testing_tab1.png)

<span data-ttu-id="969f1-122">Tab 2 - Upload de onderdelen van uw pakket door een zip-bestand te uploaden met uw hele test (binaries, afhankelijkheden, scripts, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="969f1-122">Tab 2 - Upload the components of your package by uploading a zip file with your entire test (binaries, dependencies, scripts etc).</span></span> 

<span data-ttu-id="969f1-123">Zie aka.ms/usl-package-outline voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="969f1-123">See aka.ms/usl-package-outline for details.</span></span> <span data-ttu-id="969f1-124">(Opmerking: Zowel de out-of-box-testscripts als de inhoud van de functionele test moeten in hetzelfde zip-bestand worden geplaatst.</span><span class="sxs-lookup"><span data-stu-id="969f1-124">(Note: Both the Out-of-Box test scripts and the Functional test contents should be placed into the same zip file).</span></span> <span data-ttu-id="969f1-125">Momenteel is de bestandsgrootte beperkt tot 2 GB.</span><span class="sxs-lookup"><span data-stu-id="969f1-125">Currently, the file size is limited to 2GB.</span></span>

<span data-ttu-id="969f1-126">Tab 3- Configureer de taken Voor de out-of-box- en functionele test.</span><span class="sxs-lookup"><span data-stu-id="969f1-126">Tab 3 - Configure the Out-of-Box and Functional test tasks.</span></span> <span data-ttu-id="969f1-127">Kies hier het pad(en) naar de PowerShell-scripts die uw toepassing (voor Out-of-Box) installeren, starten, sluiten en verwijderen, evenals de pad(s) naar al uw aangepaste scripts om uw functionele test uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="969f1-127">Here, choose the path(s) to the PowerShell scripts that will install, launch, close, and uninstall your application (for Out-of-Box) as well as the path(s) to all your custom scripts to perform your functional test.</span></span> <span data-ttu-id="969f1-128">**(Opmerking: een script om de toepassing te verwijderen is optioneel).**</span><span class="sxs-lookup"><span data-stu-id="969f1-128">**(Note: A script to uninstall your application is optional).**</span></span>

<span data-ttu-id="969f1-129">Momenteel kunt u tussen 1 en 8 scripts uploaden voor uw functionele tests.</span><span class="sxs-lookup"><span data-stu-id="969f1-129">Currently, you can upload between 1 and 8 scripts for your functional tests.</span></span> <span data-ttu-id="969f1-130">(Een vriendelijke opmerking over dit bericht als u meer scripts nodig hebt!)</span><span class="sxs-lookup"><span data-stu-id="969f1-130">(Kindly comment on this post if you need more scripts!)</span></span>

![Upload maximaal 8 scripts met functionele tests](Media/functional_testing_tab3.png)

<span data-ttu-id="969f1-132">(Optioneel) Een herstart configureren na de installatie.</span><span class="sxs-lookup"><span data-stu-id="969f1-132">(Optional) Configure a restart after installation.</span></span> <span data-ttu-id="969f1-133">Voor sommige toepassingen is een herstart na de installatie vereist.</span><span class="sxs-lookup"><span data-stu-id="969f1-133">Some applications require a restart after installation.</span></span> 

<span data-ttu-id="969f1-134">Selecteer voor het specifieke script op het tabblad Taken als u een herstart wilt uitvoeren ```Reboot After Execution``` na de uitvoering van dat script.</span><span class="sxs-lookup"><span data-stu-id="969f1-134">Select ```Reboot After Execution``` for the specific Script in the Tasks tab if you would like a restart to be conducted after the execution of that script.</span></span>

<span data-ttu-id="969f1-135">Tab 4- Kies wanneer de update Windows wordt geïnstalleerd: De toepassing van de update-Windows update wordt uitgevoerd voordat een script naar keuze wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="969f1-135">Tab 4 - Choose when the Windows update gets installed: The application of the Windows Update patch is done before any script of your choice.</span></span> <span data-ttu-id="969f1-136">U wordt aangeraden een update Windows na de installatie van de toepassing te installeren om uw scenario's voor toepassingsgebruik in de echte wereld na te bootsen.</span><span class="sxs-lookup"><span data-stu-id="969f1-136">It is recommended that you install a Windows update after the application's installation to closely mimic your real-world application use scenarios.</span></span>

![De Windows update kan worden geïnstalleerd na een specifiek script](Media/functional_testing_tab4.png)

<span data-ttu-id="969f1-138">Tab 5- Bekijk en maak het pakket.</span><span class="sxs-lookup"><span data-stu-id="969f1-138">Tab 5 - Review and create the package.</span></span> <span data-ttu-id="969f1-139">Nadat u de bovenstaande stappen hebt voltooid, selecteert u ```Create``` om het uploadproces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="969f1-139">Once you have completed the steps listed above, select ```Create``` to finish the uploading process.</span></span>

<span data-ttu-id="969f1-140">Nadat uw pakket is gemaakt, kunt u de verificatiestatus van uw pakket controleren.</span><span class="sxs-lookup"><span data-stu-id="969f1-140">Once your package has been created, you can check the verification status of your package.</span></span>

<span data-ttu-id="969f1-141">We voeren een eerste test uit om uw toepassing te installeren, te starten, te sluiten en te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="969f1-141">We run an initial test to install, launch, close, and uninstall your application.</span></span> <span data-ttu-id="969f1-142">Op deze manier kunnen we controleren of uw pakket foutloos op onze service kan worden geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="969f1-142">This allows us to verify that your package can install on our service error-free.</span></span>

<span data-ttu-id="969f1-143">Het verificatieproces kan tot 24 uur duren.</span><span class="sxs-lookup"><span data-stu-id="969f1-143">The verification process could take up to 24 hours.</span></span> <span data-ttu-id="969f1-144">Wanneer de verificatie is voltooid, kunt u de status in het menu zien, wat een van de twee items ```Manage packages``` zou zijn:</span><span class="sxs-lookup"><span data-stu-id="969f1-144">Once verification is complete, you can see the status in the ```Manage packages``` menu, which would be one of two entries:</span></span>

1. <span data-ttu-id="969f1-145">Verificatie slaagt: het pakket wordt automatisch getest op pre-release Windows updates voor de os-builds die u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="969f1-145">Verification succeeds: The package will be automatically tested against pre-release Windows updates for the OS builds you selected.</span></span>
<span data-ttu-id="969f1-146">of</span><span class="sxs-lookup"><span data-stu-id="969f1-146">or</span></span>
2. <span data-ttu-id="969f1-147">Verificatie mislukt: U moet de oorzaken van de fout onderzoeken, het probleem oplossen en uw pakket opnieuw uploaden.</span><span class="sxs-lookup"><span data-stu-id="969f1-147">Verification fails: You will need to investigate the reasons for the failure, fix the issue, and re-upload your package.</span></span>

<span data-ttu-id="969f1-148">U ontvangt ook een melding van een van beide resultaten via het meldingspictogram in de Azure-portal.</span><span class="sxs-lookup"><span data-stu-id="969f1-148">You will also be notified of either outcome via the notification icon in the Azure portal.</span></span>
