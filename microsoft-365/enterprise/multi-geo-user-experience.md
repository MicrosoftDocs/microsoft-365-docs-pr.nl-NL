---
title: Gebruikerservaring in een multi-geo-omgeving
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Meer informatie over de SharePoint, OneDrive en Exchange gebruikerservaring in een multi-geo-omgeving voor Microsoft 365.
ms.openlocfilehash: 4e752581f4ca692f9fecc5019f8e34543ebf7067
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362376"
---
# <a name="user-experience-in-a-multi-geo-environment"></a><span data-ttu-id="44a48-103">Gebruikerservaring in een multi-geo-omgeving</span><span class="sxs-lookup"><span data-stu-id="44a48-103">User experience in a multi-geo environment</span></span>

<span data-ttu-id="44a48-104">Dit is wat uw gebruikers zien in een OneDrive Multi-Geo configuratie:</span><span class="sxs-lookup"><span data-stu-id="44a48-104">Here's what your users will see in a OneDrive Multi-Geo configuration:</span></span>

## <a name="exchange-mailbox"></a><span data-ttu-id="44a48-105">Exchange postvak</span><span class="sxs-lookup"><span data-stu-id="44a48-105">Exchange mailbox</span></span>

<span data-ttu-id="44a48-106">Het postvak van Exchange gebruiker is ingericht op de gewenste gegevenslocatie en wordt automatisch verplaatst als de PDL-locatie wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="44a48-106">A user's Exchange mailbox is provisioned to their preferred data location, and is automatically relocated if their PDL changes.</span></span> <span data-ttu-id="44a48-107">Gebruikers kunnen Outlook en webversie van Outlook gebruiken zonder dat de gebruikerservaring in een multi-geoomgeving verandert.</span><span class="sxs-lookup"><span data-stu-id="44a48-107">Users can use Outlook and Outlook on the web normally with no change in user experience in a multi-geo environment.</span></span>

## <a name="hub-sites"></a><span data-ttu-id="44a48-108">Hubsites</span><span class="sxs-lookup"><span data-stu-id="44a48-108">Hub sites</span></span>

<span data-ttu-id="44a48-109">SharePoint Hubsites verbeteren de detectie en betrokkenheid met inhoud voor werknemers, terwijl er een volledige en consistente weergave wordt van projecten, afdelingen of regio's.</span><span class="sxs-lookup"><span data-stu-id="44a48-109">SharePoint Hub sites enhances the discovery and engagement with content for employees, while creating a complete and consistent representation of projects, departments or regions.</span></span> <span data-ttu-id="44a48-110">In een multi-geo-omgeving kunnen sites van satellietlocaties eenvoudig worden gekoppeld aan een hubsite, ongeacht de geografische locatie van de hubsite.</span><span class="sxs-lookup"><span data-stu-id="44a48-110">In a multi-geo environment, sites from satellite locations can easily be associated with a hub site regardless the hub site's geo location.</span></span> <span data-ttu-id="44a48-111">Gebruikers kunnen zoeken en resultaten binnen de hub krijgen via één zoekervaring, ongeacht de geografische locatie van de sites.</span><span class="sxs-lookup"><span data-stu-id="44a48-111">Users can search and get results across the hub through a single search experience, regardless of the geo location of the sites.</span></span>

## <a name="microsoft-365-app-launcher"></a><span data-ttu-id="44a48-112">Microsoft 365 start-app</span><span class="sxs-lookup"><span data-stu-id="44a48-112">Microsoft 365 app launcher</span></span>

<span data-ttu-id="44a48-113">Het start start- en start start-start start-element voor apps is multi-geo aware en stuurt elke tegel naar de juiste geografische locatie van de werkbelasting.</span><span class="sxs-lookup"><span data-stu-id="44a48-113">The app launcher is multi-geo aware and will direct each tile to the appropriate geo location of the workload.</span></span> <span data-ttu-id="44a48-114">De SharePoint en OneDrive-tegels geven de gebruiker de locatie aan die overeenkomt met de geolocatie van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="44a48-114">The SharePoint and OneDrive tiles will point the user to the location corresponding to the user's provisioned geo location.</span></span> <span data-ttu-id="44a48-115">Dit betekent dat de gebruiker een OneDrive op de centrale locatie heeft, dat de tegel SharePoint deze naar SP Home op de centrale locatie zal wijzen, maar dat de groepssite wordt ingericht op de locatie die overeenkomt met hun PDL.</span><span class="sxs-lookup"><span data-stu-id="44a48-115">This means that is the user has a OneDrive in the central location, their SharePoint tile will point them to SP Home in the central location but their group site will be provisioned in the location corresponding to their PDL.</span></span> 

## <a name="office-applications"></a><span data-ttu-id="44a48-116">Office-toepassingen</span><span class="sxs-lookup"><span data-stu-id="44a48-116">Office applications</span></span>

<span data-ttu-id="44a48-117">Office toepassingen zoals Word, Excel en PowerPoint worden automatisch de juiste OneDrive geolocatie voor elke gebruiker gedetecteerd wanneer ze zich aanmelden.</span><span class="sxs-lookup"><span data-stu-id="44a48-117">Office applications such as Word, Excel, and PowerPoint will automatically detect the correct OneDrive geo-location for each user when they log in.</span></span> <span data-ttu-id="44a48-118">Gebruikers hoeven de geospecifieke URL niet in te voeren voor hun OneDrive of SharePoint sites.</span><span class="sxs-lookup"><span data-stu-id="44a48-118">Users do not need to enter the geo-specific URL for their OneDrive or SharePoint sites.</span></span>

## <a name="onedrive-sync-app"></a><span data-ttu-id="44a48-119">OneDrive-synchronisatie app</span><span class="sxs-lookup"><span data-stu-id="44a48-119">OneDrive sync app</span></span>

<span data-ttu-id="44a48-120">De OneDrive-synchronisatie app (versie 17.3.6943.0625 en hoger) detecteert automatisch de juiste OneDrive geolocatie voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="44a48-120">The OneDrive sync app (version 17.3.6943.0625 and later) will automatically detect the correct OneDrive geo location for the user.</span></span> <span data-ttu-id="44a48-121">Ondersteuning voor synchronisatie-apps omvat de mogelijkheid om sites op basis van groepen te synchroniseren, ongeacht hun geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="44a48-121">Sync app support includes the ability to sync groups-based sites regardless of their geo location.</span></span> <span data-ttu-id="44a48-122">Houd er rekening mee Groove de synchronisatieclient niet wordt ondersteund voor multi-geo.</span><span class="sxs-lookup"><span data-stu-id="44a48-122">Note that the Groove sync client is not supported for multi-geo.</span></span> 

## <a name="onedrive-location"></a><span data-ttu-id="44a48-123">OneDrive locatie</span><span class="sxs-lookup"><span data-stu-id="44a48-123">OneDrive location</span></span>

<span data-ttu-id="44a48-124">Gebruikers hebben hun OneDrive ingericht op hun gewenste gegevenslocatie.</span><span class="sxs-lookup"><span data-stu-id="44a48-124">Users will have their OneDrive provisioned in their preferred data location.</span></span> <span data-ttu-id="44a48-125">Als een gebruiker naar een OneDrive-URL navigeert die een onjuiste geografische locatie bevat (zoals een bladwijzer van een vorige geografische locatie), worden deze automatisch omgeleid naar de OneDrive op de juiste geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="44a48-125">If a user navigates to a OneDrive URL that contains an incorrect geo location (such as a bookmark from a previous geo location), they are automatically redirected to the OneDrive in the appropriate geo location.</span></span>

## <a name="onedrive-ios-and-android"></a><span data-ttu-id="44a48-126">OneDrive iOS en Android</span><span class="sxs-lookup"><span data-stu-id="44a48-126">OneDrive iOS and Android</span></span> 

<span data-ttu-id="44a48-127">In OneDrive mobiele iOS- en Android-apps ziet u uw OneDrive bestanden en bestanden die met u worden gedeeld, ongeacht hun geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="44a48-127">The OneDrive iOS and Android mobile apps will show you your OneDrive files and files shared with you regardless of their geo location.</span></span> <span data-ttu-id="44a48-128">Zoeken vanuit de OneDrive mobiele apps geeft relevante resultaten weer van alle geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="44a48-128">Search from the OneDrive mobile apps will show relevant results from all geo locations.</span></span> <span data-ttu-id="44a48-129">Download de nieuwste versie van deze apps.</span><span class="sxs-lookup"><span data-stu-id="44a48-129">Please download the latest version of these apps.</span></span>

<span data-ttu-id="44a48-130">Zie Gebruik [OneDrive voor iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) [en Gebruik OneDrive voor Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="44a48-130">See Use [OneDrive on iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) and [Use OneDrive for Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) for more information.</span></span>

## <a name="onedrive-mobile-client"></a><span data-ttu-id="44a48-131">OneDrive Mobiele client</span><span class="sxs-lookup"><span data-stu-id="44a48-131">OneDrive Mobile Client</span></span> 

<span data-ttu-id="44a48-132">De OneDrive Mobile Client is multi-geo aware en geeft relevante inhoud en resultaten van alle geografische locaties weer.</span><span class="sxs-lookup"><span data-stu-id="44a48-132">The OneDrive Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="search"></a><span data-ttu-id="44a48-133">Zoeken</span><span class="sxs-lookup"><span data-stu-id="44a48-133">Search</span></span>

<span data-ttu-id="44a48-134">Elke geografische locatie heeft een eigen zoekindex en zoekcentrum.</span><span class="sxs-lookup"><span data-stu-id="44a48-134">Each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="44a48-135">Wanneer een gebruiker zoekt, wordt de query naar alle geografische locaties verzonden en worden de geretourneerde resultaten samengevoegd en vervolgens gerangschikt, zodat de gebruiker geïntegreerde resultaten krijgt.</span><span class="sxs-lookup"><span data-stu-id="44a48-135">When a user searches, the query is sent to all the geo locations, and the returned results are merged and then ranked so the user gets unified results.</span></span> <span data-ttu-id="44a48-136">Gebruikers krijgen resultaten van alle geografische locaties, ongeacht hun eigen geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="44a48-136">Users get results from all geo locations regardless of their own geo location.</span></span> <span data-ttu-id="44a48-137">Zie [Zoeken naar OneDrive Multi-Geo](configure-search-for-multi-geo.md) details configureren.</span><span class="sxs-lookup"><span data-stu-id="44a48-137">See [Configure Search for OneDrive Multi-Geo](configure-search-for-multi-geo.md) for specifics.</span></span>

<span data-ttu-id="44a48-138">De volgende zoek clients worden ondersteund:</span><span class="sxs-lookup"><span data-stu-id="44a48-138">The following search clients are supported:</span></span>

-   <span data-ttu-id="44a48-139">OneDrive</span><span class="sxs-lookup"><span data-stu-id="44a48-139">OneDrive</span></span>

-   <span data-ttu-id="44a48-140">Delve</span><span class="sxs-lookup"><span data-stu-id="44a48-140">Delve</span></span>

-   <span data-ttu-id="44a48-141">SharePoint Start</span><span class="sxs-lookup"><span data-stu-id="44a48-141">SharePoint Home</span></span>

-   <span data-ttu-id="44a48-142">Het zoekcentrum</span><span class="sxs-lookup"><span data-stu-id="44a48-142">The Search Center</span></span>

-   <span data-ttu-id="44a48-143">Aangepaste zoektoepassingen die gebruikmaken van de SharePoint Search API</span><span class="sxs-lookup"><span data-stu-id="44a48-143">Custom search applications that use the SharePoint Search API</span></span>

## <a name="sharepoint-home"></a><span data-ttu-id="44a48-144">SharePoint Start</span><span class="sxs-lookup"><span data-stu-id="44a48-144">SharePoint Home</span></span> 

<span data-ttu-id="44a48-145">In SharePoint Multi-Geo uw SharePoint wordt gehost op de locatie waar de gebruiker zich bevindt, zoals bepaald door de OneDrive locatie.</span><span class="sxs-lookup"><span data-stu-id="44a48-145">In SharePoint Multi-Geo your SharePoint home is hosted in the location where the user resides as determined by their OneDrive location.</span></span> <span data-ttu-id="44a48-146">Bijvoorbeeld: als de gebruiker zijn of haar OneDrive op een Europese satellietlocatie heeft gehost, wordt zijn of haar SharePoint vanuit Europa weergegeven.</span><span class="sxs-lookup"><span data-stu-id="44a48-146">For example: if the user has their OneDrive hosted in an European satellite location, their SharePoint Home will be rendered from Europe.</span></span> <span data-ttu-id="44a48-147">SharePoint home bevat alle inhoud die relevant is voor de gebruiker, ongeacht de geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="44a48-147">SharePoint home includes all content relevant to the user regardless of its geo location.</span></span> 

<span data-ttu-id="44a48-148">**Gevolgde sites, nieuws van sites, recente sites, veelgebruikte sites en voorgestelde sites**</span><span class="sxs-lookup"><span data-stu-id="44a48-148">**Followed Sites, News from Sites, Recent Sites, Frequent Sites, and Suggested sites**</span></span>

<span data-ttu-id="44a48-149">Al deze onderdelen worden voor de gebruiker gebruikt, ongeacht de geografische locatie waar de inhoud wordt gehost, zolang de gebruiker machtigingen heeft voor deze inhoud.</span><span class="sxs-lookup"><span data-stu-id="44a48-149">All of these components will show up for the user regardless of the geo location where the content is hosted, so long as the user has permissions to said content.</span></span> 

<span data-ttu-id="44a48-150">**Functieskoppelingen**</span><span class="sxs-lookup"><span data-stu-id="44a48-150">**Features Links**</span></span>

<span data-ttu-id="44a48-151">Beheerders kunnen aanbevolen koppelingen configureren in SharePoint home, naar eigen goed gebruik voor elke geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="44a48-151">Admins may configure Featured links in SharePoint home as appropriate to each geo location.</span></span> <span data-ttu-id="44a48-152">Hierdoor kan de beheerder in de SP Home voor elke regio de koppelingen gebruiken die geschikt zijn voor gebruikers in de regio.</span><span class="sxs-lookup"><span data-stu-id="44a48-152">This allows the admin to feature in the SP Home for each region the links that are appropriate for users in the region.</span></span> 

## <a name="sharepoint-mobile-client"></a><span data-ttu-id="44a48-153">SharePoint Mobiele client</span><span class="sxs-lookup"><span data-stu-id="44a48-153">SharePoint Mobile Client</span></span> 

<span data-ttu-id="44a48-154">De SharePoint Mobile Client is multi-geo aware en geeft relevante inhoud en resultaten weer van alle geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="44a48-154">The SharePoint Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="sharing"></a><span data-ttu-id="44a48-155">Delen</span><span class="sxs-lookup"><span data-stu-id="44a48-155">Sharing</span></span>

<span data-ttu-id="44a48-156">De gebruikers picker-ervaring toont alle gebruikers, ongeacht hun geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="44a48-156">The People Picker experience shows all users regardless of their geo location.</span></span> <span data-ttu-id="44a48-157">Op deze manier kan een gebruiker delen met een andere gebruiker in dezelfde geo of op een andere geografische locatie van uw tenant.</span><span class="sxs-lookup"><span data-stu-id="44a48-157">This allows a user to share with another user in their same geo or in any other of your tenant's geo locations.</span></span> <span data-ttu-id="44a48-158">Inhoud van verschillende geografische locaties  wordt in de weergave Gedeeld met mij in de OneDrive van de gebruiker weergeven en kan worden gebruikt met een enkele Sign-On-ervaring, ongeacht de geografische locatie waarin deze wordt gehost.</span><span class="sxs-lookup"><span data-stu-id="44a48-158">Content from different geo locations will show up in the **Shared with Me** view in the user's OneDrive and can be accessed with Single Sign-On experience regardless of which geo location it is hosted in.</span></span>

## <a name="teams-experience"></a><span data-ttu-id="44a48-159">Teams Ervaring</span><span class="sxs-lookup"><span data-stu-id="44a48-159">Teams Experience</span></span>

<span data-ttu-id="44a48-160">Teams is een multi-geo-service.</span><span class="sxs-lookup"><span data-stu-id="44a48-160">Teams is a multi-geo service.</span></span> <span data-ttu-id="44a48-161">OneDrive bestanden en onlangs bekeken bestanden worden weergegeven, ongeacht de geografische locatie van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="44a48-161">OneDrive files and recently viewed files are shown regardless of the user's geo location.</span></span> <span data-ttu-id="44a48-162">@ vermeldingen werken met gebruikers van alle geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="44a48-162">@ mentions work with users from all geo-locations.</span></span>

## <a name="user-profiles"></a><span data-ttu-id="44a48-163">Gebruikersprofielen</span><span class="sxs-lookup"><span data-stu-id="44a48-163">User profiles</span></span>

<span data-ttu-id="44a48-164">Gebruikersprofielgegevens worden beheerst op de geografische locatie van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="44a48-164">User profile information is mastered in the user's geo location.</span></span> <span data-ttu-id="44a48-165">Wanneer u een gebruiker selecteert, wordt u doorgestuurd naar de juiste geografische locatie voor de gebruiker, waar u de volledige profielgegevens ziet.</span><span class="sxs-lookup"><span data-stu-id="44a48-165">When selecting a user, you will be directed to the appropriate geo location for the user, where you will see their full profile details.</span></span>

<span data-ttu-id="44a48-166">Als Delve is uitgeschakeld, ziet u de klassieke profielervaring in SharePoint, die niet multi-geo-aware is.</span><span class="sxs-lookup"><span data-stu-id="44a48-166">If Delve is turned off, you will see the classic profile experience in SharePoint, which is not multi-geo aware.</span></span>


