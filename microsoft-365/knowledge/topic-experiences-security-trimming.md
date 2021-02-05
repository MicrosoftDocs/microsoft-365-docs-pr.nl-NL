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
ms.openlocfilehash: fc8e2a08fcf9af266aee49eee878738f7f17aa59
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107516"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="e4b44-103">Beveiligingsknippen voor Microsoft Viva-onderwerpen</span><span class="sxs-lookup"><span data-stu-id="e4b44-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="e4b44-104">Gebruikers van Viva-onderwerpen kunnen geen informatie bekijken in onderwerpen die hun bestaande Office 365-machtigingen niet kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="e4b44-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="e4b44-105">Alles wat een gebruiker op een onderwerppagina ziet (bijvoorbeeld SharePoint-sites, documenten en bestanden), is informatie die hij of zij al mag zien.</span><span class="sxs-lookup"><span data-stu-id="e4b44-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="e4b44-106">Viva-onderwerpen brengen geen wijzigingen aan in bestaande machtigingen.</span><span class="sxs-lookup"><span data-stu-id="e4b44-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="e4b44-107">Waarom twee gebruikers mogelijk verschillende weergaven van hetzelfde onderwerp hebben</span><span class="sxs-lookup"><span data-stu-id="e4b44-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="e4b44-108">Wanneer een onderwerp wordt gemaakt via AI of handmatige curation, kan het een beschrijving bevatten van het onderwerp, alternatieve namen, personen die aan het onderwerp zijn gekoppeld, evenals sites, pagina's en bestanden met betrekking tot het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="e4b44-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="e4b44-109">Wanneer deze informatie wordt weergegeven op een onderwerppagina, is het mogelijk dat twee gebruikers die hetzelfde onderwerp bekijken, dezelfde informatie niet zien.</span><span class="sxs-lookup"><span data-stu-id="e4b44-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="e4b44-110">Wanneer Gebruiker 1 bijvoorbeeld de onderwerppagina Van Nieuw bekijkt, kan deze weergave van de onderwerppagina worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="e4b44-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![Het onderwerp Van Zuid voor gebruiker 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="e4b44-112">Wanneer Gebruiker 2 echter naar dezelfde Pagina van het Onderwerp kijkt, verschilt de weergave van Gebruiker 1.</span><span class="sxs-lookup"><span data-stu-id="e4b44-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="e4b44-113">Gebruiker 2 kan het bestand *DG-2000 Product overview* zien in de sectie **Vastgemaakte** bestanden en pagina's van de onderwerppagina, die niet wordt weergegeven voor Gebruiker 1.</span><span class="sxs-lookup"><span data-stu-id="e4b44-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Het onderwerp Van 365 voor Gebruiker 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="e4b44-115">Het verschil met wat gebruikers over hetzelfde onderwerp kunnen zien, is dat gebruikers mogelijk niet over de office 365-machtigingen voor het weergeven van een gerelateerde site of een gerelateerd bestand zijn.</span><span class="sxs-lookup"><span data-stu-id="e4b44-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="e4b44-116">Viva-onderwerpen respecteert de machtigingen die zijn ingesteld voor items in een onderwerp en kunnen de toegang tot deze items niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e4b44-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="e4b44-117">In ons voorbeeld kan Gebruiker 1 het bestand *DG-2000 Product Overview* niet weergeven op de onderwerppagina voor Deze omdat Gebruiker 1 geen Office 365-machtigingen heeft om het bestand te bekijken.</span><span class="sxs-lookup"><span data-stu-id="e4b44-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="e4b44-118">Als een gebruiker niet voldoende informatie in een onderwerp kan zien om het nuttig te maken, is het onderwerp niet beschikbaar voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="e4b44-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="e4b44-119">Wanneer dit gebeurt, ziet de gebruiker het gemarkeerde onderwerp niet.</span><span class="sxs-lookup"><span data-stu-id="e4b44-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="e4b44-120">Een andere gebruiker die machtigingen heeft voor meer informatie over het onderwerp om dit nuttig te maken, kan het onderwerp zien.</span><span class="sxs-lookup"><span data-stu-id="e4b44-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="e4b44-121">Onderwerpmachtigingen voor kennisbeheerders en onderwerpbijdragers</span><span class="sxs-lookup"><span data-stu-id="e4b44-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="e4b44-122">Gebruikers aan wie een machtiging is toegewezen om onderwerpen te beheren (knowledge managers) kunnen alleen informatie bekijken die ze over machtigingen voor het bekijken van onderwerpen hebben.</span><span class="sxs-lookup"><span data-stu-id="e4b44-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="e4b44-123">Op dezelfde manier kunnen gebruikers die onderwerpmachtigingen (onderwerpbijdragen) hebben, alleen informatie bekijken die ze over machtigingen voor weergave in onderwerpen hebben.</span><span class="sxs-lookup"><span data-stu-id="e4b44-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="e4b44-124">AI versus handmatig curated topic information</span><span class="sxs-lookup"><span data-stu-id="e4b44-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="e4b44-125">Onderwerpen kunnen informatie bevatten die wordt gegenereerd door AI en informatie die is toegevoegd of bewerkt door onderwerpbijdragers of knowledge managers.</span><span class="sxs-lookup"><span data-stu-id="e4b44-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="e4b44-126">De informatie in een onderwerp dat door AI is toegevoegd, is alleen zichtbaar voor personen die toegang hebben tot de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="e4b44-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="e4b44-127">Informatie die handmatig is toegevoegd of bewerkt door een onderwerp-medewerker of Knowledge Manager is zichtbaar voor iedereen die het onderwerp kan zien.</span><span class="sxs-lookup"><span data-stu-id="e4b44-127">Information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>

<span data-ttu-id="e4b44-128">In de volgende tabel wordt beschreven wat gebruikers , onderwerpbekijkers, medewerkers en kennismanagers, in een bepaald onderwerp kunnen zien op basis van hun machtigingen.</span><span class="sxs-lookup"><span data-stu-id="e4b44-128">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="e4b44-129">Onderwerpitem</span><span class="sxs-lookup"><span data-stu-id="e4b44-129">Topic item</span></span>|<span data-ttu-id="e4b44-130">Wat gebruikers kunnen zien</span><span class="sxs-lookup"><span data-stu-id="e4b44-130">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="e4b44-131">Onderwerpnaam</span><span class="sxs-lookup"><span data-stu-id="e4b44-131">Topic name</span></span>|<span data-ttu-id="e4b44-132">Gebruikers kunnen de onderwerpnaam van alle onderwerpen in het onderwerpcentrum zien.</span><span class="sxs-lookup"><span data-stu-id="e4b44-132">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="e4b44-133">Sommige onderwerpen zijn mogelijk niet zichtbaar als ze een lage relevantie voor de gebruiker hebben.</span><span class="sxs-lookup"><span data-stu-id="e4b44-133">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="e4b44-134">Onderwerpbeschrijving</span><span class="sxs-lookup"><span data-stu-id="e4b44-134">Topic description</span></span>|<span data-ttu-id="e4b44-135">Door AI gegenereerde beschrijvingen zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="e4b44-135">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="e4b44-136">Handmatig ingevoerde of bewerkte beschrijvingen zijn zichtbaar voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="e4b44-136">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="e4b44-137">Personen</span><span class="sxs-lookup"><span data-stu-id="e4b44-137">People</span></span>|<span data-ttu-id="e4b44-138">Vastgemaakte personen zijn zichtbaar voor alle gebruikers.</span><span class="sxs-lookup"><span data-stu-id="e4b44-138">Pinned people are visible to all users.</span></span> <span data-ttu-id="e4b44-139">Voorgestelde personen zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="e4b44-139">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="e4b44-140">Bestanden</span><span class="sxs-lookup"><span data-stu-id="e4b44-140">Files</span></span>|<span data-ttu-id="e4b44-141">Bestanden zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="e4b44-141">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="e4b44-142">Pagina's</span><span class="sxs-lookup"><span data-stu-id="e4b44-142">Pages</span></span>|<span data-ttu-id="e4b44-143">Pagina's zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="e4b44-143">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="e4b44-144">Sites</span><span class="sxs-lookup"><span data-stu-id="e4b44-144">Sites</span></span>|<span data-ttu-id="e4b44-145">Sites zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.</span><span class="sxs-lookup"><span data-stu-id="e4b44-145">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="e4b44-146">Zie ook</span><span class="sxs-lookup"><span data-stu-id="e4b44-146">See also</span></span>

