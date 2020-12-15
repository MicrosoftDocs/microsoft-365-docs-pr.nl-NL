---
title: Onderwerp ervaring plannen in Microsoft 365
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
description: Meer informatie over het plannen van onderwerpen in Microsoft 365
ms.openlocfilehash: 153937cf6bc4a12f0a27866204b2286c343ddf55
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668154"
---
# <a name="plan-topic-experiences-in-microsoft-365"></a><span data-ttu-id="cb87d-103">Onderwerp ervaring plannen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb87d-103">Plan topic experiences in Microsoft 365</span></span>

<span data-ttu-id="cb87d-104">U bepaalt zelf hoe de onderwerpen in uw organisatie worden ervaren.</span><span class="sxs-lookup"><span data-stu-id="cb87d-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="cb87d-105">Met uw plannings beslissingen voor de ervaringen van een onderwerp zorgt u ervoor dat de producten van hoge kwaliteit voor uw gebruikers worden weergegeven en dat ze de juiste machtigingen hebben om kennis te maken en Contribute te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cb87d-105">Your planning decisions for topic experiences ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="cb87d-106">In dit artikel worden deze plannings beslissingen onderzocht:</span><span class="sxs-lookup"><span data-stu-id="cb87d-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="cb87d-107">De SharePoint-sites die u wilt verkennen voor onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="cb87d-107">Which SharePoint sites you want to crawl for topics.</span></span>
- <span data-ttu-id="cb87d-108">Welke onderwerpen, indien van toepassing, wilt u uitsluiten van onderwerp-ervaringen</span><span class="sxs-lookup"><span data-stu-id="cb87d-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="cb87d-109">De gebruikers van wie u de onderwerpen zichtbaar wilt maken.</span><span class="sxs-lookup"><span data-stu-id="cb87d-109">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="cb87d-110">Welke gebruikers u machtigingen wilt geven om onderwerpen te beheren in het onderwerp centrum.</span><span class="sxs-lookup"><span data-stu-id="cb87d-110">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="cb87d-111">Welke gebruikers u machtigingen wilt geven om onderwerpen te maken of te bewerken in het onderwerp centrum.</span><span class="sxs-lookup"><span data-stu-id="cb87d-111">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="cb87d-112">De naam van het onderwerp dat u wilt geven.</span><span class="sxs-lookup"><span data-stu-id="cb87d-112">What name you want to give your topic center.</span></span>

<span data-ttu-id="cb87d-113">Beveiliging en privacy van uw gegevens worden geëerbiedigd en de onderwerp-ervaringen geven gebruikers geen toegang meer tot de bestanden waartoe ze geen rechten hebben.</span><span class="sxs-lookup"><span data-stu-id="cb87d-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="cb87d-114">U wordt aangeraden ook een onderwerp te lezen dat op het gebied van uw planningsproces [beveiliging en privacy te](topic-experiences-security-privacy.md) maken heeft.</span><span class="sxs-lookup"><span data-stu-id="cb87d-114">We recommend you also read [Topic experiences security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="cb87d-115">Vereisten</span><span class="sxs-lookup"><span data-stu-id="cb87d-115">Requirements</span></span>

<span data-ttu-id="cb87d-116">U moet een globale beheerder of SharePoint-beheerder zijn om toegang te krijgen tot het Microsoft 365-Beheercentrum en de functies voor het onderwerp in te stellen.</span><span class="sxs-lookup"><span data-stu-id="cb87d-116">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

<span data-ttu-id="cb87d-117">Voor alle gebruikers die de functies voor het gebruik van een onderwerp gaan gebruiken, is een licentie voor de **onderwerp-ervaring** vereist.</span><span class="sxs-lookup"><span data-stu-id="cb87d-117">All users who are going to use topic experiences require a **Topic Experiences** license.</span></span> <span data-ttu-id="cb87d-118">Het toewijzen van licenties valt onder de functies voor het instellen van het [onderwerp](set-up-topic-experiences.md).</span><span class="sxs-lookup"><span data-stu-id="cb87d-118">Assigning licenses is covered in [Set up topic experiences](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="cb87d-119">Onderwerp detecteren</span><span class="sxs-lookup"><span data-stu-id="cb87d-119">Topic discovery</span></span>

<span data-ttu-id="cb87d-120">De instellingen voor de detectie van het onderwerp opgeven welke SharePoint-sites worden gebruikt als bronnen voor onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="cb87d-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="cb87d-121">U kunt ervoor kiezen om alle SharePoint-sites, een specifieke lijst met sites of geen sites op te nemen.</span><span class="sxs-lookup"><span data-stu-id="cb87d-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="cb87d-122">We raden u aan om alle sites te kiezen, zodat de functies van het onderwerp een groot aantal goede onderwerpen kunnen ontdekken voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="cb87d-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="cb87d-123">Wanneer u onderwerpeert, kunt u kiezen uit de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="cb87d-123">When you set up topic experiences, you can choose from the following options:</span></span>

- <span data-ttu-id="cb87d-124">**Alle sites**: alle SharePoint-sites in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="cb87d-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="cb87d-125">Dit geldt ook voor huidige en toekomstige sites.</span><span class="sxs-lookup"><span data-stu-id="cb87d-125">This includes current and future sites.</span></span>
- <span data-ttu-id="cb87d-126">**Alles, met uitzondering van geselecteerde sites**: alle sites, behalve voor de accounts die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="cb87d-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="cb87d-127">Sites die in de toekomst zijn gemaakt, worden opgenomen als bronnen voor de detectie van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="cb87d-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="cb87d-128">**Alleen geselecteerde sites**: alleen de sites die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="cb87d-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="cb87d-129">Sites die u later maakt, worden niet opgenomen als bronnen voor de detectie van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="cb87d-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="cb87d-130">**Geen sites**: geen SharePoint-sites opnemen.</span><span class="sxs-lookup"><span data-stu-id="cb87d-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="cb87d-131">Als u alle selecteert **, met uitzondering van geselecteerde sites** of **alleen geselecteerde sites**, kunt u een CSV-bestand uploaden met een lijst met sites.</span><span class="sxs-lookup"><span data-stu-id="cb87d-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="cb87d-132">Deze opties zijn handig als u een pilot uitvoert en u een beperkt aantal sites wilt toevoegen om te starten.</span><span class="sxs-lookup"><span data-stu-id="cb87d-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="cb87d-133">U kunt de. CSV-sjabloon hieronder kopiëren:</span><span class="sxs-lookup"><span data-stu-id="cb87d-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="cb87d-134">We raden u niet aan **geen sites** te kiezen omdat het voorkomt dat onderwerpen automatisch worden gemaakt of bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="cb87d-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="cb87d-135">U kunt echter deze optie selecteren als u topic Experience wilt instellen en later sites wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="cb87d-135">However, you can choose this option if you want to set up topic experiences and then add sites later.</span></span>

<span data-ttu-id="cb87d-136">We raden u aan om een proces te maken voor gebruikers of kennis beheerders die de aanvraaging van de onderwerps detectie indien nodig in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="cb87d-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="cb87d-137">Gebruikersmachtigingen</span><span class="sxs-lookup"><span data-stu-id="cb87d-137">User permissions</span></span>

<span data-ttu-id="cb87d-138">De gebruikersmachtigingen die u opgeeft, bepalen welke personen in uw organisatie werken met onderwerpen en wat ze kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="cb87d-138">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="cb87d-139">*Onderwerpen beheren*</span><span class="sxs-lookup"><span data-stu-id="cb87d-139">*Manage topics*</span></span>

<span data-ttu-id="cb87d-140">Kennis beheerders houden de kwaliteit van de informatie over, hoe de gestructureerd en andere aanbevolen procedures in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="cb87d-140">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="cb87d-141">Ze kunnen onderwerpen bevestigen en negeren.</span><span class="sxs-lookup"><span data-stu-id="cb87d-141">They can confirm and reject topics.</span></span>

<span data-ttu-id="cb87d-142">U kunt ook afzonderlijke onderwerpen van een onderwerp opgeven, maar u kunt wel een beveiligingsgroep maken (of een bestaande maken) met de personen die u willen weten.</span><span class="sxs-lookup"><span data-stu-id="cb87d-142">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="cb87d-143">U kunt deze beveiligingsgroep tijdens het installatieproces opgeven.</span><span class="sxs-lookup"><span data-stu-id="cb87d-143">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="cb87d-144">*Onderwerpen maken en bewerken*</span><span class="sxs-lookup"><span data-stu-id="cb87d-144">*Create and edit topics*</span></span>

<span data-ttu-id="cb87d-145">Medewerkers in het leiders zijn de experts van de onderhevige experts van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="cb87d-145">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="cb87d-146">Ze kunnen onderwerpen maken en bewerken.</span><span class="sxs-lookup"><span data-stu-id="cb87d-146">They can create and edit topics.</span></span> 

<span data-ttu-id="cb87d-147">We raden u aan om iedereen in uw organisatie in staat te stellen onderwerpen te maken en bewerken omdat de functies voor het gebruik van onderwerpen het beste werken wanneer alle gebruikers informatie kunnen delen.</span><span class="sxs-lookup"><span data-stu-id="cb87d-147">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="cb87d-148">Als u het maken en bewerken van onderwerpen wilt beperken tot specifieke personen of groepen, maakt u hiervoor een beveiligingsgroep en geeft u deze op tijdens het installatieproces.</span><span class="sxs-lookup"><span data-stu-id="cb87d-148">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="cb87d-149">U kunt ervoor kiezen dat iedereen geen bijdrage biedt aan onderwerpen, maar dit wordt niet aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="cb87d-149">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="cb87d-150">Kennis beheerders kunnen nog steeds onderwerpen bewerken en maken.</span><span class="sxs-lookup"><span data-stu-id="cb87d-150">Knowledge managers will still be able to edit and create topics.</span></span>

<span data-ttu-id="cb87d-151">*Onderwerp viewers*</span><span class="sxs-lookup"><span data-stu-id="cb87d-151">*Topic viewers*</span></span>

<span data-ttu-id="cb87d-152">De bezoekers van een onderwerp kunnen op de pagina met zoekresultaten en wanneer onderwerpen zijn gemarkeerd in de inhoud van de SharePoint-pagina's.</span><span class="sxs-lookup"><span data-stu-id="cb87d-152">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="cb87d-153">Gebruikers kunnen alleen ontdekte onderwerpen zien wanneer ze toegang hebben tot de bestanden en pagina's waarvan het onderwerp is gevonden.</span><span class="sxs-lookup"><span data-stu-id="cb87d-153">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="cb87d-154">Wanneer u topic viewers instelt, kunt u kiezen uit:</span><span class="sxs-lookup"><span data-stu-id="cb87d-154">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="cb87d-155">**Iedereen binnen mijn organisatie**</span><span class="sxs-lookup"><span data-stu-id="cb87d-155">**Everyone in my organization**</span></span>
- <span data-ttu-id="cb87d-156">**Alleen geselecteerde personen of beveiligingsgroepen**</span><span class="sxs-lookup"><span data-stu-id="cb87d-156">**Only selected people or security groups**</span></span>
- <span data-ttu-id="cb87d-157">**Niemand**</span><span class="sxs-lookup"><span data-stu-id="cb87d-157">**No one**</span></span>

<span data-ttu-id="cb87d-158">We raden **iedereen binnen mijn organisatie** aan, maar als u een pilot uitvoert, kunt u alleen geselecteerde personen of beveiligingsgroepen kiezen.</span><span class="sxs-lookup"><span data-stu-id="cb87d-158">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="cb87d-159">U kunt **er** ook voor kiezen om het onderwerp in te stellen, maar u kunt geen onderwerpen weergeven.</span><span class="sxs-lookup"><span data-stu-id="cb87d-159">You can also choose **No one** if you want to set up topic experiences, but not allow people to see topics yet.</span></span> <span data-ttu-id="cb87d-160">(Kennis managers hebben nog steeds toegang tot de onderwerpen) en Help met de beslissing om de functies van het onderwerp algemeen beschikbaar te maken.)</span><span class="sxs-lookup"><span data-stu-id="cb87d-160">(Knowledge managers will still have access to allow them view the topics and help with the decision to make topic experiences broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="cb87d-161">Kennis regels</span><span class="sxs-lookup"><span data-stu-id="cb87d-161">Knowledge rules</span></span>

<span data-ttu-id="cb87d-162">Als beheerder kunt u bepaalde onderwerpen uitsluiten van topic experiences.</span><span class="sxs-lookup"><span data-stu-id="cb87d-162">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="cb87d-163">Dit is handig als u wilt voorkomen dat gevoelige gegevens in onderwerpen worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="cb87d-163">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="cb87d-164">Hoewel kennis beheerders onderwerpen in het onderwerp centrum kunnen uitsluiten, zijn de onderwerpen die door de beheerder worden uitgesloten niet zichtbaar voor de kennis managers.</span><span class="sxs-lookup"><span data-stu-id="cb87d-164">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="cb87d-165">(Kennis managers kunnen ook onderwerpen in het onderwerp centrum verwijderen na ontdekking.)</span><span class="sxs-lookup"><span data-stu-id="cb87d-165">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="cb87d-166">Als u onderwerpen wilt uitsluiten van het niveau van de beheerder, moet u deze toevoegen aan een CSV-bestand en het bestand uploaden.</span><span class="sxs-lookup"><span data-stu-id="cb87d-166">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="cb87d-167">U kunt dit doen tijdens de installatie of later.</span><span class="sxs-lookup"><span data-stu-id="cb87d-167">You can do this during setup or later.</span></span>

<span data-ttu-id="cb87d-168">Het. CSV-bestand moet de volgende parameters bevatten:</span><span class="sxs-lookup"><span data-stu-id="cb87d-168">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="cb87d-169">**Naam**: Typ de naam van het onderwerp dat u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="cb87d-169">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="cb87d-170">U kunt dit op twee manieren doen:</span><span class="sxs-lookup"><span data-stu-id="cb87d-170">There are two ways to do this:</span></span>
- <span data-ttu-id="cb87d-171">**MatchType-exact/gedeeltelijk**: Typ of de ingevoerde naam een *exact* of *gedeeltelijk* overeenkomend type is.</span><span class="sxs-lookup"><span data-stu-id="cb87d-171">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="cb87d-172">Exacte overeenkomst: u kunt de exacte naam of het acroniem opnemen, bijvoorbeeld *Contoso* of *ATL*.</span><span class="sxs-lookup"><span data-stu-id="cb87d-172">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="cb87d-173">Gedeeltelijke overeenkomst: u kunt alle onderwerpen met een specifiek woord uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="cb87d-173">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="cb87d-174">Met de *boog* worden bijvoorbeeld alle onderwerpen met het woord *boog* weggelaten, zoals *boog cirkel*, *plasma boog lassen* of *boog boog*. Houd er rekening mee dat onderwerpen waarvan de tekst deel uitmaakt van een woord, zoals de *architectuur*, niet worden uitgesloten.</span><span class="sxs-lookup"><span data-stu-id="cb87d-174">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="cb87d-175">**Staat voor (optioneel)**: (ook wel bekend als *expansie*) als u een acroniem wilt uitsluiten, typt u de woorden waarop het acroniem staat.</span><span class="sxs-lookup"><span data-stu-id="cb87d-175">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Onderwerpen in CSV-sjabloon uitsluiten](../media/exclude-topics-csv.png) 

<span data-ttu-id="cb87d-177">U kunt de onderstaande CSV-sjabloon kopiëren:</span><span class="sxs-lookup"><span data-stu-id="cb87d-177">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="cb87d-178">Beheer</span><span class="sxs-lookup"><span data-stu-id="cb87d-178">Administration</span></span>

<span data-ttu-id="cb87d-179">Wanneer u onderwerpings functies instelt, wordt er automatisch een onderwerpvenster gemaakt als onderdeel van het installatieproces.</span><span class="sxs-lookup"><span data-stu-id="cb87d-179">When you set up topic experiences, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="cb87d-180">Denk na over de naam van het onderwerp en wat u wilt dat de URL wordt.</span><span class="sxs-lookup"><span data-stu-id="cb87d-180">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="cb87d-181">U kunt zowel de naam als de URL instellen als onderdeel van het installatieproces, en u kunt de naam (maar niet de URL) wijzigen in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="cb87d-181">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="cb87d-182">U kunt maar één onderwerp centreren.</span><span class="sxs-lookup"><span data-stu-id="cb87d-182">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="cb87d-183">Installatie Controlelijst</span><span class="sxs-lookup"><span data-stu-id="cb87d-183">Setup checklist</span></span>

<span data-ttu-id="cb87d-184">Wanneer u onderwerpeert, hebt u de volgende items nodig wanneer u door de installatiewizard gaat:</span><span class="sxs-lookup"><span data-stu-id="cb87d-184">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="cb87d-185">Lijst met sites die u wilt opnemen in of uitsluiten van alle websites voor de detectie van het onderwerp</span><span class="sxs-lookup"><span data-stu-id="cb87d-185">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="cb87d-186">Beveiligingsgroep voor bezoekers van het onderwerp als u niet alle gebruikers de mogelijkheid wilt bieden om onderwerpen weer te geven</span><span class="sxs-lookup"><span data-stu-id="cb87d-186">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="cb87d-187">Beveiligingsgroep voor inzenders van een onderwerp, indien niet alle gebruikers de mogelijkheid bieden om onderwerpen te maken en bewerken</span><span class="sxs-lookup"><span data-stu-id="cb87d-187">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="cb87d-188">Beveiligingsgroep voorkennis managers van het onderwerp als u niet alle gebruikers de mogelijkheid wilt bieden om onderwerpen te beheren</span><span class="sxs-lookup"><span data-stu-id="cb87d-188">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="cb87d-189">Lijst met gevoelige onderwerpen die de detectie van het onderwerp uitsluiten</span><span class="sxs-lookup"><span data-stu-id="cb87d-189">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="cb87d-190">Een naam voor de onderwerpen centrum site</span><span class="sxs-lookup"><span data-stu-id="cb87d-190">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="cb87d-191">Zie ook</span><span class="sxs-lookup"><span data-stu-id="cb87d-191">See also</span></span>

[<span data-ttu-id="cb87d-192">Ervaring met het onderwerp instellen</span><span class="sxs-lookup"><span data-stu-id="cb87d-192">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="cb87d-193">Detectie van onderwerp beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb87d-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="cb87d-194">De zichtbaarheid van een onderwerp beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb87d-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="cb87d-195">Machtigingen voor onderwerp beheren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb87d-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="cb87d-196">De naam van het onderwerp centreren in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb87d-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
