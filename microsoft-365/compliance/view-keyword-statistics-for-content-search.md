---
title: Trefwoordstatistieken weergeven voor resultaten van inhoudszoekactie
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/30/2017
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 9701a024-c52e-43f0-b545-9a53478aec04
description: Meer informatie over het gebruik van de functie Zoekstatistieken om statistieken weer te geven en te vergelijken voor meerdere zoekopdrachten naar inhoud in & compliancecentrum.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f12c51c47045996e450772c081bd26ef4a520b5f
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/17/2021
ms.locfileid: "52161753"
---
# <a name="view-keyword-statistics-for-content-search-results"></a>Trefwoordstatistieken weergeven voor resultaten van inhoudszoekactie

Nadat u een inhoudszoekactie hebt gestart en uitgevoerd, kunt u statistieken bekijken over de geschatte zoekresultaten. Dit omvat een overzicht van de zoekresultaten (vergelijkbaar met de samenvatting van de geschatte zoekresultaten die worden weergegeven in het detailvenster), de querystatistieken, zoals het aantal inhoudslocaties met items die overeenkomen met de zoekquery en de naam van inhoudslocaties met de meest overeenkomende items. U kunt statistieken weergeven voor een of meer zoekopdrachten naar inhoud. Op deze manier kunt u snel de resultaten van meerdere zoekopdrachten vergelijken en beslissingen nemen over de effectiviteit van uw zoekquery's.
  
Daarnaast kunt u nieuwe en bestaande zoekopdrachten configureren om statistieken te retourneren voor elk trefwoord in een zoekquery. Op deze manier kunt u het aantal resultaten van elk trefwoord in een query vergelijken en de trefwoordstatistieken van meerdere zoekopdrachten vergelijken.
  
U kunt ook de zoekstatistieken en trefwoordstatistieken downloaden naar een CSV-bestand. Op deze manier kunt u de filter- en sorteerfuncties in Excel gebruiken om resultaten te vergelijken en rapporten voor te bereiden op uw zoekresultaten.
  
## <a name="get-statistics-for-content-searches"></a>Statistieken voor zoeken naar inhoud downloaden

Statistieken weergeven voor zoeken naar inhoud:
  
1. Ga in Microsoft 365 compliancecentrum naar **Alle inhoud**  >  **zoeken.**

2. Selecteer in de lijst met zoekopdrachten twee of meer zoekopdrachten en klik vervolgens op Zoekstatistieken **op** de flyoutpagina **Bulkacties.**
    
    ![Selecteer meerdere zoekopdrachten en klik vervolgens op Zoekstatistieken](../media/1195c6c3-2e00-469d-8c29-85c1c7ebe6c7.png)
  
3. Klik op **de pagina** Zoekstatistieken op een van de volgende koppelingen om statistieken weer te geven over de geselecteerde zoekopdrachten. 
    
    **Samenvatting**
    
    Op deze pagina worden statistieken weergegeven die vergelijkbaar zijn met de statistieken die worden weergegeven in het detailvenster op de **pagina Inhoud zoeken.** Statistieken voor alle geselecteerde zoekopdrachten worden weergegeven. U kunt de geselecteerde zoekopdrachten ook opnieuw uitvoeren vanaf deze pagina om de statistieken bij te werken. 
    
    ![Overzicht van de statistieken voor de geselecteerde zoekopdrachten](../media/abb663eb-b3d6-4f4c-a99f-55d20b0848af.png)
  
    a.  De naam van het zoeken naar inhoud. Zoals eerder vermeld, kunt u statistieken voor meerdere zoekopdrachten weergeven en vergelijken.
    
    b. Het type inhoudslocatie dat is doorzocht. In elke rij worden statistieken weergegeven voor postvakken, sites en openbare mappen uit de opgegeven zoekopdracht.
    
    c. Het aantal inhoudslocaties met items die overeenkomen met de zoekquery. Voor postvakken bevat deze statistiek ook het aantal archiefpostvakken dat items bevat die overeenkomen met de zoekquery.
    
    d. Het totale aantal items van alle opgegeven inhoudslocaties die overeenkomen met de zoekquery. Voorbeelden van itemtypen zijn e-mailberichten, agenda-items en documenten. Als een item meerdere exemplaren bevat van een trefwoord dat wordt gezocht, wordt dit slechts eenmaal geteld in het totale aantal items. Als u bijvoorbeeld zoekt naar woorden 'aandelen' of 'fraude' en een e-mailbericht drie exemplaren bevat van het woord 'aandelen', wordt dit slechts eenmaal geteld in de kolom **Items.** 
    
    e. De totale grootte van alle items die zijn gevonden op de opgegeven inhoudslocatie die overeenkomen met de zoekquery. 
    
    **Query's**
    
    Op deze pagina worden statistieken over de zoekquery weergegeven.
    
    ![Querystatistieken zoeken voor de geselecteerde zoekopdrachten](../media/dc817526-dfb9-43d3-a14c-4c58077eb7bb.png)
  
    a. De naam van het zoeken naar inhoud waar de rij querystatistieken voor bevat.
    
    b. Het type inhoudslocatie waar de querystatistieken op van toepassing zijn.
    
    c. In deze kolom wordt aangegeven op welk deel van de zoekquery de statistieken van toepassing zijn. **Primair** geeft de hele zoekquery aan. Als u een trefwoordlijst gebruikt wanneer u een zoekquery maakt of bewerkt, worden statistieken voor elk onderdeel van de query in deze tabel opgenomen. Zie de [sectie Trefwoordstatistieken voor zoeken](#get-keyword-statistics-for-content-searches) naar inhoud in dit artikel voor meer informatie. 
    
    d. Deze kolom bevat de werkelijke zoekquery die wordt uitgevoerd door het hulpprogramma Inhoud zoeken. Houd er rekening mee dat het hulpprogramma automatisch een paar extra onderdelen toevoegt aan de query die u maakt. 

    - Wanneer u zoekt naar alle inhoud in postvakken (door geen trefwoorden op te geven), is de werkelijke woordquery zo dat alle  `size>=0` items worden geretourneerd. 
    
     - Wanneer u op SharePoint Online en OneDrive voor Bedrijven sites, worden de twee volgende onderdelen toegevoegd:
    
          **NOT IsExternalContent:1** : Sluit inhoud uit van een on-premises SharePoint organisatie. 
    
          **NOT IsOneNotePage:1:** alle bestanden OneNote uitgesloten, omdat dit duplicaten zijn van elk document dat overeenkomt met de zoekquery. 

    
    e. Het aantal inhoudslocaties (opgegeven door de kolom ** Locatietype ** die items bevatten die overeenkomen met de zoekquery die in de **kolom Query wordt** vermeld. 
    
    f. Het aantal items (van de opgegeven inhoudslocatie) dat overeenkomen met de zoekquery in de **kolom** Query. Zoals eerder uitgelegd, als een item meerdere exemplaren bevat van een trefwoord dat wordt gezocht, wordt dit slechts eenmaal geteld in deze kolom. 
    
    g. De totale grootte van alle items die zijn gevonden (op de opgegeven inhoudslocatie) die overeenkomen met de zoekquery in de **kolom** Query. 
    
    **Toplocaties**
    
    Op deze pagina worden statistieken weergegeven over het aantal items dat overeenkomen met de zoekquery op elke gezochte inhoudslocatie. De bovenste 1000 locaties worden weergegeven. Als u statistieken voor meerdere zoekopdrachten bekijkt, worden de bovenste 1000 locaties voor elke zoekopdracht weergegeven. Houd er rekening mee dat er geen inhoudslocatie is opgenomen op deze pagina als deze geen items bevat die overeenkomen met de zoekquery.
    
    ![Statistieken over het aantal items dat is gevonden in de inhoudslocaties die zijn doorzocht](../media/35a820b0-85d9-45d1-9a0c-c74bec803e67.png)
  
    a. De naam van de inhoudslocatie.
    
    b. Het type inhoudslocatie waar de locatiestatistieken op van toepassing zijn.
    
    c. Er zijn kolommen voor elke zoekopdracht waar u statistieken voor wilt weergeven. In deze kolom ziet u het aantal (en de totale grootte) van items die overeenkomen met de zoekquery op elke inhoudslocatie. Houd er rekening mee dat wanneer u statistieken voor meerdere zoekopdrachten we weergeven, de 'NA' in deze kolom aangeeft dat de inhoudslocatie niet is opgenomen in die zoekopdracht. 

## <a name="get-keyword-statistics-for-content-searches"></a>Trefwoordstatistieken voor zoeken naar inhoud downloaden

Zoals eerder uitgelegd, worden op de pagina **Query's** de zoekquery en het aantal (en de grootte) van items weergegeven die overeenkomen met de query. Als u een lijst met trefwoorden gebruikt wanneer u een zoekquery maakt of bewerkt, kunt u uitgebreide statistieken krijgen die laten zien hoeveel items overeenkomen met elk trefwoord of trefwoord. Op deze manier kunt u snel bepalen welke onderdelen van de query het meest (en het minst) effectief zijn. Als een trefwoord bijvoorbeeld een groot aantal items retourneert, kunt u ervoor kiezen om de trefwoordquery te verfijnen om de zoekresultaten te verfijnen. U kunt een trefwoordlijst instellen wanneer u een inhoudszoekactie maakt of bewerkt. 

Een trefwoordlijst maken en trefwoordstatistieken weergeven voor een inhoudszoekactie:
  
1. Ga in Microsoft 365 compliancecentrum naar **Alle inhoud**  >  **zoeken.**
    
2. Klik in de lijst met inhoudszoekbewerkingen op een zoekopdracht en klik vervolgens op **Pictogram** ![ Bewerken ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) bewerken.
    
3. Klik **op Query** en ga vervolgens als volgt te werk: 
    
    ![Klik op het selectievakje Trefwoordlijst tonen en typ een trefwoord in elke rij](../media/73ef46dd-3d5c-415d-b5e7-c3559caaafe2.png)
  
    a. Klik op **het selectievakje Trefwoordlijst weergeven.** 
    
    b. Typ een trefwoord of trefwoordfase in een rij in de trefwoordentabel. Typ bijvoorbeeld **budget** in de eerste rij en typ vervolgens **beveiliging** in de tweede rij. 
    
4. Nadat u de trefwoorden hebt toegevoegd die u wilt zoeken en statistieken wilt krijgen, klikt u **op** Zoeken om de gewijzigde zoekopdracht uit te voeren. 
    
5. Wanneer de zoekopdracht is voltooid, selecteert u deze in de lijst met zoekopdrachten en klikt u vervolgens op **de** knop ![ ](../media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png) Zoekstatistieken. U kunt ook trefwoordstatistieken weergeven en vergelijken voor meerdere zoekopdrachten.
    
6. Klik op **de pagina Zoekstatistieken** op **Query om** de trefwoordstatistieken weer te geven voor de geselecteerde zoekopdrachten. 
    
    ![De statistieken voor elk trefwoord voor de geselecteerde zoekopdrachten worden weergegeven](../media/e7910fa9-af93-4df9-92d0-e1e3e089e14f.png)
  
    Zoals in de vorige schermafbeelding wordt weergegeven, worden de statistieken voor elk trefwoord weergegeven. dit omvat: 
    
    - De trefwoordstatistieken voor elk type inhoudslocatie dat is opgenomen in de zoekopdracht.
    
    - De werkelijke zoekquery voor elk trefwoord, met alle voorwaarden uit de zoekquery. 
    
    - De volledige zoekquery (die is geïdentificeerd als **primair** in de **kolom** Onderdeel) en de statistieken voor de volledige query. Houd er rekening mee dat dit dezelfde statistieken zijn die worden weergegeven op de **pagina** Overzicht. 

> [!NOTE]
> Als u problemen wilt beperken die worden veroorzaakt door grote trefwoordlijsten, bent u nu beperkt tot maximaal 20 rijen in de trefwoordlijst van een zoekquery.
