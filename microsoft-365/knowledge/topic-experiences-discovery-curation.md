---
title: 'Onderwerp ontdekking en curator (preview) '
description: Overzicht van de manier waarop onderwerpen worden gedetecteerd.
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: ea0bbc1f7d34ff01fcf446bfa4bbd0b95f310c4c
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976165"
---
# <a name="topic-experiences-discovery-and-curation-preview"></a><span data-ttu-id="2584f-103">Onderwerp met detectie en curator (preview)</span><span class="sxs-lookup"><span data-stu-id="2584f-103">Topic Experiences discovery and curation (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="2584f-104">De inhoud in dit artikel is bedoeld voor project cortex private preview.</span><span class="sxs-lookup"><span data-stu-id="2584f-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="2584f-105">[Meer informatie over Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="2584f-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="2584f-106">Met beantwoorde functies worden kennis gegevens geconverteerd naar informatie in uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="2584f-106">Topic Experiences converts knowledge information to knowledge in your Microsoft 365 environment.</span></span> <span data-ttu-id="2584f-107">We hebben al ervaring met het lezen van documenten en sitepagina's, waar we de voorwaarden kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="2584f-107">We've all experienced reading through documents and site pages where we encounter terms we are unfamiliar with.</span></span> <span data-ttu-id="2584f-108">Het is heel vaak om te voorkomen dat we in de loop van de tijd overgaan naar meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2584f-108">Many times we stop what we are doing to spend precious time searching for more information.</span></span>

<span data-ttu-id="2584f-109">Voor wat u doet, maakt u gebruik van Microsoft Graph en AI voor het identificeren van **onderwerpen** in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2584f-109">What Topic Experiences does is use Microsoft Graph and AI to identify **topics** in your organization.</span></span>  <span data-ttu-id="2584f-110">Een onderwerp is een woordgroep of term met een specifieke betekenis van een organisatie, waarbij gebruikers liever een wikipagina kunnen weergeven.</span><span class="sxs-lookup"><span data-stu-id="2584f-110">A topic is a phrase or term that has a specific meaning to an organization, where users would benefit by being able to view a wiki page about it.</span></span> <span data-ttu-id="2584f-111">Met AI kunt u zoeken naar personen en inhoud die met het onderwerp verbonden zijn, en als u er genoeg ter detectie wordt, wordt dit een suggestie onderwerp.</span><span class="sxs-lookup"><span data-stu-id="2584f-111">AI searches for people and content connected to the topic, and if enough it discovered, it becomes a suggested topic.</span></span>

<span data-ttu-id="2584f-112">De gegevens van een AI-gegenereerde alinea worden toegevoegd aan een **onderwerpenpagina**, die kan bestaan uit:</span><span class="sxs-lookup"><span data-stu-id="2584f-112">The AI generated topic information is added to a **Topic page**, which can contain:</span></span>
- <span data-ttu-id="2584f-113">Een korte beschrijving van het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="2584f-113">A short description of the topic.</span></span>
- <span data-ttu-id="2584f-114">Alternatieve namen voor het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="2584f-114">Alternate names for the topic.</span></span>
- <span data-ttu-id="2584f-115">Personen die mogelijk meer weten over het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="2584f-115">People who might know more about the topic.</span></span>
- <span data-ttu-id="2584f-116">Sites, bestanden en pagina's die mogelijk zijn gerelateerd aan het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="2584f-116">Sites, files, and pages that might be related to the topic.</span></span>

<span data-ttu-id="2584f-117">Met een onderwerp zorgt u ervoor dat elk exemplaar van een onderwerp is gemarkeerd op alle pagina's van de moderne SharePoint-site in uw Tenant.</span><span class="sxs-lookup"><span data-stu-id="2584f-117">Topic experiences then makes sure that every instance of a topic is highlighted on all SharePoint modern site pages in your tenant.</span></span> <span data-ttu-id="2584f-118">Wanneer een gebruiker meer wilt weten over een onderwerp, kunnen ze het gemarkeerde onderwerp selecteren om een **samenvattingsrij** met een korte beschrijving te bekijken.</span><span class="sxs-lookup"><span data-stu-id="2584f-118">When a user is curious to learn more about a topic, they can select the highlighted topic to view a **Topic summary** card that provides a short description.</span></span> <span data-ttu-id="2584f-119">En als ze meer willen weten, kunnen ze een koppeling naar **Details** van het onderwerp selecteren in het overzicht om de pagina gedetailleerd onderwerp te openen.</span><span class="sxs-lookup"><span data-stu-id="2584f-119">And if they want to learn more, they can select a **Topic details** link in the summary to open the detailed topic page.</span></span>

![Aandachtspunten](../media/knowledge-management/saturn.png) </br>

<span data-ttu-id="2584f-121">Daarnaast kunnen gebruikers ook onderwerpen zoeken via Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="2584f-121">Additionally, users will also be able to find topics through Microsoft Search.</span></span>


## <a name="topic-curation"></a><span data-ttu-id="2584f-122">Onderwerp-curator</span><span class="sxs-lookup"><span data-stu-id="2584f-122">Topic curation</span></span>

<span data-ttu-id="2584f-123">In het onderwerp wordt de kwaliteit van de onderwerpen verbeterd.</span><span class="sxs-lookup"><span data-stu-id="2584f-123">Topic Experiences welcomes human "curation" to improve the quality of your topics.</span></span> <span data-ttu-id="2584f-124">Terwijl AI in eerste instantie de onderwerpen identificeert en vermoedt, handmatig updates voor inhoud van medewerkers, bevestiging van gebruikers voor AI-inhoud die is gegenereerd en feedback over de bruikbaarheid van onderwerpen zijn allemaal essentieel.</span><span class="sxs-lookup"><span data-stu-id="2584f-124">While AI initially identifies and suggests topics, manually made updates to content from contributors, confirmation from users for AI generated content, and feedback on the usefulness of topics are all essential.</span></span>

- <span data-ttu-id="2584f-125">Met AI gegenereerde onderwerpen (' voorgestelde onderwerpen ') kunt u een beoordeling door de **kennis van beheerders** in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2584f-125">AI generated topics ("suggested topics") can be reviewed by **knowledge managers** in your organization.</span></span> <span data-ttu-id="2584f-126">Op de pagina Manage topics in het onderwerp kunnen ze ze op hun geldige manier verifiëren of weigeren om te voorkomen dat ze deze kunnen weergeven.</span><span class="sxs-lookup"><span data-stu-id="2584f-126">In the Manage Topics page in the Topic Center, they can choose to confirm them as valid, or reject them to prevent them from being viewed.</span></span>

- <span data-ttu-id="2584f-127">U kunt de machtigingen voor het *maken en bewerken van onderwerpen* toewijzen aan alle gebruikers met een licentie, zodat ze wijzigingen kunnen aanbrengen in bestaande onderwerpen of nieuwe onderwerpen kunnen maken wanneer dat nodig is.</span><span class="sxs-lookup"><span data-stu-id="2584f-127">You can assign *Create and edit topics* permissions to any of your licensed users so that they can make changes to existing topics or create new topics when needed.</span></span> 

- <span data-ttu-id="2584f-128">Zelfs gebruikers die alleen leestoegang hebben tot het onderwerp (de bezoekers van het onderwerp) worden gevraagd de bruikbaarheid van specifieke onderwerpen te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="2584f-128">Even users who only have read access to topic (topic viewers) will be asked to verify the usefulness of specific topics.</span></span>

<span data-ttu-id="2584f-129">Ook met menselijke curator zal AI continu informatie vinden over onderwerpen, en er wordt gezocht naar menselijke verificatie.</span><span class="sxs-lookup"><span data-stu-id="2584f-129">Even with human curation, AI will continually look for more information about topics, and will look for human verification.</span></span> <span data-ttu-id="2584f-130">Als u bijvoorbeeld van AI denkt dat u een persoon bent die als deskundige moet worden vastgemaakt, wordt u gevraagd om dit te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="2584f-130">For example, if AI thinks you are a person that should be pinned as an expert on a topic, it will ask you to confirm this.</span></span> 

















## <a name="see-also"></a><span data-ttu-id="2584f-131">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2584f-131">See also</span></span>



  






