---
title: Uitsluitingen van automatiseringsmappen beheren
description: Voeg uitsluitingen van automatiseringsmappen toe om de bestanden te beheren die zijn uitgesloten van een geautomatiseerd onderzoek.
keywords: manage, automation, exclusion, block, clean, malicious
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 37a251acd3b7631cffffaf2eb76bf0f2b4954ee6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185835"
---
# <a name="manage-automation-folder-exclusions"></a><span data-ttu-id="aef31-104">Uitsluitingen van automatiseringsmappen beheren</span><span class="sxs-lookup"><span data-stu-id="aef31-104">Manage automation folder exclusions</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="aef31-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="aef31-105">**Applies to:**</span></span>
- [<span data-ttu-id="aef31-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="aef31-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aef31-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aef31-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="aef31-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="aef31-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aef31-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="aef31-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

<span data-ttu-id="aef31-110">Met uitsluitingen van automatiseringsmappen kunt u mappen opgeven die door het geautomatiseerde onderzoek worden overgeslagen.</span><span class="sxs-lookup"><span data-stu-id="aef31-110">Automation folder exclusions allow you to specify folders that the Automated investigation will skip.</span></span> 

<span data-ttu-id="aef31-111">U kunt de volgende kenmerken van de map die u wilt overslaan, bepalen:</span><span class="sxs-lookup"><span data-stu-id="aef31-111">You can control the following attributes about the folder that you'd like to be skipped:</span></span>
- <span data-ttu-id="aef31-112">Mappen</span><span class="sxs-lookup"><span data-stu-id="aef31-112">Folders</span></span> 
- <span data-ttu-id="aef31-113">Uitbreidingen van de bestanden</span><span class="sxs-lookup"><span data-stu-id="aef31-113">Extensions of the files</span></span>
- <span data-ttu-id="aef31-114">Bestandsnamen</span><span class="sxs-lookup"><span data-stu-id="aef31-114">File names</span></span>


<span data-ttu-id="aef31-115">**Mappen**</span><span class="sxs-lookup"><span data-stu-id="aef31-115">**Folders**</span></span><br>
<span data-ttu-id="aef31-116">U kunt opgeven dat een map en de submappen moeten worden overgeslagen.</span><span class="sxs-lookup"><span data-stu-id="aef31-116">You can specify a folder and its subfolders to be skipped.</span></span> 


>[!NOTE]
><span data-ttu-id="aef31-117">Op dit moment wordt het gebruik van jokerkaarten als een manier om bestanden onder een adreslijst uit te sluiten nog niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="aef31-117">At this time, use of wild cards as a way to exclude files under a directory is not yet supported.</span></span> 


<span data-ttu-id="aef31-118">**Extensies**</span><span class="sxs-lookup"><span data-stu-id="aef31-118">**Extensions**</span></span><br>
<span data-ttu-id="aef31-119">U kunt de extensies opgeven die u wilt uitsluiten in een specifieke adreslijst.</span><span class="sxs-lookup"><span data-stu-id="aef31-119">You can specify the extensions to exclude in a specific directory.</span></span> <span data-ttu-id="aef31-120">De extensies zijn een manier om te voorkomen dat een aanvaller een uitgesloten map gebruikt om een exploit te verbergen.</span><span class="sxs-lookup"><span data-stu-id="aef31-120">The extensions are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="aef31-121">De extensies definiëren expliciet welke bestanden moeten worden genegeerd.</span><span class="sxs-lookup"><span data-stu-id="aef31-121">The extensions explicitly define which files to ignore.</span></span> 

<span data-ttu-id="aef31-122">**Bestandsnamen**</span><span class="sxs-lookup"><span data-stu-id="aef31-122">**File names**</span></span><br>
<span data-ttu-id="aef31-123">U kunt de bestandsnamen opgeven die u wilt uitsluiten in een specifieke adreslijst.</span><span class="sxs-lookup"><span data-stu-id="aef31-123">You can specify the file names that you want to be excluded in a specific directory.</span></span> <span data-ttu-id="aef31-124">De namen zijn een manier om te voorkomen dat een aanvaller een uitgesloten map gebruikt om een exploit te verbergen.</span><span class="sxs-lookup"><span data-stu-id="aef31-124">The names are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="aef31-125">De namen definiëren expliciet welke bestanden moeten worden genegeerd.</span><span class="sxs-lookup"><span data-stu-id="aef31-125">The names explicitly define which files to ignore.</span></span> 



## <a name="add-an-automation-folder-exclusion"></a><span data-ttu-id="aef31-126">Een uitsluiting van automatiseringsmappen toevoegen</span><span class="sxs-lookup"><span data-stu-id="aef31-126">Add an automation folder exclusion</span></span>
1. <span data-ttu-id="aef31-127">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Automatiseringsmapuitsluitingen**.</span><span class="sxs-lookup"><span data-stu-id="aef31-127">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  

2. <span data-ttu-id="aef31-128">Klik **op Nieuwe mapuitsluiting.**</span><span class="sxs-lookup"><span data-stu-id="aef31-128">Click **New folder exclusion**.</span></span>  

3. <span data-ttu-id="aef31-129">Voer de mapdetails in:</span><span class="sxs-lookup"><span data-stu-id="aef31-129">Enter the folder details:</span></span>

    - <span data-ttu-id="aef31-130">Map</span><span class="sxs-lookup"><span data-stu-id="aef31-130">Folder</span></span>
    - <span data-ttu-id="aef31-131">Extensies</span><span class="sxs-lookup"><span data-stu-id="aef31-131">Extensions</span></span>
    - <span data-ttu-id="aef31-132">Bestandsnamen</span><span class="sxs-lookup"><span data-stu-id="aef31-132">File names</span></span>
    - <span data-ttu-id="aef31-133">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="aef31-133">Description</span></span>
    

4. <span data-ttu-id="aef31-134">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="aef31-134">Click **Save**.</span></span>

>[!NOTE]
> <span data-ttu-id="aef31-135">Opdrachten voor livereactie om uitgesloten bestanden te verzamelen of te onderzoeken, mislukken met de fout: 'Bestand is uitgesloten'.</span><span class="sxs-lookup"><span data-stu-id="aef31-135">Live Response commands to collect or examine excluded files will fail with error: "File is excluded".</span></span> <span data-ttu-id="aef31-136">Bovendien worden de uitgesloten items genegeerd door automatisch onderzoek.</span><span class="sxs-lookup"><span data-stu-id="aef31-136">In addition, automated investigations will ignore the excluded items.</span></span>

## <a name="edit-an-automation-folder-exclusion"></a><span data-ttu-id="aef31-137">Een uitsluiting van automatiseringsmappen bewerken</span><span class="sxs-lookup"><span data-stu-id="aef31-137">Edit an automation folder exclusion</span></span> 
1. <span data-ttu-id="aef31-138">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Automatiseringsmapuitsluitingen**.</span><span class="sxs-lookup"><span data-stu-id="aef31-138">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span> 

2. <span data-ttu-id="aef31-139">Klik **op Bewerken** op de mapuitsluiting.</span><span class="sxs-lookup"><span data-stu-id="aef31-139">Click **Edit** on the folder exclusion.</span></span>  

3. <span data-ttu-id="aef31-140">Werk de details van de regel bij en klik op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="aef31-140">Update the details of the rule and click **Save**.</span></span>

## <a name="remove-an-automation-folder-exclusion"></a><span data-ttu-id="aef31-141">Een uitsluiting van automatiseringsmappen verwijderen</span><span class="sxs-lookup"><span data-stu-id="aef31-141">Remove an automation folder exclusion</span></span> 
1. <span data-ttu-id="aef31-142">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Automatiseringsmapuitsluitingen**.</span><span class="sxs-lookup"><span data-stu-id="aef31-142">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  
2. <span data-ttu-id="aef31-143">Klik **op Uitsluiting verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="aef31-143">Click **Remove exclusion**.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="aef31-144">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="aef31-144">Related topics</span></span>
- [<span data-ttu-id="aef31-145">Toegestane/geblokkeerde lijsten voor automatisering beheren</span><span class="sxs-lookup"><span data-stu-id="aef31-145">Manage automation allowed/blocked lists</span></span>](manage-indicators.md)
- [<span data-ttu-id="aef31-146">Uploads van automatiseringsbestand beheren</span><span class="sxs-lookup"><span data-stu-id="aef31-146">Manage automation file uploads</span></span>](manage-automation-file-uploads.md)
