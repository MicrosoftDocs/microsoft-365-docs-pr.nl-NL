---
title: Zoeken naar Microsoft 365 Multi-Geo configureren
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
description: Meer informatie over het configureren van zoeken in een multi-geo-omgeving. Alleen sommige clients, zoals OneDrive voor Bedrijven, kunnen resultaten retourneren in een multi-geoomgeving.
ms.openlocfilehash: b3a96b1d0652cb954c58ae410583befa078460d9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911160"
---
# <a name="configure-search-for-microsoft-365-multi-geo"></a>Zoeken naar Microsoft 365 Multi-Geo configureren

In een multi-geoomgeving heeft elke geografische locatie een eigen zoekindex en zoekcentrum. Wanneer een gebruiker zoekt, wordt de query uitgewaakt naar alle indexen en worden de geretourneerde resultaten samengevoegd.

Een gebruiker op één geografische locatie kan bijvoorbeeld zoeken naar inhoud die is opgeslagen op een andere geografische locatie of naar inhoud op een SharePoint-site die is beperkt tot een andere geografische locatie. Als de gebruiker toegang heeft tot deze inhoud, wordt het resultaat ervan in de zoekopdracht besyd.

## <a name="which-search-clients-work-in-a-multi-geo-environment"></a>Welke zoek clients werken in een multi-geo-omgeving?

Deze clients kunnen resultaten van alle geografische locaties retourneren:

- OneDrive voor Bedrijven
- Delve
- De startpagina van SharePoint
- Het zoekcentrum
- Aangepaste zoektoepassingen die gebruikmaken van de SharePoint Search API

### <a name="onedrive-for-business"></a>OneDrive voor Bedrijven

Zodra de multi-geo-omgeving is ingesteld, krijgen gebruikers die zoeken in OneDrive resultaten van alle geografische locaties.

### <a name="delve"></a>Delve

Zodra de multi-geo-omgeving is ingesteld, krijgen gebruikers die zoeken in Delve resultaten van alle geografische locaties.

In de Delve-feed en de profielkaart worden alleen voorbeelden weergegeven van bestanden die zijn opgeslagen op de centrale locatie. Voor bestanden die zijn opgeslagen op satellietlocaties, wordt in plaats daarvan het pictogram voor het bestandstype weergegeven.

### <a name="the-sharepoint-home-page"></a>De startpagina van SharePoint

Zodra de multi-geo-omgeving is ingesteld, zien gebruikers nieuws, recente en gevolgde sites van meerdere geografische locaties op hun SharePoint-startpagina. Als ze het zoekvak op de Startpagina van SharePoint gebruiken, krijgen ze samengevoegde resultaten van meerdere geografische locaties.

### <a name="the-search-center"></a>Het zoekcentrum

Nadat de multi-geo-omgeving is ingesteld, worden in elk zoekcentrum alleen resultaten van hun eigen geografische locatie weer te geven. Beheerders moeten [de instellingen van elk zoekcentrum wijzigen](#_Set_up_a_1) om resultaten te krijgen van alle geografische locaties. Daarna krijgen gebruikers die zoeken in het zoekcentrum resultaten van alle geografische locaties.

### <a name="custom-search-applications"></a>Aangepaste zoektoepassingen

Zoals gebruikelijk werken aangepaste zoektoepassingen samen met de zoekindexen met behulp van de bestaande SHAREPoint Search REST-API's. Als u resultaten wilt krijgen van alle of bepaalde geografische locaties, moet de toepassing de API bellen en de nieuwe [multi-geoqueryparameters](#_Get_custom_search) in de aanvraag opnemen. Hiermee wordt een ventilator uit de query naar alle geografische locaties triggers.

## <a name="whats-different-about-search-in-a-multi-geo-environment"></a>Wat is er anders aan zoeken in een multi-geo-omgeving?

Sommige zoekfuncties die u mogelijk kent, werken anders in een multi-geoomgeving.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Functie</strong></th>
<th align="left"><strong>Hoe het werkt</strong></th>
<th align="left"><strong>Tijdelijke oplossing</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Gepromoveerde resultaten</td>
<td align="left">U kunt queryregels maken met gepromoveerde resultaten op verschillende niveaus: voor de hele tenant, voor een siteverzameling of voor een site. Definieer in een multi-geoomgeving gepromoveerde resultaten op tenantniveau om de resultaten te promoveren naar de zoekcentra op alle geografische locaties. Als u alleen resultaten wilt promoten in het zoekcentrum dat zich op de geografische locatie van de siteverzameling of site bevindt, definieert u de gepromoveerde resultaten op siteverzamelings- of siteniveau. Deze resultaten worden niet gepromoveerd op andere geografische locaties.</td>
<td align="left">Als u geen andere gepromoveerde resultaten per geografische locatie nodig hebt, bijvoorbeeld andere regels voor reizen, raden we u aan gepromoveerde resultaten op tenantniveau te definiëren.</td>
</tr>
<tr class="even">
<td align="left">Verfijningen zoeken</td>
<td align="left">Zoeken retourneert verfijningen van alle geografische locaties van een tenant en verzamelt ze vervolgens. De aggregatie is een goede poging, wat betekent dat het aantal verfijningen mogelijk niet 100% nauwkeurig is. Voor de meeste zoekscenario's is deze nauwkeurigheid voldoende. 
</td>
<td align="left">Voor zoektoepassingen die afhankelijk zijn van de verfijningsversterkheid, kunt u elke geografische locatie onafhankelijk van elkaar opvragen.</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left">Multi-geo search biedt geen ondersteuning voor dynamische bucketing voor numerieke verfijningen.</td>
<td align="left">Gebruik de <a href="/sharepoint/dev/general-development/query-refinement-in-sharepoint">parameter 'Discretize'</a> voor numerieke verfijningen.</td>
</tr>
<tr class="even">
<td align="left">Document-eds</td>
<td align="left">Als u een zoektoepassing ontwikkelt die afhankelijk is van document-1D's, moet u er rekening mee houden dat document-ed's in een multi-geo-omgeving niet uniek zijn op geografische locaties, maar uniek zijn per geografische locatie.</td>
<td align="left">We hebben een kolom toegevoegd die de geografische locatie identificeert. Gebruik deze kolom om uniciteit te bereiken. Deze kolom heet 'GeoLocationSource'.</td>
</tr>
<tr class="odd">
<td align="left">Aantal resultaten</td>
<td align="left">De pagina met zoekresultaten bevat gecombineerde resultaten van de geografische locaties, maar het is niet mogelijk om meer dan 500 resultaten te pagina's.</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">Hybride zoekopdracht</td>
<td align="left">In een hybride SharePoint-omgeving met <a href="/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">hybride zoeken in</a>de cloud wordt on-premises inhoud toegevoegd aan de Microsoft 365-index van de centrale locatie.</td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="whats-not-supported-for-search-in-a-multi-geo-environment"></a>Wat wordt niet ondersteund voor zoeken in een multi-geo-omgeving?

Sommige zoekfuncties die u mogelijk kent, worden niet ondersteund in een multi-geoomgeving.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Zoekfunctie</strong></th>
<th align="left"><strong>Opmerking</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Alleen-app-verificatie</td>
<td align="left">App-only verificatie (privileged access from services) wordt niet ondersteund in multi-geo search.</td>
</tr>
<tr class="even">
<td align="left">Gastgebruikers</td>
<td align="left">Gastgebruikers krijgen alleen resultaten van de geografische locatie waar ze naar zoeken.</td>
</tr>
</tbody>
</table>

## <a name="how-does-search-work-in-a-multi-geo-environment"></a>Hoe werkt zoeken in een multi-geo-omgeving?

Alle zoek clients gebruiken de bestaande SharePoint Search REST API's om te werken met de zoekindexen.

![Diagram met de interactie tussen SharePoint Search REST-API's en de zoekindexen](../media/configure-search-for-multi-geo-image1-1.png)

1. Een zoekclient noemt het eindpunt Rest zoeken met de query-eigenschap EnableMultiGeoSearch= waar.
2. De query wordt verzonden naar alle geografische locaties in de tenant.
3. Zoekresultaten van elke geografische locatie worden samengevoegd en gerangschikt.
4. De client krijgt geïntegreerde zoekresultaten.

<span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>We voegen de zoekresultaten pas samen als we resultaten van alle geografische locaties hebben ontvangen. Dit betekent dat meerdere geografische zoekopdrachten extra latentie hebben ten opzichte van zoekopdrachten in een omgeving met slechts één geografische locatie.

<span id="_Set_up_a_1" class="anchor"><span id="_Ref505252370" class="anchor"></span></span>
## <a name="get-a-search-center-to-show-results-from-all-geo-locations"></a>Een zoekcentrum zoeken om resultaten van alle geografische locaties weer te geven

Elk zoekcentrum heeft verschillende verticaalen en u moet elke verticaal afzonderlijk instellen.

1. Zorg ervoor dat u deze stappen voert met een account dat is machtigingen voor het bewerken van de pagina met zoekresultaten en het webonderdeel Zoekresultaten.

2. Ga naar de pagina met zoekresultaten (zie de [lijst](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) met pagina's met zoekresultaten)

3. Selecteer de verticaal die u wilt instellen, **klik** in de rechterbovenhoek op Tandwielpictogram Instellingen en klik vervolgens op **Pagina bewerken.** De pagina met zoekresultaten wordt geopend in de bewerkingsmodus.

   ![Paginaselectie bewerken in Instellingen](../media/configure-search-for-multi-geo-image2.png)

4. Verplaats in het webonderdeel Zoekresultaten de aanwijzer naar de rechterbovenhoek van het webonderdeel, klik op de pijl en klik vervolgens op **Webonderdeel** bewerken in het menu. Het deelvenster Webonderdeel Zoekresultaten wordt geopend onder het lint rechtsboven op de pagina.

   ![Selectie webonderdeel bewerken](../media/configure-search-for-multi-geo-image3.png)

5. Selecteer in het taakvenster van het webonderdeel in  de sectie Instellingen onder Instellingen voor resultatenbesturingselementen de optie Resultaten met meerdere geografische velden weergeven om het webonderdeel Zoekresultaten weer te geven om resultaten van alle geografische locaties weer te geven. 

6. Klik **op OK** om de wijziging op te slaan en het taakvenster van het webonderdeel te sluiten.

7. Controleer uw wijzigingen in het webonderdeel Zoekresultaten door op **Inchecken te klikken** op het tabblad Pagina van het hoofdmenu.

8. Publiceer de wijzigingen met behulp van de koppeling in de notitie boven aan de pagina.

<span id="_Get_custom_search" class="anchor"><span id="_Ref501388387" class="anchor"></span></span>
## <a name="get-custom-search-applications-to-show-results-from-all-or-some-geo-locations"></a>Aangepaste zoektoepassingen gebruiken om resultaten van alle of sommige geografische locaties weer te geven

Aangepaste zoektoepassingen krijgen resultaten van alle of sommige geografische locaties door queryparameters op te geven met de aanvraag voor de SharePoint Search REST API. Afhankelijk van de queryparameters wordt de query uitgewaakt naar alle geografische locaties of naar bepaalde geografische locaties. Als u bijvoorbeeld alleen een subset met geografische locaties hoeft te query's uitvoeren om relevante informatie te vinden, kunt u de ventilator alleen naar deze locaties uitbesturing geven. Als de aanvraag slaagt, retourneert de SHAREPoint Search REST API antwoordgegevens.

### <a name="requirement"></a>Vereiste

Voor elke geografische locatie moet u ervoor zorgen dat  alle gebruikers in de organisatie het machtigingsniveau Lezen hebben gekregen voor de hoofdwebsite (bijvoorbeeld contoso **APAC**.sharepoint.com/ en contoso **EU**.sharepoint.com/). [Meer informatie over machtigingen.](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848)

### <a name="query-parameters"></a>Queryparameters

EnableMultiGeoSearch: dit is een Booleaanse waarde die aangeeft of de query moet worden uitgewaakt naar de indexen van andere geografische locaties van de multi-geotenant. Stel deze in **op waar om** de query uit te ventilatoren. **onwaar** om de query niet uit te waaieren. Als u deze parameter niet opgeeft, **is** de standaardwaarde onwaar, behalve wanneer u een REST API-oproep doet tegen een site die de sjabloon Enterprise Search Center gebruikt, in dit geval is de standaardwaarde **waar.** Als u de parameter gebruikt in een omgeving die niet multi-geo is, wordt de parameter genegeerd.

ClientType: dit is een tekenreeks. Voer een unieke clientnaam in voor elke zoektoepassing. Als u deze parameter niet opgeeft, wordt de query niet uitgewaakt naar andere geografische locaties.

MultiGeoSearchConfiguration - Dit is een optionele lijst van de geografische locaties in de multi-geo tenant om de query uit te ventilatoren wanneer **EnableMultiGeoSearch** **waar** is. Als u deze parameter niet opgeeft of leeg laat, wordt de query uitgewaakt naar alle geografische locaties. Voer voor elke geografische locatie de volgende items in in de JSON-indeling:

<table>
<thead>
<tr class="header">
<th align="left">Item</th>
<th align="left">Beschrijving</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">DataLocation</td>
<td align="left">De geografische locatie, bijvoorbeeld nam.</td>
</tr>
<tr class="even">
<td align="left">EndPoint</td>
<td align="left">Het eindpunt waar u verbinding mee wilt maken, bijvoorbeeld https://contoso.sharepoint.com</td>
</tr>
<tr class="odd">
<td align="left">SourceId</td>
<td align="left">De GUID van de resultatenbron, bijvoorbeeld B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</td>
</tr>
</tbody>
</table>

Als u DataLocation of EndPoint weglaat of als een DataLocation wordt gedupliceerd, mislukt de aanvraag. U kunt informatie krijgen over het eindpunt van de geografische locaties van een [tenant met Behulp van Microsoft Graph.](/sharepoint/dev/solution-guidance/multigeo-discovery)

### <a name="response-data"></a>Antwoordgegevens

MultiGeoSearchStatus: dit is een eigenschap die de SharePoint Search API retourneert als antwoord op een aanvraag. De waarde van de eigenschap is een tekenreeks en geeft de volgende informatie over de resultaten die de SharePoint Search API retourneert:

<table>
<thead>
<tr class="header">
<th align="left">Value</th>
<th align="left">Beschrijving</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Volledig</td>
<td align="left">Volledige resultaten van <strong>alle</strong> geografische locaties.</td>
</tr>
<tr class="even">
<td align="left">Gedeeltelijk</td>
<td align="left">Gedeeltelijke resultaten van een of meer geografische locaties. De resultaten zijn onvolledig vanwege een tijdelijke fout.</td>
</tr>
</tbody>
</table>

### <a name="query-using-the-rest-service"></a>Query met de REST-service

Met een GET-aanvraag geeft u de queryparameters op in de URL. Met een POST-aanvraag passeert u de queryparameters in de body in de JSON-indeling (JavaScript Object Notation).

#### <a name="request-headers"></a>Kopteksten aanvragen

<table>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Inhoudstype</td>
<td align="left">application/json;odata=verbose</td>
</tr>
</tbody>
</table>

#### <a name="sample-get-request-thats-fanned-out-to-all-geo-locations"></a>Voorbeeld van GET-aanvraag die is uitgewaakt naar **alle** geografische locaties

https:// \<tenant\> / \_ api/search/query?querytext='sharepoint'&Properties='EnableMultiGeoSearch:true'&ClientType='my \_ client \_ id'

#### <a name="sample-get-request-to-fan-out-to-some-geo-locations"></a>Voorbeeld van GET-aanvraag om uit te waaieren **naar bepaalde** geografische locaties

https:// \<tenant\> / \_ api/search/query?querytext='site'&ClientType='my_client_id'&Properties='EnableMultiGeoSearch:true, MultiGeoSearchConfiguration:[{DataLocation \\ :"NAM" \\ ,Endpoint \\ :"https \\ ://contosoNAM.sharepoint.com" \\ ,SourceId \\ :"B81EAB55-3140-4312-B0F4-9459D1B4FFEE"} \\ ,{DataLocation \\ :"CAN" \\ ,Endpoint \\ :"https \\ ://contosoCAN.sharepoint-df.com"}'

> [!NOTE]
> Komma's en dubbele puntpunten in de lijst met geografische locaties voor de eigenschap MultiGeoSearchConfiguration worden voorafgegaan door het **backslash-teken.** Dit komt omdat get-aanvragen dubbele punten gebruiken om eigenschappen en komma's te scheiden om argumenten van eigenschappen te scheiden. Zonder de backslash als een escape-teken wordt de eigenschap MultiGeoSearchConfiguration verkeerd geïnterpreteerd.

#### <a name="sample-post-request-thats-fanned-out-to-all-geo-locations"></a>Voorbeeld van een POST-aanvraag die is uitgewaakt naar **alle** geografische locaties

```text
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

#### <a name="sample-post-request-thats-fanned-out-to-some-geo-locations"></a>Voorbeeld van een POST-aanvraag die is uitgewaakt naar **bepaalde** geografische locaties

```text
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

### <a name="query-using-csom"></a>Query met behulp van CSOM

Hier is een voorbeeld van een CSOM-query die is uitgewaakt naar **alle** geografische locaties:

```text
var keywordQuery = new KeywordQuery(ctx);
keywordQuery.QueryText = query.SearchQueryText;
keywordQuery.ClientType = <enter a string here>;
keywordQuery["EnableMultiGeoSearch"] = true;
```