---
title: Onderwerpdetectie beheren in Microsoft Viva-onderwerpen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Meer informatie over het beheren van onderwerpdetectie in Microsoft Viva-onderwerpen.
ms.openlocfilehash: 53e304dc69ccf2ca6fe01d29f0997c539406b0fe
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768972"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a><span data-ttu-id="35c17-103">Onderwerpdetectie beheren in Microsoft Viva-onderwerpen</span><span class="sxs-lookup"><span data-stu-id="35c17-103">Manage topic discovery in Microsoft Viva Topics</span></span>

<span data-ttu-id="35c17-104">U kunt de instellingen voor onderwerpdetectie beheren in [het Microsoft 365 beheercentrum.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="35c17-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="35c17-105">U moet een globale beheerder of SharePoint zijn om deze taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="35c17-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="35c17-106">Toegang tot de instellingen voor onderwerpenbeheer:</span><span class="sxs-lookup"><span data-stu-id="35c17-106">To access topics management settings:</span></span>

1. <span data-ttu-id="35c17-107">Klik in Microsoft 365 beheercentrum **op** Instellingen en vervolgens **op Organisatie-instellingen.**</span><span class="sxs-lookup"><span data-stu-id="35c17-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="35c17-108">Klik op **het tabblad** Services op **Onderwerpervaringen.**</span><span class="sxs-lookup"><span data-stu-id="35c17-108">On the **Services** tab, click **Topic experiences**.</span></span>

    ![Verbinding maken mensen kennis te laten maken](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="35c17-110">Selecteer het **tabblad Onderwerpdetectie.** Zie de volgende secties voor informatie over elke instelling.</span><span class="sxs-lookup"><span data-stu-id="35c17-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="35c17-112">Selecteer SharePoint onderwerpbronnen</span><span class="sxs-lookup"><span data-stu-id="35c17-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="35c17-113">U kunt de SharePoint sites in uw organisatie wijzigen die worden verkend voor onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="35c17-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="35c17-114">Als u een specifieke lijst met sites wilt opnemen of uitsluiten, kunt u de volgende .csv gebruiken:</span><span class="sxs-lookup"><span data-stu-id="35c17-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="35c17-115">Als u sites toevoegt met de site picker, worden deze toegevoegd aan de bestaande lijst met sites die u wilt opnemen of uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="35c17-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="35c17-116">Als u een .csv uploadt, wordt elke bestaande lijst overschreven.</span><span class="sxs-lookup"><span data-stu-id="35c17-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="35c17-117">Als u eerder specifieke sites hebt opgenomen of uitgesloten, kunt u de lijst als een .csv downloaden, wijzigingen aanbrengen en de nieuwe lijst uploaden.</span><span class="sxs-lookup"><span data-stu-id="35c17-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="35c17-118">Sites kiezen voor onderwerpdetectie</span><span class="sxs-lookup"><span data-stu-id="35c17-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="35c17-119">Selecteer op **het tabblad** Onderwerpdetectie onder Selecteer **SharePoint onderwerpbronnen** de optie **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="35c17-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="35c17-120">Selecteer op **de pagina SharePoint onderwerpbronnen** selecteren welke sites SharePoint worden verkend als bronnen voor uw onderwerpen tijdens de detectie.</span><span class="sxs-lookup"><span data-stu-id="35c17-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="35c17-121">Dit zijn:</span><span class="sxs-lookup"><span data-stu-id="35c17-121">This includes:</span></span>
    - <span data-ttu-id="35c17-122">**Alle sites:** Alle SharePoint sites in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="35c17-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="35c17-123">Hiermee worden huidige en toekomstige sites vastleggen.</span><span class="sxs-lookup"><span data-stu-id="35c17-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="35c17-124">**Alle, behalve geselecteerde sites:** Typ de namen van de sites die u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="35c17-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="35c17-125">U kunt ook een lijst uploaden met sites die u niet wilt ontdekken.</span><span class="sxs-lookup"><span data-stu-id="35c17-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="35c17-126">Sites die in de toekomst worden gemaakt, worden opgenomen als bronnen voor onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="35c17-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="35c17-127">**Alleen geselecteerde sites:** Typ de namen van de sites die u wilt opnemen.</span><span class="sxs-lookup"><span data-stu-id="35c17-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="35c17-128">U kunt ook een lijst met sites uploaden.</span><span class="sxs-lookup"><span data-stu-id="35c17-128">You can also upload a list of sites.</span></span> <span data-ttu-id="35c17-129">Sites die in de toekomst worden gemaakt, worden niet opgenomen als bronnen voor onderwerpdetectie.</span><span class="sxs-lookup"><span data-stu-id="35c17-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="35c17-130">**Geen sites:** Onderwerpen worden niet automatisch gegenereerd of bijgewerkt met SharePoint inhoud.</span><span class="sxs-lookup"><span data-stu-id="35c17-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="35c17-131">Bestaande onderwerpen blijven in het onderwerpcentrum staan.</span><span class="sxs-lookup"><span data-stu-id="35c17-131">Existing topics remain in the topic center.</span></span>

    ![Schermafbeelding van SharePoint gebruikersinterface van onderwerpbronnen](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="35c17-133">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="35c17-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="35c17-134">Onderwerpen uitsluiten op naam</span><span class="sxs-lookup"><span data-stu-id="35c17-134">Exclude topics by name</span></span>

<span data-ttu-id="35c17-135">U kunt onderwerpen uitsluiten van detectie door een lijst te uploaden met een .csv bestand.</span><span class="sxs-lookup"><span data-stu-id="35c17-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="35c17-136">Als u eerder onderwerpen hebt uitgesloten, kunt u de .csv downloaden, wijzigingen aanbrengen en opnieuw uploaden.</span><span class="sxs-lookup"><span data-stu-id="35c17-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="35c17-137">Selecteer op **het tabblad** Onderwerpdetectie onder **Onderwerpen uitsluiten** de optie **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="35c17-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="35c17-138">Klik **op Onderwerpen uitsluiten op naam.**</span><span class="sxs-lookup"><span data-stu-id="35c17-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="35c17-139">Als u een lijst wilt maken, downloadt u de .csv sjabloon en voegt u de onderwerpen toe die u wilt uitsluiten (zie Werken met de *.csv sjabloon* hieronder).</span><span class="sxs-lookup"><span data-stu-id="35c17-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="35c17-140">Wanneer het bestand gereed is, klikt u **op Bladeren** en uploadt u het bestand.</span><span class="sxs-lookup"><span data-stu-id="35c17-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="35c17-141">Als er een bestaande lijst is, kunt u de .csv met de lijst downloaden.</span><span class="sxs-lookup"><span data-stu-id="35c17-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="35c17-142">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="35c17-142">Click **Save**.</span></span>

    ![Schermafbeelding van de gebruikersinterface van onderwerpen uitsluiten](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="35c17-144">Werken met de .csv sjabloon</span><span class="sxs-lookup"><span data-stu-id="35c17-144">Working with the .csv template</span></span>

<span data-ttu-id="35c17-145">U kunt de csv-sjabloon hieronder kopiëren:</span><span class="sxs-lookup"><span data-stu-id="35c17-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="35c17-146">Voer in de CSV-sjabloon de volgende informatie in over de onderwerpen die u wilt uitsluiten:</span><span class="sxs-lookup"><span data-stu-id="35c17-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="35c17-147">**Naam:** Typ de naam van het onderwerp dat u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="35c17-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="35c17-148">U kunt dit op twee manieren doen:</span><span class="sxs-lookup"><span data-stu-id="35c17-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="35c17-149">Exacte overeenkomst: U kunt de exacte naam of acroniem uitsluiten (bijvoorbeeld *Contoso* of *ATL).*</span><span class="sxs-lookup"><span data-stu-id="35c17-149">Exact match: You can exclude the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="35c17-150">Gedeeltelijke overeenkomst: U kunt alle onderwerpen met een specifiek woord uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="35c17-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="35c17-151">Met een *boog worden bijvoorbeeld* alle onderwerpen uitgesloten met de woordboog in de boog, zoals boogcirkel, lassen van de boog van Het *plasma* of *Trainingsboog.*   Houd er rekening mee dat onderwerpen waarin de tekst is opgenomen als onderdeel van een woord, zoals Architectuur, niet worden *uitgesloten.*</span><span class="sxs-lookup"><span data-stu-id="35c17-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="35c17-152">**Staat voor (optioneel)**: Als u een acroniem wilt uitsluiten, typt u de woorden waar het acroniem voor staat.</span><span class="sxs-lookup"><span data-stu-id="35c17-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="35c17-153">**MatchType-Exact/Gedeeltelijk:** Typ of de opgegeven naam *een exact* of *gedeeltelijk overeenkomend* type was.</span><span class="sxs-lookup"><span data-stu-id="35c17-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![Onderwerpen uitsluiten in CSV-sjabloon](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="35c17-155">Zie ook</span><span class="sxs-lookup"><span data-stu-id="35c17-155">See also</span></span>

[<span data-ttu-id="35c17-156">Zichtbaarheid van onderwerp beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="35c17-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="35c17-157">Onderwerpmachtigingen beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="35c17-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="35c17-158">De naam van het onderwerpcentrum wijzigen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="35c17-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
