---
title: Onderwerp Ervaar beveiligingsbeperkingen (preview)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Overzicht van de manier waarop beveiliging wordt gebruikt om onderwerpen weer te geven.
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698864"
---
# <a name="topic-experiences-security-trimming-preview"></a><span data-ttu-id="d68a9-103">Onderwerp Ervaar beveiligingsbeperkingen (preview)</span><span class="sxs-lookup"><span data-stu-id="d68a9-103">Topic Experiences security trimming (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="d68a9-104">De inhoud in dit artikel is bedoeld voor project cortex private preview.</span><span class="sxs-lookup"><span data-stu-id="d68a9-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="d68a9-105">[Meer informatie over Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="d68a9-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="d68a9-106">Met behulp van een onderwerp kunnen gebruikers niet informatie weergeven in onderwerpen die hun bestaande Office 365-machtigingen niet kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="d68a9-106">Topic experiences users will not be able to view information in topics that their existing Office 365 permissions prevents them from seeing.</span></span> <span data-ttu-id="d68a9-107">Alles wat een gebruiker op een onderwerp ziet (zoals SharePoint-sites,-documenten en-bestanden), is informatie die ze al mogen zien.</span><span class="sxs-lookup"><span data-stu-id="d68a9-107">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="d68a9-108">De onderwerp-ervaringen maken geen wijzigingen in bestaande machtigingen.</span><span class="sxs-lookup"><span data-stu-id="d68a9-108">Topic experiences does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="d68a9-109">Waarom twee gebruikers verschillende weergaven van hetzelfde onderwerp kunnen hebben</span><span class="sxs-lookup"><span data-stu-id="d68a9-109">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="d68a9-110">Wanneer u een onderwerp maakt met AI of handmatige curator, kan dit een beschrijving van het onderwerp, alternatieve namen, personen die zijn gekoppeld aan het onderwerp, bevatten, en sites, pagina's en bestanden die betrekking hebben op het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="d68a9-110">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="d68a9-111">Wanneer deze informatie op een onderwerpenpagina wordt weergegeven, is het mogelijk dat twee gebruikers die hetzelfde onderwerp bekijken, niet dezelfde informatie zien.</span><span class="sxs-lookup"><span data-stu-id="d68a9-111">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="d68a9-112">Wanneer user 1 bijvoorbeeld de Neptune-topic bevat, is dit wat ze kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="d68a9-112">For example, when User 1 views the Neptune topic page, this is what they might see.</span></span>

![Neptune onderwerp voor gebruiker 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="d68a9-114">Wanneer op de site van User 2 echter dezelfde Neptune-topic wordt weergegeven, verschilt de weergave van gebruiker 1.</span><span class="sxs-lookup"><span data-stu-id="d68a9-114">However, when User 2 looks at the same Neptune topic page, her view differs from User 1.</span></span>  <span data-ttu-id="d68a9-115">Gebruiker 2 kan het bestand *DG-2000-product overzicht* weergeven in de sectie **vastgemaakte bestanden en pagina's** van de onderwerpenpagina, die niet voor gebruiker 1 wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d68a9-115">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Neptune onderwerp voor gebruiker 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="d68a9-117">Het verschil in wat gebruikers in hetzelfde onderwerp kunnen zien, is omdat gebruikers mogelijk niet beschikken over de machtigingen van Office 365 voor het weergeven van een gerelateerde site of een bestand.</span><span class="sxs-lookup"><span data-stu-id="d68a9-117">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="d68a9-118">Met onderwerpen wordt rekening gehouden met de machtigingen die zijn ingesteld voor items in een onderwerp en kan de toegang niet worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="d68a9-118">Topic experiences respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="d68a9-119">In ons voorbeeld is gebruiker 1 het bestand *DG-2000 product Overview* niet weergegeven in de onderwerppagina voor Neptune omdat gebruikers 1 geen Office 365-machtigingen hebben voor het weergeven van het bestand.</span><span class="sxs-lookup"><span data-stu-id="d68a9-119">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="d68a9-120">Als een gebruiker niet voldoende informatie in een onderwerp kan zien, zodat het onderwerp nuttig kan zijn, is het onderwerp niet beschikbaar voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d68a9-120">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="d68a9-121">In dit voorbeeld wordt de gebruiker het gemarkeerde onderwerp niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d68a9-121">In this instance, the user will not see the highlighted topic.</span></span> <span data-ttu-id="d68a9-122">Een andere gebruiker die in het onderwerp is gemachtigd om meer informatie in het onderwerp te gebruiken, kan het onderwerp dan ook zien.</span><span class="sxs-lookup"><span data-stu-id="d68a9-122">However, a different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="d68a9-123">Machtigingen voor het onderwerp van kennis beheerders en medewerkers van een onderwerp</span><span class="sxs-lookup"><span data-stu-id="d68a9-123">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="d68a9-124">Gebruikers die zijn toegewezen aan de onderwerpen over het beheren van onderwerpen-Knowledge managers-kunnen alleen informatie weergeven die ze hebben, en kunnen de inhoud van de onderwerpen bekijken.</span><span class="sxs-lookup"><span data-stu-id="d68a9-124">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="d68a9-125">Ook gebruikers die machtigingen voor het onderwerp hebben gemaakt en bewerken-met het onderwerp medewerkers van een onderwerp kunnen alleen informatie weergeven die ze hebben gemachtigd om binnen de onderwerpen te zien.</span><span class="sxs-lookup"><span data-stu-id="d68a9-125">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="d68a9-126">AI versus handmatig gecuratore informatie over het onderwerp</span><span class="sxs-lookup"><span data-stu-id="d68a9-126">AI versus manually curated topic information</span></span>

<span data-ttu-id="d68a9-127">De onderwerpen kunnen gegevens bevatten die worden gegenereerd door de AI-en informatie die zijn toegevoegd of bewerkt door medewerkers of kennis beheerders van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="d68a9-127">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="d68a9-128">Informatie in een onderwerp dat door AI is toegevoegd, is alleen zichtbaar voor personen die toegang hebben tot de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="d68a9-128">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="d68a9-129">Gegevens die handmatig zijn toegevoegd of bewerkt door een onderwerpassistent of Knowledge Manager, zijn zichtbaar voor iedereen die het onderwerp kan zien.</span><span class="sxs-lookup"><span data-stu-id="d68a9-129">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="d68a9-130">In de volgende tabel wordt beschreven welke gebruikers van een onderwerp, medewerkers en kennis managers van de gebruikers, kunnen zien in een bepaald onderwerp op basis van hun machtigingen.</span><span class="sxs-lookup"><span data-stu-id="d68a9-130">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="d68a9-131">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="d68a9-131">Topic item</span></span>|<span data-ttu-id="d68a9-132">Wat gebruikers kunnen zien</span><span class="sxs-lookup"><span data-stu-id="d68a9-132">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="d68a9-133">Naam onderwerp</span><span class="sxs-lookup"><span data-stu-id="d68a9-133">Topic name</span></span>|<span data-ttu-id="d68a9-134">Gebruikers kunnen de naam van het onderwerp van alle onderwerpen in het onderwerp centrum zien.</span><span class="sxs-lookup"><span data-stu-id="d68a9-134">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="d68a9-135">Sommige onderwerpen zijn mogelijk niet zichtbaar als ze een lage relevantie voor de gebruiker hebben.</span><span class="sxs-lookup"><span data-stu-id="d68a9-135">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="d68a9-136">Beschrijving onderwerp</span><span class="sxs-lookup"><span data-stu-id="d68a9-136">Topic description</span></span>|<span data-ttu-id="d68a9-137">Met AI gegenereerde beschrijvingen zijn alleen zichtbaar voor gebruikers die zijn gemachtigd voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="d68a9-137">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="d68a9-138">Handmatig ingevoerde of bewerkte beschrijvingen zijn zichtbaar voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="d68a9-138">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="d68a9-139">Personen</span><span class="sxs-lookup"><span data-stu-id="d68a9-139">People</span></span>|<span data-ttu-id="d68a9-140">Vastgemaakte personen zijn zichtbaar voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="d68a9-140">Pinned people are visible to all users.</span></span> <span data-ttu-id="d68a9-141">Voorgestelde personen zijn alleen zichtbaar voor gebruikers die zijn gemachtigd voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="d68a9-141">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="d68a9-142">Bestanden</span><span class="sxs-lookup"><span data-stu-id="d68a9-142">Files</span></span>|<span data-ttu-id="d68a9-143">Bestanden zijn alleen zichtbaar voor gebruikers die zijn gemachtigd voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="d68a9-143">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="d68a9-144">Pagina's</span><span class="sxs-lookup"><span data-stu-id="d68a9-144">Pages</span></span>|<span data-ttu-id="d68a9-145">Pagina's zijn alleen zichtbaar voor gebruikers die zijn gemachtigd voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="d68a9-145">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="d68a9-146">Sites</span><span class="sxs-lookup"><span data-stu-id="d68a9-146">Sites</span></span>|<span data-ttu-id="d68a9-147">Sites zijn alleen zichtbaar voor gebruikers die zijn gemachtigd voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="d68a9-147">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="d68a9-148">Zie ook</span><span class="sxs-lookup"><span data-stu-id="d68a9-148">See also</span></span>

