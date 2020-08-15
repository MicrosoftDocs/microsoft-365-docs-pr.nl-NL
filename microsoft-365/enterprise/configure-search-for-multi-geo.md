---
title: Zoekfunctie configureren voor Microsoft 365 multi-geo
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
description: Meer informatie over het configureren van de zoekfunctie in een omgeving met meerdere geografische omgevingen. Slechts sommige klanten, zoals OneDrive voor bedrijven, kunnen resultaten retourneren in een omgeving met meerdere geografische omgevingen.
ms.openlocfilehash: 22c71661e8f3b643a1fd7afa33b38584a1cd1be5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695059"
---
# <a name="configure-search-for-microsoft-365-multi-geo"></a><span data-ttu-id="cd751-104">Zoekfunctie configureren voor Microsoft 365 multi-geo</span><span class="sxs-lookup"><span data-stu-id="cd751-104">Configure Search for Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="cd751-105">In een omgeving met meerdere geografische locaties heeft elke geografische locatie een eigen zoekindex en een zoekcentrum.</span><span class="sxs-lookup"><span data-stu-id="cd751-105">In a multi-geo environment, each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="cd751-106">Wanneer een gebruiker zoekt, is de query fanned naar alle indexen en worden de geretourneerde resultaten samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="cd751-106">When a user searches, the query is fanned out to all the indexes, and the returned results are merged.</span></span>

<span data-ttu-id="cd751-107">Een gebruiker in een geografische locatie kan bijvoorbeeld zoeken naar inhoud die is opgeslagen op een andere geografische locatie of voor inhoud op een SharePoint-site die is beperkt tot een andere geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="cd751-107">For example, a user in one geo location can search for content stored in another geo location, or for content on a SharePoint site that's restricted to a different geo location.</span></span> <span data-ttu-id="cd751-108">Als de gebruiker toegang heeft tot deze inhoud, wordt het resultaat weergegeven in de zoekfunctie.</span><span class="sxs-lookup"><span data-stu-id="cd751-108">If the user has access to this content, search will show the result.</span></span>

## <a name="which-search-clients-work-in-a-multi-geo-environment"></a><span data-ttu-id="cd751-109">Welke Zoek clients werken in een omgeving met meerdere geografische omgevingen?</span><span class="sxs-lookup"><span data-stu-id="cd751-109">Which search clients work in a multi-geo environment?</span></span>

<span data-ttu-id="cd751-110">Deze clients kunnen resultaten van alle geografische locaties retourneren:</span><span class="sxs-lookup"><span data-stu-id="cd751-110">These clients can return results from all geo locations:</span></span>

-   <span data-ttu-id="cd751-111">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="cd751-111">OneDrive for Business</span></span>

-   <span data-ttu-id="cd751-112">Delve</span><span class="sxs-lookup"><span data-stu-id="cd751-112">Delve</span></span>

-   <span data-ttu-id="cd751-113">De SharePoint-Startpagina</span><span class="sxs-lookup"><span data-stu-id="cd751-113">The SharePoint home page</span></span>

-   <span data-ttu-id="cd751-114">Het zoekcentrum</span><span class="sxs-lookup"><span data-stu-id="cd751-114">The Search Center</span></span>

-   <span data-ttu-id="cd751-115">Aangepaste zoektoepassingen die gebruikmaken van de zoek-API van SharePoint</span><span class="sxs-lookup"><span data-stu-id="cd751-115">Custom search applications that use the SharePoint Search API</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="cd751-116">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="cd751-116">OneDrive for Business</span></span>

<span data-ttu-id="cd751-117">Zodra de multifunctionele omgeving is ingesteld, krijgen gebruikers die zoeken in OneDrive resultaten van alle geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="cd751-117">As soon as the multi-geo environment has been set up, users that search in OneDrive get results from all geo locations.</span></span>

### <a name="delve"></a><span data-ttu-id="cd751-118">Delve</span><span class="sxs-lookup"><span data-stu-id="cd751-118">Delve</span></span>

<span data-ttu-id="cd751-119">Zodra de multifunctionele omgeving is ingesteld, krijgen gebruikers die zoeken in Delve resultaten van alle geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="cd751-119">As soon as the multi-geo environment has been set up, users that search in Delve get results from all geo locations.</span></span>

<span data-ttu-id="cd751-120">De feed voor Delve en de profielkaart geven alleen voorbeelden weer van bestanden die zijn opgeslagen op de centrale locatie.</span><span class="sxs-lookup"><span data-stu-id="cd751-120">The Delve feed and the profile card only show previews of files that are stored in the central location.</span></span> <span data-ttu-id="cd751-121">Voor bestanden die zijn opgeslagen op satelliet locaties, wordt in plaats hiervan het pictogram voor het bestandstype weergegeven.</span><span class="sxs-lookup"><span data-stu-id="cd751-121">For files that are stored in satellite locations, the icon for the file type is shown instead.</span></span>

### <a name="the-sharepoint-home-page"></a><span data-ttu-id="cd751-122">De SharePoint-Startpagina</span><span class="sxs-lookup"><span data-stu-id="cd751-122">The SharePoint home page</span></span>

<span data-ttu-id="cd751-123">Zodra de multi-geografische omgeving is ingesteld, zien gebruikers nieuws, recente en gevolgde sites van meerdere geo-locaties op de startpagina van SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cd751-123">As soon as the multi-geo environment has been set up, users will see news, recent and followed sites from multiple geo locations on their SharePoint home page.</span></span> <span data-ttu-id="cd751-124">Als ze het zoekvak op de SharePoint-startpagina gebruiken, krijgen ze samenvoegresultaten van meerdere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="cd751-124">If they use the search box on the SharePoint home page, they'll get merged results from multiple geo locations.</span></span>

### <a name="the-search-center"></a><span data-ttu-id="cd751-125">Het zoekcentrum</span><span class="sxs-lookup"><span data-stu-id="cd751-125">The Search Center</span></span>

<span data-ttu-id="cd751-126">Nadat de omgeving met meerdere geografische omgevingen is ingesteld, blijft elk zoekcentrum alleen resultaten van de eigen geografische locatie weergeven.</span><span class="sxs-lookup"><span data-stu-id="cd751-126">After the multi-geo environment has been set up, each Search Center continues to only show results from their own geo location.</span></span> <span data-ttu-id="cd751-127">Beheerders moeten [de instellingen van een zoekcentrum wijzigen](#_Set_up_a_1) om resultaten op te doen van alle geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="cd751-127">Admins must [change the settings of each Search Center](#_Set_up_a_1) to get results from all geo locations.</span></span> <span data-ttu-id="cd751-128">Gebruikers die zoeken in het zoekcentrum krijgen vervolgens resultaten van alle geo-locaties.</span><span class="sxs-lookup"><span data-stu-id="cd751-128">Afterwards, users that search in the Search Center get results from all geo locations.</span></span>

### <a name="custom-search-applications"></a><span data-ttu-id="cd751-129">Aangepaste zoektoepassingen</span><span class="sxs-lookup"><span data-stu-id="cd751-129">Custom search applications</span></span>

<span data-ttu-id="cd751-130">Zoals gebruikelijk werken aangepaste zoektoepassingen interactie met de zoekindexen met behulp van de bestaande SharePoint Search REST-Api's.</span><span class="sxs-lookup"><span data-stu-id="cd751-130">As usual, custom search applications interact with the search indexes by using the existing SharePoint Search REST APIs.</span></span> <span data-ttu-id="cd751-131">Voor het ophalen van resultaten van alle of van een aantal geografische locaties moet de toepassing [de API aanroepen en de nieuwe parameters voor meervoudige geo-query's opnemen](#_Get_custom_search) in de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="cd751-131">To get results from all, or some geo locations, the application must [call the API and include the new Multi-Geo query parameters](#_Get_custom_search) in the request.</span></span> <span data-ttu-id="cd751-132">Dit veroorzaakt een ventilator uit de query voor alle geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="cd751-132">This triggers a fan out of the query to all geo locations.</span></span>

## <a name="whats-different-about-search-in-a-multi-geo-environment"></a><span data-ttu-id="cd751-133">Wat is er anders in een zoekopdracht in een multi-geografische omgeving?</span><span class="sxs-lookup"><span data-stu-id="cd751-133">What's different about search in a multi-geo environment?</span></span>

<span data-ttu-id="cd751-134">Sommige zoekfuncties die u mogelijk kent, werken anders in een omgeving met meerdere geografische gebieden.</span><span class="sxs-lookup"><span data-stu-id="cd751-134">Some search features you might be familiar with, work differently in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cd751-135"><strong>Functie</strong></span><span class="sxs-lookup"><span data-stu-id="cd751-135"><strong>Feature</strong></span></span></th>
<th align="left"><span data-ttu-id="cd751-136"><strong>Werking</strong></span><span class="sxs-lookup"><span data-stu-id="cd751-136"><strong>How it works</strong></span></span></th>
<th align="left"><span data-ttu-id="cd751-137"><strong>Tijdelijke oplossing</strong></span><span class="sxs-lookup"><span data-stu-id="cd751-137"><strong>Workaround</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="cd751-138">Bevorderde resultaten</span><span class="sxs-lookup"><span data-stu-id="cd751-138">Promoted results</span></span></td>
<td align="left"><span data-ttu-id="cd751-139">U kunt op verschillende niveaus queryregels met gepromoveerde resultaten maken: voor de volledige Tenant, voor een siteverzameling of voor een site.</span><span class="sxs-lookup"><span data-stu-id="cd751-139">You can create query rules with promoted results at different levels: for the whole tenant, for a site collection, or for a site.</span></span> <span data-ttu-id="cd751-140">In een omgeving met meerdere geografische niveaus definieert u gepromoveerde resultaten op tenantniveau, zodat de resultaten van de zoek centrums in alle geografische locaties worden bevorderd.</span><span class="sxs-lookup"><span data-stu-id="cd751-140">In a multi-geo environment, define promoted results at the tenant level to promote the results to the Search Centers in all geo locations.</span></span> <span data-ttu-id="cd751-141">Als u alleen de resultaten in het zoekcentrum op de geografische locatie van de siteverzameling of site wilt promoveren, definieert u de bevorderde resultaten op siteverzameling of siteniveau.</span><span class="sxs-lookup"><span data-stu-id="cd751-141">If you only want to promote results in the Search Center that's in the geo location of the site collection or site, define the promoted results at the site collection or site level.</span></span> <span data-ttu-id="cd751-142">Deze resultaten worden niet bevorderd in andere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="cd751-142">These results are not promoted in other geo locations.</span></span></td>
<td align="left"><span data-ttu-id="cd751-143">Als u geen verschillende gepromoveerde resultaten per geografische locatie nodig hebt, zoals voor het reizen, raden we u aan om gepromoveerde resultaten op tenantniveau te definiëren.</span><span class="sxs-lookup"><span data-stu-id="cd751-143">If you don't need different promoted results per geo location, for example different rules for traveling, we recommend defining promoted results at the tenant level.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cd751-144">Verfijningen zoeken</span><span class="sxs-lookup"><span data-stu-id="cd751-144">Search refiners</span></span></td>
<td align="left"><span data-ttu-id="cd751-145">De zoekfunctie levert verfijningen op van alle geo-locaties van een Tenant en voegt deze vervolgens samen.</span><span class="sxs-lookup"><span data-stu-id="cd751-145">Search returns refiners from all the geo locations of a tenant and then aggregates them.</span></span> <span data-ttu-id="cd751-146">De aggregatie is een beste manier, wat betekent dat het aantal verfijningen mogelijk niet 100% nauwkeurig is.</span><span class="sxs-lookup"><span data-stu-id="cd751-146">The aggregation is a best effort, meaning that the refiner counts might not be 100% accurate.</span></span> <span data-ttu-id="cd751-147">Voor de meeste met een zoekopdracht gebaseerde scenario's is deze nauwkeurigheid voldoende.</span><span class="sxs-lookup"><span data-stu-id="cd751-147">For most search-driven scenarios, this accuracy is sufficient.</span></span> 
</td>
<td align="left"><span data-ttu-id="cd751-148">Voor toepassingen met een zoekopdracht die afhankelijk zijn van de voltooiing van het verfijnen, voert u een query uit op elke geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="cd751-148">For search-driven applications that depend on refiner completeness, query each geo location independently.</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><span data-ttu-id="cd751-149">De zoekfunctie voor meervoudige geo biedt geen ondersteuning voor dynamische buckets voor numerieke verfijningen.</span><span class="sxs-lookup"><span data-stu-id="cd751-149">Multi-geo search doesn't support dynamic bucketing for numerical refiners.</span></span></td>
<td align="left"><span data-ttu-id="cd751-150">Gebruik de <a href="https://docs.microsoft.com/sharepoint/dev/general-development/query-refinement-in-sharepoint">parameter ' Discretize '</a> voor numerieke verfijningen.</span><span class="sxs-lookup"><span data-stu-id="cd751-150">Use the <a href="https://docs.microsoft.com/sharepoint/dev/general-development/query-refinement-in-sharepoint">"Discretize" parameter</a> for numerical refiners.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cd751-151">Document-Id's</span><span class="sxs-lookup"><span data-stu-id="cd751-151">Document IDs</span></span></td>
<td align="left"><span data-ttu-id="cd751-152">Houd er rekening mee dat document-Id's in een omgeving met meerdere geografische locaties niet uniek zijn voor geografische locaties als u een zoekopdracht wilt ontwikkelen die afhankelijk is van document-Id's.</span><span class="sxs-lookup"><span data-stu-id="cd751-152">If you're developing a search-driven application that depends on document IDs, note that document IDs in a multi-geo environment aren't unique across geo locations, they are unique per geo location.</span></span></td>
<td align="left"><span data-ttu-id="cd751-153">Er is een kolom toegevoegd waarin de geografische locatie wordt aangegeven.</span><span class="sxs-lookup"><span data-stu-id="cd751-153">We've added a column that identifies the geo location.</span></span> <span data-ttu-id="cd751-154">Gebruik deze kolom om unieke mogelijkheden te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="cd751-154">Use this column to achieve uniqueness.</span></span> <span data-ttu-id="cd751-155">Deze kolom heeft de naam GeoLocationSource.</span><span class="sxs-lookup"><span data-stu-id="cd751-155">This column is named "GeoLocationSource".</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cd751-156">Aantal resultaten</span><span class="sxs-lookup"><span data-stu-id="cd751-156">Number of results</span></span></td>
<td align="left"><span data-ttu-id="cd751-157">Op de pagina met zoekresultaten worden gecombineerde resultaten van de geo-locaties weergegeven, maar het is niet mogelijk om meer 500 resultaten te bereiken.</span><span class="sxs-lookup"><span data-stu-id="cd751-157">The search results page shows combined results from the geo locations, but it's not possible to page beyond 500 results.</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cd751-158">Hybride zoeken</span><span class="sxs-lookup"><span data-stu-id="cd751-158">Hybrid search</span></span></td>
<td align="left"><span data-ttu-id="cd751-159">In een hybride SharePoint-omgeving met <a href="https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">hybride zoeken</a>voor de Cloud wordt on-premises inhoud toegevoegd aan de microsoft 365-index van de centrale locatie.</span><span class="sxs-lookup"><span data-stu-id="cd751-159">In a hybrid SharePoint environment with <a href="https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">cloud hybrid search</a>,  on-premises content is added to the Microsoft 365 index of the central location.</span></span></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="whats-not-supported-for-search-in-a-multi-geo-environment"></a><span data-ttu-id="cd751-160">Wat wordt er niet ondersteund voor zoeken in een multi-geografische omgeving?</span><span class="sxs-lookup"><span data-stu-id="cd751-160">What's not supported for search in a multi-geo environment?</span></span>

<span data-ttu-id="cd751-161">Een aantal van de zoekfuncties die u mogelijk kent, wordt niet ondersteund in een omgeving met meerdere geografische omgevingen.</span><span class="sxs-lookup"><span data-stu-id="cd751-161">Some of the search features you might be familiar with, aren't supported in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cd751-162"><strong>Zoekfunctie</strong></span><span class="sxs-lookup"><span data-stu-id="cd751-162"><strong>Search feature</strong></span></span></th>
<th align="left"><span data-ttu-id="cd751-163"><strong>Ziet</strong></span><span class="sxs-lookup"><span data-stu-id="cd751-163"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="cd751-164">Verificatie via app</span><span class="sxs-lookup"><span data-stu-id="cd751-164">App-only authentication</span></span></td>
<td align="left"><span data-ttu-id="cd751-165">Verificatie via een app (geprivilegieerde toegang van Services) wordt niet ondersteund in meerdere geo-zoekopdrachten.</span><span class="sxs-lookup"><span data-stu-id="cd751-165">App-only authentication (privileged access from services) isn't supported in multi-geo search.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cd751-166">Gastgebruikers</span><span class="sxs-lookup"><span data-stu-id="cd751-166">Guest users</span></span></td>
<td align="left"><span data-ttu-id="cd751-167">Gastgebruikers krijgen alleen resultaten van de geografische locatie waarnaar ze zoeken.</span><span class="sxs-lookup"><span data-stu-id="cd751-167">Guest users only get results from the geo location that they're searching from.</span></span></td>
</tr>
</tbody>
</table>

## <a name="how-does-search-work-in-a-multi-geo-environment"></a><span data-ttu-id="cd751-168">Hoe werkt zoeken in een omgeving met meerdere geografische gebieden?</span><span class="sxs-lookup"><span data-stu-id="cd751-168">How does search work in a multi-geo environment?</span></span>

<span data-ttu-id="cd751-169">Alle zoek clients gebruiken de bestaande SharePoint Search REST-Api's om te werken met de zoekindexen.</span><span class="sxs-lookup"><span data-stu-id="cd751-169">All the search clients use the existing SharePoint Search REST APIs to interact with the search indexes.</span></span>

<img src="../media/configure-search-for-multi-geo-image1-1.png" />

1. <span data-ttu-id="cd751-170">Een zoekopdracht roept het eindpunt van de zoek REST aan met de queryeigenschap EnableMultiGeoSearch = True.</span><span class="sxs-lookup"><span data-stu-id="cd751-170">A search client calls the Search REST endpoint with the query property EnableMultiGeoSearch= true.</span></span>
2. <span data-ttu-id="cd751-171">De query wordt verzonden naar alle geografische locaties in de Tenant.</span><span class="sxs-lookup"><span data-stu-id="cd751-171">The query is sent to all geo locations in the tenant.</span></span>
3. <span data-ttu-id="cd751-172">De zoekresultaten van de geografische locatie worden samengevoegd en geclassificeerd.</span><span class="sxs-lookup"><span data-stu-id="cd751-172">Search results from each geo location are merged and ranked.</span></span>
4. <span data-ttu-id="cd751-173">De client ontvangt Unified Search Results.</span><span class="sxs-lookup"><span data-stu-id="cd751-173">The client gets unified search results.</span></span>



<span data-ttu-id="cd751-174"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>De zoekresultaten worden niet samengevoegd totdat we resultaten van alle geografische locaties hebben ontvangen.</span><span class="sxs-lookup"><span data-stu-id="cd751-174"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Notice that we don't merge the search results until we've received results from all the geo locations.</span></span> <span data-ttu-id="cd751-175">Dit betekent dat er in meerdere geo-zoekopdrachten een extra latentie heeft vergeleken met zoekopdrachten in een omgeving met maar één geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="cd751-175">This means that multi-geo searches have additional latency compared to searches in an environment with only one geo location.</span></span>

<span id="_Set_up_a_1" class="anchor"><span id="_Ref505252370" class="anchor"></span></span>
## <a name="get-a-search-center-to-show-results-from-all-geo-locations"></a><span data-ttu-id="cd751-176">Een zoekcentrum weergeven om resultaten van alle geografische locaties weer te geven</span><span class="sxs-lookup"><span data-stu-id="cd751-176">Get a Search Center to show results from all geo locations</span></span>

<span data-ttu-id="cd751-177">Elk zoekcentrum heeft diverse verticaal en u moet elke verticaal apart instellen.</span><span class="sxs-lookup"><span data-stu-id="cd751-177">Each Search Center has several verticals and you have to set up each vertical individually.</span></span>

1.  <span data-ttu-id="cd751-178">Zorg ervoor dat u deze stappen uitvoert met een account dat gemachtigd is om de pagina met zoekresultaten en het webonderdeel zoekresultaten te bewerken.</span><span class="sxs-lookup"><span data-stu-id="cd751-178">Ensure that you perform these steps with an account that has permission to edit the search results page and the Search Result Web Part.</span></span>

2.  <span data-ttu-id="cd751-179">Ga naar de pagina met zoekresultaten (Zie de [lijst](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) met pagina's met zoekresultaten).</span><span class="sxs-lookup"><span data-stu-id="cd751-179">Navigate to the search results page (see the [list](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) of search results pages)</span></span>

3.  <span data-ttu-id="cd751-180">Selecteer de verticaal die u wilt instellen, klik op het tandwiel pictogram **instellingen** in de rechterbovenhoek en klik vervolgens op **pagina bewerken**.</span><span class="sxs-lookup"><span data-stu-id="cd751-180">Select the vertical to set up, click **Settings** gear icon in the upper, right corner, and then click **Edit Page**.</span></span> <span data-ttu-id="cd751-181">De pagina met zoekresultaten wordt geopend in de bewerkingsmodus.</span><span class="sxs-lookup"><span data-stu-id="cd751-181">The search results page opens in Edit mode.</span></span>

     ![](../media/configure-search-for-multi-geo-image2.png)
1.  <span data-ttu-id="cd751-182">In het webonderdeel Zoekresultaten plaatst u de aanwijzer in de rechterbovenhoek van het webonderdeel, klikt u op de pijl en klikt u vervolgens op **webonderdeel bewerken** in het menu.</span><span class="sxs-lookup"><span data-stu-id="cd751-182">In the Search Results Web Part, move the pointer to the upper, right corner of the web part, click the arrow, and then click **Edit Web Part** on the menu.</span></span> <span data-ttu-id="cd751-183">Het taakvenster van het webonderdeel Zoekresultaten wordt geopend onder het lint in de rechterbovenhoek van de pagina.</span><span class="sxs-lookup"><span data-stu-id="cd751-183">The Search Results Web Part tool pane opens under the ribbon in the top right of the page.</span></span> ![](../media/configure-search-for-multi-geo-image3.png)

1.  <span data-ttu-id="cd751-184">Selecteer in het taakvenster van het webonderdeel, in de sectie **instellingen** , onder **instellingen voor besturingselementen voor resultaten**de optie **Meervoudige geografische resultaten weergeven** om het webonderdeel zoekresultaten weer te geven voor resultaten van alle geo-locaties.</span><span class="sxs-lookup"><span data-stu-id="cd751-184">In the Web Part tool pane, in the **Settings** section, under **Results control settings**, select **Show Multi-Geo results** to get the Search Results Web Part to show results from all geo locations.</span></span>

2.  <span data-ttu-id="cd751-185">Klik op **OK** om uw wijzigingen op te slaan en het taakvenster van het webonderdeel te sluiten.</span><span class="sxs-lookup"><span data-stu-id="cd751-185">Click **OK** to save your change and close the Web Part tool pane.</span></span>

3.  <span data-ttu-id="cd751-186">Controleer de wijzigingen in het webonderdeel zoekresultaten door te klikken op **inchecken** op het tabblad pagina van het hoofdmenu.</span><span class="sxs-lookup"><span data-stu-id="cd751-186">Check your changes to the Search Results Web Part by clicking **Check-In** on the Page tab of the main menu.</span></span>

4.  <span data-ttu-id="cd751-187">Publiceer de wijzigingen via de koppeling die is opgenomen in de notitie boven aan de pagina.</span><span class="sxs-lookup"><span data-stu-id="cd751-187">Publish the changes by using the link provided in the note at the top of the page.</span></span>

<span id="_Get_custom_search" class="anchor"><span id="_Ref501388387" class="anchor"></span></span>
## <a name="get-custom-search-applications-to-show-results-from-all-or-some-geo-locations"></a><span data-ttu-id="cd751-188">Aangepaste zoektoepassingen aanvragen voor het weergeven van resultaten van alle of een aantal geografische locaties</span><span class="sxs-lookup"><span data-stu-id="cd751-188">Get custom search applications to show results from all or some geo locations</span></span>

<span data-ttu-id="cd751-189">Aangepaste zoektoepassingen resulteren in resultaten van alle of enkele geo-locaties door parameters op te geven, met de aanvraag voor de REST van de SharePoint Search REST-API.</span><span class="sxs-lookup"><span data-stu-id="cd751-189">Custom search applications get results from all, or some, geo locations by specifying query parameters with the request to the SharePoint Search REST API.</span></span><span data-ttu-id="cd751-190">Afhankelijk van de parameters van de query is de query fanned naar alle geografische locaties of naar een aantal geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="cd751-190"> Depending on the query parameters, the query is fanned out to all geo locations, or to some geo locations.</span></span> <span data-ttu-id="cd751-191">Als u bijvoorbeeld alleen een subset van geografische locaties hoeft te doorzoeken om relevante informatie te vinden, kunt u de waaier slechts voor deze elementen regelen.</span><span class="sxs-lookup"><span data-stu-id="cd751-191">For example, if you only need to query a subset of geo locations to find relevant information, you can control the fan out to only these.</span></span> <span data-ttu-id="cd751-192">Als het verzoek slaagt, levert de REST van de SharePoint-Zoek REST-API antwoordgegevens op.</span><span class="sxs-lookup"><span data-stu-id="cd751-192">If the request succeeds, the SharePoint Search REST API returns response data.</span></span>

<span data-ttu-id="cd751-193">**Vereiste**</span><span class="sxs-lookup"><span data-stu-id="cd751-193">**Requirement**</span></span>

<span data-ttu-id="cd751-194">Voor elke geografische locatie moet u ervoor zorgen dat alle gebruikers in de organisatie het machtigingsniveau **lezen** voor de hoofdwebsite hebben gekregen (bijvoorbeeld contoso**APAC**. SharePoint.com/en contoso**EU**. SharePoint.com/).</span><span class="sxs-lookup"><span data-stu-id="cd751-194">For each geo location, you must ensure that all users in the organization have been granted the **Read** permission level for the root website (for example contoso**APAC**.sharepoint.com/ and contoso**EU**.sharepoint.com/).</span></span> <span data-ttu-id="cd751-195">[Meer informatie over machtigingen](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).</span><span class="sxs-lookup"><span data-stu-id="cd751-195">[Learn about permissions](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).</span></span>

### <a name="query-parameters"></a><span data-ttu-id="cd751-196">Query parameters</span><span class="sxs-lookup"><span data-stu-id="cd751-196">Query parameters</span></span>

<span data-ttu-id="cd751-197">EnableMultiGeoSearch: dit is een Booleaanse waarde die aangeeft of de query moet worden fanned naar de indexen van andere geografische locaties van de multigeo-Tenant.</span><span class="sxs-lookup"><span data-stu-id="cd751-197">EnableMultiGeoSearch - This is a Boolean value that specifies whether the query shall be fanned out to the indexes of other geo locations of the multi-geo tenant.</span></span> <span data-ttu-id="cd751-198">Stel deze in op **waar** om de query uit te waaieren. **Onwaar** om de query niet uit te waaieren.</span><span class="sxs-lookup"><span data-stu-id="cd751-198">Set it to **true** to fan out the query; **false** to not fan out the query.</span></span> <span data-ttu-id="cd751-199">Als u deze parameter niet opneemt, is de standaardwaarde **Onwaar**, behalve wanneer u een rest API-oproep maakt voor een site die gebruikmaakt van de sjabloon Enterprise Search Center, in dit geval de standaardwaarde **waar**is.</span><span class="sxs-lookup"><span data-stu-id="cd751-199">If you don't include this parameter, the default value is **false**, except when making a REST API call against a site which uses the Enterprise Search Center template, in this case the default value is **true**.</span></span> <span data-ttu-id="cd751-200">Als u de parameter in een omgeving gebruikt die geen deel uitmaakt van meerdere geografische regels, wordt de parameter genegeerd.</span><span class="sxs-lookup"><span data-stu-id="cd751-200">If you use the parameter in an environment that isn't multi-geo, the parameter is ignored.</span></span>

<span data-ttu-id="cd751-201">ClientType: dit is een tekenreeks.</span><span class="sxs-lookup"><span data-stu-id="cd751-201">ClientType - This is a string.</span></span> <span data-ttu-id="cd751-202">Voer voor elke zoektoepassing een unieke naam voor de client in.</span><span class="sxs-lookup"><span data-stu-id="cd751-202">Enter a unique client name for each search application.</span></span> <span data-ttu-id="cd751-203">Als u deze parameter niet opneemt, is de query niet fanned naar andere geo-locaties.</span><span class="sxs-lookup"><span data-stu-id="cd751-203">If you don't include this parameter, the query is not fanned out to other geo locations.</span></span>

<span data-ttu-id="cd751-204">MultiGeoSearchConfiguration: dit is een optionele lijst met de geografische locaties in de Tenant Tenant om de query uit te waaieren op als **EnableMultiGeoSearch** **waar**is.</span><span class="sxs-lookup"><span data-stu-id="cd751-204">MultiGeoSearchConfiguration - This is an optional list of which geo locations in the multi-geo tenant to fan the query out to when **EnableMultiGeoSearch** is **true**.</span></span> <span data-ttu-id="cd751-205">Als u deze parameter niet opneemt of leeg laat, is de query fanned naar alle geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="cd751-205">If you don't include this parameter, or leave it blank, the query is fanned out to all geo locations.</span></span> <span data-ttu-id="cd751-206">Voor elke geografische locatie voert u de volgende items in, in JSON-indeling:</span><span class="sxs-lookup"><span data-stu-id="cd751-206">For each geo location, enter the following items, in JSON format:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cd751-207">Item</span><span class="sxs-lookup"><span data-stu-id="cd751-207">Item</span></span></th>
<th align="left"><span data-ttu-id="cd751-208">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="cd751-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="cd751-209">DataLocation</span><span class="sxs-lookup"><span data-stu-id="cd751-209">DataLocation</span></span></td>
<td align="left"><span data-ttu-id="cd751-210">De geografische locatie van bijvoorbeeld de vestiging.</span><span class="sxs-lookup"><span data-stu-id="cd751-210">The geo location, for example NAM.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cd751-211">Conversatie</span><span class="sxs-lookup"><span data-stu-id="cd751-211">EndPoint</span></span></td>
<td align="left"><span data-ttu-id="cd751-212">Het eindpunt waarmee u verbinding wilt maken, bijvoorbeeld https://contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="cd751-212">The endpoint to connect to, for example https://contoso.sharepoint.com</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="cd751-213">Id</span><span class="sxs-lookup"><span data-stu-id="cd751-213">SourceId</span></span></td>
<td align="left"><span data-ttu-id="cd751-214">De GUID van de resultatenbron, bijvoorbeeld B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span><span class="sxs-lookup"><span data-stu-id="cd751-214">The GUID of the result source, for example B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cd751-215">Als u DataLocation of eindpunt weglaat, of als een DataLocation wordt gedupliceerd, mislukt de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="cd751-215">If you omit DataLocation or EndPoint, or if a DataLocation is duplicated, the request fails.</span></span> <span data-ttu-id="cd751-216">[U vindt informatie over het eindpunt van de geografische locaties van een Tenant met behulp van Microsoft Graph](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-discovery).</span><span class="sxs-lookup"><span data-stu-id="cd751-216">[You can get information about the endpoint of a tenant's geo locations by using Microsoft Graph](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-discovery).</span></span>

### <a name="response-data"></a><span data-ttu-id="cd751-217">Antwoordgegevens</span><span class="sxs-lookup"><span data-stu-id="cd751-217">Response data</span></span>

<span data-ttu-id="cd751-218">MultiGeoSearchStatus: dit is een eigenschap die de SharePoint-zoek-API retourneert in antwoord op een aanvraag.</span><span class="sxs-lookup"><span data-stu-id="cd751-218">MultiGeoSearchStatus – This is a property that the SharePoint Search API returns in response to a request.</span></span> <span data-ttu-id="cd751-219">De waarde van de eigenschap is een tekenreeks die de volgende informatie oplevert over de resultaten die de SharePoint-zoek-API retourneert:</span><span class="sxs-lookup"><span data-stu-id="cd751-219">The value of the property is a string and gives the following information about the results that the SharePoint Search API returns:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cd751-220">Value</span><span class="sxs-lookup"><span data-stu-id="cd751-220">Value</span></span></th>
<th align="left"><span data-ttu-id="cd751-221">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="cd751-221">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="cd751-222">Vol</span><span class="sxs-lookup"><span data-stu-id="cd751-222">Full</span></span></td>
<td align="left"><span data-ttu-id="cd751-223">Volledige resultaten van <strong>alle</strong> geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="cd751-223">Full results from <strong>all</strong> the geo locations.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="cd751-224">Partijdig</span><span class="sxs-lookup"><span data-stu-id="cd751-224">Partial</span></span></td>
<td align="left"><span data-ttu-id="cd751-225">Gedeeltelijke resultaten van een of meer geo-locaties.</span><span class="sxs-lookup"><span data-stu-id="cd751-225">Partial results from one or more geo locations.</span></span> <span data-ttu-id="cd751-226">De resultaten zijn onvolledig vanwege een tijdelijke fout.</span><span class="sxs-lookup"><span data-stu-id="cd751-226">The results are incomplete due to a transient error.</span></span></td>
</tr>

</tbody>
</table>

### <a name="query-using-the-rest-service"></a><span data-ttu-id="cd751-227">Query met behulp van de REST dienst</span><span class="sxs-lookup"><span data-stu-id="cd751-227">Query using the REST service</span></span>

<span data-ttu-id="cd751-228">Met een aanvraag voor ophalen geeft u de queryparameters op in de URL.</span><span class="sxs-lookup"><span data-stu-id="cd751-228">With a GET request, you specify the query parameters in the URL.</span></span> <span data-ttu-id="cd751-229">Met een bericht na een bericht geeft u de queryparameters in de hoofdtekst in de JSON-indeling (Object Notation) door.</span><span class="sxs-lookup"><span data-stu-id="cd751-229">With a POST request, you pass the query parameters in the body in JavaScript Object Notation (JSON) format.</span></span>


#### <a name="request-headers"></a><span data-ttu-id="cd751-230">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="cd751-230">Request headers</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cd751-231">Name</span><span class="sxs-lookup"><span data-stu-id="cd751-231">Name</span></span></th>
<th align="left"><span data-ttu-id="cd751-232">Value</span><span class="sxs-lookup"><span data-stu-id="cd751-232">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="cd751-233">Inhouds type</span><span class="sxs-lookup"><span data-stu-id="cd751-233">Content-Type</span></span></td>
<td align="left"><span data-ttu-id="cd751-234">application/json; odata = uitgebreid</span><span class="sxs-lookup"><span data-stu-id="cd751-234">application/json;odata=verbose</span></span></td>
</tr>
</tbody>
</table>

#### <a name="sample-get-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="cd751-235">Voorbeeld van een aanvraag voor het aanvragen van fanned naar **alle** geo-locaties</span><span class="sxs-lookup"><span data-stu-id="cd751-235">Sample GET request that's fanned out to **all** geo locations</span></span>

<span data-ttu-id="cd751-236">https:// \<tenant\> / \_ API/search/query? QueryText = ' SharePoint ' &Properties = ' EnableMultiGeoSearch: True ' &ClientType = ' mijn \_ client \_ -id '</span><span class="sxs-lookup"><span data-stu-id="cd751-236">https:// \<tenant\>/\_api/search/query?querytext='sharepoint'&Properties='EnableMultiGeoSearch:true'&ClientType='my\_client\_id'</span></span>

#### <a name="sample-get-request-to-fan-out-to-some-geo-locations"></a><span data-ttu-id="cd751-237">Voorbeeld van aanvraag voor het aanvragen van een uitwaaiering voor **een aantal** geografische locaties</span><span class="sxs-lookup"><span data-stu-id="cd751-237">Sample GET request to fan out to **some** geo locations</span></span>

<span data-ttu-id="cd751-238">https:// \<tenant\> / \_ API/search/query? QueryText = ' site ' &ClientType = ' my_client_id ' &eigenschappen = ' EnableMultiGeoSearch: True, MultiGeoSearchConfiguration: [{DataLocation \\ : "naam" \\ , eindpunt \\ : "https \\ ://contosoNAM.SharePoint.com" \\ , SourceId \\ : "B81EAB55-3140-4312-B0F4-9459D1B4FFEE"} \\ , {DataLocation: " \\ can" \\ , eindpunt \\ : "https \\ ://contosoCAN.SharePoint-DF.com"}] "</span><span class="sxs-lookup"><span data-stu-id="cd751-238">https:// \<tenant\>/\_api/search/query?querytext='site'&ClientType='my_client_id'&Properties='EnableMultiGeoSearch:true, MultiGeoSearchConfiguration:[{DataLocation\\:"NAM"\\,Endpoint\\:"https\\://contosoNAM.sharepoint.com"\\,SourceId\\:"B81EAB55-3140-4312-B0F4-9459D1B4FFEE"}\\,{DataLocation\\:"CAN"\\,Endpoint\\:"https\\://contosoCAN.sharepoint-df.com"}]'</span></span>

> [!NOTE]
> <span data-ttu-id="cd751-239">Komma's en dubbele punten in de lijst met geografische locaties voor de eigenschap MultiGeoSearchConfiguration worden voorafgegaan door het **backslash** teken.</span><span class="sxs-lookup"><span data-stu-id="cd751-239">Commas and colons in the list of geo locations for the MultiGeoSearchConfiguration property are preceded by the **backslash** character.</span></span> <span data-ttu-id="cd751-240">Dit komt doordat aanvragen voor aanvragen gebruikmaken van dubbele puntjes om eigenschappen en komma's te scheiden en de argumenten van eigenschappen te scheiden.</span><span class="sxs-lookup"><span data-stu-id="cd751-240">This is because GET requests use colons to separate properties and commas to separate arguments of properties.</span></span> <span data-ttu-id="cd751-241">Zonder backslash als een escape-teken, wordt de eigenschap MultiGeoSearchConfiguration niet op de juiste wijze geïnterpreteerd.</span><span class="sxs-lookup"><span data-stu-id="cd751-241">Without the backslash as an escape character, the MultiGeoSearchConfiguration property is interpreted wrongly.</span></span>

#### <a name="sample-post-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="cd751-242">Voorbeeld van een bericht dat is fanned naar **alle** geografische locaties</span><span class="sxs-lookup"><span data-stu-id="cd751-242">Sample POST request that's fanned out to **all** geo locations</span></span>

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


#### <a name="sample-post-request-thats-fanned-out-to-some-geo-locations"></a><span data-ttu-id="cd751-243">Voorbeeld van een bericht dat is fanned naar **een aantal** geografische locaties</span><span class="sxs-lookup"><span data-stu-id="cd751-243">Sample POST request that's fanned out to **some** geo locations</span></span>


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

### <a name="query-using-csom"></a><span data-ttu-id="cd751-244">Query met behulp van CSOM</span><span class="sxs-lookup"><span data-stu-id="cd751-244">Query using CSOM</span></span>

<span data-ttu-id="cd751-245">Hier ziet u een voorbeeld van een CSOM-query die is fanned voor **alle** geo-locaties:</span><span class="sxs-lookup"><span data-stu-id="cd751-245">Here's a sample CSOM query that's fanned out to **all** geo locations:</span></span>

    var keywordQuery = new KeywordQuery(ctx);
    keywordQuery.QueryText = query.SearchQueryText;
    keywordQuery.ClientType = <enter a string here>;
    keywordQuery["EnableMultiGeoSearch"] = true;

