---
title: 'Onderwerpen beheren in het onderwerp centrum in topic Experience (preview) '
description: Onderwerpen beheren in het onderwerp centrum.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 832067d157ed9ffcba1ed9ad514c375cbbdd752b
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698836"
---
# <a name="manage-topics-in-the-topic-center-preview"></a><span data-ttu-id="4075c-103">Onderwerpen beheren in het onderwerp centrum (preview)</span><span class="sxs-lookup"><span data-stu-id="4075c-103">Manage topics in the Topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="4075c-104">De inhoud in dit artikel is bedoeld voor project cortex private preview.</span><span class="sxs-lookup"><span data-stu-id="4075c-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="4075c-105">[Meer informatie over Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="4075c-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="4075c-106">In het onderwerp centrum kan een kennis Manager de pagina **onderwerpen beheren** raadplegen om onderwerpen te zien die zijn gevonden in SharePoint-bronlocaties, zoals opgegeven door uw kennis beheerder.</span><span class="sxs-lookup"><span data-stu-id="4075c-106">In the Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![Onderwerpen centrum](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="4075c-108">Met kennis beheerders kunt u de begeleidende onderwerpen voor de levenscyclus van een onderwerp in de loop van de levenscyclus van onderwerpen raadplegen</span><span class="sxs-lookup"><span data-stu-id="4075c-108">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="4075c-109">Voorgesteld: er is een onderwerp aangeduid met AI en voldoende bronnen voor ondersteuning, verbindingen en eigenschappen om te voldoen aan de onderwerps drempel.</span><span class="sxs-lookup"><span data-stu-id="4075c-109">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties to meet the topic threshold.</span></span>
- <span data-ttu-id="4075c-110">Bevestigd: een onderwerp dat door AI is voorgesteld, is gevalideerd.</span><span class="sxs-lookup"><span data-stu-id="4075c-110">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="4075c-111">De validatie wordt uitgevoerd door de bevestiging van een Knowledge-beheerder. Daarnaast kan een onderwerp worden bevestigd als ten minste twee gebruikers positieve feedback geven via de feedback van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="4075c-111">Validation is done by confirmation from a knowledge admin. Additionally, a topic can be confirmed if at least two users give positive feedback through topic feedback that the topic is valid.</span></span>
- <span data-ttu-id="4075c-112">Verwijderd: een onderwerp wordt geweigerd door een Knowledge-beheerder en is niet meer zichtbaar voor kijkers.</span><span class="sxs-lookup"><span data-stu-id="4075c-112">Removed: A topic is rejected by a knowledge admin and will no longer be visible to viewers.</span></span> <span data-ttu-id="4075c-113">Het onderwerp kan in elke status worden weergegeven wanneer het wordt verwijderd (voorgesteld of bevestigd).</span><span class="sxs-lookup"><span data-stu-id="4075c-113">The topic can be in any state when it is removed (suggested or confirmed).</span></span> 
- <span data-ttu-id="4075c-114">Gepubliceerd: een bevestigd onderwerp dat handmatig is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="4075c-114">Published: A confirmed topic that has been manually updated.</span></span>

   ![Levenscyclus van onderwerpen](../media/knowledge-management/topic-lifecycle.png) </br> 

## <a name="requirements"></a><span data-ttu-id="4075c-116">Vereisten</span><span class="sxs-lookup"><span data-stu-id="4075c-116">Requirements</span></span>

<span data-ttu-id="4075c-117">Als u onderwerpen in het onderwerp centrum wilt beheren, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="4075c-117">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="4075c-118">Laat een licentie.</span><span class="sxs-lookup"><span data-stu-id="4075c-118">Have a Topic Experiences license.</span></span>
- <span data-ttu-id="4075c-119">Machtigingen hebben voor het [**beheren van onderwerpen**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span><span class="sxs-lookup"><span data-stu-id="4075c-119">Have permissions to [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span></span> <span data-ttu-id="4075c-120">Kennis beheerders kunnen aan deze machtiging gebruikers machtigen voor de instellingen van de machtigingen van het onderwerp van het kennis netwerk.</span><span class="sxs-lookup"><span data-stu-id="4075c-120">Knowledge admins can give users this permission in the Knowledge Network topic permissions settings.</span></span> 

<span data-ttu-id="4075c-121">Het is niet mogelijk om de pagina Manage topics in het onderwerp centrum weer te geven, tenzij u beschikt over de machtiging wie de machtiging **onderwerpen kunnen beheren** .</span><span class="sxs-lookup"><span data-stu-id="4075c-121">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="4075c-122">In het onderwerp centreren kan een kennis Manager onderwerpen controleren die zijn gevonden in de SharePoint-bronlocaties die u hebt opgegeven, en deze kunnen ofwel bevestigen of weigeren.</span><span class="sxs-lookup"><span data-stu-id="4075c-122">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="4075c-123">Een Knowledge Manager kan ook nieuwe topic pagina's maken en publiceren als die niet is gevonden in het detecteren van een onderwerp of bestaande pagina's bewerken als ze moeten worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="4075c-123">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="4075c-124">Bekijk de voorgestelde onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4075c-124">Review suggested topics</span></span>

<span data-ttu-id="4075c-125">Op de pagina Manage topics voor onderwerpen die zijn gevonden in de opgegeven SharePoint-bronlocaties, wordt het tabblad **Aanbevolen** weergegeven. Een kennis Manager kan onbevestigde onderwerpen controleren en ervoor kiezen om deze te bevestigen of te weigeren.</span><span class="sxs-lookup"><span data-stu-id="4075c-125">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

<span data-ttu-id="4075c-126">Een voorgesteld onderwerp bekijken:</span><span class="sxs-lookup"><span data-stu-id="4075c-126">To review a suggested topic:</span></span>

1. <span data-ttu-id="4075c-127">Selecteer op de pagina **Manage topics** het tabblad **voorgestelde** , selecteer het onderwerp om de onderwerp-pagina te openen.</span><span class="sxs-lookup"><span data-stu-id="4075c-127">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="4075c-128">Op de pagina onderwerp controleert u het onderwerp en selecteert u **bewerken** als u wijzigingen wilt aanbrengen aan de pagina.</span><span class="sxs-lookup"><span data-stu-id="4075c-128">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="4075c-129">Nadat u het onderwerp hebt gelezen, gaat u terug naar de pagina onderwerpen beheren.</span><span class="sxs-lookup"><span data-stu-id="4075c-129">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="4075c-130">Voor het geselecteerde onderwerp kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="4075c-130">For the selected topic, you can:</span></span>

   - <span data-ttu-id="4075c-131">Selecteer het vinkje om het onderwerp te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="4075c-131">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="4075c-132">Selecteer de **x** als u het onderwerp wilt negeren.</span><span class="sxs-lookup"><span data-stu-id="4075c-132">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="4075c-133">Bevestigde onderwerpen worden verwijderd uit de lijst **suggesties** en worden nu weergegeven in de lijst **bevestigd** .</span><span class="sxs-lookup"><span data-stu-id="4075c-133">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="4075c-134">Genegeerde onderwerpen worden verwijderd uit de **voorgestelde** lijst en worden nu weergegeven in het tabblad **verwijderd** .</span><span class="sxs-lookup"><span data-stu-id="4075c-134">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

## <a name="confirmed-topics"></a><span data-ttu-id="4075c-135">Bevestigde onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4075c-135">Confirmed topics</span></span>

<span data-ttu-id="4075c-136">Op de pagina Manage topics die zijn gevonden in de opgegeven SharePoint-bronlocaties en zijn bevestigd door een kennis Manager of ' op basis van ' gepaard ' bevestigd door twee of meer mensen via het kaart feedback mechanisme worden weergegeven op het tabblad **bevestigd** . Als dat nodig is, kan een gebruiker met machtigingen voor het beheren van onderwerpen bevestigde onderwerpen controleren en ervoor kiezen om deze te weigeren.</span><span class="sxs-lookup"><span data-stu-id="4075c-136">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="4075c-137">Een bevestigd onderwerp bekijken:</span><span class="sxs-lookup"><span data-stu-id="4075c-137">To review a confirmed topic:</span></span>

1. <span data-ttu-id="4075c-138">Selecteer op het tabblad **bevestigd** het onderwerp voor het openen van de onderwerpenpagina.</span><span class="sxs-lookup"><span data-stu-id="4075c-138">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="4075c-139">Op de pagina onderwerp controleert u het onderwerp en selecteert u **bewerken** als u wijzigingen wilt aanbrengen aan de pagina.</span><span class="sxs-lookup"><span data-stu-id="4075c-139">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="4075c-140">Houd er rekening mee dat u een bevestigd onderwerp wel kunt negeren.</span><span class="sxs-lookup"><span data-stu-id="4075c-140">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="4075c-141">Als u dit wilt doen, gaat u naar het geselecteerde onderwerp in de lijst bevestigd en selecteert u de **x** als u het onderwerp wilt negeren.</span><span class="sxs-lookup"><span data-stu-id="4075c-141">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="4075c-142">Gepubliceerde onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4075c-142">Published topics</span></span>
<span data-ttu-id="4075c-143">Gepubliceerde onderwerpen zijn bewerkt, zodat bepaalde informatie altijd wordt weergegeven voor iemand die de pagina tegenkomt.</span><span class="sxs-lookup"><span data-stu-id="4075c-143">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="4075c-144">Hier worden handmatig gemaakte onderwerpen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4075c-144">Manually created topics are listed here.</span></span>




