---
title: Upload Binaries voor toepassingen
description: Aan de slag met Test Base voor M365
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
ms.openlocfilehash: 1c4ff6ac03989cc9be70e18a1b8634f2da11e721
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322817"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a><span data-ttu-id="15257-103">Stap 3: Upload, afhankelijkheden en scripts</span><span class="sxs-lookup"><span data-stu-id="15257-103">Step 3: Upload your binaries, dependencies, and scripts</span></span>

<span data-ttu-id="15257-104">Op dit tabblad uploadt u één zip-pakket met uw binaries, afhankelijkheden en scripts die worden gebruikt om uw testsuite uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="15257-104">On this tab, you will upload a single zip package containing your binaries, dependencies and scripts used to run your test suite.</span></span>

## <a name="upload-package-zip-file"></a><span data-ttu-id="15257-105">Upload pakket zip-bestand</span><span class="sxs-lookup"><span data-stu-id="15257-105">Upload package zip file</span></span>

![Upload binaries](Media/AddBinaries.png)

  - <span data-ttu-id="15257-107">Geüploade afhankelijkheden kunnen testkaders, scripting-engines of gegevens bevatten die worden gebruikt om uw toepassing of test cases uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="15257-107">Uploaded dependencies can include test frameworks, scripting engines or data that will be accessed to run your application or test cases.</span></span> <span data-ttu-id="15257-108">U kunt bijvoorbeeld Selenium en een webdriver-installatieprogramma uploaden om browsertests uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="15257-108">For example, you can upload Selenium and a webdriver installer to help run browser-based tests.</span></span>
  - <span data-ttu-id="15257-109">Het is de beste manier om ervoor te zorgen dat uw scriptactiviteiten modulair worden bewaard, dat wil zeggen.</span><span class="sxs-lookup"><span data-stu-id="15257-109">It is best practice to ensure your script activities are kept modular i.e.</span></span> 
    - <span data-ttu-id="15257-110">Het ```Install``` script voert alleen installatiebewerkingen uit.</span><span class="sxs-lookup"><span data-stu-id="15257-110">The ```Install``` script only performs install operations.</span></span>
    - <span data-ttu-id="15257-111">Het ```Launch``` script start alleen de toepassing.</span><span class="sxs-lookup"><span data-stu-id="15257-111">The ```Launch``` script only launches the application.</span></span>
    - <span data-ttu-id="15257-112">Het ```Close``` script sluit alleen de toepassing.</span><span class="sxs-lookup"><span data-stu-id="15257-112">The ```Close``` script only closes the application.</span></span>
    - <span data-ttu-id="15257-113">Met het ```Uninstall``` optionele script wordt de toepassing alleen verwijderd.</span><span class="sxs-lookup"><span data-stu-id="15257-113">The optional ```Uninstall``` script only uninstalls the application.</span></span>

<span data-ttu-id="15257-114">**Op dit moment ondersteunt de portal alleen PowerShell-scripts.**</span><span class="sxs-lookup"><span data-stu-id="15257-114">**Currently, the portal only supports PowerShell scripts.**</span></span>


## <a name="next-steps"></a><span data-ttu-id="15257-115">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="15257-115">Next steps</span></span> 

<span data-ttu-id="15257-116">Ga naar het volgende artikel om naar stap 4 te gaan: **Uw testtaken instellen.**</span><span class="sxs-lookup"><span data-stu-id="15257-116">Advance to the next article to go onto Step 4: **Set your Test Tasks**.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="15257-117">Terug</span><span class="sxs-lookup"><span data-stu-id="15257-117">Go back</span></span>](uploadApplication.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="15257-118">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="15257-118">Next step</span></span>](testtask.md)

