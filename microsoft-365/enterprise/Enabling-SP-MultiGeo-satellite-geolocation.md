---
title: SharePoint multi-geo in de geografische locatie van de satelliet inschakelen
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
description: Dit artikel bevat informatie voor globale of SharePoint beheerders over het inschakelen van SharePoint Multi-Geo in satellietlocatielocaties.
ms.openlocfilehash: 78f0e925a333dd48a6016bc749459b13e1ac21c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689520"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a><span data-ttu-id="c616f-103">SharePoint multi-geo in de geografische locatie van de satelliet inschakelen</span><span class="sxs-lookup"><span data-stu-id="c616f-103">Enabling SharePoint Multi-Geo in your satellite geo location</span></span>

<span data-ttu-id="c616f-104">Dit artikel is bedoeld voor globale of SharePoint-beheerders die een  multi-geo-satellietlocatie hebben gemaakt voordat SharePoint Multi-Geo-mogelijkheden algemeen beschikbaar werden op 27 maart 2019 en die SharePoint Multi-Geo niet hebben ingeschakeld in hun satellietlocatie(en).</span><span class="sxs-lookup"><span data-stu-id="c616f-104">This article is for Global or SharePoint administrators who have created a Multi-Geo satellite location **before** SharePoint Multi-Geo capabilities became generally available on March 27, 2019, and who have not enabled SharePoint Multi-Geo in their satellite geo location(s).</span></span> 

>[!Note]
><span data-ttu-id="c616f-105">Als u na **27** maart een nieuwe geografische locatie hebt toegevoegd, hoeft u deze instructies niet uit te voeren, omdat uw nieuwe geografische locatie al is ingeschakeld voor OneDrive en SharePoint Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="c616f-105">If you have added a new geo location **after March 27th**, you do not need to perform these instructions, as your new geo location will already be enabled for OneDrive and SharePoint Multi-Geo.</span></span>

<span data-ttu-id="c616f-106">Met deze instructies kunt u SharePoint inschakelen op uw satellietlocatie, zodat uw multi-geo satellietgebruikers kunnen profiteren van zowel OneDrive als SharePoint Multi-Geo mogelijkheden in O365.</span><span class="sxs-lookup"><span data-stu-id="c616f-106">These instructions will allow you to enable SharePoint in your satellite location, so your Multi-Geo satellite users can take advantage of both OneDrive and SharePoint Multi-Geo capabilities in O365.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="c616f-107">Houd er rekening mee dat dit een enkele manier van inschakelen is.</span><span class="sxs-lookup"><span data-stu-id="c616f-107">Please note that this is a one way enablement.</span></span> <span data-ttu-id="c616f-108">Nadat u de SPO-modus hebt ingesteld, kunt u uw tenant niet meer terugdraaien OneDrive alleen multi-geomodus zonder escalatie met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="c616f-108">Once you set SPO mode, you will not be able to revert your tenant to OneDrive only Multi-Geo mode without an escalation with support.</span></span> 

## <a name="to-set-a-geo-location-into-spo-mode"></a><span data-ttu-id="c616f-109">Een geografische locatie instellen in de SPO-modus</span><span class="sxs-lookup"><span data-stu-id="c616f-109">To set a geo location into SPO Mode</span></span>

<span data-ttu-id="c616f-110">Als u een geografische locatie wilt instellen in de SPO-modus, maakt u verbinding met de geografische locatie die u wilt instellen in de SPO-modus:</span><span class="sxs-lookup"><span data-stu-id="c616f-110">To set a geo location into SPO mode, connect to the geo location you want to set in SPO Mode:</span></span>

1.    <span data-ttu-id="c616f-111">Open uw SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="c616f-111">Open your SharePoint Online Management Shell</span></span> 
2.    <span data-ttu-id="c616f-112">Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential</span><span class="sxs-lookup"><span data-stu-id="c616f-112">Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential</span></span>
3.    <span data-ttu-id="c616f-113">Set-SPOMultiGeoExperience</span><span class="sxs-lookup"><span data-stu-id="c616f-113">Set-SPOMultiGeoExperience</span></span></br></br>
<span data-ttu-id="c616f-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="c616f-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span></span>
4.    <span data-ttu-id="c616f-115">Deze bewerking duurt meestal ongeveer een uur terwijl we verschillende publiceren backs in de service uitvoeren en uw tenant opnieuw stempelen.</span><span class="sxs-lookup"><span data-stu-id="c616f-115">This operation usually takes about an hour while we perform various publish backs in the service and re-stamp your tenant.</span></span> <span data-ttu-id="c616f-116">Voer na ten minste 1 uur een Get-SPOMultiGeoExperience uit.</span><span class="sxs-lookup"><span data-stu-id="c616f-116">After at least 1 hour, please perform a Get-SPOMultiGeoExperience.</span></span>  <span data-ttu-id="c616f-117">Op deze manier kunt u zien of deze geografische locatie zich in de SPO-modus bevindt.</span><span class="sxs-lookup"><span data-stu-id="c616f-117">This will show you whether this geo location is in SPO mode.</span></span></br></br>
<span data-ttu-id="c616f-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="c616f-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span></span>

 
 
 
>[!Note]
><span data-ttu-id="c616f-119">Bepaalde caches in de service-update worden elke 24 uur bijgewerkt, zodat het mogelijk is dat uw satelliet-geo zich voor een periode van maximaal 24 uur af en toe gedraagt alsof het zich nog in de ODB-modus heeft gedragen.</span><span class="sxs-lookup"><span data-stu-id="c616f-119">Certain caches in the service update every 24 hours, so it is possible that for a period of up to 24 hours, your satellite geo may intermittently behave as if it was still in ODB mode.</span></span> <span data-ttu-id="c616f-120">Dit veroorzaakt geen technische problemen.</span><span class="sxs-lookup"><span data-stu-id="c616f-120">This does not cause any technical issues.</span></span> 
 
<span data-ttu-id="c616f-121">Voor meer informatie over SharePoint Multi-Geo, raadpleegt u [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="c616f-121">For additional information regarding SharePoint Multi-Geo, please refer to [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)</span></span>


