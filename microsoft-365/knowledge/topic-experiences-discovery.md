---
title: Detectie van onderwerp beheren in Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het beheren van topic Discovery in Microsoft 365.
ms.openlocfilehash: dec8aeef9dda390fb19f5067638c2ebea6b6a2fe
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698541"
---
# <a name="manage-topic-discovery-in-microsoft-365"></a><span data-ttu-id="c6d7c-103">Detectie van onderwerp beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c6d7c-103">Manage topic discovery in Microsoft 365</span></span>

<span data-ttu-id="c6d7c-104">U kunt de instellingen voor de detectie van het onderwerp beheren in het [Microsoft 365-Beheercentrum](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c6d7c-104">You can manage topic discovery settings in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="c6d7c-105">U moet een globale beheerder of SharePoint-beheerder zijn om deze taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-105">You must be a global administrator or SharePoint administrator to perform these tasks.</span></span>

## <a name="to-access-topics-management-settings"></a><span data-ttu-id="c6d7c-106">De instellingen voor het beheer van onderwerpen raadplegen:</span><span class="sxs-lookup"><span data-stu-id="c6d7c-106">To access topics management settings:</span></span>

1. <span data-ttu-id="c6d7c-107">Klik in het Microsoft 365-Beheercentrum op **instellingen** en vervolgens op **organisatie-instellingen**.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-107">In the Microsoft 365 admin center, click **Settings**, then **Org settings**.</span></span>
2. <span data-ttu-id="c6d7c-108">Klik op het tabblad **Services** op **kennis netwerk**.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-108">On the **Services** tab, click **Knowledge network**.</span></span>

    ![Mensen verbinden met kennis](../media/admin-org-knowledge-options-completed.png) 

3. <span data-ttu-id="c6d7c-110">Selecteer het tabblad **detectie van onderwerp** . Zie de volgende secties voor informatie over elke instelling.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-110">Select the **Topic discovery** tab. See the following sections for information about each setting.</span></span>

    ![kennis netwerk-instellingen](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a><span data-ttu-id="c6d7c-112">Selecteer SharePoint-onderwerpen bronnen</span><span class="sxs-lookup"><span data-stu-id="c6d7c-112">Select SharePoint topic sources</span></span>

<span data-ttu-id="c6d7c-113">U kunt de SharePoint-sites in uw organisatie wijzigen die worden verkend voor onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-113">You can change the SharePoint sites in your organization that will be crawled for topics.</span></span>

<span data-ttu-id="c6d7c-114">Als u een bepaalde lijst met sites wilt opnemen of uitsluiten, kunt u de volgende CSV-sjabloon gebruiken:</span><span class="sxs-lookup"><span data-stu-id="c6d7c-114">If you want to include or exclude a specific list of sites, you can use the following .csv template:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="c6d7c-115">Als u sites toevoegt met behulp van de site kiezer, worden deze toegevoegd aan de bestaande lijst met sites die u wilt opnemen of uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-115">If you add sites using the site picker, they are added to the existing list of sites to include or exclude.</span></span> <span data-ttu-id="c6d7c-116">Als u een CSV-bestand uploadt, wordt een bestaande lijst overschreven.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-116">If you upload a .csv file, it overwrites any existing list.</span></span> <span data-ttu-id="c6d7c-117">Als u eerder specifieke sites hebt opgenomen of uitgesloten, downloadt u de lijst als een. CSV-bestand, brengt u wijzigingen aan en uploadt u de nieuwe lijst.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-117">If you have previously included or excluded specific sites, you and download the list as a .csv file, make changes, and upload the new list.</span></span>

<span data-ttu-id="c6d7c-118">Sites kiezen voor detectie van een onderwerp</span><span class="sxs-lookup"><span data-stu-id="c6d7c-118">To choose sites for topic discovery</span></span>

1. <span data-ttu-id="c6d7c-119">Selecteer op het tabblad **topic Discovery** onder **Select SharePoint topics** de optie **Edit**.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-119">On the **Topic discovery** tab, under **Select SharePoint topic sources**, select **Edit**.</span></span>
2. <span data-ttu-id="c6d7c-120">Selecteer op de pagina **SharePoint-onderwerpen selecteren** welke SharePoint-sites worden verkend als bronnen voor uw onderwerpen tijdens de detectie.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-120">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="c6d7c-121">Dit omvat:</span><span class="sxs-lookup"><span data-stu-id="c6d7c-121">This includes:</span></span>
    - <span data-ttu-id="c6d7c-122">**Alle sites**: alle SharePoint-sites in de Tenant.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-122">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="c6d7c-123">Hiermee worden de huidige en toekomstige sites vastgelegd.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-123">This captures current and future sites.</span></span>
    - <span data-ttu-id="c6d7c-124">**Alles, met uitzondering van geselecteerde sites**: Typ de namen van de sites die u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-124">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="c6d7c-125">U kunt ook een lijst uploaden met sites die u wilt afmelden bij ontdekking.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-125">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="c6d7c-126">Sites die u later maakt, worden opgenomen als bronnen voor het detecteren van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-126">Sites created in the future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="c6d7c-127">**Alleen geselecteerde sites**: Typ de namen van de sites die u wilt opnemen.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-127">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="c6d7c-128">U kunt ook een lijst met sites uploaden.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-128">You can also upload a list of sites.</span></span> <span data-ttu-id="c6d7c-129">Sites die u later maakt, worden niet opgenomen als bronnen voor de detectie van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="c6d7c-130">**Geen sites**: onderwerpen worden niet automatisch aangemaakt of bijgewerkt met SharePoint-inhoud.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-130">**No sites**: Topics won't be automatically generated or updated with SharePoint content.</span></span> <span data-ttu-id="c6d7c-131">Bestaande onderwerpen blijven behouden in het onderwerp centrum.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-131">Existing topics remain in the topic center.</span></span>

    ![Schermafbeelding van de gebruikersinterface van de SharePoint-onderwerp bronnen](../media/k-manage-select-topic-source.png)
   
3. <span data-ttu-id="c6d7c-133">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-133">Click **Save**.</span></span>

## <a name="exclude-topics-by-name"></a><span data-ttu-id="c6d7c-134">Onderwerpen uitsluiten op naam</span><span class="sxs-lookup"><span data-stu-id="c6d7c-134">Exclude topics by name</span></span>

<span data-ttu-id="c6d7c-135">U kunt onderwerpen uitsluiten van detectie door een lijst te uploaden met een. CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-135">You can exclude topics from discovery by uploading a list using a .csv file.</span></span> <span data-ttu-id="c6d7c-136">Als u eerder uitgesloten onderwerpen hebt, kunt u het CSV-bestand downloaden, wijzigingen aanbrengen en opnieuw uploaden.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-136">If you've previously excluded topics, you can download the .csv, make changes, and upload it again.</span></span>

1. <span data-ttu-id="c6d7c-137">Selecteer op het tabblad **onderwerp detecteren** onder **onderwerpen uitsluiten** de optie **bewerken**.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-137">On the **Topic discovery** tab, under **Exclude topics**, select **Edit**.</span></span>
2. <span data-ttu-id="c6d7c-138">Klik op **onderwerpen uitsluiten op naam**.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-138">Click **Exclude topics by name**.</span></span>
3. <span data-ttu-id="c6d7c-139">Als u een lijst wilt maken, downloadt u de. CSV-sjabloon en voegt u de onderwerpen toe die u wilt uitsluiten (Zie *werken met de. CSV-sjabloon* hieronder).</span><span class="sxs-lookup"><span data-stu-id="c6d7c-139">If you need to create a list, download the .csv template and add the topics that you want to exclude (see *Working with the .csv template* below).</span></span> <span data-ttu-id="c6d7c-140">Wanneer het bestand klaar is, klikt u op **Bladeren** en uploadt u het bestand.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-140">When the file is ready, click **Browse** and upload the file.</span></span> <span data-ttu-id="c6d7c-141">Als u een bestaande lijst hebt, kunt u het. CSV-bestand met de lijst downloaden.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-141">If there's an existing list, you can download the .csv containing the list.</span></span>
4. <span data-ttu-id="c6d7c-142">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-142">Click **Save**.</span></span>

    ![Schermafbeelding van de gebruikersinterface van de onderdelen uitsluiten](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a><span data-ttu-id="c6d7c-144">Werken met de. CSV-sjabloon</span><span class="sxs-lookup"><span data-stu-id="c6d7c-144">Working with the .csv template</span></span>

<span data-ttu-id="c6d7c-145">U kunt de onderstaande CSV-sjabloon kopiëren:</span><span class="sxs-lookup"><span data-stu-id="c6d7c-145">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

<span data-ttu-id="c6d7c-146">Voer de volgende informatie over de onderwerpen die u wilt uitsluiten in het CSV-sjabloon in:</span><span class="sxs-lookup"><span data-stu-id="c6d7c-146">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

- <span data-ttu-id="c6d7c-147">**Naam**: Typ de naam van het onderwerp dat u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-147">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="c6d7c-148">U kunt dit op twee manieren doen:</span><span class="sxs-lookup"><span data-stu-id="c6d7c-148">There are two ways to do this:</span></span>
    - <span data-ttu-id="c6d7c-149">Exacte overeenkomst: u kunt de exacte naam of het acroniem opnemen, bijvoorbeeld *Contoso* of *ATL*.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-149">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="c6d7c-150">Gedeeltelijke overeenkomst: u kunt alle onderwerpen met een specifiek woord uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-150">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="c6d7c-151">Met de *boog* worden bijvoorbeeld alle onderwerpen met het woord *boog* weggelaten, zoals *boog cirkel*, *plasma boog lassen* of *boog boog*. Houd er rekening mee dat onderwerpen waarvan de tekst deel uitmaakt van een woord, zoals de *architectuur*, niet worden uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-151">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="c6d7c-152">**Staat voor (optioneel)**: als u een acroniem wilt uitsluiten, typt u de woorden waarop het acroniem staat.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-152">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
- <span data-ttu-id="c6d7c-153">**MatchType-exact/gedeeltelijk**: Typ of de ingevoerde naam een *exact* of *gedeeltelijk* overeenkomend type is.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-153">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    ![Onderwerpen in CSV-sjabloon uitsluiten](../media/exclude-topics-csv.png) 

## <a name="see-also"></a><span data-ttu-id="c6d7c-155">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c6d7c-155">See also</span></span>

[<span data-ttu-id="c6d7c-156">De zichtbaarheid van een onderwerp beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c6d7c-156">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="c6d7c-157">Machtigingen voor onderwerp beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c6d7c-157">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="c6d7c-158">De naam van het onderwerp centreren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c6d7c-158">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
