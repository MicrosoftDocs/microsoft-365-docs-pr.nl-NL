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
# <a name="navigation-options-for-sharepoint-online"></a>Navigatieopties voor SharePoint Online

In dit artikel worden de Navigatieopties beschreven die beschikbaar zijn voor SharePoint-sites met SharePoint Online. De keuze en configuratie van de navigatie zijn sterk van invloed op de prestaties en schaalbaarheid van sites in SharePoint Online. De sjabloon voor de publicerende site van SharePoint mag alleen worden gebruikt als dit vereist is voor een gecentraliseerde Portal en de publicatiefunctie mag alleen worden ingeschakeld op specifieke sites en alleen wanneer de prestaties van invloed kunnen zijn op de prestaties die onjuist worden gebruikt.

>[!NOTE]
>Dit artikel is niet van toepassing op uw site als u moderne Navigatieopties voor SharePoint gebruikt, zoals het menu Mega wind, Cascading Navigation of hub Navigation. Moderne SharePoint-site architecturen profiteren van een meer afvlakkige sitehiërarchie en een hub-en-spoke-model. U kunt zo veel scenario's bereiken waarbij de publicatiefunctie van SharePoint niet is vereist.

## <a name="overview-of-navigation-options"></a>Overzicht van Navigatieopties

Configuratie van navigatie provider kan een aanzienlijke invloed hebben op de prestaties van de hele site, en zorgvuldige overweging voor het kiezen van een navigatie provider en-configuratie die effectiever schaalt voor de vereisten van een SharePoint-site. Er zijn twee kant-en-klare navigatie providers en aangepaste navigatie-implementaties.

De eerste optie, [**structurele navigatie**](#using-structural-navigation-in-sharepoint-online), is de aanbevolen optie voor navigatie in SharePoint Online voor klassieke SharePoint-sites, **Als u structurele navigatie in cache voor uw site inschakelt**. Deze navigatie provider toont de navigatie-items onder de huidige site en optioneel de huidige site en de onderliggende items. Het biedt extra mogelijkheden, zoals beveiligingsbeperkingen en inventarisatie van site structuren. Als caching is uitgeschakeld, heeft dit een negatieve invloed op de prestaties en schaalbaarheid, en kan de beperking gelden.

Met de tweede optie, [**beheerde metagegevens (metagegevens)**](#using-managed-navigation-and-metadata-in-sharepoint-online), stelt u navigatie-items met behulp van een Termenset beheerde metagegevens. U wordt aangeraden beveiligingsbeperkingen uit te schakelen, tenzij nodig. Beveiligingsbeperking is ingeschakeld als een veilig-standaardinstelling voor deze navigatie provider. voor veel sites is de overhead van beveiligingsbeperkingen niet vereist omdat navigatie-elementen vaak consistent zijn voor alle gebruikers van de site. Met de aanbevolen configuratie voor het uitschakelen van beveiligingsbeperkingen, moet u de sitestructuur niet met een inventarisatie van de sitestructuur en is deze met een acceptabele gevolgen voor de prestaties zeer uitgebreid.

Naast de kant-en-klare navigatie providers hebben veel klanten een alternatieve aangepaste navigatie-implementatie geïmplementeerd. Zie [scripts op basis van de zoekopdracht aan de clientzijde](#using-search-driven-client-side-scripting) van dit artikel.
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a>Voor-en nadelen van Navigatieopties voor SharePoint Online

De volgende tabel bevat een overzicht van de voor-en nadelen van elke optie.

|Structurele navigatie  |Beheerde navigatie  |Navigatie met zoekopdrachten  |Aangepaste operator voor navigatie  |
|---------|---------|---------|---------|
|-Professionals<br/><br/>Gemakkelijk te onderhouden<br/>Beveiligingsbeperking<br/>Automatisch updates binnen 24 uur wanneer inhoud wordt gewijzigd<br/>     |-Professionals<br/><br/>Gemakkelijk te onderhouden<br/>|-Professionals<br/><br/>Beveiligingsbeperking<br/>Wordt automatisch bijgewerkt wanneer sites worden toegevoegd<br/>Snel laadtijd en navigatiestructuur in de lokale cache<br/>|-Professionals<br/><br/>Uitgebreide optie voor beschikbare opties<br/>Snel laden wanneer cache correct wordt gebruikt<br/>Een groot aantal opties werken goed met een reactie pagina-ontwerp<br/>|
|Nadelen<br/><br/>**Beïnvloedt de prestaties als het opslaan van de cache is uitgeschakeld**<br/>Onderworpen aan beperking<br/>|Nadelen<br/><br/>Niet automatisch bijgewerkt overeenkomstig de sitestructuur<br/>**Beïnvloedt de prestaties als beveiligingsbeperkingen zijn ingeschakeld** of als de navigatiestructuur complex is<br/>|Nadelen<br/><br/>Geen mogelijkheid om sites eenvoudig te rangschikken<br/>Aanpassing van de basispagina vereist (technische vaardigheden vereist)<br/>|Nadelen<br/><br/>Aangepaste ontwikkeling is vereist<br/>Extern gegevensbron/cache opslaan is vereist, zoals Azure<br/>|

De meest geschikte optie voor uw site is afhankelijk van de vereisten van uw site en over de technische mogelijkheden. Als u een eenvoudig te configureren navigatie provider wilt die automatisch wordt bijgewerkt wanneer de inhoud wordt gewijzigd, kunt u het beste de structurele navigatie met de optie [voor het opslaan van een cache](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) .

>[!NOTE]
>Hetzelfde beginsel toepassen als moderne SharePoint-sites door de structuur van de hele site te vereenvoudigen tot een flatter, een niet-hiërarchische structuur verbetert de prestaties en vergemakkelijkt de overstap naar moderne SharePoint-sites. Wat betekent dit? in plaats van dat u één siteverzameling met honderden sites (subwebs) hebt, is het een betere manier om veel siteverzamelingen met een groot aantal subsites (subwebs) te gebruiken.

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a>Navigatieprestaties analyseren in SharePoint Online

Het [hulpprogramma pagina diagnose voor SharePoint](https://aka.ms/perftool) is een browser extensie voor browsers van Microsoft Edge en Chrome waarmee de pagina's van SharePoint Online voor de moderne Portal en de klassieke publicatiesite worden geanalyseerd. Dit hulpprogramma werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.

Met het hulpprogramma wordt een rapport gegenereerd voor elke geanalyseerde pagina op basis van de manier waarop de pagina wordt uitgevoerd met een vooraf gedefinieerde set regels en gedetailleerde informatie wordt weergegeven wanneer resultaten van een test buiten de waarde van de basislijn vallen. Beheerders van SharePoint Online kunnen het hulpprogramma gebruiken voor het oplossen van prestatieproblemen om ervoor te zorgen dat nieuwe pagina's worden geoptimaliseerd voordat ze worden gepubliceerd.

**SPRequestDuration** met name is de tijd die het voor de verwerking van de pagina in SharePoint duurt. Dikke navigatie (zoals pagina's in navigatie), complexe site hiërarchieën en andere configuratie-en topologie opties kunnen alle grote bijdrage leveren aan langere duur.

## <a name="using-structural-navigation-in-sharepoint-online"></a>Structurele navigatie in SharePoint Online gebruiken

Dit is de kant-en-klare navigatie die standaard wordt gebruikt voor de meest eenvoudige oplossing. Het is niet verplicht om wijzigingen aan te brengen en een niet-technische gebruiker hoeft ook snel items toe te voegen, items te verbergen en de navigatie op de pagina instellingen te beheren. U wordt aangeraden [cache in te schakelen](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), anders is er een duurder voor de prestaties.

### <a name="how-to-implement-structural-navigation-caching"></a>Structurele navigatie in cache implementeren

In **Site Settings**  >  **Look and Feel**  >  **Navigation**het uiterlijk van site-instellingen kunt u controleren of structurele navigatie is geselecteerd voor globale navigatie of de huidige navigatie. Het selecteren van **pagina's weergeven** heeft een negatieve impact op de prestaties.

![Structurele navigatie met subsites weergeven geselecteerd](../media/SPONavOptionsStructuredShowSubsites.png)

U kunt in-en uitschakelen op siteverzamelingsniveau en op siteniveau, en is standaard ingeschakeld voor beide. Als u het niveau van de siteverzameling wilt inschakelen, schakelt u onder **site-instellingen**siteverzameling  >  **beheren**  >  **Site Collection Navigation**de optie **cache inschakelen**in.

![Cache inschakelen op siteniveau](../media/structural-nav/structural-nav-caching-site-coll.png)

Als u het siteniveau wilt inschakelen, **Site Settings**schakelt u onder  >  **Navigatie**van site-instellingen het selectievakje **cache inschakelen**in.

![Cache inschakelen op siteniveau](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a>Beheerde navigatie en metagegevens gebruiken in SharePoint Online

Beheerde navigatie is een andere gebruiksklare optie die u kunt gebruiken om dezelfde functionaliteit als de structurele navigatie opnieuw te maken. Beheerde metagegevens kunnen worden geconfigureerd om beveiligingsbeperkingen in of uit te schakelen. Wanneer de configuratie is uitgeschakeld met beveiligingsbeperkingen uitgeschakeld, is beheerde navigatie tamelijk efficiënt omdat alle navigatiekoppelingen met een constant aantal Server oproepen worden geladen. Door beveiligingsbeperkingen in te schakelen, worden echter wel enkele prestatievoordelen van beheerde navigatie genegeerd.

Als u beveiligingsbeperkingen moet inschakelen, is het raadzaam om het volgende te doen:

- Alle beschrijvende URL-koppelingen naar eenvoudige koppelingen bijwerken
- Vereiste beveiligingsbeperkingen toevoegen knooppunten als beschrijvende Url's
- Beperk het aantal navigatie-items tot maximaal 100 en mag niet groter zijn dan 3 niveaus.

Voor veel sites is geen beveiliging van beveiligingsbeperkingen vereist, aangezien de navigatiestructuur vaak consistent is voor alle gebruikers van de site. Als beveiligingsbeperkingen zijn uitgeschakeld en een koppeling wordt toegevoegd aan een navigatie die niet door alle gebruikers is geopend, wordt de koppeling weergegeven maar wordt er een bericht weergegeven dat toegang is geweigerd. Er is geen risico dat onopzettelijk toegang heeft tot de inhoud.

### <a name="how-to-implement-managed-navigation-and-the-results"></a>Het implementeren van beheerde navigatie en de resultaten

Er zijn verschillende artikelen over docs.microsoft.com over de details van beheerde navigatie. Zie [overzicht van beheerde navigatie in SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)voor meer informatie.

Als u beheerde navigatie wilt implementeren, stelt u termen in met Url's die overeenkomen met de navigatiestructuur van de site. Beheerde navigatie kan zelfs handmatig worden gecurator om structurele navigatie in veel gevallen te vervangen. Bijvoorbeeld:

![SharePoint Online-sitestructuur](../media/SPONavOptionsListOfSites.png))

## <a name="using-search-driven-client-side-scripting"></a>Het gebruik van scripts met zoekopdrachten aan de clientzijde

Eén veelgebruikte klasse van aangepaste navigatie-implementaties omvat een client weergave van de client weergave die een lokale cache van navigatieknooppunten opslaat.

Deze navigatie providers bieden een aantal belangrijke voordelen:

- Algemeen werken ze prima met beantwoordings pagina ontwerpen.
- Ze zijn zeer schaalbaar en presteert, omdat ze zonder resourcekosten kunnen weergeven (en de achtergrond na een time-out vernieuwen).
- Met behulp van de volgende navigatie providers kunt u navigatie gegevens ophalen met behulp van verschillende strategieën, variërend van eenvoudige statische configuraties tot diverse dynamische gegevensproviders.

Een voorbeeld van een gegevensprovider is het gebruik van een **zoekopdracht met een zoekopdracht**, wat flexibiliteit biedt voor het inkorten van navigatieknooppunten en de verwerking van beveiligingsbeperkingen.

Er zijn andere populaire opties om **aangepaste navigatie providers**te maken. Controleer de [Navigatie oplossingen voor SharePoint Online-portals](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) voor meer informatie over het maken van een aangepaste navigatie provider.

Met de functie zoeken kunt u de indexen gebruiken die op de achtergrond zijn opgebouwd via continue crawl. De zoekresultaten worden vanuit de zoekindex getrokken en de resultaten worden ingekort. Dit is doorgaans sneller dan de kant-en-klare navigatie providers wanneer beveiligingsbeperkingen vereist zijn. Met de zoekfunctie van structurele navigatie, met name als u een complexe sitestructuur hebt, wordt de laadtijd van de pagina aanzienlijk sneller weergegeven. Het voordeel van dit object via beheerde navigatie is dat u profiteert van beveiligingsbeperkingen.

Voor deze manier moet u een aangepaste basispagina maken en de niet-geminimaliseerde navigatie code vervangen door aangepaste HTML. Voer de volgende stappen uit in het volgende voorbeeld om de navigatie code in het bestand te vervangen `seattle.html` . In dit voorbeeld opent u het `seattle.html` bestand en vervangt u het hele element door een `id="DeltaTopNavigation"` aangepaste HTML-code.

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a>Voorbeeld: de niet-gegroepeerde navigatie code op een basispagina vervangen

1. Ga naar de pagina Site-instellingen.
2. Open de galerie met basispagina's door op **basispagina's**te klikken.
3. Van hieruit kunt u door de bibliotheek navigeren en het bestand downloaden `seattle.master` .
4. Bewerk de code met een teksteditor en verwijder het codeblok dat in de volgende schermafbeelding wordt weergegeven.<br/>![Het weergegeven codeblok verwijderen](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. Verwijder de code tussen de `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` labels en en vervang deze door het volgende fragment:<br/>

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
6. Vervang de URL in de afbeeldings ankerpunt die aan het begin wordt geladen, met een koppeling naar een laadafbeelding in de siteverzameling. Nadat u de wijzigingen hebt aangebracht, wijzigt u de naam van het bestand en uploadt u het naar de galerie met basispagina's. Hiermee wordt een nieuw modelbestand gegenereerd.<br/>
7. Dit HTML-bestand bevat de basis markeringen die worden gevuld met de zoekresultaten die worden opgehaald uit een JavaScript-code. U moet de code bewerken voor het wijzigen van de waarde voor de ' var root = ' siteverzameling-URL ' zoals wordt aangetoond in het volgende fragment:<br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. De resultaten worden toegewezen aan de matrix Self. nodes en er wordt een hiërarchie opgebouwd op basis van de objecten die linq.js de uitvoer toewijzen aan een matrix Self. Hierarchy. Deze matrix is het object dat is gekoppeld aan de HTML. Dit gebeurt in de toggleView ()-functie door het selfservice object te geven aan de functie ko. applyBinding ().<br/>Hierdoor wordt de hiërarchie matrix gebonden aan de volgende HTML:<br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

De gebeurtenis-handlers voor `mouseenter` en `mouseexit` worden toegevoegd aan de navigatie op het hoogste niveau voor het verwerken van de vervolgkeuzelijsten van subsites die in de functie worden uitgevoerd `addEventsToElements()` .

In het voorbeeld van complexe navigatie wordt een nieuwe pagina geladen zonder de lokale cache weergegeven de tijd die aan de server is besteed en die een vergelijkbaar resultaat oplevert als de beheerde navigatie aanpak.

### <a name="about-the-javascript-file"></a>Info over het JavaScript-bestand...

>[!NOTE]
>Als u aangepaste JavaScript gebruikt, moet u ervoor zorgen dat openbare CDN is ingeschakeld en dat het bestand zich op een CDN-locatie bevindt.

Het volledige JavaScript-bestand is als volgt:

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

Als u de code wilt samenvatten die hierboven wordt weergegeven, wordt de functie `jQuery $(document).ready` `viewModel object` gemaakt en wordt de `loadNavigationNodes()` functie van dat object aangeroepen. Met deze functie wordt de eerder gemaakte navigatiehiërarchie geladen die is opgeslagen in de lokale HTML5-opslag van de client van de client of wordt de functie aangeroepen `queryRemoteInterface()` .

`QueryRemoteInterface()` maakt een aanvraag met de `getRequest()` functie met de queryparameter eerder gedefinieerd in het script en retourneert vervolgens gegevens van de server. Deze gegevens zijn in feite een array van alle sites in de siteverzameling die wordt voorgesteld als objecten voor gegevensoverdracht met diverse eigenschappen.

Deze gegevens worden vervolgens geparseerd naar de eerder gedefinieerde `SPO.Models.NavigationNode` objecten die `Knockout.js` de waarden voor het gebruik van de gegevens in de opgegeven HTML moeten worden gebruikt voor het maken van waarneembare eigenschappen.

De objecten worden vervolgens opgenomen in een resultatenmatrix. Deze matrix wordt in JSON geparseerd met behulp van afdek kracht en opgeslagen in de lokale browser opslag voor betere prestaties op toekomstige pagina's.

### <a name="benefits-of-this-approach"></a>Voordelen van deze aanpak

Een belangrijk voordeel van [deze methode](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) is dat met behulp van de lokale HTML5-opslag de navigatie voor de gebruiker lokaal wordt opgeslagen wanneer deze de pagina een volgende keer laadt. We gaan belangrijke prestatieverbeteringen in het gebruik van de zoek-API voor structurele navigatie. het kan echter wel enkele technische mogelijkheden voor het uitvoeren van deze functionaliteit en het aanpassen van deze functionaliteit.

In de [Voorbeeldimplementatie](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)worden de sites op dezelfde manier geordend als de kant-en-klare structurele navigatie. alfabetische volgorde. Als u wilt afwijken van deze volgorde, is het ingewikkelder om te ontwikkelen en te onderhouden. Voor deze methode moet u ook afwijken van de ondersteunde basispagina's. Als de aangepaste basispagina niet wordt bijgehouden, mist de site updates en verbeteringen die door Microsoft worden aangebracht in de basispagina's.

De [bovenstaande code](#about-the-javascript-file) heeft de volgende afhankelijkheden:

- jQuery https://jquery.com/
- KnockoutJS https://knockoutjs.com/
- Linq.js- https://linqjs.codeplex.com/ of github.com/neuecc/linq.js

De huidige versie van LinqJS bevat niet de methode ByHierarchy die in de bovenstaande code is gebruikt en verbreekt de navigatie code. U kunt dit oplossen door de volgende methode toe te voegen aan het Linq.js-bestand vóór de regel `Flatten: function ()` .

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

[Overzicht van beheerde navigatie in SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)

[Opslag en prestaties van structurele navigatie](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)
