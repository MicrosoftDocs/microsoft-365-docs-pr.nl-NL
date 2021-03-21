---
title: Inhoud van SharePoint-site beperken tot een geografische locatie
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: In dit artikel leert u hoe u SharePoint-sites kunt beperken tot een opgegeven geografische locatie in een multi-geoomgeving.
ms.openlocfilehash: 74255db19b2ecf9b333d33208c63da260b2bd747
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927262"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a><span data-ttu-id="4c143-103">Inhoud van SharePoint-site beperken tot een geografische locatie</span><span class="sxs-lookup"><span data-stu-id="4c143-103">Restrict SharePoint site content to a geo location</span></span>

<span data-ttu-id="4c143-104">In sommige gevallen kunt u ervoor kiezen om een site en de bestandsinhoud ervan af te dwingen op de geografische locatie waar de site is gemaakt, door te voorkomen dat de site wordt verplaatst of door te voorkomen dat de bestandsinhoud van de site op een andere geografische locatie wordt ingeslagen.</span><span class="sxs-lookup"><span data-stu-id="4c143-104">Under some circumstances you may choose to enforce a site and its file content to remain in the geo location where the site was created, either by preventing the site from being moved or by preventing the caching of the site's file content in another geo location.</span></span>

<span data-ttu-id="4c143-105">U kunt dit doen met de [cmdlet Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) met de **parameter RestrictedToGeo.**</span><span class="sxs-lookup"><span data-stu-id="4c143-105">You can do this by using the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) cmdlet with the **RestrictedToGeo** parameter.</span></span> <span data-ttu-id="4c143-106">Deze parameter heeft een standaardwaarde van NULL, maar u kunt deze wijzigen in een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="4c143-106">This parameter has a default value of NULL, but you can change it to one of the following:</span></span>

|<span data-ttu-id="4c143-107">Beperking</span><span class="sxs-lookup"><span data-stu-id="4c143-107">Restriction</span></span>|<span data-ttu-id="4c143-108">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="4c143-108">Description</span></span>|
|:----------|:----------|
|<span data-ttu-id="4c143-109">NoRestriction</span><span class="sxs-lookup"><span data-stu-id="4c143-109">NoRestriction</span></span>|<span data-ttu-id="4c143-110">De site kan worden verplaatst naar een andere geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="4c143-110">The site can be moved to another geo location.</span></span>|
|<span data-ttu-id="4c143-111">BlockMoveOnly</span><span class="sxs-lookup"><span data-stu-id="4c143-111">BlockMoveOnly</span></span>|<span data-ttu-id="4c143-112">Site kan niet worden verplaatst naar een andere geografische locatie, maar site-inhoud kan in de cache worden opgeslagen op andere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="4c143-112">Site cannot be moved to another geo location, but site content can be cached in other geo locations.</span></span>|
|<span data-ttu-id="4c143-113">BlockFull</span><span class="sxs-lookup"><span data-stu-id="4c143-113">BlockFull</span></span>|<span data-ttu-id="4c143-114">Site kan niet worden verplaatst naar een andere geografische locatie en volledige bestandsinhoud wordt niet in de cache op andere geografische locaties opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="4c143-114">Site cannot be moved to another geo location, and full file content is not cached in other geo locations.</span></span> <span data-ttu-id="4c143-115">De titel van bestanden (afkomstig van de inhoud), de bestandsnaam en andere eigenschappen van het bestand kunnen nog steeds in de cache worden opgeslagen op andere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="4c143-115">Files' title (harvested from the content), file name, and other properties of the file can still be cached in other geo-locations.</span></span><br><span data-ttu-id="4c143-116">Inhoud die is opgeslagen op de site voordat deze is geconfigureerd voor BlockFull, blijft mogelijk in de cache op andere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="4c143-116">Content stored in the site before it was configured to BlockFull, may continue to be cached in other geo locations.</span></span>|

<span data-ttu-id="4c143-117">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="4c143-117">Use the following syntax:</span></span>

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

<span data-ttu-id="4c143-118">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="4c143-118">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`