---
title: Inhoud van de SharePoint-site beperken tot een geografische locatie
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
description: In dit artikel leest u hoe u SharePoint-sites beperkt tot een opgegeven geografische locatie in een omgeving met meerdere geografische omgevingen.
ms.openlocfilehash: f2a09f177c68d30121c207287e053b2b25405fbc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689014"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a><span data-ttu-id="3cbd3-103">Inhoud van de SharePoint-site beperken tot een geografische locatie</span><span class="sxs-lookup"><span data-stu-id="3cbd3-103">Restrict SharePoint site content to a geo location</span></span>

<span data-ttu-id="3cbd3-104">In sommige gevallen kunt u een site en de bestandsinhoud afdwingen om te zorgen dat de site is gemaakt op de geografische locatie waar de site is gemaakt, door te voorkomen dat de site wordt verplaatst of door te voorkomen dat de inhoud van de site in de cache wordt opgeslagen op een andere geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-104">Under some circumstances you may choose to enforce a site and its file content to remain in the geo location where the site was created, either by preventing the site from being moved or by preventing the caching of the site's file content in another geo location.</span></span>

<span data-ttu-id="3cbd3-105">U kunt dit doen met behulp van de cmdlet [set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) en de **RestrictedToGeo** -parameter.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-105">You can do this by using the [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) cmdlet with the **RestrictedToGeo** parameter.</span></span> <span data-ttu-id="3cbd3-106">Deze parameter heeft een standaardwaarde van NULL, maar u kunt deze wijzigen in een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="3cbd3-106">This parameter has a default value of NULL, but you can change it to one of the following:</span></span>

|<span data-ttu-id="3cbd3-107">Scherp</span><span class="sxs-lookup"><span data-stu-id="3cbd3-107">Restriction</span></span>|<span data-ttu-id="3cbd3-108">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3cbd3-108">Description</span></span>|
|:----------|:----------|
|<span data-ttu-id="3cbd3-109">Geen beperking</span><span class="sxs-lookup"><span data-stu-id="3cbd3-109">NoRestriction</span></span>|<span data-ttu-id="3cbd3-110">De site kan worden verplaatst naar een andere geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-110">The site can be moved to another geo location.</span></span>|
|<span data-ttu-id="3cbd3-111">BlockMoveOnly</span><span class="sxs-lookup"><span data-stu-id="3cbd3-111">BlockMoveOnly</span></span>|<span data-ttu-id="3cbd3-112">Site kan niet worden verplaatst naar een andere geografische locatie, maar site-inhoud kan worden opgeslagen in een andere geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-112">Site cannot be moved to another geo location, but site content can be cached in other geo locations.</span></span>|
|<span data-ttu-id="3cbd3-113">BlockFull</span><span class="sxs-lookup"><span data-stu-id="3cbd3-113">BlockFull</span></span>|<span data-ttu-id="3cbd3-114">Site kan niet worden verplaatst naar een andere geografische locatie en de volledige inhoud van het bestand is niet in de cache opgeslagen in andere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-114">Site cannot be moved to another geo location, and full file content is not cached in other geo locations.</span></span> <span data-ttu-id="3cbd3-115">De naam van een bestand (geoogst van de inhoud), de bestandsnaam en andere eigenschappen van het bestand, kan nog steeds in de cache voor andere geografische locaties worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-115">Files' title (harvested from the content), file name, and other properties of the file can still be cached in other geo-locations.</span></span><br><span data-ttu-id="3cbd3-116">Inhoud die is opgeslagen op de site voordat deze is geconfigureerd voor BlockFull, kan nog steeds in de cache zijn opgeslagen in andere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-116">Content stored in the site before it was configured to BlockFull, may continue to be cached in other geo locations.</span></span>|

<span data-ttu-id="3cbd3-117">Gebruik de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="3cbd3-117">Use the following syntax:</span></span>

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

<span data-ttu-id="3cbd3-118">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="3cbd3-118">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`
