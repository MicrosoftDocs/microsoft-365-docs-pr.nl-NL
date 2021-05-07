---
title: Limieten voor zoeken naar inhoud en Core eDiscovery in het compliancecentrum
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 78fe3147-1979-4c41-83bb-aeccf244368d
description: Meer informatie over de limieten die van kracht zijn voor de functie Inhoud zoeken in het Microsoft 365 compliancecentrum, zoals het maximum aantal gelijktijdige zoekopdrachten. Deze zoeklimieten zijn ook van toepassing op zoekopdrachten die zijn gekoppeld aan Core eDiscovery-zaken.
ms.openlocfilehash: 3ed7c97f633bc7e110ac5d4a84142abf612ec5b3
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162674"
---
# <a name="limits-for-content-search"></a>Limieten voor zoeken naar inhoud 
Er worden verschillende limieten toegepast op het zoekprogramma Inhoud in het Microsoft 365 compliancecentrum. Dit omvat zoekopdrachten  die worden uitgevoerd op de pagina Inhoud zoeken en zoekopdrachten die zijn gekoppeld aan een eDiscovery-zaak op de **pagina Core eDiscovery.** Deze limieten helpen bij het handhaven van de gezondheid en kwaliteit van services die aan organisaties worden geleverd. Er zijn ook limieten voor het indexeren van e-mailberichten in Exchange Online zoeken. U kunt de limieten voor Zoeken naar inhoud of e-mailindexering niet wijzigen, maar u moet hiervan op de hoogte zijn, zodat u rekening kunt houden met deze limieten bij het plannen, uitvoeren en oplossen van inhoudszoekingen.
  
## <a name="search-limits"></a>Zoeklimieten

In de volgende tabel worden de zoeklimieten vermeld wanneer u het zoekprogramma voor inhoud gebruikt in het Microsoft 365 compliancecentrum en naar zoekopdrachten die zijn gekoppeld aan een core eDiscovery-zaak.
  
| Beschrijving van limiet | Limiet |
|:-----|:-----|
|Het maximum aantal postvakken of sites dat in één zoekopdracht kan worden doorzocht  <br/> |Geen limiet <sup>1</sup> <br/> |
|Het maximum aantal zoekopdrachten dat tegelijk in uw organisatie kan worden uitgevoerd.  <br/> |30  <br/> |
|Het maximum aantal zoekopdrachten voor de hele organisatie dat tegelijk kan worden uitgevoerd. <br/> |3  <br/> |
|Het maximum aantal zoekopdrachten dat één gebruiker tegelijk kan starten. Deze limiet wordt waarschijnlijk bereikt wanneer de gebruiker meerdere zoekopdrachten probeert te starten met behulp van de opdracht **\| Start-ComplianceSearch get-ComplianceSearch** in Security & Compliance Center PowerShell.  <br/> |10  <br/> |
|Het maximum aantal items per postvak van de gebruiker dat wordt weergegeven op de voorbeeldpagina bij het bekijken van zoekresultaten voor inhoud.  <br/> |100  <br/> |
|Het maximum aantal items dat wordt gevonden in alle postvakken van gebruikers die worden weergegeven op de voorbeeldpagina bij het bekijken van zoekresultaten. De nieuwste items worden weergegeven.  <br/> |1,000  <br/> |
|Het maximum aantal gebruikerspostvakken dat kan worden bekeken voor zoekresultaten. Als er meer dan 1000 postvakken zijn die inhoud bevatten die overeenkomt met de zoekquery, zijn alleen de bovenste 1000 postvakken met de meeste zoekresultaten beschikbaar voor voorbeeld.  <br/> |1,000  <br/> |
|Het maximum aantal items dat wordt gevonden op SharePoint en OneDrive voor Bedrijven sites die worden weergegeven op de voorbeeldpagina bij het bekijken van zoekresultaten. De nieuwste items worden weergegeven.  <br/> |200  <br/> |
|Het maximum aantal sites (in SharePoint en OneDrive voor Bedrijven) dat kan worden bekeken voor zoekresultaten. Als er in totaal meer dan 200 sites zijn die inhoud bevatten die overeenkomt met de zoekquery, zijn alleen de 200 beste sites met de meeste zoekresultaten beschikbaar voor een voorbeeld.  <br/> |200  <br/> |
|Het maximum aantal items per postvak in een openbare map dat wordt weergegeven op de voorbeeldpagina bij het bekijken van de zoekresultaten van inhoud.  <br/> |100  <br/> |
|Het maximum aantal items dat wordt gevonden in alle postvakken in openbare mappen die worden weergegeven op de voorbeeldpagina bij het bekijken van de zoekresultaten van inhoud.  <br/> |200  <br/> |
|Het maximum aantal openbare postvakken dat kan worden bekeken voor zoekresultaten. Als er meer dan 500 postvakken in openbare mappen zijn die inhoud bevatten die overeenkomt met de zoekquery, zijn alleen de bovenste 500 postvakken voor openbare mappen met de meeste zoekresultaten beschikbaar voor een voorbeeld.  <br/> |500  <br/> |
|Het maximum aantal tekens voor de zoekquery (inclusief operatoren en voorwaarden) voor een zoekopdracht.  <br/><br/> **Opmerking:** Deze limiet wordt van kracht nadat de query is uitgebreid, wat betekent dat de query wordt uitgebreid met elk van de trefwoorden. Als een zoekquery bijvoorbeeld 15 trefwoorden en aanvullende parameters en voorwaarden heeft, wordt de query 15 keer uitgebreid, elk met de andere parameters en voorwaarden in de query. Dus hoewel het aantal tekens in de zoekquery mogelijk onder de limiet ligt, is het de uit uitgebreide query die kan bijdragen aan het overschrijden van deze limiet.  <br/> |**Postvakken:** 10.000  <br/> **Sites:** 4.000 bij het zoeken naar alle sites of 2.000 bij het zoeken naar maximaal 20 sites <sup>2</sup> <br/> |
|Het maximum aantal varianten dat wordt geretourneerd wanneer u een voorvoegsel-jokerteken gebruikt om te zoeken naar een exacte woordgroep in een zoekquery of wanneer u een voorvoegsel-jokerteken en de operator **NEAR** Boolean gebruikt.  <br/> |10.000 <sup>3</sup> <br/> |
|Het minimum aantal alfatekens voor jokertekens voor voorvoegsels; bijvoorbeeld ,  `time*`  `one*` of  `set*` .  <br/> |3  <br/> |
|Het maximum aantal postvakken in een zoekopdracht waarin u items kunt verwijderen door een actie 'zoeken en verwijderen' uit te voeren (met de opdracht **New-ComplianceSearchAction -Purge).** Als de zoekopdracht waar u een opsperactie voor doet, meer bronpostvakken heeft dan deze limiet, mislukt de actie voor het verwijderen. Zie E-mailberichten in uw organisatie zoeken en verwijderen voor meer informatie over zoeken [en verwijderen.](search-for-and-delete-messages-in-your-organization.md)  <br/> |50,000  <br/> |
|Het maximum aantal locaties in een zoekopdracht waaruit u items kunt exporteren. Als de zoekopdracht die u exporteert meer locaties heeft dan deze limiet, mislukt de export. Zie Zoekresultaten voor [inhoud exporteren voor meer informatie.](export-search-results.md)  <br/> |100,000  <br/> |
|||

> [!NOTE]
> <sup>1</sup> Hoewel u in één zoekopdracht een onbeperkt aantal postvakken kunt doorzoeken, kunt u de geëxporteerde zoekresultaten alleen downloaden uit maximaal 100.000 postvakken met behulp van het hulpprogramma voor eDiscovery-export in het Microsoft 365 compliancecentrum. <br/><br/> <sup>2</sup> Bij het zoeken SharePoint en OneDrive voor Bedrijven locaties worden de tekens in de URL's van de sites die worden gezocht, meegetelde met deze limiet. <br/><br/> <sup>3</sup> Voor niet-zinsquery's (een trefwoordwaarde die geen dubbele aanhalingstekens gebruikt) wordt een speciale voorvoegselindex gebruikt. Dit geeft aan dat een woord voorkomt in een document, maar niet op de plaats waar het in het document voorkomt. Als u een woordgroepsquery wilt uitvoeren (een trefwoordwaarde met dubbele aanhalingstekens), moeten we de positie in het document vergelijken voor de woorden in de woordgroep. Dit betekent dat we de voorvoegselindex niet kunnen gebruiken voor woordgroepquery's. In dit geval wordt de query intern uitgebreid met alle mogelijke woorden waar het voorvoegsel naar wordt uitgebreid. kan bijvoorbeeld  `"time*"` uitbreiden naar  `"time OR timer OR times OR timex OR timeboxed OR …"` . 10.000 is het maximum aantal varianten waar het woord naar kan uitbreiden, niet het aantal documenten dat overeenkomt met de query. Er is geen bovengrens voor niet-woordgroepstermen. 
  
## <a name="search-times"></a>Zoektijden
Microsoft verzamelt prestatiegegevens voor zoekopdrachten die worden uitgevoerd door alle organisaties. Hoewel de complexiteit van de zoekquery van invloed kan zijn op zoektijden, is het aantal gezochte postvakken de grootste factor die van invloed is op hoe lang zoekopdrachten duren. Hoewel Microsoft geen serviceovereenkomst voor zoektijden biedt, bevat de volgende tabel de gemiddelde zoektijden voor zoekopdrachten in verzamelingen op basis van het aantal postvakken dat in de zoekopdracht is opgenomen.

|Aantal postvakken|Gemiddelde zoektijd|
|:-----|:-----|
|100|30 seconden|
|1,000|45 seconden|
|10,000|4 minuten|
|25,000|10 minuten|
|50,000|20 minuten|
|100,000|25 minuten|
|||

## <a name="export-limits"></a>Exportlimieten
In de volgende tabel worden de limieten vermeld bij het exporteren van de resultaten van een inhoudszoekactie. Deze limieten zijn ook van toepassing wanneer u inhoud exporteert uit een hoofd-eDiscovery-zaak.

|Beschrijving van limiet|Limiet|
|:-----|:-----|
|Maximale hoeveelheid exporteerbare gegevens uit één zoekopdracht  <br/><br/> **Opmerking:** Als de zoekresultaten groter zijn dan 2 TB, kunt u datumbereiken of andere typen filters gebruiken om de totale grootte van de zoekresultaten te verminderen. <br/>  |2 TB  <br/> | 
|Maximum dat een organisatie in één dag kan exporteren <br/><br/> **Opmerking:** Deze limiet wordt dagelijks om 12:00 uur UTC opnieuw ingesteld <br/> |2 TB <br/> |
|Maximale gelijktijdige export die tegelijk binnen uw organisatie kan worden uitgevoerd <br/><br/> **Opmerking:** Het uitvoeren **van een rapport Alleen** export telt mee voor het totale aantal gelijktijdige exporten voor uw organisatie. Als drie gebruikers elk drie exporten uitvoeren, kan slechts één andere export worden uitgevoerd. Of het nu gaat om het exporteren van een rapport of zoekresultaten, er kunnen geen andere exporten worden uitgevoerd totdat een rapport is voltooid.   <br/> |10 <br/> |
|Maximale export van één gebruiker kan op elk moment worden uitgevoerd <br/> |3 <br/> |
|Maximum aantal postvakken voor zoekresultaten dat kan worden gedownload met behulp van het eDiscovery-exporthulpmiddel <br/>| 100,000 <br/>|
|Maximale grootte van PST-bestand dat kan worden geëxporteerd <br/><br/> **Opmerking:** Als de zoekresultaten uit het postvak van een gebruiker groter zijn dan 10 GB, worden de zoekresultaten voor het postvak geëxporteerd in twee (of meer) afzonderlijke PST-bestanden. Als u ervoor kiest om alle zoekresultaten in één PST-bestand te exporteren, wordt het PST-bestand overgeslagen naar extra PST-bestanden als de totale grootte van de zoekresultaten groter is dan 10 GB. Als u deze standaardgrootte wilt wijzigen, kunt u het register Windows bewerken op de computer die u gebruikt om de zoekresultaten te exporteren. Zie [De grootte van PST-bestanden wijzigen bij het exporteren van eDiscovery-zoekresultaten.](change-the-size-of-pst-files-when-exporting-results.md) De zoekresultaten van een specifiek postvak worden niet verdeeld over meerdere PST-bestanden, tenzij de inhoud uit één postvak meer dan 10 GB is. Als u ervoor kiest om de zoekresultaten te exporteren in één PST-bestand dat alle berichten in één map bevat en de zoekresultaten groter zijn dan 10 GB, worden de items nog steeds in chronologische volgorde ingedeeld, zodat ze worden overgeslagen in extra PST-bestanden op basis van de verzonden datum.<br/> | 10 GB <br/> |
|De snelheid waarmee zoekresultaten van postvakken en sites worden geüpload naar een door Microsoft verstrekte Azure Storage locatie. |Maximum van 2 GB per uur|
|||

## <a name="indexing-limits-for-email-messages"></a>Indexeringslimieten voor e-mailberichten

In de volgende tabel worden de indexeringslimieten beschreven die ertoe kunnen leiden dat een e-mailbericht wordt geretourneerd als een niet-geïndexeerd item of een gedeeltelijk geïndexeerd item in de resultaten van een inhoudszoekactie.
  
| Indexeringslimiet | Maximumwaarde | Beschrijving |
|:-----|:-----|:-----|
|Maximale bijlagegrootte|150 MB  <br/> |De maximale grootte van een e-mailbijlage die wordt geparseerd voor indexering. Elke bijlage die groter is dan deze limiet, wordt niet geparseerd voor indexering en het bericht met de bijlage wordt gemarkeerd als gedeeltelijk geïndexeerd.  <br/> <br/>**Opmerking:** Parseren is het proces waarbij de indexeringsservice tekst uit de bijlage haalt, overbodige tekens zoals interpunctie en spaties verwijdert en vervolgens de tekst opsplitst in woorden (in een proces dat tokenisatie wordt genoemd), die vervolgens in de index worden opgeslagen.           |
|Maximum aantal bijlagen  <br/> |250  <br/> |Het maximum aantal bestanden dat is gekoppeld aan een e-mailbericht dat wordt geparseerd voor indexering. Als een bericht meer dan 250 bijlagen heeft, worden de eerste 250 bijlagen geparseerd en geïndexeerd en wordt het bericht gemarkeerd als gedeeltelijk geïndexeerd omdat het extra bijlagen had die niet zijn geparseerd.  <br/> |
|Maximale bijlagediepte  <br/> |30  <br/> |Het maximum aantal geneste bijlagen dat is geparseerd. Als er bijvoorbeeld een ander e-mailbericht aan een e-mailbericht is gekoppeld en het bijgevoegde bericht een Word-document bevat, worden het Word-document en het bijgevoegde bericht geïndexeerd. Dit gedrag blijft bestaan voor maximaal 30 geneste bijlagen.  <br/> |
|Maximum aantal bijgevoegde afbeeldingen  <br/> |0  <br/> |Een afbeelding die is gekoppeld aan een e-mailbericht, wordt overgeslagen door de parser en wordt niet geïndexeerd.  <br/> |
|Maximale tijd besteed aan het parseren van een item  <br/> |30 seconden  <br/> |Er wordt maximaal 30 seconden besteed aan het parseren van een item voor indexering. Als de parsatietijd langer is dan 30 seconden, wordt het item gemarkeerd als gedeeltelijk geïndexeerd.  <br/> |
|Maximale parseruitvoer  <br/> |2 miljoen tekens  <br/> |De maximale hoeveelheid tekstuitvoer van de parser die is geïndexeerd. Als de parser bijvoorbeeld 8 miljoen tekens uit een document haalt, worden alleen de eerste 2 miljoen tekens geïndexeerd.  <br/> |
|Maximumnotatietokens  <br/> |2 miljoen  <br/> |Wanneer een e-mailbericht wordt geïndexeerd, wordt elk woord geannoteerd met verschillende verwerkingsinstructies die aangeven hoe dat woord moet worden geïndexeerd. Elke set verwerkingsinstructies wordt een aantekeningen token genoemd. Als u de kwaliteit van de service in Office 365 wilt behouden, is er een limiet van 2 miljoen aantekeningentokens voor een e-mailbericht.  <br/> |
|Maximale lichaamsgrootte in index  <br/> |67 miljoen tekens  <br/> |Het totale aantal tekens in de hoofdbeslag van een e-mailbericht en alle bijlagen. Wanneer een e-mailbericht wordt geïndexeerd, wordt alle tekst in de hoofdtekst van het bericht en in alle bijlagen samenvoegd tot één tekenreeks. De maximale grootte van deze tekenreeks die wordt geïndexeerd, is 67 miljoen tekens.  <br/> |
|Maximale unieke tokens in de body  <br/> |1 miljoen  <br/> |Zoals eerder is uitgelegd, zijn tokens het resultaat van het extraheren van tekst uit inhoud, het verwijderen van interpunctie en spaties en het vervolgens verdelen in woorden (tokens genoemd) die zijn opgeslagen in de index. De woordgroep bevat  `"cat, mouse, bird, dog, dog"` bijvoorbeeld 5 tokens. Maar slechts 4 daarvan zijn unieke tokens. Er is een limiet van 1 miljoen unieke tokens per e-mailbericht, waardoor de index niet te groot wordt met willekeurige tokens.  <br/> |
|||
  
## <a name="more-information"></a>Meer informatie

Er zijn extra limieten met betrekking tot verschillende aspecten van het zoeken naar inhoud, zoals inhoudsindexering. Zie de volgende onderwerpen voor meer informatie over deze limieten:

- [Gedeeltelijk geïndexeerde items in Inhoud zoeken](partially-indexed-items-in-content-search.md)

- [Gedeeltelijk geïndexeerde items in eDiscovery onderzoeken](investigating-partially-indexed-items-in-ediscovery.md)

- [Zoeklimieten voor SharePoint Online](/sharepoint/search-limits)

Zie voor meer informatie over inhoudszoekingen:
  
- [Zoeken naar inhoud in Microsoft 365](content-search.md)

- [Zoeken naar inhoud in een hoofd-eDiscovery-zaak](search-for-content-in-core-ediscovery.md)

- [Trefwoordquery's en zoekvoorwaarden voor zoeken naar inhoud](keyword-queries-and-search-conditions.md)

Zie voor caselimieten met betrekking tot Core eDiscovery en Advanced eDiscovery:

- [Limieten in Core eDiscovery](limits-core-ediscovery.md)

- [Limieten in Advanced eDiscovery](limits-ediscovery20.md)
