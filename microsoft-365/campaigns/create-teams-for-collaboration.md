---
title: Teams voor samenwerking aanmaken
f1.keywords:
- NOCSH
ms.author: samanro
author: samanro
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Maak een samenwerkingsruimte voor uw team met Microsoft teams.
ms.openlocfilehash: 7a07b7b90f5c89f6b1c6a6dd17145ca11af5dfa6
ms.sourcegitcommit: 1522a6471e0c5254a6d0f592e1f4dfacd1dd473a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/24/2020
ms.locfileid: "48245843"
---
# <a name="create-teams-for-collaboration-in-microsoft-teams"></a><span data-ttu-id="f291d-103">Teams maken voor samenwerking in Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="f291d-103">Create teams for collaboration in Microsoft Teams</span></span>

<span data-ttu-id="f291d-104">Microsoft teams is een Collaborate-app waarmee uw medewerkers georganiseerd blijven en gesprekken kunnen voeren vanaf elk apparaat.</span><span class="sxs-lookup"><span data-stu-id="f291d-104">Microsoft Teams is a collaboration app that helps your staff stay organized and have conversations, from any device.</span></span> <span data-ttu-id="f291d-105">U kunt Microsoft teams gebruiken om te chatten met leden van uw medewerkers of gasten buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f291d-105">You can use Microsoft Teams to have instant conversations with members of your staff or guests outside your organization.</span></span> <span data-ttu-id="f291d-106">U kunt ook telefoongesprekken voeren, vergaderingen hosten en bestanden delen.</span><span class="sxs-lookup"><span data-stu-id="f291d-106">You can also make phone calls, host meetings, and share files.</span></span>

## <a name="best-practices"></a><span data-ttu-id="f291d-107">Aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="f291d-107">Best practices</span></span>

<span data-ttu-id="f291d-108">In het voorbeeld kunnen campagnes de volgende teams maken om veilig te communiceren en samen te werken:</span><span class="sxs-lookup"><span data-stu-id="f291d-108">As an example, campaigns can create the following teams to communicate and collaborate securely:</span></span>

1. <span data-ttu-id="f291d-109">**Een team voor campagne-potentiële klanten:** Stel dit in als een privé team, zodat alleen de belangrijkste campagne leden toegang hebben tot de site en mogelijke gevoelige zaken te bespreken.</span><span class="sxs-lookup"><span data-stu-id="f291d-109">**A Campaign Leads team:** Set this up as a private team so that only your key campaign members can access it and discuss potentially sensitive concerns.</span></span>
2. <span data-ttu-id="f291d-110">**Een algemeen campagne team:** Dit is voor iedereen die moet worden gebruikt voor dagelijkse communicatie en werken.</span><span class="sxs-lookup"><span data-stu-id="f291d-110">**A general Campaign team:** This is for everyone to use for day to day communications and work.</span></span> <span data-ttu-id="f291d-111">Personen, groepen of comités kunnen kanalen in dit team instellen om hun werk te doen.</span><span class="sxs-lookup"><span data-stu-id="f291d-111">Individuals, groups, or committees can set up channels in this team to do their work.</span></span> <span data-ttu-id="f291d-112">Met bijvoorbeeld de evenementen voor het organiseren van activiteiten kunnen personen een kanaal opzetten voor het chatten en coördineren van de logistiek voor campagne gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="f291d-112">For example, the event planning people can set up a channel to chat and coordinate logistics for campaign events.</span></span>
3. <span data-ttu-id="f291d-113">**Partners team:** Dit is een team waar u kunt stemmen met uw leveranciers, partners of vrijwilligers, zonder dat ze iets gevoeliger mogen zijn.</span><span class="sxs-lookup"><span data-stu-id="f291d-113">**A partners team:** This is a team where you can coordinate with your vendors, partners, or volunteers without allowing them into anything sensitive.</span></span>

<span data-ttu-id="f291d-114">U kunt ook teams voor specifieke projecten maken en de juiste hoeveelheid bescherming toepassen op basis van wie moet worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="f291d-114">You can also create teams for specific projects and apply the right amount of protection based on who should be included.</span></span> 

![Diagram van een Microsoft teams-venster met drie afzonderlijke teams waarmee u veilig communicatie en samenwerking kunt toestaan](../media/m365-democracy-teams-collab.png)

<span data-ttu-id="f291d-116">Wanneer u een team maakt, wordt het volgende gemaakt:</span><span class="sxs-lookup"><span data-stu-id="f291d-116">When you create a team, here's what else gets created:</span></span>

- <span data-ttu-id="f291d-117">Een nieuwe [Microsoft 365-groep](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)</span><span class="sxs-lookup"><span data-stu-id="f291d-117">A new [Microsoft 365 group](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)</span></span>
- <span data-ttu-id="f291d-118">Een [SharePoint Online-](https://docs.microsoft.com/MicrosoftTeams/sharepoint-onedrive-interact) site en-documentbibliotheek voor het opslaan van team bestanden</span><span class="sxs-lookup"><span data-stu-id="f291d-118">A [SharePoint Online](https://docs.microsoft.com/MicrosoftTeams/sharepoint-onedrive-interact) site and document library to store team files</span></span>
- <span data-ttu-id="f291d-119">Een gedeeld postvak van [Exchange Online](https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact) en agenda</span><span class="sxs-lookup"><span data-stu-id="f291d-119">An [Exchange Online](https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact) shared mailbox and calendar</span></span>
- <span data-ttu-id="f291d-120">Een OneNote-notitieblok</span><span class="sxs-lookup"><span data-stu-id="f291d-120">A OneNote notebook</span></span>
- <span data-ttu-id="f291d-121">Is in andere Office 365-apps opgenomen, zoals planner en Power BI</span><span class="sxs-lookup"><span data-stu-id="f291d-121">Ties into other Office 365 apps such as Planner and Power BI</span></span>

<span data-ttu-id="f291d-122">In Microsoft teams kunt u het volgende vinden:</span><span class="sxs-lookup"><span data-stu-id="f291d-122">Inside Microsoft Teams, you can find:</span></span>
1. <span data-ttu-id="f291d-123">**Teams:** Kanalen zoeken waarmee u een deel wilt uitmaken.</span><span class="sxs-lookup"><span data-stu-id="f291d-123">**Teams:** Find channels to belong to or create your own.</span></span> <span data-ttu-id="f291d-124">Binnen kanalen kunt u tijdens het plaatsen van vergaderingen in de wacht zetten, gesprekken voeren en bestanden delen.</span><span class="sxs-lookup"><span data-stu-id="f291d-124">Inside channels you can hold on-the-spot meetings, have conversations, and share files.</span></span>

2. <span data-ttu-id="f291d-125">**Vergaderingen:** Bekijk alles wat u hebt uitgelijnd voor de dag of week.</span><span class="sxs-lookup"><span data-stu-id="f291d-125">**Meetings:** See everything you've got lined up for the day or week.</span></span> <span data-ttu-id="f291d-126">Of een vergadering plannen.</span><span class="sxs-lookup"><span data-stu-id="f291d-126">Or, schedule a meeting.</span></span> <span data-ttu-id="f291d-127">Deze agenda wordt gesynchroniseerd met uw Outlook-agenda.</span><span class="sxs-lookup"><span data-stu-id="f291d-127">This calendar syncs with your Outlook calendar.</span></span>
 
3. <span data-ttu-id="f291d-128">**Gesprekken:** In sommige gevallen, als uw organisatie dit heeft geconfigureerd, kunt u iedereen bellen vanuit Microsoft teams, zelfs als ze Microsoft teams niet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f291d-128">**Calls:** In some cases, if your organization has it set up, you can call anyone from Microsoft Teams, even if they're not using Microsoft Teams.</span></span>

4. <span data-ttu-id="f291d-129">**Activiteit:** Neem contact op met uw ongelezen berichten, @mentions, antwoorden en meer.</span><span class="sxs-lookup"><span data-stu-id="f291d-129">**Activity:** Catch up on all your unread messages, @mentions, replies, and more.</span></span> 

<span data-ttu-id="f291d-130">Gebruik het opdrachtvenster bovenaan om naar specifieke items of mensen te zoeken, snel acties te ondernemen en apps te starten.</span><span class="sxs-lookup"><span data-stu-id="f291d-130">Use the command box at the top to search for specific items or people, take quick actions, and launch apps.</span></span>


## <a name="set-it-up"></a><span data-ttu-id="f291d-131">Instellen</span><span class="sxs-lookup"><span data-stu-id="f291d-131">Set it up</span></span>


<span data-ttu-id="f291d-132">Maak een privé team voor alleen de campagne manager en de kandidaat zoals u dat wilt.</span><span class="sxs-lookup"><span data-stu-id="f291d-132">Create a private team for just the campaign manager and candidate like this.</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWeqWA]

<span data-ttu-id="f291d-133">Maak een team voor hele organisatie dat iedereen in de campagne kan gebruiken om bestanden te communiceren en te delen.</span><span class="sxs-lookup"><span data-stu-id="f291d-133">Create an organization-wide team that everyone in the campaign can use to communicate and share files.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2GCG9]

<span data-ttu-id="f291d-134">Maak een team dat u deelt met gasten buiten de campagne, zoals advertenties van financiering.</span><span class="sxs-lookup"><span data-stu-id="f291d-134">Create a team that you share with guests outside the campaign, such as advertising of financing.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FQMp]

<span data-ttu-id="f291d-135">Meer informatie over Microsoft teams voor [technische documentatie voor Microsoft teams](https://docs.microsoft.com/microsoftteams/microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="f291d-135">Learn more about Microsoft Teams at [Microsoft Teams technical documentation](https://docs.microsoft.com/microsoftteams/microsoft-teams)</span></span>

## <a name="admin-settings"></a><span data-ttu-id="f291d-136">Beheerdersinstellingen</span><span class="sxs-lookup"><span data-stu-id="f291d-136">Admin settings</span></span>

<span data-ttu-id="f291d-137">U moet een beheerder zijn om een team voor de hele organisatie te maken.</span><span class="sxs-lookup"><span data-stu-id="f291d-137">You must be an admin to create an organization-wide team.</span></span> <span data-ttu-id="f291d-138">Zie [Wat is een beheerder in Microsoft 365?](https://support.office.com/article/what-is-an-admin-e123627e-4892-4461-b9aa-1b6d57a5cfa4?ui=en-US&rs=en-US&ad=US)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f291d-138">For more information, see [What is an Admin in Microsoft 365?](https://support.office.com/article/what-is-an-admin-e123627e-4892-4461-b9aa-1b6d57a5cfa4?ui=en-US&rs=en-US&ad=US).</span></span>
  
