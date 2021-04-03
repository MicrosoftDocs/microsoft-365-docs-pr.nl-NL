---
title: Toegang tot onderwerpen beperken in Microsoft Viva-onderwerpen
description: Onderwerpen uitsluiten om te voorkomen dat ze worden ontdekt.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: d6dfb2f7f432a40c5b6e96a9437f50ba47e23387
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500883"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a><span data-ttu-id="2b1a8-103">Toegang tot onderwerpen beperken in Microsoft Viva-onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2b1a8-103">Restrict access to topics in Microsoft Viva Topics</span></span>

<span data-ttu-id="2b1a8-104">In Microsoft Viva willen belanghebbenden in uw organisatie er mogelijk voor zorgen dat specifieke onderwerpen niet worden gevonden en worden blootgesteld aan uw gelicentieerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-104">In Microsoft Viva, stakeholders in your organization may want to make sure that specific topics aren't discovered and exposed to your licensed users.</span></span> <span data-ttu-id="2b1a8-105">U werkt bijvoorbeeld aan een project waar u nog geen informatie over wilt onthullen.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="2b1a8-106">Hoewel gebruikers met Office 365-machtigingen voor sites, bestanden en andere bronnen kunnen voorkomen dat gebruikers van onderwerpervaringen gevoelige informatie in onderwerpen kunnen bekijken, zijn er aanvullende beveiligingen om te voorkomen dat specifieke onderwerpen ooit worden ontdekt.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="2b1a8-107">Hoewel kennisbeheerders de instellingen beheren om te voorkomen dat onderwerpen worden ontdekt, moeten kennisbeheerders en andere belanghebbenden weten hoe dit wordt gedaan, zodat ze kunnen samenwerken.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-107">While knowledge admins control the settings to prevent topics from being discovered, knowledge managers and other stakeholders need to know how it is done so that they can work collaboratively.</span></span>

> [!Important] 
> <span data-ttu-id="2b1a8-108">In dit artikel worden manieren beschreven om te voorkomen dat onderwerpen worden geïdentificeerd via AI of worden bekeken in uw omgeving als extra beveiligingsbeveiliging.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="2b1a8-109">Het is belangrijk om te weten dat gebruikers in Viva-onderwerpen niets mogen bekijken in een onderwerp dat ze niet mogen openen via Office 365-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-109">It is important to note that in Viva Topics, users aren't allowed to view anything in a topic that they aren't allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="2b1a8-110">Zelfs als een gebruiker een onderwerp kan bekijken, zijn de bestanden, sites en pagina's die ze niet kunnen weergeven niet zichtbaar voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="2b1a8-111">Zorg ervoor dat machtigingen voor gevoelige bestanden correct zijn ingesteld, moet uw primaire beveiligingsbeveiliging zijn.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="2b1a8-112">Voorkomen dat onderwerpen worden geïdentificeerd</span><span class="sxs-lookup"><span data-stu-id="2b1a8-112">Prevent topics from being identified</span></span>

<span data-ttu-id="2b1a8-113">Kennisbeheerder kan de toegang tot specifieke onderwerpen beperken door te voorkomen dat deze worden gevonden in de eerste indexering.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="2b1a8-114">U kunt deze taak op twee manieren uitvoeren in de instellingen van de Viva-onderwerpenbeheerder in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-114">There are two ways to do this task in the Viva Topics admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="2b1a8-115">[Selecteer SharePoint-sites om uit te](./topic-experiences-discovery.md#select-sharepoint-topic-sources)sluiten van onderwerpdetectie: U kunt deze instelling gebruiken om te voorkomen dat specifieke SharePoint-sites worden verkend voor onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-115">[Select SharePoint sites to exclude from topic discovery](./topic-experiences-discovery.md#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="2b1a8-116">[Onderwerpen uitsluiten op naam:](./topic-experiences-discovery.md#exclude-topics-by-name)beheerders kunnen deze instelling gebruiken om te voorkomen dat specifieke onderwerpen bij naam worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-116">[Exclude topics by name](./topic-experiences-discovery.md#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="2b1a8-117">In de instellingen van de Viva-onderwerpenbeheerder kan een beheerder een lijst met onderwerpen uploaden die moeten worden uitgesloten in een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-117">In the Viva Topics admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="2b1a8-118">U kunt onderwerpen uitsluiten met exacte of gedeeltelijke overeenkomsten van een onderwerpnaam.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="2b1a8-119">Voorkomen dat onderwerpen worden bekeken door specifieke gebruikers</span><span class="sxs-lookup"><span data-stu-id="2b1a8-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="2b1a8-120">Kennisbeheerders kunnen ook [selecteren wie onderwerpen in uw organisatie kan bekijken.](./topic-experiences-knowledge-rules.md)</span><span class="sxs-lookup"><span data-stu-id="2b1a8-120">Knowledge admins can also [select who can view topics in your organization](./topic-experiences-knowledge-rules.md).</span></span> <span data-ttu-id="2b1a8-121">Met deze instelling kunt u selecteren welke gebruikers met een licentie alle onderwerpen kunnen bekijken.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="2b1a8-122">In een testomgeving kunt u bijvoorbeeld alleen toestaan dat een kleine groep gebruikers onderwerpen kan bekijken.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="2b1a8-123">Onderwerpen verwijderen uit weergave</span><span class="sxs-lookup"><span data-stu-id="2b1a8-123">Remove topics from being viewed</span></span>

<span data-ttu-id="2b1a8-124">Kennisbeheerders kunnen ervoor kiezen [om onderwerpen te verwijderen,](./manage-topics.md) zodat gebruikers ze niet meer kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-124">Knowledge managers can choose to [remove topics](./manage-topics.md) so that users can no longer see them.</span></span> <span data-ttu-id="2b1a8-125">Op de **pagina Onderwerpen beheren** in het **onderwerpcentrum** kunnen kennisbeheerders ervoor kiezen specifieke onderwerpen te weigeren om te voorkomen dat ze worden bekeken.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="2b1a8-126">Onderwerpen kunnen worden verwijderd, ongeacht of ze een voorgestelde of bevestigd status hebben.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="2b1a8-127">Verwijderde onderwerpen kunnen later worden toegevoegd als eerbare onderwerpen indien nodig.</span><span class="sxs-lookup"><span data-stu-id="2b1a8-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="2b1a8-128">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2b1a8-128">See also</span></span>



