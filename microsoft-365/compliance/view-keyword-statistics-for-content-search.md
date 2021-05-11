---
title: Statistieken weergeven voor eDiscovery-zoekresultaten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Lees hoe u de functie zoekstatistieken kunt gebruiken om statistieken weer te geven voor zoekopdrachten en zoekopdrachten voor inhoud die zijn gekoppeld aan een hoofd-eDiscovery-zaak in het Microsoft 365 compliancecentrum.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311094"
---
# <a name="view-statistics-for-ediscovery-search-results"></a>Statistieken weergeven voor eDiscovery-zoekresultaten

Nadat u een inhoudszoekactie of een zoekopdracht hebt uitgevoerd die is gekoppeld aan een Hoofd-eDiscovery-zaak, kunt u statistieken bekijken over de geschatte zoekresultaten. Dit omvat een overzicht van de zoekresultaten (vergelijkbaar met de samenvatting van de geschatte zoekresultaten die worden weergegeven op de flyoutpagina voor zoeken), de querystatistieken, zoals het aantal inhoudslocaties met items die overeenkomen met de zoekquery en de identiteit van inhoudslocaties met de meest overeenkomende items.
  
Daarnaast kunt u de lijst met trefwoorden gebruiken om een zoekopdracht te configureren om statistieken te retourneren voor elk trefwoord in een zoekquery. Hiermee kunt u het aantal resultaten vergelijken dat door elk trefwoord in een query wordt geretourneerd.
  
U kunt ook zoekstatistieken downloaden naar een CSV-bestand. Op deze manier kunt u de filter- en sorteerfuncties in Excel gebruiken om resultaten te vergelijken en rapporten voor te bereiden op uw zoekresultaten.
  
## <a name="get-statistics-for-searches"></a>Statistieken voor zoekopdrachten krijgen

Als u statistieken wilt weergeven voor een inhoudszoekactie of een zoekopdracht die is gekoppeld aan een hoofd-eDiscovery-zaak.:
  
1. Klik in Microsoft 365 compliancecentrum op **Alles tonen** en ga op een van de volgende dingen te werk:

   - Klik **op Inhoud zoeken** en selecteer vervolgens een zoekopdracht om de flyoutpagina weer te geven.

     OF

   - Klik **op eDiscovery** Core, selecteer een hoofddeksel en selecteer vervolgens een zoekopdracht op het tabblad Zoekopdrachten om de  >  flyoutpagina weer te geven. 

2. Klik op de flyoutpagina van de geselecteerde zoekopdracht op **het tabblad Statistieken** zoeken.
  
   ![Het tabblad Zoekstatistieken](../media/SearchStatistics1.png)

Het **tabblad Zoekstatistieken** bevat voor volgende secties die verschillende soorten statistieken over de zoekopdracht bevatten.

### <a name="search-content"></a>Inhoud zoeken

In deze sectie wordt een grafische samenvatting weergegeven van de geschatte items die door de zoekopdracht worden geretourneerd. Dit geeft het aantal items aan dat voldoet aan de zoekcriteria. Deze informatie geeft een idee van het geschatte aantal items dat door de zoekopdracht wordt geretourneerd.

![Zoekschattingen voor een zoekopdracht](../media/SearchContentReport.png)

- **Geschatte items per locatie:** het totale aantal geschatte items dat door de zoekopdracht wordt geretourneerd. Het specifieke aantal items in postvakken en op sites wordt ook weergegeven.

- **Geschatte locaties met hits:** het totale aantal inhoudslocaties dat items bevat die door de zoekopdracht zijn geretourneerd. Het specifieke aantal postvakken en sitelocaties wordt ook weergegeven.

- **Gegevensvolume per locatie (in MB)**: de totale grootte van alle geschatte items die door de zoekopdracht worden geretourneerd. De specifieke grootte van postvakitems en site-items wordt ook weergegeven.

### <a name="condition-report"></a>Rapport Voorwaarde

In deze sectie worden statistieken weergegeven over de zoekquery en het aantal geschatte items dat overeenkomen met verschillende onderdelen van de zoekquery. U kunt deze statistieken gebruiken om het aantal items te analyseren dat overeenkomen met elk onderdeel van de zoekquery. Dit kan u helpen de zoekcriteria te verfijnen en zo nodig het bereik van het bereik te beperken. U kunt ook een kopie van dit rapport downloaden in CSV-indeling.

![Rapport Voorwaarde](../media/SearchContentReportNoKeywordList.png)

- **Locatietype:** Het type inhoudslocatie waar de querystatistieken op van toepassing zijn. De waarde van **Exchange** geeft een postvaklocatie aan. een waarde van **SharePoint** geeft een sitelocatie aan.

- **Deel**: Het deel van de zoekquery waar de statistieken op van toepassing zijn. **Primair** geeft de hele zoekquery aan. **Trefwoord** geeft aan dat de statistieken in de rij voor een specifiek trefwoord zijn. Als u een trefwoordlijst voor zoekquery gebruikt, worden statistieken voor elk onderdeel van de query opgenomen in deze tabel. Zie Trefwoordstatistieken [voor zoekopdrachten voor meer informatie.](#get-keyword-statistics-for-searches)

- **Voorwaarde:** Het werkelijke onderdeel (trefwoord of voorwaarde) van de zoekquery die de statistieken heeft geretourneerd die in de bijbehorende rij worden weergegeven.

- **Locaties met treffers:** het aantal inhoudslocaties (opgegeven door de kolom Locatietype) die items bevatten die overeenkomen met de primaire query of trefwoordquery in de kolom **Voorwaarde.** 

- **Items:** Het aantal items (van de opgegeven inhoudslocatie) dat overeenkomen met de query die wordt weergegeven in **de** kolom Voorwaarde. Zoals eerder uitgelegd, als een item meerdere exemplaren bevat van een trefwoord dat wordt gezocht, wordt dit slechts eenmaal geteld in deze kolom.

- **Grootte (MB)**: De totale grootte van alle items die zijn gevonden (op de opgegeven inhoudslocatie) die overeenkomen met de zoekquery in **de** kolom Voorwaarde.

### <a name="top-locations"></a>Toplocaties

In deze sectie worden statistieken weergegeven over de specifieke inhoudslocaties met de meeste items die door de zoekopdracht worden geretourneerd. De bovenste 1000 locaties worden weergegeven. U kunt ook een kopie van dit rapport downloaden in CSV-indeling.

- De naam van de locatienaam (het e-mailadres van postvakken en de URL voor sites).

- Locatietype (een postvak of site).

- Geschatte hoeveelheid items op de inhoudslocatie die door de zoekopdracht wordt geretourneerd.

- De totale grootte van geschatte items op elke inhoudslocatie.

## <a name="get-keyword-statistics-for-searches"></a>Trefwoordstatistieken voor zoekopdrachten krijgen

Zoals eerder uitgelegd, worden in **de sectie Rapport** Voorwaarde de zoekquery en het aantal items (en de grootte) van de items die overeenkomen met de query, in de sectie Voorwaarde. Als u een lijst met trefwoorden gebruikt wanneer u een zoekquery maakt of bewerkt, kunt u uitgebreide statistieken krijgen die laten zien hoeveel items overeenkomen met elk trefwoord of trefwoord. Op deze manier kunt u snel bepalen welke onderdelen van de query het meest (en het minst) effectief zijn. Als een trefwoord bijvoorbeeld een groot aantal items retourneert, kunt u ervoor kiezen om de trefwoordquery te verfijnen om de zoekresultaten te verfijnen.

Een trefwoordlijst maken en trefwoordstatistieken weergeven voor een zoekopdracht:
  
1. Maak in Microsoft 365 compliancecentrum een nieuwe inhoudszoekactie of een zoekopdracht die is gekoppeld aan een core eDiscovery-zaak.

2. Op de **pagina Voorwaarden** van de wizard Zoeken. schakel het **selectievakje Trefwoordlijst tonen** in.

   ![Selectievakje Trefwoordenlijst weergeven](../media/SearchKeywordsList1.png)

3. Typ een trefwoord of trefwoordfase in een rij in de trefwoordentabel. Typ bijvoorbeeld **budget** in de eerste rij, typ **beveiliging** in de tweede rij en typ **FY2021** in de derde rij.

   ![Typ maximaal 20 trefwoorden of trefwoordzinnen in de lijst](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > Als u problemen wilt beperken die worden veroorzaakt door grote lijsten met trefwoorden, kunt u maximaal 20 rijen in de lijst met trefwoorden van een zoekquery gebruiken.

4. Nadat u de trefwoorden hebt toegevoegd aan de lijst die u wilt zoeken en statistieken wilt krijgen, kunt u de zoekopdracht uitvoeren.

5. Wanneer de zoekopdracht is voltooid, selecteert u deze om de flyoutpagina weer te geven.

6. Klik op **het tabblad Zoekstatistieken** op het **rapport Voorwaarde om** de trefwoordstatistieken voor de zoekopdracht weer te geven.

    ![De statistieken voor elk trefwoord worden weergegeven](../media/SearchKeywordsList3.png)
  
    Zoals in de vorige schermafbeelding wordt weergegeven, worden de statistieken voor elk trefwoord weergegeven. dit omvat:

    - De trefwoordstatistieken voor elk type inhoudslocatie dat is opgenomen in de zoekopdracht.

    - Het aantal niet-geïndexeerde postvakitems.

    - De werkelijke zoekquery en de resultaten voor  elk trefwoord (geïdentificeerd als Trefwoord **in** de kolom Onderdeel), met alle voorwaarden uit de zoekquery.

    - De volledige zoekquery (die  is geïdentificeerd als **primair** in de kolom Onderdeel) en de statistieken voor de volledige query voor elk locatietype. Let op: dit zijn dezelfde statistieken die worden weergegeven op het **tabblad** Overzicht.
