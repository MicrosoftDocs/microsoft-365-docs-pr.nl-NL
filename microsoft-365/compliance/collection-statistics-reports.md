---
title: Verzamelingsstatistieken en -rapporten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Lees hoe u statistieken en rapporten kunt openen en gebruiken voor conceptverzamelingen en verzamelingen die zijn vastgelegd voor een revisieset in Advanced eDiscovery.
ms.openlocfilehash: 5edbd4a3b7212e027c777ed6ce5284f4e9cf595c
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/17/2021
ms.locfileid: "52161744"
---
# <a name="collection-statistics-and-reports-in-advanced-ediscovery"></a>Statistische gegevens en rapporten verzamelen in Advanced eDiscovery

Nadat u een conceptverzameling hebt gemaakt, kunt u statistieken bekijken over de opgehaalde items, zoals de inhoudslocaties die de meeste items bevatten die overeenkomen met de zoekcriteria en het aantal items dat door de zoekquery wordt geretourneerd. U kunt ook een voorbeeld van een subset van de resultaten bekijken.

Wanneer u de set documenten hebt geïdentificeerd die u verder wilt onderzoeken, kunt u de zoekresultaten toevoegen aan een revisieset die u wilt verzamelen en verwerken.

## <a name="statistics-and-reports-for-draft-collections"></a>Statistieken en rapporten voor conceptverzamelingen

In deze sectie worden de statistieken beschreven die beschikbaar zijn voor conceptverzamelingen. Deze statistieken zijn beschikbaar op het tabblad **Zoekstatistieken** op de flyoutpagina van een conceptverzameling.

### <a name="collection-estimates"></a>Verzamelingsschattingen

In deze sectie wordt een grafische samenvatting weergegeven van de geschatte items die door de verzameling worden geretourneerd. Dit geeft het aantal items aan dat voldoet aan de zoekcriteria van de verzameling. Deze informatie geeft een idee van het geschatte aantal items dat door de verzameling wordt geretourneerd.

![Verzamelingsramingen voor een conceptverzameling](../media/AeDCollectionEstimates.png)

- **Geschatte items per locatie:** het totale aantal geschatte items dat door de verzameling wordt geretourneerd. Het specifieke aantal items in postvakken en op sites wordt ook weergegeven.

- **Geschatte locaties met hits:** het totale aantal inhoudslocaties dat items bevat die door de verzameling worden geretourneerd. Het specifieke aantal postvakken en sitelocaties wordt ook weergegeven.

- **Gegevensvolume per locatie (in MB)**: de totale grootte van alle geschatte items die door de verzameling worden geretourneerd. De specifieke grootte van postvakitems en site-items wordt ook weergegeven.

### <a name="condition-report"></a>Rapport Voorwaarde

In deze sectie worden statistieken weergegeven over de zoekquery van de verzameling en het aantal geschatte items dat overeenkomen met verschillende onderdelen van de zoekquery. U kunt deze statistieken gebruiken om het aantal items te analyseren dat overeenkomen met elk onderdeel van de zoekquery. Hiermee kunt u de zoekcriteria voor de verzameling verfijnen en zo nodig het bereik van de verzameling beperken.

- **Locatietype:** Het type inhoudslocatie waar de querystatistieken op van toepassing zijn. De waarde van **Exchange** geeft een postvaklocatie aan. een waarde van **SharePoint** geeft een sitelocatie aan.

- **Deel**: Het deel van de zoekquery waar de statistieken op van toepassing zijn. **Primair** geeft de hele zoekquery aan. **Trefwoord** geeft aan dat de statistieken in de rij voor een specifiek trefwoord zijn. Als u een trefwoordlijst gebruikt voor de zoekquery in de verzameling, worden statistieken voor elk onderdeel van de query in deze tabel opgenomen.

- **Voorwaarde:** het werkelijke onderdeel (trefwoord of voorwaarde) van de zoekquery die is uitgevoerd voor de conceptverzameling die de statistieken heeft geretourneerd die in de bijbehorende rij worden weergegeven.

- **Locaties met treffers:** het aantal inhoudslocaties (opgegeven door de kolom Locatietype) die items bevatten die overeenkomen met de primaire query of trefwoordquery in de kolom **Voorwaarde.** 

- **Items:** Het aantal items (van de opgegeven inhoudslocatie) dat overeenkomen met de query die wordt weergegeven in **de** kolom Voorwaarde. Zoals eerder uitgelegd, als een item meerdere exemplaren bevat van een trefwoord dat wordt gezocht, wordt dit slechts eenmaal geteld in deze kolom.

- **Grootte (MB)**: De totale grootte van alle items die zijn gevonden (op de opgegeven inhoudslocatie) die overeenkomen met de zoekquery in **de** kolom Voorwaarde.

### <a name="top-locations"></a>Toplocaties

In deze sectie worden statistieken weergegeven over de specifieke inhoudslocaties met de meeste items die door de verzameling worden geretourneerd.

- De naam van de locatienaam (het e-mailadres van postvakken en de URL voor sites).

- Locatietype (een postvak of site).

- Geschatte hoeveelheid items op de inhoudslocatie die door de verzameling wordt geretourneerd.

- De totale grootte van geschatte items op elke inhoudslocatie.

## <a name="statistics-and-reports-for-committed-collections"></a>Statistieken en rapporten voor vastgelegde verzamelingen

In deze sectie worden de statistieken beschreven die beschikbaar zijn nadat u een verzameling hebt toegevoegd aan een revisieset, inclusief het werkelijke aantal items dat aan de revisieset is toegevoegd. Deze statistieken (naast gegevens over ladensets) bevatten historische informatie over inhoud die aan een zaak is toegevoegd.

Nadat u een verzameling hebt toegevoegd aan een revisieset, worden de volgende tabbladen weergegeven op de flyoutpagina van de vastgelegde verbinding. Elk van deze tabbladen bevat verschillende typen informatie over de verzameling.

![Tabbladen op flyoutpagina van vastgelegde verzameling](../media/CommittedCollectionFlyoutPage.png)

### <a name="collection-contents"></a>Inhoud van verzameling

Deze sectie van het **tabblad** Samenvatting bevat statistieken en andere informatie over de items die zijn verzameld uit de gegevensbronnen in de verzameling en zijn toegevoegd aan de revisieset.

- **Totaal uitgepakte items**. Het totale aantal items dat is toegevoegd aan de revisieset. Dit getal geeft de som aan van bovenliggende items en onderliggende items die aan de revisieset zijn toegevoegd.

  > [!TIP]
  > Plaats de cursor op de bovenliggende of onderliggende itembalken om het totale aantal bovenliggende of onderliggende items weer te geven.

- **Bovenliggende items**. Het aantal items dat is geretourneerd door de verzameling die is gebruikt om de items te verzamelen die zijn toegevoegd aan de revisieset. Dit getal komt overeen met (en is gelijk aan) het geschatte aantal items dat wordt weergegeven in de sectie **Verzamelingsparameters.** Het aantal bovenliggende items dat hij heeft verzameld om de items te verzamelen die aan de revisieset zijn toegevoegd.
 
   Een bovenliggend item kan meerdere onderliggende items bevatten. Een e-mailbericht is bijvoorbeeld een bovenliggend item als het een bijgevoegd bestand bevat of een cloudbijlage bevat. In dit geval worden het bijgevoegde bestand of het doel van de cloudbijlage beschouwd als onderliggende items. Wanneer u een verzameling begaat, worden bovenliggende items en bijbehorende onderliggende items als afzonderlijke items of bestanden toegevoegd aan de revisieset.

- **Onderliggende items**. Het aantal onderliggende items dat is toegevoegd aan de revisieset. Onderliggende items zijn bijlagen of andere onderdelen van een bovenliggend item. Onderliggende items zijn bijgevoegde bestanden, cloudbijlagen, afbeeldingen en e-mailhandtekeningen. Wanneer u een verzameling aan een revisieset verbindt, worden onderliggende items geëxtraheerd, geïndexeerd en toegevoegd aan de revisieset als afzonderlijke bestanden.

- **Unieke items.** Het aantal unieke items dat is toegevoegd aan de revisieset. Unieke items zijn uniek voor de revisieset. Alle items zijn uniek wanneer de eerste verzameling wordt toegevoegd aan een nieuwe revisieset omdat er geen eerdere items in de revisieset waren.

- **Geïdentificeerde dubbele items**. Het aantal items uit de verzameling dat niet is toegevoegd aan de revisieset omdat hetzelfde item al bestaat in de revisieset. Statistieken over dubbele items kunnen helpen bij het verklaren van de verschillen tussen het aantal geschatte items uit een conceptverzameling en het werkelijke aantal items dat aan de revisieset is toegevoegd.

### <a name="indexing"></a>Indexeren

De **sectie Indexering** op **het** tabblad Overzicht van een vastgelegde revisieset bevat indexeringsgegevens over de items die aan de revisieset zijn toegevoegd.

**Nieuwe geïndexeerde items**. Het aantal items dat onlangs is geïndexeerd voordat ze aan de revisieset zijn toegevoegd. Een voorbeeld van een nieuw geïndexeerd item zijn onderliggende items die worden geëxtraheerd uit een bovenliggend item en vervolgens worden geïndexeerd voordat ze worden toegevoegd aan de revisieset. Items die zich niet bevinden in bewaargegevensbronnen en niet-bewaarder-inhoudslocaties die worden vermeld op het tabblad Gegevensbronnen in de zaak, worden ook geïndexeerd voordat ze aan de revisie worden toegevoegd.  Nieuw geïndexeerde items bevatten bijvoorbeeld items die zijn verzameld op extra locaties.

**Bijgewerkte geïndexeerde items**. Het aantal gedeeltelijk geïndexeerde items dat is geïndexeerd en toegevoegd aan de revisieset. Hierdoor zouden items uit bewaar- en niet-bewaarder-inhoudslocaties gedeeltelijk worden geïndexeerd op het tabblad Gegevensbronnen die met succes zijn geïndexeerd toen de verzameling werd vastgelegd in de revisieset. 

**Indexeringsfouten**. Het aantal gedeeltelijk geïndexeerde items dat niet kon worden geïndexeerd voordat ze aan de revisieset werden toegevoegd. Voor deze items is mogelijk een foutsanering vereist.

### <a name="collection-parameters"></a>Verzamelingsparameters

In deze sectie worden de verzamelingsgegevens weergegeven die zijn gebruikt om de items te verzamelen die zijn toegevoegd aan de revisieset. Op dit tabblad worden gegevens weergegeven die vergelijkbaar zijn met de informatie op het **tabblad Zoekstatistieken.** In deze sectie vindt u een beknopt overzicht van de zoekquery die door de verzameling wordt gebruikt, de inhoudslocaties die zijn doorzocht en de geschatte verzamelingsresultaten. Zoals eerder uitgelegd, zou het aantal geschatte items in deze sectie gelijk zijn aan het aantal bovenliggende items dat wordt weergegeven in de sectie **Verzamelingsinhoud.**

### <a name="search-statistics-tab"></a>Tabblad Zoekstatistieken

De statistieken die worden weergegeven op het tabblad **Zoekstatistieken** zijn dezelfde statistieken als de laatste keer dat een conceptverzameling is uitgevoerd. Dit omvat verzamelingsschattingen, rapport met voorwaarden en toplocaties. Deze gegevens worden bewaard in de conceptverzameling voor historische verwijzingen en kunnen worden vergeleken met de werkelijke verzameling die is vastgelegd in de revisieset.

## <a name="differences-between-draft-collection-estimates-and-the-actual-committed-collection"></a>Verschillen tussen conceptverzamelingsschattingen en de werkelijke vastgelegde verzameling

Wanneer u een conceptverzameling uit te voeren, wordt een schatting weergegeven van het aantal  items (en de totale grootte) dat voldoet aan de verzamelingscriteria op het tabblad Overzicht en in de sectie **Verzamelingsschattingen** van het tabblad Zoekstatistieken.  Nadat u een conceptverzameling hebt toegevoegd aan een revisieset, verschilt het werkelijke aantal items (en de totale grootte) van de revisieset vaak van de schattingen. In de meeste gevallen worden er meer items aan de revisieset toegevoegd dan uit de conceptverzameling is geraamd. In de volgende lijst worden de meest voorkomende redenen voor deze verschillen en tips voor het identificeren van deze verschillen beschreven:

- **Onderliggende items**. Onderliggende items die worden geëxtraheerd uit de bovenliggende items en als afzonderlijke bestanden worden toegevoegd. Het aantal onderliggende items kan het aantal items dat daadwerkelijk aan de revisieset wordt toegevoegd aanzienlijk verhogen. In het algemeen moet het aantal  bovenliggende items  dat is geïdentificeerd in de sectie Verzamelingsinhoud op het tabblad Overzicht van een vastgelegde verzameling, gelijk zijn aan het aantal geschatte items uit de conceptverzameling.

- **Dubbele items**. Items uit de conceptverzameling die al zijn toegevoegd aan de revisieset in een vorige verzameling, worden niet toegevoegd. Zoals eerder uitgelegd, wordt het aantal dubbele items in de verzameling weergegeven in de sectie **Verzamelingsinhoud** op het **tabblad** Overzicht.

- **Opties voor verzamelingsconfiguratie**. Wanneer u een conceptverzameling verbindt aan een revisieset, moet u de optie gebruiken om gespreksthreads, cloudbijlagen en documentversies op te nemen. Alle items die aan de revisieset worden toegevoegd, worden niet opgenomen in de schattingen van de conceptverzameling. Ze worden alleen geïdentificeerd en verzameld wanneer u de verzameling begaat. Als u deze opties selecteert, wordt het aantal items dat aan de revisieset is toegevoegd waarschijnlijk groter. 

    Zo worden meerdere versies van SharePoint documenten niet opgenomen in de schatting voor de conceptverzameling. Maar als u de optie selecteert om alle documentversies op te nemen wanneer u de zoekresultaten exporteert, wordt het werkelijke aantal (en de totale grootte) van de items die aan de revisieset zijn toegevoegd, vergroot. 

    Zie Een conceptverzameling aan een revisieset verbinden voor meer [informatie over deze opties.](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery) 

Hier zijn andere redenen waarom de geschatte resultaten van een conceptverzameling kunnen verschillen van de werkelijke vastgelegde resultaten.

- **De manier waarop resultaten worden geschat voor conceptverzamelingen.** Een schatting van de zoekresultaten die door een conceptverzameling worden geretourneerd, is alleen dat, een schatting (en niet een werkelijke telling) van de items die voldoen aan de criteria voor de verzamelingsquery. Als u de schatting van e-mailitems wilt compileren, wordt een lijst met de bericht-ed's die voldoen aan de zoekcriteria, aangevraagd in de Exchange database. Maar wanneer u de verzameling aan een revisieset verbindt, wordt de verzameling opnieuw gebruikt en worden de werkelijke berichten opgehaald uit de Exchange database. Verschillen kunnen dus het gevolg zijn van de manier waarop het geschatte aantal items en het werkelijke aantal items worden bepaald.

- **Wijzigingen die plaatsvinden tussen het tijdstip waarop conceptverzamelingen worden** ge schat en gemaakt. Wanneer u een conceptverzameling verbindt aan een revisieset, wordt de zoekopdracht opnieuw gestart om de meest recente items in de zoekindex te verzamelen die voldoen aan de zoekcriteria. Het is mogelijk dat er extra items zijn gemaakt, verzonden of verwijderd die voldoen aan de zoekcriteria in de periode tussen de laatste keer dat de conceptverzameling is uitgevoerd en wanneer de conceptverzameling is vastgelegd in een revisieset. Het is ook mogelijk dat items die in de zoekindex stonden toen de resultaten van de conceptverzameling werden geschat, er niet meer zijn omdat ze uit een gegevensbron zijn verwijderd voordat de verzameling werd gemaakt. U kunt dit probleem onder andere beperken door een datumbereik voor een verzameling op te geven. Een andere manier is om inhoudslocaties in de wacht te zetten, zodat items behouden blijven en niet kunnen worden verwijderd.

- **Niet-geïndexeerde items**. Als de conceptverzameling alle Exchange-postvakken of alle SharePoint-sites bevat, worden alleen niet-geïndexeerde items van inhoudslocaties die items bevatten die voldoen aan de verzamelingscriteria, toegevoegd aan de revisieset. Met andere woorden: als er geen resultaten worden gevonden in een postvak of site, worden niet-geïndexeerde items in dat postvak of de site niet toegevoegd aan de revisieset. Niet-geïndexeerde items van alle inhoudslocaties (zelfs items die niet overeenkomen met de verzamelingsquery) worden echter opgenomen in de geschatte verzamelingsresultaten.

    Als de conceptverzameling ook specifieke inhoudslocaties bevat (wat betekent dat specifieke  postvakken of sites die zijn opgegeven op de pagina Extra locaties in de wizard conceptverzameling), worden niet-geïndexeerde items (die niet worden uitgesloten door de verzamelingscriteria) van de inhoudslocaties die in de zoekopdracht zijn opgegeven, geëxporteerd. In dit geval moeten het geschatte aantal niet-geïndexeerde items en het aantal niet-geïndexeerde items dat aan de revisieset worden toegevoegd, hetzelfde zijn.
