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
# <a name="configure-search-for-microsoft-365-multi-geo"></a>Zoekfunctie configureren voor Microsoft 365 multi-geo

In een omgeving met meerdere geografische locaties heeft elke geografische locatie een eigen zoekindex en een zoekcentrum. Wanneer een gebruiker zoekt, is de query fanned naar alle indexen en worden de geretourneerde resultaten samengevoegd.

Een gebruiker in een geografische locatie kan bijvoorbeeld zoeken naar inhoud die is opgeslagen op een andere geografische locatie of voor inhoud op een SharePoint-site die is beperkt tot een andere geografische locatie. Als de gebruiker toegang heeft tot deze inhoud, wordt het resultaat weergegeven in de zoekfunctie.

## <a name="which-search-clients-work-in-a-multi-geo-environment"></a>Welke Zoek clients werken in een omgeving met meerdere geografische omgevingen?

Deze clients kunnen resultaten van alle geografische locaties retourneren:

-   OneDrive voor Bedrijven

-   Delve

-   De SharePoint-Startpagina

-   Het zoekcentrum

-   Aangepaste zoektoepassingen die gebruikmaken van de zoek-API van SharePoint

### <a name="onedrive-for-business"></a>OneDrive voor Bedrijven

Zodra de multifunctionele omgeving is ingesteld, krijgen gebruikers die zoeken in OneDrive resultaten van alle geografische locaties.

### <a name="delve"></a>Delve

Zodra de multifunctionele omgeving is ingesteld, krijgen gebruikers die zoeken in Delve resultaten van alle geografische locaties.

De feed voor Delve en de profielkaart geven alleen voorbeelden weer van bestanden die zijn opgeslagen op de centrale locatie. Voor bestanden die zijn opgeslagen op satelliet locaties, wordt in plaats hiervan het pictogram voor het bestandstype weergegeven.

### <a name="the-sharepoint-home-page"></a>De SharePoint-Startpagina

Zodra de multi-geografische omgeving is ingesteld, zien gebruikers nieuws, recente en gevolgde sites van meerdere geo-locaties op de startpagina van SharePoint. Als ze het zoekvak op de SharePoint-startpagina gebruiken, krijgen ze samenvoegresultaten van meerdere geografische locaties.

### <a name="the-search-center"></a>Het zoekcentrum

Nadat de omgeving met meerdere geografische omgevingen is ingesteld, blijft elk zoekcentrum alleen resultaten van de eigen geografische locatie weergeven. Beheerders moeten [de instellingen van een zoekcentrum wijzigen](#_Set_up_a_1) om resultaten op te doen van alle geografische locaties. Gebruikers die zoeken in het zoekcentrum krijgen vervolgens resultaten van alle geo-locaties.

### <a name="custom-search-applications"></a>Aangepaste zoektoepassingen

Zoals gebruikelijk werken aangepaste zoektoepassingen interactie met de zoekindexen met behulp van de bestaande SharePoint Search REST-Api's. Voor het ophalen van resultaten van alle of van een aantal geografische locaties moet de toepassing [de API aanroepen en de nieuwe parameters voor meervoudige geo-query's opnemen](#_Get_custom_search) in de aanvraag. Dit veroorzaakt een ventilator uit de query voor alle geografische locaties.

## <a name="whats-different-about-search-in-a-multi-geo-environment"></a>Wat is er anders in een zoekopdracht in een multi-geografische omgeving?

Sommige zoekfuncties die u mogelijk kent, werken anders in een omgeving met meerdere geografische gebieden.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Functie</strong></th>
<th align="left"><strong>Werking</strong></th>
<th align="left"><strong>Tijdelijke oplossing</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Bevorderde resultaten</td>
<td align="left">U kunt op verschillende niveaus queryregels met gepromoveerde resultaten maken: voor de volledige Tenant, voor een siteverzameling of voor een site. In een omgeving met meerdere geografische niveaus definieert u gepromoveerde resultaten op tenantniveau, zodat de resultaten van de zoek centrums in alle geografische locaties worden bevorderd. Als u alleen de resultaten in het zoekcentrum op de geografische locatie van de siteverzameling of site wilt promoveren, definieert u de bevorderde resultaten op siteverzameling of siteniveau. Deze resultaten worden niet bevorderd in andere geografische locaties.</td>
<td align="left">Als u geen verschillende gepromoveerde resultaten per geografische locatie nodig hebt, zoals voor het reizen, raden we u aan om gepromoveerde resultaten op tenantniveau te definiëren.</td>
</tr>
<tr class="even">
<td align="left">Verfijningen zoeken</td>
<td align="left">De zoekfunctie levert verfijningen op van alle geo-locaties van een Tenant en voegt deze vervolgens samen. De aggregatie is een beste manier, wat betekent dat het aantal verfijningen mogelijk niet 100% nauwkeurig is. Voor de meeste met een zoekopdracht gebaseerde scenario's is deze nauwkeurigheid voldoende. 
</td>
<td align="left">Voor toepassingen met een zoekopdracht die afhankelijk zijn van de voltooiing van het verfijnen, voert u een query uit op elke geografische locatie.</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left">De zoekfunctie voor meervoudige geo biedt geen ondersteuning voor dynamische buckets voor numerieke verfijningen.</td>
<td align="left">Gebruik de <a href="https://docs.microsoft.com/sharepoint/dev/general-development/query-refinement-in-sharepoint">parameter ' Discretize '</a> voor numerieke verfijningen.</td>
</tr>
<tr class="even">
<td align="left">Document-Id's</td>
<td align="left">Houd er rekening mee dat document-Id's in een omgeving met meerdere geografische locaties niet uniek zijn voor geografische locaties als u een zoekopdracht wilt ontwikkelen die afhankelijk is van document-Id's.</td>
<td align="left">Er is een kolom toegevoegd waarin de geografische locatie wordt aangegeven. Gebruik deze kolom om unieke mogelijkheden te verkrijgen. Deze kolom heeft de naam GeoLocationSource.</td>
</tr>
<tr class="odd">
<td align="left">Aantal resultaten</td>
<td align="left">Op de pagina met zoekresultaten worden gecombineerde resultaten van de geo-locaties weergegeven, maar het is niet mogelijk om meer 500 resultaten te bereiken.</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">Hybride zoeken</td>
<td align="left">In een hybride SharePoint-omgeving met <a href="https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">hybride zoeken</a>voor de Cloud wordt on-premises inhoud toegevoegd aan de microsoft 365-index van de centrale locatie.</td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="whats-not-supported-for-search-in-a-multi-geo-environment"></a>Wat wordt er niet ondersteund voor zoeken in een multi-geografische omgeving?

Een aantal van de zoekfuncties die u mogelijk kent, wordt niet ondersteund in een omgeving met meerdere geografische omgevingen.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Zoekfunctie</strong></th>
<th align="left"><strong>Ziet</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Verificatie via app</td>
<td align="left">Verificatie via een app (geprivilegieerde toegang van Services) wordt niet ondersteund in meerdere geo-zoekopdrachten.</td>
</tr>
<tr class="even">
<td align="left">Gastgebruikers</td>
<td align="left">Gastgebruikers krijgen alleen resultaten van de geografische locatie waarnaar ze zoeken.</td>
</tr>
</tbody>
</table>

## <a name="how-does-search-work-in-a-multi-geo-environment"></a>Hoe werkt zoeken in een omgeving met meerdere geografische gebieden?

Alle zoek clients gebruiken de bestaande SharePoint Search REST-Api's om te werken met de zoekindexen.

<img src="../media/configure-search-for-multi-geo-image1-1.png" />

1. Een zoekopdracht roept het eindpunt van de zoek REST aan met de queryeigenschap EnableMultiGeoSearch = True.
2. De query wordt verzonden naar alle geografische locaties in de Tenant.
3. De zoekresultaten van de geografische locatie worden samengevoegd en geclassificeerd.
4. De client ontvangt Unified Search Results.



<span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>De zoekresultaten worden niet samengevoegd totdat we resultaten van alle geografische locaties hebben ontvangen. Dit betekent dat er in meerdere geo-zoekopdrachten een extra latentie heeft vergeleken met zoekopdrachten in een omgeving met maar één geografische locatie.

<span id="_Set_up_a_1" class="anchor"><span id="_Ref505252370" class="anchor"></span></span>
## <a name="get-a-search-center-to-show-results-from-all-geo-locations"></a>Een zoekcentrum weergeven om resultaten van alle geografische locaties weer te geven

Elk zoekcentrum heeft diverse verticaal en u moet elke verticaal apart instellen.

1.  Zorg ervoor dat u deze stappen uitvoert met een account dat gemachtigd is om de pagina met zoekresultaten en het webonderdeel zoekresultaten te bewerken.

2.  Ga naar de pagina met zoekresultaten (Zie de [lijst](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) met pagina's met zoekresultaten).

3.  Selecteer de verticaal die u wilt instellen, klik op het tandwiel pictogram **instellingen** in de rechterbovenhoek en klik vervolgens op **pagina bewerken**. De pagina met zoekresultaten wordt geopend in de bewerkingsmodus.

     ![](../media/configure-search-for-multi-geo-image2.png)
1.  In het webonderdeel Zoekresultaten plaatst u de aanwijzer in de rechterbovenhoek van het webonderdeel, klikt u op de pijl en klikt u vervolgens op **webonderdeel bewerken** in het menu. Het taakvenster van het webonderdeel Zoekresultaten wordt geopend onder het lint in de rechterbovenhoek van de pagina. ![](../media/configure-search-for-multi-geo-image3.png)

1.  Selecteer in het taakvenster van het webonderdeel, in de sectie **instellingen** , onder **instellingen voor besturingselementen voor resultaten**de optie **Meervoudige geografische resultaten weergeven** om het webonderdeel zoekresultaten weer te geven voor resultaten van alle geo-locaties.

2.  Klik op **OK** om uw wijzigingen op te slaan en het taakvenster van het webonderdeel te sluiten.

3.  Controleer de wijzigingen in het webonderdeel zoekresultaten door te klikken op **inchecken** op het tabblad pagina van het hoofdmenu.

4.  Publiceer de wijzigingen via de koppeling die is opgenomen in de notitie boven aan de pagina.

<span id="_Get_custom_search" class="anchor"><span id="_Ref501388387" class="anchor"></span></span>
## <a name="get-custom-search-applications-to-show-results-from-all-or-some-geo-locations"></a>Aangepaste zoektoepassingen aanvragen voor het weergeven van resultaten van alle of een aantal geografische locaties

Aangepaste zoektoepassingen resulteren in resultaten van alle of enkele geo-locaties door parameters op te geven, met de aanvraag voor de REST van de SharePoint Search REST-API.Afhankelijk van de parameters van de query is de query fanned naar alle geografische locaties of naar een aantal geografische locaties. Als u bijvoorbeeld alleen een subset van geografische locaties hoeft te doorzoeken om relevante informatie te vinden, kunt u de waaier slechts voor deze elementen regelen. Als het verzoek slaagt, levert de REST van de SharePoint-Zoek REST-API antwoordgegevens op.

**Vereiste**

Voor elke geografische locatie moet u ervoor zorgen dat alle gebruikers in de organisatie het machtigingsniveau **lezen** voor de hoofdwebsite hebben gekregen (bijvoorbeeld contoso**APAC**. SharePoint.com/en contoso**EU**. SharePoint.com/). [Meer informatie over machtigingen](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).

### <a name="query-parameters"></a>Query parameters

EnableMultiGeoSearch: dit is een Booleaanse waarde die aangeeft of de query moet worden fanned naar de indexen van andere geografische locaties van de multigeo-Tenant. Stel deze in op **waar** om de query uit te waaieren. **Onwaar** om de query niet uit te waaieren. Als u deze parameter niet opneemt, is de standaardwaarde **Onwaar**, behalve wanneer u een rest API-oproep maakt voor een site die gebruikmaakt van de sjabloon Enterprise Search Center, in dit geval de standaardwaarde **waar**is. Als u de parameter in een omgeving gebruikt die geen deel uitmaakt van meerdere geografische regels, wordt de parameter genegeerd.

ClientType: dit is een tekenreeks. Voer voor elke zoektoepassing een unieke naam voor de client in. Als u deze parameter niet opneemt, is de query niet fanned naar andere geo-locaties.

MultiGeoSearchConfiguration: dit is een optionele lijst met de geografische locaties in de Tenant Tenant om de query uit te waaieren op als **EnableMultiGeoSearch** **waar**is. Als u deze parameter niet opneemt of leeg laat, is de query fanned naar alle geografische locaties. Voor elke geografische locatie voert u de volgende items in, in JSON-indeling:

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
<td align="left">De geografische locatie van bijvoorbeeld de vestiging.</td>
</tr>
<tr class="even">
<td align="left">Conversatie</td>
<td align="left">Het eindpunt waarmee u verbinding wilt maken, bijvoorbeeld https://contoso.sharepoint.com</td>
</tr>
<tr class="odd">
<td align="left">Id</td>
<td align="left">De GUID van de resultatenbron, bijvoorbeeld B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</td>
</tr>
</tbody>
</table>

Als u DataLocation of eindpunt weglaat, of als een DataLocation wordt gedupliceerd, mislukt de aanvraag. [U vindt informatie over het eindpunt van de geografische locaties van een Tenant met behulp van Microsoft Graph](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-discovery).

### <a name="response-data"></a>Antwoordgegevens

MultiGeoSearchStatus: dit is een eigenschap die de SharePoint-zoek-API retourneert in antwoord op een aanvraag. De waarde van de eigenschap is een tekenreeks die de volgende informatie oplevert over de resultaten die de SharePoint-zoek-API retourneert:

<table>
<thead>
<tr class="header">
<th align="left">Value</th>
<th align="left">Beschrijving</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Vol</td>
<td align="left">Volledige resultaten van <strong>alle</strong> geografische locaties.</td>
</tr>
<tr class="even">
<td align="left">Partijdig</td>
<td align="left">Gedeeltelijke resultaten van een of meer geo-locaties. De resultaten zijn onvolledig vanwege een tijdelijke fout.</td>
</tr>

</tbody>
</table>

### <a name="query-using-the-rest-service"></a>Query met behulp van de REST dienst

Met een aanvraag voor ophalen geeft u de queryparameters op in de URL. Met een bericht na een bericht geeft u de queryparameters in de hoofdtekst in de JSON-indeling (Object Notation) door.


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
<td align="left">Inhouds type</td>
<td align="left">application/json; odata = uitgebreid</td>
</tr>
</tbody>
</table>

#### <a name="sample-get-request-thats-fanned-out-to-all-geo-locations"></a>Voorbeeld van een aanvraag voor het aanvragen van fanned naar **alle** geo-locaties

https:// \<tenant\> / \_ API/search/query? QueryText = ' SharePoint ' &Properties = ' EnableMultiGeoSearch: True ' &ClientType = ' mijn \_ client \_ -id '

#### <a name="sample-get-request-to-fan-out-to-some-geo-locations"></a>Voorbeeld van aanvraag voor het aanvragen van een uitwaaiering voor **een aantal** geografische locaties

https:// \<tenant\> / \_ API/search/query? QueryText = ' site ' &ClientType = ' my_client_id ' &eigenschappen = ' EnableMultiGeoSearch: True, MultiGeoSearchConfiguration: [{DataLocation \\ : "naam" \\ , eindpunt \\ : "https \\ ://contosoNAM.SharePoint.com" \\ , SourceId \\ : "B81EAB55-3140-4312-B0F4-9459D1B4FFEE"} \\ , {DataLocation: " \\ can" \\ , eindpunt \\ : "https \\ ://contosoCAN.SharePoint-DF.com"}] "

> [!NOTE]
> Komma's en dubbele punten in de lijst met geografische locaties voor de eigenschap MultiGeoSearchConfiguration worden voorafgegaan door het **backslash** teken. Dit komt doordat aanvragen voor aanvragen gebruikmaken van dubbele puntjes om eigenschappen en komma's te scheiden en de argumenten van eigenschappen te scheiden. Zonder backslash als een escape-teken, wordt de eigenschap MultiGeoSearchConfiguration niet op de juiste wijze geïnterpreteerd.

#### <a name="sample-post-request-thats-fanned-out-to-all-geo-locations"></a>Voorbeeld van een bericht dat is fanned naar **alle** geografische locaties

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


#### <a name="sample-post-request-thats-fanned-out-to-some-geo-locations"></a>Voorbeeld van een bericht dat is fanned naar **een aantal** geografische locaties


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

### <a name="query-using-csom"></a>Query met behulp van CSOM

Hier ziet u een voorbeeld van een CSOM-query die is fanned voor **alle** geo-locaties:

    var keywordQuery = new KeywordQuery(ctx);
    keywordQuery.QueryText = query.SearchQueryText;
    keywordQuery.ClientType = <enter a string here>;
    keywordQuery["EnableMultiGeoSearch"] = true;

