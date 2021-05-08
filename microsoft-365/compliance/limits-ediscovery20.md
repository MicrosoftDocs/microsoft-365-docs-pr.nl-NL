---
title: Limieten voor Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over de hoofdcaselimieten, indexeringslimieten en zoeklimieten die van kracht zijn voor de Advanced eDiscovery oplossing in Microsoft 365.
ms.openlocfilehash: 335e40c6918fc33acc12082546b98f28c319c814
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244574"
---
# <a name="limits-in-advanced-ediscovery"></a>Limieten in Advanced eDiscovery

In dit artikel worden de limieten in de Advanced eDiscovery in Microsoft 365.

## <a name="case-and-review-set-limits"></a>Limieten voor case- en revisiesets

De volgende tabel bevat de limieten voor zaken en revisiesets in Advanced eDiscovery.

| Beschrijving van limiet | Limiet |
|:-----|:-----|
|Totaal aantal documenten dat aan een zaak kan worden toegevoegd (voor alle revisiesets in een zaak).  <br/> |3 miljoen <br/> |
|Totale bestandsgrootte per laadset. Dit omvat het laden van niet-Office 365 in een revisieset.  <br/> |300 GB <br/> |
|De totale hoeveelheid gegevens die is geladen in alle revisiesets in de organisatie per dag.<br/> |2 TB <br/> |
|Maximum aantal laadsets per zaak.  <br/> |200 <br/> |
|Maximum aantal revisiesets per zaak.  <br/> |20 <br/> |
|Maximum aantal taggroepen per zaak.  <br/> |1000 <br/> |
|Maximum aantal tags per zaak.  <br/> |1000 <br/> |
|Maximum gelijktijdige taken in uw organisatie om inhoud toe te voegen aan een revisieset. Deze taken hebben de naam **Gegevens toevoegen aan een revisieset** en worden weergegeven op het tabblad Taken in een zaak. | 10 <sup>4</sup> |
|Maximum gelijktijdige taken om inhoud toe te voegen aan een revisieset per gebruiker. Deze taken hebben de naam **Gegevens toevoegen aan een revisieset** en worden weergegeven op het tabblad Taken in een zaak.  | 3 |
|||

## <a name="hold-limits"></a>Limieten in wacht houden

In de volgende tabel worden de limieten vermeld voor de limieten die zijn gekoppeld aan een Advanced eDiscovery geval.

| Beschrijving van limiet | Limiet |
|:-----|:-----|
|Maximum aantal postvakken in één case hold. Deze limiet omvat het gecombineerde totaal van gebruikerspostvakken en de postvakken die zijn gekoppeld aan Microsoft 365 Groepen, Microsoft Teams en Yammer Groepen. <br/> |1,000  <br/> |
|Maximum aantal sites in één geval. Deze limiet omvat het gecombineerde totaal OneDrive voor Bedrijven sites, SharePoint sites en de sites die zijn gekoppeld aan Microsoft 365 Groepen, Microsoft Teams en Yammer Groepen.  <br/> |100  <br/> |

## <a name="indexing-limits"></a>Indexeringslimieten

In de volgende tabel worden de indexeringslimieten in Advanced eDiscovery.

| Beschrijving van limiet | Limiet |
|:-----|:-----|
|Maximum aantal tekens dat uit één bestand wordt gehaald.  <br/> |10 miljoen<sup>1</sup> <br/> |
|Maximale grootte van één bestand.   <br/> |100 MB<sup>1</sup> <br/> |
|Maximale diepte van ingesloten items in een document.  <br/> |25<sup>1</sup> <br/> |
|Maximale grootte van bestanden die zijn verwerkt door OCR (Optical Character Recognition).  <br/> |24 MB<sup>1</sup> <br/> 
|Maximum aantal indexeringstaken per organisatie per dag. <br/> |10<sup>6</sup> <br/>|  
|||

## <a name="search-limits"></a>Zoeklimieten

De limieten die in deze sectie worden beschreven, zijn gerelateerd aan het gebruik van het zoekprogramma op **het** tabblad Zoekopdrachten om gegevens voor een zaak te verzamelen. Zie Gegevens verzamelen [voor een](collecting-data-for-ediscovery.md)zaak in Advanced eDiscovery.

| Beschrijving van limiet | Limiet |
|:-----|:-----|
|Het maximum aantal postvakken of sites dat in één zoekopdracht kan worden doorzocht. |Geen limiet|
|Het maximum aantal zoekopdrachten dat tegelijk kan worden uitgevoerd. |Geen limiet |
|Het maximum aantal zoekopdrachten dat één gebruiker tegelijk kan starten. |10 | 
|Maximum aantal tekens voor een zoekquery (inclusief operatoren en voorwaarden). |10.000 &nbsp; <sup>2</sup>|
|Maximum aantal tekens voor een zoekquery voor SharePoint en OneDrive voor Bedrijven sites (inclusief operatoren en voorwaarden). |10,000<br>4.000 met Jokertekens &nbsp; <sup>2</sup>|
|Minimum aantal alfatekens voor jokertekens voor voorvoegsel; bijvoorbeeld één **\* *_ of* \* _ set**.|3 |  
|Maximumvarianten die worden geretourneerd wanneer u een voorvoegsel-jokerteken gebruikt om te zoeken naar een exacte woordgroep of wanneer u een voorvoegsel-jokerteken en de operator **NEAR** Boolean gebruikt. |10.000 &nbsp; <sup>3</sup>|
|Maximum aantal items per gebruikerspostvak dat wordt weergegeven op de voorbeeldpagina voor zoekopdrachten. De nieuwste items worden weergegeven. |100|
|Maximum aantal items uit alle postvakken dat wordt weergegeven op de voorbeeldpagina voor zoekopdrachten.|1,000|
|Maximum aantal postvakken dat kan worden bekeken voor zoekresultaten.  Als er meer dan 1000 postvakken zijn die items bevatten die overeenkomen met de zoekquery, zijn alleen de bovenste 1000 postvakken met de meeste resultaten beschikbaar voor voorbeeld.|1,000|
|Maximum aantal items van SharePoint en OneDrive voor Bedrijven sites die worden weergegeven op de voorbeeldpagina voor zoekopdrachten. De nieuwste items worden weergegeven. |200|
|Maximum aantal SharePoint en OneDrive voor Bedrijven sites die kunnen worden bekeken voor zoekresultaten. Als er meer dan 200 sites zijn die items bevatten die overeenkomen met de zoekquery, zijn alleen de bovenste 200 sites met de meeste resultaten beschikbaar voor een voorbeeld.|200|
|Het maximum aantal items per postvak in een openbare map dat wordt weergegeven op de voorbeeldpagina voor zoekopdrachten. |100|
|Het maximum aantal items dat is gevonden in alle postvakitems in een openbare map die worden weergegeven op de voorbeeldpagina voor zoekopdrachten. |200|
|Maximum aantal postvakken in openbare mappen dat kan worden bekeken voor zoekresultaten. Als er meer dan 500 postvakken in openbare mappen zijn die items bevatten die overeenkomen met de zoekquery, zijn alleen de bovenste 500 postvakken met de meeste resultaten beschikbaar voor een voorbeeld.|500|
|||

## <a name="search-times"></a>Zoektijden

Microsoft verzamelt prestatiegegevens voor zoekopdrachten die worden uitgevoerd door alle organisaties. Hoewel de complexiteit van de zoekquery van invloed kan zijn op zoektijden, is het aantal gezochte postvakken de grootste factor die van invloed is op hoe lang zoekopdrachten duren. Hoewel Microsoft geen serviceovereenkomst voor zoektijden biedt, bevat de volgende tabel de gemiddelde zoektijden voor zoekopdrachten in verzamelingen op basis van het aantal postvakken dat in de zoekopdracht is opgenomen.
  
  | Aantal postvakken | Gemiddelde zoektijd |
  |:-----|:-----|
  |100  <br/> |30 seconden  <br/> |
  |1,000  <br/> |45 seconden  <br/> |
  |10,000  <br/> |4 minuten  <br/> |
  |25,000  <br/> |10 minuten  <br/> |
  |50,000  <br/> |20 minuten  <br/> |
  |100,000  <br/> |25 minuten  <br/> |
  |||

## <a name="viewer-limits"></a>Viewer-limieten

| Beschrijving van limiet | Limiet |
|:-----|:-----|
|Maximale grootte van Excel bestand dat kan worden bekeken in de native viewer.  <br/> |4 MB  <br/> |
|||

## <a name="export-limits---final-export-out-of-review-set"></a>Exportlimieten - Definitieve export uit revisieset

De limieten die in deze sectie worden beschreven, zijn gerelateerd aan het exporteren van documenten uit een revisieset.

| Beschrijving van limiet | Limiet |
|:-----|:-----|
|Maximale grootte van één export.|5 miljoen documenten of 500 GB, wat kleiner is|
|Maximum gelijktijdige export per revisieset. | 1 |
|||

## <a name="review-set-download-limits"></a>Downloadlimieten instellen controleren

| Beschrijving van limiet | Limiet |
|:-----|:-----|
|Totale bestandsgrootte of maximum aantal documenten dat is gedownload uit een revisieset.  <br/> |3 MB of 50 documenten <sup>5</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup> Een item dat één bestandslimiet overschrijdt, wordt weergegeven als een verwerkingsfout.
>
> <sup>2</sup> Bij het zoeken SharePoint en OneDrive voor Bedrijven locaties tellen de tekens in de URL's van de sites die worden gezocht mee voor deze limiet. Het totale aantal tekens bestaat uit:<br>
> - Alle tekens in de velden Gebruikers en Filters.
> - Alle zoekmachtigingenfilters die van toepassing zijn op de gebruiker.
> - De tekens van alle locatieeigenschappen in de zoekopdracht; Dit omvat ExchangeLocation,PublicFolderLocation,SharPointLocation,ExchangeLocationExclusion,PublicFolderLocationExclusion,SharePointLocationExclusion, OneDriveLocationExclusion.
>   Als u bijvoorbeeld alle SharePoint sites en OneDrive-accounts in de zoekopdracht oprekent, worden zes tekens geteld, omdat het woord 'ALLES' wordt weergegeven voor zowel het veld SharePointLocation als OneDriveLocation.
>
> <sup>3</sup> Voor niet-zinsquery's (een trefwoordwaarde die geen dubbele aanhalingstekens gebruikt) wordt een speciale voorvoegselindex gebruikt. Dit geeft aan dat een woord voorkomt in een document, maar niet op de plaats waar het in het document voorkomt. Als u een woordgroepsquery wilt uitvoeren (een trefwoordwaarde met dubbele aanhalingstekens), moeten we de positie in het document vergelijken voor de woorden in de woordgroep. Dit betekent dat we de voorvoegselindex niet kunnen gebruiken voor woordgroepquery's. In dit geval wordt de query intern uitgebreid met alle mogelijke woorden waar het voorvoegsel naar wordt uitgebreid. bijvoorbeeld: tijd **_ kan worden uitgebreid tot \* *_*"time OR timer OR times OR timex OR timex OR timeboxed OR ..."**. De limiet van 10.000 is het maximum aantal varianten waar het woord naar kan uitbreiden, niet het aantal documenten dat overeenkomt met de query. Er is geen bovengrens voor niet-woordgroepstermen.
>
> <sup>4</sup> Deze limiet wordt gedeeld met het exporteren van inhoud in andere eDiscovery-hulpprogramma's. Dit betekent dat gelijktijdige exporten in Inhoud zoeken en Core eDiscovery (en het toevoegen van inhoud aan revisiesets in Advanced eDiscovery) allemaal worden toegepast op deze limiet.
>
> <sup>5</sup> Deze limiet is van toepassing op het downloaden van geselecteerde documenten uit een revisieset. Het is niet van toepassing op het exporteren van documenten uit een revisieset. Zie Case data exporteren in Advanced eDiscovery voor meer informatie over het downloaden en [exporteren van documenten.](exporting-data-ediscover20.md)
>
> <sup>6</sup> Indexeringslimieten per organisatie per dag. Als tijdelijke oplossing kunt u meerdere beheerders  selecteren op het tabblad Gegevensbronnen in een zaak en vervolgens op **Index bijwerken** klikken om te voorkomen dat er voor elke bewaarder een afzonderlijke indexbaan wordt aangetrokken. 
