---
title: Zoeken naar Microsoft 365 multi-geo configureren
ms.reviewer: adwood
ms.author: tlarsen
author: tklarsen
manager: arnek
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-mar2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: Meer informatie over het configureren van zoeken in een multi-geo-omgeving. Alleen sommige clients, zoals OneDrive, kunnen resultaten retourneren in een multi-geoomgeving.
ms.openlocfilehash: dfc9e3dd986132810f363ba47ba18eae45666fc7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362268"
---
# <a name="configure-search-for-microsoft-365-multi-geo"></a><span data-ttu-id="6c73d-104">Zoeken naar Microsoft 365 multi-geo configureren</span><span class="sxs-lookup"><span data-stu-id="6c73d-104">Configure Search for Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="6c73d-105">In een multi-geoomgeving heeft elke geografische locatie een eigen zoekindex en zoekcentrum.</span><span class="sxs-lookup"><span data-stu-id="6c73d-105">In a multi-geo environment, each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="6c73d-106">Wanneer een gebruiker zoekt, wordt de query uitgewaakt naar alle indexen en worden de geretourneerde resultaten samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="6c73d-106">When a user searches, the query is fanned out to all the indexes, and the returned results are merged.</span></span>

<span data-ttu-id="6c73d-107">Een gebruiker op één geografische locatie kan bijvoorbeeld zoeken naar inhoud die is opgeslagen op een andere geografische locatie of naar inhoud op een SharePoint-site die is beperkt tot een andere geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="6c73d-107">For example, a user in one geo location can search for content stored in another geo location, or for content on a SharePoint site that's restricted to a different geo location.</span></span> <span data-ttu-id="6c73d-108">Als de gebruiker toegang heeft tot deze inhoud, wordt het resultaat ervan in de zoekopdracht besyd.</span><span class="sxs-lookup"><span data-stu-id="6c73d-108">If the user has access to this content, search will show the result.</span></span>

## <a name="which-search-clients-work-in-a-multi-geo-environment"></a><span data-ttu-id="6c73d-109">Welke zoek clients werken in een multi-geo-omgeving?</span><span class="sxs-lookup"><span data-stu-id="6c73d-109">Which search clients work in a multi-geo environment?</span></span>

<span data-ttu-id="6c73d-110">Deze clients kunnen resultaten van alle geografische locaties retourneren:</span><span class="sxs-lookup"><span data-stu-id="6c73d-110">These clients can return results from all geo locations:</span></span>

- <span data-ttu-id="6c73d-111">OneDrive</span><span class="sxs-lookup"><span data-stu-id="6c73d-111">OneDrive</span></span>
- <span data-ttu-id="6c73d-112">Delve</span><span class="sxs-lookup"><span data-stu-id="6c73d-112">Delve</span></span>
- <span data-ttu-id="6c73d-113">De SharePoint startpagina</span><span class="sxs-lookup"><span data-stu-id="6c73d-113">The SharePoint home page</span></span>
- <span data-ttu-id="6c73d-114">Het zoekcentrum</span><span class="sxs-lookup"><span data-stu-id="6c73d-114">The Search Center</span></span>
- <span data-ttu-id="6c73d-115">Aangepaste zoektoepassingen die gebruikmaken van de SharePoint Search API</span><span class="sxs-lookup"><span data-stu-id="6c73d-115">Custom search applications that use the SharePoint Search API</span></span>

### <a name="onedrive"></a><span data-ttu-id="6c73d-116">OneDrive</span><span class="sxs-lookup"><span data-stu-id="6c73d-116">OneDrive</span></span>

<span data-ttu-id="6c73d-117">Zodra de multi-geo-omgeving is ingesteld, krijgen gebruikers die zoeken in OneDrive resultaten van alle geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="6c73d-117">As soon as the multi-geo environment has been set up, users that search in OneDrive get results from all geo locations.</span></span>

### <a name="delve"></a><span data-ttu-id="6c73d-118">Delve</span><span class="sxs-lookup"><span data-stu-id="6c73d-118">Delve</span></span>

<span data-ttu-id="6c73d-119">Zodra de multi-geo-omgeving is ingesteld, krijgen gebruikers die zoeken in Delve resultaten van alle geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="6c73d-119">As soon as the multi-geo environment has been set up, users that search in Delve get results from all geo locations.</span></span>

<span data-ttu-id="6c73d-120">De Delve en de profielkaart geven alleen voorbeelden weer van bestanden die zijn opgeslagen op de centrale locatie.</span><span class="sxs-lookup"><span data-stu-id="6c73d-120">The Delve feed and the profile card only show previews of files that are stored in the central location.</span></span> <span data-ttu-id="6c73d-121">Voor bestanden die zijn opgeslagen op satellietlocaties, wordt in plaats daarvan het pictogram voor het bestandstype weergegeven.</span><span class="sxs-lookup"><span data-stu-id="6c73d-121">For files that are stored in satellite locations, the icon for the file type is shown instead.</span></span>

### <a name="the-sharepoint-home-page"></a><span data-ttu-id="6c73d-122">De SharePoint startpagina</span><span class="sxs-lookup"><span data-stu-id="6c73d-122">The SharePoint home page</span></span>

<span data-ttu-id="6c73d-123">Zodra de multi-geo-omgeving is ingesteld, zien gebruikers nieuws, recente en gevolgde sites van meerdere geografische locaties op hun SharePoint startpagina.</span><span class="sxs-lookup"><span data-stu-id="6c73d-123">As soon as the multi-geo environment has been set up, users will see news, recent and followed sites from multiple geo locations on their SharePoint home page.</span></span> <span data-ttu-id="6c73d-124">Als ze het zoekvak op de SharePoint startpagina gebruiken, krijgen ze samengevoegde resultaten van meerdere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="6c73d-124">If they use the search box on the SharePoint home page, they'll get merged results from multiple geo locations.</span></span>

### <a name="the-search-center"></a><span data-ttu-id="6c73d-125">Het zoekcentrum</span><span class="sxs-lookup"><span data-stu-id="6c73d-125">The Search Center</span></span>

<span data-ttu-id="6c73d-126">Nadat de multi-geo-omgeving is ingesteld, worden in elk zoekcentrum alleen resultaten van hun eigen geografische locatie weer te geven.</span><span class="sxs-lookup"><span data-stu-id="6c73d-126">After the multi-geo environment has been set up, each Search Center continues to only show results from their own geo location.</span></span> <span data-ttu-id="6c73d-127">Beheerders moeten [de instellingen van elk zoekcentrum wijzigen](#_Set_up_a_1) om resultaten te krijgen van alle geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="6c73d-127">Admins must [change the settings of each Search Center](#_Set_up_a_1) to get results from all geo locations.</span></span> <span data-ttu-id="6c73d-128">Daarna krijgen gebruikers die zoeken in het zoekcentrum resultaten van alle geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="6c73d-128">Afterwards, users that search in the Search Center get results from all geo locations.</span></span>

### <a name="custom-search-applications"></a><span data-ttu-id="6c73d-129">Aangepaste zoektoepassingen</span><span class="sxs-lookup"><span data-stu-id="6c73d-129">Custom search applications</span></span>

<span data-ttu-id="6c73d-130">Zoals gewoonlijk werken aangepaste zoektoepassingen samen met de zoekindexen met behulp van de bestaande SharePoint SEARCH REST-API's.</span><span class="sxs-lookup"><span data-stu-id="6c73d-130">As usual, custom search applications interact with the search indexes by using the existing SharePoint Search REST APIs.</span></span> <span data-ttu-id="6c73d-131">Als u resultaten wilt krijgen van alle of bepaalde geografische locaties, moet de toepassing de API bellen en de nieuwe [multi-geoqueryparameters](#_Get_custom_search) in de aanvraag opnemen.</span><span class="sxs-lookup"><span data-stu-id="6c73d-131">To get results from all, or some geo locations, the application must [call the API and include the new Multi-Geo query parameters](#_Get_custom_search) in the request.</span></span> <span data-ttu-id="6c73d-132">Hiermee wordt een ventilator uit de query naar alle geografische locaties triggers.</span><span class="sxs-lookup"><span data-stu-id="6c73d-132">This triggers a fan out of the query to all geo locations.</span></span>

## <a name="whats-different-about-search-in-a-multi-geo-environment"></a><span data-ttu-id="6c73d-133">Wat is er anders aan zoeken in een multi-geo-omgeving?</span><span class="sxs-lookup"><span data-stu-id="6c73d-133">What's different about search in a multi-geo environment?</span></span>

<span data-ttu-id="6c73d-134">Sommige zoekfuncties die u mogelijk kent, werken anders in een multi-geoomgeving.</span><span class="sxs-lookup"><span data-stu-id="6c73d-134">Some search features you might be familiar with, work differently in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6c73d-135">Functie</span><span class="sxs-lookup"><span data-stu-id="6c73d-135">Feature</span></span></th>
<th align="left"><span data-ttu-id="6c73d-136">Hoe het werkt</span><span class="sxs-lookup"><span data-stu-id="6c73d-136">How it works</span></span></th>
<th align="left"><span data-ttu-id="6c73d-137">Tijdelijke oplossing</span><span class="sxs-lookup"><span data-stu-id="6c73d-137">Workaround</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="6c73d-138">Gepromoveerde resultaten</span><span class="sxs-lookup"><span data-stu-id="6c73d-138">Promoted results</span></span></td>
<td align="left"><span data-ttu-id="6c73d-139">U kunt queryregels maken met gepromoveerde resultaten op verschillende niveaus: voor de hele tenant, voor een siteverzameling of voor een site.</span><span class="sxs-lookup"><span data-stu-id="6c73d-139">You can create query rules with promoted results at different levels: for the whole tenant, for a site collection, or for a site.</span></span> <span data-ttu-id="6c73d-140">Definieer in een multi-geoomgeving gepromoveerde resultaten op tenantniveau om de resultaten te promoveren naar de zoekcentra op alle geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="6c73d-140">In a multi-geo environment, define promoted results at the tenant level to promote the results to the Search Centers in all geo locations.</span></span> <span data-ttu-id="6c73d-141">Als u alleen resultaten wilt promoten in het zoekcentrum dat zich op de geografische locatie van de siteverzameling of site bevindt, definieert u de gepromoveerde resultaten op siteverzamelings- of siteniveau.</span><span class="sxs-lookup"><span data-stu-id="6c73d-141">If you only want to promote results in the Search Center that's in the geo location of the site collection or site, define the promoted results at the site collection or site level.</span></span> <span data-ttu-id="6c73d-142">Deze resultaten worden niet gepromoveerd op andere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="6c73d-142">These results are not promoted in other geo locations.</span></span></td>
<td align="left"><span data-ttu-id="6c73d-143">Als u geen andere gepromoveerde resultaten per geografische locatie nodig hebt, bijvoorbeeld andere regels voor reizen, raden we u aan gepromoveerde resultaten op tenantniveau te definiëren.</span><span class="sxs-lookup"><span data-stu-id="6c73d-143">If you don't need different promoted results per geo location, for example different rules for traveling, we recommend defining promoted results at the tenant level.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="6c73d-144">Verfijningen zoeken</span><span class="sxs-lookup"><span data-stu-id="6c73d-144">Search refiners</span></span></td>
<td align="left"><span data-ttu-id="6c73d-145">Zoeken retourneert verfijningen van alle geografische locaties van een tenant en verzamelt ze vervolgens.</span><span class="sxs-lookup"><span data-stu-id="6c73d-145">Search returns refiners from all the geo locations of a tenant and then aggregates them.</span></span> <span data-ttu-id="6c73d-146">De aggregatie is een goede poging, wat betekent dat het aantal verfijningen mogelijk niet 100% nauwkeurig is.</span><span class="sxs-lookup"><span data-stu-id="6c73d-146">The aggregation is a best effort, meaning that the refiner counts might not be 100% accurate.</span></span> <span data-ttu-id="6c73d-147">Voor de meeste zoekscenario's is deze nauwkeurigheid voldoende.</span><span class="sxs-lookup"><span data-stu-id="6c73d-147">For most search-driven scenarios, this accuracy is sufficient.</span></span> 
</td>
<td align="left"><span data-ttu-id="6c73d-148">Voor zoektoepassingen die afhankelijk zijn van de verfijningsversterkheid, kunt u elke geografische locatie onafhankelijk van elkaar opvragen.</span><span class="sxs-lookup"><span data-stu-id="6c73d-148">For search-driven applications that depend on refiner completeness, query each geo location independently.</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><span data-ttu-id="6c73d-149">Multi-geo search biedt geen ondersteuning voor dynamische bucketing voor numerieke verfijningen.</span><span class="sxs-lookup"><span data-stu-id="6c73d-149">Multi-geo search doesn't support dynamic bucketing for numerical refiners.</span></span></td>
<td align="left"><span data-ttu-id="6c73d-150">Gebruik de <a href="/sharepoint/dev/general-development/query-refinement-in-sharepoint">parameter 'Discretize'</a> voor numerieke verfijningen.</span><span class="sxs-lookup"><span data-stu-id="6c73d-150">Use the <a href="/sharepoint/dev/general-development/query-refinement-in-sharepoint">"Discretize" parameter</a> for numerical refiners.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="6c73d-151">Document-eds</span><span class="sxs-lookup"><span data-stu-id="6c73d-151">Document IDs</span></span></td>
<td align="left"><span data-ttu-id="6c73d-152">Als u een zoektoepassing ontwikkelt die afhankelijk is van document-1D's, moet u er rekening mee houden dat document-ed's in een multi-geo-omgeving niet uniek zijn op geografische locaties, maar uniek zijn per geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="6c73d-152">If you're developing a search-driven application that depends on document IDs, note that document IDs in a multi-geo environment aren't unique across geo locations, they are unique per geo location.</span></span></td>
<td align="left"><span data-ttu-id="6c73d-153">We hebben een kolom toegevoegd die de geografische locatie identificeert.</span><span class="sxs-lookup"><span data-stu-id="6c73d-153">We've added a column that identifies the geo location.</span></span> <span data-ttu-id="6c73d-154">Gebruik deze kolom om uniciteit te bereiken.</span><span class="sxs-lookup"><span data-stu-id="6c73d-154">Use this column to achieve uniqueness.</span></span> <span data-ttu-id="6c73d-155">Deze kolom heet 'GeoLocationSource'.</span><span class="sxs-lookup"><span data-stu-id="6c73d-155">This column is named "GeoLocationSource".</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="6c73d-156">Aantal resultaten</span><span class="sxs-lookup"><span data-stu-id="6c73d-156">Number of results</span></span></td>
<td align="left"><span data-ttu-id="6c73d-157">De pagina met zoekresultaten bevat gecombineerde resultaten van de geografische locaties, maar het is niet mogelijk om meer dan 500 resultaten te pagina's.</span><span class="sxs-lookup"><span data-stu-id="6c73d-157">The search results page shows combined results from the geo locations, but it's not possible to page beyond 500 results.</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="6c73d-158">Hybride zoekopdracht</span><span class="sxs-lookup"><span data-stu-id="6c73d-158">Hybrid search</span></span></td>
<td align="left"><span data-ttu-id="6c73d-159">In een hybride SharePoint omgeving met hybride zoeken in de <a href="/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">cloud,</a>wordt on-premises inhoud toegevoegd aan de Microsoft 365 index van de centrale locatie.</span><span class="sxs-lookup"><span data-stu-id="6c73d-159">In a hybrid SharePoint environment with <a href="/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">cloud hybrid search</a>,  on-premises content is added to the Microsoft 365 index of the central location.</span></span></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="whats-not-supported-for-search-in-a-multi-geo-environment"></a><span data-ttu-id="6c73d-160">Wat wordt niet ondersteund voor zoeken in een multi-geo-omgeving?</span><span class="sxs-lookup"><span data-stu-id="6c73d-160">What's not supported for search in a multi-geo environment?</span></span>

<span data-ttu-id="6c73d-161">Sommige zoekfuncties die u mogelijk kent, worden niet ondersteund in een multi-geoomgeving.</span><span class="sxs-lookup"><span data-stu-id="6c73d-161">Some of the search features you might be familiar with, aren't supported in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6c73d-162">Zoekfunctie</span><span class="sxs-lookup"><span data-stu-id="6c73d-162">Search feature</span></span></th>
<th align="left"><span data-ttu-id="6c73d-163">Opmerking</span><span class="sxs-lookup"><span data-stu-id="6c73d-163">Note</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="6c73d-164">Alleen-app-verificatie</span><span class="sxs-lookup"><span data-stu-id="6c73d-164">App-only authentication</span></span></td>
<td align="left"><span data-ttu-id="6c73d-165">App-only verificatie (privileged access from services) wordt niet ondersteund in multi-geo-zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="6c73d-165">App-only authentication (privileged access from services) isn't supported in multi-geo search.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="6c73d-166">Gasten</span><span class="sxs-lookup"><span data-stu-id="6c73d-166">Guests</span></span></td>
<td align="left"><span data-ttu-id="6c73d-167">Gasten krijgen alleen resultaten van de geografische locatie waar ze naar zoeken.</span><span class="sxs-lookup"><span data-stu-id="6c73d-167">Guests only get results from the geo location that they're searching from.</span></span></td>
</tr>
</tbody>
</table>

## <a name="how-does-search-work-in-a-multi-geo-environment"></a><span data-ttu-id="6c73d-168">Hoe werkt zoeken in een multi-geo-omgeving?</span><span class="sxs-lookup"><span data-stu-id="6c73d-168">How does search work in a multi-geo environment?</span></span>

<span data-ttu-id="6c73d-169">Alle zoek clients gebruiken de bestaande SharePoint SEARCH REST API's om te werken met de zoekindexen.</span><span class="sxs-lookup"><span data-stu-id="6c73d-169">All the search clients use the existing SharePoint Search REST APIs to interact with the search indexes.</span></span>

![Diagram waarin wordt SharePoint de interactie tussen zoek-REST-API's en de zoekindexen](../media/configure-search-for-multi-geo-image1-1.png)

1. <span data-ttu-id="6c73d-171">Een zoekclient noemt het eindpunt Rest zoeken met de query-eigenschap EnableMultiGeoSearch= waar.</span><span class="sxs-lookup"><span data-stu-id="6c73d-171">A search client calls the Search REST endpoint with the query property EnableMultiGeoSearch= true.</span></span>
2. <span data-ttu-id="6c73d-172">De query wordt verzonden naar alle geografische locaties in de tenant.</span><span class="sxs-lookup"><span data-stu-id="6c73d-172">The query is sent to all geo locations in the tenant.</span></span>
3. <span data-ttu-id="6c73d-173">Zoekresultaten van elke geografische locatie worden samengevoegd en gerangschikt.</span><span class="sxs-lookup"><span data-stu-id="6c73d-173">Search results from each geo location are merged and ranked.</span></span>
4. <span data-ttu-id="6c73d-174">De client krijgt geïntegreerde zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="6c73d-174">The client gets unified search results.</span></span>

<span data-ttu-id="6c73d-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>We voegen de zoekresultaten pas samen als we resultaten van alle geografische locaties hebben ontvangen.</span><span class="sxs-lookup"><span data-stu-id="6c73d-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Notice that we don't merge the search results until we've received results from all the geo locations.</span></span> <span data-ttu-id="6c73d-176">Dit betekent dat meerdere geografische zoekopdrachten extra latentie hebben ten opzichte van zoekopdrachten in een omgeving met slechts één geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="6c73d-176">This means that multi-geo searches have additional latency compared to searches in an environment with only one geo location.</span></span>

<span id="_Set_up_a_1" class="anchor"><span id="_Ref505252370" class="anchor"></span></span>
## <a name="get-a-search-center-to-show-results-from-all-geo-locations"></a><span data-ttu-id="6c73d-177">Een zoekcentrum zoeken om resultaten van alle geografische locaties weer te geven</span><span class="sxs-lookup"><span data-stu-id="6c73d-177">Get a Search Center to show results from all geo locations</span></span>

<span data-ttu-id="6c73d-178">Elk zoekcentrum heeft verschillende verticaalen en u moet elke verticaal afzonderlijk instellen.</span><span class="sxs-lookup"><span data-stu-id="6c73d-178">Each Search Center has several verticals and you have to set up each vertical individually.</span></span>

1. <span data-ttu-id="6c73d-179">Zorg ervoor dat u deze stappen voert met een account dat is machtigingen voor het bewerken van de pagina met zoekresultaten en het webonderdeel Zoekresultaten.</span><span class="sxs-lookup"><span data-stu-id="6c73d-179">Ensure that you perform these steps with an account that has permission to edit the search results page and the Search Result Web Part.</span></span>

2. <span data-ttu-id="6c73d-180">Ga naar de pagina met zoekresultaten (zie de [lijst](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) met pagina's met zoekresultaten)</span><span class="sxs-lookup"><span data-stu-id="6c73d-180">Navigate to the search results page (see the [list](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) of search results pages)</span></span>

3. <span data-ttu-id="6c73d-181">Selecteer de verticale positie die u wilt instellen, klik **Instellingen** tandwielpictogram in de rechterbovenhoek en klik vervolgens op **Pagina bewerken.**</span><span class="sxs-lookup"><span data-stu-id="6c73d-181">Select the vertical to set up, click **Settings** gear icon in the upper, right corner, and then click **Edit Page**.</span></span> <span data-ttu-id="6c73d-182">De pagina met zoekresultaten wordt geopend in de bewerkingsmodus.</span><span class="sxs-lookup"><span data-stu-id="6c73d-182">The search results page opens in Edit mode.</span></span>

   ![Paginaselectie bewerken in Instellingen](../media/configure-search-for-multi-geo-image2.png)

4. <span data-ttu-id="6c73d-184">Verplaats in het webonderdeel Zoekresultaten de aanwijzer naar de rechterbovenhoek van het webonderdeel, klik op de pijl en klik vervolgens op **Webonderdeel** bewerken in het menu.</span><span class="sxs-lookup"><span data-stu-id="6c73d-184">In the Search Results Web Part, move the pointer to the upper, right corner of the web part, click the arrow, and then click **Edit Web Part** on the menu.</span></span> <span data-ttu-id="6c73d-185">Het deelvenster Webonderdeel Zoekresultaten wordt geopend onder het lint rechtsboven op de pagina.</span><span class="sxs-lookup"><span data-stu-id="6c73d-185">The Search Results Web Part tool pane opens under the ribbon in the top right of the page.</span></span>

   ![Selectie webonderdeel bewerken](../media/configure-search-for-multi-geo-image3.png)

5. <span data-ttu-id="6c73d-187">Selecteer in het taakvenster van het **webonderdeel in** de sectie Instellingen onder Instellingen voor resultatenbesturingselement de optie  **Multi-Geo-resultaten** weergeven om het webonderdeel Zoekresultaten weer te geven om resultaten van alle geografische locaties weer te geven.</span><span class="sxs-lookup"><span data-stu-id="6c73d-187">In the Web Part tool pane, in the **Settings** section, under **Results control settings**, select **Show Multi-Geo results** to get the Search Results Web Part to show results from all geo locations.</span></span>

6. <span data-ttu-id="6c73d-188">Klik **op OK** om de wijziging op te slaan en het taakvenster van het webonderdeel te sluiten.</span><span class="sxs-lookup"><span data-stu-id="6c73d-188">Click **OK** to save your change and close the Web Part tool pane.</span></span>

7. <span data-ttu-id="6c73d-189">Controleer uw wijzigingen in het webonderdeel Zoekresultaten door op **Inchecken te klikken** op het tabblad Pagina van het hoofdmenu.</span><span class="sxs-lookup"><span data-stu-id="6c73d-189">Check your changes to the Search Results Web Part by clicking **Check-In** on the Page tab of the main menu.</span></span>

8. <span data-ttu-id="6c73d-190">Publiceer de wijzigingen met behulp van de koppeling in de notitie boven aan de pagina.</span><span class="sxs-lookup"><span data-stu-id="6c73d-190">Publish the changes by using the link provided in the note at the top of the page.</span></span>

<span id="_Get_custom_search" class="anchor"><span id="_Ref501388387" class="anchor"></span></span>
## <a name="get-custom-search-applications-to-show-results-from-all-or-some-geo-locations"></a><span data-ttu-id="6c73d-191">Aangepaste zoektoepassingen gebruiken om resultaten van alle of sommige geografische locaties weer te geven</span><span class="sxs-lookup"><span data-stu-id="6c73d-191">Get custom search applications to show results from all or some geo locations</span></span>

<span data-ttu-id="6c73d-192">Aangepaste zoektoepassingen krijgen resultaten van alle of sommige geografische locaties door queryparameters op te geven met de aanvraag voor de SharePoint SEARCH REST API.</span><span class="sxs-lookup"><span data-stu-id="6c73d-192">Custom search applications get results from all, or some, geo locations by specifying query parameters with the request to the SharePoint Search REST API.</span></span> <span data-ttu-id="6c73d-193">Afhankelijk van de queryparameters wordt de query uitgewaakt naar alle geografische locaties of naar bepaalde geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="6c73d-193">Depending on the query parameters, the query is fanned out to all geo locations, or to some geo locations.</span></span> <span data-ttu-id="6c73d-194">Als u bijvoorbeeld alleen een subset met geografische locaties hoeft te query's uitvoeren om relevante informatie te vinden, kunt u de ventilator alleen naar deze locaties uitbesturing geven.</span><span class="sxs-lookup"><span data-stu-id="6c73d-194">For example, if you only need to query a subset of geo locations to find relevant information, you can control the fan out to only these.</span></span> <span data-ttu-id="6c73d-195">Als de aanvraag slaagt, retourneert SharePoint SEARCH REST API antwoordgegevens.</span><span class="sxs-lookup"><span data-stu-id="6c73d-195">If the request succeeds, the SharePoint Search REST API returns response data.</span></span>

### <a name="requirement"></a><span data-ttu-id="6c73d-196">Vereiste</span><span class="sxs-lookup"><span data-stu-id="6c73d-196">Requirement</span></span>

<span data-ttu-id="6c73d-197">Voor elke geografische locatie moet u ervoor zorgen dat  alle gebruikers in de organisatie het machtigingsniveau Lezen hebben gekregen voor de hoofdwebsite (bijvoorbeeld contoso **APAC**.sharepoint.com/ en contoso **EU**.sharepoint.com/).</span><span class="sxs-lookup"><span data-stu-id="6c73d-197">For each geo location, you must ensure that all users in the organization have been granted the **Read** permission level for the root website (for example contoso **APAC**.sharepoint.com/ and contoso **EU**.sharepoint.com/).</span></span> <span data-ttu-id="6c73d-198">[Meer informatie over machtigingen.](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848)</span><span class="sxs-lookup"><span data-stu-id="6c73d-198">[Learn about permissions](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).</span></span>

### <a name="query-parameters"></a><span data-ttu-id="6c73d-199">Queryparameters</span><span class="sxs-lookup"><span data-stu-id="6c73d-199">Query parameters</span></span>

<span data-ttu-id="6c73d-200">EnableMultiGeoSearch: dit is een Booleaanse waarde die aangeeft of de query moet worden uitgewaakt naar de indexen van andere geografische locaties van de multi-geotenant.</span><span class="sxs-lookup"><span data-stu-id="6c73d-200">EnableMultiGeoSearch - This is a Boolean value that specifies whether the query shall be fanned out to the indexes of other geo locations of the multi-geo tenant.</span></span> <span data-ttu-id="6c73d-201">Stel deze in **op waar om** de query uit te ventilatoren. **onwaar** om de query niet uit te waaieren.</span><span class="sxs-lookup"><span data-stu-id="6c73d-201">Set it to **true** to fan out the query; **false** to not fan out the query.</span></span> <span data-ttu-id="6c73d-202">Als u deze parameter niet opgeeft, **is** de standaardwaarde onwaar, behalve wanneer u een REST API-oproep doet tegen een site die de sjabloon Enterprise Search Center gebruikt, in dit geval is de standaardwaarde **waar.**</span><span class="sxs-lookup"><span data-stu-id="6c73d-202">If you don't include this parameter, the default value is **false**, except when making a REST API call against a site which uses the Enterprise Search Center template, in this case the default value is **true**.</span></span> <span data-ttu-id="6c73d-203">Als u de parameter gebruikt in een omgeving die niet multi-geo is, wordt de parameter genegeerd.</span><span class="sxs-lookup"><span data-stu-id="6c73d-203">If you use the parameter in an environment that isn't multi-geo, the parameter is ignored.</span></span>

<span data-ttu-id="6c73d-204">ClientType: dit is een tekenreeks.</span><span class="sxs-lookup"><span data-stu-id="6c73d-204">ClientType - This is a string.</span></span> <span data-ttu-id="6c73d-205">Voer een unieke clientnaam in voor elke zoektoepassing.</span><span class="sxs-lookup"><span data-stu-id="6c73d-205">Enter a unique client name for each search application.</span></span> <span data-ttu-id="6c73d-206">Als u deze parameter niet opgeeft, wordt de query niet uitgewaakt naar andere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="6c73d-206">If you don't include this parameter, the query is not fanned out to other geo locations.</span></span>

<span data-ttu-id="6c73d-207">MultiGeoSearchConfiguration - Dit is een optionele lijst van de geografische locaties in de multi-geo tenant om de query uit te ventilatoren wanneer **EnableMultiGeoSearch** **waar** is.</span><span class="sxs-lookup"><span data-stu-id="6c73d-207">MultiGeoSearchConfiguration - This is an optional list of which geo locations in the multi-geo tenant to fan the query out to when **EnableMultiGeoSearch** is **true**.</span></span> <span data-ttu-id="6c73d-208">Als u deze parameter niet opgeeft of leeg laat, wordt de query uitgewaakt naar alle geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="6c73d-208">If you don't include this parameter, or leave it blank, the query is fanned out to all geo locations.</span></span> <span data-ttu-id="6c73d-209">Voer voor elke geografische locatie de volgende items in in de JSON-indeling:</span><span class="sxs-lookup"><span data-stu-id="6c73d-209">For each geo location, enter the following items, in JSON format:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6c73d-210">Item</span><span class="sxs-lookup"><span data-stu-id="6c73d-210">Item</span></span></th>
<th align="left"><span data-ttu-id="6c73d-211">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6c73d-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="6c73d-212">DataLocation</span><span class="sxs-lookup"><span data-stu-id="6c73d-212">DataLocation</span></span></td>
<td align="left"><span data-ttu-id="6c73d-213">De geografische locatie, bijvoorbeeld nam.</span><span class="sxs-lookup"><span data-stu-id="6c73d-213">The geo location, for example NAM.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="6c73d-214">EndPoint</span><span class="sxs-lookup"><span data-stu-id="6c73d-214">EndPoint</span></span></td>
<td align="left"><span data-ttu-id="6c73d-215">Het eindpunt waar u verbinding mee wilt maken, bijvoorbeeld https://contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="6c73d-215">The endpoint to connect to, for example https://contoso.sharepoint.com</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="6c73d-216">SourceId</span><span class="sxs-lookup"><span data-stu-id="6c73d-216">SourceId</span></span></td>
<td align="left"><span data-ttu-id="6c73d-217">De GUID van de resultatenbron, bijvoorbeeld B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span><span class="sxs-lookup"><span data-stu-id="6c73d-217">The GUID of the result source, for example B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6c73d-218">Als u DataLocation of EndPoint weglaat of als een DataLocation wordt gedupliceerd, mislukt de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="6c73d-218">If you omit DataLocation or EndPoint, or if a DataLocation is duplicated, the request fails.</span></span> <span data-ttu-id="6c73d-219">U kunt informatie krijgen over het eindpunt van de geografische locaties van een [tenant met Behulp van Microsoft Graph.](/sharepoint/dev/solution-guidance/multigeo-discovery)</span><span class="sxs-lookup"><span data-stu-id="6c73d-219">[You can get information about the endpoint of a tenant's geo locations by using Microsoft Graph](/sharepoint/dev/solution-guidance/multigeo-discovery).</span></span>

### <a name="response-data"></a><span data-ttu-id="6c73d-220">Antwoordgegevens</span><span class="sxs-lookup"><span data-stu-id="6c73d-220">Response data</span></span>

<span data-ttu-id="6c73d-221">MultiGeoSearchStatus: dit is een eigenschap die SharePoint zoek-API retourneert als antwoord op een aanvraag.</span><span class="sxs-lookup"><span data-stu-id="6c73d-221">MultiGeoSearchStatus – This is a property that the SharePoint Search API returns in response to a request.</span></span> <span data-ttu-id="6c73d-222">De waarde van de eigenschap is een tekenreeks en geeft de volgende informatie over de resultaten die SharePoint Zoek-API retourneert:</span><span class="sxs-lookup"><span data-stu-id="6c73d-222">The value of the property is a string and gives the following information about the results that the SharePoint Search API returns:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6c73d-223">Waarde</span><span class="sxs-lookup"><span data-stu-id="6c73d-223">Value</span></span></th>
<th align="left"><span data-ttu-id="6c73d-224">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6c73d-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="6c73d-225">Volledig</span><span class="sxs-lookup"><span data-stu-id="6c73d-225">Full</span></span></td>
<td align="left"><span data-ttu-id="6c73d-226">Volledige resultaten van <strong>alle</strong> geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="6c73d-226">Full results from <strong>all</strong> the geo locations.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="6c73d-227">Gedeeltelijk</span><span class="sxs-lookup"><span data-stu-id="6c73d-227">Partial</span></span></td>
<td align="left"><span data-ttu-id="6c73d-228">Gedeeltelijke resultaten van een of meer geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="6c73d-228">Partial results from one or more geo locations.</span></span> <span data-ttu-id="6c73d-229">De resultaten zijn onvolledig vanwege een tijdelijke fout.</span><span class="sxs-lookup"><span data-stu-id="6c73d-229">The results are incomplete due to a transient error.</span></span></td>
</tr>
</tbody>
</table>

### <a name="query-using-the-rest-service"></a><span data-ttu-id="6c73d-230">Query met de REST-service</span><span class="sxs-lookup"><span data-stu-id="6c73d-230">Query using the REST service</span></span>

<span data-ttu-id="6c73d-231">Met een GET-aanvraag geeft u de queryparameters op in de URL.</span><span class="sxs-lookup"><span data-stu-id="6c73d-231">With a GET request, you specify the query parameters in the URL.</span></span> <span data-ttu-id="6c73d-232">Met een POST-aanvraag passeert u de queryparameters in de body in de JSON-indeling (JavaScript Object Notation).</span><span class="sxs-lookup"><span data-stu-id="6c73d-232">With a POST request, you pass the query parameters in the body in JavaScript Object Notation (JSON) format.</span></span>

#### <a name="request-headers"></a><span data-ttu-id="6c73d-233">Aanvraagheaders</span><span class="sxs-lookup"><span data-stu-id="6c73d-233">Request headers</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6c73d-234">Name</span><span class="sxs-lookup"><span data-stu-id="6c73d-234">Name</span></span></th>
<th align="left"><span data-ttu-id="6c73d-235">Value</span><span class="sxs-lookup"><span data-stu-id="6c73d-235">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="6c73d-236">Content-Type</span><span class="sxs-lookup"><span data-stu-id="6c73d-236">Content-Type</span></span></td>
<td align="left"><span data-ttu-id="6c73d-237">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="6c73d-237">application/json;odata=verbose</span></span></td>
</tr>
</tbody>
</table>

#### <a name="sample-get-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="6c73d-238">Voorbeeld van GET-aanvraag die is uitgewaakt naar **alle** geografische locaties</span><span class="sxs-lookup"><span data-stu-id="6c73d-238">Sample GET request that's fanned out to **all** geo locations</span></span>

```http
https:// \<tenant\>/\_api/search/query?querytext='sharepoint'&Properties='EnableMultiGeoSearch:true'&ClientType='my\_client\_id'
```

#### <a name="sample-get-request-to-fan-out-to-some-geo-locations"></a><span data-ttu-id="6c73d-239">Voorbeeld van GET-aanvraag om uit te waaieren **naar bepaalde** geografische locaties</span><span class="sxs-lookup"><span data-stu-id="6c73d-239">Sample GET request to fan out to **some** geo locations</span></span>

```http
https:// \<tenant\>/\_api/search/query?querytext='site'&ClientType='my_client_id'&Properties='EnableMultiGeoSearch:true, MultiGeoSearchConfiguration:[{DataLocation\\:"NAM"\\,Endpoint\\:"https\\://contosoNAM.sharepoint.com"\\,SourceId\\:"B81EAB55-3140-4312-B0F4-9459D1B4FFEE"}\\,{DataLocation\\:"CAN"\\,Endpoint\\:"https\\://contosoCAN.sharepoint-df.com"}]'
```

> [!NOTE]
> <span data-ttu-id="6c73d-240">Komma's en dubbele puntpunten in de lijst met geografische locaties voor de eigenschap MultiGeoSearchConfiguration worden voorafgegaan door het **backslash-teken.**</span><span class="sxs-lookup"><span data-stu-id="6c73d-240">Commas and colons in the list of geo locations for the MultiGeoSearchConfiguration property are preceded by the **backslash** character.</span></span> <span data-ttu-id="6c73d-241">Dit komt omdat get-aanvragen dubbele punten gebruiken om eigenschappen en komma's te scheiden om argumenten van eigenschappen te scheiden.</span><span class="sxs-lookup"><span data-stu-id="6c73d-241">This is because GET requests use colons to separate properties and commas to separate arguments of properties.</span></span> <span data-ttu-id="6c73d-242">Zonder de backslash als een escape-teken wordt de eigenschap MultiGeoSearchConfiguration verkeerd geïnterpreteerd.</span><span class="sxs-lookup"><span data-stu-id="6c73d-242">Without the backslash as an escape character, the MultiGeoSearchConfiguration property is interpreted wrongly.</span></span>

#### <a name="sample-post-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="6c73d-243">Voorbeeld van een POST-aanvraag die is uitgewaakt naar **alle** geografische locaties</span><span class="sxs-lookup"><span data-stu-id="6c73d-243">Sample POST request that's fanned out to **all** geo locations</span></span>

```http
    {
    "request": {
            "__metadata": {
            "type": "Microsoft.Office.Server.Search.REST.SearchRequest"
        },
        "Querytext": "sharepoint",
        "Properties": {
            "results": [
                {
                    "Name": "EnableMultiGeoSearch",
                    "Value": {
                        "QueryPropertyValueTypeIndex": 3,
                        "BoolVal": true
                    }
                }
            ]
        },
        "ClientType": "my_client_id"
        }
    }
```

#### <a name="sample-post-request-thats-fanned-out-to-some-geo-locations"></a><span data-ttu-id="6c73d-244">Voorbeeld van een POST-aanvraag die is uitgewaakt naar **bepaalde** geografische locaties</span><span class="sxs-lookup"><span data-stu-id="6c73d-244">Sample POST request that's fanned out to **some** geo locations</span></span>

```http
    {
        "request": {
            "Querytext": "SharePoint",
            "ClientType": "my_client_id",
            "Properties": {
                "results": [
                    {
                        "Name": "EnableMultiGeoSearch",
                        "Value": {
                            "QueryPropertyValueTypeIndex": 3,
                            "BoolVal": true
                        }
                    },
                    {
                        "Name": "MultiGeoSearchConfiguration",
                        "Value": {
                        "StrVal": "[{\"DataLocation\":\"NAM\",\"Endpoint\":\"https://contoso.sharepoint.com\",\"SourceId\":\"B81EAB55-3140-4312-B0F4-9459D1B4FFEE\"},{\"DataLocation\":\"CAN\",\"Endpoint\":\"https://contosoCAN.sharepoint.com\"}]",
                            "QueryPropertyValueTypeIndex": 1
                        }
                    }
                ]
            }
        }
    }
```

### <a name="query-using-csom"></a><span data-ttu-id="6c73d-245">Query met behulp van CSOM</span><span class="sxs-lookup"><span data-stu-id="6c73d-245">Query using CSOM</span></span>

<span data-ttu-id="6c73d-246">Hier is een voorbeeld van een CSOM-query die is uitgewaakt naar **alle** geografische locaties:</span><span class="sxs-lookup"><span data-stu-id="6c73d-246">Here's a sample CSOM query that's fanned out to **all** geo locations:</span></span>

```CSOM
var keywordQuery = new KeywordQuery(ctx);
keywordQuery.QueryText = query.SearchQueryText;
keywordQuery.ClientType = <enter a string here>;
keywordQuery.Properties["EnableMultiGeoSearch"] = true;
```
