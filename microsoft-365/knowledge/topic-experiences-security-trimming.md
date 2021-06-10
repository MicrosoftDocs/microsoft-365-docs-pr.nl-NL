---
title: Beveiliging van Microsoft Viva-onderwerpen
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
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939621"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="f0c27-103">Beveiliging van Microsoft Viva-onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f0c27-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="f0c27-104">Gebruikers van Viva-onderwerpen kunnen geen informatie weergeven in onderwerpen die hun bestaande Office 365 voorkomen dat ze deze kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="f0c27-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="f0c27-105">Alles wat een gebruiker ziet op een onderwerppagina (bijvoorbeeld SharePoint sites, documenten, bestanden) zijn gegevens die ze al mogen zien.</span><span class="sxs-lookup"><span data-stu-id="f0c27-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="f0c27-106">Viva-onderwerpen brengen geen wijzigingen aan in bestaande machtigingen.</span><span class="sxs-lookup"><span data-stu-id="f0c27-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="f0c27-107">Waarom twee gebruikers verschillende weergaven van hetzelfde onderwerp hebben</span><span class="sxs-lookup"><span data-stu-id="f0c27-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="f0c27-108">Wanneer een onderwerp wordt gemaakt via AI of handmatige curatie, kan het een beschrijving bevatten van het onderwerp, alternatieve namen, personen die aan het onderwerp zijn gekoppeld, evenals sites, pagina's en bestanden met betrekking tot het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="f0c27-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="f0c27-109">Wanneer deze informatie wordt weergegeven op een onderwerppagina, is het mogelijk dat twee gebruikers die hetzelfde onderwerp bekijken, dezelfde informatie niet zien.</span><span class="sxs-lookup"><span data-stu-id="f0c27-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="f0c27-110">Als gebruiker 1 bijvoorbeeld de onderwerppagina van Den Oudsten bekijkt, kunnen ze deze weergave van de onderwerppagina zien.</span><span class="sxs-lookup"><span data-stu-id="f0c27-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![Onderwerp Van Den Oudsten voor gebruiker 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="f0c27-112">Wanneer gebruiker 2 echter naar dezelfde onderwerppagina van Neptunus kijkt, verschilt de weergave van gebruiker 1.</span><span class="sxs-lookup"><span data-stu-id="f0c27-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="f0c27-113">Gebruiker 2 kan het *BESTAND PRODUCToverzicht VAN DG-2000* zien in de sectie Vastgemaakte bestanden en pagina's van de onderwerppagina, die niet wordt weergegeven voor gebruiker 1. </span><span class="sxs-lookup"><span data-stu-id="f0c27-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Onderwerp Van Den Oudsten voor gebruiker 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="f0c27-115">Het verschil in wat gebruikers over hetzelfde onderwerp kunnen zien, is omdat gebruikers mogelijk niet de Office 365 hebben om een gerelateerde site of bestand te bekijken.</span><span class="sxs-lookup"><span data-stu-id="f0c27-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="f0c27-116">Viva-onderwerpen respecteert de machtigingen die zijn ingesteld voor items in een onderwerp en kunnen de toegang tot items niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="f0c27-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="f0c27-117">In ons voorbeeld kan gebruiker 1 het *BESTAND VAN DG-2000 Productoverzicht* niet weergeven op de onderwerppagina voor Neptunus, omdat gebruiker 1 geen Office 365 machtigingen heeft om het bestand te bekijken.</span><span class="sxs-lookup"><span data-stu-id="f0c27-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="f0c27-118">Als een gebruiker onvoldoende informatie in een onderwerp kan zien om het nuttig te maken, is het onderwerp niet beschikbaar voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="f0c27-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="f0c27-119">Wanneer dit gebeurt, ziet de gebruiker het gemarkeerde onderwerp niet.</span><span class="sxs-lookup"><span data-stu-id="f0c27-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="f0c27-120">Een andere gebruiker die machtigingen heeft voor meer informatie in het onderwerp, kan het onderwerp zien.</span><span class="sxs-lookup"><span data-stu-id="f0c27-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="f0c27-121">Onderwerpmachtigingen voor kennismanagers en onderwerpcontribuanten</span><span class="sxs-lookup"><span data-stu-id="f0c27-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="f0c27-122">Gebruikers aan wie machtigingen zijn toegewezen voor het beheren van onderwerpen - kennisbeheerders - kunnen alleen informatie bekijken die ze in onderwerpen kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="f0c27-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="f0c27-123">Op dezelfde manier kunnen gebruikers die onderwerpmachtigingen ( onderwerpcontribuanten) hebben, alleen informatie bekijken die ze in onderwerpen kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="f0c27-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="f0c27-124">AI versus handmatig samengestelde onderwerpgegevens</span><span class="sxs-lookup"><span data-stu-id="f0c27-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="f0c27-125">Onderwerpen kunnen informatie bevatten die wordt gegenereerd door AI en informatie die is toegevoegd of bewerkt door onderwerpcontribuanten of kennisbeheerders.</span><span class="sxs-lookup"><span data-stu-id="f0c27-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="f0c27-126">Informatie in een onderwerp dat door AI is toegevoegd, is alleen zichtbaar voor personen die toegang hebben tot de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="f0c27-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="f0c27-127">Onderwerpbeschrijving en personengegevens die handmatig zijn toegevoegd of bewerkt door een inzender of kennisbeheerder van het onderwerp, zijn zichtbaar voor iedereen die het onderwerp kan zien.</span><span class="sxs-lookup"><span data-stu-id="f0c27-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="f0c27-128">Bestanden, pagina's en sites zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud, ongeacht of ze handmatig zijn toegevoegd of toegevoegd door AI.</span><span class="sxs-lookup"><span data-stu-id="f0c27-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="f0c27-129">In de volgende tabel wordt beschreven wat gebruikers - kijkers van onderwerpen, medewerkers en kennisbeheerders - kunnen zien in een bepaald onderwerp op basis van hun machtigingen.</span><span class="sxs-lookup"><span data-stu-id="f0c27-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="f0c27-130">Onderwerpitem</span><span class="sxs-lookup"><span data-stu-id="f0c27-130">Topic item</span></span>|<span data-ttu-id="f0c27-131">Wat gebruikers kunnen zien</span><span class="sxs-lookup"><span data-stu-id="f0c27-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="f0c27-132">Onderwerpnaam</span><span class="sxs-lookup"><span data-stu-id="f0c27-132">Topic name</span></span>|<span data-ttu-id="f0c27-133">Gebruikers kunnen de onderwerpnaam van onderwerpen zien in het onderwerpcentrum.</span><span class="sxs-lookup"><span data-stu-id="f0c27-133">Users can see the topic name of topics in the topic center.</span></span> <span data-ttu-id="f0c27-134">Sommige onderwerpen zijn mogelijk niet zichtbaar als gebruikers geen machtigingen voor de broninhoud hebben of een lage relevantie voor de gebruiker hebben.</span><span class="sxs-lookup"><span data-stu-id="f0c27-134">Some topics may not be visible if users don't have permissions to the source content or have a low relevancy to the user.</span></span>|
|<span data-ttu-id="f0c27-135">Beschrijving van onderwerp</span><span class="sxs-lookup"><span data-stu-id="f0c27-135">Topic description</span></span>|<span data-ttu-id="f0c27-136">Door AI gegenereerde beschrijvingen zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="f0c27-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="f0c27-137">Handmatig ingevoerde of bewerkte beschrijvingen zijn zichtbaar voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="f0c27-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="f0c27-138">Personen</span><span class="sxs-lookup"><span data-stu-id="f0c27-138">People</span></span>|<span data-ttu-id="f0c27-139">Vastgemaakte personen zijn zichtbaar voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="f0c27-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="f0c27-140">Voorgestelde personen zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="f0c27-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="f0c27-141">Bestanden</span><span class="sxs-lookup"><span data-stu-id="f0c27-141">Files</span></span>|<span data-ttu-id="f0c27-142">Bestanden zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="f0c27-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="f0c27-143">Pagina's</span><span class="sxs-lookup"><span data-stu-id="f0c27-143">Pages</span></span>|<span data-ttu-id="f0c27-144">Pagina's zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="f0c27-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="f0c27-145">Sites</span><span class="sxs-lookup"><span data-stu-id="f0c27-145">Sites</span></span>|<span data-ttu-id="f0c27-146">Sites zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="f0c27-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="f0c27-147">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f0c27-147">See also</span></span>

