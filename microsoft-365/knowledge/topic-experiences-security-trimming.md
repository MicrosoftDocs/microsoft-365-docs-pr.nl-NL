---
title: Beveiligingsknippen voor Microsoft Viva-onderwerpen
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: Overzicht van de manier waarop beveiliging wordt gebruikt om onderwerpen weer te geven.
ms.openlocfilehash: 12a2ad34c55cd63468266abca1fa053048053dd2
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279330"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="bc9ac-103">Beveiligingsknippen voor Microsoft Viva-onderwerpen</span><span class="sxs-lookup"><span data-stu-id="bc9ac-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="bc9ac-104">Gebruikers van Viva-onderwerpen kunnen geen informatie bekijken in onderwerpen die hun bestaande Office 365-machtigingen niet kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="bc9ac-105">Alles wat een gebruiker op een onderwerppagina ziet (bijvoorbeeld SharePoint-sites, documenten en bestanden), is informatie die hij of zij al mag zien.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="bc9ac-106">Viva-onderwerpen brengen geen wijzigingen aan in bestaande machtigingen.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="bc9ac-107">Waarom twee gebruikers mogelijk verschillende weergaven van hetzelfde onderwerp hebben</span><span class="sxs-lookup"><span data-stu-id="bc9ac-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="bc9ac-108">Wanneer een onderwerp wordt gemaakt via AI of handmatige curation, kan het een beschrijving bevatten van het onderwerp, alternatieve namen, personen die aan het onderwerp zijn gekoppeld, evenals sites, pagina's en bestanden met betrekking tot het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="bc9ac-109">Wanneer deze informatie wordt weergegeven op een onderwerppagina, is het mogelijk dat twee gebruikers die hetzelfde onderwerp bekijken, dezelfde informatie niet zien.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="bc9ac-110">Wanneer Gebruiker 1 bijvoorbeeld de onderwerppagina Van Nieuw bekijkt, kan deze weergave van de onderwerppagina worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![Toegangsonderwerp voor gebruiker 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="bc9ac-112">Wanneer Gebruiker 2 echter naar dezelfde Pagina van het Onderwerp kijkt, verschilt de weergave van Gebruiker 1.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="bc9ac-113">Gebruiker 2 kan het bestand *DG-2000* Product  overview zien in de sectie Vastgemaakte bestanden en pagina's van de onderwerppagina, die niet wordt weergegeven voor Gebruiker 1.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Het onderwerp Van 365 voor gebruiker 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="bc9ac-115">Het verschil met wat gebruikers over hetzelfde onderwerp kunnen zien, is dat gebruikers mogelijk niet over de office 365-machtigingen voor het weergeven van een gerelateerde site of een gerelateerd bestand zijn.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="bc9ac-116">Viva-onderwerpen respecteert de machtigingen die zijn ingesteld voor items in een onderwerp en kunnen de toegang tot deze items niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="bc9ac-117">In ons voorbeeld kan Gebruiker 1 het bestand *DG-2000 Product Overview* niet weergeven op de onderwerppagina voor Deze omdat Gebruiker 1 geen Office 365-machtigingen heeft om het bestand te bekijken.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="bc9ac-118">Als een gebruiker niet voldoende informatie in een onderwerp kan zien om het nuttig te maken, is het onderwerp niet beschikbaar voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="bc9ac-119">Wanneer dit gebeurt, ziet de gebruiker het gemarkeerde onderwerp niet.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="bc9ac-120">Een andere gebruiker die over machtigingen beschikt om meer informatie hierover te lezen, kan het onderwerp bekijken.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="bc9ac-121">Onderwerpmachtigingen voor kennisbeheerders en onderwerpbijdragers</span><span class="sxs-lookup"><span data-stu-id="bc9ac-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="bc9ac-122">Gebruikers aan wie een machtiging is toegewezen om onderwerpen te beheren (knowledge managers) kunnen alleen informatie bekijken die ze over machtigingen voor het bekijken van onderwerpen hebben.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="bc9ac-123">Op dezelfde manier kunnen gebruikers die onderwerpmachtigingen (onderwerpbijdragen) hebben, alleen informatie bekijken die ze over machtigingen voor weergave in onderwerpen hebben.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="bc9ac-124">AI versus handmatig curated topic information</span><span class="sxs-lookup"><span data-stu-id="bc9ac-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="bc9ac-125">Onderwerpen kunnen informatie bevatten die wordt gegenereerd door AI en informatie die is toegevoegd of bewerkt door onderwerpbijdragers of knowledge managers.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="bc9ac-126">De informatie in een onderwerp dat door AI is toegevoegd, is alleen zichtbaar voor personen die toegang hebben tot de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="bc9ac-127">Informatie over onderwerpbeschrijvingen en personen die handmatig zijn toegevoegd of bewerkt door een onderwerpbijdrager of Knowledge Manager, is zichtbaar voor iedereen die het onderwerp kan zien.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="bc9ac-128">Bestanden, pagina's en sites zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud, ongeacht of ze handmatig zijn toegevoegd of toegevoegd door AI.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="bc9ac-129">In de volgende tabel wordt beschreven wat gebruikers , onderwerpbekijkers, medewerkers en kennismanagers, in een bepaald onderwerp kunnen zien op basis van hun machtigingen.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="bc9ac-130">Onderwerpitem</span><span class="sxs-lookup"><span data-stu-id="bc9ac-130">Topic item</span></span>|<span data-ttu-id="bc9ac-131">Wat gebruikers kunnen zien</span><span class="sxs-lookup"><span data-stu-id="bc9ac-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="bc9ac-132">Onderwerpnaam</span><span class="sxs-lookup"><span data-stu-id="bc9ac-132">Topic name</span></span>|<span data-ttu-id="bc9ac-133">Gebruikers kunnen de onderwerpnaam van alle onderwerpen in het onderwerpcentrum zien.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-133">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="bc9ac-134">Sommige onderwerpen zijn mogelijk niet zichtbaar als ze een lage relevantie voor de gebruiker hebben.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-134">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="bc9ac-135">Onderwerpbeschrijving</span><span class="sxs-lookup"><span data-stu-id="bc9ac-135">Topic description</span></span>|<span data-ttu-id="bc9ac-136">Door AI gegenereerde beschrijvingen zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="bc9ac-137">Handmatig ingevoerde of bewerkte beschrijvingen zijn zichtbaar voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="bc9ac-138">Personen</span><span class="sxs-lookup"><span data-stu-id="bc9ac-138">People</span></span>|<span data-ttu-id="bc9ac-139">Vastgemaakte personen zijn zichtbaar voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="bc9ac-140">Voorgestelde personen zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="bc9ac-141">Bestanden</span><span class="sxs-lookup"><span data-stu-id="bc9ac-141">Files</span></span>|<span data-ttu-id="bc9ac-142">Bestanden zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="bc9ac-143">Pagina's</span><span class="sxs-lookup"><span data-stu-id="bc9ac-143">Pages</span></span>|<span data-ttu-id="bc9ac-144">Pagina's zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="bc9ac-145">Sites</span><span class="sxs-lookup"><span data-stu-id="bc9ac-145">Sites</span></span>|<span data-ttu-id="bc9ac-146">Sites zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="bc9ac-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="bc9ac-147">Zie ook</span><span class="sxs-lookup"><span data-stu-id="bc9ac-147">See also</span></span>

