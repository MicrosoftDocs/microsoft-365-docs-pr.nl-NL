---
title: Toegang tot onderwerpen beperken
description: Onderwerpen uitsluiten om te voorkomen dat ze worden gedetecteerd.
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
ms.openlocfilehash: b23d01585d9282132d9e55c74bb22bcdc6ca314a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698868"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a><span data-ttu-id="50368-103">Toegang tot onderwerpen beperken in de onderwerp ervaring</span><span class="sxs-lookup"><span data-stu-id="50368-103">Restrict access to topics in Topic Experiences</span></span>

<span data-ttu-id="50368-104">In het onderwerp kunnen belanghebbenden in uw organisatie er mogelijk voor zorgen dat specifieke onderwerpen niet worden gedetecteerd en blootgesteld aan uw gelicentieerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="50368-104">In Topic Experiences, stakeholders in your organization may want to make sure that specific topics are not discovered and exposed to your licensed users.</span></span> <span data-ttu-id="50368-105">U kunt bijvoorbeeld werken aan een project waarvan u de informatie over nog niet wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="50368-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="50368-106">Hoewel de machtigingen van Office 365 op sites, bestanden en andere bronnen geen ondersteuning bieden voor het weergeven van gevoelige informatie in onderwerpen, hebben gebruikers geen extra beveiligingsmaatregelen om bepaalde onderwerpen van ooit te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="50368-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="50368-107">Hoewel de kennis beheerder de instellingen van het kennis netwerk beheert om te voorkomen dat onderwerpen worden gedetecteerd, moeten kennis beheerders en andere belanghebbenden weten hoe dit is gebeurd, zodat ze hieraan samen kunnen werken.</span><span class="sxs-lookup"><span data-stu-id="50368-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to be know how this is done so that they can work collaboratively on this.</span></span>

> [!Important] 
> <span data-ttu-id="50368-108">In dit artikel leest u hoe u kunt voorkomen dat onderwerpen worden geïdentificeerd via AI of als extra beveiligingsmaatregelen worden weergegeven in uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="50368-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="50368-109">Het is belangrijk te weten dat gebruikers geen toegang hebben tot de machtigingen van Office 365 via de functies in het onderwerp.</span><span class="sxs-lookup"><span data-stu-id="50368-109">It is important to note that in Topic Experiences, users are not allowed to view anything in a topic that they are not allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="50368-110">Zelfs als een gebruiker een onderwerp kan weergeven, zijn bestanden, sites en pagina's waarvoor ze geen Office 365-machtigingen hebben, zichtbaar.</span><span class="sxs-lookup"><span data-stu-id="50368-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="50368-111">Zorg ervoor dat machtigingen voor gevoelige bestanden correct zijn ingesteld als uw primaire beveiligingsmaatregelen.</span><span class="sxs-lookup"><span data-stu-id="50368-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="50368-112">Voorkomen dat onderwerpen worden geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="50368-112">Prevent topics from being identified</span></span>

<span data-ttu-id="50368-113">De Knowledge-beheerder kan de toegang tot bepaalde onderwerpen beperken, zodat deze niet kan worden gevonden bij het indexeren.</span><span class="sxs-lookup"><span data-stu-id="50368-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="50368-114">U kunt dit op twee manieren doen in de Beheerdersinstellingen voor de kennis netwerk in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="50368-114">There are two ways to do this in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="50368-115">[Selecteer SharePoint-sites die u niet wilt opnemen in de detectie van het onderwerp](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): u kunt deze instelling gebruiken om te voorkomen dat bepaalde SharePoint-sites worden verkend voor onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="50368-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="50368-116">[Onderwerpen uitsluiten van naam](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): beheerders kunnen deze instelling gebruiken om te voorkomen dat bepaalde onderwerpen op naam worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="50368-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="50368-117">In de beheerdersinstellingen van de Knowledge netwerk kan een beheerder een lijst met onderwerpen uploaden die moeten worden uitgesloten van een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="50368-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="50368-118">U kunt onderwerpen uitsluiten die exact of gedeeltelijk overeenkomen met de naam van een onderwerp.</span><span class="sxs-lookup"><span data-stu-id="50368-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="50368-119">Voorkomen dat onderwerpen worden weergegeven door bepaalde gebruikers</span><span class="sxs-lookup"><span data-stu-id="50368-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="50368-120">Met kennis beheerders kunt [u ook selecteren wie onderwerpen in uw organisatie kan bekijken](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span><span class="sxs-lookup"><span data-stu-id="50368-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="50368-121">Met deze instelling kunt u selecteren welke gebruikers met een licentie alle onderwerpen kunnen weergeven.</span><span class="sxs-lookup"><span data-stu-id="50368-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="50368-122">U kunt bijvoorbeeld in een testomgeving alleen toestaan dat een kleine groep gebruikers onderwerpen kan weergeven.</span><span class="sxs-lookup"><span data-stu-id="50368-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="50368-123">Het weergeven van onderwerpen verwijderen</span><span class="sxs-lookup"><span data-stu-id="50368-123">Remove topics from being viewed</span></span>

<span data-ttu-id="50368-124">Kennis beheerders kunnen ervoor kiezen om [onderwerpen te verwijderen](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) , zodat gebruikers deze niet meer kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="50368-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="50368-125">Op de pagina **Manage topics** in het **onderwerp Center** kunnen kennis beheerders bepaalde onderwerpen negeren om te voorkomen dat ze worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="50368-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="50368-126">Onderwerpen kunnen worden verwijderd, ongeacht of ze een voorgestelde of bevestigde status hebben.</span><span class="sxs-lookup"><span data-stu-id="50368-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="50368-127">Verwijderde onderwerpen kunnen later indien nodig worden toegevoegd als weergegeven onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="50368-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="50368-128">Zie ook</span><span class="sxs-lookup"><span data-stu-id="50368-128">See also</span></span>



  






