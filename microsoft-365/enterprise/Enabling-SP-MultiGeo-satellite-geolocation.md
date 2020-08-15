---
title: Meerdere geografische SharePoint-geografische locaties inschakelen
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
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Dit artikel bevat informatie over globale beheerders en SharePoint-beheerders over het inschakelen van meervoudige SharePoint-geografische locaties voor satellieten.
ms.openlocfilehash: 78f0e925a333dd48a6016bc749459b13e1ac21c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689520"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a><span data-ttu-id="82951-103">Meerdere geografische SharePoint-geografische locaties inschakelen</span><span class="sxs-lookup"><span data-stu-id="82951-103">Enabling SharePoint Multi-Geo in your satellite geo location</span></span>

<span data-ttu-id="82951-104">Dit artikel is bedoeld voor globale beheerders en SharePoint-beheerders die een locatie voor meervoudige geo-satelliet hebben gemaakt, zodat de mogelijkheden van SharePoint in meerdere geografische groepen algemeen beschikbaar zijn op 27 maart 2019 en die niet meerdere gebruikers van **SharePoint hebben** ingeschakeld op hun satelliet locatie (s).</span><span class="sxs-lookup"><span data-stu-id="82951-104">This article is for Global or SharePoint administrators who have created a Multi-Geo satellite location **before** SharePoint Multi-Geo capabilities became generally available on March 27, 2019, and who have not enabled SharePoint Multi-Geo in their satellite geo location(s).</span></span> 

>[!Note]
><span data-ttu-id="82951-105">Als u **na maart 27**een nieuwe geo-locatie hebt toegevoegd, hoeft u deze instructies niet uit te voeren, aangezien de nieuwe geografische locatie al voor OneDrive en SharePoint is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="82951-105">If you have added a new geo location **after March 27th**, you do not need to perform these instructions, as your new geo location will already be enabled for OneDrive and SharePoint Multi-Geo.</span></span>

<span data-ttu-id="82951-106">Met deze instructies kunt u SharePoint op uw locatie inschakelen, zodat de gebruikers van de multi-geo-satelliet gebruikmaken van de mogelijkheden van OneDrive en SharePoint voor meerdere gebruikers in O365.</span><span class="sxs-lookup"><span data-stu-id="82951-106">These instructions will allow you to enable SharePoint in your satellite location, so your Multi-Geo satellite users can take advantage of both OneDrive and SharePoint Multi-Geo capabilities in O365.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="82951-107">Dit vormt één manier van activering.</span><span class="sxs-lookup"><span data-stu-id="82951-107">Please note that this is a one way enablement.</span></span> <span data-ttu-id="82951-108">Wanneer u de SPO-modus hebt ingesteld, kunt u uw Tenant niet terugzetten naar de modus voor meerdere geo-modus zonder dat u een escalatie hoeft te voeren.</span><span class="sxs-lookup"><span data-stu-id="82951-108">Once you set SPO mode, you will not be able to revert your tenant to OneDrive only Multi-Geo mode without an escalation with support.</span></span> 

## <a name="to-set-a-geo-location-into-spo-mode"></a><span data-ttu-id="82951-109">Een geografische locatie instellen in de SPO-modus</span><span class="sxs-lookup"><span data-stu-id="82951-109">To set a geo location into SPO Mode</span></span>

<span data-ttu-id="82951-110">Als u een geografische locatie wilt instellen in de SPO-modus, maakt u verbinding met de geografische locatie die u wilt instellen in de SPO-modus:</span><span class="sxs-lookup"><span data-stu-id="82951-110">To set a geo location into SPO mode, connect to the geo location you want to set in SPO Mode:</span></span>

1.    <span data-ttu-id="82951-111">Uw SharePoint Online Management Shell openen</span><span class="sxs-lookup"><span data-stu-id="82951-111">Open your SharePoint Online Management Shell</span></span> 
2.    <span data-ttu-id="82951-112">Connect-SPOService-URL "https://$tenantGeo-admin.sharepoint.com"-Credential $credential</span><span class="sxs-lookup"><span data-stu-id="82951-112">Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential</span></span>
3.    <span data-ttu-id="82951-113">Set-SPOMultiGeoExperience</span><span class="sxs-lookup"><span data-stu-id="82951-113">Set-SPOMultiGeoExperience</span></span></br></br>
<span data-ttu-id="82951-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="82951-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span></span>
4.    <span data-ttu-id="82951-115">Deze bewerking duurt doorgaans ongeveer een uur, wat betekent dat u diverse publicaties in de service maakt en de Tenant opnieuw stempelt.</span><span class="sxs-lookup"><span data-stu-id="82951-115">This operation usually takes about an hour while we perform various publish backs in the service and re-stamp your tenant.</span></span> <span data-ttu-id="82951-116">Voer na minstens 1 uur een Get-SPOMultiGeoExperience uit.</span><span class="sxs-lookup"><span data-stu-id="82951-116">After at least 1 hour, please perform a Get-SPOMultiGeoExperience.</span></span>  <span data-ttu-id="82951-117">Hiermee wordt aangegeven of deze geo-locatie in de SPO-modus is.</span><span class="sxs-lookup"><span data-stu-id="82951-117">This will show you whether this geo location is in SPO mode.</span></span></br></br>
<span data-ttu-id="82951-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="82951-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span></span>

 
 
 
>[!Note]
><span data-ttu-id="82951-119">Bepaalde caches in de service-update elke 24 uur, dus het is mogelijk dat de satelliet voor een periode van maximaal 24 uur niet af en toe verloopt alsof deze nog steeds in de ODB-modus was.</span><span class="sxs-lookup"><span data-stu-id="82951-119">Certain caches in the service update every 24 hours, so it is possible that for a period of up to 24 hours, your satellite geo may intermittently behave as if it was still in ODB mode.</span></span> <span data-ttu-id="82951-120">Dit veroorzaakt geen technische problemen.</span><span class="sxs-lookup"><span data-stu-id="82951-120">This does not cause any technical issues.</span></span> 
 
<span data-ttu-id="82951-121">Ga naar [aka.MS/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md) voor meer informatie over multi-geo SharePoint.</span><span class="sxs-lookup"><span data-stu-id="82951-121">For additional information regarding SharePoint Multi-Geo, please refer to [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)</span></span>


