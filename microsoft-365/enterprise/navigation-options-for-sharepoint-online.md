---
title: Navigatieopties voor SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: In dit artikel worden de Navigatieopties beschreven die beschikbaar zijn voor SharePoint-sites met SharePoint Online.
ms.openlocfilehash: 86cefc60a26687835fd6a88de7f249143811de4f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695712"
---
# <a name="navigation-options-for-sharepoint-online"></a><span data-ttu-id="39b6a-103">Navigatieopties voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="39b6a-103">Navigation options for SharePoint Online</span></span>

<span data-ttu-id="39b6a-104">In dit artikel worden de Navigatieopties beschreven die beschikbaar zijn voor SharePoint-sites met SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="39b6a-104">This article describes navigation options sites with SharePoint Publishing enabled in SharePoint Online.</span></span> <span data-ttu-id="39b6a-105">De keuze en configuratie van de navigatie zijn sterk van invloed op de prestaties en schaalbaarheid van sites in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="39b6a-105">The choice and configuration of navigation significantly impacts the performance and scalability of sites in SharePoint Online.</span></span> <span data-ttu-id="39b6a-106">De sjabloon voor de publicerende site van SharePoint mag alleen worden gebruikt als dit vereist is voor een gecentraliseerde Portal en de publicatiefunctie mag alleen worden ingeschakeld op specifieke sites en alleen wanneer de prestaties van invloed kunnen zijn op de prestaties die onjuist worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="39b6a-106">The SharePoint Publishing site template should only be used if required for a centralized portal and the publishing feature should only be enabled on specific sites and only when absolutely required as it can impact performance when used incorrectly.</span></span>

>[!NOTE]
><span data-ttu-id="39b6a-107">Dit artikel is niet van toepassing op uw site als u moderne Navigatieopties voor SharePoint gebruikt, zoals het menu Mega wind, Cascading Navigation of hub Navigation.</span><span class="sxs-lookup"><span data-stu-id="39b6a-107">If you're using modern SharePoint navigation options like mega menu, cascading navigation, or hub navigation, this article does not apply to your site.</span></span> <span data-ttu-id="39b6a-108">Moderne SharePoint-site architecturen profiteren van een meer afvlakkige sitehiërarchie en een hub-en-spoke-model.</span><span class="sxs-lookup"><span data-stu-id="39b6a-108">Modern SharePoint site architectures leverage a more flattened site hierarchy and a hub-and-spoke model.</span></span> <span data-ttu-id="39b6a-109">U kunt zo veel scenario's bereiken waarbij de publicatiefunctie van SharePoint niet is vereist.</span><span class="sxs-lookup"><span data-stu-id="39b6a-109">This allows many scenarios to be achieved that do NOT require use of the SharePoint Publishing feature.</span></span>

## <a name="overview-of-navigation-options"></a><span data-ttu-id="39b6a-110">Overzicht van Navigatieopties</span><span class="sxs-lookup"><span data-stu-id="39b6a-110">Overview of navigation options</span></span>

<span data-ttu-id="39b6a-111">Configuratie van navigatie provider kan een aanzienlijke invloed hebben op de prestaties van de hele site, en zorgvuldige overweging voor het kiezen van een navigatie provider en-configuratie die effectiever schaalt voor de vereisten van een SharePoint-site.</span><span class="sxs-lookup"><span data-stu-id="39b6a-111">Navigation provider configuration can significantly impact performance for the entire site, and careful consideration must be taken to pick a navigation provider and configuration that scales effectively for the requirements of a SharePoint site.</span></span> <span data-ttu-id="39b6a-112">Er zijn twee kant-en-klare navigatie providers en aangepaste navigatie-implementaties.</span><span class="sxs-lookup"><span data-stu-id="39b6a-112">There are two out-of-the-box navigation providers, as well as custom navigation implementations.</span></span>

<span data-ttu-id="39b6a-113">De eerste optie, [**structurele navigatie**](#using-structural-navigation-in-sharepoint-online), is de aanbevolen optie voor navigatie in SharePoint Online voor klassieke SharePoint-sites, **Als u structurele navigatie in cache voor uw site inschakelt**.</span><span class="sxs-lookup"><span data-stu-id="39b6a-113">The first option, [**Structural navigation**](#using-structural-navigation-in-sharepoint-online), is the recommended navigation option in SharePoint Online for classic Sharepoint sites, **if you turn on structural navigation caching for your site**.</span></span> <span data-ttu-id="39b6a-114">Deze navigatie provider toont de navigatie-items onder de huidige site en optioneel de huidige site en de onderliggende items.</span><span class="sxs-lookup"><span data-stu-id="39b6a-114">This navigation provider displays the navigation items below the current site, and optionally the current site and its siblings.</span></span> <span data-ttu-id="39b6a-115">Het biedt extra mogelijkheden, zoals beveiligingsbeperkingen en inventarisatie van site structuren.</span><span class="sxs-lookup"><span data-stu-id="39b6a-115">It provides additional capabilities such as security trimming and site structure enumeration.</span></span> <span data-ttu-id="39b6a-116">Als caching is uitgeschakeld, heeft dit een negatieve invloed op de prestaties en schaalbaarheid, en kan de beperking gelden.</span><span class="sxs-lookup"><span data-stu-id="39b6a-116">If caching is disabled, this will negatively impact performance and scalability, and may be subject to throttling.</span></span>

<span data-ttu-id="39b6a-117">Met de tweede optie, [**beheerde metagegevens (metagegevens)**](#using-managed-navigation-and-metadata-in-sharepoint-online), stelt u navigatie-items met behulp van een Termenset beheerde metagegevens.</span><span class="sxs-lookup"><span data-stu-id="39b6a-117">The second option, [**Managed (Metadata) navigation**](#using-managed-navigation-and-metadata-in-sharepoint-online), represents navigation items using a Managed Metadata term set.</span></span> <span data-ttu-id="39b6a-118">U wordt aangeraden beveiligingsbeperkingen uit te schakelen, tenzij nodig.</span><span class="sxs-lookup"><span data-stu-id="39b6a-118">We recommend that security trimming be disabled unless required.</span></span> <span data-ttu-id="39b6a-119">Beveiligingsbeperking is ingeschakeld als een veilig-standaardinstelling voor deze navigatie provider. voor veel sites is de overhead van beveiligingsbeperkingen niet vereist omdat navigatie-elementen vaak consistent zijn voor alle gebruikers van de site.</span><span class="sxs-lookup"><span data-stu-id="39b6a-119">Security trimming is enabled as a secure-by-default setting for this navigation provider; however, many sites do not require the overhead of security trimming since navigation elements often are consistent for all users of the site.</span></span> <span data-ttu-id="39b6a-120">Met de aanbevolen configuratie voor het uitschakelen van beveiligingsbeperkingen, moet u de sitestructuur niet met een inventarisatie van de sitestructuur en is deze met een acceptabele gevolgen voor de prestaties zeer uitgebreid.</span><span class="sxs-lookup"><span data-stu-id="39b6a-120">With the recommended configuration to disable security trimming, this navigation provider does not require enumerating site structure and is highly scalable with acceptable performance impact.</span></span>

<span data-ttu-id="39b6a-121">Naast de kant-en-klare navigatie providers hebben veel klanten een alternatieve aangepaste navigatie-implementatie geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="39b6a-121">In addition to the out-of-the-box navigation providers, many customers have successfully implemented alternative custom navigation implementations.</span></span> <span data-ttu-id="39b6a-122">Zie [scripts op basis van de zoekopdracht aan de clientzijde](#using-search-driven-client-side-scripting) van dit artikel.</span><span class="sxs-lookup"><span data-stu-id="39b6a-122">See [Search-driven client-side scripting](#using-search-driven-client-side-scripting) in this article.</span></span>
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a><span data-ttu-id="39b6a-123">Voor-en nadelen van Navigatieopties voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="39b6a-123">Pros and Cons of SharePoint Online navigation options</span></span>

<span data-ttu-id="39b6a-124">De volgende tabel bevat een overzicht van de voor-en nadelen van elke optie.</span><span class="sxs-lookup"><span data-stu-id="39b6a-124">The following table summarizes the pros and cons of each option.</span></span>

|<span data-ttu-id="39b6a-125">Structurele navigatie</span><span class="sxs-lookup"><span data-stu-id="39b6a-125">Structural navigation</span></span>  |<span data-ttu-id="39b6a-126">Beheerde navigatie</span><span class="sxs-lookup"><span data-stu-id="39b6a-126">Managed navigation</span></span>  |<span data-ttu-id="39b6a-127">Navigatie met zoekopdrachten</span><span class="sxs-lookup"><span data-stu-id="39b6a-127">Search-driven navigation</span></span>  |<span data-ttu-id="39b6a-128">Aangepaste operator voor navigatie</span><span class="sxs-lookup"><span data-stu-id="39b6a-128">Custom-navigation provider</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="39b6a-129">-Professionals</span><span class="sxs-lookup"><span data-stu-id="39b6a-129">Pros:</span></span><br/><br/><span data-ttu-id="39b6a-130">Gemakkelijk te onderhouden</span><span class="sxs-lookup"><span data-stu-id="39b6a-130">Easy to maintain</span></span><br/><span data-ttu-id="39b6a-131">Beveiligingsbeperking</span><span class="sxs-lookup"><span data-stu-id="39b6a-131">Security trimmed</span></span><br/><span data-ttu-id="39b6a-132">Automatisch updates binnen 24 uur wanneer inhoud wordt gewijzigd</span><span class="sxs-lookup"><span data-stu-id="39b6a-132">Automatically updates within 24 hours when content is changed</span></span><br/>     |<span data-ttu-id="39b6a-133">-Professionals</span><span class="sxs-lookup"><span data-stu-id="39b6a-133">Pros:</span></span><br/><br/><span data-ttu-id="39b6a-134">Gemakkelijk te onderhouden</span><span class="sxs-lookup"><span data-stu-id="39b6a-134">Easy to maintain</span></span><br/>|<span data-ttu-id="39b6a-135">-Professionals</span><span class="sxs-lookup"><span data-stu-id="39b6a-135">Pros:</span></span><br/><br/><span data-ttu-id="39b6a-136">Beveiligingsbeperking</span><span class="sxs-lookup"><span data-stu-id="39b6a-136">Security trimmed</span></span><br/><span data-ttu-id="39b6a-137">Wordt automatisch bijgewerkt wanneer sites worden toegevoegd</span><span class="sxs-lookup"><span data-stu-id="39b6a-137">Automatically updates as sites are added</span></span><br/><span data-ttu-id="39b6a-138">Snel laadtijd en navigatiestructuur in de lokale cache</span><span class="sxs-lookup"><span data-stu-id="39b6a-138">Fast loading time and locally cached navigation structure</span></span><br/>|<span data-ttu-id="39b6a-139">-Professionals</span><span class="sxs-lookup"><span data-stu-id="39b6a-139">Pros:</span></span><br/><br/><span data-ttu-id="39b6a-140">Uitgebreide optie voor beschikbare opties</span><span class="sxs-lookup"><span data-stu-id="39b6a-140">Wider choice of options available</span></span><br/><span data-ttu-id="39b6a-141">Snel laden wanneer cache correct wordt gebruikt</span><span class="sxs-lookup"><span data-stu-id="39b6a-141">Fast loading when caching is used correctly</span></span><br/><span data-ttu-id="39b6a-142">Een groot aantal opties werken goed met een reactie pagina-ontwerp</span><span class="sxs-lookup"><span data-stu-id="39b6a-142">Many options work well with responsive page design</span></span><br/>|
|<span data-ttu-id="39b6a-143">Nadelen</span><span class="sxs-lookup"><span data-stu-id="39b6a-143">Cons:</span></span><br/><br/><span data-ttu-id="39b6a-144">**Beïnvloedt de prestaties als het opslaan van de cache is uitgeschakeld**</span><span class="sxs-lookup"><span data-stu-id="39b6a-144">**Impacts performance if caching is disabled**</span></span><br/><span data-ttu-id="39b6a-145">Onderworpen aan beperking</span><span class="sxs-lookup"><span data-stu-id="39b6a-145">Subject to throttling</span></span><br/>|<span data-ttu-id="39b6a-146">Nadelen</span><span class="sxs-lookup"><span data-stu-id="39b6a-146">Cons:</span></span><br/><br/><span data-ttu-id="39b6a-147">Niet automatisch bijgewerkt overeenkomstig de sitestructuur</span><span class="sxs-lookup"><span data-stu-id="39b6a-147">Not automatically updated to reflect site structure</span></span><br/><span data-ttu-id="39b6a-148">**Beïnvloedt de prestaties als beveiligingsbeperkingen zijn ingeschakeld** of als de navigatiestructuur complex is</span><span class="sxs-lookup"><span data-stu-id="39b6a-148">**Impacts performance if security trimming is enabled** or when navigation structure is complex</span></span><br/>|<span data-ttu-id="39b6a-149">Nadelen</span><span class="sxs-lookup"><span data-stu-id="39b6a-149">Cons:</span></span><br/><br/><span data-ttu-id="39b6a-150">Geen mogelijkheid om sites eenvoudig te rangschikken</span><span class="sxs-lookup"><span data-stu-id="39b6a-150">No ability to easily order sites</span></span><br/><span data-ttu-id="39b6a-151">Aanpassing van de basispagina vereist (technische vaardigheden vereist)</span><span class="sxs-lookup"><span data-stu-id="39b6a-151">Requires customization of the master page (technical skills required)</span></span><br/>|<span data-ttu-id="39b6a-152">Nadelen</span><span class="sxs-lookup"><span data-stu-id="39b6a-152">Cons:</span></span><br/><br/><span data-ttu-id="39b6a-153">Aangepaste ontwikkeling is vereist</span><span class="sxs-lookup"><span data-stu-id="39b6a-153">Custom development is required</span></span><br/><span data-ttu-id="39b6a-154">Extern gegevensbron/cache opslaan is vereist, zoals Azure</span><span class="sxs-lookup"><span data-stu-id="39b6a-154">External data source / cache stored is needed e.g. Azure</span></span><br/>|

<span data-ttu-id="39b6a-155">De meest geschikte optie voor uw site is afhankelijk van de vereisten van uw site en over de technische mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="39b6a-155">The most appropriate option for your site will depend on your site requirements and on your technical capability.</span></span> <span data-ttu-id="39b6a-156">Als u een eenvoudig te configureren navigatie provider wilt die automatisch wordt bijgewerkt wanneer de inhoud wordt gewijzigd, kunt u het beste de structurele navigatie met de optie [voor het opslaan van een cache](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) .</span><span class="sxs-lookup"><span data-stu-id="39b6a-156">If you want an easy-to-configure navigation provider that automatically updates when content is changed, then structural navigation [with caching enabled](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) is a good option.</span></span>

>[!NOTE]
><span data-ttu-id="39b6a-157">Hetzelfde beginsel toepassen als moderne SharePoint-sites door de structuur van de hele site te vereenvoudigen tot een flatter, een niet-hiërarchische structuur verbetert de prestaties en vergemakkelijkt de overstap naar moderne SharePoint-sites.</span><span class="sxs-lookup"><span data-stu-id="39b6a-157">Applying the same principle as modern SharePoint sites by simplifying the overall site structure to a flatter, non-hierarchical structure improves performance and simplifies moving to modern SharePoint sites.</span></span> <span data-ttu-id="39b6a-158">Wat betekent dit? in plaats van dat u één siteverzameling met honderden sites (subwebs) hebt, is het een betere manier om veel siteverzamelingen met een groot aantal subsites (subwebs) te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="39b6a-158">What this means is that instead of having a single site collection with hundreds of sites (subwebs), a better approach is to have many site collections with very few subsites (subwebs).</span></span>

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a><span data-ttu-id="39b6a-159">Navigatieprestaties analyseren in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="39b6a-159">Analyzing navigation performance in SharePoint Online</span></span>

<span data-ttu-id="39b6a-160">Het [hulpprogramma pagina diagnose voor SharePoint](https://aka.ms/perftool) is een browser extensie voor browsers van Microsoft Edge en Chrome waarmee de pagina's van SharePoint Online voor de moderne Portal en de klassieke publicatiesite worden geanalyseerd.</span><span class="sxs-lookup"><span data-stu-id="39b6a-160">The [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) is a browser extension for Microsoft Edge and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="39b6a-161">Dit hulpprogramma werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.</span><span class="sxs-lookup"><span data-stu-id="39b6a-161">This tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="39b6a-162">Met het hulpprogramma wordt een rapport gegenereerd voor elke geanalyseerde pagina op basis van de manier waarop de pagina wordt uitgevoerd met een vooraf gedefinieerde set regels en gedetailleerde informatie wordt weergegeven wanneer resultaten van een test buiten de waarde van de basislijn vallen.</span><span class="sxs-lookup"><span data-stu-id="39b6a-162">The tool generates a report for each analyzed page showing how the page performs against a pre-defined set of rules and displays detailed information when results for a test fall outside the baseline value.</span></span> <span data-ttu-id="39b6a-163">Beheerders van SharePoint Online kunnen het hulpprogramma gebruiken voor het oplossen van prestatieproblemen om ervoor te zorgen dat nieuwe pagina's worden geoptimaliseerd voordat ze worden gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="39b6a-163">SharePoint Online administrators and designers can use the tool to troubleshoot performance issues to ensure that new pages are optimized prior to publishing.</span></span>

<span data-ttu-id="39b6a-164">**SPRequestDuration** met name is de tijd die het voor de verwerking van de pagina in SharePoint duurt.</span><span class="sxs-lookup"><span data-stu-id="39b6a-164">**SPRequestDuration** in particular is the time it takes for SharePoint to process the page.</span></span> <span data-ttu-id="39b6a-165">Dikke navigatie (zoals pagina's in navigatie), complexe site hiërarchieën en andere configuratie-en topologie opties kunnen alle grote bijdrage leveren aan langere duur.</span><span class="sxs-lookup"><span data-stu-id="39b6a-165">Heavy navigation (like including pages in navigation), complex site hierarchies, and other configuration and topology options can all dramatically contribute to longer durations.</span></span>

## <a name="using-structural-navigation-in-sharepoint-online"></a><span data-ttu-id="39b6a-166">Structurele navigatie in SharePoint Online gebruiken</span><span class="sxs-lookup"><span data-stu-id="39b6a-166">Using structural navigation in SharePoint Online</span></span>

<span data-ttu-id="39b6a-167">Dit is de kant-en-klare navigatie die standaard wordt gebruikt voor de meest eenvoudige oplossing.</span><span class="sxs-lookup"><span data-stu-id="39b6a-167">This is the out-of-the-box navigation used by default and is the most straightforward solution.</span></span> <span data-ttu-id="39b6a-168">Het is niet verplicht om wijzigingen aan te brengen en een niet-technische gebruiker hoeft ook snel items toe te voegen, items te verbergen en de navigatie op de pagina instellingen te beheren.</span><span class="sxs-lookup"><span data-stu-id="39b6a-168">It does not require any customization and a non-technical user can also easily add items, hide items, and manage the navigation from the settings page.</span></span> <span data-ttu-id="39b6a-169">U wordt aangeraden [cache in te schakelen](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), anders is er een duurder voor de prestaties.</span><span class="sxs-lookup"><span data-stu-id="39b6a-169">We recommend [enabling caching](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), otherwise there is an expensive performance trade-off.</span></span>

### <a name="how-to-implement-structural-navigation-caching"></a><span data-ttu-id="39b6a-170">Structurele navigatie in cache implementeren</span><span class="sxs-lookup"><span data-stu-id="39b6a-170">How to implement structural navigation caching</span></span>

<span data-ttu-id="39b6a-171">In **Site Settings**  >  **Look and Feel**  >  **Navigation**het uiterlijk van site-instellingen kunt u controleren of structurele navigatie is geselecteerd voor globale navigatie of de huidige navigatie.</span><span class="sxs-lookup"><span data-stu-id="39b6a-171">Under **Site Settings** > **Look and Feel** > **Navigation**, you can validate if structural navigation is selected for either global navigation or current navigation.</span></span> <span data-ttu-id="39b6a-172">Het selecteren van **pagina's weergeven** heeft een negatieve impact op de prestaties.</span><span class="sxs-lookup"><span data-stu-id="39b6a-172">Selecting **Show pages** will have negative impact on performance.</span></span>

![Structurele navigatie met subsites weergeven geselecteerd](../media/SPONavOptionsStructuredShowSubsites.png)

<span data-ttu-id="39b6a-174">U kunt in-en uitschakelen op siteverzamelingsniveau en op siteniveau, en is standaard ingeschakeld voor beide.</span><span class="sxs-lookup"><span data-stu-id="39b6a-174">Caching can be enabled or disabled at the site collection level and at the site level, and is enabled for both by default.</span></span> <span data-ttu-id="39b6a-175">Als u het niveau van de siteverzameling wilt inschakelen, schakelt u onder **site-instellingen**siteverzameling  >  **beheren**  >  **Site Collection Navigation**de optie **cache inschakelen**in.</span><span class="sxs-lookup"><span data-stu-id="39b6a-175">To enable at the site collection level, under **Site Settings** > **Site Collection Administration** > **Site Collection Navigation**, check the box for **Enable caching**.</span></span>

![Cache inschakelen op siteniveau](../media/structural-nav/structural-nav-caching-site-coll.png)

<span data-ttu-id="39b6a-177">Als u het siteniveau wilt inschakelen, **Site Settings**schakelt u onder  >  **Navigatie**van site-instellingen het selectievakje **cache inschakelen**in.</span><span class="sxs-lookup"><span data-stu-id="39b6a-177">To enable at the site level, under **Site Settings** > **Navigation**, check the box for **Enable caching**.</span></span>

![Cache inschakelen op siteniveau](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a><span data-ttu-id="39b6a-179">Beheerde navigatie en metagegevens gebruiken in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="39b6a-179">Using managed navigation and metadata in SharePoint Online</span></span>

<span data-ttu-id="39b6a-180">Beheerde navigatie is een andere gebruiksklare optie die u kunt gebruiken om dezelfde functionaliteit als de structurele navigatie opnieuw te maken.</span><span class="sxs-lookup"><span data-stu-id="39b6a-180">Managed navigation is another out-of-the-box option that you can use to recreate most of the same functionality as structural navigation.</span></span> <span data-ttu-id="39b6a-181">Beheerde metagegevens kunnen worden geconfigureerd om beveiligingsbeperkingen in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="39b6a-181">Managed metadata can be configured to have security trimming enabled or disabled.</span></span> <span data-ttu-id="39b6a-182">Wanneer de configuratie is uitgeschakeld met beveiligingsbeperkingen uitgeschakeld, is beheerde navigatie tamelijk efficiënt omdat alle navigatiekoppelingen met een constant aantal Server oproepen worden geladen.</span><span class="sxs-lookup"><span data-stu-id="39b6a-182">When configured with security trimming disabled, managed navigation is fairly efficient as it loads all the navigation links with a constant number of server calls.</span></span> <span data-ttu-id="39b6a-183">Door beveiligingsbeperkingen in te schakelen, worden echter wel enkele prestatievoordelen van beheerde navigatie genegeerd.</span><span class="sxs-lookup"><span data-stu-id="39b6a-183">Enabling security trimming, however, negates some of the performance advantages of managed navigation.</span></span>

<span data-ttu-id="39b6a-184">Als u beveiligingsbeperkingen moet inschakelen, is het raadzaam om het volgende te doen:</span><span class="sxs-lookup"><span data-stu-id="39b6a-184">If you need to enable security trimming, we recommend that you:</span></span>

- <span data-ttu-id="39b6a-185">Alle beschrijvende URL-koppelingen naar eenvoudige koppelingen bijwerken</span><span class="sxs-lookup"><span data-stu-id="39b6a-185">Update all friendly URL links to simple links</span></span>
- <span data-ttu-id="39b6a-186">Vereiste beveiligingsbeperkingen toevoegen knooppunten als beschrijvende Url's</span><span class="sxs-lookup"><span data-stu-id="39b6a-186">Add required security trimming nodes as friendly URLs</span></span>
- <span data-ttu-id="39b6a-187">Beperk het aantal navigatie-items tot maximaal 100 en mag niet groter zijn dan 3 niveaus.</span><span class="sxs-lookup"><span data-stu-id="39b6a-187">Limit the number of navigation items to no more than 100 and no more than 3 levels deep</span></span>

<span data-ttu-id="39b6a-188">Voor veel sites is geen beveiliging van beveiligingsbeperkingen vereist, aangezien de navigatiestructuur vaak consistent is voor alle gebruikers van de site.</span><span class="sxs-lookup"><span data-stu-id="39b6a-188">Many sites do not require security trimming, as the navigation structure is often consistent for all users of the site.</span></span> <span data-ttu-id="39b6a-189">Als beveiligingsbeperkingen zijn uitgeschakeld en een koppeling wordt toegevoegd aan een navigatie die niet door alle gebruikers is geopend, wordt de koppeling weergegeven maar wordt er een bericht weergegeven dat toegang is geweigerd.</span><span class="sxs-lookup"><span data-stu-id="39b6a-189">If security trimming is disabled and a link is added to navigation that not all users have access to, the link will still show but will lead to an access denied message.</span></span> <span data-ttu-id="39b6a-190">Er is geen risico dat onopzettelijk toegang heeft tot de inhoud.</span><span class="sxs-lookup"><span data-stu-id="39b6a-190">There is no risk of inadvertent access to the content.</span></span>

### <a name="how-to-implement-managed-navigation-and-the-results"></a><span data-ttu-id="39b6a-191">Het implementeren van beheerde navigatie en de resultaten</span><span class="sxs-lookup"><span data-stu-id="39b6a-191">How to implement managed navigation and the results</span></span>

<span data-ttu-id="39b6a-192">Er zijn verschillende artikelen over docs.microsoft.com over de details van beheerde navigatie.</span><span class="sxs-lookup"><span data-stu-id="39b6a-192">There are several articles on docs.microsoft.com about the details of managed navigation.</span></span> <span data-ttu-id="39b6a-193">Zie [overzicht van beheerde navigatie in SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="39b6a-193">For example, see [Overview of managed navigation in SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation).</span></span>

<span data-ttu-id="39b6a-194">Als u beheerde navigatie wilt implementeren, stelt u termen in met Url's die overeenkomen met de navigatiestructuur van de site.</span><span class="sxs-lookup"><span data-stu-id="39b6a-194">In order to implement managed navigation, you set up terms with URLs corresponding to the navigation structure of the site.</span></span> <span data-ttu-id="39b6a-195">Beheerde navigatie kan zelfs handmatig worden gecurator om structurele navigatie in veel gevallen te vervangen.</span><span class="sxs-lookup"><span data-stu-id="39b6a-195">Managed navigation can even be manually curated to replace structural navigation in many cases.</span></span> <span data-ttu-id="39b6a-196">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="39b6a-196">For example:</span></span>

![SharePoint Online-sitestructuur](../media/SPONavOptionsListOfSites.png)<span data-ttu-id="39b6a-198">)</span><span class="sxs-lookup"><span data-stu-id="39b6a-198">)</span></span>

## <a name="using-search-driven-client-side-scripting"></a><span data-ttu-id="39b6a-199">Het gebruik van scripts met zoekopdrachten aan de clientzijde</span><span class="sxs-lookup"><span data-stu-id="39b6a-199">Using Search-driven client-side scripting</span></span>

<span data-ttu-id="39b6a-200">Eén veelgebruikte klasse van aangepaste navigatie-implementaties omvat een client weergave van de client weergave die een lokale cache van navigatieknooppunten opslaat.</span><span class="sxs-lookup"><span data-stu-id="39b6a-200">One common class of custom navigation implementations embraces client-rendered design patterns that store a local cache of navigation nodes.</span></span>

<span data-ttu-id="39b6a-201">Deze navigatie providers bieden een aantal belangrijke voordelen:</span><span class="sxs-lookup"><span data-stu-id="39b6a-201">These navigation providers have a couple of key advantages:</span></span>

- <span data-ttu-id="39b6a-202">Algemeen werken ze prima met beantwoordings pagina ontwerpen.</span><span class="sxs-lookup"><span data-stu-id="39b6a-202">They generally work well with responsive page designs.</span></span>
- <span data-ttu-id="39b6a-203">Ze zijn zeer schaalbaar en presteert, omdat ze zonder resourcekosten kunnen weergeven (en de achtergrond na een time-out vernieuwen).</span><span class="sxs-lookup"><span data-stu-id="39b6a-203">They are extremely scalable and performant because they can render with no resource cost (and refresh in the background after a timeout).</span></span>
- <span data-ttu-id="39b6a-204">Met behulp van de volgende navigatie providers kunt u navigatie gegevens ophalen met behulp van verschillende strategieën, variërend van eenvoudige statische configuraties tot diverse dynamische gegevensproviders.</span><span class="sxs-lookup"><span data-stu-id="39b6a-204">These navigation providers can retrieve navigation data using various strategies, ranging from simple static configurations to various dynamic data providers.</span></span>

<span data-ttu-id="39b6a-205">Een voorbeeld van een gegevensprovider is het gebruik van een **zoekopdracht met een zoekopdracht**, wat flexibiliteit biedt voor het inkorten van navigatieknooppunten en de verwerking van beveiligingsbeperkingen.</span><span class="sxs-lookup"><span data-stu-id="39b6a-205">An example of a data provider is to use a **Search-driven navigation**, which allows flexibility for enumerating navigation nodes and handling security trimming efficiently.</span></span>

<span data-ttu-id="39b6a-206">Er zijn andere populaire opties om **aangepaste navigatie providers**te maken.</span><span class="sxs-lookup"><span data-stu-id="39b6a-206">There are other popular options to build **Custom navigation providers**.</span></span> <span data-ttu-id="39b6a-207">Controleer de [Navigatie oplossingen voor SharePoint Online-portals](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) voor meer informatie over het maken van een aangepaste navigatie provider.</span><span class="sxs-lookup"><span data-stu-id="39b6a-207">Please review [Navigation solutions for SharePoint Online portals](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) for further guidance on building a Custom navigation provider.</span></span>

<span data-ttu-id="39b6a-208">Met de functie zoeken kunt u de indexen gebruiken die op de achtergrond zijn opgebouwd via continue crawl.</span><span class="sxs-lookup"><span data-stu-id="39b6a-208">Using search you can leverage the indexes that are built up in the background using continuous crawl.</span></span> <span data-ttu-id="39b6a-209">De zoekresultaten worden vanuit de zoekindex getrokken en de resultaten worden ingekort.</span><span class="sxs-lookup"><span data-stu-id="39b6a-209">The search results are pulled from the search index and the results are security-trimmed.</span></span> <span data-ttu-id="39b6a-210">Dit is doorgaans sneller dan de kant-en-klare navigatie providers wanneer beveiligingsbeperkingen vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="39b6a-210">This is generally faster than out-of-the-box navigation providers when security trimming is required.</span></span> <span data-ttu-id="39b6a-211">Met de zoekfunctie van structurele navigatie, met name als u een complexe sitestructuur hebt, wordt de laadtijd van de pagina aanzienlijk sneller weergegeven.</span><span class="sxs-lookup"><span data-stu-id="39b6a-211">Using search for structural navigation, especially if you have a complex site structure, will speed up page loading time considerably.</span></span> <span data-ttu-id="39b6a-212">Het voordeel van dit object via beheerde navigatie is dat u profiteert van beveiligingsbeperkingen.</span><span class="sxs-lookup"><span data-stu-id="39b6a-212">The main advantage of this over managed navigation is that you benefit from security trimming.</span></span>

<span data-ttu-id="39b6a-213">Voor deze manier moet u een aangepaste basispagina maken en de niet-geminimaliseerde navigatie code vervangen door aangepaste HTML.</span><span class="sxs-lookup"><span data-stu-id="39b6a-213">This approach involves creating a custom master page and replacing the out-of-the-box navigation code with custom HTML.</span></span> <span data-ttu-id="39b6a-214">Voer de volgende stappen uit in het volgende voorbeeld om de navigatie code in het bestand te vervangen `seattle.html` .</span><span class="sxs-lookup"><span data-stu-id="39b6a-214">Follow this procedure outlined in the following example to replace the navigation code in the file `seattle.html`.</span></span> <span data-ttu-id="39b6a-215">In dit voorbeeld opent u het `seattle.html` bestand en vervangt u het hele element door een `id="DeltaTopNavigation"` aangepaste HTML-code.</span><span class="sxs-lookup"><span data-stu-id="39b6a-215">In this example, you will open the `seattle.html` file and replace the whole element `id="DeltaTopNavigation"` with custom HTML code.</span></span>

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a><span data-ttu-id="39b6a-216">Voorbeeld: de niet-gegroepeerde navigatie code op een basispagina vervangen</span><span class="sxs-lookup"><span data-stu-id="39b6a-216">Example: Replace the out-of-the-box navigation code in a master page</span></span>

1. <span data-ttu-id="39b6a-217">Ga naar de pagina Site-instellingen.</span><span class="sxs-lookup"><span data-stu-id="39b6a-217">Navigate to the Site Settings page.</span></span>
2. <span data-ttu-id="39b6a-218">Open de galerie met basispagina's door op **basispagina's**te klikken.</span><span class="sxs-lookup"><span data-stu-id="39b6a-218">Open the master page gallery by clicking **Master Pages**.</span></span>
3. <span data-ttu-id="39b6a-219">Van hieruit kunt u door de bibliotheek navigeren en het bestand downloaden `seattle.master` .</span><span class="sxs-lookup"><span data-stu-id="39b6a-219">From here you can navigate through the library and download the file `seattle.master`.</span></span>
4. <span data-ttu-id="39b6a-220">Bewerk de code met een teksteditor en verwijder het codeblok dat in de volgende schermafbeelding wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="39b6a-220">Edit the code using a text editor and delete the code block in the following screen shot.</span></span><br/>![Het weergegeven codeblok verwijderen](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. <span data-ttu-id="39b6a-222">Verwijder de code tussen de `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` labels en en vervang deze door het volgende fragment:</span><span class="sxs-lookup"><span data-stu-id="39b6a-222">Remove the code between the `<SharePoint:AjaxDelta id="DeltaTopNavigation">` and `<\SharePoint:AjaxDelta>` tags and replace it with the following snippet:</span></span><br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. <span data-ttu-id="39b6a-223">Vervang de URL in de afbeeldings ankerpunt die aan het begin wordt geladen, met een koppeling naar een laadafbeelding in de siteverzameling.</span><span class="sxs-lookup"><span data-stu-id="39b6a-223">Replace the URL in the loading image anchor tag at the beginning, with a link to a loading image in your site collection.</span></span> <span data-ttu-id="39b6a-224">Nadat u de wijzigingen hebt aangebracht, wijzigt u de naam van het bestand en uploadt u het naar de galerie met basispagina's.</span><span class="sxs-lookup"><span data-stu-id="39b6a-224">After you have made the changes, rename the file and then upload it to the master page gallery.</span></span> <span data-ttu-id="39b6a-225">Hiermee wordt een nieuw modelbestand gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="39b6a-225">This generates a new .master file.</span></span><br/>
7. <span data-ttu-id="39b6a-226">Dit HTML-bestand bevat de basis markeringen die worden gevuld met de zoekresultaten die worden opgehaald uit een JavaScript-code.</span><span class="sxs-lookup"><span data-stu-id="39b6a-226">This HTML is the basic markup that will be populated by the search results returned from JavaScript code.</span></span> <span data-ttu-id="39b6a-227">U moet de code bewerken voor het wijzigen van de waarde voor de ' var root = ' siteverzameling-URL ' zoals wordt aangetoond in het volgende fragment:</span><span class="sxs-lookup"><span data-stu-id="39b6a-227">You will need to edit the code to change the value for var root = "site collection URL" as demonstrated in the following snippet:</span></span><br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. <span data-ttu-id="39b6a-228">De resultaten worden toegewezen aan de matrix Self. nodes en er wordt een hiërarchie opgebouwd op basis van de objecten die linq.js de uitvoer toewijzen aan een matrix Self. Hierarchy.</span><span class="sxs-lookup"><span data-stu-id="39b6a-228">The results are assigned to the self.nodes array and a hierarchy is built out of the objects using linq.js assigning the output to an array self.hierarchy.</span></span> <span data-ttu-id="39b6a-229">Deze matrix is het object dat is gekoppeld aan de HTML.</span><span class="sxs-lookup"><span data-stu-id="39b6a-229">This array is the object that is bound to the HTML.</span></span> <span data-ttu-id="39b6a-230">Dit gebeurt in de toggleView ()-functie door het selfservice object te geven aan de functie ko. applyBinding ().</span><span class="sxs-lookup"><span data-stu-id="39b6a-230">This is done in the toggleView() function by passing the self object to the ko.applyBinding() function.</span></span><br/><span data-ttu-id="39b6a-231">Hierdoor wordt de hiërarchie matrix gebonden aan de volgende HTML:</span><span class="sxs-lookup"><span data-stu-id="39b6a-231">This then causes the hierarchy array to be bound to the following HTML:</span></span><br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

<span data-ttu-id="39b6a-232">De gebeurtenis-handlers voor `mouseenter` en `mouseexit` worden toegevoegd aan de navigatie op het hoogste niveau voor het verwerken van de vervolgkeuzelijsten van subsites die in de functie worden uitgevoerd `addEventsToElements()` .</span><span class="sxs-lookup"><span data-stu-id="39b6a-232">The event handlers for `mouseenter` and `mouseexit` are added to the top-level navigation to handle the subsite drop-down menus which is done in the `addEventsToElements()` function.</span></span>

<span data-ttu-id="39b6a-233">In het voorbeeld van complexe navigatie wordt een nieuwe pagina geladen zonder de lokale cache weergegeven de tijd die aan de server is besteed en die een vergelijkbaar resultaat oplevert als de beheerde navigatie aanpak.</span><span class="sxs-lookup"><span data-stu-id="39b6a-233">In our complex navigation example, a fresh page load without the local caching shows the time spent on the server has been cut down from the benchmark structural navigation to get a similar result as the managed navigation approach.</span></span>

### <a name="about-the-javascript-file"></a><span data-ttu-id="39b6a-234">Info over het JavaScript-bestand...</span><span class="sxs-lookup"><span data-stu-id="39b6a-234">About the JavaScript file...</span></span>

>[!NOTE]
><span data-ttu-id="39b6a-235">Als u aangepaste JavaScript gebruikt, moet u ervoor zorgen dat openbare CDN is ingeschakeld en dat het bestand zich op een CDN-locatie bevindt.</span><span class="sxs-lookup"><span data-stu-id="39b6a-235">If using custom JavaScript, ensure that public CDN is enabled and the file is in a CDN location.</span></span>

<span data-ttu-id="39b6a-236">Het volledige JavaScript-bestand is als volgt:</span><span class="sxs-lookup"><span data-stu-id="39b6a-236">The entire JavaScript file is as follows:</span></span>

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

<span data-ttu-id="39b6a-237">Als u de code wilt samenvatten die hierboven wordt weergegeven, wordt de functie `jQuery $(document).ready` `viewModel object` gemaakt en wordt de `loadNavigationNodes()` functie van dat object aangeroepen.</span><span class="sxs-lookup"><span data-stu-id="39b6a-237">To summarize the code shown above in the `jQuery $(document).ready` function there is a `viewModel object` created and then the `loadNavigationNodes()` function on that object is called.</span></span> <span data-ttu-id="39b6a-238">Met deze functie wordt de eerder gemaakte navigatiehiërarchie geladen die is opgeslagen in de lokale HTML5-opslag van de client van de client of wordt de functie aangeroepen `queryRemoteInterface()` .</span><span class="sxs-lookup"><span data-stu-id="39b6a-238">This function either loads the previously built navigation hierarchy stored in the HTML5 local storage of the client browser or it calls the function `queryRemoteInterface()`.</span></span>

<span data-ttu-id="39b6a-239">`QueryRemoteInterface()` maakt een aanvraag met de `getRequest()` functie met de queryparameter eerder gedefinieerd in het script en retourneert vervolgens gegevens van de server.</span><span class="sxs-lookup"><span data-stu-id="39b6a-239">`QueryRemoteInterface()` builds a request using the `getRequest()` function with the query parameter defined earlier in the script and then returns data from the server.</span></span> <span data-ttu-id="39b6a-240">Deze gegevens zijn in feite een array van alle sites in de siteverzameling die wordt voorgesteld als objecten voor gegevensoverdracht met diverse eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="39b6a-240">This data is essentially an array of all the sites in the site collection represented as data transfer objects with various properties.</span></span>

<span data-ttu-id="39b6a-241">Deze gegevens worden vervolgens geparseerd naar de eerder gedefinieerde `SPO.Models.NavigationNode` objecten die `Knockout.js` de waarden voor het gebruik van de gegevens in de opgegeven HTML moeten worden gebruikt voor het maken van waarneembare eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="39b6a-241">This data is then parsed into the previously defined `SPO.Models.NavigationNode` objects which use `Knockout.js` to create observable properties for use by data binding the values into the HTML that we defined earlier.</span></span>

<span data-ttu-id="39b6a-242">De objecten worden vervolgens opgenomen in een resultatenmatrix.</span><span class="sxs-lookup"><span data-stu-id="39b6a-242">The objects are then put into a results array.</span></span> <span data-ttu-id="39b6a-243">Deze matrix wordt in JSON geparseerd met behulp van afdek kracht en opgeslagen in de lokale browser opslag voor betere prestaties op toekomstige pagina's.</span><span class="sxs-lookup"><span data-stu-id="39b6a-243">This array is parsed into JSON using Knockout and stored in the local browser storage for improved performance on future page loads.</span></span>

### <a name="benefits-of-this-approach"></a><span data-ttu-id="39b6a-244">Voordelen van deze aanpak</span><span class="sxs-lookup"><span data-stu-id="39b6a-244">Benefits of this approach</span></span>

<span data-ttu-id="39b6a-245">Een belangrijk voordeel van [deze methode](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) is dat met behulp van de lokale HTML5-opslag de navigatie voor de gebruiker lokaal wordt opgeslagen wanneer deze de pagina een volgende keer laadt.</span><span class="sxs-lookup"><span data-stu-id="39b6a-245">One major benefit of [this approach](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) is that by using HTML5 local storage, the navigation is stored locally for the user the next time they load the page.</span></span> <span data-ttu-id="39b6a-246">We gaan belangrijke prestatieverbeteringen in het gebruik van de zoek-API voor structurele navigatie. het kan echter wel enkele technische mogelijkheden voor het uitvoeren van deze functionaliteit en het aanpassen van deze functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="39b6a-246">We get major performance improvements from using the search API for structural navigation; however, it takes some technical capability to execute and customize this functionality.</span></span>

<span data-ttu-id="39b6a-247">In de [Voorbeeldimplementatie](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)worden de sites op dezelfde manier geordend als de kant-en-klare structurele navigatie. alfabetische volgorde.</span><span class="sxs-lookup"><span data-stu-id="39b6a-247">In the [example implementation](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page), the sites are ordered in the same way as the out-of-the-box structural navigation; alphabetical order.</span></span> <span data-ttu-id="39b6a-248">Als u wilt afwijken van deze volgorde, is het ingewikkelder om te ontwikkelen en te onderhouden.</span><span class="sxs-lookup"><span data-stu-id="39b6a-248">If you wanted to deviate from this order, it would be more complicated to develop and maintain.</span></span> <span data-ttu-id="39b6a-249">Voor deze methode moet u ook afwijken van de ondersteunde basispagina's.</span><span class="sxs-lookup"><span data-stu-id="39b6a-249">Also, this approach requires you to deviate from the supported master pages.</span></span> <span data-ttu-id="39b6a-250">Als de aangepaste basispagina niet wordt bijgehouden, mist de site updates en verbeteringen die door Microsoft worden aangebracht in de basispagina's.</span><span class="sxs-lookup"><span data-stu-id="39b6a-250">If the custom master page is not maintained, your site will miss out on updates and improvements that Microsoft makes to the master pages.</span></span>

<span data-ttu-id="39b6a-251">De [bovenstaande code](#about-the-javascript-file) heeft de volgende afhankelijkheden:</span><span class="sxs-lookup"><span data-stu-id="39b6a-251">The [above code](#about-the-javascript-file) has the following dependencies:</span></span>

- <span data-ttu-id="39b6a-252">jQuery https://jquery.com/</span><span class="sxs-lookup"><span data-stu-id="39b6a-252">jQuery - https://jquery.com/</span></span>
- <span data-ttu-id="39b6a-253">KnockoutJS https://knockoutjs.com/</span><span class="sxs-lookup"><span data-stu-id="39b6a-253">KnockoutJS - https://knockoutjs.com/</span></span>
- <span data-ttu-id="39b6a-254">Linq.js- https://linqjs.codeplex.com/ of github.com/neuecc/linq.js</span><span class="sxs-lookup"><span data-stu-id="39b6a-254">Linq.js - https://linqjs.codeplex.com/, or github.com/neuecc/linq.js</span></span>

<span data-ttu-id="39b6a-255">De huidige versie van LinqJS bevat niet de methode ByHierarchy die in de bovenstaande code is gebruikt en verbreekt de navigatie code.</span><span class="sxs-lookup"><span data-stu-id="39b6a-255">The current version of LinqJS does not contain the ByHierarchy method used in the above code and will break the navigation code.</span></span> <span data-ttu-id="39b6a-256">U kunt dit oplossen door de volgende methode toe te voegen aan het Linq.js-bestand vóór de regel `Flatten: function ()` .</span><span class="sxs-lookup"><span data-stu-id="39b6a-256">To fix this, add the following method to the Linq.js file before the line `Flatten: function ()`.</span></span>

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a><span data-ttu-id="39b6a-257">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="39b6a-257">Related topics</span></span>

[<span data-ttu-id="39b6a-258">Overzicht van beheerde navigatie in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="39b6a-258">Overview of managed navigation in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)

[<span data-ttu-id="39b6a-259">Opslag en prestaties van structurele navigatie</span><span class="sxs-lookup"><span data-stu-id="39b6a-259">Structural navigation caching and performance</span></span>](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)
