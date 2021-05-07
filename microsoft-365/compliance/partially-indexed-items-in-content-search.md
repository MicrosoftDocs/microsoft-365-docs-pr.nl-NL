---
title: Gedeeltelijk geïndexeerde items in Inhoud zoeken en andere eDiscovery-hulpprogramma's
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnindexedItemsLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: d1691de4-ca0d-446f-a0d0-373a4fc8487b
description: Meer informatie over niet-geïndexeerde items in Exchange en SharePoint die u kunt opnemen in een eDiscovery-zoekopdracht die u in het Microsoft 365 compliancecentrum.
ms.openlocfilehash: 40995aa403686caadd5e35b6fa9c6ca20ee017ee
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/24/2021
ms.locfileid: "52162718"
---
# <a name="partially-indexed-items-in-ediscovery"></a>Gedeeltelijk geïndexeerde items in eDiscovery

Een eDiscovery-zoekopdracht die u vanuit het Microsoft 365 compliancecentrum hebt uitgevoerd, bevat automatisch gedeeltelijk geïndexeerde items in de geschatte zoekresultaten wanneer u een zoekopdracht uit te voeren. Gedeeltelijk geïndexeerde items Exchange postvakitems en documenten op SharePoint en OneDrive voor Bedrijven sites die om een of andere reden niet volledig zijn geïndexeerd voor zoeken. In Exchange bevat een gedeeltelijk geïndexeerd item meestal een bestand (van een bestandstype dat niet kan worden geïndexeerd) dat is gekoppeld aan een e-mailbericht. Hier volgen enkele andere redenen waarom items niet kunnen worden geïndexeerd voor zoeken en worden geretourneerd als gedeeltelijk geïndexeerde items wanneer u een eDiscovery-zoekopdracht uit te voeren:
  
- Het bestandstype wordt niet herkend of niet ondersteund voor indexering.

- Berichten hebben een bijgevoegd bestand zonder een geldige handler, zoals afbeeldingsbestanden; Dit is de meest voorkomende oorzaak van gedeeltelijk geïndexeerde e-mailitems.

- Het bestandstype wordt ondersteund voor indexering, maar er is een indexeringsfout opgetreden voor een specifiek bestand.

- Te veel bestanden die zijn gekoppeld aan een e-mailbericht.

- Een bestand dat aan een e-mailbericht is gekoppeld, is te groot.

- Een bestand wordt versleuteld met niet-Microsoft-technologieën.

- Een bestand is beveiligd met een wachtwoord.

> [!NOTE]
> De meeste organisaties hebben minder dan 1% van de inhoud per volume en minder dan 12% per grootte die gedeeltelijk is geïndexeerd. De reden voor het verschil tussen volume en grootte is dat grotere bestanden een hogere kans hebben op het bevatten van inhoud die niet volledig kan worden geïndexeerd.
  
Voor juridische onderzoeken moet uw organisatie mogelijk gedeeltelijk geïndexeerde items controleren. U kunt ook opgeven of u gedeeltelijk geïndexeerde items wilt opnemen wanneer u zoekresultaten exporteert naar een lokale computer of wanneer u de resultaten voorbereidt op analyse met Advanced eDiscovery. Zie Gedeeltelijk geïndexeerde [items onderzoeken in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)voor meer informatie.
  
## <a name="file-types-not-indexed-for-search"></a>Bestandstypen die niet zijn geïndexeerd voor zoeken

Bepaalde typen bestanden, zoals Bitmap- of MP3-bestanden, bevatten geen inhoud die kan worden geïndexeerd. Hierdoor worden de zoekindexservers in Exchange en SharePoint niet volledig geïndexeerd voor dit type bestanden. Deze typen bestanden worden beschouwd als niet-ondersteunde bestandstypen. Er zijn ook bestandstypen waarvoor volledige tekstindexering is uitgeschakeld, standaard of door een beheerder. Niet-ondersteunde en uitgeschakelde bestandstypen worden gelabeld als niet-geïndexeerde items in inhoudszoekingen. Zoals eerder vermeld, kunnen gedeeltelijk geïndexeerde items worden opgenomen in de reeks zoekresultaten wanneer u een zoekopdracht uitvoert, de zoekresultaten exporteert naar een lokale computer of zoekresultaten voorbereidt voor Advanced eDiscovery.
  
Zie de volgende onderwerpen voor een lijst met ondersteunde en uitgeschakelde bestandsindelingen:
  
- **Exchange**  -  [Bestandsindelingen geïndexeerd door Exchange Zoeken](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- **Exchange**  -  [Get-SearchDocumentFormat](/powershell/module/exchange/get-searchdocumentformat)

- **SharePoint**  -  [Standaard verkende bestandsnaamextensies en geparseerde bestandstypen in SharePoint](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a>Berichten en documenten met gedeeltelijk geïndexeerde bestandstypen kunnen worden geretourneerd in zoekresultaten

Niet elk e-mailbericht met een gedeeltelijk geïndexeerde bestandsbijlage of elk gedeeltelijk geïndexeerd SharePoint document wordt automatisch geretourneerd als een gedeeltelijk geïndexeerd item. Dat komt omdat andere eigenschappen van berichten  of documenten, zoals de  eigenschap Onderwerp in e-mailberichten en de eigenschappen **Titel** of Auteur voor documenten, worden geïndexeerd en beschikbaar zijn om te worden doorzocht. Een trefwoordzoekactie naar 'financieel' retourneert bijvoorbeeld items met een gedeeltelijk geïndexeerde bestandsbijlage als dat trefwoord wordt weergegeven in het onderwerp van een e-mailbericht of in de bestandsnaam of titel van een document. Als het trefwoord echter alleen in de hoofdindeling van het bestand wordt weergegeven, wordt het bericht of document geretourneerd als een gedeeltelijk geïndexeerd item.
  
Op dezelfde manier worden berichten met gedeeltelijk geïndexeerde bestandsbijlagen en documenten van een gedeeltelijk geïndexeerd bestandstype opgenomen in de zoekresultaten wanneer andere bericht- of documenteigenschappen, die worden geïndexeerd en doorzoekbaar, voldoen aan de zoekcriteria. Berichteigenschappen die worden geïndexeerd voor zoeken, zijn verzonden en ontvangen datums, afzender en geadresseerde, de bestandsnaam van een bijlage en tekst in de hoofdtekst van het bericht. Documenteigenschappen die zijn geïndexeerd voor zoeken, bevatten gemaakte en gewijzigde datums. Hoewel een berichtbijlage een gedeeltelijk geïndexeerd item kan zijn, wordt het bericht opgenomen in de normale zoekresultaten als de waarde van andere bericht- of documenteigenschappen overeenkomt met de zoekcriteria.
  
Zie Keyword-query's en zoekvoorwaarden voor [eDiscovery](keyword-queries-and-search-conditions.md)voor een lijst met e-mail- en documenteigenschappen die u kunt zoeken met de functie Zoeken in het beveiligings- & compliancecentrum.
  
## <a name="partially-indexed-items-included-in-the-search-results"></a>Gedeeltelijk geïndexeerde items in de zoekresultaten

Mogelijk moet uw organisatie aanvullende analyses op gedeeltelijk geïndexeerde items identificeren en uitvoeren om te bepalen wat ze zijn, wat ze bevatten en of ze relevant zijn voor een specifiek onderzoek. Zoals eerder is uitgelegd, worden de gedeeltelijk geïndexeerde items in de inhoudslocaties die worden gezocht, automatisch opgenomen in de geschatte zoekresultaten. U kunt deze gedeeltelijk geïndexeerde items opnemen wanneer u zoekresultaten exporteert of de zoekresultaten voorbereidt voor Advanced eDiscovery.
  
Houd rekening met de volgende gegevens over gedeeltelijk geïndexeerde items:
  
- Wanneer u een eDiscovery-zoekopdracht uitvoert, worden het totale aantal en de grootte van gedeeltelijk geïndexeerde Exchange-items (geretourneerd door de zoekquery) weergegeven in de zoekstatistieken op de flyoutpagina en aangeduid als niet-geïndexeerde **items.** Statistieken over gedeeltelijk geïndexeerde items die op de flyoutpagina worden weergegeven, bevatten geen gedeeltelijk geïndexeerde items in SharePoint of OneDrive.

- Als de zoekopdracht waaruit u resultaten exporteert een zoekopdracht was naar specifieke inhoudslocaties of alle inhoudslocaties in uw organisatie, worden alleen de niet-geïndexeerde items van inhoudslocaties die items bevatten die voldoen aan de zoekcriteria, geëxporteerd. Met andere woorden: als er geen zoekresultaten worden gevonden in een postvak of site, worden niet-geïndexeerde items in dat postvak of de site niet geëxporteerd. De reden hiervoor is dat het exporteren van gedeeltelijk geïndexeerde items vanuit een groot aantal locaties in de organisatie de kans op exportfouten kan vergroten en de tijd kan vergroten om de zoekresultaten te exporteren en te downloaden.

    Als u gedeeltelijk geïndexeerde items wilt exporteren van alle inhoudslocaties voor een zoekopdracht, configureert u de zoekopdracht om alle items te retourneren (door trefwoorden uit de zoekquery te verwijderen) en vervolgens alleen gedeeltelijk geïndexeerde items te exporteren wanneer u de zoekresultaten exporteert (door te klikken op Alleen items met een niet-herkende **notatie,** worden versleuteld of zijn om andere redenen niet geïndexeerd onder Uitvoeropties). 

- Als u ervoor kiest om alle postvakitems in de zoekresultaten op te nemen, of als in een zoekquery geen trefwoorden worden opgegeven of alleen een datumbereik wordt opgegeven, worden gedeeltelijk geïndexeerde items mogelijk niet gekopieerd naar het PST-bestand dat de gedeeltelijk geïndexeerde items bevat. Dit komt omdat alle items, inclusief gedeeltelijk geïndexeerde items, automatisch worden opgenomen in de normale zoekresultaten.

- Gedeeltelijk geïndexeerde items kunnen niet worden bekeken. U moet de zoekresultaten exporteren om gedeeltelijk geïndexeerde items weer te geven die door de zoekopdracht zijn geretourneerd.

Wanneer u zoekresultaten exporteert en gedeeltelijk geïndexeerde items in de export opneemt, worden gedeeltelijk geïndexeerde items uit SharePoint-items geëxporteerd naar een map met de naam **Niet-bewerkbaar.** Wanneer u gedeeltelijk geïndexeerde Exchange-items exporteert, worden ze anders geëxporteerd, afhankelijk van of de gedeeltelijk geïndexeerde items overeenkomen met de zoekquery en de configuratie van de exportinstellingen. 

In de volgende tabel ziet u het exportgedrag van geïndexeerde en gedeeltelijk geïndexeerde items en of elke items zijn opgenomen voor de verschillende exportconfiguratie-instellingen.

|**Configuratie exporteren**|**Geïndexeerde items die overeenkomen met de zoekquery**|**Gedeeltelijk geïndexeerde items die overeenkomen met de zoekquery**|**Gedeeltelijk geïndexeerde items die niet overeenkomen met zoekquery**|
|:-----|:-----|:-----|:-----|
|Alleen geïndexeerde items exporteren  <br/> |Geëxporteerd<br/> |Geëxporteerd (inbegrepen bij de geïndexeerde items die worden geëxporteerd)<br/>  |Niet geëxporteerd <br/>|
|Alleen gedeeltelijk geïndexeerde items exporteren  <br/> |Niet geëxporteerd  <br/> |Geëxporteerd (als gedeeltelijk geïndexeerde items)<br/> |Geëxporteerd (als gedeeltelijk geïndexeerde items)|
|Geïndexeerde en gedeeltelijk geïndexeerde items exporteren  <br/> |Geëxporteerd<br/> |Geëxporteerd (inbegrepen bij de geïndexeerde items die worden geëxporteerd)<br/>  |Geëxporteerd (als gedeeltelijk geïndexeerde items)<br/>|
||||

## <a name="partially-indexed-items-excluded-from-the-search-results"></a>Gedeeltelijk geïndexeerde items die zijn uitgesloten van de zoekresultaten

Als een item gedeeltelijk is geïndexeerd, maar niet voldoet aan de zoekquerycriteria, wordt het item niet opgenomen als een gedeeltelijk geïndexeerd item in de zoekresultaten. Met andere woorden, het item is uitgesloten van de zoekresultaten. Als u ervoor kiest om gedeeltelijk geïndexeerde items op te nemen wanneer u de resultaten van een zoekopdracht exporteert, worden gedeeltelijk geïndexeerde items die zijn uitgesloten van de zoekresultaten, niet geëxporteerd.
  
Een uitzondering op deze regel is wanneer u een op query gebaseerde wachtpositie maakt die is gekoppeld aan een eDiscovery-zaak. Als u een op query gebaseerde eDiscovery-wachtstand maakt, worden alle gedeeltelijk geïndexeerde items in de wachtstand geplaatst. Dit geldt ook voor gedeeltelijk geïndexeerde items die niet overeenkomen met de zoekquerycriteria. Zie Een eDiscovery-hold maken voor meer informatie over het maken van op query's gebaseerde [eDiscovery-inhoud.](create-ediscovery-holds.md)
  
## <a name="indexing-limits-for-messages"></a>Indexeringslimieten voor berichten

In de volgende tabel worden de indexeringslimieten beschreven die ertoe kunnen leiden dat een e-mailbericht wordt geretourneerd als een gedeeltelijk geïndexeerd item in een eDiscovery-zoekopdracht in Microsoft 365.
  
Zie Zoeklimieten voor SharePoint Online voor een lijst met indexeringslimieten voor SharePoint [documenten.](/sharepoint/search-limits)
  
|**Indexeringslimiet**|**Maximumwaarde**|**Beschrijving**|
|:-----|:-----|:-----|
|Maximale bijlagegrootte (met uitzondering van Excel bestanden)  <br/> |150 MB  <br/> |De maximale grootte van een e-mailbijlage die wordt geparseerd voor indexering. Elke bijlage die groter is dan deze limiet, wordt niet geparseerd voor indexering en het bericht met de bijlage wordt gemarkeerd als gedeeltelijk geïndexeerd.  <br/><br/> **Opmerking:** Parseren is het proces waarbij de indexeringsservice tekst uit de bijlage haalt, overbodige tekens zoals interpunctie en spaties verwijdert en vervolgens de tekst opsplitst in woorden (in een proces dat tokenisatie wordt genoemd), die vervolgens in de index worden opgeslagen.           |
|Maximale grootte van Excel bestanden  <br/> |4 MB  <br/> |De maximale grootte van een Excel op een site of gekoppeld aan een e-mailbericht dat wordt geparseerd voor indexering. Elk Excel bestand dat groter is dan deze limiet, wordt niet geparseerd en het bestand of de e-mail die het bericht met de bestandsbijlage bevat, wordt gemarkeerd als niet-geïndexeerd.  <br/> |
|Maximum aantal bijlagen  <br/> |250  <br/> |Het maximum aantal bestanden dat is gekoppeld aan een e-mailbericht dat wordt geparseerd voor indexering. Als een bericht meer dan 250 bijlagen heeft, worden de eerste 250 bijlagen geparseerd en geïndexeerd en wordt het bericht gemarkeerd als gedeeltelijk geïndexeerd omdat het extra bijlagen had die niet zijn geparseerd.  <br/> |
|Maximale bijlagediepte  <br/> |30  <br/> |Het maximum aantal geneste bijlagen dat is geparseerd. Als er bijvoorbeeld een ander e-mailbericht aan een e-mailbericht is gekoppeld en het bijgevoegde bericht een Word-document bevat, worden het Word-document en het bijgevoegde bericht geïndexeerd. Dit gedrag blijft bestaan voor maximaal 30 geneste bijlagen.  <br/> |
|Maximum aantal bijgevoegde afbeeldingen  <br/> |0  <br/> |Een afbeelding die is gekoppeld aan een e-mailbericht, wordt overgeslagen door de parser en wordt niet geïndexeerd.  <br/> |
|Maximale tijd besteed aan het parseren van een item  <br/> |30 seconden  <br/> |Er wordt maximaal 30 seconden besteed aan het parseren van een item voor indexering. Als de parsatietijd langer is dan 30 seconden, wordt het item gemarkeerd als gedeeltelijk geïndexeerd.  <br/> |
|Maximale parseruitvoer  <br/> |2 miljoen tekens  <br/> |De maximale hoeveelheid tekstuitvoer van de parser die is geïndexeerd. Als de parser bijvoorbeeld 8 miljoen tekens uit een document haalt, worden alleen de eerste 2 miljoen tekens geïndexeerd.  <br/> |
|Maximumnotatietokens  <br/> |2 miljoen  <br/> |Wanneer een e-mailbericht wordt geïndexeerd, wordt elk woord geannoteerd met verschillende verwerkingsinstructies die aangeven hoe dat woord moet worden geïndexeerd. Elke set verwerkingsinstructies wordt een aantekeningen token genoemd. Als u de kwaliteit van de service in Office 365 wilt behouden, is er een limiet van 2 miljoen aantekeningentokens voor een e-mailbericht.  <br/> |
|Maximale lichaamsgrootte in index  <br/> |67 miljoen tekens  <br/> |Het totale aantal tekens in de hoofdbeslag van een e-mailbericht en alle bijlagen. Wanneer een e-mailbericht wordt geïndexeerd, wordt alle tekst in de hoofdtekst van het bericht en in alle bijlagen samenvoegd tot één tekenreeks. De maximale grootte van deze tekenreeks die wordt geïndexeerd, is 67 miljoen tekens.  <br/> |
|Maximale unieke tokens in de body  <br/> |1 miljoen  <br/> |Zoals eerder is uitgelegd, zijn tokens het resultaat van het extraheren van tekst uit inhoud, het verwijderen van interpunctie en spaties en het vervolgens verdelen in woorden (tokens genoemd) die zijn opgeslagen in de index. De woordgroep bevat  `"cat, mouse, bird, dog, dog"` bijvoorbeeld 5 tokens. Maar slechts 4 daarvan zijn unieke tokens. Er is een limiet van 1 miljoen unieke tokens per e-mailbericht, waardoor de index niet te groot wordt met willekeurige tokens.  <br/> |

## <a name="more-information-about-partially-indexed-items"></a>Meer informatie over gedeeltelijk geïndexeerde items

- Zoals eerder vermeld, omdat de eigenschappen van berichten en documenten en de metagegevens worden geïndexeerd, kan een trefwoordzoek resultaten opleveren als dat trefwoord wordt weergegeven in de geïndexeerde metagegevens. Hetzelfde trefwoord kan echter niet hetzelfde item retourneren als het trefwoord alleen wordt weergegeven in de inhoud van een item met een niet-ondersteund bestandstype. In dit geval wordt het item geretourneerd als een gedeeltelijk geïndexeerd item.

- Als een gedeeltelijk geïndexeerd item in de zoekresultaten wordt opgenomen omdat het voldoet aan de zoekquerycriteria (en niet is uitgesloten), wordt het niet opgenomen als een gedeeltelijk geïndexeerd item in de geschatte zoekstatistieken. Bovendien wordt deze niet opgenomen in gedeeltelijk geïndexeerde items wanneer u zoekresultaten exporteert.

- Hoewel een bestandstype wordt ondersteund voor indexering en geïndexeerd, kunnen er indexerings- of zoekfouten zijn die ervoor zorgen dat een bestand wordt geretourneerd als een gedeeltelijk geïndexeerd item. Het zoeken naar een zeer groot Excel bestand kan bijvoorbeeld gedeeltelijk succesvol zijn (omdat de eerste 4 MB worden geïndexeerd), maar mislukt omdat de bestandsgroottelimiet wordt overschreden. In dit geval is het mogelijk dat hetzelfde bestand wordt geretourneerd met de zoekresultaten en als een gedeeltelijk geïndexeerd item.

- Bestanden die zijn [](encryption.md) versleuteld met Microsoft-versleutelingstechnologieën en zijn gekoppeld aan een e-mailbericht dat voldoet aan de criteria van een zoekopdracht, kunnen worden bekeken en worden ontsleuteld wanneer ze worden geëxporteerd. Op dit moment worden bestanden die zijn versleuteld met Microsoft-versleutelingstechnologieën (en opgeslagen in SharePoint of OneDrive voor Bedrijven) gedeeltelijk geïndexeerd.

- E-mailberichten die zijn versleuteld met S/MIME, worden gedeeltelijk geïndexeerd. Dit geldt ook voor versleutelde berichten met of zonder bestandsbijlagen.

- E-mailberichten die Azure Rights Management worden geïndexeerd en worden opgenomen in de zoekresultaten als ze overeenkomen met de zoekquery. Met rechten beveiligde e-mailberichten worden ontsleuteld en kunnen worden bekeken en geëxporteerd. Voor deze functionaliteit moet u de rol RMS Decrypt toegewezen krijgen, die standaard is toegewezen aan de rollengroep eDiscover Manager.

## <a name="see-also"></a>Zie ook

[Gedeeltelijk geïndexeerde items in eDiscovery onderzoeken](investigating-partially-indexed-items-in-ediscovery.md)