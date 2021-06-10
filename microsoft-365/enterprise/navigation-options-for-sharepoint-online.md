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
description: In dit artikel worden sites met navigatieopties beschreven SharePoint Publiceren is ingeschakeld in SharePoint Online.
ms.openlocfilehash: b5989bf26ebf7bb1452f983af89a6e6739821d53
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923622"
---
# <a name="navigation-options-for-sharepoint-online"></a>Navigatieopties voor SharePoint Online

In dit artikel worden sites met navigatieopties beschreven SharePoint Publiceren is ingeschakeld in SharePoint Online. De keuze en configuratie van navigatie zijn aanzienlijk van invloed op de prestaties en schaalbaarheid van sites in SharePoint Online. De SharePoint Publicerende sitesjabloon mag alleen worden gebruikt als dit vereist is voor een gecentraliseerde portal en de publicatiefunctie mag alleen worden ingeschakeld op specifieke sites en alleen wanneer dit absoluut vereist is, omdat deze van invloed kan zijn op de prestaties wanneer deze onjuist worden gebruikt.

>[!NOTE]
>Als u moderne navigatieopties SharePoint, zoals megamenu, trapsgevatte navigatie of hubnavigatie, is dit artikel niet van toepassing op uw site. Moderne SharePoint sitearchitectuur maken gebruik van een meer afgeplatte sitehiërarchie en een hub- en spaakmodel. Hierdoor kunnen veel scenario's worden bereikt waarvoor geen gebruik hoeft te worden SharePoint publicatiefunctie.

## <a name="overview-of-navigation-options"></a>Overzicht van navigatieopties

De configuratie van navigatieproviders kan aanzienlijk van invloed zijn op de prestaties van de hele site en er moet zorgvuldig rekening mee worden gehouden om een navigatieprovider en configuratie te kiezen die effectief wordt geschaald voor de vereisten van een SharePoint site. Er zijn twee out-of-the-box navigatieproviders, evenals aangepaste navigatie-implementaties.

De eerste optie, [**Structurele navigatie,**](#using-structural-navigation-in-sharepoint-online)is de aanbevolen navigatieoptie in SharePoint Online voor klassieke Sharepoint-sites, als u structurele **navigatie-caching** voor uw site in- of uitkeert. Deze navigatieprovider geeft de navigatie-items weer onder de huidige site, en eventueel de huidige site en de huidige locatie. Het biedt extra mogelijkheden, zoals beveiliging bijsnijden en het opsnoemen van sitestructuur. Als caching is uitgeschakeld, heeft dit een negatieve invloed op de prestaties en schaalbaarheid en kan de beperking van de caching van invloed zijn.

De tweede optie, [**Beheerde navigatie (metagegevens),**](#using-managed-navigation-and-metadata-in-sharepoint-online)vertegenwoordigt navigatie-items met behulp van een termset beheerde metagegevens. U wordt aangeraden beveiligingssnijding uit te staan, tenzij dit vereist is. Beveiligingssnijding is ingeschakeld als een standaardinstelling voor deze navigatieprovider. Voor veel sites hoeft echter niet de beveiliging te worden bijgesneden, omdat navigatie-elementen vaak consistent zijn voor alle gebruikers van de site. Met de aanbevolen configuratie om beveiligingsscheiding uit te schakelen, hoeft deze navigatieprovider geen sitestructuur op te geven en is deze zeer schaalbaar met acceptabele prestatie-effecten.

Naast de out-of-the-box navigatieproviders hebben veel klanten ook alternatieve aangepaste navigatie-implementaties geïmplementeerd. Zie [Op zoek gebaseerde clientscripting](#using-search-driven-client-side-scripting) in dit artikel.
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a>Voor- en nadelen van SharePoint onlinenavigatieopties

In de volgende tabel worden de voor- en nadelen van elke optie samengevat.

|Structurele navigatie  |Beheerde navigatie  |Navigatie op zoek  |Provider voor aangepaste navigatie  |
|---------|---------|---------|---------|
|Professionals:<br/><br/>Eenvoudig te onderhouden<br/>Beveiliging bijgesneden<br/>Automatisch updates binnen 24 uur wanneer inhoud wordt gewijzigd<br/>     |Professionals:<br/><br/>Eenvoudig te onderhouden<br/>|Professionals:<br/><br/>Beveiliging bijgesneden<br/>Automatisch updates wanneer sites worden toegevoegd<br/>Snelle laadtijd en navigatiestructuur met lokaal cachegeheugen<br/>|Professionals:<br/><br/>Bredere keuze aan beschikbare opties<br/>Snel laden wanneer caching correct wordt gebruikt<br/>Veel opties werken goed met het snel reagerende paginaontwerp<br/>|
|Nadelen:<br/><br/>**Invloed op de prestaties als caching is uitgeschakeld**<br/>Afhankelijk van beperking<br/>|Nadelen:<br/><br/>Niet automatisch bijgewerkt om de sitestructuur weer te geven<br/>**Beïnvloedt de prestaties als beveiligingsmaatregelen zijn ingeschakeld of** als de navigatiestructuur complex is<br/>|Nadelen:<br/><br/>Geen mogelijkheid om eenvoudig sites te bestellen<br/>Vereist aanpassing van de basispagina (technische vaardigheden vereist)<br/>|Nadelen:<br/><br/>Aangepaste ontwikkeling is vereist<br/>Externe gegevensbron/cache die is opgeslagen, is nodig, bijvoorbeeld Azure<br/>|

De meest geschikte optie voor uw site is afhankelijk van uw sitevereisten en van uw technische mogelijkheden. Als u een eenvoudig te configureren navigatieprovider wilt die automatisch wordt bijgewerkt wanneer inhoud wordt gewijzigd, is structurele navigatie met [ingeschakelde caching](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) een goede optie.

>[!NOTE]
>Het toepassen van hetzelfde principe als moderne SharePoint sites door de algehele sitestructuur te vereenvoudigen naar een vlakkere, niet-hiërarchische structuur, verbetert de prestaties en vereenvoudigt het verplaatsen naar moderne SharePoint sites. Dit betekent dat in plaats van één siteverzameling met honderden sites (subwebs) veel siteverzamelingen met zeer weinig subsites (subwebs) te hebben.

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a>Navigatieprestaties analyseren in SharePoint Online

Het [hulpprogramma Paginadiagnose voor SharePoint](./page-diagnostics-for-spo.md) is een browserextensie voor Microsoft Edge- en Chrome-browsers die zowel SharePoint moderne portal van Online als klassieke publicerende sitepagina's analyseert. Dit hulpprogramma werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint systeempagina.

Het hulpprogramma genereert een rapport voor elke geanalyseerde pagina waarin wordt weergegeven hoe de pagina presteert ten opzichte van een vooraf gedefinieerde set regels en gedetailleerde informatie wekt wanneer de resultaten voor een test buiten de basislijnwaarde vallen. SharePoint Onlinebeheerders en ontwerpers kunnen het hulpprogramma gebruiken om prestatieproblemen op te lossen om ervoor te zorgen dat nieuwe pagina's worden geoptimaliseerd voordat ze worden gepubliceerd.

**SPRequestDuration** is met name de tijd die nodig is om de SharePoint te verwerken. Zware navigatie (zoals pagina's in navigatie), complexe sitehiërarchieën en andere configuratie- en topologieopties kunnen allemaal aanzienlijk bijdragen aan langere duur.

## <a name="using-structural-navigation-in-sharepoint-online"></a>Structurele navigatie gebruiken in SharePoint Online

Dit is de standaard gebruikte standaardnavigatie en is de meest eenvoudige oplossing. Er is geen aanpassing vereist en een niet-technische gebruiker kan ook eenvoudig items toevoegen, items verbergen en de navigatie beheren vanaf de pagina Instellingen. Het is [raadzaam om caching in te](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)schakelen, anders is er sprake van een dure prestatie-trade-off.

### <a name="how-to-implement-structural-navigation-caching"></a>Structurele navigatie caching implementeren

Onder **Site Instellingen** Navigatie zoeken en voelen kunt u valideren of structurele navigatie is geselecteerd voor globale navigatie of huidige  >    >  navigatie. Als **u Pagina's** tonen selecteert, heeft dit een negatief effect op de prestaties.

![Structurele navigatie met Subsites weergeven geselecteerd](../media/SPONavOptionsStructuredShowSubsites.png)

Caching kan worden ingeschakeld of uitgeschakeld op siteverzamelingsniveau en op siteniveau en is standaard ingeschakeld voor beide. Als u op het niveau van de siteverzameling wilt inschakelen, schakel Instellingen Siteverzamelingsbeheersiteverzamelingsnavigatie het selectievakje  >    >   **Caching inschakelen in.**

![Caching op siteniveau inschakelen](../media/structural-nav/structural-nav-caching-site-coll.png)

Schakel onder Site-Instellingen Navigatie het selectievakje  >   **Caching inschakelen** in als u het siteniveau wilt inschakelen.

![Caching op siteniveau inschakelen](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a>Beheerde navigatie en metagegevens gebruiken in SharePoint Online

Beheerde navigatie is een andere out-of-the-box-optie die u kunt gebruiken om de meeste van dezelfde functionaliteit opnieuw te maken als structurele navigatie. Beheerde metagegevens kunnen zo worden geconfigureerd dat beveiligingssnijding is ingeschakeld of uitgeschakeld. Wanneer het beveiligingsbeheer is uitgeschakeld, is beheerde navigatie redelijk efficiënt omdat alle navigatiekoppelingen worden geladen met een constant aantal serveroproepen. Als u beveiligingsmaatregelen inschakelen, worden enkele prestatievoordelen van beheerde navigatie echter niet bespreekbaar.

Als u beveiliging wilt inschakelen, raden we u aan het volgende te doen:

- Alle vriendelijke URL-koppelingen naar eenvoudige koppelingen bijwerken
- Vereiste beveiligingsknooppunten toevoegen als vriendelijke URL's
- Het aantal navigatie-items beperken tot maximaal 100 en maximaal 3 niveaus diep

Voor veel sites is geen beveiliging nodig, omdat de navigatiestructuur vaak consistent is voor alle gebruikers van de site. Als beveiligingsbeveiligingsbeveiliging is uitgeschakeld en er een koppeling wordt toegevoegd aan navigatie waar niet alle gebruikers toegang toe hebben, wordt de koppeling nog steeds weergegeven, maar wordt een bericht met toegang geweigerd weergegeven. Er bestaat geen risico op onbedoelde toegang tot de inhoud.

### <a name="how-to-implement-managed-navigation-and-the-results"></a>Beheerde navigatie en de resultaten implementeren

Er zijn verschillende artikelen over docs.microsoft.com over de details van beheerde navigatie. Zie Bijvoorbeeld Overzicht van [beheerde navigatie in SharePoint Server.](/sharepoint/administration/overview-of-managed-navigation)

Als u beheerde navigatie wilt implementeren, stelt u voorwaarden in met URL's die overeenkomen met de navigatiestructuur van de site. Beheerde navigatie kan zelfs handmatig worden samengesteld om structurele navigatie in veel gevallen te vervangen. Bijvoorbeeld:

![SharePoint Onlinesitestructuur](../media/SPONavOptionsListOfSites.png))

## <a name="using-search-driven-client-side-scripting"></a>Scripting op basis van zoekgestuurde client

Een veelgebruikte klasse van aangepaste navigatie-implementaties omvat door de client gerenderde ontwerppatronen die een lokale cache met navigatieknooppunten opslaan.

Deze navigatieproviders hebben een paar belangrijke voordelen:

- Ze werken over het algemeen goed met snel reagerende paginaontwerpen.
- Ze zijn zeer schaalbaar en performant omdat ze zonder resourcekosten kunnen worden weergegeven (en vernieuwen op de achtergrond na een time-out).
- Deze navigatieproviders kunnen navigatiegegevens ophalen met behulp van verschillende strategieën, variërend van eenvoudige statische configuraties tot verschillende dynamische gegevensproviders.

Een voorbeeld van een gegevensprovider is het gebruik van een op zoeken gebaseerde **navigatie,** waarmee u flexibel navigatieknooppunten kunt opsnoemen en beveiliging efficiënt kunt inkorten.

Er zijn andere populaire opties voor het maken **van aangepaste navigatieproviders.** Bekijk [navigatieoplossingen voor SharePoint Online-portals](/sharepoint/dev/solution-guidance/portal-navigation) voor meer informatie over het bouwen van een aangepaste navigatieprovider.

Met behulp van zoeken kunt u gebruikmaken van de indexen die op de achtergrond zijn opgebouwd met behulp van continue verkenning. De zoekresultaten worden uit de zoekindex gehaald en de resultaten worden met beveiliging bijgesneden. Dit is over het algemeen sneller dan out-of-the-box navigatieproviders wanneer beveiliging moet worden bijgesneden. Als u zoekt naar structurele navigatie, met name als u een complexe sitestructuur hebt, wordt het laden van pagina's aanzienlijk sneller. Het belangrijkste voordeel hiervan ten opzichte van beheerde navigatie is dat u profiteert van beveiliging.

Bij deze benadering moet u een aangepaste basispagina maken en de out-of-the-box-navigatiecode vervangen door aangepaste HTML. Volg deze procedure die in het volgende voorbeeld wordt beschreven om de navigatiecode in het bestand te `seattle.html` vervangen. In dit voorbeeld opent u het `seattle.html` bestand en vervangt u het hele element door aangepaste `id="DeltaTopNavigation"` HTML-code.

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a>Voorbeeld: De out-of-the-box-navigatiecode op een basispagina vervangen

1. Ga naar de pagina Site Instellingen site.
2. Open de galerie met basispagina's door op **Basispagina's te klikken.**
3. Vanaf hier kunt u door de bibliotheek navigeren en het bestand `seattle.master` downloaden.
4. Bewerk de code met een teksteditor en verwijder het codeblok in de volgende schermafbeelding.<br/>![Het weergegeven codeblok verwijderen](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. Verwijder de code tussen de `<SharePoint:AjaxDelta id="DeltaTopNavigation">` tags en vervang deze door het volgende `<\SharePoint:AjaxDelta>` fragment:<br/>

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
6. Vervang de URL in het ankerlabel voor het laden van de afbeelding aan het begin, door een koppeling naar een laadafbeelding in uw siteverzameling. Nadat u de wijzigingen hebt aangebracht, wijzigt u de naam van het bestand en uploadt u het naar de galerie met basispagina's. Hiermee wordt een nieuw .master-bestand gegenereerd.<br/>
7. Deze HTML is de basisopmerking die wordt ingevuld door de zoekresultaten die worden geretourneerd uit JavaScript-code. U moet de code bewerken om de waarde voor var-hoofdmap = 'URL van de siteverzameling' te wijzigen, zoals wordt gedemonstreerd in het volgende fragment:<br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. De resultaten worden toegewezen aan de matrix self.nodes en een hiërarchie is opgebouwd uit de objecten met behulp van linq.js de uitvoer toe te wijzen aan een zelfhiërarchie van een matrix. Deze matrix is het object dat is gebonden aan de HTML. Dit gebeurt in de functie Beeld() door het zelfobject door te geven aan de functie ko.applyBinding().<br/>Hierdoor wordt de hiërarchiearray gebonden aan de volgende HTML:<br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

De gebeurtenis handlers voor en worden toegevoegd aan de navigatie op het hoogste niveau om de vervolgkeuzemenu's van de subsite te verwerken die `mouseenter` in de functie worden `mouseexit` `addEventsToElements()` uitgevoerd.

In ons complexe navigatievoorbeeld wordt met een nieuwe paginabelasting zonder de lokale caching de tijd die aan de server is besteed, afgesneden van de structurele navigatie voor benchmarks om een vergelijkbaar resultaat te krijgen als de beheerde navigatieaanpak.

### <a name="about-the-javascript-file"></a>Over het JavaScript-bestand...

>[!NOTE]
>Als u aangepaste JavaScript gebruikt, controleert u of openbare CDN is ingeschakeld en dat het bestand zich op een CDN bevindt.

Het hele JavaScript-bestand is als volgt:

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

Als u de code wilt samenvatten die hierboven wordt weergegeven in de functie, wordt er een gemaakt en wordt de `jQuery $(document).ready` functie op dat object `viewModel object` `loadNavigationNodes()` aangeroepen. Met deze functie wordt de eerder gebouwde navigatiehiërarchie geladen die is opgeslagen in de lokale HTML5-opslag van de clientbrowser of wordt de functie `queryRemoteInterface()` aanroepen.

`QueryRemoteInterface()` maakt een aanvraag met behulp van de functie met de queryparameter die eerder in het script is gedefinieerd en retourneert vervolgens `getRequest()` gegevens van de server. Deze gegevens zijn in feite een matrix van alle sites in de siteverzameling die worden weergegeven als objecten voor gegevensoverdracht met verschillende eigenschappen.

Deze gegevens worden vervolgens geparseerd in de eerder gedefinieerde objecten die worden gebruikt om waarneembare eigenschappen te maken voor gebruik door gegevens die de waarden binden aan de HTML die we eerder `SPO.Models.NavigationNode` `Knockout.js` hebben gedefinieerd.

De objecten worden vervolgens in een resultatenarray gezet. Deze matrix wordt geparseerd in JSON met Behulp van Knockout en opgeslagen in de lokale browseropslag voor verbeterde prestaties bij toekomstige paginabelastingen.

### <a name="benefits-of-this-approach"></a>Voordelen van deze benadering

Een belangrijk voordeel van [deze benadering](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) is dat de navigatie lokaal wordt opgeslagen door html5-opslag, zodat de gebruiker de volgende keer dat de pagina wordt geladen, lokaal wordt opgeslagen. We krijgen belangrijke prestatieverbeteringen van het gebruik van de zoek-API voor structurele navigatie. Er is echter enige technische mogelijkheid nodig om deze functionaliteit uit te voeren en aan te passen.

In de [voorbeelduitvoering](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)worden de sites op dezelfde manier geordend als de kant-en-zover structurele navigatie. alfabetische volgorde. Als u van deze volgorde wilt afwijken, is het ingewikkelder om deze te ontwikkelen en te onderhouden. Voor deze benadering moet u ook afwijken van de ondersteunde basispagina's. Als de aangepaste basispagina niet wordt onderhouden, mist uw site updates en verbeteringen die Microsoft aan de basispagina's aanbreed.

De [bovenstaande code](#about-the-javascript-file) heeft de volgende afhankelijkheden:

- jQuery - https://jquery.com/
- KnockoutJS - https://knockoutjs.com/
- Linq.js - https://linqjs.codeplex.com/ of github.com/neuecc/linq.js

De huidige versie van LinqJS bevat niet de methode ByHierarchy die in de bovenstaande code wordt gebruikt en zal de navigatiecode breken. Als u dit wilt oplossen, voegt u de volgende methode toe aan het Linq.js vóór de `Flatten: function ()` regel.

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
  
## <a name="related-topics"></a>Verwante onderwerpen

[Overzicht van beheerde navigatie in SharePoint Server](/sharepoint/administration/overview-of-managed-navigation)

[Structurele navigatie caching en prestaties](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)