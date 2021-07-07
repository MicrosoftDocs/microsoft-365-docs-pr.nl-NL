---
title: Testtaken instellen
description: Testtaken instellen
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
ms.openlocfilehash: 64abb5b10e3dc1d52b6baf8ceccd5aff2baacefe
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322560"
---
# <a name="step-4-the-tasks-tab"></a><span data-ttu-id="ec57f-103">Stap 4: het tabblad Taken</span><span class="sxs-lookup"><span data-stu-id="ec57f-103">Step 4: The tasks tab</span></span>

<span data-ttu-id="ec57f-104">Op het tabblad Taken worden de paden naar de testscripts verwacht in de zipmap die u hebt geüpload onder het tabblad Binaries.</span><span class="sxs-lookup"><span data-stu-id="ec57f-104">On the tasks tab, you are expected to provide the paths to your test scripts which are in the zip folder you uploaded under the binaries tab.</span></span>

  - <span data-ttu-id="ec57f-105">**Out-of-box testscripts:** Typ de relatieve paden naar uw installatie, start, sluit en verwijder scripts.</span><span class="sxs-lookup"><span data-stu-id="ec57f-105">**Out of Box Test Scripts:** Type in the relative paths to your install, launch, close and uninstall scripts.</span></span> <span data-ttu-id="ec57f-106">U hebt ook de optie om extra instellingen voor het installatiescript te selecteren.</span><span class="sxs-lookup"><span data-stu-id="ec57f-106">You also have the option to select additional settings for the install script.</span></span>
  - <span data-ttu-id="ec57f-107">**Functionele testscripts:** Typ het relatieve pad naar elk functioneel testscript dat is geüpload.</span><span class="sxs-lookup"><span data-stu-id="ec57f-107">**Functional Test Scripts:** Type in the relative path to each functional test script uploaded.</span></span> <span data-ttu-id="ec57f-108">U kunt extra functionele testscripts toevoegen met behulp van de ```Add Script``` knop.</span><span class="sxs-lookup"><span data-stu-id="ec57f-108">Additional functional test scripts can be added using the ```Add Script``` button.</span></span> <span data-ttu-id="ec57f-109">U hebt minimaal één (1) script nodig en kunt maximaal acht (8) functionele testscripts toevoegen.</span><span class="sxs-lookup"><span data-stu-id="ec57f-109">You need a minimum of one (1) script and can add up to eight (8) functional test scripts.</span></span> 
  
    <span data-ttu-id="ec57f-110">De scripts worden in de volgorde van uploaden uitgevoerd en een fout in een bepaald script stopt met het uitvoeren van de volgende scripts.</span><span class="sxs-lookup"><span data-stu-id="ec57f-110">The scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>
    <span data-ttu-id="ec57f-111">U hebt ook de optie om extra instellingen voor elk script te selecteren.</span><span class="sxs-lookup"><span data-stu-id="ec57f-111">You also have the option of selecting additional settings for each script provided.</span></span>

## <a name="set-script-path"></a><span data-ttu-id="ec57f-112">Scriptpad instellen</span><span class="sxs-lookup"><span data-stu-id="ec57f-112">Set script path</span></span>

![Afbeelding van testtaak](Media/testtask.png)

<span data-ttu-id="ec57f-114">Voorbeeld van het geven van het relatieve pad in een mapstructuur vindt u hieronder:</span><span class="sxs-lookup"><span data-stu-id="ec57f-114">Sample of how to provide the relative path on a folder structure is below:</span></span>

<span data-ttu-id="ec57f-115">_**Zip_file_uploaded**_</span><span class="sxs-lookup"><span data-stu-id="ec57f-115">_**Zip_file_uploaded**_</span></span>
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="ec57f-116">**ScriptX.ps1** zou hebben.</span><span class="sxs-lookup"><span data-stu-id="ec57f-116">**ScriptX.ps1** would have.</span></span> <span data-ttu-id="ec57f-117">_ScriptX.ps1_ als het relatieve pad.</span><span class="sxs-lookup"><span data-stu-id="ec57f-117">_ScriptX.ps1_ as the relative path.</span></span>
  - <span data-ttu-id="ec57f-118">**Script.ps1** _map1/script.ps1als_ het relatieve pad.</span><span class="sxs-lookup"><span data-stu-id="ec57f-118">**Script.ps1** would have _folder1/script.ps1_ as the relative path.</span></span>


## <a name="next-steps"></a><span data-ttu-id="ec57f-119">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="ec57f-119">Next steps</span></span>

<span data-ttu-id="ec57f-120">Details van het tabblad Testopties weergeven in het volgende artikel</span><span class="sxs-lookup"><span data-stu-id="ec57f-120">View details of the Test Options tab in the next article</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="ec57f-121">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="ec57f-121">Next step</span></span>](testoptions.md)
