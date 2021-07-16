---
title: Multi-Geo-mogelijkheden in Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: Meer informatie over hoe Teams werken met Microsoft 365 Multi-Geo.
ms.openlocfilehash: 7da2032e1106d03178eccf3bcfb4f37fc63780d7
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453523"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a><span data-ttu-id="8c86d-103">Multi-Geo-mogelijkheden in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c86d-103">Multi-Geo capabilities in Microsoft Teams</span></span>

<span data-ttu-id="8c86d-104">Met multi-geo-mogelijkheden in Teams kunt Teams chatgegevens in rust opslaan op een opgegeven geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="8c86d-104">Multi-Geo capabilities in Teams enables Teams chat data to be stored at rest in a specified geo location.</span></span> <span data-ttu-id="8c86d-105">Chatgegevens bestaan uit chatberichten, waaronder privéberichten, kanaalberichten en afbeeldingen die worden gebruikt in chats.</span><span class="sxs-lookup"><span data-stu-id="8c86d-105">Chat data consists of chat messages, including private messages, channel messages, and images used in chats.</span></span>

<span data-ttu-id="8c86d-106">Teams gebruikt pdl (Preferred Data Location) voor gebruikers en groepen om te bepalen waar gegevens moeten worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="8c86d-106">Teams uses the Preferred Data Location (PDL) for users and groups to determine where to store data.</span></span> <span data-ttu-id="8c86d-107">Als het PDF-nummer niet is ingesteld of ongeldig is, worden gegevens opgeslagen op de centrale locatie van de tenant.</span><span class="sxs-lookup"><span data-stu-id="8c86d-107">If the PDL is not set or is invalid, data is stored in the tenant's central location.</span></span>

## <a name="user-chat"></a><span data-ttu-id="8c86d-108">Gebruikerschat</span><span class="sxs-lookup"><span data-stu-id="8c86d-108">User chat</span></span>

<span data-ttu-id="8c86d-109">Gebruikerschat bevat een-op-een-, een-op-veel- en privévergaderingsberichten.</span><span class="sxs-lookup"><span data-stu-id="8c86d-109">User chat includes one-to-one, one-to-many, and private meeting messages.</span></span>

<span data-ttu-id="8c86d-110">Wanneer een nieuwe gebruiker wordt gemaakt, Teams de PDL van de gebruiker en slaat u al hun chatgegevens op die geografische locatie op.</span><span class="sxs-lookup"><span data-stu-id="8c86d-110">When a new user is created, Teams reads the user's PDL and stores all their chat data in that geo location.</span></span>

<span data-ttu-id="8c86d-111">Als een beheerder voor bestaande gebruikers de PDL voor een gebruiker toevoegt of wijzigt, worden de chatgegevens van die gebruiker toegevoegd aan een migratiewachtrij die moet worden verplaatst naar de opgegeven geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="8c86d-111">For existing users, if an administrator adds or modifies the PDL for a user, that user's chat data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="8c86d-112">De opslaglocatie voor een een-op-een- of een-op-veel-chat is gebaseerd op de PDL van de persoon die de chat heeft gemaakt.</span><span class="sxs-lookup"><span data-stu-id="8c86d-112">The storage location for a one-to-one or one-to-many chat is based on the PDL of the person who created the chat.</span></span> <span data-ttu-id="8c86d-113">Als de PDL van die gebruiker wordt gewijzigd, wordt de chat gemigreerd naar de nieuwe geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="8c86d-113">If that user's PDL is changed, the chat will be migrated to the new geo location.</span></span> <span data-ttu-id="8c86d-114">De opslaglocatie voor een vergaderingschat is gebaseerd op de PDL van de organisator van de vergadering.</span><span class="sxs-lookup"><span data-stu-id="8c86d-114">The storage location for a meeting chat is based on the PDL of the meeting organizer.</span></span>

<span data-ttu-id="8c86d-115">Als u de huidige locatie van de gegevens van een gebruiker wilt Teams, maakt u verbinding Teams [PowerShell en](/powershell/module/teams/connect-microsoftteams) voer u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="8c86d-115">To find the current location of a user's Teams data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a><span data-ttu-id="8c86d-116">Kanaalberichten</span><span class="sxs-lookup"><span data-stu-id="8c86d-116">Channel messages</span></span>

<span data-ttu-id="8c86d-117">Elke Microsoft 365 groep heeft een voorkeursgegevenslocatie (PDL) die de geografische locatie aanneert waar gerelateerde gegevens moeten worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="8c86d-117">Each Microsoft 365 group has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="8c86d-118">Teams gebruikt de PDL voor de groep die aan elk team is gekoppeld om te bepalen waar kanaalberichtengegevens voor dat team moeten worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="8c86d-118">Teams uses the PDL for the group associated with each team to determine where to store channel messaging data for that team.</span></span> <span data-ttu-id="8c86d-119">Dit geldt zowel voor privékanalen als voor chatberichten die plaatsvinden binnen een kanaalvergadering.</span><span class="sxs-lookup"><span data-stu-id="8c86d-119">This includes private channels as well as chat that occurs within a channel meeting.</span></span>

<span data-ttu-id="8c86d-120">Wanneer een gebruiker een nieuw team maakt, bepaalt de PDL van die gebruiker welke PDL is toegewezen aan de Microsoft 365 groep.</span><span class="sxs-lookup"><span data-stu-id="8c86d-120">When a user creates a new team, that user's PDL determines what PDL is assigned to the Microsoft 365 group.</span></span> <span data-ttu-id="8c86d-121">De groep PDL bepaalt waar de gegevens van dat team worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="8c86d-121">The group PDL determines where that team's data is stored.</span></span> <span data-ttu-id="8c86d-122">Als de PDL van die gebruiker later wordt gewijzigd, wordt de PDL van de groep niet gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="8c86d-122">If that user's PDL later changes, the group's PDL is not changed.</span></span>

<span data-ttu-id="8c86d-123">Als een beheerder voor bestaande teams de PDL toevoegt of wijzigt voor de Microsoft 365-groep die een team backt, worden de kanaalberichtengegevens van dat team toegevoegd aan een migratiewachtrij die moet worden verplaatst naar de opgegeven geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="8c86d-123">For existing teams, if an administrator adds or modifies the PDL for the Microsoft 365 group that backs a team, that team's channel messaging data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="8c86d-124">Als u de PDL van de Microsoft 365 groep verandert, worden Teams gegevens gemigreerd naar de gekozen locatie.</span><span class="sxs-lookup"><span data-stu-id="8c86d-124">Changing the PDL of the Microsoft 365 group queues the Teams data to migrate to the chosen location.</span></span> <span data-ttu-id="8c86d-125">De site of bestanden die aan de groep zijn gekoppeld, worden hierdoor SharePoint niet automatisch gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="8c86d-125">However, this does not migrate the SharePoint site or files associated with the Group automatically.</span></span> <span data-ttu-id="8c86d-126">U moet de site afzonderlijk verplaatsen door de procedures in Een site verplaatsen SharePoint naar een andere geografische locatie te [volgen.](/microsoft-365/enterprise/move-sharepoint-between-geo-locations)</span><span class="sxs-lookup"><span data-stu-id="8c86d-126">You must move the site separately by following the procedures in [Move a SharePoint site to a different geo location](/microsoft-365/enterprise/move-sharepoint-between-geo-locations).</span></span> <span data-ttu-id="8c86d-127">Zorg ervoor dat u beide stappen uit te voeren om te voorkomen dat Teams gegevens en SharePoint voor één groep op verschillende locaties.</span><span class="sxs-lookup"><span data-stu-id="8c86d-127">Be sure to do both steps to avoid Teams data and SharePoint data for one group in different locations.</span></span>

<span data-ttu-id="8c86d-128">Als u de huidige locatie van de gegevens van een team wilt vinden, maakt u [verbinding met Teams PowerShell](/powershell/module/teams/connect-microsoftteams) en voer u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="8c86d-128">To find the current location of a team's data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a><span data-ttu-id="8c86d-129">Gebruikerservaring</span><span class="sxs-lookup"><span data-stu-id="8c86d-129">User Experience</span></span>

<span data-ttu-id="8c86d-130">Teams Multi-Geo is naadloos voor de eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="8c86d-130">Teams Multi-Geo is seamless to the end user.</span></span> <span data-ttu-id="8c86d-131">Nadat u het PDF-gegevensbestand van een gebruiker of een groep hebt gewijzigd, worden de betreffende gegevens in de wachtrij geplaatst voor de migratie en vindt de migratie automatisch plaats zonder gevolgen voor de gebruiker of de Teams-client, zelfs als deze actief is terwijl de migratie plaatsvindt.</span><span class="sxs-lookup"><span data-stu-id="8c86d-131">Once you change the PDL of a user or a group, the respective data will queue for migration and the migration will occur automatically with no impact to the user or their Teams client even if they are active while the migration occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c86d-132">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8c86d-132">See also</span></span>

[<span data-ttu-id="8c86d-133">Microsoft 365 Multi-Geo tenantconfiguratie</span><span class="sxs-lookup"><span data-stu-id="8c86d-133">Microsoft 365 Multi-Geo tenant configuration</span></span>](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[<span data-ttu-id="8c86d-134">Een multi-geo-omgeving beheren</span><span class="sxs-lookup"><span data-stu-id="8c86d-134">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="8c86d-135">Postvakken Exchange Online in een multi-geo-omgeving beheren</span><span class="sxs-lookup"><span data-stu-id="8c86d-135">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
